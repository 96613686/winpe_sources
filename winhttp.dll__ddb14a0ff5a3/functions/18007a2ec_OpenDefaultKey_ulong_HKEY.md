# OpenDefaultKey(ulong,HKEY__ * *)

- ea: `0x18007a2ec`
- end: `0x18007a580`
- name: `?OpenDefaultKey@@YAKKPEAPEAUHKEY__@@@Z`
- size: `660`
- prototype: `unsigned int __fastcall(unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180079f8c`

## callees

- `0x180041eb0`
- `0x180058f80`
- `0x18007a2ec`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800dc68c`
- `0x1800dce80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a440`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007a440`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a475`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007a475`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007a3fc`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007a3fc`

## pseudocode

```c
__int64 __fastcall OpenDefaultKey(__int64 a1, HKEY *a2)
{
  int v3; // edx
  int v4; // ecx
  int v5; // r8d
  int v6; // ebx
  int PersistedStateLocation; // eax
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  int v11; // edi
  unsigned int v12; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-278h]
  WCHAR *phkResulta; // [rsp+20h] [rbp-278h]
  HKEY hKey; // [rsp+48h] [rbp-250h] BYREF
  WCHAR SubKey[72]; // [rsp+50h] [rbp-248h] BYREF
  _BYTE v18[384]; // [rsp+E0h] [rbp-1B8h] BYREF

  wcscpy(SubKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Connections");
  hKey = 0;
  memset_0(v18, 0, 0x178u);
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 56, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, 1, phkResult);
  v6 = 0;
  if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_SSSqd(
      v4,
      v3,
      v5,
      (unsigned int)L"InternetSettingsConnections",
      (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Connections",
      0,
      (__int64)SubKey);
  phkResulta = SubKey;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"InternetSettingsConnections",
                             0,
                             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Connections",
                             0);
  v11 = PersistedStateLocation;
  if ( PersistedStateLocation < 0 )
  {
    if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
      WPP_SF_SSSd(
        v9,
        v8,
        v10,
        (unsigned int)L"InternetSettingsConnections",
        (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Connections",
        0,
        PersistedStateLocation);
    v6 = HRESULT_FROM_NTSTATUS(v11);
  }
  if ( (BYTE3(xmmword_180107A60) & 0x20) != 0 )
    WPP_SF_d(1053, 14, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v6, phkResulta);
  if ( v6 < 0 )
  {
    v12 = WX_WIN32_FROM_HR((unsigned int)v6);
  }
  else
  {
    v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
    if ( !v12 )
    {
      *a2 = hKey;
      hKey = 0;
    }
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    WPP_SF_q(1029, 57, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids);
    if ( (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_d(1029, 58, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids, v12, phkResulta);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v12;
}

```

## disassembly

