# PerfCache::dwGetHandle(ushort const *)

- ea: `0x18000f104`
- end: `0x18000f22d`
- name: `?dwGetHandle@PerfCache@@AEAAKPEBG@Z`
- size: `297`
- prototype: `__int64 __fastcall(PCNZWCH *this, const unsigned __int16 *lpString2)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f234`

## callees

- `0x180001010`
- `0x180001310`
- `0x1800013d0`
- `0x1800087f0`
- `0x18000f104`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f149`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f1dc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f149`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000f1dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f175`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f175`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18000f1f0`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x18000f1f0`

## pseudocode

```c
__int64 __fastcall PerfCache::dwGetHandle(PCNZWCH *this, const unsigned __int16 *lpString2)
{
  LPCWSTR *v4; // rsi
  HKEY *v5; // rbx
  HKEY v6; // rcx
  unsigned int v7; // edi
  __int16 *v8; // [rsp+30h] [rbp-38h] BYREF
  __int16 v9; // [rsp+38h] [rbp-30h] BYREF
  int v10; // [rsp+3Ch] [rbp-2Ch]

  if ( !lpString2 )
    return 2147749896LL;
  v4 = this + 46;
  v5 = (HKEY *)(this + 45);
  if ( CompareStringW(0x7Fu, 1u, this[46], -1, lpString2, -1) == 2 && *v5 )
    return 0;
  v6 = *v5;
  if ( *v5 && v6 != HKEY_PERFORMANCE_DATA )
    RegCloseKey(v6);
  v9 = 0;
  v8 = &v9;
  v10 = 0;
  TString::assign((TString *)&v8, lpString2);
  TString::operator=(v4, &v8);
  TString::Empty((TString *)&v8);
  if ( CompareStringW(0x7Fu, 1u, lpString2, -1, L"local", -1) == 2 )
  {
    TString::operator=(v4, L"Local");
    *v5 = HKEY_PERFORMANCE_DATA;
    return 0;
  }
  else
  {
    v7 = RegConnectRegistryW(*v4, HKEY_PERFORMANCE_DATA, v5);
    if ( v7 )
    {
      *v5 = 0;
      TString::Empty((TString *)v4);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000f104  push    rbx
0x18000f106  push    rsi
0x18000f107  push    rdi
0x18000f108  push    r14
0x18000f10a  sub     rsp, 48h
0x18000f10e  mov     rdi, rdx
0x18000f111  test    rdx, rdx
0x18000f114  jnz     short loc_18000F120
0x18000f116  mov     eax, 80041008h
0x18000f11b  jmp     loc_18000F223
0x18000f120  lea     rsi, [rcx+170h]
0x18000f127  lea     rbx, [rcx+168h]
0x18000f12e  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000f136  mov     [rsp+68h+lpString2], rdi; lpString2
0x18000f13b  or      r9d, 0FFFFFFFFh; cchCount1
0x18000f13f  mov     r8, [rsi]; lpString1
0x18000f142  lea     edx, [r9+2]; dwCmpFlags
0x18000f146  lea     ecx, [rdx+7Eh]; Locale
0x18000f149  call    cs:__imp_CompareStringW
0x18000f14f  cmp     eax, 2
0x18000f152  jnz     short loc_18000F161
0x18000f154  cmp     qword ptr [rbx], 0
0x18000f158  jz      short loc_18000F161
0x18000f15a  xor     eax, eax
0x18000f15c  jmp     loc_18000F223
0x18000f161  mov     rcx, [rbx]; hKey
0x18000f164  mov     r14, 0FFFFFFFF80000004h
0x18000f16b  test    rcx, rcx
0x18000f16e  jz      short loc_18000F17B
0x18000f170  cmp     rcx, r14
0x18000f173  jz      short loc_18000F17B
0x18000f175  call    cs:__imp_RegCloseKey
0x18000f17b  xor     eax, eax
0x18000f17d  mov     [rsp+68h+var_30], ax
0x18000f182  lea     rax, [rsp+68h+var_30]
0x18000f187  mov     [rsp+68h+var_38], rax
0x18000f18c  mov     [rsp+68h+var_2C], 0
0x18000f194  mov     rdx, rdi; unsigned __int16 *
0x18000f197  lea     rcx, [rsp+68h+var_38]; this
0x18000f19c  call    ?assign@TString@@AEAAXPEBG@Z; TString::assign(ushort const *)
0x18000f1a1  nop
0x18000f1a2  lea     rdx, [rsp+68h+var_38]
0x18000f1a7  mov     rcx, rsi
0x18000f1aa  call    ??4TString@@QEAAAEAV0@AEBV0@@Z; TString::operator=(TString const &)
0x18000f1af  nop
0x18000f1b0  lea     rcx, [rsp+68h+var_38]; this
0x18000f1b5  call    ?Empty@TString@@QEAAXXZ; TString::Empty(void)
0x18000f1ba  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000f1c2  lea     rax, aLocal_1; "local"
0x18000f1c9  mov     [rsp+68h+lpString2], rax; lpString2
0x18000f1ce  or      r9d, 0FFFFFFFFh; cchCount1
0x18000f1d2  mov     r8, rdi; lpString1
0x18000f1d5  lea     edx, [r9+2]; dwCmpFlags
0x18000f1d9  lea     ecx, [rdx+7Eh]; Locale
0x18000f1dc  call    cs:__imp_CompareStringW
0x18000f1e2  cmp     eax, 2
0x18000f1e5  jz      short loc_18000F20D
0x18000f1e7  mov     r8, rbx; phkResult
0x18000f1ea  mov     rdx, r14; hKey
0x18000f1ed  mov     rcx, [rsi]; lpMachineName
0x18000f1f0  call    cs:__imp_RegConnectRegistryW
0x18000f1f6  mov     edi, eax
0x18000f1f8  test    eax, eax
0x18000f1fa  jz      short loc_18000F221
0x18000f1fc  mov     qword ptr [rbx], 0
0x18000f203  mov     rcx, rsi; this
0x18000f206  call    ?Empty@TString@@QEAAXXZ; TString::Empty(void)
0x18000f20b  jmp     short loc_18000F221
0x18000f20d  lea     rdx, aLocal_0; "Local"
0x18000f214  mov     rcx, rsi
0x18000f217  call    ??4TString@@QEAAAEAV0@PEAG@Z; TString::operator=(ushort *)
0x18000f21c  mov     [rbx], r14
0x18000f21f  xor     edi, edi
0x18000f221  mov     eax, edi
0x18000f223  add     rsp, 48h
0x18000f227  pop     r14
0x18000f229  pop     rdi
0x18000f22a  pop     rsi
0x18000f22b  pop     rbx
0x18000f22c  retn
```
