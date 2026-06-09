# HrUnregisterWizardComponent(_GUID const *,_GUID const *,int)

- ea: `0x180009ca0`
- end: `0x18000a161`
- name: `?HrUnregisterWizardComponent@@YAJPEBU_GUID@@0H@Z`
- size: `1217`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, int)`
- caller_count: `4`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007470`
- `0x180007570`
- `0x180007610`
- `0x180007730`

## callees

- `0x1800011dc`
- `0x180007820`
- `0x180007860`
- `0x180007a00`
- `0x180007a34`
- `0x180007a84`
- `0x180007aa8`
- `0x1800095a0`
- `0x180009994`
- `0x1800099b4`
- `0x180009ca0`
- `0x18000a168`
- `0x18000a768`
- `0x18000aabc`
- `0x180010ff4`
- `0x180011710`
- `0x180011820`
- `0x180011a10`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HrUnregisterWizardComponent(struct _GUID *a1, struct _GUID *a2, int a3)
{
  struct _GUID *v3; // r15
  struct _GUID *v4; // r12
  int IsBaseOSComponent; // ebx
  PVOID *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // r8
  CPXWizardMutexLock **v10; // r14
  CPXWizardSemaphoreLock *v12; // rsi
  CPXWizardSemaphoreLock *v13; // rax
  unsigned __int16 *v14; // rdx
  unsigned __int16 *v15; // rdx
  CPXWizardSemaphoreLock *v16; // rax
  int v17; // r8d
  int v18; // eax
  int v19; // eax
  int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // edx
  unsigned int v24; // edx
  __int64 v25; // [rsp+0h] [rbp-98h] BYREF
  int v26; // [rsp+30h] [rbp-68h]
  CPXWizardMutexLock **v27; // [rsp+38h] [rbp-60h]
  CPXWizardSemaphoreLock *v28; // [rsp+40h] [rbp-58h]
  _BYTE v29[80]; // [rsp+48h] [rbp-50h] BYREF
  CPXWizardSemaphoreLock *v33; // [rsp+B8h] [rbp+20h] BYREF

  v3 = a2;
  v4 = a1;
  LODWORD(v33) = 0;
  IsBaseOSComponent = HrIsBaseOSComponent(a1, (int *)&v33);
  v26 = IsBaseOSComponent;
  if ( IsBaseOSComponent < 0 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return (unsigned int)IsBaseOSComponent;
    v7 = 87;
    goto LABEL_84;
  }
  if ( IsBaseOSComponent || !(_DWORD)v33 )
  {
    v12 = 0;
    v33 = 0;
    v10 = 0;
    v27 = 0;
    if ( !v3 )
      goto LABEL_91;
  }
  else
  {
    if ( !v3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          90,
          &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
          2147942405LL);
      return 2147942405LL;
    }
    IsBaseOSComponent = HrIsBaseOSComponent(v3, (int *)&v33);
    v26 = IsBaseOSComponent;
    if ( IsBaseOSComponent < 0 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        return (unsigned int)IsBaseOSComponent;
      v7 = 88;
      goto LABEL_84;
    }
    if ( !IsBaseOSComponent && (_DWORD)v33 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_LLD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, v3->Data1, v4->Data1);
      return 2147942405LL;
    }
    v33 = 0;
    v10 = 0;
    v27 = 0;
  }
  try
  {
    v13 = (CPXWizardSemaphoreLock *)operator new(0x28u);
    v28 = v13;
    if ( v13 )
      v12 = CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(v13, v14, v3);
    else
      v12 = 0;
    v33 = v12;
  }
  catch ( ... )
  {
    v3 = a2;
    v4 = a1;
    IsBaseOSComponent = v26;
    v12 = v33;
    v10 = v27;
  }
  if ( v12 )
  {
LABEL_91:
    try
    {
      v16 = (CPXWizardSemaphoreLock *)operator new(0x28u);
      v28 = v16;
      if ( v16 )
        v10 = (CPXWizardMutexLock **)CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(v16, v15, v4);
      else
        v10 = 0;
      v27 = v10;
    }
    catch ( ... )
    {
      v15 = (unsigned __int16 *)&v25;
      v3 = a2;
      v4 = a1;
      IsBaseOSComponent = v26;
      v12 = v33;
      v10 = v27;
    }
    if ( !v10 )
    {
      IsBaseOSComponent = -2147024882;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_72;
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, 2147942414LL);
      goto LABEL_71;
    }
    if ( v12 && (int)CPXWizardSemaphoreLock::Lock((CPXWizardMutexLock **)v12, (unsigned int)v15, v17) >= 0 )
    {
      CPXWizardSemaphoreLock::Lock(v10, (unsigned int)v15, v17);
    }
    else
    {
      v18 = CPXWizardSemaphoreLock::Lock(v10, (unsigned int)v15, v17);
      IsBaseOSComponent = v18;
      if ( v18 >= 0 )
        goto LABEL_49;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
LABEL_48:
        if ( IsBaseOSComponent < 0 )
        {
LABEL_72:
          if ( !v12 )
            goto LABEL_77;
          if ( (unsigned int)CPXWizardSemaphoreLock::IsLocked(v12, (int)v15) )
            CPXWizardSemaphoreLock::Unlock(v12, v23);
          CPXWizardSemaphoreLock::`scalar deleting destructor'(v12, v23);
LABEL_76:
          v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_77:
          if ( v10 )
          {
            if ( (unsigned int)CPXWizardSemaphoreLock::IsLocked((CPXWizardSemaphoreLock *)v10, (int)v15) )
              CPXWizardSemaphoreLock::Unlock((CPXWizardSemaphoreLock *)v10, v24);
            CPXWizardSemaphoreLock::`scalar deleting destructor'((CPXWizardSemaphoreLock *)v10, v24);
            v6 = (PVOID *)WPP_GLOBAL_Control;
          }
          goto LABEL_81;
        }
