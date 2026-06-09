# SURFACE::Map(void)

- ea: `0x1400414b0`
- end: `0x140041867`
- name: `?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ`
- size: `951`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002ebe8`
- `0x140041460`

## callees

- `0x140025b50`
- `0x140028590`
- `0x1400414b0`
- `0x14004189c`
- `0x140041970`
- `0x140041bd0`
- `0x140041ce0`
- `0x140041d08`
- `0x140042060`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400416b1`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400416b1`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400415cc`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140041753`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140041802`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400415cc`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140041753`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140041802`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140041513`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140041513`
- `ntoskrnl!PsGetProcessId` at `0x1400417c5`
- `ntoskrnl!PsGetProcessId` at `0x1400417c5`
- `ntoskrnl!MmMapViewOfSection` at `0x1400416f9`
- `ntoskrnl!MmMapViewOfSection` at `0x1400416f9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004153f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140041599`
- `ntoskrnl!KeWaitForSingleObject` at `0x140041642`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004153f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140041599`
- `ntoskrnl!KeWaitForSingleObject` at `0x140041642`
- `ntoskrnl!KeReleaseMutex` at `0x140041575`
- `ntoskrnl!KeReleaseMutex` at `0x140041625`
- `ntoskrnl!KeReleaseMutex` at `0x140041575`
- `ntoskrnl!KeReleaseMutex` at `0x140041625`
- `WIN32K!W32GetSessionState` at `0x1400415a5`
- `WIN32K!W32GetSessionState` at `0x1400415a5`

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
0x1400414b0  mov     [rsp-28h+arg_10], rbx
0x1400414b5  mov     [rsp-28h+arg_18], rsi
0x1400414ba  push    rbp
0x1400414bb  push    rdi
0x1400414bc  push    r12
0x1400414be  push    r14
0x1400414c0  push    r15
0x1400414c2  mov     rbp, rsp
0x1400414c5  sub     rsp, 80h
0x1400414cc  xor     r12d, r12d
0x1400414cf  mov     r14, rcx
0x1400414d2  cmp     [rcx+128h], r12
0x1400414d9  jnz     short loc_140041504
0x1400414db  mov     eax, [rcx+0A4h]
0x1400414e1  test    al, 1
0x1400414e3  jnz     short loc_140041504
0x1400414e5  xor     eax, eax
0x1400414e7  lea     r11, [rsp+80h+var_s0]
0x1400414ef  mov     rbx, [r11+40h]
0x1400414f3  mov     rsi, [r11+48h]
0x1400414f7  mov     rsp, r11
0x1400414fa  pop     r15
0x1400414fc  pop     r14
0x1400414fe  pop     r12
0x140041500  pop     rdi
0x140041501  pop     rbp
0x140041502  retn
0x140041504  bt      word ptr [rcx+66h], 0Bh
0x14004150a  jnb     short loc_1400414E5
0x14004150c  lea     r15, [rcx+140h]
0x140041513  call    cs:__imp_PsGetCurrentProcessId
0x14004151a  nop     dword ptr [rax+rax+00h]
0x14004151f  mov     rbx, rax
0x140041522  mov     esi, 6
0x140041527  and     ebx, 0FFFFFFFCh
0x14004152a  mov     rcx, [r15+28h]
0x14004152e  xor     r9d, r9d; Alertable
0x140041531  xor     r8d, r8d; WaitMode
0x140041534  mov     [rsp+80h+Timeout], r12; Timeout
0x140041539  mov     edx, esi; WaitReason
0x14004153b  mov     rcx, [rcx+40h]; Object
0x14004153f  call    cs:__imp_KeWaitForSingleObject
0x140041546  nop     dword ptr [rax+rax+00h]
0x14004154b  mov     eax, [r15]
0x14004154e  test    eax, eax
0x140041550  jnz     loc_14004160F
0x140041556  inc     dword ptr [r15+8]
0x14004155a  mov     eax, [r15+8]
0x14004155e  mov     [r15], ebx
0x140041561  cmp     eax, [r15+0Ch]
0x140041565  jle     short loc_14004156B
0x140041567  mov     [r15+0Ch], eax
0x14004156b  mov     rcx, [r15+28h]
0x14004156f  xor     edx, edx; Wait
0x140041571  mov     rcx, [rcx+40h]; Mutex
0x140041575  call    cs:__imp_KeReleaseMutex
0x14004157c  nop     dword ptr [rax+rax+00h]
0x140041581  mov     rcx, [r14+168h]
0x140041588  xor     r9d, r9d; Alertable
0x14004158b  xor     r8d, r8d; WaitMode
0x14004158e  mov     [rsp+80h+Timeout], r12; Timeout
0x140041593  mov     edx, esi; WaitReason
0x140041595  mov     rcx, [rcx+40h]; Object
0x140041599  call    cs:__imp_KeWaitForSingleObject
0x1400415a0  nop     dword ptr [rax+rax+00h]
0x1400415a5  call    cs:__imp_W32GetSessionState
0x1400415ac  nop     dword ptr [rax+rax+00h]
0x1400415b1  mov     rcx, [rax+58h]
0x1400415b5  mov     rbx, [rcx]
0x1400415b8  add     rbx, 3A8h
0x1400415bf  mov     rcx, rbx; Resource
0x1400415c2  call    ?GreAcquireSemaphoreInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreInternal(HSEMAPHORE__ *)
0x1400415c7  call    ??$GrepAcquireLockValidate@$0CE@@@YAXXZ; GrepAcquireLockValidate<36>(void)
0x1400415cc  call    cs:__imp_PsGetCurrentProcessWin32Process
0x1400415d3  nop     dword ptr [rax+rax+00h]
0x1400415d8  mov     rdx, rax
0x1400415db  test    rax, rax
0x1400415de  jz      short loc_1400415EC
0x1400415e0  mov     rax, [rax]
0x1400415e3  neg     rax
0x1400415e6  sbb     rcx, rcx
0x1400415e9  and     rdx, rcx
0x1400415ec  mov     rcx, [r14+138h]
0x1400415f3  cmp     rcx, rdx
0x1400415f6  jnz     short loc_140041653
0x1400415f8  test    rbx, rbx
0x1400415fb  jz      short loc_140041605
0x1400415fd  mov     rdx, rbx
0x140041600  call    ??$GreReleaseSemaphoreCommon@$0CE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140041605  mov     eax, 1
0x14004160a  jmp     loc_1400414E7
0x14004160f  cmp     eax, ebx
0x140041611  jz      loc_140041556
0x140041617  mov     rcx, [r15+28h]
0x14004161b  xor     edx, edx; Wait
0x14004161d  inc     dword ptr [r15+4]
0x140041621  mov     rcx, [rcx+40h]; Mutex
0x140041625  call    cs:__imp_KeReleaseMutex
0x14004162c  nop     dword ptr [rax+rax+00h]
0x140041631  mov     rcx, [r15+28h]; Object
0x140041635  xor     r9d, r9d; Alertable
0x140041638  xor     r8d, r8d; WaitMode
0x14004163b  mov     [rsp+80h+Timeout], r12; Timeout
0x140041640  mov     edx, esi; WaitReason
0x140041642  call    cs:__imp_KeWaitForSingleObject
0x140041649  nop     dword ptr [rax+rax+00h]
0x14004164e  jmp     loc_14004152A
0x140041653  test    rcx, rcx
0x140041656  jnz     loc_140041787
0x14004165c  mov     eax, [r14+0A4h]
0x140041663  mov     rdi, r12
0x140041666  and     eax, 1
0x140041669  jnz     short loc_140041673
0x14004166b  mov     [r14+48h], r12
0x14004166f  mov     [r14+50h], r12
0x140041673  mov     [r14+138h], r12
0x14004167a  mov     [r14+130h], r12
0x140041681  test    eax, eax
0x140041683  jnz     loc_140041753
0x140041689  mov     edi, [r14+40h]
0x14004168d  xor     eax, eax
0x14004168f  mov     [rbp+var_10], esi
0x140041692  mov     rsi, [r14+128h]
0x140041699  mov     [rbp+var_28], rax
0x14004169d  mov     [rbp+var_30], r12
0x1400416a1  mov     [rbp+var_20], r12
0x1400416a5  mov     [rbp+var_18], r12
0x1400416a9  mov     [rbp+arg_8], r12
0x1400416ad  mov     [rbp+arg_0], r12
0x1400416b1  call    cs:__imp_PsGetCurrentProcess
0x1400416b8  nop     dword ptr [rax+rax+00h]
0x1400416bd  mov     [rsp+80h+var_38], 4
0x1400416c5  lea     r8, [rbp+var_20]
0x1400416c9  mov     [rsp+80h+var_40], 400000h
0x1400416d1  mov     rdx, rax
0x1400416d4  mov     [rsp+80h+var_48], 2
0x1400416dc  lea     rax, [rbp+arg_0]
0x1400416e0  mov     [rsp+80h+var_50], rax
0x1400416e5  xor     r9d, r9d
0x1400416e8  lea     rax, [rbp+arg_8]
0x1400416ec  mov     rcx, rsi
0x1400416ef  mov     [rsp+80h+var_58], rax
0x1400416f4  mov     [rsp+80h+Timeout], rdi
0x1400416f9  call    cs:__imp_MmMapViewOfSection
0x140041700  nop     dword ptr [rax+rax+00h]
0x140041705  test    eax, eax
0x140041707  jns     short loc_14004174F
0x140041709  test    rbx, rbx
0x14004170c  jz      short loc_140041719
0x14004170e  mov     rdx, rbx
0x140041711  call    ??$GreReleaseSemaphoreCommon@$0CE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140041716  mov     rbx, r12
0x140041719  mov     rcx, r15; this
0x14004171c  call    ?vUnlockSingleThread@W32PIDLOCK@@QEAAXXZ; W32PIDLOCK::vUnlockSingleThread(void)
0x140041721  mov     rcx, r15; this
0x140041724  call    ?vUnlockSimple@W32PIDLOCK@@QEAAXXZ; W32PIDLOCK::vUnlockSimple(void)
0x140041729  cmp     [rbp+var_10], 6
0x14004172d  jz      short loc_140041745
0x14004172f  lea     rcx, [rbp+var_30]; this
0x140041733  call    ?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ; Gre::MapViewOfSectionObj::Unmap(void)
0x140041738  test    rbx, rbx
0x14004173b  jz      short loc_140041745
0x14004173d  mov     rdx, rbx
0x140041740  call    ??$GreReleaseSemaphoreCommon@$0CE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140041745  mov     eax, 2
0x14004174a  jmp     loc_1400414E7
0x14004174f  mov     rdi, [rbp+var_20]
0x140041753  call    cs:__imp_PsGetCurrentProcessWin32Process
0x14004175a  nop     dword ptr [rax+rax+00h]
0x14004175f  test    rax, rax
0x140041762  jz      short loc_140041770
0x140041764  mov     rcx, [rax]
0x140041767  neg     rcx
0x14004176a  sbb     rdx, rdx
0x14004176d  and     rax, rdx
0x140041770  lea     rcx, [rax+0E0h]
0x140041777  mov     rdx, [rcx]
0x14004177a  cmp     [rdx+8], rcx
0x14004177e  jz      short loc_1400417E1
0x140041780  mov     ecx, 3
0x140041785  int     29h; Win8: RtlFailFast(ecx)
0x140041787  lea     rax, [r14+240h]
0x14004178e  mov     rcx, [rax]
0x140041791  cmp     [rcx+8], rax
0x140041795  jnz     short loc_140041780
0x140041797  mov     rdx, [rax+8]
0x14004179b  cmp     [rdx], rax
0x14004179e  jnz     short loc_140041780
0x1400417a0  mov     [rdx], rcx
0x1400417a3  mov     [rcx+8], rdx
0x1400417a7  mov     [rax+8], rax
0x1400417ab  mov     [rax], rax
0x1400417ae  mov     rdi, [r14+48h]
0x1400417b2  test    rdi, rdi
0x1400417b5  jz      loc_14004165C
0x1400417bb  mov     rcx, [r14+138h]
0x1400417c2  mov     rcx, [rcx]; Process
0x1400417c5  call    cs:__imp_PsGetProcessId
0x1400417cc  nop     dword ptr [rax+rax+00h]
0x1400417d1  mov     rcx, rax; unsigned int
0x1400417d4  mov     rdx, rdi; void *
0x1400417d7  call    ?Unmap@MapViewOfSectionObj@Gre@@SA_NKPEAX@Z; Gre::MapViewOfSectionObj::Unmap(ulong,void *)
0x1400417dc  jmp     loc_14004165C
0x1400417e1  lea     rax, [r14+240h]
0x1400417e8  mov     [rax], rdx
0x1400417eb  mov     [rax+8], rcx
0x1400417ef  mov     [rdx+8], rax
0x1400417f3  mov     [rcx], rax
0x1400417f6  call    ?GreGetCurrentThread@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThread(void)
0x1400417fb  mov     [r14+130h], rax
0x140041802  call    cs:__imp_PsGetCurrentProcessWin32Process
0x140041809  nop     dword ptr [rax+rax+00h]
0x14004180e  test    rax, rax
0x140041811  jz      short loc_14004181F
0x140041813  mov     rcx, [rax]
0x140041816  neg     rcx
0x140041819  sbb     rdx, rdx
0x14004181c  and     rax, rdx
0x14004181f  mov     [r14+138h], rax
0x140041826  mov     eax, [r14+0A4h]
0x14004182d  test    al, 1
0x14004182f  jnz     short loc_140041840
0x140041831  test    byte ptr [r14+66h], 1
0x140041836  mov     [r14+48h], rdi
0x14004183a  jz      short loc_140041856
0x14004183c  mov     [r14+50h], rdi
0x140041840  test    rbx, rbx
0x140041843  jz      loc_1400414E5
0x140041849  mov     rdx, rbx
0x14004184c  call    ??$GreReleaseSemaphoreCommon@$0CE@P6AXPEAUHSEMAPHORE__@@@Z@@YAXP6AXPEAUHSEMAPHORE__@@@Z0@Z; GreReleaseSemaphoreCommon<36,void (*)(HSEMAPHORE__ *)>(void (*)(HSEMAPHORE__ *),HSEMAPHORE__ *)
0x140041851  jmp     loc_1400414E5
0x140041856  mov     ecx, [r14+58h]
0x14004185a  add     ecx, [r14+40h]
0x14004185e  add     rcx, rdi
0x140041861  mov     [r14+50h], rcx
0x140041865  jmp     short loc_140041840
```
