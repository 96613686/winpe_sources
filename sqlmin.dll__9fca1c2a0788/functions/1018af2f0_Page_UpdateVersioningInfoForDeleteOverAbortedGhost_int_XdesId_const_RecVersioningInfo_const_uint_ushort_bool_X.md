# Page::UpdateVersioningInfoForDeleteOverAbortedGhost(int,XdesId const &,RecVersioningInfo const *,uint,ushort,bool,XdesId const *)

- ea: `0x1018af2f0`
- end: `0x1018b11fc`
- name: `?UpdateVersioningInfoForDeleteOverAbortedGhost@Page@@QEAAXHAEBVXdesId@@PEBVRecVersioningInfo@@IG_NPEBV2@@Z`
- size: `7948`
- prototype: `void __fastcall(Page *__hidden this, int, const struct XdesId *, const struct RecVersioningInfo *, unsigned int, unsigned __int16, bool, const struct XdesId *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1004410c0`
- `0x1018f4830`

## callees

- `0x100401490`
- `0x100402000`
- `0x100415e90`
- `0x10043e110`
- `0x100441e00`
- `0x10046bf90`
- `0x1004729d0`
- `0x100480030`
- `0x100480b60`
- `0x10049dc80`
- `0x1012c9010`
- `0x1018af2f0`
- `0x1021d8a90`
- `0x1021e8b50`
- `0x1021eab40`
- `0x1021ed230`

## import_xrefs

- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018af3f8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018af712`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018af7ab`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018af99d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018afa69`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018afa9c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018afb15`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018afc24`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018afcef`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018afdcb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b001d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b00f0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b024e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0318`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b03e1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0648`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0708`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b08f7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0970`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0abb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0b8f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0c62`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0f16`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0fd5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b1077`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018af3f8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018af712`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018af7ab`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018af99d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018afa69`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018afa9c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018afb15`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018afc24`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018afcef`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018afdcb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b001d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b00f0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b024e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0318`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b03e1`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0648`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0708`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b08f7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0970`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0abb`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0b8f`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0c62`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0f16`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b0fd5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b1077`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018afc00`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018afccb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018afd8e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018afff7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b00b3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0228`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b02f2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b03bb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0622`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b06e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0a98`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0b6c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0c3f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0ef3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0fb2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018afc00`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018afccb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018afd8e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018afff7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b00b3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0228`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b02f2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b03bb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0622`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b06e2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0a98`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0b6c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0c3f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0ef3`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b0fb2`
- `sqldk!SystemThread_TlsIndex` at `0x1018afbaa`
- `sqldk!SystemThread_TlsIndex` at `0x1018afc75`
- `sqldk!SystemThread_TlsIndex` at `0x1018afd38`
- `sqldk!SystemThread_TlsIndex` at `0x1018affa1`
- `sqldk!SystemThread_TlsIndex` at `0x1018b005d`
- `sqldk!SystemThread_TlsIndex` at `0x1018b01d2`
- `sqldk!SystemThread_TlsIndex` at `0x1018b029c`
- `sqldk!SystemThread_TlsIndex` at `0x1018b0365`
- `sqldk!SystemThread_TlsIndex` at `0x1018b05cc`
- `sqldk!SystemThread_TlsIndex` at `0x1018b068c`
- `sqldk!SystemThread_TlsIndex` at `0x1018b0a42`
- `sqldk!SystemThread_TlsIndex` at `0x1018b0b16`
- `sqldk!SystemThread_TlsIndex` at `0x1018b0be9`
- `sqldk!SystemThread_TlsIndex` at `0x1018b0e9d`
- `sqldk!SystemThread_TlsIndex` at `0x1018b0f5c`
- `sqldk!SystemThread_TlsOffset` at `0x1018afbb3`
- `sqldk!SystemThread_TlsOffset` at `0x1018afc7e`
- `sqldk!SystemThread_TlsOffset` at `0x1018afd41`
- `sqldk!SystemThread_TlsOffset` at `0x1018affaa`
- `sqldk!SystemThread_TlsOffset` at `0x1018b0066`
- `sqldk!SystemThread_TlsOffset` at `0x1018b01db`
- `sqldk!SystemThread_TlsOffset` at `0x1018b02a5`
- `sqldk!SystemThread_TlsOffset` at `0x1018b036e`
- `sqldk!SystemThread_TlsOffset` at `0x1018b05d5`
- `sqldk!SystemThread_TlsOffset` at `0x1018b0695`
- `sqldk!SystemThread_TlsOffset` at `0x1018b0a4b`
- `sqldk!SystemThread_TlsOffset` at `0x1018b0b1f`
- `sqldk!SystemThread_TlsOffset` at `0x1018b0bf2`
- `sqldk!SystemThread_TlsOffset` at `0x1018b0ea6`
- `sqldk!SystemThread_TlsOffset` at `0x1018b0f65`

## string_xrefs

- `0x1018af3f1`: `IsValidSlot(sid)`

## pseudocode

```c

```
