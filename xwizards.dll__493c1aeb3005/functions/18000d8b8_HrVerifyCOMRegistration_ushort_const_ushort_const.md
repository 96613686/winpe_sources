# HrVerifyCOMRegistration(ushort * const,ushort * * const)

- ea: `0x18000d8b8`
- end: `0x18000db6c`
- name: `?HrVerifyCOMRegistration@@YAJQEAGQEAPEAG@Z`
- size: `692`
- prototype: `__int64 __fastcall(unsigned __int16 *const, unsigned __int16 **const)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000db74`
- `0x18001bb24`

## callees

- `0x1800085a8`
- `0x180008634`
- `0x18000ae04`
- `0x18000ae90`
- `0x18000d598`
- `0x18000d8b8`
- `0x180032a02`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dadb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dadb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d9ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d9ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d985`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d985`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000da2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000da2b`

## string_xrefs

- `0x18000d90d`: `CLSID`

## pseudocode

```c
__int64 __fastcall HrVerifyCOMRegistration(unsigned __int16 *const a1, unsigned __int16 **const a2)
{
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  int FullNonHardCodedPath; // eax
  __int64 v7; // rax
  __int64 v8; // r14
  unsigned __int16 *v9; // rax
  PVOID *v10; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[72]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v15[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Data[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  hKey = 0;
  if ( a2 )
    *a2 = 0;
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x41u, L"CLSID");
  StringCchCatW(SubKey, 0x41u, &qword_18003C618);
  StringCchCatW(SubKey, 0x41u, a1);
  StringCchCatW(SubKey, 0x41u, &qword_18003C618);
  StringCchCatW(SubKey, 0x41u, L"InprocServer32");
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey) )
  {
    v4 = 0;
    if ( a2 )
    {
      memset_0(Data, 0, 0x20Au);
      cbData = 522;
      v5 = RegQueryValueExW(hKey, 0, 0, 0, (LPBYTE)Data, &cbData);
      v4 = v5;
      if ( v5 )
      {
        if ( v5 > 0 )
          v4 = (unsigned __int16)v5 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            117,
            (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
            (unsigned int)SubKey,
            v4);
      }
      else
      {
        FullNonHardCodedPath = HrMakeFullNonHardCodedPath(Data, v15);
        v4 = FullNonHardCodedPath;
        if ( FullNonHardCodedPath < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              116,
              (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
              (unsigned int)Data,
              FullNonHardCodedPath);
        }
        else
        {
          v7 = -1;
          do
            ++v7;
          while ( v15[v7] );
          v8 = (unsigned int)(v7 + 1);
          v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8);
          *a2 = v9;
          if ( v9 )
          {
            *v9 = 0;
            StringCchCopyW(*a2, (unsigned int)v8, v15);
          }
          else
          {
            v4 = -2147024882;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_SD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                115,
                (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
                (unsigned int)v15,
                14);
          }
        }
      }
    }
    RegCloseKey(hKey);
    goto LABEL_26;
  }
  v4 = 1;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      118,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (unsigned int)SubKey,
      1);
