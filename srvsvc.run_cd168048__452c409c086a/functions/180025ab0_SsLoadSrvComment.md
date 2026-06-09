# SsLoadSrvComment

- ea: `0x180025ab0`
- end: `0x180025e8b`
- name: `SsLoadSrvComment`
- size: `987`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015500`

## callees

- `0x180020de8`
- `0x1800215e8`
- `0x180025ab0`
- `0x180026958`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180025de7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180025de7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025e6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025e6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025cb9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025d7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025cb9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025d7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025c3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025c3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025b5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025d05`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025b5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025d05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025e7a`
- `ntdll!RtlGetPersistedStateLocation` at `0x180025b00`
- `ntdll!RtlGetPersistedStateLocation` at `0x180025bcd`
- `ntdll!RtlGetPersistedStateLocation` at `0x180025b00`
- `ntdll!RtlGetPersistedStateLocation` at `0x180025bcd`
- `ntdll!RtlNtStatusToDosError` at `0x180025b49`
- `ntdll!RtlNtStatusToDosError` at `0x180025c15`
- `ntdll!RtlNtStatusToDosError` at `0x180025b49`
- `ntdll!RtlNtStatusToDosError` at `0x180025c15`

## string_xrefs

- `0x180025cb2`: `srvcomment`
- `0x180025d76`: `srvcomment`
- `0x180025acc`: `SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters`
- `0x180025bac`: `SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c
__int64 SsLoadSrvComment()
{
  BYTE *v0; // rdi
  unsigned int PersistedStateLocation; // ebx
  ULONG v2; // ebx
  WCHAR *v3; // rsi
  __int64 v4; // r8
  NTSTATUS v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  SIZE_T uBytes; // [rsp+70h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+30h] BYREF
  DWORD Type; // [rsp+80h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+40h] BYREF

  LODWORD(uBytes) = 0;
  v0 = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"SrvParameters",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
                             0,
                             0,
                             0,
                             &uBytes);
  if ( PersistedStateLocation != -2147483643 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        123,
        WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
        PersistedStateLocation);
    }
LABEL_6:
    v2 = RtlNtStatusToDosError(PersistedStateLocation);
    goto LABEL_52;
  }
  v3 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)uBytes);
  if ( !v3 )
  {
    PersistedStateLocation = -1073741670;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_Ld(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, v4, (unsigned int)uBytes, -1073741670);
    }
    goto LABEL_6;
  }
  v5 = RtlGetPersistedStateLocation(
         L"SrvParameters",
         0,
         L"SYSTEM\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
         0,
         v3,
         uBytes,
         0);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        125,
        WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
        (unsigned int)v5);
    }
    v2 = RtlNtStatusToDosError(v5);
    goto LABEL_51;
  }
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        126,
        (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
        (_DWORD)v3,
        v2);
    }
    goto LABEL_51;
  }
  v2 = RegQueryValueExW(hKey, L"srvcomment", 0, &Type, 0, &cbData);
  if ( v2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_51;
    }
    v7 = 127;
  }
  else
  {
    v0 = (BYTE *)LocalAlloc(0x40u, cbData);
    if ( !v0 )
    {
      v2 = 8;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_Ld(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, v8, (unsigned int)uBytes, 8);
      }
      goto LABEL_51;
    }
    v2 = RegQueryValueExW(hKey, L"srvcomment", 0, &Type, v0, &cbData);
    if ( v2 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_51;
      }
      v7 = 129;
    }
    else if ( Type != 1 || (cbData & 1) != 0 || (cbData & 0xFFFFFFFE) > 0x202 )
    {
      v2 = 13;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_51;
      }
      v7 = 130;
    }
    else
    {
      if ( !(unsigned int)_o_wcscpy_s(word_18005D560, 257) )
        goto LABEL_51;
      v2 = 111;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_51;
      }
      v7 = 131;
    }
  }
  WPP_SF_d(v6[2], v7, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, v2);
LABEL_51:
  LocalFree(v3);
LABEL_52:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v0 )
    LocalFree(v0);
  return v2;
}

