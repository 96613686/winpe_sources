# GetTasksFolder(ushort * *)

- ea: `0x18002abc4`
- end: `0x18002adc6`
- name: `?GetTasksFolder@@YAJPEAPEAG@Z`
- size: `514`
- prototype: `signed int __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002ae64`
- `0x18002c5d4`

## callees

- `0x180003ef0`
- `0x180007488`
- `0x1800074c8`
- `0x18002abc4`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ac8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002acf7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ac8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002acf7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ac80`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ac80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ac1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002acb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ac1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002acb4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ace7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ace7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ad34`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ad86`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ad34`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002ad86`

## string_xrefs

- `0x18002ac14`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x18002aca6`: `SOFTWARE\Microsoft\SchedulingAgent`
- `0x18002ac69`: `TasksFolder`
- `0x18002acca`: `TasksFolder`
- `0x18002ac43`: `%WinDir%\Tasks`

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
0x18002abc4  mov     [rsp-8+arg_8], rbx
0x18002abc9  mov     [rsp-8+arg_10], rsi
0x18002abce  push    rbp
0x18002abcf  push    rdi
0x18002abd0  push    r14
0x18002abd2  lea     rbp, [rsp-160h]
0x18002abda  sub     rsp, 260h
0x18002abe1  mov     rax, cs:__security_cookie
0x18002abe8  xor     rax, rsp
0x18002abeb  mov     [rbp+170h+var_20], rax
0x18002abf2  mov     rsi, rcx
0x18002abf5  lea     rax, [rsp+270h+hKey]
0x18002abfa  xor     r14d, r14d
0x18002abfd  mov     [rsp+270h+phkResult], rax; phkResult
0x18002ac02  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ac09  mov     [rsp+270h+hKey], r14
0x18002ac0e  mov     r9d, 20019h; samDesired
0x18002ac14  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x18002ac1b  xor     r8d, r8d; ulOptions
0x18002ac1e  call    cs:__imp_RegOpenKeyExW
0x18002ac24  mov     ebx, 208h
0x18002ac29  mov     word ptr [rsp+270h+Data], r14w
0x18002ac2f  mov     r8d, ebx; Size
0x18002ac32  lea     rcx, [rsp+270h+var_22E]; void *
0x18002ac37  xor     edx, edx; Val
0x18002ac39  call    memset_0
0x18002ac3e  mov     rcx, [rsp+270h+hKey]; hKey
0x18002ac43  lea     rdi, aWindirTasks; "%WinDir%\\Tasks"
0x18002ac4a  mov     [rbp+170h+var_28], r14w
0x18002ac52  test    rcx, rcx
0x18002ac55  jz      loc_18002ACFD
0x18002ac5b  lea     rax, [rsp+270h+cbData]
0x18002ac60  mov     [rsp+270h+cbData], ebx
0x18002ac64  mov     [rsp+270h+lpcbData], rax; lpcbData
0x18002ac69  lea     rdx, aTasksfolder; "TasksFolder"
0x18002ac70  lea     rax, [rsp+270h+Data]
0x18002ac75  xor     r9d, r9d; lpType
0x18002ac78  xor     r8d, r8d; lpReserved
0x18002ac7b  mov     [rsp+270h+phkResult], rax; lpData
0x18002ac80  call    cs:__imp_RegQueryValueExW
0x18002ac86  test    eax, eax
0x18002ac88  jz      short loc_18002ACED
0x18002ac8a  mov     rcx, [rsp+270h+hKey]; hKey
0x18002ac8f  call    cs:__imp_RegCloseKey
0x18002ac95  lea     rax, [rsp+270h+hKey]
0x18002ac9a  xor     r8d, r8d; ulOptions
0x18002ac9d  lea     r9d, [r14+2]; samDesired
0x18002aca1  mov     [rsp+270h+phkResult], rax; phkResult
0x18002aca6  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x18002acad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002acb4  call    cs:__imp_RegOpenKeyExW
0x18002acba  test    eax, eax
0x18002acbc  jz      short loc_18002ACC5
0x18002acbe  mov     [rsp+270h+hKey], r14
0x18002acc3  jmp     short loc_18002ACFD
0x18002acc5  mov     rcx, [rsp+270h+hKey]; hKey
0x18002acca  lea     rdx, aTasksfolder; "TasksFolder"
0x18002acd1  mov     dword ptr [rsp+270h+lpcbData], 1Eh; cbData
0x18002acd9  mov     r9d, 2; dwType
0x18002acdf  xor     r8d, r8d; Reserved
0x18002ace2  mov     [rsp+270h+phkResult], rdi; lpData
0x18002ace7  call    cs:__imp_RegSetValueExW
0x18002aced  mov     rcx, [rsp+270h+hKey]; hKey
0x18002acf2  test    rcx, rcx
0x18002acf5  jz      short loc_18002ACFD
0x18002acf7  call    cs:__imp_RegCloseKey
0x18002acfd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002ad01  lea     rcx, [rsp+270h+Data]
0x18002ad06  mov     rax, rbx
0x18002ad09  inc     rax
0x18002ad0c  cmp     [rcx+rax*2], r14w
0x18002ad11  jnz     short loc_18002AD09
0x18002ad13  test    rax, rax
0x18002ad16  jnz     short loc_18002AD2A
0x18002ad18  mov     r8, rdi; unsigned __int16 *
0x18002ad1b  lea     rcx, [rsp+270h+Data]; unsigned __int16 *
0x18002ad20  mov     edx, 105h; unsigned __int64
0x18002ad25  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ad2a  xor     r8d, r8d; nSize
0x18002ad2d  lea     rcx, [rsp+270h+Data]; lpSrc
0x18002ad32  xor     edx, edx; lpDst
0x18002ad34  call    cs:__imp_ExpandEnvironmentStringsW
0x18002ad3a  mov     edi, eax
0x18002ad3c  test    eax, eax
0x18002ad3e  jnz     short loc_18002AD54
0x18002ad40  call    cs:__imp_GetLastError
0x18002ad46  test    eax, eax
0x18002ad48  jle     short loc_18002AD9F
0x18002ad4a  movzx   eax, ax
0x18002ad4d  or      eax, 80070000h
0x18002ad52  jmp     short loc_18002AD9F
0x18002ad54  mov     eax, 2
0x18002ad59  mul     rdi
0x18002ad5c  cmovb   rax, rbx
0x18002ad60  mov     rcx, rax; Size
0x18002ad63  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ad68  mov     rbx, rax
0x18002ad6b  test    rax, rax
0x18002ad6e  jnz     short loc_18002AD77
0x18002ad70  mov     eax, 8007000Eh
0x18002ad75  jmp     short loc_18002AD9F
0x18002ad77  mov     r8d, edi; nSize
0x18002ad7a  mov     [rax], r14w
0x18002ad7e  mov     rdx, rbx; lpDst
0x18002ad81  lea     rcx, [rsp+270h+Data]; lpSrc
0x18002ad86  call    cs:__imp_ExpandEnvironmentStringsW
0x18002ad8c  test    eax, eax
0x18002ad8e  jnz     short loc_18002AD9A
0x18002ad90  mov     rcx, rbx; Block
0x18002ad93  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ad98  jmp     short loc_18002AD40
0x18002ad9a  mov     [rsi], rbx
0x18002ad9d  xor     eax, eax
0x18002ad9f  mov     rcx, [rbp+170h+var_20]
0x18002ada6  xor     rcx, rsp; StackCookie
0x18002ada9  call    __security_check_cookie
0x18002adae  lea     r11, [rsp+270h+var_10]
0x18002adb6  mov     rbx, [r11+28h]
0x18002adba  mov     rsi, [r11+30h]
0x18002adbe  mov     rsp, r11
0x18002adc1  pop     r14
0x18002adc3  pop     rdi
0x18002adc4  pop     rbp
0x18002adc5  retn
```
