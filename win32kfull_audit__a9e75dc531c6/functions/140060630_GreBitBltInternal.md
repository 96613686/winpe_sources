# GreBitBltInternal

- ea: `0x140060630`
- end: `0x140060b16`
- name: `GreBitBltInternal`
- size: `1254`
- prototype: `__int64 __fastcall(Gre::Base *, int, int, int, int, __int64, int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `27`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000a7d4`
- `0x14000c8b0`
- `0x14001c384`
- `0x14003609c`
- `0x140038a8c`
- `0x14003b4c4`
- `0x140096770`
- `0x1400a76b4`
- `0x1400cb970`
- `0x1400cbf30`
- `0x1400d1534`
- `0x1401ae678`
- `0x1401ebf38`
- `0x1401eca34`
- `0x1401edd10`
- `0x1401eef54`
- `0x1401ef3fc`
- `0x1401ef8b0`
- `0x1401f0594`
- `0x1401f0910`
- `0x140203ddc`
- `0x140216be0`
- `0x140245f70`
- `0x140275878`
- `0x14028f2ac`
- `0x1402eb1a8`
- `0x1402f4370`

## callees

- `0x1400539b0`
- `0x14005b820`
- `0x14005b938`
- `0x1400601c0`
- `0x140060630`
- `0x140062340`
- `0x1400a4e80`
- `0x140154d18`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14006089d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140060968`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14006089d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140060968`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060660`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140060660`
- `win32kbase!HmgPentryFromPobj` at `0x1400608c3`
- `win32kbase!HmgPentryFromPobj` at `0x140060990`
- `win32kbase!HmgPentryFromPobj` at `0x1400608c3`
- `win32kbase!HmgPentryFromPobj` at `0x140060990`
- `win32kbase!PopThreadGuardedObject` at `0x140060871`
- `win32kbase!PopThreadGuardedObject` at `0x140060921`
- `win32kbase!PopThreadGuardedObject` at `0x14006093c`
- `win32kbase!PopThreadGuardedObject` at `0x1400609f4`
- `win32kbase!PopThreadGuardedObject` at `0x140060871`
- `win32kbase!PopThreadGuardedObject` at `0x140060921`
- `win32kbase!PopThreadGuardedObject` at `0x14006093c`
- `win32kbase!PopThreadGuardedObject` at `0x1400609f4`
- `win32kbase!PushThreadGuardedObject` at `0x14006069b`
- `win32kbase!PushThreadGuardedObject` at `0x14006073f`
- `win32kbase!PushThreadGuardedObject` at `0x1400607a9`
- `win32kbase!PushThreadGuardedObject` at `0x1400607cf`
- `win32kbase!PushThreadGuardedObject` at `0x14006069b`
- `win32kbase!PushThreadGuardedObject` at `0x14006073f`
- `win32kbase!PushThreadGuardedObject` at `0x1400607a9`
- `win32kbase!PushThreadGuardedObject` at `0x1400607cf`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x1400608f8`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x1400609c7`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x1400608f8`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x1400609c7`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x1400608e0`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x1400609ae`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x1400608e0`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x1400609ae`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140060ac7`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140060afe`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140060ac7`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140060afe`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140060a60`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140060a60`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140060a48`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140060a48`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400606b9`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400606b9`
- `win32kbase!EngSetLastError` at `0x140060a1b`
- `win32kbase!EngSetLastError` at `0x140060a1b`

## pseudocode

