# NtGdiExtSelectClipRgn

- ea: `0x140061980`
- end: `0x140061e1b`
- name: `NtGdiExtSelectClipRgn`
- size: `1179`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400604f0`
- `0x140061980`
- `0x1400620a8`
- `0x140063ee0`
- `0x1400781e8`
- `0x14007eef8`
- `0x140080590`
- `0x140081a54`
- `0x140164228`
- `0x14016ca80`
- `0x140303af4`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140061a5d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140061a5d`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400619b8`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400619b8`
- `win32kbase!HmgPentryFromPobj` at `0x140061a86`
- `win32kbase!HmgPentryFromPobj` at `0x140061b7d`
- `win32kbase!HmgPentryFromPobj` at `0x140061a86`
- `win32kbase!HmgPentryFromPobj` at `0x140061b7d`
- `win32kbase!PopThreadGuardedObject` at `0x140061c5a`
- `win32kbase!PopThreadGuardedObject` at `0x140061c5a`
- `win32kbase!PushThreadGuardedObject` at `0x140061a01`
- `win32kbase!PushThreadGuardedObject` at `0x140061b10`
- `win32kbase!PushThreadGuardedObject` at `0x140061a01`
- `win32kbase!PushThreadGuardedObject` at `0x140061b10`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140061aa4`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140061aa4`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140061da5`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140061e03`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140061da5`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140061e03`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x140061abd`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x140061abd`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140061d55`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140061d55`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140061d41`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140061d41`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140061a1f`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140061a1f`
- `win32kbase!EngSetLastError` at `0x140061c6d`
- `win32kbase!EngSetLastError` at `0x140061d29`
- `win32kbase!EngSetLastError` at `0x140061c6d`
- `win32kbase!EngSetLastError` at `0x140061d29`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140061bf6`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140061ce7`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140061bf6`
- `win32kbase!?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z` at `0x140061ce7`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140061baf`
- `win32kbase!??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z` at `0x140061baf`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x140061c3c`
- `win32kbase!?UpdateUserRgn@RGNOBJ@@QEAAXXZ` at `0x140061c3c`

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
  _BYTE v32[176]; // [rsp+D0h] [rbp-30h] BYREF
  struct REGION *v33; // [rsp+1C8h] [rbp+C8h] BYREF

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
  v7 = HmgLock(v24, a1, v6);
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
        DEVLOCKOBJ::DEVLOCKOBJ(v32, 4);
        v17 = 0;
        if ( DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v32, (struct XDCOBJ *)&v22, 1) )
        {
          v33 = XDCOBJ::prgnEffRao((XDCOBJ *)&v22);
          v17 = RGNOBJ::iComplexity((RGNOBJ *)&v33);
        }
        DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v32);
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
      DEVLOCKOBJ::DEVLOCKOBJ(v32, 4);
      v17 = 0;
      if ( DEVLOCKOBJ::bLock((DEVLOCKOBJ *)v32, (struct XDCOBJ *)&v22, 1) )
      {
        v33 = DC::prgnVisSnap(v22);
        v17 = RGNOBJ::iComplexity((RGNOBJ *)&v33);
      }
      DEVLOCKOBJ::~DEVLOCKOBJ((DEVLOCKOBJ *)v32);
    }
  }
LABEL_37:
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v22);
  return v17;
}

```

## disassembly

