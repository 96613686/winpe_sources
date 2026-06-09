# StSaveProfileMetaData(_GUID const *,int,_GUID *,_ST_PROFILE_METADATA *)

- ea: `0x180201a00`
- end: `0x180201c03`
- name: `?StSaveProfileMetaData@@YAKPEBU_GUID@@HPEAU1@PEAU_ST_PROFILE_METADATA@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(const struct _GUID *, int, struct _GUID *, BYTE *lpData)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b9730`
- `0x1801fd6a0`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180019820`
- `0x180106340`
- `0x180201a00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180201afd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180201b48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180201b99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180201afd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180201b48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180201b99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180201bab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180201bab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180201acd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180201acd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180201b71`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180201b71`

## pseudocode

```c
__int64 __fastcall StSaveProfileMetaData(const struct _GUID *a1, int a2, struct _GUID *a3, BYTE *lpData)
{
  unsigned int RegKeyPath; // ebx
  const BYTE *v9; // rcx
  __int64 v10; // rax
  LSTATUS v11; // eax
  void *v12; // rcx
  DWORD samDesired; // [rsp+28h] [rbp-290h]
  HKEY hKey; // [rsp+50h] [rbp-268h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-258h] BYREF

  hKey = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 28, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids);
  }
  RegKeyPath = StpGetRegKeyPath(a1, a2, a3, 0, 0, SubKey, 0x104u);
  if ( !RegKeyPath )
  {
    RegKeyPath = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( !RegKeyPath )
    {
      RegKeyPath = RegSetValueExW(hKey, L"Flags", 0, 4u, lpData, 4u);
      if ( !RegKeyPath )
      {
        if ( !a2 )
        {
          v12 = (void *)*((_QWORD *)lpData + 1);
          if ( !v12 )
            goto LABEL_16;
          samDesired = GetLengthSid(v12);
          v11 = RegSetValueExW(hKey, L"SID", 0, 3u, *((const BYTE **)lpData + 1), samDesired);
          goto LABEL_15;
        }
        v9 = (const BYTE *)*((_QWORD *)lpData + 2);
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)&v9[2 * v10] );
        RegKeyPath = RegSetValueExW(hKey, L"Name", 0, 1u, v9, 2 * v10 + 2);
        if ( !RegKeyPath )
        {
          v11 = RegSetValueExW(hKey, L"Delta", 0, 3u, *((const BYTE **)lpData + 4), *((_DWORD *)lpData + 6));
LABEL_15:
          RegKeyPath = v11;
        }
      }
    }
  }
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, &WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids, RegKeyPath);
  }
  return RegKeyPath;
}

```

## disassembly

