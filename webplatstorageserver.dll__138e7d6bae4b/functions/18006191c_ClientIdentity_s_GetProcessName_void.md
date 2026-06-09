# ClientIdentity::s_GetProcessName(void)

- ea: `0x18006191c`
- end: `0x180061a65`
- name: `?s_GetProcessName@ClientIdentity@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `329`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18009ed80`
- `0x1800becb9`

## callees

- `0x1800169b0`
- `0x18006191c`
- `0x180061c90`
- `0x180080fb0`
- `0x180081b40`
- `0x180093f70`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061a41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061a41`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800619a1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800619a1`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180061a0b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180061a0b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180061a2c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180061a2c`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180061970`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180061970`

## pseudocode

```c
__int64 __fastcall ClientIdentity::s_GetProcessName(__int64 a1)
{
  unsigned int v2; // eax
  HANDLE v3; // rbx
  const char *v4; // r9
  const char *v5; // r9
  LPWSTR FileNameW; // rax
  DWORD dwSize[4]; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE v9; // [rsp+30h] [rbp-D0h]
  _DWORD RpcCallAttributes[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[56]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwProcessId; // [rsp+80h] [rbp-80h]
  WCHAR ExeName[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v14[524]; // [rsp+B4h] [rbp-4Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  *(_QWORD *)dwSize = a1;
  memset_0(v11, 0, 0x68u);
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 16;
  v2 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v2 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\clientidentity.cxx",
      (const char *)v2,
      dwSize[0]);
  v3 = OpenProcess(0x1000u, 0, dwProcessId);
  v9 = v3;
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\clientidentity.cxx",
      v4);
  *(_DWORD *)ExeName = 0;
  memset_0(v14, 0, 0x206u);
  dwSize[0] = 261;
  if ( !QueryFullProcessImageNameW(v3, 1u, ExeName, dwSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\clientidentity.cxx",
      v5);
  FileNameW = PathFindFileNameW(ExeName);
  std::wstring::wstring(a1, FileNameW);
  CloseHandle(v3);
  return a1;
}

```

## disassembly

```asm
0x18006191c  push    rbp
0x18006191e  push    rbx
0x18006191f  push    rsi
0x180061920  push    rdi
0x180061921  lea     rbp, [rsp-1D8h]
0x180061929  sub     rsp, 2D8h
0x180061930  mov     rax, cs:__security_cookie
0x180061937  xor     rax, rsp
0x18006193a  mov     [rbp+1F0h+var_30], rax
0x180061941  mov     rdi, rcx
0x180061944  mov     qword ptr [rsp+2F0h+dwSize], rcx; unsigned int
0x180061949  xor     edx, edx; Val
0x18006194b  lea     r8d, [rdx+68h]; Size
0x18006194f  lea     rcx, [rsp+2F0h+var_2A8]; void *
0x180061954  call    memset_0
0x180061959  mov     [rsp+2F0h+RpcCallAttributes], 2
0x180061961  mov     [rsp+2F0h+var_2AC], 10h
0x180061969  lea     rdx, [rsp+2F0h+RpcCallAttributes]; RpcCallAttributes
0x18006196e  xor     ecx, ecx; ClientBinding
0x180061970  call    cs:__imp_RpcServerInqCallAttributesW
0x180061976  mov     rcx, [rbp+1F8h]; this
0x18006197d  test    eax, eax
0x18006197f  jz      short loc_180061996
0x180061981  mov     r9d, eax; char *
0x180061984  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\webplatstorageser"...
0x18006198b  mov     edx, 72h ; 'r'; void *
0x180061990  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180061996  mov     r8d, [rbp+1F0h+dwProcessId]; dwProcessId
0x18006199a  xor     edx, edx; bInheritHandle
0x18006199c  mov     ecx, 1000h; dwDesiredAccess
0x1800619a1  call    cs:__imp_OpenProcess
0x1800619a7  mov     rbx, rax
0x1800619aa  mov     [rsp+2F0h+var_2C0], rax
0x1800619af  mov     rcx, [rbp+1F8h]; this
0x1800619b6  inc     rax
0x1800619b9  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800619bf  jnz     short loc_1800619D3
0x1800619c1  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\webplatstorageser"...
0x1800619c8  mov     edx, 76h ; 'v'; void *
0x1800619cd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800619d3  mov     dword ptr [rbp+1F0h+ExeName], 0
0x1800619da  xor     edx, edx; Val
0x1800619dc  mov     r8d, 206h; Size
0x1800619e2  lea     rcx, [rbp+1F0h+var_23C]; void *
0x1800619e6  call    memset_0
0x1800619eb  mov     [rsp+2F0h+dwSize], 105h
0x1800619f3  mov     rsi, [rbp+1F8h]
0x1800619fa  lea     r9, [rsp+2F0h+dwSize]; lpdwSize
0x1800619ff  lea     r8, [rbp+1F0h+ExeName]; lpExeName
0x180061a03  mov     edx, 1; dwFlags
0x180061a08  mov     rcx, rbx; hProcess
0x180061a0b  call    cs:__imp_QueryFullProcessImageNameW
0x180061a11  test    eax, eax
0x180061a13  jnz     short loc_180061A28
0x180061a15  lea     r8, aOnecoreuapInet_44; "onecoreuap\\inetcore\\webplatstorageser"...
0x180061a1c  lea     edx, [rax+7Bh]; void *
0x180061a1f  mov     rcx, rsi; this
0x180061a22  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180061a28  lea     rcx, [rbp+1F0h+ExeName]; pszPath
0x180061a2c  call    cs:__imp_PathFindFileNameW
0x180061a32  mov     rdx, rax
0x180061a35  mov     rcx, rdi
0x180061a38  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180061a3d  nop
0x180061a3e  mov     rcx, rbx; hObject
0x180061a41  call    cs:__imp_CloseHandle
0x180061a47  mov     rax, rdi
0x180061a4a  mov     rcx, [rbp+1F0h+var_30]
0x180061a51  xor     rcx, rsp; StackCookie
0x180061a54  call    __security_check_cookie
0x180061a59  add     rsp, 2D8h
0x180061a60  pop     rdi
0x180061a61  pop     rsi
0x180061a62  pop     rbx
0x180061a63  pop     rbp
0x180061a64  retn
```
