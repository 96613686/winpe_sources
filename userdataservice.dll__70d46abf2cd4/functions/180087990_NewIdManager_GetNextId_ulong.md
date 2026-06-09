# NewIdManager::GetNextId(ulong *)

- ea: `0x180087990`
- end: `0x180087b57`
- name: `?GetNextId@NewIdManager@@QEAAJPEAK@Z`
- size: `455`
- prototype: `__int64 __fastcall(NewIdManager *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c2164`

## callees

- `0x180008f0c`
- `0x180068404`
- `0x180087990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800879ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800879ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087b3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087b3b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180087a35`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180087a35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087a6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087b2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087a6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180087b2f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180087afe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180087afe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180087aad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180087aad`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x1800879f0`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x1800879f0`

## string_xrefs

- `0x1800879bd`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\CallFavorite.h`
- `0x180087a52`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\CallFavorite.h`

## pseudocode

```c
__int64 __fastcall NewIdManager::GetNextId(NewIdManager *this, unsigned int *a2)
{
  unsigned int v4; // ebx
  HKEY *v5; // rax
  const WCHAR *v6; // rdi
  HKEY *phkResult; // rbx
  int v8; // eax
  LSTATUS Key; // eax
  __int64 v10; // r9
  const WCHAR *v11; // rdx
  LSTATUS v12; // eax
  unsigned int v13; // eax
  const WCHAR *v14; // rdx
  LSTATUS v15; // eax
  HKEY v16; // rcx
  BYTE v18[8]; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  unsigned int Data; // [rsp+90h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+40h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( !*(_DWORD *)this )
  {
    v4 = -2147467259;
    Log_HREvent(
      2147500037LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\CallFavorite.h",
      47);
    goto LABEL_23;
  }
  hKey = 0;
  v5 = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  v6 = (const WCHAR *)*((_QWORD *)this + 6);
  phkResult = v5;
  v8 = IsCommsSystemService();
  Key = RegCreateKeyExW((HKEY)((v8 != 0) - 0x7FFFFFFFLL), v6, 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  v4 = Key;
  if ( Key )
  {
    if ( Key > 0 )
      v4 = (unsigned __int16)Key | 0x80070000;
    v10 = 59;
LABEL_7:
    Log_HREvent(
      v4,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\CallFavorite.h",
      v10);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_23;
  }
  v11 = (const WCHAR *)*((_QWORD *)this + 7);
  Type = 4;
  Data = 0;
  cbData = 4;
  v12 = RegQueryValueExW(hKey, v11, 0, &Type, (LPBYTE)&Data, &cbData);
  v4 = v12;
  if ( v12 == 2 )
  {
    v13 = 0;
    Data = 0;
  }
  else
  {
    if ( v12 )
    {
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      v10 = 77;
      goto LABEL_7;
    }
    v13 = Data;
  }
  v14 = (const WCHAR *)*((_QWORD *)this + 7);
  *(_DWORD *)v18 = v13 + 1;
  v15 = RegSetValueExW(hKey, v14, 0, 4u, v18, 4u);
  v4 = v15;
  if ( v15 )
  {
    if ( v15 > 0 )
      v4 = (unsigned __int16)v15 | 0x80070000;
    v10 = 87;
    goto LABEL_7;
  }
  v16 = hKey;
  *a2 = Data;
  if ( v16 )
    RegCloseKey(v16);
  v4 = 0;
LABEL_23:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return v4;
}

```

## disassembly

```asm
0x180087990  mov     [rsp-28h+arg_8], rbx
0x180087995  push    rbp
0x180087996  push    rsi
0x180087997  push    rdi
0x180087998  push    r14
0x18008799a  push    r15
0x18008799c  mov     rbp, rsp
0x18008799f  sub     rsp, 60h
0x1800879a3  mov     rsi, rcx
0x1800879a6  mov     r15, rdx
0x1800879a9  add     rcx, 8; lpCriticalSection
0x1800879ad  call    cs:__imp_EnterCriticalSection
0x1800879b3  cmp     dword ptr [rsi], 0
0x1800879b6  jnz     short loc_1800879D8
0x1800879b8  mov     ebx, 80004005h
0x1800879bd  lea     r8, aOnecoreuapBase_122; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800879c4  mov     ecx, ebx
0x1800879c6  mov     r9d, 2Fh ; '/'
0x1800879cc  xor     edx, edx
0x1800879ce  call    Log_HREvent
0x1800879d3  jmp     loc_180087B37
0x1800879d8  lea     rcx, [rbp+hKey]
0x1800879dc  mov     [rbp+hKey], 0
0x1800879e4  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x1800879e9  mov     rdi, [rsi+30h]
0x1800879ed  mov     rbx, rax
0x1800879f0  call    cs:__imp_IsCommsSystemService
0x1800879f6  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800879ff  mov     rdx, rdi; lpSubKey
0x180087a02  mov     [rsp+60h+phkResult], rbx; phkResult
0x180087a07  neg     eax
0x180087a09  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180087a12  sbb     rcx, rcx
0x180087a15  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x180087a1d  neg     rcx
0x180087a20  mov     [rsp+60h+dwOptions], 0; dwOptions
0x180087a28  add     rcx, 0FFFFFFFF80000001h; hKey
0x180087a2f  xor     r9d, r9d; lpClass
0x180087a32  xor     r8d, r8d; Reserved
0x180087a35  call    cs:__imp_RegCreateKeyExW
0x180087a3b  mov     ebx, eax
0x180087a3d  test    eax, eax
0x180087a3f  jz      short loc_180087A7A
0x180087a41  jle     short loc_180087A4C
0x180087a43  movzx   ebx, ax
0x180087a46  or      ebx, 80070000h
0x180087a4c  mov     r9d, 3Bh ; ';'
0x180087a52  lea     r8, aOnecoreuapBase_122; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180087a59  xor     edx, edx
0x180087a5b  mov     ecx, ebx
0x180087a5d  call    Log_HREvent
0x180087a62  mov     rcx, [rbp+hKey]; hKey
0x180087a66  test    rcx, rcx
0x180087a69  jz      loc_180087B37
0x180087a6f  call    cs:__imp_RegCloseKey
0x180087a75  jmp     loc_180087B37
0x180087a7a  mov     rdx, [rsi+38h]; lpValueName
0x180087a7e  lea     rax, [rbp+cbData]
0x180087a82  mov     rcx, [rbp+hKey]; hKey
0x180087a86  lea     r9, [rbp+Type]; lpType
0x180087a8a  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180087a8f  mov     edi, 4
0x180087a94  lea     rax, [rbp+Data]
0x180087a98  mov     [rbp+Type], edi
0x180087a9b  xor     r8d, r8d; lpReserved
0x180087a9e  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180087aa3  mov     [rbp+Data], 0
0x180087aaa  mov     [rbp+cbData], edi
0x180087aad  call    cs:__imp_RegQueryValueExW
0x180087ab3  mov     ebx, eax
0x180087ab5  cmp     eax, 2
0x180087ab8  jnz     short loc_180087AC1
0x180087aba  xor     eax, eax
0x180087abc  mov     [rbp+Data], eax
0x180087abf  jmp     short loc_180087ADE
0x180087ac1  test    eax, eax
0x180087ac3  jz      short loc_180087ADB
0x180087ac5  jle     short loc_180087AD0
0x180087ac7  movzx   ebx, ax
0x180087aca  or      ebx, 80070000h
0x180087ad0  mov     r9d, 4Dh ; 'M'
0x180087ad6  jmp     loc_180087A52
0x180087adb  mov     eax, [rbp+Data]
0x180087ade  mov     rdx, [rsi+38h]; lpValueName
0x180087ae2  inc     eax
0x180087ae4  mov     rcx, [rbp+hKey]; hKey
0x180087ae8  mov     r9d, edi; dwType
0x180087aeb  mov     dword ptr [rbp+var_10], eax
0x180087aee  xor     r8d, r8d; Reserved
0x180087af1  lea     rax, [rbp+var_10]
0x180087af5  mov     [rsp+60h+samDesired], edi; cbData
0x180087af9  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180087afe  call    cs:__imp_RegSetValueExW
0x180087b04  mov     ebx, eax
0x180087b06  test    eax, eax
0x180087b08  jz      short loc_180087B20
0x180087b0a  jle     short loc_180087B15
0x180087b0c  movzx   ebx, ax
0x180087b0f  or      ebx, 80070000h
0x180087b15  mov     r9d, 57h ; 'W'
0x180087b1b  jmp     loc_180087A52
0x180087b20  mov     rcx, [rbp+hKey]; hKey
0x180087b24  mov     eax, [rbp+Data]
0x180087b27  mov     [r15], eax
0x180087b2a  test    rcx, rcx
0x180087b2d  jz      short loc_180087B35
0x180087b2f  call    cs:__imp_RegCloseKey
0x180087b35  xor     ebx, ebx
0x180087b37  lea     rcx, [rsi+8]; lpCriticalSection
0x180087b3b  call    cs:__imp_LeaveCriticalSection
0x180087b41  mov     eax, ebx
0x180087b43  mov     rbx, [rsp+60h+arg_8]
0x180087b4b  add     rsp, 60h
0x180087b4f  pop     r15
0x180087b51  pop     r14
0x180087b53  pop     rdi
0x180087b54  pop     rsi
0x180087b55  pop     rbp
0x180087b56  retn
```
