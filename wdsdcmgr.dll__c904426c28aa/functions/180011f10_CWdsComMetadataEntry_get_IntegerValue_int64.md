# CWdsComMetadataEntry::get_IntegerValue(__int64 *)

- ea: `0x180011f10`
- end: `0x180011fc4`
- name: `?get_IntegerValue@CWdsComMetadataEntry@@UEAAJPEA_J@Z`
- size: `180`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180011f10`
- `0x180014d58`
- `0x180014ee0`

## string_xrefs

- `0x180011f3d`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180011f82`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::get_IntegerValue(CWdsComMetadataEntry *this, char *a2)
{
  unsigned int v2; // edi
  __int64 v3; // rbx
  signed int v6; // esi

  v2 = 0;
  v3 = 0;
  if ( a2
    || (v2 = -2147024809,
        (int)ElValidateHr(-2147024809, 0, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x217u) >= 0) )
  {
    v6 = 0;
    if ( *((_DWORD *)this + 26) == 4 )
      v3 = *((_QWORD *)this + 14);
    else
      v6 = ElValidateWin32(0xDu, a2, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x657u);
    if ( ElValidateWin32(v6, a2, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x21Bu) )
    {
      v2 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        return (unsigned int)v6;
    }
    else
    {
      *(_QWORD *)a2 = v3;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180011f10  mov     rax, rsp
0x180011f13  mov     [rax+8], rbx
0x180011f17  mov     [rax+10h], rbp
0x180011f1b  mov     [rax+18h], rsi
0x180011f1f  mov     [rax+20h], rdi
0x180011f23  push    r14
0x180011f25  sub     rsp, 20h
0x180011f29  xor     edi, edi
0x180011f2b  xor     ebx, ebx
0x180011f2d  mov     r14, rdx
0x180011f30  mov     rbp, rcx
0x180011f33  test    rdx, rdx
0x180011f36  jnz     short loc_180011F55
0x180011f38  mov     edi, 80070057h
0x180011f3d  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011f44  mov     ecx, edi; int
0x180011f46  mov     r9d, 217h; unsigned int
0x180011f4c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180011f51  test    eax, eax
0x180011f53  js      short loc_180011FA7
0x180011f55  xor     esi, esi
0x180011f57  cmp     dword ptr [rbp+68h], 4
0x180011f5b  jnz     short loc_180011F63
0x180011f5d  mov     rbx, [rbp+70h]
0x180011f61  jmp     short loc_180011F7C
0x180011f63  mov     r9d, 657h; unsigned int
0x180011f69  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180011f70  mov     ecx, 0Dh; unsigned int
0x180011f75  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011f7a  mov     esi, eax
0x180011f7c  mov     r9d, 21Bh; unsigned int
0x180011f82  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180011f89  mov     ecx, esi; unsigned int
0x180011f8b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180011f90  test    eax, eax
0x180011f92  jz      short loc_180011FA4
0x180011f94  movzx   edi, si
0x180011f97  or      edi, 80070000h
0x180011f9d  test    esi, esi
0x180011f9f  cmovle  edi, esi
0x180011fa2  jmp     short loc_180011FA7
0x180011fa4  mov     [r14], rbx
0x180011fa7  mov     rbx, [rsp+28h+arg_0]
0x180011fac  mov     eax, edi
0x180011fae  mov     rdi, [rsp+28h+arg_18]
0x180011fb3  mov     rbp, [rsp+28h+arg_8]
0x180011fb8  mov     rsi, [rsp+28h+arg_10]
0x180011fbd  add     rsp, 20h
0x180011fc1  pop     r14
0x180011fc3  retn
```
