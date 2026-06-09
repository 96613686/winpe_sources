# pGetUninstallInterfaceCommon

- ea: `0x18001200c`
- end: `0x180012397`
- name: `pGetUninstallInterfaceCommon`
- size: `907`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005c30`

## callees

- `0x180003f00`
- `0x1800047ac`
- `0x180009860`
- `0x180010a40`
- `0x180010ba0`
- `0x18001200c`
- `0x1800123a0`
- `0x1800131a2`
- `0x1800131e0`
- `0x180014010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18001208c`
- `msvcrt!wcsrchr` at `0x18001208c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001222f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001234b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012217`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001222f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001234b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012209`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012209`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180012070`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180012070`
- `WDSCORE!CurrentIP` at `0x180012158`
- `WDSCORE!CurrentIP` at `0x180012290`
- `WDSCORE!CurrentIP` at `0x180012158`
- `WDSCORE!CurrentIP` at `0x180012290`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800121be`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800122f6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800121be`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800122f6`

## string_xrefs

- `0x1800120d6`: `Windows.old`
- `0x18001218f`: `pGetUninstallInterfaceCommon`
- `0x1800122c7`: `pGetUninstallInterfaceCommon`
- `0x180012164`: `pGetUninstallInterfaceCommon: Failed loading the setupplatform, hr = 0x%x`
- `0x180012202`: `_GetUninstallInterface`
- `0x18001229c`: `pGetUninstallInterfaceCommon: Failed getting the uninstall interface, hr = 0x%x`

## pseudocode

