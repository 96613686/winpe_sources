# SingletonHelpers::SingletonHelper::SingletonHelper(wil::basic_zstring_view<ushort> const &,wil::basic_zstring_view<ushort> const &)

- ea: `0x140009bfc`
- end: `0x140009d2a`
- name: `??0SingletonHelper@SingletonHelpers@@QEAA@AEBV?$basic_zstring_view@G@wil@@0@Z`
- size: `302`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400508ac`

## callees

- `0x140009bfc`
- `0x140009d30`
- `0x140009d6c`
- `0x140009dac`
- `0x140009dfc`
- `0x140009e98`
- `0x140009f08`
- `0x140009f50`
- `0x14000c118`
- `0x14000f7e0`
- `0x14005b270`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140009cdf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140009cdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009ced`

## pseudocode

```c
__int64 __fastcall SingletonHelpers::SingletonHelper::SingletonHelper(__int64 a1)
{
  const WCHAR *v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rax
  void *v5; // rdx
  HANDLE Mutex; // rbx
  unsigned int v7; // r8d
  const char *v8; // r9
  _BYTE v10[32]; // [rsp+28h] [rbp-70h] BYREF
  _BYTE v11[32]; // [rsp+48h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *(_QWORD *)a1 = &SingletonHelpers::SingletonHelper::`vftable';
  std::wstring::wstring(a1 + 8);
  std::wstring::wstring(a1 + 40);
  v2 = (const WCHAR *)(a1 + 72);
  std::wstring::wstring(a1 + 72);
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 120) = 0;
  ConnectionlessEndpoint::ConnectionlessEndpoint((ConnectionlessEndpoint *)(a1 + 128));
  *(_QWORD *)(a1 + 320) = 0;
  v3 = std::operator+<unsigned short>(v11, a1 + 8, L"!");
  v4 = std::operator+<unsigned short>(v10, v3, a1 + 40);
  std::wstring::operator=(a1 + 72, v4);
  std::wstring::~wstring(v10);
  std::wstring::~wstring(v11);
  if ( *(_QWORD *)(a1 + 96) > 7u )
    v2 = *(const WCHAR **)v2;
  Mutex = CreateMutexExW(0, v2, 0, 0x1F0001u);
  if ( !Mutex )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v5, v7, v8);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1 + 104,
    Mutex);
  return a1;
}

```

## disassembly

```asm
0x140009bfc  push    rbx
0x140009bfe  push    rsi
0x140009bff  push    rdi
0x140009c00  push    r14
0x140009c02  push    r15
0x140009c04  sub     rsp, 70h
0x140009c08  mov     rax, cs:__security_cookie
0x140009c0f  xor     rax, rsp
0x140009c12  mov     [rsp+98h+var_30], rax
0x140009c17  mov     rbx, r8
0x140009c1a  mov     r14, rcx
0x140009c1d  mov     [rsp+98h+var_78], rcx
0x140009c22  lea     rax, ??_7SingletonHelper@SingletonHelpers@@6B@; const SingletonHelpers::SingletonHelper::`vftable'
0x140009c29  mov     [rcx], rax
0x140009c2c  add     rcx, 8
0x140009c30  call    ??$?0V?$basic_zstring_view@G@wil@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_zstring_view@G@wil@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(wil::basic_zstring_view<ushort> const &,std::allocator<ushort> const &)
0x140009c35  nop
0x140009c36  mov     rdx, rbx
0x140009c39  lea     rcx, [r14+28h]
0x140009c3d  call    ??$?0V?$basic_zstring_view@G@wil@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_zstring_view@G@wil@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(wil::basic_zstring_view<ushort> const &,std::allocator<ushort> const &)
0x140009c42  nop
0x140009c43  lea     rbx, [r14+48h]
0x140009c47  mov     rcx, rbx
0x140009c4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140009c4f  nop
0x140009c50  mov     qword ptr [r14+68h], 0
0x140009c58  mov     qword ptr [r14+70h], 0
0x140009c60  mov     dword ptr [r14+78h], 0
0x140009c68  lea     rcx, [r14+80h]; this
0x140009c6f  call    ??0ConnectionlessEndpoint@@QEAA@XZ; ConnectionlessEndpoint::ConnectionlessEndpoint(void)
0x140009c74  nop
0x140009c75  mov     qword ptr [r14+140h], 0
0x140009c80  lea     r8, asc_14006BAC0; "!"
0x140009c87  lea     rdx, [r14+8]
0x140009c8b  lea     rcx, [rsp+98h+var_50]
0x140009c90  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x140009c95  nop
0x140009c96  lea     r8, [r14+28h]
0x140009c9a  mov     rdx, rax
0x140009c9d  lea     rcx, [rsp+98h+var_70]
0x140009ca2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x140009ca7  mov     rdx, rax
0x140009caa  mov     rcx, rbx
0x140009cad  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140009cb2  lea     rcx, [rsp+98h+var_70]
0x140009cb7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009cbc  nop
0x140009cbd  lea     rcx, [rsp+98h+var_50]
0x140009cc2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009cc7  cmp     qword ptr [rbx+18h], 7
0x140009ccc  jbe     short loc_140009CD1
0x140009cce  mov     rbx, [rbx]
0x140009cd1  mov     r9d, 1F0001h; dwDesiredAccess
0x140009cd7  xor     r8d, r8d; dwFlags
0x140009cda  mov     rdx, rbx; lpName
0x140009cdd  xor     ecx, ecx; lpMutexAttributes
0x140009cdf  call    cs:__imp_CreateMutexExW
0x140009ce5  mov     rbx, rax
0x140009ce8  test    rax, rax
0x140009ceb  jz      short loc_140009D1C
0x140009ced  call    cs:__imp_GetLastError
0x140009cf3  mov     rdx, rbx
0x140009cf6  lea     rcx, [r14+68h]
0x140009cfa  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140009cff  nop
0x140009d00  mov     rax, r14
0x140009d03  mov     rcx, [rsp+98h+var_30]
0x140009d08  xor     rcx, rsp; StackCookie
0x140009d0b  call    __security_check_cookie
0x140009d10  add     rsp, 70h
0x140009d14  pop     r15
0x140009d16  pop     r14
0x140009d18  pop     rdi
0x140009d19  pop     rsi
0x140009d1a  pop     rbx
0x140009d1b  retn
0x140009d1c  mov     rcx, [rsp+98h]; this
0x140009d24  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
