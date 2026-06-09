# WerpHasOobeCompleted

- ea: `0x18002f950`
- end: `0x18002fc11`
- name: `WerpHasOobeCompleted`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800316d0`

## callees

- `0x180004bb4`
- `0x18000bc10`
- `0x18001fe24`
- `0x1800293ac`
- `0x18002f950`
- `0x180038848`
- `0x180050db0`
- `0x1800974a0`
- `0x1800a5318`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f9fc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002fa8b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f9fc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002fa8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fbe4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fbe4`
- `ntdll!RtlNtStatusToDosError` at `0x18002fb05`
- `ntdll!RtlNtStatusToDosError` at `0x18002fb05`
- `ntdll!NtQueryWnfStateData` at `0x18002faf9`
- `ntdll!NtQueryWnfStateData` at `0x18002faf9`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18002fa4d`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18002fa4d`

## string_xrefs

- `0x18002f9b4`: `OobeCompleted`
- `0x18002fa06`: `%windir%\system32\kernel32.dll`

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
  if ( dword_1800D9D40 )
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
    dword_1800D9D40 = 1;
    DeviceClass = 0;
    goto LABEL_37;
  }
  v5 = 0;
  DeviceClass = UtilGetDeviceClass(lpMem);
  if ( (DeviceClass & 0x80000000) != 0 )
  {
LABEL_31:
    if ( !dword_1800D9D40 || v5 )
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
        WPP_SF_(*((_QWORD *)v3 + 2), v7, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids);
LABEL_28:
        DeviceClass = -2147024891;
        goto LABEL_31;
      }
    }
    goto LABEL_8;
  }
  if ( (unsigned int)_o__wcsicmp(lpMem[0], L"Windows.Mobile") )
  {
    dword_1800D9D40 = 1;
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids, DeviceClass);
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
  dword_1800D9D40 = 1;
LABEL_33:
  v10 = WriteDWordToRegistry(v3, v2, v4);
  if ( v10 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids,
      (unsigned int)v10);
LABEL_37:
  v11 = (char *)lpMem[0];
  *a1 = dword_1800D9D40;
  if ( v11 != &v20 )
    HeapFree(g_hWerheap, 0, v11);
  return DeviceClass;
}

