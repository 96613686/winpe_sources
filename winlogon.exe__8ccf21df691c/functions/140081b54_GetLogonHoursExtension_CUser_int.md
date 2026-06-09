# GetLogonHoursExtension(CUser *,int)

- ea: `0x140081b54`
- end: `0x140081d37`
- name: `?GetLogonHoursExtension@@YAKPEAVCUser@@H@Z`
- size: `483`
- prototype: `unsigned int __fastcall(struct CUser *this, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140082120`
- `0x1400825f0`

## callees

- `0x1400057f4`
- `0x14000d4e0`
- `0x14002f600`
- `0x140053720`
- `0x1400544e0`
- `0x140081b54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140081cd4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140081cd4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140081bfb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140081bfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140081c7f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140081c7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140081d12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140081d12`

## string_xrefs

- `0x140081c60`: `LogonExtension`
- `0x140081ccd`: `LogonExtension`

## pseudocode

```c
__int64 __fastcall GetLogonHoursExtension(struct CUser *this, int a2)
{
  unsigned int v4; // r8d
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v12[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[520]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(v12, 0, 0x208u);
  hKey = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  if ( !CUser::GetUserSidString(this, v12, v4) )
  {
    StringCchPrintfW(SubKey, 0x208u, L"Software\\Microsoft\\Windows\\CurrentVersion\\Parental Controls\\Users\\%s", v12);
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2001Bu, &hKey);
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v5);
      }
    }
    else
    {
      cbData = 4;
      v6 = RegQueryValueExW(hKey, L"LogonExtension", 0, 0, Data, &cbData);
      if ( v6
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v6);
      }
      if ( a2 )
      {
        v7 = RegDeleteValueW(hKey, L"LogonExtension");
        if ( v7 )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, v7);
          }
        }
      }
      RegCloseKey(hKey);
    }
  }
  return *(unsigned int *)Data;
}

```

## disassembly

