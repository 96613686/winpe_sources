# Wsp::Facade::FileServerFacade::CreateFileShare(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::unique_ptr<ushort,std::default_delete<ushort>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::default_delete<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,std::unique_ptr<bool,std::default_delete<bool>> const &,std::unique_ptr<bool,std::default_delete<bool>> const &)

- ea: `0x18005477c`
- end: `0x180054b0a`
- name: `?CreateFileShare@FileServerFacade@Facade@Wsp@@QEAA?AV?$shared_ptr@VFileShareFacade@Facade@Wsp@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@AEBV?$unique_ptr@GU?$default_delete@G@std@@@5@0AEBV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@2AEBV?$unique_ptr@_NU?$default_delete@_N@std@@@5@3@Z`
- size: `910`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004f5d0`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000c5c4`
- `0x18000d6a4`
- `0x18000db2c`
- `0x180049080`
- `0x180051e94`
- `0x180053a64`
- `0x180053a98`
- `0x18005477c`
- `0x1800552e4`
- `0x18005592c`
- `0x1800ab010`

## string_xrefs

- `0x180054ac7`: `Invalid volume id for create file share`
- `0x180054a49`: `Invalid protocol requested for create file share`
- `0x180054a88`: `Invalid file system type on volume for create file share`
- `0x1800548f0`: `Invalid availability type requested for create file share`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Wsp::Facade::FileServerFacade::CreateFileShare(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _WORD **a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        char **a8,
        char **a9)
{
  bool v12; // bl
  int v13; // eax
  unsigned int v14; // ebx
  char v15; // r12
  char v16; // r14
  int v17; // eax
  _WORD *v18; // rax
  int v19; // ebx
  __int64 v20; // rax
  int *i; // rax
  unsigned int v22; // ebx
  int v23; // eax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v32; // [rsp+78h] [rbp-88h]
  int *v33; // [rsp+80h] [rbp-80h] BYREF
  char *v34; // [rsp+88h] [rbp-78h]
  _BYTE v35[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+C0h] [rbp-40h] BYREF

  v30 = a3;
  v29 = a6;
  Wsp::Facade::VolumeFacade::GetInstance(&v31, a5);
  if ( !v31 )
  {
    v27 = std::wstring::wstring(&v33, L"Invalid volume id for create file share");
    v28 = 0x700000005LL;
    cxl::Exception::Exception(pExceptionObject, &v28, v27);
    throw (cxl::Exception *)pExceptionObject;
  }
  Wsp::Facade::VolumeFacade::GetFileSystemType(v31, &v28);
  if ( !v28 )
    goto LABEL_5;
  v12 = (unsigned int)(*(_DWORD *)v28 - 16) <= 1;
  v13 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 72LL))(*a1);
  if ( v12 )
  {
    if ( v13 != 1 )
    {
LABEL_5:
      v14 = 5;
      goto LABEL_6;
    }
  }
  else if ( v13 == 1 )
  {
    goto LABEL_5;
  }
  v14 = 0;
LABEL_6:
  std::unique_ptr<enum Wsp::Facade::FileShareState>::~unique_ptr<enum Wsp::Facade::FileShareState>(&v28);
  if ( v14 )
  {
    v26 = std::wstring::wstring(&v33, L"Invalid file system type on volume for create file share");
    v28 = v14 | 0x700000000LL;
    cxl::Exception::Exception(pExceptionObject, &v28, v26);
    throw (cxl::Exception *)pExceptionObject;
  }
  std::wstring::wstring(v35, &base);
  if ( *a7 )
    std::wstring::operator=(v35, *a7);
  v15 = 0;
  if ( *a9 )
    v15 = **a9;
  v16 = (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 72LL))(*a1) == 1;
  if ( *a8 )
    v16 = **a8;
  v17 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 72LL))(*a1);
  if ( !v16 )
  {
    if ( v17 != 1 )
      goto LABEL_15;
LABEL_21:
    v20 = std::wstring::wstring(&v33, L"Invalid availability type requested for create file share");
    v28 = 0x700000005LL;
    cxl::Exception::Exception(pExceptionObject, &v28, v20);
    throw (cxl::Exception *)pExceptionObject;
  }
  if ( v17 != 1 )
    goto LABEL_21;
