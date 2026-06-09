# UserManagerTokenAndShellHandler::ReadConfigFromRegistry(ushort * *,ushort * *,ushort * *,ushort * *)

- ea: `0x1800b6cdc`
- end: `0x1800b71dc`
- name: `?ReadConfigFromRegistry@UserManagerTokenAndShellHandler@@AEAAKPEAPEAG000@Z`
- size: `1280`
- prototype: `unsigned int __fastcall(UserManagerTokenAndShellHandler *__hidden this, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180046b24`

## callees

- `0x18003d38c`
- `0x18004e75c`
- `0x1800b6144`
- `0x1800b6cdc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b7059`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b7059`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b70c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b70ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b7156`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b7173`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b7190`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b71ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b70c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b70ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b7156`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b7173`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b7190`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b71ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b7048`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b70b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b70e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b7148`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b7165`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b7182`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b719f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b7048`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b70b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b70e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b7148`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b7165`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b7182`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b719f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b6e92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b6e92`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6ee2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b7034`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b7098`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b6ee2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b7034`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b7098`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b6fdd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b6fdd`

## string_xrefs

- `0x1800b6dd1`: `SiHostReadyTimeOut`

## pseudocode

```c
__int64 __fastcall UserManagerTokenAndShellHandler::ReadConfigFromRegistry(
        UserManagerTokenAndShellHandler *this,
        LPVOID *a2,
        LPVOID *a3,
        LPVOID *a4,
        unsigned __int16 **a5)
{
  unsigned __int16 **v5; // rsi
  unsigned int v6; // r14d
  unsigned int ValueW; // edi
  unsigned int i; // ebx
  const WCHAR *v12; // rdi
  DWORD v13; // ebx
  HANDLE ProcessHeap; // rax
  void *pvData; // rax
  _QWORD *v16; // rsi
  _WORD *v17; // rbx
  HANDLE v18; // rax
  _WORD *v19; // rbx
  HANDLE v20; // rax
  unsigned __int16 **v21; // rcx
  void *v22; // rbx
  HANDLE v23; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  void *v28; // rbx
  HANDLE v29; // rax
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  int v33; // [rsp+5Ch] [rbp-A4h] BYREF
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+64h] [rbp-9Ch] BYREF
  int v36; // [rsp+68h] [rbp-98h] BYREF
  int v37; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v40; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v41; // [rsp+88h] [rbp-78h] BYREF
  LPVOID v42; // [rsp+90h] [rbp-70h] BYREF
  HKEY v43; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR v44; // [rsp+A0h] [rbp-60h]
  _QWORD v45[7]; // [rsp+A8h] [rbp-58h]
  LPCWSTR lpValue; // [rsp+E0h] [rbp-20h]
  PVOID v47[23]; // [rsp+E8h] [rbp-18h]
  DWORD v48; // [rsp+1B0h] [rbp+B0h] BYREF
  int v49; // [rsp+1B4h] [rbp+B4h]
  DWORD pcbData; // [rsp+1B8h] [rbp+B8h] BYREF
  int v51; // [rsp+1C0h] [rbp+C0h] BYREF
  int v52; // [rsp+1C8h] [rbp+C8h] BYREF

  v49 = HIDWORD(this);
  v5 = a5;
  v44 = L"Shell";
  v6 = 0;
  pcbData = 4;
  *a2 = 0;
  v45[0] = &lpMem;
  *a3 = 0;
  v45[1] = L"ShellInfrastructure";
  *a4 = 0;
  v45[2] = &v40;
  v48 = 0;
  v45[3] = L"FirstUserAccount";
  lpMem = 0;
  v45[4] = &v41;
  v45[5] = L"SecondaryUserAccount";
  v45[6] = &v42;
  lpValue = L"UseVirtualAccount";
  v47[0] = &v37;
  v47[1] = L"UserMgrLaunchShell";
  v47[2] = &v51;
  v47[3] = L"SiHostCritical";
  v47[4] = &v32;
  v47[5] = L"ShellCritical";
  v47[6] = &v33;
  v47[7] = L"SiHostReadyTimeOut";
  v47[8] = &v34;
  v47[9] = L"SiHostRestartCountLimit";
  v47[10] = &v35;
  v47[11] = L"SiHostRestartTimeGap";
  v47[12] = &v36;
  v47[13] = L"UserMgrRestartShellOnCrash";
  v47[14] = &v52;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v37 = 0;
  v51 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  dwDisposition = 0;
  v52 = 0;
  hkey = 0;
  v43 = 0;
  *v5 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
             0,
             0x2001Du,
             &hkey);
  if ( !ValueW )
  {
    for ( i = 0; i < 8; ++i )
    {
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, (LPCWSTR)v47[2 * (int)i - 1], 0x20000018u, 0, v47[2 * (int)i], &pcbData) )
      {
        if ( !v51 )
          HIBYTE(dword_18014828C) = 0;
        if ( v52 )
          HIBYTE(word_1801482A0) = 1;
        if ( v32 )
          HIBYTE(word_180148290) = 1;
        if ( v33 )
          byte_180148292 = 1;
        if ( v34 )
          dword_180148294 = v34;
        else
          dword_180148294 = (_BYTE)dword_180148288 != 0 ? 600000 : 120000;
        if ( v35 )
          dword_180148298 = v35;
        if ( v36 )
          dword_18014829C = v36;
      }
    }
    if ( v37 )
      LOBYTE(word_180148290) = 1;
    if ( !(_BYTE)dword_180148288 )
      AddAuthenticatedUsersToLocalGroup();
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v43,
      0);
    ValueW = RegCreateKeyExW(hkey, L"VolatileUserMgrKey", 0, 0, 1u, 0xF003Fu, 0, &v43, &dwDisposition);
    if ( !ValueW && dwDisposition == 2 )
      LOBYTE(word_1801482A0) = 1;
    while ( v6 < 4 )
    {
      v12 = (const WCHAR *)v45[2 * (int)v6 - 1];
      if ( RegGetValueW(hkey, 0, v12, 0x20000002u, 0, 0, &v48) )
      {
        ValueW = 0;
      }
      else
      {
        v13 = v48;
        ProcessHeap = GetProcessHeap();
        pvData = HeapAlloc(ProcessHeap, 8u, v13);
        v16 = (_QWORD *)v45[2 * (int)v6];
        *v16 = pvData;
        if ( !pvData )
        {
          ValueW = 14;
          goto LABEL_39;
        }
        ValueW = RegGetValueW(hkey, 0, v12, 0x20000002u, 0, pvData, &v48);
        if ( ValueW )
        {
          v19 = (_WORD *)*v16;
          v20 = GetProcessHeap();
          HeapFree(v20, 0, v19);
          *v16 = 0;
          goto LABEL_39;
        }
        if ( v48 >= 2 )
        {
          v17 = (_WORD *)*v16;
          if ( !*(_WORD *)*v16 )
          {
            v18 = GetProcessHeap();
            HeapFree(v18, 0, v17);
            *v16 = 0;
          }
        }
      }
      ++v6;
    }
    v21 = a5;
    *a2 = lpMem;
    *a3 = v40;
    *a4 = v41;
    *v21 = (unsigned __int16 *)v42;
    lpMem = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
  }
