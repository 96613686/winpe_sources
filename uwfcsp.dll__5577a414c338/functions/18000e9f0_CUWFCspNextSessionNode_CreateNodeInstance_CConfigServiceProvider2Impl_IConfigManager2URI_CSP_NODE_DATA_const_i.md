# CUWFCspNextSessionNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x18000e9f0`
- end: `0x18000ed24`
- name: `?CreateNodeInstance@CUWFCspNextSessionNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `820`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e610`

## callees

- `0x180007788`
- `0x180007b90`
- `0x180007fc4`
- `0x18000b4dc`
- `0x18000b61c`
- `0x18000e8d4`
- `0x18000e9f0`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `uwfcfgmgmt!UwfCfgDoesFileExclusionExist` at `0x18000eb78`
- `uwfcfgmgmt!UwfCfgDoesFileExclusionExist` at `0x18000eb78`
- `uwfcfgmgmt!UwfCfgDoesVolumeExist` at `0x18000ebaa`
- `uwfcfgmgmt!UwfCfgDoesVolumeExist` at `0x18000ebaa`
- `uwfcfgmgmt!UwfCfgDoesRegExclusionExist` at `0x18000ebdc`
- `uwfcfgmgmt!UwfCfgDoesRegExclusionExist` at `0x18000ebdc`

## string_xrefs

- `0x18000ea4b`: `UWFCspNextSessionNodeCreated`

## pseudocode

