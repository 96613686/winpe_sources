# DEVLOCKOBJ_bPrepareTrgDcoWrap

- ea: `0x140083c70`
- end: `0x1400841fd`
- name: `DEVLOCKOBJ_bPrepareTrgDcoWrap`
- size: `1421`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x14005f380`
- `0x140083c70`
- `0x1400845bc`
- `0x1400846c8`
- `0x14017fad8`
- `0x14029d748`
- `0x1403420d0`

## import_xrefs

- `ntoskrnl!KeIsAttachedProcess` at `0x140083f7c`
- `ntoskrnl!KeIsAttachedProcess` at `0x140083f7c`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140084112`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140084112`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140083d18`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14008400c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140083d18`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14008400c`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140084104`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140084121`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140084104`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140084121`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400840f5`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400840f5`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140083f37`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140083f37`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140083f93`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140083f93`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140083eed`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140083eed`
- `win32kbase!HmgPentryFromPobj` at `0x140083d40`
- `win32kbase!HmgPentryFromPobj` at `0x140084033`
- `win32kbase!HmgPentryFromPobj` at `0x140083d40`
- `win32kbase!HmgPentryFromPobj` at `0x140084033`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140083fc6`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x140084197`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x140084197`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140083f67`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140083f67`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140083f06`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140083f06`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x140084069`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x140084069`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140083d64`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140084051`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140083d64`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140084051`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14008416a`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x1400841c8`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14008416a`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x1400841c8`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x140083d7c`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x140083d7c`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x1400840e4`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x1400840e4`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x1400840ce`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x1400840ce`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140083cd5`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140083cd5`
- `win32kbase!?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ` at `0x140083e18`
- `win32kbase!?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ` at `0x140083e18`

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
  unsigned int v21; // r14d
  unsigned int v22; // eax
  __int64 v23; // rdx
  int v24; // ecx
  int v25; // ecx
  Gre::Base *v26; // rcx
  HSEMAPHORE v27; // rsi
  __int64 v28; // rcx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  struct _KTHREAD *CurrentThread; // r14
  __int64 ThreadWin32Thread; // rax
  _QWORD *v34; // rdx
  __int64 v36; // rax
  __int64 v37; // rax
  unsigned int v38; // eax
  __int64 v39; // rsi
  unsigned int v40; // edi
  __int64 v41; // r14
  struct _DC_ATTR *v42; // rax
  __int64 v43; // rax
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
      v22 = v17 & 0xFFFFFFFB;
      *(_DWORD *)(v16 + 520) = v22;
      v23 = *(_QWORD *)(v16 + 976);
      v24 = *(_DWORD *)(v23 + 340);
      if ( (v22 & 1) != 0 )
        v25 = v24 | 0x16090;
      else
        v25 = v24 | 0x6090;
      *(_DWORD *)(v23 + 340) = v25;
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
    v43 = *(_QWORD *)(v7 + 1408);
    if ( v43 )
    {
      if ( !*(_QWORD *)(a1 + 136) )
      {
        *(_DWORD *)(v18 + 36) |= 0x4000u;
        DC::pSurface(*(DC **)(a1 + 32), (struct SURFACE *)(v43 - 24));
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
          v21 = SURFACE::Map(v20);
          if ( v21 <= 1 )
          {
            if ( (*(_DWORD *)(v20 + 160) & 0x800) != 0
              && *(_QWORD *)(v20 + 296)
              && (unsigned int)bHookRedir((struct XDCOBJ *)(a1 + 32)) )
            {
              *(_DWORD *)(a1 + 24) |= 0x400u;
            }
            if ( (*(_DWORD *)(v20 + 160) & 0x10) != 0 && (unsigned int)bHookBmpDrv((struct XDCOBJ *)(a1 + 32)) )
              *(_DWORD *)(a1 + 24) |= 0x2000u;
            if ( v21 == 1 )
              *(_DWORD *)(a1 + 24) |= 0x40u;
            return v4;
          }
          if ( v21 != 2 )
            return v4;
          v26 = *(Gre::Base **)(a1 + 32);
          if ( v26
            && *(_BYTE *)(a1 + 129)
            && (*(_DWORD *)(a1 + 24) & 0x1000) != 0
            && (*((_DWORD *)v26 + 9) & 0x200) != 0 )
          {
            v27 = (HSEMAPHORE)(*(_QWORD *)Gre::Base::Globals(v26) + 728LL);
            GreAcquireSemaphoreSharedInternal(v27);
            GrepAcquireLockValidate<3>();
            if ( !*(_QWORD *)(a1 + 136) )
              DC::vClearRendering(*(DC **)(a1 + 32));
            if ( (*(_DWORD *)(*(_QWORD *)(a1 + 32) + 36LL) & 0x4000) == 0 )
            {
              CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v28);
              if ( CurrentThreadWin32Thread )
              {
                v30 = *CurrentThreadWin32Thread;
                if ( v30 )
                {
                  v31 = v30 + 8;
                  if ( v31 )
                    *(_DWORD *)(v31 + 336) &= ~1u;
                }
              }
            }
            EtwTraceGreLockReleaseSemaphore(L"DCVisRgn", v27);
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
                  v34 = (_QWORD *)(*(_QWORD *)ThreadWin32Thread + 8LL);
                  if ( *(_QWORD *)ThreadWin32Thread != -8 )
                  {
                    if ( (*(_BYTE *)(*(_QWORD *)ThreadWin32Thread + 19LL))-- == 1 )
                      *v34 &= ~8uLL;
                    if ( !*v34 )
                      GrepOnAllLocksReleased();
                  }
                }
              }
            }
            ((void (__fastcall *)(HSEMAPHORE))GreReleaseSemaphoreSharedInternal)(v27);
          }
          v36 = *(_QWORD *)(a1 + 32);
          if ( v36 && *(_BYTE *)(a1 + 128) )
          {
            *(_DWORD *)(v36 + 40) &= ~2u;
            *(_BYTE *)(a1 + 128) = 0;
          }
          v37 = *(_QWORD *)(a1 + 32);
          if ( v37 )
          {
            if ( *(_DWORD *)(a1 + 40) && (*(_DWORD *)(v37 + 44) & 2) != 0 )
            {
              v38 = (unsigned int)PsGetCurrentProcessId();
              v39 = *(_QWORD *)(a1 + 32);
              v40 = v38 & 0xFFFFFFFC;
              if ( *(_QWORD *)v39 )
              {
                v41 = HmgPentryFromPobj(*(_QWORD *)(a1 + 48), *(_QWORD *)(a1 + 32));
              }
              else
              {
                v41 = v39 + 2152;
                *(_OWORD *)(v39 + 2152) = 0;
                *(_QWORD *)(v39 + 2168) = 0;
                *(_DWORD *)(v39 + 2160) = -2147483630;
                *(_QWORD *)(v39 + 2168) = GreEncodeUserModePointer(0);
              }
              if ( v40 == (*(_DWORD *)(v41 + 8) & 0xFFFFFFFE) )
              {
                v42 = DCOBJ::GetUserAttr((DCOBJ *)(a1 + 32));
                if ( v42 )
                  DC::RestoreAttributes(*(DC **)(a1 + 32), v42);
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
0x140083c70  mov     [rsp+arg_10], rbx
0x140083c75  mov     [rsp+arg_18], rbp
0x140083c7a  push    rsi
0x140083c7b  push    rdi
0x140083c7c  push    r12
0x140083c7e  push    r14
0x140083c80  push    r15
0x140083c82  sub     rsp, 20h
0x140083c86  xor     r15d, r15d
0x140083c89  mov     rsi, rdx
0x140083c8c  mov     rbp, rcx
0x140083c8f  mov     edi, 1
0x140083c94  test    rdx, rdx
0x140083c97  jnz     short loc_140083CB7
0x140083c99  mov     [rbp+20h], r15
0x140083c9d  mov     rbx, [rsp+48h+arg_10]
0x140083ca2  mov     eax, edi
0x140083ca4  mov     rbp, [rsp+48h+arg_18]
0x140083ca9  add     rsp, 20h
0x140083cad  pop     r15
0x140083caf  pop     r14
0x140083cb1  pop     r12
0x140083cb3  pop     rdi
0x140083cb4  pop     rsi
0x140083cb5  retn
0x140083cb7  mov     rdx, [rdx]
0x140083cba  test    dword ptr [rdx+24h], 200h
0x140083cc1  jz      short loc_140083C99
0x140083cc3  mov     r12, [rdx+30h]
0x140083cc7  xor     r9d, r9d
0x140083cca  mov     rdx, [rdx]
0x140083ccd  movzx   r8d, dil
0x140083cd1  mov     rcx, [rcx+30h]
0x140083cd5  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140083cdc  nop     dword ptr [rax+rax+00h]
0x140083ce1  mov     [rbp+20h], rax
0x140083ce5  test    rax, rax
0x140083ce8  jz      loc_1400840CE
0x140083cee  cmp     [rax+858h], r15d
0x140083cf5  jnz     loc_14008413A
0x140083cfb  mov     rax, [rbp+20h]
0x140083cff  test    rax, rax
0x140083d02  jz      loc_140083DB0
0x140083d08  mov     eax, [rax+2Ch]
0x140083d0b  test    al, 2
0x140083d0d  jnz     loc_140083D9E
0x140083d13  mov     [rsp+48h+arg_0], r13
0x140083d18  call    cs:__imp_PsGetCurrentProcessId
0x140083d1f  nop     dword ptr [rax+rax+00h]
0x140083d24  mov     r15, [rbp+20h]
0x140083d28  mov     r14, rax
0x140083d2b  and     r14d, 0FFFFFFFCh
0x140083d2f  cmp     qword ptr [r15], 0
0x140083d33  jz      loc_140084148
0x140083d39  mov     rcx, [rbp+30h]
0x140083d3d  mov     rdx, r15
0x140083d40  call    cs:__imp_HmgPentryFromPobj
0x140083d47  nop     dword ptr [rax+rax+00h]
0x140083d4c  mov     r13, rax
0x140083d4f  mov     eax, [r13+8]
0x140083d53  mov     r13, [rsp+48h+arg_0]
0x140083d58  and     eax, 0FFFFFFFEh
0x140083d5b  cmp     r14d, eax
0x140083d5e  jnz     short loc_140083D90
0x140083d60  lea     rcx, [rbp+20h]
0x140083d64  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x140083d6b  nop     dword ptr [rax+rax+00h]
0x140083d70  test    rax, rax
0x140083d73  jz      short loc_140083D90
0x140083d75  mov     rcx, [rbp+20h]
0x140083d79  mov     rdx, rax
0x140083d7c  call    cs:__imp_?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x140083d83  nop     dword ptr [rax+rax+00h]
0x140083d88  test    eax, eax
0x140083d8a  jz      loc_140084182
0x140083d90  mov     rax, [rbp+20h]
0x140083d94  or      dword ptr [rax+2Ch], 2
0x140083d98  xor     r15d, r15d
0x140083d9b  mov     [rbp+28h], edi
0x140083d9e  mov     rcx, [rbp+20h]
0x140083da2  mov     eax, [rcx+208h]
0x140083da8  test    al, 4
0x140083daa  jnz     loc_140083E5B
0x140083db0  mov     rdx, [rbp+20h]
0x140083db4  test    rdx, rdx
0x140083db7  jnz     short loc_140083DC1
0x140083db9  mov     edi, r15d
0x140083dbc  jmp     loc_140083C99
0x140083dc1  cmp     byte ptr [rbp+81h], 0
0x140083dc8  jz      short loc_140083DB9
0x140083dca  mov     rax, [rsi]
0x140083dcd  mov     ecx, [rax+24h]
0x140083dd0  and     ecx, 4001h
0x140083dd6  cmp     ecx, edi
0x140083dd8  jz      loc_140084092
0x140083dde  test    dword ptr [rbp+18h], 1000h
0x140083de5  jz      loc_140083C9D
0x140083deb  mov     rsi, [rbp+20h]
0x140083def  test    rsi, rsi
0x140083df2  jz      loc_140083C9D
0x140083df8  cmp     byte ptr [rbp+81h], 0
0x140083dff  jz      loc_140083C9D
0x140083e05  mov     rsi, [rsi+1F0h]
0x140083e0c  test    rsi, rsi
0x140083e0f  jz      loc_140083C9D
0x140083e15  mov     rcx, rsi
0x140083e18  call    cs:__imp_?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ; SURFACE::Map(void)
0x140083e1f  nop     dword ptr [rax+rax+00h]
0x140083e24  mov     r14d, eax
0x140083e27  cmp     eax, edi
0x140083e29  ja      loc_140083EAF
0x140083e2f  test    dword ptr [rsi+0A0h], 800h
0x140083e39  jnz     short loc_140083E87
0x140083e3b  mov     eax, [rsi+0A0h]
0x140083e41  test    al, 10h
0x140083e43  jnz     loc_1400841E0
0x140083e49  cmp     r14d, edi
0x140083e4c  jnz     loc_140083C9D
0x140083e52  or      dword ptr [rbp+18h], 40h
0x140083e56  jmp     loc_140083C9D
0x140083e5b  and     eax, 0FFFFFFFBh
0x140083e5e  mov     [rcx+208h], eax
0x140083e64  mov     rdx, [rcx+3D0h]
0x140083e6b  mov     ecx, [rdx+154h]
0x140083e71  test    dil, al
0x140083e74  jz      short loc_140083EA7
0x140083e76  or      ecx, 16090h
0x140083e7c  mov     [rdx+154h], ecx
0x140083e82  jmp     loc_140083DB0
0x140083e87  cmp     qword ptr [rsi+128h], 0
0x140083e8f  jz      short loc_140083E3B
0x140083e91  lea     rcx, [rbp+20h]; struct XDCOBJ *
0x140083e95  call    ?bHookRedir@@YAHAEAVXDCOBJ@@@Z; bHookRedir(XDCOBJ &)
0x140083e9a  test    eax, eax
0x140083e9c  jz      short loc_140083E3B
0x140083e9e  or      dword ptr [rbp+18h], 400h
0x140083ea5  jmp     short loc_140083E3B
0x140083ea7  or      ecx, 6090h
0x140083ead  jmp     short loc_140083E7C
0x140083eaf  cmp     r14d, 2
0x140083eb3  jnz     loc_140083C9D
0x140083eb9  mov     rcx, [rbp+20h]
0x140083ebd  test    rcx, rcx
0x140083ec0  jz      loc_140083FD5
0x140083ec6  cmp     byte ptr [rbp+81h], 0
0x140083ecd  jz      loc_140083FD5
0x140083ed3  test    dword ptr [rbp+18h], 1000h
0x140083eda  jz      loc_140083FD5
0x140083ee0  test    dword ptr [rcx+24h], 200h
0x140083ee7  jz      loc_140083FD5
0x140083eed  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140083ef4  nop     dword ptr [rax+rax+00h]
0x140083ef9  mov     rsi, [rax]
0x140083efc  add     rsi, 2D8h
0x140083f03  mov     rcx, rsi
0x140083f06  call    cs:__imp_?GreAcquireSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreAcquireSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140083f0d  nop     dword ptr [rax+rax+00h]
0x140083f12  call    ??$GrepAcquireLockValidate@$02@@YAXXZ; GrepAcquireLockValidate<3>(void)
0x140083f17  cmp     qword ptr [rbp+88h], 0
0x140083f1f  jnz     short loc_140083F2A
0x140083f21  mov     rcx, [rbp+20h]; this
0x140083f25  call    ?vClearRendering@DC@@QEAAXXZ; DC::vClearRendering(void)
0x140083f2a  mov     rax, [rbp+20h]
0x140083f2e  test    dword ptr [rax+24h], 4000h
0x140083f35  jnz     short loc_140083F5D
0x140083f37  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140083f3e  nop     dword ptr [rax+rax+00h]
0x140083f43  test    rax, rax
0x140083f46  jz      short loc_140083F5D
0x140083f48  mov     rax, [rax]
0x140083f4b  test    rax, rax
0x140083f4e  jz      short loc_140083F5D
0x140083f50  add     rax, 8
0x140083f54  jz      short loc_140083F5D
0x140083f56  and     dword ptr [rax+150h], 0FFFFFFFEh
0x140083f5d  mov     rdx, rsi
0x140083f60  lea     rcx, aDcvisrgn; "DCVisRgn"
0x140083f67  call    cs:__imp_EtwTraceGreLockReleaseSemaphore
0x140083f6e  nop     dword ptr [rax+rax+00h]
0x140083f73  mov     r14, gs:188h
0x140083f7c  call    cs:__imp_KeIsAttachedProcess
0x140083f83  nop     dword ptr [rax+rax+00h]
0x140083f88  test    al, al
0x140083f8a  jnz     loc_1400840F5
0x140083f90  mov     rcx, r14
0x140083f93  call    cs:__imp_PsGetThreadWin32Thread
0x140083f9a  nop     dword ptr [rax+rax+00h]
0x140083f9f  test    rax, rax
0x140083fa2  jz      short loc_140083FC6
0x140083fa4  mov     rdx, [rax]
0x140083fa7  test    rdx, rdx
0x140083faa  jz      short loc_140083FC6
0x140083fac  add     rdx, 8
0x140083fb0  jz      short loc_140083FC6
0x140083fb2  add     byte ptr [rdx+0Bh], 0FFh
0x140083fb6  jnz     short loc_140083FBC
0x140083fb8  and     qword ptr [rdx], 0FFFFFFFFFFFFFFF7h
0x140083fbc  cmp     qword ptr [rdx], 0
0x140083fc0  jz      loc_140084197
0x140083fc6  mov     rax, cs:__imp_?GreReleaseSemaphoreSharedInternal@@YAXPEAUHSEMAPHORE__@@@Z; GreReleaseSemaphoreSharedInternal(HSEMAPHORE__ *)
0x140083fcd  mov     rcx, rsi
0x140083fd0  call    _guard_dispatch_icall
0x140083fd5  mov     rax, [rbp+20h]
0x140083fd9  test    rax, rax
0x140083fdc  jz      short loc_140083FF2
0x140083fde  cmp     byte ptr [rbp+80h], 0
0x140083fe5  jz      short loc_140083FF2
0x140083fe7  and     dword ptr [rax+28h], 0FFFFFFFDh
0x140083feb  mov     byte ptr [rbp+80h], 0
0x140083ff2  mov     rax, [rbp+20h]
0x140083ff6  test    rax, rax
0x140083ff9  jz      loc_140083DB9
0x140083fff  cmp     dword ptr [rbp+28h], 0
0x140084003  jz      short loc_140084081
0x140084005  mov     eax, [rax+2Ch]
0x140084008  test    al, 2
0x14008400a  jz      short loc_140084081
0x14008400c  call    cs:__imp_PsGetCurrentProcessId
0x140084013  nop     dword ptr [rax+rax+00h]
0x140084018  mov     rsi, [rbp+20h]
0x14008401c  mov     rdi, rax
0x14008401f  and     edi, 0FFFFFFFCh
0x140084022  cmp     qword ptr [rsi], 0
0x140084026  jz      loc_1400841A8
0x14008402c  mov     rcx, [rbp+30h]
0x140084030  mov     rdx, rsi
0x140084033  call    cs:__imp_HmgPentryFromPobj
0x14008403a  nop     dword ptr [rax+rax+00h]
0x14008403f  mov     r14, rax
0x140084042  mov     eax, [r14+8]
0x140084046  and     eax, 0FFFFFFFEh
0x140084049  cmp     edi, eax
0x14008404b  jnz     short loc_140084075
0x14008404d  lea     rcx, [rbp+20h]
0x140084051  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x140084058  nop     dword ptr [rax+rax+00h]
0x14008405d  test    rax, rax
0x140084060  jz      short loc_140084075
0x140084062  mov     rcx, [rbp+20h]
0x140084066  mov     rdx, rax
0x140084069  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x140084070  nop     dword ptr [rax+rax+00h]
0x140084075  mov     rax, [rbp+20h]
0x140084079  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x14008407d  mov     [rbp+28h], r15d
0x140084081  mov     rax, [rbp+20h]
0x140084085  mov     edi, r15d
0x140084088  lock dec word ptr [rax+0Ch]
0x14008408d  jmp     loc_140083C99
0x140084092  mov     rax, [r12+580h]
0x14008409a  test    rax, rax
0x14008409d  jz      loc_140083DDE
0x1400840a3  cmp     qword ptr [rbp+88h], 0
0x1400840ab  jnz     loc_140083DDE
0x1400840b1  or      dword ptr [rdx+24h], 4000h
0x1400840b8  lea     rdx, [rax-18h]; struct SURFACE *
0x1400840bc  mov     rcx, [rbp+20h]; this
0x1400840c0  call    ?pSurface@DC@@QEAAXPEAVSURFACE@@@Z; DC::pSurface(SURFACE *)
0x1400840c5  or      dword ptr [rbp+18h], 10h
0x1400840c9  jmp     loc_140083DDE
0x1400840ce  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x1400840d5  nop     dword ptr [rax+rax+00h]
0x1400840da  cmp     eax, edi
0x1400840dc  jz      loc_140083CFB
0x1400840e2  mov     ecx, edi
0x1400840e4  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x1400840eb  nop     dword ptr [rax+rax+00h]
0x1400840f0  jmp     loc_140083CFB
0x1400840f5  call    cs:__imp_PsGetCurrentProcess
0x1400840fc  nop     dword ptr [rax+rax+00h]
0x140084101  mov     rcx, rax
0x140084104  call    cs:__imp_PsGetProcessSessionIdEx
0x14008410b  nop     dword ptr [rax+rax+00h]
0x140084110  mov     edi, eax
0x140084112  call    cs:__imp_PsGetCurrentThreadProcess
0x140084119  nop     dword ptr [rax+rax+00h]
0x14008411e  mov     rcx, rax
0x140084121  call    cs:__imp_PsGetProcessSessionIdEx
0x140084128  nop     dword ptr [rax+rax+00h]
0x14008412d  cmp     edi, eax
0x14008412f  jz      loc_140083F90
0x140084135  jmp     loc_140083FC6
0x14008413a  lock dec word ptr [rax+0Ch]
0x14008413f  mov     [rbp+20h], r15
0x140084143  jmp     loc_140083CFB
0x140084148  xorps   xmm0, xmm0
0x14008414b  lea     r13, [r15+868h]
0x140084152  movups  xmmword ptr [r13+0], xmm0
0x140084157  xor     eax, eax
0x140084159  xor     ecx, ecx
0x14008415b  mov     [r13+10h], rax
0x14008415f  mov     dword ptr [r15+870h], 80000012h
0x14008416a  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x140084171  nop     dword ptr [rax+rax+00h]
0x140084176  mov     [r15+878h], rax
0x14008417d  jmp     loc_140083D4F
0x140084182  mov     rax, [rbp+20h]
0x140084186  lock dec word ptr [rax+0Ch]
0x14008418b  xor     r15d, r15d
0x14008418e  mov     [rbp+20h], r15
  ... truncated ...
```