LABEL_39:
  v22 = lpMem;
  if ( lpMem )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v22);
  }
  v24 = v40;
  if ( v40 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
  }
  v26 = v41;
  if ( v41 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26);
  }
  v28 = v42;
  if ( v42 )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v28);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v43);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return ValueW;
}

```

## disassembly

```asm
0x1800b6cdc  mov     qword ptr [rsp-8+arg_0], rcx
0x1800b6ce1  push    rbp
0x1800b6ce2  push    rbx
0x1800b6ce3  push    rsi
0x1800b6ce4  push    rdi
0x1800b6ce5  push    r12
0x1800b6ce7  push    r13
0x1800b6ce9  push    r14
0x1800b6ceb  push    r15
0x1800b6ced  lea     rbp, [rsp-68h]
0x1800b6cf2  sub     rsp, 168h
0x1800b6cf9  mov     rsi, [rbp+0A0h+arg_20]
0x1800b6d00  lea     rax, aShell; "Shell"
0x1800b6d07  mov     [rbp+0A0h+var_100], rax
0x1800b6d0b  lea     rcx, [rsp+1A0h+hkey]
0x1800b6d10  xor     r14d, r14d
0x1800b6d13  mov     [rbp+0A0h+arg_8], 4
0x1800b6d1d  mov     [rdx], r14
0x1800b6d20  lea     rax, [rsp+1A0h+lpMem]
0x1800b6d25  mov     [rbp+0A0h+var_F8], rax
0x1800b6d29  mov     r13, rdx
0x1800b6d2c  lea     rax, aShellinfrastru; "ShellInfrastructure"
0x1800b6d33  mov     [r8], r14
0x1800b6d36  mov     [rbp+0A0h+var_F0], rax
0x1800b6d3a  xor     edx, edx
0x1800b6d3c  lea     rax, [rbp+0A0h+var_120]
0x1800b6d40  mov     [r9], r14
0x1800b6d43  mov     [rbp+0A0h+var_E8], rax
0x1800b6d47  mov     r15, r9
0x1800b6d4a  lea     rax, aFirstuseraccou; "FirstUserAccount"
0x1800b6d51  mov     [rbp+0A0h+arg_0], r14d
0x1800b6d58  mov     [rbp+0A0h+var_E0], rax
0x1800b6d5c  mov     r12, r8
0x1800b6d5f  lea     rax, [rbp+0A0h+var_118]
0x1800b6d63  mov     [rsp+1A0h+lpMem], r14
0x1800b6d68  mov     [rbp+0A0h+var_D8], rax
0x1800b6d6c  lea     rax, aSecondaryusera; "SecondaryUserAccount"
0x1800b6d73  mov     [rbp+0A0h+var_D0], rax
0x1800b6d77  lea     rax, [rbp+0A0h+var_110]
0x1800b6d7b  mov     [rbp+0A0h+var_C8], rax
0x1800b6d7f  lea     rax, aUsevirtualacco; "UseVirtualAccount"
0x1800b6d86  mov     [rbp+0A0h+lpValue], rax
0x1800b6d8a  lea     rax, [rsp+1A0h+var_134]
0x1800b6d8f  mov     [rbp+0A0h+var_B8], rax
0x1800b6d93  lea     rax, aUsermgrlaunchs; "UserMgrLaunchShell"
0x1800b6d9a  mov     [rbp+0A0h+var_B0], rax
0x1800b6d9e  lea     rax, [rbp+0A0h+arg_10]
0x1800b6da5  mov     [rbp+0A0h+var_A8], rax
0x1800b6da9  lea     rax, aSihostcritical; "SiHostCritical"
0x1800b6db0  mov     [rbp+0A0h+var_A0], rax
0x1800b6db4  lea     rax, [rsp+1A0h+var_148]
0x1800b6db9  mov     [rbp+0A0h+var_98], rax
0x1800b6dbd  lea     rax, aShellcritical; "ShellCritical"
0x1800b6dc4  mov     [rbp+0A0h+var_90], rax
0x1800b6dc8  lea     rax, [rsp+1A0h+var_144]
0x1800b6dcd  mov     [rbp+0A0h+var_88], rax
0x1800b6dd1  lea     rax, aSihostreadytim; "SiHostReadyTimeOut"
0x1800b6dd8  mov     [rbp+0A0h+var_80], rax
0x1800b6ddc  lea     rax, [rsp+1A0h+var_140]
0x1800b6de1  mov     [rbp+0A0h+var_78], rax
0x1800b6de5  lea     rax, aSihostrestartc; "SiHostRestartCountLimit"
0x1800b6dec  mov     [rbp+0A0h+var_70], rax
0x1800b6df0  lea     rax, [rsp+1A0h+var_13C]
0x1800b6df5  mov     [rbp+0A0h+var_68], rax
0x1800b6df9  lea     rax, aSihostrestartt; "SiHostRestartTimeGap"
0x1800b6e00  mov     [rbp+0A0h+var_60], rax
0x1800b6e04  lea     rax, [rsp+1A0h+var_138]
0x1800b6e09  mov     [rbp+0A0h+var_58], rax
0x1800b6e0d  lea     rax, aUsermgrrestart; "UserMgrRestartShellOnCrash"
0x1800b6e14  mov     [rbp+0A0h+var_50], rax
0x1800b6e18  lea     rax, [rbp+0A0h+arg_18]
0x1800b6e1f  mov     [rbp+0A0h+var_48], rax
0x1800b6e23  mov     [rbp+0A0h+var_120], r14
0x1800b6e27  mov     [rbp+0A0h+var_118], r14
0x1800b6e2b  mov     [rbp+0A0h+var_110], r14
0x1800b6e2f  mov     [rsp+1A0h+var_134], r14d
0x1800b6e34  mov     [rbp+0A0h+arg_10], r14d
0x1800b6e3b  mov     [rsp+1A0h+var_148], r14d
0x1800b6e40  mov     [rsp+1A0h+var_144], r14d
0x1800b6e45  mov     [rsp+1A0h+var_140], r14d
0x1800b6e4a  mov     [rsp+1A0h+var_13C], r14d
0x1800b6e4f  mov     [rsp+1A0h+var_138], r14d
0x1800b6e54  mov     [rsp+1A0h+dwDisposition], r14d
0x1800b6e59  mov     [rbp+0A0h+arg_18], r14d
0x1800b6e60  mov     [rsp+1A0h+hkey], r14
0x1800b6e65  mov     [rbp+0A0h+var_108], r14
0x1800b6e69  mov     [rsi], r14
0x1800b6e6c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800b6e71  lea     rax, [rsp+1A0h+hkey]
0x1800b6e76  mov     r9d, 2001Dh; samDesired
0x1800b6e7c  mov     [rsp+1A0h+phkResult], rax; phkResult
0x1800b6e81  xor     r8d, r8d; ulOptions
0x1800b6e84  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800b6e8b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b6e92  call    cs:__imp_RegOpenKeyExW
0x1800b6e98  mov     edi, eax
0x1800b6e9a  test    eax, eax
0x1800b6e9c  jnz     loc_1800B713E
0x1800b6ea2  mov     ebx, r14d
0x1800b6ea5  mov     rcx, [rsp+1A0h+hkey]; hkey
0x1800b6eaa  lea     rax, [rbp+0A0h+arg_8]
0x1800b6eb1  mov     [rsp+1A0h+pcbData], rax; pcbData
0x1800b6eb6  mov     r9d, 20000018h; dwFlags
0x1800b6ebc  movsxd  r8, ebx
0x1800b6ebf  xor     edx, edx; lpSubKey
0x1800b6ec1  add     r8, r8
0x1800b6ec4  mov     [rbp+0A0h+arg_8], 4
0x1800b6ece  mov     rax, [rbp+r8*8+0A0h+var_B8]
0x1800b6ed3  mov     r8, [rbp+r8*8+0A0h+lpValue]; lpValue
0x1800b6ed8  mov     [rsp+1A0h+pvData], rax; pvData
0x1800b6edd  mov     [rsp+1A0h+phkResult], r14; pdwType
0x1800b6ee2  call    cs:__imp_RegGetValueW
0x1800b6ee8  mov     dl, byte ptr cs:dword_180148288
0x1800b6eee  test    eax, eax
0x1800b6ef0  jnz     loc_1800B6F76
0x1800b6ef6  cmp     [rbp+0A0h+arg_10], r14d
0x1800b6efd  jnz     short loc_1800B6F06
0x1800b6eff  mov     byte ptr cs:dword_18014828C+3, r14b
0x1800b6f06  cmp     [rbp+0A0h+arg_18], r14d
0x1800b6f0d  jz      short loc_1800B6F16
0x1800b6f0f  mov     byte ptr cs:word_1801482A0+1, 1
0x1800b6f16  cmp     [rsp+1A0h+var_148], r14d
0x1800b6f1b  jz      short loc_1800B6F24
0x1800b6f1d  mov     byte ptr cs:word_180148290+1, 1
0x1800b6f24  cmp     [rsp+1A0h+var_144], r14d
0x1800b6f29  jz      short loc_1800B6F32
0x1800b6f2b  mov     cs:byte_180148292, 1
0x1800b6f32  mov     eax, [rsp+1A0h+var_140]
0x1800b6f36  test    eax, eax
0x1800b6f38  jz      short loc_1800B6F42
0x1800b6f3a  mov     cs:dword_180148294, eax
0x1800b6f40  jmp     short loc_1800B6F5A
0x1800b6f42  mov     al, dl
0x1800b6f44  neg     al
0x1800b6f46  sbb     ecx, ecx
0x1800b6f48  and     ecx, 75300h
0x1800b6f4e  add     ecx, 1D4C0h
0x1800b6f54  mov     cs:dword_180148294, ecx
0x1800b6f5a  mov     eax, [rsp+1A0h+var_13C]
0x1800b6f5e  test    eax, eax
0x1800b6f60  jz      short loc_1800B6F68
0x1800b6f62  mov     cs:dword_180148298, eax
0x1800b6f68  mov     eax, [rsp+1A0h+var_138]
0x1800b6f6c  test    eax, eax
0x1800b6f6e  jz      short loc_1800B6F76
0x1800b6f70  mov     cs:dword_18014829C, eax
0x1800b6f76  inc     ebx
0x1800b6f78  cmp     ebx, 8
0x1800b6f7b  jb      loc_1800B6EA5
0x1800b6f81  cmp     [rsp+1A0h+var_134], r14d
0x1800b6f86  jz      short loc_1800B6F8F
0x1800b6f88  mov     byte ptr cs:word_180148290, 1
0x1800b6f8f  test    dl, dl
0x1800b6f91  jnz     short loc_1800B6F98
0x1800b6f93  call    ?AddAuthenticatedUsersToLocalGroup@@YAHXZ; AddAuthenticatedUsersToLocalGroup(void)
0x1800b6f98  xor     edx, edx
0x1800b6f9a  lea     rcx, [rbp+0A0h+var_108]
0x1800b6f9e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800b6fa3  mov     rcx, [rsp+1A0h+hkey]; hKey
0x1800b6fa8  lea     rax, [rsp+1A0h+dwDisposition]
0x1800b6fad  mov     [rsp+1A0h+lpdwDisposition], rax; lpdwDisposition
0x1800b6fb2  lea     rdx, aVolatileusermg; "VolatileUserMgrKey"
0x1800b6fb9  lea     rax, [rbp+0A0h+var_108]
0x1800b6fbd  xor     r9d, r9d; lpClass
0x1800b6fc0  mov     [rsp+1A0h+var_168], rax; phkResult
0x1800b6fc5  xor     r8d, r8d; Reserved
0x1800b6fc8  mov     [rsp+1A0h+pcbData], r14; lpSecurityAttributes
0x1800b6fcd  mov     dword ptr [rsp+1A0h+pvData], 0F003Fh; samDesired
0x1800b6fd5  mov     dword ptr [rsp+1A0h+phkResult], 1; dwOptions
0x1800b6fdd  call    cs:__imp_RegCreateKeyExW
0x1800b6fe3  mov     edi, eax
0x1800b6fe5  test    eax, eax
0x1800b6fe7  jnz     short loc_1800B6FF7
0x1800b6fe9  cmp     [rsp+1A0h+dwDisposition], 2
0x1800b6fee  jnz     short loc_1800B6FF7
0x1800b6ff0  mov     byte ptr cs:word_1801482A0, 1
0x1800b6ff7  cmp     r14d, 4
0x1800b6ffb  jnb     loc_1800B7104
0x1800b7001  mov     rcx, [rsp+1A0h+hkey]; hkey
0x1800b7006  lea     rax, [rbp+0A0h+arg_0]
0x1800b700d  mov     [rsp+1A0h+pcbData], rax; pcbData
0x1800b7012  xor     ebx, ebx
0x1800b7014  movsxd  rsi, r14d
0x1800b7017  mov     r9d, 20000002h; dwFlags
0x1800b701d  add     rsi, rsi
0x1800b7020  mov     [rsp+1A0h+pvData], rbx; pvData
0x1800b7025  xor     edx, edx; lpSubKey
0x1800b7027  mov     [rsp+1A0h+phkResult], rbx; pdwType
0x1800b702c  mov     rdi, [rbp+rsi*8+0A0h+var_100]
0x1800b7031  mov     r8, rdi; lpValue
0x1800b7034  call    cs:__imp_RegGetValueW
0x1800b703a  test    eax, eax
0x1800b703c  jnz     loc_1800B70D4
0x1800b7042  mov     ebx, [rbp+0A0h+arg_0]
0x1800b7048  call    cs:__imp_GetProcessHeap
0x1800b704e  mov     r8d, ebx; dwBytes
0x1800b7051  mov     edx, 8; dwFlags
0x1800b7056  mov     rcx, rax; hHeap
0x1800b7059  call    cs:__imp_HeapAlloc
0x1800b705f  mov     rsi, [rbp+rsi*8+0A0h+var_F8]
0x1800b7064  xor     ebx, ebx
0x1800b7066  mov     [rsi], rax
0x1800b7069  test    rax, rax
0x1800b706c  jz      loc_1800B70FD
0x1800b7072  lea     rcx, [rbp+0A0h+arg_0]
0x1800b7079  mov     r9d, 20000002h; dwFlags
0x1800b707f  mov     [rsp+1A0h+pcbData], rcx; pcbData
0x1800b7084  mov     r8, rdi; lpValue
0x1800b7087  mov     rcx, [rsp+1A0h+hkey]; hkey
0x1800b708c  xor     edx, edx; lpSubKey
0x1800b708e  mov     [rsp+1A0h+pvData], rax; pvData
0x1800b7093  mov     [rsp+1A0h+phkResult], rbx; pdwType
0x1800b7098  call    cs:__imp_RegGetValueW
0x1800b709e  mov     edi, eax
0x1800b70a0  test    eax, eax
0x1800b70a2  jnz     short loc_1800B70DE
0x1800b70a4  cmp     [rbp+0A0h+arg_0], 2
0x1800b70ab  jb      short loc_1800B70D6
0x1800b70ad  mov     rbx, [rsi]
0x1800b70b0  xor     eax, eax
0x1800b70b2  cmp     [rbx], ax
0x1800b70b5  jnz     short loc_1800B70D6
0x1800b70b7  call    cs:__imp_GetProcessHeap
0x1800b70bd  mov     r8, rbx; lpMem
0x1800b70c0  xor     edx, edx; dwFlags
0x1800b70c2  mov     rcx, rax; hHeap
0x1800b70c5  call    cs:__imp_HeapFree
0x1800b70cb  mov     qword ptr [rsi], 0
0x1800b70d2  jmp     short loc_1800B70D6
0x1800b70d4  mov     edi, ebx
0x1800b70d6  inc     r14d
0x1800b70d9  jmp     loc_1800B6FF7
0x1800b70de  mov     rbx, [rsi]
0x1800b70e1  call    cs:__imp_GetProcessHeap
0x1800b70e7  mov     r8, rbx; lpMem
0x1800b70ea  xor     edx, edx; dwFlags
0x1800b70ec  mov     rcx, rax; hHeap
0x1800b70ef  call    cs:__imp_HeapFree
0x1800b70f5  xor     r14d, r14d
0x1800b70f8  mov     [rsi], r14
0x1800b70fb  jmp     short loc_1800B713E
0x1800b70fd  mov     edi, 0Eh
0x1800b7102  jmp     short loc_1800B713E
0x1800b7104  mov     rax, [rsp+1A0h+lpMem]
0x1800b7109  xor     r14d, r14d
0x1800b710c  mov     rcx, [rbp+0A0h+arg_20]
0x1800b7113  mov     [r13+0], rax
0x1800b7117  mov     rax, [rbp+0A0h+var_120]
0x1800b711b  mov     [r12], rax
0x1800b711f  mov     rax, [rbp+0A0h+var_118]
0x1800b7123  mov     [r15], rax
0x1800b7126  mov     rax, [rbp+0A0h+var_110]
0x1800b712a  mov     [rcx], rax
0x1800b712d  mov     [rsp+1A0h+lpMem], r14
0x1800b7132  mov     [rbp+0A0h+var_120], r14
0x1800b7136  mov     [rbp+0A0h+var_118], r14
0x1800b713a  mov     [rbp+0A0h+var_110], r14
0x1800b713e  mov     rbx, [rsp+1A0h+lpMem]
0x1800b7143  test    rbx, rbx
0x1800b7146  jz      short loc_1800B715C
0x1800b7148  call    cs:__imp_GetProcessHeap
0x1800b714e  mov     r8, rbx; lpMem
0x1800b7151  xor     edx, edx; dwFlags
0x1800b7153  mov     rcx, rax; hHeap
0x1800b7156  call    cs:__imp_HeapFree
0x1800b715c  mov     rbx, [rbp+0A0h+var_120]
0x1800b7160  test    rbx, rbx
0x1800b7163  jz      short loc_1800B7179
0x1800b7165  call    cs:__imp_GetProcessHeap
0x1800b716b  mov     r8, rbx; lpMem
0x1800b716e  xor     edx, edx; dwFlags
0x1800b7170  mov     rcx, rax; hHeap
0x1800b7173  call    cs:__imp_HeapFree
0x1800b7179  mov     rbx, [rbp+0A0h+var_118]
0x1800b717d  test    rbx, rbx
0x1800b7180  jz      short loc_1800B7196
0x1800b7182  call    cs:__imp_GetProcessHeap
0x1800b7188  mov     r8, rbx; lpMem
0x1800b718b  xor     edx, edx; dwFlags
0x1800b718d  mov     rcx, rax; hHeap
0x1800b7190  call    cs:__imp_HeapFree
0x1800b7196  mov     rbx, [rbp+0A0h+var_110]
0x1800b719a  test    rbx, rbx
0x1800b719d  jz      short loc_1800B71B3
0x1800b719f  call    cs:__imp_GetProcessHeap
0x1800b71a5  mov     r8, rbx; lpMem
0x1800b71a8  xor     edx, edx; dwFlags
0x1800b71aa  mov     rcx, rax; hHeap
0x1800b71ad  call    cs:__imp_HeapFree
0x1800b71b3  lea     rcx, [rbp+0A0h+var_108]
0x1800b71b7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b71bc  lea     rcx, [rsp+1A0h+hkey]
0x1800b71c1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b71c6  mov     eax, edi
0x1800b71c8  add     rsp, 168h
0x1800b71cf  pop     r15
0x1800b71d1  pop     r14
0x1800b71d3  pop     r13
0x1800b71d5  pop     r12
0x1800b71d7  pop     rdi
  ... truncated ...
```
