# NtGdiExtSelectClipRgn

- ea: `0x140069c70`
- end: `0x14006a101`
- name: `NtGdiExtSelectClipRgn`
- size: `1169`
- prototype: `__int64 __fastcall(Gre::Base *, HRGN, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400539b0`
- `0x14005b820`
- `0x14005d010`
- `0x140066c94`
- `0x1400697e4`
- `0x140069bc8`
- `0x140069c70`
- `0x14006b938`
- `0x14006bd2c`
- `0x1400a4e80`
- `0x140154d18`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140069d4d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140069d4d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140069ca8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140069ca8`
- `win32kbase!HmgPentryFromPobj` at `0x140069d76`
- `win32kbase!HmgPentryFromPobj` at `0x140069e6d`
- `win32kbase!HmgPentryFromPobj` at `0x140069d76`
- `win32kbase!HmgPentryFromPobj` at `0x140069e6d`
- `win32kbase!PopThreadGuardedObject` at `0x140069f45`
- `win32kbase!PopThreadGuardedObject` at `0x140069f45`
- `win32kbase!PushThreadGuardedObject` at `0x140069cf1`
- `win32kbase!PushThreadGuardedObject` at `0x140069e00`
- `win32kbase!PushThreadGuardedObject` at `0x140069cf1`
- `win32kbase!PushThreadGuardedObject` at `0x140069e00`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140069d94`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140069d94`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14006a08b`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14006a0e9`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14006a08b`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14006a0e9`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x140069dad`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x140069dad`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14006a03b`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14006a03b`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14006a027`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14006a027`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140069d0f`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140069d0f`
- `win32kbase!EngSetLastError` at `0x140069f58`
- `win32kbase!EngSetLastError` at `0x14006a00f`
- `win32kbase!EngSetLastError` at `0x140069f58`
- `win32kbase!EngSetLastError` at `0x14006a00f`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140069ee1`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140069fcd`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140069ee1`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140069fcd`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140069e9f`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140069e9f`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x140069f27`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x140069f27`

## pseudocode

```c
__int64 __fastcall NtGdiExtSelectClipRgn(Gre::Base *a1, HRGN a2, int a3)
{
  __int64 v6; // r8
  __int64 v7; // rax
  DC *v8; // rcx
  unsigned int CurrentProcessId; // eax
  DC *v10; // rdi
  unsigned int v11; // ebx
  char *v12; // rsi
  struct _DC_ATTR *UserAttr; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  DC *v16; // rdi
  unsigned int v17; // ebx
  char *v18; // rsi
  struct REGION *v19; // rax
  ULONG v21; // ecx
  DC *v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+28h] [rbp-D8h]
  struct Gre::Base::SESSION_GLOBALS *v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  _OWORD v26[2]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v27[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v28; // [rsp+80h] [rbp-80h]
  struct REGION *v29; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[40]; // [rsp+98h] [rbp-68h] BYREF
  int v31; // [rsp+C0h] [rbp-40h]
  HDC v32[20]; // [rsp+D0h] [rbp-30h] BYREF
  struct REGION *v33; // [rsp+1B8h] [rbp+B8h] BYREF

  v25 = 0;
  v24 = Gre::Base::Globals(a1);
  v22 = 0;
  v23 = 0;
  memset(v26, 0, sizeof(v26));
  PushThreadGuardedObject(
    v26,
    &v22,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  LOBYTE(v6) = 1;
  v7 = HmgLock(v24, a1, v6, 0);
  v22 = (DC *)v7;
  v8 = (DC *)v7;
  if ( v7 )
  {
    if ( *(_DWORD *)(v7 + 2136) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)(v7 + 12));
      v8 = 0;
      v22 = 0;
    }
  }
  else
  {
    if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction(0) != 1 )
      GrepAuditBehaviorRestrictionViolations(1);
    v8 = v22;
  }
  if ( v8 )
  {
    if ( (*((_DWORD *)v8 + 11) & 2) == 0 )
    {
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      v10 = v22;
      v11 = CurrentProcessId & 0xFFFFFFFC;
      if ( *(_QWORD *)v22 )
      {
        v12 = (char *)HmgPentryFromPobj(v24, v22);
      }
      else
      {
        v12 = (char *)v22 + 2152;
        *(_OWORD *)((char *)v22 + 2152) = 0;
        *((_QWORD *)v10 + 271) = 0;
        *((_DWORD *)v10 + 540) = -2147483630;
        *((_QWORD *)v10 + 271) = GreEncodeUserModePointer(0);
      }
      if ( v11 == (*((_DWORD *)v12 + 2) & 0xFFFFFFFE) )
      {
        UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v22);
        if ( UserAttr )
        {
          if ( !DC::SaveAttributes(v22, UserAttr) )
          {
            _InterlockedDecrement16((volatile signed __int16 *)v22 + 6);
            v22 = 0;
            goto LABEL_14;
          }
        }
      }
      *((_DWORD *)v22 + 11) |= 2u;
      v8 = v22;
      v23 = 1;
    }
    if ( (*((_DWORD *)v8 + 130) & 4) != 0 )
      DC::vMarkTransformDirty(v8);
  }
