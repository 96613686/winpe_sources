# CClientUtils::WriteRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar * const,int,long)

- ea: `0x180009d6c`
- end: `0x18000a02c`
- name: `?WriteRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1QEAEHJ@Z`
- size: `704`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, BYTE *lpData, DWORD cbData, DWORD dwType)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180009bc0`
- `0x18000a040`
- `0x18000a090`
- `0x18000a250`

## callees

- `0x180003970`
- `0x180005438`
- `0x180007f84`
- `0x180009d6c`
- `0x18000a508`
- `0x18000a858`
- `0x18000aea0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180009f29`
- `ADVAPI32!RegSetValueExW` at `0x180009f29`
- `ADVAPI32!RegCreateKeyExW` at `0x180009df6`
- `ADVAPI32!RegCreateKeyExW` at `0x180009df6`
- `ADVAPI32!RegCloseKey` at `0x180009fc4`
- `ADVAPI32!RegCloseKey` at `0x180009fc4`

## string_xrefs

- `0x180009eca`: `Created`
- `0x180009ec3`: `Opened`

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
  _BYTE *v12; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v14; // r8
  unsigned int v15; // eax
  const wchar_t *v16; // rbx
  LSTATUS v17; // ebx
  _BYTE *v18; // rax
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
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v14, CurrentThreadActivityIdPrefix, v11);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v12 != (_BYTE *)&WPP_GLOBAL_Control && (v12[28] & 1) != 0 && v12[25] >= 3u )
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
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dl(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v20, v19, v17);
          v18 = WPP_GLOBAL_Control;
        }
        if ( v18 != (_BYTE *)&WPP_GLOBAL_Control && (v18[28] & 1) != 0 && v18[25] >= 3u )
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
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
0x180009d6c  push    rbp
0x180009d6e  push    rbx
0x180009d6f  push    rsi
0x180009d70  push    rdi
0x180009d71  push    r12
0x180009d73  push    r14
0x180009d75  push    r15
0x180009d77  lea     rbp, [rsp-190h]
0x180009d7f  sub     rsp, 290h
0x180009d86  mov     rax, cs:__security_cookie
0x180009d8d  xor     rax, rsp
0x180009d90  mov     [rbp+1C0h+var_40], rax
0x180009d97  mov     r14, r8
0x180009d9a  mov     [rsp+2C0h+hKey], 0
0x180009da3  mov     rbx, rcx
0x180009da6  mov     [rsp+2C0h+dwDisposition], 0
0x180009dae  mov     r8, rdx; unsigned __int16 *
0x180009db1  lea     rcx, [rsp+2C0h+SubKey]; unsigned __int16 *
0x180009db6  mov     r15, r9
0x180009db9  mov     r12, rdx
0x180009dbc  xor     esi, esi
0x180009dbe  call    ?MakeSubKey@CClientUtils@@KAXPEAGIPEBG@Z; CClientUtils::MakeSubKey(ushort *,uint,ushort const *)
0x180009dc3  lea     rax, [rsp+2C0h+dwDisposition]
0x180009dc8  xor     r9d, r9d; lpClass
0x180009dcb  mov     [rsp+2C0h+lpdwDisposition], rax; lpdwDisposition
0x180009dd0  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x180009dd5  lea     rax, [rsp+2C0h+hKey]
0x180009dda  xor     r8d, r8d; Reserved
0x180009ddd  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180009de2  mov     rcx, rbx; hKey
0x180009de5  mov     [rsp+2C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180009dea  mov     [rsp+2C0h+samDesired], 20006h; samDesired
0x180009df2  mov     [rsp+2C0h+dwOptions], esi; dwOptions
0x180009df6  call    cs:__imp_RegCreateKeyExW
0x180009dfc  mov     ebx, eax
0x180009dfe  test    eax, eax
0x180009e00  jz      loc_180009E9F
0x180009e06  mov     rax, cs:WPP_GLOBAL_Control
0x180009e0d  lea     rdi, WPP_GLOBAL_Control
0x180009e14  cmp     rax, rdi
0x180009e17  jz      loc_18000A009
0x180009e1d  test    byte ptr [rax+1Ch], 1
0x180009e21  jz      short loc_180009E4F
0x180009e23  cmp     byte ptr [rax+19h], 2
0x180009e27  jb      short loc_180009E4F
0x180009e29  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e35  lea     edx, [rsi+10h]
0x180009e38  mov     r9d, eax
0x180009e3b  mov     [rsp+2C0h+dwOptions], ebx
0x180009e3f  mov     rcx, [rcx+10h]
0x180009e43  call    WPP_SF_Dl
0x180009e48  mov     rax, cs:WPP_GLOBAL_Control
0x180009e4f  cmp     rax, rdi
0x180009e52  jz      loc_18000A009
0x180009e58  test    byte ptr [rax+1Ch], 1
0x180009e5c  jz      loc_18000A009
0x180009e62  cmp     byte ptr [rax+19h], 3
0x180009e66  jb      loc_18000A009
0x180009e6c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009e71  lea     rcx, [rsp+2C0h+SubKey]
0x180009e76  mov     edx, 11h
0x180009e7b  mov     qword ptr [rsp+2C0h+dwOptions], rcx
0x180009e80  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180009e87  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e8e  mov     r9d, eax
0x180009e91  mov     rcx, [rcx+10h]
0x180009e95  call    WPP_SF_DS
0x180009e9a  jmp     loc_18000A009
0x180009e9f  mov     rax, cs:WPP_GLOBAL_Control
0x180009ea6  lea     rdi, WPP_GLOBAL_Control
0x180009ead  cmp     rax, rdi
0x180009eb0  jz      short loc_180009F08
0x180009eb2  test    byte ptr [rax+1Ch], 1
0x180009eb6  jz      short loc_180009F08
0x180009eb8  cmp     byte ptr [rax+19h], 4
0x180009ebc  jb      short loc_180009F08
0x180009ebe  cmp     [rsp+2C0h+dwDisposition], 1
0x180009ec3  lea     rax, aOpened; "Opened"
0x180009eca  lea     rbx, aCreated; "Created"
0x180009ed1  cmovnz  rbx, rax
0x180009ed5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009eda  lea     rcx, [rsp+2C0h+SubKey]
0x180009edf  mov     edx, 12h
0x180009ee4  mov     qword ptr [rsp+2C0h+samDesired], rcx; __int64
0x180009ee9  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180009ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ef7  mov     r9d, eax
0x180009efa  mov     qword ptr [rsp+2C0h+dwOptions], rbx; __int64
0x180009eff  mov     rcx, [rcx+10h]; LoggerHandle
0x180009f03  call    WPP_SF_DSS
0x180009f08  mov     eax, [rbp+1C0h+cbData]
0x180009f0e  xor     r8d, r8d; Reserved
0x180009f11  mov     r9d, [rbp+1C0h+dwType]; dwType
0x180009f18  mov     rdx, r14; lpValueName
0x180009f1b  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180009f20  mov     [rsp+2C0h+samDesired], eax; cbData
0x180009f24  mov     qword ptr [rsp+2C0h+dwOptions], r15; lpData
0x180009f29  call    cs:__imp_RegSetValueExW
0x180009f2f  mov     ebx, eax
0x180009f31  test    eax, eax
0x180009f33  jz      loc_180009FBA
0x180009f39  mov     rax, cs:WPP_GLOBAL_Control
0x180009f40  cmp     rax, rdi
0x180009f43  jz      short loc_180009FBF
0x180009f45  test    byte ptr [rax+1Ch], 1
0x180009f49  jz      short loc_180009F79
0x180009f4b  cmp     byte ptr [rax+19h], 2
0x180009f4f  jb      short loc_180009F79
0x180009f51  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009f56  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f5d  mov     edx, 13h
0x180009f62  mov     r9d, eax
0x180009f65  mov     [rsp+2C0h+dwOptions], ebx
0x180009f69  mov     rcx, [rcx+10h]
0x180009f6d  call    WPP_SF_Dl
0x180009f72  mov     rax, cs:WPP_GLOBAL_Control
0x180009f79  cmp     rax, rdi
0x180009f7c  jz      short loc_180009FBF
0x180009f7e  test    byte ptr [rax+1Ch], 1
0x180009f82  jz      short loc_180009FBF
0x180009f84  cmp     byte ptr [rax+19h], 3
0x180009f88  jb      short loc_180009FBF
0x180009f8a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f96  lea     r8, WPP_72aaf7d92de938e37e89151f64d0d640_Traceguids
0x180009f9d  mov     edx, 14h
0x180009fa2  mov     qword ptr [rsp+2C0h+samDesired], r14; __int64
0x180009fa7  mov     r9d, eax
0x180009faa  mov     qword ptr [rsp+2C0h+dwOptions], r12; __int64
0x180009faf  mov     rcx, [rcx+10h]; LoggerHandle
0x180009fb3  call    WPP_SF_DSS
0x180009fb8  jmp     short loc_180009FBF
0x180009fba  mov     esi, 1
0x180009fbf  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180009fc4  call    cs:__imp_RegCloseKey
0x180009fca  mov     ebx, eax
0x180009fcc  test    eax, eax
0x180009fce  jz      short loc_18000A009
0x180009fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fd7  cmp     rcx, rdi
0x180009fda  jz      short loc_18000A009
0x180009fdc  test    byte ptr [rcx+1Ch], 1
0x180009fe0  jz      short loc_18000A009
0x180009fe2  cmp     byte ptr [rcx+19h], 2
0x180009fe6  jb      short loc_18000A009
0x180009fe8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009fed  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ff4  mov     edx, 15h
0x180009ff9  mov     r9d, eax
0x180009ffc  mov     [rsp+2C0h+dwOptions], ebx
0x18000a000  mov     rcx, [rcx+10h]
0x18000a004  call    WPP_SF_Dl
0x18000a009  mov     eax, esi
0x18000a00b  mov     rcx, [rbp+1C0h+var_40]
0x18000a012  xor     rcx, rsp; StackCookie
0x18000a015  call    __security_check_cookie
0x18000a01a  add     rsp, 290h
0x18000a021  pop     r15
0x18000a023  pop     r14
0x18000a025  pop     r12
0x18000a027  pop     rdi
0x18000a028  pop     rsi
0x18000a029  pop     rbx
0x18000a02a  pop     rbp
0x18000a02b  retn
```
