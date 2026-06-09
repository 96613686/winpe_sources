# _anonymous_namespace_::UserAccountImpl::GetConnectedUsername

- ea: `0x14008f5a4`
- end: `0x14008f8fa`
- name: `_anonymous_namespace_::UserAccountImpl::GetConnectedUsername`
- size: `854`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14008fe90`

## callees

- `0x140005530`
- `0x140006338`
- `0x140009858`
- `0x14000b744`
- `0x14000ccac`
- `0x14001f6b4`
- `0x1400201d8`
- `0x140060498`
- `0x140060f58`
- `0x14008f5a4`
- `0x140097130`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14008f6de`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14008f6de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14008f7c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14008f7c7`
- `PROPSYS!PropVariantToStringAlloc` at `0x14008f6c7`
- `PROPSYS!PropVariantToStringAlloc` at `0x14008f6c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall anonymous_namespace_::UserAccountImpl::GetConnectedUsername(__int64 a1, __int64 a2)
{
  struct _GUID *v3; // rdx
  PROPVARIANT *v4; // rcx
  int v5; // esi
  __int64 v6; // rax
  int v7; // esi
  PWSTR *v8; // r14
  __int64 v9; // rcx
  HRESULT v10; // esi
  _BYTE *v11; // rdx
  unsigned __int64 v12; // r8
  __int64 v14; // [rsp+30h] [rbp-128h] BYREF
  void *v15; // [rsp+38h] [rbp-120h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-118h] BYREF
  _QWORD v17[4]; // [rsp+50h] [rbp-108h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+70h] [rbp-E8h] BYREF
  _BYTE v19[40]; // [rsp+98h] [rbp-C0h] BYREF
  PROPVARIANT propvar[2]; // [rsp+C0h] [rbp-98h] BYREF
  __m128i si128; // [rsp+D0h] [rbp-88h]
  __int64 v22; // [rsp+E0h] [rbp-78h] BYREF
  _BYTE v23[56]; // [rsp+E8h] [rbp-70h] BYREF
  _BYTE *v24; // [rsp+120h] [rbp-38h]

  v17[1] = a1;
  v17[2] = a2;
  v15 = 0;
  std::wstring::wstring((__int64)propvar, a1 + 72);
  v4 = propvar;
  if ( si128.m128i_i64[1] > 7uLL )
    v4 = (PROPVARIANT *)propvar[0];
  v5 = SHFindConnectedUserBySid((const unsigned __int16 *)v4, v3, &v15);
  std::wstring::~wstring((char **)propvar);
  if ( v5 < 0 )
  {
    if ( v15 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
    *(_QWORD *)(a2 + 40) = 0;
    return a2;
  }
  else
  {
    v14 = 0;
    if ( !v15 )
      _com_issue_error(-2147467261);
    v6 = *(_QWORD *)v15;
    v14 = 0;
    v7 = (*(__int64 (__fastcall **)(void *, __int64 *))(v6 + 24))(v15, &v14);
    if ( v7 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          14,
          WPP_1224a785cfc73c5ce67aec7bb3f31008_Traceguids,
          (unsigned int)v7);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v7);
      throw (ErrorCodeException *)pExceptionObject;
    }
    pv[0] = 0;
    v8 = (PWSTR *)stdext::get_pointer<std::unique_ptr<unsigned short,ComDeallocator>>((__int64)&v22, (__int64)pv);
    v9 = v14;
    *v8 = 0;
    *(_OWORD *)propvar = 0;
    si128.m128i_i64[0] = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v9 + 40LL))(
            v9,
            &PKEY_Identity_UserName,
            propvar);
    if ( v10 >= 0 )
    {
      if ( LOWORD(propvar[0]) )
        v10 = PropVariantToStringAlloc(propvar, v8);
      else
        v10 = -2147023728;
      PropVariantClear(propvar);
    }
    if ( v24 )
    {
      v17[0] = v22;
      (*(void (__fastcall **)(_BYTE *, _QWORD *))(*(_QWORD *)v24 + 16LL))(v24, v17);
      if ( v24 )
      {
        v11 = v23;
        LOBYTE(v11) = v24 != v23;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v24 + 32LL))(v24, v11);
      }
    }
    if ( v10 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          15,
          WPP_1224a785cfc73c5ce67aec7bb3f31008_Traceguids,
          (unsigned int)v10);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v19, v10);
      throw (ErrorCodeException *)v19;
    }
    *(_OWORD *)propvar = 0;
    si128 = 0;
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)pv[0] + v12) );
    std::wstring::_Construct<1,unsigned short const *>((char **)propvar, pv[0], v12);
    *(_OWORD *)(a2 + 8) = *(_OWORD *)propvar;
    *(__m128i *)(a2 + 24) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(propvar[0]) = 0;
    *(_QWORD *)(a2 + 40) = a2 + 8;
    std::wstring::~wstring((char **)propvar);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v15 )
      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)v15 + 16LL))(v15, *(_QWORD *)v15);
    return a2;
  }
}

