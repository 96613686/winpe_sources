# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000f290`
- end: `0x14000f585`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `757`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003fd10`
- `0x14003fd20`
- `0x14003fd40`
- `0x14003fd60`
- `0x14003fd80`
- `0x14003fda0`
- `0x14003fdc0`

## callees

- `0x14000f290`
- `0x14006a010`

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
0x14000f290  push    rbx
0x14000f292  sub     rsp, 20h
0x14000f296  mov     qword ptr [r8], 0
0x14000f29d  cmp     dword ptr [rdx], 0
0x14000f2a0  jz      loc_14000F381
0x14000f2a6  cmp     dword ptr [rdx], 0AF86E2E0h
0x14000f2ac  jz      loc_14000F3FB
0x14000f2b2  cmp     dword ptr [rdx], 36h ; '6'
0x14000f2b5  jz      loc_14000F421
0x14000f2bb  lea     r9, [rcx+50h]
0x14000f2bf  mov     ebx, 80004002h
0x14000f2c4  cmp     dword ptr [rdx], 94EA2B94h
0x14000f2ca  jz      loc_14000F3C4
0x14000f2d0  cmp     dword ptr [rdx], 3
0x14000f2d3  jz      loc_14000F554
0x14000f2d9  mov     eax, ebx
0x14000f2db  cmp     eax, ebx
0x14000f2dd  jnz     loc_14000F57D
0x14000f2e3  add     rcx, 0A8h
0x14000f2ea  cmp     dword ptr [rdx], 38h ; '8'
0x14000f2ed  jz      loc_14000F453
0x14000f2f3  add     rcx, 8
0x14000f2f7  cmp     dword ptr [rdx], 0B2B6814Fh
0x14000f2fd  jz      loc_14000F485
0x14000f303  add     rcx, 8
0x14000f307  cmp     dword ptr [rdx], 7A900AF8h
0x14000f30d  jz      loc_14000F4B7
0x14000f313  add     rcx, 8
0x14000f317  cmp     dword ptr [rdx], 5FB52445h
0x14000f31d  jz      loc_14000F4E9
0x14000f323  add     rcx, 8
0x14000f327  cmp     dword ptr [rdx], 47CFCC0Eh
0x14000f32d  jz      short loc_14000F359
0x14000f32f  cmp     dword ptr [rdx], 19874D36h
0x14000f335  jz      loc_14000F51B
0x14000f33b  test    ebx, ebx
0x14000f33d  jns     short loc_14000F348
0x14000f33f  mov     eax, ebx
0x14000f341  add     rsp, 20h
0x14000f345  pop     rbx
0x14000f346  retn
0x14000f348  mov     rcx, [r8]
0x14000f34b  mov     rdx, [rcx]
0x14000f34e  mov     rax, [rdx+8]
0x14000f352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f357  jmp     short loc_14000F33F
0x14000f359  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data2
0x14000f35f  cmp     [rdx+4], eax
0x14000f362  jnz     short loc_14000F33B
0x14000f364  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4
0x14000f36a  cmp     [rdx+8], eax
0x14000f36d  jnz     short loc_14000F33B
0x14000f36f  mov     eax, dword ptr cs:_GUID_47cfcc0e_6012_43ca_81a9_ab7bc86ad5d4.Data4+4
0x14000f375  cmp     [rdx+0Ch], eax
0x14000f378  jnz     short loc_14000F33B
0x14000f37a  mov     [r8], rcx
0x14000f37d  xor     ebx, ebx
0x14000f37f  jmp     short loc_14000F33B
0x14000f381  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x14000f387  cmp     [rdx+4], eax
0x14000f38a  jnz     loc_14000F2BB
0x14000f390  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x14000f396  cmp     [rdx+8], eax
0x14000f399  jnz     loc_14000F2BB
0x14000f39f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x14000f3a5  cmp     [rdx+0Ch], eax
0x14000f3a8  jnz     loc_14000F2BB
0x14000f3ae  mov     [r8], rcx
0x14000f3b1  mov     rax, [rcx]
0x14000f3b4  mov     rax, [rax+8]
0x14000f3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f3bd  xor     ebx, ebx
0x14000f3bf  jmp     loc_14000F33F
0x14000f3c4  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data2
0x14000f3ca  cmp     [rdx+4], eax
0x14000f3cd  jnz     loc_14000F2D9
0x14000f3d3  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4
0x14000f3d9  cmp     [rdx+8], eax
0x14000f3dc  jnz     loc_14000F2D9
0x14000f3e2  mov     eax, dword ptr cs:_GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90.Data4+4
0x14000f3e8  cmp     [rdx+0Ch], eax
0x14000f3eb  jnz     loc_14000F2D9
0x14000f3f1  mov     [r8], r9
0x14000f3f4  xor     eax, eax
0x14000f3f6  jmp     loc_14000F2DB
0x14000f3fb  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x14000f401  cmp     [rdx+4], eax
0x14000f404  jnz     loc_14000F2BB
0x14000f40a  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x14000f410  cmp     [rdx+8], eax
0x14000f413  jnz     loc_14000F2BB
0x14000f419  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x14000f41f  jmp     short loc_14000F3A5
0x14000f421  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data2
0x14000f427  cmp     [rdx+4], eax
0x14000f42a  jnz     loc_14000F2BB
0x14000f430  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4
0x14000f436  cmp     [rdx+8], eax
0x14000f439  jnz     loc_14000F2BB
0x14000f43f  mov     eax, dword ptr cs:_GUID_00000036_0000_0000_c000_000000000046.Data4+4
0x14000f445  cmp     [rdx+0Ch], eax
0x14000f448  jz      loc_14000F37A
0x14000f44e  jmp     loc_14000F2BB
0x14000f453  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data2
0x14000f459  cmp     [rdx+4], eax
0x14000f45c  jnz     loc_14000F2F3
0x14000f462  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4
0x14000f468  cmp     [rdx+8], eax
0x14000f46b  jnz     loc_14000F2F3
0x14000f471  mov     eax, dword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data4+4
0x14000f477  cmp     [rdx+0Ch], eax
0x14000f47a  jnz     loc_14000F2F3
0x14000f480  jmp     loc_14000F37A
0x14000f485  mov     eax, dword ptr cs:_GUID_b2b6814f_02c2_5b0c_9e14_159eb77f4462.Data2
0x14000f48b  cmp     [rdx+4], eax
0x14000f48e  jnz     loc_14000F303
0x14000f494  mov     eax, dword ptr cs:_GUID_b2b6814f_02c2_5b0c_9e14_159eb77f4462.Data4
0x14000f49a  cmp     [rdx+8], eax
0x14000f49d  jnz     loc_14000F303
0x14000f4a3  mov     eax, dword ptr cs:_GUID_b2b6814f_02c2_5b0c_9e14_159eb77f4462.Data4+4
0x14000f4a9  cmp     [rdx+0Ch], eax
0x14000f4ac  jnz     loc_14000F303
0x14000f4b2  jmp     loc_14000F37A
0x14000f4b7  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data2
0x14000f4bd  cmp     [rdx+4], eax
0x14000f4c0  jnz     loc_14000F313
0x14000f4c6  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4
0x14000f4cc  cmp     [rdx+8], eax
0x14000f4cf  jnz     loc_14000F313
0x14000f4d5  mov     eax, dword ptr cs:_GUID_7a900af8_b975_45f7_8c93_3ae17df5c5d0.Data4+4
0x14000f4db  cmp     [rdx+0Ch], eax
0x14000f4de  jnz     loc_14000F313
0x14000f4e4  jmp     loc_14000F37A
0x14000f4e9  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data2
0x14000f4ef  cmp     [rdx+4], eax
0x14000f4f2  jnz     loc_14000F323
0x14000f4f8  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4
0x14000f4fe  cmp     [rdx+8], eax
0x14000f501  jnz     loc_14000F323
0x14000f507  mov     eax, dword ptr cs:_GUID_5fb52445_1407_4f25_9aa4_ac25bb3a9606.Data4+4
0x14000f50d  cmp     [rdx+0Ch], eax
0x14000f510  jz      loc_14000F37A
0x14000f516  jmp     loc_14000F323
0x14000f51b  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data2
0x14000f521  cmp     [rdx+4], eax
0x14000f524  jnz     loc_14000F33B
0x14000f52a  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4
0x14000f530  cmp     [rdx+8], eax
0x14000f533  jnz     loc_14000F33B
0x14000f539  mov     eax, dword ptr cs:_GUID_19874d36_ba31_46b7_986b_121aa1bbcd62.Data4+4
0x14000f53f  cmp     [rdx+0Ch], eax
0x14000f542  jnz     loc_14000F33B
0x14000f548  lea     rax, [rcx+8]
0x14000f54c  mov     [r8], rax
0x14000f54f  jmp     loc_14000F37D
0x14000f554  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data2
0x14000f55a  cmp     [rdx+4], eax
0x14000f55d  jnz     loc_14000F2D9
0x14000f563  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4
0x14000f569  cmp     [rdx+8], eax
0x14000f56c  jnz     loc_14000F2D9
0x14000f572  mov     eax, dword ptr cs:_GUID_00000003_0000_0000_c000_000000000046.Data4+4
0x14000f578  jmp     loc_14000F3E8
0x14000f57d  mov     ebx, eax
0x14000f57f  jmp     loc_14000F33B
```
