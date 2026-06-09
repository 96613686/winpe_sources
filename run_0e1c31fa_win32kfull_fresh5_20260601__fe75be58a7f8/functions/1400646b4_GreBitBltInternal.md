# GreBitBltInternal

- ea: `0x1400646b4`
- end: `0x140064b9a`
- name: `GreBitBltInternal`
- size: `1254`
- prototype: ``
- caller_count: `27`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140008d60`
- `0x1400095c0`
- `0x14000f0bc`
- `0x14000fafc`
- `0x140021550`
- `0x14005b5c0`
- `0x1400a3944`
- `0x1400a75a4`
- `0x1400a96c8`
- `0x1400aa744`
- `0x1400abef8`
- `0x1400ccbc8`
- `0x1400ce290`
- `0x1400d12dc`
- `0x1400d1774`
- `0x1400d1c28`
- `0x1400d7b3c`
- `0x1401334ac`
- `0x140138efc`
- `0x140197750`
- `0x140215554`
- `0x140239e88`
- `0x140244f00`
- `0x140271d58`
- `0x14028cdbc`
- `0x1402e9394`
- `0x1402f24f0`

## callees

- `0x1400604f0`
- `0x1400645f0`
- `0x1400646b4`
- `0x1400663c0`
- `0x1400781e8`
- `0x14007eef8`
- `0x14007f010`
- `0x140164228`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140064921`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400649ec`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140064921`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400649ec`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400646e4`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400646e4`
- `win32kbase!HmgPentryFromPobj` at `0x140064947`
- `win32kbase!HmgPentryFromPobj` at `0x140064a14`
- `win32kbase!HmgPentryFromPobj` at `0x140064947`
- `win32kbase!HmgPentryFromPobj` at `0x140064a14`
- `win32kbase!PopThreadGuardedObject` at `0x1400648f5`
- `win32kbase!PopThreadGuardedObject` at `0x1400649a5`
- `win32kbase!PopThreadGuardedObject` at `0x1400649c0`
- `win32kbase!PopThreadGuardedObject` at `0x140064a78`
- `win32kbase!PopThreadGuardedObject` at `0x1400648f5`
- `win32kbase!PopThreadGuardedObject` at `0x1400649a5`
- `win32kbase!PopThreadGuardedObject` at `0x1400649c0`
- `win32kbase!PopThreadGuardedObject` at `0x140064a78`
- `win32kbase!PushThreadGuardedObject` at `0x14006471f`
- `win32kbase!PushThreadGuardedObject` at `0x1400647c3`
- `win32kbase!PushThreadGuardedObject` at `0x14006482d`
- `win32kbase!PushThreadGuardedObject` at `0x140064853`
- `win32kbase!PushThreadGuardedObject` at `0x14006471f`
- `win32kbase!PushThreadGuardedObject` at `0x1400647c3`
- `win32kbase!PushThreadGuardedObject` at `0x14006482d`
- `win32kbase!PushThreadGuardedObject` at `0x140064853`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14006497c`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x140064a4b`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14006497c`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x140064a4b`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140064964`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140064a32`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140064964`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140064a32`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140064b4b`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140064b82`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140064b4b`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140064b82`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140064ae4`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140064ae4`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140064acc`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140064acc`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14006473d`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14006473d`
- `win32kbase!EngSetLastError` at `0x140064a9f`
- `win32kbase!EngSetLastError` at `0x140064a9f`

## pseudocode

```c
__int64 __fastcall GreBitBltInternal(
        Gre::Base *a1,
        LONG a2,
        LONG a3,
        int a4,
        int a5,
        __int64 a6,
        int a7,
        LONG a8,
        unsigned int a9,
        unsigned int a10,
        char a11)
{
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // r14d
  DC *v19; // rcx
  unsigned int CurrentProcessId; // eax
  DC *v21; // rdi
  unsigned int v22; // ebx
  char *v23; // rsi
  struct _DC_ATTR *UserAttr; // rax
  DC *v25; // rcx
  unsigned int v26; // eax
  DC *v27; // rbx
  unsigned int v28; // edi
  char *v29; // rsi
  struct _DC_ATTR *v30; // rax
  DC *v32; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+68h] [rbp-98h]
  struct Gre::Base::SESSION_GLOBALS *v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  _OWORD v36[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v37[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v38; // [rsp+C0h] [rbp-40h]
  DC *v39; // [rsp+C8h] [rbp-38h] BYREF
  int v40; // [rsp+D0h] [rbp-30h]
  struct Gre::Base::SESSION_GLOBALS *v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  _OWORD v43[2]; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v44[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v45; // [rsp+128h] [rbp+28h]
  __int16 v46; // [rsp+130h] [rbp+30h]

  v35 = 0;
  v34 = Gre::Base::Globals(a1);
  v32 = 0;
  v33 = 0;
  memset(v36, 0, sizeof(v36));
  PushThreadGuardedObject(
    v36,
    &v32,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  LOBYTE(v15) = 1;
  v16 = HmgLock(v34, a1, v15);
  v32 = (DC *)v16;
  if ( v16 )
  {
    if ( *(_DWORD *)(v16 + 2136) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)(v16 + 12));
      v32 = 0;
    }
  }
  else if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction(v17) != 1 )
  {
    GrepAuditBehaviorRestrictionViolations(1);
  }
  if ( v32 )
  {
    if ( (*((_DWORD *)v32 + 11) & 2) == 0 )
    {
      if ( !(unsigned int)DCOBJ::SaveAttributesHelper((DCOBJ *)&v32) )
      {
        _InterlockedDecrement16((volatile signed __int16 *)v32 + 6);
        v32 = 0;
        goto LABEL_10;
      }
      *((_DWORD *)v32 + 11) |= 2u;
      v33 = 1;
    }
    if ( (*((_DWORD *)v32 + 130) & 4) != 0 )
      DC::vMarkTransformDirty(v32);
  }
LABEL_10:
  memset(v37, 0, sizeof(v37));
  PushThreadGuardedObject(v37, &v32, UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v38 = 1;
  if ( v32 )
  {
    if ( *((_WORD *)v32 + 6) != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    if ( *((_WORD *)v32 + 6) != 1 )
      DCOBJ::vUnlock((DCOBJ *)&v32);
  }
  v41 = v34;
  v42 = 0;
  v39 = 0;
  memset(v43, 0, sizeof(v43));
  v40 = 0;
  PushThreadGuardedObject(
    v43,
    &v39,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  memset(v44, 0, sizeof(v44));
  PushThreadGuardedObject(
    v44,
    &v39,
    UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v45 = a6;
  v46 = 1;
  if ( v32 )
  {
    if ( a6 == *(_QWORD *)v32 )
    {
      v46 = 256;
      v39 = v32;
    }
    v18 = GrepBitBltImpl(&v32, a2, a3, a4, a5, (struct OPTAPIDCOBJ *)&v39, a7, a8, a9, a10, a11);
    if ( !(_BYTE)v46 )
      v39 = 0;
    PopThreadGuardedObject(v44);
    v19 = v39;
    if ( v39 )
    {
      if ( v40 && (*((_DWORD *)v39 + 11) & 2) != 0 )
      {
        CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
        v21 = v39;
        v22 = CurrentProcessId & 0xFFFFFFFC;
        if ( *(_QWORD *)v39 )
        {
          v23 = (char *)HmgPentryFromPobj(v41, v39);
        }
        else
        {
          v23 = (char *)v39 + 2152;
          *(_OWORD *)((char *)v39 + 2152) = 0;
          *((_QWORD *)v21 + 271) = 0;
          *((_DWORD *)v21 + 540) = -2147483630;
          *((_QWORD *)v21 + 271) = GreEncodeUserModePointer(0);
        }
        if ( v22 == (*((_DWORD *)v23 + 2) & 0xFFFFFFFE) )
        {
          UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v39);
          if ( UserAttr )
            DC::RestoreAttributes(v39, UserAttr);
        }
        *((_DWORD *)v39 + 11) &= ~2u;
        v19 = v39;
        v40 = 0;
      }
      _InterlockedDecrement16((volatile signed __int16 *)v19 + 6);
      v39 = 0;
    }
    PopThreadGuardedObject(v43);
    if ( !v38 )
      v32 = 0;
    PopThreadGuardedObject(v37);
    v25 = v32;
    if ( v32 )
    {
      if ( v33 && (*((_DWORD *)v32 + 11) & 2) != 0 )
      {
        v26 = (unsigned int)PsGetCurrentProcessId();
        v27 = v32;
        v28 = v26 & 0xFFFFFFFC;
        if ( *(_QWORD *)v32 )
        {
          v29 = (char *)HmgPentryFromPobj(v34, v32);
        }
        else
        {
          v29 = (char *)v32 + 2152;
          *(_OWORD *)((char *)v32 + 2152) = 0;
          *((_QWORD *)v27 + 271) = 0;
          *((_DWORD *)v27 + 540) = -2147483630;
          *((_QWORD *)v27 + 271) = GreEncodeUserModePointer(0);
        }
        if ( v28 == (*((_DWORD *)v29 + 2) & 0xFFFFFFFE) )
        {
          v30 = DCOBJ::GetUserAttr((DCOBJ *)&v32);
          if ( v30 )
            DC::RestoreAttributes(v32, v30);
        }
        *((_DWORD *)v32 + 11) &= ~2u;
        v25 = v32;
        v33 = 0;
      }
      _InterlockedDecrement16((volatile signed __int16 *)v25 + 6);
      v32 = 0;
    }
    PopThreadGuardedObject(v36);
    return v18;
  }
  else
  {
    EngSetLastError(6u);
    OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)&v39);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v32);
    return 0;
  }
}

