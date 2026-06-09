# CsCloseConsole

- ea: `0x140126c90`
- end: `0x140126eae`
- name: `CsCloseConsole`
- size: `542`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400e333c`
- `0x1400fe2c0`

## callees

- `0x140126c90`
- `0x140126eb4`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x140126cc2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x140126cc2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140126cae`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x140126cae`
- `ntdll!TpReleaseIoCompletion` at `0x140126d2f`
- `ntdll!TpReleaseIoCompletion` at `0x140126d2f`
- `ntdll!NtDeviceIoControlFile` at `0x140126d0d`
- `ntdll!NtDeviceIoControlFile` at `0x140126d0d`
- `ntdll!NtClose` at `0x140126d3e`
- `ntdll!NtClose` at `0x140126da4`
- `ntdll!NtClose` at `0x140126e73`
- `ntdll!NtClose` at `0x140126d3e`
- `ntdll!NtClose` at `0x140126da4`
- `ntdll!NtClose` at `0x140126e73`
- `ntdll!RtlFreeHeap` at `0x140126d65`
- `ntdll!RtlFreeHeap` at `0x140126dc2`
- `ntdll!RtlFreeHeap` at `0x140126e05`
- `ntdll!RtlFreeHeap` at `0x140126e5a`
- `ntdll!RtlFreeHeap` at `0x140126e91`
- `ntdll!RtlFreeHeap` at `0x140126d65`
- `ntdll!RtlFreeHeap` at `0x140126dc2`
- `ntdll!RtlFreeHeap` at `0x140126e05`
- `ntdll!RtlFreeHeap` at `0x140126e5a`
- `ntdll!RtlFreeHeap` at `0x140126e91`
- `ntdll!TpWaitForIoCompletion` at `0x140126d1f`
- `ntdll!TpWaitForIoCompletion` at `0x140126d1f`

## pseudocode

```c
BOOLEAN __fastcall CsCloseConsole(char *P)
{
  void *v2; // r8
  _QWORD **v3; // rsi
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  void *v6; // rcx
  _QWORD **v7; // rbx
  _QWORD *v8; // r8
  _QWORD *v9; // rax
  _QWORD *i; // rbx
  _QWORD **v11; // rbx
  _QWORD *v12; // r8
  _QWORD *v13; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  IoStatusBlock = 0;
  RtlAcquireSRWLockExclusive(P + 48);
  P[56] = 1;
  RtlReleaseSRWLockExclusive(P + 48);
  NtDeviceIoControlFile(*(HANDLE *)P, 0, 0, 0, &IoStatusBlock, 0x50001Bu, 0, 0, 0, 0);
  TpWaitForIoCompletion(*((_QWORD *)P + 3), 0);
  TpReleaseIoCompletion(*((_QWORD *)P + 3));
  NtClose(*(HANDLE *)P);
  v2 = (void *)*((_QWORD *)P + 19);
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  v3 = (_QWORD **)(P + 64);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == v3 )
      break;
    if ( (_QWORD **)v4[1] != v3 || (v5 = (_QWORD *)*v4, *(_QWORD **)(*v4 + 8LL) != v4) )
LABEL_23:
      __fastfail(3u);
    *v3 = v5;
    v5[1] = v3;
    v6 = (void *)v4[3];
    if ( v6 )
      NtClose(v6);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  v7 = (_QWORD **)(P + 112);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == v7 )
      break;
    if ( (_QWORD **)v8[1] != v7 )
      goto LABEL_23;
    v9 = (_QWORD *)*v8;
    if ( *(_QWORD **)(*v8 + 8LL) != v8 )
      goto LABEL_23;
    *v7 = v9;
    v9[1] = v7;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  }
  for ( i = P + 80; (_QWORD *)*i != i; CspFreeServerScreen(*i) )
    ;
  v11 = (_QWORD **)(P + 184);
  while ( 1 )
  {
    v12 = *v11;
    if ( *v11 == v11 )
      break;
    if ( (_QWORD **)v12[1] != v11 )
      goto LABEL_23;
    v13 = (_QWORD *)*v12;
    if ( *(_QWORD **)(*v12 + 8LL) != v12 )
      goto LABEL_23;
    *v11 = v13;
    v13[1] = v11;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  }
  NtClose(*((HANDLE *)P + 1));
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
}

