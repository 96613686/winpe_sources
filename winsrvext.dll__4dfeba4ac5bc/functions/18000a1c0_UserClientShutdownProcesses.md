# UserClientShutdownProcesses

- ea: `0x18000a1c0`
- end: `0x18000a4ec`
- name: `UserClientShutdownProcesses`
- size: `812`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000a1c0`
- `0x18000a500`
- `0x180011a70`
- `0x1800138c5`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18000a31e`
- `KERNELBASE!LocalAlloc` at `0x18000a31e`
- `ntdll!NtSetEvent` at `0x18000a44d`
- `ntdll!NtSetEvent` at `0x18000a44d`
- `ntdll!NtWaitForSingleObject` at `0x18000a420`
- `ntdll!NtWaitForSingleObject` at `0x18000a462`
- `ntdll!NtWaitForSingleObject` at `0x18000a420`
- `ntdll!NtWaitForSingleObject` at `0x18000a462`
- `ntdll!RtlCreateUserThread` at `0x18000a3e3`
- `ntdll!RtlCreateUserThread` at `0x18000a3e3`
- `ntdll!NtCreateEvent` at `0x18000a2e6`
- `ntdll!NtCreateEvent` at `0x18000a2e6`
- `ntdll!RtlInitializeCriticalSection` at `0x18000a22f`
- `ntdll!RtlInitializeCriticalSection` at `0x18000a22f`
- `ntdll!NtClose` at `0x18000a430`
- `ntdll!NtClose` at `0x18000a472`
- `ntdll!NtClose` at `0x18000a487`
- `ntdll!NtClose` at `0x18000a49c`
- `ntdll!NtClose` at `0x18000a4b1`
- `ntdll!NtClose` at `0x18000a430`
- `ntdll!NtClose` at `0x18000a472`
- `ntdll!NtClose` at `0x18000a487`
- `ntdll!NtClose` at `0x18000a49c`
- `ntdll!NtClose` at `0x18000a4b1`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a4c2`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a4c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3f6`

## pseudocode

