# CUWFCspCurrentSessionNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x18000d2d0`
- end: `0x18000d617`
- name: `?CreateNodeInstance@CUWFCspCurrentSessionNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `839`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007788`
- `0x180007b90`
- `0x180007fc4`
- `0x18000b4dc`
- `0x18000b61c`
- `0x18000d1bc`
- `0x18000d2d0`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `uwfcfgmgmt!UwfCfgDoesFileExclusionExist` at `0x18000d4c6`
- `uwfcfgmgmt!UwfCfgDoesFileExclusionExist` at `0x18000d4c6`
- `uwfcfgmgmt!UwfCfgDoesVolumeExist` at `0x18000d412`
- `uwfcfgmgmt!UwfCfgDoesVolumeExist` at `0x18000d412`
- `uwfcfgmgmt!UwfCfgDoesRegExclusionExist` at `0x18000d441`
- `uwfcfgmgmt!UwfCfgDoesRegExclusionExist` at `0x18000d441`

## string_xrefs

- `0x18000d32b`: `UWFCspCurrentSessionNodeCreated`

## pseudocode

```c
__int64 __fastcall CUWFCspCurrentSessionNode::CreateNodeInstance(
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
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  int DoesRegExclusionExist; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // eax
  struct ICSPNode *v21; // r15
  int *v22; // r14
  int v23; // esi
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v26; // [rsp+38h] [rbp-C8h] BYREF
  struct ICSPNode *v27; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v28; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v29; // [rsp+50h] [rbp-B0h] BYREF
  int *v30; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v31[42]; // [rsp+60h] [rbp-A0h] BYREF

  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v31);
  v31[0] = &UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable';
  UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(v31, L"UWFCspCurrentSessionNodeCreated");
  v10 = 0;
  v25 = 0;
  v30 = 0;
  v27 = 0;
  v26 = 0;
  v28 = 0;
  v29 = 0;
  if ( !a1 || !a2 || !a3 || !a5 || !a6 )
  {
    v12 = -2147024809;
    goto LABEL_41;
  }
  *a5 = 0;
  *a6 = 0;
  v11 = *((_DWORD *)a3 + 6);
  if ( !a4 )
  {
    if ( !v11 )
    {
      v13 = *((_DWORD *)a3 + 3);
      if ( v13 <= 0x16 )
      {
        if ( v13 == 22 )
          goto LABEL_16;
        v14 = v13 - 14;
        if ( !v14 )
        {
          v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                  a2,
                  3,
                  &v28);
          if ( v12 < 0 )
            goto LABEL_41;
          DoesRegExclusionExist = UwfCfgDoesRegExclusionExist(1, v28);
LABEL_20:
          if ( DoesRegExclusionExist < 0 )
          {
            v12 = -2046820350;
            goto LABEL_41;
          }
          goto LABEL_29;
        }
        v15 = v14 - 4;
        if ( !v15 || (v16 = v15 - 1) == 0 || v16 - 1 <= 1 )
        {
LABEL_16:
          v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                  a2,
                  3,
                  &v26);
          if ( v12 < 0 )
            goto LABEL_41;
          DoesRegExclusionExist = UwfCfgDoesVolumeExist(1, v26);
          goto LABEL_20;
        }
        goto LABEL_25;
      }
      v18 = v13 - 23;
      if ( !v18 )
        goto LABEL_16;
      v19 = v18 - 1;
      if ( !v19 )
      {
        v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                a2,
                3,
                &v26);
        if ( v12 < 0 )
          goto LABEL_41;
        v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                a2,
                5,
                &v29);
        if ( v12 < 0 )
          goto LABEL_41;
        DoesRegExclusionExist = UwfCfgDoesFileExclusionExist(1, v26, v29);
        goto LABEL_20;
      }
      if ( v19 - 1 >= 2 )
      {
LABEL_25:
        v12 = -2046820350;
        goto LABEL_42;
      }
    }
LABEL_29:
    v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v25);
    if ( v12 >= 0 )
    {
      if ( *((_DWORD *)a3 + 2) + 1 == v25 )
      {
        v20 = ATL::CComObject<CUWFCspCurrentSessionNode>::CreateInstance(&v27);
        v10 = v27;
        v12 = v20;
        if ( v20 >= 0 )
        {
          if ( v27 )
          {
            if ( (unsigned int)(*((_DWORD *)a3 + 3) - 25) <= 3 )
              *a6 |= 2u;
            v21 = v10;
            v12 = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v10 + 136LL))(
                    v10,
                    a1,
                    a2,
                    a3);
            if ( v12 >= 0 )
            {
              v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, int **))(*(_QWORD *)a2 + 88LL))(
                      a2,
                      *((unsigned int *)a3 + 2),
                      &v30);
              if ( v12 >= 0 )
              {
                (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v10 + 8LL))(v10);
                v10 = 0;
                *a5 = v21;
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
LABEL_41:
    v22 = v30;
    if ( v30 )
      goto LABEL_43;
    goto LABEL_42;
  }
  if ( !v11 )
    goto LABEL_29;
  v12 = -2046820335;
LABEL_42:
  v22 = &dword_18001F7A4;
LABEL_43:
  if ( a3 )
    v23 = *((_DWORD *)a3 + 3);
  else
    v23 = -1;
  wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
    v31,
    (unsigned int)v12);
  UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<unsigned long,unsigned short const *>((__int64)v31, v23, v22);
  if ( v10 )
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v10 + 16LL))(v10);
  UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(v31);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000d2d0  mov     [rsp-8+arg_18], rbx
0x18000d2d5  push    rbp
0x18000d2d6  push    rsi
0x18000d2d7  push    rdi
0x18000d2d8  push    r12
0x18000d2da  push    r13
0x18000d2dc  push    r14
0x18000d2de  push    r15
0x18000d2e0  lea     rbp, [rsp-0C0h]
0x18000d2e8  sub     rsp, 1C0h
0x18000d2ef  mov     rax, cs:__security_cookie
0x18000d2f6  xor     rax, rsp
0x18000d2f9  mov     [rbp+0F0h+var_40], rax
0x18000d300  mov     r12, [rbp+0F0h+arg_20]
0x18000d307  mov     r13, rcx
0x18000d30a  mov     r15, [rbp+0F0h+arg_28]
0x18000d311  lea     rcx, [rsp+1F0h+var_190]
0x18000d316  mov     edi, r9d
0x18000d319  mov     rsi, r8
0x18000d31c  mov     r14, rdx
0x18000d31f  call    ??0?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000d324  lea     rax, ??_7ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@6B@; const UwfTraceLoggingProvider<2>::ConfigurationActivity::`vftable'
0x18000d32b  lea     rdx, aUwfcspcurrents_1; "UWFCspCurrentSessionNodeCreated"
0x18000d332  mov     [rsp+1F0h+var_190], rax
0x18000d337  lea     rcx, [rsp+1F0h+var_190]
0x18000d33c  call    ?StartActivity@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::StartActivity(ushort const *)
0x18000d341  xor     ebx, ebx
0x18000d343  mov     [rsp+1F0h+var_1C0], 0
0x18000d34b  mov     [rsp+1F0h+var_198], 0
0x18000d354  mov     [rsp+1F0h+var_1B0], rbx
0x18000d359  mov     [rsp+1F0h+var_1B8], rbx
0x18000d35e  mov     [rsp+1F0h+var_1A8], rbx
0x18000d363  mov     [rsp+1F0h+var_1A0], rbx
0x18000d368  test    r13, r13
0x18000d36b  jz      loc_18000D58F
0x18000d371  test    r14, r14
0x18000d374  jz      loc_18000D58F
0x18000d37a  test    rsi, rsi
0x18000d37d  jz      loc_18000D58F
0x18000d383  test    r12, r12
0x18000d386  jz      loc_18000D58F
0x18000d38c  test    r15, r15
0x18000d38f  jz      loc_18000D58F
0x18000d395  mov     [r12], rbx
0x18000d399  lea     ecx, [rbx+3]
0x18000d39c  mov     [r15], ebx
0x18000d39f  mov     eax, [rsi+18h]
0x18000d3a2  test    edi, edi
0x18000d3a4  jz      short loc_18000D3B8
0x18000d3a6  test    eax, eax
0x18000d3a8  jz      loc_18000D4D1
0x18000d3ae  mov     edi, 86000011h
0x18000d3b3  jmp     loc_18000D59E
0x18000d3b8  test    eax, eax
0x18000d3ba  jnz     loc_18000D4D1
0x18000d3c0  mov     eax, [rsi+0Ch]
0x18000d3c3  cmp     eax, 16h
0x18000d3c6  ja      loc_18000D459
0x18000d3cc  jz      short loc_18000D3EB
0x18000d3ce  sub     eax, 0Eh
0x18000d3d1  jz      short loc_18000D41A
0x18000d3d3  sub     eax, 4
0x18000d3d6  jz      short loc_18000D3EB
0x18000d3d8  sub     eax, 1
0x18000d3db  jz      short loc_18000D3EB
0x18000d3dd  sub     eax, 1
0x18000d3e0  jz      short loc_18000D3EB
0x18000d3e2  cmp     eax, 1
0x18000d3e5  jnz     loc_18000D46D
0x18000d3eb  mov     rax, [r14]
0x18000d3ee  lea     r8, [rsp+1F0h+var_1B8]
0x18000d3f3  mov     edx, ecx
0x18000d3f5  mov     rcx, r14
0x18000d3f8  mov     rax, [rax+58h]
0x18000d3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d401  mov     edi, eax
0x18000d403  test    eax, eax
0x18000d405  js      loc_18000D594
0x18000d40b  mov     rdx, [rsp+1F0h+var_1B8]
0x18000d410  mov     cl, 1
0x18000d412  call    cs:__imp_?UwfCfgDoesVolumeExist@@YAJ_NPEBG@Z; UwfCfgDoesVolumeExist(bool,ushort const *)
0x18000d418  jmp     short loc_18000D447
0x18000d41a  mov     rax, [r14]
0x18000d41d  lea     r8, [rsp+1F0h+var_1A8]
0x18000d422  mov     edx, ecx
0x18000d424  mov     rcx, r14
0x18000d427  mov     rax, [rax+58h]
0x18000d42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d430  mov     edi, eax
0x18000d432  test    eax, eax
0x18000d434  js      loc_18000D594
0x18000d43a  mov     rdx, [rsp+1F0h+var_1A8]
0x18000d43f  mov     cl, 1
0x18000d441  call    cs:__imp_?UwfCfgDoesRegExclusionExist@@YAJ_NPEBG@Z; UwfCfgDoesRegExclusionExist(bool,ushort const *)
0x18000d447  test    eax, eax
0x18000d449  jns     loc_18000D4D1
0x18000d44f  mov     edi, 86000002h
0x18000d454  jmp     loc_18000D594
0x18000d459  sub     eax, 17h
0x18000d45c  jz      short loc_18000D3EB
0x18000d45e  sub     eax, 1
0x18000d461  jz      short loc_18000D477
0x18000d463  sub     eax, 1
0x18000d466  jz      short loc_18000D4D1
0x18000d468  cmp     eax, 1
0x18000d46b  jz      short loc_18000D4D1
0x18000d46d  mov     edi, 86000002h
0x18000d472  jmp     loc_18000D59E
0x18000d477  mov     rax, [r14]
0x18000d47a  lea     r8, [rsp+1F0h+var_1B8]
0x18000d47f  mov     edx, ecx
0x18000d481  mov     rcx, r14
0x18000d484  mov     rax, [rax+58h]
0x18000d488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d48d  mov     edi, eax
0x18000d48f  test    eax, eax
0x18000d491  js      loc_18000D594
0x18000d497  mov     rax, [r14]
0x18000d49a  lea     r8, [rsp+1F0h+var_1A0]
0x18000d49f  mov     edx, 5
0x18000d4a4  mov     rcx, r14
0x18000d4a7  mov     rax, [rax+58h]
0x18000d4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4b0  mov     edi, eax
0x18000d4b2  test    eax, eax
0x18000d4b4  js      loc_18000D594
0x18000d4ba  mov     r8, [rsp+1F0h+var_1A0]
0x18000d4bf  mov     cl, 1
0x18000d4c1  mov     rdx, [rsp+1F0h+var_1B8]
0x18000d4c6  call    cs:__imp_?UwfCfgDoesFileExclusionExist@@YAJ_NPEBG1@Z; UwfCfgDoesFileExclusionExist(bool,ushort const *,ushort const *)
0x18000d4cc  jmp     loc_18000D447
0x18000d4d1  mov     rax, [r14]
0x18000d4d4  lea     rdx, [rsp+1F0h+var_1C0]
0x18000d4d9  mov     rcx, r14
0x18000d4dc  mov     rax, [rax+88h]
0x18000d4e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4e8  mov     edi, eax
0x18000d4ea  test    eax, eax
0x18000d4ec  js      loc_18000D594
0x18000d4f2  mov     eax, [rsi+8]
0x18000d4f5  inc     eax
0x18000d4f7  cmp     eax, [rsp+1F0h+var_1C0]
0x18000d4fb  jz      short loc_18000D507
0x18000d4fd  mov     edi, 8000FFFFh
0x18000d502  jmp     loc_18000D594
0x18000d507  lea     rcx, [rsp+1F0h+var_1B0]
0x18000d50c  call    ?CreateInstance@?$CComObject@VCUWFCspCurrentSessionNode@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUWFCspCurrentSessionNode>::CreateInstance(ATL::CComObject<CUWFCspCurrentSessionNode> * *)
0x18000d511  mov     rbx, [rsp+1F0h+var_1B0]
0x18000d516  mov     edi, eax
0x18000d518  test    eax, eax
0x18000d51a  js      short loc_18000D594
0x18000d51c  test    rbx, rbx
0x18000d51f  jnz     short loc_18000D528
0x18000d521  mov     edi, 8007000Eh
0x18000d526  jmp     short loc_18000D594
0x18000d528  mov     eax, [rsi+0Ch]
0x18000d52b  sub     eax, 19h
0x18000d52e  cmp     eax, 3
0x18000d531  ja      short loc_18000D537
0x18000d533  or      dword ptr [r15], 2
0x18000d537  mov     rax, [rbx]
0x18000d53a  mov     r9, rsi
0x18000d53d  mov     r8, r14
0x18000d540  mov     rdx, r13
0x18000d543  mov     rcx, rbx
0x18000d546  mov     r15, rbx
0x18000d549  mov     rax, [rax+88h]
0x18000d550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d555  mov     edi, eax
0x18000d557  test    eax, eax
0x18000d559  js      short loc_18000D594
0x18000d55b  mov     rax, [r14]
0x18000d55e  lea     r8, [rsp+1F0h+var_198]
0x18000d563  mov     edx, [rsi+8]
0x18000d566  mov     rcx, r14
0x18000d569  mov     rax, [rax+58h]
0x18000d56d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d572  mov     edi, eax
0x18000d574  test    eax, eax
0x18000d576  js      short loc_18000D594
0x18000d578  mov     rax, [rbx]
0x18000d57b  mov     rcx, rbx
0x18000d57e  mov     rax, [rax+8]
0x18000d582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d587  xor     ebx, ebx
0x18000d589  mov     [r12], r15
0x18000d58d  jmp     short loc_18000D594
0x18000d58f  mov     edi, 80070057h
0x18000d594  mov     r14, [rsp+1F0h+var_198]
0x18000d599  test    r14, r14
0x18000d59c  jnz     short loc_18000D5A5
0x18000d59e  lea     r14, dword_18001F7A4
0x18000d5a5  test    rsi, rsi
0x18000d5a8  jz      short loc_18000D5AF
0x18000d5aa  mov     esi, [rsi+0Ch]
0x18000d5ad  jmp     short loc_18000D5B2
0x18000d5af  or      esi, 0FFFFFFFFh
0x18000d5b2  mov     edx, edi
0x18000d5b4  lea     rcx, [rsp+1F0h+var_190]
0x18000d5b9  call    ?SetStopResult@?$ActivityBase@V?$UwfTraceLoggingProvider@$01@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<UwfTraceLoggingProvider<2>,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000d5be  mov     r8, r14
0x18000d5c1  lea     rcx, [rsp+1F0h+var_190]
0x18000d5c6  mov     edx, esi
0x18000d5c8  call    ??$Stop@KPEBG@ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAAXKPEBG@Z; UwfTraceLoggingProvider<2>::ConfigurationActivity::Stop<ulong,ushort const *>(ulong,ushort const *)
0x18000d5cd  test    rbx, rbx
0x18000d5d0  jz      short loc_18000D5E1
0x18000d5d2  mov     rax, [rbx]
0x18000d5d5  mov     rcx, rbx
0x18000d5d8  mov     rax, [rax+10h]
0x18000d5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5e1  lea     rcx, [rsp+1F0h+var_190]
0x18000d5e6  call    ??1ConfigurationActivity@?$UwfTraceLoggingProvider@$01@@QEAA@XZ; UwfTraceLoggingProvider<2>::ConfigurationActivity::~ConfigurationActivity(void)
0x18000d5eb  mov     eax, edi
0x18000d5ed  mov     rcx, [rbp+0F0h+var_40]
0x18000d5f4  xor     rcx, rsp; StackCookie
0x18000d5f7  call    __security_check_cookie
0x18000d5fc  mov     rbx, [rsp+1F0h+arg_18]
0x18000d604  add     rsp, 1C0h
0x18000d60b  pop     r15
0x18000d60d  pop     r14
0x18000d60f  pop     r13
0x18000d611  pop     r12
0x18000d613  pop     rdi
0x18000d614  pop     rsi
0x18000d615  pop     rbp
0x18000d616  retn
```
