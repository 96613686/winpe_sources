# SURFACE::Map(void)

- ea: `0x14003b150`
- end: `0x14003b507`
- name: `?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ`
- size: `951`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140039f10`
- `0x14003b100`

## callees

- `0x1400324c0`
- `0x14003af40`
- `0x14003b150`
- `0x14003b53c`
- `0x14003b610`
- `0x14003b7b0`
- `0x14003b8c0`
- `0x14003b8e8`
- `0x140079f00`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14003b351`
- `ntoskrnl!PsGetCurrentProcess` at `0x14003b351`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14003b26c`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14003b3f3`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14003b4a2`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14003b26c`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14003b3f3`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14003b4a2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003b1b3`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003b1b3`
- `ntoskrnl!PsGetProcessId` at `0x14003b465`
- `ntoskrnl!PsGetProcessId` at `0x14003b465`
- `ntoskrnl!MmMapViewOfSection` at `0x14003b399`
- `ntoskrnl!MmMapViewOfSection` at `0x14003b399`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003b1df`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003b239`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003b2e2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003b1df`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003b239`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003b2e2`
- `ntoskrnl!KeReleaseMutex` at `0x14003b215`
- `ntoskrnl!KeReleaseMutex` at `0x14003b2c5`
- `ntoskrnl!KeReleaseMutex` at `0x14003b215`
- `ntoskrnl!KeReleaseMutex` at `0x14003b2c5`
- `WIN32K!W32GetSessionState` at `0x14003b245`
- `WIN32K!W32GetSessionState` at `0x14003b245`

## pseudocode

