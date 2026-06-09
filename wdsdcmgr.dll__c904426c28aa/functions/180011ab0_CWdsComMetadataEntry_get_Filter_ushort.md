# CWdsComMetadataEntry::get_Filter(ushort * *)

- ea: `0x180011ab0`
- end: `0x180011b5f`
- name: `?get_Filter@CWdsComMetadataEntry@@UEAAJPEAPEAG@Z`
- size: `175`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180011ab0`
- `0x18001381c`
- `0x180014ee0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011b47`
- `OLEAUT32!__imp_SysFreeString` at `0x180011b47`

## string_xrefs

- `0x180011ad5`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180011af8`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180011b24`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::get_Filter(const unsigned __int16 **this, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  const char *v5; // rdx
  int v6; // eax
  unsigned __int16 *v7; // rcx
  unsigned __int16 *v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  if ( a2
    || (v4 = -2147024809,
        (int)ElValidateHr(-2147024809, 0, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x11Bu) >= 0) )
  {
    if ( *((_DWORD *)this + 24)
      || (v4 = -2147467259,
          (int)ElValidateHr(
                 -2147467259,
                 (const char *)a2,
                 "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp",
                 0x121u) >= 0) )
    {
      v4 = SysAllocStringHr(this[10], &v9);
      v6 = ElValidateHr(v4, v5, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x125u);
      v7 = v9;
      if ( v6 >= 0 )
      {
        *a2 = v9;
        v7 = 0;
      }
      if ( v7 )
        SysFreeString(v7);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180011ab0  mov     [rsp+arg_0], rbx
0x180011ab5  mov     [rsp+arg_10], rsi
0x180011aba  push    rdi
0x180011abb  sub     rsp, 20h
0x180011abf  and     [rsp+28h+arg_8], 0
0x180011ac5  mov     rdi, rdx
0x180011ac8  mov     rsi, rcx
0x180011acb  test    rdx, rdx
0x180011ace  jnz     short loc_180011AED
0x180011ad0  mov     ebx, 80070057h
0x180011ad5  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011adc  mov     ecx, ebx; int
0x180011ade  mov     r9d, 11Bh; unsigned int
0x180011ae4  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011ae9  test    eax, eax
0x180011aeb  js      short loc_180011B4D
0x180011aed  cmp     dword ptr [rsi+60h], 0
0x180011af1  jnz     short loc_180011B10
0x180011af3  mov     ebx, 80004005h
0x180011af8  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011aff  mov     ecx, ebx; int
0x180011b01  mov     r9d, 121h; unsigned int
0x180011b07  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011b0c  test    eax, eax
0x180011b0e  js      short loc_180011B4D
0x180011b10  mov     rcx, [rsi+50h]; unsigned __int16 *
0x180011b14  lea     rdx, [rsp+28h+arg_8]; unsigned __int16 **
0x180011b19  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x180011b1e  mov     r9d, 125h; unsigned int
0x180011b24  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011b2b  mov     ecx, eax; int
0x180011b2d  mov     ebx, eax
0x180011b2f  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011b34  mov     rcx, [rsp+28h+arg_8]
0x180011b39  test    eax, eax
0x180011b3b  js      short loc_180011B42
0x180011b3d  mov     [rdi], rcx
0x180011b40  xor     ecx, ecx; bstrString
0x180011b42  test    rcx, rcx
0x180011b45  jz      short loc_180011B4D
0x180011b47  call    cs:__imp_SysFreeString
0x180011b4d  mov     rsi, [rsp+28h+arg_10]
0x180011b52  mov     eax, ebx
0x180011b54  mov     rbx, [rsp+28h+arg_0]
0x180011b59  add     rsp, 20h
0x180011b5d  pop     rdi
0x180011b5e  retn
```
