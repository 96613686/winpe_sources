# ClusWmi::DataStore::GetCluster(std::shared_ptr<ClusApi::ICluster> *)

- ea: `0x180019720`
- end: `0x1800198e6`
- name: `?GetCluster@DataStore@ClusWmi@@QEAAJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(struct ProtectedPwd *)`
- caller_count: `14`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180019b0c`
- `0x180019da4`
- `0x180019e98`
- `0x180019f8c`
- `0x18001a084`
- `0x18001a14c`
- `0x18002dc10`
- `0x18004b9b0`
- `0x18004bf20`
- `0x180061f90`
- `0x180062798`
- `0x180063988`
- `0x180064604`
- `0x180082680`

## callees

- `0x180002b50`
- `0x18000bc64`
- `0x18000cde0`
- `0x18000daf8`
- `0x18000e4b8`
- `0x180016148`
- `0x180016e9c`
- `0x180017d20`
- `0x1800191d0`
- `0x1800194bc`
- `0x18001962c`
- `0x180019720`
- `0x18008e010`

## string_xrefs

- `0x18001989d`: `Could not determine the callers SID.`
- `0x180019872`: `Could not retrieve the cache object.`

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
      cxl::TextWriter::WriteLine<37>((char *)v8 + 40, "Could not retrieve the cache object.");
      Cluster = -2147023782;
    }
    if ( v11[1] )
      std::_Ref_count_base::_Decref(v11[1]);
  }
  else
  {
    v9 = cxl::TraceManager::Instance();
    cxl::TextWriter::WriteLine<37>((char *)v9 + 40, "Could not determine the callers SID.");
    Cluster = -2147023782;
  }
  cxl::Sid::~Sid((cxl::Sid *)v12);
  std::wstring::_Tidy_deallocate(v17);
  return Cluster;
}

```

## disassembly