```asm
0x180201a00  push    rbx
0x180201a02  push    rbp
0x180201a03  push    rsi
0x180201a04  push    rdi
0x180201a05  push    r12
0x180201a07  push    r14
0x180201a09  sub     rsp, 288h
0x180201a10  mov     rax, cs:__security_cookie
0x180201a17  xor     rax, rsp
0x180201a1a  mov     [rsp+2B8h+var_48], rax
0x180201a22  xor     r14d, r14d
0x180201a25  mov     rdi, r9
0x180201a28  mov     [rsp+2B8h+hKey], r14
0x180201a2d  mov     rbp, r8
0x180201a30  mov     esi, edx
0x180201a32  mov     rbx, rcx
0x180201a35  mov     rcx, cs:WPP_GLOBAL_Control
0x180201a3c  lea     r12, WPP_GLOBAL_Control
0x180201a43  cmp     rcx, r12
0x180201a46  jz      short loc_180201A68
0x180201a48  cmp     byte ptr [rcx+69h], 4
0x180201a4c  jb      short loc_180201A68
0x180201a4e  test    byte ptr [rcx+6Ch], 1
0x180201a52  jz      short loc_180201A68
0x180201a54  mov     rcx, [rcx+60h]
0x180201a58  lea     edx, [r14+1Ch]
0x180201a5c  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180201a63  call    WPP_SF_
0x180201a68  lea     rax, [rsp+2B8h+SubKey]
0x180201a6d  mov     [rsp+2B8h+lpSecurityAttributes], 104h; unsigned __int64
0x180201a76  mov     qword ptr [rsp+2B8h+samDesired], rax; unsigned __int16 *
0x180201a7b  xor     r9d, r9d; int
0x180201a7e  mov     r8, rbp; struct _GUID *
0x180201a81  mov     [rsp+2B8h+dwOptions], r14d; int
0x180201a86  mov     edx, esi; int
0x180201a88  mov     rcx, rbx; struct _GUID *
0x180201a8b  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@HPEAU1@HHPEAG_K@Z; StpGetRegKeyPath(_GUID const *,int,_GUID *,int,int,ushort *,unsigned __int64)
0x180201a90  mov     ebx, eax
0x180201a92  test    eax, eax
0x180201a94  jnz     loc_180201BA1
0x180201a9a  mov     [rsp+2B8h+lpdwDisposition], r14; lpdwDisposition
0x180201a9f  lea     rax, [rsp+2B8h+hKey]
0x180201aa4  mov     [rsp+2B8h+phkResult], rax; phkResult
0x180201aa9  lea     rdx, [rsp+2B8h+SubKey]; lpSubKey
0x180201aae  mov     [rsp+2B8h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180201ab3  xor     r9d, r9d; lpClass
0x180201ab6  mov     [rsp+2B8h+samDesired], 20006h; samDesired
0x180201abe  xor     r8d, r8d; Reserved
0x180201ac1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180201ac8  mov     [rsp+2B8h+dwOptions], r14d; dwOptions
0x180201acd  call    cs:__imp_RegCreateKeyExW
0x180201ad3  mov     ebx, eax
0x180201ad5  test    eax, eax
0x180201ad7  jnz     loc_180201BA1
0x180201add  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180201ae2  lea     r9d, [rax+4]; dwType
0x180201ae6  mov     [rsp+2B8h+samDesired], 4; cbData
0x180201aee  lea     rdx, aFlags; "Flags"
0x180201af5  xor     r8d, r8d; Reserved
0x180201af8  mov     qword ptr [rsp+2B8h+dwOptions], rdi; lpData
0x180201afd  call    cs:__imp_RegSetValueExW
0x180201b03  mov     ebx, eax
0x180201b05  test    eax, eax
0x180201b07  jnz     loc_180201BA1
0x180201b0d  test    esi, esi
0x180201b0f  jz      short loc_180201B68
0x180201b11  mov     rcx, [rdi+10h]
0x180201b15  or      rax, 0FFFFFFFFFFFFFFFFh
0x180201b19  inc     rax
0x180201b1c  cmp     [rcx+rax*2], r14w
0x180201b21  jnz     short loc_180201B19
0x180201b23  lea     eax, ds:2[rax*2]
0x180201b2a  mov     r9d, 1; dwType
0x180201b30  mov     [rsp+2B8h+samDesired], eax; cbData
0x180201b34  lea     rdx, aName; "Name"
0x180201b3b  mov     qword ptr [rsp+2B8h+dwOptions], rcx; lpData
0x180201b40  xor     r8d, r8d; Reserved
0x180201b43  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180201b48  call    cs:__imp_RegSetValueExW
0x180201b4e  mov     ebx, eax
0x180201b50  test    eax, eax
0x180201b52  jnz     short loc_180201BA1
0x180201b54  mov     eax, [rdi+18h]
0x180201b57  lea     rdx, aDelta; "Delta"
0x180201b5e  mov     [rsp+2B8h+samDesired], eax
0x180201b62  mov     rax, [rdi+20h]
0x180201b66  jmp     short loc_180201B86
0x180201b68  mov     rcx, [rdi+8]; pSid
0x180201b6c  test    rcx, rcx
0x180201b6f  jz      short loc_180201BA1
0x180201b71  call    cs:__imp_GetLengthSid
0x180201b77  mov     [rsp+2B8h+samDesired], eax; cbData
0x180201b7b  lea     rdx, aSid; "SID"
0x180201b82  mov     rax, [rdi+8]
0x180201b86  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180201b8b  mov     r9d, 3; dwType
0x180201b91  xor     r8d, r8d; Reserved
0x180201b94  mov     qword ptr [rsp+2B8h+dwOptions], rax; lpData
0x180201b99  call    cs:__imp_RegSetValueExW
0x180201b9f  mov     ebx, eax
0x180201ba1  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180201ba6  test    rcx, rcx
0x180201ba9  jz      short loc_180201BB1
0x180201bab  call    cs:__imp_RegCloseKey
0x180201bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180201bb8  cmp     rcx, r12
0x180201bbb  jz      short loc_180201BE1
0x180201bbd  cmp     byte ptr [rcx+69h], 4
0x180201bc1  jb      short loc_180201BE1
0x180201bc3  test    byte ptr [rcx+6Ch], 1
0x180201bc7  jz      short loc_180201BE1
0x180201bc9  mov     rcx, [rcx+60h]
0x180201bcd  lea     r8, WPP_d35b4e0e825b3126173a8f9fbc52d996_Traceguids
0x180201bd4  mov     edx, 1Dh
0x180201bd9  mov     r9d, ebx
0x180201bdc  call    WPP_SF_d
0x180201be1  mov     eax, ebx
0x180201be3  mov     rcx, [rsp+2B8h+var_48]
0x180201beb  xor     rcx, rsp; StackCookie
0x180201bee  call    __security_check_cookie
0x180201bf3  add     rsp, 288h
0x180201bfa  pop     r14
0x180201bfc  pop     r12
0x180201bfe  pop     rdi
0x180201bff  pop     rsi
0x180201c00  pop     rbp
0x180201c01  pop     rbx
0x180201c02  retn
```
