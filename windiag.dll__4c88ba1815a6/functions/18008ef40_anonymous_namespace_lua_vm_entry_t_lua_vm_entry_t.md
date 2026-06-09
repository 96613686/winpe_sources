# _anonymous_namespace_::lua_vm_entry_t::lua_vm_entry_t

- ea: `0x18008ef40`
- end: `0x18008f074`
- name: `_anonymous_namespace_::lua_vm_entry_t::lua_vm_entry_t`
- size: `308`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180090780`
- `0x180090bf0`

## callees

- `0x180004510`
- `0x18003b3b0`
- `0x180041564`
- `0x1800416a0`
- `0x18008ef40`
- `0x180096b94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configthreadlocale` at `0x18008ef92`
- `api-ms-win-crt-private-l1-1-0!_o__configthreadlocale` at `0x18008ef92`
- `api-ms-win-crt-private-l1-1-0!_o_setlocale` at `0x18008efa4`
- `api-ms-win-crt-private-l1-1-0!_o_setlocale` at `0x18008efa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008efc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f035`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008efc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008f035`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008efeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008efeb`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18008f041`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18008f041`
- `api-ms-win-core-processthreads-l1-1-3!GetThreadDescription` at `0x18008efd1`
- `api-ms-win-core-processthreads-l1-1-3!GetThreadDescription` at `0x18008efd1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::lua_vm_entry_t::lua_vm_entry_t(__int64 a1, const CHAR *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  HANDLE CurrentThread; // rax
  void *v7; // rcx
  const WCHAR *v8; // rbx
  HANDLE v9; // rax
  PWSTR ppszThreadDescription[2]; // [rsp+20h] [rbp-48h] BYREF
  PCWSTR lpThreadDescription[4]; // [rsp+30h] [rbp-38h] BYREF

  ppszThreadDescription[1] = (PWSTR)a1;
  *(_QWORD *)a1 = 0;
  v4 = a1 + 16;
  *(_OWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 15;
  *(_BYTE *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 8) = _o__configthreadlocale(1);
  v5 = _o_setlocale(0, ".utf8");
  if ( v5 )
    std::string::operator=(v4, v5);
  ppszThreadDescription[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( GetThreadDescription(CurrentThread, ppszThreadDescription) >= 0 )
  {
    v7 = *(void **)a1;
    *(PWSTR *)a1 = ppszThreadDescription[0];
    if ( v7 )
      LocalFree(v7);
  }
  if ( *(_QWORD *)a1 && wcscmp_0(*(const wchar_t **)a1, L"main") )
  {
    if ( !a2 )
      a2 = "<lua_module>";
    windiag::char_to_wstring((__int64)lpThreadDescription, a2);
    v8 = (const WCHAR *)lpThreadDescription;
    if ( lpThreadDescription[3] > (PCWSTR)7 )
      v8 = lpThreadDescription[0];
    v9 = GetCurrentThread();
    SetThreadDescription(v9, v8);
    std::wstring::~wstring((char **)lpThreadDescription);
  }
  return a1;
}

```

## disassembly

```asm
0x18008ef40  mov     [rsp+arg_10], rbx
0x18008ef45  mov     [rsp+arg_18], rsi
0x18008ef4a  push    rdi
0x18008ef4b  sub     rsp, 60h
0x18008ef4f  mov     rax, cs:__security_cookie
0x18008ef56  xor     rax, rsp
0x18008ef59  mov     [rsp+68h+var_18], rax
0x18008ef5e  mov     rsi, rdx
0x18008ef61  mov     rdi, rcx
0x18008ef64  mov     [rsp+68h+var_40], rcx
0x18008ef69  mov     qword ptr [rcx], 0
0x18008ef70  lea     rbx, [rcx+10h]
0x18008ef74  xorps   xmm0, xmm0
0x18008ef77  movups  xmmword ptr [rbx], xmm0
0x18008ef7a  mov     qword ptr [rbx+10h], 0
0x18008ef82  mov     qword ptr [rbx+18h], 0Fh
0x18008ef8a  mov     byte ptr [rbx], 0
0x18008ef8d  mov     ecx, 1
0x18008ef92  call    cs:__imp__o__configthreadlocale
0x18008ef98  mov     [rdi+8], eax
0x18008ef9b  lea     rdx, aUtf8; ".utf8"
0x18008efa2  xor     ecx, ecx
0x18008efa4  call    cs:__imp__o_setlocale
0x18008efaa  test    rax, rax
0x18008efad  jz      short loc_18008EFBA
0x18008efaf  mov     rdx, rax
0x18008efb2  mov     rcx, rbx
0x18008efb5  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@QEBD@Z; std::string::operator=(char const * const)
0x18008efba  mov     [rsp+68h+ppszThreadDescription], 0
0x18008efc3  call    cs:__imp_GetCurrentThread
0x18008efc9  mov     rcx, rax; hThread
0x18008efcc  lea     rdx, [rsp+68h+ppszThreadDescription]; ppszThreadDescription
0x18008efd1  call    cs:__imp_GetThreadDescription
0x18008efd7  test    eax, eax
0x18008efd9  js      short loc_18008EFF1
0x18008efdb  mov     rcx, [rdi]; hMem
0x18008efde  mov     rax, [rsp+68h+ppszThreadDescription]
0x18008efe3  mov     [rdi], rax
0x18008efe6  test    rcx, rcx
0x18008efe9  jz      short loc_18008EFF1
0x18008efeb  call    cs:__imp_LocalFree
0x18008eff1  mov     rcx, [rdi]; String1
0x18008eff4  test    rcx, rcx
0x18008eff7  jz      short loc_18008F052
0x18008eff9  lea     rdx, aMain; "main"
0x18008f000  call    wcscmp_0
0x18008f005  test    eax, eax
0x18008f007  jz      short loc_18008F052
0x18008f009  lea     rax, aLuaModule; "<lua_module>"
0x18008f010  test    rsi, rsi
0x18008f013  cmovz   rsi, rax
0x18008f017  mov     rdx, rsi
0x18008f01a  lea     rcx, [rsp+68h+lpThreadDescription]
0x18008f01f  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18008f024  lea     rbx, [rsp+68h+lpThreadDescription]
0x18008f029  cmp     [rsp+68h+var_20], 7
0x18008f02f  cmova   rbx, [rsp+68h+lpThreadDescription]
0x18008f035  call    cs:__imp_GetCurrentThread
0x18008f03b  mov     rdx, rbx; lpThreadDescription
0x18008f03e  mov     rcx, rax; hThread
0x18008f041  call    cs:__imp_SetThreadDescription
0x18008f047  lea     rcx, [rsp+68h+lpThreadDescription]
0x18008f04c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008f051  nop
0x18008f052  mov     rax, rdi
0x18008f055  mov     rcx, [rsp+68h+var_18]
0x18008f05a  xor     rcx, rsp; StackCookie
0x18008f05d  call    __security_check_cookie
0x18008f062  lea     r11, [rsp+68h+var_8]
0x18008f067  mov     rbx, [r11+20h]
0x18008f06b  mov     rsi, [r11+28h]
0x18008f06f  mov     rsp, r11
0x18008f072  pop     rdi
0x18008f073  retn
```
