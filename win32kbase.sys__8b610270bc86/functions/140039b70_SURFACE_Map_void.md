# SURFACE::Map(void)

- ea: `0x140039b70`
- end: `0x140039f27`
- name: `?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14019b200`

## callees

- `0x14001cb30`
- `0x14001f570`
- `0x140039b70`
- `0x140039f5c`
- `0x14003a030`
- `0x14003a290`
- `0x14003a3a0`
- `0x14003a3c8`
- `0x14003a720`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140039d71`
- `ntoskrnl!PsGetCurrentProcess` at `0x140039d71`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140039c8c`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140039e13`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140039ec2`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140039c8c`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140039e13`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140039ec2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140039bd3`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140039bd3`
- `ntoskrnl!PsGetProcessId` at `0x140039e85`
- `ntoskrnl!PsGetProcessId` at `0x140039e85`
- `ntoskrnl!MmMapViewOfSection` at `0x140039db9`
- `ntoskrnl!MmMapViewOfSection` at `0x140039db9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039bff`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039c59`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039d02`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039bff`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039c59`
- `ntoskrnl!KeWaitForSingleObject` at `0x140039d02`
- `ntoskrnl!KeReleaseMutex` at `0x140039c35`
- `ntoskrnl!KeReleaseMutex` at `0x140039ce5`
- `ntoskrnl!KeReleaseMutex` at `0x140039c35`
- `ntoskrnl!KeReleaseMutex` at `0x140039ce5`
- `WIN32K!W32GetSessionState` at `0x140039c65`
- `WIN32K!W32GetSessionState` at `0x140039c65`

## pseudocode

