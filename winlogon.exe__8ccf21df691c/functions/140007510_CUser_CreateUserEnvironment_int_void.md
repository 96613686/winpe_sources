# CUser::CreateUserEnvironment(int,void * *)

- ea: `0x140007510`
- end: `0x140007962`
- name: `?CreateUserEnvironment@CUser@@QEAAKHPEAPEAX@Z`
- size: `1106`
- prototype: `unsigned int __fastcall(CUser *__hidden this, int, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140006fc0`

## callees

- `0x1400057f4`
- `0x140007510`
- `0x140007970`
- `0x140007e30`
- `0x140008700`
- `0x14000d4e0`
- `0x14003ec9c`
- `0x140053720`

## import_xrefs

- `ntdll!RtlCreateEnvironment` at `0x140007553`
- `ntdll!RtlCreateEnvironment` at `0x140007553`
- `ntdll!RtlDestroyEnvironment` at `0x140007932`
- `ntdll!RtlDestroyEnvironment` at `0x14009cf48`
- `ntdll!RtlDestroyEnvironment` at `0x140007932`
- `ntdll!RtlDestroyEnvironment` at `0x14009cf48`
- `ntdll!RtlNtStatusToDosError` at `0x14000756b`
- `ntdll!RtlNtStatusToDosError` at `0x14000756b`

## pseudocode

```c
__int64 __fastcall CUser::CreateUserEnvironment(CUser *this, int a2, PWSTR *a3)
{
  int v6; // eax
  ULONG updated; // eax
  ULONG v8; // edi
  CUser *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax
  ULONG v13; // eax
  ULONG v14; // eax
  ULONG v15; // eax
  ULONG v16; // eax
  ULONG v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  PWSTR Environment; // [rsp+38h] [rbp-250h] BYREF
  unsigned __int16 v23[264]; // [rsp+40h] [rbp-248h] BYREF

  Environment = 0;
  v6 = RtlCreateEnvironment(1u, &Environment);
  if ( v6 < 0 )
    updated = RtlNtStatusToDosError(v6);
  else
    updated = UpdateEnvironment((void **)&Environment);
  v8 = updated;
  if ( updated )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 40;
      v11 = updated;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v11);
    }
  }
  else
  {
    v12 = SetupBasicEnvironment((void **)&Environment);
    v8 = v12;
    if ( !v12 )
    {
      if ( !*((_DWORD *)this + 76) )
      {
        v13 = CUser::LoadUserEnvironmentFromRegistry((__int64)this, L"Environment", 0, &Environment);
        v8 = v13;
        if ( v13 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v10 = 42;
            v11 = v13;
            goto LABEL_9;
          }
          goto LABEL_60;
        }
        v14 = CUser::LoadUserEnvironmentFromRegistry((__int64)this, L"Volatile Environment", 0, &Environment);
        v8 = v14;
        if ( v14 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v10 = 43;
            v11 = v14;
            goto LABEL_9;
          }
          goto LABEL_60;
        }
        v15 = CUser::LoadUserEnvironmentFromRegistry((__int64)this, L"Environment", 1, &Environment);
        v8 = v15;
        if ( v15 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v10 = 44;
            v11 = v15;
            goto LABEL_9;
          }
          goto LABEL_60;
        }
        v16 = CUser::LoadUserEnvironmentFromRegistry((__int64)this, L"Volatile Environment", 0, &Environment);
        v8 = v16;
        if ( v16 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v10 = 45;
            v11 = v16;
            goto LABEL_9;
          }
          goto LABEL_60;
        }
        v17 = CUser::LoadUserEnvironmentFromRegistry((__int64)this, L"Volatile Environment", 1, &Environment);
        v8 = v17;
        if ( v17 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v10 = 46;
            v11 = v17;
            goto LABEL_9;
          }
          goto LABEL_60;
        }
        if ( (int)StringCchPrintfW(v23, 0x104u, L"%s\\%lu", L"Volatile Environment", NtCurrentPeb()->SessionId) >= 0 )
        {
          v18 = CUser::LoadUserEnvironmentFromRegistry((__int64)this, v23, 0, &Environment);
          if ( v18
            && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v18);
          }
          v19 = CUser::LoadUserEnvironmentFromRegistry((__int64)this, v23, 1, &Environment);
          if ( v19
            && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v19);
          }
        }
        v8 = 0;
      }
      if ( !a2 || (v20 = CUser::UpdateUserEnvironment(this, (void **)&Environment), (v8 = v20) == 0) )
      {
        *a3 = Environment;
        goto LABEL_60;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 49;
        v11 = v20;
        goto LABEL_9;
      }
      goto LABEL_60;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 41;
      v11 = v12;
      goto LABEL_9;
    }
  }
LABEL_60:
  if ( v8 && Environment )
    RtlDestroyEnvironment(Environment);
  return v8;
}

```

