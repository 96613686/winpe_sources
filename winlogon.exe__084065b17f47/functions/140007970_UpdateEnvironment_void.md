# UpdateEnvironment(void * *)

- ea: `0x140007970`
- end: `0x140007e1c`
- name: `?UpdateEnvironment@@YAKPEAPEAX@Z`
- size: `1196`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x140007510`
- `0x14004e838`

## callees

- `0x1400057f4`
- `0x140007970`
- `0x140008370`
- `0x140008550`
- `0x14001a200`
- `0x140041c34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007a89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007ad4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007a89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007ad4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007c5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007c5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007a78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007ac3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007c4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007a78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007ac3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007c4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007da3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007a60`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007a60`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140007b4e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140007bf0`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140007b4e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140007bf0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400079dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400079dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007df6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009cf72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007df6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14009cf72`

## pseudocode

```c
__int64 __fastcall UpdateEnvironment(void **a1)
{
  void *v2; // r14
  _WORD *v3; // rsi
  unsigned int v4; // edi
  __int64 v5; // r9
  unsigned int v6; // eax
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v9; // eax
  SIZE_T v10; // rbx
  HANDLE v11; // rax
  DWORD i; // ebx
  DWORD v13; // eax
  int v14; // r9d
  DWORD v15; // ebx
  unsigned __int16 *v16; // r15
  int v17; // r9d
  HANDLE v18; // rax
  DWORD LastError; // eax
  DWORD v20; // eax
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-74h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-70h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-6Ch] BYREF
  DWORD v25; // [rsp+70h] [rbp-68h]
  DWORD cValues; // [rsp+74h] [rbp-64h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-60h] BYREF
  void *v28; // [rsp+80h] [rbp-58h] BYREF
  void *v29; // [rsp+88h] [rbp-50h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+90h] [rbp-48h] BYREF
  DWORD cbData; // [rsp+E8h] [rbp+10h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+F0h] [rbp+18h] BYREF
  DWORD cSubKeys; // [rsp+F8h] [rbp+20h] BYREF

  hKey = 0;
  cchValueName = 0;
  Type = 0;
  cbData = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cSubKeys = 0;
  ftLastWriteTime = 0;
  v2 = 0;
  v28 = 0;
  v3 = 0;
  v29 = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Session Manager\\Environment",
         0,
         1u,
         &hKey);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_1548da81bc2035b30c7c377f18831895_Traceguids, v5);
    }
  }
  else
  {
    v6 = RegQueryInfoKeyW(
           hKey,
           0,
           0,
           0,
           &cSubKeys,
           &cSubKeys,
           &cSubKeys,
           &cValues,
           &cbMaxValueNameLen,
           &cbMaxValueLen,
           &cSubKeys,
           &ftLastWriteTime);
    v4 = v6;
    if ( !v6 || v6 == 234 )
    {
      v7 = cbMaxValueLen;
      ProcessHeap = GetProcessHeap();
      v3 = HeapAlloc(ProcessHeap, 8u, v7);
      v29 = v3;
      if ( !v3 )
        goto LABEL_24;
      v9 = cbMaxValueNameLen;
      if ( cbMaxValueNameLen > 0x1000 )
      {
        v4 = 24;
        goto LABEL_43;
      }
      ++cbMaxValueNameLen;
      v10 = 2LL * (v9 + 1);
      v11 = GetProcessHeap();
      v2 = HeapAlloc(v11, 8u, v10);
      v28 = v2;
      if ( !v2 )
      {
LABEL_24:
        v4 = 14;
        goto LABEL_43;
      }
      for ( i = 0; ; ++i )
      {
        v25 = i;
        v13 = cValues;
        if ( i >= cValues )
          break;
        cchValueName = cbMaxValueNameLen;
        cbData = cbMaxValueLen;
        v4 = RegEnumValueW(hKey, i, (LPWSTR)v2, &cchValueName, 0, &Type, (LPBYTE)v3, &cbData);
        if ( v4 )
          goto LABEL_43;
        if ( cbData >= 0x2000 )
          v3[4095] = 0;
        if ( Type == 1
          && !(unsigned int)SetUserEnvironmentVariable(a1, (const unsigned __int16 *)v2, v3, v14)
          && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_1548da81bc2035b30c7c377f18831895_Traceguids, LastError);
        }
      }
      v15 = 0;
      v25 = 0;
      while ( v15 < v13 )
      {
        cchValueName = cbMaxValueNameLen;
        cbData = cbMaxValueLen;
        v4 = RegEnumValueW(hKey, v15, (LPWSTR)v2, &cchValueName, 0, &Type, (LPBYTE)v3, &cbData);
        if ( v4 )
          break;
        if ( cbData >= 0x2000 )
          v3[4095] = 0;
        if ( Type == 2 )
        {
          v16 = AllocAndExpandEnvironmentStrings(v3);
          if ( !(unsigned int)SetUserEnvironmentVariable(a1, (const unsigned __int16 *)v2, v16, v17)
            && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v20 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_1548da81bc2035b30c7c377f18831895_Traceguids, v20);
          }
          v18 = GetProcessHeap();
          HeapFree(v18, 0, v16);
        }
        v25 = ++v15;
        v13 = cValues;
      }
    }
    else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_1548da81bc2035b30c7c377f18831895_Traceguids, v6);
    }
  }
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v2 )
    UHHeapFree(&v28);
  if ( v3 )
    UHHeapFree(&v29);
  return v4;
}

```

