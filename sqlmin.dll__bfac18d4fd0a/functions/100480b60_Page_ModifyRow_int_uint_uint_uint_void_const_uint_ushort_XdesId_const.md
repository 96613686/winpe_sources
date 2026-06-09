# Page::ModifyRow(int,uint,uint,uint,void const *,uint,ushort,XdesId const *)

- ea: `0x100480b60`
- end: `0x100480e5f`
- name: `?ModifyRow@Page@@QEAAXHIIIPEBXIGPEBVXdesId@@@Z`
- size: `767`
- prototype: `void __fastcall(Page *__hidden this, int, unsigned int, unsigned int, rsize_t SourceSize, const void *Source, unsigned int, unsigned __int16, const struct XdesId *)`
- caller_count: `11`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x100445640`
- `0x1004839e0`
- `0x10048b650`
- `0x10056b280`
- `0x100604ea0`
- `0x1018af2f0`
- `0x1018b1210`
- `0x1018b7050`
- `0x1018e32f0`
- `0x1018e5b90`
- `0x1018f4830`

## callees

- `0x1004025c0`
- `0x100415e90`
- `0x100441e00`
- `0x100441e40`
- `0x100480b60`
- `0x10048c200`
- `0x1004a08c0`
- `0x1005ac690`
- `0x1006058b0`
- `0x1021d8a90`
- `0x1021e8a60`
- `0x1021e8ae0`
- `0x1021eab40`

## import_xrefs

- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5696`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b581b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5877`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5935`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b59f0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5ab4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5c2e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5cec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5eb9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5f00`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5fc0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6082`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6144`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b635d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6415`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6970`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b699b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b69c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6a9c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6ac7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6b77`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6be6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6c0e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6c37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6cad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6cd6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6cff`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6ecc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6f1a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5696`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b581b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5877`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5935`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b59f0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5ab4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5c2e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5cec`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5eb9`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5f00`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b5fc0`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6082`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6144`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b635d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6415`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6970`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b699b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b69c6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6a9c`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6ac7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6b77`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6be6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6c0e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6c37`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6cad`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6cd6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6cff`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6ecc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1018b6f1a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b58f2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b59af`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b5a6b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b5beb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b5ca9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b5f7e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b603b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b60fd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b6320`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b63d8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b6539`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b65f0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b66a5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b6891`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b6933`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b58f2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b59af`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b5a6b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b5beb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b5ca9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b5f7e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b603b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b60fd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b6320`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b63d8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b6539`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b65f0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b66a5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b6891`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1018b6933`
- `sqldk!SystemThread_TlsIndex` at `0x1018b589c`
- `sqldk!SystemThread_TlsIndex` at `0x1018b5959`
- `sqldk!SystemThread_TlsIndex` at `0x1018b5a15`
- `sqldk!SystemThread_TlsIndex` at `0x1018b5b95`
- `sqldk!SystemThread_TlsIndex` at `0x1018b5c53`
- `sqldk!SystemThread_TlsIndex` at `0x1018b5f28`
- `sqldk!SystemThread_TlsIndex` at `0x1018b5fe5`
- `sqldk!SystemThread_TlsIndex` at `0x1018b60a7`
- `sqldk!SystemThread_TlsIndex` at `0x1018b62ca`
- `sqldk!SystemThread_TlsIndex` at `0x1018b6382`
- `sqldk!SystemThread_TlsIndex` at `0x1018b64db`
- `sqldk!SystemThread_TlsIndex` at `0x1018b6592`
- `sqldk!SystemThread_TlsIndex` at `0x1018b6647`
- `sqldk!SystemThread_TlsIndex` at `0x1018b6833`
- `sqldk!SystemThread_TlsIndex` at `0x1018b68d5`
- `sqldk!SystemThread_TlsOffset` at `0x1018b58a5`
- `sqldk!SystemThread_TlsOffset` at `0x1018b5962`
- `sqldk!SystemThread_TlsOffset` at `0x1018b5a1e`
- `sqldk!SystemThread_TlsOffset` at `0x1018b5b9e`
- `sqldk!SystemThread_TlsOffset` at `0x1018b5c5c`
- `sqldk!SystemThread_TlsOffset` at `0x1018b5f31`
- `sqldk!SystemThread_TlsOffset` at `0x1018b5fee`
- `sqldk!SystemThread_TlsOffset` at `0x1018b60b0`
- `sqldk!SystemThread_TlsOffset` at `0x1018b62d3`
- `sqldk!SystemThread_TlsOffset` at `0x1018b638b`
- `sqldk!SystemThread_TlsOffset` at `0x1018b64e4`
- `sqldk!SystemThread_TlsOffset` at `0x1018b659b`
- `sqldk!SystemThread_TlsOffset` at `0x1018b6650`
- `sqldk!SystemThread_TlsOffset` at `0x1018b683c`
- `sqldk!SystemThread_TlsOffset` at `0x1018b68de`

## string_xrefs

- `0x1018b6c30`: `rowLength >= offset + deleteLength`

## pseudocode

```c

```
