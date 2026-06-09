# Private::AddSsoPropertyToWebRequest(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> &)

- ea: `0x14007b090`
- end: `0x14007b234`
- name: `?AddSsoPropertyToWebRequest@Private@@YAXAEAV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Z`
- size: `420`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14007c310`
- `0x14007de14`

## callees

- `0x140005530`
- `0x140006338`
- `0x14001f6b4`
- `0x140031ba0`
- `0x140060f58`
- `0x14007b090`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007b0fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007b129`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007b0fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14007b129`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Private::AddSsoPropertyToWebRequest(_QWORD *a1)
{
  int v1; // eax
  int v2; // ebx
  _QWORD *v3; // rbx
  __int64 v4; // rdi
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  HSTRING v8; // rsi
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  __int64 result; // rax
  int v13; // ebx
  _QWORD *v14; // rcx
  _BYTE v15[8]; // [rsp+30h] [rbp-29h] BYREF
  _QWORD *v16; // [rsp+38h] [rbp-21h] BYREF
  HSTRING_HEADER pExceptionObject; // [rsp+40h] [rbp-19h] BYREF
  HSTRING v18; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+80h] [rbp+27h] BYREF

  v15[0] = 0;
  v16 = 0;
  v1 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)*a1 + 80LL))(*a1, &v16);
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v1);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v2);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v3 = v16;
  v4 = *v16;
  string = 0;
  v5 = WindowsCreateStringReference(L"windows", 7u, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    goto LABEL_17;
  }
  v8 = string;
  v18 = 0;
  v9 = WindowsCreateStringReference(L"ssoappgroup", 0xBu, &pExceptionObject, &v18);
  if ( v9 < 0 )
  {
LABEL_17:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    JUMPOUT(0x14007B233LL);
  }
  result = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING, _BYTE *))(v4 + 80))(v3, v18, v8, v15);
  v13 = result;
  if ( (int)result < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)result);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v13);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v14 = v16;
  if ( v16 )
  {
    v16 = 0;
    return (*(__int64 (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
  }
  return result;
}

```

## disassembly

```asm
0x14007b090  push    rbp
0x14007b092  push    rbx
0x14007b093  push    rsi
0x14007b094  push    rdi
0x14007b095  lea     rbp, [rsp-3Fh]
0x14007b09a  sub     rsp, 98h
0x14007b0a1  mov     rax, cs:__security_cookie
0x14007b0a8  xor     rax, rsp
0x14007b0ab  mov     [rbp+57h+var_28], rax
0x14007b0af  mov     [rbp+57h+var_80], 0
0x14007b0b3  mov     [rbp+57h+var_78], 0
0x14007b0bb  mov     rcx, [rcx]
0x14007b0be  mov     rax, [rcx]
0x14007b0c1  lea     rdx, [rbp+57h+var_78]
0x14007b0c5  mov     rax, [rax+50h]
0x14007b0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007b0ce  mov     ebx, eax
0x14007b0d0  test    eax, eax
0x14007b0d2  js      loc_14007B1D7
0x14007b0d8  mov     rbx, [rbp+57h+var_78]
0x14007b0dc  mov     rdi, [rbx]
0x14007b0df  mov     [rbp+57h+string], 0
0x14007b0e7  lea     r9, [rbp+57h+string]; string
0x14007b0eb  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x14007b0ef  mov     edx, 7; length
0x14007b0f4  lea     rcx, sourceString; "windows"
0x14007b0fb  call    cs:__imp_WindowsCreateStringReference
0x14007b101  test    eax, eax
0x14007b103  js      loc_14007B224
0x14007b109  mov     rsi, [rbp+57h+string]
0x14007b10d  mov     [rbp+57h+var_58], 0
0x14007b115  lea     r9, [rbp+57h+var_58]; string
0x14007b119  lea     r8, [rbp+57h+pExceptionObject]; hstringHeader
0x14007b11d  mov     edx, 0Bh; length
0x14007b122  lea     rcx, aSsoappgroup; "ssoappgroup"
0x14007b129  call    cs:__imp_WindowsCreateStringReference
0x14007b12f  test    eax, eax
0x14007b131  js      loc_14007B22C
0x14007b137  lea     r9, [rbp+57h+var_80]
0x14007b13b  mov     r8, rsi
0x14007b13e  mov     rdx, [rbp+57h+var_58]
0x14007b142  mov     rcx, rbx
0x14007b145  mov     rax, [rdi+50h]
0x14007b149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007b14e  mov     ebx, eax
0x14007b150  test    eax, eax
0x14007b152  js      short loc_14007B18A
0x14007b154  mov     rcx, [rbp+57h+var_78]
0x14007b158  test    rcx, rcx
0x14007b15b  jz      short loc_14007B172
0x14007b15d  mov     [rbp+57h+var_78], 0
0x14007b165  mov     rax, [rcx]
0x14007b168  mov     rax, [rax+10h]
0x14007b16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007b171  nop
0x14007b172  mov     rcx, [rbp+57h+var_28]
0x14007b176  xor     rcx, rsp; StackCookie
0x14007b179  call    __security_check_cookie
0x14007b17e  add     rsp, 98h
0x14007b185  pop     rdi
0x14007b186  pop     rsi
0x14007b187  pop     rbx
0x14007b188  pop     rbp
0x14007b189  retn
0x14007b18a  lea     rdx, WPP_GLOBAL_Control
0x14007b191  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b198  cmp     rcx, rdx
0x14007b19b  jz      short loc_14007B1BB
0x14007b19d  test    byte ptr [rcx+1Ch], 1
0x14007b1a1  jz      short loc_14007B1BB
0x14007b1a3  mov     edx, 0Bh
0x14007b1a8  mov     r9d, ebx
0x14007b1ab  lea     r8, WPP_d559cce52a1433e229f26c816596a62e_Traceguids
0x14007b1b2  mov     rcx, [rcx+10h]
0x14007b1b6  call    WPP_SF_d
0x14007b1bb  mov     edx, ebx; int
0x14007b1bd  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14007b1c1  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14007b1c6  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14007b1cd  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14007b1d1  call    _CxxThrowException_0
0x14007b1d7  lea     rdx, WPP_GLOBAL_Control
0x14007b1de  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b1e5  cmp     rcx, rdx
0x14007b1e8  jz      short loc_14007B208
0x14007b1ea  test    byte ptr [rcx+1Ch], 1
0x14007b1ee  jz      short loc_14007B208
0x14007b1f0  mov     edx, 0Ah
0x14007b1f5  mov     r9d, ebx
0x14007b1f8  lea     r8, WPP_d559cce52a1433e229f26c816596a62e_Traceguids
0x14007b1ff  mov     rcx, [rcx+10h]
0x14007b203  call    WPP_SF_d
0x14007b208  mov     edx, ebx; int
0x14007b20a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14007b20e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14007b213  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x14007b21a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14007b21e  call    _CxxThrowException_0
0x14007b224  mov     ecx, eax; this
0x14007b226  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14007b22b  nop
0x14007b22c  mov     ecx, eax; this
0x14007b22e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
