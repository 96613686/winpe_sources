# ReadFileLogConfig

- ea: `0x18000ce30`
- end: `0x18000d45e`
- name: `ReadFileLogConfig`
- size: `1582`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000c91c`
- `0x18000ca10`

## callees

- `0x18000c574`
- `0x18000ce30`
- `0x18002a340`
- `0x18003d270`
- `0x18003d6e0`
- `0x18003dd2c`
- `0x18004e760`
- `0x18004ed6c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18000d27b`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18000d30f`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18000d27b`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x18000d30f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000d2a7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000d2d0`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000d2a7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000d2d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d439`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d44d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d439`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d44d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ceab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d113`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d22f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d397`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ceab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d113`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d22f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cf18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cf18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d06d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d06d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cf5d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cfa2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cff5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d046`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d1f5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d35b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cf5d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cfa2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cff5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d046`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d1f5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d35b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000d3c4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000d3c4`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000cee3`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18000cee3`

## string_xrefs

- `0x18000cedc`: `W32TimeConfig`
- `0x18000ced5`: `System\CurrentControlSet\Services\W32Time\Config`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall ReadFileLogConfig(_QWORD *a1)
{
  char *v2; // r14
  unsigned __int16 *v3; // rsi
  char *pvData; // rbx
  signed int v5; // edi
  bool v7; // zf
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  int ValueW; // eax
  LSTATUS v11; // eax
  unsigned __int16 *v12; // rax
  wchar_t *i; // rcx
  unsigned int v14; // eax
  unsigned int v15; // edi
  unsigned int v16; // eax
  size_t v17; // rax
  unsigned __int64 v18; // r8
  WCHAR *v19; // rax
  unsigned __int64 v20; // rdx
  const unsigned __int16 *v21; // r8
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pdwType; // [rsp+44h] [rbp-BCh] BYREF
  wchar_t *EndPtr; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Src; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[526]; // [rsp+62h] [rbp-9Eh] BYREF
  WCHAR SubKey; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v29[526]; // [rsp+272h] [rbp+172h] BYREF

  pcbData = 0;
  pdwType = 0;
  EndPtr = 0;
  hkey = 0;
  v2 = 0;
  v3 = 0;
  SubKey = 0;
  memset_0(v29, 0, 0x206u);
  *a1 = 0;
  pvData = (char *)LocalAlloc(0x40u, 0x30u);
  if ( pvData )
  {
    if ( (unsigned int)GetPersistedRegistryLocationW(
                         L"W32TimeConfig",
                         L"System\\CurrentControlSet\\Services\\W32Time\\Config",
                         &SubKey,
                         520,
                         0)
      || RegOpenKeyExW(HKEY_LOCAL_MACHINE, &SubKey, 0, 0x20019u, &hkey) )
    {
LABEL_8:
      v5 = 0;
      *a1 = pvData;
      v3 = 0;
      goto LABEL_9;
    }
    *((_DWORD *)pvData + 10) = 0;
    if ( RegGetValueW(hkey, 0, L"FileLogEntries", 0xFFFFu, &pdwType, 0, &pcbData) || pdwType != 1 )
    {
LABEL_5:
      *((_DWORD *)pvData + 11) = 0;
      if ( !RegGetValueW(hkey, 0, L"FileLogName", 0xFFFFu, &pdwType, 0, &pcbData) && pdwType == 1 )
      {
        Src = 0;
        memset_0(v27, 0, 0x206u);
        if ( pcbData > 0x208 )
        {
          v5 = -2147024882;
LABEL_19:
          v3 = 0;
LABEL_20:
          FreeFileLogConfig(pvData);
          goto LABEL_9;
        }
        ValueW = RegGetValueW(hkey, 0, L"FileLogName", 0xFFFFu, &pdwType, &Src, &pcbData);
        v5 = ValueW;
        if ( ValueW )
        {
          if ( ValueW <= 0 )
            goto LABEL_19;
        }
        else
        {
          v18 = (pcbData & 0xFFFFFFFE) - 2LL;
          if ( v18 >= 0x208 )
            _report_rangecheckfailure();
          *(_WORD *)&v27[v18 - 2] = 0;
          v19 = (WCHAR *)LocalAlloc(0x40u, 0x208u);
          *((_QWORD *)pvData + 3) = v19;
          if ( !v19 )
          {
            v5 = -2147024882;
            goto LABEL_19;
          }
          if ( ExpandEnvironmentStringsW(&Src, v19, 0x104u) )
          {
            v7 = _pwszFileNameSuffix == 0;
            *(_WORD *)(*((_QWORD *)pvData + 3) + 518LL) = 0;
            if ( !v7 )
              StringCbCatW(*((unsigned __int16 **)pvData + 3), v20, v21);
            *((_DWORD *)pvData + 11) = 2;
            goto LABEL_6;
          }
          ValueW = GetLastError();
          v5 = ValueW;
          if ( ValueW <= 0 )
            goto LABEL_19;
        }
        v5 = (unsigned __int16)ValueW | 0x80070000;
        goto LABEL_19;
      }
LABEL_6:
      *((_DWORD *)pvData + 8) = 1;
      *(_DWORD *)pvData = 0;
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"FileLogFlags", 0xFFFFu, &pdwType, pvData, &pcbData) && pdwType == 4 )
        *((_DWORD *)pvData + 8) = 2;
      *((_DWORD *)pvData + 9) = 0;
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"FileLogSize", 0xFFFFu, &pdwType, pvData + 4, &pcbData) && pdwType == 4 )
        *((_DWORD *)pvData + 9) = 2;
      goto LABEL_8;
    }
    v2 = (char *)LocalAlloc(0x40u, pcbData);
    if ( !v2 )
    {
      v5 = -2147024882;
      FreeFileLogConfig(pvData);
      goto LABEL_9;
    }
    v11 = RegGetValueW(hkey, 0, L"FileLogEntries", 0xFFFFu, &pdwType, v2, &pcbData);
    v5 = v11;
    if ( !v11 )
    {
      v8 = -1;
      *(_WORD *)&v2[2 * ((unsigned __int64)pcbData >> 1) - 2] = 0;
      do
        v7 = *(_WORD *)&v2[2 * v8++ + 2] == 0;
      while ( !v7 );
      v9 = 2LL * (unsigned int)(v8 + 1);
      if ( v9 > 0xFFFFFFFF )
      {
        pcbData = -1;
        v5 = -2147024362;
        FreeFileLogConfig(pvData);
        goto LABEL_9;
      }
      pcbData = 2 * (v8 + 1);
      v12 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)v9);
      v3 = v12;
      if ( !v12 )
      {
        v5 = -2147024882;
        goto LABEL_20;
      }
      v5 = StringCbCopyW(v12, pcbData, (const unsigned __int16 *)v2);
      if ( v5 < 0 )
        goto LABEL_20;
      *((_QWORD *)pvData + 2) = v3;
      *((_DWORD *)pvData + 10) = 2;
      for ( i = (wchar_t *)&v2[2 * wcscspn((const wchar_t *)v2, L"0123456789")]; ; i = &EndPtr[v17] )
      {
        EndPtr = i;
        if ( !*i )
          break;
        v14 = wcstoul(i, &EndPtr, 0);
        v15 = v14;
        if ( *EndPtr == 45 && (++EndPtr, v14 = wcstoul(EndPtr, &EndPtr, 0), v14 < v15) )
          v16 = 1;
        else
          v16 = v14 - v15 + 1;
        v5 = AddRegionToLogEntryRangeChain((struct LogEntryRange **)pvData + 1, v15, v16);
        if ( v5 < 0 )
          goto LABEL_19;
        v17 = wcscspn(EndPtr, L"0123456789");
      }
      goto LABEL_5;
    }
    if ( v11 <= 0 )
      goto LABEL_20;
    v5 = (unsigned __int16)v11 | 0x80070000;
    FreeFileLogConfig(pvData);
  }
  else
  {
    v5 = -2147024882;
  }