LABEL_14:
  memset(v27, 0, sizeof(v27));
  PushThreadGuardedObject(v27, &v22, UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v28 = 1;
  if ( !v22 )
    goto LABEL_36;
  if ( *((_WORD *)v22 + 6) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v15, v14);
  if ( *((_WORD *)v22 + 6) != 1 )
    DCOBJ::vUnlock((DCOBJ *)&v22);
  v16 = v22;
  if ( !v22 )
  {
LABEL_36:
    EngSetLastError(6u);
    v17 = 0;
    goto LABEL_37;
  }
  v17 = 0;
  if ( (unsigned int)(a3 - 1) > 4 )
  {
    v21 = 87;
LABEL_44:
    EngSetLastError(v21);
    goto LABEL_37;
  }
  if ( *(_QWORD *)v22 )
  {
    v18 = (char *)HmgPentryFromPobj(v24, v22);
  }
  else
  {
    v18 = (char *)v22 + 2152;
    *(_OWORD *)((char *)v22 + 2152) = 0;
    *((_QWORD *)v16 + 271) = 0;
    *((_DWORD *)v16 + 540) = -2147483630;
    *((_QWORD *)v16 + 271) = GreEncodeUserModePointer(0);
  }
  if ( (*((_DWORD *)v18 + 2) & 0xFFFFFFFE) == 0 )
  {
    v21 = 6;
    goto LABEL_44;
  }
  if ( a2 )
  {
    RGNOBJAPI::RGNOBJAPI((RGNOBJAPI *)&v29, a2, 1, 0);
    v19 = v29;
    if ( v29 )
    {
      v17 = DC::iSelect(v22, v29, a3);
      if ( v17 )
      {
        DEVLOCKOBJ::DEVLOCKOBJ((DEVLOCKOBJ *)v32);
        v17 = 0;
        if ( DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v32, (struct XDCOBJ *)&v22, 1) )
        {
          v33 = XDCOBJ::prgnEffRao((XDCOBJ *)&v22);
          v17 = RGNOBJ::iComplexity((RGNOBJ *)&v33);
        }
        DEVLOCKOBJ::~DEVLOCKOBJ(v32);
      }
      v19 = v29;
    }
    if ( !v31 )
    {
      RGNOBJ::UpdateUserRgn((RGNOBJ *)&v29);
      v19 = v29;
    }
    if ( v19 )
      _InterlockedDecrement16((volatile signed __int16 *)v19 + 6);
    PopThreadGuardedObject(v30);
  }
  else if ( a3 == 5 )
  {
    v17 = DC::iSelect(v22, 0, 5);
    if ( v17 )
    {
      DEVLOCKOBJ::DEVLOCKOBJ((DEVLOCKOBJ *)v32);
      v17 = 0;
      if ( DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v32, (struct XDCOBJ *)&v22, 1) )
      {
        v33 = DC::prgnVisSnap(v22);
        v17 = RGNOBJ::iComplexity((RGNOBJ *)&v33);
      }
      DEVLOCKOBJ::~DEVLOCKOBJ(v32);
    }
  }
LABEL_37:
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v22);
  return v17;
}