```c
__int64 __fastcall SURFACE::Map(__int64 a1)
{
  __int64 v3; // r15
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rcx
  HSEMAPHORE v7; // rbx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v9; // r8
  _QWORD *v10; // rdx
  _QWORD *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdi
  int v14; // eax
  __int64 v15; // rdi
  __int64 v16; // rsi
  __int64 CurrentProcess; // rax
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // rax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  _QWORD *v23; // rax
  void *v24; // rdi
  unsigned int ProcessId; // eax
  __int64 v26; // rax
  __int64 v27; // rcx
  int v28; // r8d
  bool v29; // zf
  _QWORD v30[2]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v31[2]; // [rsp+60h] [rbp-20h] BYREF
  int v32; // [rsp+70h] [rbp-10h]
  __int64 v33; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v34; // [rsp+B8h] [rbp+38h] BYREF

  if ( !*(_QWORD *)(a1 + 296) && (*(_DWORD *)(a1 + 164) & 1) == 0
    || !_bittest16((const signed __int16 *)(a1 + 102), 0xBu) )
  {
    return 0;
  }
  v3 = a1 + 320;
  v4 = (unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC;
  while ( 1 )
  {
    KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(v3 + 40) + 64LL), UserRequest, 0, 0, 0);
    if ( !*(_DWORD *)v3 || *(_DWORD *)v3 == v4 )
      break;
    v12 = *(_QWORD *)(v3 + 40);
    ++*(_DWORD *)(v3 + 4);
    KeReleaseMutex(*(PRKMUTEX *)(v12 + 64), 0);
    KeWaitForSingleObject(*(PVOID *)(v3 + 40), UserRequest, 0, 0, 0);
  }
  v5 = ++*(_DWORD *)(v3 + 8);
  *(_DWORD *)v3 = v4;
  if ( v5 > *(_DWORD *)(v3 + 12) )
    *(_DWORD *)(v3 + 12) = v5;
  KeReleaseMutex(*(PRKMUTEX *)(*(_QWORD *)(v3 + 40) + 64LL), 0);
  KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(a1 + 360) + 64LL), UserRequest, 0, 0, 0);
  v7 = (HSEMAPHORE)(**(_QWORD **)(W32GetSessionState(v6) + 88) + 936LL);
  GreAcquireSemaphoreInternal(v7);
  GrepAcquireLockValidate<36>();
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
  v10 = (_QWORD *)CurrentProcessWin32Process;
  if ( CurrentProcessWin32Process )
    v10 = (_QWORD *)(-(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process);
  v11 = *(_QWORD **)(a1 + 312);
  if ( v11 == v10 )
  {
    if ( v7 )
      GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>((int)v11, v7, v9);
    return 1;
  }
  if ( v11 )
  {
    v23 = (_QWORD *)(a1 + 576);
    v11 = *(_QWORD **)(a1 + 576);
    if ( v11[1] != a1 + 576 )
      goto LABEL_31;
    v10 = *(_QWORD **)(a1 + 584);
    if ( (_QWORD *)*v10 != v23 )
      goto LABEL_31;
    *v10 = v11;
    v11[1] = v10;
    *(_QWORD *)(a1 + 584) = a1 + 576;
    *v23 = v23;
    v24 = *(void **)(a1 + 72);
    if ( v24 )
    {
      ProcessId = (unsigned int)PsGetProcessId(**(PEPROCESS **)(a1 + 312));
      Gre::MapViewOfSectionObj::Unmap(ProcessId, v24);
    }
  }
  v13 = 0;
  v14 = *(_DWORD *)(a1 + 164) & 1;
  if ( !v14 )
  {
    *(_QWORD *)(a1 + 72) = 0;
    *(_QWORD *)(a1 + 80) = 0;
  }
  *(_QWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 304) = 0;
  if ( v14 )
  {
LABEL_28:
    v20 = PsGetCurrentProcessWin32Process();
    if ( v20 )
      v20 &= -(__int64)(*(_QWORD *)v20 != 0);
    v21 = (_QWORD *)(v20 + 224);
    v22 = *(_QWORD *)(v20 + 224);
    if ( *(_QWORD *)(v22 + 8) != v20 + 224 )
LABEL_31:
      __fastfail(3u);
    *(_QWORD *)(a1 + 576) = v22;
    *(_QWORD *)(a1 + 584) = v21;
    *(_QWORD *)(v22 + 8) = a1 + 576;
    *v21 = a1 + 576;
    *(_QWORD *)(a1 + 304) = GreGetCurrentThread();
    v26 = PsGetCurrentProcessWin32Process();
    if ( v26 )
    {
      v27 = -*(_QWORD *)v26;
      v26 &= -(__int64)(*(_QWORD *)v26 != 0);
    }
    *(_QWORD *)(a1 + 312) = v26;
    if ( (*(_DWORD *)(a1 + 164) & 1) == 0 )
    {
      v29 = (*(_BYTE *)(a1 + 102) & 1) == 0;
      *(_QWORD *)(a1 + 72) = v13;
      if ( v29 )
      {
        v27 = v13 + (unsigned int)(*(_DWORD *)(a1 + 64) + *(_DWORD *)(a1 + 88));
        *(_QWORD *)(a1 + 80) = v27;
      }
      else
      {
        *(_QWORD *)(a1 + 80) = v13;
      }
    }
    if ( v7 )
      GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(v27, v7, v28);
    return 0;
  }
  v15 = *(unsigned int *)(a1 + 64);
  v32 = 6;
  v16 = *(_QWORD *)(a1 + 296);
  v30[1] = 0;
  v30[0] = 0;
  v31[0] = 0;
  v31[1] = 0;
  v34 = 0;
  v33 = 0;
  CurrentProcess = PsGetCurrentProcess(v11, v10, v9);
  if ( (int)MmMapViewOfSection(v16, CurrentProcess, v31, 0, v15, &v34, &v33, 2, 0x400000, 4) >= 0 )
  {
    v13 = v31[0];
    goto LABEL_28;
  }
  if ( v7 )
    GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(v18, v7, v19);
  W32PIDLOCK::vUnlockSingleThread((W32PIDLOCK *)v3);
  W32PIDLOCK::vUnlockSimple((W32PIDLOCK *)v3);
  if ( v32 != 6 )
    Gre::MapViewOfSectionObj::Unmap((Gre::MapViewOfSectionObj *)v30);
  return 2;
}

```

## disassembly