```c
__int64 __fastcall SURFACE::Map(__int64 a1)
{
  __int64 v3; // r15
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  struct _ERESOURCE *v10; // rbx
  __int64 v11; // rcx
  __int64 CurrentProcessWin32Process; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdi
  int v17; // eax
  __int64 v18; // rdi
  __int64 v19; // rsi
  __int64 CurrentProcess; // rax
  __int64 v21; // rax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  _QWORD *v24; // rax
  _QWORD *v25; // rdx
  void *v26; // rdi
  int ProcessId; // eax
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rcx
  bool v31; // zf
  _QWORD v32[2]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v33[2]; // [rsp+60h] [rbp-20h] BYREF
  int v34; // [rsp+70h] [rbp-10h]
  __int64 v35; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v36; // [rsp+B8h] [rbp+38h] BYREF

  if ( !*(_QWORD *)(a1 + 280) && (*(_DWORD *)(a1 + 148) & 1) == 0
    || !_bittest16((const signed __int16 *)(a1 + 102), 0xBu) )
  {
    return 0;
  }
  v3 = a1 + 304;
  v4 = (unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC;
  while ( 1 )
  {
    KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(v3 + 40) + 64LL), UserRequest, 0, 0, 0);
    if ( !*(_DWORD *)v3 || *(_DWORD *)v3 == v4 )
      break;
    v15 = *(_QWORD *)(v3 + 40);
    ++*(_DWORD *)(v3 + 4);
    KeReleaseMutex(*(PRKMUTEX *)(v15 + 64), 0);
    KeWaitForSingleObject(*(PVOID *)(v3 + 40), UserRequest, 0, 0, 0);
  }
  v5 = ++*(_DWORD *)(v3 + 8);
  *(_DWORD *)v3 = v4;
  if ( v5 > *(_DWORD *)(v3 + 12) )
    *(_DWORD *)(v3 + 12) = v5;
  KeReleaseMutex(*(PRKMUTEX *)(*(_QWORD *)(v3 + 40) + 64LL), 0);
  KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(a1 + 344) + 64LL), UserRequest, 0, 0, 0);
  v10 = (struct _ERESOURCE *)(**(_QWORD **)(W32GetSessionState(v7, v6, v8, v9) + 88) + 936LL);
  GreAcquireSemaphoreInternal(v10);
  GrepAcquireLockValidate<36>();
  CurrentProcessWin32Process = PsGetCurrentProcessWin32Process(v11);
  v13 = CurrentProcessWin32Process;
  if ( CurrentProcessWin32Process )
    v13 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0) & CurrentProcessWin32Process;
  v14 = *(_QWORD *)(a1 + 296);
  if ( v14 == v13 )
  {
    if ( v10 )
      GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(v14, v10);
    return 1;
  }
  if ( v14 )
  {
    v24 = (_QWORD *)(a1 + 560);
    v14 = *(_QWORD *)(a1 + 560);
    if ( *(_QWORD *)(v14 + 8) != a1 + 560 )
      goto LABEL_31;
    v25 = *(_QWORD **)(a1 + 568);
    if ( (_QWORD *)*v25 != v24 )
      goto LABEL_31;
    *v25 = v14;
    *(_QWORD *)(v14 + 8) = v25;
    *(_QWORD *)(a1 + 568) = a1 + 560;
    *v24 = v24;
    v26 = *(void **)(a1 + 72);
    if ( v26 )
    {
      ProcessId = (unsigned int)PsGetProcessId(**(PEPROCESS **)(a1 + 296));
      Gre::MapViewOfSectionObj::Unmap(ProcessId, v26);
    }
  }
  v16 = 0;
  v17 = *(_DWORD *)(a1 + 148) & 1;
  if ( !v17 )
  {
    *(_QWORD *)(a1 + 72) = 0;
    *(_QWORD *)(a1 + 80) = 0;
  }
  *(_QWORD *)(a1 + 296) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  if ( v17 )
  {
LABEL_28:
    v21 = PsGetCurrentProcessWin32Process(v14);
    if ( v21 )
      v21 &= -(__int64)(*(_QWORD *)v21 != 0);
    v22 = (_QWORD *)(v21 + 224);
    v23 = *(_QWORD *)(v21 + 224);
    if ( *(_QWORD *)(v23 + 8) != v21 + 224 )
LABEL_31:
      __fastfail(3u);
    *(_QWORD *)(a1 + 560) = v23;
    *(_QWORD *)(a1 + 568) = v22;
    *(_QWORD *)(v23 + 8) = a1 + 560;
    *v22 = a1 + 560;
    *(_QWORD *)(a1 + 288) = GreGetCurrentThread();
    v29 = PsGetCurrentProcessWin32Process(v28);
    if ( v29 )
    {
      v30 = -*(_QWORD *)v29;
      v29 &= -(__int64)(*(_QWORD *)v29 != 0);
    }
    *(_QWORD *)(a1 + 296) = v29;
    if ( (*(_DWORD *)(a1 + 148) & 1) == 0 )
    {
      v31 = (*(_BYTE *)(a1 + 102) & 1) == 0;
      *(_QWORD *)(a1 + 72) = v16;
      if ( v31 )
      {
        v30 = v16 + (unsigned int)(*(_DWORD *)(a1 + 64) + *(_DWORD *)(a1 + 88));
        *(_QWORD *)(a1 + 80) = v30;
      }
      else
      {
        *(_QWORD *)(a1 + 80) = v16;
      }
    }
    if ( v10 )
      GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(v30, v10);
    return 0;
  }
  v18 = *(unsigned int *)(a1 + 64);
  v34 = 6;
  v19 = *(_QWORD *)(a1 + 280);
  v32[1] = 0;
  v32[0] = 0;
  v33[0] = 0;
  v33[1] = 0;
  v36 = 0;
  v35 = 0;
  CurrentProcess = PsGetCurrentProcess(v14);
  if ( (int)MmMapViewOfSection(v19, CurrentProcess, v33, 0, v18, &v36, &v35, 2, 0x400000, 4) >= 0 )
  {
    v16 = v33[0];
    goto LABEL_28;
  }
  if ( v10 )
    GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(v14, v10);
  W32PIDLOCK::vUnlockSingleThread((W32PIDLOCK *)v3);
  W32PIDLOCK::vUnlockSimple((W32PIDLOCK *)v3);
  if ( v34 != 6 )
    Gre::MapViewOfSectionObj::Unmap((Gre::MapViewOfSectionObj *)v32);
  return 2;
}

```

## disassembly

