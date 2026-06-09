# SclLogGenericMessageV

- ea: `0x18000a564`
- end: `0x18000a696`
- name: `SclLogGenericMessageV`
- size: `306`
- prototype: `int __fastcall(_QWORD *, unsigned int, __int64, int, __int64, char *Format, va_list ArgList)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000a524`

## callees

- `0x18000a564`
- `0x1800179e0`
- `0x180018010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000a651`
- `ntdll!EtwEventWrite` at `0x18000a651`
- `ntdll!_vsnprintf` at `0x18000a5ae`
- `ntdll!_vsnprintf` at `0x18000a5ae`

## pseudocode

```c
int __fastcall SclLogGenericMessageV(
        _QWORD *a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        char *Format,
        va_list ArgList)
{
  __int64 (__fastcall *v11)(_QWORD, char *, _QWORD); // rax
  bool v12; // zf
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v18; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v19[3]; // [rsp+28h] [rbp-D8h] BYREF
  int v20; // [rsp+40h] [rbp-C0h]
  int v21; // [rsp+44h] [rbp-BCh]
  char *v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+50h] [rbp-B0h]
  int v24; // [rsp+54h] [rbp-ACh]
  char Buffer[2048]; // [rsp+60h] [rbp-A0h] BYREF

  LODWORD(v11) = _vsnprintf(Buffer, 0x7FFu, Format, ArgList);
  if ( (unsigned int)v11 < 0x800 )
  {
    if ( (_DWORD)v11 == 2047 )
      Buffer[2047] = 0;
    v12 = a1[4] == 0;
    LODWORD(v18) = a4;
    if ( !v12 )
    {
      v13 = -1;
      v19[0] = &v18;
      v14 = -1;
      v19[1] = 4;
      v19[2] = a5;
      do
        ++v14;
      while ( *(_BYTE *)(a5 + v14) );
      v21 = 0;
      v20 = v14 + 1;
      v22 = Buffer;
      do
        ++v13;
      while ( Buffer[v13] );
      v15 = v13 + 1;
      v24 = 0;
      v16 = a1[4];
      v23 = v15;
      ((void (__fastcall *)(__int64, __int64, __int64, _QWORD *, __int64))EtwEventWrite)(v16, a3, 3, v19, v18);
    }
    v11 = (__int64 (__fastcall *)(_QWORD, char *, _QWORD))a1[2];
    if ( v11 )
      LODWORD(v11) = v11(a2, Buffer, a1[3]);
  }
  return (int)v11;
}

```

## disassembly

```asm
0x18000a564  push    rbp
0x18000a566  push    rbx
0x18000a567  push    rsi
0x18000a568  push    rdi
0x18000a569  push    r14
0x18000a56b  lea     rbp, [rsp-770h]
0x18000a573  sub     rsp, 870h
0x18000a57a  mov     rax, cs:__security_cookie
0x18000a581  xor     rax, rsp
0x18000a584  mov     [rbp+790h+var_30], rax
0x18000a58b  mov     edi, r9d
0x18000a58e  mov     r14, r8
0x18000a591  mov     r8, [rbp+790h+Format]; Format
0x18000a598  mov     esi, edx
0x18000a59a  mov     r9, [rbp+790h+ArgList]; ArgList
0x18000a5a1  mov     rbx, rcx
0x18000a5a4  mov     edx, 7FFh; BufferCount
0x18000a5a9  lea     rcx, [rsp+890h+Buffer]; Buffer
0x18000a5ae  call    cs:__imp__vsnprintf
0x18000a5b4  test    eax, eax
0x18000a5b6  js      loc_18000A672
0x18000a5bc  cmp     eax, 7FFh
0x18000a5c1  ja      loc_18000A672
0x18000a5c7  jnz     short loc_18000A5D0
0x18000a5c9  mov     [rbp+790h+var_31], 0
0x18000a5d0  cmp     qword ptr [rbx+20h], 0
0x18000a5d5  mov     dword ptr [rsp+890h+var_870], edi
0x18000a5d9  jz      short loc_18000A657
0x18000a5db  mov     rdx, [rbp+790h+arg_20]
0x18000a5e2  lea     rax, [rsp+890h+var_870]
0x18000a5e7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000a5eb  mov     [rsp+890h+var_868], rax
0x18000a5f0  mov     rax, rcx
0x18000a5f3  mov     [rsp+890h+var_860], 4
0x18000a5fc  mov     [rsp+890h+var_858], rdx
0x18000a601  inc     rax
0x18000a604  cmp     byte ptr [rdx+rax], 0
0x18000a608  jnz     short loc_18000A601
0x18000a60a  inc     eax
0x18000a60c  mov     [rsp+890h+var_84C], 0
0x18000a614  mov     [rsp+890h+var_850], eax
0x18000a618  lea     rax, [rsp+890h+Buffer]
0x18000a61d  mov     [rsp+890h+var_848], rax
0x18000a622  lea     rax, [rsp+890h+Buffer]
0x18000a627  inc     rcx
0x18000a62a  cmp     byte ptr [rax+rcx], 0
0x18000a62e  jnz     short loc_18000A627
0x18000a630  lea     eax, [rcx+1]
0x18000a633  mov     [rsp+890h+var_83C], 0
0x18000a63b  mov     rcx, [rbx+20h]
0x18000a63f  lea     r9, [rsp+890h+var_868]
0x18000a644  mov     r8d, 3
0x18000a64a  mov     [rsp+890h+var_840], eax
0x18000a64e  mov     rdx, r14
0x18000a651  call    cs:__imp_EtwEventWrite
0x18000a657  mov     rax, [rbx+10h]
0x18000a65b  test    rax, rax
0x18000a65e  jz      short loc_18000A679
0x18000a660  mov     r8, [rbx+18h]
0x18000a664  lea     rdx, [rsp+890h+Buffer]
0x18000a669  mov     ecx, esi
0x18000a66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a670  jmp     short loc_18000A679
0x18000a672  mov     [rbp+790h+var_31], 0
0x18000a679  mov     rcx, [rbp+790h+var_30]
0x18000a680  xor     rcx, rsp; StackCookie
0x18000a683  call    __security_check_cookie
0x18000a688  add     rsp, 870h
0x18000a68f  pop     r14
0x18000a691  pop     rdi
0x18000a692  pop     rsi
0x18000a693  pop     rbx
0x18000a694  pop     rbp
0x18000a695  retn
```
