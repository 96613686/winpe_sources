# CImpReg::MakeEnum(IWbemClassObject *,CProvObj &,CEnumInfo * *)

- ea: `0x180011cf0`
- end: `0x180012116`
- name: `?MakeEnum@CImpReg@@UEAAJPEAUIWbemClassObject@@AEAVCProvObj@@PEAPEAVCEnumInfo@@@Z`
- size: `1062`
- prototype: `__int64 __fastcall(CImpReg *this, struct IWbemClassObject *, struct CProvObj *, HKEY *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002e10`
- `0x180006524`
- `0x1800087c0`
- `0x180011cf0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180011e8b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180011ed6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180011f2a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180011e8b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180011ed6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180011f2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011fc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011fc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011fed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001200e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011fed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001200e`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180011f3f`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180011f3f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011dfe`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011f4e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011f57`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011fcd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011fd6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800120f1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800120fa`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011dfe`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011f4e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011f57`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011fcd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180011fd6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800120f1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800120fa`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011d72`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011ded`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001202d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001208b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011d72`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180011ded`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001202d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001208b`

## pseudocode

```c
__int64 __fastcall CImpReg::MakeEnum(CImpReg *this, struct IWbemClassObject *a2, struct CProvObj *a3, HKEY *a4)
{
  const unsigned __int16 *Token; // rcx
  __int64 v9; // rax
  unsigned __int64 v10; // rsi
  unsigned __int16 *v11; // rdi
  const unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  unsigned __int16 *v16; // rsi
  const unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // r10
  unsigned __int16 i; // ax
  const WCHAR *v20; // r14
  int j; // ebx
  HKEY v22; // rbx
  int v23; // ebx
  LSTATUS v24; // eax
  HKEY v25; // rax
  LSTATUS v26; // eax
  LSTATUS v27; // ebx
  HKEY v28; // rax
  HKEY v29; // r9
  __int64 v30; // rdx
  HKEY v31; // r8
  HKEY v32; // rcx
  HKEY v33; // rcx
  HKEY v34; // rax
  HKEY v35; // [rsp+40h] [rbp-18h] BYREF
  HKEY v36; // [rsp+48h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+B0h] [rbp+58h] BYREF

  v35 = 0;
  phkResult = 0;
  if ( *((int *)a3 + 2) < 2 )
    return 2147749896LL;
  if ( CProvObj::sGetToken(a3, 1) )
  {
    Token = CProvObj::sGetToken(a3, 1);
    v9 = -1;
    do
      ++v9;
    while ( Token[v9] );
  }
  else
  {
    LODWORD(v9) = 0;
  }
  v10 = (unsigned int)(v9 + 1);
  v11 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v10, 2u));
  if ( !v11 )
    return 2147749894LL;
  v12 = CProvObj::sGetToken(a3, 1);
  StringCchCopyW(v11, v10, v12);
  if ( CProvObj::sGetToken(a3, 0) )
  {
    v13 = CProvObj::sGetToken(a3, 0);
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
  }
  else
  {
    LODWORD(v14) = 0;
  }
  v15 = (unsigned int)(v14 + 1);
  v16 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v15, 2u));
  if ( !v16 )
  {
    CWin32DefaultArena::WbemMemFree(v11);
    return 2147749894LL;
  }
  v17 = CProvObj::sGetToken(a3, 0);
  StringCchCopyW(v16, v15, v17);
  v18 = v11;
  for ( i = *v11; i && i != 92; i = *v18 )
    ++v18;
  if ( *v18 && (v20 = v18 + 1, v18[1]) )
    *v18 = 0;
  else
    v20 = 0;
  for ( j = 0; ; ++j )
  {
    if ( j >= 7 )
      goto LABEL_60;
    if ( CompareStringW(0x7Fu, 1u, v11, -1, (PCNZWCH)*(&Bases + 2 * j), -1) == 2 )
      break;
  }
  v22 = (HKEY)*(&Bases + 2 * j + 1);
  v36 = v22;
  if ( !v22 )
  {
LABEL_60:
    CWin32DefaultArena::WbemMemFree(v11);
    CWin32DefaultArena::WbemMemFree(v16);
    return 2147749889LL;
  }
  if ( CompareStringW(0x7Fu, 1u, v16, -1, L"local", -1) == 2
    && (((unsigned __int64)v22 + 0x7FFFFFFF) & 0xFFFFFFFFFFFFFFFDuLL) == 0 )
  {
    v23 = AutoProfile::LoadProfile((CImpReg *)((char *)this + 176), &v36);
    if ( v23 < 0 )
    {
LABEL_37:
      CWin32DefaultArena::WbemMemFree(v11);
      CWin32DefaultArena::WbemMemFree(v16);
      return (unsigned int)v23;
    }
    v22 = v36;
  }
  if ( CompareStringW(0x7Fu, 1u, v16, -1, L"local", -1) == 2 )
  {
    v25 = phkResult;
  }
  else
  {
    v24 = RegConnectRegistryW(v16, v22, &phkResult);
    if ( v24 )
    {
      v23 = v24;
      goto LABEL_37;
    }
    v25 = phkResult;
    v22 = phkResult;
  }
  if ( !*((_QWORD *)this + 16) || v25 )
    v26 = RegOpenKeyExW(v22, v20, 0, 9u, &v35);
  else
    v26 = (*((__int64 (__fastcall **)(HKEY, const WCHAR *, _QWORD, _QWORD, int, HKEY *))this + 17))(
            v22,
            v20,
            0,
            0,
            983103,
            &v35);
  v27 = v26;
  CWin32DefaultArena::WbemMemFree(v11);
  CWin32DefaultArena::WbemMemFree(v16);
  if ( v27 == 1346 )
  {
    if ( phkResult )
      RegCloseKey(phkResult);
    return 2147749891LL;
  }
  if ( v27 )
  {
    if ( phkResult )
      RegCloseKey(phkResult);
    return 2147749889LL;
  }
  if ( !*((_QWORD *)this + 16) || phkResult )
  {
    v29 = (HKEY)CWin32DefaultArena::WbemMemAlloc(0x28u);
    v36 = v29;
    if ( v29 )
    {
      v33 = phkResult;
      v34 = v35;
      *(_QWORD *)v29 = &CObject::`vftable';
      *(_QWORD *)v29 = &CEnumInfo::`vftable';
      *((_DWORD *)v29 + 2) = 1;
      *(_QWORD *)v29 = &CEnumRegInfo::`vftable';
      *((_QWORD *)v29 + 4) = 0;
      *((_QWORD *)v29 + 2) = v34;
      *((_QWORD *)v29 + 3) = v33;
    }
    else
    {
      v29 = 0;
    }
  }
  else
  {
    v28 = (HKEY)CWin32DefaultArena::WbemMemAlloc(0x28u);
    v29 = v28;
    v36 = v28;
    if ( v28 )
    {
      v30 = *((_QWORD *)this + 18);
      v31 = phkResult;
      v32 = v35;
      *(_QWORD *)v28 = &CObject::`vftable';
      *(_QWORD *)v28 = &CEnumInfo::`vftable';
      *((_DWORD *)v28 + 2) = 1;
      *(_QWORD *)v28 = &CEnumRegInfo::`vftable';
      *((_QWORD *)v28 + 4) = v30;
      *((_QWORD *)v28 + 2) = v32;
      *((_QWORD *)v28 + 3) = v31;
    }
    else
    {
      v29 = 0;
    }
  }
  *a4 = v29;
  return v29 == 0 ? 0x80041006 : 0;
}

```

## disassembly

```asm
0x180011cf0  push    rbp
0x180011cf2  push    rbx
0x180011cf3  push    rsi
0x180011cf4  push    rdi
0x180011cf5  push    r12
0x180011cf7  push    r13
0x180011cf9  push    r14
0x180011cfb  push    r15
0x180011cfd  mov     rbp, rsp
0x180011d00  sub     rsp, 58h
0x180011d04  mov     r12, r9
0x180011d07  mov     rbx, r8
0x180011d0a  mov     r13, rcx
0x180011d0d  xor     r15d, r15d
0x180011d10  mov     [rbp+var_18], r15
0x180011d14  mov     [rbp+phkResult], r15
0x180011d18  cmp     dword ptr [r8+8], 2
0x180011d1d  jge     short loc_180011D29
0x180011d1f  mov     eax, 80041008h
0x180011d24  jmp     loc_180012105
0x180011d29  mov     edi, 1
0x180011d2e  mov     edx, edi; int
0x180011d30  mov     rcx, rbx; this
0x180011d33  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180011d38  or      r14, 0FFFFFFFFFFFFFFFFh
0x180011d3c  test    rax, rax
0x180011d3f  jz      short loc_180011D5D
0x180011d41  mov     edx, edi; int
0x180011d43  mov     rcx, rbx; this
0x180011d46  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180011d4b  mov     rcx, rax
0x180011d4e  mov     rax, r14
0x180011d51  inc     rax
0x180011d54  cmp     [rcx+rax*2], r15w
0x180011d59  jnz     short loc_180011D51
0x180011d5b  jmp     short loc_180011D60
0x180011d5d  mov     rax, r15
0x180011d60  lea     esi, [rax+1]
0x180011d63  mov     eax, 2
0x180011d68  mul     rsi
0x180011d6b  cmovb   rax, r14
0x180011d6f  mov     rcx, rax
0x180011d72  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180011d78  mov     rdi, rax
0x180011d7b  test    rax, rax
0x180011d7e  jnz     short loc_180011D8A
0x180011d80  mov     eax, 80041006h
0x180011d85  jmp     loc_180012105
0x180011d8a  mov     edx, 1; int
0x180011d8f  mov     rcx, rbx; this
0x180011d92  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180011d97  mov     r8, rax; unsigned __int16 *
0x180011d9a  mov     rdx, rsi; unsigned __int64
0x180011d9d  mov     rcx, rdi; unsigned __int16 *
0x180011da0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011da5  xor     edx, edx; int
0x180011da7  mov     rcx, rbx; this
0x180011daa  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180011daf  test    rax, rax
0x180011db2  jz      short loc_180011DD0
0x180011db4  xor     edx, edx; int
0x180011db6  mov     rcx, rbx; this
0x180011db9  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180011dbe  mov     rcx, rax
0x180011dc1  mov     rax, r14
0x180011dc4  inc     rax
0x180011dc7  cmp     [rcx+rax*2], r15w
0x180011dcc  jnz     short loc_180011DC4
0x180011dce  jmp     short loc_180011DD3
0x180011dd0  mov     rax, r15
0x180011dd3  lea     r14d, [rax+1]
0x180011dd7  mov     eax, 2
0x180011ddc  mul     r14
0x180011ddf  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180011de6  cmovb   rax, rcx
0x180011dea  mov     rcx, rax
0x180011ded  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180011df3  mov     rsi, rax
0x180011df6  test    rax, rax
0x180011df9  jnz     short loc_180011E09
0x180011dfb  mov     rcx, rdi
0x180011dfe  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180011e04  jmp     loc_180011D80
0x180011e09  xor     edx, edx; int
0x180011e0b  mov     rcx, rbx; this
0x180011e0e  call    ?sGetToken@CProvObj@@QEAAPEBGH@Z; CProvObj::sGetToken(int)
0x180011e13  mov     r8, rax; unsigned __int16 *
0x180011e16  mov     rdx, r14; unsigned __int64
0x180011e19  mov     rcx, rsi; unsigned __int16 *
0x180011e1c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011e21  mov     r10, rdi
0x180011e24  movzx   eax, word ptr [rdi]
0x180011e27  jmp     short loc_180011E37
0x180011e29  cmp     ax, 5Ch ; '\'
0x180011e2d  jz      short loc_180011E3C
0x180011e2f  add     r10, 2
0x180011e33  movzx   eax, word ptr [r10]
0x180011e37  test    ax, ax
0x180011e3a  jnz     short loc_180011E29
0x180011e3c  cmp     [r10], r15w
0x180011e40  jz      short loc_180011E52
0x180011e42  lea     r14, [r10+2]
0x180011e46  cmp     [r14], r15w
0x180011e4a  jz      short loc_180011E52
0x180011e4c  mov     [r10], r15w
0x180011e50  jmp     short loc_180011E55
0x180011e52  mov     r14, r15
0x180011e55  mov     ebx, r15d
0x180011e58  lea     rax, ?Bases@@3PAUBaseTypes@@A; BaseTypes near * Bases
0x180011e5f  cmp     ebx, 7
0x180011e62  jge     loc_1800120EE
0x180011e68  movsxd  r15, ebx
0x180011e6b  add     r15, r15
0x180011e6e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180011e72  mov     [rsp+58h+cchCount2], ecx; cchCount2
0x180011e76  mov     rax, [rax+r15*8]
0x180011e7a  mov     [rsp+58h+lpString2], rax; lpString2
0x180011e7f  mov     r9d, ecx; cchCount1
0x180011e82  mov     r8, rdi; lpString1
0x180011e85  lea     edx, [rcx+2]; dwCmpFlags
0x180011e88  lea     ecx, [rdx+7Eh]; Locale
0x180011e8b  call    cs:__imp_CompareStringW
0x180011e91  cmp     eax, 2
0x180011e94  jz      short loc_180011E9A
0x180011e96  inc     ebx
0x180011e98  jmp     short loc_180011E58
0x180011e9a  lea     rbx, ?Bases@@3PAUBaseTypes@@A; BaseTypes near * Bases
0x180011ea1  mov     rbx, [rbx+r15*8+8]
0x180011ea6  mov     [rbp+var_10], rbx
0x180011eaa  xor     r15d, r15d
0x180011ead  test    rbx, rbx
0x180011eb0  jz      loc_1800120EE
0x180011eb6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011eba  mov     [rsp+58h+cchCount2], eax; cchCount2
0x180011ebe  lea     rcx, aLocal_1; "local"
0x180011ec5  mov     [rsp+58h+lpString2], rcx; lpString2
0x180011eca  mov     r9d, eax; cchCount1
0x180011ecd  mov     r8, rsi; lpString1
0x180011ed0  lea     edx, [rax+2]; dwCmpFlags
0x180011ed3  lea     ecx, [rdx+7Eh]; Locale
0x180011ed6  call    cs:__imp_CompareStringW
0x180011edc  cmp     eax, 2
0x180011edf  jnz     short loc_180011F0A
0x180011ee1  lea     rax, [rbx+7FFFFFFFh]
0x180011ee8  test    rax, 0FFFFFFFFFFFFFFFDh
0x180011eee  jnz     short loc_180011F0A
0x180011ef0  lea     rcx, [r13+0B0h]; this
0x180011ef7  lea     rdx, [rbp+var_10]; HKEY *
0x180011efb  call    ?LoadProfile@AutoProfile@@QEAAJAEAPEAUHKEY__@@@Z; AutoProfile::LoadProfile(HKEY__ * &)
0x180011f00  mov     ebx, eax
0x180011f02  test    eax, eax
0x180011f04  js      short loc_180011F4B
0x180011f06  mov     rbx, [rbp+var_10]
0x180011f0a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011f0e  mov     [rsp+58h+cchCount2], eax; cchCount2
0x180011f12  lea     rcx, aLocal_1; "local"
0x180011f19  mov     [rsp+58h+lpString2], rcx; lpString2
0x180011f1e  mov     r9d, eax; cchCount1
0x180011f21  mov     r8, rsi; lpString1
0x180011f24  lea     edx, [rax+2]; dwCmpFlags
0x180011f27  lea     ecx, [rdx+7Eh]; Locale
0x180011f2a  call    cs:__imp_CompareStringW
0x180011f30  cmp     eax, 2
0x180011f33  jz      short loc_180011F6D
0x180011f35  lea     r8, [rbp+phkResult]; phkResult
0x180011f39  mov     rdx, rbx; hKey
0x180011f3c  mov     rcx, rsi; lpMachineName
0x180011f3f  call    cs:__imp_RegConnectRegistryW
0x180011f45  test    eax, eax
0x180011f47  jz      short loc_180011F64
0x180011f49  mov     ebx, eax
0x180011f4b  mov     rcx, rdi
0x180011f4e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180011f54  mov     rcx, rsi
0x180011f57  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180011f5d  mov     eax, ebx
0x180011f5f  jmp     loc_180012105
0x180011f64  mov     rax, [rbp+phkResult]
0x180011f68  mov     rbx, rax
0x180011f6b  jmp     short loc_180011F71
0x180011f6d  mov     rax, [rbp+phkResult]
0x180011f71  cmp     [r13+80h], r15
0x180011f78  jz      short loc_180011FAA
0x180011f7a  test    rax, rax
0x180011f7d  jnz     short loc_180011FAA
0x180011f7f  lea     rax, [rbp+var_18]
0x180011f83  mov     qword ptr [rsp+58h+cchCount2], rax
0x180011f88  mov     dword ptr [rsp+58h+lpString2], 0F003Fh
0x180011f90  xor     r9d, r9d
0x180011f93  xor     r8d, r8d
0x180011f96  mov     rdx, r14
0x180011f99  mov     rcx, rbx
0x180011f9c  mov     rax, [r13+88h]
0x180011fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fa8  jmp     short loc_180011FC8
0x180011faa  lea     rax, [rbp+var_18]
0x180011fae  mov     [rsp+58h+lpString2], rax; phkResult
0x180011fb3  mov     r9d, 9; samDesired
0x180011fb9  xor     r8d, r8d; ulOptions
0x180011fbc  mov     rdx, r14; lpSubKey
0x180011fbf  mov     rcx, rbx; hKey
0x180011fc2  call    cs:__imp_RegOpenKeyExW
0x180011fc8  mov     ebx, eax
0x180011fca  mov     rcx, rdi
0x180011fcd  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180011fd3  mov     rcx, rsi
0x180011fd6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180011fdc  cmp     ebx, 542h
0x180011fe2  jnz     short loc_180011FFD
0x180011fe4  mov     rcx, [rbp+phkResult]; hKey
0x180011fe8  test    rcx, rcx
0x180011feb  jz      short loc_180011FF3
0x180011fed  call    cs:__imp_RegCloseKey
0x180011ff3  mov     eax, 80041003h
0x180011ff8  jmp     loc_180012105
0x180011ffd  test    ebx, ebx
0x180011fff  jz      short loc_180012019
0x180012001  mov     rcx, [rbp+phkResult]; hKey
0x180012005  test    rcx, rcx
0x180012008  jz      loc_180012100
0x18001200e  call    cs:__imp_RegCloseKey
0x180012014  jmp     loc_180012100
0x180012019  cmp     [r13+80h], r15
0x180012020  jz      short loc_180012086
0x180012022  cmp     [rbp+phkResult], r15
0x180012026  jnz     short loc_180012086
0x180012028  mov     ecx, 28h ; '('
0x18001202d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180012033  mov     r9, rax
0x180012036  mov     [rbp+var_10], rax
0x18001203a  test    rax, rax
0x18001203d  jz      short loc_180012081
0x18001203f  mov     rdx, [r13+90h]
0x180012046  mov     r8, [rbp+phkResult]
0x18001204a  mov     rcx, [rbp+var_18]
0x18001204e  lea     r10, ??_7CObject@@6B@; const CObject::`vftable'
0x180012055  mov     [rax], r10
0x180012058  lea     r10, ??_7CEnumInfo@@6B@; const CEnumInfo::`vftable'
0x18001205f  mov     [rax], r10
0x180012062  mov     dword ptr [rax+8], 1
0x180012069  lea     r10, ??_7CEnumRegInfo@@6B@; const CEnumRegInfo::`vftable'
0x180012070  mov     [rax], r10
0x180012073  mov     [rax+20h], rdx
0x180012077  mov     [rax+10h], rcx
0x18001207b  mov     [rax+18h], r8
0x18001207f  jmp     short loc_180012084
0x180012081  mov     r9, r15
0x180012084  jmp     short loc_1800120DC
0x180012086  mov     ecx, 28h ; '('
0x18001208b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180012091  mov     r9, rax
0x180012094  mov     [rbp+var_10], rax
0x180012098  test    rax, rax
0x18001209b  jz      short loc_1800120D9
0x18001209d  mov     rcx, [rbp+phkResult]
0x1800120a1  mov     rax, [rbp+var_18]
0x1800120a5  lea     r10, ??_7CObject@@6B@; const CObject::`vftable'
0x1800120ac  mov     [r9], r10
0x1800120af  lea     r10, ??_7CEnumInfo@@6B@; const CEnumInfo::`vftable'
0x1800120b6  mov     [r9], r10
0x1800120b9  mov     dword ptr [r9+8], 1
0x1800120c1  lea     r10, ??_7CEnumRegInfo@@6B@; const CEnumRegInfo::`vftable'
0x1800120c8  mov     [r9], r10
0x1800120cb  mov     [r9+20h], r15
0x1800120cf  mov     [r9+10h], rax
0x1800120d3  mov     [r9+18h], rcx
0x1800120d7  jmp     short loc_1800120DC
0x1800120d9  mov     r9, r15
0x1800120dc  mov     [r12], r9
0x1800120e0  neg     r9
0x1800120e3  sbb     eax, eax
0x1800120e5  not     eax
0x1800120e7  and     eax, 80041006h
0x1800120ec  jmp     short loc_180012105
0x1800120ee  mov     rcx, rdi
0x1800120f1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800120f7  mov     rcx, rsi
0x1800120fa  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180012100  mov     eax, 80041001h
0x180012105  add     rsp, 58h
0x180012109  pop     r15
0x18001210b  pop     r14
0x18001210d  pop     r13
0x18001210f  pop     r12
0x180012111  pop     rdi
0x180012112  pop     rsi
0x180012113  pop     rbx
0x180012114  pop     rbp
0x180012115  retn
```
