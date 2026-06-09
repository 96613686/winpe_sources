# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000afe0`
- end: `0x14000b337`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `855`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003e6c0`
- `0x14003e6d0`
- `0x14003e6f0`
- `0x14003e710`
- `0x14003e730`
- `0x14003e750`
- `0x14003e770`

## callees

- `0x14000afe0`
- `0x140068010`

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
0x14000afe0  push    rbx
0x14000afe2  sub     rsp, 20h
0x14000afe6  mov     r10, rdx
0x14000afe9  mov     r11, rcx
0x14000afec  mov     qword ptr [r8], 0
0x14000aff3  mov     eax, [rdx]
0x14000aff5  test    eax, eax
0x14000aff7  jz      loc_14000B0B5
0x14000affd  cmp     eax, 0AF86E2E0h
0x14000b002  jz      loc_14000B100
0x14000b008  cmp     eax, 36h ; '6'
0x14000b00b  jz      loc_14000B129
0x14000b011  lea     rcx, [r11+50h]
0x14000b015  mov     ebx, 80004002h
0x14000b01a  cmp     eax, 94EA2B94h
0x14000b01f  jz      loc_14000B162
0x14000b025  cmp     eax, 3
0x14000b028  jz      loc_14000B2FC
0x14000b02e  mov     eax, ebx
0x14000b030  cmp     eax, ebx
0x14000b032  jnz     loc_14000B15B
0x14000b038  lea     rdx, [r11+0A8h]
0x14000b03f  mov     ecx, [r10]
0x14000b042  cmp     ecx, 38h ; '8'
0x14000b045  jz      loc_14000B19C
0x14000b04b  add     rdx, 8
0x14000b04f  cmp     ecx, 0F84B2C99h
0x14000b055  jz      loc_14000B1D6
0x14000b05b  add     rdx, 8
0x14000b05f  cmp     ecx, 7A900AF8h
0x14000b065  jz      loc_14000B210
0x14000b06b  add     rdx, 8
0x14000b06f  cmp     ecx, 5FB52445h
0x14000b075  jz      loc_14000B24A
0x14000b07b  add     rdx, 8
0x14000b07f  mov     eax, ecx
0x14000b081  cmp     ecx, 47CFCC0Eh
0x14000b087  jz      loc_14000B284
0x14000b08d  cmp     eax, 19874D36h
0x14000b092  jz      loc_14000B2BE
0x14000b098  test    ebx, ebx
0x14000b09a  jns     short loc_14000B0A4
0x14000b09c  mov     eax, ebx
0x14000b09e  add     rsp, 20h
0x14000b0a2  pop     rbx
0x14000b0a3  retn
0x14000b0a4  mov     rcx, [r8]
0x14000b0a7  mov     rdx, [rcx]
0x14000b0aa  mov     rax, [rdx+8]
0x14000b0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b0b3  jmp     short loc_14000B09C
0x14000b0b5  mov     r9d, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x14000b0bc  cmp     [rdx+4], r9d
0x14000b0c0  jnz     loc_14000B011
0x14000b0c6  mov     edx, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14000b0cc  cmp     [r10+8], edx
0x14000b0d0  jnz     loc_14000B011
0x14000b0d6  mov     ecx, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14000b0dc  cmp     [r10+0Ch], ecx
0x14000b0e0  jnz     loc_14000B011
0x14000b0e6  mov     [r8], r11
0x14000b0e9  mov     rax, [r11]
0x14000b0ec  mov     rcx, r11
0x14000b0ef  mov     rax, [rax+8]
0x14000b0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b0f8  xor     eax, eax
0x14000b0fa  add     rsp, 20h
0x14000b0fe  pop     rbx
0x14000b0ff  retn
0x14000b100  mov     ecx, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x14000b106  cmp     [rdx+4], ecx
0x14000b109  jnz     loc_14000B011
0x14000b10f  mov     ecx, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x14000b115  cmp     [rdx+8], ecx
0x14000b118  jnz     loc_14000B011
0x14000b11e  mov     ecx, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x14000b124  cmp     [rdx+0Ch], ecx
0x14000b127  jmp     short loc_14000B0E0
0x14000b129  mov     ecx, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data2
0x14000b12f  cmp     [rdx+4], ecx
0x14000b132  jnz     loc_14000B011
0x14000b138  mov     ecx, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4
0x14000b13e  cmp     [rdx+8], ecx
0x14000b141  jnz     loc_14000B011
0x14000b147  mov     ecx, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4+4
0x14000b14d  cmp     [rdx+0Ch], ecx
0x14000b150  jnz     loc_14000B011
0x14000b156  mov     [r8], r11
0x14000b159  xor     eax, eax
0x14000b15b  mov     ebx, eax
0x14000b15d  jmp     loc_14000B098
0x14000b162  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x14000b168  cmp     [r10+4], eax
0x14000b16c  jnz     loc_14000B02E
0x14000b172  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x14000b178  cmp     [r10+8], eax
0x14000b17c  jnz     loc_14000B02E
0x14000b182  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x14000b188  cmp     [r10+0Ch], eax
0x14000b18c  jnz     loc_14000B02E
0x14000b192  mov     [r8], rcx
0x14000b195  xor     eax, eax
0x14000b197  jmp     loc_14000B030
0x14000b19c  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x14000b1a2  cmp     [r10+4], eax
0x14000b1a6  jnz     loc_14000B04B
0x14000b1ac  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x14000b1b2  cmp     [r10+8], eax
0x14000b1b6  jnz     loc_14000B04B
0x14000b1bc  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x14000b1c2  cmp     [r10+0Ch], eax
0x14000b1c6  jnz     loc_14000B04B
0x14000b1cc  mov     [r8], rdx
0x14000b1cf  xor     ebx, ebx
0x14000b1d1  jmp     loc_14000B098
0x14000b1d6  mov     eax, dword ptr cs:_GUID_f84b2c99_2f3d_5877_bf78_4f40f6bd25c0.Data2
0x14000b1dc  cmp     [r10+4], eax
0x14000b1e0  jnz     loc_14000B05B
0x14000b1e6  mov     eax, dword ptr cs:_GUID_f84b2c99_2f3d_5877_bf78_4f40f6bd25c0.Data4
0x14000b1ec  cmp     [r10+8], eax
0x14000b1f0  jnz     loc_14000B05B
0x14000b1f6  mov     eax, dword ptr cs:_GUID_f84b2c99_2f3d_5877_bf78_4f40f6bd25c0.Data4+4
0x14000b1fc  cmp     [r10+0Ch], eax
0x14000b200  jnz     loc_14000B05B
0x14000b206  mov     [r8], rdx
0x14000b209  xor     ebx, ebx
0x14000b20b  jmp     loc_14000B098
0x14000b210  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data2
0x14000b216  cmp     [r10+4], eax
0x14000b21a  jnz     loc_14000B06B
0x14000b220  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4
0x14000b226  cmp     [r10+8], eax
0x14000b22a  jnz     loc_14000B06B
0x14000b230  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4+4
0x14000b236  cmp     [r10+0Ch], eax
0x14000b23a  jnz     loc_14000B06B
0x14000b240  mov     [r8], rdx
0x14000b243  xor     ebx, ebx
0x14000b245  jmp     loc_14000B098
0x14000b24a  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data2
0x14000b250  cmp     [r10+4], eax
0x14000b254  jnz     loc_14000B07B
0x14000b25a  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4
0x14000b260  cmp     [r10+8], eax
0x14000b264  jnz     loc_14000B07B
0x14000b26a  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4+4
0x14000b270  cmp     [r10+0Ch], eax
0x14000b274  jnz     loc_14000B07B
0x14000b27a  mov     [r8], rdx
0x14000b27d  xor     ebx, ebx
0x14000b27f  jmp     loc_14000B098
0x14000b284  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data2
0x14000b28a  cmp     [r10+4], eax
0x14000b28e  jnz     loc_14000B098
0x14000b294  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4
0x14000b29a  cmp     [r10+8], eax
0x14000b29e  jnz     loc_14000B098
0x14000b2a4  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4+4
0x14000b2aa  cmp     [r10+0Ch], eax
0x14000b2ae  jnz     loc_14000B098
0x14000b2b4  mov     [r8], rdx
0x14000b2b7  xor     ebx, ebx
0x14000b2b9  jmp     loc_14000B098
0x14000b2be  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data2
0x14000b2c4  cmp     [r10+4], eax
0x14000b2c8  jnz     loc_14000B098
0x14000b2ce  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4
0x14000b2d4  cmp     [r10+8], eax
0x14000b2d8  jnz     loc_14000B098
0x14000b2de  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4+4
0x14000b2e4  cmp     [r10+0Ch], eax
0x14000b2e8  jnz     loc_14000B098
0x14000b2ee  lea     rax, [rdx+8]
0x14000b2f2  mov     [r8], rax
0x14000b2f5  xor     ebx, ebx
0x14000b2f7  jmp     loc_14000B098
0x14000b2fc  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x14000b302  cmp     [r10+4], eax
0x14000b306  jnz     loc_14000B02E
0x14000b30c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x14000b312  cmp     [r10+8], eax
0x14000b316  jnz     loc_14000B02E
0x14000b31c  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x14000b322  cmp     [r10+0Ch], eax
0x14000b326  jnz     loc_14000B02E
0x14000b32c  mov     [r8], rcx
0x14000b32f  xor     eax, eax
0x14000b331  jmp     loc_14000B030
```
