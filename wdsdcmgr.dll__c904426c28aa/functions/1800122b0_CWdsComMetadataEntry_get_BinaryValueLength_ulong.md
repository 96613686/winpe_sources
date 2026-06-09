# CWdsComMetadataEntry::get_BinaryValueLength(ulong *)

- ea: `0x1800122b0`
- end: `0x18001238e`
- name: `?get_BinaryValueLength@CWdsComMetadataEntry@@UEAAJPEAK@Z`
- size: `222`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800122b0`
- `0x180014d58`
- `0x180014ee0`

## string_xrefs

- `0x1800122db`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180012320`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180012347`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::get_BinaryValueLength(CWdsComMetadataEntry *this, char *a2)
{
  unsigned __int64 v2; // rbp
  unsigned int v5; // ebx
  signed int v6; // edi
  const char *v7; // rdx
  unsigned int v8; // ecx

  v2 = 0;
  if ( a2
    || (v5 = -2147024809,
        (int)ElValidateHr(-2147024809, 0, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x2A0u) >= 0) )
  {
    v6 = 0;
    if ( *((_DWORD *)this + 26) == 7 )
      v2 = *((_QWORD *)this + 15);
    else
      v6 = ElValidateWin32(0xDu, a2, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x6FDu);
    if ( ElValidateWin32(v6, a2, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x2A4u) )
    {
      v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        return (unsigned int)v6;
    }
    else
    {
      v8 = -1;
      if ( v2 <= 0xFFFFFFFF )
        v8 = v2;
      *(_DWORD *)a2 = v8;
      v5 = v2 > 0xFFFFFFFF ? 0x80070216 : 0;
      ElValidateHr(v5, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x2A7u);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800122b0  mov     rax, rsp
0x1800122b3  mov     [rax+8], rbx
0x1800122b7  mov     [rax+10h], rbp
0x1800122bb  mov     [rax+18h], rsi
0x1800122bf  mov     [rax+20h], rdi
0x1800122c3  push    r14
0x1800122c5  sub     rsp, 20h
0x1800122c9  xor     ebp, ebp
0x1800122cb  mov     r14, rdx
0x1800122ce  mov     rsi, rcx
0x1800122d1  test    rdx, rdx
0x1800122d4  jnz     short loc_1800122F3
0x1800122d6  mov     ebx, 80070057h
0x1800122db  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800122e2  mov     ecx, ebx; int
0x1800122e4  mov     r9d, 2A0h; unsigned int
0x1800122ea  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800122ef  test    eax, eax
0x1800122f1  js      short loc_180012371
0x1800122f3  xor     edi, edi
0x1800122f5  cmp     dword ptr [rsi+68h], 7
0x1800122f9  jnz     short loc_180012301
0x1800122fb  mov     rbp, [rsi+78h]
0x1800122ff  jmp     short loc_18001231A
0x180012301  mov     r9d, 6FDh; unsigned int
0x180012307  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18001230e  mov     ecx, 0Dh; unsigned int
0x180012313  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180012318  mov     edi, eax
0x18001231a  mov     r9d, 2A4h; unsigned int
0x180012320  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180012327  mov     ecx, edi; unsigned int
0x180012329  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001232e  test    eax, eax
0x180012330  jz      short loc_180012342
0x180012332  movzx   ebx, di
0x180012335  or      ebx, 80070000h
0x18001233b  test    edi, edi
0x18001233d  cmovle  ebx, edi
0x180012340  jmp     short loc_180012371
0x180012342  mov     eax, 0FFFFFFFFh
0x180012347  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001234e  cmp     rbp, rax
0x180012351  mov     ecx, eax
0x180012353  mov     r9d, 2A7h; unsigned int
0x180012359  cmovbe  ecx, ebp
0x18001235c  cmp     rax, rbp
0x18001235f  mov     [r14], ecx
0x180012362  sbb     ebx, ebx
0x180012364  and     ebx, 80070216h
0x18001236a  mov     ecx, ebx; int
0x18001236c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180012371  mov     rbp, [rsp+28h+arg_8]
0x180012376  mov     eax, ebx
0x180012378  mov     rbx, [rsp+28h+arg_0]
0x18001237d  mov     rsi, [rsp+28h+arg_10]
0x180012382  mov     rdi, [rsp+28h+arg_18]
0x180012387  add     rsp, 20h
0x18001238b  pop     r14
0x18001238d  retn
```
