# CDialMon::PromptForDisconnect(int,int *)

- ea: `0x180025798`
- end: `0x180025936`
- name: `?PromptForDisconnect@CDialMon@@AEAAHHPEAH@Z`
- size: `414`
- prototype: `__int64 __fastcall(CDialMon *__hidden this, int, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180024d74`

## callees

- `0x1800057fc`
- `0x180008320`
- `0x18000bf78`
- `0x180025798`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800257e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800257e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025914`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025914`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800258b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800258b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800258e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025909`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800258e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180025909`

## string_xrefs

- `0x180025861`: `RemoteAccess`
- `0x1800257cd`: `webcheck.dll`

## pseudocode

```c
HMODULE __fastcall CDialMon::PromptForDisconnect(CDialMon *this, unsigned int a2, int *a3)
{
  HMODULE result; // rax
  unsigned int v7; // eax
  unsigned int v8; // edi
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPARAM v11[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v12; // [rsp+50h] [rbp-B0h]
  CDialMon *v13; // [rsp+60h] [rbp-A0h]
  WCHAR SubKey[128]; // [rsp+70h] [rbp-90h] BYREF

  v13 = 0;
  *(_OWORD *)v11 = 0;
  v12 = 0;
  result = LoadLibraryExW(L"webcheck.dll", 0, 0x22u);
  v11[0] = (LPARAM)result;
  if ( result )
  {
    *(_QWORD *)&v12 = __PAIR64__(a2, *((_DWORD *)this + 1));
    v11[1] = (LPARAM)this + 24;
    v13 = this;
    v7 = SHFusionDialogBoxParam(
           result,
           (LPCWSTR)(a2 != 0 ? 6003LL : 6000LL),
           0,
           (DLGPROC)DisconnectPromptDlgProc,
           (LPARAM)v11);
    *((_QWORD *)this + 70) = 0;
    v8 = v7;
    *a3 = 0;
    if ( !v7 && HIDWORD(v12) )
    {
      *a3 = 1;
      *(_DWORD *)Data = 0;
      hKey = 0;
      StringCchPrintfW(SubKey, 0x80u, L"%s\\Profile\\%s", L"RemoteAccess", (char *)this + 24);
      if ( !RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, &hKey) )
      {
        RegSetValueExW(hKey, L"EnableAutodisconnect", 0, 4u, Data, 4u);
        RegSetValueExW(hKey, L"EnableExitDisconnect", 0, 4u, Data, 4u);
        RegCloseKey(hKey);
      }
    }
    return (HMODULE)v8;
  }
  return result;
}

```

## disassembly

