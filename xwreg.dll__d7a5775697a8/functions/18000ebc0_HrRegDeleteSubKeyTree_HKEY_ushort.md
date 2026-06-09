# HrRegDeleteSubKeyTree(HKEY__ *,ushort *)

- ea: `0x18000ebc0`
- end: `0x18000edfe`
- name: `?HrRegDeleteSubKeyTree@@YAJPEAUHKEY__@@PEAG@Z`
- size: `574`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180007b28`
- `0x1800099b4`
- `0x18000c240`
- `0x18000dd3c`
- `0x18000ebc0`
- `0x18000f484`

## callees

- `0x180007820`
- `0x18000abbc`
- `0x18000ace0`
- `0x18000ebc0`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ec0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ec0e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000ec67`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000ec67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ecfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ecfa`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000ed4a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000ed4a`

## pseudocode

```c
__int64 __fastcall HrRegDeleteSubKeyTree(HKEY a1, unsigned __int16 *a2)
{
  LSTATUS v4; // eax
  struct _FILETIME v5; // rbx
  LSTATUS v6; // eax
  LSTATUS v7; // edi
  int v8; // eax
  PVOID *v9; // rcx
  DWORD *phkResult; // [rsp+20h] [rbp-E0h]
  WCHAR *lpClass; // [rsp+28h] [rbp-D8h]
  DWORD *lpcchClass; // [rsp+30h] [rbp-D0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0x2000Eu, &hKey);
  v5 = (struct _FILETIME)(unsigned int)v4;
  if ( !v4 )
  {
    memset_0(Name, 0, 0x20Au);
    ftLastWriteTime = v5;
    lpcchClass = (DWORD *)v5;
    lpClass = (WCHAR *)v5;
    for ( phkResult = (DWORD *)v5; ; phkResult = 0 )
    {
      cchName = 261;
      v6 = RegEnumKeyExW(hKey, 0, Name, &cchName, phkResult, lpClass, lpcchClass, &ftLastWriteTime);
      v7 = v6;
      if ( v6 )
      {
        if ( v6 != 234 )
          break;
      }
      v8 = HrRegDeleteSubKeyTree(hKey, Name);
      v5.dwLowDateTime = v8;
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
            (_DWORD)a2,
            (__int64)Name,
            v8);
        break;
      }
      lpcchClass = 0;
      lpClass = 0;
    }
    RegCloseKey(hKey);
    if ( (v5.dwLowDateTime & 0x80000000) == 0 )
    {
      if ( !v7 || v7 == 259 )
      {
        v7 = RegDeleteKeyW(a1, a2);
      }
      else
      {
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_18;
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
          (_DWORD)a2,
          v5.dwLowDateTime);
      }
      v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_18:
      if ( v7 > 0 )
        v5.dwLowDateTime = (unsigned __int16)v7 | 0x80070000;
      else
        v5.dwLowDateTime = v7;
LABEL_27:
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
        WPP_SF_D(v9[2], 38, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v5.dwLowDateTime);
      return v5.dwLowDateTime;
    }
LABEL_26:
    v9 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  if ( v4 > 0 )
    v5.dwLowDateTime = (unsigned __int16)v4 | 0x80070000;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_27;
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (_DWORD)a2,
      v5.dwLowDateTime);
    goto LABEL_26;
  }
  return v5.dwLowDateTime;
}

```

## disassembly