```asm
0x18007a2ec  push    rbx
0x18007a2ee  push    rsi
0x18007a2ef  push    rdi
0x18007a2f0  push    r13
0x18007a2f2  sub     rsp, 278h
0x18007a2f9  mov     rax, cs:__security_cookie
0x18007a300  xor     rax, rsp
0x18007a303  mov     [rsp+298h+var_38], rax
0x18007a30b  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18007a312  lea     rcx, [rsp+298h+var_1B8]; void *
0x18007a31a  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_7+10h; "\\Microsoft\\Windows\\CurrentVersion\\I"...
0x18007a321  mov     rsi, rdx
0x18007a324  movups  xmmword ptr [rsp+298h+SubKey], xmm0
0x18007a329  xor     edx, edx; Val
0x18007a32b  mov     r8d, 178h; Size
0x18007a331  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_7+20h; "ft\\Windows\\CurrentVersion\\Internet S"...
0x18007a338  movups  [rsp+298h+var_228], xmm0
0x18007a33d  mov     [rsp+298h+hKey], 0
0x18007a346  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_7+40h; "ntVersion\\Internet Settings\\Connectio"...
0x18007a34d  movups  [rsp+298h+var_238], xmm1
0x18007a352  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_7+30h; "ws\\CurrentVersion\\Internet Settings\\"...
0x18007a359  movups  [rsp+298h+var_208], xmm0
0x18007a361  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_7+60h; "et Settings\\Connections"
0x18007a368  movups  [rsp+298h+var_218], xmm1
0x18007a370  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_7+50h; "n\\Internet Settings\\Connections"
0x18007a377  movups  [rsp+298h+var_1E8], xmm0
0x18007a37f  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_7+80h; "ections"
0x18007a386  movups  [rsp+298h+var_1F8], xmm1
0x18007a38e  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_7+70h; "ngs\\Connections"
0x18007a395  movups  [rsp+298h+var_1C8], xmm0
0x18007a39d  movups  [rsp+298h+var_1D8], xmm1
0x18007a3a5  call    memset_0
0x18007a3aa  test    byte ptr cs:xmmword_180107A60, 20h
0x18007a3b1  jnz     loc_18007A50E
0x18007a3b7  xor     ebx, ebx
0x18007a3b9  mov     [rsp+298h+var_258], ebx
0x18007a3bd  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18007a3c4  lea     r13, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18007a3cb  jnz     loc_18007A49A
0x18007a3d1  lea     rax, [rsp+298h+var_258]
0x18007a3d6  xor     r9d, r9d
0x18007a3d9  mov     [rsp+298h+var_268], rax
0x18007a3de  lea     rcx, aInternetsettin_0; "InternetSettingsConnections"
0x18007a3e5  lea     rax, [rsp+298h+SubKey]
0x18007a3ea  mov     dword ptr [rsp+298h+var_270], 208h
0x18007a3f2  mov     r8, r13
0x18007a3f5  mov     [rsp+298h+phkResult], rax
0x18007a3fa  xor     edx, edx
0x18007a3fc  call    cs:__imp_RtlGetPersistedStateLocation
0x18007a402  mov     edi, eax
0x18007a404  test    eax, eax
0x18007a406  js      loc_18007A4DD
0x18007a40c  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18007a413  jnz     loc_18007A4BF
0x18007a419  test    ebx, ebx
0x18007a41b  js      loc_18007A52D
0x18007a421  lea     rax, [rsp+298h+hKey]
0x18007a426  mov     r9d, 1; samDesired
0x18007a42c  xor     r8d, r8d; ulOptions
0x18007a42f  mov     [rsp+298h+phkResult], rax; phkResult
0x18007a434  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x18007a439  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007a440  call    cs:__imp_RegOpenKeyExW
0x18007a446  mov     ebx, eax
0x18007a448  test    eax, eax
0x18007a44a  jnz     short loc_18007A45D
0x18007a44c  mov     rax, [rsp+298h+hKey]
0x18007a451  mov     [rsi], rax
0x18007a454  mov     [rsp+298h+hKey], 0
0x18007a45d  mov     al, byte ptr cs:xmmword_180107A60
0x18007a463  test    al, 20h
0x18007a465  jnz     loc_18007A53B
0x18007a46b  mov     rcx, [rsp+298h+hKey]; hKey
0x18007a470  test    rcx, rcx
0x18007a473  jz      short loc_18007A47B
0x18007a475  call    cs:__imp_RegCloseKey
0x18007a47b  mov     eax, ebx
0x18007a47d  mov     rcx, [rsp+298h+var_38]
0x18007a485  xor     rcx, rsp; StackCookie
0x18007a488  call    __security_check_cookie
0x18007a48d  add     rsp, 278h
0x18007a494  pop     r13
0x18007a496  pop     rdi
0x18007a497  pop     rsi
0x18007a498  pop     rbx
0x18007a499  retn
0x18007a49a  lea     rax, [rsp+298h+SubKey]
0x18007a49f  mov     [rsp+298h+var_268], rax
0x18007a4a4  lea     r9, aInternetsettin_0; "InternetSettingsConnections"
0x18007a4ab  mov     [rsp+298h+var_270], rbx
0x18007a4b0  mov     [rsp+298h+phkResult], r13
0x18007a4b5  call    WPP_SF_SSSqd
0x18007a4ba  jmp     loc_18007A3D1
0x18007a4bf  mov     edx, 0Eh
0x18007a4c4  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x18007a4cb  mov     ecx, 41Dh
0x18007a4d0  mov     r9d, ebx
0x18007a4d3  call    WPP_SF_d
0x18007a4d8  jmp     loc_18007A419
0x18007a4dd  test    byte ptr cs:xmmword_180107A60+3, 20h
0x18007a4e4  jz      short loc_18007A500
0x18007a4e6  mov     dword ptr [rsp+298h+var_268], edi
0x18007a4ea  lea     r9, aInternetsettin_0; "InternetSettingsConnections"
0x18007a4f1  mov     [rsp+298h+var_270], rbx
0x18007a4f6  mov     [rsp+298h+phkResult], r13
0x18007a4fb  call    WPP_SF_SSSd
0x18007a500  mov     ecx, edi; int
0x18007a502  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x18007a507  mov     ebx, eax
0x18007a509  jmp     loc_18007A40C
0x18007a50e  mov     edx, 38h ; '8'
0x18007a513  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x18007a51a  mov     ecx, 405h
0x18007a51f  lea     r9d, [rdx-37h]
0x18007a523  call    WPP_SF_d
0x18007a528  jmp     loc_18007A3B7
0x18007a52d  mov     ecx, ebx
0x18007a52f  call    WX_WIN32_FROM_HR
0x18007a534  mov     ebx, eax
0x18007a536  jmp     loc_18007A45D
0x18007a53b  mov     r9, [rsi]
0x18007a53e  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x18007a545  mov     edx, 39h ; '9'
0x18007a54a  mov     ecx, 405h
0x18007a54f  call    WPP_SF_q
0x18007a554  mov     al, byte ptr cs:xmmword_180107A60
0x18007a55a  test    al, 20h
0x18007a55c  jz      loc_18007A46B
0x18007a562  mov     edx, 3Ah ; ':'
0x18007a567  lea     r8, WPP_e24404dfc44e30604b090ca3bc8bd519_Traceguids
0x18007a56e  mov     ecx, 405h
0x18007a573  mov     r9d, ebx
0x18007a576  call    WPP_SF_d
0x18007a57b  jmp     loc_18007A46B
```