```

## disassembly

```asm
0x14008f5a4  mov     [rsp+arg_10], rbx
0x14008f5a9  push    rsi
0x14008f5aa  push    rdi
0x14008f5ab  push    r14
0x14008f5ad  sub     rsp, 140h
0x14008f5b4  mov     rax, cs:__security_cookie
0x14008f5bb  xor     rax, rsp
0x14008f5be  mov     [rsp+158h+var_28], rax
0x14008f5c6  mov     rdi, rdx
0x14008f5c9  mov     [rsp+158h+var_100], rcx
0x14008f5ce  mov     [rsp+158h+var_F8], rdx
0x14008f5d3  xor     ebx, ebx
0x14008f5d5  mov     [rsp+158h+var_120], rbx
0x14008f5da  lea     rdx, [rcx+48h]
0x14008f5de  lea     rcx, [rsp+158h+propvar]
0x14008f5e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14008f5eb  nop
0x14008f5ec  lea     rcx, [rsp+158h+propvar]
0x14008f5f4  cmp     qword ptr [rsp+158h+var_88+8], 7
0x14008f5fd  cmova   rcx, [rsp+158h+propvar]; unsigned __int16 *
0x14008f606  lea     r8, [rsp+158h+var_120]; void **
0x14008f60b  call    ?SHFindConnectedUserBySid@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; SHFindConnectedUserBySid(ushort const *,_GUID const &,void * *)
0x14008f610  mov     esi, eax
0x14008f612  lea     rcx, [rsp+158h+propvar]
0x14008f61a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008f61f  test    esi, esi
0x14008f621  js      loc_14008F801
0x14008f627  mov     [rsp+158h+var_128], rbx
0x14008f62c  mov     rcx, [rsp+158h+var_120]
0x14008f631  test    rcx, rcx
0x14008f634  jz      loc_14008F8EE
0x14008f63a  mov     rax, [rcx]
0x14008f63d  mov     [rsp+158h+var_128], rbx
0x14008f642  lea     rdx, [rsp+158h+var_128]
0x14008f647  mov     rax, [rax+18h]
0x14008f64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008f650  mov     esi, eax
0x14008f652  test    eax, eax
0x14008f654  js      loc_14008F84C
0x14008f65a  mov     [rsp+158h+pv], rbx
0x14008f65f  lea     rdx, [rsp+158h+pv]
0x14008f664  lea     rcx, [rsp+158h+var_78]
0x14008f66c  call    ??$get_pointer@V?$unique_ptr@GUComDeallocator@@@std@@@stdext@@YA?AV?$GetPointer@PEAG@0@AEAV?$unique_ptr@GUComDeallocator@@@std@@@Z; stdext::get_pointer<std::unique_ptr<ushort,ComDeallocator>>(std::unique_ptr<ushort,ComDeallocator> &)
0x14008f671  mov     r14, rax
0x14008f674  mov     rcx, [rsp+158h+var_128]
0x14008f679  mov     [rax], rbx
0x14008f67c  xorps   xmm0, xmm0
0x14008f67f  xor     eax, eax
0x14008f681  movups  xmmword ptr [rsp+158h+propvar], xmm0
0x14008f689  mov     qword ptr [rsp+158h+var_88], rax
0x14008f691  mov     rax, [rcx]
0x14008f694  lea     r8, [rsp+158h+propvar]
0x14008f69c  lea     rdx, PKEY_Identity_UserName
0x14008f6a3  mov     rax, [rax+28h]
0x14008f6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008f6ac  mov     esi, eax
0x14008f6ae  test    eax, eax
0x14008f6b0  js      short loc_14008F6E5
0x14008f6b2  cmp     bx, word ptr [rsp+158h+propvar]
0x14008f6ba  jz      short loc_14008F6D1
0x14008f6bc  mov     rdx, r14; ppszOut
0x14008f6bf  lea     rcx, [rsp+158h+propvar]; propvar
0x14008f6c7  call    cs:__imp_PropVariantToStringAlloc
0x14008f6cd  mov     esi, eax
0x14008f6cf  jmp     short loc_14008F6D6
0x14008f6d1  mov     esi, 80070490h
0x14008f6d6  lea     rcx, [rsp+158h+propvar]; pvar
0x14008f6de  call    cs:__imp_PropVariantClear
0x14008f6e4  nop
0x14008f6e5  mov     rcx, [rsp+158h+var_38]
0x14008f6ed  test    rcx, rcx
0x14008f6f0  jz      short loc_14008F738
0x14008f6f2  mov     rax, [rsp+158h+var_78]
0x14008f6fa  mov     [rsp+158h+var_108], rax
0x14008f6ff  mov     rax, [rcx]
0x14008f702  lea     rdx, [rsp+158h+var_108]
0x14008f707  mov     rax, [rax+10h]
0x14008f70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008f710  mov     rcx, [rsp+158h+var_38]
0x14008f718  test    rcx, rcx
0x14008f71b  jz      short loc_14008F738
0x14008f71d  mov     rax, [rcx]
0x14008f720  lea     rdx, [rsp+158h+var_70]
0x14008f728  cmp     rcx, rdx
0x14008f72b  setnz   dl
0x14008f72e  mov     rax, [rax+20h]
0x14008f732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008f737  nop
0x14008f738  test    esi, esi
0x14008f73a  js      loc_14008F899
0x14008f740  mov     rdx, [rsp+158h+pv]
0x14008f745  xorps   xmm0, xmm0
0x14008f748  movups  xmmword ptr [rsp+158h+propvar], xmm0
0x14008f750  xorps   xmm1, xmm1
0x14008f753  movdqu  [rsp+158h+var_88], xmm1
0x14008f75c  or      r8, 0FFFFFFFFFFFFFFFFh
0x14008f760  inc     r8
0x14008f763  cmp     [rdx+r8*2], bx
0x14008f768  jnz     short loc_14008F760
0x14008f76a  lea     rcx, [rsp+158h+propvar]
0x14008f772  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14008f777  lea     rax, [rdi+8]
0x14008f77b  movups  xmm0, xmmword ptr [rsp+158h+propvar]
0x14008f783  movups  xmmword ptr [rax], xmm0
0x14008f786  movups  xmm1, [rsp+158h+var_88]
0x14008f78e  movups  xmmword ptr [rax+10h], xmm1
0x14008f792  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14008f79a  movdqu  [rsp+158h+var_88], xmm0
0x14008f7a3  mov     word ptr [rsp+158h+propvar], bx
0x14008f7ab  mov     [rdi+28h], rax
0x14008f7af  lea     rcx, [rsp+158h+propvar]
0x14008f7b7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008f7bc  nop
0x14008f7bd  mov     rcx, [rsp+158h+pv]; pv
0x14008f7c2  test    rcx, rcx
0x14008f7c5  jz      short loc_14008F7CE
0x14008f7c7  call    cs:__imp_CoTaskMemFree
0x14008f7cd  nop
0x14008f7ce  mov     rcx, [rsp+158h+var_128]
0x14008f7d3  test    rcx, rcx
0x14008f7d6  jz      short loc_14008F7E5
0x14008f7d8  mov     rax, [rcx]
0x14008f7db  mov     rax, [rax+10h]
0x14008f7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008f7e4  nop
0x14008f7e5  mov     rcx, [rsp+158h+var_120]
0x14008f7ea  test    rcx, rcx
0x14008f7ed  jz      short loc_14008F7FC
0x14008f7ef  mov     rdx, [rcx]
0x14008f7f2  mov     rax, [rdx+10h]
0x14008f7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008f7fb  nop
0x14008f7fc  mov     rax, rdi
0x14008f7ff  jmp     short loc_14008F828
0x14008f801  mov     rcx, [rsp+158h+var_120]
0x14008f806  test    rcx, rcx
0x14008f809  jz      short loc_14008F818
0x14008f80b  mov     rax, [rcx]
0x14008f80e  mov     rax, [rax+10h]
0x14008f812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008f817  nop
0x14008f818  jmp     short loc_14008F821
0x14008f81a  xor     ebx, ebx
0x14008f81c  mov     rdi, [rsp+158h+var_F8]
0x14008f821  mov     [rdi+28h], rbx
0x14008f825  mov     rax, rdi
0x14008f828  mov     rcx, [rsp+158h+var_28]
0x14008f830  xor     rcx, rsp; StackCookie
0x14008f833  call    __security_check_cookie
0x14008f838  mov     rbx, [rsp+158h+arg_10]
0x14008f840  add     rsp, 140h
0x14008f847  pop     r14
0x14008f849  pop     rdi
0x14008f84a  pop     rsi
0x14008f84b  retn
0x14008f84c  lea     rax, WPP_GLOBAL_Control
0x14008f853  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f85a  cmp     rcx, rax
0x14008f85d  jz      short loc_14008F87B
0x14008f85f  test    byte ptr [rcx+1Ch], 1
0x14008f863  jz      short loc_14008F87B
0x14008f865  lea     edx, [rbx+0Eh]
0x14008f868  mov     r9d, esi
0x14008f86b  lea     r8, WPP_1224a785cfc73c5ce67aec7bb3f31008_Traceguids
0x14008f872  mov     rcx, [rcx+10h]
0x14008f876  call    WPP_SF_d
0x14008f87b  mov     edx, esi; int
0x14008f87d  lea     rcx, [rsp+158h+pExceptionObject]; this
0x14008f882  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14008f887  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14008f88e  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x14008f893  call    _CxxThrowException_0
0x14008f899  lea     rax, WPP_GLOBAL_Control
0x14008f8a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f8a7  cmp     rcx, rax
0x14008f8aa  jz      short loc_14008F8CA
0x14008f8ac  test    byte ptr [rcx+1Ch], 1
0x14008f8b0  jz      short loc_14008F8CA
0x14008f8b2  mov     edx, 0Fh
0x14008f8b7  mov     r9d, esi
0x14008f8ba  lea     r8, WPP_1224a785cfc73c5ce67aec7bb3f31008_Traceguids
0x14008f8c1  mov     rcx, [rcx+10h]
0x14008f8c5  call    WPP_SF_d
0x14008f8ca  mov     edx, esi; int
0x14008f8cc  lea     rcx, [rsp+158h+var_C0]; this
0x14008f8d4  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14008f8d9  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14008f8e0  lea     rcx, [rsp+158h+var_C0]; pExceptionObject
0x14008f8e8  call    _CxxThrowException_0
0x14008f8ee  mov     ecx, 80004003h; int
0x14008f8f3  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