```

## disassembly

```asm
0x180025ab0  push    rbp
0x180025ab2  push    rbx
0x180025ab3  push    rsi
0x180025ab4  push    rdi
0x180025ab5  mov     rbp, rsp
0x180025ab8  sub     rsp, 48h
0x180025abc  lea     rax, [rbp+uBytes]
0x180025ac0  mov     dword ptr [rbp+uBytes], 0
0x180025ac7  mov     [rsp+48h+var_18], rax
0x180025acc  lea     r8, SubKey; "SYSTEM\\CurrentControlSet\\Services\\La"...
0x180025ad3  xor     edi, edi
0x180025ad5  mov     [rbp+hKey], 0
0x180025add  mov     dword ptr [rsp+48h+lpcbData], edi
0x180025ae1  lea     rcx, aSrvparameters; "SrvParameters"
0x180025ae8  xor     r9d, r9d
0x180025aeb  mov     [rsp+48h+phkResult], rdi
0x180025af0  xor     edx, edx
0x180025af2  mov     [rbp+Type], 0
0x180025af9  mov     [rbp+cbData], 0
0x180025b00  call    cs:__imp_RtlGetPersistedStateLocation
0x180025b06  mov     ebx, eax
0x180025b08  cmp     eax, 80000005h
0x180025b0d  jz      short loc_180025B56
0x180025b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b16  lea     rax, WPP_GLOBAL_Control
0x180025b1d  cmp     rcx, rax
0x180025b20  jz      short loc_180025B47
0x180025b22  test    dword ptr [rcx+1Ch], 100h
0x180025b29  jz      short loc_180025B47
0x180025b2b  cmp     byte ptr [rcx+19h], 1
0x180025b2f  jb      short loc_180025B47
0x180025b31  mov     rcx, [rcx+10h]
0x180025b35  lea     edx, [rdi+7Bh]
0x180025b38  mov     r9d, ebx
0x180025b3b  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180025b42  call    WPP_SF_d
0x180025b47  mov     ecx, ebx; Status
0x180025b49  call    cs:__imp_RtlNtStatusToDosError
0x180025b4f  mov     ebx, eax
0x180025b51  jmp     loc_180025E63
0x180025b56  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180025b59  mov     ecx, 40h ; '@'; uFlags
0x180025b5e  call    cs:__imp_LocalAlloc
0x180025b64  mov     rsi, rax
0x180025b67  test    rax, rax
0x180025b6a  jnz     short loc_180025BA9
0x180025b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b73  lea     rax, WPP_GLOBAL_Control
0x180025b7a  mov     ebx, 0C000009Ah
0x180025b7f  cmp     rcx, rax
0x180025b82  jz      short loc_180025B47
0x180025b84  test    dword ptr [rcx+1Ch], 100h
0x180025b8b  jz      short loc_180025B47
0x180025b8d  cmp     byte ptr [rcx+19h], 1
0x180025b91  jb      short loc_180025B47
0x180025b93  mov     r9d, dword ptr [rbp+uBytes]
0x180025b97  lea     edx, [rsi+7Ch]
0x180025b9a  mov     rcx, [rcx+10h]
0x180025b9e  mov     dword ptr [rsp+48h+phkResult], ebx
0x180025ba2  call    WPP_SF_Ld
0x180025ba7  jmp     short loc_180025B47
0x180025ba9  mov     eax, dword ptr [rbp+uBytes]
0x180025bac  lea     r8, SubKey; "SYSTEM\\CurrentControlSet\\Services\\La"...
0x180025bb3  mov     [rsp+48h+var_18], rdi
0x180025bb8  lea     rcx, aSrvparameters; "SrvParameters"
0x180025bbf  mov     dword ptr [rsp+48h+lpcbData], eax
0x180025bc3  xor     r9d, r9d
0x180025bc6  xor     edx, edx
0x180025bc8  mov     [rsp+48h+phkResult], rsi
0x180025bcd  call    cs:__imp_RtlGetPersistedStateLocation
0x180025bd3  mov     ebx, eax
0x180025bd5  test    eax, eax
0x180025bd7  jns     short loc_180025C22
0x180025bd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025be0  lea     rax, WPP_GLOBAL_Control
0x180025be7  cmp     rcx, rax
0x180025bea  jz      short loc_180025C13
0x180025bec  test    dword ptr [rcx+1Ch], 100h
0x180025bf3  jz      short loc_180025C13
0x180025bf5  cmp     byte ptr [rcx+19h], 1
0x180025bf9  jb      short loc_180025C13
0x180025bfb  mov     rcx, [rcx+10h]
0x180025bff  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180025c06  mov     edx, 7Dh ; '}'
0x180025c0b  mov     r9d, ebx
0x180025c0e  call    WPP_SF_d
0x180025c13  mov     ecx, ebx; Status
0x180025c15  call    cs:__imp_RtlNtStatusToDosError
0x180025c1b  mov     ebx, eax
0x180025c1d  jmp     loc_180025E5A
0x180025c22  lea     rax, [rbp+hKey]
0x180025c26  mov     r9d, 20019h; samDesired
0x180025c2c  xor     r8d, r8d; ulOptions
0x180025c2f  mov     [rsp+48h+phkResult], rax; phkResult
0x180025c34  mov     rdx, rsi; lpSubKey
0x180025c37  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025c3e  call    cs:__imp_RegOpenKeyExW
0x180025c44  mov     ebx, eax
0x180025c46  test    eax, eax
0x180025c48  jz      short loc_180025C99
0x180025c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c51  lea     rax, WPP_GLOBAL_Control
0x180025c58  cmp     rcx, rax
0x180025c5b  jz      loc_180025E5A
0x180025c61  test    dword ptr [rcx+1Ch], 100h
0x180025c68  jz      loc_180025E5A
0x180025c6e  cmp     byte ptr [rcx+19h], 1
0x180025c72  jb      loc_180025E5A
0x180025c78  mov     rcx, [rcx+10h]
0x180025c7c  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180025c83  mov     edx, 7Eh ; '~'
0x180025c88  mov     dword ptr [rsp+48h+phkResult], ebx
0x180025c8c  mov     r9, rsi
0x180025c8f  call    WPP_SF_Sd
0x180025c94  jmp     loc_180025E5A
0x180025c99  mov     rcx, [rbp+hKey]; hKey
0x180025c9d  lea     rax, [rbp+cbData]
0x180025ca1  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180025ca6  lea     r9, [rbp+Type]; lpType
0x180025caa  xor     r8d, r8d; lpReserved
0x180025cad  mov     [rsp+48h+phkResult], rdi; lpData
0x180025cb2  lea     rdx, aSrvcomment; "srvcomment"
0x180025cb9  call    cs:__imp_RegQueryValueExW
0x180025cbf  mov     ebx, eax
0x180025cc1  test    eax, eax
0x180025cc3  jz      short loc_180025CFD
0x180025cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ccc  lea     rax, WPP_GLOBAL_Control
0x180025cd3  cmp     rcx, rax
0x180025cd6  jz      loc_180025E5A
0x180025cdc  test    dword ptr [rcx+1Ch], 100h
0x180025ce3  jz      loc_180025E5A
0x180025ce9  cmp     byte ptr [rcx+19h], 1
0x180025ced  jb      loc_180025E5A
0x180025cf3  mov     edx, 7Fh
0x180025cf8  jmp     loc_180025E47
0x180025cfd  mov     edx, [rbp+cbData]; uBytes
0x180025d00  mov     ecx, 40h ; '@'; uFlags
0x180025d05  call    cs:__imp_LocalAlloc
0x180025d0b  mov     rdi, rax
0x180025d0e  test    rax, rax
0x180025d11  jnz     short loc_180025D5D
0x180025d13  lea     ebx, [rax+8]
0x180025d16  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d1d  lea     rax, WPP_GLOBAL_Control
0x180025d24  cmp     rcx, rax
0x180025d27  jz      loc_180025E5A
0x180025d2d  test    dword ptr [rcx+1Ch], 100h
0x180025d34  jz      loc_180025E5A
0x180025d3a  cmp     byte ptr [rcx+19h], 1
0x180025d3e  jb      loc_180025E5A
0x180025d44  mov     r9d, dword ptr [rbp+uBytes]
0x180025d48  lea     edx, [rbx+78h]
0x180025d4b  mov     rcx, [rcx+10h]
0x180025d4f  mov     dword ptr [rsp+48h+phkResult], ebx
0x180025d53  call    WPP_SF_Ld
0x180025d58  jmp     loc_180025E5A
0x180025d5d  mov     rcx, [rbp+hKey]; hKey
0x180025d61  lea     rax, [rbp+cbData]
0x180025d65  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180025d6a  lea     r9, [rbp+Type]; lpType
0x180025d6e  xor     r8d, r8d; lpReserved
0x180025d71  mov     [rsp+48h+phkResult], rdi; lpData
0x180025d76  lea     rdx, aSrvcomment; "srvcomment"
0x180025d7d  call    cs:__imp_RegQueryValueExW
0x180025d83  mov     ebx, eax
0x180025d85  test    eax, eax
0x180025d87  jz      short loc_180025DC1
0x180025d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d90  lea     rax, WPP_GLOBAL_Control
0x180025d97  cmp     rcx, rax
0x180025d9a  jz      loc_180025E5A
0x180025da0  test    dword ptr [rcx+1Ch], 100h
0x180025da7  jz      loc_180025E5A
0x180025dad  cmp     byte ptr [rcx+19h], 1
0x180025db1  jb      loc_180025E5A
0x180025db7  mov     edx, 81h
0x180025dbc  jmp     loc_180025E47
0x180025dc1  cmp     [rbp+Type], 1
0x180025dc5  jnz     short loc_180025E1D
0x180025dc7  mov     eax, [rbp+cbData]
0x180025dca  test    al, 1
0x180025dcc  jnz     short loc_180025E1D
0x180025dce  and     eax, 0FFFFFFFEh
0x180025dd1  cmp     eax, 202h
0x180025dd6  ja      short loc_180025E1D
0x180025dd8  mov     r8, rdi
0x180025ddb  lea     rcx, word_18005D560
0x180025de2  mov     edx, 101h
0x180025de7  call    cs:__imp__o_wcscpy_s
0x180025ded  test    eax, eax
0x180025def  jz      short loc_180025E5A
0x180025df1  mov     ebx, 6Fh ; 'o'
0x180025df6  mov     rcx, cs:WPP_GLOBAL_Control
0x180025dfd  lea     rax, WPP_GLOBAL_Control
0x180025e04  cmp     rcx, rax
0x180025e07  jz      short loc_180025E5A
0x180025e09  test    dword ptr [rcx+1Ch], 100h
0x180025e10  jz      short loc_180025E5A
0x180025e12  cmp     byte ptr [rcx+19h], 1
0x180025e16  jb      short loc_180025E5A
0x180025e18  lea     edx, [rbx+14h]
0x180025e1b  jmp     short loc_180025E47
0x180025e1d  mov     ebx, 0Dh
0x180025e22  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e29  lea     rax, WPP_GLOBAL_Control
0x180025e30  cmp     rcx, rax
0x180025e33  jz      short loc_180025E5A
0x180025e35  test    dword ptr [rcx+1Ch], 100h
0x180025e3c  jz      short loc_180025E5A
0x180025e3e  cmp     byte ptr [rcx+19h], 1
0x180025e42  jb      short loc_180025E5A
0x180025e44  lea     edx, [rbx+75h]
0x180025e47  mov     rcx, [rcx+10h]
0x180025e4b  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180025e52  mov     r9d, ebx
0x180025e55  call    WPP_SF_d
0x180025e5a  mov     rcx, rsi; hMem
0x180025e5d  call    cs:__imp_LocalFree
0x180025e63  mov     rcx, [rbp+hKey]; hKey
0x180025e67  test    rcx, rcx
0x180025e6a  jz      short loc_180025E72
0x180025e6c  call    cs:__imp_RegCloseKey
0x180025e72  test    rdi, rdi
0x180025e75  jz      short loc_180025E80
0x180025e77  mov     rcx, rdi; hMem
0x180025e7a  call    cs:__imp_LocalFree
0x180025e80  mov     eax, ebx
0x180025e82  add     rsp, 48h
0x180025e86  pop     rdi
0x180025e87  pop     rsi
0x180025e88  pop     rbx
0x180025e89  pop     rbp
0x180025e8a  retn
```
