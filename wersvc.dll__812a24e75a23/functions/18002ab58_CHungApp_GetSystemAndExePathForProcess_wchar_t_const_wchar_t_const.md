# CHungApp::_GetSystemAndExePathForProcess(wchar_t const * *,wchar_t const * *)

- ea: `0x18002ab58`
- end: `0x18002acc5`
- name: `?_GetSystemAndExePathForProcess@CHungApp@@AEAAXPEAPEB_W0@Z`
- size: `365`
- prototype: `void __fastcall(CHungApp *__hidden this, const wchar_t **, const wchar_t **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027460`
- `0x18002accc`

## callees

- `0x18000f270`
- `0x18000ff1c`
- `0x180011ef8`
- `0x180013678`
- `0x18002ab58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ac3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ac3d`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18002ab97`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18002ab97`

## pseudocode

```c
void __fastcall CHungApp::_GetSystemAndExePathForProcess(CHungApp *this, const wchar_t **a2, const wchar_t **a3)
{
  __int64 v6; // rcx
  void *v7; // rcx
  int IFEOKeyForProcess; // eax
  unsigned int DWORD; // esi
  const wchar_t *v10; // rax
  bool *v11; // [rsp+20h] [rbp-28h]
  bool *v12; // [rsp+20h] [rbp-28h]
  bool v13; // [rsp+28h] [rbp-20h]
  bool v14; // [rsp+28h] [rbp-20h]
  __int16 v15; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+10h]

  *a2 = &CHungApp::ms_systemPath;
  *a3 = &CHungApp::ms_exePath;
  v6 = *((_QWORD *)this + 148);
  v15 = 0;
  if ( (unsigned int)IsWow64Process2(v6, &v15, 0)
    && !UtilRegGetDWORD(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting",
          L"ForceNativeDump",
          0,
          v11,
          v13) )
  {
    v7 = (void *)*((_QWORD *)this + 148);
    hKey = 0;
    IFEOKeyForProcess = UtilGetIFEOKeyForProcess(v7);
    if ( IFEOKeyForProcess >= 0 )
    {
      DWORD = UtilRegGetDWORD(hKey, 0, L"ForceNativeDump", 0, v12, v14);
    }
    else
    {
      DWORD = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
          (unsigned int)IFEOKeyForProcess);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( !DWORD )
    {
      if ( v15 == 332 )
      {
        *a2 = (const wchar_t *)&CHungApp::ms_systemPath32;
        v10 = &CHungApp::ms_exePath32;
      }
      else
      {
        if ( v15 != 452 )
          goto LABEL_16;
        *a2 = (const wchar_t *)&CHungApp::ms_systemPathArm32;
        v10 = &CHungApp::ms_exePathArm32;
      }
      *a3 = v10;
    }
  }
LABEL_16:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      (unsigned int)WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids,
      (unsigned int)*a2,
      (__int64)*a3);
}

```

## disassembly

