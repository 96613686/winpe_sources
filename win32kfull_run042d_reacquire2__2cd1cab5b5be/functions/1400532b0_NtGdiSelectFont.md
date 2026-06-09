# NtGdiSelectFont

- ea: `0x1400532b0`
- end: `0x1400536ca`
- name: `NtGdiSelectFont`
- size: `1050`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400532b0`
- `0x1400539b0`
- `0x14005b820`
- `0x1400a4e80`
- `0x140154d18`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140053364`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140053364`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400532d8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400536a3`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400532d8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400536a3`
- `win32kbase!HmgPentryFromPobj` at `0x14005338a`
- `win32kbase!HmgPentryFromPobj` at `0x140053468`
- `win32kbase!HmgPentryFromPobj` at `0x1400534f9`
- `win32kbase!HmgPentryFromPobj` at `0x14005338a`
- `win32kbase!HmgPentryFromPobj` at `0x140053468`
- `win32kbase!HmgPentryFromPobj` at `0x1400534f9`
- `win32kbase!HmgShareLock` at `0x1400534b0`
- `win32kbase!HmgShareLock` at `0x1400534b0`
- `win32kbase!PopThreadGuardedObject` at `0x14005358e`
- `win32kbase!PopThreadGuardedObject` at `0x14005358e`
- `win32kbase!PushThreadGuardedObject` at `0x14005330e`
- `win32kbase!PushThreadGuardedObject` at `0x14005340b`
- `win32kbase!PushThreadGuardedObject` at `0x1400534da`
- `win32kbase!PushThreadGuardedObject` at `0x14005330e`
- `win32kbase!PushThreadGuardedObject` at `0x14005340b`
- `win32kbase!PushThreadGuardedObject` at `0x1400534da`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x1400533a7`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x1400533a7`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140053634`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005368b`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140053634`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005368b`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x1400533bf`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x1400533bf`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x1400535e5`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x1400535e5`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x1400535d1`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x1400535d1`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14005332b`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14005332b`
- `win32kbase!DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT` at `0x14005351d`
- `win32kbase!DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT` at `0x1400536b5`
- `win32kbase!DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT` at `0x14005351d`
- `win32kbase!DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT` at `0x1400536b5`

## pseudocode

```c
__int64 __fastcall NtGdiSelectFont(Gre::Base *a1, __int64 a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  DC *v6; // rcx
  unsigned int CurrentProcessId; // eax
  DC *v8; // rdi
  unsigned int v9; // ebx
  char *v10; // rsi
  struct _DC_ATTR *UserAttr; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  DC *v14; // rdi
  __int64 v15; // rbx
  char *v16; // rsi
  __int64 v17; // r8
  __int64 *v18; // rcx
  struct Gre::Base::SESSION_GLOBALS *v19; // rsi
  Gre::Base *v20; // rcx
  struct LFONT *v21; // rdi
  __int64 v22; // rcx
  struct Gre::Base::SESSION_GLOBALS *v24; // rax
  DC *v25; // [rsp+20h] [rbp-79h] BYREF
  int v26; // [rsp+28h] [rbp-71h]
  struct Gre::Base::SESSION_GLOBALS *v27; // [rsp+30h] [rbp-69h]
  __int64 v28; // [rsp+38h] [rbp-61h]
  _OWORD v29[2]; // [rsp+40h] [rbp-59h] BYREF
  _OWORD v30[2]; // [rsp+60h] [rbp-39h] BYREF
  char v31; // [rsp+80h] [rbp-19h]
  __int64 v32; // [rsp+90h] [rbp-9h] BYREF
  _OWORD v33[5]; // [rsp+98h] [rbp-1h] BYREF

  v28 = 0;
  v27 = Gre::Base::Globals(a1);
  v25 = 0;
  v26 = 0;
  memset(v29, 0, sizeof(v29));
  PushThreadGuardedObject(
    v29,
    &v25,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  LOBYTE(v4) = 1;
  v5 = HmgLock(v27, a1, v4);
  v25 = (DC *)v5;
  v6 = (DC *)v5;
  if ( v5 )
  {
    if ( *(_DWORD *)(v5 + 2136) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)(v5 + 12));
      v6 = 0;
      v25 = 0;
    }
  }
  else
  {
    if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction(0) != 1 )
      GrepAuditBehaviorRestrictionViolations(1);
    v6 = v25;
  }
  if ( v6 )
  {
    if ( (*((_DWORD *)v6 + 11) & 2) == 0 )
    {
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      v8 = v25;
      v9 = CurrentProcessId & 0xFFFFFFFC;
      if ( *(_QWORD *)v25 )
      {
        v10 = (char *)HmgPentryFromPobj(v27, v25);
      }
      else
      {
        v10 = (char *)v25 + 2152;
        *(_OWORD *)((char *)v25 + 2152) = 0;
        *((_QWORD *)v8 + 271) = 0;
        *((_DWORD *)v8 + 540) = -2147483630;
        *((_QWORD *)v8 + 271) = GreEncodeUserModePointer(0);
      }
      if ( v9 == (*((_DWORD *)v10 + 2) & 0xFFFFFFFE) )
      {
        UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v25);
        if ( UserAttr )
        {
          if ( !DC::SaveAttributes(v25, UserAttr) )
          {
            _InterlockedDecrement16((volatile signed __int16 *)v25 + 6);
            v25 = 0;
            goto LABEL_14;
          }
        }
      }
      *((_DWORD *)v25 + 11) |= 2u;
      v6 = v25;
      v26 = 1;
    }
    if ( (*((_DWORD *)v6 + 130) & 4) != 0 )
      DC::vMarkTransformDirty(v6);
  }
