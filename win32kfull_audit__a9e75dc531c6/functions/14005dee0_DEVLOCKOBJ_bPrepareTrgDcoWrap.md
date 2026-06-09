# DEVLOCKOBJ_bPrepareTrgDcoWrap

- ea: `0x14005dee0`
- end: `0x14005e46d`
- name: `DEVLOCKOBJ_bPrepareTrgDcoWrap`
- size: `1421`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x14005da8c`
- `0x14005db98`
- `0x14005dee0`
- `0x140099c84`
- `0x14018cdb8`
- `0x14029fc18`
- `0x140343080`

## import_xrefs

- `ntoskrnl!KeIsAttachedProcess` at `0x14005e1ec`
- `ntoskrnl!KeIsAttachedProcess` at `0x14005e1ec`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14005e382`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14005e382`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005df88`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005e27c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005df88`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005e27c`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14005e374`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14005e391`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14005e374`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14005e391`
- `ntoskrnl!PsGetCurrentProcess` at `0x14005e365`
- `ntoskrnl!PsGetCurrentProcess` at `0x14005e365`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14005e1a7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14005e1a7`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14005e203`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14005e203`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005e15d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005e15d`
- `win32kbase!HmgPentryFromPobj` at `0x14005dfb0`
- `win32kbase!HmgPentryFromPobj` at `0x14005e2a3`
- `win32kbase!HmgPentryFromPobj` at `0x14005dfb0`
- `win32kbase!HmgPentryFromPobj` at `0x14005e2a3`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14005e236`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14005e407`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14005e407`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14005e1d7`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14005e1d7`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x14005e176`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x14005e176`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14005e2d9`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14005e2d9`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005dfd4`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005e2c1`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005dfd4`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005e2c1`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005e3da`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005e438`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005e3da`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005e438`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14005dfec`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14005dfec`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14005e354`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14005e354`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14005e33e`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14005e33e`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14005df45`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14005df45`
- `win32kbase!?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ` at `0x14005e088`
- `win32kbase!?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ` at `0x14005e088`

## pseudocode

```c
__int64 __fastcall DEVLOCKOBJ_bPrepareTrgDcoWrap(__int64 a1, __int64 *a2)
{
  unsigned int v4; // edi
  __int64 v6; // rdx
  __int64 v7; // r12
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int CurrentProcessId; // eax
  __int64 v12; // r15
  unsigned int v13; // r14d
  __int64 v14; // r13
  struct _DC_ATTR *UserAttr; // rax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rsi
  __int64 v20; // rsi
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned int v24; // r14d
  unsigned int v25; // eax
  __int64 v26; // rdx
  int v27; // ecx
  int v28; // ecx
  Gre::Base *v29; // rcx
  HSEMAPHORE v30; // rsi
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  struct _KTHREAD *CurrentThread; // r14
  __int64 ThreadWin32Thread; // rax
  _QWORD *v38; // rdx
  __int64 v40; // rax
  __int64 v41; // rax
  unsigned int v42; // eax
  __int64 v43; // rsi
  unsigned int v44; // edi
  __int64 v45; // r14
  struct _DC_ATTR *v46; // rax
  __int64 v47; // rax
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // edi
  __int64 CurrentThreadProcess; // rax

  v4 = 1;
  if ( !a2 )
    goto LABEL_2;
  v6 = *a2;
  if ( (*(_DWORD *)(v6 + 36) & 0x200) == 0 )
    goto LABEL_2;
  v7 = *(_QWORD *)(v6 + 48);
  v8 = HmgLock(*(_QWORD *)(a1 + 48), *(_QWORD *)v6, 1, 0);
  *(_QWORD *)(a1 + 32) = v8;
  if ( v8 )
  {
    if ( *(_DWORD *)(v8 + 2136) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)(v8 + 12));
      *(_QWORD *)(a1 + 32) = 0;
    }
  }
  else if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction(v9) != 1 )
  {
    GrepAuditBehaviorRestrictionViolations(1);
  }
  v10 = *(_QWORD *)(a1 + 32);
  if ( v10 )
  {
    if ( (*(_DWORD *)(v10 + 44) & 2) == 0 )
    {
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      v12 = *(_QWORD *)(a1 + 32);
      v13 = CurrentProcessId & 0xFFFFFFFC;
      if ( *(_QWORD *)v12 )
      {
        v14 = HmgPentryFromPobj(*(_QWORD *)(a1 + 48), *(_QWORD *)(a1 + 32));
      }
      else
      {
        v14 = v12 + 2152;
        *(_OWORD *)(v12 + 2152) = 0;
        *(_QWORD *)(v12 + 2168) = 0;
        *(_DWORD *)(v12 + 2160) = -2147483630;
        *(_QWORD *)(v12 + 2168) = GreEncodeUserModePointer(0);
      }
      if ( v13 == (*(_DWORD *)(v14 + 8) & 0xFFFFFFFE) )
      {
        UserAttr = DCOBJ::GetUserAttr((DCOBJ *)(a1 + 32));
        if ( UserAttr )
        {
          if ( !DC::SaveAttributes(*(DC **)(a1 + 32), UserAttr) )
          {
            _InterlockedDecrement16((volatile signed __int16 *)(*(_QWORD *)(a1 + 32) + 12LL));
            *(_QWORD *)(a1 + 32) = 0;
            goto LABEL_17;
          }
        }
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 32) + 44LL) |= 2u;
      *(_DWORD *)(a1 + 40) = 1;
    }
    v16 = *(_QWORD *)(a1 + 32);
    v17 = *(_DWORD *)(v16 + 520);
    if ( (v17 & 4) != 0 )
    {
      v25 = v17 & 0xFFFFFFFB;
      *(_DWORD *)(v16 + 520) = v25;
      v26 = *(_QWORD *)(v16 + 976);
      v27 = *(_DWORD *)(v26 + 340);
      if ( (v25 & 1) != 0 )
        v28 = v27 | 0x16090;
      else
        v28 = v27 | 0x6090;
      *(_DWORD *)(v26 + 340) = v28;
    }
  }
