# CWdsComMetadataEntry::get_VersionValue(unsigned __int64 *)

- ea: `0x180011fd0`
- end: `0x180012084`
- name: `?get_VersionValue@CWdsComMetadataEntry@@UEAAJPEA_K@Z`
- size: `180`
- prototype: `__int64 __fastcall(CWdsComMetadataEntry *__hidden this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180011fd0`
- `0x180014d58`
- `0x180014ee0`

## string_xrefs

- `0x180011ffd`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`
- `0x180012042`: `base\eco\wds\lib\metadata\com\wdscommetadataentry.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataEntry::get_VersionValue(CWdsComMetadataEntry *this, char *a2)
{
  unsigned int v2; // edi
  unsigned __int64 v3; // rbx
  signed int v6; // esi

  v2 = 0;
  v3 = 0;
  if ( a2
    || (v2 = -2147024809,
        (int)ElValidateHr(-2147024809, 0, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x23Fu) >= 0) )
  {
    v6 = 0;
    if ( *((_DWORD *)this + 26) == 5 )
      v3 = *((_QWORD *)this + 14);
    else
      v6 = ElValidateWin32(0xDu, a2, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x67Bu);
    if ( ElValidateWin32(v6, a2, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadataentry.cpp", 0x243u) )
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
0x180011fd0  mov     rax, rsp
0x180011fd3  mov     [rax+8], rbx
0x180011fd7  mov     [rax+10h], rbp
0x180011fdb  mov     [rax+18h], rsi
0x180011fdf  mov     [rax+20h], rdi
0x180011fe3  push    r14
0x180011fe5  sub     rsp, 20h
0x180011fe9  xor     edi, edi
0x180011feb  xor     ebx, ebx
0x180011fed  mov     r14, rdx
0x180011ff0  mov     rbp, rcx
0x180011ff3  test    rdx, rdx
0x180011ff6  jnz     short loc_180012015
0x180011ff8  mov     edi, 80070057h
0x180011ffd  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180012004  mov     ecx, edi; int
0x180012006  mov     r9d, 23Fh; unsigned int
0x18001200c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180012011  test    eax, eax
0x180012013  js      short loc_180012067
0x180012015  xor     esi, esi
0x180012017  cmp     dword ptr [rbp+68h], 5
0x18001201b  jnz     short loc_180012023
0x18001201d  mov     rbx, [rbp+70h]
0x180012021  jmp     short loc_18001203C
0x180012023  mov     r9d, 67Bh; unsigned int
0x180012029  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180012030  mov     ecx, 0Dh; unsigned int
0x180012035  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001203a  mov     esi, eax
0x18001203c  mov     r9d, 243h; unsigned int
0x180012042  lea     r8, aBaseEcoWdsLibM_2; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180012049  mov     ecx, esi; unsigned int
0x18001204b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180012050  test    eax, eax
0x180012052  jz      short loc_180012064
0x180012054  movzx   edi, si
0x180012057  or      edi, 80070000h
0x18001205d  test    esi, esi
0x18001205f  cmovle  edi, esi
0x180012062  jmp     short loc_180012067
0x180012064  mov     [r14], rbx
0x180012067  mov     rbx, [rsp+28h+arg_0]
0x18001206c  mov     eax, edi
0x18001206e  mov     rdi, [rsp+28h+arg_18]
0x180012073  mov     rbp, [rsp+28h+arg_8]
0x180012078  mov     rsi, [rsp+28h+arg_10]
0x18001207d  add     rsp, 20h
0x180012081  pop     r14
0x180012083  retn
```