```

## disassembly

```asm
0x18002f950  mov     [rsp-28h+arg_8], rbx
0x18002f955  mov     [rsp-28h+arg_10], rsi
0x18002f95a  push    rbp
0x18002f95b  push    rdi
0x18002f95c  push    r12
0x18002f95e  push    r13
0x18002f960  push    r15
0x18002f962  mov     rbp, rsp
0x18002f965  sub     rsp, 70h
0x18002f969  mov     rax, cs:__security_cookie
0x18002f970  xor     rax, rsp
0x18002f973  mov     [rbp+var_8], rax
0x18002f977  mov     rsi, rcx
0x18002f97a  lea     rcx, [rbp+lpMem]; void *
0x18002f97e  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18002f983  cmp     cs:dword_1800D9D40, 0
0x18002f98a  lea     r13, WPP_GLOBAL_Control
0x18002f991  mov     r15d, 1
0x18002f997  jz      short loc_18002F9A1
0x18002f999  mov     edi, r15d
0x18002f99c  jmp     loc_18002FB84
0x18002f9a1  mov     r12, 0FFFFFFFF80000002h
0x18002f9a8  mov     [rsp+70h+var_50], 0; bool *
0x18002f9b1  mov     rcx, r12; HKEY
0x18002f9b4  lea     r8, aOobecompleted; "OobeCompleted"
0x18002f9bb  xor     r9d, r9d; unsigned int
0x18002f9be  lea     rdx, aSoftwareMicros_22; "Software\\Microsoft\\Windows\\Windows E"...
0x18002f9c5  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18002f9ca  test    eax, eax
0x18002f9cc  jz      short loc_18002F9DC
0x18002f9ce  mov     cs:dword_1800D9D40, r15d
0x18002f9d5  xor     ebx, ebx
0x18002f9d7  jmp     loc_18002FBC6
0x18002f9dc  lea     rcx, [rbp+lpMem]
0x18002f9e0  xor     edi, edi
0x18002f9e2  call    ?UtilGetDeviceClass@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetDeviceClass(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18002f9e7  mov     ebx, eax
0x18002f9e9  test    eax, eax
0x18002f9eb  js      loc_18002FB86
0x18002f9f1  mov     rcx, [rbp+lpMem]
0x18002f9f5  lea     rdx, aWindowsDesktop; "Windows.Desktop"
0x18002f9fc  call    cs:__imp__o__wcsicmp
0x18002fa02  test    eax, eax
0x18002fa04  jnz     short loc_18002FA80
0x18002fa06  lea     rcx, aWindirSystem32; "%windir%\\system32\\kernel32.dll"
0x18002fa0d  call    ?UtilFileExists@@YA_NPEB_W@Z; UtilFileExists(wchar_t const *)
0x18002fa12  test    al, al
0x18002fa14  jnz     short loc_18002FA24
0x18002fa16  xor     ebx, ebx
0x18002fa18  mov     cs:dword_1800D9D40, r15d
0x18002fa1f  jmp     loc_18002FB93
0x18002fa24  xor     r9d, r9d; unsigned int
0x18002fa27  mov     [rsp+70h+var_50], rdi; bool *
0x18002fa2c  lea     r8, aSkipmachineoob; "SkipMachineOOBE"
0x18002fa33  mov     rcx, r12; HKEY
0x18002fa36  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002fa3d  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18002fa42  test    eax, eax
0x18002fa44  jnz     short loc_18002FA16
0x18002fa46  lea     rcx, [rbp+var_40]
0x18002fa4a  mov     [rbp+var_40], edi
0x18002fa4d  call    cs:__imp_OOBEComplete
0x18002fa53  test    eax, eax
0x18002fa55  jz      short loc_18002FA5C
0x18002fa57  cmp     [rbp+var_40], edi
0x18002fa5a  jnz     short loc_18002FA16
0x18002fa5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa63  cmp     rcx, r13
0x18002fa66  jz      loc_18002FB76
0x18002fa6c  test    [rcx+1Ch], r15b
0x18002fa70  jz      loc_18002FB76
0x18002fa76  mov     edx, 5Ah ; 'Z'
0x18002fa7b  jmp     loc_18002FB66
0x18002fa80  mov     rcx, [rbp+lpMem]
0x18002fa84  lea     rdx, aWindowsMobile; "Windows.Mobile"
0x18002fa8b  call    cs:__imp__o__wcsicmp
0x18002fa91  test    eax, eax
0x18002fa93  jnz     loc_18002FB7D
0x18002fa99  xor     r9d, r9d; unsigned int
0x18002fa9c  mov     [rsp+70h+var_50], rdi; bool *
0x18002faa1  lea     r8, aOobeheadless; "OobeHeadless"
0x18002faa8  mov     rcx, r12; HKEY
0x18002faab  lea     rdx, aSoftwareMicros_26; "SOFTWARE\\Microsoft\\Shell\\Oobe"
0x18002fab2  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18002fab7  test    eax, eax
0x18002fab9  jnz     loc_18002FA16
0x18002fabf  lea     rax, [rbp+var_38]
0x18002fac3  mov     [rbp+var_10], 0A3BC3875h
0x18002faca  mov     [rsp+70h+var_48], rax
0x18002facf  lea     r9, [rbp+var_34]
0x18002fad3  lea     rax, [rbp+var_3C]
0x18002fad7  mov     [rbp+var_C], 418A063Eh
0x18002fade  xor     r8d, r8d
0x18002fae1  mov     [rsp+70h+var_50], rax
0x18002fae6  xor     edx, edx
0x18002fae8  mov     [rbp+var_34], edi
0x18002faeb  lea     rcx, [rbp+var_10]
0x18002faef  mov     [rbp+var_3C], edi
0x18002faf2  mov     [rbp+var_38], 4
0x18002faf9  call    cs:__imp_NtQueryWnfStateData
0x18002faff  test    eax, eax
0x18002fb01  jns     short loc_18002FB46
0x18002fb03  mov     ecx, eax; Status
0x18002fb05  call    cs:__imp_RtlNtStatusToDosError
0x18002fb0b  mov     ebx, eax
0x18002fb0d  test    eax, eax
0x18002fb0f  jle     short loc_18002FB1A
0x18002fb11  movzx   ebx, ax
0x18002fb14  or      ebx, 80070000h
0x18002fb1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb21  cmp     rcx, r13
0x18002fb24  jz      short loc_18002FB86
0x18002fb26  test    [rcx+1Ch], r15b
0x18002fb2a  jz      short loc_18002FB86
0x18002fb2c  mov     rcx, [rcx+10h]
0x18002fb30  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x18002fb37  mov     edx, 5Bh ; '['
0x18002fb3c  mov     r9d, ebx
0x18002fb3f  call    WPP_SF_d
0x18002fb44  jmp     short loc_18002FB86
0x18002fb46  cmp     [rbp+var_3C], edi
0x18002fb49  jnz     loc_18002FA16
0x18002fb4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb56  cmp     rcx, r13
0x18002fb59  jz      short loc_18002FB76
0x18002fb5b  test    [rcx+1Ch], r15b
0x18002fb5f  jz      short loc_18002FB76
0x18002fb61  mov     edx, 5Ch ; '\'
0x18002fb66  mov     rcx, [rcx+10h]
0x18002fb6a  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x18002fb71  call    WPP_SF_
0x18002fb76  mov     ebx, 80070005h
0x18002fb7b  jmp     short loc_18002FB86
0x18002fb7d  mov     cs:dword_1800D9D40, r15d
0x18002fb84  xor     ebx, ebx
0x18002fb86  cmp     cs:dword_1800D9D40, 0
0x18002fb8d  jz      short loc_18002FBC6
0x18002fb8f  test    edi, edi
0x18002fb91  jnz     short loc_18002FBC6
0x18002fb93  call    ?WriteDWordToRegistry@@YAJPEAUHKEY__@@PEB_W1K@Z; WriteDWordToRegistry(HKEY__ *,wchar_t const *,wchar_t const *,ulong)
0x18002fb98  test    eax, eax
0x18002fb9a  jns     short loc_18002FBC6
0x18002fb9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fba3  cmp     rcx, r13
0x18002fba6  jz      short loc_18002FBC6
0x18002fba8  test    [rcx+1Ch], r15b
0x18002fbac  jz      short loc_18002FBC6
0x18002fbae  mov     rcx, [rcx+10h]
0x18002fbb2  lea     r8, WPP_1636fc8926073599aef2e91bea7cde7d_Traceguids
0x18002fbb9  mov     edx, 5Dh ; ']'
0x18002fbbe  mov     r9d, eax
0x18002fbc1  call    WPP_SF_d
0x18002fbc6  mov     eax, cs:dword_1800D9D40
0x18002fbcc  mov     r8, [rbp+lpMem]; lpMem
0x18002fbd0  mov     [rsi], eax
0x18002fbd2  lea     rax, [rbp+var_20]
0x18002fbd6  cmp     r8, rax
0x18002fbd9  jz      short loc_18002FBEA
0x18002fbdb  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18002fbe2  xor     edx, edx; dwFlags
0x18002fbe4  call    cs:__imp_HeapFree
0x18002fbea  mov     eax, ebx
0x18002fbec  mov     rcx, [rbp+var_8]
0x18002fbf0  xor     rcx, rsp; StackCookie
0x18002fbf3  call    __security_check_cookie
0x18002fbf8  lea     r11, [rsp+70h+var_s0]
0x18002fbfd  mov     rbx, [r11+38h]
0x18002fc01  mov     rsi, [r11+40h]
0x18002fc05  mov     rsp, r11
0x18002fc08  pop     r15
0x18002fc0a  pop     r13
0x18002fc0c  pop     r12
0x18002fc0e  pop     rdi
0x18002fc0f  pop     rbp
0x18002fc10  retn
```