LABEL_17:
  v18 = *(_QWORD *)(a1 + 32);
  if ( !v18 || !*(_BYTE *)(a1 + 129) )
  {
LABEL_18:
    v4 = 0;
LABEL_2:
    *(_QWORD *)(a1 + 32) = 0;
    return v4;
  }
  if ( (*(_DWORD *)(*a2 + 36) & 0x4001) == 1 )
  {
    v47 = *(_QWORD *)(v7 + 1408);
    if ( v47 )
    {
      if ( !*(_QWORD *)(a1 + 136) )
      {
        *(_DWORD *)(v18 + 36) |= 0x4000u;
        DC::pSurface(*(DC **)(a1 + 32), (struct SURFACE *)(v47 - 24));
        *(_DWORD *)(a1 + 24) |= 0x10u;
      }
    }
  }
  if ( (*(_DWORD *)(a1 + 24) & 0x1000) != 0 )
  {
    v19 = *(_QWORD *)(a1 + 32);
    if ( v19 )
    {
      if ( *(_BYTE *)(a1 + 129) )
      {
        v20 = *(_QWORD *)(v19 + 496);
        if ( v20 )
        {
          v24 = SURFACE::Map(v20);
          if ( v24 <= 1 )
          {
            if ( (*(_DWORD *)(v20 + 144) & 0x800) != 0
              && *(_QWORD *)(v20 + 280)
              && (unsigned int)bHookRedir((struct XDCOBJ *)(a1 + 32), v21, v22, v23) )
            {
              *(_DWORD *)(a1 + 24) |= 0x400u;
            }
            if ( (*(_DWORD *)(v20 + 144) & 0x10) != 0
              && (unsigned int)bHookBmpDrv((struct XDCOBJ *)(a1 + 32), v21, v22, v23) )
            {
              *(_DWORD *)(a1 + 24) |= 0x2000u;
            }
            if ( v24 == 1 )
              *(_DWORD *)(a1 + 24) |= 0x40u;
            return v4;
          }
          if ( v24 != 2 )
            return v4;
          v29 = *(Gre::Base **)(a1 + 32);
          if ( v29
            && *(_BYTE *)(a1 + 129)
            && (*(_DWORD *)(a1 + 24) & 0x1000) != 0
            && (*((_DWORD *)v29 + 9) & 0x200) != 0 )
          {
            v30 = (HSEMAPHORE)(*(_QWORD *)Gre::Base::Globals(v29) + 728LL);
            GreAcquireSemaphoreSharedInternal(v30);
            GrepAcquireLockValidate<3>();
            if ( !*(_QWORD *)(a1 + 136) )
              DC::vClearRendering(*(DC **)(a1 + 32));
            if ( (*(_DWORD *)(*(_QWORD *)(a1 + 32) + 36LL) & 0x4000) == 0 )
            {
              CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v32, v31);
              if ( CurrentThreadWin32Thread )
              {
                v34 = *CurrentThreadWin32Thread;
                if ( v34 )
                {
                  v35 = v34 + 8;
                  if ( v35 )
                    *(_DWORD *)(v35 + 336) &= ~1u;
                }
              }
            }
            EtwTraceGreLockReleaseSemaphore(L"DCVisRgn", v30);
            CurrentThread = KeGetCurrentThread();
            if ( !(unsigned __int8)KeIsAttachedProcess()
              || (CurrentProcess = PsGetCurrentProcess(),
                  ProcessSessionId = PsGetProcessSessionIdEx(CurrentProcess),
                  CurrentThreadProcess = PsGetCurrentThreadProcess(),
                  ProcessSessionId == (unsigned int)PsGetProcessSessionIdEx(CurrentThreadProcess)) )
            {
              ThreadWin32Thread = PsGetThreadWin32Thread(CurrentThread);
              if ( ThreadWin32Thread )
              {
                if ( *(_QWORD *)ThreadWin32Thread )
                {
                  v38 = (_QWORD *)(*(_QWORD *)ThreadWin32Thread + 8LL);
                  if ( *(_QWORD *)ThreadWin32Thread != -8 )
                  {
                    if ( (*(_BYTE *)(*(_QWORD *)ThreadWin32Thread + 19LL))-- == 1 )
                      *v38 &= ~8uLL;
                    if ( !*v38 )
                      GrepOnAllLocksReleased();
                  }
                }
              }
            }
            ((void (__fastcall *)(HSEMAPHORE))GreReleaseSemaphoreSharedInternal)(v30);
          }
          v40 = *(_QWORD *)(a1 + 32);
          if ( v40 && *(_BYTE *)(a1 + 128) )
          {
            *(_DWORD *)(v40 + 40) &= ~2u;
            *(_BYTE *)(a1 + 128) = 0;
          }
          v41 = *(_QWORD *)(a1 + 32);
          if ( v41 )
          {
            if ( *(_DWORD *)(a1 + 40) && (*(_DWORD *)(v41 + 44) & 2) != 0 )
            {
              v42 = (unsigned int)PsGetCurrentProcessId();
              v43 = *(_QWORD *)(a1 + 32);
              v44 = v42 & 0xFFFFFFFC;
              if ( *(_QWORD *)v43 )
              {
                v45 = HmgPentryFromPobj(*(_QWORD *)(a1 + 48), *(_QWORD *)(a1 + 32));
              }
              else
              {
                v45 = v43 + 2152;
                *(_OWORD *)(v43 + 2152) = 0;
                *(_QWORD *)(v43 + 2168) = 0;
                *(_DWORD *)(v43 + 2160) = -2147483630;
                *(_QWORD *)(v43 + 2168) = GreEncodeUserModePointer(0);
              }
              if ( v44 == (*(_DWORD *)(v45 + 8) & 0xFFFFFFFE) )
              {
                v46 = DCOBJ::GetUserAttr((DCOBJ *)(a1 + 32));
                if ( v46 )
                  DC::RestoreAttributes(*(DC **)(a1 + 32), v46);
              }
              *(_DWORD *)(*(_QWORD *)(a1 + 32) + 44LL) &= ~2u;
              *(_DWORD *)(a1 + 40) = 0;
            }
            v4 = 0;
            _InterlockedDecrement16((volatile signed __int16 *)(*(_QWORD *)(a1 + 32) + 12LL));
            goto LABEL_2;
          }
          goto LABEL_18;
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14005dee0  mov     [rsp+arg_10], rbx
0x14005dee5  mov     [rsp+arg_18], rbp
0x14005deea  push    rsi
0x14005deeb  push    rdi
0x14005deec  push    r12
0x14005deee  push    r14
0x14005def0  push    r15
0x14005def2  sub     rsp, 20h
0x14005def6  xor     r15d, r15d
0x14005def9  mov     rsi, rdx
0x14005defc  mov     rbp, rcx
0x14005deff  mov     edi, 1
0x14005df04  test    rdx, rdx
0x14005df07  jnz     short loc_14005DF27
0x14005df09  mov     [rbp+20h], r15
0x14005df0d  mov     rbx, [rsp+48h+arg_10]
0x14005df12  mov     eax, edi
0x14005df14  mov     rbp, [rsp+48h+arg_18]
0x14005df19  add     rsp, 20h
0x14005df1d  pop     r15
0x14005df1f  pop     r14
0x14005df21  pop     r12
0x14005df23  pop     rdi
0x14005df24  pop     rsi
0x14005df25  retn
0x14005df27  mov     rdx, [rdx]
0x14005df2a  test    dword ptr [rdx+24h], 200h
0x14005df31  jz      short loc_14005DF09
0x14005df33  mov     r12, [rdx+30h]
0x14005df37  xor     r9d, r9d
0x14005df3a  mov     rdx, [rdx]
0x14005df3d  movzx   r8d, dil
0x14005df41  mov     rcx, [rcx+30h]
0x14005df45  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14005df4c  nop     dword ptr [rax+rax+00h]
0x14005df51  mov     [rbp+20h], rax
0x14005df55  test    rax, rax
0x14005df58  jz      loc_14005E33E
0x14005df5e  cmp     [rax+858h], r15d
0x14005df65  jnz     loc_14005E3AA
0x14005df6b  mov     rax, [rbp+20h]
0x14005df6f  test    rax, rax
0x14005df72  jz      loc_14005E020
0x14005df78  mov     eax, [rax+2Ch]
0x14005df7b  test    al, 2
0x14005df7d  jnz     loc_14005E00E
0x14005df83  mov     [rsp+48h+arg_0], r13
0x14005df88  call    cs:__imp_PsGetCurrentProcessId
0x14005df8f  nop     dword ptr [rax+rax+00h]
0x14005df94  mov     r15, [rbp+20h]
0x14005df98  mov     r14, rax
0x14005df9b  and     r14d, 0FFFFFFFCh
0x14005df9f  cmp     qword ptr [r15], 0
0x14005dfa3  jz      loc_14005E3B8
0x14005dfa9  mov     rcx, [rbp+30h]
0x14005dfad  mov     rdx, r15
0x14005dfb0  call    cs:__imp_HmgPentryFromPobj
0x14005dfb7  nop     dword ptr [rax+rax+00h]
0x14005dfbc  mov     r13, rax
0x14005dfbf  mov     eax, [r13+8]
0x14005dfc3  mov     r13, [rsp+48h+arg_0]
0x14005dfc8  and     eax, 0FFFFFFFEh
0x14005dfcb  cmp     r14d, eax
0x14005dfce  jnz     short loc_14005E000
0x14005dfd0  lea     rcx, [rbp+20h]
0x14005dfd4  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14005dfdb  nop     dword ptr [rax+rax+00h]
0x14005dfe0  test    rax, rax
0x14005dfe3  jz      short loc_14005E000
0x14005dfe5  mov     rcx, [rbp+20h]
0x14005dfe9  mov     rdx, rax
0x14005dfec  call    cs:__imp_?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x14005dff3  nop     dword ptr [rax+rax+00h]
0x14005dff8  test    eax, eax
0x14005dffa  jz      loc_14005E3F2
0x14005e000  mov     rax, [rbp+20h]
0x14005e004  or      dword ptr [rax+2Ch], 2
0x14005e008  xor     r15d, r15d
0x14005e00b  mov     [rbp+28h], edi
0x14005e00e  mov     rcx, [rbp+20h]
0x14005e012  mov     eax, [rcx+208h]
0x14005e018  test    al, 4
0x14005e01a  jnz     loc_14005E0CB
0x14005e020  mov     rdx, [rbp+20h]
0x14005e024  test    rdx, rdx
0x14005e027  jnz     short loc_14005E031
0x14005e029  mov     edi, r15d
0x14005e02c  jmp     loc_14005DF09
0x14005e031  cmp     byte ptr [rbp+81h], 0
0x14005e038  jz      short loc_14005E029
0x14005e03a  mov     rax, [rsi]
0x14005e03d  mov     ecx, [rax+24h]
0x14005e040  and     ecx, 4001h
0x14005e046  cmp     ecx, edi
0x14005e048  jz      loc_14005E302
0x14005e04e  test    dword ptr [rbp+18h], 1000h
0x14005e055  jz      loc_14005DF0D
0x14005e05b  mov     rsi, [rbp+20h]
0x14005e05f  test    rsi, rsi
0x14005e062  jz      loc_14005DF0D
0x14005e068  cmp     byte ptr [rbp+81h], 0
0x14005e06f  jz      loc_14005DF0D
0x14005e075  mov     rsi, [rsi+1F0h]
0x14005e07c  test    rsi, rsi
0x14005e07f  jz      loc_14005DF0D
0x14005e085  mov     rcx, rsi
0x14005e088  call    cs:__imp_?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ; SURFACE::Map(void)
0x14005e08f  nop     dword ptr [rax+rax+00h]
0x14005e094  mov     r14d, eax
0x14005e097  cmp     eax, edi
0x14005e099  ja      loc_14005E11F
0x14005e09f  test    dword ptr [rsi+90h], 800h
0x14005e0a9  jnz     short loc_14005E0F7
0x14005e0ab  mov     eax, [rsi+90h]
0x14005e0b1  test    al, 10h
0x14005e0b3  jnz     loc_14005E450
0x14005e0b9  cmp     r14d, edi
0x14005e0bc  jnz     loc_14005DF0D
0x14005e0c2  or      dword ptr [rbp+18h], 40h
0x14005e0c6  jmp     loc_14005DF0D
0x14005e0cb  and     eax, 0FFFFFFFBh
0x14005e0ce  mov     [rcx+208h], eax
0x14005e0d4  mov     rdx, [rcx+3D0h]
0x14005e0db  mov     ecx, [rdx+154h]
0x14005e0e1  test    dil, al
0x14005e0e4  jz      short loc_14005E117
0x14005e0e6  or      ecx, 16090h
0x14005e0ec  mov     [rdx+154h], ecx
0x14005e0f2  jmp     loc_14005E020
0x14005e0f7  cmp     qword ptr [rsi+118h], 0
0x14005e0ff  jz      short loc_14005E0AB
0x14005e101  lea     rcx, [rbp+20h]; struct XDCOBJ *
0x14005e105  call    ?bHookRedir@@YAHAEAVXDCOBJ@@@Z; bHookRedir(XDCOBJ &)
0x14005e10a  test    eax, eax
0x14005e10c  jz      short loc_14005E0AB
0x14005e10e  or      dword ptr [rbp+18h], 400h
0x14005e115  jmp     short loc_14005E0AB
0x14005e117  or      ecx, 6090h
0x14005e11d  jmp     short loc_14005E0EC
0x14005e11f  cmp     r14d, 2
0x14005e123  jnz     loc_14005DF0D
0x14005e129  mov     rcx, [rbp+20h]
0x14005e12d  test    rcx, rcx
0x14005e130  jz      loc_14005E245
0x14005e136  cmp     byte ptr [rbp+81h], 0
0x14005e13d  jz      loc_14005E245
0x14005e143  test    dword ptr [rbp+18h], 1000h
0x14005e14a  jz      loc_14005E245
0x14005e150  test    dword ptr [rcx+24h], 200h
0x14005e157  jz      loc_14005E245
0x14005e15d  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005e164  nop     dword ptr [rax+rax+00h]
0x14005e169  mov     rsi, [rax]
0x14005e16c  add     rsi, 2D8h
0x14005e173  mov     rcx, rsi
0x14005e176  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14005e17d  nop     dword ptr [rax+rax+00h]
0x14005e182  call    ??$GrepAcquireLockValidate@$02@@YAXXZ; GrepAcquireLockValidate<3>(void)
0x14005e187  cmp     qword ptr [rbp+88h], 0
0x14005e18f  jnz     short loc_14005E19A
0x14005e191  mov     rcx, [rbp+20h]; this
0x14005e195  call    ?vClearRendering@DC@@QEAAXXZ; DC::vClearRendering(void)
0x14005e19a  mov     rax, [rbp+20h]
0x14005e19e  test    dword ptr [rax+24h], 4000h
0x14005e1a5  jnz     short loc_14005E1CD
0x14005e1a7  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14005e1ae  nop     dword ptr [rax+rax+00h]
0x14005e1b3  test    rax, rax
0x14005e1b6  jz      short loc_14005E1CD
0x14005e1b8  mov     rax, [rax]
0x14005e1bb  test    rax, rax
0x14005e1be  jz      short loc_14005E1CD
0x14005e1c0  add     rax, 8
0x14005e1c4  jz      short loc_14005E1CD
0x14005e1c6  and     dword ptr [rax+150h], 0FFFFFFFEh
0x14005e1cd  mov     rdx, rsi
0x14005e1d0  lea     rcx, aDcvisrgn; "DCVisRgn"
0x14005e1d7  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x14005e1de  nop     dword ptr [rax+rax+00h]
0x14005e1e3  mov     r14, gs:188h
0x14005e1ec  call    cs:__imp_KeIsAttachedProcess
0x14005e1f3  nop     dword ptr [rax+rax+00h]
0x14005e1f8  test    al, al
0x14005e1fa  jnz     loc_14005E365
0x14005e200  mov     rcx, r14
0x14005e203  call    cs:__imp_PsGetThreadWin32Thread
0x14005e20a  nop     dword ptr [rax+rax+00h]
0x14005e20f  test    rax, rax
0x14005e212  jz      short loc_14005E236
0x14005e214  mov     rdx, [rax]
0x14005e217  test    rdx, rdx
0x14005e21a  jz      short loc_14005E236
0x14005e21c  add     rdx, 8
0x14005e220  jz      short loc_14005E236
0x14005e222  add     byte ptr [rdx+0Bh], 0FFh
0x14005e226  jnz     short loc_14005E22C
0x14005e228  and     qword ptr [rdx], 0FFFFFFFFFFFFFFF7h
0x14005e22c  cmp     qword ptr [rdx], 0
0x14005e230  jz      loc_14005E407
0x14005e236  mov     rax, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x14005e23d  mov     rcx, rsi
0x14005e240  call    _guard_dispatch_icall
0x14005e245  mov     rax, [rbp+20h]
0x14005e249  test    rax, rax
0x14005e24c  jz      short loc_14005E262
0x14005e24e  cmp     byte ptr [rbp+80h], 0
0x14005e255  jz      short loc_14005E262
0x14005e257  and     dword ptr [rax+28h], 0FFFFFFFDh
0x14005e25b  mov     byte ptr [rbp+80h], 0
0x14005e262  mov     rax, [rbp+20h]
0x14005e266  test    rax, rax
0x14005e269  jz      loc_14005E029
0x14005e26f  cmp     dword ptr [rbp+28h], 0
0x14005e273  jz      short loc_14005E2F1
0x14005e275  mov     eax, [rax+2Ch]
0x14005e278  test    al, 2
0x14005e27a  jz      short loc_14005E2F1
0x14005e27c  call    cs:__imp_PsGetCurrentProcessId
0x14005e283  nop     dword ptr [rax+rax+00h]
0x14005e288  mov     rsi, [rbp+20h]
0x14005e28c  mov     rdi, rax
0x14005e28f  and     edi, 0FFFFFFFCh
0x14005e292  cmp     qword ptr [rsi], 0
0x14005e296  jz      loc_14005E418
0x14005e29c  mov     rcx, [rbp+30h]
0x14005e2a0  mov     rdx, rsi
0x14005e2a3  call    cs:__imp_HmgPentryFromPobj
0x14005e2aa  nop     dword ptr [rax+rax+00h]
0x14005e2af  mov     r14, rax
0x14005e2b2  mov     eax, [r14+8]
0x14005e2b6  and     eax, 0FFFFFFFEh
0x14005e2b9  cmp     edi, eax
0x14005e2bb  jnz     short loc_14005E2E5
0x14005e2bd  lea     rcx, [rbp+20h]
0x14005e2c1  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14005e2c8  nop     dword ptr [rax+rax+00h]
0x14005e2cd  test    rax, rax
0x14005e2d0  jz      short loc_14005E2E5
0x14005e2d2  mov     rcx, [rbp+20h]
0x14005e2d6  mov     rdx, rax
0x14005e2d9  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x14005e2e0  nop     dword ptr [rax+rax+00h]
0x14005e2e5  mov     rax, [rbp+20h]
0x14005e2e9  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x14005e2ed  mov     [rbp+28h], r15d
0x14005e2f1  mov     rax, [rbp+20h]
0x14005e2f5  mov     edi, r15d
0x14005e2f8  lock dec word ptr [rax+0Ch]
0x14005e2fd  jmp     loc_14005DF09
0x14005e302  mov     rax, [r12+580h]
0x14005e30a  test    rax, rax
0x14005e30d  jz      loc_14005E04E
0x14005e313  cmp     qword ptr [rbp+88h], 0
0x14005e31b  jnz     loc_14005E04E
0x14005e321  or      dword ptr [rdx+24h], 4000h
0x14005e328  lea     rdx, [rax-18h]; struct SURFACE *
0x14005e32c  mov     rcx, [rbp+20h]; this
0x14005e330  call    ?pSurface@DC@@QEAAXPEAVSURFACE@@@Z; DC::pSurface(SURFACE *)
0x14005e335  or      dword ptr [rbp+18h], 10h
0x14005e339  jmp     loc_14005E04E
0x14005e33e  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x14005e345  nop     dword ptr [rax+rax+00h]
0x14005e34a  cmp     eax, edi
0x14005e34c  jz      loc_14005DF6B
0x14005e352  mov     ecx, edi
0x14005e354  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x14005e35b  nop     dword ptr [rax+rax+00h]
0x14005e360  jmp     loc_14005DF6B
0x14005e365  call    cs:__imp_PsGetCurrentProcess
0x14005e36c  nop     dword ptr [rax+rax+00h]
0x14005e371  mov     rcx, rax
0x14005e374  call    cs:__imp_PsGetProcessSessionIdEx
0x14005e37b  nop     dword ptr [rax+rax+00h]
0x14005e380  mov     edi, eax
0x14005e382  call    cs:__imp_PsGetCurrentThreadProcess
0x14005e389  nop     dword ptr [rax+rax+00h]
0x14005e38e  mov     rcx, rax
0x14005e391  call    cs:__imp_PsGetProcessSessionIdEx
0x14005e398  nop     dword ptr [rax+rax+00h]
0x14005e39d  cmp     edi, eax
0x14005e39f  jz      loc_14005E200
0x14005e3a5  jmp     loc_14005E236
0x14005e3aa  lock dec word ptr [rax+0Ch]
0x14005e3af  mov     [rbp+20h], r15
0x14005e3b3  jmp     loc_14005DF6B
0x14005e3b8  xorps   xmm0, xmm0
0x14005e3bb  lea     r13, [r15+868h]
0x14005e3c2  movups  xmmword ptr [r13+0], xmm0
0x14005e3c7  xor     eax, eax
0x14005e3c9  xor     ecx, ecx
0x14005e3cb  mov     [r13+10h], rax
0x14005e3cf  mov     dword ptr [r15+870h], 80000012h
0x14005e3da  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x14005e3e1  nop     dword ptr [rax+rax+00h]
0x14005e3e6  mov     [r15+878h], rax
0x14005e3ed  jmp     loc_14005DFBF
0x14005e3f2  mov     rax, [rbp+20h]
0x14005e3f6  lock dec word ptr [rax+0Ch]
0x14005e3fb  xor     r15d, r15d
0x14005e3fe  mov     [rbp+20h], r15
  ... truncated ...
```
