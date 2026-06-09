# _anonymous_namespace_::GetInformation__TOKEN_USER_1_

- ea: `0x140080c70`
- end: `0x140080ef0`
- name: `_anonymous_namespace_::GetInformation__TOKEN_USER_1_`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140082fe8`

## callees

- `0x1400057f0`
- `0x140006338`
- `0x14001f6b4`
- `0x140020340`
- `0x140060f58`
- `0x14006d2c0`
- `0x140080c70`
- `0x1400a8010`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140080cb3`
- `ADVAPI32!GetTokenInformation` at `0x140080d83`
- `ADVAPI32!GetTokenInformation` at `0x140080cb3`
- `ADVAPI32!GetTokenInformation` at `0x140080d83`
- `KERNEL32!GetLastError` at `0x140080cbd`
- `KERNEL32!GetLastError` at `0x140080e8e`
- `KERNEL32!GetLastError` at `0x140080cbd`
- `KERNEL32!GetLastError` at `0x140080e8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall anonymous_namespace_::GetInformation__TOKEN_USER_1_(_QWORD *a1, void *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  _DWORD *v6; // rdi
  volatile signed __int32 *v7; // rbx
  LPVOID v8; // rcx
  volatile signed __int32 *v9; // rbx
  signed int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // [rsp+38h] [rbp-21h] BYREF
  volatile signed __int32 *v14; // [rsp+40h] [rbp-19h]
  _OWORD v15[2]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+68h] [rbp+Fh] BYREF
  DWORD ReturnLength; // [rsp+D0h] [rbp+77h] BYREF
  _DWORD *v18; // [rsp+D8h] [rbp+7Fh]

  ReturnLength = 0;
  if ( !GetTokenInformation(a2, TokenUser, 0, 0, &ReturnLength) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 122 || !ReturnLength )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v5);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
      throw (ErrorCodeException *)pExceptionObject;
    }
  }
  v6 = operator new(0x28u);
  v18 = v6;
  *(_OWORD *)v6 = 0;
  v6[2] = 1;
  v6[3] = 1;
  *(_QWORD *)v6 = &std::_Ref_count_obj2<std::vector<unsigned char>>::`vftable';
  std::vector<unsigned char>::vector<unsigned char>(v6 + 4, ReturnLength);
  *(_QWORD *)&v15[0] = v6 + 4;
  *((_QWORD *)&v15[0] + 1) = v6;
  stdext::shared_ref<Lazy<std::wstring,Optional>::Impl>::shared_ref<Lazy<std::wstring,Optional>::Impl>(&v13, v15);
  v7 = (volatile signed __int32 *)*((_QWORD *)&v15[0] + 1);
  if ( *((_QWORD *)&v15[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v15[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  if ( !GetTokenInformation(a2, TokenUser, *(LPVOID *)v13, *(_DWORD *)(v13 + 8) - *(_DWORD *)v13, &ReturnLength) )
  {
    v11 = GetLastError();
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v12);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v12);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v8 = *(LPVOID *)v13;
  v9 = v14;
  if ( v14 )
  {
    _InterlockedAdd(v14 + 2, 1u);
    v9 = v14;
  }
  v15[0] = 0;
  *a1 = v8;
  a1[1] = v9;
  v15[1] = 0;
  if ( !v8 )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140080c70  mov     [rsp-8+arg_8], rbx
0x140080c75  mov     [rsp-8+arg_0], rcx
0x140080c7a  push    rbp
0x140080c7b  push    rsi
0x140080c7c  push    rdi
0x140080c7d  push    r12
0x140080c7f  push    r14
0x140080c81  lea     rbp, [rsp-37h]
0x140080c86  sub     rsp, 90h
0x140080c8d  mov     r14, rdx
0x140080c90  mov     rsi, rcx
0x140080c93  mov     [rbp+57h+arg_10], 0
0x140080c9a  lea     rax, [rbp+57h+arg_10]
0x140080c9e  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x140080ca3  xor     r9d, r9d; TokenInformationLength
0x140080ca6  xor     r8d, r8d; TokenInformation
0x140080ca9  lea     r12d, [r9+1]
0x140080cad  mov     edx, r12d; TokenInformationClass
0x140080cb0  mov     rcx, r14; TokenHandle
0x140080cb3  call    cs:__imp_GetTokenInformation
0x140080cb9  test    eax, eax
0x140080cbb  jnz     short loc_140080CD8
0x140080cbd  call    cs:__imp_GetLastError
0x140080cc3  mov     ebx, eax
0x140080cc5  cmp     eax, 7Ah ; 'z'
0x140080cc8  jnz     loc_140080E34
0x140080cce  cmp     [rbp+57h+arg_10], 0
0x140080cd2  jz      loc_140080E34
0x140080cd8  mov     ecx, 28h ; '('; Size
0x140080cdd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140080ce2  mov     rdi, rax
0x140080ce5  mov     [rbp+57h+arg_18], rax
0x140080ce9  xorps   xmm0, xmm0
0x140080cec  movups  xmmword ptr [rax], xmm0
0x140080cef  mov     [rax+8], r12d
0x140080cf3  mov     [rax+0Ch], r12d
0x140080cf7  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@EV?$allocator@E@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<uchar>>::`vftable'
0x140080cfe  mov     [rdi], rax
0x140080d01  lea     rbx, [rdi+10h]
0x140080d05  mov     edx, [rbp+57h+arg_10]
0x140080d08  mov     rcx, rbx
0x140080d0b  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140080d10  nop
0x140080d11  mov     qword ptr [rbp+57h+var_68], rbx
0x140080d15  mov     qword ptr [rbp+57h+var_68+8], rdi
0x140080d19  lea     rdx, [rbp+57h+var_68]
0x140080d1d  lea     rcx, [rbp+57h+var_78]
0x140080d21  call    ??$?0UImpl@?$Lazy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VOptional@@@@@?$shared_ref@UImpl@?$Lazy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VOptional@@@@@stdext@@QEAA@$$QEAV?$shared_ptr@UImpl@?$Lazy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VOptional@@@@@std@@@Z; stdext::shared_ref<Lazy<std::wstring,Optional>::Impl>::shared_ref<Lazy<std::wstring,Optional>::Impl>(std::shared_ptr<Lazy<std::wstring,Optional>::Impl> &&)
0x140080d26  nop
0x140080d27  or      edi, 0FFFFFFFFh
0x140080d2a  mov     rbx, qword ptr [rbp+57h+var_68+8]
0x140080d2e  test    rbx, rbx
0x140080d31  jz      short loc_140080D66
0x140080d33  mov     eax, edi
0x140080d35  lock xadd [rbx+8], eax
0x140080d3a  add     eax, edi
0x140080d3c  jnz     short loc_140080D66
0x140080d3e  mov     rax, [rbx]
0x140080d41  mov     rcx, rbx
0x140080d44  mov     rax, [rax]
0x140080d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080d4c  mov     eax, edi
0x140080d4e  lock xadd [rbx+0Ch], eax
0x140080d53  add     eax, edi
0x140080d55  jnz     short loc_140080D66
0x140080d57  mov     rax, [rbx]
0x140080d5a  mov     rcx, rbx
0x140080d5d  mov     rax, [rax+8]
0x140080d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080d66  mov     r8, [rbp+57h+var_78]
0x140080d6a  mov     r9d, [r8+8]
0x140080d6e  sub     r9d, [r8]; TokenInformationLength
0x140080d71  lea     rax, [rbp+57h+arg_10]
0x140080d75  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x140080d7a  mov     r8, [r8]; TokenInformation
0x140080d7d  mov     edx, r12d; TokenInformationClass
0x140080d80  mov     rcx, r14; TokenHandle
0x140080d83  call    cs:__imp_GetTokenInformation
0x140080d89  test    eax, eax
0x140080d8b  jz      loc_140080E8E
0x140080d91  mov     rax, [rbp+57h+var_78]
0x140080d95  mov     rcx, [rax]
0x140080d98  mov     rbx, [rbp+57h+var_70]
0x140080d9c  test    rbx, rbx
0x140080d9f  jz      short loc_140080DAA
0x140080da1  lock add [rbx+8], r12d
0x140080da6  mov     rbx, [rbp+57h+var_70]
0x140080daa  xorps   xmm0, xmm0
0x140080dad  movdqu  [rbp+57h+var_68], xmm0
0x140080db2  mov     [rsi], rcx
0x140080db5  mov     [rsi+8], rbx
0x140080db9  movdqu  [rbp+57h+var_58], xmm0
0x140080dbe  test    rcx, rcx
0x140080dc1  jz      short loc_140080E15
0x140080dc3  test    rbx, rbx
0x140080dc6  jz      short loc_140080DFB
0x140080dc8  mov     eax, edi
0x140080dca  lock xadd [rbx+8], eax
0x140080dcf  add     eax, edi
0x140080dd1  jnz     short loc_140080DFB
0x140080dd3  mov     rax, [rbx]
0x140080dd6  mov     rcx, rbx
0x140080dd9  mov     rax, [rax]
0x140080ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080de1  mov     eax, edi
0x140080de3  lock xadd [rbx+0Ch], eax
0x140080de8  add     eax, edi
0x140080dea  jnz     short loc_140080DFB
0x140080dec  mov     rax, [rbx]
0x140080def  mov     rcx, rbx
0x140080df2  mov     rax, [rax+8]
0x140080df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140080dfb  mov     rax, rsi
0x140080dfe  mov     rbx, [rsp+0B0h+arg_8]
0x140080e06  add     rsp, 90h
0x140080e0d  pop     r14
0x140080e0f  pop     r12
0x140080e11  pop     rdi
0x140080e12  pop     rsi
0x140080e13  pop     rbp
0x140080e14  retn
0x140080e15  mov     edx, 8000FFFFh; int
0x140080e1a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140080e1e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140080e23  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140080e2a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140080e2e  call    _CxxThrowException_0
0x140080e34  test    eax, eax
0x140080e36  jle     short loc_140080E41
0x140080e38  movzx   ebx, ax
0x140080e3b  or      ebx, 80070000h
0x140080e41  lea     rax, WPP_GLOBAL_Control
0x140080e48  mov     rcx, cs:WPP_GLOBAL_Control
0x140080e4f  cmp     rcx, rax
0x140080e52  jz      short loc_140080E72
0x140080e54  test    [rcx+1Ch], r12b
0x140080e58  jz      short loc_140080E72
0x140080e5a  mov     edx, 0Ah
0x140080e5f  mov     r9d, ebx
0x140080e62  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x140080e69  mov     rcx, [rcx+10h]
0x140080e6d  call    WPP_SF_d
0x140080e72  mov     edx, ebx; int
0x140080e74  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140080e78  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140080e7d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140080e84  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140080e88  call    _CxxThrowException_0
0x140080e8e  call    cs:__imp_GetLastError
0x140080e94  mov     ebx, eax
0x140080e96  test    eax, eax
0x140080e98  jle     short loc_140080EA3
0x140080e9a  movzx   ebx, ax
0x140080e9d  or      ebx, 80070000h
0x140080ea3  lea     rax, WPP_GLOBAL_Control
0x140080eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x140080eb1  cmp     rcx, rax
0x140080eb4  jz      short loc_140080ED4
0x140080eb6  test    [rcx+1Ch], r12b
0x140080eba  jz      short loc_140080ED4
0x140080ebc  mov     edx, 0Bh
0x140080ec1  mov     r9d, ebx
0x140080ec4  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x140080ecb  mov     rcx, [rcx+10h]
0x140080ecf  call    WPP_SF_d
0x140080ed4  mov     edx, ebx; int
0x140080ed6  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140080eda  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140080edf  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140080ee6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140080eea  call    _CxxThrowException_0
```
