# CBlockListManager::_HandleBlockListElement(ushort const *,uint,IXmlReader *)

- ea: `0x180105ab8`
- end: `0x180105d49`
- name: `?_HandleBlockListElement@CBlockListManager@@AEAAJPEBGIPEAUIXmlReader@@@Z`
- size: `657`
- prototype: `int(CBlockListManager *__hidden this, const unsigned __int16 *, unsigned int, struct IXmlReader *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801063f8`

## callees

- `0x180105ab8`
- `0x18010757c`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105aff`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105b7c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105bd2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105c21`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105aff`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105b7c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105bd2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180105c21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180105cef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180105d03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180105d17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180105cef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180105d03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180105d17`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180105c5a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180105c5a`

## pseudocode

```c
__int64 __fastcall CBlockListManager::_HandleBlockListElement(
        CBlockListManager *this,
        const unsigned __int16 *a2,
        int a3,
        struct IXmlReader *a4)
{
  int v6; // ebx
  struct IXmlReaderVtbl *lpVtbl; // rax
  HRESULT v8; // eax
  bool v9; // zf
  int v10; // r8d
  struct IXmlReaderVtbl *v11; // rax
  LPWSTR *p_pv; // rdx
  struct IXmlReaderVtbl *v13; // rax
  struct IXmlReaderVtbl *v14; // rax
  CBlockListManager *v15; // rcx
  CBlockListManager *v16; // rcx
  CBlockListManager *v17; // rcx
  unsigned __int16 *v19; // [rsp+20h] [rbp-30h] BYREF
  LPCWSTR pszStr1; // [rsp+28h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  LPWSTR ppwsz; // [rsp+38h] [rbp-18h] BYREF
  LPCWSTR psz[2]; // [rsp+40h] [rbp-10h] BYREF
  int nChar; // [rsp+78h] [rbp+28h] BYREF

  if ( !a2 || !a4 )
    return 2147942487LL;
  if ( a3 != 9 || StrCmpNICW(a2, L"blocklist", 9) )
    return (unsigned int)-2147019873;
  v6 = ((__int64 (__fastcall *)(struct IXmlReader *))a4->lpVtbl->MoveToFirstAttribute)(a4);
  if ( v6 )
    return (unsigned int)v6;
  pv = 0;
  v19 = 0;
  ppwsz = 0;
  while ( 1 )
  {
    lpVtbl = a4->lpVtbl;
    pszStr1 = 0;
    nChar = 0;
    v8 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, int *))lpVtbl->GetLocalName)(a4, &pszStr1, &nChar);
    v6 = -2147019873;
    v9 = v8 == 0;
    if ( v8 < 0 )
      goto LABEL_24;
    v10 = nChar;
    if ( nChar == 7 )
    {
      if ( !StrCmpNICW(pszStr1, L"version", 7) )
      {
        v11 = a4->lpVtbl;
        psz[0] = 0;
        v8 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v11->GetValue)(a4, psz, 0);
        v9 = v8 == 0;
        if ( v8 >= 0 )
        {
          p_pv = (LPWSTR *)&pv;
          goto LABEL_22;
        }
        goto LABEL_24;
      }
      v10 = nChar;
    }
    if ( v10 != 7 )
      goto LABEL_18;
    if ( StrCmpNICW(pszStr1, L"ttlhigh", 7) )
      break;
    v13 = a4->lpVtbl;
    psz[0] = 0;
    v8 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v13->GetValue)(a4, psz, 0);
    v9 = v8 == 0;
    if ( v8 >= 0 )
    {
      p_pv = &v19;
      goto LABEL_22;
    }
LABEL_24:
    if ( !v9 )
      goto LABEL_27;
  }
  v10 = nChar;
LABEL_18:
  if ( v10 == 6 && !StrCmpNICW(pszStr1, L"ttllow", 6) )
  {
    v14 = a4->lpVtbl;
    psz[0] = 0;
    v8 = ((__int64 (__fastcall *)(struct IXmlReader *, LPCWSTR *, _QWORD))v14->GetValue)(a4, psz, 0);
    v9 = v8 == 0;
    if ( v8 < 0 )
      goto LABEL_24;
    p_pv = &ppwsz;
LABEL_22:
    v8 = SHStrDupW(psz[0], p_pv);
    v9 = v8 == 0;
    if ( v8 >= 0 )
    {
      v8 = ((__int64 (__fastcall *)(struct IXmlReader *))a4->lpVtbl->MoveToNextAttribute)(a4);
      v9 = v8 == 0;
    }
    goto LABEL_24;
  }
  v8 = -2147019873;
