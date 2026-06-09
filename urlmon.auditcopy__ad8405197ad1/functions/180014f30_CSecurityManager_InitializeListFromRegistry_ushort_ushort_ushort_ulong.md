# CSecurityManager::InitializeListFromRegistry(ushort *,ushort *,ushort * * *,ulong *)

- ea: `0x180014f30`
- end: `0x1800154db`
- name: `?InitializeListFromRegistry@CSecurityManager@@KAJPEAG0PEAPEAPEAGPEAK@Z`
- size: `1451`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 ***, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015f80`
- `0x1800a47d4`
- `0x18010a688`

## callees

- `0x180014f30`
- `0x18001db50`
- `0x180021650`
- `0x18005c8d0`
- `0x180063d60`
- `0x18006b840`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800151e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015243`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800152ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800151e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015243`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800152ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001502c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001505d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015097`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800150cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001502c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001505d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015097`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800150cb`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180015135`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180015152`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18001516f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18001519d`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180015135`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180015152`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18001516f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18001519d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800154ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800154c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800154ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800154c3`

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
  DWORD i; // ecx
  unsigned __int16 *v18; // rax
  unsigned int j; // edi
  unsigned __int16 *v20; // rcx
  DWORD v21; // [rsp+48h] [rbp-C0h]
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
      if ( !(unsigned int)CRegKey::Open((CRegKey *)&v30, 0, a2, 0x20019u) )
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
          if ( !(unsigned int)CRegKey::Open((CRegKey *)&v38, 0, a1, 0x20019u) )
            CRegKey::QuerySubKeyInfo((CRegKey *)&v38, v23, &v22, &v26);
        }
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a1, 0, 0x20019u, &hKey) )
        {
          RegCloseKey(hKey);
          LODWORD(v37) = 1;
          v32 = 1;
          if ( !(unsigned int)CRegKey::Open((CRegKey *)&v34, 0, a1, 0x20019u) )
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
      if ( !(unsigned int)CRegKey::Open((CRegKey *)&v42, 0, a2, 0x20019u) )
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
0x180014f30  mov     r11, rsp
0x180014f33  push    rbp
0x180014f34  push    rbx
0x180014f35  lea     rbp, [r11-268h]
0x180014f3c  sub     rsp, 358h
0x180014f43  mov     rax, cs:__security_cookie
0x180014f4a  xor     rax, rsp
0x180014f4d  mov     [rbp+260h+var_50], rax
0x180014f54  mov     eax, cs:?g_bUseHKLMOnly@@3HA; int g_bUseHKLMOnly
0x180014f5a  mov     [r11-18h], rsi
0x180014f5e  mov     rsi, r9
0x180014f61  mov     [r11-20h], rdi
0x180014f65  mov     rdi, r8
0x180014f68  mov     [r11-28h], r12
0x180014f6c  xor     r12d, r12d
0x180014f6f  mov     [r11-30h], r13
0x180014f73  lea     r13, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180014f7a  mov     [r11-38h], r14
0x180014f7e  mov     r14, rdx
0x180014f81  mov     [r11-40h], r15
0x180014f85  mov     r15, rcx
0x180014f88  mov     [rsp+360h+var_2E8], r13
0x180014f8d  mov     [rbp+260h+var_288], r13
0x180014f91  mov     [rbp+260h+var_2A8], r13
0x180014f95  mov     [rbp+260h+var_2C8], r13
0x180014f99  mov     [rsp+360h+var_318], r12d
0x180014f9e  mov     [rsp+360h+var_31C], r12d
0x180014fa3  mov     [rsp+360h+var_300], r12d
0x180014fa8  mov     [rsp+360h+var_300+4], r12d
0x180014fad  mov     [rsp+360h+var_308], r12d
0x180014fb2  mov     [rsp+360h+var_304], r12d
0x180014fb7  mov     [rsp+360h+var_318+4], 104h
0x180014fbf  mov     [rsp+360h+var_2F0], r12d
0x180014fc4  mov     [rbp+260h+var_2D8], eax
0x180014fc7  mov     [rbp+260h+var_2E0], r12
0x180014fcb  mov     [rbp+260h+var_2D4], r12
0x180014fcf  mov     [rbp+260h+var_278], eax
0x180014fd2  mov     [rbp+260h+var_280], r12
0x180014fd6  mov     [rbp+260h+var_274], r12
0x180014fda  mov     [rbp+260h+var_298], eax
0x180014fdd  mov     [rbp+260h+var_2A0], r12
0x180014fe1  mov     [rbp+260h+var_294], r12
0x180014fe5  mov     [rbp+260h+var_2B8], eax
0x180014fe8  mov     [rbp+260h+hUSKey], r12
0x180014fec  mov     [rbp+260h+var_2B4], r12
0x180014ff0  mov     [rsp+360h+hKey], r12
0x180014ff5  test    r8, r8
0x180014ff8  jz      loc_1800151C5
0x180014ffe  test    r9, r9
0x180015001  jz      loc_1800151C5
0x180015007  xor     ebx, ebx
0x180015009  lea     rax, [rsp+360h+hKey]
0x18001500e  mov     [r8], rbx
0x180015011  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015018  mov     [r9], ebx
0x18001501b  xor     r8d, r8d; ulOptions
0x18001501e  mov     r9d, 20019h; samDesired
0x180015024  mov     [rsp+360h+phkResult], rax; phkResult
0x180015029  mov     r13d, r12d
0x18001502c  call    cs:__imp_RegOpenKeyExW
0x180015033  nop     dword ptr [rax+rax+00h]
0x180015038  test    eax, eax
0x18001503a  jz      loc_1800151E4
0x180015040  lea     rax, [rsp+360h+hKey]
0x180015045  mov     r9d, 20019h; samDesired
0x18001504b  xor     r8d, r8d; ulOptions
0x18001504e  mov     [rsp+360h+phkResult], rax; phkResult
0x180015053  mov     rdx, r14; lpSubKey
0x180015056  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001505d  call    cs:__imp_RegOpenKeyExW
0x180015064  nop     dword ptr [rax+rax+00h]
0x180015069  test    eax, eax
0x18001506b  jz      loc_18001523E
0x180015071  test    r12d, r12d
0x180015074  jnz     loc_1800151CF
0x18001507a  lea     rax, [rsp+360h+hKey]
0x18001507f  mov     r9d, 20019h; samDesired
0x180015085  xor     r8d, r8d; ulOptions
0x180015088  mov     [rsp+360h+phkResult], rax; phkResult
0x18001508d  mov     rdx, r15; lpSubKey
0x180015090  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180015097  call    cs:__imp_RegOpenKeyExW
0x18001509e  nop     dword ptr [rax+rax+00h]
0x1800150a3  test    eax, eax
0x1800150a5  jz      loc_180015293
0x1800150ab  xor     r12d, r12d
0x1800150ae  lea     rax, [rsp+360h+hKey]
0x1800150b3  mov     r9d, 20019h; samDesired
0x1800150b9  xor     r8d, r8d; ulOptions
0x1800150bc  mov     [rsp+360h+phkResult], rax; phkResult
0x1800150c1  mov     rdx, r15; lpSubKey
0x1800150c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800150cb  call    cs:__imp_RegOpenKeyExW
0x1800150d2  nop     dword ptr [rax+rax+00h]
0x1800150d7  test    eax, eax
0x1800150d9  jz      loc_1800152E8
0x1800150df  mov     ecx, [rsp+360h+var_308]
0x1800150e3  add     ecx, [rsp+360h+var_304]
0x1800150e7  add     ecx, [rsp+360h+var_300+4]
0x1800150eb  add     ecx, [rsp+360h+var_300]
0x1800150ef  jnz     loc_180015340
0x1800150f5  mov     r14d, ebx
0x1800150f8  mov     [rdi], r13
0x1800150fb  xor     r12d, r12d
0x1800150fe  mov     [rsi], r14d
0x180015101  lea     r13, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x180015108  mov     rcx, [rbp+260h+hUSKey]; hUSKey
0x18001510c  mov     r15, [rsp+360h+var_38]
0x180015114  mov     r14, [rsp+360h+var_30]
0x18001511c  mov     rdi, [rsp+360h+var_18]
0x180015124  mov     rsi, [rsp+350h]
0x18001512c  mov     [rbp+260h+var_2C8], r13
0x180015130  test    rcx, rcx
0x180015133  jz      short loc_180015145
0x180015135  call    cs:__imp_SHRegCloseUSKey
0x18001513c  nop     dword ptr [rax+rax+00h]
0x180015141  mov     [rbp+260h+hUSKey], r12
0x180015145  mov     rcx, [rbp+260h+var_2A0]; hUSKey
0x180015149  mov     [rbp+260h+var_2A8], r13
0x18001514d  test    rcx, rcx
0x180015150  jz      short loc_180015162
0x180015152  call    cs:__imp_SHRegCloseUSKey
0x180015159  nop     dword ptr [rax+rax+00h]
0x18001515e  mov     [rbp+260h+var_2A0], r12
0x180015162  mov     rcx, [rbp+260h+var_280]; hUSKey
0x180015166  mov     [rbp+260h+var_288], r13
0x18001516a  test    rcx, rcx
0x18001516d  jz      short loc_18001517F
0x18001516f  call    cs:__imp_SHRegCloseUSKey
0x180015176  nop     dword ptr [rax+rax+00h]
0x18001517b  mov     [rbp+260h+var_280], r12
0x18001517f  mov     rcx, [rbp+260h+var_2E0]; hUSKey
0x180015183  mov     r12, [rsp+360h+var_20]
0x18001518b  mov     [rsp+360h+var_2E8], r13
0x180015190  mov     r13, [rsp+360h+var_28]
0x180015198  test    rcx, rcx
0x18001519b  jz      short loc_1800151A9
0x18001519d  call    cs:__imp_SHRegCloseUSKey
0x1800151a4  nop     dword ptr [rax+rax+00h]
0x1800151a9  mov     eax, ebx
0x1800151ab  mov     rcx, [rbp+260h+var_50]
0x1800151b2  xor     rcx, rsp; StackCookie
0x1800151b5  call    __security_check_cookie
0x1800151ba  add     rsp, 358h
0x1800151c1  pop     rbx
0x1800151c2  pop     rbp
0x1800151c3  retn
0x1800151c5  mov     ebx, 80070057h
0x1800151ca  jmp     loc_180015108
0x1800151cf  xor     r12d, r12d
0x1800151d2  jmp     loc_1800150DF
0x1800151d7  test    ebx, ebx
0x1800151d9  jz      loc_1800150F8
0x1800151df  jmp     loc_180015496
0x1800151e4  mov     rcx, [rsp+360h+hKey]; hKey
0x1800151e9  call    cs:__imp_RegCloseKey
0x1800151f0  nop     dword ptr [rax+rax+00h]
0x1800151f5  mov     r12d, 1
0x1800151fb  lea     rcx, [rsp+360h+var_2E8]; this
0x180015200  mov     r9d, 20019h; unsigned int
0x180015206  mov     dword ptr [rbp+260h+var_2D4], r12d
0x18001520a  mov     r8, r14; unsigned __int16 *
0x18001520d  mov     [rbp+260h+var_2D8], r12d
0x180015211  xor     edx, edx; void *
0x180015213  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x180015218  test    eax, eax
0x18001521a  jnz     loc_180015040
0x180015220  lea     r9, [rsp+360h+var_300]; unsigned int *
0x180015225  lea     r8, [rsp+360h+var_31C]; unsigned int *
0x18001522a  lea     rdx, [rsp+360h+var_318]; unsigned int *
0x18001522f  lea     rcx, [rsp+360h+var_2E8]; this
0x180015234  call    ?QuerySubKeyInfo@CRegKey@@QEAAJPEAK00@Z; CRegKey::QuerySubKeyInfo(ulong *,ulong *,ulong *)
0x180015239  jmp     loc_180015040
0x18001523e  mov     rcx, [rsp+360h+hKey]; hKey
0x180015243  call    cs:__imp_RegCloseKey
0x18001524a  nop     dword ptr [rax+rax+00h]
0x18001524f  xor     r12d, r12d
0x180015252  lea     rcx, [rbp+260h+var_288]; this
0x180015256  mov     r9d, 20019h; unsigned int
0x18001525c  mov     dword ptr [rbp+260h+var_274], r12d
0x180015260  mov     r8, r14; unsigned __int16 *
0x180015263  mov     [rbp+260h+var_2D8], r12d
0x180015267  xor     edx, edx; void *
0x180015269  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x18001526e  test    eax, eax
0x180015270  jnz     loc_1800150DF
0x180015276  lea     r9, [rsp+360h+var_308]; unsigned int *
0x18001527b  lea     r8, [rsp+360h+var_31C]; unsigned int *
0x180015280  lea     rdx, [rsp+360h+var_318]; unsigned int *
0x180015285  lea     rcx, [rbp+260h+var_288]; this
0x180015289  call    ?QuerySubKeyInfo@CRegKey@@QEAAJPEAK00@Z; CRegKey::QuerySubKeyInfo(ulong *,ulong *,ulong *)
0x18001528e  jmp     loc_1800150DF
0x180015293  mov     rcx, [rsp+360h+hKey]; hKey
0x180015298  call    cs:__imp_RegCloseKey
0x18001529f  nop     dword ptr [rax+rax+00h]
0x1800152a4  xor     r12d, r12d
0x1800152a7  lea     rcx, [rbp+260h+var_2A8]; this
0x1800152ab  mov     r9d, 20019h; unsigned int
0x1800152b1  mov     dword ptr [rbp+260h+var_294], r12d
0x1800152b5  mov     r8, r15; unsigned __int16 *
0x1800152b8  mov     [rbp+260h+var_2D8], r12d
0x1800152bc  xor     edx, edx; void *
0x1800152be  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x1800152c3  test    eax, eax
0x1800152c5  jnz     loc_1800150AE
0x1800152cb  lea     r9, [rsp+360h+var_304]; unsigned int *
0x1800152d0  lea     r8, [rsp+360h+var_31C]; unsigned int *
0x1800152d5  lea     rdx, [rsp+360h+var_318]; unsigned int *
0x1800152da  lea     rcx, [rbp+260h+var_2A8]; this
0x1800152de  call    ?QuerySubKeyInfo@CRegKey@@QEAAJPEAK00@Z; CRegKey::QuerySubKeyInfo(ulong *,ulong *,ulong *)
0x1800152e3  jmp     loc_1800150AE
0x1800152e8  mov     rcx, [rsp+360h+hKey]; hKey
0x1800152ed  call    cs:__imp_RegCloseKey
0x1800152f4  nop     dword ptr [rax+rax+00h]
0x1800152f9  mov     r9d, 20019h; unsigned int
0x1800152ff  mov     dword ptr [rbp+260h+var_2B4], 1
0x180015306  mov     r8, r15; unsigned __int16 *
0x180015309  mov     [rbp+260h+var_2D8], 1
0x180015310  xor     edx, edx; void *
0x180015312  lea     rcx, [rbp+260h+var_2C8]; this
0x180015316  call    ?Open@CRegKey@@UEAAJPEAXPEBGK@Z; CRegKey::Open(void *,ushort const *,ulong)
0x18001531b  test    eax, eax
0x18001531d  jnz     loc_1800150DF
0x180015323  lea     r9, [rsp+360h+var_300+4]; unsigned int *
0x180015328  lea     r8, [rsp+360h+var_31C]; unsigned int *
0x18001532d  lea     rdx, [rsp+360h+var_318]; unsigned int *
0x180015332  lea     rcx, [rbp+260h+var_2C8]; this
0x180015336  call    ?QuerySubKeyInfo@CRegKey@@QEAAJPEAK00@Z; CRegKey::QuerySubKeyInfo(ulong *,ulong *,ulong *)
0x18001533b  jmp     loc_1800150DF
0x180015340  mov     eax, 8
0x180015345  mul     rcx
0x180015348  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001534f  cmovb   rax, rcx
0x180015353  mov     rcx, rax; Size
0x180015356  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001535b  mov     r13, rax
0x18001535e  test    rax, rax
0x180015361  jnz     short loc_180015374
0x180015363  mov     ebx, 8007000Eh
0x180015368  lea     r13, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x18001536f  jmp     loc_180015108
0x180015374  mov     [rsp+360h+var_2F8], r12
0x180015379  mov     r14d, ebx
0x18001537c  cmp     r12d, 4
0x180015380  jge     loc_1800151D7
0x180015386  xor     r15d, r15d
0x180015389  mov     ecx, r12d
0x18001538c  test    r12d, r12d
0x18001538f  jz      short loc_1800153D1
0x180015391  sub     ecx, 1
0x180015394  jz      short loc_1800153C0
0x180015396  sub     ecx, 1
0x180015399  jz      short loc_1800153B0
0x18001539b  cmp     ecx, 1
0x18001539e  jnz     short loc_1800153E1
0x1800153a0  mov     r15d, [rsp+360h+var_308]
0x1800153a5  lea     rax, [rbp+260h+var_288]
0x1800153a9  mov     [rsp+360h+var_2F8], rax
0x1800153ae  jmp     short loc_1800153E6
0x1800153b0  mov     r15d, [rsp+360h+var_304]
0x1800153b5  lea     rax, [rbp+260h+var_2A8]
0x1800153b9  mov     [rsp+360h+var_2F8], rax
0x1800153be  jmp     short loc_1800153E6
0x1800153c0  mov     r15d, [rsp+360h+var_300]
0x1800153c5  lea     rax, [rsp+360h+var_2E8]
0x1800153ca  mov     [rsp+360h+var_2F8], rax
0x1800153cf  jmp     short loc_1800153E6
0x1800153d1  mov     r15d, [rsp+360h+var_300+4]
0x1800153d6  lea     rax, [rbp+260h+var_2C8]
0x1800153da  mov     [rsp+360h+var_2F8], rax
0x1800153df  jmp     short loc_1800153E6
0x1800153e1  mov     rax, [rsp+360h+var_2F8]
0x1800153e6  xor     ecx, ecx
0x1800153e8  mov     [rsp+360h+var_320], ecx
0x1800153ec  cmp     ecx, r15d
0x1800153ef  jnb     loc_180015489
0x1800153f5  lea     rdx, [rsp+360h+var_2F0]
0x1800153fa  mov     qword ptr [rsp+30h], 0; unsigned int *
0x180015403  mov     [rsp+360h+var_338], 0; void *
0x18001540c  lea     r9, [rsp+360h+var_318+4]; unsigned int *
0x180015411  mov     [rsp+360h+phkResult], rdx; unsigned int *
0x180015416  lea     r8, [rbp+260h+var_260]; unsigned __int16 *
0x18001541a  mov     edx, ecx; unsigned int
0x18001541c  mov     [rsp+360h+var_318+4], 104h
0x180015424  mov     rcx, rax; this
0x180015427  call    ?EnumValue@CRegKey@@QEAAJKPEAGPEAK1PEAX1@Z; CRegKey::EnumValue(ulong,ushort *,ulong *,ulong *,void *,ulong *)
0x18001542c  test    eax, eax
0x18001542e  jnz     short loc_180015479
0x180015430  mov     ecx, [rsp+360h+var_318+4]
0x180015434  mov     eax, 2
0x180015439  inc     ecx
0x18001543b  mul     rcx
0x18001543e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180015445  cmovb   rax, rcx
0x180015449  mov     rcx, rax; Size
0x18001544c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015451  mov     ecx, r14d
0x180015454  mov     [r13+rcx*8+0], rax
0x180015459  test    rax, rax
0x18001545c  jz      short loc_180015491
  ... truncated ...
```
