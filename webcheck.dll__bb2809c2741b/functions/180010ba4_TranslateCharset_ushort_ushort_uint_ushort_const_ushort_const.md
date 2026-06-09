# TranslateCharset(ushort *,ushort *,uint,ushort const *,ushort const *)

- ea: `0x180010ba4`
- end: `0x180010d85`
- name: `?TranslateCharset@@YAJPEAG0IPEBG1@Z`
- size: `481`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010540`

## callees

- `0x180003950`
- `0x180010ba4`
- `0x18002924e`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetACP` at `0x180010c45`
- `KERNEL32!GetACP` at `0x180010c45`
- `ole32!CoCreateInstance` at `0x180010c23`
- `ole32!CoCreateInstance` at `0x180010c23`
- `OLEAUT32!__imp_SysAllocString` at `0x180010c52`
- `OLEAUT32!__imp_SysAllocString` at `0x180010c9e`
- `OLEAUT32!__imp_SysAllocString` at `0x180010c52`
- `OLEAUT32!__imp_SysAllocString` at `0x180010c9e`
- `OLEAUT32!__imp_SysFreeString` at `0x180010c8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180010cd0`
- `OLEAUT32!__imp_SysFreeString` at `0x180010c8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180010cd0`

## pseudocode

```c
__int64 __fastcall TranslateCharset(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        OLECHAR *psz)
{
  int v8; // ebx
  UINT ACP; // esi
  BSTR v10; // rax
  OLECHAR *v11; // rdi
  BSTR v12; // rax
  OLECHAR *v13; // rdi
  __int64 v14; // rax
  LPVOID ppv; // [rsp+58h] [rbp-89h] BYREF
  int v18; // [rsp+60h] [rbp-81h]
  _DWORD v19[3]; // [rsp+64h] [rbp-7Dh] BYREF
  _BYTE v20[4]; // [rsp+70h] [rbp-71h] BYREF
  UINT v21; // [rsp+74h] [rbp-6Dh]

  if ( a1 && a2 && psz )
  {
    ppv = 0;
    v8 = -2147467259;
    if ( CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage2, &ppv) < 0 )
      return (unsigned int)v8;
    memset_0(v20, 0, 0x6Cu);
    if ( a4 )
    {
      v10 = SysAllocString(a4);
      v11 = v10;
      if ( !v10 )
        goto LABEL_18;
      ACP = -1;
      v8 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _BYTE *))(*(_QWORD *)ppv + 56LL))(ppv, v10, v20);
      if ( v8 >= 0 )
        ACP = v21;
      SysFreeString(v11);
      if ( v8 < 0 )
        goto LABEL_19;
    }
    else
    {
      ACP = GetACP();
    }
    v12 = SysAllocString(psz);
    v13 = v12;
    if ( v12 )
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _BYTE *))(*(_QWORD *)ppv + 56LL))(ppv, v12, v20);
      SysFreeString(v13);
      if ( v8 >= 0 )
      {
        if ( ACP == v21 )
        {
          StringCchCopyW(a2, a3, a1);
        }
        else
        {
          v14 = -1;
          do
            ++v14;
          while ( a1[v14] );
          v18 = v14 + 1;
          v19[0] = 0;
          v8 = (*(__int64 (__fastcall **)(LPVOID, _DWORD *, _QWORD))(*(_QWORD *)ppv + 72LL))(ppv, v19, ACP);
        }
      }
      goto LABEL_19;
    }
LABEL_18:
    v8 = -2147024882;
LABEL_19:
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v8;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180010ba4  push    rbp
0x180010ba6  push    rbx
0x180010ba7  push    rsi
0x180010ba8  push    rdi
0x180010ba9  push    r12
0x180010bab  push    r13
0x180010bad  push    r14
0x180010baf  push    r15
0x180010bb1  lea     rbp, [rsp-17h]
0x180010bb6  sub     rsp, 0F8h
0x180010bbd  mov     rax, cs:__security_cookie
0x180010bc4  xor     rax, rsp
0x180010bc7  mov     [rbp+4Fh+var_50], rax
0x180010bcb  mov     r15, [rbp+4Fh+psz]
0x180010bcf  xor     r13d, r13d
0x180010bd2  mov     dword ptr [rsp+130h+var_E0], r8d
0x180010bd7  mov     rdi, r9
0x180010bda  mov     r12, rdx
0x180010bdd  mov     r14, rcx
0x180010be0  test    rcx, rcx
0x180010be3  jz      loc_180010D60
0x180010be9  test    rdx, rdx
0x180010bec  jz      loc_180010D60
0x180010bf2  test    r15, r15
0x180010bf5  jz      loc_180010D60
0x180010bfb  lea     rax, [rsp+130h+var_D8]
0x180010c00  mov     [rsp+130h+var_D8], r13
0x180010c05  lea     r9, IID_IMultiLanguage2; riid
0x180010c0c  mov     [rsp+130h+ppv], rax; ppv
0x180010c11  xor     edx, edx; pUnkOuter
0x180010c13  lea     r8d, [r13+1]; dwClsContext
0x180010c17  lea     rcx, CLSID_CMultiLanguage; rclsid
0x180010c1e  mov     ebx, 80004005h
0x180010c23  call    cs:__imp_CoCreateInstance
0x180010c29  test    eax, eax
0x180010c2b  js      loc_180010D5C
0x180010c31  xor     edx, edx; Val
0x180010c33  lea     r8d, [r13+6Ch]; Size
0x180010c37  lea     rcx, [rbp+4Fh+var_C0]; void *
0x180010c3b  call    memset_0
0x180010c40  test    rdi, rdi
0x180010c43  jnz     short loc_180010C4F
0x180010c45  call    cs:__imp_GetACP
0x180010c4b  mov     esi, eax
0x180010c4d  jmp     short loc_180010C9B
0x180010c4f  mov     rcx, rdi; psz
0x180010c52  call    cs:__imp_SysAllocString
0x180010c58  mov     rdi, rax
0x180010c5b  test    rax, rax
0x180010c5e  jz      loc_180010D46
0x180010c64  mov     r9, [rsp+130h+var_D8]
0x180010c69  lea     r8, [rbp+4Fh+var_C0]
0x180010c6d  mov     rdx, rdi
0x180010c70  or      esi, 0FFFFFFFFh
0x180010c73  mov     rcx, [r9]
0x180010c76  mov     rax, [rcx+38h]
0x180010c7a  mov     rcx, r9
0x180010c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c82  test    eax, eax
0x180010c84  mov     rcx, rdi; bstrString
0x180010c87  mov     ebx, eax
0x180010c89  cmovns  esi, [rbp+4Fh+var_BC]
0x180010c8d  call    cs:__imp_SysFreeString
0x180010c93  test    ebx, ebx
0x180010c95  js      loc_180010D4B
0x180010c9b  mov     rcx, r15; psz
0x180010c9e  call    cs:__imp_SysAllocString
0x180010ca4  mov     rdi, rax
0x180010ca7  test    rax, rax
0x180010caa  jz      loc_180010D46
0x180010cb0  mov     r9, [rsp+130h+var_D8]
0x180010cb5  lea     r8, [rbp+4Fh+var_C0]
0x180010cb9  mov     rdx, rdi
0x180010cbc  mov     rcx, [r9]
0x180010cbf  mov     rax, [rcx+38h]
0x180010cc3  mov     rcx, r9
0x180010cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ccb  mov     rcx, rdi; bstrString
0x180010cce  mov     ebx, eax
0x180010cd0  call    cs:__imp_SysFreeString
0x180010cd6  test    ebx, ebx
0x180010cd8  js      short loc_180010D4B
0x180010cda  mov     r9d, [rbp+4Fh+var_BC]
0x180010cde  cmp     esi, r9d
0x180010ce1  jz      short loc_180010D35
0x180010ce3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010ce7  inc     rax
0x180010cea  cmp     [r14+rax*2], r13w
0x180010cef  jnz     short loc_180010CE7
0x180010cf1  mov     rcx, [rsp+130h+var_D8]
0x180010cf6  lea     rdx, [rsp+130h+var_E0]
0x180010cfb  mov     [rsp+130h+var_F8], rdx
0x180010d00  inc     eax
0x180010d02  mov     [rsp+130h+var_D0], eax
0x180010d06  lea     rdx, [rsp+130h+var_D0]
0x180010d0b  mov     [rbp+4Fh+var_CC], r13d
0x180010d0f  mov     r8d, esi
0x180010d12  mov     rax, [rcx]
0x180010d15  mov     [rsp+130h+var_100], r12
0x180010d1a  mov     [rsp+130h+var_108], rdx
0x180010d1f  lea     rdx, [rbp+4Fh+var_CC]
0x180010d23  mov     [rsp+130h+ppv], r14
0x180010d28  mov     rax, [rax+48h]
0x180010d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d31  mov     ebx, eax
0x180010d33  jmp     short loc_180010D4B
0x180010d35  mov     edx, dword ptr [rsp+130h+var_E0]; unsigned __int64
0x180010d39  mov     r8, r14; unsigned __int16 *
0x180010d3c  mov     rcx, r12; unsigned __int16 *
0x180010d3f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010d44  jmp     short loc_180010D4B
0x180010d46  mov     ebx, 8007000Eh
0x180010d4b  mov     rcx, [rsp+130h+var_D8]
0x180010d50  mov     rax, [rcx]
0x180010d53  mov     rax, [rax+10h]
0x180010d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d5c  mov     eax, ebx
0x180010d5e  jmp     short loc_180010D65
0x180010d60  mov     eax, 80070057h
0x180010d65  mov     rcx, [rbp+4Fh+var_50]
0x180010d69  xor     rcx, rsp; StackCookie
0x180010d6c  call    __security_check_cookie
0x180010d71  add     rsp, 0F8h
0x180010d78  pop     r15
0x180010d7a  pop     r14
0x180010d7c  pop     r13
0x180010d7e  pop     r12
0x180010d80  pop     rdi
0x180010d81  pop     rsi
0x180010d82  pop     rbx
0x180010d83  pop     rbp
0x180010d84  retn
```
