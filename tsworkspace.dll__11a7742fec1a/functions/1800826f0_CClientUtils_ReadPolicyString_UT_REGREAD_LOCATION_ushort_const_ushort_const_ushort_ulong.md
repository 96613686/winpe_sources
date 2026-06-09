# CClientUtils::ReadPolicyString(UT_REGREAD_LOCATION,ushort const *,ushort const *,ushort *,ulong)

- ea: `0x1800826f0`
- end: `0x180082861`
- name: `?ReadPolicyString@CClientUtils@@UEAAJW4UT_REGREAD_LOCATION@@PEBG1PEAGK@Z`
- size: `369`
- prototype: `int __high(enum UT_REGREAD_LOCATION, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000b1d8`
- `0x18000ec94`
- `0x1800826f0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800827e7`
- `ADVAPI32!RegQueryValueExW` at `0x1800827e7`
- `ADVAPI32!RegCloseKey` at `0x1800827f4`
- `ADVAPI32!RegCloseKey` at `0x1800827f4`
- `ADVAPI32!RegOpenKeyExW` at `0x18008273b`
- `ADVAPI32!RegOpenKeyExW` at `0x18008273b`

## pseudocode

```c
__int64 __fastcall CClientUtils::ReadPolicyString(
        __int64 a1,
        int a2,
        const WCHAR *a3,
        const WCHAR *a4,
        LPBYTE lpcbData,
        int a6)
{
  BYTE *lpData; // rdi
  LSTATUS v8; // eax
  LSTATUS v9; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v11; // rdx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+10h] BYREF

  lpData = lpcbData;
  hKey = 0;
  *(_WORD *)lpcbData = 0;
  v8 = RegOpenKeyExW((HKEY)((a2 != 0) - 0x7FFFFFFFLL), a3, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 == 2 || v8 == 5 )
    return 1;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 47;
LABEL_8:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
        CurrentThreadActivityIdPrefix,
        v9);
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  LODWORD(lpcbData) = 2 * a6;
  Type = 0;
  v9 = RegQueryValueExW(hKey, a4, 0, &Type, lpData, (LPDWORD)&lpcbData);
  RegCloseKey(hKey);
  if ( v9 == 2 || v9 == 5 )
    return 1;
  if ( !v9 )
    return Type != 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 48;
    goto LABEL_8;
  }
LABEL_9:
  if ( v9 > 0 )
    return (unsigned __int16)v9 | 0x80070000;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800826f0  mov     r11, rsp
0x1800826f3  mov     [r11+8], rbx
0x1800826f7  mov     [r11+18h], rsi
0x1800826fb  push    rdi
0x1800826fc  sub     rsp, 40h
0x180082700  mov     rdi, [rsp+48h+arg_20]
0x180082705  xor     eax, eax
0x180082707  neg     edx
0x180082709  mov     qword ptr [r11-18h], 0
0x180082711  mov     r10, r8
0x180082714  mov     rsi, r9
0x180082717  sbb     rcx, rcx
0x18008271a  mov     r9d, 20019h; samDesired
0x180082720  neg     rcx
0x180082723  mov     [rdi], ax
0x180082726  lea     rax, [r11-18h]
0x18008272a  add     rcx, 0FFFFFFFF80000001h; hKey
0x180082731  xor     r8d, r8d; ulOptions
0x180082734  mov     [r11-28h], rax
0x180082738  mov     rdx, r10; lpSubKey
0x18008273b  call    cs:__imp_RegOpenKeyExW
0x180082741  mov     ebx, eax
0x180082743  cmp     eax, 2
0x180082746  jz      loc_18008284A
0x18008274c  cmp     eax, 5
0x18008274f  jz      loc_18008284A
0x180082755  test    eax, eax
0x180082757  jz      short loc_1800827B6
0x180082759  mov     rax, cs:WPP_GLOBAL_Control
0x180082760  lea     rcx, WPP_GLOBAL_Control
0x180082767  cmp     rax, rcx
0x18008276a  jz      short loc_1800827A0
0x18008276c  test    byte ptr [rax+1Ch], 8
0x180082770  jz      short loc_1800827A0
0x180082772  cmp     byte ptr [rax+19h], 2
0x180082776  jb      short loc_1800827A0
0x180082778  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008277d  mov     edx, 2Fh ; '/'
0x180082782  mov     rcx, cs:WPP_GLOBAL_Control
0x180082789  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180082790  mov     r9d, eax
0x180082793  mov     dword ptr [rsp+48h+lpData], ebx
0x180082797  mov     rcx, [rcx+10h]
0x18008279b  call    WPP_SF_Dd
0x1800827a0  test    ebx, ebx
0x1800827a2  jle     loc_18008284F
0x1800827a8  movzx   ebx, bx
0x1800827ab  or      ebx, 80070000h
0x1800827b1  jmp     loc_18008284F
0x1800827b6  mov     eax, [rsp+48h+arg_28]
0x1800827ba  lea     r9, [rsp+48h+Type]; lpType
0x1800827bf  mov     rcx, [rsp+48h+hKey]; hKey
0x1800827c4  add     eax, eax
0x1800827c6  mov     dword ptr [rsp+48h+arg_20], eax
0x1800827ca  xor     r8d, r8d; lpReserved
0x1800827cd  lea     rax, [rsp+48h+arg_20]
0x1800827d2  mov     [rsp+48h+Type], 0
0x1800827da  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800827df  mov     rdx, rsi; lpValueName
0x1800827e2  mov     [rsp+48h+lpData], rdi; lpData
0x1800827e7  call    cs:__imp_RegQueryValueExW
0x1800827ed  mov     rcx, [rsp+48h+hKey]; hKey
0x1800827f2  mov     ebx, eax
0x1800827f4  call    cs:__imp_RegCloseKey
0x1800827fa  cmp     ebx, 2
0x1800827fd  jz      short loc_18008284A
0x1800827ff  cmp     ebx, 5
0x180082802  jz      short loc_18008284A
0x180082804  test    ebx, ebx
0x180082806  jz      short loc_18008283E
0x180082808  mov     rax, cs:WPP_GLOBAL_Control
0x18008280f  lea     rcx, WPP_GLOBAL_Control
0x180082816  cmp     rax, rcx
0x180082819  jz      short loc_1800827A0
0x18008281b  test    byte ptr [rax+1Ch], 8
0x18008281f  jz      loc_1800827A0
0x180082825  cmp     byte ptr [rax+19h], 2
0x180082829  jb      loc_1800827A0
0x18008282f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180082834  mov     edx, 30h ; '0'
0x180082839  jmp     loc_180082782
0x18008283e  xor     ebx, ebx
0x180082840  cmp     [rsp+48h+Type], 1
0x180082845  setnz   bl
0x180082848  jmp     short loc_18008284F
0x18008284a  mov     ebx, 1
0x18008284f  mov     rsi, [rsp+48h+arg_10]
0x180082854  mov     eax, ebx
0x180082856  mov     rbx, [rsp+48h+arg_0]
0x18008285b  add     rsp, 40h
0x18008285f  pop     rdi
0x180082860  retn
```