```asm
0x180019720  mov     [rsp-8+arg_10], rbx
0x180019725  mov     [rsp-8+arg_18], rdi
0x18001972a  push    rbp
0x18001972b  lea     rbp, [rsp-10h]
0x180019730  sub     rsp, 110h
0x180019737  mov     rax, cs:__security_cookie
0x18001973e  xor     rax, rsp
0x180019741  mov     [rbp+10h+var_10], rax
0x180019745  mov     rdi, rdx
0x180019748  mov     rbx, rcx
0x18001974b  lea     rcx, [rbp+10h+var_70]
0x18001974f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019754  nop
0x180019755  mov     [rsp+110h+var_D0], 0
0x18001975e  lea     rax, ??_7Sid@cxl@@6B@; const cxl::Sid::`vftable'
0x180019765  mov     [rsp+110h+var_E0], rax
0x18001976a  lea     r8, [rsp+110h+var_E0]
0x18001976f  lea     rdx, [rbp+10h+var_70]
0x180019773  mov     rcx, rbx
0x180019776  call    ?GetCacheKey@DataStore@ClusWmi@@AEAA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVSid@cxl@@@Z; ClusWmi::DataStore::GetCacheKey(std::wstring &,cxl::Sid &)
0x18001977b  test    al, al
0x18001977d  jz      loc_180019894
0x180019783  xorps   xmm0, xmm0
0x180019786  movdqu  xmmword ptr [rsp+110h+var_F0], xmm0
0x18001978c  lea     r9, [rsp+110h+var_F0]
0x180019791  lea     r8, [rsp+110h+var_E0]
0x180019796  lea     rdx, [rbp+10h+var_70]
0x18001979a  mov     rcx, rbx
0x18001979d  call    ?GetCacheObject@DataStore@ClusWmi@@AEAA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVSid@cxl@@PEAV?$shared_ptr@VCacheObject@DataStore@ClusWmi@@@4@@Z; ClusWmi::DataStore::GetCacheObject(std::wstring const &,cxl::Sid &,std::shared_ptr<ClusWmi::DataStore::CacheObject> *)
0x1800197a2  test    al, al
0x1800197a4  jz      loc_180019869
0x1800197aa  mov     [rbp+10h+var_18], 0
0x1800197b2  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_a413d403165183883ace92772bbb9a4e_@@JPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_a413d403165183883ace92772bbb9a4e_,long,std::shared_ptr<ClusApi::ICluster> *>::`vftable'
0x1800197b9  mov     [rbp+10h+var_50], rax
0x1800197bd  mov     rdx, rbx; struct ProtectedPwd *
0x1800197c0  lea     rcx, [rsp+110h+var_C8]; this
0x1800197c5  call    ??0_lambda_33e675c04fdaa7323dae71b33ee6353e_@@QEAA@PEAVProtectedPwd@@@Z; _lambda_33e675c04fdaa7323dae71b33ee6353e_::_lambda_33e675c04fdaa7323dae71b33ee6353e_(ProtectedPwd *)
0x1800197ca  mov     rcx, [rax]
0x1800197cd  mov     [rbp+10h+var_48], rcx
0x1800197d1  lea     rax, [rbp+10h+var_50]
0x1800197d5  mov     [rbp+10h+var_18], rax
0x1800197d9  mov     [rbp+10h+var_78], 0
0x1800197e1  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_4ff77fe33ab4f331b5a4e1146a620f7d_@@JPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_4ff77fe33ab4f331b5a4e1146a620f7d_,long,std::shared_ptr<ClusApi::ICluster> *>::`vftable'
0x1800197e8  mov     [rsp+110h+var_B0], rax
0x1800197ed  lea     rcx, [rsp+110h+var_C0]; this
0x1800197f2  call    ??0_lambda_33e675c04fdaa7323dae71b33ee6353e_@@QEAA@PEAVProtectedPwd@@@Z; _lambda_33e675c04fdaa7323dae71b33ee6353e_::_lambda_33e675c04fdaa7323dae71b33ee6353e_(ProtectedPwd *)
0x1800197f7  mov     rdx, [rax]
0x1800197fa  mov     [rsp+110h+var_A8], rdx
0x1800197ff  lea     rax, [rsp+110h+var_B0]
0x180019804  mov     [rbp+10h+var_78], rax
0x180019808  mov     r9, rdi
0x18001980b  lea     r8, [rbp+10h+var_50]
0x18001980f  lea     rdx, [rsp+110h+var_B0]
0x180019814  mov     rcx, [rsp+110h+var_F0]
0x180019819  call    ?GetCluster@CacheObject@DataStore@ClusWmi@@QEAAJAEBV?$function@$$A6AJPEAV?$shared_ptr@UICluster@ClusApi@@@std@@@Z@std@@0PEAV?$shared_ptr@UICluster@ClusApi@@@5@@Z; ClusWmi::DataStore::CacheObject::GetCluster(std::function<long (std::shared_ptr<ClusApi::ICluster> *)> const &,std::function<long (std::shared_ptr<ClusApi::ICluster> *)> const &,std::shared_ptr<ClusApi::ICluster> *)
0x18001981e  mov     ebx, eax
0x180019820  mov     rcx, [rbp+10h+var_78]
0x180019824  test    rcx, rcx
0x180019827  jz      short loc_180019848
0x180019829  mov     rax, [rcx]
0x18001982c  lea     rdx, [rsp+110h+var_B0]
0x180019831  cmp     rcx, rdx
0x180019834  setnz   dl
0x180019837  mov     rax, [rax+20h]
0x18001983b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019840  mov     [rbp+10h+var_78], 0
0x180019848  mov     rcx, [rbp+10h+var_18]
0x18001984c  test    rcx, rcx
0x18001984f  jz      short loc_180019883
0x180019851  mov     rax, [rcx]
0x180019854  lea     rdx, [rbp+10h+var_50]
0x180019858  cmp     rcx, rdx
0x18001985b  setnz   dl
0x18001985e  mov     rax, [rax+20h]
0x180019862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019867  jmp     short loc_180019883
0x180019869  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x18001986e  lea     rcx, [rax+28h]
0x180019872  lea     rdx, aCouldNotRetrie; "Could not retrieve the cache object."
0x180019879  call    ??$WriteLine@$0CF@@TextWriter@cxl@@QEAAAEAV01@AEAY0CF@$$CBD@Z; cxl::TextWriter::WriteLine<37>(char const (&)[37])
0x18001987e  mov     ebx, 8007045Ah
0x180019883  mov     rcx, [rsp+110h+var_F0+8]; this
0x180019888  test    rcx, rcx
0x18001988b  jz      short loc_1800198AE
0x18001988d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019892  jmp     short loc_1800198AE
0x180019894  call    ?Instance@TraceManager@cxl@@SAAEAV12@XZ; cxl::TraceManager::Instance(void)
0x180019899  lea     rcx, [rax+28h]
0x18001989d  lea     rdx, aCouldNotDeterm_0; "Could not determine the callers SID."
0x1800198a4  call    ??$WriteLine@$0CF@@TextWriter@cxl@@QEAAAEAV01@AEAY0CF@$$CBD@Z; cxl::TextWriter::WriteLine<37>(char const (&)[37])
0x1800198a9  mov     ebx, 8007045Ah
0x1800198ae  lea     rcx, [rsp+110h+var_E0]; this
0x1800198b3  call    ??1Sid@cxl@@UEAA@XZ; cxl::Sid::~Sid(void)
0x1800198b8  nop
0x1800198b9  lea     rcx, [rbp+10h+var_70]
0x1800198bd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800198c2  mov     eax, ebx
0x1800198c4  mov     rcx, [rbp+10h+var_10]
0x1800198c8  xor     rcx, rsp; StackCookie
0x1800198cb  call    __security_check_cookie
0x1800198d0  lea     r11, [rsp+110h+var_s0]
0x1800198d8  mov     rbx, [r11+20h]
0x1800198dc  mov     rdi, [r11+28h]
0x1800198e0  mov     rsp, r11
0x1800198e3  pop     rbp
0x1800198e4  retn
```