```asm
0x140081b54  push    rbp
0x140081b56  push    rbx
0x140081b57  push    rsi
0x140081b58  push    rdi
0x140081b59  lea     rbp, [rsp-578h]
0x140081b61  sub     rsp, 678h
0x140081b68  mov     rax, cs:__security_cookie
0x140081b6f  xor     rax, rsp
0x140081b72  mov     [rbp+590h+var_30], rax
0x140081b79  mov     esi, edx
0x140081b7b  mov     rbx, rcx
0x140081b7e  mov     edi, 208h
0x140081b83  lea     rcx, [rsp+690h+var_650]; void *
0x140081b88  mov     r8d, edi; Size
0x140081b8b  xor     edx, edx; Val
0x140081b8d  call    memset_0
0x140081b92  lea     rdx, [rsp+690h+var_650]; unsigned __int16 *
0x140081b97  mov     [rsp+690h+hKey], 0
0x140081ba0  mov     rcx, rbx; this
0x140081ba3  mov     [rsp+690h+cbData], 0
0x140081bab  mov     dword ptr [rsp+690h+Data], 0
0x140081bb3  call    ?GetUserSidString@CUser@@QEAAKPEAGK@Z; CUser::GetUserSidString(ushort *,ulong)
0x140081bb8  test    eax, eax
0x140081bba  jnz     loc_140081D18
0x140081bc0  lea     r9, [rsp+690h+var_650]
0x140081bc5  mov     edx, edi; unsigned __int64
0x140081bc7  lea     r8, aSoftwareMicros_18; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140081bce  lea     rcx, [rbp+590h+SubKey]; unsigned __int16 *
0x140081bd5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140081bda  lea     rax, [rsp+690h+hKey]
0x140081bdf  mov     r9d, 2001Bh; samDesired
0x140081be5  xor     r8d, r8d; ulOptions
0x140081be8  mov     [rsp+690h+phkResult], rax; phkResult
0x140081bed  lea     rdx, [rbp+590h+SubKey]; lpSubKey
0x140081bf4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140081bfb  call    cs:__imp_RegOpenKeyExW
0x140081c01  test    eax, eax
0x140081c03  jz      short loc_140081C51
0x140081c05  mov     rcx, cs:WPP_GLOBAL_Control
0x140081c0c  lea     rdi, WPP_GLOBAL_Control
0x140081c13  cmp     rcx, rdi
0x140081c16  jz      loc_140081D18
0x140081c1c  mov     ebx, 1000h
0x140081c21  test    [rcx+1Ch], ebx
0x140081c24  jz      loc_140081D18
0x140081c2a  cmp     byte ptr [rcx+19h], 4
0x140081c2e  jb      loc_140081D18
0x140081c34  mov     rcx, [rcx+10h]
0x140081c38  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140081c3f  mov     edx, 4Eh ; 'N'
0x140081c44  mov     r9d, eax
0x140081c47  call    WPP_SF_d
0x140081c4c  jmp     loc_140081D18
0x140081c51  mov     rcx, [rsp+690h+hKey]; hKey
0x140081c56  lea     rax, [rsp+690h+cbData]
0x140081c5b  mov     [rsp+690h+lpcbData], rax; lpcbData
0x140081c60  lea     rdx, aLogonextension; "LogonExtension"
0x140081c67  lea     rax, [rsp+690h+Data]
0x140081c6c  mov     [rsp+690h+cbData], 4
0x140081c74  xor     r9d, r9d; lpType
0x140081c77  mov     [rsp+690h+phkResult], rax; lpData
0x140081c7c  xor     r8d, r8d; lpReserved
0x140081c7f  call    cs:__imp_RegQueryValueExW
0x140081c85  mov     ebx, 1000h
0x140081c8a  lea     rdi, WPP_GLOBAL_Control
0x140081c91  test    eax, eax
0x140081c93  jz      short loc_140081CC4
0x140081c95  mov     rcx, cs:WPP_GLOBAL_Control
0x140081c9c  cmp     rcx, rdi
0x140081c9f  jz      short loc_140081CC4
0x140081ca1  test    [rcx+1Ch], ebx
0x140081ca4  jz      short loc_140081CC4
0x140081ca6  cmp     byte ptr [rcx+19h], 4
0x140081caa  jb      short loc_140081CC4
0x140081cac  mov     rcx, [rcx+10h]
0x140081cb0  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140081cb7  mov     edx, 4Fh ; 'O'
0x140081cbc  mov     r9d, eax
0x140081cbf  call    WPP_SF_d
0x140081cc4  test    esi, esi
0x140081cc6  jz      short loc_140081D0D
0x140081cc8  mov     rcx, [rsp+690h+hKey]; hKey
0x140081ccd  lea     rdx, aLogonextension; "LogonExtension"
0x140081cd4  call    cs:__imp_RegDeleteValueW
0x140081cda  test    eax, eax
0x140081cdc  jz      short loc_140081D0D
0x140081cde  mov     rcx, cs:WPP_GLOBAL_Control
0x140081ce5  cmp     rcx, rdi
0x140081ce8  jz      short loc_140081D0D
0x140081cea  test    [rcx+1Ch], ebx
0x140081ced  jz      short loc_140081D0D
0x140081cef  cmp     byte ptr [rcx+19h], 2
0x140081cf3  jb      short loc_140081D0D
0x140081cf5  mov     rcx, [rcx+10h]
0x140081cf9  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140081d00  mov     edx, 50h ; 'P'
0x140081d05  mov     r9d, eax
0x140081d08  call    WPP_SF_d
0x140081d0d  mov     rcx, [rsp+690h+hKey]; hKey
0x140081d12  call    cs:__imp_RegCloseKey
0x140081d18  mov     eax, dword ptr [rsp+690h+Data]
0x140081d1c  mov     rcx, [rbp+590h+var_30]
0x140081d23  xor     rcx, rsp; StackCookie
0x140081d26  call    __security_check_cookie
0x140081d2b  add     rsp, 678h
0x140081d32  pop     rdi
0x140081d33  pop     rsi
0x140081d34  pop     rbx
0x140081d35  pop     rbp
0x140081d36  retn
```