```

## disassembly

```asm
0x140069c70  mov     [rsp-8+arg_0], rbx
0x140069c75  mov     [rsp-8+arg_8], rsi
0x140069c7a  push    rbp
0x140069c7b  push    rdi
0x140069c7c  push    r13
0x140069c7e  push    r14
0x140069c80  push    r15
0x140069c82  lea     rbp, [rsp-70h]
0x140069c87  sub     rsp, 170h
0x140069c8e  mov     r14d, r8d
0x140069c91  mov     [rsp+190h+var_170], 0
0x140069c9a  mov     r15, rdx
0x140069c9d  mov     [rsp+190h+var_168], 0
0x140069ca5  mov     rbx, rcx
0x140069ca8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140069caf  nop     dword ptr [rax+rax+00h]
0x140069cb4  xorps   xmm0, xmm0
0x140069cb7  mov     [rsp+190h+var_158], 0
0x140069cc0  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x140069cc7  mov     [rsp+190h+var_160], rax
0x140069ccc  lea     rdx, [rsp+190h+var_170]
0x140069cd1  mov     [rsp+190h+var_170], 0
0x140069cda  lea     rcx, [rsp+190h+var_150]
0x140069cdf  mov     [rsp+190h+var_168], 0
0x140069ce7  movups  [rsp+190h+var_150], xmm0
0x140069cec  movups  [rsp+190h+var_140], xmm0
0x140069cf1  call    cs:__imp_PushThreadGuardedObject
0x140069cf8  nop     dword ptr [rax+rax+00h]
0x140069cfd  mov     rcx, [rsp+190h+var_160]
0x140069d02  xor     r9d, r9d
0x140069d05  mov     rdx, rbx
0x140069d08  lea     r13d, [r9+1]
0x140069d0c  mov     r8b, r13b
0x140069d0f  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140069d16  nop     dword ptr [rax+rax+00h]
0x140069d1b  mov     [rsp+190h+var_170], rax
0x140069d20  mov     rcx, rax
0x140069d23  test    rax, rax
0x140069d26  jz      loc_14006A027
0x140069d2c  cmp     dword ptr [rax+858h], 0
0x140069d33  jnz     loc_14006A05B
0x140069d39  test    rcx, rcx
0x140069d3c  jz      loc_140069DE2
0x140069d42  mov     eax, [rcx+2Ch]
0x140069d45  test    al, 2
0x140069d47  jnz     loc_140069DD4
0x140069d4d  call    cs:__imp_PsGetCurrentProcessId
0x140069d54  nop     dword ptr [rax+rax+00h]
0x140069d59  mov     rdi, [rsp+190h+var_170]
0x140069d5e  mov     rbx, rax
0x140069d61  and     ebx, 0FFFFFFFCh
0x140069d64  cmp     qword ptr [rdi], 0
0x140069d68  jz      loc_14006A06C
0x140069d6e  mov     rcx, [rsp+190h+var_160]
0x140069d73  mov     rdx, rdi
0x140069d76  call    cs:__imp_HmgPentryFromPobj
0x140069d7d  nop     dword ptr [rax+rax+00h]
0x140069d82  mov     rsi, rax
0x140069d85  mov     eax, [rsi+8]
0x140069d88  and     eax, 0FFFFFFFEh
0x140069d8b  cmp     ebx, eax
0x140069d8d  jnz     short loc_140069DC1
0x140069d8f  lea     rcx, [rsp+190h+var_170]
0x140069d94  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x140069d9b  nop     dword ptr [rax+rax+00h]
0x140069da0  test    rax, rax
0x140069da3  jz      short loc_140069DC1
0x140069da5  mov     rcx, [rsp+190h+var_170]
0x140069daa  mov     rdx, rax
0x140069dad  call    cs:__imp_?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x140069db4  nop     dword ptr [rax+rax+00h]
0x140069db9  test    eax, eax
0x140069dbb  jz      loc_14006A0A3
0x140069dc1  mov     rax, [rsp+190h+var_170]
0x140069dc6  or      dword ptr [rax+2Ch], 2
0x140069dca  mov     rcx, [rsp+190h+var_170]; this
0x140069dcf  mov     [rsp+190h+var_168], r13d
0x140069dd4  mov     eax, [rcx+208h]
0x140069dda  test    al, 4
0x140069ddc  jnz     loc_140069F8F
0x140069de2  xorps   xmm0, xmm0
0x140069de5  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140069dec  lea     rdx, [rsp+190h+var_170]
0x140069df1  lea     rcx, [rsp+190h+var_130]
0x140069df6  movups  [rsp+190h+var_130], xmm0
0x140069dfb  movups  [rsp+190h+var_120], xmm0
0x140069e00  call    cs:__imp_PushThreadGuardedObject
0x140069e07  nop     dword ptr [rax+rax+00h]
0x140069e0c  mov     rax, [rsp+190h+var_170]
0x140069e11  mov     [rbp+90h+var_110], r13b
0x140069e15  test    rax, rax
0x140069e18  jz      loc_140069F53
0x140069e1e  movzx   eax, word ptr [rax+0Ch]
0x140069e22  cmp     ax, r13w
0x140069e26  jnz     loc_14006A051
0x140069e2c  mov     rax, [rsp+190h+var_170]
0x140069e31  movzx   ecx, word ptr [rax+0Ch]
0x140069e35  cmp     cx, r13w
0x140069e39  jnz     loc_14006A0BB
0x140069e3f  mov     rdi, [rsp+190h+var_170]
0x140069e44  test    rdi, rdi
0x140069e47  jz      loc_140069F53
0x140069e4d  xor     ebx, ebx
0x140069e4f  lea     eax, [r14-1]
0x140069e53  cmp     eax, 4
0x140069e56  ja      loc_14006A00A
0x140069e5c  cmp     [rdi], rbx
0x140069e5f  jz      loc_14006A0CA
0x140069e65  mov     rcx, [rsp+190h+var_160]
0x140069e6a  mov     rdx, rdi
0x140069e6d  call    cs:__imp_HmgPentryFromPobj
0x140069e74  nop     dword ptr [rax+rax+00h]
0x140069e79  mov     rsi, rax
0x140069e7c  test    dword ptr [rsi+8], 0FFFFFFFEh
0x140069e83  jz      loc_14006A020
0x140069e89  test    r15, r15
0x140069e8c  jz      loc_140069F99
0x140069e92  xor     r9d, r9d
0x140069e95  lea     rcx, [rbp+90h+var_100]
0x140069e99  mov     r8d, r13d
0x140069e9c  mov     rdx, r15
0x140069e9f  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x140069ea6  nop     dword ptr [rax+rax+00h]
0x140069eab  mov     rax, [rbp+90h+var_100]
0x140069eaf  test    rax, rax
0x140069eb2  jz      short loc_140069F1D
0x140069eb4  mov     rcx, [rsp+190h+var_170]; this
0x140069eb9  mov     r8d, r14d; int
0x140069ebc  mov     rdx, rax; struct REGION *
0x140069ebf  call    ?iSelect@DC@@QEAAHPEAVREGION@@H@Z; DC::iSelect(REGION *,int)
0x140069ec4  mov     ebx, eax
0x140069ec6  test    eax, eax
0x140069ec8  jz      short loc_140069F19
0x140069eca  lea     rcx, [rbp+90h+var_C0]; this
0x140069ece  call    ??0DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::DEVLOCKOBJ(void)
0x140069ed3  mov     r8d, r13d
0x140069ed6  lea     rdx, [rsp+190h+var_170]
0x140069edb  lea     rcx, [rbp+90h+var_C0]
0x140069edf  xor     ebx, ebx
0x140069ee1  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x140069ee8  nop     dword ptr [rax+rax+00h]
0x140069eed  test    eax, eax
0x140069eef  jz      short loc_140069F10
0x140069ef1  lea     rcx, [rsp+190h+var_170]; this
0x140069ef6  call    ?prgnEffRao@XDCOBJ@@QEAAPEAVREGION@@XZ; XDCOBJ::prgnEffRao(void)
0x140069efb  lea     rcx, [rbp+90h+arg_18]; this
0x140069f02  mov     [rbp+90h+arg_18], rax
0x140069f09  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x140069f0e  mov     ebx, eax
0x140069f10  lea     rcx, [rbp+90h+var_C0]; this
0x140069f14  call    ??1DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::~DEVLOCKOBJ(void)
0x140069f19  mov     rax, [rbp+90h+var_100]
0x140069f1d  cmp     [rbp+90h+var_D0], 0
0x140069f21  jnz     short loc_140069F37
0x140069f23  lea     rcx, [rbp+90h+var_100]
0x140069f27  call    cs:__imp_?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x140069f2e  nop     dword ptr [rax+rax+00h]
0x140069f33  mov     rax, [rbp+90h+var_100]
0x140069f37  test    rax, rax
0x140069f3a  jz      short loc_140069F41
0x140069f3c  lock dec word ptr [rax+0Ch]
0x140069f41  lea     rcx, [rbp+90h+var_F8]
0x140069f45  call    cs:__imp_PopThreadGuardedObject
0x140069f4c  nop     dword ptr [rax+rax+00h]
0x140069f51  jmp     short loc_140069F66
0x140069f53  mov     ecx, 6; iError
0x140069f58  call    cs:__imp_EngSetLastError
0x140069f5f  nop     dword ptr [rax+rax+00h]
0x140069f64  xor     ebx, ebx
0x140069f66  lea     rcx, [rsp+190h+var_170]; this
0x140069f6b  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x140069f70  lea     r11, [rsp+190h+var_20]
0x140069f78  mov     eax, ebx
0x140069f7a  mov     rbx, [r11+30h]
0x140069f7e  mov     rsi, [r11+38h]
0x140069f82  mov     rsp, r11
0x140069f85  pop     r15
0x140069f87  pop     r14
0x140069f89  pop     r13
0x140069f8b  pop     rdi
0x140069f8c  pop     rbp
0x140069f8d  retn
0x140069f8f  call    ?vMarkTransformDirty@DC@@QEAAXXZ; DC::vMarkTransformDirty(void)
0x140069f94  jmp     loc_140069DE2
0x140069f99  mov     r8d, 5; int
0x140069f9f  cmp     r14d, r8d
0x140069fa2  jnz     short loc_140069F66
0x140069fa4  mov     rcx, [rsp+190h+var_170]; this
0x140069fa9  xor     edx, edx; struct REGION *
0x140069fab  call    ?iSelect@DC@@QEAAHPEAVREGION@@H@Z; DC::iSelect(REGION *,int)
0x140069fb0  mov     ebx, eax
0x140069fb2  test    eax, eax
0x140069fb4  jz      short loc_140069F66
0x140069fb6  lea     rcx, [rbp+90h+var_C0]; this
0x140069fba  call    ??0DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::DEVLOCKOBJ(void)
0x140069fbf  mov     r8d, r13d
0x140069fc2  lea     rdx, [rsp+190h+var_170]
0x140069fc7  lea     rcx, [rbp+90h+var_C0]
0x140069fcb  xor     ebx, ebx
0x140069fcd  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x140069fd4  nop     dword ptr [rax+rax+00h]
0x140069fd9  test    eax, eax
0x140069fdb  jz      short loc_140069FFC
0x140069fdd  mov     rcx, [rsp+190h+var_170]; this
0x140069fe2  call    ?prgnVisSnap@DC@@QEBAPEAVREGION@@XZ; DC::prgnVisSnap(void)
0x140069fe7  lea     rcx, [rbp+90h+arg_18]; this
0x140069fee  mov     [rbp+90h+arg_18], rax
0x140069ff5  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x140069ffa  mov     ebx, eax
0x140069ffc  lea     rcx, [rbp+90h+var_C0]; this
0x14006a000  call    ??1DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::~DEVLOCKOBJ(void)
0x14006a005  jmp     loc_140069F66
0x14006a00a  mov     ecx, 57h ; 'W'; iError
0x14006a00f  call    cs:__imp_EngSetLastError
0x14006a016  nop     dword ptr [rax+rax+00h]
0x14006a01b  jmp     loc_140069F66
0x14006a020  mov     ecx, 6
0x14006a025  jmp     short loc_14006A00F
0x14006a027  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x14006a02e  nop     dword ptr [rax+rax+00h]
0x14006a033  cmp     eax, r13d
0x14006a036  jz      short loc_14006A047
0x14006a038  mov     ecx, r13d
0x14006a03b  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x14006a042  nop     dword ptr [rax+rax+00h]
0x14006a047  mov     rcx, [rsp+190h+var_170]
0x14006a04c  jmp     loc_140069D39
0x14006a051  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14006a056  jmp     loc_140069E2C
0x14006a05b  lock dec word ptr [rax+0Ch]
0x14006a060  xor     ecx, ecx
0x14006a062  mov     [rsp+190h+var_170], rcx
0x14006a067  jmp     loc_140069D39
0x14006a06c  xorps   xmm0, xmm0
0x14006a06f  lea     rsi, [rdi+868h]
0x14006a076  movups  xmmword ptr [rsi], xmm0
0x14006a079  xor     eax, eax
0x14006a07b  xor     ecx, ecx
0x14006a07d  mov     [rsi+10h], rax
0x14006a081  mov     dword ptr [rdi+870h], 80000012h
0x14006a08b  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x14006a092  nop     dword ptr [rax+rax+00h]
0x14006a097  mov     [rdi+878h], rax
0x14006a09e  jmp     loc_140069D85
0x14006a0a3  mov     rax, [rsp+190h+var_170]
0x14006a0a8  lock dec word ptr [rax+0Ch]
0x14006a0ad  mov     [rsp+190h+var_170], 0
0x14006a0b6  jmp     loc_140069DE2
0x14006a0bb  lea     rcx, [rsp+190h+var_170]; this
0x14006a0c0  call    ?vUnlock@DCOBJ@@QEAAXXZ; DCOBJ::vUnlock(void)
0x14006a0c5  jmp     loc_140069E3F
0x14006a0ca  xorps   xmm0, xmm0
0x14006a0cd  lea     rsi, [rdi+868h]
0x14006a0d4  movups  xmmword ptr [rsi], xmm0
0x14006a0d7  xor     eax, eax
0x14006a0d9  xor     ecx, ecx
0x14006a0db  mov     [rsi+10h], rax
0x14006a0df  mov     dword ptr [rdi+870h], 80000012h
0x14006a0e9  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x14006a0f0  nop     dword ptr [rax+rax+00h]
0x14006a0f5  mov     [rdi+878h], rax
0x14006a0fc  jmp     loc_140069E7C
```