```

## disassembly

```asm
0x140126c90  mov     [rsp+arg_0], rbx
0x140126c95  mov     [rsp+arg_8], rsi
0x140126c9a  push    rdi
0x140126c9b  sub     rsp, 60h
0x140126c9f  mov     rdi, rcx
0x140126ca2  xorps   xmm0, xmm0
0x140126ca5  add     rcx, 30h ; '0'
0x140126ca9  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x140126cae  call    cs:__imp_RtlAcquireSRWLockExclusive
0x140126cb5  nop     dword ptr [rax+rax+00h]
0x140126cba  lea     rcx, [rdi+30h]
0x140126cbe  mov     byte ptr [rdi+38h], 1
0x140126cc2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x140126cc9  nop     dword ptr [rax+rax+00h]
0x140126cce  mov     rcx, [rdi]; FileHandle
0x140126cd1  lea     rax, [rsp+68h+var_18]
0x140126cd6  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x140126cde  xor     r9d, r9d; ApcContext
0x140126ce1  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x140126cea  xor     r8d, r8d; ApcRoutine
0x140126ced  mov     [rsp+68h+InputBufferLength], 0; InputBufferLength
0x140126cf5  xor     edx, edx; Event
0x140126cf7  mov     [rsp+68h+InputBuffer], 0; InputBuffer
0x140126d00  mov     [rsp+68h+IoControlCode], 50001Bh; IoControlCode
0x140126d08  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x140126d0d  call    cs:__imp_NtDeviceIoControlFile
0x140126d14  nop     dword ptr [rax+rax+00h]
0x140126d19  mov     rcx, [rdi+18h]
0x140126d1d  xor     edx, edx
0x140126d1f  call    cs:__imp_TpWaitForIoCompletion
0x140126d26  nop     dword ptr [rax+rax+00h]
0x140126d2b  mov     rcx, [rdi+18h]
0x140126d2f  call    cs:__imp_TpReleaseIoCompletion
0x140126d36  nop     dword ptr [rax+rax+00h]
0x140126d3b  mov     rcx, [rdi]; Handle
0x140126d3e  call    cs:__imp_NtClose
0x140126d45  nop     dword ptr [rax+rax+00h]
0x140126d4a  mov     r8, [rdi+98h]; P
0x140126d51  test    r8, r8
0x140126d54  jz      short loc_140126D71
0x140126d56  mov     rcx, gs:60h
0x140126d5f  xor     edx, edx; Flags
0x140126d61  mov     rcx, [rcx+30h]; HeapHandle
0x140126d65  call    cs:__imp_RtlFreeHeap
0x140126d6c  nop     dword ptr [rax+rax+00h]
0x140126d71  lea     rsi, [rdi+40h]
0x140126d75  mov     rbx, [rsi]
0x140126d78  cmp     rbx, rsi
0x140126d7b  jz      short loc_140126DD0
0x140126d7d  cmp     [rbx+8], rsi
0x140126d81  jnz     loc_140126E68
0x140126d87  mov     rax, [rbx]
0x140126d8a  cmp     [rax+8], rbx
0x140126d8e  jnz     loc_140126E68
0x140126d94  mov     [rsi], rax
0x140126d97  mov     [rax+8], rsi
0x140126d9b  mov     rcx, [rbx+18h]; Handle
0x140126d9f  test    rcx, rcx
0x140126da2  jz      short loc_140126DB0
0x140126da4  call    cs:__imp_NtClose
0x140126dab  nop     dword ptr [rax+rax+00h]
0x140126db0  mov     rcx, gs:60h
0x140126db9  mov     r8, rbx; P
0x140126dbc  xor     edx, edx; Flags
0x140126dbe  mov     rcx, [rcx+30h]; HeapHandle
0x140126dc2  call    cs:__imp_RtlFreeHeap
0x140126dc9  nop     dword ptr [rax+rax+00h]
0x140126dce  jmp     short loc_140126D75
0x140126dd0  lea     rbx, [rdi+70h]
0x140126dd4  mov     r8, [rbx]; P
0x140126dd7  cmp     r8, rbx
0x140126dda  jz      short loc_140126E13
0x140126ddc  cmp     [r8+8], rbx
0x140126de0  jnz     loc_140126E68
0x140126de6  mov     rax, [r8]
0x140126de9  cmp     [rax+8], r8
0x140126ded  jnz     short loc_140126E68
0x140126def  mov     [rbx], rax
0x140126df2  xor     edx, edx; Flags
0x140126df4  mov     [rax+8], rbx
0x140126df8  mov     rcx, gs:60h
0x140126e01  mov     rcx, [rcx+30h]; HeapHandle
0x140126e05  call    cs:__imp_RtlFreeHeap
0x140126e0c  nop     dword ptr [rax+rax+00h]
0x140126e11  jmp     short loc_140126DD4
0x140126e13  lea     rbx, [rdi+50h]
0x140126e17  cmp     [rbx], rbx
0x140126e1a  jz      short loc_140126E26
0x140126e1c  mov     rcx, [rbx]
0x140126e1f  call    CspFreeServerScreen
0x140126e24  jmp     short loc_140126E17
0x140126e26  lea     rbx, [rdi+0B8h]
0x140126e2d  mov     r8, [rbx]; P
0x140126e30  cmp     r8, rbx
0x140126e33  jz      short loc_140126E6F
0x140126e35  cmp     [r8+8], rbx
0x140126e39  jnz     short loc_140126E68
0x140126e3b  mov     rax, [r8]
0x140126e3e  cmp     [rax+8], r8
0x140126e42  jnz     short loc_140126E68
0x140126e44  mov     [rbx], rax
0x140126e47  xor     edx, edx; Flags
0x140126e49  mov     [rax+8], rbx
0x140126e4d  mov     rcx, gs:60h
0x140126e56  mov     rcx, [rcx+30h]; HeapHandle
0x140126e5a  call    cs:__imp_RtlFreeHeap
0x140126e61  nop     dword ptr [rax+rax+00h]
0x140126e66  jmp     short loc_140126E2D
0x140126e68  mov     ecx, 3
0x140126e6d  int     29h; Win8: RtlFailFast(ecx)
0x140126e6f  mov     rcx, [rdi+8]; Handle
0x140126e73  call    cs:__imp_NtClose
0x140126e7a  nop     dword ptr [rax+rax+00h]
0x140126e7f  mov     rcx, gs:60h
0x140126e88  mov     r8, rdi; P
0x140126e8b  xor     edx, edx; Flags
0x140126e8d  mov     rcx, [rcx+30h]; HeapHandle
0x140126e91  call    cs:__imp_RtlFreeHeap
0x140126e98  nop     dword ptr [rax+rax+00h]
0x140126e9d  mov     rbx, [rsp+68h+arg_0]
0x140126ea2  mov     rsi, [rsp+68h+arg_8]
0x140126ea7  add     rsp, 60h
0x140126eab  pop     rdi
0x140126eac  retn
```