```c
__int64 __fastcall UserClientShutdownProcesses(__int64 a1, _DWORD *a2, unsigned int a3, int a4, char a5, int a6)
{
  unsigned __int64 v9; // rdx
  void *v10; // r8
  int v11; // eax
  void **v12; // rdx
  bool v13; // si
  char v14; // r13
  __int64 v15; // rbx
  _OWORD *Reserved6; // rdi
  int v17; // ecx
  __int64 v18; // rax
  bool v19; // zf
  void **v21; // [rsp+50h] [rbp-B0h]
  void *v22[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[8]; // [rsp+70h] [rbp-90h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+78h] [rbp-88h] BYREF
  HANDLE v25; // [rsp+A0h] [rbp-60h]
  HANDLE v26; // [rsp+A8h] [rbp-58h]
  HANDLE v27; // [rsp+B0h] [rbp-50h]
  HANDLE Handle; // [rsp+B8h] [rbp-48h]
  int v29; // [rsp+C0h] [rbp-40h]
  _OWORD hMem[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v31; // [rsp+100h] [rbp+0h]
  void *EventHandle; // [rsp+158h] [rbp+58h] BYREF
  unsigned int i; // [rsp+160h] [rbp+60h] BYREF

  v31 = 0;
  i = 0;
  EventHandle = 0;
  memset(hMem, 0, sizeof(hMem));
  memset_0(v23, 0, 0x58u);
  v22[1] = v22;
  v22[0] = v22;
  RtlInitializeCriticalSection(&CriticalSection);
  EventHandle = 0;
  v9 = a3;
  if ( a3 )
  {
    if ( ((unsigned __int8)a2 & 4) != 0 )
    {
      *a2 = 2;
      v9 = a3 - 1LL;
      if ( a3 == 1 )
        goto LABEL_8;
      v10 = a2 + 1;
    }
    else
    {
      v10 = a2;
    }
    memset64(v10, 0x200000002uLL, v9 >> 1);
    if ( (v9 & 1) != 0 )
      *((_DWORD *)v10 + v9 - 1) = 2;
  }
LABEL_8:
  v11 = 1075380276;
  if ( (a4 & 4) == 0 )
    v11 = ShutdownResolverContextStart(v22);
  v12 = v22;
  if ( v11 )
  {
    a4 |= 4u;
    v12 = 0;
  }
  v21 = v12;
  if ( gfAllowBlockingApps )
  {
    v13 = 1;
    v14 = 1;
  }
  else
  {
    v14 = 0;
    v13 = NtCreateEvent(&EventHandle, 0x1F0003u, 0, NotificationEvent, 0) < 0;
  }
  v15 = 0;
  for ( i = a3; (unsigned int)v15 < a3; v15 = (unsigned int)(v15 + 1) )
  {
    if ( v13 )
    {
      Reserved6 = hMem;
    }
    else
    {
      Reserved6 = LocalAlloc(0, 0x38u);
      if ( !Reserved6 )
        goto LABEL_25;
    }
    v17 = a6;
    *Reserved6 = 0;
    Reserved6[1] = 0;
    Reserved6[2] = 0;
    *((_QWORD *)Reserved6 + 6) = 0;
    *(_QWORD *)Reserved6 = &i;
    *((_QWORD *)Reserved6 + 1) = EventHandle;
    *((_QWORD *)Reserved6 + 2) = &a2[v15];
    *((_QWORD *)Reserved6 + 3) = v21;
    v18 = *(_QWORD *)(a1 + 8 * v15);
    *((_DWORD *)Reserved6 + 11) &= ~1u;
    v19 = a5 == 0;
    *((_QWORD *)Reserved6 + 4) = v18;
    *((_DWORD *)Reserved6 + 10) = a4;
    *((_DWORD *)Reserved6 + 11) |= !v19;
    *((_DWORD *)Reserved6 + 12) = v17;
    if ( v13 )
    {
      UserClientShutdownWorker(Reserved6);
      if ( v14 && **((_DWORD **)Reserved6 + 2) == 3 )
        break;
    }
    else
    {
      *((_DWORD *)Reserved6 + 11) |= 2u;
      if ( RtlCreateUserThread((PVOID)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0, 0, 0, UserClientShutdownWorker, Reserved6, 0, 0) < 0 )
      {
        LocalFree(Reserved6);
LABEL_25:
        LODWORD(v15) = v15 - 1;
        v13 = 1;
      }
    }
  }
  if ( EventHandle )
  {
    NtWaitForSingleObject(EventHandle, 0, 0);
    NtClose(EventHandle);
  }
  if ( Handle )
  {
    v29 |= 1u;
    NtSetEvent(v25, 0);
    NtWaitForSingleObject(Handle, 0, 0);
    NtClose(Handle);
  }
  if ( v27 )
    NtClose(v27);
  if ( v25 )
    NtClose(v25);
  if ( v26 )
    NtClose(v26);
  RtlDeleteCriticalSection(&CriticalSection);
  return 0;
}

```

## disassembly

