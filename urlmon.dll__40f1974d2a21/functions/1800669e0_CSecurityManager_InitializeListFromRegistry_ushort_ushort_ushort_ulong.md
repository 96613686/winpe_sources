# CSecurityManager::InitializeListFromRegistry(ushort *,ushort *,ushort * * *,ulong *)

- ea: `0x1800669e0`
- end: `0x180066f36`
- name: `?InitializeListFromRegistry@CSecurityManager@@KAJPEAG0PEAPEAPEAGPEAK@Z`
- size: `1366`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 ***, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800101fc`
- `0x18009db34`
- `0x1800ff6ec`

## callees

- `0x1800150e0`
- `0x18001b1d0`
- `0x180056ed0`
- `0x180060640`
- `0x1800669e0`
- `0x180066f40`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066c68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066cbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066d0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066d5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066c68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066cbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066d0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066d5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066adc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066b07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066b3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066b69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066adc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066b07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066b3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066b69`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180066bcd`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180066be4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180066bfb`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180066c23`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180066bcd`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180066be4`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180066bfb`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180066c23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066f24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066f24`

## pseudocode

```c
__int64 __fastcall CSecurityManager::InitializeListFromRegistry(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 ***a3,
        unsigned int *a4)
{
  int v6; // r12d
  unsigned int v9; // ebx
  unsigned __int16 **v10; // r13
  int v11; // r12d
  unsigned __int64 v12; // rcx
  unsigned int v13; // r14d
  unsigned int v15; // r15d
  const unsigned int **v16; // rax
  unsigned int i; // ecx
  unsigned __int16 *v18; // rax
  unsigned int j; // edi
  unsigned __int16 *v20; // rcx
  unsigned int v21; // [rsp+48h] [rbp-C0h]
  unsigned int v22; // [rsp+4Ch] [rbp-BCh] BYREF
  unsigned int v23[2]; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v26; // [rsp+64h] [rbp-A4h] BYREF
  unsigned int v27[2]; // [rsp+68h] [rbp-A0h] BYREF
  const unsigned int **v28; // [rsp+70h] [rbp-98h]
  unsigned int v29[2]; // [rsp+78h] [rbp-90h] BYREF
  const unsigned int *v30; // [rsp+80h] [rbp-88h] BYREF
  HUSKEY v31; // [rsp+88h] [rbp-80h]
  int v32; // [rsp+90h] [rbp-78h]
  __int64 v33; // [rsp+94h] [rbp-74h]
  const unsigned int *v34; // [rsp+A0h] [rbp-68h] BYREF
  HUSKEY hUSKey; // [rsp+A8h] [rbp-60h]
  int v36; // [rsp+B0h] [rbp-58h]
  __int64 v37; // [rsp+B4h] [rbp-54h]
  const unsigned int *v38; // [rsp+C0h] [rbp-48h] BYREF
  HUSKEY v39; // [rsp+C8h] [rbp-40h]
  int v40; // [rsp+D0h] [rbp-38h]
  __int64 v41; // [rsp+D4h] [rbp-34h]
  const unsigned int *v42; // [rsp+E0h] [rbp-28h] BYREF
  HUSKEY v43; // [rsp+E8h] [rbp-20h]
  int v44; // [rsp+F0h] [rbp-18h]
  __int64 v45; // [rsp+F4h] [rbp-14h]
  unsigned __int16 v46[264]; // [rsp+108h] [rbp+0h] BYREF

  v6 = 0;
  v30 = &CRegKey::`vftable';
  v42 = &CRegKey::`vftable';
  v38 = &CRegKey::`vftable';
  v34 = &CRegKey::`vftable';
  v23[0] = 0;
  v22 = 0;
  v27[0] = 0;
  v27[1] = 0;
  v25 = 0;
  v26 = 0;
  v23[1] = 260;
  v29[0] = 0;
  v32 = g_bUseHKLMOnly;
  v31 = 0;
  v33 = 0;
  v44 = g_bUseHKLMOnly;
  v43 = 0;
  v45 = 0;
  v40 = g_bUseHKLMOnly;
  v39 = 0;
  v41 = 0;
  v36 = g_bUseHKLMOnly;
  hUSKey = 0;
  v37 = 0;
  hKey = 0;
  if ( a3 && a4 )
  {
    v9 = 0;
    *a3 = 0;
    *a4 = 0;
    v10 = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey) )
    {
      RegCloseKey(hKey);
      v6 = 1;
      LODWORD(v33) = 1;
      v32 = 1;
      if ( !CRegKey::Open((CRegKey *)&v30, 0, a2, 0x20019u) )
        CRegKey::QuerySubKeyInfo((CRegKey *)&v30, v23, &v22, v27);
    }
    if ( RegOpenKeyExW(HKEY_CURRENT_USER, a2, 0, 0x20019u, &hKey) )
    {
      if ( v6 )
      {
        v11 = 0;
      }
      else
      {
        if ( RegOpenKeyExW(HKEY_CURRENT_USER, a1, 0, 0x20019u, &hKey) )
        {
          v11 = 0;
        }
        else
        {
          RegCloseKey(hKey);
          v11 = 0;
          LODWORD(v41) = 0;
          v32 = 0;
          if ( !CRegKey::Open((CRegKey *)&v38, 0, a1, 0x20019u) )
            CRegKey::QuerySubKeyInfo((CRegKey *)&v38, v23, &v22, &v26);
        }
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a1, 0, 0x20019u, &hKey) )
        {
          RegCloseKey(hKey);
          LODWORD(v37) = 1;
          v32 = 1;
          if ( !CRegKey::Open((CRegKey *)&v34, 0, a1, 0x20019u) )
            CRegKey::QuerySubKeyInfo((CRegKey *)&v34, v23, &v22, &v27[1]);
        }
      }
    }
    else
    {
      RegCloseKey(hKey);
      v11 = 0;
      LODWORD(v45) = 0;
      v32 = 0;
      if ( !CRegKey::Open((CRegKey *)&v42, 0, a2, 0x20019u) )
        CRegKey::QuerySubKeyInfo((CRegKey *)&v42, v23, &v22, &v25);
    }
    v12 = v27[0] + v27[1] + v26 + v25;
    if ( !(_DWORD)v12 )
    {
      v13 = 0;
LABEL_11:
      *a3 = v10;
      *a4 = v13;
      goto LABEL_12;
    }
    v10 = (unsigned __int16 **)operator new(saturated_mul(v12, 8u));
    if ( v10 )
    {
      v28 = 0;
      v13 = 0;
LABEL_36:
      if ( v11 < 4 )
      {
        v15 = 0;
        if ( v11 )
        {
          switch ( v11 )
          {
            case 1:
              v15 = v27[0];
              v16 = &v30;
              v28 = &v30;
              break;
            case 2:
              v15 = v26;
              v16 = &v38;
              v28 = &v38;
              break;
            case 3:
              v15 = v25;
              v16 = &v42;
              v28 = &v42;
              break;
            default:
              v16 = v28;
              break;
          }
        }
        else
        {
          v15 = v27[1];
          v16 = &v34;
          v28 = &v34;
        }
        for ( i = 0; ; i = v21 + 1 )
        {
          v21 = i;
          if ( i >= v15 )
          {
            ++v11;
            goto LABEL_36;
          }
          v23[1] = 260;
          if ( !CRegKey::EnumValue((CRegKey *)v16, i, v46, &v23[1], v29, 0, 0) )
          {
            v18 = (unsigned __int16 *)operator new(saturated_mul(v23[1] + 1, 2u));
            v10[v13] = v18;
            if ( !v18 )
            {
              v9 = -2147024882;
              goto LABEL_54;
            }
            v9 = StringCchCopyNW(v18, v23[1] + 1, v46, v23[1]);
            ++v13;
          }
          v16 = v28;
        }
      }
      if ( !v9 )
        goto LABEL_11;
LABEL_54:
      for ( j = 0; j < v13; ++j )
      {
        v20 = v10[j];
        if ( v20 )
          CoTaskMemFree(v20);
      }
      CoTaskMemFree(v10);
    }
    else
    {
      v9 = -2147024882;
    }
  }
  else
  {
    v9 = -2147024809;
  }