```asm
0x18002ab58  mov     [rsp+arg_10], rbx
0x18002ab5d  push    rbp
0x18002ab5e  push    rsi
0x18002ab5f  push    rdi
0x18002ab60  sub     rsp, 30h
0x18002ab64  lea     rax, ?ms_systemPath@CHungApp@@0PA_WA; wchar_t near * CHungApp::ms_systemPath
0x18002ab6b  mov     rbx, r8
0x18002ab6e  mov     [rdx], rax
0x18002ab71  mov     rdi, rdx
0x18002ab74  lea     rax, ?ms_exePath@CHungApp@@0PA_WA; wchar_t near * CHungApp::ms_exePath
0x18002ab7b  mov     rsi, rcx
0x18002ab7e  mov     [r8], rax
0x18002ab81  lea     rdx, [rsp+48h+arg_0]
0x18002ab86  mov     rcx, [rcx+4A0h]
0x18002ab8d  xor     eax, eax
0x18002ab8f  xor     r8d, r8d
0x18002ab92  mov     [rsp+48h+arg_0], ax
0x18002ab97  call    cs:__imp_IsWow64Process2
0x18002ab9d  lea     rbp, WPP_GLOBAL_Control
0x18002aba4  test    eax, eax
0x18002aba6  jz      loc_18002AC86
0x18002abac  xor     r9d, r9d; unsigned int
0x18002abaf  lea     r8, aForcenativedum; "ForceNativeDump"
0x18002abb6  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\Windows E"...
0x18002abbd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002abc4  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18002abc9  test    eax, eax
0x18002abcb  jnz     loc_18002AC86
0x18002abd1  mov     rcx, [rsi+4A0h]; hProcess
0x18002abd8  lea     r9, [rsp+48h+hKey]
0x18002abdd  mov     [rsp+48h+hKey], 0
0x18002abe6  call    ?UtilGetIFEOKeyForProcess@@YAJPEAXKKPEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; UtilGetIFEOKeyForProcess(void *,ulong,ulong,tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> *)
0x18002abeb  test    eax, eax
0x18002abed  jns     short loc_18002AC1B
0x18002abef  xor     esi, esi
0x18002abf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abf8  cmp     rcx, rbp
0x18002abfb  jz      short loc_18002AC33
0x18002abfd  test    byte ptr [rcx+1Ch], 1
0x18002ac01  jz      short loc_18002AC33
0x18002ac03  mov     rcx, [rcx+10h]
0x18002ac07  lea     edx, [rsi+69h]
0x18002ac0a  mov     r9d, eax
0x18002ac0d  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x18002ac14  call    WPP_SF_d
0x18002ac19  jmp     short loc_18002AC33
0x18002ac1b  mov     rcx, [rsp+48h+hKey]; hKey
0x18002ac20  lea     r8, aForcenativedum; "ForceNativeDump"
0x18002ac27  xor     r9d, r9d; unsigned int
0x18002ac2a  xor     edx, edx; lpSubKey
0x18002ac2c  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18002ac31  mov     esi, eax
0x18002ac33  mov     rcx, [rsp+48h+hKey]; hKey
0x18002ac38  test    rcx, rcx
0x18002ac3b  jz      short loc_18002AC43
0x18002ac3d  call    cs:__imp_RegCloseKey
0x18002ac43  test    esi, esi
0x18002ac45  jnz     short loc_18002AC86
0x18002ac47  mov     eax, 14Ch
0x18002ac4c  cmp     [rsp+48h+arg_0], ax
0x18002ac51  jnz     short loc_18002AC66
0x18002ac53  lea     rax, ?ms_systemPath32@CHungApp@@0PA_WA; wchar_t near * CHungApp::ms_systemPath32
0x18002ac5a  mov     [rdi], rax
0x18002ac5d  lea     rax, ?ms_exePath32@CHungApp@@0PA_WA; wchar_t near * CHungApp::ms_exePath32
0x18002ac64  jmp     short loc_18002AC83
0x18002ac66  mov     eax, 1C4h
0x18002ac6b  cmp     [rsp+48h+arg_0], ax
0x18002ac70  jnz     short loc_18002AC86
0x18002ac72  lea     rax, ?ms_systemPathArm32@CHungApp@@0PA_WA; wchar_t near * CHungApp::ms_systemPathArm32
0x18002ac79  mov     [rdi], rax
0x18002ac7c  lea     rax, ?ms_exePathArm32@CHungApp@@0PA_WA; wchar_t near * CHungApp::ms_exePathArm32
0x18002ac83  mov     [rbx], rax
0x18002ac86  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac8d  cmp     rcx, rbp
0x18002ac90  jz      short loc_18002ACB8
0x18002ac92  test    byte ptr [rcx+1Ch], 4
0x18002ac96  jz      short loc_18002ACB8
0x18002ac98  mov     rax, [rbx]
0x18002ac9b  lea     r8, WPP_28e55efa1b5d3afdb4532fbb5bd9be34_Traceguids
0x18002aca2  mov     r9, [rdi]
0x18002aca5  mov     edx, 1Dh
0x18002acaa  mov     rcx, [rcx+10h]
0x18002acae  mov     [rsp+48h+var_28], rax
0x18002acb3  call    WPP_SF_SS
0x18002acb8  mov     rbx, [rsp+48h+arg_10]
0x18002acbd  add     rsp, 30h
0x18002acc1  pop     rdi
0x18002acc2  pop     rsi
0x18002acc3  pop     rbp
0x18002acc4  retn
```
