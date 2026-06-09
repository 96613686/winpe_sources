# IsDriverOperationAllowedForTesting(ushort const *,ushort const *)

- ea: `0x1400325b8`
- end: `0x140032799`
- name: `?IsDriverOperationAllowedForTesting@@YAHPEBG0@Z`
- size: `481`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140034bc0`
- `0x140034d10`
- `0x140035d80`
- `0x140035e70`
- `0x1400375a0`

## callees

- `0x14001748c`
- `0x14002d0a0`
- `0x14002dd20`
- `0x140031720`
- `0x1400325b8`
- `0x14005e820`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400326eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400326eb`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14003267a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x14003267a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400326fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400326fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003262c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14003262c`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1400326ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1400326ab`

## string_xrefs

- `0x140032656`: `Checking if driver %ws is allowed to install`
- `0x14003271b`: `GetWindowsDirectory failed with 0x%x`

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
0x1400325b8  mov     [rsp+arg_10], rbx
0x1400325bd  push    rbp
0x1400325be  push    rsi
0x1400325bf  push    rdi
0x1400325c0  sub     rsp, 270h
0x1400325c7  mov     rax, cs:__security_cookie
0x1400325ce  xor     rax, rsp
0x1400325d1  mov     [rsp+288h+var_28], rax
0x1400325d9  mov     rbx, rdx
0x1400325dc  mov     rsi, rcx
0x1400325df  call    ?IsTestSigningEnabled@@YAHXZ; IsTestSigningEnabled(void)
0x1400325e4  xor     ebp, ebp
0x1400325e6  test    eax, eax
0x1400325e8  jz      loc_140032773
0x1400325ee  lea     rax, [rsp+288h+var_244]
0x1400325f3  mov     [rsp+288h+var_248], ebp
0x1400325f7  mov     [rsp+288h+pcbData], rax; pcbData
0x1400325fc  lea     r9d, [rbp+10h]; dwFlags
0x140032600  lea     rax, [rsp+288h+var_248]
0x140032605  mov     [rsp+288h+var_244], 4
0x14003260d  mov     [rsp+288h+pvData], rax; pvData
0x140032612  lea     r8, aAllowtestdrive; "AllowTestDriversForWindowsProtectedPrin"...
0x140032619  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x140032620  mov     [rsp+288h+pdwType], rbp; pdwType
0x140032625  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14003262c  call    cs:__imp_RegGetValueW
0x140032633  nop     dword ptr [rax+rax+00h]
0x140032638  test    eax, eax
0x14003263a  jnz     loc_140032773
0x140032640  cmp     [rsp+288h+var_248], ebp
0x140032644  jz      loc_140032773
0x14003264a  test    rsi, rsi
0x14003264d  jz      loc_140032773
0x140032653  mov     r8, rsi
0x140032656  lea     rdx, aCheckingIfDriv; "Checking if driver %ws is allowed to in"...
0x14003265d  lea     rcx, aIsdriveroperat; "IsDriverOperationAllowedForTesting"
0x140032664  mov     edi, ebp
0x140032666  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14003266b  test    rbx, rbx
0x14003266e  jz      loc_140032732
0x140032674  lea     edx, [rbp+5Ch]; Ch
0x140032677  mov     rcx, rbx; Str
0x14003267a  call    cs:__imp_wcschr
0x140032681  nop     dword ptr [rax+rax+00h]
0x140032686  test    rax, rax
0x140032689  jz      loc_140032732
0x14003268f  xor     edx, edx; Val
0x140032691  lea     rcx, [rsp+288h+Buffer]; void *
0x140032696  mov     r8d, 208h; Size
0x14003269c  call    memset_0
0x1400326a1  mov     edx, 104h; uSize
0x1400326a6  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x1400326ab  call    cs:__imp_GetWindowsDirectoryW
0x1400326b2  nop     dword ptr [rax+rax+00h]
0x1400326b7  test    eax, eax
0x1400326b9  jz      short loc_1400326FD
0x1400326bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400326bf  lea     rcx, [rsp+288h+Buffer]
0x1400326c4  mov     r8, rax
0x1400326c7  inc     r8
0x1400326ca  cmp     [rcx+r8*2], bp
0x1400326cf  jnz     short loc_1400326C7
0x1400326d1  inc     rax
0x1400326d4  cmp     [rbx+rax*2], bp
0x1400326d8  jnz     short loc_1400326D1
0x1400326da  cmp     r8, rax
0x1400326dd  ja      loc_14003276F
0x1400326e3  mov     rdx, rbx
0x1400326e6  lea     rcx, [rsp+288h+Buffer]
0x1400326eb  call    cs:__imp__o__wcsnicmp
0x1400326f2  nop     dword ptr [rax+rax+00h]
0x1400326f7  test    eax, eax
0x1400326f9  jz      short loc_140032732
0x1400326fb  jmp     short loc_14003276F
0x1400326fd  call    cs:__imp_GetLastError
0x140032704  nop     dword ptr [rax+rax+00h]
0x140032709  mov     ebx, eax
0x14003270b  test    eax, eax
0x14003270d  jle     short loc_140032718
0x14003270f  movzx   ebx, ax
0x140032712  or      ebx, 80070000h
0x140032718  mov     r8d, ebx
0x14003271b  lea     rdx, aGetwindowsdire; "GetWindowsDirectory failed with 0x%x"
0x140032722  lea     rcx, aIsdriveroperat; "IsDriverOperationAllowedForTesting"
0x140032729  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14003272e  test    ebx, ebx
0x140032730  js      short loc_14003276F
0x140032732  mov     ecx, ebp
0x140032734  cmp     ecx, 9
0x140032737  jnb     short loc_14003276F
0x140032739  mov     eax, ecx
0x14003273b  lea     r9, ?g_pszDriverAllowList@@3PAPEBGA; ushort const * near * g_pszDriverAllowList
0x140032742  mov     rdx, rsi
0x140032745  mov     r9, [r9+rax*8]
0x140032749  sub     r9, rsi
0x14003274c  movzx   eax, word ptr [rdx]
0x14003274f  movzx   r8d, word ptr [rdx+r9]
0x140032754  sub     eax, r8d
0x140032757  jnz     short loc_140032762
0x140032759  add     rdx, 2
0x14003275d  test    r8d, r8d
0x140032760  jnz     short loc_14003274C
0x140032762  test    eax, eax
0x140032764  jz      short loc_14003276A
0x140032766  inc     ecx
0x140032768  jmp     short loc_140032734
0x14003276a  mov     edi, 1
0x14003276f  mov     eax, edi
0x140032771  jmp     short loc_140032775
0x140032773  xor     eax, eax
0x140032775  mov     rcx, [rsp+288h+var_28]
0x14003277d  xor     rcx, rsp; StackCookie
0x140032780  call    __security_check_cookie
0x140032785  mov     rbx, [rsp+288h+arg_10]
0x14003278d  add     rsp, 270h
0x140032794  pop     rdi
0x140032795  pop     rsi
0x140032796  pop     rbp
0x140032797  retn
```