LABEL_12:
  v34 = &CRegKey::`vftable';
  if ( hUSKey )
  {
    SHRegCloseUSKey(hUSKey);
    hUSKey = 0;
  }
  v38 = &CRegKey::`vftable';
  if ( v39 )
  {
    SHRegCloseUSKey(v39);
    v39 = 0;
  }
  v42 = &CRegKey::`vftable';
  if ( v43 )
  {
    SHRegCloseUSKey(v43);
    v43 = 0;
  }
  v30 = &CRegKey::`vftable';
  if ( v31 )
    SHRegCloseUSKey(v31);
  return v9;
}

```

## disassembly

```asm
0x1800669e0  mov     r11, rsp
0x1800669e3  push    rbp
0x1800669e4  push    rbx
0x1800669e5  lea     rbp, [r11-268h]
0x1800669ec  sub     rsp, 358h
0x1800669f3  mov     rax, cs:__security_cookie
0x1800669fa  xor     rax, rsp
0x1800669fd  mov     [rbp+260h+var_50], rax
0x180066a04  mov     eax, cs:?g_bUseHKLMOnly@@3HA; int g_bUseHKLMOnly
0x180066a0a  mov     [r11-18h], rsi
0x180066a0e  mov     rsi, r9
0x180066a11  mov     [r11-20h], rdi
0x180066a15  mov     rdi, r8
0x180066a18  mov     [r11-28h], r12
0x180066a1c  xor     r12d, r12d
0x180066a1f  mov     [r11-30h], r13
0x180066a23  lea     r13, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180066a2a  mov     [r11-38h], r14
0x180066a2e  mov     r14, rdx
0x180066a31  mov     [r11-40h], r15
0x180066a35  mov     r15, rcx
0x180066a38  mov     [rsp+360h+var_2E8], r13
0x180066a3d  mov     [rbp+260h+var_288], r13
0x180066a41  mov     [rbp+260h+var_2A8], r13
0x180066a45  mov     [rbp+260h+var_2C8], r13
0x180066a49  mov     [rsp+360h+var_318], r12d
0x180066a4e  mov     [rsp+360h+var_31C], r12d
0x180066a53  mov     [rsp+360h+var_300], r12d
0x180066a58  mov     [rsp+360h+var_300+4], r12d
0x180066a5d  mov     [rsp+360h+var_308], r12d
0x180066a62  mov     [rsp+360h+var_304], r12d
0x180066a67  mov     [rsp+360h+var_318+4], 104h
0x180066a6f  mov     [rsp+360h+var_2F0], r12d
0x180066a74  mov     [rbp+260h+var_2D8], eax
0x180066a77  mov     [rbp+260h+var_2E0], r12
0x180066a7b  mov     [rbp+260h+var_2D4], r12
0x180066a7f  mov     [rbp+260h+var_278], eax
0x180066a82  mov     [rbp+260h+var_280], r12
0x180066a86  mov     [rbp+260h+var_274], r12
0x180066a8a  mov     [rbp+260h+var_298], eax
0x180066a8d  mov     [rbp+260h+var_2A0], r12
0x180066a91  mov     [rbp+260h+var_294], r12
0x180066a95  mov     [rbp+260h+var_2B8], eax
0x180066a98  mov     [rbp+260h+hUSKey], r12
0x180066a9c  mov     [rbp+260h+var_2B4], r12
0x180066aa0  mov     [rsp+360h+hKey], r12
0x180066aa5  test    r8, r8
0x180066aa8  jz      loc_180066C44
0x180066aae  test    r9, r9
0x180066ab1  jz      loc_180066C44
0x180066ab7  xor     ebx, ebx
0x180066ab9  lea     rax, [rsp+360h+hKey]
0x180066abe  mov     [r8], rbx
0x180066ac1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180066ac8  mov     [r9], ebx
0x180066acb  xor     r8d, r8d; ulOptions
0x180066ace  mov     r9d, 20019h; samDesired
0x180066ad4  mov     [rsp+360h+phkResult], rax; phkResult
0x180066ad9  mov     r13d, r12d
0x180066adc  call    cs:__imp_RegOpenKeyExW
0x180066ae2  test    eax, eax
0x180066ae4  jz      loc_180066C63
0x180066aea  lea     rax, [rsp+360h+hKey]
0x180066aef  mov     r9d, 20019h; samDesired
0x180066af5  xor     r8d, r8d; ulOptions
0x180066af8  mov     [rsp+360h+phkResult], rax; phkResult
0x180066afd  mov     rdx, r14; lpSubKey
0x180066b00  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180066b07  call    cs:__imp_RegOpenKeyExW
0x180066b0d  test    eax, eax
0x180066b0f  jz      loc_180066CB7
0x180066b15  test    r12d, r12d
0x180066b18  jnz     loc_180066C4E
0x180066b1e  lea     rax, [rsp+360h+hKey]
0x180066b23  mov     r9d, 20019h; samDesired
0x180066b29  xor     r8d, r8d; ulOptions
0x180066b2c  mov     [rsp+360h+phkResult], rax; phkResult
0x180066b31  mov     rdx, r15; lpSubKey
0x180066b34  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180066b3b  call    cs:__imp_RegOpenKeyExW
0x180066b41  test    eax, eax
0x180066b43  jz      loc_180066D06
0x180066b49  xor     r12d, r12d
0x180066b4c  lea     rax, [rsp+360h+hKey]
0x180066b51  mov     r9d, 20019h; samDesired
0x180066b57  xor     r8d, r8d; ulOptions
0x180066b5a  mov     [rsp+360h+phkResult], rax; phkResult
0x180066b5f  mov     rdx, r15; lpSubKey
0x180066b62  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180066b69  call    cs:__imp_RegOpenKeyExW
0x180066b6f  test    eax, eax
0x180066b71  jz      loc_180066D55
0x180066b77  mov     ecx, [rsp+360h+var_308]
0x180066b7b  add     ecx, [rsp+360h+var_304]
0x180066b7f  add     ecx, [rsp+360h+var_300+4]
0x180066b83  add     ecx, [rsp+360h+var_300]
0x180066b87  jnz     loc_180066DA7
0x180066b8d  mov     r14d, ebx
0x180066b90  mov     [rdi], r13
0x180066b93  xor     r12d, r12d
0x180066b96  mov     [rsi], r14d
0x180066b99  lea     r13, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180066ba0  mov     rcx, [rbp+260h+hUSKey]; hUSKey
0x180066ba4  mov     r15, [rsp+360h+var_38]
0x180066bac  mov     r14, [rsp+360h+var_30]
0x180066bb4  mov     rdi, [rsp+360h+var_18]
0x180066bbc  mov     rsi, [rsp+350h]
0x180066bc4  mov     [rbp+260h+var_2C8], r13
0x180066bc8  test    rcx, rcx
0x180066bcb  jz      short loc_180066BD7
0x180066bcd  call    cs:__imp_SHRegCloseUSKey
0x180066bd3  mov     [rbp+260h+hUSKey], r12
0x180066bd7  mov     rcx, [rbp+260h+var_2A0]; hUSKey
0x180066bdb  mov     [rbp+260h+var_2A8], r13
0x180066bdf  test    rcx, rcx
0x180066be2  jz      short loc_180066BEE
0x180066be4  call    cs:__imp_SHRegCloseUSKey
0x180066bea  mov     [rbp+260h+var_2A0], r12
0x180066bee  mov     rcx, [rbp+260h+var_280]; hUSKey
0x180066bf2  mov     [rbp+260h+var_288], r13
0x180066bf6  test    rcx, rcx
0x180066bf9  jz      short loc_180066C05
0x180066bfb  call    cs:__imp_SHRegCloseUSKey
0x180066c01  mov     [rbp+260h+var_280], r12
0x180066c05  mov     rcx, [rbp+260h+var_2E0]; hUSKey
0x180066c09  mov     r12, [rsp+360h+var_20]
0x180066c11  mov     [rsp+360h+var_2E8], r13
0x180066c16  mov     r13, [rsp+360h+var_28]
0x180066c1e  test    rcx, rcx
0x180066c21  jz      short loc_180066C29
0x180066c23  call    cs:__imp_SHRegCloseUSKey
0x180066c29  mov     eax, ebx
0x180066c2b  mov     rcx, [rbp+260h+var_50]
0x180066c32  xor     rcx, rsp; StackCookie
0x180066c35  call    __security_check_cookie
0x180066c3a  add     rsp, 358h
0x180066c41  pop     rbx
0x180066c42  pop     rbp
0x180066c43  retn
0x180066c44  mov     ebx, 80070057h
0x180066c49  jmp     loc_180066BA0
0x180066c4e  xor     r12d, r12d
0x180066c51  jmp     loc_180066B77
0x180066c56  test    ebx, ebx
0x180066c58  jz      loc_180066B90
0x180066c5e  jmp     loc_180066EFD
0x180066c63  mov     rcx, [rsp+360h+hKey]; hKey
0x180066c68  call    cs:__imp_RegCloseKey
0x180066c6e  mov     r12d, 1
0x180066c74  lea     rcx, [rsp+360h+var_2E8]; this
0x180066c79  mov     r9d, 20019h; unsigned int
0x180066c7f  mov     dword ptr [rbp+260h+var_2D4], r12d
0x180066c83  mov     r8, r14; unsigned __int16 *
0x180066c86  mov     [rbp+260h+var_2D8], r12d
0x180066c8a  xor     edx, edx; void *
0x180066c8c  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x180066c91  test    eax, eax
0x180066c93  jnz     loc_180066AEA
0x180066c99  lea     r9, [rsp+360h+var_300]; unsigned int *
0x180066c9e  lea     r8, [rsp+360h+var_31C]; unsigned int *
0x180066ca3  lea     rdx, [rsp+360h+var_318]; unsigned int *
0x180066ca8  lea     rcx, [rsp+360h+var_2E8]; this
0x180066cad  call    ?QuerySubKeyInfo@CRegKey@@QEAAJPEAK00@Z; CRegKey::QuerySubKeyInfo(ulong *,ulong *,ulong *)
0x180066cb2  jmp     loc_180066AEA
0x180066cb7  mov     rcx, [rsp+360h+hKey]; hKey
0x180066cbc  call    cs:__imp_RegCloseKey
0x180066cc2  xor     r12d, r12d
0x180066cc5  lea     rcx, [rbp+260h+var_288]; this
0x180066cc9  mov     r9d, 20019h; unsigned int
0x180066ccf  mov     dword ptr [rbp+260h+var_274], r12d
0x180066cd3  mov     r8, r14; unsigned __int16 *
0x180066cd6  mov     [rbp+260h+var_2D8], r12d
0x180066cda  xor     edx, edx; void *
0x180066cdc  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x180066ce1  test    eax, eax
0x180066ce3  jnz     loc_180066B77
0x180066ce9  lea     r9, [rsp+360h+var_308]; unsigned int *
0x180066cee  lea     r8, [rsp+360h+var_31C]; unsigned int *
0x180066cf3  lea     rdx, [rsp+360h+var_318]; unsigned int *
0x180066cf8  lea     rcx, [rbp+260h+var_288]; this
0x180066cfc  call    ?QuerySubKeyInfo@CRegKey@@QEAAJPEAK00@Z; CRegKey::QuerySubKeyInfo(ulong *,ulong *,ulong *)
0x180066d01  jmp     loc_180066B77
0x180066d06  mov     rcx, [rsp+360h+hKey]; hKey
0x180066d0b  call    cs:__imp_RegCloseKey
0x180066d11  xor     r12d, r12d
0x180066d14  lea     rcx, [rbp+260h+var_2A8]; this
0x180066d18  mov     r9d, 20019h; unsigned int
0x180066d1e  mov     dword ptr [rbp+260h+var_294], r12d
0x180066d22  mov     r8, r15; unsigned __int16 *
0x180066d25  mov     [rbp+260h+var_2D8], r12d
0x180066d29  xor     edx, edx; void *
0x180066d2b  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x180066d30  test    eax, eax
0x180066d32  jnz     loc_180066B4C
0x180066d38  lea     r9, [rsp+360h+var_304]; unsigned int *
0x180066d3d  lea     r8, [rsp+360h+var_31C]; unsigned int *
0x180066d42  lea     rdx, [rsp+360h+var_318]; unsigned int *
0x180066d47  lea     rcx, [rbp+260h+var_2A8]; this
0x180066d4b  call    ?QuerySubKeyInfo@CRegKey@@QEAAJPEAK00@Z; CRegKey::QuerySubKeyInfo(ulong *,ulong *,ulong *)
0x180066d50  jmp     loc_180066B4C
0x180066d55  mov     rcx, [rsp+360h+hKey]; hKey
0x180066d5a  call    cs:__imp_RegCloseKey
0x180066d60  mov     r9d, 20019h; unsigned int
0x180066d66  mov     dword ptr [rbp+260h+var_2B4], 1
0x180066d6d  mov     r8, r15; unsigned __int16 *
0x180066d70  mov     [rbp+260h+var_2D8], 1
0x180066d77  xor     edx, edx; void *
0x180066d79  lea     rcx, [rbp+260h+var_2C8]; this
0x180066d7d  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x180066d82  test    eax, eax
0x180066d84  jnz     loc_180066B77
0x180066d8a  lea     r9, [rsp+360h+var_300+4]; unsigned int *
0x180066d8f  lea     r8, [rsp+360h+var_31C]; unsigned int *
0x180066d94  lea     rdx, [rsp+360h+var_318]; unsigned int *
0x180066d99  lea     rcx, [rbp+260h+var_2C8]; this
0x180066d9d  call    ?QuerySubKeyInfo@CRegKey@@QEAAJPEAK00@Z; CRegKey::QuerySubKeyInfo(ulong *,ulong *,ulong *)
0x180066da2  jmp     loc_180066B77
0x180066da7  mov     eax, 8
0x180066dac  mul     rcx
0x180066daf  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180066db6  cmovb   rax, rcx
0x180066dba  mov     rcx, rax; Size
0x180066dbd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180066dc2  mov     r13, rax
0x180066dc5  test    rax, rax
0x180066dc8  jnz     short loc_180066DDB
0x180066dca  mov     ebx, 8007000Eh
0x180066dcf  lea     r13, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180066dd6  jmp     loc_180066BA0
0x180066ddb  mov     [rsp+360h+var_2F8], r12
0x180066de0  mov     r14d, ebx
0x180066de3  cmp     r12d, 4
0x180066de7  jge     loc_180066C56
0x180066ded  xor     r15d, r15d
0x180066df0  mov     ecx, r12d
0x180066df3  test    r12d, r12d
0x180066df6  jz      short loc_180066E38
0x180066df8  sub     ecx, 1
0x180066dfb  jz      short loc_180066E27
0x180066dfd  sub     ecx, 1
0x180066e00  jz      short loc_180066E17
0x180066e02  cmp     ecx, 1
0x180066e05  jnz     short loc_180066E48
0x180066e07  mov     r15d, [rsp+360h+var_308]
0x180066e0c  lea     rax, [rbp+260h+var_288]
0x180066e10  mov     [rsp+360h+var_2F8], rax
0x180066e15  jmp     short loc_180066E4D
0x180066e17  mov     r15d, [rsp+360h+var_304]
0x180066e1c  lea     rax, [rbp+260h+var_2A8]
0x180066e20  mov     [rsp+360h+var_2F8], rax
0x180066e25  jmp     short loc_180066E4D
0x180066e27  mov     r15d, [rsp+360h+var_300]
0x180066e2c  lea     rax, [rsp+360h+var_2E8]
0x180066e31  mov     [rsp+360h+var_2F8], rax
0x180066e36  jmp     short loc_180066E4D
0x180066e38  mov     r15d, [rsp+360h+var_300+4]
0x180066e3d  lea     rax, [rbp+260h+var_2C8]
0x180066e41  mov     [rsp+360h+var_2F8], rax
0x180066e46  jmp     short loc_180066E4D
0x180066e48  mov     rax, [rsp+360h+var_2F8]
0x180066e4d  xor     ecx, ecx
0x180066e4f  mov     [rsp+360h+var_320], ecx
0x180066e53  cmp     ecx, r15d
0x180066e56  jnb     loc_180066EF0
0x180066e5c  lea     rdx, [rsp+360h+var_2F0]
0x180066e61  mov     qword ptr [rsp+30h], 0; unsigned int *
0x180066e6a  mov     [rsp+360h+var_338], 0; void *
0x180066e73  lea     r9, [rsp+360h+var_318+4]; unsigned int *
0x180066e78  mov     [rsp+360h+phkResult], rdx; unsigned int *
0x180066e7d  lea     r8, [rbp+260h+var_260]; unsigned __int16 *
0x180066e81  mov     edx, ecx; unsigned int
0x180066e83  mov     [rsp+360h+var_318+4], 104h
0x180066e8b  mov     rcx, rax; this
0x180066e8e  call    ?EnumValue@CRegKey@@QEAAJKPEAGPEAK1PEAX1@Z; CRegKey::EnumValue(ulong,ushort *,ulong *,ulong *,void *,ulong *)
0x180066e93  test    eax, eax
0x180066e95  jnz     short loc_180066EE0
0x180066e97  mov     ecx, [rsp+360h+var_318+4]
0x180066e9b  mov     eax, 2
0x180066ea0  inc     ecx
0x180066ea2  mul     rcx
0x180066ea5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180066eac  cmovb   rax, rcx
0x180066eb0  mov     rcx, rax; Size
0x180066eb3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180066eb8  mov     ecx, r14d
0x180066ebb  mov     [r13+rcx*8+0], rax
0x180066ec0  test    rax, rax
0x180066ec3  jz      short loc_180066EF8
0x180066ec5  mov     ecx, [rsp+360h+var_318+4]
0x180066ec9  lea     r8, [rbp+260h+var_260]; unsigned __int16 *
0x180066ecd  mov     r9d, ecx; unsigned __int64
0x180066ed0  lea     edx, [rcx+1]; unsigned __int64
0x180066ed3  mov     rcx, rax; unsigned __int16 *
0x180066ed6  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180066edb  mov     ebx, eax
0x180066edd  inc     r14d
0x180066ee0  mov     ecx, [rsp+360h+var_320]
0x180066ee4  mov     rax, [rsp+360h+var_2F8]
0x180066ee9  inc     ecx
0x180066eeb  jmp     loc_180066E4F
  ... truncated ...
```