```asm
0x140061980  mov     [rsp-8+arg_0], rbx
0x140061985  mov     [rsp-8+arg_8], rsi
0x14006198a  push    rbp
0x14006198b  push    rdi
0x14006198c  push    r13
0x14006198e  push    r14
0x140061990  push    r15
0x140061992  lea     rbp, [rsp-80h]
0x140061997  sub     rsp, 180h
0x14006199e  mov     r14d, r8d
0x1400619a1  mov     [rsp+1A0h+var_180], 0
0x1400619aa  mov     r15, rdx
0x1400619ad  mov     [rsp+1A0h+var_178], 0
0x1400619b5  mov     rbx, rcx
0x1400619b8  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400619bf  nop     dword ptr [rax+rax+00h]
0x1400619c4  xorps   xmm0, xmm0
0x1400619c7  mov     [rsp+1A0h+var_168], 0
0x1400619d0  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x1400619d7  mov     [rsp+1A0h+var_170], rax
0x1400619dc  lea     rdx, [rsp+1A0h+var_180]
0x1400619e1  mov     [rsp+1A0h+var_180], 0
0x1400619ea  lea     rcx, [rsp+1A0h+var_160]
0x1400619ef  mov     [rsp+1A0h+var_178], 0
0x1400619f7  movups  [rsp+1A0h+var_160], xmm0
0x1400619fc  movups  [rsp+1A0h+var_150], xmm0
0x140061a01  call    cs:__imp_PushThreadGuardedObject
0x140061a08  nop     dword ptr [rax+rax+00h]
0x140061a0d  mov     rcx, [rsp+1A0h+var_170]
0x140061a12  xor     r9d, r9d
0x140061a15  mov     rdx, rbx
0x140061a18  lea     r13d, [r9+1]
0x140061a1c  mov     r8b, r13b
0x140061a1f  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140061a26  nop     dword ptr [rax+rax+00h]
0x140061a2b  mov     [rsp+1A0h+var_180], rax
0x140061a30  mov     rcx, rax
0x140061a33  test    rax, rax
0x140061a36  jz      loc_140061D41
0x140061a3c  cmp     dword ptr [rax+858h], 0
0x140061a43  jnz     loc_140061D75
0x140061a49  test    rcx, rcx
0x140061a4c  jz      loc_140061AF2
0x140061a52  mov     eax, [rcx+2Ch]
0x140061a55  test    al, 2
0x140061a57  jnz     loc_140061AE4
0x140061a5d  call    cs:__imp_PsGetCurrentProcessId
0x140061a64  nop     dword ptr [rax+rax+00h]
0x140061a69  mov     rdi, [rsp+1A0h+var_180]
0x140061a6e  mov     rbx, rax
0x140061a71  and     ebx, 0FFFFFFFCh
0x140061a74  cmp     qword ptr [rdi], 0
0x140061a78  jz      loc_140061D86
0x140061a7e  mov     rcx, [rsp+1A0h+var_170]
0x140061a83  mov     rdx, rdi
0x140061a86  call    cs:__imp_HmgPentryFromPobj
0x140061a8d  nop     dword ptr [rax+rax+00h]
0x140061a92  mov     rsi, rax
0x140061a95  mov     eax, [rsi+8]
0x140061a98  and     eax, 0FFFFFFFEh
0x140061a9b  cmp     ebx, eax
0x140061a9d  jnz     short loc_140061AD1
0x140061a9f  lea     rcx, [rsp+1A0h+var_180]
0x140061aa4  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x140061aab  nop     dword ptr [rax+rax+00h]
0x140061ab0  test    rax, rax
0x140061ab3  jz      short loc_140061AD1
0x140061ab5  mov     rcx, [rsp+1A0h+var_180]
0x140061aba  mov     rdx, rax
0x140061abd  call    cs:__imp_?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x140061ac4  nop     dword ptr [rax+rax+00h]
0x140061ac9  test    eax, eax
0x140061acb  jz      loc_140061DBD
0x140061ad1  mov     rax, [rsp+1A0h+var_180]
0x140061ad6  or      dword ptr [rax+2Ch], 2
0x140061ada  mov     rcx, [rsp+1A0h+var_180]; this
0x140061adf  mov     [rsp+1A0h+var_178], r13d
0x140061ae4  mov     eax, [rcx+208h]
0x140061aea  test    al, 4
0x140061aec  jnz     loc_140061CA4
0x140061af2  xorps   xmm0, xmm0
0x140061af5  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140061afc  lea     rdx, [rsp+1A0h+var_180]
0x140061b01  lea     rcx, [rsp+1A0h+var_140]
0x140061b06  movups  [rsp+1A0h+var_140], xmm0
0x140061b0b  movups  [rsp+1A0h+var_130], xmm0
0x140061b10  call    cs:__imp_PushThreadGuardedObject
0x140061b17  nop     dword ptr [rax+rax+00h]
0x140061b1c  mov     rax, [rsp+1A0h+var_180]
0x140061b21  mov     [rbp+0A0h+var_120], r13b
0x140061b25  test    rax, rax
0x140061b28  jz      loc_140061C68
0x140061b2e  movzx   eax, word ptr [rax+0Ch]
0x140061b32  cmp     ax, r13w
0x140061b36  jnz     loc_140061D6B
0x140061b3c  mov     rax, [rsp+1A0h+var_180]
0x140061b41  movzx   ecx, word ptr [rax+0Ch]
0x140061b45  cmp     cx, r13w
0x140061b49  jnz     loc_140061DD5
0x140061b4f  mov     rdi, [rsp+1A0h+var_180]
0x140061b54  test    rdi, rdi
0x140061b57  jz      loc_140061C68
0x140061b5d  xor     ebx, ebx
0x140061b5f  lea     eax, [r14-1]
0x140061b63  cmp     eax, 4
0x140061b66  ja      loc_140061D24
0x140061b6c  cmp     [rdi], rbx
0x140061b6f  jz      loc_140061DE4
0x140061b75  mov     rcx, [rsp+1A0h+var_170]
0x140061b7a  mov     rdx, rdi
0x140061b7d  call    cs:__imp_HmgPentryFromPobj
0x140061b84  nop     dword ptr [rax+rax+00h]
0x140061b89  mov     rsi, rax
0x140061b8c  test    dword ptr [rsi+8], 0FFFFFFFEh
0x140061b93  jz      loc_140061D3A
0x140061b99  test    r15, r15
0x140061b9c  jz      loc_140061CAE
0x140061ba2  xor     r9d, r9d
0x140061ba5  lea     rcx, [rbp+0A0h+var_110]
0x140061ba9  mov     r8d, r13d
0x140061bac  mov     rdx, r15
0x140061baf  call    cs:__imp_??0RGNOBJAPI@@QEAA@PEAUHRGN__@@HH@Z; RGNOBJAPI::RGNOBJAPI(HRGN__ *,int,int)
0x140061bb6  nop     dword ptr [rax+rax+00h]
0x140061bbb  mov     rax, [rbp+0A0h+var_110]
0x140061bbf  test    rax, rax
0x140061bc2  jz      short loc_140061C32
0x140061bc4  mov     rcx, [rsp+1A0h+var_180]; this
0x140061bc9  mov     r8d, r14d; int
0x140061bcc  mov     rdx, rax; struct REGION *
0x140061bcf  call    ?iSelect@DC@@QEAAHPEAVREGION@@H@Z; DC::iSelect(REGION *,int)
0x140061bd4  mov     ebx, eax
0x140061bd6  test    eax, eax
0x140061bd8  jz      short loc_140061C2E
0x140061bda  mov     edx, 4
0x140061bdf  lea     rcx, [rbp+0A0h+var_D0]
0x140061be3  call    ??0DEVLOCKOBJ@@QEAA@W4U2KMMAPStatus@@@Z; DEVLOCKOBJ::DEVLOCKOBJ(U2KMMAPStatus)
0x140061be8  mov     r8d, r13d
0x140061beb  lea     rdx, [rsp+1A0h+var_180]
0x140061bf0  lea     rcx, [rbp+0A0h+var_D0]
0x140061bf4  xor     ebx, ebx
0x140061bf6  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x140061bfd  nop     dword ptr [rax+rax+00h]
0x140061c02  test    eax, eax
0x140061c04  jz      short loc_140061C25
0x140061c06  lea     rcx, [rsp+1A0h+var_180]; this
0x140061c0b  call    ?prgnEffRao@XDCOBJ@@QEAAPEAVREGION@@XZ; XDCOBJ::prgnEffRao(void)
0x140061c10  lea     rcx, [rbp+0A0h+arg_18]; this
0x140061c17  mov     [rbp+0A0h+arg_18], rax
0x140061c1e  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x140061c23  mov     ebx, eax
0x140061c25  lea     rcx, [rbp+0A0h+var_D0]; this
0x140061c29  call    ??1DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::~DEVLOCKOBJ(void)
0x140061c2e  mov     rax, [rbp+0A0h+var_110]
0x140061c32  cmp     [rbp+0A0h+var_E0], 0
0x140061c36  jnz     short loc_140061C4C
0x140061c38  lea     rcx, [rbp+0A0h+var_110]
0x140061c3c  call    cs:__imp_?UpdateUserRgn@RGNOBJ@@QEAAXXZ; RGNOBJ::UpdateUserRgn(void)
0x140061c43  nop     dword ptr [rax+rax+00h]
0x140061c48  mov     rax, [rbp+0A0h+var_110]
0x140061c4c  test    rax, rax
0x140061c4f  jz      short loc_140061C56
0x140061c51  lock dec word ptr [rax+0Ch]
0x140061c56  lea     rcx, [rbp+0A0h+var_108]
0x140061c5a  call    cs:__imp_PopThreadGuardedObject
0x140061c61  nop     dword ptr [rax+rax+00h]
0x140061c66  jmp     short loc_140061C7B
0x140061c68  mov     ecx, 6; iError
0x140061c6d  call    cs:__imp_EngSetLastError
0x140061c74  nop     dword ptr [rax+rax+00h]
0x140061c79  xor     ebx, ebx
0x140061c7b  lea     rcx, [rsp+1A0h+var_180]; this
0x140061c80  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x140061c85  lea     r11, [rsp+1A0h+var_20]
0x140061c8d  mov     eax, ebx
0x140061c8f  mov     rbx, [r11+30h]
0x140061c93  mov     rsi, [r11+38h]
0x140061c97  mov     rsp, r11
0x140061c9a  pop     r15
0x140061c9c  pop     r14
0x140061c9e  pop     r13
0x140061ca0  pop     rdi
0x140061ca1  pop     rbp
0x140061ca2  retn
0x140061ca4  call    ?vMarkTransformDirty@DC@@QEAAXXZ; DC::vMarkTransformDirty(void)
0x140061ca9  jmp     loc_140061AF2
0x140061cae  mov     r8d, 5; int
0x140061cb4  cmp     r14d, r8d
0x140061cb7  jnz     short loc_140061C7B
0x140061cb9  mov     rcx, [rsp+1A0h+var_180]; this
0x140061cbe  xor     edx, edx; struct REGION *
0x140061cc0  call    ?iSelect@DC@@QEAAHPEAVREGION@@H@Z; DC::iSelect(REGION *,int)
0x140061cc5  mov     ebx, eax
0x140061cc7  test    eax, eax
0x140061cc9  jz      short loc_140061C7B
0x140061ccb  mov     edx, 4
0x140061cd0  lea     rcx, [rbp+0A0h+var_D0]
0x140061cd4  call    ??0DEVLOCKOBJ@@QEAA@W4U2KMMAPStatus@@@Z; DEVLOCKOBJ::DEVLOCKOBJ(U2KMMAPStatus)
0x140061cd9  mov     r8d, r13d
0x140061cdc  lea     rdx, [rsp+1A0h+var_180]
0x140061ce1  lea     rcx, [rbp+0A0h+var_D0]
0x140061ce5  xor     ebx, ebx
0x140061ce7  call    cs:__imp_?bLock@DEVLOCKOBJ@@QEAAHAEAVXDCOBJ@@H@Z; DEVLOCKOBJ::bLock(XDCOBJ &,int)
0x140061cee  nop     dword ptr [rax+rax+00h]
0x140061cf3  test    eax, eax
0x140061cf5  jz      short loc_140061D16
0x140061cf7  mov     rcx, [rsp+1A0h+var_180]; this
0x140061cfc  call    ?prgnVisSnap@DC@@QEBAPEAVREGION@@XZ; DC::prgnVisSnap(void)
0x140061d01  lea     rcx, [rbp+0A0h+arg_18]; this
0x140061d08  mov     [rbp+0A0h+arg_18], rax
0x140061d0f  call    ?iComplexity@RGNOBJ@@QEBAJXZ; RGNOBJ::iComplexity(void)
0x140061d14  mov     ebx, eax
0x140061d16  lea     rcx, [rbp+0A0h+var_D0]; this
0x140061d1a  call    ??1DEVLOCKOBJ@@QEAA@XZ; DEVLOCKOBJ::~DEVLOCKOBJ(void)
0x140061d1f  jmp     loc_140061C7B
0x140061d24  mov     ecx, 57h ; 'W'; iError
0x140061d29  call    cs:__imp_EngSetLastError
0x140061d30  nop     dword ptr [rax+rax+00h]
0x140061d35  jmp     loc_140061C7B
0x140061d3a  mov     ecx, 6
0x140061d3f  jmp     short loc_140061D29
0x140061d41  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x140061d48  nop     dword ptr [rax+rax+00h]
0x140061d4d  cmp     eax, r13d
0x140061d50  jz      short loc_140061D61
0x140061d52  mov     ecx, r13d
0x140061d55  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x140061d5c  nop     dword ptr [rax+rax+00h]
0x140061d61  mov     rcx, [rsp+1A0h+var_180]
0x140061d66  jmp     loc_140061A49
0x140061d6b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140061d70  jmp     loc_140061B3C
0x140061d75  lock dec word ptr [rax+0Ch]
0x140061d7a  xor     ecx, ecx
0x140061d7c  mov     [rsp+1A0h+var_180], rcx
0x140061d81  jmp     loc_140061A49
0x140061d86  xorps   xmm0, xmm0
0x140061d89  lea     rsi, [rdi+868h]
0x140061d90  movups  xmmword ptr [rsi], xmm0
0x140061d93  xor     eax, eax
0x140061d95  xor     ecx, ecx
0x140061d97  mov     [rsi+10h], rax
0x140061d9b  mov     dword ptr [rdi+870h], 80000012h
0x140061da5  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x140061dac  nop     dword ptr [rax+rax+00h]
0x140061db1  mov     [rdi+878h], rax
0x140061db8  jmp     loc_140061A95
0x140061dbd  mov     rax, [rsp+1A0h+var_180]
0x140061dc2  lock dec word ptr [rax+0Ch]
0x140061dc7  mov     [rsp+1A0h+var_180], 0
0x140061dd0  jmp     loc_140061AF2
0x140061dd5  lea     rcx, [rsp+1A0h+var_180]; this
0x140061dda  call    ?vUnlock@DCOBJ@@QEAAXXZ; DCOBJ::vUnlock(void)
0x140061ddf  jmp     loc_140061B4F
0x140061de4  xorps   xmm0, xmm0
0x140061de7  lea     rsi, [rdi+868h]
0x140061dee  movups  xmmword ptr [rsi], xmm0
0x140061df1  xor     eax, eax
0x140061df3  xor     ecx, ecx
0x140061df5  mov     [rsi+10h], rax
0x140061df9  mov     dword ptr [rdi+870h], 80000012h
0x140061e03  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x140061e0a  nop     dword ptr [rax+rax+00h]
0x140061e0f  mov     [rdi+878h], rax
0x140061e16  jmp     loc_140061B8C
```
