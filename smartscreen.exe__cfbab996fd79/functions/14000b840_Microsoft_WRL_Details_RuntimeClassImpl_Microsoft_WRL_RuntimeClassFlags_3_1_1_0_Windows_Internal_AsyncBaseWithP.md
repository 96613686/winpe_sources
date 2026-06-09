# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000b840`
- end: `0x14000bb99`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `857`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003fde0`
- `0x14003fdf0`
- `0x14003fe10`
- `0x14003fe30`
- `0x14003fe50`
- `0x14003fe70`
- `0x14003fe90`

## callees

- `0x14000b840`
- `0x14006a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(
        __int64 a1,
        int *a2,
        _QWORD *a3)
{
  int v4; // eax
  __int64 v5; // rcx
  int v6; // ebx
  int v7; // eax
  int v8; // ecx
  bool v10; // zf

  *a3 = 0;
  v4 = *a2;
  if ( !*a2 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_4;
    }
    v10 = a2[3] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
    goto LABEL_20;
  }
  if ( v4 == -1350114592 )
  {
    if ( a2[1] != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
      || a2[2] != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
    {
      goto LABEL_4;
    }
    v10 = a2[3] == *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4];
LABEL_20:
    if ( v10 )
    {
      *a3 = a1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      return 0;
    }
    goto LABEL_4;
  }
  if ( v4 == 54
    && a2[1] == *(_DWORD *)&GUID_00000036_0000_0000_c000_000000000046.Data2
    && a2[2] == *(_DWORD *)GUID_00000036_0000_0000_c000_000000000046.Data4
    && a2[3] == *(_DWORD *)&GUID_00000036_0000_0000_c000_000000000046.Data4[4] )
  {
    *a3 = a1;
    v7 = 0;
    goto LABEL_29;
  }
LABEL_4:
  v5 = a1 + 80;
  v6 = -2147467262;
  if ( v4 == -1796592748 )
  {
    if ( a2[1] == *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
      && a2[2] == *(_DWORD *)GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
      && a2[3] == *(_DWORD *)&GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4[4] )
    {
      *a3 = v5;
      v7 = 0;
      goto LABEL_7;
    }
LABEL_6:
    v7 = -2147467262;
    goto LABEL_7;
  }
  if ( v4 != 3
    || a2[1] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data2
    || a2[2] != *(_DWORD *)GUID_00000003_0000_0000_c000_000000000046.Data4
    || a2[3] != *(_DWORD *)&GUID_00000003_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_6;
  }
  *a3 = v5;
  v7 = 0;
LABEL_7:
  if ( v7 == -2147467262 )
  {
    v8 = *a2;
    if ( *a2 == 56
      && a2[1] == *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data2
      && a2[2] == *(_DWORD *)GUID_00000038_0000_0000_c000_000000000046.Data4
      && a2[3] == *(_DWORD *)&GUID_00000038_0000_0000_c000_000000000046.Data4[4] )
    {
      *a3 = a1 + 168;
      v6 = 0;
    }
    else if ( v8 == -129291111
           && a2[1] == *(_DWORD *)&GUID_f84b2c99_2f3d_5877_bf78_4f40f6bd25c0.Data2
           && a2[2] == *(_DWORD *)GUID_f84b2c99_2f3d_5877_bf78_4f40f6bd25c0.Data4
           && a2[3] == *(_DWORD *)&GUID_f84b2c99_2f3d_5877_bf78_4f40f6bd25c0.Data4[4] )
    {
      *a3 = a1 + 176;
      v6 = 0;
    }
    else if ( v8 == 2056260344
           && a2[1] == *(_DWORD *)&GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data2
           && a2[2] == *(_DWORD *)GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4
           && a2[3] == *(_DWORD *)&GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4[4] )
    {
      *a3 = a1 + 184;
      v6 = 0;
    }
    else if ( v8 == 1605706821
           && a2[1] == *(_DWORD *)&GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data2
           && a2[2] == *(_DWORD *)GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4
           && a2[3] == *(_DWORD *)&GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4[4] )
    {
      *a3 = a1 + 192;
      v6 = 0;
    }
    else if ( v8 == 1204800526 )
    {
      if ( a2[1] == *(_DWORD *)&GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data2
        && a2[2] == *(_DWORD *)GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4
        && a2[3] == *(_DWORD *)&GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4[4] )
      {
        *a3 = a1 + 200;
        v6 = 0;
      }
    }
    else if ( v8 == 428297526
           && a2[1] == *(_DWORD *)&GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data2
           && a2[2] == *(_DWORD *)GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4
           && a2[3] == *(_DWORD *)&GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4[4] )
    {
      *a3 = a1 + 208;
      v6 = 0;
    }
    goto LABEL_14;
  }