```asm
0x18000a1c0  mov     [rsp-8+arg_18], rbx
0x18000a1c5  mov     [rsp-8+arg_0], rcx
0x18000a1ca  push    rbp
0x18000a1cb  push    rsi
0x18000a1cc  push    rdi
0x18000a1cd  push    r12
0x18000a1cf  push    r13
0x18000a1d1  push    r14
0x18000a1d3  push    r15
0x18000a1d5  lea     rbp, [rsp-10h]
0x18000a1da  sub     rsp, 110h
0x18000a1e1  xor     eax, eax
0x18000a1e3  mov     r12d, r8d
0x18000a1e6  xorps   xmm0, xmm0
0x18000a1e9  mov     [rbp+40h+var_40], rax
0x18000a1ed  mov     r14, rdx
0x18000a1f0  mov     [rbp+40h+arg_10], eax
0x18000a1f3  xor     edx, edx; Val
0x18000a1f5  mov     [rbp+40h+EventHandle], rax
0x18000a1f9  lea     r8d, [rax+58h]; Size
0x18000a1fd  mov     r15d, r9d
0x18000a200  lea     rcx, [rsp+140h+var_D0]; void *
0x18000a205  movups  [rbp+40h+hMem], xmm0
0x18000a209  movups  [rbp+40h+var_60], xmm0
0x18000a20d  movups  [rbp+40h+var_50], xmm0
0x18000a211  call    memset_0
0x18000a216  lea     rax, [rsp+140h+var_E0]
0x18000a21b  mov     [rsp+140h+var_D8], rax
0x18000a220  lea     rcx, [rsp+140h+CriticalSection]; CriticalSection
0x18000a225  lea     rax, [rsp+140h+var_E0]
0x18000a22a  mov     [rsp+140h+var_E0], rax
0x18000a22f  call    cs:__imp_RtlInitializeCriticalSection
0x18000a236  nop     dword ptr [rax+rax+00h]
0x18000a23b  mov     [rbp+40h+EventHandle], 0
0x18000a243  mov     ebx, 1
0x18000a248  mov     edx, r12d
0x18000a24b  lea     r9d, [rbx+1]
0x18000a24f  test    r12d, r12d
0x18000a252  jz      short loc_18000A28A
0x18000a254  test    r14b, 4
0x18000a258  jz      short loc_18000A268
0x18000a25a  mov     [r14], r9d
0x18000a25d  sub     rdx, rbx
0x18000a260  jz      short loc_18000A28A
0x18000a262  lea     r8, [r14+4]
0x18000a266  jmp     short loc_18000A26B
0x18000a268  mov     r8, r14
0x18000a26b  mov     rcx, rdx
0x18000a26e  mov     rax, 200000002h
0x18000a278  shr     rcx, 1
0x18000a27b  mov     rdi, r8
0x18000a27e  rep stosq
0x18000a281  test    bl, dl
0x18000a283  jz      short loc_18000A28A
0x18000a285  mov     [r8+rdx*4-4], r9d
0x18000a28a  mov     eax, 40190034h
0x18000a28f  test    r15b, 4
0x18000a293  jnz     short loc_18000A29F
0x18000a295  lea     rcx, [rsp+140h+var_E0]; Reserved6
0x18000a29a  call    ShutdownResolverContextStart
0x18000a29f  mov     ecx, r15d
0x18000a2a2  lea     rdx, [rsp+140h+var_E0]
0x18000a2a7  or      ecx, 4
0x18000a2aa  test    eax, eax
0x18000a2ac  cmovnz  r15d, ecx
0x18000a2b0  xor     ecx, ecx
0x18000a2b2  test    eax, eax
0x18000a2b4  cmovnz  rdx, rcx
0x18000a2b8  cmp     cs:gfAllowBlockingApps, ecx
0x18000a2be  mov     [rsp+140h+var_F0], rdx
0x18000a2c3  jz      short loc_18000A2CD
0x18000a2c5  mov     sil, bl
0x18000a2c8  mov     r13b, bl
0x18000a2cb  jmp     short loc_18000A2FB
0x18000a2cd  mov     [rsp+140h+InitialState], cl; InitialState
0x18000a2d1  xor     r9d, r9d; EventType
0x18000a2d4  lea     rcx, [rbp+40h+EventHandle]; EventHandle
0x18000a2d8  xor     r8d, r8d; ObjectAttributes
0x18000a2db  mov     edx, 1F0003h; DesiredAccess
0x18000a2e0  xor     dil, dil
0x18000a2e3  xor     r13b, r13b
0x18000a2e6  call    cs:__imp_NtCreateEvent
0x18000a2ed  nop     dword ptr [rax+rax+00h]
0x18000a2f2  test    eax, eax
0x18000a2f4  movzx   esi, dil
0x18000a2f8  cmovs   esi, ebx
0x18000a2fb  xor     ebx, ebx
0x18000a2fd  mov     [rbp+40h+arg_10], r12d
0x18000a301  test    r12d, r12d
0x18000a304  jz      loc_18000A412
0x18000a30a  test    sil, sil
0x18000a30d  jz      short loc_18000A317
0x18000a30f  lea     rdi, [rbp+40h+hMem]
0x18000a313  xor     edx, edx
0x18000a315  jmp     short loc_18000A338
0x18000a317  mov     edx, 38h ; '8'; uBytes
0x18000a31c  xor     ecx, ecx; uFlags
0x18000a31e  call    cs:__imp_LocalAlloc
0x18000a325  nop     dword ptr [rax+rax+00h]
0x18000a32a  xor     edx, edx
0x18000a32c  mov     rdi, rax
0x18000a32f  test    rax, rax
0x18000a332  jz      loc_18000A402
0x18000a338  mov     ecx, [rbp+40h+arg_28]
0x18000a33b  xor     eax, eax
0x18000a33d  xorps   xmm0, xmm0
0x18000a340  movups  xmmword ptr [rdi], xmm0
0x18000a343  movups  xmmword ptr [rdi+10h], xmm0
0x18000a347  movups  xmmword ptr [rdi+20h], xmm0
0x18000a34b  mov     [rdi+30h], rax
0x18000a34f  lea     rax, [rbp+40h+arg_10]
0x18000a353  mov     [rdi], rax
0x18000a356  mov     rax, [rbp+40h+EventHandle]
0x18000a35a  mov     [rdi+8], rax
0x18000a35e  lea     rax, [r14+rbx*4]
0x18000a362  mov     [rdi+10h], rax
0x18000a366  mov     rax, [rsp+140h+var_F0]
0x18000a36b  mov     [rdi+18h], rax
0x18000a36f  mov     rax, [rbp+40h+arg_0]
0x18000a373  mov     rax, [rax+rbx*8]
0x18000a377  and     dword ptr [rdi+2Ch], 0FFFFFFFEh
0x18000a37b  cmp     [rbp+40h+arg_20], dl
0x18000a37e  mov     [rdi+20h], rax
0x18000a382  mov     eax, edx
0x18000a384  setnz   al
0x18000a387  mov     [rdi+28h], r15d
0x18000a38b  or      [rdi+2Ch], eax
0x18000a38e  mov     [rdi+30h], ecx
0x18000a391  test    sil, sil
0x18000a394  jz      short loc_18000A3AE
0x18000a396  mov     rcx, rdi; hMem
0x18000a399  call    UserClientShutdownWorker
0x18000a39e  test    r13b, r13b
0x18000a3a1  jz      short loc_18000A407
0x18000a3a3  mov     rax, [rdi+10h]
0x18000a3a7  cmp     dword ptr [rax], 3
0x18000a3aa  jz      short loc_18000A412
0x18000a3ac  jmp     short loc_18000A407
0x18000a3ae  or      dword ptr [rdi+2Ch], 2
0x18000a3b2  lea     rax, UserClientShutdownWorker
0x18000a3b9  mov     [rsp+140h+Reserved8], rdx; Reserved8
0x18000a3be  xor     r9d, r9d; Reserved2
0x18000a3c1  mov     [rsp+140h+Reserved7], rdx; Reserved7
0x18000a3c6  xor     r8d, r8d; Reserved1
0x18000a3c9  mov     [rsp+140h+Reserved6], rdi; Reserved6
0x18000a3ce  or      rcx, 0FFFFFFFFFFFFFFFFh; ThreadContext
0x18000a3d2  mov     [rsp+140h+Reserved5], rax; Reserved5
0x18000a3d7  mov     [rsp+140h+Reserved4], rdx; Reserved4
0x18000a3dc  mov     qword ptr [rsp+140h+InitialState], rdx; Reserved3
0x18000a3e1  xor     edx, edx; OutThreadHandle
0x18000a3e3  call    cs:__imp_RtlCreateUserThread
0x18000a3ea  nop     dword ptr [rax+rax+00h]
0x18000a3ef  test    eax, eax
0x18000a3f1  jns     short loc_18000A407
0x18000a3f3  mov     rcx, rdi; hMem
0x18000a3f6  call    cs:__imp_LocalFree
0x18000a3fd  nop     dword ptr [rax+rax+00h]
0x18000a402  dec     ebx
0x18000a404  mov     sil, 1
0x18000a407  inc     ebx
0x18000a409  cmp     ebx, r12d
0x18000a40c  jb      loc_18000A30A
0x18000a412  mov     rcx, [rbp+40h+EventHandle]; Handle
0x18000a416  test    rcx, rcx
0x18000a419  jz      short loc_18000A43C
0x18000a41b  xor     r8d, r8d; Timeout
0x18000a41e  xor     edx, edx; Alertable
0x18000a420  call    cs:__imp_NtWaitForSingleObject
0x18000a427  nop     dword ptr [rax+rax+00h]
0x18000a42c  mov     rcx, [rbp+40h+EventHandle]; Handle
0x18000a430  call    cs:__imp_NtClose
0x18000a437  nop     dword ptr [rax+rax+00h]
0x18000a43c  cmp     [rbp+40h+Handle], 0
0x18000a441  jz      short loc_18000A47E
0x18000a443  mov     rcx, [rbp+40h+var_A0]; EventHandle
0x18000a447  xor     edx, edx; PreviousState
0x18000a449  or      [rbp+40h+var_80], 1
0x18000a44d  call    cs:__imp_NtSetEvent
0x18000a454  nop     dword ptr [rax+rax+00h]
0x18000a459  mov     rcx, [rbp+40h+Handle]; Handle
0x18000a45d  xor     r8d, r8d; Timeout
0x18000a460  xor     edx, edx; Alertable
0x18000a462  call    cs:__imp_NtWaitForSingleObject
0x18000a469  nop     dword ptr [rax+rax+00h]
0x18000a46e  mov     rcx, [rbp+40h+Handle]; Handle
0x18000a472  call    cs:__imp_NtClose
0x18000a479  nop     dword ptr [rax+rax+00h]
0x18000a47e  mov     rcx, [rbp+40h+var_90]; Handle
0x18000a482  test    rcx, rcx
0x18000a485  jz      short loc_18000A493
0x18000a487  call    cs:__imp_NtClose
0x18000a48e  nop     dword ptr [rax+rax+00h]
0x18000a493  mov     rcx, [rbp+40h+var_A0]; Handle
0x18000a497  test    rcx, rcx
0x18000a49a  jz      short loc_18000A4A8
0x18000a49c  call    cs:__imp_NtClose
0x18000a4a3  nop     dword ptr [rax+rax+00h]
0x18000a4a8  mov     rcx, [rbp+40h+var_98]; Handle
0x18000a4ac  test    rcx, rcx
0x18000a4af  jz      short loc_18000A4BD
0x18000a4b1  call    cs:__imp_NtClose
0x18000a4b8  nop     dword ptr [rax+rax+00h]
0x18000a4bd  lea     rcx, [rsp+140h+CriticalSection]; CriticalSection
0x18000a4c2  call    cs:__imp_RtlDeleteCriticalSection
0x18000a4c9  nop     dword ptr [rax+rax+00h]
0x18000a4ce  mov     rbx, [rsp+140h+arg_18]
0x18000a4d6  xor     eax, eax
0x18000a4d8  add     rsp, 110h
0x18000a4df  pop     r15
0x18000a4e1  pop     r14
0x18000a4e3  pop     r13
0x18000a4e5  pop     r12
0x18000a4e7  pop     rdi
0x18000a4e8  pop     rsi
0x18000a4e9  pop     rbp
0x18000a4ea  retn
```
