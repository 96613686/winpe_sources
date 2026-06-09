# WerpHasOobeCompleted

- ea: `0x180031310`
- end: `0x1800315fa`
- name: `WerpHasOobeCompleted`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033030`

## callees

- `0x180004c64`
- `0x18000cf50`
- `0x180020680`
- `0x18002a0f4`
- `0x180031310`
- `0x18003a9f4`
- `0x180053300`
- `0x18009b81c`
- `0x1800aa154`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800313bc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003145b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800313bc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003145b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800315c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800315c6`
- `ntdll!RtlNtStatusToDosError` at `0x1800314e1`
- `ntdll!RtlNtStatusToDosError` at `0x1800314e1`
- `ntdll!NtQueryWnfStateData` at `0x1800314cf`
- `ntdll!NtQueryWnfStateData` at `0x1800314cf`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180031417`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180031417`

## string_xrefs

- `0x180031374`: `OobeCompleted`
- `0x1800313d0`: `%windir%\system32\kernel32.dll`

## pseudocode

```c
__int64 __fastcall WerpHasOobeCompleted(_DWORD *a1)
{
  const wchar_t *v2; // rdx
  HKEY v3; // rcx
  const wchar_t *v4; // r8
  int v5; // edi
  unsigned int DeviceClass; // ebx
  __int64 v7; // rdx
  NTSTATUS v8; // eax
  signed int v9; // eax
  int v10; // eax
  char *v11; // r8
  bool v13; // [rsp+28h] [rbp-48h]
  bool v14; // [rsp+28h] [rbp-48h]
  int v15; // [rsp+30h] [rbp-40h] BYREF
  int v16; // [rsp+34h] [rbp-3Ch] BYREF
  int v17; // [rsp+38h] [rbp-38h] BYREF
  int v18; // [rsp+3Ch] [rbp-34h] BYREF
  LPVOID lpMem[2]; // [rsp+40h] [rbp-30h] BYREF
  char v20; // [rsp+50h] [rbp-20h] BYREF
  _DWORD v21[2]; // [rsp+60h] [rbp-10h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  if ( dword_1800DED50 )
  {
    v5 = 1;
LABEL_30:
    DeviceClass = 0;
    goto LABEL_31;
  }
  if ( UtilRegGetDWORD(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting",
         L"OobeCompleted",
         0,
         0,
         v13) )
  {
    dword_1800DED50 = 1;
    DeviceClass = 0;
    goto LABEL_37;
  }
  v5 = 0;
  DeviceClass = UtilGetDeviceClass(lpMem);
  if ( (DeviceClass & 0x80000000) != 0 )
  {
LABEL_31:
    if ( !dword_1800DED50 || v5 )
      goto LABEL_37;
    goto LABEL_33;
  }
  if ( !(unsigned int)_o__wcsicmp(lpMem[0], L"Windows.Desktop") )
  {
    if ( UtilFileExists(L"%windir%\\system32\\kernel32.dll")
      && !UtilRegGetDWORD(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
            L"SkipMachineOOBE",
            0,
            0,
            v14) )
    {
      v15 = 0;
      if ( !(unsigned int)OOBEComplete(&v15) || !v15 )
      {
        v3 = (HKEY)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_28;
        v7 = 90;
LABEL_27:
        WPP_SF_(*((_QWORD *)v3 + 2), v7, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids);
LABEL_28:
        DeviceClass = -2147024891;
        goto LABEL_31;
      }
    }
    goto LABEL_8;
  }
  if ( (unsigned int)_o__wcsicmp(lpMem[0], L"Windows.Mobile") )
  {
    dword_1800DED50 = 1;
    goto LABEL_30;
  }
  if ( UtilRegGetDWORD(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Shell\\Oobe", L"OobeHeadless", 0, 0, v14) )
    goto LABEL_8;
  v21[0] = -1547945867;
  v21[1] = 1099564606;
  v18 = 0;
  v16 = 0;
  v17 = 4;
  v8 = NtQueryWnfStateData(v21, 0, 0, &v18, &v16, &v17);
  if ( v8 < 0 )
  {
    v9 = RtlNtStatusToDosError(v8);
    DeviceClass = v9;
    if ( v9 > 0 )
      DeviceClass = (unsigned __int16)v9 | 0x80070000;
    v3 = (HKEY)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids, DeviceClass);
    goto LABEL_31;
  }
  if ( !v16 )
  {
    v3 = (HKEY)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_28;
    v7 = 92;
    goto LABEL_27;
  }
LABEL_8:
  DeviceClass = 0;
  dword_1800DED50 = 1;
LABEL_33:
  v10 = WriteDWordToRegistry(v3, v2, v4);
  if ( v10 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids,
      (unsigned int)v10);
LABEL_37:
  v11 = (char *)lpMem[0];
  *a1 = dword_1800DED50;
  if ( v11 != &v20 )
    HeapFree(g_hWerheap, 0, v11);
  return DeviceClass;
}

```