LABEL_14:
  memset(v30, 0, sizeof(v30));
  PushThreadGuardedObject(v30, &v25, UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v31 = 1;
  if ( !v25 )
    goto LABEL_33;
  if ( *((_WORD *)v25 + 6) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v13, v12);
  if ( *((_WORD *)v25 + 6) != 1 )
    DCOBJ::vUnlock((DCOBJ *)&v25);
  v14 = v25;
  if ( !v25 )
  {
LABEL_33:
    v15 = 0;
    goto LABEL_32;
  }
  v15 = 0;
  if ( *(_QWORD *)v25 )
  {
    v16 = (char *)HmgPentryFromPobj(v27, v25);
  }
  else
  {
    v16 = (char *)v25 + 2152;
    *(_OWORD *)((char *)v25 + 2152) = 0;
    *((_QWORD *)v14 + 271) = 0;
    *((_DWORD *)v14 + 540) = -2147483630;
    *((_QWORD *)v14 + 271) = GreEncodeUserModePointer(0);
  }
  if ( (*((_DWORD *)v16 + 2) & 0xFFFFFFFE) != 0 )
  {
    v18 = (__int64 *)*((_QWORD *)v25 + 19);
    if ( v18 )
      v15 = *v18;
    if ( a2 != v15 )
    {
      v19 = v27;
      LOBYTE(v17) = 10;
      v32 = HmgShareLock(v27, a2, v17, 0);
      memset(v33, 0, 32);
      PushThreadGuardedObject(
        v33,
        &v32,
        UnexpectedThreadTerminationHandler<HmgShareLockResult<LFONT>>::OnUnexpectedThreadTerminationStatic);
      v21 = (struct LFONT *)v32;
      if ( v32 )
      {
        if ( (*(_BYTE *)(HmgPentryFromPobj(v19, v32) + 15) & 2) == 0 )
        {
          DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT(v19, *((struct LFONT **)v25 + 19));
          v22 = v32;
          v32 = 0;
          *((_QWORD *)v25 + 19) = v22;
          *(_QWORD *)(*((_QWORD *)v25 + 122) + 296LL) = a2;
          *((_QWORD *)v25 + 218) = 0;
          *(_DWORD *)(*((_QWORD *)v25 + 122) + 152LL) |= 0x10u;
          v20 = (Gre::Base *)*((_QWORD *)v25 + 122);
          *((_DWORD *)v20 + 38) &= ~0x20u;
          v21 = (struct LFONT *)v32;
LABEL_29:
          if ( v21 )
          {
            v24 = Gre::Base::Globals(v20);
            DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT(v24, v21);
            v32 = 0;
          }
          PopThreadGuardedObject(v33);
          goto LABEL_32;
        }
        v21 = (struct LFONT *)v32;
      }
      v15 = 0;
      goto LABEL_29;
    }
  }
LABEL_32:
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v25);
  return v15;
}

