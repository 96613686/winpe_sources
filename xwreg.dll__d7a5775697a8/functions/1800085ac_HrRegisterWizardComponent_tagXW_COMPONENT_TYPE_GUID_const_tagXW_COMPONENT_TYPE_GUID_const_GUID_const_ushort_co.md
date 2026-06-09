# HrRegisterWizardComponent(tagXW_COMPONENT_TYPE,_GUID const *,tagXW_COMPONENT_TYPE,_GUID const *,_GUID const *,ushort * const,ushort * const,ulong,ulong,ushort * const,ulong,void * const)

- ea: `0x1800085ac`
- end: `0x180008b44`
- name: `?HrRegisterWizardComponent@@YAJW4tagXW_COMPONENT_TYPE@@PEBU_GUID@@011QEAG2KK2KQEAX@Z`
- size: `1432`
- prototype: `__int64 __fastcall(unsigned int, const GUID *, unsigned int, const GUID *, GUID *rguid, __int64, __int64, int, int, __int64, DWORD dwProcessId, void *)`
- caller_count: `4`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006ca0`
- `0x180006ea0`
- `0x180006fe0`
- `0x180007240`

## callees

- `0x1800011dc`
- `0x180007820`
- `0x180007860`
- `0x180007a00`
- `0x180007a34`
- `0x180007a84`
- `0x180007b28`
- `0x1800085ac`
- `0x180008b4c`
- `0x1800095a0`
- `0x180009994`
- `0x18000abbc`
- `0x180010ff4`
- `0x180011710`
- `0x180011820`
- `0x180011a10`
- `0x18001250c`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180008806`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180008822`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800088d4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180008806`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180008822`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800088d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008aa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008aa1`

## pseudocode

