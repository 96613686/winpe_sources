# _InitPropVariantFromParsedString(ushort const *,tagPROPVARIANT *)

- ea: `0x180061d40`
- end: `0x180061f49`
- name: `?_InitPropVariantFromParsedString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `521`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180061f50`

## callees

- `0x180016694`
- `0x180024418`
- `0x18002b1b0`
- `0x1800366a0`
- `0x180036d70`
- `0x180061d40`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180061d8c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180061e93`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180061d8c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180061e93`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x180061e8a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x180061e8a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180061dd5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180061e69`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180061dd5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180061e69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061eee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061eff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061f17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061eee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061eff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061f17`

## pseudocode

```c
__int64 __fastcall _InitPropVariantFromParsedString(const unsigned __int16 *a1, struct tagPROPVARIANT *a2)
{
  unsigned __int16 *v2; // rsi
  __int64 v5; // rcx
  int v6; // eax
  int v7; // ebx
  int v8; // edi
  const WCHAR *v9; // r8
  PWSTR v10; // rax
  int v11; // ecx
  BYTE *v12; // r12
  void *v13; // rcx
  unsigned int v14; // r9d
  int v15; // eax
  WCHAR *v16; // r14
  __int64 v17; // rdi
  PWSTR v18; // rax
  WCHAR *v19; // r15
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned __int64 v22; // r14
  unsigned __int64 i; // rdi
  PCWSTR pszStart; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  void *v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v28[264]; // [rsp+40h] [rbp-C0h] BYREF

  v2 = v28;
  pszStart = v28;
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  if ( (unsigned int)lstrlenW(a1) < 0x104 )
  {
    v6 = StringCchCopyW(v28, 0x104u, a1);
  }
  else
  {
    v6 = _AllocString<CTCoAllocPolicy>(v5, 260, a1, &pszStart);
    v2 = (unsigned __int16 *)pszStart;
  }
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = 0;
    v9 = v2;
    while ( v9 )
    {
      v10 = StrChrW(v9, 0x3Bu);
      v11 = v8 + 1;
      if ( !v10 )
        v11 = v8;
      v9 = v10 + 1;
      v8 = v11;
      if ( !v10 )
        v9 = 0;
    }
    LODWORD(pszStart) = v8 + 1;
    if ( v8 != -1 )
    {
      v12 = 0;
      v27 = 0;
      v26 = 0;
      v7 = ULongLongMult((unsigned int)(v8 + 1), 8u, &v26);
      if ( v7 >= 0 )
      {
        v15 = CTCoAllocPolicy::Alloc(v13, 1u, v26, &v27);
        v14 = (unsigned int)pszStart;
        v7 = v15;
        v12 = (BYTE *)v27;
      }
      if ( v7 >= 0 )
      {
        v16 = v2;
        v17 = 0;
        while ( v16 )
        {
          if ( (unsigned int)v17 >= v14 )
            goto LABEL_24;
          v18 = StrChrW(v16, 0x3Bu);
          v19 = v18;
          if ( v18 )
          {
            *v18 = 0;
            v19 = v18 + 1;
          }
          StrTrimW(v16, L" ");
          if ( lstrlenW(v16) <= 0 || (v7 = _AllocString<CTCoAllocPolicy>(v21, v20, v16, &v12[8 * v17]), v7 < 0) )
          {
            v14 = (unsigned int)pszStart;
            v16 = v19;
            if ( v7 < 0 )
            {
LABEL_24:
              if ( v7 < 0 )
                goto LABEL_27;
              break;
            }
          }
          else
          {
            v14 = (unsigned int)pszStart;
            v17 = (unsigned int)(v17 + 1);
            v16 = v19;
          }
        }
        if ( (_DWORD)v17 )
        {
          a2->vt = 4127;
          a2->lVal = v17;
          a2->bstrblobVal.pData = v12;
          goto LABEL_30;
        }
LABEL_27:
        v22 = (unsigned int)v17;
        for ( i = 0; i < v22; ++i )
          CoTaskMemFree(*(LPVOID *)&v12[8 * i]);
        CoTaskMemFree(v12);
      }
    }
  }
LABEL_30:
  if ( v2 && v2 != v28 )
    CoTaskMemFree(v2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180061d40  mov     [rsp-8+arg_10], rbx
0x180061d45  push    rbp
0x180061d46  push    rsi
0x180061d47  push    rdi
0x180061d48  push    r12
0x180061d4a  push    r13
0x180061d4c  push    r14
0x180061d4e  push    r15
0x180061d50  lea     rbp, [rsp-160h]
0x180061d58  sub     rsp, 260h
0x180061d5f  mov     rax, cs:__security_cookie
0x180061d66  xor     rax, rsp
0x180061d69  mov     [rbp+190h+var_40], rax
0x180061d70  xorps   xmm0, xmm0
0x180061d73  lea     rsi, [rsp+290h+var_250]
0x180061d78  xor     eax, eax
0x180061d7a  mov     [rsp+290h+pszStart], rsi
0x180061d7f  movups  xmmword ptr [rdx], xmm0
0x180061d82  mov     [rdx+10h], rax
0x180061d86  mov     r13, rdx
0x180061d89  mov     rbx, rcx
0x180061d8c  call    cs:__imp_lstrlenW
0x180061d92  mov     edx, 104h; unsigned __int64
0x180061d97  mov     r8, rbx; unsigned __int16 *
0x180061d9a  cmp     eax, edx
0x180061d9c  jb      short loc_180061DAF
0x180061d9e  lea     r9, [rsp+290h+pszStart]
0x180061da3  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180061da8  mov     rsi, [rsp+290h+pszStart]
0x180061dad  jmp     short loc_180061DB9
0x180061daf  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x180061db4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180061db9  mov     ebx, eax
0x180061dbb  test    eax, eax
0x180061dbd  js      loc_180061F05
0x180061dc3  xor     edi, edi
0x180061dc5  mov     r8, rsi
0x180061dc8  test    rsi, rsi
0x180061dcb  jz      short loc_180061DF3
0x180061dcd  mov     edx, 3Bh ; ';'; wMatch
0x180061dd2  mov     rcx, r8; pszStart
0x180061dd5  call    cs:__imp_StrChrW
0x180061ddb  test    rax, rax
0x180061dde  lea     ecx, [rdi+1]
0x180061de1  cmovz   ecx, edi
0x180061de4  lea     r8, [rax+2]
0x180061de8  mov     edi, ecx
0x180061dea  cmovz   r8, rax
0x180061dee  test    r8, r8
0x180061df1  jnz     short loc_180061DCD
0x180061df3  lea     r9d, [rdi+1]
0x180061df7  mov     dword ptr [rsp+290h+pszStart], r9d
0x180061dfc  test    r9d, r9d
0x180061dff  jz      loc_180061F05
0x180061e05  xor     r12d, r12d
0x180061e08  mov     ecx, r9d; unsigned __int64
0x180061e0b  lea     r8, [rsp+290h+var_268]; unsigned __int64 *
0x180061e10  mov     [rsp+290h+var_260], r12
0x180061e15  mov     [rsp+290h+var_268], r12
0x180061e1a  lea     edx, [r12+8]; unsigned __int64
0x180061e1f  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180061e24  mov     ebx, eax
0x180061e26  test    eax, eax
0x180061e28  js      short loc_180061E4A
0x180061e2a  mov     r8, [rsp+290h+var_268]; unsigned __int64
0x180061e2f  lea     r9, [rsp+290h+var_260]; void **
0x180061e34  lea     edx, [r12+1]; unsigned int
0x180061e39  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180061e3e  mov     r9d, dword ptr [rsp+290h+pszStart]
0x180061e43  mov     ebx, eax
0x180061e45  mov     r12, [rsp+290h+var_260]
0x180061e4a  test    ebx, ebx
0x180061e4c  js      loc_180061F05
0x180061e52  mov     r14, rsi
0x180061e55  xor     edi, edi
0x180061e57  test    r14, r14
0x180061e5a  jz      short loc_180061ECB
0x180061e5c  cmp     edi, r9d
0x180061e5f  jnb     short loc_180061EC7
0x180061e61  mov     edx, 3Bh ; ';'; wMatch
0x180061e66  mov     rcx, r14; pszStart
0x180061e69  call    cs:__imp_StrChrW
0x180061e6f  mov     r15, rax
0x180061e72  test    rax, rax
0x180061e75  jz      short loc_180061E80
0x180061e77  xor     ecx, ecx
0x180061e79  mov     [rax], cx
0x180061e7c  add     r15, 2
0x180061e80  lea     rdx, pszTrimChars; " "
0x180061e87  mov     rcx, r14; psz
0x180061e8a  call    cs:__imp_StrTrimW
0x180061e90  mov     rcx, r14; lpString
0x180061e93  call    cs:__imp_lstrlenW
0x180061e99  test    eax, eax
0x180061e9b  jle     short loc_180061EBB
0x180061e9d  lea     r9, [r12+rdi*8]
0x180061ea1  mov     r8, r14
0x180061ea4  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180061ea9  mov     ebx, eax
0x180061eab  test    eax, eax
0x180061ead  js      short loc_180061EBB
0x180061eaf  mov     r9d, dword ptr [rsp+290h+pszStart]
0x180061eb4  inc     edi
0x180061eb6  mov     r14, r15
0x180061eb9  jmp     short loc_180061E57
0x180061ebb  mov     r9d, dword ptr [rsp+290h+pszStart]
0x180061ec0  mov     r14, r15
0x180061ec3  test    ebx, ebx
0x180061ec5  jns     short loc_180061E57
0x180061ec7  test    ebx, ebx
0x180061ec9  js      short loc_180061EE0
0x180061ecb  test    edi, edi
0x180061ecd  jz      short loc_180061EE0
0x180061ecf  mov     word ptr [r13+0], 101Fh
0x180061ed6  mov     [r13+8], edi
0x180061eda  mov     [r13+10h], r12
0x180061ede  jmp     short loc_180061F05
0x180061ee0  mov     r14d, edi
0x180061ee3  xor     edi, edi
0x180061ee5  test    r14, r14
0x180061ee8  jz      short loc_180061EFC
0x180061eea  mov     rcx, [r12+rdi*8]; pv
0x180061eee  call    cs:__imp_CoTaskMemFree
0x180061ef4  inc     rdi
0x180061ef7  cmp     rdi, r14
0x180061efa  jb      short loc_180061EEA
0x180061efc  mov     rcx, r12; pv
0x180061eff  call    cs:__imp_CoTaskMemFree
0x180061f05  test    rsi, rsi
0x180061f08  jz      short loc_180061F1D
0x180061f0a  lea     rax, [rsp+290h+var_250]
0x180061f0f  cmp     rsi, rax
0x180061f12  jz      short loc_180061F1D
0x180061f14  mov     rcx, rsi; pv
0x180061f17  call    cs:__imp_CoTaskMemFree
0x180061f1d  mov     eax, ebx
0x180061f1f  mov     rcx, [rbp+190h+var_40]
0x180061f26  xor     rcx, rsp; StackCookie
0x180061f29  call    __security_check_cookie
0x180061f2e  mov     rbx, [rsp+290h+arg_10]
0x180061f36  add     rsp, 260h
0x180061f3d  pop     r15
0x180061f3f  pop     r14
0x180061f41  pop     r13
0x180061f43  pop     r12
0x180061f45  pop     rdi
0x180061f46  pop     rsi
0x180061f47  pop     rbp
0x180061f48  retn
```