```asm
0x140039b70  mov     [rsp-28h+arg_10], rbx
0x140039b75  mov     [rsp-28h+arg_18], rsi
0x140039b7a  push    rbp
0x140039b7b  push    rdi
0x140039b7c  push    r12
0x140039b7e  push    r14
0x140039b80  push    r15
0x140039b82  mov     rbp, rsp
0x140039b85  sub     rsp, 80h
0x140039b8c  xor     r12d, r12d
0x140039b8f  mov     r14, rcx
0x140039b92  cmp     [rcx+128h], r12
0x140039b99  jnz     short loc_140039BC4
0x140039b9b  mov     eax, [rcx+0A4h]
0x140039ba1  test    al, 1
0x140039ba3  jnz     short loc_140039BC4
0x140039ba5  xor     eax, eax
0x140039ba7  lea     r11, [rsp+80h+var_s0]
0x140039baf  mov     rbx, [r11+40h]
0x140039bb3  mov     rsi, [r11+48h]
0x140039bb7  mov     rsp, r11
0x140039bba  pop     r15
0x140039bbc  pop     r14
0x140039bbe  pop     r12
0x140039bc0  pop     rdi
0x140039bc1  pop     rbp
0x140039bc2  retn
0x140039bc4  bt      word ptr [rcx+66h], 0Bh
0x140039bca  jnb     short loc_140039BA5
0x140039bcc  lea     r15, [rcx+140h]
0x140039bd3  call    cs:__imp_PsGetCurrentProcessId
0x140039bda  nop     dword ptr [rax+rax+00h]
0x140039bdf  mov     rbx, rax
0x140039be2  mov     esi, 6
0x140039be7  and     ebx, 0FFFFFFFCh
0x140039bea  mov     rcx, [r15+28h]
0x140039bee  xor     r9d, r9d; Alertable
0x140039bf1  xor     r8d, r8d; WaitMode
0x140039bf4  mov     [rsp+80h+Timeout], r12; Timeout
0x140039bf9  mov     edx, esi; WaitReason
0x140039bfb  mov     rcx, [rcx+40h]; Object
0x140039bff  call    cs:__imp_KeWaitForSingleObject
0x140039c06  nop     dword ptr [rax+rax+00h]
0x140039c0b  mov     eax, [r15]
0x140039c0e  test    eax, eax
0x140039c10  jnz     loc_140039CCF
0x140039c16  inc     dword ptr [r15+8]
0x140039c1a  mov     eax, [r15+8]
0x140039c1e  mov     [r15], ebx
0x140039c21  cmp     eax, [r15+0Ch]
0x140039c25  jle     short loc_140039C2B
0x140039c27  mov     [r15+0Ch], eax
0x140039c2b  mov     rcx, [r15+28h]
0x140039c2f  xor     edx, edx; Wait
0x140039c31  mov     rcx, [rcx+40h]; Mutex
0x140039c35  call    cs:__imp_KeReleaseMutex
0x140039c3c  nop     dword ptr [rax+rax+00h]
0x140039c41  mov     rcx, [r14+168h]
0x140039c48  xor     r9d, r9d; Alertable
0x140039c4b  xor     r8d, r8d; WaitMode
0x140039c4e  mov     [rsp+80h+Timeout], r12; Timeout
0x140039c53  mov     edx, esi; WaitReason
0x140039c55  mov     rcx, [rcx+40h]; Object
0x140039c59  call    cs:__imp_KeWaitForSingleObject
0x140039c60  nop     dword ptr [rax+rax+00h]
0x140039c65  call    cs:__imp_W32GetSessionState
0x140039c6c  nop     dword ptr [rax+rax+00h]
0x140039c71  mov     rcx, [rax+58h]
0x140039c75  mov     rbx, [rcx]
0x140039c78  add     rbx, 3A8h
0x140039c7f  mov     rcx, rbx; Resource
0x140039c82  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x140039c87  call    ??$GrepAcquireLockValidate@$0CE@@@YAXXZ; GrepAcquireLockValidate<36>(void)
0x140039c8c  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140039c93  nop     dword ptr [rax+rax+00h]
0x140039c98  mov     rdx, rax
0x140039c9b  test    rax, rax
0x140039c9e  jz      short loc_140039CAC
0x140039ca0  mov     rax, [rax]
0x140039ca3  neg     rax
0x140039ca6  sbb     rcx, rcx
0x140039ca9  and     rdx, rcx
0x140039cac  mov     rcx, [r14+138h]
0x140039cb3  cmp     rcx, rdx
0x140039cb6  jnz     short loc_140039D13
0x140039cb8  test    rbx, rbx
0x140039cbb  jz      short loc_140039CC5
0x140039cbd  mov     rdx, rbx
0x140039cc0  call    ??$GreReleaseSemaphoreCommon@$0CE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140039cc5  mov     eax, 1
0x140039cca  jmp     loc_140039BA7
0x140039ccf  cmp     eax, ebx
0x140039cd1  jz      loc_140039C16
0x140039cd7  mov     rcx, [r15+28h]
0x140039cdb  xor     edx, edx; Wait
0x140039cdd  inc     dword ptr [r15+4]
0x140039ce1  mov     rcx, [rcx+40h]; Mutex
0x140039ce5  call    cs:__imp_KeReleaseMutex
0x140039cec  nop     dword ptr [rax+rax+00h]
0x140039cf1  mov     rcx, [r15+28h]; Object
0x140039cf5  xor     r9d, r9d; Alertable
0x140039cf8  xor     r8d, r8d; WaitMode
0x140039cfb  mov     [rsp+80h+Timeout], r12; Timeout
0x140039d00  mov     edx, esi; WaitReason
0x140039d02  call    cs:__imp_KeWaitForSingleObject
0x140039d09  nop     dword ptr [rax+rax+00h]
0x140039d0e  jmp     loc_140039BEA
0x140039d13  test    rcx, rcx
0x140039d16  jnz     loc_140039E47
0x140039d1c  mov     eax, [r14+0A4h]
0x140039d23  mov     rdi, r12
0x140039d26  and     eax, 1
0x140039d29  jnz     short loc_140039D33
0x140039d2b  mov     [r14+48h], r12
0x140039d2f  mov     [r14+50h], r12
0x140039d33  mov     [r14+138h], r12
0x140039d3a  mov     [r14+130h], r12
0x140039d41  test    eax, eax
0x140039d43  jnz     loc_140039E13
0x140039d49  mov     edi, [r14+40h]
0x140039d4d  xor     eax, eax
0x140039d4f  mov     [rbp+var_10], esi
0x140039d52  mov     rsi, [r14+128h]
0x140039d59  mov     [rbp+var_28], rax
0x140039d5d  mov     [rbp+var_30], r12
0x140039d61  mov     [rbp+var_20], r12
0x140039d65  mov     [rbp+var_18], r12
0x140039d69  mov     [rbp+arg_8], r12
0x140039d6d  mov     [rbp+arg_0], r12
0x140039d71  call    cs:__imp_PsGetCurrentProcess
0x140039d78  nop     dword ptr [rax+rax+00h]
0x140039d7d  mov     [rsp+80h+var_38], 4
0x140039d85  lea     r8, [rbp+var_20]
0x140039d89  mov     [rsp+80h+var_40], 400000h
0x140039d91  mov     rdx, rax
0x140039d94  mov     [rsp+80h+var_48], 2
0x140039d9c  lea     rax, [rbp+arg_0]
0x140039da0  mov     [rsp+80h+var_50], rax
0x140039da5  xor     r9d, r9d
0x140039da8  lea     rax, [rbp+arg_8]
0x140039dac  mov     rcx, rsi
0x140039daf  mov     [rsp+80h+var_58], rax
0x140039db4  mov     [rsp+80h+Timeout], rdi
0x140039db9  call    cs:__imp_MmMapViewOfSection
0x140039dc0  nop     dword ptr [rax+rax+00h]
0x140039dc5  test    eax, eax
0x140039dc7  jns     short loc_140039E0F
0x140039dc9  test    rbx, rbx
0x140039dcc  jz      short loc_140039DD9
0x140039dce  mov     rdx, rbx
0x140039dd1  call    ??$GreReleaseSemaphoreCommon@$0CE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140039dd6  mov     rbx, r12
0x140039dd9  mov     rcx, r15; this
0x140039ddc  call    ?vUnlockSingleThread@W32PIDLOCK@@QEAAXXZ; W32PIDLOCK::vUnlockSingleThread(void)
0x140039de1  mov     rcx, r15; this
0x140039de4  call    ?vUnlockSimple@W32PIDLOCK@@QEAAXXZ; W32PIDLOCK::vUnlockSimple(void)
0x140039de9  cmp     [rbp+var_10], 6
0x140039ded  jz      short loc_140039E05
0x140039def  lea     rcx, [rbp+var_30]; this
0x140039df3  call    ?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ; Gre::MapViewOfSectionObj::Unmap(void)
0x140039df8  test    rbx, rbx
0x140039dfb  jz      short loc_140039E05
0x140039dfd  mov     rdx, rbx
0x140039e00  call    ??$GreReleaseSemaphoreCommon@$0CE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140039e05  mov     eax, 2
0x140039e0a  jmp     loc_140039BA7
0x140039e0f  mov     rdi, [rbp+var_20]
0x140039e13  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140039e1a  nop     dword ptr [rax+rax+00h]
0x140039e1f  test    rax, rax
0x140039e22  jz      short loc_140039E30
0x140039e24  mov     rcx, [rax]
0x140039e27  neg     rcx
0x140039e2a  sbb     rdx, rdx
0x140039e2d  and     rax, rdx
0x140039e30  lea     rcx, [rax+0E0h]
0x140039e37  mov     rdx, [rcx]
0x140039e3a  cmp     [rdx+8], rcx
0x140039e3e  jz      short loc_140039EA1
0x140039e40  mov     ecx, 3
0x140039e45  int     29h; Win8: RtlFailFast(ecx)
0x140039e47  lea     rax, [r14+240h]
0x140039e4e  mov     rcx, [rax]
0x140039e51  cmp     [rcx+8], rax
0x140039e55  jnz     short loc_140039E40
0x140039e57  mov     rdx, [rax+8]
0x140039e5b  cmp     [rdx], rax
0x140039e5e  jnz     short loc_140039E40
0x140039e60  mov     [rdx], rcx
0x140039e63  mov     [rcx+8], rdx
0x140039e67  mov     [rax+8], rax
0x140039e6b  mov     [rax], rax
0x140039e6e  mov     rdi, [r14+48h]
0x140039e72  test    rdi, rdi
0x140039e75  jz      loc_140039D1C
0x140039e7b  mov     rcx, [r14+138h]
0x140039e82  mov     rcx, [rcx]; Process
0x140039e85  call    cs:__imp_PsGetProcessId
0x140039e8c  nop     dword ptr [rax+rax+00h]
0x140039e91  mov     rcx, rax; unsigned int
0x140039e94  mov     rdx, rdi; void *
0x140039e97  call    ?Unmap@MapViewOfSectionObj@Gre@@SA_NKPEAX@Z; Gre::MapViewOfSectionObj::Unmap(ulong,void *)
0x140039e9c  jmp     loc_140039D1C
0x140039ea1  lea     rax, [r14+240h]
0x140039ea8  mov     [rax], rdx
0x140039eab  mov     [rax+8], rcx
0x140039eaf  mov     [rdx+8], rax
0x140039eb3  mov     [rcx], rax
0x140039eb6  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x140039ebb  mov     [r14+130h], rax
0x140039ec2  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140039ec9  nop     dword ptr [rax+rax+00h]
0x140039ece  test    rax, rax
0x140039ed1  jz      short loc_140039EDF
0x140039ed3  mov     rcx, [rax]
0x140039ed6  neg     rcx
0x140039ed9  sbb     rdx, rdx
0x140039edc  and     rax, rdx
0x140039edf  mov     [r14+138h], rax
0x140039ee6  mov     eax, [r14+0A4h]
0x140039eed  test    al, 1
0x140039eef  jnz     short loc_140039F00
0x140039ef1  test    byte ptr [r14+66h], 1
0x140039ef6  mov     [r14+48h], rdi
0x140039efa  jz      short loc_140039F16
0x140039efc  mov     [r14+50h], rdi
0x140039f00  test    rbx, rbx
0x140039f03  jz      loc_140039BA5
0x140039f09  mov     rdx, rbx
0x140039f0c  call    ??$GreReleaseSemaphoreCommon@$0CE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140039f11  jmp     loc_140039BA5
0x140039f16  mov     ecx, [r14+58h]
0x140039f1a  add     ecx, [r14+40h]
0x140039f1e  add     rcx, rdi
0x140039f21  mov     [r14+50h], rcx
0x140039f25  jmp     short loc_140039F00
```
