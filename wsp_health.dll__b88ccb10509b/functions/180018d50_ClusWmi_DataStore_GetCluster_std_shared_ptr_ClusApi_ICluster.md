# ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)

- ea: `0x180018d50`
- end: `0x180018f15`
- name: `?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(struct ProtectedPwd *)`
- caller_count: `14`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180019124`
- `0x1800193a0`
- `0x180019494`
- `0x180019588`
- `0x18001967c`
- `0x180019744`
- `0x18002cd20`
- `0x18004a070`
- `0x18004a5c0`
- `0x180060790`
- `0x180060f98`
- `0x180062184`
- `0x180062e00`
- `0x1800802c0`

## callees

- `0x180002ae0`
- `0x18000b8e4`
- `0x18000ca34`
- `0x18000d6dc`
- `0x18000e044`
- `0x180015964`
- `0x18001657c`
- `0x1800173e8`
- `0x18001880c`
- `0x180018aec`
- `0x180018c5c`
- `0x180018d50`
- `0x18008c010`

## string_xrefs

- `0x180018ea2`: `Could not retrieve the cache object.`
- `0x180018ecd`: `Could not determine the callers SID.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ClusWmi::DataStore::GetCluster(struct ProtectedPwd *a1, __int64 a2)
{
  struct ProtectedPwd *v4; // rdx
  unsigned int Cluster; // ebx
  _QWORD *v6; // rdx
  _QWORD *v7; // rdx
  struct cxl::TraceManager *v8; // rax
  struct cxl::TraceManager *v9; // rax
  std::_Ref_count_base *v11[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v12[3]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v14[16]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v15[7]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v16; // [rsp+98h] [rbp-68h]
  _BYTE v17[32]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v18[7]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v19; // [rsp+F8h] [rbp-8h]

  std::wstring::wstring(v17);
  v12[2] = 0;
  v12[0] = &cxl::Sid::`vftable';
  if ( (unsigned __int8)ClusWmi::DataStore::GetCacheKey(a1, v17, v12) )
  {
    *(_OWORD *)v11 = 0;
    if ( (unsigned __int8)ClusWmi::DataStore::GetCacheObject(a1, v17, v12, v11) )
    {
      v19 = 0;
      v18[0] = &std::_Func_impl_no_alloc<_lambda_a413d403165183883ace92772bbb9a4e_,long,std::shared_ptr<ClusApi::ICluster> *>::`vftable';
      v18[1] = *(_QWORD *)_lambda_33e675c04fdaa7323dae71b33ee6353e_::_lambda_33e675c04fdaa7323dae71b33ee6353e_(
                            (_lambda_33e675c04fdaa7323dae71b33ee6353e_ *)v13,
                            a1);
      v19 = v18;
      v16 = 0;
      v15[0] = &std::_Func_impl_no_alloc<_lambda_4ff77fe33ab4f331b5a4e1146a620f7d_,long,std::shared_ptr<ClusApi::ICluster> *>::`vftable';
      v15[1] = *(_QWORD *)_lambda_33e675c04fdaa7323dae71b33ee6353e_::_lambda_33e675c04fdaa7323dae71b33ee6353e_(
                            (_lambda_33e675c04fdaa7323dae71b33ee6353e_ *)v14,
                            v4);
      v16 = v15;
      Cluster = ClusWmi::DataStore::CacheObject::GetCluster(v11[0], v15, v18, a2);
      if ( v16 )
      {
        v6 = v15;
        LOBYTE(v6) = v16 != v15;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v16 + 32LL))(v16, v6);
        v16 = 0;
      }
      if ( v19 )
      {
        v7 = v18;
        LOBYTE(v7) = v19 != v18;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v19 + 32LL))(v19, v7);
      }
    }
    else
    {
      v8 = cxl::TraceManager::Instance();
      cxl::TextWriter::WriteLine<37>((__int64)v8 + 40, (__int64)"Could not retrieve the cache object.");
      Cluster = -2147023782;
    }
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
  }
  else
  {
    v9 = cxl::TraceManager::Instance();
    cxl::TextWriter::WriteLine<37>((__int64)v9 + 40, (__int64)"Could not determine the callers SID.");
    Cluster = -2147023782;
  }
  cxl::Sid::~Sid((cxl::Sid *)v12);
  std::wstring::_Tidy_deallocate(v17);
  return Cluster;
}

```

## disassembly

```asm
0x180018d50  mov     [rsp-8+arg_10], rbx
0x180018d55  mov     [rsp-8+arg_18], rdi
0x180018d5a  push    rbp
0x180018d5b  lea     rbp, [rsp-10h]
0x180018d60  sub     rsp, 110h
0x180018d67  mov     rax, cs:__security_cookie
0x180018d6e  xor     rax, rsp
0x180018d71  mov     [rbp+10h+var_10], rax
0x180018d75  mov     rdi, rdx
0x180018d78  mov     rbx, rcx
0x180018d7b  lea     rcx, [rbp+10h+var_70]
0x180018d7f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180018d84  nop
0x180018d85  mov     [rsp+110h+var_D0], 0
0x180018d8e  lea     rax, ??_7Sid@cxl@@6B@; const cxl::Sid::`vftable'
0x180018d95  mov     [rsp+110h+var_E0], rax
0x180018d9a  lea     r8, [rsp+110h+var_E0]
0x180018d9f  lea     rdx, [rbp+10h+var_70]
0x180018da3  mov     rcx, rbx
0x180018da6  call    ?GetCacheKey@DataStore@ClusWmi@@AEAA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVSid@cxl@@@Z; ClusWmi::DataStore::GetCacheKey(std::wstring &,cxl::Sid &)
0x180018dab  test    al, al
0x180018dad  jz      loc_180018EC4
0x180018db3  xorps   xmm0, xmm0
0x180018db6  movdqu  xmmword ptr [rsp+110h+var_F0], xmm0
0x180018dbc  lea     r9, [rsp+110h+var_F0]
0x180018dc1  lea     r8, [rsp+110h+var_E0]
0x180018dc6  lea     rdx, [rbp+10h+var_70]
0x180018dca  mov     rcx, rbx
0x180018dcd  call    ?GetCacheObject@DataStore@ClusWmi@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVSid@cxl@@PEAV?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@4@@Z; ClusWmi::DataStore::GetCacheObject(std::wstring const &,cxl::Sid &,std::shared_ptr<ClusWmi::DataStore::CacheObject> *)
0x180018dd2  test    al, al
0x180018dd4  jz      loc_180018E99
0x180018dda  mov     [rbp+10h+var_18], 0
0x180018de2  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_a413d403165183883ace92772bbb9a4e_@@JPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_a413d403165183883ace92772bbb9a4e_,long,std::shared_ptr<ClusApi::ICluster> *>::`vftable'
0x180018de9  mov     [rbp+10h+var_50], rax
0x180018ded  mov     rdx, rbx; struct ProtectedPwd *
0x180018df0  lea     rcx, [rsp+110h+var_C8]; this
0x180018df5  call    ??0_lambda_33e675c04fdaa7323dae71b33ee6353e_@@QEAA@PEAVProtectedPwd@@@Z; _lambda_33e675c04fdaa7323dae71b33ee6353e_::_lambda_33e675c04fdaa7323dae71b33ee6353e_(ProtectedPwd *)
0x180018dfa  mov     rcx, [rax]
0x180018dfd  mov     [rbp+10h+var_48], rcx
0x180018e01  lea     rax, [rbp+10h+var_50]
0x180018e05  mov     [rbp+10h+var_18], rax
0x180018e09  mov     [rbp+10h+var_78], 0
0x180018e11  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_4ff77fe33ab4f331b5a4e1146a620f7d_@@JPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_4ff77fe33ab4f331b5a4e1146a620f7d_,long,std::shared_ptr<ClusApi::ICluster> *>::`vftable'
0x180018e18  mov     [rsp+110h+var_B0], rax
0x180018e1d  lea     rcx, [rsp+110h+var_C0]; this
0x180018e22  call    ??0_lambda_33e675c04fdaa7323dae71b33ee6353e_@@QEAA@PEAVProtectedPwd@@@Z; _lambda_33e675c04fdaa7323dae71b33ee6353e_::_lambda_33e675c04fdaa7323dae71b33ee6353e_(ProtectedPwd *)
0x180018e27  mov     rdx, [rax]
0x180018e2a  mov     [rsp+110h+var_A8], rdx
0x180018e2f  lea     rax, [rsp+110h+var_B0]
0x180018e34  mov     [rbp+10h+var_78], rax
0x180018e38  mov     r9, rdi
0x180018e3b  lea     r8, [rbp+10h+var_50]
0x180018e3f  lea     rdx, [rsp+110h+var_B0]
0x180018e44  mov     rcx, [rsp+110h+var_F0]
0x180018e49  call    ?GetCluster@CacheObject@DataStore@ClusWmi@@QEAAJAEBV?$function@$$A6AJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z@std@@0PEAV?$shared_ptr@UICluster@ClusApi@@@5@@Z; ClusWmi::DataStore::CacheObject::GetCluster(std::function<long (std::shared_ptr<ClusApi::ICluster> *)> const &,std::function<long (std::shared_ptr<ClusApi::ICluster> *)> const &,std::shared_ptr<ClusApi::ICluster> *)
0x180018e4e  mov     ebx, eax
0x180018e50  mov     rcx, [rbp+10h+var_78]
0x180018e54  test    rcx, rcx
0x180018e57  jz      short loc_180018E78
0x180018e59  mov     rax, [rcx]
0x180018e5c  lea     rdx, [rsp+110h+var_B0]
0x180018e61  cmp     rcx, rdx
0x180018e64  setnz   dl
0x180018e67  mov     rax, [rax+20h]
0x180018e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e70  mov     [rbp+10h+var_78], 0
0x180018e78  mov     rcx, [rbp+10h+var_18]
0x180018e7c  test    rcx, rcx
0x180018e7f  jz      short loc_180018EB3
0x180018e81  mov     rax, [rcx]
0x180018e84  lea     rdx, [rbp+10h+var_50]
0x180018e88  cmp     rcx, rdx
0x180018e8b  setnz   dl
0x180018e8e  mov     rax, [rax+20h]
0x180018e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e97  jmp     short loc_180018EB3
0x180018e99  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180018e9e  lea     rcx, [rax+28h]
0x180018ea2  lea     rdx, aCouldNotRetrie; "Could not retrieve the cache object."
0x180018ea9  call    ??$WriteLine@$0CF@@TextWriter@cxl@@QEAAAEAV01@AEAY0CF@$$CBD@Z; cxl::TextWriter::WriteLine<37>(char const (&)[37])
0x180018eae  mov     ebx, 8007045Ah
0x180018eb3  mov     rcx, [rsp+110h+var_F0+8]; this
0x180018eb8  test    rcx, rcx
0x180018ebb  jz      short loc_180018EDE
0x180018ebd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018ec2  jmp     short loc_180018EDE
0x180018ec4  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180018ec9  lea     rcx, [rax+28h]
0x180018ecd  lea     rdx, aCouldNotDeterm_0; "Could not determine the callers SID."
0x180018ed4  call    ??$WriteLine@$0CF@@TextWriter@cxl@@QEAAAEAV01@AEAY0CF@$$CBD@Z; cxl::TextWriter::WriteLine<37>(char const (&)[37])
0x180018ed9  mov     ebx, 8007045Ah
0x180018ede  lea     rcx, [rsp+110h+var_E0]; this
0x180018ee3  call    ??1Sid@cxl@@UEAA@XZ; cxl::Sid::~Sid(void)
0x180018ee8  nop
0x180018ee9  lea     rcx, [rbp+10h+var_70]
0x180018eed  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018ef2  mov     eax, ebx
0x180018ef4  mov     rcx, [rbp+10h+var_10]
0x180018ef8  xor     rcx, rsp; StackCookie
0x180018efb  call    __security_check_cookie
0x180018f00  lea     r11, [rsp+110h+var_s0]
0x180018f08  mov     rbx, [r11+20h]
0x180018f0c  mov     rdi, [r11+28h]
0x180018f10  mov     rsp, r11
0x180018f13  pop     rbp
0x180018f14  retn
```
