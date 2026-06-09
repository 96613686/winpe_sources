# WamRegMetabaseConfig::MDCreatePath(IMSAdminBaseW *,ushort const *)

- ea: `0x180005738`
- end: `0x180005897`
- name: `?MDCreatePath@WamRegMetabaseConfig@@QEAAJPEAUIMSAdminBaseW@@PEBG@Z`
- size: `351`
- prototype: `__int64 __fastcall(WamRegMetabaseConfig *this, struct IMSAdminBaseW *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001ed0`
- `0x180002850`

## callees

- `0x180005738`
- `0x180007010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000576f`
- `msvcrt!_wcsnicmp` at `0x180005786`
- `msvcrt!_wcsnicmp` at `0x18000576f`
- `msvcrt!_wcsnicmp` at `0x180005786`
- `iisutil!PuDbgPrint` at `0x18000580b`
- `iisutil!PuDbgPrint` at `0x180005869`
- `iisutil!PuDbgPrint` at `0x18000580b`
- `iisutil!PuDbgPrint` at `0x180005869`

## string_xrefs

- `0x1800057f2`: `inetsrv\iis\svcs\wam\wamreg\mdconfig.cpp`
- `0x18000584b`: `inetsrv\iis\svcs\wam\wamreg\mdconfig.cpp`
- `0x1800057f9`: `Failed to Open metabase key, path is /LM/W3SVC, hr = %08x\n`
- `0x1800057e7`: `WamRegMetabaseConfig::MDCreatePath`
- `0x180005840`: `WamRegMetabaseConfig::MDCreatePath`
- `0x180005852`: `Failed to AddKey to metabase, path is %S, hr = %08x\n`

## pseudocode

```c
__int64 __fastcall WamRegMetabaseConfig::MDCreatePath(
        WamRegMetabaseConfig *this,
        struct IMSAdminBaseW *a2,
        const unsigned __int16 *a3)
{
  LPVOID v3; // rdi
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  unsigned int v9; // [rsp+58h] [rbp+10h] BYREF
  int v10; // [rsp+5Ch] [rbp+14h]

  v10 = HIDWORD(a2);
  v3 = WamRegMetabaseConfig::m_pMetabase;
  v9 = 0;
  if ( _wcsnicmp(a3, L"\\LM\\W3SVC\\", 0xAu) && _wcsnicmp(a3, L"/LM/W3SVC/", 0xAu) )
    return 2147942487LL;
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, __int64, int, unsigned int *))(*(_QWORD *)v3 + 136LL))(
         v3,
         0,
         L"/LM/W3SVC/",
         2,
         30000,
         &v9);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *))(*(_QWORD *)v3 + 24LL))(v3, v9, a3 + 10);
    v7 = v8;
    if ( v8 < 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconfig.cpp",
        618,
        "WamRegMetabaseConfig::MDCreatePath",
        "Failed to AddKey to metabase, path is %S, hr = %08x\n",
        a3,
        v8);
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v3 + 144LL))(v3, v9);
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconfig.cpp",
      609,
      "WamRegMetabaseConfig::MDCreatePath",
      "Failed to Open metabase key, path is /LM/W3SVC, hr = %08x\n",
      v6);
  }
  return v7;
}

```

## disassembly

