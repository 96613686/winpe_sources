# NtGdiSelectFont

- ea: `0x14005fdf0`
- end: `0x14006020a`
- name: `NtGdiSelectFont`
- size: `1050`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x14005fdf0`
- `0x1400604f0`
- `0x1400781e8`
- `0x14007eef8`
- `0x140164228`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14005fea4`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005fea4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005fe18`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400601e3`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005fe18`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400601e3`
- `win32kbase!HmgPentryFromPobj` at `0x14005feca`
- `win32kbase!HmgPentryFromPobj` at `0x14005ffa8`
- `win32kbase!HmgPentryFromPobj` at `0x140060039`
- `win32kbase!HmgPentryFromPobj` at `0x14005feca`
- `win32kbase!HmgPentryFromPobj` at `0x14005ffa8`
- `win32kbase!HmgPentryFromPobj` at `0x140060039`
- `win32kbase!HmgShareLock` at `0x14005fff0`
- `win32kbase!HmgShareLock` at `0x14005fff0`
- `win32kbase!PopThreadGuardedObject` at `0x1400600ce`
- `win32kbase!PopThreadGuardedObject` at `0x1400600ce`
- `win32kbase!PushThreadGuardedObject` at `0x14005fe4e`
- `win32kbase!PushThreadGuardedObject` at `0x14005ff4b`
- `win32kbase!PushThreadGuardedObject` at `0x14006001a`
- `win32kbase!PushThreadGuardedObject` at `0x14005fe4e`
- `win32kbase!PushThreadGuardedObject` at `0x14005ff4b`
- `win32kbase!PushThreadGuardedObject` at `0x14006001a`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005fee7`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005fee7`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140060174`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x1400601cb`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140060174`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x1400601cb`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14005feff`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14005feff`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140060125`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140060125`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140060111`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140060111`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14005fe6b`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14005fe6b`
- `win32kbase!DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT` at `0x14006005d`
- `win32kbase!DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT` at `0x1400601f5`
- `win32kbase!DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT` at `0x14006005d`
- `win32kbase!DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT` at `0x1400601f5`

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
  v5 = HmgLock(v27, a1, v4, 0);
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
0x14005fdf0  push    rbp
0x14005fdf2  push    rbx
0x14005fdf3  push    rsi
0x14005fdf4  push    rdi
0x14005fdf5  push    r12
0x14005fdf7  push    r14
0x14005fdf9  push    r15
0x14005fdfb  lea     rbp, [rsp-27h]
0x14005fe00  sub     rsp, 0C0h
0x14005fe07  xor     r15d, r15d
0x14005fe0a  mov     r14, rdx
0x14005fe0d  mov     [rbp+57h+var_D0], r15
0x14005fe11  mov     rbx, rcx
0x14005fe14  mov     [rbp+57h+var_C8], r15d
0x14005fe18  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14005fe1f  nop     dword ptr [rax+rax+00h]
0x14005fe24  xorps   xmm0, xmm0
0x14005fe27  mov     [rbp+57h+var_B8], r15
0x14005fe2b  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14005fe32  mov     [rbp+57h+var_C0], rax
0x14005fe36  lea     rdx, [rbp+57h+var_D0]
0x14005fe3a  mov     [rbp+57h+var_D0], r15
0x14005fe3e  lea     rcx, [rbp+57h+var_B0]
0x14005fe42  mov     [rbp+57h+var_C8], r15d
0x14005fe46  movups  [rbp+57h+var_B0], xmm0
0x14005fe4a  movups  [rbp+57h+var_A0], xmm0
0x14005fe4e  call    cs:__imp_PushThreadGuardedObject
0x14005fe55  nop     dword ptr [rax+rax+00h]
0x14005fe5a  mov     rcx, [rbp+57h+var_C0]
0x14005fe5e  lea     r12d, [r15+1]
0x14005fe62  mov     r8b, r12b
0x14005fe65  xor     r9d, r9d
0x14005fe68  mov     rdx, rbx
0x14005fe6b  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14005fe72  nop     dword ptr [rax+rax+00h]
0x14005fe77  mov     [rbp+57h+var_D0], rax
0x14005fe7b  mov     rcx, rax
0x14005fe7e  test    rax, rax
0x14005fe81  jz      loc_140060111
0x14005fe87  cmp     [rax+858h], r15d
0x14005fe8e  jnz     loc_140060144
0x14005fe94  test    rcx, rcx
0x14005fe97  jz      loc_14005FF31
0x14005fe9d  mov     eax, [rcx+2Ch]
0x14005fea0  test    al, 2
0x14005fea2  jnz     short loc_14005FF23
0x14005fea4  call    cs:__imp_PsGetCurrentProcessId
0x14005feab  nop     dword ptr [rax+rax+00h]
0x14005feb0  mov     rdi, [rbp+57h+var_D0]
0x14005feb4  mov     rbx, rax
0x14005feb7  and     ebx, 0FFFFFFFCh
0x14005feba  cmp     [rdi], r15
0x14005febd  jz      loc_140060155
0x14005fec3  mov     rcx, [rbp+57h+var_C0]
0x14005fec7  mov     rdx, rdi
0x14005feca  call    cs:__imp_HmgPentryFromPobj
0x14005fed1  nop     dword ptr [rax+rax+00h]
0x14005fed6  mov     rsi, rax
0x14005fed9  mov     eax, [rsi+8]
0x14005fedc  and     eax, 0FFFFFFFEh
0x14005fedf  cmp     ebx, eax
0x14005fee1  jnz     short loc_14005FF13
0x14005fee3  lea     rcx, [rbp+57h+var_D0]
0x14005fee7  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14005feee  nop     dword ptr [rax+rax+00h]
0x14005fef3  test    rax, rax
0x14005fef6  jz      short loc_14005FF13
0x14005fef8  mov     rcx, [rbp+57h+var_D0]
0x14005fefc  mov     rdx, rax
0x14005feff  call    cs:__imp_?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z; DC::SaveAttributes(_DC_ATTR *)
0x14005ff06  nop     dword ptr [rax+rax+00h]
0x14005ff0b  test    eax, eax
0x14005ff0d  jz      loc_14006018C
0x14005ff13  mov     rax, [rbp+57h+var_D0]
0x14005ff17  or      dword ptr [rax+2Ch], 2
0x14005ff1b  mov     rcx, [rbp+57h+var_D0]; this
0x14005ff1f  mov     [rbp+57h+var_C8], r12d
0x14005ff23  mov     eax, [rcx+208h]
0x14005ff29  test    al, 4
0x14005ff2b  jnz     loc_140060107
0x14005ff31  xorps   xmm0, xmm0
0x14005ff34  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14005ff3b  lea     rdx, [rbp+57h+var_D0]
0x14005ff3f  lea     rcx, [rbp+57h+var_90]
0x14005ff43  movups  [rbp+57h+var_90], xmm0
0x14005ff47  movups  [rbp+57h+var_80], xmm0
0x14005ff4b  call    cs:__imp_PushThreadGuardedObject
0x14005ff52  nop     dword ptr [rax+rax+00h]
0x14005ff57  mov     rax, [rbp+57h+var_D0]
0x14005ff5b  mov     [rbp+57h+var_70], r12b
0x14005ff5f  test    rax, rax
0x14005ff62  jz      loc_1400600F9
0x14005ff68  movzx   eax, word ptr [rax+0Ch]
0x14005ff6c  cmp     ax, r12w
0x14005ff70  jnz     loc_14006013A
0x14005ff76  mov     rax, [rbp+57h+var_D0]
0x14005ff7a  movzx   ecx, word ptr [rax+0Ch]
0x14005ff7e  cmp     cx, r12w
0x14005ff82  jnz     loc_14006019E
0x14005ff88  mov     rdi, [rbp+57h+var_D0]
0x14005ff8c  test    rdi, rdi
0x14005ff8f  jz      loc_1400600F9
0x14005ff95  mov     rbx, r15
0x14005ff98  cmp     [rdi], r15
0x14005ff9b  jz      loc_1400601AC
0x14005ffa1  mov     rcx, [rbp+57h+var_C0]
0x14005ffa5  mov     rdx, rdi
0x14005ffa8  call    cs:__imp_HmgPentryFromPobj
0x14005ffaf  nop     dword ptr [rax+rax+00h]
0x14005ffb4  mov     rsi, rax
0x14005ffb7  test    dword ptr [rsi+8], 0FFFFFFFEh
0x14005ffbe  jz      loc_1400600DA
0x14005ffc4  mov     rax, [rbp+57h+var_D0]
0x14005ffc8  mov     rcx, [rax+98h]
0x14005ffcf  test    rcx, rcx
0x14005ffd2  jz      short loc_14005FFD7
0x14005ffd4  mov     rbx, [rcx]
0x14005ffd7  cmp     r14, rbx
0x14005ffda  jz      loc_1400600DA
0x14005ffe0  mov     rsi, [rbp+57h+var_C0]
0x14005ffe4  xor     r9d, r9d
0x14005ffe7  mov     rcx, rsi
0x14005ffea  mov     r8b, 0Ah
0x14005ffed  mov     rdx, r14
0x14005fff0  call    cs:__imp_?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x14005fff7  nop     dword ptr [rax+rax+00h]
0x14005fffc  xorps   xmm0, xmm0
0x14005ffff  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgShareLockResult@VLFONT@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgShareLockResult<LFONT>>::OnUnexpectedThreadTerminationStatic(void *)
0x140060006  lea     rdx, [rbp+57h+var_60]
0x14006000a  mov     [rbp+57h+var_60], rax
0x14006000e  lea     rcx, [rbp+57h+var_58]
0x140060012  movups  [rbp+57h+var_58], xmm0
0x140060016  movups  [rbp+57h+var_48], xmm0
0x14006001a  call    cs:__imp_PushThreadGuardedObject
0x140060021  nop     dword ptr [rax+rax+00h]
0x140060026  mov     rdi, [rbp+57h+var_60]
0x14006002a  test    rdi, rdi
0x14006002d  jz      loc_140060102
0x140060033  mov     rdx, rdi
0x140060036  mov     rcx, rsi
0x140060039  call    cs:__imp_HmgPentryFromPobj
0x140060040  nop     dword ptr [rax+rax+00h]
0x140060045  test    byte ptr [rax+0Fh], 2
0x140060049  jnz     loc_1400600FE
0x14006004f  mov     rdx, [rbp+57h+var_D0]
0x140060053  mov     rcx, rsi
0x140060056  mov     rdx, [rdx+98h]
0x14006005d  call    cs:__imp_?DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT@@YAXAEAUSESSION_GLOBALS@Base@Gre@@PEAVLFONT@@@Z; DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT(Gre::Base::SESSION_GLOBALS &,LFONT *)
0x140060064  nop     dword ptr [rax+rax+00h]
0x140060069  mov     rcx, [rbp+57h+var_60]
0x14006006d  mov     rax, [rbp+57h+var_D0]
0x140060071  mov     [rbp+57h+var_60], r15
0x140060075  mov     [rax+98h], rcx
0x14006007c  mov     rax, [rbp+57h+var_D0]
0x140060080  mov     rcx, [rax+3D0h]
0x140060087  mov     [rcx+128h], r14
0x14006008e  mov     rax, [rbp+57h+var_D0]
0x140060092  mov     [rax+6D0h], r15
0x140060099  mov     rax, [rbp+57h+var_D0]
0x14006009d  mov     rcx, [rax+3D0h]
0x1400600a4  or      dword ptr [rcx+98h], 10h
0x1400600ab  mov     rax, [rbp+57h+var_D0]
0x1400600af  mov     rcx, [rax+3D0h]
0x1400600b6  and     dword ptr [rcx+98h], 0FFFFFFDFh
0x1400600bd  mov     rdi, [rbp+57h+var_60]
0x1400600c1  test    rdi, rdi
0x1400600c4  jnz     loc_1400601E3
0x1400600ca  lea     rcx, [rbp+57h+var_58]
0x1400600ce  call    cs:__imp_PopThreadGuardedObject
0x1400600d5  nop     dword ptr [rax+rax+00h]
0x1400600da  lea     rcx, [rbp+57h+var_D0]; this
0x1400600de  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x1400600e3  mov     rax, rbx
0x1400600e6  add     rsp, 0C0h
0x1400600ed  pop     r15
0x1400600ef  pop     r14
0x1400600f1  pop     r12
0x1400600f3  pop     rdi
0x1400600f4  pop     rsi
0x1400600f5  pop     rbx
0x1400600f6  pop     rbp
0x1400600f7  retn
0x1400600f9  mov     rbx, r15
0x1400600fc  jmp     short loc_1400600DA
0x1400600fe  mov     rdi, [rbp+57h+var_60]
0x140060102  mov     rbx, r15
0x140060105  jmp     short loc_1400600C1
0x140060107  call    ?vMarkTransformDirty@DC@@QEAAXXZ; DC::vMarkTransformDirty(void)
0x14006010c  jmp     loc_14005FF31
0x140060111  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x140060118  nop     dword ptr [rax+rax+00h]
0x14006011d  cmp     eax, r12d
0x140060120  jz      short loc_140060131
0x140060122  mov     ecx, r12d
0x140060125  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x14006012c  nop     dword ptr [rax+rax+00h]
0x140060131  mov     rcx, [rbp+57h+var_D0]
0x140060135  jmp     loc_14005FE94
0x14006013a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14006013f  jmp     loc_14005FF76
0x140060144  lock dec word ptr [rax+0Ch]
0x140060149  mov     rcx, r15
0x14006014c  mov     [rbp+57h+var_D0], rcx
0x140060150  jmp     loc_14005FE94
0x140060155  xorps   xmm0, xmm0
0x140060158  lea     rsi, [rdi+868h]
0x14006015f  movups  xmmword ptr [rsi], xmm0
0x140060162  xor     eax, eax
0x140060164  xor     ecx, ecx
0x140060166  mov     [rsi+10h], rax
0x14006016a  mov     dword ptr [rdi+870h], 80000012h
0x140060174  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x14006017b  nop     dword ptr [rax+rax+00h]
0x140060180  mov     [rdi+878h], rax
0x140060187  jmp     loc_14005FED9
0x14006018c  mov     rax, [rbp+57h+var_D0]
0x140060190  lock dec word ptr [rax+0Ch]
0x140060195  mov     [rbp+57h+var_D0], r15
0x140060199  jmp     loc_14005FF31
0x14006019e  lea     rcx, [rbp+57h+var_D0]; this
0x1400601a2  call    ?vUnlock@DCOBJ@@QEAAXXZ; DCOBJ::vUnlock(void)
0x1400601a7  jmp     loc_14005FF88
0x1400601ac  xorps   xmm0, xmm0
0x1400601af  lea     rsi, [rdi+868h]
0x1400601b6  movups  xmmword ptr [rsi], xmm0
0x1400601b9  xor     eax, eax
0x1400601bb  xor     ecx, ecx
0x1400601bd  mov     [rsi+10h], rax
0x1400601c1  mov     dword ptr [rdi+870h], 80000012h
0x1400601cb  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x1400601d2  nop     dword ptr [rax+rax+00h]
0x1400601d7  mov     [rdi+878h], rax
0x1400601de  jmp     loc_14005FFB7
0x1400601e3  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400601ea  nop     dword ptr [rax+rax+00h]
0x1400601ef  mov     rcx, rax
0x1400601f2  mov     rdx, rdi
0x1400601f5  call    cs:__imp_?DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT@@YAXAEAUSESSION_GLOBALS@Base@Gre@@PEAVLFONT@@@Z; DEC_SHARE_REF_CNT_LAZY_DEL_LOGFONT(Gre::Base::SESSION_GLOBALS &,LFONT *)
0x1400601fc  nop     dword ptr [rax+rax+00h]
0x140060201  mov     [rbp+57h+var_60], r15
0x140060205  jmp     loc_1400600CA
```
