# IsDriverOperationAllowedForTesting(ushort const *,ushort const *)

- ea: `0x14002fe2c`
- end: `0x14002ffee`
- name: `?IsDriverOperationAllowedForTesting@@YAHPEBG0@Z`
- size: `450`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400322c0`
- `0x1400323f0`
- `0x140033380`
- `0x140033450`
- `0x140034970`

## callees

- `0x1400160a0`
- `0x14002abc0`
- `0x14002b810`
- `0x14002f030`
- `0x14002fe2c`
- `0x14005907c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14002ff4d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14002ff4d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14002fee8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14002fee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ff59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ff59`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002fea0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002fea0`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14002ff13`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14002ff13`

## string_xrefs

- `0x14002fec4`: `Checking if driver %ws is allowed to install`
- `0x14002ff71`: `GetWindowsDirectory failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IsDriverOperationAllowedForTesting(char *a1, const unsigned __int16 *a2)
{
  unsigned int v4; // edi
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // r8
  signed int LastError; // eax
  signed int v8; // ebx
  unsigned int i; // ecx
  char *v10; // rdx
  int v11; // r8d
  int v12; // eax
  int pvData; // [rsp+40h] [rbp-248h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-244h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-238h] BYREF

  if ( (unsigned int)IsTestSigningEnabled() )
  {
    pvData = 0;
    pcbData[0] = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows NT\\Printers\\WPP",
            L"AllowTestDriversForWindowsProtectedPrint",
            0x10u,
            0,
            &pvData,
            pcbData)
      && pvData
      && a1 )
    {
      v4 = 0;
      SpoolerServiceTelemetry::WriteDbgTraceInfo(
        "IsDriverOperationAllowedForTesting",
        L"Checking if driver %ws is allowed to install",
        a1);
      if ( a2 && wcschr(a2, 0x5Cu) )
      {
        memset_0(Buffer, 0, 0x208u);
        if ( GetWindowsDirectoryW(Buffer, 0x104u) )
        {
          v5 = -1;
          v6 = -1;
          do
            ++v6;
          while ( Buffer[v6] );
          do
            ++v5;
          while ( a2[v5] );
          if ( v6 > v5 || (unsigned int)_o__wcsnicmp(Buffer, a2) )
            return v4;
        }
        else
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          SpoolerServiceTelemetry::WriteDbgTraceError(
            "IsDriverOperationAllowedForTesting",
            L"GetWindowsDirectory failed with 0x%x",
            (unsigned int)v8);
          if ( v8 < 0 )
            return v4;
        }
      }
      for ( i = 0; i < 9; ++i )
      {
        v10 = a1;
        do
        {
          v11 = *(unsigned __int16 *)&v10[(char *)(&g_pszDriverAllowList)[i] - a1];
          v12 = *(unsigned __int16 *)v10 - v11;
          if ( v12 )
            break;
          v10 += 2;
        }
        while ( v11 );
        if ( !v12 )
          return 1;
      }
      return v4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002fe2c  mov     [rsp+arg_10], rbx
0x14002fe31  push    rbp
0x14002fe32  push    rsi
0x14002fe33  push    rdi
0x14002fe34  sub     rsp, 270h
0x14002fe3b  mov     rax, cs:__security_cookie
0x14002fe42  xor     rax, rsp
0x14002fe45  mov     [rsp+288h+var_28], rax
0x14002fe4d  mov     rbx, rdx
0x14002fe50  mov     rsi, rcx
0x14002fe53  call    ?IsTestSigningEnabled@@YAHXZ; IsTestSigningEnabled(void)
0x14002fe58  xor     ebp, ebp
0x14002fe5a  test    eax, eax
0x14002fe5c  jz      loc_14002FFC9
0x14002fe62  lea     rax, [rsp+288h+var_244]
0x14002fe67  mov     [rsp+288h+var_248], ebp
0x14002fe6b  mov     [rsp+288h+pcbData], rax; pcbData
0x14002fe70  lea     r9d, [rbp+10h]; dwFlags
0x14002fe74  lea     rax, [rsp+288h+var_248]
0x14002fe79  mov     [rsp+288h+var_244], 4
0x14002fe81  mov     [rsp+288h+pvData], rax; pvData
0x14002fe86  lea     r8, aAllowtestdrive; "AllowTestDriversForWindowsProtectedPrin"...
0x14002fe8d  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x14002fe94  mov     [rsp+288h+pdwType], rbp; pdwType
0x14002fe99  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14002fea0  call    cs:__imp_RegGetValueW
0x14002fea6  test    eax, eax
0x14002fea8  jnz     loc_14002FFC9
0x14002feae  cmp     [rsp+288h+var_248], ebp
0x14002feb2  jz      loc_14002FFC9
0x14002feb8  test    rsi, rsi
0x14002febb  jz      loc_14002FFC9
0x14002fec1  mov     r8, rsi
0x14002fec4  lea     rdx, aCheckingIfDriv; "Checking if driver %ws is allowed to in"...
0x14002fecb  lea     rcx, aIsdriveroperat; "IsDriverOperationAllowedForTesting"
0x14002fed2  mov     edi, ebp
0x14002fed4  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14002fed9  test    rbx, rbx
0x14002fedc  jz      loc_14002FF88
0x14002fee2  lea     edx, [rbp+5Ch]; Ch
0x14002fee5  mov     rcx, rbx; Str
0x14002fee8  call    cs:__imp_wcschr
0x14002feee  test    rax, rax
0x14002fef1  jz      loc_14002FF88
0x14002fef7  xor     edx, edx; Val
0x14002fef9  lea     rcx, [rsp+288h+Buffer]; void *
0x14002fefe  mov     r8d, 208h; Size
0x14002ff04  call    memset_0
0x14002ff09  mov     edx, 104h; uSize
0x14002ff0e  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x14002ff13  call    cs:__imp_GetWindowsDirectoryW
0x14002ff19  test    eax, eax
0x14002ff1b  jz      short loc_14002FF59
0x14002ff1d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002ff21  lea     rcx, [rsp+288h+Buffer]
0x14002ff26  mov     r8, rax
0x14002ff29  inc     r8
0x14002ff2c  cmp     [rcx+r8*2], bp
0x14002ff31  jnz     short loc_14002FF29
0x14002ff33  inc     rax
0x14002ff36  cmp     [rbx+rax*2], bp
0x14002ff3a  jnz     short loc_14002FF33
0x14002ff3c  cmp     r8, rax
0x14002ff3f  ja      loc_14002FFC5
0x14002ff45  mov     rdx, rbx
0x14002ff48  lea     rcx, [rsp+288h+Buffer]
0x14002ff4d  call    cs:__imp__o__wcsnicmp
0x14002ff53  test    eax, eax
0x14002ff55  jz      short loc_14002FF88
0x14002ff57  jmp     short loc_14002FFC5
0x14002ff59  call    cs:__imp_GetLastError
0x14002ff5f  mov     ebx, eax
0x14002ff61  test    eax, eax
0x14002ff63  jle     short loc_14002FF6E
0x14002ff65  movzx   ebx, ax
0x14002ff68  or      ebx, 80070000h
0x14002ff6e  mov     r8d, ebx
0x14002ff71  lea     rdx, aGetwindowsdire; "GetWindowsDirectory failed with 0x%x"
0x14002ff78  lea     rcx, aIsdriveroperat; "IsDriverOperationAllowedForTesting"
0x14002ff7f  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14002ff84  test    ebx, ebx
0x14002ff86  js      short loc_14002FFC5
0x14002ff88  mov     ecx, ebp
0x14002ff8a  cmp     ecx, 9
0x14002ff8d  jnb     short loc_14002FFC5
0x14002ff8f  mov     eax, ecx
0x14002ff91  lea     r9, ?g_pszDriverAllowList@@3PAPEBGA; ushort const * near * g_pszDriverAllowList
0x14002ff98  mov     rdx, rsi
0x14002ff9b  mov     r9, [r9+rax*8]
0x14002ff9f  sub     r9, rsi
0x14002ffa2  movzx   eax, word ptr [rdx]
0x14002ffa5  movzx   r8d, word ptr [rdx+r9]
0x14002ffaa  sub     eax, r8d
0x14002ffad  jnz     short loc_14002FFB8
0x14002ffaf  add     rdx, 2
0x14002ffb3  test    r8d, r8d
0x14002ffb6  jnz     short loc_14002FFA2
0x14002ffb8  test    eax, eax
0x14002ffba  jz      short loc_14002FFC0
0x14002ffbc  inc     ecx
0x14002ffbe  jmp     short loc_14002FF8A
0x14002ffc0  mov     edi, 1
0x14002ffc5  mov     eax, edi
0x14002ffc7  jmp     short loc_14002FFCB
0x14002ffc9  xor     eax, eax
0x14002ffcb  mov     rcx, [rsp+288h+var_28]
0x14002ffd3  xor     rcx, rsp; StackCookie
0x14002ffd6  call    __security_check_cookie
0x14002ffdb  mov     rbx, [rsp+288h+arg_10]
0x14002ffe3  add     rsp, 270h
0x14002ffea  pop     rdi
0x14002ffeb  pop     rsi
0x14002ffec  pop     rbp
0x14002ffed  retn
```
