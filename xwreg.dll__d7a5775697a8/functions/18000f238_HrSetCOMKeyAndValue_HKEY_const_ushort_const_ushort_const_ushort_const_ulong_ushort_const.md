# HrSetCOMKeyAndValue(HKEY__ * const,ushort const *,ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x18000f238`
- end: `0x18000f47e`
- name: `?HrSetCOMKeyAndValue@@YAJQEAUHKEY__@@PEBG11K1@Z`
- size: `582`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ee04`

## callees

- `0x180007820`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000f238`
- `0x18001084c`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f2fc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000f2fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f3b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f3b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f364`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f364`

## pseudocode

```c
__int64 __fastcall HrSetCOMKeyAndValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwType,
        BYTE *lpData)
{
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  DWORD v11; // eax
  const WCHAR *v12; // rdx
  LSTATUS v13; // eax
  PVOID *v14; // rcx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[80]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  if ( a2 && *a2 )
  {
    SubKey[0] = 0;
    StringCchCopyW(SubKey, 0x4Bu, a2);
    if ( a3 && *a3 )
    {
      StringCchCatW(SubKey, 0x4Bu, &qword_180017630);
      StringCchCatW(SubKey, 0x4Bu, a3);
    }
    v8 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    v9 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v9;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_27:
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x10) != 0 )
          WPP_SF_D(v14[2], 42, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v9);
        return v9;
      }
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
        (unsigned int)SubKey,
        v9);
    }
    else
    {
      v9 = 0;
      if ( lpData && *(_WORD *)lpData )
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)&lpData[2 * v10] );
        v11 = 2 * v10 + 2;
        if ( !a4 || (v12 = a4, !*a4) )
          v12 = 0;
        v13 = RegSetValueExW(hKey, v12, 0, dwType, lpData, v11);
        v9 = v13;
        if ( v13 > 0 )
          v9 = (unsigned __int16)v13 | 0x80070000;
        if ( (v9 & 0x80000000) != 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_SSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a4, (__int64)lpData, v9);
        }
      }
      RegCloseKey(hKey);
    }
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18000f238  mov     [rsp-8+arg_0], rbx
0x18000f23d  push    rbp
0x18000f23e  push    rsi
0x18000f23f  push    rdi
0x18000f240  push    r14
0x18000f242  push    r15
0x18000f244  lea     rbp, [rsp-10h]
0x18000f249  sub     rsp, 110h
0x18000f250  mov     rax, cs:__security_cookie
0x18000f257  xor     rax, rsp
0x18000f25a  mov     [rbp+30h+var_30], rax
0x18000f25e  mov     rsi, [rbp+30h+lpData]
0x18000f262  xor     r15d, r15d
0x18000f265  mov     [rsp+130h+hKey], r15
0x18000f26a  mov     r14, r9
0x18000f26d  mov     rbx, r8
0x18000f270  test    rdx, rdx
0x18000f273  jz      loc_18000F428
0x18000f279  cmp     [rdx], r15w
0x18000f27d  jz      loc_18000F428
0x18000f283  mov     r8, rdx; unsigned __int16 *
0x18000f286  mov     [rsp+130h+SubKey], r15w
0x18000f28c  lea     edi, [r15+4Bh]
0x18000f290  mov     edx, edi; unsigned __int64
0x18000f292  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x18000f297  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f29c  test    rbx, rbx
0x18000f29f  jz      short loc_18000F2C9
0x18000f2a1  cmp     [rbx], r15w
0x18000f2a5  jz      short loc_18000F2C9
0x18000f2a7  lea     r8, qword_180017630; unsigned __int16 *
0x18000f2ae  mov     edx, edi; unsigned __int64
0x18000f2b0  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x18000f2b5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f2ba  mov     r8, rbx; unsigned __int16 *
0x18000f2bd  lea     rcx, [rsp+130h+SubKey]; unsigned __int16 *
0x18000f2c2  mov     edx, edi; unsigned __int64
0x18000f2c4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f2c9  mov     [rsp+130h+lpdwDisposition], r15; lpdwDisposition
0x18000f2ce  lea     rax, [rsp+130h+hKey]
0x18000f2d3  mov     [rsp+130h+phkResult], rax; phkResult
0x18000f2d8  lea     rdx, [rsp+130h+SubKey]; lpSubKey
0x18000f2dd  mov     [rsp+130h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000f2e2  xor     r9d, r9d; lpClass
0x18000f2e5  mov     [rsp+130h+samDesired], 20006h; samDesired
0x18000f2ed  xor     r8d, r8d; Reserved
0x18000f2f0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000f2f7  mov     [rsp+130h+dwOptions], r15d; dwOptions
0x18000f2fc  call    cs:__imp_RegCreateKeyExW
0x18000f302  mov     ebx, eax
0x18000f304  test    eax, eax
0x18000f306  jnz     loc_18000F3B8
0x18000f30c  lea     rdi, WPP_GLOBAL_Control
0x18000f313  mov     ebx, r15d
0x18000f316  test    rsi, rsi
0x18000f319  jz      loc_18000F3AB
0x18000f31f  cmp     [rsi], r15w
0x18000f323  jz      loc_18000F3AB
0x18000f329  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f32d  inc     rax
0x18000f330  cmp     [rsi+rax*2], r15w
0x18000f335  jnz     short loc_18000F32D
0x18000f337  lea     eax, ds:2[rax*2]
0x18000f33e  test    r14, r14
0x18000f341  jz      short loc_18000F34C
0x18000f343  mov     rdx, r14
0x18000f346  cmp     [r14], r15w
0x18000f34a  jnz     short loc_18000F34F
0x18000f34c  mov     rdx, r15; lpValueName
0x18000f34f  mov     r9d, [rbp+30h+dwType]; dwType
0x18000f353  xor     r8d, r8d; Reserved
0x18000f356  mov     rcx, [rsp+130h+hKey]; hKey
0x18000f35b  mov     [rsp+130h+samDesired], eax; cbData
0x18000f35f  mov     qword ptr [rsp+130h+dwOptions], rsi; lpData
0x18000f364  call    cs:__imp_RegSetValueExW
0x18000f36a  mov     ebx, eax
0x18000f36c  test    eax, eax
0x18000f36e  jle     short loc_18000F379
0x18000f370  movzx   ebx, ax
0x18000f373  or      ebx, 80070000h
0x18000f379  test    ebx, ebx
0x18000f37b  jns     short loc_18000F3AB
0x18000f37d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f384  cmp     rcx, rdi
0x18000f387  jz      short loc_18000F3AB
0x18000f389  test    byte ptr [rcx+1Ch], 4
0x18000f38d  jz      short loc_18000F3AB
0x18000f38f  mov     rcx, [rcx+10h]; LoggerHandle
0x18000f393  lea     r9, [rsp+130h+SubKey]
0x18000f398  mov     dword ptr [rsp+130h+lpSecurityAttributes], ebx; char
0x18000f39c  mov     qword ptr [rsp+130h+samDesired], rsi; __int64
0x18000f3a1  mov     qword ptr [rsp+130h+dwOptions], r14; __int64
0x18000f3a6  call    WPP_SF_SSSD
0x18000f3ab  mov     rcx, [rsp+130h+hKey]; hKey
0x18000f3b0  call    cs:__imp_RegCloseKey
0x18000f3b6  jmp     short loc_18000F3FA
0x18000f3b8  jle     short loc_18000F3C3
0x18000f3ba  movzx   ebx, ax
0x18000f3bd  or      ebx, 80070000h
0x18000f3c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3ca  lea     rdi, WPP_GLOBAL_Control
0x18000f3d1  cmp     rcx, rdi
0x18000f3d4  jz      short loc_18000F424
0x18000f3d6  test    byte ptr [rcx+1Ch], 4
0x18000f3da  jz      short loc_18000F401
0x18000f3dc  mov     rcx, [rcx+10h]
0x18000f3e0  lea     r9, [rsp+130h+SubKey]
0x18000f3e5  mov     edx, 29h ; ')'
0x18000f3ea  mov     [rsp+130h+dwOptions], ebx
0x18000f3ee  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000f3f5  call    WPP_SF_SD
0x18000f3fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f401  cmp     rcx, rdi
0x18000f404  jz      short loc_18000F424
0x18000f406  test    byte ptr [rcx+1Ch], 10h
0x18000f40a  jz      short loc_18000F424
0x18000f40c  mov     rcx, [rcx+10h]
0x18000f410  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000f417  mov     edx, 2Ah ; '*'
0x18000f41c  mov     r9d, ebx
0x18000f41f  call    WPP_SF_D
0x18000f424  mov     eax, ebx
0x18000f426  jmp     short loc_18000F45B
0x18000f428  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f42f  lea     rdi, WPP_GLOBAL_Control
0x18000f436  cmp     rcx, rdi
0x18000f439  jz      short loc_18000F459
0x18000f43b  test    byte ptr [rcx+1Ch], 10h
0x18000f43f  jz      short loc_18000F459
0x18000f441  mov     rcx, [rcx+10h]
0x18000f445  lea     r8, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000f44c  mov     edx, 27h ; '''
0x18000f451  xor     r9d, r9d
0x18000f454  call    WPP_SF_D
0x18000f459  xor     eax, eax
0x18000f45b  mov     rcx, [rbp+30h+var_30]
0x18000f45f  xor     rcx, rsp; StackCookie
0x18000f462  call    __security_check_cookie
0x18000f467  mov     rbx, [rsp+130h+arg_0]
0x18000f46f  add     rsp, 110h
0x18000f476  pop     r15
0x18000f478  pop     r14
0x18000f47a  pop     rdi
0x18000f47b  pop     rsi
0x18000f47c  pop     rbp
0x18000f47d  retn
```
