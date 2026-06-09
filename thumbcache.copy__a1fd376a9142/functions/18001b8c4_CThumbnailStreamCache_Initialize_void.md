# CThumbnailStreamCache::Initialize(void)

- ea: `0x18001b8c4`
- end: `0x18001ba08`
- name: `?Initialize@CThumbnailStreamCache@@AEAAJXZ`
- size: `324`
- prototype: `__int64 __fastcall(CThumbnailStreamCache *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b79c`
- `0x18003bcbc`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x18001b8c4`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b9db`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b9db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b90e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b90e`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001b924`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18001b924`

## string_xrefs

- `0x18001b937`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18001b9e9`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18001b907`: `Windows.Internal.Storage.ThumbnailCache.ThumbnailCache`

## pseudocode

```c
__int64 __fastcall CThumbnailStreamCache::Initialize(CThumbnailStreamCache *this)
{
  HRESULT v2; // eax
  int v3; // eax
  unsigned int v4; // ebx
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, char *); // rdi
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF
  __int64 (__fastcall ***v13)(_QWORD, GUID *, char *); // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]

  v13 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  string = 0;
  v2 = WindowsCreateStringReference(
         L"Windows.Internal.Storage.ThumbnailCache.ThumbnailCache",
         0x36u,
         &hstringHeader,
         &string);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    __debugbreak();
  }
  v3 = RoActivateInstance(string, &v13);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E7,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v3,
      (int)hstringHeader.Reserved.Reserved1);
    v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v13;
    if ( v13 )
    {
      v13 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v5)[2])(v5);
    }
    return v4;
  }
  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v13;
  v8 = **v13;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 48);
  v9 = v8(v7, &GUID_ff41dbc3_30c7_496a_bf1b_3697b1a21f18, (char *)this + 48);
  v4 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E8,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v9,
      (int)hstringHeader.Reserved.Reserved1);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    return v4;
  }
  v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v13;
  if ( v13 )
  {
    v13 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v10)[2])(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18001b8c4  push    rbp
0x18001b8c6  push    rbx
0x18001b8c7  push    rsi
0x18001b8c8  push    rdi
0x18001b8c9  mov     rbp, rsp
0x18001b8cc  sub     rsp, 58h
0x18001b8d0  mov     rax, cs:__security_cookie
0x18001b8d7  xor     rax, rsp
0x18001b8da  mov     [rbp+var_10], rax
0x18001b8de  mov     rsi, rcx
0x18001b8e1  mov     [rbp+var_18], 0
0x18001b8e9  lea     rcx, [rbp+var_18]
0x18001b8ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b8f2  mov     [rbp+string], 0
0x18001b8fa  lea     r9, [rbp+string]; string
0x18001b8fe  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001b902  mov     edx, 36h ; '6'; length
0x18001b907  lea     rcx, ?RuntimeClass_Windows_Internal_Storage_ThumbnailCache_ThumbnailCache@@3QBGB; "Windows.Internal.Storage.ThumbnailCache"...
0x18001b90e  call    cs:__imp_WindowsCreateStringReference
0x18001b914  test    eax, eax
0x18001b916  js      loc_18001B9CF
0x18001b91c  lea     rdx, [rbp+var_18]
0x18001b920  mov     rcx, [rbp+string]
0x18001b924  call    cs:__imp_RoActivateInstance
0x18001b92a  mov     ebx, eax
0x18001b92c  test    eax, eax
0x18001b92e  jns     short loc_18001B97E
0x18001b930  mov     rcx, [rbp+20h]; this
0x18001b934  mov     r9d, eax; char *
0x18001b937  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001b93e  mov     edx, 4E7h; void *
0x18001b943  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b948  nop
0x18001b949  mov     rcx, [rbp+var_18]
0x18001b94d  test    rcx, rcx
0x18001b950  jz      short loc_18001B967
0x18001b952  mov     [rbp+var_18], 0
0x18001b95a  mov     rax, [rcx]
0x18001b95d  mov     rax, [rax+10h]
0x18001b961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b966  nop
0x18001b967  mov     eax, ebx
0x18001b969  mov     rcx, [rbp+var_10]
0x18001b96d  xor     rcx, rsp; StackCookie
0x18001b970  call    __security_check_cookie
0x18001b975  add     rsp, 58h
0x18001b979  pop     rdi
0x18001b97a  pop     rsi
0x18001b97b  pop     rbx
0x18001b97c  pop     rbp
0x18001b97d  retn
0x18001b97e  mov     rbx, [rbp+var_18]
0x18001b982  mov     rax, [rbx]
0x18001b985  mov     rdi, [rax]
0x18001b988  lea     rcx, [rsi+30h]
0x18001b98c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b991  lea     r8, [rsi+30h]
0x18001b995  lea     rdx, _GUID_ff41dbc3_30c7_496a_bf1b_3697b1a21f18
0x18001b99c  mov     rcx, rbx
0x18001b99f  mov     rax, rdi
0x18001b9a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9a7  mov     ebx, eax
0x18001b9a9  test    eax, eax
0x18001b9ab  js      short loc_18001B9E2
0x18001b9ad  mov     rcx, [rbp+var_18]
0x18001b9b1  test    rcx, rcx
0x18001b9b4  jz      short loc_18001B9CB
0x18001b9b6  mov     [rbp+var_18], 0
0x18001b9be  mov     rax, [rcx]
0x18001b9c1  mov     rax, [rax+10h]
0x18001b9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9ca  nop
0x18001b9cb  xor     eax, eax
0x18001b9cd  jmp     short loc_18001B969
0x18001b9cf  xor     r9d, r9d; lpArguments
0x18001b9d2  xor     r8d, r8d; nNumberOfArguments
0x18001b9d5  lea     edx, [r9+1]; dwExceptionFlags
0x18001b9d9  mov     ecx, eax; dwExceptionCode
0x18001b9db  call    cs:__imp_RaiseException
0x18001b9e1  int     3; Trap to Debugger
0x18001b9e2  mov     rcx, [rbp+20h]; this
0x18001b9e6  mov     r9d, ebx; char *
0x18001b9e9  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001b9f0  mov     edx, 4E8h; void *
0x18001b9f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b9fa  lea     rcx, [rbp+var_18]
0x18001b9fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ba03  jmp     loc_18001B967
```