```c
__int64 __fastcall GreBitBltInternal(
        Gre::Base *a1,
        int a2,
        int a3,
        int a4,
        int a5,
        __int64 a6,
        int a7,
        int a8,
        unsigned int a9,
        unsigned int a10,
        unsigned int a11)
{
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned int v20; // r14d
  DC *v21; // rcx
  unsigned int CurrentProcessId; // eax
  DC *v23; // rdi
  unsigned int v24; // ebx
  char *v25; // rsi
  struct _DC_ATTR *UserAttr; // rax
  DC *v27; // rcx
  unsigned int v28; // eax
  DC *v29; // rbx
  unsigned int v30; // edi
  char *v31; // rsi
  struct _DC_ATTR *v32; // rax
  DC *v34; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+68h] [rbp-98h]
  struct Gre::Base::SESSION_GLOBALS *v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+78h] [rbp-88h]
  _OWORD v38[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v39[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v40; // [rsp+C0h] [rbp-40h]
  DC *v41; // [rsp+C8h] [rbp-38h] BYREF
  int v42; // [rsp+D0h] [rbp-30h]
  struct Gre::Base::SESSION_GLOBALS *v43; // [rsp+D8h] [rbp-28h]
  __int64 v44; // [rsp+E0h] [rbp-20h]
  _OWORD v45[2]; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v46[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v47; // [rsp+128h] [rbp+28h]
  __int16 v48; // [rsp+130h] [rbp+30h]

  v37 = 0;
  v36 = Gre::Base::Globals(a1);
  v34 = 0;
  v35 = 0;
  memset(v38, 0, sizeof(v38));
  PushThreadGuardedObject(
    v38,
    &v34,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  LOBYTE(v15) = 1;
  v16 = HmgLock(v36, a1, v15, 0);
  v34 = (DC *)v16;
  if ( v16 )
  {
    if ( *(_DWORD *)(v16 + 2136) )
    {
      _InterlockedDecrement16((volatile signed __int16 *)(v16 + 12));
      v34 = 0;
    }
  }
  else if ( (unsigned int)GrepGetCurrentProcessBehaviorRestriction(v17) != 1 )
  {
    GrepAuditBehaviorRestrictionViolations(1);
  }
  if ( v34 )
  {
    if ( (*((_DWORD *)v34 + 11) & 2) == 0 )
    {
      if ( !DCOBJ::SaveAttributesHelper((DCOBJ *)&v34) )
      {
        _InterlockedDecrement16((volatile signed __int16 *)v34 + 6);
        v34 = 0;
        goto LABEL_10;
      }
      *((_DWORD *)v34 + 11) |= 2u;
      v35 = 1;
    }
    if ( (*((_DWORD *)v34 + 130) & 4) != 0 )
      DC::vMarkTransformDirty(v34);
  }
LABEL_10:
  memset(v39, 0, sizeof(v39));
  PushThreadGuardedObject(v39, &v34, UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v40 = 1;
  if ( v34 )
  {
    if ( *((_WORD *)v34 + 6) != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v19, v18);
    if ( *((_WORD *)v34 + 6) != 1 )
      DCOBJ::vUnlock((DCOBJ *)&v34);
  }
  v43 = v36;
  v44 = 0;
  v41 = 0;
  memset(v45, 0, sizeof(v45));
  v42 = 0;
  PushThreadGuardedObject(
    v45,
    &v41,
    UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic);
  memset(v46, 0, sizeof(v46));
  PushThreadGuardedObject(
    v46,
    &v41,
    UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::OnUnexpectedThreadTerminationStatic);
  v47 = a6;
  v48 = 1;
  if ( v34 )
  {
    if ( a6 == *(_QWORD *)v34 )
    {
      v48 = 256;
      v41 = v34;
    }
    v20 = GrepBitBltImpl((struct XDCOBJ *)&v34, a2, a3, a4, a5, (struct OPTAPIDCOBJ *)&v41, a7, a8, a9, a10, a11);
    if ( !(_BYTE)v48 )
      v41 = 0;
    PopThreadGuardedObject(v46);
    v21 = v41;
    if ( v41 )
    {
      if ( v42 && (*((_DWORD *)v41 + 11) & 2) != 0 )
      {
        CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
        v23 = v41;
        v24 = CurrentProcessId & 0xFFFFFFFC;
        if ( *(_QWORD *)v41 )
        {
          v25 = (char *)HmgPentryFromPobj(v43, v41);
        }
        else
        {
          v25 = (char *)v41 + 2152;
          *(_OWORD *)((char *)v41 + 2152) = 0;
          *((_QWORD *)v23 + 271) = 0;
          *((_DWORD *)v23 + 540) = -2147483630;
          *((_QWORD *)v23 + 271) = GreEncodeUserModePointer(0);
        }
        if ( v24 == (*((_DWORD *)v25 + 2) & 0xFFFFFFFE) )
        {
          UserAttr = DCOBJ::GetUserAttr((DCOBJ *)&v41);
          if ( UserAttr )
            DC::RestoreAttributes(v41, UserAttr);
        }
        *((_DWORD *)v41 + 11) &= ~2u;
        v21 = v41;
        v42 = 0;
      }
      _InterlockedDecrement16((volatile signed __int16 *)v21 + 6);
      v41 = 0;
    }
    PopThreadGuardedObject(v45);
    if ( !v40 )
      v34 = 0;
    PopThreadGuardedObject(v39);
    v27 = v34;
    if ( v34 )
    {
      if ( v35 && (*((_DWORD *)v34 + 11) & 2) != 0 )
      {
        v28 = (unsigned int)PsGetCurrentProcessId();
        v29 = v34;
        v30 = v28 & 0xFFFFFFFC;
        if ( *(_QWORD *)v34 )
        {
          v31 = (char *)HmgPentryFromPobj(v36, v34);
        }
        else
        {
          v31 = (char *)v34 + 2152;
          *(_OWORD *)((char *)v34 + 2152) = 0;
          *((_QWORD *)v29 + 271) = 0;
          *((_DWORD *)v29 + 540) = -2147483630;
          *((_QWORD *)v29 + 271) = GreEncodeUserModePointer(0);
        }
        if ( v30 == (*((_DWORD *)v31 + 2) & 0xFFFFFFFE) )
        {
          v32 = DCOBJ::GetUserAttr((DCOBJ *)&v34);
          if ( v32 )
            DC::RestoreAttributes(v34, v32);
        }
        *((_DWORD *)v34 + 11) &= ~2u;
        v27 = v34;
        v35 = 0;
      }
      _InterlockedDecrement16((volatile signed __int16 *)v27 + 6);
      v34 = 0;
    }
    PopThreadGuardedObject(v38);
    return v20;
  }
  else
  {
    EngSetLastError(6u);
    OPTAPIDCOBJ::~OPTAPIDCOBJ((OPTAPIDCOBJ *)&v41);
    APIDCOBJ::~APIDCOBJ((APIDCOBJ *)&v34);
    return 0;
  }
}

```

