# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000e9d0`
- end: `0x14000ecc4`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `756`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003e5f0`
- `0x14003e600`
- `0x14003e620`
- `0x14003e640`
- `0x14003e660`
- `0x14003e680`
- `0x14003e6a0`

## callees

- `0x14000e9d0`
- `0x140068010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v3; // ebx
  int v4; // eax
  int v6; // eax
  int v7; // eax

  *a3 = 0;
  if ( !*a2 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_4;
    }
    v6 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
    goto LABEL_25;
  }
  if ( *a2 == -1350114592 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
      || a2[2] != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
    {
      goto LABEL_4;
    }
    v6 = *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4];
LABEL_25:
    if ( a2[3] == v6 )
    {
      *a3 = a1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      return 0;
    }
    goto LABEL_4;
  }
  if ( *a2 == 54
    && a2[1] == *(_DWORD *)&GUID_00000036_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000036_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000036_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_20;
  }
LABEL_4:
  v3 = -2147467262;
  if ( *a2 == -1796592748 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
      || a2[2] != *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4 )
    {
      goto LABEL_6;
    }
    v7 = *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4];
  }
  else
  {
    if ( *a2 != 3
      || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_6;
    }
    v7 = *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] != v7 )
  {
LABEL_6:
    v4 = -2147467262;
    goto LABEL_7;
  }
  *a3 = a1 + 80;
  v4 = 0;
LABEL_7:
  if ( v4 != -2147467262 )
  {
    v3 = v4;
    goto LABEL_14;
  }
  a1 += 168;
  if ( *a2 == 56
    && a2[1] == *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000038_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_20;
  }
  a1 += 8;
  if ( *a2 == -1296662193
    && a2[1] == *(_DWORD *)&GUID_b2b6814f_02c2_5b0c_9e14_159eb77f4462.Data2
    && a2[2] == *(_DWORD *)GUID_b2b6814f_02c2_5b0c_9e14_159eb77f4462.Data4
    && a2[3] == *(_DWORD *)&GUID_b2b6814f_02c2_5b0c_9e14_159eb77f4462.Data4[4] )
  {
    goto LABEL_20;
  }
  a1 += 8;
  if ( *a2 == 2056260344
    && a2[1] == *(_DWORD *)&GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data2
    && a2[2] == *(_DWORD *)GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4
    && a2[3] == *(_DWORD *)&GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4[4] )
  {
    goto LABEL_20;
  }
  a1 += 8;
  if ( *a2 == 1605706821
    && a2[1] == *(_DWORD *)&GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data2
    && a2[2] == *(_DWORD *)GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4
    && a2[3] == *(_DWORD *)&GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4[4] )
  {
    goto LABEL_20;
  }
  a1 += 8;
  if ( *a2 == 1204800526 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data2
      || a2[2] != *(_DWORD *)GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4
      || a2[3] != *(_DWORD *)&GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4[4] )
    {
      goto LABEL_14;
    }
LABEL_20:
    *a3 = a1;
LABEL_21:
    v3 = 0;
    goto LABEL_14;
  }
  if ( *a2 == 428297526
    && a2[1] == *(_DWORD *)&GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data2
    && a2[2] == *(_DWORD *)GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4
    && a2[3] == *(_DWORD *)&GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4[4] )
  {
    *a3 = a1 + 8;
    goto LABEL_21;
  }