LABEL_9:
  if ( hkey )
    RegCloseKey(hkey);
  if ( v2 )
    LocalFree(v2);
  if ( v3 )
    LocalFree(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ce30  mov     [rsp-8+arg_8], rbx
0x18000ce35  mov     [rsp-8+arg_10], rsi
0x18000ce3a  push    rbp
0x18000ce3b  push    rdi
0x18000ce3c  push    r12
0x18000ce3e  push    r14
0x18000ce40  push    r15
0x18000ce42  lea     rbp, [rsp-390h]
0x18000ce4a  sub     rsp, 490h
0x18000ce51  mov     rax, cs:__security_cookie
0x18000ce58  xor     rax, rsp
0x18000ce5b  mov     [rbp+3B0h+var_30], rax
0x18000ce62  xor     r12d, r12d
0x18000ce65  mov     r15, rcx
0x18000ce68  lea     rcx, [rbp+3B0h+var_23E]; void *
0x18000ce6f  mov     [rsp+4B0h+var_470], r12d
0x18000ce74  xor     edx, edx; Val
0x18000ce76  mov     [rsp+4B0h+pdwType], r12d
0x18000ce7b  mov     r8d, 206h; Size
0x18000ce81  mov     [rsp+4B0h+EndPtr], r12
0x18000ce86  mov     [rsp+4B0h+hkey], r12
0x18000ce8b  mov     r14d, r12d
0x18000ce8e  mov     esi, r12d
0x18000ce91  mov     [rbp+3B0h+SubKey], r12w
0x18000ce99  call    memset_0
0x18000ce9e  mov     edx, 30h ; '0'; uBytes
0x18000cea3  mov     [r15], r12
0x18000cea6  mov     ecx, 40h ; '@'; uFlags
0x18000ceab  call    cs:__imp_LocalAlloc
0x18000ceb2  nop     dword ptr [rax+rax+00h]
0x18000ceb7  mov     rbx, rax
0x18000ceba  test    rax, rax
0x18000cebd  jz      loc_18000D1BE
0x18000cec3  mov     r9d, 208h
0x18000cec9  mov     [rsp+4B0h+phkResult], r12
0x18000cece  lea     r8, [rbp+3B0h+SubKey]
0x18000ced5  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\W3"...
0x18000cedc  lea     rcx, aW32timeconfig; "W32TimeConfig"
0x18000cee3  call    cs:__imp_GetPersistedRegistryLocationW
0x18000ceea  nop     dword ptr [rax+rax+00h]
0x18000ceef  test    eax, eax
0x18000cef1  jnz     loc_18000D05A
0x18000cef7  lea     rax, [rsp+4B0h+hkey]
0x18000cefc  mov     r9d, 20019h; samDesired
0x18000cf02  xor     r8d, r8d; ulOptions
0x18000cf05  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000cf0a  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x18000cf11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000cf18  call    cs:__imp_RegOpenKeyExW
0x18000cf1f  nop     dword ptr [rax+rax+00h]
0x18000cf24  test    eax, eax
0x18000cf26  jnz     loc_18000D05A
0x18000cf2c  lea     rax, [rsp+4B0h+var_470]
0x18000cf31  mov     [rbx+28h], r12d
0x18000cf35  mov     rcx, [rsp+4B0h+hkey]; hkey
0x18000cf3a  lea     r8, aFilelogentries; "FileLogEntries"
0x18000cf41  mov     [rsp+4B0h+pcbData], rax; pcbData
0x18000cf46  mov     r9d, 0FFFFh; dwFlags
0x18000cf4c  lea     rax, [rsp+4B0h+pdwType]
0x18000cf51  mov     [rsp+4B0h+pvData], r12; pvData
0x18000cf56  xor     edx, edx; lpSubKey
0x18000cf58  mov     [rsp+4B0h+phkResult], rax; pdwType
0x18000cf5d  call    cs:__imp_RegGetValueW
0x18000cf64  nop     dword ptr [rax+rax+00h]
0x18000cf69  test    eax, eax
0x18000cf6b  jz      loc_18000D0FF
0x18000cf71  lea     rax, [rsp+4B0h+var_470]
0x18000cf76  mov     [rbx+2Ch], r12d
0x18000cf7a  mov     rcx, [rsp+4B0h+hkey]; hkey
0x18000cf7f  lea     r8, aFilelogname; "FileLogName"
0x18000cf86  mov     [rsp+4B0h+pcbData], rax; pcbData
0x18000cf8b  mov     r9d, 0FFFFh; dwFlags
0x18000cf91  lea     rax, [rsp+4B0h+pdwType]
0x18000cf96  mov     [rsp+4B0h+pvData], r12; pvData
0x18000cf9b  xor     edx, edx; lpSubKey
0x18000cf9d  mov     [rsp+4B0h+phkResult], rax; pdwType
0x18000cfa2  call    cs:__imp_RegGetValueW
0x18000cfa9  nop     dword ptr [rax+rax+00h]
0x18000cfae  test    eax, eax
0x18000cfb0  jz      loc_18000D0B9
0x18000cfb6  mov     dword ptr [rbx+20h], 1
0x18000cfbd  lea     rax, [rsp+4B0h+var_470]
0x18000cfc2  mov     [rsp+4B0h+pcbData], rax; pcbData
0x18000cfc7  lea     r8, aFilelogflags; "FileLogFlags"
0x18000cfce  mov     [rbx], r12d
0x18000cfd1  lea     rax, [rsp+4B0h+pdwType]
0x18000cfd6  mov     rcx, [rsp+4B0h+hkey]; hkey
0x18000cfdb  mov     r9d, 0FFFFh; dwFlags
0x18000cfe1  mov     [rsp+4B0h+pvData], rbx; pvData
0x18000cfe6  xor     edx, edx; lpSubKey
0x18000cfe8  mov     [rsp+4B0h+phkResult], rax; pdwType
0x18000cfed  mov     [rsp+4B0h+var_470], 4
0x18000cff5  call    cs:__imp_RegGetValueW
0x18000cffc  nop     dword ptr [rax+rax+00h]
0x18000d001  test    eax, eax
0x18000d003  jz      loc_18000D408
0x18000d009  mov     [rbx+24h], r12d
0x18000d00d  lea     rcx, [rsp+4B0h+var_470]
0x18000d012  mov     [rsp+4B0h+pcbData], rcx; pcbData
0x18000d017  lea     rax, [rbx+4]
0x18000d01b  mov     rcx, [rsp+4B0h+hkey]; hkey
0x18000d020  lea     r8, aFilelogsize; "FileLogSize"
0x18000d027  mov     [rsp+4B0h+pvData], rax; pvData
0x18000d02c  mov     r9d, 0FFFFh; dwFlags
0x18000d032  lea     rax, [rsp+4B0h+pdwType]
0x18000d037  mov     [rsp+4B0h+var_470], 4
0x18000d03f  xor     edx, edx; lpSubKey
0x18000d041  mov     [rsp+4B0h+phkResult], rax; pdwType
0x18000d046  call    cs:__imp_RegGetValueW
0x18000d04d  nop     dword ptr [rax+rax+00h]
0x18000d052  test    eax, eax
0x18000d054  jz      loc_18000D41F
0x18000d05a  mov     edi, r12d
0x18000d05d  mov     [r15], rbx
0x18000d060  mov     rsi, r12
0x18000d063  mov     rcx, [rsp+4B0h+hkey]; hKey
0x18000d068  test    rcx, rcx
0x18000d06b  jz      short loc_18000D079
0x18000d06d  call    cs:__imp_RegCloseKey
0x18000d074  nop     dword ptr [rax+rax+00h]
0x18000d079  test    r14, r14
0x18000d07c  jnz     loc_18000D436
0x18000d082  test    rsi, rsi
0x18000d085  jnz     loc_18000D44A
0x18000d08b  mov     eax, edi
0x18000d08d  mov     rcx, [rbp+3B0h+var_30]
0x18000d094  xor     rcx, rsp; StackCookie
0x18000d097  call    __security_check_cookie
0x18000d09c  lea     r11, [rsp+4B0h+var_20]
0x18000d0a4  mov     rbx, [r11+38h]
0x18000d0a8  mov     rsi, [r11+40h]
0x18000d0ac  mov     rsp, r11
0x18000d0af  pop     r15
0x18000d0b1  pop     r14
0x18000d0b3  pop     r12
0x18000d0b5  pop     rdi
0x18000d0b6  pop     rbp
0x18000d0b7  retn
0x18000d0b9  cmp     [rsp+4B0h+pdwType], 1
0x18000d0be  jnz     loc_18000CFB6
0x18000d0c4  xor     edx, edx; Val
0x18000d0c6  mov     [rsp+4B0h+Src], r12w
0x18000d0cc  mov     r8d, 206h; Size
0x18000d0d2  lea     rcx, [rsp+4B0h+var_44E]; void *
0x18000d0d7  call    memset_0
0x18000d0dc  cmp     [rsp+4B0h+var_470], 208h
0x18000d0e4  jbe     loc_18000D329
0x18000d0ea  mov     edi, 8007000Eh
0x18000d0ef  mov     rsi, r12
0x18000d0f2  mov     rcx, rbx
0x18000d0f5  call    FreeFileLogConfig
0x18000d0fa  jmp     loc_18000D063
0x18000d0ff  cmp     [rsp+4B0h+pdwType], 1
0x18000d104  jnz     loc_18000CF71
0x18000d10a  mov     edx, [rsp+4B0h+var_470]; uBytes
0x18000d10e  mov     ecx, 40h ; '@'; uFlags
0x18000d113  call    cs:__imp_LocalAlloc
0x18000d11a  nop     dword ptr [rax+rax+00h]
0x18000d11f  mov     r14, rax
0x18000d122  test    rax, rax
0x18000d125  jnz     loc_18000D1C8
0x18000d12b  mov     rcx, rbx
0x18000d12e  mov     edi, 8007000Eh
0x18000d133  call    FreeFileLogConfig
0x18000d138  jmp     loc_18000D063
0x18000d140  cmp     [r14+rax*2+2], si
0x18000d146  lea     rax, [rax+1]
0x18000d14a  jnz     short loc_18000D140
0x18000d14c  lea     ecx, [rax+1]
0x18000d14f  mov     eax, 0FFFFFFFFh
0x18000d154  add     rcx, rcx
0x18000d157  cmp     rcx, rax
0x18000d15a  jbe     loc_18000D224
0x18000d160  mov     rcx, rbx
0x18000d163  mov     [rsp+4B0h+var_470], eax
0x18000d167  mov     edi, 80070216h
0x18000d16c  call    FreeFileLogConfig
0x18000d171  jmp     loc_18000D063
0x18000d176  jle     loc_18000D0F2
0x18000d17c  movzx   edi, ax
0x18000d17f  mov     rcx, rbx
0x18000d182  or      edi, 80070000h
0x18000d188  call    FreeFileLogConfig
0x18000d18d  jmp     loc_18000D063
0x18000d192  jle     loc_18000D0EF
0x18000d198  movzx   edi, ax
0x18000d19b  or      edi, 80070000h
0x18000d1a1  jmp     loc_18000D0EF
0x18000d1a6  call    cs:__imp_GetLastError
0x18000d1ad  nop     dword ptr [rax+rax+00h]
0x18000d1b2  mov     edi, eax
0x18000d1b4  test    eax, eax
0x18000d1b6  jle     loc_18000D0EF
0x18000d1bc  jmp     short loc_18000D198
0x18000d1be  mov     edi, 8007000Eh
0x18000d1c3  jmp     loc_18000D063
0x18000d1c8  mov     rcx, [rsp+4B0h+hkey]; hkey
0x18000d1cd  lea     rax, [rsp+4B0h+var_470]
0x18000d1d2  mov     [rsp+4B0h+pcbData], rax; pcbData
0x18000d1d7  lea     r8, aFilelogentries; "FileLogEntries"
0x18000d1de  lea     rax, [rsp+4B0h+pdwType]
0x18000d1e3  mov     [rsp+4B0h+pvData], r14; pvData
0x18000d1e8  mov     r9d, 0FFFFh; dwFlags
0x18000d1ee  mov     [rsp+4B0h+phkResult], rax; pdwType
0x18000d1f3  xor     edx, edx; lpSubKey
0x18000d1f5  call    cs:__imp_RegGetValueW
0x18000d1fc  nop     dword ptr [rax+rax+00h]
0x18000d201  mov     edi, eax
0x18000d203  test    eax, eax
0x18000d205  jnz     loc_18000D176
0x18000d20b  mov     ecx, [rsp+4B0h+var_470]
0x18000d20f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000d216  shr     rcx, 1
0x18000d219  mov     [r14+rcx*2-2], r12w
0x18000d21f  jmp     loc_18000D140
0x18000d224  mov     edx, ecx; uBytes
0x18000d226  mov     ecx, 40h ; '@'; uFlags
0x18000d22b  mov     [rsp+4B0h+var_470], edx
0x18000d22f  call    cs:__imp_LocalAlloc
0x18000d236  nop     dword ptr [rax+rax+00h]
0x18000d23b  mov     rsi, rax
0x18000d23e  test    rax, rax
0x18000d241  jnz     short loc_18000D24D
0x18000d243  mov     edi, 8007000Eh
0x18000d248  jmp     loc_18000D0F2
0x18000d24d  mov     edx, [rsp+4B0h+var_470]; unsigned __int64
0x18000d251  mov     r8, r14; unsigned __int16 *
0x18000d254  mov     rcx, rsi; unsigned __int16 *
0x18000d257  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d25c  mov     edi, eax
0x18000d25e  test    eax, eax
0x18000d260  js      loc_18000D0F2
0x18000d266  lea     rdx, a0123456789; "0123456789"
0x18000d26d  mov     [rbx+10h], rsi
0x18000d271  mov     rcx, r14; String
0x18000d274  mov     dword ptr [rbx+28h], 2
0x18000d27b  call    cs:__imp_wcscspn
0x18000d282  nop     dword ptr [rax+rax+00h]
0x18000d287  mov     esi, 2Dh ; '-'
0x18000d28c  lea     rcx, [r14+rax*2]; String
0x18000d290  mov     [rsp+4B0h+EndPtr], rcx
0x18000d295  cmp     r12w, [rcx]
0x18000d299  jz      loc_18000CF71
0x18000d29f  xor     r8d, r8d; Radix
0x18000d2a2  lea     rdx, [rsp+4B0h+EndPtr]; EndPtr
0x18000d2a7  call    cs:__imp_wcstoul
0x18000d2ae  nop     dword ptr [rax+rax+00h]
0x18000d2b3  mov     rcx, [rsp+4B0h+EndPtr]
0x18000d2b8  mov     edi, eax
0x18000d2ba  cmp     si, [rcx]
0x18000d2bd  jnz     short loc_18000D2E7
0x18000d2bf  add     rcx, 2; String
0x18000d2c3  lea     rdx, [rsp+4B0h+EndPtr]; EndPtr
0x18000d2c8  xor     r8d, r8d; Radix
0x18000d2cb  mov     [rsp+4B0h+EndPtr], rcx
0x18000d2d0  call    cs:__imp_wcstoul
0x18000d2d7  nop     dword ptr [rax+rax+00h]
0x18000d2dc  cmp     eax, edi
0x18000d2de  jnb     short loc_18000D2E7
0x18000d2e0  mov     eax, 1
0x18000d2e5  jmp     short loc_18000D2EB
0x18000d2e7  sub     eax, edi
0x18000d2e9  inc     eax
0x18000d2eb  lea     rcx, [rbx+8]; struct LogEntryRange **
0x18000d2ef  mov     r8d, eax; unsigned int
0x18000d2f2  mov     edx, edi; unsigned int
0x18000d2f4  call    ?AddRegionToLogEntryRangeChain@@YAJPEAPEAULogEntryRange@@KK@Z; AddRegionToLogEntryRangeChain(LogEntryRange * *,ulong,ulong)
0x18000d2f9  mov     edi, eax
0x18000d2fb  test    eax, eax
0x18000d2fd  js      loc_18000D0EF
0x18000d303  mov     rcx, [rsp+4B0h+EndPtr]; String
0x18000d308  lea     rdx, a0123456789; "0123456789"
0x18000d30f  call    cs:__imp_wcscspn
0x18000d316  nop     dword ptr [rax+rax+00h]
0x18000d31b  mov     rcx, [rsp+4B0h+EndPtr]
0x18000d320  lea     rcx, [rcx+rax*2]
0x18000d324  jmp     loc_18000D290
0x18000d329  mov     rcx, [rsp+4B0h+hkey]; hkey
0x18000d32e  lea     rax, [rsp+4B0h+var_470]
0x18000d333  mov     [rsp+4B0h+pcbData], rax; pcbData
0x18000d338  lea     r8, aFilelogname; "FileLogName"
0x18000d33f  lea     rax, [rsp+4B0h+Src]
0x18000d344  mov     r9d, 0FFFFh; dwFlags
0x18000d34a  mov     [rsp+4B0h+pvData], rax; pvData
0x18000d34f  xor     edx, edx; lpSubKey
0x18000d351  lea     rax, [rsp+4B0h+pdwType]
0x18000d356  mov     [rsp+4B0h+phkResult], rax; pdwType
0x18000d35b  call    cs:__imp_RegGetValueW
0x18000d362  nop     dword ptr [rax+rax+00h]
0x18000d367  mov     edi, eax
0x18000d369  test    eax, eax
0x18000d36b  jnz     loc_18000D192
0x18000d371  mov     r8d, [rsp+4B0h+var_470]
0x18000d376  and     r8, 0FFFFFFFFFFFFFFFEh
0x18000d37a  add     r8, 0FFFFFFFFFFFFFFFEh
0x18000d37e  cmp     r8, 208h
0x18000d385  jnb     short loc_18000D402
0x18000d387  mov     edx, 208h; uBytes
0x18000d38c  mov     [rsp+r8+4B0h+Src], r12w
0x18000d392  mov     ecx, 40h ; '@'; uFlags
  ... truncated ...
```
