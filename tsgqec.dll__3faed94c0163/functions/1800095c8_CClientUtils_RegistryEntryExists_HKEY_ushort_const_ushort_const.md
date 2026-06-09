# CClientUtils::RegistryEntryExists(HKEY__ *,ushort const *,ushort const *)

- ea: `0x1800095c8`
- end: `0x1800097a3`
- name: `?RegistryEntryExists@CClientUtils@@KAHPEAUHKEY__@@PEBG1@Z`
- size: `475`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800097b0`
- `0x1800097e0`
- `0x180009960`

## callees

- `0x180003970`
- `0x180007f84`
- `0x1800095c8`
- `0x18000a7b8`
- `0x18000a858`
- `0x18000aea0`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x18000971b`
- `ADVAPI32!RegEnumValueW` at `0x18000971b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000962f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000962f`
- `ADVAPI32!RegCloseKey` at `0x18000972c`
- `ADVAPI32!RegCloseKey` at `0x18000972c`

## pseudocode

```c
__int64 __fastcall CClientUtils::RegistryEntryExists(HKEY hKey, const unsigned __int16 *a2, char *a3)
{
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  char v7; // di
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // r8d
  DWORD i; // edx
  WCHAR *v11; // rax
  int v12; // r8d
  int v13; // edx
  LSTATUS v14; // edi
  unsigned int v15; // eax
  __int64 v16; // r8
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[272]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[272]; // [rsp+270h] [rbp+170h] BYREF

  hKeya = 0;
  cchValueName = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  v5 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &hKeya);
  v6 = 0;
  v7 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v9, CurrentThreadActivityIdPrefix, (__int64)SubKey, v7);
    }
  }
  else
  {
    for ( i = 0; ; i = v6 )
    {
      cchValueName = 265;
      if ( RegEnumValueW(hKeya, i, ValueName, &cchValueName, 0, 0, 0, 0) )
      {
        v6 = 0;
        goto LABEL_14;
      }
      v11 = ValueName;
      do
      {
        v12 = *(WCHAR *)((char *)v11 + a3 - (char *)ValueName);
        v13 = *v11 - v12;
        if ( v13 )
          break;
        ++v11;
      }
      while ( v12 );
      if ( !v13 )
        break;
      ++v6;
    }
    v6 = 1;
LABEL_14:
    v14 = RegCloseKey(hKeya);
    if ( v14
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v16, v15, v14);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800095c8  mov     [rsp-8+arg_10], rbx
0x1800095cd  push    rbp
0x1800095ce  push    rsi
0x1800095cf  push    rdi
0x1800095d0  lea     rbp, [rsp-3A0h]
0x1800095d8  sub     rsp, 4A0h
0x1800095df  mov     rax, cs:__security_cookie
0x1800095e6  xor     rax, rsp
0x1800095e9  mov     [rbp+3B0h+var_20], rax
0x1800095f0  mov     rsi, r8
0x1800095f3  mov     [rsp+4B0h+hKey], 0
0x1800095fc  mov     rbx, rcx
0x1800095ff  mov     [rsp+4B0h+cchValueName], 0
0x180009607  mov     r8, rdx; unsigned __int16 *
0x18000960a  lea     rcx, [rsp+4B0h+SubKey]; unsigned __int16 *
0x18000960f  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x180009614  lea     rax, [rsp+4B0h+hKey]
0x180009619  mov     r9d, 20019h; samDesired
0x18000961f  xor     r8d, r8d; ulOptions
0x180009622  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180009627  lea     rdx, [rsp+4B0h+SubKey]; lpSubKey
0x18000962c  mov     rcx, rbx; hKey
0x18000962f  call    cs:__imp_RegOpenKeyExW
0x180009635  xor     ebx, ebx
0x180009637  mov     edi, eax
0x180009639  test    eax, eax
0x18000963b  jz      short loc_180009696
0x18000963d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009644  lea     rdx, WPP_GLOBAL_Control
0x18000964b  cmp     rcx, rdx
0x18000964e  jz      loc_180009778
0x180009654  test    byte ptr [rcx+1Ch], 1
0x180009658  jz      loc_180009778
0x18000965e  cmp     byte ptr [rcx+19h], 4
0x180009662  jb      loc_180009778
0x180009668  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000966d  lea     rcx, [rsp+4B0h+SubKey]
0x180009672  mov     dword ptr [rsp+4B0h+lpType], edi
0x180009676  mov     [rsp+4B0h+phkResult], rcx
0x18000967b  lea     edx, [rbx+0Ah]
0x18000967e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009685  mov     r9d, eax
0x180009688  mov     rcx, [rcx+10h]
0x18000968c  call    WPP_SF_DSd
0x180009691  jmp     loc_180009778
0x180009696  mov     [rsp+4B0h+lpcbData], rbx
0x18000969b  mov     edi, 109h
0x1800096a0  mov     [rsp+4B0h+lpData], rbx
0x1800096a5  xor     edx, edx
0x1800096a7  mov     [rsp+4B0h+lpType], rbx
0x1800096ac  mov     [rsp+4B0h+phkResult], rbx
0x1800096b1  jmp     short loc_180009706
0x1800096b3  lea     rax, [rbp+3B0h+ValueName]
0x1800096ba  mov     rcx, rsi
0x1800096bd  sub     rcx, rax
0x1800096c0  movzx   edx, word ptr [rax]
0x1800096c3  movzx   r8d, word ptr [rax+rcx]
0x1800096c8  sub     edx, r8d
0x1800096cb  jnz     short loc_1800096D6
0x1800096cd  add     rax, 2
0x1800096d1  test    r8d, r8d
0x1800096d4  jnz     short loc_1800096C0
0x1800096d6  test    edx, edx
0x1800096d8  jz      loc_18000979C
0x1800096de  mov     [rsp+4B0h+lpcbData], 0; lpcbData
0x1800096e7  inc     ebx
0x1800096e9  mov     [rsp+4B0h+lpData], 0; lpData
0x1800096f2  mov     edx, ebx; dwIndex
0x1800096f4  mov     [rsp+4B0h+lpType], 0; lpType
0x1800096fd  mov     [rsp+4B0h+phkResult], 0; lpReserved
0x180009706  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000970b  lea     r9, [rsp+4B0h+cchValueName]; lpcchValueName
0x180009710  lea     r8, [rbp+3B0h+ValueName]; lpValueName
0x180009717  mov     [rsp+4B0h+cchValueName], edi
0x18000971b  call    cs:__imp_RegEnumValueW
0x180009721  test    eax, eax
0x180009723  jz      short loc_1800096B3
0x180009725  xor     ebx, ebx
0x180009727  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000972c  call    cs:__imp_RegCloseKey
0x180009732  mov     edi, eax
0x180009734  test    eax, eax
0x180009736  jz      short loc_180009778
0x180009738  mov     rcx, cs:WPP_GLOBAL_Control
0x18000973f  lea     rdx, WPP_GLOBAL_Control
0x180009746  cmp     rcx, rdx
0x180009749  jz      short loc_180009778
0x18000974b  test    byte ptr [rcx+1Ch], 1
0x18000974f  jz      short loc_180009778
0x180009751  cmp     byte ptr [rcx+19h], 2
0x180009755  jb      short loc_180009778
0x180009757  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000975c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009763  mov     edx, 0Bh
0x180009768  mov     r9d, eax
0x18000976b  mov     dword ptr [rsp+4B0h+phkResult], edi
0x18000976f  mov     rcx, [rcx+10h]
0x180009773  call    WPP_SF_Dl
0x180009778  mov     eax, ebx
0x18000977a  mov     rcx, [rbp+3B0h+var_20]
0x180009781  xor     rcx, rsp; StackCookie
0x180009784  call    __security_check_cookie
0x180009789  mov     rbx, [rsp+4B0h+arg_10]
0x180009791  add     rsp, 4A0h
0x180009798  pop     rdi
0x180009799  pop     rsi
0x18000979a  pop     rbp
0x18000979b  retn
0x18000979c  mov     ebx, 1
0x1800097a1  jmp     short loc_180009727
```
