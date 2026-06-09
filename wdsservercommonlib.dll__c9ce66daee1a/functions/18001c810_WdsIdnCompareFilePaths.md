# WdsIdnCompareFilePaths

- ea: `0x18001c810`
- end: `0x18001cb43`
- name: `WdsIdnCompareFilePaths`
- size: `819`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180016520`
- `0x180019a40`
- `0x18001a28c`
- `0x18001c810`
- `0x180024990`
- `0x180024b20`
- `0x180024be0`
- `0x180029770`
- `0x18002e468`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001ca98`
- `msvcrt!_wcsicmp` at `0x18001ca98`
- `SHLWAPI!PathIsUNCW` at `0x18001c893`
- `SHLWAPI!PathIsUNCW` at `0x18001c8ab`
- `SHLWAPI!PathIsUNCW` at `0x18001c893`
- `SHLWAPI!PathIsUNCW` at `0x18001c8ab`

## pseudocode

```c
__int64 __fastcall WdsIdnCompareFilePaths(LPCWSTR pszPath, const WCHAR *a2, int *a3)
{
  unsigned int v3; // ebx
  WCHAR *v4; // rsi
  WCHAR *v5; // rdi
  void *v6; // r14
  void *v7; // r13
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rax
  unsigned __int16 *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  int v28; // eax
  const wchar_t *v29; // rdx
  const wchar_t *v30; // rcx
  LPCWSTR lpUnicodeCharStr; // [rsp+38h] [rbp-59h] BYREF
  void *lpMem; // [rsp+40h] [rbp-51h] BYREF
  void *v34; // [rsp+48h] [rbp-49h] BYREF
  void *v35; // [rsp+50h] [rbp-41h]
  void *v36; // [rsp+58h] [rbp-39h]
  unsigned __int16 *v37[2]; // [rsp+60h] [rbp-31h] BYREF
  __int64 v38; // [rsp+70h] [rbp-21h]
  int v39; // [rsp+78h] [rbp-19h]
  unsigned __int16 *v40[2]; // [rsp+80h] [rbp-11h] BYREF
  __int64 v41; // [rsp+90h] [rbp-1h]
  int v42; // [rsp+98h] [rbp+7h]
  void *v46; // [rsp+110h] [rbp+7Fh] BYREF

  v41 = 0;
  v3 = 0;
  v38 = 0;
  *(_OWORD *)v40 = 0;
  lpMem = 0;
  v42 = 4;
  v4 = 0;
  v39 = 4;
  v5 = 0;
  lpUnicodeCharStr = 0;
  *(_OWORD *)v37 = 0;
  v35 = 0;
  v36 = 0;
  v6 = 0;
  v7 = 0;
  v46 = 0;
  v34 = 0;
  if ( !PathIsUNCW(pszPath) || !PathIsUNCW(a2) )
  {
    v29 = a2;
    v30 = pszPath;
    goto LABEL_24;
  }
  v3 = CTokenString::Initialize(v40, pszPath, L"\\", 0);
  if ( (unsigned int)ElValidateWin32_8(v3, v8, v9, 4942) )
    goto LABEL_37;
  v3 = CTokenString::Initialize(v37, a2, L"\\", 0);
  if ( (unsigned int)ElValidateWin32_8(v3, v10, v11, 4945) )
    goto LABEL_37;
  v3 = CTokenString::GetAt((CTokenString *)v40, 1u, (unsigned __int16 **)&lpMem);
  if ( (unsigned int)ElValidateWin32_8(v3, v12, v13, 4951) )
  {
    v4 = (WCHAR *)lpMem;
  }
  else
  {
    v3 = CTokenString::GetAt((CTokenString *)v37, 1u, (unsigned __int16 **)&lpUnicodeCharStr);
    v16 = ElValidateWin32_8(v3, v14, v15, 4954);
    v4 = (WCHAR *)lpMem;
    if ( v16 )
    {
      v5 = (WCHAR *)lpUnicodeCharStr;
    }
    else
    {
      v17 = -1;
      v18 = -1;
      do
        ++v18;
      while ( *((_WORD *)lpMem + v18) );
      v19 = WcsDup(&pszPath[v18 + 3]);
      v5 = (WCHAR *)lpUnicodeCharStr;
      v35 = v19;
      if ( !v19 )
        goto LABEL_10;
      do
        ++v17;
      while ( lpUnicodeCharStr[v17] );
      v36 = WcsDup(&a2[v17 + 3]);
      if ( v36 )
      {
        v3 = WdsIdnToAscii(1u, v4);
        if ( (unsigned int)ElValidateWin32_8(v3, v20, v21, 4973) )
          goto LABEL_25;
        v3 = WdsIdnToAscii(1u, v5);
        if ( (unsigned int)ElValidateWin32_8(v3, v22, v23, 4978) )
          goto LABEL_25;
        v3 = ConcatenatePaths(0, v35, &v46);
        if ( (unsigned int)ElValidateWin32_8(v3, v24, v25, 4987) )
        {
          v6 = v46;
        }
        else
        {
          v3 = ConcatenatePaths(0, v36, &v34);
          v28 = ElValidateWin32_8(v3, v26, v27, 4992);
          v7 = v34;
          v6 = v46;
          if ( !v28 )
          {
            v29 = (const wchar_t *)v34;
            v30 = (const wchar_t *)v46;
LABEL_24:
            *a3 = _wcsicmp(v30, v29);
          }
        }
      }
      else
      {
LABEL_10:
        v3 = 8;
      }
    }
  }
LABEL_25:
  if ( v4 )
    operator delete(v4);
  if ( v5 )
    operator delete(v5);
  if ( v35 )
    operator delete(v35);
  if ( v36 )
    operator delete(v36);
  if ( v6 )
    operator delete(v6);
  if ( v7 )
    operator delete(v7);
LABEL_37:
  CTokenString::Shutdown((CTokenString *)v37);
  CTokenString::Shutdown((CTokenString *)v40);
  return v3;
}

```