## disassembly

```asm
0x140007510  mov     [rsp+arg_8], rbx
0x140007515  push    rsi
0x140007516  push    rdi
0x140007517  push    r12
0x140007519  push    r14
0x14000751b  push    r15
0x14000751d  sub     rsp, 260h
0x140007524  mov     rax, cs:__security_cookie
0x14000752b  xor     rax, rsp
0x14000752e  mov     [rsp+288h+var_38], rax
0x140007536  mov     r14, r8
0x140007539  mov     r15d, edx
0x14000753c  mov     rbx, rcx
0x14000753f  xor     r12d, r12d
0x140007542  mov     [rsp+288h+var_258], r12d
0x140007547  mov     [rsp+288h+Environment], r12
0x14000754c  lea     rdx, [rsp+288h+Environment]; Environment
0x140007551  mov     cl, 1; Inherit
0x140007553  call    cs:__imp_RtlCreateEnvironment
0x140007559  test    eax, eax
0x14000755b  js      short loc_140007569
0x14000755d  lea     rcx, [rsp+288h+Environment]; void **
0x140007562  call    ?UpdateEnvironment@@YAKPEAPEAX@Z; UpdateEnvironment(void * *)
0x140007567  jmp     short loc_140007571
0x140007569  mov     ecx, eax; Status
0x14000756b  call    cs:__imp_RtlNtStatusToDosError
0x140007571  mov     edi, eax
0x140007573  mov     [rsp+288h+var_258], eax
0x140007577  test    eax, eax
0x140007579  jz      short loc_1400075C3
0x14000757b  lea     rsi, WPP_GLOBAL_Control
0x140007582  mov     rcx, cs:WPP_GLOBAL_Control
0x140007589  cmp     rcx, rsi
0x14000758c  jz      loc_140007924
0x140007592  test    byte ptr [rcx+1Ch], 20h
0x140007596  jz      loc_140007924
0x14000759c  cmp     byte ptr [rcx+19h], 2
0x1400075a0  jb      loc_140007924
0x1400075a6  mov     edx, 28h ; '('
0x1400075ab  mov     r9d, eax
0x1400075ae  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x1400075b5  mov     rcx, [rcx+10h]
0x1400075b9  call    WPP_SF_d
0x1400075be  jmp     loc_140007924
0x1400075c3  lea     rcx, [rsp+288h+Environment]; void **
0x1400075c8  call    ?SetupBasicEnvironment@@YAKPEAPEAX@Z; SetupBasicEnvironment(void * *)
0x1400075cd  mov     edi, eax
0x1400075cf  mov     [rsp+288h+var_258], eax
0x1400075d3  test    eax, eax
0x1400075d5  jz      short loc_14000760C
0x1400075d7  lea     rsi, WPP_GLOBAL_Control
0x1400075de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400075e5  cmp     rcx, rsi
0x1400075e8  jz      loc_140007924
0x1400075ee  test    byte ptr [rcx+1Ch], 20h
0x1400075f2  jz      loc_140007924
0x1400075f8  cmp     byte ptr [rcx+19h], 2
0x1400075fc  jb      loc_140007924
0x140007602  mov     edx, 29h ; ')'
0x140007607  mov     r9d, eax
0x14000760a  jmp     short loc_1400075AE
0x14000760c  cmp     dword ptr [rbx+130h], 0
0x140007613  jnz     loc_1400078D4
0x140007619  lea     r9, [rsp+288h+Environment]
0x14000761e  xor     r8d, r8d
0x140007621  lea     rdx, aEnvironment; "Environment"
0x140007628  mov     rcx, rbx
0x14000762b  call    ?LoadUserEnvironmentFromRegistry@CUser@@AEAAKPEBGW4_ENV_PASS@1@PEAPEAX@Z; CUser::LoadUserEnvironmentFromRegistry(ushort const *,CUser::_ENV_PASS,void * *)
0x140007630  mov     edi, eax
0x140007632  mov     [rsp+288h+var_258], eax
0x140007636  test    eax, eax
0x140007638  jz      short loc_140007672
0x14000763a  lea     rsi, WPP_GLOBAL_Control
0x140007641  mov     rcx, cs:WPP_GLOBAL_Control
0x140007648  cmp     rcx, rsi
0x14000764b  jz      loc_140007924
0x140007651  test    byte ptr [rcx+1Ch], 20h
0x140007655  jz      loc_140007924
0x14000765b  cmp     byte ptr [rcx+19h], 2
0x14000765f  jb      loc_140007924
0x140007665  mov     edx, 2Ah ; '*'
0x14000766a  mov     r9d, eax
0x14000766d  jmp     loc_1400075AE
0x140007672  lea     r9, [rsp+288h+Environment]
0x140007677  xor     r8d, r8d
0x14000767a  lea     rdx, aVolatileEnviro; "Volatile Environment"
0x140007681  mov     rcx, rbx
0x140007684  call    ?LoadUserEnvironmentFromRegistry@CUser@@AEAAKPEBGW4_ENV_PASS@1@PEAPEAX@Z; CUser::LoadUserEnvironmentFromRegistry(ushort const *,CUser::_ENV_PASS,void * *)
0x140007689  mov     edi, eax
0x14000768b  mov     [rsp+288h+var_258], eax
0x14000768f  test    eax, eax
0x140007691  jz      short loc_1400076CB
0x140007693  lea     rsi, WPP_GLOBAL_Control
0x14000769a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400076a1  cmp     rcx, rsi
0x1400076a4  jz      loc_140007924
0x1400076aa  test    byte ptr [rcx+1Ch], 20h
0x1400076ae  jz      loc_140007924
0x1400076b4  cmp     byte ptr [rcx+19h], 2
0x1400076b8  jb      loc_140007924
0x1400076be  mov     edx, 2Bh ; '+'
0x1400076c3  mov     r9d, eax
0x1400076c6  jmp     loc_1400075AE
0x1400076cb  lea     r9, [rsp+288h+Environment]
0x1400076d0  mov     r8d, 1
0x1400076d6  lea     rdx, aEnvironment; "Environment"
0x1400076dd  mov     rcx, rbx
0x1400076e0  call    ?LoadUserEnvironmentFromRegistry@CUser@@AEAAKPEBGW4_ENV_PASS@1@PEAPEAX@Z; CUser::LoadUserEnvironmentFromRegistry(ushort const *,CUser::_ENV_PASS,void * *)
0x1400076e5  mov     edi, eax
0x1400076e7  mov     [rsp+288h+var_258], eax
0x1400076eb  test    eax, eax
0x1400076ed  jz      short loc_140007727
0x1400076ef  lea     rsi, WPP_GLOBAL_Control
0x1400076f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400076fd  cmp     rcx, rsi
0x140007700  jz      loc_140007924
0x140007706  test    byte ptr [rcx+1Ch], 20h
0x14000770a  jz      loc_140007924
0x140007710  cmp     byte ptr [rcx+19h], 2
0x140007714  jb      loc_140007924
0x14000771a  mov     edx, 2Ch ; ','
0x14000771f  mov     r9d, eax
0x140007722  jmp     loc_1400075AE
0x140007727  lea     r9, [rsp+288h+Environment]
0x14000772c  xor     r8d, r8d
0x14000772f  lea     rdx, aVolatileEnviro; "Volatile Environment"
0x140007736  mov     rcx, rbx
0x140007739  call    ?LoadUserEnvironmentFromRegistry@CUser@@AEAAKPEBGW4_ENV_PASS@1@PEAPEAX@Z; CUser::LoadUserEnvironmentFromRegistry(ushort const *,CUser::_ENV_PASS,void * *)
0x14000773e  mov     edi, eax
0x140007740  mov     [rsp+288h+var_258], eax
0x140007744  test    eax, eax
0x140007746  jz      short loc_140007780
0x140007748  lea     rsi, WPP_GLOBAL_Control
0x14000774f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007756  cmp     rcx, rsi
0x140007759  jz      loc_140007924
0x14000775f  test    byte ptr [rcx+1Ch], 20h
0x140007763  jz      loc_140007924
0x140007769  cmp     byte ptr [rcx+19h], 2
0x14000776d  jb      loc_140007924
0x140007773  mov     edx, 2Dh ; '-'
0x140007778  mov     r9d, eax
0x14000777b  jmp     loc_1400075AE
0x140007780  lea     r9, [rsp+288h+Environment]
0x140007785  mov     r8d, 1
0x14000778b  lea     rdx, aVolatileEnviro; "Volatile Environment"
0x140007792  mov     rcx, rbx
0x140007795  call    ?LoadUserEnvironmentFromRegistry@CUser@@AEAAKPEBGW4_ENV_PASS@1@PEAPEAX@Z; CUser::LoadUserEnvironmentFromRegistry(ushort const *,CUser::_ENV_PASS,void * *)
0x14000779a  mov     edi, eax
0x14000779c  mov     [rsp+288h+var_258], eax
0x1400077a0  test    eax, eax
0x1400077a2  jz      short loc_1400077DC
0x1400077a4  lea     rsi, WPP_GLOBAL_Control
0x1400077ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400077b2  cmp     rcx, rsi
0x1400077b5  jz      loc_140007924
0x1400077bb  test    byte ptr [rcx+1Ch], 20h
0x1400077bf  jz      loc_140007924
0x1400077c5  cmp     byte ptr [rcx+19h], 2
0x1400077c9  jb      loc_140007924
0x1400077cf  mov     edx, 2Eh ; '.'
0x1400077d4  mov     r9d, eax
0x1400077d7  jmp     loc_1400075AE
0x1400077dc  mov     rax, gs:60h
0x1400077e5  mov     ecx, [rax+2C0h]
0x1400077eb  mov     [rsp+288h+var_268], ecx
0x1400077ef  lea     r9, aVolatileEnviro; "Volatile Environment"
0x1400077f6  lea     r8, aSLu; "%s\\%lu"
0x1400077fd  mov     edx, 104h; unsigned __int64
0x140007802  lea     rcx, [rsp+288h+var_248]; unsigned __int16 *
0x140007807  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000780c  test    eax, eax
0x14000780e  js      loc_1400078C3
0x140007814  lea     r9, [rsp+288h+Environment]
0x140007819  xor     r8d, r8d
0x14000781c  lea     rdx, [rsp+288h+var_248]
0x140007821  mov     rcx, rbx
0x140007824  call    ?LoadUserEnvironmentFromRegistry@CUser@@AEAAKPEBGW4_ENV_PASS@1@PEAPEAX@Z; CUser::LoadUserEnvironmentFromRegistry(ushort const *,CUser::_ENV_PASS,void * *)
0x140007829  mov     [rsp+288h+var_258], eax
0x14000782d  test    eax, eax
0x14000782f  jz      short loc_14000786A
0x140007831  lea     rsi, WPP_GLOBAL_Control
0x140007838  mov     rcx, cs:WPP_GLOBAL_Control
0x14000783f  cmp     rcx, rsi
0x140007842  jz      short loc_140007871
0x140007844  test    byte ptr [rcx+1Ch], 20h
0x140007848  jz      short loc_140007871
0x14000784a  cmp     byte ptr [rcx+19h], 2
0x14000784e  jb      short loc_140007871
0x140007850  mov     edx, 2Fh ; '/'
0x140007855  mov     r9d, eax
0x140007858  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x14000785f  mov     rcx, [rcx+10h]
0x140007863  call    WPP_SF_d
0x140007868  jmp     short loc_140007871
0x14000786a  lea     rsi, WPP_GLOBAL_Control
0x140007871  lea     r9, [rsp+288h+Environment]
0x140007876  mov     r8d, 1
0x14000787c  lea     rdx, [rsp+288h+var_248]
0x140007881  mov     rcx, rbx
0x140007884  call    ?LoadUserEnvironmentFromRegistry@CUser@@AEAAKPEBGW4_ENV_PASS@1@PEAPEAX@Z; CUser::LoadUserEnvironmentFromRegistry(ushort const *,CUser::_ENV_PASS,void * *)
0x140007889  mov     [rsp+288h+var_258], eax
0x14000788d  test    eax, eax
0x14000788f  jz      short loc_1400078CA
0x140007891  mov     rcx, cs:WPP_GLOBAL_Control
0x140007898  cmp     rcx, rsi
0x14000789b  jz      short loc_1400078CA
0x14000789d  test    byte ptr [rcx+1Ch], 20h
0x1400078a1  jz      short loc_1400078CA
0x1400078a3  cmp     byte ptr [rcx+19h], 2
0x1400078a7  jb      short loc_1400078CA
0x1400078a9  mov     edx, 30h ; '0'
0x1400078ae  mov     r9d, eax
0x1400078b1  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x1400078b8  mov     rcx, [rcx+10h]
0x1400078bc  call    WPP_SF_d
0x1400078c1  jmp     short loc_1400078CA
0x1400078c3  lea     rsi, WPP_GLOBAL_Control
0x1400078ca  mov     edi, r12d
0x1400078cd  mov     [rsp+288h+var_258], r12d
0x1400078d2  jmp     short loc_1400078DB
0x1400078d4  lea     rsi, WPP_GLOBAL_Control
0x1400078db  test    r15d, r15d
0x1400078de  jz      short loc_14000791C
0x1400078e0  lea     rdx, [rsp+288h+Environment]; void **
0x1400078e5  mov     rcx, rbx; this
0x1400078e8  call    ?UpdateUserEnvironment@CUser@@AEAAKPEAPEAX@Z; CUser::UpdateUserEnvironment(void * *)
0x1400078ed  mov     edi, eax
0x1400078ef  mov     [rsp+288h+var_258], eax
0x1400078f3  test    eax, eax
0x1400078f5  jz      short loc_14000791C
0x1400078f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400078fe  cmp     rcx, rsi
0x140007901  jz      short loc_140007924
0x140007903  test    byte ptr [rcx+1Ch], 20h
0x140007907  jz      short loc_140007924
0x140007909  cmp     byte ptr [rcx+19h], 2
0x14000790d  jb      short loc_140007924
0x14000790f  mov     edx, 31h ; '1'
0x140007914  mov     r9d, eax
0x140007917  jmp     loc_1400075AE
0x14000791c  mov     rax, [rsp+288h+Environment]
0x140007921  mov     [r14], rax
0x140007924  test    edi, edi
0x140007926  jz      short loc_140007938
0x140007928  mov     rcx, [rsp+288h+Environment]; Environment
0x14000792d  test    rcx, rcx
0x140007930  jz      short loc_140007938
0x140007932  call    cs:__imp_RtlDestroyEnvironment
0x140007938  mov     eax, edi
0x14000793a  mov     rcx, [rsp+288h+var_38]
0x140007942  xor     rcx, rsp; StackCookie
0x140007945  call    __security_check_cookie
0x14000794a  mov     rbx, [rsp+288h+arg_8]
0x140007952  add     rsp, 260h
0x140007959  pop     r15
0x14000795b  pop     r14
0x14000795d  pop     r12
0x14000795f  pop     rdi
0x140007960  pop     rsi
0x140007961  retn
0x14009cf30  push    rbp
0x14009cf32  sub     rsp, 30h
0x14009cf36  mov     rbp, rdx
0x14009cf39  cmp     dword ptr [rbp+30h], 0
0x14009cf3d  jz      short loc_14009CF4F
0x14009cf3f  mov     rcx, [rbp+38h]; Environment
0x14009cf43  test    rcx, rcx
0x14009cf46  jz      short loc_14009CF4F
0x14009cf48  call    cs:__imp_RtlDestroyEnvironment
0x14009cf4e  nop
0x14009cf4f  add     rsp, 30h
0x14009cf53  pop     rbp
0x14009cf54  retn
```
