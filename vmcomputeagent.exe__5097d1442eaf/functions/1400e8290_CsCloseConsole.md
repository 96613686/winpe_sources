# CsCloseConsole

- ea: `0x1400e8290`
- end: `0x1400e845b`
- name: `CsCloseConsole`
- size: `459`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400e4970`
- `0x1400e4b88`
- `0x1400e4ba8`

## callees

- `0x1400e8290`
- `0x1400e8b3c`

## import_xrefs

- `ntdll!TpReleaseIoCompletion` at `0x1400e8317`
- `ntdll!TpReleaseIoCompletion` at `0x1400e8317`
- `ntdll!TpWaitForIoCompletion` at `0x1400e830d`
- `ntdll!TpWaitForIoCompletion` at `0x1400e830d`
- `ntdll!RtlFreeHeap` at `0x1400e8341`
- `ntdll!RtlFreeHeap` at `0x1400e8392`
- `ntdll!RtlFreeHeap` at `0x1400e83cb`
- `ntdll!RtlFreeHeap` at `0x1400e841a`
- `ntdll!RtlFreeHeap` at `0x1400e8445`
- `ntdll!RtlFreeHeap` at `0x1400e8341`
- `ntdll!RtlFreeHeap` at `0x1400e8392`
- `ntdll!RtlFreeHeap` at `0x1400e83cb`
- `ntdll!RtlFreeHeap` at `0x1400e841a`
- `ntdll!RtlFreeHeap` at `0x1400e8445`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400e82ae`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400e82ae`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e82bc`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400e82bc`
- `ntdll!NtDeviceIoControlFile` at `0x1400e8301`
- `ntdll!NtDeviceIoControlFile` at `0x1400e8301`
- `ntdll!NtClose` at `0x1400e8320`
- `ntdll!NtClose` at `0x1400e837a`
- `ntdll!NtClose` at `0x1400e842d`
- `ntdll!NtClose` at `0x1400e8320`
- `ntdll!NtClose` at `0x1400e837a`
- `ntdll!NtClose` at `0x1400e842d`

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
0x1400e8290  mov     [rsp+arg_0], rbx
0x1400e8295  mov     [rsp+arg_8], rsi
0x1400e829a  push    rdi
0x1400e829b  sub     rsp, 60h
0x1400e829f  mov     rdi, rcx
0x1400e82a2  xorps   xmm0, xmm0
0x1400e82a5  add     rcx, 30h ; '0'
0x1400e82a9  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x1400e82ae  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1400e82b4  lea     rcx, [rdi+30h]
0x1400e82b8  mov     byte ptr [rdi+38h], 1
0x1400e82bc  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1400e82c2  mov     rcx, [rdi]; FileHandle
0x1400e82c5  lea     rax, [rsp+68h+var_18]
0x1400e82ca  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x1400e82d2  xor     r9d, r9d; ApcContext
0x1400e82d5  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x1400e82de  xor     r8d, r8d; ApcRoutine
0x1400e82e1  mov     [rsp+68h+InputBufferLength], 0; InputBufferLength
0x1400e82e9  xor     edx, edx; Event
0x1400e82eb  mov     [rsp+68h+InputBuffer], 0; InputBuffer
0x1400e82f4  mov     [rsp+68h+IoControlCode], 50001Bh; IoControlCode
0x1400e82fc  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x1400e8301  call    cs:__imp_NtDeviceIoControlFile
0x1400e8307  mov     rcx, [rdi+18h]
0x1400e830b  xor     edx, edx
0x1400e830d  call    cs:__imp_TpWaitForIoCompletion
0x1400e8313  mov     rcx, [rdi+18h]
0x1400e8317  call    cs:__imp_TpReleaseIoCompletion
0x1400e831d  mov     rcx, [rdi]; Handle
0x1400e8320  call    cs:__imp_NtClose
0x1400e8326  mov     r8, [rdi+98h]; P
0x1400e832d  test    r8, r8
0x1400e8330  jz      short loc_1400E8347
0x1400e8332  mov     rcx, gs:60h
0x1400e833b  xor     edx, edx; Flags
0x1400e833d  mov     rcx, [rcx+30h]; HeapHandle
0x1400e8341  call    cs:__imp_RtlFreeHeap
0x1400e8347  lea     rsi, [rdi+40h]
0x1400e834b  mov     rbx, [rsi]
0x1400e834e  cmp     rbx, rsi
0x1400e8351  jz      short loc_1400E839A
0x1400e8353  cmp     [rbx+8], rsi
0x1400e8357  jnz     loc_1400E8422
0x1400e835d  mov     rax, [rbx]
0x1400e8360  cmp     [rax+8], rbx
0x1400e8364  jnz     loc_1400E8422
0x1400e836a  mov     [rsi], rax
0x1400e836d  mov     [rax+8], rsi
0x1400e8371  mov     rcx, [rbx+18h]; Handle
0x1400e8375  test    rcx, rcx
0x1400e8378  jz      short loc_1400E8380
0x1400e837a  call    cs:__imp_NtClose
0x1400e8380  mov     rcx, gs:60h
0x1400e8389  mov     r8, rbx; P
0x1400e838c  xor     edx, edx; Flags
0x1400e838e  mov     rcx, [rcx+30h]; HeapHandle
0x1400e8392  call    cs:__imp_RtlFreeHeap
0x1400e8398  jmp     short loc_1400E834B
0x1400e839a  lea     rbx, [rdi+70h]
0x1400e839e  mov     r8, [rbx]; P
0x1400e83a1  cmp     r8, rbx
0x1400e83a4  jz      short loc_1400E83D3
0x1400e83a6  cmp     [r8+8], rbx
0x1400e83aa  jnz     short loc_1400E8422
0x1400e83ac  mov     rax, [r8]
0x1400e83af  cmp     [rax+8], r8
0x1400e83b3  jnz     short loc_1400E8422
0x1400e83b5  mov     [rbx], rax
0x1400e83b8  xor     edx, edx; Flags
0x1400e83ba  mov     [rax+8], rbx
0x1400e83be  mov     rcx, gs:60h
0x1400e83c7  mov     rcx, [rcx+30h]; HeapHandle
0x1400e83cb  call    cs:__imp_RtlFreeHeap
0x1400e83d1  jmp     short loc_1400E839E
0x1400e83d3  lea     rbx, [rdi+50h]
0x1400e83d7  cmp     [rbx], rbx
0x1400e83da  jz      short loc_1400E83E6
0x1400e83dc  mov     rcx, [rbx]
0x1400e83df  call    CspFreeServerScreen
0x1400e83e4  jmp     short loc_1400E83D7
0x1400e83e6  lea     rbx, [rdi+0B8h]
0x1400e83ed  mov     r8, [rbx]; P
0x1400e83f0  cmp     r8, rbx
0x1400e83f3  jz      short loc_1400E8429
0x1400e83f5  cmp     [r8+8], rbx
0x1400e83f9  jnz     short loc_1400E8422
0x1400e83fb  mov     rax, [r8]
0x1400e83fe  cmp     [rax+8], r8
0x1400e8402  jnz     short loc_1400E8422
0x1400e8404  mov     [rbx], rax
0x1400e8407  xor     edx, edx; Flags
0x1400e8409  mov     [rax+8], rbx
0x1400e840d  mov     rcx, gs:60h
0x1400e8416  mov     rcx, [rcx+30h]; HeapHandle
0x1400e841a  call    cs:__imp_RtlFreeHeap
0x1400e8420  jmp     short loc_1400E83ED
0x1400e8422  mov     ecx, 3
0x1400e8427  int     29h; Win8: RtlFailFast(ecx)
0x1400e8429  mov     rcx, [rdi+8]; Handle
0x1400e842d  call    cs:__imp_NtClose
0x1400e8433  mov     rcx, gs:60h
0x1400e843c  mov     r8, rdi; P
0x1400e843f  xor     edx, edx; Flags
0x1400e8441  mov     rcx, [rcx+30h]; HeapHandle
0x1400e8445  call    cs:__imp_RtlFreeHeap
0x1400e844b  mov     rbx, [rsp+68h+arg_0]
0x1400e8450  mov     rsi, [rsp+68h+arg_8]
0x1400e8455  add     rsp, 60h
0x1400e8459  pop     rdi
0x1400e845a  retn
```
