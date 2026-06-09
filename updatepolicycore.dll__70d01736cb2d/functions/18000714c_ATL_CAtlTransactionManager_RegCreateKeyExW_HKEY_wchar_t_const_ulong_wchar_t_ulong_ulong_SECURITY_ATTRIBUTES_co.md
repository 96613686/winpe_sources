# ATL::CAtlTransactionManager::RegCreateKeyExW(HKEY__ *,wchar_t const *,ulong,wchar_t *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)

- ea: `0x18000714c`
- end: `0x180007256`
- name: `?RegCreateKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEB_WKPEA_WKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU3@PEAK@Z`
- size: `266`
- prototype: `int(ATL::CAtlTransactionManager *__hidden this, HKEY, const wchar_t *, unsigned int, wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *const, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007ee0`

## callees

- `0x18000714c`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007175`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007175`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000718e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000718e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007239`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007239`

## string_xrefs

- `0x180007184`: `RegCreateKeyTransactedW`
- `0x18000716e`: `Advapi32.dll`

## pseudocode

```c
LSTATUS __fastcall ATL::CAtlTransactionManager::RegCreateKeyExW(
        ATL::CAtlTransactionManager *this,
        HKEY a2,
        const wchar_t *a3,
        __int64 a4,
        wchar_t *a5,
        unsigned int a6,
        unsigned int a7,
        struct _SECURITY_ATTRIBUTES *const a8,
        HKEY *phkResult,
        unsigned int *lpdwDisposition)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  if ( *(_QWORD *)this )
  {
    ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "RegCreateKeyTransactedW");
      if ( ProcAddress )
        return ((__int64 (__fastcall *)(HKEY, const wchar_t *, _QWORD, _QWORD, _DWORD, int, _QWORD, HKEY *, unsigned int *, _QWORD, _QWORD))ProcAddress)(
                 a2,
                 a3,
                 0,
                 0,
                 0,
                 131103,
                 0,
                 phkResult,
                 lpdwDisposition,
                 *(_QWORD *)this,
                 0);
    }
  }
  else if ( *((_DWORD *)this + 2) )
  {
    return RegCreateKeyExW(a2, a3, 0, 0, 0, 0x2001Fu, 0, phkResult, lpdwDisposition);
  }
  return 1;
}

```

## disassembly

```asm
0x18000714c  mov     [rsp+arg_0], rbx
0x180007151  mov     [rsp+arg_8], rsi
0x180007156  push    rdi
0x180007157  sub     rsp, 60h
0x18000715b  cmp     qword ptr [rcx], 0
0x18000715f  mov     rdi, r8
0x180007162  mov     rsi, rdx
0x180007165  mov     rbx, rcx
0x180007168  jz      loc_1800071F4
0x18000716e  lea     rcx, aAdvapi32Dll; "Advapi32.dll"
0x180007175  call    cs:__imp_GetModuleHandleW
0x18000717b  test    rax, rax
0x18000717e  jz      loc_180007241
0x180007184  lea     rdx, aRegcreatekeytr; "RegCreateKeyTransactedW"
0x18000718b  mov     rcx, rax; hModule
0x18000718e  call    cs:__imp_GetProcAddress
0x180007194  test    rax, rax
0x180007197  jz      loc_180007241
0x18000719d  mov     rcx, [rbx]
0x1800071a0  xor     r9d, r9d
0x1800071a3  mov     [rsp+68h+var_18], 0
0x1800071ac  xor     r8d, r8d
0x1800071af  mov     [rsp+68h+var_20], rcx
0x1800071b4  mov     rdx, rdi
0x1800071b7  mov     rcx, [rsp+68h+arg_48]
0x1800071bf  mov     [rsp+68h+lpdwDisposition], rcx
0x1800071c4  mov     rcx, [rsp+68h+arg_40]
0x1800071cc  mov     [rsp+68h+phkResult], rcx
0x1800071d1  mov     rcx, rsi
0x1800071d4  mov     [rsp+68h+lpSecurityAttributes], 0
0x1800071dd  mov     [rsp+68h+samDesired], 2001Fh
0x1800071e5  mov     [rsp+68h+dwOptions], 0
0x1800071ed  call    _guard_dispatch_icall
0x1800071f2  jmp     short loc_180007246
0x1800071f4  cmp     dword ptr [rcx+8], 0
0x1800071f8  jz      short loc_180007241
0x1800071fa  mov     rax, [rsp+68h+arg_48]
0x180007202  xor     r9d, r9d; lpClass
0x180007205  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x18000720a  xor     r8d, r8d; Reserved
0x18000720d  mov     rax, [rsp+68h+arg_40]
0x180007215  mov     rdx, rdi; lpSubKey
0x180007218  mov     [rsp+68h+phkResult], rax; phkResult
0x18000721d  mov     rcx, rsi; hKey
0x180007220  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180007229  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x180007231  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180007239  call    cs:__imp_RegCreateKeyExW
0x18000723f  jmp     short loc_180007246
0x180007241  mov     eax, 1
0x180007246  mov     rbx, [rsp+68h+arg_0]
0x18000724b  mov     rsi, [rsp+68h+arg_8]
0x180007250  add     rsp, 60h
0x180007254  pop     rdi
0x180007255  retn
```
