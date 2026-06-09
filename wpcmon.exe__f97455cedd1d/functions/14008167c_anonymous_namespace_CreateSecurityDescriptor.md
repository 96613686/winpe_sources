# _anonymous_namespace_::CreateSecurityDescriptor

- ea: `0x14008167c`
- end: `0x140081a4b`
- name: `_anonymous_namespace_::CreateSecurityDescriptor`
- size: `975`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e4ac`
- `0x14000edf0`

## callees

- `0x140005530`
- `0x1400057f0`
- `0x140006338`
- `0x14000ccac`
- `0x14001c478`
- `0x14001c804`
- `0x1400231d4`
- `0x14002e0c0`
- `0x14002f3a0`
- `0x1400604d4`
- `0x140060e60`
- `0x140060f58`
- `0x14008167c`
- `0x1400a8010`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400818a4`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400818a4`
- `KERNEL32!LocalFree` at `0x14008194f`
- `KERNEL32!LocalFree` at `0x14008194f`
- `KERNEL32!GetLastError` at `0x140081996`
- `KERNEL32!GetLastError` at `0x140081996`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall anonymous_namespace_::CreateSecurityDescriptor(_QWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rcx
  __int64 v8; // rdx
  _QWORD *v9; // rcx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  const WCHAR *v17; // rcx
  BOOL v18; // ebx
  _BYTE *v19; // rdx
  HLOCAL v20; // rbx
  _DWORD *v21; // rax
  signed int LastError; // eax
  unsigned int v24; // ebx
  int v25; // eax
  __int64 v26; // r10
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR v28[2]; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v29; // [rsp+58h] [rbp-A8h]
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h]
  unsigned __int64 v32; // [rsp+78h] [rbp-88h]
  char *pExceptionObject[8]; // [rsp+80h] [rbp-80h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v35[56]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE *v36; // [rsp+100h] [rbp+0h]

  v28[0] = a1;
  v29 = (_DWORD *)a4;
  *(_OWORD *)StringSecurityDescriptor = 0;
  v31 = 0;
  v32 = 7;
  LOWORD(StringSecurityDescriptor[0]) = 0;
  v7 = a4 + 24;
  v8 = 24;
  if ( a4 == -1 )
    v7 = 24;
  if ( *(_QWORD *)v7 )
  {
    v9 = *(_QWORD **)(a4 + 24);
    if ( !v9 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v10 = (_QWORD *)*v9;
    if ( v10 )
    {
      v11 = v10[2];
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v11) < 2 )
        goto LABEL_44;
      if ( v10[3] > 7u )
        v10 = (_QWORD *)*v10;
      std::wstring::wstring(pExceptionObject, v11, a3, L"O:", 2, v10, v11);
      std::wstring::append(StringSecurityDescriptor);
      std::wstring::~wstring(pExceptionObject);
    }
    else
    {
      std::wstring::operator+=(StringSecurityDescriptor, L"O:CO");
    }
    v13 = *(_QWORD *)(a4 + 24);
    if ( !v13 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v14 = *(_QWORD **)(v13 + 8);
    if ( v14 )
    {
      v15 = v14[2];
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v15) < 2 )
        goto LABEL_44;
      if ( v14[3] > 7u )
        v14 = (_QWORD *)*v14;
      std::wstring::wstring(pExceptionObject, v15, v12, L"G:", 2, v14, v15);
      std::wstring::append(StringSecurityDescriptor);
      std::wstring::~wstring(pExceptionObject);
    }
    else
    {
      std::wstring::operator+=(StringSecurityDescriptor, L"G:CG");
    }
  }
  if ( !a2 )
    goto LABEL_23;
  v16 = a2[2];
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v16) < 2 )
LABEL_44:
    std::_Xlen_string();
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  std::wstring::wstring(pExceptionObject, v8, a3, L"D:", 2, a2, v16);
  std::wstring::append(StringSecurityDescriptor);
  std::wstring::~wstring(pExceptionObject);
LABEL_23:
  hMem = 0;
  pExceptionObject[0] = (char *)&std::_Func_impl_no_alloc<_lambda_1a0a9a37411416c90e606832c1826ed5_,void,void *>::`vftable';
  pExceptionObject[1] = (char *)&hMem;
  pExceptionObject[7] = (char *)pExceptionObject;
  stdext::GetPointer<void *>::GetPointer<void *>(&SecurityDescriptor, pExceptionObject);
  v17 = (const WCHAR *)StringSecurityDescriptor;
  if ( v32 > 7 )
    v17 = StringSecurityDescriptor[0];
  v18 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v17, 1u, &SecurityDescriptor, 0);
  if ( v36 )
  {
    v28[0] = SecurityDescriptor;
    (*(void (__fastcall **)(_BYTE *, PSECURITY_DESCRIPTOR *))(*(_QWORD *)v36 + 16LL))(v36, v28);
    if ( v36 )
    {
      v19 = v35;
      LOBYTE(v19) = v36 != v35;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v36 + 32LL))(v36, v19);
    }
  }
  if ( !v18 )
  {
    LastError = GetLastError();
    v24 = LastError;
    if ( LastError > 0 )
      v24 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v25 = std::wstring::c_str(StringSecurityDescriptor);
      WPP_SF_Sd(*(_QWORD *)(v26 + 16), 10, (unsigned int)WPP_3c253eb01cea33b92b41eb2eed79eb93_Traceguids, v25, v24);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v24);
    throw (ErrorCodeException *)pExceptionObject;
  }
  *a1 = 0;
  a1[1] = 0;
  v20 = hMem;
  if ( hMem )
  {
    v21 = operator new(0x18u);
    v29 = v21;
    *(_OWORD *)v21 = 0;
    v21[2] = 1;
    v21[3] = 1;
    *(_QWORD *)v21 = &std::_Ref_count_resource<void *,LocalDeallocator>::`vftable';
    *((_QWORD *)v21 + 2) = v20;
    *a1 = v20;
    a1[1] = v21;
    v20 = 0;
    hMem = 0;
  }
  if ( v20 )
    LocalFree(v20);
  std::wstring::~wstring((char **)StringSecurityDescriptor);
  if ( *(_QWORD *)(a4 + 24) )
    *(_QWORD *)(a4 + 24) = 0;
  return a1;
}

```

## disassembly

```asm
0x14008167c  mov     [rsp-8+arg_10], rbx
0x140081681  push    rbp
0x140081682  push    rsi
0x140081683  push    rdi
0x140081684  push    r12
0x140081686  push    r14
0x140081688  lea     rbp, [rsp-20h]
0x14008168d  sub     rsp, 120h
0x140081694  mov     rax, cs:__security_cookie
0x14008169b  xor     rax, rsp
0x14008169e  mov     [rbp+40h+var_30], rax
0x1400816a2  mov     r14, r9
0x1400816a5  mov     rbx, rdx
0x1400816a8  mov     rsi, rcx
0x1400816ab  mov     [rsp+140h+var_F8], rcx
0x1400816b0  mov     [rsp+140h+var_E8], r9
0x1400816b5  xorps   xmm0, xmm0
0x1400816b8  movups  xmmword ptr [rsp+140h+StringSecurityDescriptor], xmm0
0x1400816bd  mov     [rsp+140h+var_D0], 0
0x1400816c6  mov     [rsp+140h+var_C8], 7
0x1400816cf  xor     eax, eax
0x1400816d1  mov     word ptr [rsp+140h+StringSecurityDescriptor], ax
0x1400816d6  lea     rax, [r9+1]
0x1400816da  lea     rcx, [rax+17h]
0x1400816de  mov     edx, 18h
0x1400816e3  test    rax, rax
0x1400816e6  cmovz   rcx, rdx
0x1400816ea  mov     rdi, 7FFFFFFFFFFFFFFEh
0x1400816f4  lea     r12d, [rdx-16h]
0x1400816f8  cmp     qword ptr [rcx], 0
0x1400816fc  jz      loc_1400817FD
0x140081702  mov     rcx, [r9+18h]
0x140081706  test    rcx, rcx
0x140081709  jz      loc_140081A07
0x14008170f  mov     rcx, [rcx]
0x140081712  test    rcx, rcx
0x140081715  jz      short loc_14008176E
0x140081717  mov     rdx, [rcx+10h]
0x14008171b  mov     rax, rdi
0x14008171e  sub     rax, rdx
0x140081721  cmp     rax, r12
0x140081724  jb      loc_140081A45
0x14008172a  cmp     qword ptr [rcx+18h], 7
0x14008172f  jbe     short loc_140081734
0x140081731  mov     rcx, [rcx]
0x140081734  mov     [rsp+140h+var_110], rdx
0x140081739  mov     [rsp+140h+var_118], rcx
0x14008173e  mov     [rsp+140h+var_120], r12
0x140081743  lea     r9, aO; "O:"
0x14008174a  lea     rcx, [rbp+40h+pExceptionObject]
0x14008174e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x140081753  nop
0x140081754  lea     rdx, [rbp+40h+pExceptionObject]
0x140081758  lea     rcx, [rsp+140h+StringSecurityDescriptor]; Src
0x14008175d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x140081762  nop
0x140081763  lea     rcx, [rbp+40h+pExceptionObject]
0x140081767  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008176c  jmp     short loc_14008177F
0x14008176e  lea     rdx, aOCo; "O:CO"
0x140081775  lea     rcx, [rsp+140h+StringSecurityDescriptor]; Src
0x14008177a  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x14008177f  mov     rcx, [r14+18h]
0x140081783  test    rcx, rcx
0x140081786  jz      loc_140081A26
0x14008178c  mov     rcx, [rcx+8]
0x140081790  test    rcx, rcx
0x140081793  jz      short loc_1400817EC
0x140081795  mov     rdx, [rcx+10h]
0x140081799  mov     rax, rdi
0x14008179c  sub     rax, rdx
0x14008179f  cmp     rax, r12
0x1400817a2  jb      loc_140081A45
0x1400817a8  cmp     qword ptr [rcx+18h], 7
0x1400817ad  jbe     short loc_1400817B2
0x1400817af  mov     rcx, [rcx]
0x1400817b2  mov     [rsp+140h+var_110], rdx
0x1400817b7  mov     [rsp+140h+var_118], rcx
0x1400817bc  mov     [rsp+140h+var_120], r12
0x1400817c1  lea     r9, aG; "G:"
0x1400817c8  lea     rcx, [rbp+40h+pExceptionObject]
0x1400817cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1400817d1  nop
0x1400817d2  lea     rdx, [rbp+40h+pExceptionObject]
0x1400817d6  lea     rcx, [rsp+140h+StringSecurityDescriptor]; Src
0x1400817db  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1400817e0  nop
0x1400817e1  lea     rcx, [rbp+40h+pExceptionObject]
0x1400817e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400817ea  jmp     short loc_1400817FD
0x1400817ec  lea     rdx, aGCg; "G:CG"
0x1400817f3  lea     rcx, [rsp+140h+StringSecurityDescriptor]; Src
0x1400817f8  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1400817fd  test    rbx, rbx
0x140081800  jz      short loc_140081854
0x140081802  mov     rax, [rbx+10h]
0x140081806  sub     rdi, rax
0x140081809  cmp     rdi, r12
0x14008180c  jb      loc_140081A45
0x140081812  cmp     qword ptr [rbx+18h], 7
0x140081817  jbe     short loc_14008181C
0x140081819  mov     rbx, [rbx]
0x14008181c  mov     [rsp+140h+var_110], rax
0x140081821  mov     [rsp+140h+var_118], rbx
0x140081826  mov     [rsp+140h+var_120], r12
0x14008182b  lea     r9, aD_1; "D:"
0x140081832  lea     rcx, [rbp+40h+pExceptionObject]
0x140081836  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x14008183b  nop
0x14008183c  lea     rdx, [rbp+40h+pExceptionObject]
0x140081840  lea     rcx, [rsp+140h+StringSecurityDescriptor]; Src
0x140081845  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x14008184a  nop
0x14008184b  lea     rcx, [rbp+40h+pExceptionObject]
0x14008184f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140081854  mov     [rsp+140h+hMem], 0
0x14008185d  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1a0a9a37411416c90e606832c1826ed5_@@XPEAX@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1a0a9a37411416c90e606832c1826ed5_,void,void *>::`vftable'
0x140081864  mov     [rbp+40h+pExceptionObject], rax
0x140081868  lea     rax, [rsp+140h+hMem]
0x14008186d  mov     [rbp+40h+var_B8], rax
0x140081871  lea     rax, [rbp+40h+pExceptionObject]
0x140081875  mov     [rbp+40h+var_88], rax
0x140081879  lea     rdx, [rbp+40h+pExceptionObject]
0x14008187d  lea     rcx, [rbp+40h+SecurityDescriptor]
0x140081881  call    ??0?$GetPointer@PEAX@stdext@@QEAA@V?$function@$$A6AXPEAX@Z@std@@@Z; stdext::GetPointer<void *>::GetPointer<void *>(std::function<void (void *)>)
0x140081886  lea     rcx, [rsp+140h+StringSecurityDescriptor]
0x14008188b  cmp     [rsp+140h+var_C8], 7
0x140081891  cmova   rcx, [rsp+140h+StringSecurityDescriptor]; StringSecurityDescriptor
0x140081897  xor     r9d, r9d; SecurityDescriptorSize
0x14008189a  lea     r8, [rbp+40h+SecurityDescriptor]; SecurityDescriptor
0x14008189e  lea     edi, [r9+1]
0x1400818a2  mov     edx, edi; StringSDRevision
0x1400818a4  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400818aa  mov     ebx, eax
0x1400818ac  mov     rcx, [rbp+40h+var_40]
0x1400818b0  test    rcx, rcx
0x1400818b3  jz      short loc_1400818EF
0x1400818b5  mov     rax, [rbp+40h+SecurityDescriptor]
0x1400818b9  mov     [rsp+140h+var_F8], rax
0x1400818be  mov     rax, [rcx]
0x1400818c1  lea     rdx, [rsp+140h+var_F8]
0x1400818c6  mov     rax, [rax+10h]
0x1400818ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400818cf  mov     rcx, [rbp+40h+var_40]
0x1400818d3  test    rcx, rcx
0x1400818d6  jz      short loc_1400818EF
0x1400818d8  mov     rax, [rcx]
0x1400818db  lea     rdx, [rbp+40h+var_78]
0x1400818df  cmp     rcx, rdx
0x1400818e2  setnz   dl
0x1400818e5  mov     rax, [rax+20h]
0x1400818e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400818ee  nop
0x1400818ef  test    ebx, ebx
0x1400818f1  jz      loc_140081996
0x1400818f7  mov     qword ptr [rsi], 0
0x1400818fe  mov     qword ptr [rsi+8], 0
0x140081906  mov     rbx, [rsp+140h+hMem]
0x14008190b  test    rbx, rbx
0x14008190e  jz      short loc_140081947
0x140081910  mov     ecx, 18h; Size
0x140081915  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14008191a  mov     [rsp+140h+var_E8], rax
0x14008191f  xorps   xmm0, xmm0
0x140081922  movups  xmmword ptr [rax], xmm0
0x140081925  mov     [rax+8], edi
0x140081928  mov     [rax+0Ch], edi
0x14008192b  lea     rcx, ??_7?$_Ref_count_resource@PEAXULocalDeallocator@@@std@@6B@; const std::_Ref_count_resource<void *,LocalDeallocator>::`vftable'
0x140081932  mov     [rax], rcx
0x140081935  mov     [rax+10h], rbx
0x140081939  mov     [rsi], rbx
0x14008193c  mov     [rsi+8], rax
0x140081940  xor     ebx, ebx
0x140081942  mov     [rsp+140h+hMem], rbx
0x140081947  test    rbx, rbx
0x14008194a  jz      short loc_140081956
0x14008194c  mov     rcx, rbx; hMem
0x14008194f  call    cs:__imp_LocalFree
0x140081955  nop
0x140081956  lea     rcx, [rsp+140h+StringSecurityDescriptor]
0x14008195b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140081960  nop
0x140081961  cmp     qword ptr [r14+18h], 0
0x140081966  jz      short loc_140081970
0x140081968  mov     qword ptr [r14+18h], 0
0x140081970  mov     rax, rsi
0x140081973  mov     rcx, [rbp+40h+var_30]
0x140081977  xor     rcx, rsp; StackCookie
0x14008197a  call    __security_check_cookie
0x14008197f  mov     rbx, [rsp+140h+arg_10]
0x140081987  add     rsp, 120h
0x14008198e  pop     r14
0x140081990  pop     r12
0x140081992  pop     rdi
0x140081993  pop     rsi
0x140081994  pop     rbp
0x140081995  retn
0x140081996  call    cs:__imp_GetLastError
0x14008199c  nop
0x14008199d  mov     ebx, eax
0x14008199f  test    eax, eax
0x1400819a1  jle     short loc_1400819AC
0x1400819a3  movzx   ebx, ax
0x1400819a6  or      ebx, 80070000h
0x1400819ac  lea     rax, WPP_GLOBAL_Control
0x1400819b3  mov     r10, cs:WPP_GLOBAL_Control
0x1400819ba  cmp     r10, rax
0x1400819bd  jz      short loc_1400819EB
0x1400819bf  test    [r10+1Ch], dil
0x1400819c3  jz      short loc_1400819EB
0x1400819c5  lea     rcx, [rsp+140h+StringSecurityDescriptor]
0x1400819ca  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1400819cf  mov     edx, 0Ah
0x1400819d4  mov     dword ptr [rsp+140h+var_120], ebx
0x1400819d8  mov     r9, rax
0x1400819db  lea     r8, WPP_3c253eb01cea33b92b41eb2eed79eb93_Traceguids
0x1400819e2  mov     rcx, [r10+10h]
0x1400819e6  call    WPP_SF_Sd
0x1400819eb  mov     edx, ebx; int
0x1400819ed  lea     rcx, [rbp+40h+pExceptionObject]; this
0x1400819f1  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400819f6  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400819fd  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x140081a01  call    _CxxThrowException_0
0x140081a07  mov     edx, 80004003h; int
0x140081a0c  lea     rcx, [rbp+40h+pExceptionObject]; this
0x140081a10  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140081a15  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140081a1c  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x140081a20  call    _CxxThrowException_0
0x140081a26  mov     edx, 80004003h; int
0x140081a2b  lea     rcx, [rbp+40h+pExceptionObject]; this
0x140081a2f  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140081a34  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140081a3b  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x140081a3f  call    _CxxThrowException_0
0x140081a45  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