```

## disassembly

```asm
0x1400646b4  push    rbp
0x1400646b6  push    rbx
0x1400646b7  push    rsi
0x1400646b8  push    rdi
0x1400646b9  push    r12
0x1400646bb  push    r14
0x1400646bd  push    r15
0x1400646bf  lea     rbp, [rsp-40h]
0x1400646c4  sub     rsp, 140h
0x1400646cb  xor     r15d, r15d
0x1400646ce  mov     edi, r9d
0x1400646d1  mov     [rsp+170h+var_110], r15
0x1400646d6  mov     esi, r8d
0x1400646d9  mov     [rsp+170h+var_108], r15d
0x1400646de  mov     r14d, edx
0x1400646e1  mov     rbx, rcx
0x1400646e4  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400646eb  nop     dword ptr [rax+rax+00h]
0x1400646f0  xorps   xmm0, xmm0
0x1400646f3  mov     [rsp+170h+var_F8], r15
0x1400646f8  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x1400646ff  mov     [rsp+170h+var_100], rax
0x140064704  lea     rdx, [rsp+170h+var_110]
0x140064709  mov     [rsp+170h+var_110], r15
0x14006470e  lea     rcx, [rbp+70h+var_F0]
0x140064712  mov     [rsp+170h+var_108], r15d
0x140064717  movups  [rbp+70h+var_F0], xmm0
0x14006471b  movups  [rbp+70h+var_E0], xmm0
0x14006471f  call    cs:__imp_PushThreadGuardedObject
0x140064726  nop     dword ptr [rax+rax+00h]
0x14006472b  mov     rcx, [rsp+170h+var_100]
0x140064730  lea     r12d, [r15+1]
0x140064734  mov     r8b, r12b
0x140064737  xor     r9d, r9d
0x14006473a  mov     rdx, rbx
0x14006473d  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140064744  nop     dword ptr [rax+rax+00h]
0x140064749  mov     [rsp+170h+var_110], rax
0x14006474e  test    rax, rax
0x140064751  jz      loc_140064ACC
0x140064757  cmp     [rax+858h], r15d
0x14006475e  jnz     loc_140064AFF
0x140064764  mov     rax, [rsp+170h+var_110]
0x140064769  test    rax, rax
0x14006476c  jz      short loc_1400647A8
0x14006476e  mov     eax, [rax+2Ch]
0x140064771  test    al, 2
0x140064773  jnz     short loc_140064795
0x140064775  lea     rcx, [rsp+170h+var_110]; this
0x14006477a  call    ?SaveAttributesHelper@DCOBJ@@AEAAHXZ; DCOBJ::SaveAttributesHelper(void)
0x14006477f  test    eax, eax
0x140064781  mov     rax, [rsp+170h+var_110]
0x140064786  jz      loc_140064B0E
0x14006478c  or      dword ptr [rax+2Ch], 2
0x140064790  mov     [rsp+170h+var_108], r12d
0x140064795  mov     rcx, [rsp+170h+var_110]; this
0x14006479a  mov     eax, [rcx+208h]
0x1400647a0  test    al, 4
0x1400647a2  jnz     loc_140064AC2
0x1400647a8  xorps   xmm0, xmm0
0x1400647ab  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x1400647b2  lea     rdx, [rsp+170h+var_110]
0x1400647b7  lea     rcx, [rbp+70h+var_D0]
0x1400647bb  movups  [rbp+70h+var_D0], xmm0
0x1400647bf  movups  [rbp+70h+var_C0], xmm0
0x1400647c3  call    cs:__imp_PushThreadGuardedObject
0x1400647ca  nop     dword ptr [rax+rax+00h]
0x1400647cf  mov     rax, [rsp+170h+var_110]
0x1400647d4  mov     [rbp+70h+var_B0], r12b
0x1400647d8  test    rax, rax
0x1400647db  jz      short loc_1400647FE
0x1400647dd  movzx   eax, word ptr [rax+0Ch]
0x1400647e1  cmp     ax, r12w
0x1400647e5  jnz     loc_140064AF5
0x1400647eb  mov     rax, [rsp+170h+var_110]
0x1400647f0  movzx   ecx, word ptr [rax+0Ch]
0x1400647f4  cmp     cx, r12w
0x1400647f8  jnz     loc_140064B1D
0x1400647fe  mov     rax, [rsp+170h+var_100]
0x140064803  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14006480a  xorps   xmm0, xmm0
0x14006480d  mov     [rbp+70h+var_98], rax
0x140064811  lea     rdx, [rbp+70h+var_A8]
0x140064815  mov     [rbp+70h+var_90], r15
0x140064819  lea     rcx, [rbp+70h+var_88]
0x14006481d  mov     [rbp+70h+var_A8], r15
0x140064821  movups  [rbp+70h+var_88], xmm0
0x140064825  mov     [rbp+70h+var_A0], r15d
0x140064829  movups  [rbp+70h+var_78], xmm0
0x14006482d  call    cs:__imp_PushThreadGuardedObject
0x140064834  nop     dword ptr [rax+rax+00h]
0x140064839  xorps   xmm0, xmm0
0x14006483c  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VOPTAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x140064843  lea     rdx, [rbp+70h+var_A8]
0x140064847  lea     rcx, [rbp+70h+var_68]
0x14006484b  movups  [rbp+70h+var_68], xmm0
0x14006484f  movups  [rbp+70h+var_58], xmm0
0x140064853  call    cs:__imp_PushThreadGuardedObject
0x14006485a  nop     dword ptr [rax+rax+00h]
0x14006485f  mov     rax, [rsp+170h+var_110]
0x140064864  mov     rcx, [rbp+70h+arg_28]
0x14006486b  mov     [rbp+70h+var_48], rcx
0x14006486f  mov     [rbp+70h+var_40], r12w
0x140064874  test    rax, rax
0x140064877  jz      loc_140064A9A
0x14006487d  cmp     rcx, [rax]
0x140064880  jnz     short loc_14006488C
0x140064882  mov     [rbp+70h+var_40], 100h
0x140064888  mov     [rbp+70h+var_A8], rax
0x14006488c  mov     eax, [rbp+70h+arg_50]
0x140064892  lea     rcx, [rsp+170h+var_110]; struct XDCOBJ *
0x140064897  mov     [rsp+170h+var_120], eax; unsigned int
0x14006489b  mov     r9d, edi; int
0x14006489e  mov     eax, [rbp+70h+arg_48]
0x1400648a4  mov     r8d, esi; int
0x1400648a7  mov     [rsp+170h+var_128], eax; unsigned int
0x1400648ab  mov     edx, r14d; int
0x1400648ae  mov     eax, [rbp+70h+arg_40]
0x1400648b4  mov     [rsp+170h+var_130], eax; unsigned int
0x1400648b8  mov     eax, [rbp+70h+arg_38]
0x1400648be  mov     [rsp+170h+var_138], eax; int
0x1400648c2  mov     eax, [rbp+70h+arg_30]
0x1400648c8  mov     [rsp+170h+var_140], eax; int
0x1400648cc  lea     rax, [rbp+70h+var_A8]
0x1400648d0  mov     [rsp+170h+var_148], rax; struct OPTAPIDCOBJ *
0x1400648d5  mov     eax, [rbp+70h+arg_20]
0x1400648db  mov     [rsp+170h+var_150], eax; int
0x1400648df  call    ?GrepBitBltImpl@@YAHAEAVXDCOBJ@@HHHHAEAVOPTAPIDCOBJ@@HHKKK@Z; GrepBitBltImpl(XDCOBJ &,int,int,int,int,OPTAPIDCOBJ &,int,int,ulong,ulong,ulong)
0x1400648e4  mov     r14d, eax
0x1400648e7  cmp     byte ptr [rbp+70h+var_40], r15b
0x1400648eb  jnz     short loc_1400648F1
0x1400648ed  mov     [rbp+70h+var_A8], r15
0x1400648f1  lea     rcx, [rbp+70h+var_68]
0x1400648f5  call    cs:__imp_PopThreadGuardedObject
0x1400648fc  nop     dword ptr [rax+rax+00h]
0x140064901  mov     rcx, [rbp+70h+var_A8]
0x140064905  mov     r12d, 0FFFFFFFCh
0x14006490b  test    rcx, rcx
0x14006490e  jz      loc_1400649A1
0x140064914  cmp     [rbp+70h+var_A0], r15d
0x140064918  jz      short loc_140064998
0x14006491a  mov     eax, [rcx+2Ch]
0x14006491d  test    al, 2
0x14006491f  jz      short loc_140064998
0x140064921  call    cs:__imp_PsGetCurrentProcessId
0x140064928  nop     dword ptr [rax+rax+00h]
0x14006492d  mov     rdi, [rbp+70h+var_A8]
0x140064931  mov     rbx, rax
0x140064934  and     ebx, r12d
0x140064937  cmp     [rdi], r15
0x14006493a  jz      loc_140064B2C
0x140064940  mov     rcx, [rbp+70h+var_98]
0x140064944  mov     rdx, rdi
0x140064947  call    cs:__imp_HmgPentryFromPobj
0x14006494e  nop     dword ptr [rax+rax+00h]
0x140064953  mov     rsi, rax
0x140064956  mov     eax, [rsi+8]
0x140064959  and     eax, 0FFFFFFFEh
0x14006495c  cmp     ebx, eax
0x14006495e  jnz     short loc_140064988
0x140064960  lea     rcx, [rbp+70h+var_A8]
0x140064964  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x14006496b  nop     dword ptr [rax+rax+00h]
0x140064970  test    rax, rax
0x140064973  jz      short loc_140064988
0x140064975  mov     rcx, [rbp+70h+var_A8]
0x140064979  mov     rdx, rax
0x14006497c  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x140064983  nop     dword ptr [rax+rax+00h]
0x140064988  mov     rax, [rbp+70h+var_A8]
0x14006498c  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x140064990  mov     rcx, [rbp+70h+var_A8]
0x140064994  mov     [rbp+70h+var_A0], r15d
0x140064998  lock dec word ptr [rcx+0Ch]
0x14006499d  mov     [rbp+70h+var_A8], r15
0x1400649a1  lea     rcx, [rbp+70h+var_88]
0x1400649a5  call    cs:__imp_PopThreadGuardedObject
0x1400649ac  nop     dword ptr [rax+rax+00h]
0x1400649b1  cmp     [rbp+70h+var_B0], r15b
0x1400649b5  jnz     short loc_1400649BC
0x1400649b7  mov     [rsp+170h+var_110], r15
0x1400649bc  lea     rcx, [rbp+70h+var_D0]
0x1400649c0  call    cs:__imp_PopThreadGuardedObject
0x1400649c7  nop     dword ptr [rax+rax+00h]
0x1400649cc  mov     rcx, [rsp+170h+var_110]
0x1400649d1  test    rcx, rcx
0x1400649d4  jz      loc_140064A74
0x1400649da  cmp     [rsp+170h+var_108], r15d
0x1400649df  jz      loc_140064A6A
0x1400649e5  mov     eax, [rcx+2Ch]
0x1400649e8  test    al, 2
0x1400649ea  jz      short loc_140064A6A
0x1400649ec  call    cs:__imp_PsGetCurrentProcessId
0x1400649f3  nop     dword ptr [rax+rax+00h]
0x1400649f8  mov     rbx, [rsp+170h+var_110]
0x1400649fd  mov     rdi, rax
0x140064a00  and     edi, r12d
0x140064a03  cmp     [rbx], r15
0x140064a06  jz      loc_140064B63
0x140064a0c  mov     rcx, [rsp+170h+var_100]
0x140064a11  mov     rdx, rbx
0x140064a14  call    cs:__imp_HmgPentryFromPobj
0x140064a1b  nop     dword ptr [rax+rax+00h]
0x140064a20  mov     rsi, rax
0x140064a23  mov     eax, [rsi+8]
0x140064a26  and     eax, 0FFFFFFFEh
0x140064a29  cmp     edi, eax
0x140064a2b  jnz     short loc_140064A57
0x140064a2d  lea     rcx, [rsp+170h+var_110]
0x140064a32  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x140064a39  nop     dword ptr [rax+rax+00h]
0x140064a3e  test    rax, rax
0x140064a41  jz      short loc_140064A57
0x140064a43  mov     rcx, [rsp+170h+var_110]
0x140064a48  mov     rdx, rax
0x140064a4b  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x140064a52  nop     dword ptr [rax+rax+00h]
0x140064a57  mov     rax, [rsp+170h+var_110]
0x140064a5c  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x140064a60  mov     rcx, [rsp+170h+var_110]
0x140064a65  mov     [rsp+170h+var_108], r15d
0x140064a6a  lock dec word ptr [rcx+0Ch]
0x140064a6f  mov     [rsp+170h+var_110], r15
0x140064a74  lea     rcx, [rbp+70h+var_F0]
0x140064a78  call    cs:__imp_PopThreadGuardedObject
0x140064a7f  nop     dword ptr [rax+rax+00h]
0x140064a84  mov     eax, r14d
0x140064a87  add     rsp, 140h
0x140064a8e  pop     r15
0x140064a90  pop     r14
0x140064a92  pop     r12
0x140064a94  pop     rdi
0x140064a95  pop     rsi
0x140064a96  pop     rbx
0x140064a97  pop     rbp
0x140064a98  retn
0x140064a9a  mov     ecx, 6; iError
0x140064a9f  call    cs:__imp_EngSetLastError
0x140064aa6  nop     dword ptr [rax+rax+00h]
0x140064aab  lea     rcx, [rbp+70h+var_A8]; this
0x140064aaf  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x140064ab4  lea     rcx, [rsp+170h+var_110]; this
0x140064ab9  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x140064abe  xor     eax, eax
0x140064ac0  jmp     short loc_140064A87
0x140064ac2  call    ?vMarkTransformDirty@DC@@QEAAXXZ; DC::vMarkTransformDirty(void)
0x140064ac7  jmp     loc_1400647A8
0x140064acc  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x140064ad3  nop     dword ptr [rax+rax+00h]
0x140064ad8  cmp     eax, r12d
0x140064adb  jz      loc_140064764
0x140064ae1  mov     ecx, r12d
0x140064ae4  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x140064aeb  nop     dword ptr [rax+rax+00h]
0x140064af0  jmp     loc_140064764
0x140064af5  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140064afa  jmp     loc_1400647EB
0x140064aff  lock dec word ptr [rax+0Ch]
0x140064b04  mov     [rsp+170h+var_110], r15
0x140064b09  jmp     loc_140064764
0x140064b0e  lock dec word ptr [rax+0Ch]
0x140064b13  mov     [rsp+170h+var_110], r15
0x140064b18  jmp     loc_1400647A8
0x140064b1d  lea     rcx, [rsp+170h+var_110]; this
0x140064b22  call    ?vUnlock@DCOBJ@@QEAAXXZ; DCOBJ::vUnlock(void)
0x140064b27  jmp     loc_1400647FE
0x140064b2c  xorps   xmm0, xmm0
0x140064b2f  lea     rsi, [rdi+868h]
0x140064b36  movups  xmmword ptr [rsi], xmm0
0x140064b39  xor     eax, eax
0x140064b3b  xor     ecx, ecx
0x140064b3d  mov     [rsi+10h], rax
0x140064b41  mov     dword ptr [rdi+870h], 80000012h
0x140064b4b  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x140064b52  nop     dword ptr [rax+rax+00h]
0x140064b57  mov     [rdi+878h], rax
0x140064b5e  jmp     loc_140064956
0x140064b63  xorps   xmm0, xmm0
0x140064b66  lea     rsi, [rbx+868h]
0x140064b6d  movups  xmmword ptr [rsi], xmm0
0x140064b70  xor     eax, eax
0x140064b72  xor     ecx, ecx
0x140064b74  mov     [rsi+10h], rax
0x140064b78  mov     dword ptr [rbx+870h], 80000012h
0x140064b82  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x140064b89  nop     dword ptr [rax+rax+00h]
0x140064b8e  mov     [rbx+878h], rax
0x140064b95  jmp     loc_140064A23
```
