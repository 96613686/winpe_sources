# Page::ModifyRowAndReplaceVersionInfo(int,uint,uint,uint,void const *,uint,ushort,XdesId const *,RecVersioningInfo const *)

- ea: `0x1018b7050`
- end: `0x1018b90c4`
- name: `?ModifyRowAndReplaceVersionInfo@Page@@QEAAXHIIIPEBXIGPEBVXdesId@@PEBVRecVersioningInfo@@@Z`
- size: `8308`
- prototype: `void __fastcall(Page *__hidden this, int, unsigned int, unsigned int, unsigned int, const void *, unsigned int, unsigned __int16, const struct XdesId *, const struct RecVersioningInfo *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x100445640`
- `0x1018f4830`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x100402000`
- `0x1004025c0`
- `0x100415e90`
- `0x10043e110`
- `0x100441e00`
- `0x1004729d0`
- `0x100480030`
- `0x100480b60`
- `0x10049a6f0`
- `0x10049a760`
- `0x1012c5d10`
- `0x1012c9010`
- `0x1018b7050`
- `0x1021d8a90`
- `0x1021e89d0`
- `0x1021eab40`

## import_xrefs

- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b73c0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b744e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b763a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b76e1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7807`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b78d9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b79a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7c29`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7ce9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7d7b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7daa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7ddc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7ec4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b80df`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b81bd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b837e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8452`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8524`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b87c3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8883`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b89d9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8aaa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8b7a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8e01`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8ebf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b73c0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b744e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b763a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b76e1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7807`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b78d9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b79a9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7c29`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7ce9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7d7b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7daa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7ddc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b7ec4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b80df`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b81bd`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b837e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8452`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8524`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b87c3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8883`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b89d9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8aaa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8b7a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8e01`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b8ebf`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b77e4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b78b6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b7984`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b7c03`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b7cc3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b835a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b842e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b8500`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b879f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b885f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b89b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b8a86`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b8b56`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b8ddd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b8e9b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b77e4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b78b6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b7984`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b7c03`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b7cc3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b835a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b842e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b8500`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b879f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b885f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b89b5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b8a86`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b8b56`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b8ddd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b8e9b`
- `sqldk!SystemThread_TlsIndex` at `0x1018b778e`
- `sqldk!SystemThread_TlsIndex` at `0x1018b7860`
- `sqldk!SystemThread_TlsIndex` at `0x1018b792e`
- `sqldk!SystemThread_TlsIndex` at `0x1018b7bad`
- `sqldk!SystemThread_TlsIndex` at `0x1018b7c6d`
- `sqldk!SystemThread_TlsIndex` at `0x1018b8304`
- `sqldk!SystemThread_TlsIndex` at `0x1018b83d8`
- `sqldk!SystemThread_TlsIndex` at `0x1018b84aa`
- `sqldk!SystemThread_TlsIndex` at `0x1018b8749`
- `sqldk!SystemThread_TlsIndex` at `0x1018b8809`
- `sqldk!SystemThread_TlsIndex` at `0x1018b895f`
- `sqldk!SystemThread_TlsIndex` at `0x1018b8a30`
- `sqldk!SystemThread_TlsIndex` at `0x1018b8b00`
- `sqldk!SystemThread_TlsIndex` at `0x1018b8d87`
- `sqldk!SystemThread_TlsIndex` at `0x1018b8e45`
- `sqldk!SystemThread_TlsOffset` at `0x1018b7797`
- `sqldk!SystemThread_TlsOffset` at `0x1018b7869`
- `sqldk!SystemThread_TlsOffset` at `0x1018b7937`
- `sqldk!SystemThread_TlsOffset` at `0x1018b7bb6`
- `sqldk!SystemThread_TlsOffset` at `0x1018b7c76`
- `sqldk!SystemThread_TlsOffset` at `0x1018b830d`
- `sqldk!SystemThread_TlsOffset` at `0x1018b83e1`
- `sqldk!SystemThread_TlsOffset` at `0x1018b84b3`
- `sqldk!SystemThread_TlsOffset` at `0x1018b8752`
- `sqldk!SystemThread_TlsOffset` at `0x1018b8812`
- `sqldk!SystemThread_TlsOffset` at `0x1018b8968`
- `sqldk!SystemThread_TlsOffset` at `0x1018b8a39`
- `sqldk!SystemThread_TlsOffset` at `0x1018b8b09`
- `sqldk!SystemThread_TlsOffset` at `0x1018b8d90`
- `sqldk!SystemThread_TlsOffset` at `0x1018b8e4e`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1018b7e25`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1018b7e3c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1018b7e25`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1018b7e3c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1018b7e48`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1018b7e48`

## pseudocode

```c

```