LABEL_14:
  if ( v3 >= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000e9d0  push    rbx
0x14000e9d2  sub     rsp, 20h
0x14000e9d6  mov     qword ptr [r8], 0
0x14000e9dd  cmp     dword ptr [rdx], 0
0x14000e9e0  jz      loc_14000EAC0
0x14000e9e6  cmp     dword ptr [rdx], 0AF86E2E0h
0x14000e9ec  jz      loc_14000EB3A
0x14000e9f2  cmp     dword ptr [rdx], 36h ; '6'
0x14000e9f5  jz      loc_14000EB60
0x14000e9fb  lea     r9, [rcx+50h]
0x14000e9ff  mov     ebx, 80004002h
0x14000ea04  cmp     dword ptr [rdx], 94EA2B94h
0x14000ea0a  jz      loc_14000EB03
0x14000ea10  cmp     dword ptr [rdx], 3
0x14000ea13  jz      loc_14000EC93
0x14000ea19  mov     eax, ebx
0x14000ea1b  cmp     eax, ebx
0x14000ea1d  jnz     loc_14000ECBC
0x14000ea23  add     rcx, 0A8h
0x14000ea2a  cmp     dword ptr [rdx], 38h ; '8'
0x14000ea2d  jz      loc_14000EB92
0x14000ea33  add     rcx, 8
0x14000ea37  cmp     dword ptr [rdx], 0B2B6814Fh
0x14000ea3d  jz      loc_14000EBC4
0x14000ea43  add     rcx, 8
0x14000ea47  cmp     dword ptr [rdx], 7A900AF8h
0x14000ea4d  jz      loc_14000EBF6
0x14000ea53  add     rcx, 8
0x14000ea57  cmp     dword ptr [rdx], 5FB52445h
0x14000ea5d  jz      loc_14000EC28
0x14000ea63  add     rcx, 8
0x14000ea67  cmp     dword ptr [rdx], 47CFCC0Eh
0x14000ea6d  jz      short loc_14000EA98
0x14000ea6f  cmp     dword ptr [rdx], 19874D36h
0x14000ea75  jz      loc_14000EC5A
0x14000ea7b  test    ebx, ebx
0x14000ea7d  jns     short loc_14000EA87
0x14000ea7f  mov     eax, ebx
0x14000ea81  add     rsp, 20h
0x14000ea85  pop     rbx
0x14000ea86  retn
0x14000ea87  mov     rcx, [r8]
0x14000ea8a  mov     rdx, [rcx]
0x14000ea8d  mov     rax, [rdx+8]
0x14000ea91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ea96  jmp     short loc_14000EA7F
0x14000ea98  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data2
0x14000ea9e  cmp     [rdx+4], eax
0x14000eaa1  jnz     short loc_14000EA7B
0x14000eaa3  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4
0x14000eaa9  cmp     [rdx+8], eax
0x14000eaac  jnz     short loc_14000EA7B
0x14000eaae  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4+4
0x14000eab4  cmp     [rdx+0Ch], eax
0x14000eab7  jnz     short loc_14000EA7B
0x14000eab9  mov     [r8], rcx
0x14000eabc  xor     ebx, ebx
0x14000eabe  jmp     short loc_14000EA7B
0x14000eac0  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x14000eac6  cmp     [rdx+4], eax
0x14000eac9  jnz     loc_14000E9FB
0x14000eacf  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14000ead5  cmp     [rdx+8], eax
0x14000ead8  jnz     loc_14000E9FB
0x14000eade  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14000eae4  cmp     [rdx+0Ch], eax
0x14000eae7  jnz     loc_14000E9FB
0x14000eaed  mov     [r8], rcx
0x14000eaf0  mov     rax, [rcx]
0x14000eaf3  mov     rax, [rax+8]
0x14000eaf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eafc  xor     ebx, ebx
0x14000eafe  jmp     loc_14000EA7F
0x14000eb03  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x14000eb09  cmp     [rdx+4], eax
0x14000eb0c  jnz     loc_14000EA19
0x14000eb12  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x14000eb18  cmp     [rdx+8], eax
0x14000eb1b  jnz     loc_14000EA19
0x14000eb21  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x14000eb27  cmp     [rdx+0Ch], eax
0x14000eb2a  jnz     loc_14000EA19
0x14000eb30  mov     [r8], r9
0x14000eb33  xor     eax, eax
0x14000eb35  jmp     loc_14000EA1B
0x14000eb3a  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x14000eb40  cmp     [rdx+4], eax
0x14000eb43  jnz     loc_14000E9FB
0x14000eb49  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x14000eb4f  cmp     [rdx+8], eax
0x14000eb52  jnz     loc_14000E9FB
0x14000eb58  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x14000eb5e  jmp     short loc_14000EAE4
0x14000eb60  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data2
0x14000eb66  cmp     [rdx+4], eax
0x14000eb69  jnz     loc_14000E9FB
0x14000eb6f  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4
0x14000eb75  cmp     [rdx+8], eax
0x14000eb78  jnz     loc_14000E9FB
0x14000eb7e  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4+4
0x14000eb84  cmp     [rdx+0Ch], eax
0x14000eb87  jz      loc_14000EAB9
0x14000eb8d  jmp     loc_14000E9FB
0x14000eb92  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x14000eb98  cmp     [rdx+4], eax
0x14000eb9b  jnz     loc_14000EA33
0x14000eba1  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x14000eba7  cmp     [rdx+8], eax
0x14000ebaa  jnz     loc_14000EA33
0x14000ebb0  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x14000ebb6  cmp     [rdx+0Ch], eax
0x14000ebb9  jnz     loc_14000EA33
0x14000ebbf  jmp     loc_14000EAB9
0x14000ebc4  mov     eax, dword ptr cs:_GUID_b2b6814f_02c2_5b0c_9e14_159eb77f4462.Data2
0x14000ebca  cmp     [rdx+4], eax
0x14000ebcd  jnz     loc_14000EA43
0x14000ebd3  mov     eax, dword ptr cs:_GUID_b2b6814f_02c2_5b0c_9e14_159eb77f4462.Data4
0x14000ebd9  cmp     [rdx+8], eax
0x14000ebdc  jnz     loc_14000EA43
0x14000ebe2  mov     eax, dword ptr cs:_GUID_b2b6814f_02c2_5b0c_9e14_159eb77f4462.Data4+4
0x14000ebe8  cmp     [rdx+0Ch], eax
0x14000ebeb  jnz     loc_14000EA43
0x14000ebf1  jmp     loc_14000EAB9
0x14000ebf6  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data2
0x14000ebfc  cmp     [rdx+4], eax
0x14000ebff  jnz     loc_14000EA53
0x14000ec05  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4
0x14000ec0b  cmp     [rdx+8], eax
0x14000ec0e  jnz     loc_14000EA53
0x14000ec14  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4+4
0x14000ec1a  cmp     [rdx+0Ch], eax
0x14000ec1d  jnz     loc_14000EA53
0x14000ec23  jmp     loc_14000EAB9
0x14000ec28  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data2
0x14000ec2e  cmp     [rdx+4], eax
0x14000ec31  jnz     loc_14000EA63
0x14000ec37  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4
0x14000ec3d  cmp     [rdx+8], eax
0x14000ec40  jnz     loc_14000EA63
0x14000ec46  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4+4
0x14000ec4c  cmp     [rdx+0Ch], eax
0x14000ec4f  jz      loc_14000EAB9
0x14000ec55  jmp     loc_14000EA63
0x14000ec5a  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data2
0x14000ec60  cmp     [rdx+4], eax
0x14000ec63  jnz     loc_14000EA7B
0x14000ec69  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4
0x14000ec6f  cmp     [rdx+8], eax
0x14000ec72  jnz     loc_14000EA7B
0x14000ec78  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4+4
0x14000ec7e  cmp     [rdx+0Ch], eax
0x14000ec81  jnz     loc_14000EA7B
0x14000ec87  lea     rax, [rcx+8]
0x14000ec8b  mov     [r8], rax
0x14000ec8e  jmp     loc_14000EABC
0x14000ec93  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x14000ec99  cmp     [rdx+4], eax
0x14000ec9c  jnz     loc_14000EA19
0x14000eca2  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x14000eca8  cmp     [rdx+8], eax
0x14000ecab  jnz     loc_14000EA19
0x14000ecb1  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x14000ecb7  jmp     loc_14000EB27
0x14000ecbc  mov     ebx, eax
0x14000ecbe  jmp     loc_14000EA7B
```