LABEL_49:
        CPXWizardRegistryLockedTransaction<1>::CPXWizardRegistryLockedTransaction<1>((__int64)v29);
        v19 = CPXWizardRegistryLockedTransaction<3>::HrBackup(v29);
        IsBaseOSComponent = v19;
        if ( v19 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              97,
              &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
              (unsigned int)v19);
          goto LABEL_70;
        }
        if ( v3 )
        {
          IsBaseOSComponent = HrUnregisterWizardComponentLink(v4, v3);
          if ( IsBaseOSComponent < 0 )
            goto LABEL_62;
LABEL_66:
          CPXWizardRegistryLockedTransaction<3>::HrRelease(v29);
LABEL_70:
          CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(v29);
LABEL_71:
          v6 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_72;
        }
        v20 = HrUnregisterWizardComponentLinks(v4);
        IsBaseOSComponent = v20;
        if ( v20 < 0 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v22 = 95;
            goto LABEL_61;
          }
        }
        else
        {
          v20 = HrUnregisterCoreWizardComponent(v4, a3);
          IsBaseOSComponent = v20;
          if ( v20 >= 0 )
            goto LABEL_66;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v22 = 94;
LABEL_61:
            WPP_SF_D(v21[2], v22, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, (unsigned int)v20);
          }
        }
LABEL_62:
        if ( (int)CPXWizardRegistryLockedTransaction<3>::HrRestore(v29) < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
            (unsigned int)IsBaseOSComponent);
        }
        goto LABEL_66;
      }
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
        (unsigned int)v18);
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  IsBaseOSComponent = -2147024882;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_81:
      if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 0x10) == 0 )
        return (unsigned int)IsBaseOSComponent;
      v7 = 98;
LABEL_84:
      WPP_SF_D(v6[2], v7, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, (unsigned int)IsBaseOSComponent);
      return (unsigned int)IsBaseOSComponent;
    }
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, 2147942414LL);
    goto LABEL_76;
  }
  return (unsigned int)IsBaseOSComponent;
}

