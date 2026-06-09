# GetTasksFolder(ushort * *)

- ea: `0x18002c720`
- end: `0x18002c959`
- name: `?GetTasksFolder@@YAJPEAPEAG@Z`
- size: `569`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002ca08`
- `0x18002e3cc`

## callees

- `0x1800040c0`
- `0x180007948`
- `0x180007988`
- `0x18002c720`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c8c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c7f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c871`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c7f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c871`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c7e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c7e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c77a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c822`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c77a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c822`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c85b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c85b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c8b4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c912`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c8b4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002c912`

## string_xrefs

- `0x18002c770`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x18002c814`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x18002c7cb`: `TasksFolder`
- `0x18002c83e`: `TasksFolder`
- `0x18002c7a5`: `%WinDir%\Tasks`

## pseudocode

```c
signed int __fastcall GetTasksFolder(unsigned __int16 **a1)
{
  __int64 v2; // rax
  DWORD v3; // eax
  DWORD v4; // edi
  signed int result; // eax
  WCHAR *v6; // rax
  unsigned __int16 *v7; // rbx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[518]; // [rsp+42h] [rbp-BEh] BYREF
  __int16 v12; // [rsp+248h] [rbp+148h]

  hKey = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SchedulingAgent", 0, 0x20019u, &hKey);
  *(_WORD *)Data = 0;
  memset_0(v11, 0, 0x208u);
  v12 = 0;
  if ( hKey )
  {
    cbData = 520;
    if ( RegQueryValueExW(hKey, L"TasksFolder", 0, 0, Data, &cbData) )
    {
      RegCloseKey(hKey);
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SchedulingAgent", 0, 2u, &hKey) )
      {
        hKey = 0;
        goto LABEL_8;
      }
      RegSetValueExW(hKey, L"TasksFolder", 0, 2u, L"%WinDir%\\Tasks", 0x1Eu);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
LABEL_8:
  v2 = -1;
  do
    ++v2;
  while ( *(_WORD *)&Data[2 * v2] );
  if ( !v2 )
    StringCchCopyW((unsigned __int16 *)Data, 0x105u, L"%WinDir%\\Tasks");
  v3 = ExpandEnvironmentStringsW((LPCWSTR)Data, 0, 0);
  v4 = v3;
  if ( v3 )
  {
    v6 = (WCHAR *)operator new(saturated_mul(v3, 2u));
    v7 = v6;
    if ( !v6 )
      return -2147024882;
    *v6 = 0;
    if ( ExpandEnvironmentStringsW((LPCWSTR)Data, v6, v4) )
    {
      *a1 = v7;
      return 0;
    }
    operator delete(v7);
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18002c720  mov     [rsp-8+arg_8], rbx
0x18002c725  mov     [rsp-8+arg_10], rsi
0x18002c72a  push    rbp
0x18002c72b  push    rdi
0x18002c72c  push    r14
0x18002c72e  lea     rbp, [rsp-160h]
0x18002c736  sub     rsp, 260h
0x18002c73d  mov     rax, cs:__security_cookie
0x18002c744  xor     rax, rsp
0x18002c747  mov     [rbp+170h+var_20], rax
0x18002c74e  mov     rsi, rcx
0x18002c751  lea     rax, [rsp+270h+hKey]
0x18002c756  xor     r14d, r14d
0x18002c759  mov     [rsp+270h+phkResult], rax; phkResult
0x18002c75e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c765  mov     [rsp+270h+hKey], r14
0x18002c76a  mov     r9d, 20019h; samDesired
0x18002c770  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x18002c777  xor     r8d, r8d; ulOptions
0x18002c77a  call    cs:__imp_RegOpenKeyExW
0x18002c781  nop     dword ptr [rax+rax+00h]
0x18002c786  mov     ebx, 208h
0x18002c78b  mov     word ptr [rsp+270h+Data], r14w
0x18002c791  mov     r8d, ebx; Size
0x18002c794  lea     rcx, [rsp+270h+var_22E]; void *
0x18002c799  xor     edx, edx; Val
0x18002c79b  call    memset_0
0x18002c7a0  mov     rcx, [rsp+270h+hKey]; hKey
0x18002c7a5  lea     rdi, aWindirTasks; "%WinDir%\\Tasks"
0x18002c7ac  mov     [rbp+170h+var_28], r14w
0x18002c7b4  test    rcx, rcx
0x18002c7b7  jz      loc_18002C87D
0x18002c7bd  lea     rax, [rsp+270h+cbData]
0x18002c7c2  mov     [rsp+270h+cbData], ebx
0x18002c7c6  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18002c7cb  lea     rdx, aTasksfolder; "TasksFolder"
0x18002c7d2  lea     rax, [rsp+270h+Data]
0x18002c7d7  xor     r9d, r9d; lpType
0x18002c7da  xor     r8d, r8d; lpReserved
0x18002c7dd  mov     [rsp+270h+phkResult], rax; lpData
0x18002c7e2  call    cs:__imp_RegQueryValueExW
0x18002c7e9  nop     dword ptr [rax+rax+00h]
0x18002c7ee  test    eax, eax
0x18002c7f0  jz      short loc_18002C867
0x18002c7f2  mov     rcx, [rsp+270h+hKey]; hKey
0x18002c7f7  call    cs:__imp_RegCloseKey
0x18002c7fe  nop     dword ptr [rax+rax+00h]
0x18002c803  lea     rax, [rsp+270h+hKey]
0x18002c808  xor     r8d, r8d; ulOptions
0x18002c80b  lea     r9d, [r14+2]; samDesired
0x18002c80f  mov     [rsp+270h+phkResult], rax; phkResult
0x18002c814  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x18002c81b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c822  call    cs:__imp_RegOpenKeyExW
0x18002c829  nop     dword ptr [rax+rax+00h]
0x18002c82e  test    eax, eax
0x18002c830  jz      short loc_18002C839
0x18002c832  mov     [rsp+270h+hKey], r14
0x18002c837  jmp     short loc_18002C87D
0x18002c839  mov     rcx, [rsp+270h+hKey]; hKey
0x18002c83e  lea     rdx, aTasksfolder; "TasksFolder"
0x18002c845  mov     dword ptr [rsp+270h+lpcbData], 1Eh; cbData
0x18002c84d  mov     r9d, 2; dwType
0x18002c853  xor     r8d, r8d; Reserved
0x18002c856  mov     [rsp+270h+phkResult], rdi; lpData
0x18002c85b  call    cs:__imp_RegSetValueExW
0x18002c862  nop     dword ptr [rax+rax+00h]
0x18002c867  mov     rcx, [rsp+270h+hKey]; hKey
0x18002c86c  test    rcx, rcx
0x18002c86f  jz      short loc_18002C87D
0x18002c871  call    cs:__imp_RegCloseKey
0x18002c878  nop     dword ptr [rax+rax+00h]
0x18002c87d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002c881  lea     rcx, [rsp+270h+Data]
0x18002c886  mov     rax, rbx
0x18002c889  inc     rax
0x18002c88c  cmp     [rcx+rax*2], r14w
0x18002c891  jnz     short loc_18002C889
0x18002c893  test    rax, rax
0x18002c896  jnz     short loc_18002C8AA
0x18002c898  mov     r8, rdi; unsigned __int16 *
0x18002c89b  lea     rcx, [rsp+270h+Data]; unsigned __int16 *
0x18002c8a0  mov     edx, 105h; unsigned __int64
0x18002c8a5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c8aa  xor     r8d, r8d; nSize
0x18002c8ad  lea     rcx, [rsp+270h+Data]; lpSrc
0x18002c8b2  xor     edx, edx; lpDst
0x18002c8b4  call    cs:__imp_ExpandEnvironmentStringsW
0x18002c8bb  nop     dword ptr [rax+rax+00h]
0x18002c8c0  mov     edi, eax
0x18002c8c2  test    eax, eax
0x18002c8c4  jnz     short loc_18002C8E0
0x18002c8c6  call    cs:__imp_GetLastError
0x18002c8cd  nop     dword ptr [rax+rax+00h]
0x18002c8d2  test    eax, eax
0x18002c8d4  jle     short loc_18002C931
0x18002c8d6  movzx   eax, ax
0x18002c8d9  or      eax, 80070000h
0x18002c8de  jmp     short loc_18002C931
0x18002c8e0  mov     eax, 2
0x18002c8e5  mul     rdi
0x18002c8e8  cmovb   rax, rbx
0x18002c8ec  mov     rcx, rax; Size
0x18002c8ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c8f4  mov     rbx, rax
0x18002c8f7  test    rax, rax
0x18002c8fa  jnz     short loc_18002C903
0x18002c8fc  mov     eax, 8007000Eh
0x18002c901  jmp     short loc_18002C931
0x18002c903  mov     r8d, edi; nSize
0x18002c906  mov     [rax], r14w
0x18002c90a  mov     rdx, rbx; lpDst
0x18002c90d  lea     rcx, [rsp+270h+Data]; lpSrc
0x18002c912  call    cs:__imp_ExpandEnvironmentStringsW
0x18002c919  nop     dword ptr [rax+rax+00h]
0x18002c91e  test    eax, eax
0x18002c920  jnz     short loc_18002C92C
0x18002c922  mov     rcx, rbx; Block
0x18002c925  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c92a  jmp     short loc_18002C8C6
0x18002c92c  mov     [rsi], rbx
0x18002c92f  xor     eax, eax
0x18002c931  mov     rcx, [rbp+170h+var_20]
0x18002c938  xor     rcx, rsp; StackCookie
0x18002c93b  call    __security_check_cookie
0x18002c940  lea     r11, [rsp+270h+var_10]
0x18002c948  mov     rbx, [r11+28h]
0x18002c94c  mov     rsi, [r11+30h]
0x18002c950  mov     rsp, r11
0x18002c953  pop     r14
0x18002c955  pop     rdi
0x18002c956  pop     rbp
0x18002c957  retn
```
