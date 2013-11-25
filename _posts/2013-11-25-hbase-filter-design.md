---
layout: post
title: "HBase filter design"
description: "HBase filter 设计与实现"
category: "HBase"
tags: [HBase]
---
{% include JB/setup %}

## HBase支持的过滤器 

#### Filter api

!['filter-api'](/images/2013/11/hbase-filter/filter-api.png)


FilterBase
	
	public abstract class FilterBase implements Filter {

	}

#### HBase Filter

!['filter-api'](/images/2013/11/hbase-filter/filters.png)




FilterList 

####过滤条件####

	a > 5 && (b > 5 || c > 5)

	a > 5 || (b > 5 && c > 5) || (d > 10 && d < 15)

####Filter FilterList####

	每个条件定义为一个Filter，如a>5
	多个条件定义为一个FilterList，如 a>5 && b>5
	FilterList里面的Fliter的关系，只能是and或or

####HBase FilterList####

Operator定义FilterList里Filter的关系，只能是and或or

FilterList跟其他的Filter一样，也都实现了Filter接口

!['filter-list'](/images/2013/11/hbase-filter/filter-list.png)




####SingleColumnValueFilter 实现



	
	public SingleColumnValueFilter(final byte [] family, final byte [] qualifier,
	      final CompareOp compareOp, final WritableByteArrayComparable comparator) {
	    this.columnFamily = family;
	    this.columnQualifier = qualifier;
	    this.compareOp = compareOp;
	    this.comparator = comparator;
	}

通过WritableByteArrayComparable接口，实现不同的Comparator，实现不同的过滤功能,如字符串比较，正则表达式匹配等

WritableByteArrayComparable接口

!['filter-api'](/images/2013/11/hbase-filter/comparator.png)

WritableByteArrayComparable

	public abstract class WritableByteArrayComparable implements Writable, Comparable<byte[]> {
		public abstract int compareTo(byte [] value, int offset, int length);
	}

SubstringComparator


	public class SubstringComparator extends WritableByteArrayComparable {
		@Override
		public int compareTo(byte[] value, int offset, int length) {
		return Bytes.toString(value, offset, length).toLowerCase().contains(substr) ? 0
		    : 1;
		}
	}



## 相关资料

[HBase过滤器 ](http://blog.sina.com.cn/s/blog_8026da3a0101e9fo.html)