## disassembly

```asm
0x180031310  mov     [rsp-28h+arg_8], rbx
0x180031315  mov     [rsp-28h+arg_10], rsi
0x18003131a  push    rbp
0x18003131b  push    rdi
0x18003131c  push    r12
0x18003131e  push    r13
0x180031320  push    r15
0x180031322  mov     rbp, rsp
0x180031325  sub     rsp, 70h
0x180031329  mov     rax, cs:__security_cookie
0x180031330  xor     rax, rsp
0x180031333  mov     [rbp+var_8], rax
0x180031337  mov     rsi, rcx
0x18003133a  lea     rcx, [rbp+lpMem]; void *
0x18003133e  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180031343  cmp     cs:dword_1800DED50, 0
0x18003134a  lea     r13, WPP_GLOBAL_Control
0x180031351  mov     r15d, 1
0x180031357  jz      short loc_180031361
0x180031359  mov     edi, r15d
0x18003135c  jmp     loc_180031566
0x180031361  mov     r12, 0FFFFFFFF80000002h
0x180031368  mov     [rsp+70h+var_50], 0; bool *
0x180031371  mov     rcx, r12; HKEY
0x180031374  lea     r8, aOobecompleted; "OobeCompleted"
0x18003137b  xor     r9d, r9d; unsigned int
0x18003137e  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\Windows E"...
0x180031385  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18003138a  test    eax, eax
0x18003138c  jz      short loc_18003139C
0x18003138e  mov     cs:dword_1800DED50, r15d
0x180031395  xor     ebx, ebx
0x180031397  jmp     loc_1800315A8
0x18003139c  lea     rcx, [rbp+lpMem]
0x1800313a0  xor     edi, edi
0x1800313a2  call    ?UtilGetDeviceClass@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetDeviceClass(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800313a7  mov     ebx, eax
0x1800313a9  test    eax, eax
0x1800313ab  js      loc_180031568
0x1800313b1  mov     rcx, [rbp+lpMem]
0x1800313b5  lea     rdx, aWindowsDesktop; "Windows.Desktop"
0x1800313bc  call    cs:__imp__o__wcsicmp
0x1800313c3  nop     dword ptr [rax+rax+00h]
0x1800313c8  test    eax, eax
0x1800313ca  jnz     loc_180031450
0x1800313d0  lea     rcx, aWindirSystem32; "%windir%\\system32\\kernel32.dll"
0x1800313d7  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x1800313dc  test    al, al
0x1800313de  jnz     short loc_1800313EE
0x1800313e0  xor     ebx, ebx
0x1800313e2  mov     cs:dword_1800DED50, r15d
0x1800313e9  jmp     loc_180031575
0x1800313ee  xor     r9d, r9d; unsigned int
0x1800313f1  mov     [rsp+70h+var_50], rdi; bool *
0x1800313f6  lea     r8, aSkipmachineoob; "SkipMachineOOBE"
0x1800313fd  mov     rcx, r12; HKEY
0x180031400  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180031407  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18003140c  test    eax, eax
0x18003140e  jnz     short loc_1800313E0
0x180031410  lea     rcx, [rbp+var_40]
0x180031414  mov     [rbp+var_40], edi
0x180031417  call    cs:__imp_OOBEComplete
0x18003141e  nop     dword ptr [rax+rax+00h]
0x180031423  test    eax, eax
0x180031425  jz      short loc_18003142C
0x180031427  cmp     [rbp+var_40], edi
0x18003142a  jnz     short loc_1800313E0
0x18003142c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031433  cmp     rcx, r13
0x180031436  jz      loc_180031558
0x18003143c  test    [rcx+1Ch], r15b
0x180031440  jz      loc_180031558
0x180031446  mov     edx, 5Ah ; 'Z'
0x18003144b  jmp     loc_180031548
0x180031450  mov     rcx, [rbp+lpMem]
0x180031454  lea     rdx, aWindowsMobile; "Windows.Mobile"
0x18003145b  call    cs:__imp__o__wcsicmp
0x180031462  nop     dword ptr [rax+rax+00h]
0x180031467  test    eax, eax
0x180031469  jnz     loc_18003155F
0x18003146f  xor     r9d, r9d; unsigned int
0x180031472  mov     [rsp+70h+var_50], rdi; bool *
0x180031477  lea     r8, aOobeheadless; "OobeHeadless"
0x18003147e  mov     rcx, r12; HKEY
0x180031481  lea     rdx, aSoftwareMicros_27; "SOFTWARE\\Microsoft\\Shell\\Oobe"
0x180031488  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18003148d  test    eax, eax
0x18003148f  jnz     loc_1800313E0
0x180031495  lea     rax, [rbp+var_38]
0x180031499  mov     [rbp+var_10], 0A3BC3875h
0x1800314a0  mov     [rsp+70h+var_48], rax
0x1800314a5  lea     r9, [rbp+var_34]
0x1800314a9  lea     rax, [rbp+var_3C]
0x1800314ad  mov     [rbp+var_C], 418A063Eh
0x1800314b4  xor     r8d, r8d
0x1800314b7  mov     [rsp+70h+var_50], rax
0x1800314bc  xor     edx, edx
0x1800314be  mov     [rbp+var_34], edi
0x1800314c1  lea     rcx, [rbp+var_10]
0x1800314c5  mov     [rbp+var_3C], edi
0x1800314c8  mov     [rbp+var_38], 4
0x1800314cf  call    cs:__imp_NtQueryWnfStateData
0x1800314d6  nop     dword ptr [rax+rax+00h]
0x1800314db  test    eax, eax
0x1800314dd  jns     short loc_180031528
0x1800314df  mov     ecx, eax; Status
0x1800314e1  call    cs:__imp_RtlNtStatusToDosError
0x1800314e8  nop     dword ptr [rax+rax+00h]
0x1800314ed  mov     ebx, eax
0x1800314ef  test    eax, eax
0x1800314f1  jle     short loc_1800314FC
0x1800314f3  movzx   ebx, ax
0x1800314f6  or      ebx, 80070000h
0x1800314fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180031503  cmp     rcx, r13
0x180031506  jz      short loc_180031568
0x180031508  test    [rcx+1Ch], r15b
0x18003150c  jz      short loc_180031568
0x18003150e  mov     rcx, [rcx+10h]
0x180031512  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x180031519  mov     edx, 5Bh ; '['
0x18003151e  mov     r9d, ebx
0x180031521  call    WPP_SF_d
0x180031526  jmp     short loc_180031568
0x180031528  cmp     [rbp+var_3C], edi
0x18003152b  jnz     loc_1800313E0
0x180031531  mov     rcx, cs:WPP_GLOBAL_Control
0x180031538  cmp     rcx, r13
0x18003153b  jz      short loc_180031558
0x18003153d  test    [rcx+1Ch], r15b
0x180031541  jz      short loc_180031558
0x180031543  mov     edx, 5Ch ; '\'
0x180031548  mov     rcx, [rcx+10h]
0x18003154c  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x180031553  call    WPP_SF_
0x180031558  mov     ebx, 80070005h
0x18003155d  jmp     short loc_180031568
0x18003155f  mov     cs:dword_1800DED50, r15d
0x180031566  xor     ebx, ebx
0x180031568  cmp     cs:dword_1800DED50, 0
0x18003156f  jz      short loc_1800315A8
0x180031571  test    edi, edi
0x180031573  jnz     short loc_1800315A8
0x180031575  call    ?WriteDWordToRegistry@@YAJPEAUHKEY__@@PEB_W1K@Z; WriteDWordToRegistry(HKEY__ *,wchar_t const *,wchar_t const *,ulong)
0x18003157a  test    eax, eax
0x18003157c  jns     short loc_1800315A8
0x18003157e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031585  cmp     rcx, r13
0x180031588  jz      short loc_1800315A8
0x18003158a  test    [rcx+1Ch], r15b
0x18003158e  jz      short loc_1800315A8
0x180031590  mov     rcx, [rcx+10h]
0x180031594  lea     r8, WPP_9dfd7ac6136136787bccfd9dc78fa34e_Traceguids
0x18003159b  mov     edx, 5Dh ; ']'
0x1800315a0  mov     r9d, eax
0x1800315a3  call    WPP_SF_d
0x1800315a8  mov     eax, cs:dword_1800DED50
0x1800315ae  mov     r8, [rbp+lpMem]; lpMem
0x1800315b2  mov     [rsi], eax
0x1800315b4  lea     rax, [rbp+var_20]
0x1800315b8  cmp     r8, rax
0x1800315bb  jz      short loc_1800315D2
0x1800315bd  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x1800315c4  xor     edx, edx; dwFlags
0x1800315c6  call    cs:__imp_HeapFree
0x1800315cd  nop     dword ptr [rax+rax+00h]
0x1800315d2  mov     eax, ebx
0x1800315d4  mov     rcx, [rbp+var_8]
0x1800315d8  xor     rcx, rsp; StackCookie
0x1800315db  call    __security_check_cookie
0x1800315e0  lea     r11, [rsp+70h+var_s0]
0x1800315e5  mov     rbx, [r11+38h]
0x1800315e9  mov     rsi, [r11+40h]
0x1800315ed  mov     rsp, r11
0x1800315f0  pop     r15
0x1800315f2  pop     r13
0x1800315f4  pop     r12
0x1800315f6  pop     rdi
0x1800315f7  pop     rbp
0x1800315f8  retn
```