## disassembly

```asm
0x18001c810  mov     rax, rsp
0x18001c813  mov     [rax+18h], r8
0x18001c817  mov     [rax+10h], rdx
0x18001c81b  mov     [rax+8], rcx
0x18001c81f  push    rbp
0x18001c820  push    rbx
0x18001c821  push    rsi
0x18001c822  push    rdi
0x18001c823  push    r12
0x18001c825  push    r13
0x18001c827  push    r14
0x18001c829  push    r15
0x18001c82b  lea     rbp, [rax-5Fh]
0x18001c82f  sub     rsp, 0A8h
0x18001c836  xor     r8d, r8d
0x18001c839  mov     rax, rcx
0x18001c83c  xorps   xmm0, xmm0
0x18001c83f  mov     [rbp+57h+var_58], r8
0x18001c843  mov     ebx, r8d
0x18001c846  mov     [rbp+57h+var_78], r8
0x18001c84a  movdqu  xmmword ptr [rbp+57h+var_68], xmm0
0x18001c84f  lea     ecx, [r8+4]
0x18001c853  mov     [rbp+57h+lpMem], r8
0x18001c857  mov     [rbp+57h+var_50], ecx
0x18001c85a  mov     esi, r8d
0x18001c85d  mov     [rbp+57h+var_70], ecx
0x18001c860  mov     edi, r8d
0x18001c863  mov     rcx, rax; pszPath
0x18001c866  mov     [rbp+57h+lpUnicodeCharStr], r8
0x18001c86a  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18001c86f  mov     [rbp+57h+var_98], r8
0x18001c873  mov     r12d, r8d
0x18001c876  mov     [rbp+57h+var_90], r8
0x18001c87a  mov     r15d, r8d
0x18001c87d  mov     [rbp+57h+var_B8], r8
0x18001c881  mov     r14d, r8d
0x18001c884  mov     [rbp+57h+var_C0], r8
0x18001c888  mov     r13d, r8d
0x18001c88b  mov     [rbp+57h+arg_18], r8
0x18001c88f  mov     [rbp+57h+var_A0], r8
0x18001c893  call    cs:__imp_PathIsUNCW
0x18001c89a  nop     dword ptr [rax+rax+00h]
0x18001c89f  test    eax, eax
0x18001c8a1  jz      loc_18001CA90
0x18001c8a7  mov     rcx, [rbp+57h+pszPath]; pszPath
0x18001c8ab  call    cs:__imp_PathIsUNCW
0x18001c8b2  nop     dword ptr [rax+rax+00h]
0x18001c8b7  test    eax, eax
0x18001c8b9  jz      loc_18001CA90
0x18001c8bf  mov     rdx, [rbp+57h+String1]; unsigned __int16 *
0x18001c8c3  lea     r8, SubBlock; "\\"
0x18001c8ca  xor     r9d, r9d; unsigned int
0x18001c8cd  lea     rcx, [rbp+57h+var_68]; this
0x18001c8d1  call    ?Initialize@CTokenString@@QEAAKPEBG0K@Z; CTokenString::Initialize(ushort const *,ushort const *,ulong)
0x18001c8d6  mov     r9d, 134Eh
0x18001c8dc  mov     ecx, eax
0x18001c8de  mov     ebx, eax
0x18001c8e0  call    ElValidateWin32_8
0x18001c8e5  test    eax, eax
0x18001c8e7  jnz     loc_18001CB1A
0x18001c8ed  mov     rdx, [rbp+57h+pszPath]; unsigned __int16 *
0x18001c8f1  lea     r8, SubBlock; "\\"
0x18001c8f8  xor     r9d, r9d; unsigned int
0x18001c8fb  lea     rcx, [rbp+57h+var_88]; this
0x18001c8ff  call    ?Initialize@CTokenString@@QEAAKPEBG0K@Z; CTokenString::Initialize(ushort const *,ushort const *,ulong)
0x18001c904  mov     r9d, 1351h
0x18001c90a  mov     ecx, eax
0x18001c90c  mov     ebx, eax
0x18001c90e  call    ElValidateWin32_8
0x18001c913  test    eax, eax
0x18001c915  jnz     loc_18001CB1A
0x18001c91b  lea     r8, [rbp+57h+lpMem]; unsigned __int16 **
0x18001c91f  lea     edx, [rax+1]; unsigned int
0x18001c922  lea     rcx, [rbp+57h+var_68]; this
0x18001c926  call    ?GetAt@CTokenString@@QEAAKKPEAPEAG@Z; CTokenString::GetAt(ulong,ushort * *)
0x18001c92b  mov     r9d, 1357h
0x18001c931  mov     ecx, eax
0x18001c933  mov     ebx, eax
0x18001c935  call    ElValidateWin32_8
0x18001c93a  test    eax, eax
0x18001c93c  jnz     loc_18001CA8A
0x18001c942  lea     r8, [rbp+57h+lpUnicodeCharStr]; unsigned __int16 **
0x18001c946  lea     edx, [rax+1]; unsigned int
0x18001c949  lea     rcx, [rbp+57h+var_88]; this
0x18001c94d  call    ?GetAt@CTokenString@@QEAAKKPEAPEAG@Z; CTokenString::GetAt(ulong,ushort * *)
0x18001c952  mov     r9d, 135Ah
0x18001c958  mov     ecx, eax
0x18001c95a  mov     ebx, eax
0x18001c95c  call    ElValidateWin32_8
0x18001c961  mov     rsi, [rbp+57h+lpMem]
0x18001c965  test    eax, eax
0x18001c967  jnz     loc_18001CA84
0x18001c96d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001c971  mov     rax, rbx
0x18001c974  inc     rax
0x18001c977  cmp     [rsi+rax*2], di
0x18001c97b  jnz     short loc_18001C974
0x18001c97d  mov     rcx, [rbp+57h+String1]
0x18001c981  lea     rcx, [rcx+rax*2]
0x18001c985  add     rcx, 6; Src
0x18001c989  call    ?WcsDup@@YAPEAGPEBG@Z; WcsDup(ushort const *)
0x18001c98e  mov     rdi, [rbp+57h+lpUnicodeCharStr]
0x18001c992  mov     [rbp+57h+var_98], rax
0x18001c996  test    rax, rax
0x18001c999  jnz     short loc_18001C9A5
0x18001c99b  mov     ebx, 8
0x18001c9a0  jmp     loc_18001CAAA
0x18001c9a5  xor     eax, eax
0x18001c9a7  inc     rbx
0x18001c9aa  cmp     [rdi+rbx*2], ax
0x18001c9ae  jnz     short loc_18001C9A7
0x18001c9b0  mov     rcx, [rbp+57h+pszPath]
0x18001c9b4  add     rcx, 6
0x18001c9b8  lea     rcx, [rcx+rbx*2]; Src
0x18001c9bc  call    ?WcsDup@@YAPEAGPEBG@Z; WcsDup(ushort const *)
0x18001c9c1  mov     [rbp+57h+var_90], rax
0x18001c9c5  test    rax, rax
0x18001c9c8  jz      short loc_18001C99B
0x18001c9ca  lea     r8, [rbp+57h+var_B8]
0x18001c9ce  mov     rdx, rsi; lpUnicodeCharStr
0x18001c9d1  mov     ecx, 1; dwFlags
0x18001c9d6  call    WdsIdnToAscii
0x18001c9db  mov     r9d, 136Dh
0x18001c9e1  mov     ecx, eax
0x18001c9e3  mov     ebx, eax
0x18001c9e5  call    ElValidateWin32_8
0x18001c9ea  test    eax, eax
0x18001c9ec  jnz     loc_18001CA7E
0x18001c9f2  lea     r8, [rbp+57h+var_C0]
0x18001c9f6  mov     rdx, rdi; lpUnicodeCharStr
0x18001c9f9  lea     ecx, [rax+1]; dwFlags
0x18001c9fc  call    WdsIdnToAscii
0x18001ca01  mov     r9d, 1372h
0x18001ca07  mov     ecx, eax
0x18001ca09  mov     ebx, eax
0x18001ca0b  call    ElValidateWin32_8
0x18001ca10  mov     r12, [rbp+57h+var_B8]
0x18001ca14  test    eax, eax
0x18001ca16  jnz     short loc_18001CA78
0x18001ca18  mov     rdx, [rbp+57h+var_98]
0x18001ca1c  lea     r8, [rbp+57h+arg_18]
0x18001ca20  mov     rcx, r12
0x18001ca23  call    ConcatenatePaths
0x18001ca28  mov     r9d, 137Bh
0x18001ca2e  mov     ecx, eax
0x18001ca30  mov     ebx, eax
0x18001ca32  call    ElValidateWin32_8
0x18001ca37  mov     r15, [rbp+57h+var_C0]
0x18001ca3b  test    eax, eax
0x18001ca3d  jnz     short loc_18001CA72
0x18001ca3f  mov     rdx, [rbp+57h+var_90]
0x18001ca43  lea     r8, [rbp+57h+var_A0]
0x18001ca47  mov     rcx, r15
0x18001ca4a  call    ConcatenatePaths
0x18001ca4f  mov     r9d, 1380h
0x18001ca55  mov     ecx, eax
0x18001ca57  mov     ebx, eax
0x18001ca59  call    ElValidateWin32_8
0x18001ca5e  mov     r13, [rbp+57h+var_A0]
0x18001ca62  mov     r14, [rbp+57h+arg_18]
0x18001ca66  test    eax, eax
0x18001ca68  jnz     short loc_18001CAAA
0x18001ca6a  mov     rdx, r13
0x18001ca6d  mov     rcx, r14
0x18001ca70  jmp     short loc_18001CA98
0x18001ca72  mov     r14, [rbp+57h+arg_18]
0x18001ca76  jmp     short loc_18001CAAA
0x18001ca78  mov     r15, [rbp+57h+var_C0]
0x18001ca7c  jmp     short loc_18001CAAA
0x18001ca7e  mov     r12, [rbp+57h+var_B8]
0x18001ca82  jmp     short loc_18001CAAA
0x18001ca84  mov     rdi, [rbp+57h+lpUnicodeCharStr]
0x18001ca88  jmp     short loc_18001CAAA
0x18001ca8a  mov     rsi, [rbp+57h+lpMem]
0x18001ca8e  jmp     short loc_18001CAAA
0x18001ca90  mov     rdx, [rbp+57h+pszPath]; String2
0x18001ca94  mov     rcx, [rbp+57h+String1]; String1
0x18001ca98  call    cs:__imp__wcsicmp
0x18001ca9f  nop     dword ptr [rax+rax+00h]
0x18001caa4  mov     rcx, [rbp+57h+arg_10]
0x18001caa8  mov     [rcx], eax
0x18001caaa  test    rsi, rsi
0x18001caad  jz      short loc_18001CAB7
0x18001caaf  mov     rcx, rsi; lpMem
0x18001cab2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cab7  test    rdi, rdi
0x18001caba  jz      short loc_18001CAC4
0x18001cabc  mov     rcx, rdi; lpMem
0x18001cabf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cac4  mov     rax, [rbp+57h+var_98]
0x18001cac8  test    rax, rax
0x18001cacb  jz      short loc_18001CAD5
0x18001cacd  mov     rcx, rax; lpMem
0x18001cad0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cad5  mov     rax, [rbp+57h+var_90]
0x18001cad9  test    rax, rax
0x18001cadc  jz      short loc_18001CAE6
0x18001cade  mov     rcx, rax; lpMem
0x18001cae1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cae6  test    r12, r12
0x18001cae9  jz      short loc_18001CAF3
0x18001caeb  mov     rcx, r12; lpMem
0x18001caee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001caf3  test    r15, r15
0x18001caf6  jz      short loc_18001CB00
0x18001caf8  mov     rcx, r15; lpMem
0x18001cafb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cb00  test    r14, r14
0x18001cb03  jz      short loc_18001CB0D
0x18001cb05  mov     rcx, r14; lpMem
0x18001cb08  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cb0d  test    r13, r13
0x18001cb10  jz      short loc_18001CB1A
0x18001cb12  mov     rcx, r13; lpMem
0x18001cb15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cb1a  lea     rcx, [rbp+57h+var_88]; this
0x18001cb1e  call    ?Shutdown@CTokenString@@QEAAKXZ; CTokenString::Shutdown(void)
0x18001cb23  lea     rcx, [rbp+57h+var_68]; this
0x18001cb27  call    ?Shutdown@CTokenString@@QEAAKXZ; CTokenString::Shutdown(void)
0x18001cb2c  mov     eax, ebx
0x18001cb2e  add     rsp, 0A8h
0x18001cb35  pop     r15
0x18001cb37  pop     r14
0x18001cb39  pop     r13
0x18001cb3b  pop     r12
0x18001cb3d  pop     rdi
0x18001cb3e  pop     rsi
0x18001cb3f  pop     rbx
0x18001cb40  pop     rbp
0x18001cb41  retn
```