```asm
0x18000ebc0  mov     [rsp-8+arg_10], rbx
0x18000ebc5  push    rbp
0x18000ebc6  push    rsi
0x18000ebc7  push    rdi
0x18000ebc8  push    r14
0x18000ebca  push    r15
0x18000ebcc  lea     rbp, [rsp-180h]
0x18000ebd4  sub     rsp, 280h
0x18000ebdb  mov     rax, cs:__security_cookie
0x18000ebe2  xor     rax, rsp
0x18000ebe5  mov     [rbp+1A0h+var_30], rax
0x18000ebec  lea     rax, [rsp+2A0h+hKey]
0x18000ebf1  mov     [rsp+2A0h+hKey], 0
0x18000ebfa  mov     r9d, 2000Eh; samDesired
0x18000ec00  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18000ec05  xor     r8d, r8d; ulOptions
0x18000ec08  mov     r14, rdx
0x18000ec0b  mov     r15, rcx
0x18000ec0e  call    cs:__imp_RegOpenKeyExW
0x18000ec14  mov     ebx, eax
0x18000ec16  test    eax, eax
0x18000ec18  jnz     loc_18000ED6C
0x18000ec1e  xor     edx, edx; Val
0x18000ec20  lea     rcx, [rsp+2A0h+Name]; void *
0x18000ec25  mov     r8d, 20Ah; Size
0x18000ec2b  call    memset_0
0x18000ec30  lea     rax, [rsp+2A0h+ftLastWriteTime]
0x18000ec35  mov     qword ptr [rsp+2A0h+ftLastWriteTime.dwLowDateTime], rbx
0x18000ec3a  mov     [rsp+2A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000ec3f  mov     [rsp+2A0h+lpcchClass], rbx; lpcchClass
0x18000ec44  mov     [rsp+2A0h+lpClass], rbx; lpClass
0x18000ec49  mov     [rsp+2A0h+phkResult], rbx; lpReserved
0x18000ec4e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000ec53  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x18000ec58  lea     r8, [rsp+2A0h+Name]; lpName
0x18000ec5d  mov     [rsp+2A0h+cchName], 105h
0x18000ec65  xor     edx, edx; dwIndex
0x18000ec67  call    cs:__imp_RegEnumKeyExW
0x18000ec6d  lea     rsi, WPP_GLOBAL_Control
0x18000ec74  mov     edi, eax
0x18000ec76  test    eax, eax
0x18000ec78  jz      short loc_18000EC81
0x18000ec7a  cmp     eax, 0EAh
0x18000ec7f  jnz     short loc_18000ECF5
0x18000ec81  mov     rcx, [rsp+2A0h+hKey]; HKEY
0x18000ec86  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x18000ec8b  call    ?HrRegDeleteSubKeyTree@@YAJPEAUHKEY__@@PEAG@Z; HrRegDeleteSubKeyTree(HKEY__ *,ushort *)
0x18000ec90  mov     ebx, eax
0x18000ec92  test    eax, eax
0x18000ec94  js      short loc_18000ECBD
0x18000ec96  lea     rax, [rsp+2A0h+ftLastWriteTime]
0x18000ec9b  mov     [rsp+2A0h+lpftLastWriteTime], rax
0x18000eca0  mov     [rsp+2A0h+lpcchClass], 0
0x18000eca9  mov     [rsp+2A0h+lpClass], 0
0x18000ecb2  mov     [rsp+2A0h+phkResult], 0
0x18000ecbb  jmp     short loc_18000EC4E
0x18000ecbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecc4  cmp     rcx, rsi
0x18000ecc7  jz      short loc_18000ECF5
0x18000ecc9  test    byte ptr [rcx+1Ch], 4
0x18000eccd  jz      short loc_18000ECF5
0x18000eccf  mov     rcx, [rcx+10h]
0x18000ecd3  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000ecda  mov     dword ptr [rsp+2A0h+lpClass], eax
0x18000ecde  mov     edx, 23h ; '#'
0x18000ece3  lea     rax, [rsp+2A0h+Name]
0x18000ece8  mov     r9, r14
0x18000eceb  mov     [rsp+2A0h+phkResult], rax
0x18000ecf0  call    WPP_SF_SSD
0x18000ecf5  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000ecfa  call    cs:__imp_RegCloseKey
0x18000ed00  test    ebx, ebx
0x18000ed02  js      loc_18000EDAC
0x18000ed08  test    edi, edi
0x18000ed0a  jz      short loc_18000ED44
0x18000ed0c  cmp     edi, 103h
0x18000ed12  jz      short loc_18000ED44
0x18000ed14  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed1b  cmp     rcx, rsi
0x18000ed1e  jz      short loc_18000ED59
0x18000ed20  test    byte ptr [rcx+1Ch], 4
0x18000ed24  jz      short loc_18000ED59
0x18000ed26  mov     rcx, [rcx+10h]
0x18000ed2a  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000ed31  mov     edx, 24h ; '$'
0x18000ed36  mov     dword ptr [rsp+2A0h+phkResult], ebx
0x18000ed3a  mov     r9, r14
0x18000ed3d  call    WPP_SF_SD
0x18000ed42  jmp     short loc_18000ED52
0x18000ed44  mov     rdx, r14; lpSubKey
0x18000ed47  mov     rcx, r15; hKey
0x18000ed4a  call    cs:__imp_RegDeleteKeyW
0x18000ed50  mov     edi, eax
0x18000ed52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed59  test    edi, edi
0x18000ed5b  jg      short loc_18000ED61
0x18000ed5d  mov     ebx, edi
0x18000ed5f  jmp     short loc_18000EDB3
0x18000ed61  movzx   ebx, di
0x18000ed64  or      ebx, 80070000h
0x18000ed6a  jmp     short loc_18000EDB3
0x18000ed6c  jle     short loc_18000ED77
0x18000ed6e  movzx   ebx, ax
0x18000ed71  or      ebx, 80070000h
0x18000ed77  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed7e  lea     rsi, WPP_GLOBAL_Control
0x18000ed85  cmp     rcx, rsi
0x18000ed88  jz      short loc_18000EDD6
0x18000ed8a  test    byte ptr [rcx+1Ch], 10h
0x18000ed8e  jz      short loc_18000EDB3
0x18000ed90  mov     rcx, [rcx+10h]
0x18000ed94  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000ed9b  mov     edx, 25h ; '%'
0x18000eda0  mov     dword ptr [rsp+2A0h+phkResult], ebx
0x18000eda4  mov     r9, r14
0x18000eda7  call    WPP_SF_SD
0x18000edac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edb3  cmp     rcx, rsi
0x18000edb6  jz      short loc_18000EDD6
0x18000edb8  test    byte ptr [rcx+1Ch], 10h
0x18000edbc  jz      short loc_18000EDD6
0x18000edbe  mov     rcx, [rcx+10h]
0x18000edc2  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000edc9  mov     edx, 26h ; '&'
0x18000edce  mov     r9d, ebx
0x18000edd1  call    WPP_SF_D
0x18000edd6  mov     eax, ebx
0x18000edd8  mov     rcx, [rbp+1A0h+var_30]
0x18000eddf  xor     rcx, rsp; StackCookie
0x18000ede2  call    __security_check_cookie
0x18000ede7  mov     rbx, [rsp+2A0h+arg_10]
0x18000edef  add     rsp, 280h
0x18000edf6  pop     r15
0x18000edf8  pop     r14
0x18000edfa  pop     rdi
0x18000edfb  pop     rsi
0x18000edfc  pop     rbp
0x18000edfd  retn
```