LABEL_15:
  LODWORD(v28) = -1;
  v18 = *a4;
  if ( *a4 )
  {
    v19 = 2;
    if ( *v18 == 2 )
    {
      LODWORD(v28) = 2;
    }
    else
    {
      v19 = -1;
      if ( *v18 == 3 )
      {
        LODWORD(v28) = 3;
        v19 = 3;
      }
    }
  }
  else
  {
    Wsp::Facade::FileServerFacade::GetSupportedProtocols(a1, &v33);
    v19 = -1;
    if ( (v34 - (char *)v33) >> 5 )
    {
      v19 = *v33;
      LODWORD(v28) = *v33;
    }
    std::vector<Wsp::Facade::FileServerProtocol>::_Tidy(&v33);
  }
  Wsp::Facade::FileServerFacade::GetSupportedProtocols(a1, &v33);
  for ( i = v33; i != (int *)v34; i += 8 )
  {
    if ( *i == v19 )
    {
      v22 = 0;
      goto LABEL_33;
    }
  }
  v22 = 58014;
LABEL_33:
  std::vector<Wsp::Facade::FileServerProtocol>::_Tidy(&v33);
  if ( v22 )
  {
    v25 = std::wstring::wstring(&v33, L"Invalid protocol requested for create file share");
    v28 = v22 | 0x700000000LL;
    cxl::Exception::Exception(pExceptionObject, &v28, v25);
    throw (cxl::Exception *)pExceptionObject;
  }
  v23 = (*(__int64 (__fastcall **)(_QWORD, int **))(*(_QWORD *)*a1 + 24LL))(*a1, &v33);
  Wsp::Facade::FileShareFacade::CreateFileShare(
    a2,
    (unsigned int)&v28,
    v30,
    v23,
    (__int64)&v31,
    v29,
    (__int64)v35,
    v16,
    v15);
  std::wstring::_Tidy_deallocate(&v33);
  std::wstring::_Tidy_deallocate(v35);
  if ( v32 )
    std::_Ref_count_base::_Decref(v32);
  return a2;
}