## disassembly

```asm
0x140060630  push    rbp
0x140060632  push    rbx
0x140060633  push    rsi
0x140060634  push    rdi
0x140060635  push    r12
0x140060637  push    r14
0x140060639  push    r15
0x14006063b  lea     rbp, [rsp-40h]
0x140060640  sub     rsp, 140h
0x140060647  xor     r15d, r15d
0x14006064a  mov     edi, r9d
0x14006064d  mov     [rsp+170h+var_110], r15
0x140060652  mov     esi, r8d
0x140060655  mov     [rsp+170h+var_108], r15d
0x14006065a  mov     r14d, edx
0x14006065d  mov     rbx, rcx
0x140060660  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x140060667  nop     dword ptr [rax+rax+00h]
0x14006066c  xorps   xmm0, xmm0
0x14006066f  mov     [rsp+170h+var_F8], r15
0x140060674  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x14006067b  mov     [rsp+170h+var_100], rax
0x140060680  lea     rdx, [rsp+170h+var_110]
0x140060685  mov     [rsp+170h+var_110], r15
0x14006068a  lea     rcx, [rbp+70h+var_F0]
0x14006068e  mov     [rsp+170h+var_108], r15d
0x140060693  movups  [rbp+70h+var_F0], xmm0
0x140060697  movups  [rbp+70h+var_E0], xmm0
0x14006069b  call    cs:__imp_PushThreadGuardedObject
0x1400606a2  nop     dword ptr [rax+rax+00h]
0x1400606a7  mov     rcx, [rsp+170h+var_100]
0x1400606ac  lea     r12d, [r15+1]
0x1400606b0  mov     r8b, r12b
0x1400606b3  xor     r9d, r9d
0x1400606b6  mov     rdx, rbx
0x1400606b9  call    cs:__imp_?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x1400606c0  nop     dword ptr [rax+rax+00h]
0x1400606c5  mov     [rsp+170h+var_110], rax
0x1400606ca  test    rax, rax
0x1400606cd  jz      loc_140060A48
0x1400606d3  cmp     [rax+858h], r15d
0x1400606da  jnz     loc_140060A7B
0x1400606e0  mov     rax, [rsp+170h+var_110]
0x1400606e5  test    rax, rax
0x1400606e8  jz      short loc_140060724
0x1400606ea  mov     eax, [rax+2Ch]
0x1400606ed  test    al, 2
0x1400606ef  jnz     short loc_140060711
0x1400606f1  lea     rcx, [rsp+170h+var_110]; this
0x1400606f6  call    ?SaveAttributesHelper@DCOBJ@@AEAAHXZ; DCOBJ::SaveAttributesHelper(void)
0x1400606fb  test    eax, eax
0x1400606fd  mov     rax, [rsp+170h+var_110]
0x140060702  jz      loc_140060A8A
0x140060708  or      dword ptr [rax+2Ch], 2
0x14006070c  mov     [rsp+170h+var_108], r12d
0x140060711  mov     rcx, [rsp+170h+var_110]; this
0x140060716  mov     eax, [rcx+208h]
0x14006071c  test    al, 4
0x14006071e  jnz     loc_140060A3E
0x140060724  xorps   xmm0, xmm0
0x140060727  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<APIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x14006072e  lea     rdx, [rsp+170h+var_110]
0x140060733  lea     rcx, [rbp+70h+var_D0]
0x140060737  movups  [rbp+70h+var_D0], xmm0
0x14006073b  movups  [rbp+70h+var_C0], xmm0
0x14006073f  call    cs:__imp_PushThreadGuardedObject
0x140060746  nop     dword ptr [rax+rax+00h]
0x14006074b  mov     rax, [rsp+170h+var_110]
0x140060750  mov     [rbp+70h+var_B0], r12b
0x140060754  test    rax, rax
0x140060757  jz      short loc_14006077A
0x140060759  movzx   eax, word ptr [rax+0Ch]
0x14006075d  cmp     ax, r12w
0x140060761  jnz     loc_140060A71
0x140060767  mov     rax, [rsp+170h+var_110]
0x14006076c  movzx   ecx, word ptr [rax+0Ch]
0x140060770  cmp     cx, r12w
0x140060774  jnz     loc_140060A99
0x14006077a  mov     rax, [rsp+170h+var_100]
0x14006077f  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@V?$HmgLockResult@VMETA@@@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<HmgLockResult<META>>::OnUnexpectedThreadTerminationStatic(void *)
0x140060786  xorps   xmm0, xmm0
0x140060789  mov     [rbp+70h+var_98], rax
0x14006078d  lea     rdx, [rbp+70h+var_A8]
0x140060791  mov     [rbp+70h+var_90], r15
0x140060795  lea     rcx, [rbp+70h+var_88]
0x140060799  mov     [rbp+70h+var_A8], r15
0x14006079d  movups  [rbp+70h+var_88], xmm0
0x1400607a1  mov     [rbp+70h+var_A0], r15d
0x1400607a5  movups  [rbp+70h+var_78], xmm0
0x1400607a9  call    cs:__imp_PushThreadGuardedObject
0x1400607b0  nop     dword ptr [rax+rax+00h]
0x1400607b5  xorps   xmm0, xmm0
0x1400607b8  lea     r8, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VOPTAPIDCOBJ@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<OPTAPIDCOBJ>::OnUnexpectedThreadTerminationStatic(void *)
0x1400607bf  lea     rdx, [rbp+70h+var_A8]
0x1400607c3  lea     rcx, [rbp+70h+var_68]
0x1400607c7  movups  [rbp+70h+var_68], xmm0
0x1400607cb  movups  [rbp+70h+var_58], xmm0
0x1400607cf  call    cs:__imp_PushThreadGuardedObject
0x1400607d6  nop     dword ptr [rax+rax+00h]
0x1400607db  mov     rax, [rsp+170h+var_110]
0x1400607e0  mov     rcx, [rbp+70h+arg_28]
0x1400607e7  mov     [rbp+70h+var_48], rcx
0x1400607eb  mov     [rbp+70h+var_40], r12w
0x1400607f0  test    rax, rax
0x1400607f3  jz      loc_140060A16
0x1400607f9  cmp     rcx, [rax]
0x1400607fc  jnz     short loc_140060808
0x1400607fe  mov     [rbp+70h+var_40], 100h
0x140060804  mov     [rbp+70h+var_A8], rax
0x140060808  mov     eax, [rbp+70h+arg_50]
0x14006080e  lea     rcx, [rsp+170h+var_110]; struct XDCOBJ *
0x140060813  mov     [rsp+170h+var_120], eax; unsigned int
0x140060817  mov     r9d, edi; int
0x14006081a  mov     eax, [rbp+70h+arg_48]
0x140060820  mov     r8d, esi; int
0x140060823  mov     [rsp+170h+var_128], eax; unsigned int
0x140060827  mov     edx, r14d; int
0x14006082a  mov     eax, [rbp+70h+arg_40]
0x140060830  mov     [rsp+170h+var_130], eax; unsigned int
0x140060834  mov     eax, [rbp+70h+arg_38]
0x14006083a  mov     [rsp+170h+var_138], eax; int
0x14006083e  mov     eax, [rbp+70h+arg_30]
0x140060844  mov     [rsp+170h+var_140], eax; int
0x140060848  lea     rax, [rbp+70h+var_A8]
0x14006084c  mov     [rsp+170h+var_148], rax; struct OPTAPIDCOBJ *
0x140060851  mov     eax, [rbp+70h+arg_20]
0x140060857  mov     [rsp+170h+var_150], eax; int
0x14006085b  call    ?GrepBitBltImpl@@YAHAEAVXDCOBJ@@HHHHAEAVOPTAPIDCOBJ@@HHKKK@Z; GrepBitBltImpl(XDCOBJ &,int,int,int,int,OPTAPIDCOBJ &,int,int,ulong,ulong,ulong)
0x140060860  mov     r14d, eax
0x140060863  cmp     byte ptr [rbp+70h+var_40], r15b
0x140060867  jnz     short loc_14006086D
0x140060869  mov     [rbp+70h+var_A8], r15
0x14006086d  lea     rcx, [rbp+70h+var_68]
0x140060871  call    cs:__imp_PopThreadGuardedObject
0x140060878  nop     dword ptr [rax+rax+00h]
0x14006087d  mov     rcx, [rbp+70h+var_A8]
0x140060881  mov     r12d, 0FFFFFFFCh
0x140060887  test    rcx, rcx
0x14006088a  jz      loc_14006091D
0x140060890  cmp     [rbp+70h+var_A0], r15d
0x140060894  jz      short loc_140060914
0x140060896  mov     eax, [rcx+2Ch]
0x140060899  test    al, 2
0x14006089b  jz      short loc_140060914
0x14006089d  call    cs:__imp_PsGetCurrentProcessId
0x1400608a4  nop     dword ptr [rax+rax+00h]
0x1400608a9  mov     rdi, [rbp+70h+var_A8]
0x1400608ad  mov     rbx, rax
0x1400608b0  and     ebx, r12d
0x1400608b3  cmp     [rdi], r15
0x1400608b6  jz      loc_140060AA8
0x1400608bc  mov     rcx, [rbp+70h+var_98]
0x1400608c0  mov     rdx, rdi
0x1400608c3  call    cs:__imp_HmgPentryFromPobj
0x1400608ca  nop     dword ptr [rax+rax+00h]
0x1400608cf  mov     rsi, rax
0x1400608d2  mov     eax, [rsi+8]
0x1400608d5  and     eax, 0FFFFFFFEh
0x1400608d8  cmp     ebx, eax
0x1400608da  jnz     short loc_140060904
0x1400608dc  lea     rcx, [rbp+70h+var_A8]
0x1400608e0  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x1400608e7  nop     dword ptr [rax+rax+00h]
0x1400608ec  test    rax, rax
0x1400608ef  jz      short loc_140060904
0x1400608f1  mov     rcx, [rbp+70h+var_A8]
0x1400608f5  mov     rdx, rax
0x1400608f8  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x1400608ff  nop     dword ptr [rax+rax+00h]
0x140060904  mov     rax, [rbp+70h+var_A8]
0x140060908  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x14006090c  mov     rcx, [rbp+70h+var_A8]
0x140060910  mov     [rbp+70h+var_A0], r15d
0x140060914  lock dec word ptr [rcx+0Ch]
0x140060919  mov     [rbp+70h+var_A8], r15
0x14006091d  lea     rcx, [rbp+70h+var_88]
0x140060921  call    cs:__imp_PopThreadGuardedObject
0x140060928  nop     dword ptr [rax+rax+00h]
0x14006092d  cmp     [rbp+70h+var_B0], r15b
0x140060931  jnz     short loc_140060938
0x140060933  mov     [rsp+170h+var_110], r15
0x140060938  lea     rcx, [rbp+70h+var_D0]
0x14006093c  call    cs:__imp_PopThreadGuardedObject
0x140060943  nop     dword ptr [rax+rax+00h]
0x140060948  mov     rcx, [rsp+170h+var_110]
0x14006094d  test    rcx, rcx
0x140060950  jz      loc_1400609F0
0x140060956  cmp     [rsp+170h+var_108], r15d
0x14006095b  jz      loc_1400609E6
0x140060961  mov     eax, [rcx+2Ch]
0x140060964  test    al, 2
0x140060966  jz      short loc_1400609E6
0x140060968  call    cs:__imp_PsGetCurrentProcessId
0x14006096f  nop     dword ptr [rax+rax+00h]
0x140060974  mov     rbx, [rsp+170h+var_110]
0x140060979  mov     rdi, rax
0x14006097c  and     edi, r12d
0x14006097f  cmp     [rbx], r15
0x140060982  jz      loc_140060ADF
0x140060988  mov     rcx, [rsp+170h+var_100]
0x14006098d  mov     rdx, rbx
0x140060990  call    cs:__imp_HmgPentryFromPobj
0x140060997  nop     dword ptr [rax+rax+00h]
0x14006099c  mov     rsi, rax
0x14006099f  mov     eax, [rsi+8]
0x1400609a2  and     eax, 0FFFFFFFEh
0x1400609a5  cmp     edi, eax
0x1400609a7  jnz     short loc_1400609D3
0x1400609a9  lea     rcx, [rsp+170h+var_110]
0x1400609ae  call    cs:__imp_?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ; DCOBJ::GetUserAttr(void)
0x1400609b5  nop     dword ptr [rax+rax+00h]
0x1400609ba  test    rax, rax
0x1400609bd  jz      short loc_1400609D3
0x1400609bf  mov     rcx, [rsp+170h+var_110]
0x1400609c4  mov     rdx, rax
0x1400609c7  call    cs:__imp_?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z; DC::RestoreAttributes(_DC_ATTR *)
0x1400609ce  nop     dword ptr [rax+rax+00h]
0x1400609d3  mov     rax, [rsp+170h+var_110]
0x1400609d8  and     dword ptr [rax+2Ch], 0FFFFFFFDh
0x1400609dc  mov     rcx, [rsp+170h+var_110]
0x1400609e1  mov     [rsp+170h+var_108], r15d
0x1400609e6  lock dec word ptr [rcx+0Ch]
0x1400609eb  mov     [rsp+170h+var_110], r15
0x1400609f0  lea     rcx, [rbp+70h+var_F0]
0x1400609f4  call    cs:__imp_PopThreadGuardedObject
0x1400609fb  nop     dword ptr [rax+rax+00h]
0x140060a00  mov     eax, r14d
0x140060a03  add     rsp, 140h
0x140060a0a  pop     r15
0x140060a0c  pop     r14
0x140060a0e  pop     r12
0x140060a10  pop     rdi
0x140060a11  pop     rsi
0x140060a12  pop     rbx
0x140060a13  pop     rbp
0x140060a14  retn
0x140060a16  mov     ecx, 6; iError
0x140060a1b  call    cs:__imp_EngSetLastError
0x140060a22  nop     dword ptr [rax+rax+00h]
0x140060a27  lea     rcx, [rbp+70h+var_A8]; this
0x140060a2b  call    ??1OPTAPIDCOBJ@@QEAA@XZ; OPTAPIDCOBJ::~OPTAPIDCOBJ(void)
0x140060a30  lea     rcx, [rsp+170h+var_110]; this
0x140060a35  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x140060a3a  xor     eax, eax
0x140060a3c  jmp     short loc_140060A03
0x140060a3e  call    ?vMarkTransformDirty@DC@@QEAAXXZ; DC::vMarkTransformDirty(void)
0x140060a43  jmp     loc_140060724
0x140060a48  call    cs:__imp_?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ; GrepGetCurrentProcessBehaviorRestriction(void)
0x140060a4f  nop     dword ptr [rax+rax+00h]
0x140060a54  cmp     eax, r12d
0x140060a57  jz      loc_1400606E0
0x140060a5d  mov     ecx, r12d
0x140060a60  call    cs:__imp_?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z; GrepAuditBehaviorRestrictionViolations(GreBehaviorRestriction)
0x140060a67  nop     dword ptr [rax+rax+00h]
0x140060a6c  jmp     loc_1400606E0
0x140060a71  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140060a76  jmp     loc_140060767
0x140060a7b  lock dec word ptr [rax+0Ch]
0x140060a80  mov     [rsp+170h+var_110], r15
0x140060a85  jmp     loc_1400606E0
0x140060a8a  lock dec word ptr [rax+0Ch]
0x140060a8f  mov     [rsp+170h+var_110], r15
0x140060a94  jmp     loc_140060724
0x140060a99  lea     rcx, [rsp+170h+var_110]; this
0x140060a9e  call    ?vUnlock@DCOBJ@@QEAAXXZ; DCOBJ::vUnlock(void)
0x140060aa3  jmp     loc_14006077A
0x140060aa8  xorps   xmm0, xmm0
0x140060aab  lea     rsi, [rdi+868h]
0x140060ab2  movups  xmmword ptr [rsi], xmm0
0x140060ab5  xor     eax, eax
0x140060ab7  xor     ecx, ecx
0x140060ab9  mov     [rsi+10h], rax
0x140060abd  mov     dword ptr [rdi+870h], 80000012h
0x140060ac7  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x140060ace  nop     dword ptr [rax+rax+00h]
0x140060ad3  mov     [rdi+878h], rax
0x140060ada  jmp     loc_1400608D2
0x140060adf  xorps   xmm0, xmm0
0x140060ae2  lea     rsi, [rbx+868h]
0x140060ae9  movups  xmmword ptr [rsi], xmm0
0x140060aec  xor     eax, eax
0x140060aee  xor     ecx, ecx
0x140060af0  mov     [rsi+10h], rax
0x140060af4  mov     dword ptr [rbx+870h], 80000012h
0x140060afe  call    cs:__imp_?GreEncodeUserModePointer@@YAPEAXPEAX@Z; GreEncodeUserModePointer(void *)
0x140060b05  nop     dword ptr [rax+rax+00h]
0x140060b0a  mov     [rbx+878h], rax
0x140060b11  jmp     loc_14006099F
```