```asm
0x14003b150  mov     [rsp-28h+arg_10], rbx
0x14003b155  mov     [rsp-28h+arg_18], rsi
0x14003b15a  push    rbp
0x14003b15b  push    rdi
0x14003b15c  push    r12
0x14003b15e  push    r14
0x14003b160  push    r15
0x14003b162  mov     rbp, rsp
0x14003b165  sub     rsp, 80h
0x14003b16c  xor     r12d, r12d
0x14003b16f  mov     r14, rcx
0x14003b172  cmp     [rcx+118h], r12
0x14003b179  jnz     short loc_14003B1A4
0x14003b17b  mov     eax, [rcx+94h]
0x14003b181  test    al, 1
0x14003b183  jnz     short loc_14003B1A4
0x14003b185  xor     eax, eax
0x14003b187  lea     r11, [rsp+80h+var_s0]
0x14003b18f  mov     rbx, [r11+40h]
0x14003b193  mov     rsi, [r11+48h]
0x14003b197  mov     rsp, r11
0x14003b19a  pop     r15
0x14003b19c  pop     r14
0x14003b19e  pop     r12
0x14003b1a0  pop     rdi
0x14003b1a1  pop     rbp
0x14003b1a2  retn
0x14003b1a4  bt      word ptr [rcx+66h], 0Bh
0x14003b1aa  jnb     short loc_14003B185
0x14003b1ac  lea     r15, [rcx+130h]
0x14003b1b3  call    cs:__imp_PsGetCurrentProcessId
0x14003b1ba  nop     dword ptr [rax+rax+00h]
0x14003b1bf  mov     rbx, rax
0x14003b1c2  mov     esi, 6
0x14003b1c7  and     ebx, 0FFFFFFFCh
0x14003b1ca  mov     rcx, [r15+28h]
0x14003b1ce  xor     r9d, r9d; Alertable
0x14003b1d1  xor     r8d, r8d; WaitMode
0x14003b1d4  mov     [rsp+80h+Timeout], r12; Timeout
0x14003b1d9  mov     edx, esi; WaitReason
0x14003b1db  mov     rcx, [rcx+40h]; Object
0x14003b1df  call    cs:__imp_KeWaitForSingleObject
0x14003b1e6  nop     dword ptr [rax+rax+00h]
0x14003b1eb  mov     eax, [r15]
0x14003b1ee  test    eax, eax
0x14003b1f0  jnz     loc_14003B2AF
0x14003b1f6  inc     dword ptr [r15+8]
0x14003b1fa  mov     eax, [r15+8]
0x14003b1fe  mov     [r15], ebx
0x14003b201  cmp     eax, [r15+0Ch]
0x14003b205  jle     short loc_14003B20B
0x14003b207  mov     [r15+0Ch], eax
0x14003b20b  mov     rcx, [r15+28h]
0x14003b20f  xor     edx, edx; Wait
0x14003b211  mov     rcx, [rcx+40h]; Mutex
0x14003b215  call    cs:__imp_KeReleaseMutex
0x14003b21c  nop     dword ptr [rax+rax+00h]
0x14003b221  mov     rcx, [r14+158h]
0x14003b228  xor     r9d, r9d; Alertable
0x14003b22b  xor     r8d, r8d; WaitMode
0x14003b22e  mov     [rsp+80h+Timeout], r12; Timeout
0x14003b233  mov     edx, esi; WaitReason
0x14003b235  mov     rcx, [rcx+40h]; Object
0x14003b239  call    cs:__imp_KeWaitForSingleObject
0x14003b240  nop     dword ptr [rax+rax+00h]
0x14003b245  call    cs:__imp_W32GetSessionState
0x14003b24c  nop     dword ptr [rax+rax+00h]
0x14003b251  mov     rcx, [rax+58h]
0x14003b255  mov     rbx, [rcx]
0x14003b258  add     rbx, 3A8h
0x14003b25f  mov     rcx, rbx; Resource
0x14003b262  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x14003b267  call    ??$GrepAcquireLockValidate@$0CE@@@YAXXZ; GrepAcquireLockValidate<36>(void)
0x14003b26c  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14003b273  nop     dword ptr [rax+rax+00h]
0x14003b278  mov     rdx, rax
0x14003b27b  test    rax, rax
0x14003b27e  jz      short loc_14003B28C
0x14003b280  mov     rax, [rax]
0x14003b283  neg     rax
0x14003b286  sbb     rcx, rcx
0x14003b289  and     rdx, rcx
0x14003b28c  mov     rcx, [r14+128h]
0x14003b293  cmp     rcx, rdx
0x14003b296  jnz     short loc_14003B2F3
0x14003b298  test    rbx, rbx
0x14003b29b  jz      short loc_14003B2A5
0x14003b29d  mov     rdx, rbx
0x14003b2a0  call    ??$GreReleaseSemaphoreCommon@$0CE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14003b2a5  mov     eax, 1
0x14003b2aa  jmp     loc_14003B187
0x14003b2af  cmp     eax, ebx
0x14003b2b1  jz      loc_14003B1F6
0x14003b2b7  mov     rcx, [r15+28h]
0x14003b2bb  xor     edx, edx; Wait
0x14003b2bd  inc     dword ptr [r15+4]
0x14003b2c1  mov     rcx, [rcx+40h]; Mutex
0x14003b2c5  call    cs:__imp_KeReleaseMutex
0x14003b2cc  nop     dword ptr [rax+rax+00h]
0x14003b2d1  mov     rcx, [r15+28h]; Object
0x14003b2d5  xor     r9d, r9d; Alertable
0x14003b2d8  xor     r8d, r8d; WaitMode
0x14003b2db  mov     [rsp+80h+Timeout], r12; Timeout
0x14003b2e0  mov     edx, esi; WaitReason
0x14003b2e2  call    cs:__imp_KeWaitForSingleObject
0x14003b2e9  nop     dword ptr [rax+rax+00h]
0x14003b2ee  jmp     loc_14003B1CA
0x14003b2f3  test    rcx, rcx
0x14003b2f6  jnz     loc_14003B427
0x14003b2fc  mov     eax, [r14+94h]
0x14003b303  mov     rdi, r12
0x14003b306  and     eax, 1
0x14003b309  jnz     short loc_14003B313
0x14003b30b  mov     [r14+48h], r12
0x14003b30f  mov     [r14+50h], r12
0x14003b313  mov     [r14+128h], r12
0x14003b31a  mov     [r14+120h], r12
0x14003b321  test    eax, eax
0x14003b323  jnz     loc_14003B3F3
0x14003b329  mov     edi, [r14+40h]
0x14003b32d  xor     eax, eax
0x14003b32f  mov     [rbp+var_10], esi
0x14003b332  mov     rsi, [r14+118h]
0x14003b339  mov     [rbp+var_28], rax
0x14003b33d  mov     [rbp+var_30], r12
0x14003b341  mov     [rbp+var_20], r12
0x14003b345  mov     [rbp+var_18], r12
0x14003b349  mov     [rbp+arg_8], r12
0x14003b34d  mov     [rbp+arg_0], r12
0x14003b351  call    cs:__imp_PsGetCurrentProcess
0x14003b358  nop     dword ptr [rax+rax+00h]
0x14003b35d  mov     [rsp+80h+var_38], 4
0x14003b365  lea     r8, [rbp+var_20]
0x14003b369  mov     [rsp+80h+var_40], 400000h
0x14003b371  mov     rdx, rax
0x14003b374  mov     [rsp+80h+var_48], 2
0x14003b37c  lea     rax, [rbp+arg_0]
0x14003b380  mov     [rsp+80h+var_50], rax
0x14003b385  xor     r9d, r9d
0x14003b388  lea     rax, [rbp+arg_8]
0x14003b38c  mov     rcx, rsi
0x14003b38f  mov     [rsp+80h+var_58], rax
0x14003b394  mov     [rsp+80h+Timeout], rdi
0x14003b399  call    cs:__imp_MmMapViewOfSection
0x14003b3a0  nop     dword ptr [rax+rax+00h]
0x14003b3a5  test    eax, eax
0x14003b3a7  jns     short loc_14003B3EF
0x14003b3a9  test    rbx, rbx
0x14003b3ac  jz      short loc_14003B3B9
0x14003b3ae  mov     rdx, rbx
0x14003b3b1  call    ??$GreReleaseSemaphoreCommon@$0CE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14003b3b6  mov     rbx, r12
0x14003b3b9  mov     rcx, r15; this
0x14003b3bc  call    ?vUnlockSingleThread@W32PIDLOCK@@QEAAXXZ; W32PIDLOCK::vUnlockSingleThread(void)
0x14003b3c1  mov     rcx, r15; this
0x14003b3c4  call    ?vUnlockSimple@W32PIDLOCK@@QEAAXXZ; W32PIDLOCK::vUnlockSimple(void)
0x14003b3c9  cmp     [rbp+var_10], 6
0x14003b3cd  jz      short loc_14003B3E5
0x14003b3cf  lea     rcx, [rbp+var_30]; this
0x14003b3d3  call    ?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ; Gre::MapViewOfSectionObj::Unmap(void)
0x14003b3d8  test    rbx, rbx
0x14003b3db  jz      short loc_14003B3E5
0x14003b3dd  mov     rdx, rbx
0x14003b3e0  call    ??$GreReleaseSemaphoreCommon@$0CE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14003b3e5  mov     eax, 2
0x14003b3ea  jmp     loc_14003B187
0x14003b3ef  mov     rdi, [rbp+var_20]
0x14003b3f3  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14003b3fa  nop     dword ptr [rax+rax+00h]
0x14003b3ff  test    rax, rax
0x14003b402  jz      short loc_14003B410
0x14003b404  mov     rcx, [rax]
0x14003b407  neg     rcx
0x14003b40a  sbb     rdx, rdx
0x14003b40d  and     rax, rdx
0x14003b410  lea     rcx, [rax+0E0h]
0x14003b417  mov     rdx, [rcx]
0x14003b41a  cmp     [rdx+8], rcx
0x14003b41e  jz      short loc_14003B481
0x14003b420  mov     ecx, 3
0x14003b425  int     29h; Win8: RtlFailFast(ecx)
0x14003b427  lea     rax, [r14+230h]
0x14003b42e  mov     rcx, [rax]
0x14003b431  cmp     [rcx+8], rax
0x14003b435  jnz     short loc_14003B420
0x14003b437  mov     rdx, [rax+8]
0x14003b43b  cmp     [rdx], rax
0x14003b43e  jnz     short loc_14003B420
0x14003b440  mov     [rdx], rcx
0x14003b443  mov     [rcx+8], rdx
0x14003b447  mov     [rax+8], rax
0x14003b44b  mov     [rax], rax
0x14003b44e  mov     rdi, [r14+48h]
0x14003b452  test    rdi, rdi
0x14003b455  jz      loc_14003B2FC
0x14003b45b  mov     rcx, [r14+128h]
0x14003b462  mov     rcx, [rcx]; Process
0x14003b465  call    cs:__imp_PsGetProcessId
0x14003b46c  nop     dword ptr [rax+rax+00h]
0x14003b471  mov     rcx, rax; unsigned int
0x14003b474  mov     rdx, rdi; void *
0x14003b477  call    ?Unmap@MapViewOfSectionObj@Gre@@SA_NKPEAX@Z; Gre::MapViewOfSectionObj::Unmap(ulong,void *)
0x14003b47c  jmp     loc_14003B2FC
0x14003b481  lea     rax, [r14+230h]
0x14003b488  mov     [rax], rdx
0x14003b48b  mov     [rax+8], rcx
0x14003b48f  mov     [rdx+8], rax
0x14003b493  mov     [rcx], rax
0x14003b496  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x14003b49b  mov     [r14+120h], rax
0x14003b4a2  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14003b4a9  nop     dword ptr [rax+rax+00h]
0x14003b4ae  test    rax, rax
0x14003b4b1  jz      short loc_14003B4BF
0x14003b4b3  mov     rcx, [rax]
0x14003b4b6  neg     rcx
0x14003b4b9  sbb     rdx, rdx
0x14003b4bc  and     rax, rdx
0x14003b4bf  mov     [r14+128h], rax
0x14003b4c6  mov     eax, [r14+94h]
0x14003b4cd  test    al, 1
0x14003b4cf  jnz     short loc_14003B4E0
0x14003b4d1  test    byte ptr [r14+66h], 1
0x14003b4d6  mov     [r14+48h], rdi
0x14003b4da  jz      short loc_14003B4F6
0x14003b4dc  mov     [r14+50h], rdi
0x14003b4e0  test    rbx, rbx
0x14003b4e3  jz      loc_14003B185
0x14003b4e9  mov     rdx, rbx
0x14003b4ec  call    ??$GreReleaseSemaphoreCommon@$0CE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x14003b4f1  jmp     loc_14003B185
0x14003b4f6  mov     ecx, [r14+58h]
0x14003b4fa  add     ecx, [r14+40h]
0x14003b4fe  add     rcx, rdi
0x14003b501  mov     [r14+50h], rcx
0x14003b505  jmp     short loc_14003B4E0
```
