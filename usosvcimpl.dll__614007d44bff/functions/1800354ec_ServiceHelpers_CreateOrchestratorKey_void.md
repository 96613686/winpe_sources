# ServiceHelpers::CreateOrchestratorKey(void)

- ea: `0x1800354ec`
- end: `0x1800356d4`
- name: `?CreateOrchestratorKey@ServiceHelpers@@SAJXZ`
- size: `488`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800349a8`
- `0x180035a5c`

## callees

- `0x180011680`
- `0x18001aee4`
- `0x18001b064`
- `0x1800354ec`
- `0x180039510`
- `0x18006ea28`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035699`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035699`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003564c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003564c`

## string_xrefs

- `0x18003565d`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180035672`: `USO service created Orchestrator non-volatile registry key`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 ServiceHelpers::CreateOrchestratorKey(void)
{
  __int64 *System; // rax
  __int64 v1; // rax
  __int64 v2; // rbx
  void (__fastcall *v3)(__int64, LPCWSTR *, __int128 *, __int128 *); // rdi
  _QWORD *v4; // rax
  __int64 v5; // rdx
  volatile signed __int32 *v6; // rbx
  volatile signed __int32 *v7; // rbx
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  DWORD dwOptions; // [rsp+28h] [rbp-59h]
  __int128 v13; // [rsp+58h] [rbp-29h] BYREF
  __int128 v14; // [rsp+68h] [rbp-19h] BYREF
  _BYTE v15[8]; // [rsp+78h] [rbp-9h] BYREF
  volatile signed __int32 *v16; // [rsp+80h] [rbp-1h]
  __int64 v17; // [rsp+88h] [rbp+7h] BYREF
  volatile signed __int32 *v18; // [rsp+90h] [rbp+Fh]
  HKEY hKey; // [rsp+A8h] [rbp+27h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+B0h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  System = SystemInterface::Service::GetSystem(&v17);
  v1 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*System + 32LL))(*System, v15);
  v2 = *(_QWORD *)v1;
  v3 = *(void (__fastcall **)(__int64, LPCWSTR *, __int128 *, __int128 *))(**(_QWORD **)v1 + 96LL);
  v4 = wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>();
  v5 = -1;
  do
    ++v5;
  while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v5] );
  v14 = *(_OWORD *)v4;
  *(_QWORD *)&v13 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
  *((_QWORD *)&v13 + 1) = v5;
  v3(v2, lpSubKey, &v13, &v14);
  v6 = v16;
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v7 = v18;
  if ( v18 )
  {
    if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  hKey = 0;
  v8 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v8 = lpSubKey[0];
  v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v9 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x4E2,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
            (const char *)v9,
            dwOptions);
  }
  else
  {
    *(_QWORD *)&v13 = L"USO service created Orchestrator non-volatile registry key";
    *((_QWORD *)&v13 + 1) = 58;
    SystemInterface::Log<>(&v13);
    v10 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpSubKey);
  return v10;
}

```

## disassembly