```

## disassembly

```asm
0x18005477c  push    rbp
0x18005477e  push    rbx
0x18005477f  push    rsi
0x180054780  push    r12
0x180054782  push    r13
0x180054784  push    r14
0x180054786  push    r15
0x180054788  lea     rbp, [rsp-40h]
0x18005478d  sub     rsp, 140h
0x180054794  mov     rax, cs:__security_cookie
0x18005479b  xor     rax, rsp
0x18005479e  mov     [rbp+70h+var_40], rax
0x1800547a2  mov     r13, r9
0x1800547a5  mov     [rsp+170h+var_108], r8
0x1800547aa  mov     r15, rdx
0x1800547ad  mov     rsi, rcx
0x1800547b0  mov     r14, [rbp+70h+arg_30]
0x1800547b7  mov     [rsp+170h+var_118], rdx
0x1800547bc  mov     rdx, [rbp+70h+arg_20]
0x1800547c3  mov     rax, [rbp+70h+arg_28]
0x1800547ca  mov     [rsp+170h+var_118], rax
0x1800547cf  lea     rcx, [rsp+170h+var_100]
0x1800547d4  call    ?GetInstance@VolumeFacade@Facade@Wsp@@SA?AV?$shared_ptr@VVolumeFacade@Facade@Wsp@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Wsp::Facade::VolumeFacade::GetInstance(std::wstring const &)
0x1800547d9  nop
0x1800547da  mov     rcx, [rsp+170h+var_100]
0x1800547df  test    rcx, rcx
0x1800547e2  jz      loc_180054AC7
0x1800547e8  lea     rdx, [rsp+170h+var_120]
0x1800547ed  call    ?GetFileSystemType@VolumeFacade@Facade@Wsp@@QEBA?AV?$unique_ptr@W4FileSystemType@Facade@Wsp@@U?$default_delete@W4FileSystemType@Facade@Wsp@@@std@@@std@@XZ; Wsp::Facade::VolumeFacade::GetFileSystemType(void)
0x1800547f2  nop
0x1800547f3  mov     rax, [rsp+170h+var_120]
0x1800547f8  test    rax, rax
0x1800547fb  jz      short loc_180054828
0x1800547fd  mov     ecx, [rax]
0x1800547ff  sub     ecx, 10h
0x180054802  cmp     ecx, 1
0x180054805  setbe   bl
0x180054808  mov     rcx, [rsi]
0x18005480b  mov     rax, [rcx]
0x18005480e  mov     rax, [rax+48h]
0x180054812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054817  test    bl, bl
0x180054819  jz      loc_1800548DB
0x18005481f  cmp     eax, 1
0x180054822  jz      loc_1800548E4
0x180054828  mov     ebx, 5
0x18005482d  lea     rcx, [rsp+170h+var_120]
0x180054832  call    ??1?$unique_ptr@W4FileShareState@Facade@Wsp@@U?$default_delete@W4FileShareState@Facade@Wsp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Wsp::Facade::FileShareState>::~unique_ptr<Wsp::Facade::FileShareState>(void)
0x180054837  test    ebx, ebx
0x180054839  jnz     loc_180054A88
0x18005483f  lea     rdx, base
0x180054846  lea     rcx, [rbp+70h+var_D0]
0x18005484a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005484f  nop
0x180054850  mov     rdx, [r14]
0x180054853  test    rdx, rdx
0x180054856  jz      short loc_180054861
0x180054858  lea     rcx, [rbp+70h+var_D0]
0x18005485c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180054861  xor     r12b, r12b
0x180054864  mov     rax, [rbp+70h+arg_40]
0x18005486b  mov     rcx, [rax]
0x18005486e  test    rcx, rcx
0x180054871  jz      short loc_180054876
0x180054873  mov     r12b, [rcx]
0x180054876  mov     rcx, [rsi]
0x180054879  mov     rax, [rcx]
0x18005487c  mov     rax, [rax+48h]
0x180054880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054885  cmp     eax, 1
0x180054888  setz    r14b
0x18005488c  mov     rax, [rbp+70h+arg_38]
0x180054893  mov     rcx, [rax]
0x180054896  test    rcx, rcx
0x180054899  jz      short loc_18005489E
0x18005489b  mov     r14b, [rcx]
0x18005489e  mov     rcx, [rsi]
0x1800548a1  mov     rax, [rcx]
0x1800548a4  mov     rax, [rax+48h]
0x1800548a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548ad  test    r14b, r14b
0x1800548b0  jz      short loc_1800548EB
0x1800548b2  cmp     eax, 1
0x1800548b5  jnz     short loc_1800548F0
0x1800548b7  mov     dword ptr [rsp+170h+var_120], 0FFFFFFFFh
0x1800548bf  mov     rax, [r13+0]
0x1800548c3  test    rax, rax
0x1800548c6  jz      short loc_180054946
0x1800548c8  mov     ebx, 2
0x1800548cd  cmp     [rax], bx
0x1800548d0  jnz     short loc_180054933
0x1800548d2  mov     dword ptr [rsp+170h+var_120], ebx
0x1800548d6  jmp     loc_180054978
0x1800548db  cmp     eax, 1
0x1800548de  jz      loc_180054828
0x1800548e4  xor     ebx, ebx
0x1800548e6  jmp     loc_18005482D
0x1800548eb  cmp     eax, 1
0x1800548ee  jnz     short loc_1800548B7
0x1800548f0  lea     rdx, aInvalidAvailab; "Invalid availability type requested for"...
0x1800548f7  lea     rcx, [rbp+70h+var_F0]
0x1800548fb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180054900  nop
0x180054901  mov     dword ptr [rsp+170h+var_120], 5
0x180054909  mov     dword ptr [rsp+170h+var_120+4], 7
0x180054911  mov     r8, rax
0x180054914  lea     rdx, [rsp+170h+var_120]
0x180054919  lea     rcx, [rbp+70h+pExceptionObject]
0x18005491d  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180054922  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180054929  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x18005492d  call    _CxxThrowException_0
0x180054933  or      ebx, 0FFFFFFFFh
0x180054936  lea     ecx, [rbx+4]
0x180054939  cmp     [rax], cx
0x18005493c  jnz     short loc_180054978
0x18005493e  mov     dword ptr [rsp+170h+var_120], ecx
0x180054942  mov     ebx, ecx
0x180054944  jmp     short loc_180054978
0x180054946  lea     rdx, [rbp+70h+var_F0]
0x18005494a  mov     rcx, rsi
0x18005494d  call    ?GetSupportedProtocols@FileServerFacade@Facade@Wsp@@QEBA?BV?$vector@UFileServerProtocol@Facade@Wsp@@V?$allocator@UFileServerProtocol@Facade@Wsp@@@std@@@std@@XZ; Wsp::Facade::FileServerFacade::GetSupportedProtocols(void)
0x180054952  or      ebx, 0FFFFFFFFh
0x180054955  mov     rax, [rbp+70h+var_E8]
0x180054959  mov     rcx, [rbp+70h+var_F0]
0x18005495d  sub     rax, rcx
0x180054960  sar     rax, 5
0x180054964  test    rax, rax
0x180054967  jz      short loc_18005496F
0x180054969  mov     ebx, [rcx]
0x18005496b  mov     dword ptr [rsp+170h+var_120], ebx
0x18005496f  lea     rcx, [rbp+70h+var_F0]
0x180054973  call    ?_Tidy@?$vector@UFileServerProtocol@Facade@Wsp@@V?$allocator@UFileServerProtocol@Facade@Wsp@@@std@@@std@@AEAAXXZ; std::vector<Wsp::Facade::FileServerProtocol>::_Tidy(void)
0x180054978  lea     rdx, [rbp+70h+var_F0]
0x18005497c  mov     rcx, rsi
0x18005497f  call    ?GetSupportedProtocols@FileServerFacade@Facade@Wsp@@QEBA?BV?$vector@UFileServerProtocol@Facade@Wsp@@V?$allocator@UFileServerProtocol@Facade@Wsp@@@std@@@std@@XZ; Wsp::Facade::FileServerFacade::GetSupportedProtocols(void)
0x180054984  mov     rax, [rbp+70h+var_F0]
0x180054988  cmp     rax, [rbp+70h+var_E8]
0x18005498c  jz      short loc_18005499C
0x18005498e  cmp     [rax], ebx
0x180054990  jz      short loc_180054998
0x180054992  add     rax, 20h ; ' '
0x180054996  jmp     short loc_180054988
0x180054998  xor     ebx, ebx
0x18005499a  jmp     short loc_1800549A1
0x18005499c  mov     ebx, 0E29Eh
0x1800549a1  lea     rcx, [rbp+70h+var_F0]
0x1800549a5  call    ?_Tidy@?$vector@UFileServerProtocol@Facade@Wsp@@V?$allocator@UFileServerProtocol@Facade@Wsp@@@std@@@std@@AEAAXXZ; std::vector<Wsp::Facade::FileServerProtocol>::_Tidy(void)
0x1800549aa  test    ebx, ebx
0x1800549ac  jnz     loc_180054A49
0x1800549b2  mov     rcx, [rsi]
0x1800549b5  mov     rax, [rcx]
0x1800549b8  lea     rdx, [rbp+70h+var_F0]
0x1800549bc  mov     rax, [rax+18h]
0x1800549c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549c5  nop
0x1800549c6  mov     [rsp+170h+var_130], r12b
0x1800549cb  mov     [rsp+170h+var_138], r14b
0x1800549d0  lea     rcx, [rbp+70h+var_D0]
0x1800549d4  mov     [rsp+170h+var_140], rcx
0x1800549d9  mov     rcx, [rsp+170h+var_118]
0x1800549de  mov     [rsp+170h+var_148], rcx
0x1800549e3  lea     rcx, [rsp+170h+var_100]
0x1800549e8  mov     [rsp+170h+var_150], rcx
0x1800549ed  mov     r9, rax
0x1800549f0  mov     r8, [rsp+170h+var_108]
0x1800549f5  lea     rdx, [rsp+170h+var_120]
0x1800549fa  mov     rcx, r15
0x1800549fd  call    ?CreateFileShare@FileShareFacade@Facade@Wsp@@SA?AV?$shared_ptr@VFileShareFacade@Facade@Wsp@@@std@@AEBW4FileShareProtocol@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@1AEBV?$shared_ptr@VVolumeFacade@Facade@Wsp@@@5@AEBV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@1_N4@Z; Wsp::Facade::FileShareFacade::CreateFileShare(Wsp::Facade::FileShareProtocol const &,std::wstring const &,std::wstring const &,std::shared_ptr<Wsp::Facade::VolumeFacade> const &,std::unique_ptr<std::wstring> const &,std::wstring const &,bool,bool)
0x180054a02  nop
0x180054a03  lea     rcx, [rbp+70h+var_F0]
0x180054a07  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054a0c  nop
0x180054a0d  lea     rcx, [rbp+70h+var_D0]
0x180054a11  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180054a16  nop
0x180054a17  mov     rcx, [rsp+170h+var_F8]; this
0x180054a1c  test    rcx, rcx
0x180054a1f  jz      short loc_180054A26
0x180054a21  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180054a26  mov     rax, r15
0x180054a29  mov     rcx, [rbp+70h+var_40]
0x180054a2d  xor     rcx, rsp; StackCookie
0x180054a30  call    __security_check_cookie
0x180054a35  add     rsp, 140h
0x180054a3c  pop     r15
0x180054a3e  pop     r14
0x180054a40  pop     r13
0x180054a42  pop     r12
0x180054a44  pop     rsi
0x180054a45  pop     rbx
0x180054a46  pop     rbp
0x180054a47  retn
0x180054a49  lea     rdx, aInvalidProtoco; "Invalid protocol requested for create f"...
0x180054a50  lea     rcx, [rbp+70h+var_F0]
0x180054a54  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180054a59  nop
0x180054a5a  mov     dword ptr [rsp+170h+var_120], ebx
0x180054a5e  mov     dword ptr [rsp+170h+var_120+4], 7
0x180054a66  mov     r8, rax
0x180054a69  lea     rdx, [rsp+170h+var_120]
0x180054a6e  lea     rcx, [rbp+70h+pExceptionObject]
0x180054a72  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180054a77  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180054a7e  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180054a82  call    _CxxThrowException_0
0x180054a88  lea     rdx, aInvalidFileSys; "Invalid file system type on volume for "...
0x180054a8f  lea     rcx, [rbp+70h+var_F0]
0x180054a93  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180054a98  nop
0x180054a99  mov     dword ptr [rsp+170h+var_120], ebx
0x180054a9d  mov     dword ptr [rsp+170h+var_120+4], 7
0x180054aa5  mov     r8, rax
0x180054aa8  lea     rdx, [rsp+170h+var_120]
0x180054aad  lea     rcx, [rbp+70h+pExceptionObject]
0x180054ab1  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180054ab6  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180054abd  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180054ac1  call    _CxxThrowException_0
0x180054ac7  lea     rdx, aInvalidVolumeI; "Invalid volume id for create file share"
0x180054ace  lea     rcx, [rbp+70h+var_F0]
0x180054ad2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180054ad7  nop
0x180054ad8  mov     dword ptr [rsp+170h+var_120], 5
0x180054ae0  mov     dword ptr [rsp+170h+var_120+4], 7
0x180054ae8  mov     r8, rax
0x180054aeb  lea     rdx, [rsp+170h+var_120]
0x180054af0  lea     rcx, [rbp+70h+pExceptionObject]
0x180054af4  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180054af9  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180054b00  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180054b04  call    _CxxThrowException_0
```