```c
__int64 __fastcall CUWFCspNextSessionNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode *v10; // rbx
  int v11; // eax
  int v12; // edi
  int DoesRegExclusionExist; // eax
  int v14; // eax
  struct ICSPNode *v15; // r15
  int *v16; // r14
  int v17; // esi
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v20; // [rsp+38h] [rbp-C8h] BYREF
  struct ICSPNode *v21; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v22; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v23; // [rsp+50h] [rbp-B0h] BYREF
  int *v24; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v25[42]; // [rsp+60h] [rbp-A0h] BYREF

  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v25);
  v25[0] = &UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable';
  UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(v25, L"UWFCspNextSessionNodeCreated");
  v10 = 0;
  v19 = 0;
  v21 = 0;
  v24 = 0;
  v20 = 0;
  v23 = 0;
  v22 = 0;
  if ( !a1 || !a2 || !a3 || !a5 || !a6 )
  {
    v12 = -2147024809;
    goto LABEL_38;
  }
  *a5 = 0;
  *a6 = 0;
  v11 = *((_DWORD *)a3 + 6);
  if ( !a4 )
  {
    if ( v11 )
      goto LABEL_28;
    if ( *((_DWORD *)a3 + 3) == 38 )
    {
      v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
              a2,
              3,
              &v23);
      if ( v12 < 0 )
        goto LABEL_38;
      DoesRegExclusionExist = UwfCfgDoesRegExclusionExist(0, v23);
    }
    else
    {
      if ( *((_DWORD *)a3 + 3) != 43 )
      {
        if ( *((_DWORD *)a3 + 3) == 44 )
          goto LABEL_28;
        if ( *((_DWORD *)a3 + 3) != 45 && *((_DWORD *)a3 + 3) != 46 )
        {
          if ( *((_DWORD *)a3 + 3) != 47 && *((_DWORD *)a3 + 3) != 48 )
          {
            if ( *((_DWORD *)a3 + 3) != 49 )
            {
              v12 = -2046820350;
              goto LABEL_39;
            }
            v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                    a2,
                    3,
                    &v20);
            if ( v12 < 0
              || (v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                          a2,
                          5,
                          &v22),
                  v12 < 0) )
            {
LABEL_38:
              v16 = v24;
              if ( v24 )
                goto LABEL_40;
              goto LABEL_39;
            }
            DoesRegExclusionExist = UwfCfgDoesFileExclusionExist(0, v20, v22);
            goto LABEL_26;
          }
LABEL_28:
          v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v19);
          if ( v12 >= 0 )
          {
            if ( *((_DWORD *)a3 + 2) + 1 == v19 )
            {
              v14 = ATL::CComObject<CUWFCspNextSessionNode>::CreateInstance(&v21);
              v10 = v21;
              v12 = v14;
              if ( v14 >= 0 )
              {
                if ( v21 )
                {
                  v15 = v21;
                  v12 = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v21 + 136LL))(
                          v21,
                          a1,
                          a2,
                          a3);
                  if ( v12 >= 0 )
                  {
                    v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, int **))(*(_QWORD *)a2 + 88LL))(
                            a2,
                            *((unsigned int *)a3 + 2),
                            &v24);
                    if ( v12 >= 0 )
                    {
                      (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v10 + 8LL))(v10);
                      v10 = 0;
                      *a5 = v15;
                    }
                  }
                }
                else
                {
                  v12 = -2147024882;
                }
              }
            }
            else
            {
              v12 = -2147418113;
            }
          }
          goto LABEL_38;
        }
      }
      v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
              a2,
              3,
              &v20);
      if ( v12 < 0 )
        goto LABEL_38;
      DoesRegExclusionExist = UwfCfgDoesVolumeExist(0, v20);
    }
LABEL_26:
    if ( DoesRegExclusionExist < 0 )
    {
      v12 = -2046820350;
      goto LABEL_38;
    }
    goto LABEL_28;
  }
  if ( !v11 )
    goto LABEL_28;
  v12 = -2046820335;
LABEL_39:
  v16 = &dword_18001F7A4;
LABEL_40:
  if ( a3 )
    v17 = *((_DWORD *)a3 + 3);
  else
    v17 = -1;
  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
    v25,
    (unsigned int)v12);
  UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned short const *>((__int64)v25, v17, v16);
  if ( v10 )
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v10 + 16LL))(v10);
  UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(v25);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000e9f0  mov     [rsp-8+arg_18], rbx
0x18000e9f5  push    rbp
0x18000e9f6  push    rsi
0x18000e9f7  push    rdi
0x18000e9f8  push    r12
0x18000e9fa  push    r13
0x18000e9fc  push    r14
0x18000e9fe  push    r15
0x18000ea00  lea     rbp, [rsp-0C0h]
0x18000ea08  sub     rsp, 1C0h
0x18000ea0f  mov     rax, cs:__security_cookie
0x18000ea16  xor     rax, rsp
0x18000ea19  mov     [rbp+0F0h+var_40], rax
0x18000ea20  mov     r12, [rbp+0F0h+arg_20]
0x18000ea27  mov     r13, rcx
0x18000ea2a  mov     rdi, [rbp+0F0h+arg_28]
0x18000ea31  lea     rcx, [rsp+1F0h+var_190]
0x18000ea36  mov     r15d, r9d
0x18000ea39  mov     rsi, r8
0x18000ea3c  mov     r14, rdx
0x18000ea3f  call    ??0?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000ea44  lea     rax, ??_7ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@6B@; const UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable'
0x18000ea4b  lea     rdx, aUwfcspnextsess_2; "UWFCspNextSessionNodeCreated"
0x18000ea52  mov     [rsp+1F0h+var_190], rax
0x18000ea57  lea     rcx, [rsp+1F0h+var_190]
0x18000ea5c  call    ?StartActivity@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(ushort const *)
0x18000ea61  xor     ebx, ebx
0x18000ea63  mov     [rsp+1F0h+var_1C0], 0
0x18000ea6b  mov     [rsp+1F0h+var_1B0], rbx
0x18000ea70  mov     [rsp+1F0h+var_198], rbx
0x18000ea75  mov     [rsp+1F0h+var_1B8], rbx
0x18000ea7a  mov     [rsp+1F0h+var_1A0], rbx
0x18000ea7f  mov     [rsp+1F0h+var_1A8], rbx
0x18000ea84  test    r13, r13
0x18000ea87  jz      loc_18000EC9C
0x18000ea8d  test    r14, r14
0x18000ea90  jz      loc_18000EC9C
0x18000ea96  test    rsi, rsi
0x18000ea99  jz      loc_18000EC9C
0x18000ea9f  test    r12, r12
0x18000eaa2  jz      loc_18000EC9C
0x18000eaa8  test    rdi, rdi
0x18000eaab  jz      loc_18000EC9C
0x18000eab1  mov     [r12], rbx
0x18000eab5  mov     [rdi], ebx
0x18000eab7  mov     eax, [rsi+18h]
0x18000eaba  test    r15d, r15d
0x18000eabd  jz      short loc_18000EAD1
0x18000eabf  test    eax, eax
0x18000eac1  jz      loc_18000EBF0
0x18000eac7  mov     edi, 86000011h
0x18000eacc  jmp     loc_18000ECAB
0x18000ead1  test    eax, eax
0x18000ead3  jnz     loc_18000EBF0
0x18000ead9  mov     ecx, [rsi+0Ch]
0x18000eadc  sub     ecx, 26h ; '&'
0x18000eadf  jz      loc_18000EBB2
0x18000eae5  sub     ecx, 5
0x18000eae8  jz      loc_18000EB80
0x18000eaee  sub     ecx, 1
0x18000eaf1  jz      loc_18000EBF0
0x18000eaf7  sub     ecx, 1
0x18000eafa  jz      loc_18000EB80
0x18000eb00  sub     ecx, 1
0x18000eb03  jz      short loc_18000EB80
0x18000eb05  sub     ecx, 1
0x18000eb08  jz      loc_18000EBF0
0x18000eb0e  sub     ecx, 1
0x18000eb11  jz      loc_18000EBF0
0x18000eb17  cmp     ecx, 1
0x18000eb1a  jz      short loc_18000EB26
0x18000eb1c  mov     edi, 86000002h
0x18000eb21  jmp     loc_18000ECAB
0x18000eb26  mov     rax, [r14]
0x18000eb29  lea     r8, [rsp+1F0h+var_1B8]
0x18000eb2e  mov     edx, 3
0x18000eb33  mov     rcx, r14
0x18000eb36  mov     rax, [rax+58h]
0x18000eb3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb3f  mov     edi, eax
0x18000eb41  test    eax, eax
0x18000eb43  js      loc_18000ECA1
0x18000eb49  mov     rax, [r14]
0x18000eb4c  lea     r8, [rsp+1F0h+var_1A8]
0x18000eb51  mov     edx, 5
0x18000eb56  mov     rcx, r14
0x18000eb59  mov     rax, [rax+58h]
0x18000eb5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb62  mov     edi, eax
0x18000eb64  test    eax, eax
0x18000eb66  js      loc_18000ECA1
0x18000eb6c  mov     r8, [rsp+1F0h+var_1A8]
0x18000eb71  xor     ecx, ecx
0x18000eb73  mov     rdx, [rsp+1F0h+var_1B8]
0x18000eb78  call    cs:__imp_?UwfCfgDoesFileExclusionExist@@YAJ_NPEBG1@Z; UwfCfgDoesFileExclusionExist(bool,ushort const *,ushort const *)
0x18000eb7e  jmp     short loc_18000EBE2
0x18000eb80  mov     rax, [r14]
0x18000eb83  lea     r8, [rsp+1F0h+var_1B8]
0x18000eb88  mov     edx, 3
0x18000eb8d  mov     rcx, r14
0x18000eb90  mov     rax, [rax+58h]
0x18000eb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb99  mov     edi, eax
0x18000eb9b  test    eax, eax
0x18000eb9d  js      loc_18000ECA1
0x18000eba3  mov     rdx, [rsp+1F0h+var_1B8]
0x18000eba8  xor     ecx, ecx
0x18000ebaa  call    cs:__imp_?UwfCfgDoesVolumeExist@@YAJ_NPEBG@Z; UwfCfgDoesVolumeExist(bool,ushort const *)
0x18000ebb0  jmp     short loc_18000EBE2
0x18000ebb2  mov     rax, [r14]
0x18000ebb5  lea     r8, [rsp+1F0h+var_1A0]
0x18000ebba  mov     edx, 3
0x18000ebbf  mov     rcx, r14
0x18000ebc2  mov     rax, [rax+58h]
0x18000ebc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebcb  mov     edi, eax
0x18000ebcd  test    eax, eax
0x18000ebcf  js      loc_18000ECA1
0x18000ebd5  mov     rdx, [rsp+1F0h+var_1A0]
0x18000ebda  xor     ecx, ecx
0x18000ebdc  call    cs:__imp_?UwfCfgDoesRegExclusionExist@@YAJ_NPEBG@Z; UwfCfgDoesRegExclusionExist(bool,ushort const *)
0x18000ebe2  test    eax, eax
0x18000ebe4  jns     short loc_18000EBF0
0x18000ebe6  mov     edi, 86000002h
0x18000ebeb  jmp     loc_18000ECA1
0x18000ebf0  mov     rax, [r14]
0x18000ebf3  lea     rdx, [rsp+1F0h+var_1C0]
0x18000ebf8  mov     rcx, r14
0x18000ebfb  mov     rax, [rax+88h]
0x18000ec02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec07  mov     edi, eax
0x18000ec09  test    eax, eax
0x18000ec0b  js      loc_18000ECA1
0x18000ec11  mov     eax, [rsi+8]
0x18000ec14  inc     eax
0x18000ec16  cmp     eax, [rsp+1F0h+var_1C0]
0x18000ec1a  jz      short loc_18000EC23
0x18000ec1c  mov     edi, 8000FFFFh
0x18000ec21  jmp     short loc_18000ECA1
0x18000ec23  lea     rcx, [rsp+1F0h+var_1B0]
0x18000ec28  call    ?CreateInstance@?$CComObject@VCUWFCspNextSessionNode@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUWFCspNextSessionNode>::CreateInstance(ATL::CComObject<CUWFCspNextSessionNode> * *)
0x18000ec2d  mov     rbx, [rsp+1F0h+var_1B0]
0x18000ec32  mov     edi, eax
0x18000ec34  test    eax, eax
0x18000ec36  js      short loc_18000ECA1
0x18000ec38  test    rbx, rbx
0x18000ec3b  jnz     short loc_18000EC44
0x18000ec3d  mov     edi, 8007000Eh
0x18000ec42  jmp     short loc_18000ECA1
0x18000ec44  mov     rax, [rbx]
0x18000ec47  mov     r9, rsi
0x18000ec4a  mov     r8, r14
0x18000ec4d  mov     rdx, r13
0x18000ec50  mov     rcx, rbx
0x18000ec53  mov     r15, rbx
0x18000ec56  mov     rax, [rax+88h]
0x18000ec5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec62  mov     edi, eax
0x18000ec64  test    eax, eax
0x18000ec66  js      short loc_18000ECA1
0x18000ec68  mov     rax, [r14]
0x18000ec6b  lea     r8, [rsp+1F0h+var_198]
0x18000ec70  mov     edx, [rsi+8]
0x18000ec73  mov     rcx, r14
0x18000ec76  mov     rax, [rax+58h]
0x18000ec7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec7f  mov     edi, eax
0x18000ec81  test    eax, eax
0x18000ec83  js      short loc_18000ECA1
0x18000ec85  mov     rax, [rbx]
0x18000ec88  mov     rcx, rbx
0x18000ec8b  mov     rax, [rax+8]
0x18000ec8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec94  xor     ebx, ebx
0x18000ec96  mov     [r12], r15
0x18000ec9a  jmp     short loc_18000ECA1
0x18000ec9c  mov     edi, 80070057h
0x18000eca1  mov     r14, [rsp+1F0h+var_198]
0x18000eca6  test    r14, r14
0x18000eca9  jnz     short loc_18000ECB2
0x18000ecab  lea     r14, dword_18001F7A4
0x18000ecb2  test    rsi, rsi
0x18000ecb5  jz      short loc_18000ECBC
0x18000ecb7  mov     esi, [rsi+0Ch]
0x18000ecba  jmp     short loc_18000ECBF
0x18000ecbc  or      esi, 0FFFFFFFFh
0x18000ecbf  mov     edx, edi
0x18000ecc1  lea     rcx, [rsp+1F0h+var_190]
0x18000ecc6  call    ?SetStopResult@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000eccb  mov     r8, r14
0x18000ecce  lea     rcx, [rsp+1F0h+var_190]
0x18000ecd3  mov     edx, esi
0x18000ecd5  call    ??$Stop@KPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXKPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ulong,ushort const *>(ulong,ushort const *)
0x18000ecda  test    rbx, rbx
0x18000ecdd  jz      short loc_18000ECEE
0x18000ecdf  mov     rax, [rbx]
0x18000ece2  mov     rcx, rbx
0x18000ece5  mov     rax, [rax+10h]
0x18000ece9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecee  lea     rcx, [rsp+1F0h+var_190]
0x18000ecf3  call    ??1ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAA@XZ; UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(void)
0x18000ecf8  mov     eax, edi
0x18000ecfa  mov     rcx, [rbp+0F0h+var_40]
0x18000ed01  xor     rcx, rsp; StackCookie
0x18000ed04  call    __security_check_cookie
0x18000ed09  mov     rbx, [rsp+1F0h+arg_18]
0x18000ed11  add     rsp, 1C0h
0x18000ed18  pop     r15
0x18000ed1a  pop     r14
0x18000ed1c  pop     r13
0x18000ed1e  pop     r12
0x18000ed20  pop     rdi
0x18000ed21  pop     rsi
0x18000ed22  pop     rbp
0x18000ed23  retn
```