```asm
0x1800354ec  mov     rax, rsp
0x1800354ef  mov     [rax+8], rbx
0x1800354f3  mov     [rax+10h], rsi
0x1800354f7  mov     [rax+18h], rdi
0x1800354fb  mov     [rax+20h], r14
0x1800354ff  push    rbp
0x180035500  lea     rbp, [rax-5Fh]
0x180035504  sub     rsp, 0D0h
0x18003550b  mov     rax, cs:__security_cookie
0x180035512  xor     rax, rsp
0x180035515  mov     [rbp+57h+var_8], rax
0x180035519  lea     rcx, [rbp+57h+var_50]
0x18003551d  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180035522  nop
0x180035523  mov     rcx, [rax]
0x180035526  mov     rax, [rcx]
0x180035529  lea     rdx, [rbp+57h+var_60]
0x18003552d  mov     rax, [rax+20h]
0x180035531  call    _guard_dispatch_icall
0x180035536  nop
0x180035537  mov     rbx, [rax]
0x18003553a  mov     rax, [rbx]
0x18003553d  mov     rdi, [rax+60h]
0x180035541  lea     rcx, [rbp+57h+var_40]
0x180035545  call    ??$?0$00@?$basic_zstring_view@_W@wil@@QEAA@AEAY00$$CB_W@Z; wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(wchar_t const (&)[1])
0x18003554a  mov     r8, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x180035551  or      r14, 0FFFFFFFFFFFFFFFFh
0x180035555  mov     rdx, r14
0x180035558  xor     esi, esi
0x18003555a  inc     rdx
0x18003555d  cmp     [r8+rdx*2], si
0x180035562  jnz     short loc_18003555A
0x180035564  movups  xmm0, xmmword ptr [rax]
0x180035567  movdqu  [rbp+57h+var_70], xmm0
0x18003556c  mov     [rbp+57h+var_80], r8
0x180035570  mov     [rbp+57h+var_78], rdx
0x180035574  lea     r9, [rbp+57h+var_70]
0x180035578  lea     r8, [rbp+57h+var_80]
0x18003557c  lea     rdx, [rbp+57h+lpSubKey]
0x180035580  mov     rcx, rbx
0x180035583  mov     rax, rdi
0x180035586  call    _guard_dispatch_icall
0x18003558b  nop
0x18003558c  mov     rbx, [rbp+57h+var_58]
0x180035590  test    rbx, rbx
0x180035593  jz      short loc_1800355CD
0x180035595  mov     eax, r14d
0x180035598  lock xadd [rbx+8], eax
0x18003559d  add     eax, r14d
0x1800355a0  jnz     short loc_1800355CD
0x1800355a2  mov     rax, [rbx]
0x1800355a5  mov     rcx, rbx
0x1800355a8  mov     rax, [rax]
0x1800355ab  call    _guard_dispatch_icall
0x1800355b0  mov     eax, r14d
0x1800355b3  lock xadd [rbx+0Ch], eax
0x1800355b8  add     eax, r14d
0x1800355bb  jnz     short loc_1800355CD
0x1800355bd  mov     rax, [rbx]
0x1800355c0  mov     rcx, rbx
0x1800355c3  mov     rax, [rax+8]
0x1800355c7  call    _guard_dispatch_icall
0x1800355cc  nop
0x1800355cd  mov     rbx, [rbp+57h+var_48]
0x1800355d1  test    rbx, rbx
0x1800355d4  jz      short loc_18003560E
0x1800355d6  mov     eax, r14d
0x1800355d9  lock xadd [rbx+8], eax
0x1800355de  add     eax, r14d
0x1800355e1  jnz     short loc_18003560E
0x1800355e3  mov     rax, [rbx]
0x1800355e6  mov     rcx, rbx
0x1800355e9  mov     rax, [rax]
0x1800355ec  call    _guard_dispatch_icall
0x1800355f1  mov     eax, r14d
0x1800355f4  lock xadd [rbx+0Ch], eax
0x1800355f9  add     eax, r14d
0x1800355fc  jnz     short loc_18003560E
0x1800355fe  mov     rax, [rbx]
0x180035601  mov     rcx, rbx
0x180035604  mov     rax, [rax+8]
0x180035608  call    _guard_dispatch_icall
0x18003560d  nop
0x18003560e  mov     [rbp+57h+hKey], rsi
0x180035612  lea     rdx, [rbp+57h+lpSubKey]
0x180035616  cmp     [rbp+57h+var_10], 7
0x18003561b  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180035620  mov     [rsp+0D0h+lpdwDisposition], rsi; lpdwDisposition
0x180035625  lea     rax, [rbp+57h+hKey]
0x180035629  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18003562e  mov     [rsp+0D0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180035633  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x18003563b  mov     [rsp+0D0h+dwOptions], esi; unsigned int
0x18003563f  xor     r9d, r9d; lpClass
0x180035642  xor     r8d, r8d; Reserved
0x180035645  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003564c  call    cs:__imp_RegCreateKeyExW
0x180035652  test    eax, eax
0x180035654  jz      short loc_180035672
0x180035656  mov     rcx, [rbp+5Fh]; this
0x18003565a  mov     r9d, eax; char *
0x18003565d  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180035664  mov     edx, 4E2h; void *
0x180035669  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003566e  mov     ebx, eax
0x180035670  jmp     short loc_180035690
0x180035672  lea     rax, aUsoServiceCrea; "USO service created Orchestrator non-vo"...
0x180035679  mov     [rbp+57h+var_80], rax
0x18003567d  mov     [rbp+57h+var_78], 3Ah ; ':'
0x180035685  lea     rcx, [rbp+57h+var_80]
0x180035689  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x18003568e  mov     ebx, esi
0x180035690  mov     rcx, [rbp+57h+hKey]; hKey
0x180035694  test    rcx, rcx
0x180035697  jz      short loc_1800356A0
0x180035699  call    cs:__imp_RegCloseKey
0x18003569f  nop
0x1800356a0  lea     rcx, [rbp+57h+lpSubKey]; void *
0x1800356a4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800356a9  mov     eax, ebx
0x1800356ab  mov     rcx, [rbp+57h+var_8]
0x1800356af  xor     rcx, rsp; StackCookie
0x1800356b2  call    __security_check_cookie
0x1800356b7  lea     r11, [rsp+0D0h+var_s0]
0x1800356bf  mov     rbx, [r11+10h]
0x1800356c3  mov     rsi, [r11+18h]
0x1800356c7  mov     rdi, [r11+20h]
0x1800356cb  mov     r14, [r11+28h]
0x1800356cf  mov     rsp, r11
0x1800356d2  pop     rbp
0x1800356d3  retn
```