```c
__int64 __fastcall pGetUninstallInterfaceCommon(__int64 a1, __int64 a2, _QWORD *a3)
{
  wchar_t *v5; // rax
  wchar_t **v6; // rax
  int v7; // ebx
  SetupPlatform *v8; // rax
  int SetupPlatform; // r14d
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  HMODULE v14; // rax
  FARPROC ProcAddress; // rbx
  signed int v16; // eax
  bool v17; // sf
  signed int v18; // eax
  __int64 v19; // rax
  int v20; // esi
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  __int64 v24; // rax
  signed int LastError; // eax
  bool v26; // sf
  signed int v27; // eax
  void **v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h]
  _QWORD v30[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  memset_0(Buffer, 0, 0x208u);
  if ( GetWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    v26 = LastError < 0;
    if ( LastError > 0 )
      v26 = 1;
    if ( v26 )
    {
      v27 = GetLastError();
      v7 = v27;
      if ( v27 > 0 )
        return (unsigned __int16)v27 | 0x80070000;
    }
    else
    {
      return (unsigned int)-2147467259;
    }
    return (unsigned int)v7;
  }
  v5 = wcsrchr(Buffer, 0x5Cu);
  if ( v5 )
    *v5 = 0;
  v30[1] = 0;
  v30[0] = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  v6 = (wchar_t **)RAII::CAutoCleanupBase<unsigned short *>::operator&((__int64)v30);
  v7 = BuildPathMultiHr(v6, 4u, Buffer, L"Windows.old", (__int64)L"$WINDOWS.~BT");
  if ( v7 < 0 )
  {
LABEL_7:
    v30[0] = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
    RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release((__int64)v30);
    return (unsigned int)v7;
  }
  v29 = 0;
  v28 = &RAII::CAutoFreeLibrary::`vftable';
  RAII::CAutoCleanupBase<unsigned short *>::operator&((__int64)&v28);
  v8 = (SetupPlatform *)(*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 32LL))(v30);
  SetupPlatform = pLoadSetupPlatform(v8);
  if ( SetupPlatform < 0 )
  {
    v10 = GetLastError();
    v11 = CurrentIP();
    v12 = ConstructPartialMsgW(
            0x2000000,
            "pGetUninstallInterfaceCommon: Failed loading the setupplatform, hr = 0x%x",
            SetupPlatform);
    WdsSetupLogMessageW(
      v12,
      0,
      L"D",
      0,
      237,
      L"base\\ntsetup\\setupplatform\\lib\\static\\setupplatform.cpp",
      L"pGetUninstallInterfaceCommon",
      v11,
      v10,
      0,
      0);
    v28 = &RAII::CAutoFreeLibrary::`vftable';
    RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)&v28);
    v30[0] = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
    RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release((__int64)v30);
    return (unsigned int)SetupPlatform;
  }
  v14 = (HMODULE)((__int64 (__fastcall *)(void ***))v28[4])(&v28);
  ProcAddress = GetProcAddress(v14, "_GetUninstallInterface");
  if ( !ProcAddress )
  {
    v16 = GetLastError();
    v17 = v16 < 0;
    if ( v16 > 0 )
      v17 = 1;
    if ( v17 )
    {
      v18 = GetLastError();
      v7 = v18;
      if ( v18 > 0 )
        v7 = (unsigned __int16)v18 | 0x80070000;
    }
    else
    {
      v7 = -2147467259;
    }
    v28 = &RAII::CAutoFreeLibrary::`vftable';
    RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)&v28);
    goto LABEL_7;
  }
  v19 = ((__int64 (__fastcall *)(void ***))v28[4])(&v28);
  v20 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64))ProcAddress)(v19, 0, a2);
  if ( v20 >= 0 )
  {
    v24 = v29;
    v29 = 0;
    *a3 = v24;
  }
  else
  {
    v21 = GetLastError();
    v22 = CurrentIP();
    v23 = ConstructPartialMsgW(
            0x2000000,
            "pGetUninstallInterfaceCommon: Failed getting the uninstall interface, hr = 0x%x",
            v20);
    WdsSetupLogMessageW(
      v23,
      0,
      L"D",
      0,
      258,
      L"base\\ntsetup\\setupplatform\\lib\\static\\setupplatform.cpp",
      L"pGetUninstallInterfaceCommon",
      v22,
      v21,
      0,
      0);
  }
  v28 = &RAII::CAutoFreeLibrary::`vftable';
  RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)&v28);
  v30[0] = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release((__int64)v30);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18001200c  mov     [rsp-8+arg_0], rbx
0x180012011  mov     [rsp-8+arg_18], rsi
0x180012016  push    rbp
0x180012017  push    rdi
0x180012018  push    r12
0x18001201a  push    r13
0x18001201c  push    r14
0x18001201e  lea     rbp, [rsp-1A0h]
0x180012026  sub     rsp, 2A0h
0x18001202d  mov     rax, cs:__security_cookie
0x180012034  xor     rax, rsp
0x180012037  mov     [rbp+1C0h+var_30], rax
0x18001203e  mov     rdi, r8
0x180012041  mov     rsi, rdx
0x180012044  test    rdx, rdx
0x180012047  jz      loc_180012367
0x18001204d  test    r8, r8
0x180012050  jz      loc_180012367
0x180012056  xor     edx, edx; Val
0x180012058  mov     r8d, 208h; Size
0x18001205e  lea     rcx, [rbp+1C0h+Buffer]; void *
0x180012062  call    memset_0
0x180012067  mov     edx, 104h; uSize
0x18001206c  lea     rcx, [rbp+1C0h+Buffer]; lpBuffer
0x180012070  call    cs:__imp_GetWindowsDirectoryW
0x180012076  dec     eax
0x180012078  cmp     eax, 102h
0x18001207d  ja      loc_180012333
0x180012083  mov     edx, 5Ch ; '\'; Ch
0x180012088  lea     rcx, [rbp+1C0h+Buffer]; Str
0x18001208c  call    cs:__imp_wcsrchr
0x180012092  test    rax, rax
0x180012095  jz      short loc_18001209C
0x180012097  xor     ecx, ecx
0x180012099  mov     [rax], cx
0x18001209c  mov     [rsp+2C0h+var_248], 0
0x1800120a5  lea     r12, ??_7?$CAutoWdsLibFree@PEAG@RAII@@6B@; const RAII::CAutoWdsLibFree<ushort *>::`vftable'
0x1800120ac  mov     [rsp+2C0h+var_250], r12
0x1800120b1  lea     rcx, [rsp+2C0h+var_250]
0x1800120b6  call    ??I?$CAutoCleanupBase@PEAG@RAII@@UEBAPEBQEAGXZ; RAII::CAutoCleanupBase<ushort *>::operator&(void)
0x1800120bb  mov     rcx, rax
0x1800120be  lea     rax, aSources; "Sources"
0x1800120c5  mov     [rsp+2C0h+var_298], rax
0x1800120ca  lea     rax, aWindowsBt; "$WINDOWS.~BT"
0x1800120d1  mov     [rsp+2C0h+var_2A0], rax
0x1800120d6  lea     r9, aWindowsOld_0; "Windows.old"
0x1800120dd  lea     r8, [rbp+1C0h+Buffer]
0x1800120e1  mov     edx, 4
0x1800120e6  call    BuildPathMultiHr
0x1800120eb  mov     ebx, eax
0x1800120ed  test    eax, eax
0x1800120ef  jns     short loc_180012105
0x1800120f1  mov     [rsp+2C0h+var_250], r12
0x1800120f6  lea     rcx, [rsp+2C0h+var_250]
0x1800120fb  call    ?Release@?$CAutoWdsLibFree@PEAUtagVS_FIXEDFILEINFO@@@RAII@@UEAAXXZ; RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release(void)
0x180012100  jmp     loc_180012363
0x180012105  mov     [rsp+2C0h+var_258], 0
0x18001210e  lea     r13, ??_7CAutoFreeLibrary@RAII@@6B@; const RAII::CAutoFreeLibrary::`vftable'
0x180012115  mov     [rsp+2C0h+var_260], r13
0x18001211a  lea     rcx, [rsp+2C0h+var_260]
0x18001211f  call    ??I?$CAutoCleanupBase@PEAG@RAII@@UEBAPEBQEAGXZ; RAII::CAutoCleanupBase<ushort *>::operator&(void)
0x180012124  mov     rbx, rax
0x180012127  mov     rcx, [rsp+2C0h+var_250]
0x18001212c  mov     rax, [rcx+20h]
0x180012130  lea     rcx, [rsp+2C0h+var_250]
0x180012135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001213a  mov     rdx, rbx
0x18001213d  mov     rcx, rax; this
0x180012140  call    pLoadSetupPlatform
0x180012145  mov     r14d, eax
0x180012148  test    eax, eax
0x18001214a  jns     loc_1800121EC
0x180012150  call    cs:__imp_GetLastError
0x180012156  mov     edi, eax
0x180012158  call    cs:__imp_CurrentIP
0x18001215e  mov     rbx, rax
0x180012161  mov     r8d, r14d
0x180012164  lea     rdx, aPgetuninstalli_1; "pGetUninstallInterfaceCommon: Failed lo"...
0x18001216b  mov     ecx, 2000000h; unsigned int
0x180012170  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180012175  mov     [rsp+2C0h+var_270], 0
0x18001217d  mov     [rsp+2C0h+var_278], 0
0x180012186  mov     [rsp+2C0h+var_280], edi
0x18001218a  mov     [rsp+2C0h+var_288], rbx
0x18001218f  lea     rcx, aPgetuninstalli; "pGetUninstallInterfaceCommon"
0x180012196  mov     [rsp+2C0h+var_290], rcx
0x18001219b  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x1800121a2  mov     [rsp+2C0h+var_298], rcx
0x1800121a7  mov     dword ptr [rsp+2C0h+var_2A0], 0EDh
0x1800121af  xor     r9d, r9d
0x1800121b2  lea     r8, aD; "D"
0x1800121b9  xor     edx, edx
0x1800121bb  mov     rcx, rax
0x1800121be  call    cs:__imp_WdsSetupLogMessageW
0x1800121c4  nop
0x1800121c5  mov     [rsp+2C0h+var_260], r13
0x1800121ca  lea     rcx, [rsp+2C0h+var_260]; this
0x1800121cf  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x1800121d4  nop
0x1800121d5  mov     [rsp+2C0h+var_250], r12
0x1800121da  lea     rcx, [rsp+2C0h+var_250]
0x1800121df  call    ?Release@?$CAutoWdsLibFree@PEAUtagVS_FIXEDFILEINFO@@@RAII@@UEAAXXZ; RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release(void)
0x1800121e4  mov     eax, r14d
0x1800121e7  jmp     loc_18001236C
0x1800121ec  mov     rax, [rsp+2C0h+var_260]
0x1800121f1  lea     rcx, [rsp+2C0h+var_260]
0x1800121f6  mov     rax, [rax+20h]
0x1800121fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121ff  mov     rcx, rax; hModule
0x180012202  lea     rdx, aGetuninstallin; "_GetUninstallInterface"
0x180012209  call    cs:__imp_GetProcAddress
0x18001220f  mov     rbx, rax
0x180012212  test    rax, rax
0x180012215  jnz     short loc_18001225B
0x180012217  call    cs:__imp_GetLastError
0x18001221d  mov     edi, 80070000h
0x180012222  test    eax, eax
0x180012224  jle     short loc_18001222D
0x180012226  movzx   eax, ax
0x180012229  or      eax, edi
0x18001222b  test    eax, eax
0x18001222d  jns     short loc_180012242
0x18001222f  call    cs:__imp_GetLastError
0x180012235  mov     ebx, eax
0x180012237  test    eax, eax
0x180012239  jle     short loc_180012247
0x18001223b  movzx   ebx, ax
0x18001223e  or      ebx, edi
0x180012240  jmp     short loc_180012247
0x180012242  mov     ebx, 80004005h
0x180012247  mov     [rsp+2C0h+var_260], r13
0x18001224c  lea     rcx, [rsp+2C0h+var_260]; this
0x180012251  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x180012256  jmp     loc_1800120F1
0x18001225b  mov     rax, [rsp+2C0h+var_260]
0x180012260  lea     rcx, [rsp+2C0h+var_260]
0x180012265  mov     rax, [rax+20h]
0x180012269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001226e  mov     rcx, rax
0x180012271  mov     r8, rsi
0x180012274  xor     edx, edx
0x180012276  mov     rax, rbx
0x180012279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001227e  mov     esi, eax
0x180012280  test    eax, eax
0x180012282  jns     loc_180012320
0x180012288  call    cs:__imp_GetLastError
0x18001228e  mov     edi, eax
0x180012290  call    cs:__imp_CurrentIP
0x180012296  mov     rbx, rax
0x180012299  mov     r8d, esi
0x18001229c  lea     rdx, aPgetuninstalli_0; "pGetUninstallInterfaceCommon: Failed ge"...
0x1800122a3  mov     ecx, 2000000h; unsigned int
0x1800122a8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800122ad  mov     [rsp+2C0h+var_270], 0
0x1800122b5  mov     [rsp+2C0h+var_278], 0
0x1800122be  mov     [rsp+2C0h+var_280], edi
0x1800122c2  mov     [rsp+2C0h+var_288], rbx
0x1800122c7  lea     rcx, aPgetuninstalli; "pGetUninstallInterfaceCommon"
0x1800122ce  mov     [rsp+2C0h+var_290], rcx
0x1800122d3  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x1800122da  mov     [rsp+2C0h+var_298], rcx
0x1800122df  mov     dword ptr [rsp+2C0h+var_2A0], 102h
0x1800122e7  xor     r9d, r9d
0x1800122ea  lea     r8, aD; "D"
0x1800122f1  xor     edx, edx
0x1800122f3  mov     rcx, rax
0x1800122f6  call    cs:__imp_WdsSetupLogMessageW
0x1800122fc  nop
0x1800122fd  mov     [rsp+2C0h+var_260], r13
0x180012302  lea     rcx, [rsp+2C0h+var_260]; this
0x180012307  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x18001230c  nop
0x18001230d  mov     [rsp+2C0h+var_250], r12
0x180012312  lea     rcx, [rsp+2C0h+var_250]
0x180012317  call    ?Release@?$CAutoWdsLibFree@PEAUtagVS_FIXEDFILEINFO@@@RAII@@UEAAXXZ; RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release(void)
0x18001231c  mov     eax, esi
0x18001231e  jmp     short loc_18001236C
0x180012320  mov     rax, [rsp+2C0h+var_258]
0x180012325  mov     [rsp+2C0h+var_258], 0
0x18001232e  mov     [rdi], rax
0x180012331  jmp     short loc_1800122FD
0x180012333  call    cs:__imp_GetLastError
0x180012339  mov     edi, 80070000h
0x18001233e  test    eax, eax
0x180012340  jle     short loc_180012349
0x180012342  movzx   eax, ax
0x180012345  or      eax, edi
0x180012347  test    eax, eax
0x180012349  jns     short loc_18001235E
0x18001234b  call    cs:__imp_GetLastError
0x180012351  mov     ebx, eax
0x180012353  test    eax, eax
0x180012355  jle     short loc_180012363
0x180012357  movzx   ebx, ax
0x18001235a  or      ebx, edi
0x18001235c  jmp     short loc_180012363
0x18001235e  mov     ebx, 80004005h
0x180012363  mov     eax, ebx
0x180012365  jmp     short loc_18001236C
0x180012367  mov     eax, 80070057h
0x18001236c  mov     rcx, [rbp+1C0h+var_30]
0x180012373  xor     rcx, rsp; StackCookie
0x180012376  call    __security_check_cookie
0x18001237b  lea     r11, [rsp+2C0h+var_20]
0x180012383  mov     rbx, [r11+30h]
0x180012387  mov     rsi, [r11+48h]
0x18001238b  mov     rsp, r11
0x18001238e  pop     r14
0x180012390  pop     r13
0x180012392  pop     r12
0x180012394  pop     rdi
0x180012395  pop     rbp
0x180012396  retn
```