```c
__int64 __fastcall HrRegisterWizardComponent(
        unsigned int a1,
        const GUID *a2,
        unsigned int a3,
        const GUID *a4,
        GUID *rguid,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9,
        __int64 a10,
        DWORD dwProcessId,
        void *a12)
{
  const GUID *v12; // rdi
  const GUID *v13; // r12
  const GUID *v14; // r15
  CPXWizardSemaphoreLock *v15; // rsi
  CPXWizardSemaphoreLock *v16; // rax
  unsigned __int16 *v17; // rdx
  int v18; // r9d
  int v19; // ebx
  PVOID *v20; // rcx
  CPXWizardSemaphoreLock *v21; // rax
  unsigned __int16 *v22; // rdx
  int v23; // r8d
  int v24; // r9d
  CPXWizardSemaphoreLock *v25; // r14
  __int64 v26; // rdx
  __int64 v27; // r9
  int v28; // r9d
  int v29; // eax
  unsigned __int64 v30; // r8
  HANDLE v31; // r15
  unsigned int v32; // r12d
  int v33; // eax
  int v34; // eax
  unsigned int v35; // edx
  unsigned int v36; // edx
  __int64 v38; // [rsp+0h] [rbp-208h] BYREF
  unsigned int v39; // [rsp+40h] [rbp-1C8h]
  unsigned int v40; // [rsp+48h] [rbp-1C0h]
  HANDLE hObject; // [rsp+50h] [rbp-1B8h] BYREF
  unsigned int v42; // [rsp+58h] [rbp-1B0h]
  CPXWizardSemaphoreLock *v43; // [rsp+60h] [rbp-1A8h]
  CPXWizardSemaphoreLock *v44; // [rsp+68h] [rbp-1A0h]
  const GUID *v45; // [rsp+70h] [rbp-198h]
  const GUID *v46; // [rsp+78h] [rbp-190h]
  GUID *v47; // [rsp+80h] [rbp-188h]
  HANDLE hSourceHandle; // [rsp+88h] [rbp-180h]
  __int64 v49; // [rsp+90h] [rbp-178h]
  __int64 v50; // [rsp+98h] [rbp-170h]
  __int64 v51; // [rsp+A0h] [rbp-168h]
  CPXWizardSemaphoreLock *v52; // [rsp+A8h] [rbp-160h]
  _BYTE v53[32]; // [rsp+B0h] [rbp-158h] BYREF
  OLECHAR sz[40]; // [rsp+D0h] [rbp-138h] BYREF
  OLECHAR v55[40]; // [rsp+120h] [rbp-E8h] BYREF
  OLECHAR v56[40]; // [rsp+170h] [rbp-98h] BYREF

  v12 = a4;
  v13 = a2;
  v39 = a1;
  v40 = a1;
  v45 = a2;
  v42 = a3;
  v46 = a4;
  v14 = rguid;
  v47 = rguid;
  v50 = a6;
  v49 = a7;
  v51 = a10;
  hSourceHandle = a12;
  v15 = 0;
  v43 = 0;
  v44 = 0;
  hObject = 0;
  if ( !a4 )
    goto LABEL_76;
  try
  {
    v16 = (CPXWizardSemaphoreLock *)operator new(0x28u);
    v52 = v16;
    if ( v16 )
      v15 = CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(v16, v17, v12, v18);
    else
      v15 = 0;
    v43 = v15;
  }
  catch ( ... )
  {
    v15 = v43;
    v39 = v40;
    v13 = v45;
    v12 = v46;
    v14 = v47;
  }
  if ( v15 )
  {
LABEL_76:
    try
    {
      v21 = (CPXWizardSemaphoreLock *)operator new(0x28u);
      v52 = v21;
      if ( v21 )
        v25 = CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(v21, v22, v13, v24);
      else
        v25 = 0;
      v44 = v25;
    }
    catch ( ... )
    {
      v22 = (unsigned __int16 *)&v38;
      v15 = v43;
      v25 = v44;
      v39 = v40;
      v13 = v45;
      v12 = v46;
      v14 = v47;
    }
    if ( !v25 )
    {
      v19 = -2147024882;
      v20 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_56;
      v26 = 80;
      v27 = 2147942414LL;
      goto LABEL_19;
    }
    if ( v15 && (int)CPXWizardSemaphoreLock::Lock(v15, (unsigned int)v22, v23) >= 0 )
    {
      CPXWizardSemaphoreLock::Lock(v25, (unsigned int)v22, v23);
    }
    else
    {
      v34 = CPXWizardSemaphoreLock::Lock(v25, (unsigned int)v22, v23);
      v19 = v34;
      if ( v34 < 0 )
      {
        v20 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_56;
        v26 = 81;
        v27 = (unsigned int)v34;
LABEL_19:
        WPP_SF_D(v20[2], v26, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, v27);
LABEL_55:
        v20 = (PVOID *)WPP_GLOBAL_Control;
LABEL_56:
        if ( v15 )
        {
          if ( (unsigned int)CPXWizardSemaphoreLock::IsLocked(v15, (int)v22) )
            CPXWizardSemaphoreLock::Unlock(v15, v35);
          CPXWizardSemaphoreLock::`scalar deleting destructor'(v15, v35);
          v20 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( !v25 )
          goto LABEL_65;
        if ( (unsigned int)CPXWizardSemaphoreLock::IsLocked(v25, (int)v22) )
          CPXWizardSemaphoreLock::Unlock(v25, v36);
        CPXWizardSemaphoreLock::`scalar deleting destructor'(v25, v36);
        goto LABEL_64;
      }
    }
    v19 = HrDuplicateHandle(hSourceHandle, dwProcessId, &hObject, v28);
    if ( v19 < 0 )
    {
      v31 = hObject;
LABEL_53:
      if ( v31 )
        CloseHandle(v31);
      goto LABEL_55;
    }
    memset_0(sz, 0, sizeof(sz));
    memset_0(v55, 0, sizeof(v55));
    StringFromGUID2(v13, sz, 40);
    if ( v14 )
      StringFromGUID2(v14, v55, 40);
    CPXWizardRegistryLockedTransaction<1>::CPXWizardRegistryLockedTransaction<1>(v53);
    v29 = CPXWizardRegistryLockedTransaction<3>::HrBackup(v53);
    v19 = v29;
    if ( v29 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
          (unsigned int)sz,
          v29);
      v31 = hObject;
      goto LABEL_51;
    }
    v30 = (unsigned __int64)v55 & -(__int64)(v14 != 0);
    v31 = hObject;
    v32 = v39;
    v33 = HrRegisterCoreWizardComponent(v39, sz, v30, v50, v49, a8, hObject);
    v19 = v33;
    if ( v33 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
          (unsigned int)sz,
          v33);
      goto LABEL_42;
    }
    if ( v12 )
    {
      memset_0(v56, 0, sizeof(v56));
      StringFromGUID2(v12, v56, 40);
      v19 = HrRegisterWizardComponentLink(v32, sz, v42, v56, a9, v51, v31);
    }
    else
    {
      v19 = 0;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_46;
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        82,
        (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
        (unsigned int)sz,
        0);
    }
    if ( v19 < 0 )
    {
LABEL_42:
      if ( (int)CPXWizardRegistryLockedTransaction<3>::HrRestore(v53) < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          84,
          (unsigned int)&WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
          (unsigned int)sz,
          5);
      }
    }
LABEL_46:
    CPXWizardRegistryLockedTransaction<3>::HrRelease(v53);
LABEL_51:
    CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(v53);
    goto LABEL_53;
  }
  v19 = -2147024882;
  v20 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v19;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, 2147942414LL);
LABEL_64:
    v20 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_65:
  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 0x10) != 0 )
    WPP_SF_D(v20[2], 86, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, (unsigned int)v19);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800085ac  push    rbx
0x1800085ae  push    rsi
0x1800085af  push    rdi
0x1800085b0  push    r12
0x1800085b2  push    r14
0x1800085b4  push    r15
0x1800085b6  sub     rsp, 1D8h
0x1800085bd  mov     rax, cs:__security_cookie
0x1800085c4  xor     rax, rsp
0x1800085c7  mov     [rsp+208h+var_48], rax
0x1800085cf  mov     rdi, r9
0x1800085d2  mov     r12, rdx
0x1800085d5  mov     [rsp+208h+var_1C8], ecx
0x1800085d9  mov     [rsp+208h+var_1C0], ecx
0x1800085dd  mov     [rsp+208h+var_198], rdx
0x1800085e2  mov     [rsp+208h+var_1B0], r8d
0x1800085e7  mov     [rsp+208h+var_190], r9
0x1800085ec  mov     r15, [rsp+208h+rguid]
0x1800085f4  mov     [rsp+208h+var_188], r15
0x1800085fc  mov     rax, [rsp+208h+arg_28]
0x180008604  mov     [rsp+208h+var_170], rax
0x18000860c  mov     rax, [rsp+208h+arg_30]
0x180008614  mov     [rsp+208h+var_178], rax
0x18000861c  mov     rax, [rsp+208h+arg_48]
0x180008624  mov     [rsp+208h+var_168], rax
0x18000862c  mov     rax, [rsp+208h+arg_58]
0x180008634  mov     [rsp+208h+hSourceHandle], rax
0x18000863c  xor     esi, esi
0x18000863e  mov     [rsp+208h+var_1A8], rsi
0x180008643  mov     [rsp+208h+var_1A0], rsi
0x180008648  mov     [rsp+208h+hObject], rsi
0x18000864d  test    r9, r9
0x180008650  jz      loc_1800086EC
0x180008656  lea     ecx, [rsi+28h]; Size
0x180008659  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000865e  mov     [rsp+208h+var_160], rax
0x180008666  test    rax, rax
0x180008669  jz      short loc_18000867B
0x18000866b  mov     r8, rdi; struct _GUID *
0x18000866e  mov     rcx, rax; this
0x180008671  call    ??0CPXWizardSemaphoreLock@@QEAA@QEAGPEBU_GUID@@H@Z; CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(ushort * const,_GUID const *,int)
0x180008676  mov     rsi, rax
0x180008679  jmp     short loc_18000867D
0x18000867b  xor     esi, esi
0x18000867d  mov     [rsp+208h+var_1A8], rsi
0x180008682  jmp     short loc_1800086A3
0x180008684  mov     rsi, [rsp+208h+var_1A8]
0x180008689  mov     eax, [rsp+208h+var_1C0]
0x18000868d  mov     [rsp+208h+var_1C8], eax
0x180008691  mov     r12, [rsp+208h+var_198]
0x180008696  mov     rdi, [rsp+208h+var_190]
0x18000869b  mov     r15, [rsp+208h+var_188]
0x1800086a3  test    rsi, rsi
0x1800086a6  jnz     short loc_1800086EC
0x1800086a8  mov     ebx, 8007000Eh
0x1800086ad  lea     rdi, WPP_GLOBAL_Control
0x1800086b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086bb  cmp     rcx, rdi
0x1800086be  jz      loc_180008B21
0x1800086c4  test    byte ptr [rcx+1Ch], 4
0x1800086c8  jz      loc_180008AFE
0x1800086ce  lea     edx, [rsi+4Fh]
0x1800086d1  mov     r9d, 8007000Eh
0x1800086d7  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x1800086de  mov     rcx, [rcx+10h]
0x1800086e2  call    WPP_SF_D
0x1800086e7  jmp     loc_180008AF7
0x1800086ec  mov     ecx, 28h ; '('; Size
0x1800086f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800086f6  mov     [rsp+208h+var_160], rax
0x1800086fe  test    rax, rax
0x180008701  jz      short loc_180008713
0x180008703  mov     r8, r12; struct _GUID *
0x180008706  mov     rcx, rax; this
0x180008709  call    ??0CPXWizardSemaphoreLock@@QEAA@QEAGPEBU_GUID@@H@Z; CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(ushort * const,_GUID const *,int)
0x18000870e  mov     r14, rax
0x180008711  jmp     short loc_180008716
0x180008713  xor     r14d, r14d
0x180008716  mov     [rsp+208h+var_1A0], r14
0x18000871b  jmp     short loc_180008741
0x18000871d  mov     rsi, [rsp+208h+var_1A8]
0x180008722  mov     r14, [rsp+208h+var_1A0]
0x180008727  mov     eax, [rsp+208h+var_1C0]
0x18000872b  mov     [rsp+208h+var_1C8], eax
0x18000872f  mov     r12, [rsp+208h+var_198]
0x180008734  mov     rdi, [rsp+208h+var_190]
0x180008739  mov     r15, [rsp+208h+var_188]
0x180008741  test    r14, r14
0x180008744  jnz     short loc_18000878B
0x180008746  mov     ebx, 8007000Eh
0x18000874b  lea     rdi, WPP_GLOBAL_Control
0x180008752  mov     rcx, cs:WPP_GLOBAL_Control
0x180008759  cmp     rcx, rdi
0x18000875c  jz      loc_180008AAE
0x180008762  test    byte ptr [rcx+1Ch], 4
0x180008766  jz      loc_180008AAE
0x18000876c  lea     edx, [r14+50h]
0x180008770  mov     r9d, 8007000Eh
0x180008776  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x18000877d  mov     rcx, [rcx+10h]
0x180008781  call    WPP_SF_D
0x180008786  jmp     loc_180008AA7
0x18000878b  test    rsi, rsi
0x18000878e  jz      loc_180008922
0x180008794  mov     rcx, rsi; this
0x180008797  call    ?Lock@CPXWizardSemaphoreLock@@QEAAJKH@Z; CPXWizardSemaphoreLock::Lock(ulong,int)
0x18000879c  test    eax, eax
0x18000879e  js      loc_180008922
0x1800087a4  mov     rcx, r14; this
0x1800087a7  call    ?Lock@CPXWizardSemaphoreLock@@QEAAJKH@Z; CPXWizardSemaphoreLock::Lock(ulong,int)
0x1800087ac  lea     r8, [rsp+208h+hObject]; void **
0x1800087b1  mov     edx, [rsp+208h+dwProcessId]; dwProcessId
0x1800087b8  mov     rcx, [rsp+208h+hSourceHandle]; hSourceHandle
0x1800087c0  call    ?HrDuplicateHandle@@YAJPEAXKPEAPEAXH@Z; HrDuplicateHandle(void *,ulong,void * *,int)
0x1800087c5  mov     ebx, eax
0x1800087c7  test    eax, eax
0x1800087c9  js      loc_180008A8D
0x1800087cf  xor     edx, edx; Val
0x1800087d1  lea     r8d, [rdx+50h]; Size
0x1800087d5  lea     rcx, [rsp+208h+sz]; void *
0x1800087dd  call    memset_0
0x1800087e2  xor     edx, edx; Val
0x1800087e4  lea     r8d, [rdx+50h]; Size
0x1800087e8  lea     rcx, [rsp+208h+var_E8]; void *
0x1800087f0  call    memset_0
0x1800087f5  mov     r8d, 28h ; '('; cchMax
0x1800087fb  lea     rdx, [rsp+208h+sz]; lpsz
0x180008803  mov     rcx, r12; rguid
0x180008806  call    cs:__imp_StringFromGUID2
0x18000880c  test    r15, r15
0x18000880f  jz      short loc_180008828
0x180008811  mov     r8d, 28h ; '('; cchMax
0x180008817  lea     rdx, [rsp+208h+var_E8]; lpsz
0x18000881f  mov     rcx, r15; rguid
0x180008822  call    cs:__imp_StringFromGUID2
0x180008828  lea     rcx, [rsp+208h+var_158]
0x180008830  call    ??0?$CPXWizardRegistryLockedTransaction@$00@@QEAA@XZ; CPXWizardRegistryLockedTransaction<1>::CPXWizardRegistryLockedTransaction<1>(void)
0x180008835  nop
0x180008836  lea     rcx, [rsp+208h+var_158]
0x18000883e  call    ?HrBackup@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJK@Z; CPXWizardRegistryLockedTransaction<3>::HrBackup(ulong)
0x180008843  mov     ebx, eax
0x180008845  test    eax, eax
0x180008847  js      loc_180008A3F
0x18000884d  neg     r15
0x180008850  sbb     r8, r8
0x180008853  lea     rax, [rsp+208h+var_E8]
0x18000885b  and     r8, rax
0x18000885e  mov     r15, [rsp+208h+hObject]
0x180008863  mov     [rsp+208h+var_1D8], r15
0x180008868  mov     eax, [rsp+208h+arg_38]
0x18000886f  mov     dword ptr [rsp+208h+var_1E0], eax
0x180008873  mov     rax, [rsp+208h+var_178]
0x18000887b  mov     [rsp+208h+var_1E8], rax
0x180008880  mov     r9, [rsp+208h+var_170]
0x180008888  lea     rdx, [rsp+208h+sz]
0x180008890  mov     r12d, [rsp+208h+var_1C8]
0x180008895  mov     ecx, r12d
0x180008898  call    ?HrRegisterCoreWizardComponent@@YAJW4tagXW_COMPONENT_TYPE@@QEAG111KQEAX@Z; HrRegisterCoreWizardComponent(tagXW_COMPONENT_TYPE,ushort * const,ushort * const,ushort * const,ushort * const,ulong,void * const)
0x18000889d  mov     ebx, eax
0x18000889f  test    eax, eax
0x1800088a1  js      loc_1800089AE
0x1800088a7  test    rdi, rdi
0x1800088aa  jz      loc_180008962
0x1800088b0  xor     edx, edx; Val
0x1800088b2  lea     r8d, [rdx+50h]; Size
0x1800088b6  lea     rcx, [rsp+208h+var_98]; void *
0x1800088be  call    memset_0
0x1800088c3  mov     r8d, 28h ; '('; cchMax
0x1800088c9  lea     rdx, [rsp+208h+var_98]; lpsz
0x1800088d1  mov     rcx, rdi; rguid
0x1800088d4  call    cs:__imp_StringFromGUID2
0x1800088da  mov     [rsp+208h+var_1D8], r15
0x1800088df  mov     rax, [rsp+208h+var_168]
0x1800088e7  mov     [rsp+208h+var_1E0], rax
0x1800088ec  mov     eax, [rsp+208h+arg_40]
0x1800088f3  mov     dword ptr [rsp+208h+var_1E8], eax
0x1800088f7  lea     r9, [rsp+208h+var_98]
0x1800088ff  mov     r8d, [rsp+208h+var_1B0]
0x180008904  lea     rdx, [rsp+208h+sz]
0x18000890c  mov     ecx, r12d
0x18000890f  call    ?HrRegisterWizardComponentLink@@YAJW4tagXW_COMPONENT_TYPE@@QEAG01K1QEAX@Z; HrRegisterWizardComponentLink(tagXW_COMPONENT_TYPE,ushort * const,tagXW_COMPONENT_TYPE,ushort * const,ulong,ushort * const,void * const)
0x180008914  mov     ebx, eax
0x180008916  lea     rdi, WPP_GLOBAL_Control
0x18000891d  jmp     loc_1800089A4
0x180008922  mov     rcx, r14; this
0x180008925  call    ?Lock@CPXWizardSemaphoreLock@@QEAAJKH@Z; CPXWizardSemaphoreLock::Lock(ulong,int)
0x18000892a  mov     ebx, eax
0x18000892c  test    eax, eax
0x18000892e  jns     loc_1800087AC
0x180008934  lea     rdi, WPP_GLOBAL_Control
0x18000893b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008942  cmp     rcx, rdi
0x180008945  jz      loc_180008AAE
0x18000894b  test    byte ptr [rcx+1Ch], 10h
0x18000894f  jz      loc_180008AAE
0x180008955  mov     edx, 51h ; 'Q'
0x18000895a  mov     r9d, eax
0x18000895d  jmp     loc_180008776
0x180008962  xor     ebx, ebx
0x180008964  lea     rdi, WPP_GLOBAL_Control
0x18000896b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008972  cmp     rcx, rdi
0x180008975  jz      loc_180008A30
0x18000897b  test    byte ptr [rcx+1Ch], 10h
0x18000897f  jz      loc_180008A30
0x180008985  lea     edx, [rbx+52h]
0x180008988  mov     dword ptr [rsp+208h+var_1E8], ebx
0x18000898c  lea     r9, [rsp+208h+sz]
0x180008994  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x18000899b  mov     rcx, [rcx+10h]
0x18000899f  call    WPP_SF_SD
0x1800089a4  test    ebx, ebx
0x1800089a6  jns     loc_180008A30
0x1800089ac  jmp     short loc_1800089E8
0x1800089ae  lea     rdi, WPP_GLOBAL_Control
0x1800089b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089bc  cmp     rcx, rdi
0x1800089bf  jz      short loc_1800089E8
0x1800089c1  test    byte ptr [rcx+1Ch], 10h
0x1800089c5  jz      short loc_1800089E8
0x1800089c7  mov     edx, 53h ; 'S'
0x1800089cc  mov     dword ptr [rsp+208h+var_1E8], eax
0x1800089d0  lea     r9, [rsp+208h+sz]
0x1800089d8  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x1800089df  mov     rcx, [rcx+10h]
0x1800089e3  call    WPP_SF_SD
0x1800089e8  lea     rcx, [rsp+208h+var_158]
0x1800089f0  call    ?HrRestore@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ; CPXWizardRegistryLockedTransaction<3>::HrRestore(void)
0x1800089f5  test    eax, eax
0x1800089f7  jns     short loc_180008A30
0x1800089f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a00  cmp     rcx, rdi
0x180008a03  jz      short loc_180008A30
0x180008a05  test    byte ptr [rcx+1Ch], 4
0x180008a09  jz      short loc_180008A30
0x180008a0b  mov     edx, 54h ; 'T'
0x180008a10  mov     dword ptr [rsp+208h+var_1E8], 80004005h
0x180008a18  lea     r9, [rsp+208h+sz]
0x180008a20  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180008a27  mov     rcx, [rcx+10h]
0x180008a2b  call    WPP_SF_SD
0x180008a30  lea     rcx, [rsp+208h+var_158]
0x180008a38  call    ?HrRelease@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ; CPXWizardRegistryLockedTransaction<3>::HrRelease(void)
0x180008a3d  jmp     short loc_180008A7E
0x180008a3f  lea     rdi, WPP_GLOBAL_Control
0x180008a46  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a4d  cmp     rcx, rdi
0x180008a50  jz      short loc_180008A79
0x180008a52  test    byte ptr [rcx+1Ch], 4
0x180008a56  jz      short loc_180008A79
0x180008a58  mov     edx, 55h ; 'U'
0x180008a5d  mov     dword ptr [rsp+208h+var_1E8], eax
0x180008a61  lea     r9, [rsp+208h+sz]
0x180008a69  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180008a70  mov     rcx, [rcx+10h]
0x180008a74  call    WPP_SF_SD
0x180008a79  mov     r15, [rsp+208h+hObject]
0x180008a7e  lea     rcx, [rsp+208h+var_158]
0x180008a86  call    ??1?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ; CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(void)
0x180008a8b  jmp     short loc_180008A99
0x180008a8d  lea     rdi, WPP_GLOBAL_Control
0x180008a94  mov     r15, [rsp+208h+hObject]
0x180008a99  test    r15, r15
0x180008a9c  jz      short loc_180008AA7
0x180008a9e  mov     rcx, r15; hObject
0x180008aa1  call    cs:__imp_CloseHandle
0x180008aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180008aae  test    rsi, rsi
0x180008ab1  jz      short loc_180008AD6
0x180008ab3  mov     rcx, rsi; this
0x180008ab6  call    ?IsLocked@CPXWizardSemaphoreLock@@QEAAHH@Z; CPXWizardSemaphoreLock::IsLocked(int)
0x180008abb  test    eax, eax
0x180008abd  jz      short loc_180008AC7
0x180008abf  mov     rcx, rsi; this
0x180008ac2  call    ?Unlock@CPXWizardSemaphoreLock@@QEAAJH@Z; CPXWizardSemaphoreLock::Unlock(int)
0x180008ac7  mov     rcx, rsi; this
0x180008aca  call    ??_GCPXWizardSemaphoreLock@@QEAAPEAXI@Z; CPXWizardSemaphoreLock::`scalar deleting destructor'(uint)
0x180008acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ad6  test    r14, r14
0x180008ad9  jz      short loc_180008AFE
0x180008adb  mov     rcx, r14; this
0x180008ade  call    ?IsLocked@CPXWizardSemaphoreLock@@QEAAHH@Z; CPXWizardSemaphoreLock::IsLocked(int)
0x180008ae3  test    eax, eax
0x180008ae5  jz      short loc_180008AEF
0x180008ae7  mov     rcx, r14; this
0x180008aea  call    ?Unlock@CPXWizardSemaphoreLock@@QEAAJH@Z; CPXWizardSemaphoreLock::Unlock(int)
0x180008aef  mov     rcx, r14; this
0x180008af2  call    ??_GCPXWizardSemaphoreLock@@QEAAPEAXI@Z; CPXWizardSemaphoreLock::`scalar deleting destructor'(uint)
0x180008af7  mov     rcx, cs:WPP_GLOBAL_Control
0x180008afe  cmp     rcx, rdi
0x180008b01  jz      short loc_180008B21
0x180008b03  test    byte ptr [rcx+1Ch], 10h
0x180008b07  jz      short loc_180008B21
0x180008b09  mov     edx, 56h ; 'V'
0x180008b0e  mov     r9d, ebx
0x180008b11  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180008b18  mov     rcx, [rcx+10h]
0x180008b1c  call    WPP_SF_D
0x180008b21  mov     eax, ebx
0x180008b23  mov     rcx, [rsp+208h+var_48]
  ... truncated ...
```