LABEL_29:
  v6 = v7;
LABEL_14:
  if ( v6 >= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000b840  push    rbx
0x14000b842  sub     rsp, 20h
0x14000b846  mov     r10, rdx
0x14000b849  mov     r11, rcx
0x14000b84c  mov     qword ptr [r8], 0
0x14000b853  mov     eax, [rdx]
0x14000b855  test    eax, eax
0x14000b857  jz      loc_14000B916
0x14000b85d  cmp     eax, 0AF86E2E0h
0x14000b862  jz      loc_14000B962
0x14000b868  cmp     eax, 36h ; '6'
0x14000b86b  jz      loc_14000B98B
0x14000b871  lea     rcx, [r11+50h]
0x14000b875  mov     ebx, 80004002h
0x14000b87a  cmp     eax, 94EA2B94h
0x14000b87f  jz      loc_14000B9C4
0x14000b885  cmp     eax, 3
0x14000b888  jz      loc_14000BB5E
0x14000b88e  mov     eax, ebx
0x14000b890  cmp     eax, ebx
0x14000b892  jnz     loc_14000B9BD
0x14000b898  lea     rdx, [r11+0A8h]
0x14000b89f  mov     ecx, [r10]
0x14000b8a2  cmp     ecx, 38h ; '8'
0x14000b8a5  jz      loc_14000B9FE
0x14000b8ab  add     rdx, 8
0x14000b8af  cmp     ecx, 0F84B2C99h
0x14000b8b5  jz      loc_14000BA38
0x14000b8bb  add     rdx, 8
0x14000b8bf  cmp     ecx, 7A900AF8h
0x14000b8c5  jz      loc_14000BA72
0x14000b8cb  add     rdx, 8
0x14000b8cf  cmp     ecx, 5FB52445h
0x14000b8d5  jz      loc_14000BAAC
0x14000b8db  add     rdx, 8
0x14000b8df  mov     eax, ecx
0x14000b8e1  cmp     ecx, 47CFCC0Eh
0x14000b8e7  jz      loc_14000BAE6
0x14000b8ed  cmp     eax, 19874D36h
0x14000b8f2  jz      loc_14000BB20
0x14000b8f8  test    ebx, ebx
0x14000b8fa  jns     short loc_14000B905
0x14000b8fc  mov     eax, ebx
0x14000b8fe  add     rsp, 20h
0x14000b902  pop     rbx
0x14000b903  retn
0x14000b905  mov     rcx, [r8]
0x14000b908  mov     rdx, [rcx]
0x14000b90b  mov     rax, [rdx+8]
0x14000b90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b914  jmp     short loc_14000B8FC
0x14000b916  mov     r9d, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x14000b91d  cmp     [rdx+4], r9d
0x14000b921  jnz     loc_14000B871
0x14000b927  mov     edx, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14000b92d  cmp     [r10+8], edx
0x14000b931  jnz     loc_14000B871
0x14000b937  mov     ecx, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14000b93d  cmp     [r10+0Ch], ecx
0x14000b941  jnz     loc_14000B871
0x14000b947  mov     [r8], r11
0x14000b94a  mov     rax, [r11]
0x14000b94d  mov     rcx, r11
0x14000b950  mov     rax, [rax+8]
0x14000b954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b959  xor     eax, eax
0x14000b95b  add     rsp, 20h
0x14000b95f  pop     rbx
0x14000b960  retn
0x14000b962  mov     ecx, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x14000b968  cmp     [rdx+4], ecx
0x14000b96b  jnz     loc_14000B871
0x14000b971  mov     ecx, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x14000b977  cmp     [rdx+8], ecx
0x14000b97a  jnz     loc_14000B871
0x14000b980  mov     ecx, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x14000b986  cmp     [rdx+0Ch], ecx
0x14000b989  jmp     short loc_14000B941
0x14000b98b  mov     ecx, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data2
0x14000b991  cmp     [rdx+4], ecx
0x14000b994  jnz     loc_14000B871
0x14000b99a  mov     ecx, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4
0x14000b9a0  cmp     [rdx+8], ecx
0x14000b9a3  jnz     loc_14000B871
0x14000b9a9  mov     ecx, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4+4
0x14000b9af  cmp     [rdx+0Ch], ecx
0x14000b9b2  jnz     loc_14000B871
0x14000b9b8  mov     [r8], r11
0x14000b9bb  xor     eax, eax
0x14000b9bd  mov     ebx, eax
0x14000b9bf  jmp     loc_14000B8F8
0x14000b9c4  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x14000b9ca  cmp     [r10+4], eax
0x14000b9ce  jnz     loc_14000B88E
0x14000b9d4  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x14000b9da  cmp     [r10+8], eax
0x14000b9de  jnz     loc_14000B88E
0x14000b9e4  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x14000b9ea  cmp     [r10+0Ch], eax
0x14000b9ee  jnz     loc_14000B88E
0x14000b9f4  mov     [r8], rcx
0x14000b9f7  xor     eax, eax
0x14000b9f9  jmp     loc_14000B890
0x14000b9fe  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x14000ba04  cmp     [r10+4], eax
0x14000ba08  jnz     loc_14000B8AB
0x14000ba0e  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x14000ba14  cmp     [r10+8], eax
0x14000ba18  jnz     loc_14000B8AB
0x14000ba1e  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x14000ba24  cmp     [r10+0Ch], eax
0x14000ba28  jnz     loc_14000B8AB
0x14000ba2e  mov     [r8], rdx
0x14000ba31  xor     ebx, ebx
0x14000ba33  jmp     loc_14000B8F8
0x14000ba38  mov     eax, dword ptr cs:_GUID_f84b2c99_2f3d_5877_bf78_4f40f6bd25c0.Data2
0x14000ba3e  cmp     [r10+4], eax
0x14000ba42  jnz     loc_14000B8BB
0x14000ba48  mov     eax, dword ptr cs:_GUID_f84b2c99_2f3d_5877_bf78_4f40f6bd25c0.Data4
0x14000ba4e  cmp     [r10+8], eax
0x14000ba52  jnz     loc_14000B8BB
0x14000ba58  mov     eax, dword ptr cs:_GUID_f84b2c99_2f3d_5877_bf78_4f40f6bd25c0.Data4+4
0x14000ba5e  cmp     [r10+0Ch], eax
0x14000ba62  jnz     loc_14000B8BB
0x14000ba68  mov     [r8], rdx
0x14000ba6b  xor     ebx, ebx
0x14000ba6d  jmp     loc_14000B8F8
0x14000ba72  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data2
0x14000ba78  cmp     [r10+4], eax
0x14000ba7c  jnz     loc_14000B8CB
0x14000ba82  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4
0x14000ba88  cmp     [r10+8], eax
0x14000ba8c  jnz     loc_14000B8CB
0x14000ba92  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4+4
0x14000ba98  cmp     [r10+0Ch], eax
0x14000ba9c  jnz     loc_14000B8CB
0x14000baa2  mov     [r8], rdx
0x14000baa5  xor     ebx, ebx
0x14000baa7  jmp     loc_14000B8F8
0x14000baac  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data2
0x14000bab2  cmp     [r10+4], eax
0x14000bab6  jnz     loc_14000B8DB
0x14000babc  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4
0x14000bac2  cmp     [r10+8], eax
0x14000bac6  jnz     loc_14000B8DB
0x14000bacc  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4+4
0x14000bad2  cmp     [r10+0Ch], eax
0x14000bad6  jnz     loc_14000B8DB
0x14000badc  mov     [r8], rdx
0x14000badf  xor     ebx, ebx
0x14000bae1  jmp     loc_14000B8F8
0x14000bae6  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data2
0x14000baec  cmp     [r10+4], eax
0x14000baf0  jnz     loc_14000B8F8
0x14000baf6  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4
0x14000bafc  cmp     [r10+8], eax
0x14000bb00  jnz     loc_14000B8F8
0x14000bb06  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4+4
0x14000bb0c  cmp     [r10+0Ch], eax
0x14000bb10  jnz     loc_14000B8F8
0x14000bb16  mov     [r8], rdx
0x14000bb19  xor     ebx, ebx
0x14000bb1b  jmp     loc_14000B8F8
0x14000bb20  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data2
0x14000bb26  cmp     [r10+4], eax
0x14000bb2a  jnz     loc_14000B8F8
0x14000bb30  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4
0x14000bb36  cmp     [r10+8], eax
0x14000bb3a  jnz     loc_14000B8F8
0x14000bb40  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4+4
0x14000bb46  cmp     [r10+0Ch], eax
0x14000bb4a  jnz     loc_14000B8F8
0x14000bb50  lea     rax, [rdx+8]
0x14000bb54  mov     [r8], rax
0x14000bb57  xor     ebx, ebx
0x14000bb59  jmp     loc_14000B8F8
0x14000bb5e  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x14000bb64  cmp     [r10+4], eax
0x14000bb68  jnz     loc_14000B88E
0x14000bb6e  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x14000bb74  cmp     [r10+8], eax
0x14000bb78  jnz     loc_14000B88E
0x14000bb7e  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x14000bb84  cmp     [r10+0Ch], eax
0x14000bb88  jnz     loc_14000B88E
0x14000bb8e  mov     [r8], rcx
0x14000bb91  xor     eax, eax
0x14000bb93  jmp     loc_14000B890
```