```asm
0x180025798  push    rbp
0x18002579a  push    rbx
0x18002579b  push    rsi
0x18002579c  push    rdi
0x18002579d  push    r14
0x18002579f  lea     rbp, [rsp-80h]
0x1800257a4  sub     rsp, 180h
0x1800257ab  mov     rax, cs:__security_cookie
0x1800257b2  xor     rax, rsp
0x1800257b5  mov     [rbp+0A0h+var_30], rax
0x1800257b9  xor     eax, eax
0x1800257bb  xorps   xmm0, xmm0
0x1800257be  mov     r14, r8
0x1800257c1  mov     [rsp+1A0h+var_140], rax
0x1800257c6  mov     edi, edx
0x1800257c8  mov     rbx, rcx
0x1800257cb  xor     edx, edx; hFile
0x1800257cd  lea     rcx, aWebcheckDll; "webcheck.dll"
0x1800257d4  lea     r8d, [rax+22h]; dwFlags
0x1800257d8  movups  xmmword ptr [rsp+1A0h+var_160], xmm0
0x1800257dd  movups  [rsp+1A0h+var_150], xmm0
0x1800257e2  call    cs:__imp_LoadLibraryExW
0x1800257e8  mov     [rsp+1A0h+var_160], rax
0x1800257ed  mov     rcx, rax; hInstance
0x1800257f0  test    rax, rax
0x1800257f3  jz      loc_18002591C
0x1800257f9  mov     eax, [rbx+4]
0x1800257fc  lea     rsi, [rbx+18h]
0x180025800  mov     dword ptr [rsp+1A0h+var_150+4], edi
0x180025804  lea     r9, ?DisconnectPromptDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18002580b  mov     dword ptr [rsp+1A0h+var_150], eax
0x18002580f  neg     edi
0x180025811  lea     rax, [rsp+1A0h+var_160]
0x180025816  mov     [rsp+1A0h+var_160+8], rsi
0x18002581b  sbb     rdx, rdx
0x18002581e  mov     [rsp+1A0h+var_140], rbx
0x180025823  and     edx, 3
0x180025826  mov     [rsp+1A0h+phkResult], rax; LPARAM
0x18002582b  add     rdx, 1770h; lpTemplateName
0x180025832  xor     r8d, r8d; hWndParent
0x180025835  call    SHFusionDialogBoxParam
0x18002583a  mov     qword ptr [rbx+230h], 0
0x180025845  mov     rdi, rax
0x180025848  mov     dword ptr [r14], 0
0x18002584f  test    eax, eax
0x180025851  jnz     loc_18002591A
0x180025857  cmp     dword ptr [rsp+1A0h+var_150+0Ch], eax
0x18002585b  jz      loc_18002591A
0x180025861  lea     r9, aRemoteaccess; "RemoteAccess"
0x180025868  mov     dword ptr [r14], 1
0x18002586f  lea     r8, aSProfileS; "%s\\Profile\\%s"
0x180025876  mov     dword ptr [rsp+1A0h+Data], eax
0x18002587a  mov     edx, 80h; unsigned __int64
0x18002587f  mov     [rsp+1A0h+hKey], 0
0x180025888  lea     rcx, [rsp+1A0h+SubKey]; unsigned __int16 *
0x18002588d  mov     [rsp+1A0h+phkResult], rsi
0x180025892  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025897  lea     rax, [rsp+1A0h+hKey]
0x18002589c  mov     r9d, 20006h; samDesired
0x1800258a2  xor     r8d, r8d; ulOptions
0x1800258a5  mov     [rsp+1A0h+phkResult], rax; phkResult
0x1800258aa  lea     rdx, [rsp+1A0h+SubKey]; lpSubKey
0x1800258af  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800258b6  call    cs:__imp_RegOpenKeyExW
0x1800258bc  test    eax, eax
0x1800258be  jnz     short loc_18002591A
0x1800258c0  mov     rcx, [rsp+1A0h+hKey]; hKey
0x1800258c5  lea     ebx, [rax+4]
0x1800258c8  lea     rax, [rsp+1A0h+Data]
0x1800258cd  mov     [rsp+1A0h+cbData], ebx; cbData
0x1800258d1  mov     r9d, ebx; dwType
0x1800258d4  mov     [rsp+1A0h+phkResult], rax; lpData
0x1800258d9  xor     r8d, r8d; Reserved
0x1800258dc  lea     rdx, ValueName; "EnableAutodisconnect"
0x1800258e3  call    cs:__imp_RegSetValueExW
0x1800258e9  mov     rcx, [rsp+1A0h+hKey]; hKey
0x1800258ee  lea     rax, [rsp+1A0h+Data]
0x1800258f3  mov     [rsp+1A0h+cbData], ebx; cbData
0x1800258f7  lea     rdx, aEnableexitdisc; "EnableExitDisconnect"
0x1800258fe  mov     r9d, ebx; dwType
0x180025901  mov     [rsp+1A0h+phkResult], rax; lpData
0x180025906  xor     r8d, r8d; Reserved
0x180025909  call    cs:__imp_RegSetValueExW
0x18002590f  mov     rcx, [rsp+1A0h+hKey]; hKey
0x180025914  call    cs:__imp_RegCloseKey
0x18002591a  mov     eax, edi
0x18002591c  mov     rcx, [rbp+0A0h+var_30]
0x180025920  xor     rcx, rsp; StackCookie
0x180025923  call    __security_check_cookie
0x180025928  add     rsp, 180h
0x18002592f  pop     r14
0x180025931  pop     rdi
0x180025932  pop     rsi
0x180025933  pop     rbx
0x180025934  pop     rbp
0x180025935  retn
```