LABEL_26:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
    WPP_SF_d(v10[2], 119, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18000d8b8  mov     [rsp-8+arg_10], rbx
0x18000d8bd  mov     [rsp-8+arg_18], rsi
0x18000d8c2  push    rbp
0x18000d8c3  push    rdi
0x18000d8c4  push    r12
0x18000d8c6  push    r14
0x18000d8c8  push    r15
0x18000d8ca  lea     rbp, [rsp-400h]
0x18000d8d2  sub     rsp, 500h
0x18000d8d9  mov     rax, cs:__security_cookie
0x18000d8e0  xor     rax, rsp
0x18000d8e3  mov     [rbp+420h+var_30], rax
0x18000d8ea  xor     r15d, r15d
0x18000d8ed  mov     rsi, rdx
0x18000d8f0  mov     [rsp+520h+hKey], r15
0x18000d8f5  mov     rbx, rcx
0x18000d8f8  test    rdx, rdx
0x18000d8fb  jz      short loc_18000D900
0x18000d8fd  mov     [rdx], r15
0x18000d900  mov     edi, 41h ; 'A'
0x18000d905  mov     [rsp+520h+SubKey], r15w
0x18000d90b  mov     edx, edi; unsigned __int64
0x18000d90d  lea     r8, aClsid_0; "CLSID"
0x18000d914  lea     rcx, [rsp+520h+SubKey]; unsigned __int16 *
0x18000d919  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d91e  lea     r8, qword_18003C618; unsigned __int16 *
0x18000d925  mov     edx, edi; unsigned __int64
0x18000d927  lea     rcx, [rsp+520h+SubKey]; unsigned __int16 *
0x18000d92c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d931  mov     r8, rbx; unsigned __int16 *
0x18000d934  lea     rcx, [rsp+520h+SubKey]; unsigned __int16 *
0x18000d939  mov     edx, edi; unsigned __int64
0x18000d93b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d940  lea     r8, qword_18003C618; unsigned __int16 *
0x18000d947  mov     edx, edi; unsigned __int64
0x18000d949  lea     rcx, [rsp+520h+SubKey]; unsigned __int16 *
0x18000d94e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d953  lea     r8, aInprocserver32; "InprocServer32"
0x18000d95a  mov     edx, edi; unsigned __int64
0x18000d95c  lea     rcx, [rsp+520h+SubKey]; unsigned __int16 *
0x18000d961  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d966  lea     rax, [rsp+520h+hKey]
0x18000d96b  mov     r9d, 20019h; samDesired
0x18000d971  xor     r8d, r8d; ulOptions
0x18000d974  mov     [rsp+520h+phkResult], rax; phkResult
0x18000d979  lea     rdx, [rsp+520h+SubKey]; lpSubKey
0x18000d97e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000d985  call    cs:__imp_RegOpenKeyExW
0x18000d98b  lea     r12, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000d992  test    eax, eax
0x18000d994  jnz     loc_18000DAE3
0x18000d99a  lea     rdi, WPP_GLOBAL_Control
0x18000d9a1  mov     ebx, r15d
0x18000d9a4  test    rsi, rsi
0x18000d9a7  jz      loc_18000DAD6
0x18000d9ad  mov     ebx, 20Ah
0x18000d9b2  lea     rcx, [rbp+420h+Data]; void *
0x18000d9b9  mov     r8d, ebx; Size
0x18000d9bc  xor     edx, edx; Val
0x18000d9be  call    memset_0
0x18000d9c3  mov     rcx, [rsp+520h+hKey]; hKey
0x18000d9c8  lea     rax, [rsp+520h+cbData]
0x18000d9cd  mov     [rsp+520h+lpcbData], rax; lpcbData
0x18000d9d2  xor     r9d, r9d; lpType
0x18000d9d5  lea     rax, [rbp+420h+Data]
0x18000d9dc  mov     [rsp+520h+cbData], ebx
0x18000d9e0  xor     r8d, r8d; lpReserved
0x18000d9e3  mov     [rsp+520h+phkResult], rax; lpData
0x18000d9e8  xor     edx, edx; lpValueName
0x18000d9ea  call    cs:__imp_RegQueryValueExW
0x18000d9f0  mov     ebx, eax
0x18000d9f2  test    eax, eax
0x18000d9f4  jnz     loc_18000DA9F
0x18000d9fa  lea     rdx, [rbp+420h+var_450]; unsigned __int16 *
0x18000d9fe  lea     rcx, [rbp+420h+Data]; lpSrc
0x18000da05  call    ?HrMakeFullNonHardCodedPath@@YAJQEAGPEAGI@Z; HrMakeFullNonHardCodedPath(ushort * const,ushort *,uint)
0x18000da0a  mov     ebx, eax
0x18000da0c  test    eax, eax
0x18000da0e  js      short loc_18000DA7B
0x18000da10  lea     rcx, [rbp+420h+var_450]
0x18000da14  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000da18  inc     rax
0x18000da1b  cmp     [rcx+rax*2], r15w
0x18000da20  jnz     short loc_18000DA18
0x18000da22  inc     eax
0x18000da24  mov     r14d, eax
0x18000da27  lea     rcx, [rax+rax]; cb
0x18000da2b  call    cs:__imp_CoTaskMemAlloc
0x18000da31  mov     [rsi], rax
0x18000da34  test    rax, rax
0x18000da37  jz      short loc_18000DA51
0x18000da39  mov     [rax], r15w
0x18000da3d  lea     r8, [rbp+420h+var_450]; unsigned __int16 *
0x18000da41  mov     rcx, [rsi]; unsigned __int16 *
0x18000da44  mov     edx, r14d; unsigned __int64
0x18000da47  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000da4c  jmp     loc_18000DAD6
0x18000da51  mov     ebx, 8007000Eh
0x18000da56  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da5d  cmp     rcx, rdi
0x18000da60  jz      short loc_18000DAD6
0x18000da62  test    byte ptr [rcx+1Ch], 4
0x18000da66  jz      short loc_18000DAD6
0x18000da68  mov     edx, 73h ; 's'
0x18000da6d  mov     dword ptr [rsp+520h+phkResult], 8007000Eh
0x18000da75  lea     r9, [rbp+420h+var_450]
0x18000da79  jmp     short loc_18000DACA
0x18000da7b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da82  cmp     rcx, rdi
0x18000da85  jz      short loc_18000DAD6
0x18000da87  test    byte ptr [rcx+1Ch], 4
0x18000da8b  jz      short loc_18000DAD6
0x18000da8d  mov     edx, 74h ; 't'
0x18000da92  mov     dword ptr [rsp+520h+phkResult], eax
0x18000da96  lea     r9, [rbp+420h+Data]
0x18000da9d  jmp     short loc_18000DACA
0x18000da9f  jle     short loc_18000DAAA
0x18000daa1  movzx   ebx, ax
0x18000daa4  or      ebx, 80070000h
0x18000daaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dab1  cmp     rcx, rdi
0x18000dab4  jz      short loc_18000DAD6
0x18000dab6  test    byte ptr [rcx+1Ch], 4
0x18000daba  jz      short loc_18000DAD6
0x18000dabc  mov     edx, 75h ; 'u'
0x18000dac1  mov     dword ptr [rsp+520h+phkResult], ebx
0x18000dac5  lea     r9, [rsp+520h+SubKey]
0x18000daca  mov     rcx, [rcx+10h]
0x18000dace  mov     r8, r12
0x18000dad1  call    WPP_SF_SD
0x18000dad6  mov     rcx, [rsp+520h+hKey]; hKey
0x18000dadb  call    cs:__imp_RegCloseKey
0x18000dae1  jmp     short loc_18000DB19
0x18000dae3  mov     ebx, 1
0x18000dae8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000daef  lea     rdi, WPP_GLOBAL_Control
0x18000daf6  cmp     rcx, rdi
0x18000daf9  jz      short loc_18000DB3F
0x18000dafb  test    byte ptr [rcx+1Ch], 10h
0x18000daff  jz      short loc_18000DB20
0x18000db01  mov     rcx, [rcx+10h]
0x18000db05  lea     edx, [rbx+75h]
0x18000db08  lea     r9, [rsp+520h+SubKey]
0x18000db0d  mov     dword ptr [rsp+520h+phkResult], ebx
0x18000db11  mov     r8, r12
0x18000db14  call    WPP_SF_SD
0x18000db19  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db20  cmp     rcx, rdi
0x18000db23  jz      short loc_18000DB3F
0x18000db25  test    byte ptr [rcx+1Ch], 10h
0x18000db29  jz      short loc_18000DB3F
0x18000db2b  mov     rcx, [rcx+10h]
0x18000db2f  mov     edx, 77h ; 'w'
0x18000db34  mov     r9d, ebx
0x18000db37  mov     r8, r12
0x18000db3a  call    WPP_SF_d
0x18000db3f  mov     eax, ebx
0x18000db41  mov     rcx, [rbp+420h+var_30]
0x18000db48  xor     rcx, rsp; StackCookie
0x18000db4b  call    __security_check_cookie
0x18000db50  lea     r11, [rsp+520h+var_20]
0x18000db58  mov     rbx, [r11+40h]
0x18000db5c  mov     rsi, [r11+48h]
0x18000db60  mov     rsp, r11
0x18000db63  pop     r15
0x18000db65  pop     r14
0x18000db67  pop     r12
0x18000db69  pop     rdi
0x18000db6a  pop     rbp
0x18000db6b  retn
```