```

## disassembly

```asm
0x180009ca0  mov     rax, rsp
0x180009ca3  mov     [rax+18h], r8d
0x180009ca7  mov     [rax+10h], rdx
0x180009cab  mov     [rax+8], rcx
0x180009caf  push    rbx
0x180009cb0  push    rsi
0x180009cb1  push    rdi
0x180009cb2  push    r12
0x180009cb4  push    r14
0x180009cb6  push    r15
0x180009cb8  sub     rsp, 68h
0x180009cbc  mov     r15, rdx
0x180009cbf  mov     r12, rcx
0x180009cc2  mov     dword ptr [rax+20h], 0
0x180009cc9  lea     rdx, [rax+20h]; int *
0x180009ccd  call    ?HrIsBaseOSComponent@@YAJPEBU_GUID@@PEAH@Z; HrIsBaseOSComponent(_GUID const *,int *)
0x180009cd2  mov     ebx, eax
0x180009cd4  mov     [rsp+98h+var_68], eax
0x180009cd8  test    eax, eax
0x180009cda  jns     short loc_180009D07
0x180009cdc  lea     rdi, WPP_GLOBAL_Control
0x180009ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cea  cmp     rcx, rdi
0x180009ced  jz      loc_18000A151
0x180009cf3  test    byte ptr [rcx+1Ch], 4
0x180009cf7  jz      loc_18000A151
0x180009cfd  mov     edx, 57h ; 'W'
0x180009d02  jmp     loc_18000A13E
0x180009d07  test    ebx, ebx
0x180009d09  jnz     loc_180009DFA
0x180009d0f  cmp     dword ptr [rsp+98h+arg_18], ebx
0x180009d16  jz      loc_180009DFA
0x180009d1c  test    r15, r15
0x180009d1f  jz      loc_180009DBC
0x180009d25  lea     rdx, [rsp+98h+arg_18]; int *
0x180009d2d  mov     rcx, r15; struct _GUID *
0x180009d30  call    ?HrIsBaseOSComponent@@YAJPEBU_GUID@@PEAH@Z; HrIsBaseOSComponent(_GUID const *,int *)
0x180009d35  mov     ebx, eax
0x180009d37  mov     [rsp+98h+var_68], eax
0x180009d3b  test    eax, eax
0x180009d3d  jns     short loc_180009D6A
0x180009d3f  lea     rdi, WPP_GLOBAL_Control
0x180009d46  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d4d  cmp     rcx, rdi
0x180009d50  jz      loc_18000A151
0x180009d56  test    byte ptr [rcx+1Ch], 4
0x180009d5a  jz      loc_18000A151
0x180009d60  mov     edx, 58h ; 'X'
0x180009d65  jmp     loc_18000A13E
0x180009d6a  test    ebx, ebx
0x180009d6c  jnz     short loc_180009DA6
0x180009d6e  cmp     dword ptr [rsp+98h+arg_18], ebx
0x180009d75  jz      short loc_180009DA6
0x180009d77  lea     rdi, WPP_GLOBAL_Control
0x180009d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d85  cmp     rcx, rdi
0x180009d88  jz      short loc_180009DF0
0x180009d8a  test    byte ptr [rcx+1Ch], 8
0x180009d8e  jz      short loc_180009DF0
0x180009d90  mov     eax, [r12]
0x180009d94  mov     [rsp+98h+var_78], eax
0x180009d98  mov     r9d, [r15]
0x180009d9b  mov     rcx, [rcx+10h]
0x180009d9f  call    WPP_SF_LLD
0x180009da4  jmp     short loc_180009DF0
0x180009da6  mov     [rsp+98h+arg_18], 0
0x180009db2  xor     r14d, r14d
0x180009db5  mov     [rsp+98h+var_60], r14
0x180009dba  jmp     short loc_180009E15
0x180009dbc  lea     rdi, WPP_GLOBAL_Control
0x180009dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dca  cmp     rcx, rdi
0x180009dcd  jz      short loc_180009DF0
0x180009dcf  test    byte ptr [rcx+1Ch], 10h
0x180009dd3  jz      short loc_180009DF0
0x180009dd5  mov     edx, 5Ah ; 'Z'
0x180009dda  mov     r9d, 80070005h
0x180009de0  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180009de7  mov     rcx, [rcx+10h]
0x180009deb  call    WPP_SF_D
0x180009df0  mov     eax, 80070005h
0x180009df5  jmp     loc_18000A153
0x180009dfa  xor     esi, esi
0x180009dfc  mov     [rsp+98h+arg_18], rsi
0x180009e04  xor     r14d, r14d
0x180009e07  mov     [rsp+98h+var_60], r14
0x180009e0c  test    r15, r15
0x180009e0f  jz      loc_180009EAF
0x180009e15  mov     ecx, 28h ; '('; Size
0x180009e1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009e1f  mov     [rsp+98h+var_58], rax
0x180009e24  test    rax, rax
0x180009e27  jz      short loc_180009E39
0x180009e29  mov     r8, r15; struct _GUID *
0x180009e2c  mov     rcx, rax; this
0x180009e2f  call    ??0CPXWizardSemaphoreLock@@QEAA@QEAGPEBU_GUID@@H@Z; CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(ushort * const,_GUID const *,int)
0x180009e34  mov     rsi, rax
0x180009e37  jmp     short loc_180009E3B
0x180009e39  xor     esi, esi
0x180009e3b  mov     [rsp+98h+arg_18], rsi
0x180009e43  jmp     short loc_180009E66
0x180009e45  mov     r15, [rsp+98h+arg_8]
0x180009e4d  mov     r12, [rsp+98h+arg_0]
0x180009e55  mov     ebx, [rsp+98h+var_68]
0x180009e59  mov     rsi, [rsp+98h+arg_18]
0x180009e61  mov     r14, [rsp+98h+var_60]
0x180009e66  test    rsi, rsi
0x180009e69  jnz     short loc_180009EAF
0x180009e6b  mov     ebx, 8007000Eh
0x180009e70  lea     rdi, WPP_GLOBAL_Control
0x180009e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e7e  cmp     rcx, rdi
0x180009e81  jz      loc_18000A151
0x180009e87  test    byte ptr [rcx+1Ch], 4
0x180009e8b  jz      loc_18000A12E
0x180009e91  lea     edx, [rsi+5Bh]
0x180009e94  mov     r9d, 8007000Eh
0x180009e9a  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180009ea1  mov     rcx, [rcx+10h]
0x180009ea5  call    WPP_SF_D
0x180009eaa  jmp     loc_18000A0FF
0x180009eaf  mov     ecx, 28h ; '('; Size
0x180009eb4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009eb9  mov     [rsp+98h+var_58], rax
0x180009ebe  test    rax, rax
0x180009ec1  jz      short loc_180009ED3
0x180009ec3  mov     r8, r12; struct _GUID *
0x180009ec6  mov     rcx, rax; this
0x180009ec9  call    ??0CPXWizardSemaphoreLock@@QEAA@QEAGPEBU_GUID@@H@Z; CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(ushort * const,_GUID const *,int)
0x180009ece  mov     r14, rax
0x180009ed1  jmp     short loc_180009ED6
0x180009ed3  xor     r14d, r14d
0x180009ed6  mov     [rsp+98h+var_60], r14
0x180009edb  jmp     short loc_180009EFE
0x180009edd  mov     r15, [rsp+98h+arg_8]
0x180009ee5  mov     r12, [rsp+98h+arg_0]
0x180009eed  mov     ebx, [rsp+98h+var_68]
0x180009ef1  mov     rsi, [rsp+98h+arg_18]
0x180009ef9  mov     r14, [rsp+98h+var_60]
0x180009efe  test    r14, r14
0x180009f01  jnz     short loc_180009F48
0x180009f03  mov     ebx, 8007000Eh
0x180009f08  lea     rdi, WPP_GLOBAL_Control
0x180009f0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f16  cmp     rcx, rdi
0x180009f19  jz      loc_18000A0DE
0x180009f1f  test    byte ptr [rcx+1Ch], 4
0x180009f23  jz      loc_18000A0DE
0x180009f29  lea     edx, [r14+5Ch]
0x180009f2d  mov     r9d, 8007000Eh
0x180009f33  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180009f3a  mov     rcx, [rcx+10h]
0x180009f3e  call    WPP_SF_D
0x180009f43  jmp     loc_18000A0D7
0x180009f48  test    rsi, rsi
0x180009f4b  jz      short loc_180009F6A
0x180009f4d  mov     rcx, rsi; this
0x180009f50  call    ?Lock@CPXWizardSemaphoreLock@@QEAAJKH@Z; CPXWizardSemaphoreLock::Lock(ulong,int)
0x180009f55  test    eax, eax
0x180009f57  js      short loc_180009F6A
0x180009f59  mov     rcx, r14; this
0x180009f5c  call    ?Lock@CPXWizardSemaphoreLock@@QEAAJKH@Z; CPXWizardSemaphoreLock::Lock(ulong,int)
0x180009f61  lea     rdi, WPP_GLOBAL_Control
0x180009f68  jmp     short loc_180009FA9
0x180009f6a  mov     rcx, r14; this
0x180009f6d  call    ?Lock@CPXWizardSemaphoreLock@@QEAAJKH@Z; CPXWizardSemaphoreLock::Lock(ulong,int)
0x180009f72  mov     ebx, eax
0x180009f74  test    eax, eax
0x180009f76  jns     short loc_180009FB9
0x180009f78  lea     rdi, WPP_GLOBAL_Control
0x180009f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f86  cmp     rcx, rdi
0x180009f89  jz      short loc_180009FB0
0x180009f8b  test    byte ptr [rcx+1Ch], 10h
0x180009f8f  jz      short loc_180009FB0
0x180009f91  mov     edx, 5Dh ; ']'
0x180009f96  mov     r9d, eax
0x180009f99  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180009fa0  mov     rcx, [rcx+10h]
0x180009fa4  call    WPP_SF_D
0x180009fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fb0  test    ebx, ebx
0x180009fb2  jns     short loc_180009FC0
0x180009fb4  jmp     loc_18000A0DE
0x180009fb9  lea     rdi, WPP_GLOBAL_Control
0x180009fc0  lea     rcx, [rsp+98h+var_50]
0x180009fc5  call    ??0?$CPXWizardRegistryLockedTransaction@$00@@QEAA@XZ; CPXWizardRegistryLockedTransaction<1>::CPXWizardRegistryLockedTransaction<1>(void)
0x180009fca  nop
0x180009fcb  lea     rcx, [rsp+98h+var_50]
0x180009fd0  call    ?HrBackup@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJK@Z; CPXWizardRegistryLockedTransaction<3>::HrBackup(ulong)
0x180009fd5  mov     ebx, eax
0x180009fd7  test    eax, eax
0x180009fd9  js      loc_18000A0A2
0x180009fdf  mov     rcx, r12; rguid
0x180009fe2  test    r15, r15
0x180009fe5  jz      short loc_180009FFB
0x180009fe7  mov     rdx, r15; GUID *
0x180009fea  call    ?HrUnregisterWizardComponentLink@@YAJPEBU_GUID@@0@Z; HrUnregisterWizardComponentLink(_GUID const *,_GUID const *)
0x180009fef  mov     ebx, eax
0x180009ff1  test    eax, eax
0x180009ff3  jns     loc_18000A096
0x180009ff9  jmp     short loc_18000A05E
0x180009ffb  call    ?HrUnregisterWizardComponentLinks@@YAJPEBU_GUID@@@Z; HrUnregisterWizardComponentLinks(_GUID const *)
0x18000a000  mov     ebx, eax
0x18000a002  test    eax, eax
0x18000a004  js      short loc_18000A034
0x18000a006  mov     edx, [rsp+98h+arg_10]; int
0x18000a00d  mov     rcx, r12; rguid
0x18000a010  call    ?HrUnregisterCoreWizardComponent@@YAJPEBU_GUID@@H@Z; HrUnregisterCoreWizardComponent(_GUID const *,int)
0x18000a015  mov     ebx, eax
0x18000a017  test    eax, eax
0x18000a019  jns     short loc_18000A096
0x18000a01b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a022  cmp     rcx, rdi
0x18000a025  jz      short loc_18000A05E
0x18000a027  test    byte ptr [rcx+1Ch], 4
0x18000a02b  jz      short loc_18000A05E
0x18000a02d  mov     edx, 5Eh ; '^'
0x18000a032  jmp     short loc_18000A04B
0x18000a034  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a03b  cmp     rcx, rdi
0x18000a03e  jz      short loc_18000A05E
0x18000a040  test    byte ptr [rcx+1Ch], 4
0x18000a044  jz      short loc_18000A05E
0x18000a046  mov     edx, 5Fh ; '_'
0x18000a04b  mov     r9d, eax
0x18000a04e  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x18000a055  mov     rcx, [rcx+10h]
0x18000a059  call    WPP_SF_D
0x18000a05e  lea     rcx, [rsp+98h+var_50]
0x18000a063  call    ?HrRestore@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ; CPXWizardRegistryLockedTransaction<3>::HrRestore(void)
0x18000a068  test    eax, eax
0x18000a06a  jns     short loc_18000A096
0x18000a06c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a073  cmp     rcx, rdi
0x18000a076  jz      short loc_18000A096
0x18000a078  test    byte ptr [rcx+1Ch], 4
0x18000a07c  jz      short loc_18000A096
0x18000a07e  mov     edx, 60h ; '`'
0x18000a083  mov     r9d, ebx
0x18000a086  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x18000a08d  mov     rcx, [rcx+10h]
0x18000a091  call    WPP_SF_D
0x18000a096  lea     rcx, [rsp+98h+var_50]
0x18000a09b  call    ?HrRelease@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ; CPXWizardRegistryLockedTransaction<3>::HrRelease(void)
0x18000a0a0  jmp     short loc_18000A0CD
0x18000a0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0a9  cmp     rcx, rdi
0x18000a0ac  jz      short loc_18000A0CD
0x18000a0ae  test    byte ptr [rcx+1Ch], 4
0x18000a0b2  jz      short loc_18000A0CD
0x18000a0b4  mov     edx, 61h ; 'a'
0x18000a0b9  mov     r9d, eax
0x18000a0bc  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x18000a0c3  mov     rcx, [rcx+10h]
0x18000a0c7  call    WPP_SF_D
0x18000a0cc  nop
0x18000a0cd  lea     rcx, [rsp+98h+var_50]
0x18000a0d2  call    ??1?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ; CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(void)
0x18000a0d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0de  test    rsi, rsi
0x18000a0e1  jz      short loc_18000A106
0x18000a0e3  mov     rcx, rsi; this
0x18000a0e6  call    ?IsLocked@CPXWizardSemaphoreLock@@QEAAHH@Z; CPXWizardSemaphoreLock::IsLocked(int)
0x18000a0eb  test    eax, eax
0x18000a0ed  jz      short loc_18000A0F7
0x18000a0ef  mov     rcx, rsi; this
0x18000a0f2  call    ?Unlock@CPXWizardSemaphoreLock@@QEAAJH@Z; CPXWizardSemaphoreLock::Unlock(int)
0x18000a0f7  mov     rcx, rsi; this
0x18000a0fa  call    ??_GCPXWizardSemaphoreLock@@QEAAPEAXI@Z; CPXWizardSemaphoreLock::`scalar deleting destructor'(uint)
0x18000a0ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a106  test    r14, r14
0x18000a109  jz      short loc_18000A12E
0x18000a10b  mov     rcx, r14; this
0x18000a10e  call    ?IsLocked@CPXWizardSemaphoreLock@@QEAAHH@Z; CPXWizardSemaphoreLock::IsLocked(int)
0x18000a113  test    eax, eax
0x18000a115  jz      short loc_18000A11F
0x18000a117  mov     rcx, r14; this
0x18000a11a  call    ?Unlock@CPXWizardSemaphoreLock@@QEAAJH@Z; CPXWizardSemaphoreLock::Unlock(int)
0x18000a11f  mov     rcx, r14; this
0x18000a122  call    ??_GCPXWizardSemaphoreLock@@QEAAPEAXI@Z; CPXWizardSemaphoreLock::`scalar deleting destructor'(uint)
0x18000a127  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a12e  cmp     rcx, rdi
0x18000a131  jz      short loc_18000A151
0x18000a133  test    byte ptr [rcx+1Ch], 10h
0x18000a137  jz      short loc_18000A151
0x18000a139  mov     edx, 62h ; 'b'
0x18000a13e  mov     r9d, ebx
0x18000a141  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x18000a148  mov     rcx, [rcx+10h]
0x18000a14c  call    WPP_SF_D
0x18000a151  mov     eax, ebx
0x18000a153  add     rsp, 68h
0x18000a157  pop     r15
0x18000a159  pop     r14
0x18000a15b  pop     r12
0x18000a15d  pop     rdi
0x18000a15e  pop     rsi
0x18000a15f  pop     rbx
0x18000a160  retn
  ... truncated ...
```
