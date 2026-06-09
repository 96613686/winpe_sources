# CClientUtils::WriteRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar * const,int,long)

- ea: `0x180083c2c`
- end: `0x180083eec`
- name: `?WriteRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1QEAEHJ@Z`
- size: `704`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, BYTE *lpData, DWORD cbData, DWORD dwType)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180083a80`
- `0x180083f00`
- `0x180083f50`
- `0x180084110`

## callees

- `0x18000b1d8`
- `0x180020bf0`
- `0x18003ce1c`
- `0x1800824b4`
- `0x180083c2c`
- `0x180084634`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180083e84`
- `ADVAPI32!RegCloseKey` at `0x180083e84`
- `ADVAPI32!RegSetValueExW` at `0x180083de9`
- `ADVAPI32!RegSetValueExW` at `0x180083de9`
- `ADVAPI32!RegCreateKeyExW` at `0x180083cb6`
- `ADVAPI32!RegCreateKeyExW` at `0x180083cb6`

## string_xrefs

- `0x180083d83`: `Opened`
- `0x180083d8a`: `Created`

## pseudocode

```c
__int64 __fastcall CClientUtils::WriteRegistryEntry(
        HKEY hKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *lpData,
        DWORD cbData,
        DWORD dwType)
{
  unsigned int v10; // esi
  LSTATUS v11; // ebx
  PVOID *v12; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v14; // r8
  unsigned int v15; // eax
  const wchar_t *v16; // rbx
  LSTATUS v17; // ebx
  PVOID *v18; // rax
  unsigned int v19; // eax
  __int64 v20; // r8
  LSTATUS v21; // ebx
  unsigned int v22; // eax
  __int64 v23; // r8
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[272]; // [rsp+60h] [rbp-A0h] BYREF

  hKeya = 0;
  dwDisposition = 0;
  v10 = 0;
  CClientUtils::MakeSubKey(SubKey, (unsigned int)a2, a2);
  v11 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x20006u, 0, &hKeya, &dwDisposition);
  if ( v11 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v14, CurrentThreadActivityIdPrefix, v11);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 3u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids,
          v15,
          (__int64)SubKey);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v16 = L"Created";
      if ( dwDisposition != 1 )
        v16 = (const wchar_t *)L"Opened";
      RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v16, (__int64)SubKey);
    }
    v17 = RegSetValueExW(hKeya, a3, 0, dwType, lpData, cbData);
    if ( v17 )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v20, v19, v17);
          v18 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 3u )
        {
          RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, (__int64)a3);
        }
      }
    }
    else
    {
      v10 = 1;
    }
    v21 = RegCloseKey(hKeya);
    if ( v21
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v23, v22, v21);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180083c2c  push    rbp
0x180083c2e  push    rbx
0x180083c2f  push    rsi
0x180083c30  push    rdi
0x180083c31  push    r12
0x180083c33  push    r14
0x180083c35  push    r15
0x180083c37  lea     rbp, [rsp-190h]
0x180083c3f  sub     rsp, 290h
0x180083c46  mov     rax, cs:__security_cookie
0x180083c4d  xor     rax, rsp
0x180083c50  mov     [rbp+1C0h+var_40], rax
0x180083c57  mov     r14, r8
0x180083c5a  mov     [rsp+2C0h+hKey], 0
0x180083c63  mov     rbx, rcx
0x180083c66  mov     [rsp+2C0h+dwDisposition], 0
0x180083c6e  mov     r8, rdx; unsigned __int16 *
0x180083c71  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x180083c76  mov     r15, r9
0x180083c79  mov     r12, rdx
0x180083c7c  xor     esi, esi
0x180083c7e  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x180083c83  lea     rax, [rsp+2C0h+dwDisposition]
0x180083c88  xor     r9d, r9d; lpClass
0x180083c8b  mov     [rsp+2C0h+lpdwDisposition], rax; lpdwDisposition
0x180083c90  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x180083c95  lea     rax, [rsp+2C0h+hKey]
0x180083c9a  xor     r8d, r8d; Reserved
0x180083c9d  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180083ca2  mov     rcx, rbx; hKey
0x180083ca5  mov     [rsp+2C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180083caa  mov     [rsp+2C0h+samDesired], 20006h; samDesired
0x180083cb2  mov     [rsp+2C0h+dwOptions], esi; dwOptions
0x180083cb6  call    cs:__imp_RegCreateKeyExW
0x180083cbc  mov     ebx, eax
0x180083cbe  test    eax, eax
0x180083cc0  jz      loc_180083D5F
0x180083cc6  mov     rax, cs:WPP_GLOBAL_Control
0x180083ccd  lea     rdi, WPP_GLOBAL_Control
0x180083cd4  cmp     rax, rdi
0x180083cd7  jz      loc_180083EC9
0x180083cdd  test    byte ptr [rax+1Ch], 1
0x180083ce1  jz      short loc_180083D0F
0x180083ce3  cmp     byte ptr [rax+19h], 2
0x180083ce7  jb      short loc_180083D0F
0x180083ce9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180083cee  mov     rcx, cs:WPP_GLOBAL_Control
0x180083cf5  lea     edx, [rsi+10h]
0x180083cf8  mov     r9d, eax
0x180083cfb  mov     [rsp+2C0h+dwOptions], ebx
0x180083cff  mov     rcx, [rcx+10h]
0x180083d03  call    WPP_SF_Dl
0x180083d08  mov     rax, cs:WPP_GLOBAL_Control
0x180083d0f  cmp     rax, rdi
0x180083d12  jz      loc_180083EC9
0x180083d18  test    byte ptr [rax+1Ch], 1
0x180083d1c  jz      loc_180083EC9
0x180083d22  cmp     byte ptr [rax+19h], 3
0x180083d26  jb      loc_180083EC9
0x180083d2c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180083d31  lea     rcx, [rsp+2C0h+SubKey]
0x180083d36  mov     edx, 11h
0x180083d3b  mov     qword ptr [rsp+2C0h+dwOptions], rcx
0x180083d40  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180083d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180083d4e  mov     r9d, eax
0x180083d51  mov     rcx, [rcx+10h]
0x180083d55  call    WPP_SF_DS
0x180083d5a  jmp     loc_180083EC9
0x180083d5f  mov     rax, cs:WPP_GLOBAL_Control
0x180083d66  lea     rdi, WPP_GLOBAL_Control
0x180083d6d  cmp     rax, rdi
0x180083d70  jz      short loc_180083DC8
0x180083d72  test    byte ptr [rax+1Ch], 1
0x180083d76  jz      short loc_180083DC8
0x180083d78  cmp     byte ptr [rax+19h], 4
0x180083d7c  jb      short loc_180083DC8
0x180083d7e  cmp     [rsp+2C0h+dwDisposition], 1
0x180083d83  lea     rax, aOpened; "Opened"
0x180083d8a  lea     rbx, aCreated; "Created"
0x180083d91  cmovnz  rbx, rax
0x180083d95  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180083d9a  lea     rcx, [rsp+2C0h+SubKey]
0x180083d9f  mov     edx, 12h
0x180083da4  mov     qword ptr [rsp+2C0h+samDesired], rcx; __int64
0x180083da9  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180083db0  mov     rcx, cs:WPP_GLOBAL_Control
0x180083db7  mov     r9d, eax
0x180083dba  mov     qword ptr [rsp+2C0h+dwOptions], rbx; __int64
0x180083dbf  mov     rcx, [rcx+10h]; LoggerHandle
0x180083dc3  call    WPP_SF_DSS
0x180083dc8  mov     eax, [rbp+1C0h+cbData]
0x180083dce  xor     r8d, r8d; Reserved
0x180083dd1  mov     r9d, [rbp+1C0h+dwType]; dwType
0x180083dd8  mov     rdx, r14; lpValueName
0x180083ddb  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180083de0  mov     [rsp+2C0h+samDesired], eax; cbData
0x180083de4  mov     qword ptr [rsp+2C0h+dwOptions], r15; lpData
0x180083de9  call    cs:__imp_RegSetValueExW
0x180083def  mov     ebx, eax
0x180083df1  test    eax, eax
0x180083df3  jz      loc_180083E7A
0x180083df9  mov     rax, cs:WPP_GLOBAL_Control
0x180083e00  cmp     rax, rdi
0x180083e03  jz      short loc_180083E7F
0x180083e05  test    byte ptr [rax+1Ch], 1
0x180083e09  jz      short loc_180083E39
0x180083e0b  cmp     byte ptr [rax+19h], 2
0x180083e0f  jb      short loc_180083E39
0x180083e11  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180083e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180083e1d  mov     edx, 13h
0x180083e22  mov     r9d, eax
0x180083e25  mov     [rsp+2C0h+dwOptions], ebx
0x180083e29  mov     rcx, [rcx+10h]
0x180083e2d  call    WPP_SF_Dl
0x180083e32  mov     rax, cs:WPP_GLOBAL_Control
0x180083e39  cmp     rax, rdi
0x180083e3c  jz      short loc_180083E7F
0x180083e3e  test    byte ptr [rax+1Ch], 1
0x180083e42  jz      short loc_180083E7F
0x180083e44  cmp     byte ptr [rax+19h], 3
0x180083e48  jb      short loc_180083E7F
0x180083e4a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180083e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180083e56  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180083e5d  mov     edx, 14h
0x180083e62  mov     qword ptr [rsp+2C0h+samDesired], r14; __int64
0x180083e67  mov     r9d, eax
0x180083e6a  mov     qword ptr [rsp+2C0h+dwOptions], r12; __int64
0x180083e6f  mov     rcx, [rcx+10h]; LoggerHandle
0x180083e73  call    WPP_SF_DSS
0x180083e78  jmp     short loc_180083E7F
0x180083e7a  mov     esi, 1
0x180083e7f  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180083e84  call    cs:__imp_RegCloseKey
0x180083e8a  mov     ebx, eax
0x180083e8c  test    eax, eax
0x180083e8e  jz      short loc_180083EC9
0x180083e90  mov     rcx, cs:WPP_GLOBAL_Control
0x180083e97  cmp     rcx, rdi
0x180083e9a  jz      short loc_180083EC9
0x180083e9c  test    byte ptr [rcx+1Ch], 1
0x180083ea0  jz      short loc_180083EC9
0x180083ea2  cmp     byte ptr [rcx+19h], 2
0x180083ea6  jb      short loc_180083EC9
0x180083ea8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180083ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180083eb4  mov     edx, 15h
0x180083eb9  mov     r9d, eax
0x180083ebc  mov     [rsp+2C0h+dwOptions], ebx
0x180083ec0  mov     rcx, [rcx+10h]
0x180083ec4  call    WPP_SF_Dl
0x180083ec9  mov     eax, esi
0x180083ecb  mov     rcx, [rbp+1C0h+var_40]
0x180083ed2  xor     rcx, rsp; StackCookie
0x180083ed5  call    __security_check_cookie
0x180083eda  add     rsp, 290h
0x180083ee1  pop     r15
0x180083ee3  pop     r14
0x180083ee5  pop     r12
0x180083ee7  pop     rdi
0x180083ee8  pop     rsi
0x180083ee9  pop     rbx
0x180083eea  pop     rbp
0x180083eeb  retn
```