LABEL_27:
  v15 = 0;
  if ( v8 != 1 )
    v15 = (CBlockListManager *)(unsigned int)v8;
  if ( (int)v15 < 0 )
  {
    v6 = (int)v15;
  }
  else if ( pv )
  {
    if ( ppwsz )
    {
      if ( v19 )
      {
        v6 = CBlockListManager::_StringToULong(
               v15,
               (const unsigned __int16 *)pv,
               (unsigned int *)this + 148,
               0xFFFFFFFF);
        if ( v6 >= 0 )
        {
          v6 = CBlockListManager::_StringToULong(v16, ppwsz, (unsigned int *)this + 1, 0xFFFFFFFF);
          if ( v6 >= 0 )
            v6 = CBlockListManager::_StringToULong(v17, v19, (unsigned int *)this + 2, 0xFFFFFFFF);
        }
      }
    }
  }
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v19);
  v19 = 0;
  CoTaskMemFree(ppwsz);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180105ab8  mov     [rsp-18h+arg_0], rbx
0x180105abd  mov     [rsp-18h+arg_10], rsi
0x180105ac2  push    rbp
0x180105ac3  push    rdi
0x180105ac4  push    r14
0x180105ac6  mov     rbp, rsp
0x180105ac9  sub     rsp, 50h
0x180105acd  xor     r14d, r14d
0x180105ad0  mov     rdi, r9
0x180105ad3  mov     rax, rdx
0x180105ad6  mov     rsi, rcx
0x180105ad9  test    rdx, rdx
0x180105adc  jz      loc_180105D2E
0x180105ae2  test    r9, r9
0x180105ae5  jz      loc_180105D2E
0x180105aeb  cmp     r8d, 9
0x180105aef  jnz     loc_180105D25
0x180105af5  lea     rdx, aBlocklist; "blocklist"
0x180105afc  mov     rcx, rax; pszStr1
0x180105aff  call    cs:__imp_StrCmpNICW
0x180105b06  nop     dword ptr [rax+rax+00h]
0x180105b0b  test    eax, eax
0x180105b0d  jnz     loc_180105D25
0x180105b13  mov     rax, [rdi]
0x180105b16  mov     rcx, rdi
0x180105b19  mov     rax, [rax+40h]
0x180105b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105b22  mov     ebx, eax
0x180105b24  test    eax, eax
0x180105b26  jnz     loc_180105D2A
0x180105b2c  mov     [rbp+pv], r14
0x180105b30  mov     [rbp+var_30], r14
0x180105b34  mov     [rbp+ppwsz], r14
0x180105b38  mov     rax, [rdi]
0x180105b3b  lea     r8, [rbp+nChar]
0x180105b3f  lea     rdx, [rbp+pszStr1]
0x180105b43  mov     [rbp+pszStr1], r14
0x180105b47  mov     rcx, rdi
0x180105b4a  mov     [rbp+nChar], r14d
0x180105b4e  mov     rax, [rax+70h]
0x180105b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105b57  mov     ebx, 8007139Fh
0x180105b5c  test    eax, eax
0x180105b5e  js      loc_180105C7B
0x180105b64  mov     r8d, [rbp+nChar]; nChar
0x180105b68  lea     eax, [r8+1]
0x180105b6c  cmp     eax, 8
0x180105b6f  jnz     short loc_180105BBE
0x180105b71  mov     rcx, [rbp+pszStr1]; pszStr1
0x180105b75  lea     rdx, aVersion_7; "version"
0x180105b7c  call    cs:__imp_StrCmpNICW
0x180105b83  nop     dword ptr [rax+rax+00h]
0x180105b88  test    eax, eax
0x180105b8a  jnz     short loc_180105BBA
0x180105b8c  mov     rax, [rdi]
0x180105b8f  lea     rdx, [rbp+psz]
0x180105b93  xor     r8d, r8d
0x180105b96  mov     [rbp+psz], r14
0x180105b9a  mov     rcx, rdi
0x180105b9d  mov     rax, [rax+80h]
0x180105ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105ba9  test    eax, eax
0x180105bab  js      loc_180105C7B
0x180105bb1  lea     rdx, [rbp+pv]
0x180105bb5  jmp     loc_180105C56
0x180105bba  mov     r8d, [rbp+nChar]; nChar
0x180105bbe  lea     eax, [r8+1]
0x180105bc2  cmp     eax, 8
0x180105bc5  jnz     short loc_180105C0D
0x180105bc7  mov     rcx, [rbp+pszStr1]; pszStr1
0x180105bcb  lea     rdx, aTtlhigh; "ttlhigh"
0x180105bd2  call    cs:__imp_StrCmpNICW
0x180105bd9  nop     dword ptr [rax+rax+00h]
0x180105bde  test    eax, eax
0x180105be0  jnz     short loc_180105C09
0x180105be2  mov     rax, [rdi]
0x180105be5  lea     rdx, [rbp+psz]
0x180105be9  xor     r8d, r8d
0x180105bec  mov     [rbp+psz], r14
0x180105bf0  mov     rcx, rdi
0x180105bf3  mov     rax, [rax+80h]
0x180105bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105bff  test    eax, eax
0x180105c01  js      short loc_180105C7B
0x180105c03  lea     rdx, [rbp+var_30]
0x180105c07  jmp     short loc_180105C56
0x180105c09  mov     r8d, [rbp+nChar]; nChar
0x180105c0d  lea     eax, [r8+1]
0x180105c11  cmp     eax, 7
0x180105c14  jnz     short loc_180105C83
0x180105c16  mov     rcx, [rbp+pszStr1]; pszStr1
0x180105c1a  lea     rdx, aTtllow; "ttllow"
0x180105c21  call    cs:__imp_StrCmpNICW
0x180105c28  nop     dword ptr [rax+rax+00h]
0x180105c2d  test    eax, eax
0x180105c2f  jnz     short loc_180105C83
0x180105c31  mov     rax, [rdi]
0x180105c34  lea     rdx, [rbp+psz]
0x180105c38  xor     r8d, r8d
0x180105c3b  mov     [rbp+psz], r14
0x180105c3f  mov     rcx, rdi
0x180105c42  mov     rax, [rax+80h]
0x180105c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105c4e  test    eax, eax
0x180105c50  js      short loc_180105C7B
0x180105c52  lea     rdx, [rbp+ppwsz]; ppwsz
0x180105c56  mov     rcx, [rbp+psz]; psz
0x180105c5a  call    cs:__imp_SHStrDupW
0x180105c61  nop     dword ptr [rax+rax+00h]
0x180105c66  test    eax, eax
0x180105c68  js      short loc_180105C7B
0x180105c6a  mov     rax, [rdi]
0x180105c6d  mov     rcx, rdi
0x180105c70  mov     rax, [rax+48h]
0x180105c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105c79  test    eax, eax
0x180105c7b  jz      loc_180105B38
0x180105c81  jmp     short loc_180105C85
0x180105c83  mov     eax, ebx
0x180105c85  cmp     eax, 1
0x180105c88  mov     ecx, r14d
0x180105c8b  cmovnz  ecx, eax; this
0x180105c8e  test    ecx, ecx
0x180105c90  js      short loc_180105CE9
0x180105c92  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180105c96  test    rdx, rdx
0x180105c99  jz      short loc_180105CEB
0x180105c9b  cmp     [rbp+ppwsz], r14
0x180105c9f  jz      short loc_180105CEB
0x180105ca1  cmp     [rbp+var_30], r14
0x180105ca5  jz      short loc_180105CEB
0x180105ca7  lea     r8, [rsi+250h]; unsigned int *
0x180105cae  or      r9d, 0FFFFFFFFh; unsigned int
0x180105cb2  call    ?_StringToULong@CBlockListManager@@AEAAJPEBGPEAKK@Z; CBlockListManager::_StringToULong(ushort const *,ulong *,ulong)
0x180105cb7  mov     ebx, eax
0x180105cb9  test    eax, eax
0x180105cbb  js      short loc_180105CEB
0x180105cbd  mov     rdx, [rbp+ppwsz]; unsigned __int16 *
0x180105cc1  lea     r8, [rsi+4]; unsigned int *
0x180105cc5  or      r9d, 0FFFFFFFFh; unsigned int
0x180105cc9  call    ?_StringToULong@CBlockListManager@@AEAAJPEBGPEAKK@Z; CBlockListManager::_StringToULong(ushort const *,ulong *,ulong)
0x180105cce  mov     ebx, eax
0x180105cd0  test    eax, eax
0x180105cd2  js      short loc_180105CEB
0x180105cd4  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x180105cd8  lea     r8, [rsi+8]; unsigned int *
0x180105cdc  or      r9d, 0FFFFFFFFh; unsigned int
0x180105ce0  call    ?_StringToULong@CBlockListManager@@AEAAJPEBGPEAKK@Z; CBlockListManager::_StringToULong(ushort const *,ulong *,ulong)
0x180105ce5  mov     ebx, eax
0x180105ce7  jmp     short loc_180105CEB
0x180105ce9  mov     ebx, ecx
0x180105ceb  mov     rcx, [rbp+pv]; pv
0x180105cef  call    cs:__imp_CoTaskMemFree
0x180105cf6  nop     dword ptr [rax+rax+00h]
0x180105cfb  mov     rcx, [rbp+var_30]; pv
0x180105cff  mov     [rbp+pv], r14
0x180105d03  call    cs:__imp_CoTaskMemFree
0x180105d0a  nop     dword ptr [rax+rax+00h]
0x180105d0f  mov     rcx, [rbp+ppwsz]; pv
0x180105d13  mov     [rbp+var_30], r14
0x180105d17  call    cs:__imp_CoTaskMemFree
0x180105d1e  nop     dword ptr [rax+rax+00h]
0x180105d23  jmp     short loc_180105D2A
0x180105d25  mov     ebx, 8007139Fh
0x180105d2a  mov     eax, ebx
0x180105d2c  jmp     short loc_180105D33
0x180105d2e  mov     eax, 80070057h
0x180105d33  lea     r11, [rsp+50h+var_s0]
0x180105d38  mov     rbx, [r11+20h]
0x180105d3c  mov     rsi, [r11+30h]
0x180105d40  mov     rsp, r11
0x180105d43  pop     r14
0x180105d45  pop     rdi
0x180105d46  pop     rbp
0x180105d47  retn
```