## disassembly

```asm
0x140007970  mov     rax, rsp
0x140007973  push    rbx
0x140007974  push    rsi
0x140007975  push    rdi
0x140007976  push    r12
0x140007978  push    r13
0x14000797a  push    r14
0x14000797c  push    r15
0x14000797e  sub     rsp, 0A0h
0x140007985  mov     r12, rcx
0x140007988  xor     r15d, r15d
0x14000798b  mov     [rax-60h], r15
0x14000798f  mov     [rax-70h], r15d
0x140007993  mov     [rax-6Ch], r15d
0x140007997  mov     [rax+10h], r15d
0x14000799b  mov     [rax-64h], r15d
0x14000799f  mov     [rax+18h], r15d
0x1400079a3  mov     [rax-74h], r15d
0x1400079a7  mov     [rax+20h], r15d
0x1400079ab  mov     [rax-48h], r15
0x1400079af  mov     r14d, r15d
0x1400079b2  mov     [rax-58h], r15
0x1400079b6  mov     esi, r15d
0x1400079b9  mov     [rax-50h], r15
0x1400079bd  lea     rax, [rax-60h]
0x1400079c1  mov     [rsp+0D8h+phkResult], rax; phkResult
0x1400079c6  mov     r9d, 1; samDesired
0x1400079cc  xor     r8d, r8d; ulOptions
0x1400079cf  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ses"...
0x1400079d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400079dd  call    cs:__imp_RegOpenKeyExW
0x1400079e3  mov     edi, eax
0x1400079e5  mov     [rsp+0D8h+var_78], eax
0x1400079e9  test    eax, eax
0x1400079eb  jnz     loc_140007C73
0x1400079f1  lea     rax, [rsp+0D8h+ftLastWriteTime]
0x1400079f9  mov     [rsp+0D8h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1400079fe  lea     rax, [rsp+0D8h+cSubKeys]
0x140007a06  mov     [rsp+0D8h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x140007a0b  lea     rax, [rsp+0D8h+cbMaxValueLen]
0x140007a10  mov     [rsp+0D8h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x140007a15  lea     rax, [rsp+0D8h+cbMaxValueNameLen]
0x140007a1d  mov     [rsp+0D8h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140007a22  lea     rax, [rsp+0D8h+cValues]
0x140007a27  mov     [rsp+0D8h+lpcValues], rax; lpcValues
0x140007a2c  lea     rax, [rsp+0D8h+cSubKeys]
0x140007a34  mov     [rsp+0D8h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x140007a39  lea     rax, [rsp+0D8h+cSubKeys]
0x140007a41  mov     [rsp+0D8h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140007a46  lea     rax, [rsp+0D8h+cSubKeys]
0x140007a4e  mov     [rsp+0D8h+phkResult], rax; lpcSubKeys
0x140007a53  xor     r9d, r9d; lpReserved
0x140007a56  xor     r8d, r8d; lpcchClass
0x140007a59  xor     edx, edx; lpClass
0x140007a5b  mov     rcx, [rsp+0D8h+hKey]; hKey
0x140007a60  call    cs:__imp_RegQueryInfoKeyW
0x140007a66  mov     edi, eax
0x140007a68  mov     [rsp+0D8h+var_78], eax
0x140007a6c  test    eax, eax
0x140007a6e  jnz     loc_140007CB8
0x140007a74  mov     ebx, [rsp+0D8h+cbMaxValueLen]
0x140007a78  call    cs:__imp_GetProcessHeap
0x140007a7e  mov     rcx, rax; hHeap
0x140007a81  mov     r8d, ebx; dwBytes
0x140007a84  mov     edx, 8; dwFlags
0x140007a89  call    cs:__imp_HeapAlloc
0x140007a8f  mov     rsi, rax
0x140007a92  mov     [rsp+0D8h+var_50], rax
0x140007a9a  test    rax, rax
0x140007a9d  jz      loc_140007C65
0x140007aa3  mov     eax, [rsp+0D8h+cbMaxValueNameLen]
0x140007aaa  cmp     eax, 1000h
0x140007aaf  ja      loc_140007D0B
0x140007ab5  inc     eax
0x140007ab7  mov     [rsp+0D8h+cbMaxValueNameLen], eax
0x140007abe  mov     ebx, eax
0x140007ac0  add     rbx, rbx
0x140007ac3  call    cs:__imp_GetProcessHeap
0x140007ac9  mov     rcx, rax; hHeap
0x140007acc  mov     r8, rbx; dwBytes
0x140007acf  mov     edx, 8; dwFlags
0x140007ad4  call    cs:__imp_HeapAlloc
0x140007ada  mov     r14, rax
0x140007add  mov     [rsp+0D8h+var_58], rax
0x140007ae5  test    rax, rax
0x140007ae8  jz      loc_140007C65
0x140007aee  mov     ebx, r15d
0x140007af1  lea     r13, WPP_GLOBAL_Control
0x140007af8  mov     [rsp+0D8h+var_68], ebx
0x140007afc  mov     eax, [rsp+0D8h+cValues]
0x140007b00  cmp     ebx, eax
0x140007b02  jnb     loc_140007B9B
0x140007b08  mov     eax, [rsp+0D8h+cbMaxValueNameLen]
0x140007b0f  mov     [rsp+0D8h+cchValueName], eax
0x140007b13  mov     eax, [rsp+0D8h+cbMaxValueLen]
0x140007b17  mov     [rsp+0D8h+cbData], eax
0x140007b1e  lea     rax, [rsp+0D8h+cbData]
0x140007b26  mov     [rsp+0D8h+lpcValues], rax; lpcbData
0x140007b2b  mov     [rsp+0D8h+lpcbMaxClassLen], rsi; lpData
0x140007b30  lea     rax, [rsp+0D8h+Type]
0x140007b35  mov     [rsp+0D8h+lpcbMaxSubKeyLen], rax; lpType
0x140007b3a  mov     [rsp+0D8h+phkResult], r15; lpReserved
0x140007b3f  lea     r9, [rsp+0D8h+cchValueName]; lpcchValueName
0x140007b44  mov     r8, r14; lpValueName
0x140007b47  mov     edx, ebx; dwIndex
0x140007b49  mov     rcx, [rsp+0D8h+hKey]; hKey
0x140007b4e  call    cs:__imp_RegEnumValueW
0x140007b54  mov     edi, eax
0x140007b56  mov     [rsp+0D8h+var_78], eax
0x140007b5a  test    eax, eax
0x140007b5c  jnz     loc_140007DCD
0x140007b62  cmp     [rsp+0D8h+cbData], 2000h
0x140007b6d  jnb     loc_140007D15
0x140007b73  mov     eax, [rsp+0D8h+Type]
0x140007b77  sub     eax, 1
0x140007b7a  jz      short loc_140007B83
0x140007b7c  inc     ebx
0x140007b7e  jmp     loc_140007AF8
0x140007b83  mov     r8, rsi; unsigned __int16 *
0x140007b86  mov     rdx, r14; unsigned __int16 *
0x140007b89  mov     rcx, r12; void **
0x140007b8c  call    ?SetUserEnvironmentVariable@@YAHPEAPEAXPEBG1H@Z; SetUserEnvironmentVariable(void * *,ushort const *,ushort const *,int)
0x140007b91  test    eax, eax
0x140007b93  jz      loc_140007D22
0x140007b99  jmp     short loc_140007B7C
0x140007b9b  mov     ebx, r15d
0x140007b9e  mov     [rsp+0D8h+var_68], ebx
0x140007ba2  cmp     ebx, eax
0x140007ba4  jnb     loc_140007DCD
0x140007baa  mov     eax, [rsp+0D8h+cbMaxValueNameLen]
0x140007bb1  mov     [rsp+0D8h+cchValueName], eax
0x140007bb5  mov     eax, [rsp+0D8h+cbMaxValueLen]
0x140007bb9  mov     [rsp+0D8h+cbData], eax
0x140007bc0  lea     rax, [rsp+0D8h+cbData]
0x140007bc8  mov     [rsp+0D8h+lpcValues], rax; lpcbData
0x140007bcd  mov     [rsp+0D8h+lpcbMaxClassLen], rsi; lpData
0x140007bd2  lea     rax, [rsp+0D8h+Type]
0x140007bd7  mov     [rsp+0D8h+lpcbMaxSubKeyLen], rax; lpType
0x140007bdc  mov     [rsp+0D8h+phkResult], r15; lpReserved
0x140007be1  lea     r9, [rsp+0D8h+cchValueName]; lpcchValueName
0x140007be6  mov     r8, r14; lpValueName
0x140007be9  mov     edx, ebx; dwIndex
0x140007beb  mov     rcx, [rsp+0D8h+hKey]; hKey
0x140007bf0  call    cs:__imp_RegEnumValueW
0x140007bf6  mov     edi, eax
0x140007bf8  mov     [rsp+0D8h+var_78], eax
0x140007bfc  test    eax, eax
0x140007bfe  jnz     loc_140007DCD
0x140007c04  cmp     [rsp+0D8h+cbData], 2000h
0x140007c0f  jnb     loc_140007D70
0x140007c15  cmp     [rsp+0D8h+Type], 2
0x140007c1a  jz      short loc_140007C2B
0x140007c1c  inc     ebx
0x140007c1e  mov     [rsp+0D8h+var_68], ebx
0x140007c22  mov     eax, [rsp+0D8h+cValues]
0x140007c26  jmp     loc_140007BA2
0x140007c2b  mov     rcx, rsi; lpSrc
0x140007c2e  call    ?AllocAndExpandEnvironmentStrings@@YAPEAGPEBG@Z; AllocAndExpandEnvironmentStrings(ushort const *)
0x140007c33  mov     r15, rax
0x140007c36  mov     r8, rax; unsigned __int16 *
0x140007c39  mov     rdx, r14; unsigned __int16 *
0x140007c3c  mov     rcx, r12; void **
0x140007c3f  call    ?SetUserEnvironmentVariable@@YAHPEAPEAXPEBG1H@Z; SetUserEnvironmentVariable(void * *,ushort const *,ushort const *,int)
0x140007c44  test    eax, eax
0x140007c46  jz      loc_140007D7F
0x140007c4c  call    cs:__imp_GetProcessHeap
0x140007c52  mov     r8, r15; lpMem
0x140007c55  xor     edx, edx; dwFlags
0x140007c57  mov     rcx, rax; hHeap
0x140007c5a  call    cs:__imp_HeapFree
0x140007c60  xor     r15d, r15d
0x140007c63  jmp     short loc_140007C1C
0x140007c65  mov     edi, 0Eh
0x140007c6a  mov     [rsp+0D8h+var_78], edi
0x140007c6e  jmp     loc_140007DCD
0x140007c73  lea     r13, WPP_GLOBAL_Control
0x140007c7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007c81  cmp     rcx, r13
0x140007c84  jz      loc_140007DCD
0x140007c8a  test    byte ptr [rcx+1Ch], 20h
0x140007c8e  jz      loc_140007DCD
0x140007c94  cmp     byte ptr [rcx+19h], 2
0x140007c98  jb      loc_140007DCD
0x140007c9e  mov     edx, 0Eh
0x140007ca3  lea     r8, WPP_1548da81bc2035b30c7c377f18831895_Traceguids
0x140007caa  mov     rcx, [rcx+10h]
0x140007cae  call    WPP_SF_
0x140007cb3  jmp     loc_140007DCD
0x140007cb8  cmp     eax, 0EAh
0x140007cbd  jz      loc_140007A74
0x140007cc3  lea     r13, WPP_GLOBAL_Control
0x140007cca  mov     rcx, cs:WPP_GLOBAL_Control
0x140007cd1  cmp     rcx, r13
0x140007cd4  jz      loc_140007DCD
0x140007cda  test    byte ptr [rcx+1Ch], 20h
0x140007cde  jz      loc_140007DCD
0x140007ce4  cmp     byte ptr [rcx+19h], 2
0x140007ce8  jb      loc_140007DCD
0x140007cee  mov     edx, 0Fh
0x140007cf3  mov     r9d, eax
0x140007cf6  lea     r8, WPP_1548da81bc2035b30c7c377f18831895_Traceguids
0x140007cfd  mov     rcx, [rcx+10h]
0x140007d01  call    WPP_SF_d
0x140007d06  jmp     loc_140007DCD
0x140007d0b  mov     edi, 18h
0x140007d10  jmp     loc_140007C6A
0x140007d15  mov     [rsi+1FFEh], r15w
0x140007d1d  jmp     loc_140007B73
0x140007d22  mov     rax, cs:WPP_GLOBAL_Control
0x140007d29  cmp     rax, r13
0x140007d2c  jz      loc_140007B99
0x140007d32  test    byte ptr [rax+1Ch], 20h
0x140007d36  jz      loc_140007B99
0x140007d3c  cmp     byte ptr [rax+19h], 2
0x140007d40  jb      loc_140007B99
0x140007d46  call    cs:__imp_GetLastError
0x140007d4c  mov     edx, 10h
0x140007d51  mov     r9d, eax
0x140007d54  lea     r8, WPP_1548da81bc2035b30c7c377f18831895_Traceguids
0x140007d5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d62  mov     rcx, [rcx+10h]
0x140007d66  call    WPP_SF_d
0x140007d6b  jmp     loc_140007B99
0x140007d70  mov     eax, r15d
0x140007d73  mov     [rsi+1FFEh], ax
0x140007d7a  jmp     loc_140007C15
0x140007d7f  mov     rax, cs:WPP_GLOBAL_Control
0x140007d86  cmp     rax, r13
0x140007d89  jz      loc_140007C4C
0x140007d8f  test    byte ptr [rax+1Ch], 20h
0x140007d93  jz      loc_140007C4C
0x140007d99  cmp     byte ptr [rax+19h], 2
0x140007d9d  jb      loc_140007C4C
0x140007da3  call    cs:__imp_GetLastError
0x140007da9  mov     edx, 11h
0x140007dae  mov     r9d, eax
0x140007db1  lea     r8, WPP_1548da81bc2035b30c7c377f18831895_Traceguids
0x140007db8  mov     rcx, cs:WPP_GLOBAL_Control
0x140007dbf  mov     rcx, [rcx+10h]
0x140007dc3  call    WPP_SF_d
0x140007dc8  jmp     loc_140007C4C
0x140007dcd  mov     rcx, [rsp+0D8h+hKey]; hKey
0x140007dd2  test    rcx, rcx
0x140007dd5  jnz     short loc_140007DF6
0x140007dd7  test    r14, r14
0x140007dda  jnz     short loc_140007DFE
0x140007ddc  test    rsi, rsi
0x140007ddf  jnz     short loc_140007E0D
0x140007de1  mov     eax, edi
0x140007de3  add     rsp, 0A0h
0x140007dea  pop     r15
0x140007dec  pop     r14
0x140007dee  pop     r13
0x140007df0  pop     r12
0x140007df2  pop     rdi
0x140007df3  pop     rsi
0x140007df4  pop     rbx
0x140007df5  retn
0x140007df6  call    cs:__imp_RegCloseKey
0x140007dfc  jmp     short loc_140007DD7
0x140007dfe  lea     rcx, [rsp+0D8h+var_58]
0x140007e06  call    UHHeapFree
0x140007e0b  jmp     short loc_140007DDC
0x140007e0d  lea     rcx, [rsp+0D8h+var_50]
0x140007e15  call    UHHeapFree
0x140007e1a  jmp     short loc_140007DE1
0x14009cf60  push    rbp
0x14009cf62  sub     rsp, 60h
0x14009cf66  mov     rbp, rdx
0x14009cf69  mov     rcx, [rbp+78h]; hKey
0x14009cf6d  test    rcx, rcx
0x14009cf70  jz      short loc_14009CF79
0x14009cf72  call    cs:__imp_RegCloseKey
0x14009cf78  nop
0x14009cf79  cmp     qword ptr [rbp+80h], 0
0x14009cf81  jz      short loc_14009CF90
0x14009cf83  lea     rcx, [rbp+80h]
0x14009cf8a  call    UHHeapFree
0x14009cf8f  nop
0x14009cf90  cmp     qword ptr [rbp+88h], 0
0x14009cf98  jz      short loc_14009CFA7
0x14009cf9a  lea     rcx, [rbp+88h]
0x14009cfa1  call    UHHeapFree
0x14009cfa6  nop
0x14009cfa7  add     rsp, 60h
0x14009cfab  pop     rbp
0x14009cfac  retn
```