```

## disassembly

```asm
0x1400532b0  push    rbp
0x1400532b2  push    rbx
0x1400532b3  push    rsi
0x1400532b4  push    rdi
0x1400532b5  push    r12
0x1400532b7  push    r14
0x1400532b9  push    r15
0x1400532bb  lea     rbp, [rsp-27h]
0x1400532c0  sub     rsp, 0C0h
0x1400532c7  xor     r15d, r15d
0x1400532ca  mov     r14, rdx
0x1400532cd  mov     [rbp+57h+var_D0], r15
0x1400532d1  mov     rbx, rcx
0x1400532d4  mov     [rbp+57h+var_C8], r15d
0x1400532d8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400532df  nop     dword ptr [rax+rax+00h]
0x1400532e4  xorps   xmm0, xmm0
0x1400532e7  mov     [rbp+57h+var_B8], r15
0x1400532eb  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x1400532f2  mov     [rbp+57h+var_C0], rax
0x1400532f6  lea     rdx, [rbp+57h+var_D0]
0x1400532fa  mov     [rbp+57h+var_D0], r15
0x1400532fe  lea     rcx, [rbp+57h+var_B0]
0x140053302  mov     [rbp+57h+var_C8], r15d
0x140053306  movups  [rbp+57h+var_B0], xmm0
0x14005330a  movups  [rbp+57h+var_A0], xmm0
0x14005330e  call    cs:__imp_PushThreadGuardedObject
0x140053315  nop     dword ptr [rax+rax+00h]
0x14005331a  mov     rcx, [rbp+57h+var_C0]
0x14005331e  lea     r12d, [r15+1]
0x140053322  mov     r8b, r12b
0x140053325  xor     r9d, r9d
0x140053328  mov     rdx, rbx
0x14005332b  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140053332  nop     dword ptr [rax+rax+00h]
0x140053337  mov     [rbp+57h+var_D0], rax
0x14005333b  mov     rcx, rax
0x14005333e  test    rax, rax
0x140053341  jz      loc_1400535D1
0x140053347  cmp     [rax+858h], r15d
0x14005334e  jnz     loc_140053604
0x140053354  test    rcx, rcx
0x140053357  jz      loc_1400533F1
0x14005335d  mov     eax, [rcx+2Ch]
0x140053360  test    al, 2
0x140053362  jnz     short loc_1400533E3
0x140053364  call    cs:__imp_PsGetCurrentProcessId
0x14005336b  nop     dword ptr [rax+rax+00h]
0x140053370  mov     rdi, [rbp+57h+var_D0]
0x140053374  mov     rbx, rax
0x140053377  and     ebx, 0FFFFFFFCh
0x14005337a  cmp     [rdi], r15
0x14005337d  jz      loc_140053615
0x140053383  mov     rcx, [rbp+57h+var_C0]
0x140053387  mov     rdx, rdi
0x14005338a  call    cs:__imp_HmgPentryFromPobj
0x140053391  nop     dword ptr [rax+rax+00h]
0x140053396  mov     rsi, rax
0x140053399  mov     eax, [rsi+8]
0x14005339c  and     eax, 0FFFFFFFEh
0x14005339f  cmp     ebx, eax
0x1400533a1  jnz     short loc_1400533D3
0x1400533a3  lea     rcx, [rbp+57h+var_D0]
0x1400533a7  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x1400533ae  nop     dword ptr [rax+rax+00h]
0x1400533b3  test    rax, rax
0x1400533b6  jz      short loc_1400533D3
0x1400533b8  mov     rcx, [rbp+57h+var_D0]
0x1400533bc  mov     rdx, rax
0x1400533bf  call    cs:__imp_?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x1400533c6  nop     dword ptr [rax+rax+00h]
0x1400533cb  test    eax, eax
0x1400533cd  jz      loc_14005364C
0x1400533d3  mov     rax, [rbp+57h+var_D0]
0x1400533d7  or      dword ptr [rax+2Ch], 2
0x1400533db  mov     rcx, [rbp+57h+var_D0]; this
0x1400533df  mov     [rbp+57h+var_C8], r12d
0x1400533e3  mov     eax, [rcx+208h]
0x1400533e9  test    al, 4
0x1400533eb  jnz     loc_1400535C7
0x1400533f1  xorps   xmm0, xmm0
0x1400533f4  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x1400533fb  lea     rdx, [rbp+57h+var_D0]
0x1400533ff  lea     rcx, [rbp+57h+var_90]
0x140053403  movups  [rbp+57h+var_90], xmm0
0x140053407  movups  [rbp+57h+var_80], xmm0
0x14005340b  call    cs:__imp_PushThreadGuardedObject
0x140053412  nop     dword ptr [rax+rax+00h]
0x140053417  mov     rax, [rbp+57h+var_D0]
0x14005341b  mov     [rbp+57h+var_70], r12b
0x14005341f  test    rax, rax
0x140053422  jz      loc_1400535B9
0x140053428  movzx   eax, word ptr [rax+0Ch]
0x14005342c  cmp     ax, r12w
0x140053430  jnz     loc_1400535FA
0x140053436  mov     rax, [rbp+57h+var_D0]
0x14005343a  movzx   ecx, word ptr [rax+0Ch]
0x14005343e  cmp     cx, r12w
0x140053442  jnz     loc_14005365E
0x140053448  mov     rdi, [rbp+57h+var_D0]
0x14005344c  test    rdi, rdi
0x14005344f  jz      loc_1400535B9
0x140053455  mov     rbx, r15
0x140053458  cmp     [rdi], r15
0x14005345b  jz      loc_14005366C
0x140053461  mov     rcx, [rbp+57h+var_C0]
0x140053465  mov     rdx, rdi
0x140053468  call    cs:__imp_HmgPentryFromPobj
0x14005346f  nop     dword ptr [rax+rax+00h]
0x140053474  mov     rsi, rax
0x140053477  test    dword ptr [rsi+8], 0FFFFFFFEh
0x14005347e  jz      loc_14005359A
0x140053484  mov     rax, [rbp+57h+var_D0]
0x140053488  mov     rcx, [rax+98h]
0x14005348f  test    rcx, rcx
0x140053492  jz      short loc_140053497
0x140053494  mov     rbx, [rcx]
0x140053497  cmp     r14, rbx
0x14005349a  jz      loc_14005359A
0x1400534a0  mov     rsi, [rbp+57h+var_C0]
0x1400534a4  xor     r9d, r9d
0x1400534a7  mov     rcx, rsi
0x1400534aa  mov     r8b, 0Ah
0x1400534ad  mov     rdx, r14
0x1400534b0  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400534b7  nop     dword ptr [rax+rax+00h]
0x1400534bc  xorps   xmm0, xmm0
0x1400534bf  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgShareLockResult@VLFONT@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgShareLockResult<LFONT>>::OnUnexpectedThreadTerminationStatic(void *)
0x1400534c6  lea     rdx, [rbp+57h+var_60]
0x1400534ca  mov     [rbp+57h+var_60], rax
0x1400534ce  lea     rcx, [rbp+57h+var_58]
0x1400534d2  movups  [rbp+57h+var_58], xmm0
0x1400534d6  movups  [rbp+57h+var_48], xmm0
0x1400534da  call    cs:__imp_PushThreadGuardedObject
0x1400534e1  nop     dword ptr [rax+rax+00h]
0x1400534e6  mov     rdi, [rbp+57h+var_60]
0x1400534ea  test    rdi, rdi
0x1400534ed  jz      loc_1400535C2
0x1400534f3  mov     rdx, rdi
0x1400534f6  mov     rcx, rsi
0x1400534f9  call    cs:__imp_HmgPentryFromPobj
0x140053500  nop     dword ptr [rax+rax+00h]
0x140053505  test    byte ptr [rax+0Fh], 2
0x140053509  jnz     loc_1400535BE
0x14005350f  mov     rdx, [rbp+57h+var_D0]
0x140053513  mov     rcx, rsi
0x140053516  mov     rdx, [rdx+98h]
0x14005351d  call    cs:__imp_?DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT@@YAXAEAUSESSION_GLOBALS@Base@Gre@@PEAVLFONT@@@Z; DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT(Gre::Base::SESSION_GLOBALS &,LFONT *)
0x140053524  nop     dword ptr [rax+rax+00h]
0x140053529  mov     rcx, [rbp+57h+var_60]
0x14005352d  mov     rax, [rbp+57h+var_D0]
0x140053531  mov     [rbp+57h+var_60], r15
0x140053535  mov     [rax+98h], rcx
0x14005353c  mov     rax, [rbp+57h+var_D0]
0x140053540  mov     rcx, [rax+3D0h]
0x140053547  mov     [rcx+128h], r14
0x14005354e  mov     rax, [rbp+57h+var_D0]
0x140053552  mov     [rax+6D0h], r15
0x140053559  mov     rax, [rbp+57h+var_D0]
0x14005355d  mov     rcx, [rax+3D0h]
0x140053564  or      dword ptr [rcx+98h], 10h
0x14005356b  mov     rax, [rbp+57h+var_D0]
0x14005356f  mov     rcx, [rax+3D0h]
0x140053576  and     dword ptr [rcx+98h], 0FFFFFFDFh
0x14005357d  mov     rdi, [rbp+57h+var_60]
0x140053581  test    rdi, rdi
0x140053584  jnz     loc_1400536A3
0x14005358a  lea     rcx, [rbp+57h+var_58]
0x14005358e  call    cs:__imp_PopThreadGuardedObject
0x140053595  nop     dword ptr [rax+rax+00h]
0x14005359a  lea     rcx, [rbp+57h+var_D0]; this
0x14005359e  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x1400535a3  mov     rax, rbx
0x1400535a6  add     rsp, 0C0h
0x1400535ad  pop     r15
0x1400535af  pop     r14
0x1400535b1  pop     r12
0x1400535b3  pop     rdi
0x1400535b4  pop     rsi
0x1400535b5  pop     rbx
0x1400535b6  pop     rbp
0x1400535b7  retn
0x1400535b9  mov     rbx, r15
0x1400535bc  jmp     short loc_14005359A
0x1400535be  mov     rdi, [rbp+57h+var_60]
0x1400535c2  mov     rbx, r15
0x1400535c5  jmp     short loc_140053581
0x1400535c7  call    ?vMarkTransformDirty@DC@@QEAAXXZ; DC::vMarkTransformDirty(void)
0x1400535cc  jmp     loc_1400533F1
0x1400535d1  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x1400535d8  nop     dword ptr [rax+rax+00h]
0x1400535dd  cmp     eax, r12d
0x1400535e0  jz      short loc_1400535F1
0x1400535e2  mov     ecx, r12d
0x1400535e5  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x1400535ec  nop     dword ptr [rax+rax+00h]
0x1400535f1  mov     rcx, [rbp+57h+var_D0]
0x1400535f5  jmp     loc_140053354
0x1400535fa  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400535ff  jmp     loc_140053436
0x140053604  lock dec word ptr [rax+0Ch]
0x140053609  mov     rcx, r15
0x14005360c  mov     [rbp+57h+var_D0], rcx
0x140053610  jmp     loc_140053354
0x140053615  xorps   xmm0, xmm0
0x140053618  lea     rsi, [rdi+868h]
0x14005361f  movups  xmmword ptr [rsi], xmm0
0x140053622  xor     eax, eax
0x140053624  xor     ecx, ecx
0x140053626  mov     [rsi+10h], rax
0x14005362a  mov     dword ptr [rdi+870h], 80000012h
0x140053634  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x14005363b  nop     dword ptr [rax+rax+00h]
0x140053640  mov     [rdi+878h], rax
0x140053647  jmp     loc_140053399
0x14005364c  mov     rax, [rbp+57h+var_D0]
0x140053650  lock dec word ptr [rax+0Ch]
0x140053655  mov     [rbp+57h+var_D0], r15
0x140053659  jmp     loc_1400533F1
0x14005365e  lea     rcx, [rbp+57h+var_D0]; this
0x140053662  call    ?vUnlock@DCOBJ@@QEAAXXZ; DCOBJ::vUnlock(void)
0x140053667  jmp     loc_140053448
0x14005366c  xorps   xmm0, xmm0
0x14005366f  lea     rsi, [rdi+868h]
0x140053676  movups  xmmword ptr [rsi], xmm0
0x140053679  xor     eax, eax
0x14005367b  xor     ecx, ecx
0x14005367d  mov     [rsi+10h], rax
0x140053681  mov     dword ptr [rdi+870h], 80000012h
0x14005368b  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x140053692  nop     dword ptr [rax+rax+00h]
0x140053697  mov     [rdi+878h], rax
0x14005369e  jmp     loc_140053477
0x1400536a3  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400536aa  nop     dword ptr [rax+rax+00h]
0x1400536af  mov     rcx, rax
0x1400536b2  mov     rdx, rdi
0x1400536b5  call    cs:__imp_?DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT@@YAXAEAUSESSION_GLOBALS@Base@Gre@@PEAVLFONT@@@Z; DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT(Gre::Base::SESSION_GLOBALS &,LFONT *)
0x1400536bc  nop     dword ptr [rax+rax+00h]
0x1400536c1  mov     [rbp+57h+var_60], r15
0x1400536c5  jmp     loc_14005358A
```
