# CSaveResMapHandler::_GetUniqueTempFileName(ushort *,unsigned __int64)

- ea: `0x18006423c`
- end: `0x1800642e5`
- name: `?_GetUniqueTempFileName@CSaveResMapHandler@@AEAAJPEAG_K@Z`
- size: `169`
- prototype: `int(CSaveResMapHandler *__hidden this, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180064880`

## callees

- `0x180002ad0`
- `0x18004e9f8`
- `0x18006423c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180064273`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180064273`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006428d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18006428d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800642be`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800642be`

## pseudocode

```c
int __fastcall CSaveResMapHandler::_GetUniqueTempFileName(const WCHAR *this, unsigned __int16 *a2)
{
  int result; // eax
  GUID pguid; // [rsp+20h] [rbp-88h] BYREF
  OLECHAR sz[48]; // [rsp+30h] [rbp-78h] BYREF

  *a2 = 0;
  pguid = 0;
  result = CoCreateGuid(&pguid);
  if ( result >= 0 )
  {
    StringFromGUID2(&pguid, sz, 44);
    result = StringCchCatW(sz, 0x2Cu, L".tmp");
    if ( result >= 0 )
      return PathCchCombine(a2, 0x104u, this + 8, sz);
  }
  return result;
}

```

## disassembly

```asm
0x18006423c  mov     [rsp+arg_10], rbx
0x180064241  push    rdi
0x180064242  sub     rsp, 0A0h
0x180064249  mov     rax, cs:__security_cookie
0x180064250  xor     rax, rsp
0x180064253  mov     [rsp+0A8h+var_18], rax
0x18006425b  mov     rdi, rcx
0x18006425e  xor     eax, eax
0x180064260  xorps   xmm0, xmm0
0x180064263  mov     [rdx], ax
0x180064266  lea     rcx, [rsp+0A8h+pguid]; pguid
0x18006426b  mov     rbx, rdx
0x18006426e  movups  xmmword ptr [rsp+0A8h+pguid.Data1], xmm0
0x180064273  call    cs:__imp_CoCreateGuid
0x180064279  test    eax, eax
0x18006427b  js      short loc_1800642C4
0x18006427d  mov     r8d, 2Ch ; ','; cchMax
0x180064283  lea     rdx, [rsp+0A8h+sz]; lpsz
0x180064288  lea     rcx, [rsp+0A8h+pguid]; rguid
0x18006428d  call    cs:__imp_StringFromGUID2
0x180064293  lea     r8, aTmp; ".tmp"
0x18006429a  mov     edx, 2Ch ; ','; unsigned __int64
0x18006429f  lea     rcx, [rsp+0A8h+sz]; unsigned __int16 *
0x1800642a4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800642a9  test    eax, eax
0x1800642ab  js      short loc_1800642C4
0x1800642ad  lea     r8, [rdi+10h]; pszPathIn
0x1800642b1  mov     edx, 104h; cchPathOut
0x1800642b6  lea     r9, [rsp+0A8h+sz]; pszMore
0x1800642bb  mov     rcx, rbx; pszPathOut
0x1800642be  call    cs:__imp_PathCchCombine
0x1800642c4  mov     rcx, [rsp+0A8h+var_18]
0x1800642cc  xor     rcx, rsp; StackCookie
0x1800642cf  call    __security_check_cookie
0x1800642d4  mov     rbx, [rsp+0A8h+arg_10]
0x1800642dc  add     rsp, 0A0h
0x1800642e3  pop     rdi
0x1800642e4  retn
```
