# CWdsComMetadataEntry::get_Tag(ushort * *)

- ea: `0x1800119b0`
- end: `0x180011a3c`
- name: `?get_Tag@CWdsComMetadataEntry@@UEAAJPEAPEAG@Z`
- size: `140`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800119b0`
- `0x18001381c`
- `0x180014ee0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011a24`
- `OLEAUT32!__imp_SysFreeString` at `0x180011a24`

## string_xrefs

- `0x1800119d5`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180011a01`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::get_Tag(const unsigned __int16 **this, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  const char *v5; // rdx
  int v6; // eax
  unsigned __int16 *v7; // rcx
  unsigned __int16 *v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  if ( a2
    || (v4 = -2147024809,
        (int)ElValidateHr(-2147024809, 0, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0xCCu) >= 0) )
  {
    v4 = SysAllocStringHr(this[8], &v9);
    v6 = ElValidateHr(v4, v5, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0xD0u);
    v7 = v9;
    if ( v6 >= 0 )
    {
      *a2 = v9;
      v7 = 0;
    }
    if ( v7 )
      SysFreeString(v7);
  }
  return v4;
}

```

## disassembly

```asm
0x1800119b0  mov     [rsp+arg_0], rbx
0x1800119b5  mov     [rsp+arg_10], rsi
0x1800119ba  push    rdi
0x1800119bb  sub     rsp, 20h
0x1800119bf  and     [rsp+28h+arg_8], 0
0x1800119c5  mov     rdi, rdx
0x1800119c8  mov     rsi, rcx
0x1800119cb  test    rdx, rdx
0x1800119ce  jnz     short loc_1800119ED
0x1800119d0  mov     ebx, 80070057h
0x1800119d5  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800119dc  mov     ecx, ebx; int
0x1800119de  mov     r9d, 0CCh; unsigned int
0x1800119e4  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800119e9  test    eax, eax
0x1800119eb  js      short loc_180011A2A
0x1800119ed  mov     rcx, [rsi+40h]; unsigned __int16 *
0x1800119f1  lea     rdx, [rsp+28h+arg_8]; unsigned __int16 **
0x1800119f6  call    ?SysAllocStringHr@@YAJPEBGPEAPEAG@Z; SysAllocStringHr(ushort const *,ushort * *)
0x1800119fb  mov     r9d, 0D0h; unsigned int
0x180011a01  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011a08  mov     ecx, eax; int
0x180011a0a  mov     ebx, eax
0x180011a0c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011a11  mov     rcx, [rsp+28h+arg_8]
0x180011a16  test    eax, eax
0x180011a18  js      short loc_180011A1F
0x180011a1a  mov     [rdi], rcx
0x180011a1d  xor     ecx, ecx; bstrString
0x180011a1f  test    rcx, rcx
0x180011a22  jz      short loc_180011A2A
0x180011a24  call    cs:__imp_SysFreeString
0x180011a2a  mov     rsi, [rsp+28h+arg_10]
0x180011a2f  mov     eax, ebx
0x180011a31  mov     rbx, [rsp+28h+arg_0]
0x180011a36  add     rsp, 20h
0x180011a3a  pop     rdi
0x180011a3b  retn
```
