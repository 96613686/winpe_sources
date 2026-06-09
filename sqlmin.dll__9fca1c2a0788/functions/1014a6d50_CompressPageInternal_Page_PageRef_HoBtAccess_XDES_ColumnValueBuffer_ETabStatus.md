# CompressPageInternal(Page *,PageRef *,HoBtAccess *,XDES *,ColumnValueBuffer *,ETabStatus)

- ea: `0x1014a6d50`
- end: `0x1014aa3e8`
- name: `?CompressPageInternal@@YA?AW4PageCompressionRetCode@@PEAVPage@@PEAVPageRef@@PEAVHoBtAccess@@PEAVXDES@@PEAVColumnValueBuffer@@W4ETabStatus@@@Z`
- size: `13976`
- prototype: ``
- caller_count: `5`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x101311db0`
- `0x101331b90`
- `0x1018eeca0`
- `0x101938670`
- `0x1019530a0`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x100415e90`
- `0x10042d750`
- `0x100441e00`
- `0x100441e40`
- `0x100445e80`
- `0x100455720`
- `0x10046bf90`
- `0x1004729d0`
- `0x10047bc10`
- `0x100480030`
- `0x10058cca0`
- `0x1012c5b30`
- `0x1012c9010`
- `0x1014a6d50`
- `0x1014ae6e0`
- `0x1014af220`
- `0x1014af490`
- `0x10168b160`
- `0x1018becd0`
- `0x10190d670`
- `0x10190e220`
- `0x101d0fad0`
- `0x101d97510`
- `0x1021d5c70`
- `0x1021d8a90`
- `0x1021e8a60`
- `0x1021eab40`
- `0x1021ed230`

## import_xrefs

- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x1014a8d50`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x1014a8cfa`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014a8ed9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014a8f63`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014a8ed9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1014a8f63`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7097`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7891`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7923`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7b4a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7d26`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7d56`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7e2d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7f03`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a81e9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a82b4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a87eb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a8866`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a93e1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a946c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a9682`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a97ac`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a9892`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a996d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a9a4f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a9d3f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a9e04`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7097`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7891`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7923`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7b4a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7d26`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7d56`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7e2d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a7f03`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a81e9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a82b4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a87eb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a8866`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a93e1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a946c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a9682`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a97ac`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a9892`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a996d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a9a4f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a9d3f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1014a9e04`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a7ce6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a7e09`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a7edf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a81c5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a8290`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a986e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a9949`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a9a2b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a9d1b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a9de0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a7ce6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a7e09`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a7edf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a81c5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a8290`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a986e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a9949`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a9a2b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a9d1b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1014a9de0`
- `sqldk!SystemThread_TlsIndex` at `0x1014a7c85`
- `sqldk!SystemThread_TlsIndex` at `0x1014a7db4`
- `sqldk!SystemThread_TlsIndex` at `0x1014a7e8a`
- `sqldk!SystemThread_TlsIndex` at `0x1014a8170`
- `sqldk!SystemThread_TlsIndex` at `0x1014a823b`
- `sqldk!SystemThread_TlsIndex` at `0x1014a8d7d`
- `sqldk!SystemThread_TlsIndex` at `0x1014a8e64`
- `sqldk!SystemThread_TlsIndex` at `0x1014a9819`
- `sqldk!SystemThread_TlsIndex` at `0x1014a98f4`
- `sqldk!SystemThread_TlsIndex` at `0x1014a99d6`
- `sqldk!SystemThread_TlsIndex` at `0x1014a9cc6`
- `sqldk!SystemThread_TlsIndex` at `0x1014a9d8b`
- `sqldk!SystemThread_TlsOffset` at `0x1014a7c8e`
- `sqldk!SystemThread_TlsOffset` at `0x1014a7dbd`
- `sqldk!SystemThread_TlsOffset` at `0x1014a7e93`
- `sqldk!SystemThread_TlsOffset` at `0x1014a8179`
- `sqldk!SystemThread_TlsOffset` at `0x1014a8244`
- `sqldk!SystemThread_TlsOffset` at `0x1014a8d86`
- `sqldk!SystemThread_TlsOffset` at `0x1014a8e6d`
- `sqldk!SystemThread_TlsOffset` at `0x1014a9822`
- `sqldk!SystemThread_TlsOffset` at `0x1014a98fd`
- `sqldk!SystemThread_TlsOffset` at `0x1014a99df`
- `sqldk!SystemThread_TlsOffset` at `0x1014a9ccf`
- `sqldk!SystemThread_TlsOffset` at `0x1014a9d94`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014a8da1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014a8e88`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014a8da1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1014a8e88`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014a8f23`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014aa16d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014aa17a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014aa192`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014aa19f`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014a8f23`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014aa16d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014aa17a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014aa192`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014aa19f`

## string_xrefs

- `0x1014a8ec8`: `Sql\Ntdbms\storeng\dfs\access\PageCompression.cpp`
- `0x1014a8f52`: `Sql\Ntdbms\storeng\dfs\access\PageCompression.cpp`
- `0x1014a7086`: `PageCompression.cpp`
- `0x1014a708d`: `isPageCompressed`

## pseudocode

```c

```