```asm
0x180005738  mov     rax, rsp
0x18000573b  mov     [rax+8], rbx
0x18000573f  mov     [rax+18h], rsi
0x180005743  mov     [rax+10h], rdx
0x180005747  push    rdi
0x180005748  sub     rsp, 40h
0x18000574c  mov     rdi, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005753  lea     rdx, aLmW3svc; "\\LM\\W3SVC\\"
0x18000575a  mov     rsi, r8
0x18000575d  mov     dword ptr [rax+10h], 0
0x180005764  mov     ebx, 0Ah
0x180005769  mov     rcx, rsi; String1
0x18000576c  mov     r8d, ebx; MaxCount
0x18000576f  call    cs:__imp__wcsnicmp
0x180005775  test    eax, eax
0x180005777  jz      short loc_18000579A
0x180005779  mov     r8d, ebx; MaxCount
0x18000577c  lea     rdx, ?g_szMDAppPathPrefix@WamRegGlobal@@2QBGB; "/LM/W3SVC/"
0x180005783  mov     rcx, rsi; String1
0x180005786  call    cs:__imp__wcsnicmp
0x18000578c  test    eax, eax
0x18000578e  jz      short loc_18000579A
0x180005790  mov     eax, 80070057h
0x180005795  jmp     loc_180005887
0x18000579a  mov     rax, [rdi]
0x18000579d  lea     rcx, [rsp+48h+arg_8]
0x1800057a2  mov     [rsp+48h+var_20], rcx
0x1800057a7  lea     r8, ?g_szMDAppPathPrefix@WamRegGlobal@@2QBGB; "/LM/W3SVC/"
0x1800057ae  mov     r9d, 2
0x1800057b4  mov     dword ptr [rsp+48h+var_28], 7530h
0x1800057bc  xor     edx, edx
0x1800057be  mov     rcx, rdi
0x1800057c1  mov     rax, [rax+88h]
0x1800057c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057cd  mov     ebx, eax
0x1800057cf  test    eax, eax
0x1800057d1  jns     short loc_180005813
0x1800057d3  test    byte ptr cs:g_dwDebugFlags, 3
0x1800057da  jz      loc_180005885
0x1800057e0  mov     rcx, cs:g_pDebug
0x1800057e7  lea     r9, aWamregmetabase; "WamRegMetabaseConfig::MDCreatePath"
0x1800057ee  mov     dword ptr [rsp+48h+var_20], eax
0x1800057f2  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconf"...
0x1800057f9  lea     rax, aFailedToOpenMe_1; "Failed to Open metabase key, path is /L"...
0x180005800  mov     r8d, 261h
0x180005806  mov     [rsp+48h+var_28], rax
0x18000580b  call    cs:__imp_PuDbgPrint
0x180005811  jmp     short loc_180005885
0x180005813  mov     rax, [rdi]
0x180005816  lea     r8, [rsi+14h]
0x18000581a  mov     edx, [rsp+48h+arg_8]
0x18000581e  mov     rcx, rdi
0x180005821  mov     rax, [rax+18h]
0x180005825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000582a  mov     ebx, eax
0x18000582c  test    eax, eax
0x18000582e  jns     short loc_18000586F
0x180005830  test    byte ptr cs:g_dwDebugFlags, 3
0x180005837  jz      short loc_18000586F
0x180005839  mov     rcx, cs:g_pDebug
0x180005840  lea     r9, aWamregmetabase; "WamRegMetabaseConfig::MDCreatePath"
0x180005847  mov     [rsp+48h+var_18], eax
0x18000584b  lea     rdx, aInetsrvIisSvcs_1; "inetsrv\\iis\\svcs\\wam\\wamreg\\mdconf"...
0x180005852  lea     rax, aFailedToAddkey; "Failed to AddKey to metabase, path is %"...
0x180005859  mov     [rsp+48h+var_20], rsi
0x18000585e  mov     r8d, 26Ah
0x180005864  mov     [rsp+48h+var_28], rax
0x180005869  call    cs:__imp_PuDbgPrint
0x18000586f  mov     rax, [rdi]
0x180005872  mov     rcx, rdi
0x180005875  mov     edx, [rsp+48h+arg_8]
0x180005879  mov     rax, [rax+90h]
0x180005880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005885  mov     eax, ebx
0x180005887  mov     rbx, [rsp+48h+arg_0]
0x18000588c  mov     rsi, [rsp+48h+arg_10]
0x180005891  add     rsp, 40h
0x180005895  pop     rdi
0x180005896  retn
```
