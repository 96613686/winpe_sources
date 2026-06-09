# SHGetParsingNameFromPropertyStore(ushort const *,INamedPropertyStore *,ushort * *)

- ea: `0x18003e660`
- end: `0x18003e971`
- name: `?SHGetParsingNameFromPropertyStore@@YAJPEBGPEAUINamedPropertyStore@@PEAPEAG@Z`
- size: `785`
- prototype: `int(const unsigned __int16 *, struct INamedPropertyStore *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003f898`

## callees

- `0x180002280`
- `0x18003ad80`
- `0x18003e660`
- `0x18003eb50`
- `0x1800405c8`
- `0x18004f500`
- `0x18004f5d4`
- `0x180057010`

## import_xrefs

- `PROPSYS!PropVariantToStringAlloc` at `0x18003e7c5`
- `PROPSYS!PropVariantToStringAlloc` at `0x18003e7c5`
- `SHLWAPI!SHStrDupW` at `0x18003e92b`
- `SHLWAPI!SHStrDupW` at `0x18003e92b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e8ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e8e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e8ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e8e6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003e8f7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003e8f7`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e908`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e908`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18003e823`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18003e823`

## string_xrefs

- `0x18003e6d3`: `::{d84fa0c2-b0b3-4470-9345-75db0ec5a83a},ChildCLSID={267cf8a9-f4e3-41e6-95b1-af881be130ff}&`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SHGetParsingNameFromPropertyStore(
        const unsigned __int16 *a1,
        struct INamedPropertyStore *a2,
        unsigned __int16 **a3)
{
  HRESULT v5; // ebx
  unsigned int v6; // edi
  const unsigned __int16 *v7; // rcx
  __int64 v9; // [rsp+30h] [rbp-D0h]
  unsigned int v10; // [rsp+40h] [rbp-C0h] BYREF
  LONG rgIndices[2]; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *pv; // [rsp+50h] [rbp-B0h]
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR ppszOut; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT propvar[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v16; // [rsp+78h] [rbp-88h]
  _WORD v17[68]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR psz; // [rsp+108h] [rbp+8h]
  int v19; // [rsp+110h] [rbp+10h]
  _WORD v20[68]; // [rsp+120h] [rbp+20h] BYREF
  LPCWSTR lpString; // [rsp+1A8h] [rbp+A8h]
  int v22; // [rsp+1B0h] [rbp+B0h]
  wchar_t Buffer; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v24; // [rsp+1C2h] [rbp+C2h]
  __int16 v25; // [rsp+1CAh] [rbp+CAh]

  v10 = 0;
  v5 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, unsigned int *))a2->lpVtbl->GetNameCount)(a2, &v10);
  if ( v5 >= 0 )
  {
    v17[0] = 0;
    psz = v17;
    v19 = 65;
    ShStrW::Append(
      (ShStrW *)v17,
      L"::{d84fa0c2-b0b3-4470-9345-75db0ec5a83a},ChildCLSID={267cf8a9-f4e3-41e6-95b1-af881be130ff}&");
    v6 = 0;
    if ( v10 )
    {
      while ( 1 )
      {
        if ( v5 < 0 )
          goto LABEL_24;
        bstrString = 0;
        v5 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, _QWORD, BSTR *))a2->lpVtbl->GetNameAt)(
               a2,
               v6,
               &bstrString);
        if ( v5 >= 0 )
          break;
LABEL_21:
        if ( ++v6 >= v10 )
        {
          if ( v5 < 0 )
            goto LABEL_24;
          goto LABEL_23;
        }
      }
      *(_OWORD *)propvar = 0;
      v16 = 0;
      v5 = ((__int64 (__fastcall *)(struct INamedPropertyStore *, BSTR, PROPVARIANT *))a2->lpVtbl->GetNamedValue)(
             a2,
             bstrString,
             propvar);
      if ( v5 < 0 )
      {
LABEL_20:
        SysFreeString(bstrString);
        goto LABEL_21;
      }
      Buffer = 0;
      v24 = 0;
      v25 = 0;
      v7 = 0;
      pv = 0;
      ppszOut = 0;
      if ( LOWORD(propvar[0]) == 31 || LOWORD(propvar[0]) == 8 )
      {
        rgIndices[0] = 0;
        v5 = -2147024809;
        if ( ((__int64)propvar[0] & 0xFFF) != 0x1F && ((__int64)propvar[0] & 0xFFF) != 8 )
          goto LABEL_13;
        v7 = (const unsigned __int16 *)propvar[1];
        v5 = 0;
      }
      else
      {
        LODWORD(v9) = LOWORD(propvar[0]);
        StringCchPrintfExW(&Buffer, 6u, 0, 0, 0x800u, L":%04x", v9);
        v5 = PropVariantToStringAlloc(propvar, &ppszOut);
        v7 = ppszOut;
      }
      pv = v7;
LABEL_13:
      if ( v5 >= 0 )
      {
        *(_QWORD *)rgIndices = 0;
        v5 = _EscapeField(v7, (LPWSTR *)rgIndices);
        if ( v5 >= 0 )
        {
          v20[0] = 0;
          lpString = v20;
          v22 = 65;
          v5 = ShStrW::Printf((ShStrW *)v20, (wchar_t *)L"%s%s=%s&", bstrString, &Buffer, *(_QWORD *)rgIndices);
          if ( v5 >= 0 )
            v5 = ShStrW::Append((ShStrW *)v17, lpString);
          CoTaskMemFree(*(LPVOID *)rgIndices);
          ShStrW::Reset((ShStrW *)v20);
        }
        CoTaskMemFree(ppszOut);
      }
      PropVariantClear(propvar);
      goto LABEL_20;
    }
LABEL_23:
    v5 = SHStrDupW(psz, a3);
LABEL_24:
    ShStrW::Reset((ShStrW *)v17);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003e660  mov     [rsp-8+arg_0], rbx
0x18003e665  mov     [rsp-8+arg_18], rsi
0x18003e66a  push    rbp
0x18003e66b  push    rdi
0x18003e66c  push    r12
0x18003e66e  push    r13
0x18003e670  push    r14
0x18003e672  lea     rbp, [rsp-0E0h]
0x18003e67a  sub     rsp, 1E0h
0x18003e681  mov     rax, cs:__security_cookie
0x18003e688  xor     rax, rsp
0x18003e68b  mov     [rbp+100h+var_30], rax
0x18003e692  mov     r14, r8
0x18003e695  mov     rsi, rdx
0x18003e698  mov     [rsp+200h+var_1C0], 0
0x18003e6a0  mov     rax, [rdx]
0x18003e6a3  lea     rdx, [rsp+200h+var_1C0]
0x18003e6a8  mov     rcx, rsi
0x18003e6ab  mov     rax, [rax+28h]
0x18003e6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6b4  mov     ebx, eax
0x18003e6b6  test    eax, eax
0x18003e6b8  js      loc_18003E943
0x18003e6be  xor     ecx, ecx
0x18003e6c0  mov     [rbp+100h+var_180], cx
0x18003e6c4  lea     rax, [rbp+100h+var_180]
0x18003e6c8  mov     [rbp+100h+psz], rax
0x18003e6cc  mov     [rbp+100h+var_F0], 41h ; 'A'
0x18003e6d3  lea     rdx, String; "::{d84fa0c2-b0b3-4470-9345-75db0ec5a83a"...
0x18003e6da  lea     rcx, [rbp+100h+var_180]; this
0x18003e6de  call    ?Append@ShStrW@@QEAAJPEBG@Z; ShStrW::Append(ushort const *)
0x18003e6e3  xor     edi, edi
0x18003e6e5  cmp     [rsp+200h+var_1C0], edi
0x18003e6e9  jbe     loc_18003E924
0x18003e6ef  lea     r13d, [rdi+1Fh]
0x18003e6f3  lea     r12d, [rdi+8]
0x18003e6f7  test    ebx, ebx
0x18003e6f9  js      loc_18003E939
0x18003e6ff  mov     [rsp+200h+bstrString], 0
0x18003e708  mov     rax, [rsi]
0x18003e70b  lea     r8, [rsp+200h+bstrString]
0x18003e710  mov     edx, edi
0x18003e712  mov     rcx, rsi
0x18003e715  mov     rax, [rax+30h]
0x18003e719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e71e  mov     ebx, eax
0x18003e720  test    eax, eax
0x18003e722  js      loc_18003E914
0x18003e728  xorps   xmm0, xmm0
0x18003e72b  xor     eax, eax
0x18003e72d  movups  xmmword ptr [rsp+200h+propvar], xmm0
0x18003e732  mov     [rsp+200h+var_188], rax
0x18003e737  mov     rax, [rsi]
0x18003e73a  lea     r8, [rsp+200h+propvar]
0x18003e73f  mov     rdx, [rsp+200h+bstrString]
0x18003e744  mov     rcx, rsi
0x18003e747  mov     rax, [rax+18h]
0x18003e74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e750  mov     ebx, eax
0x18003e752  test    eax, eax
0x18003e754  js      loc_18003E903
0x18003e75a  xor     eax, eax
0x18003e75c  mov     [rbp+100h+Buffer], ax
0x18003e763  mov     [rbp+100h+var_3E], rax
0x18003e76a  mov     [rbp+100h+var_36], ax
0x18003e771  xor     ecx, ecx
0x18003e773  mov     [rsp+200h+pv], rcx
0x18003e778  mov     [rsp+200h+ppszOut], rax
0x18003e77d  movzx   eax, word ptr [rsp+200h+propvar]
0x18003e782  cmp     ax, r13w
0x18003e786  jz      short loc_18003E7DA
0x18003e788  cmp     ax, r12w
0x18003e78c  jz      short loc_18003E7DA
0x18003e78e  mov     [rsp+200h+var_1D0], eax
0x18003e792  lea     rax, a04x; ":%04x"
0x18003e799  mov     [rsp+200h+var_1D8], rax; unsigned __int16 *
0x18003e79e  mov     [rsp+200h+var_1E0], 800h; unsigned int
0x18003e7a6  xor     r9d, r9d; unsigned __int64 *
0x18003e7a9  xor     r8d, r8d; unsigned __int16 **
0x18003e7ac  lea     edx, [rcx+6]; unsigned __int64
0x18003e7af  lea     rcx, [rbp+100h+Buffer]; Buffer
0x18003e7b6  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18003e7bb  lea     rdx, [rsp+200h+ppszOut]; ppszOut
0x18003e7c0  lea     rcx, [rsp+200h+propvar]; propvar
0x18003e7c5  call    cs:__imp_PropVariantToStringAlloc
0x18003e7cc  nop     dword ptr [rax+rax+00h]
0x18003e7d1  mov     ebx, eax
0x18003e7d3  mov     rcx, [rsp+200h+ppszOut]
0x18003e7d8  jmp     short loc_18003E846
0x18003e7da  mov     [rsp+200h+rgIndices], ecx
0x18003e7de  mov     r8d, 0FFFh
0x18003e7e4  movzx   edx, ax
0x18003e7e7  and     dx, r8w
0x18003e7eb  mov     ebx, 80070057h
0x18003e7f0  cmp     r13w, dx
0x18003e7f4  jz      short loc_18003E7FC
0x18003e7f6  cmp     r12w, dx
0x18003e7fa  jnz     short loc_18003E84B
0x18003e7fc  bt      ax, 0Ch
0x18003e801  jnb     short loc_18003E80D
0x18003e803  mov     rax, [rsp+200h+var_188]
0x18003e808  mov     rcx, [rax]
0x18003e80b  jmp     short loc_18003E844
0x18003e80d  bt      ax, 0Dh
0x18003e812  jnb     short loc_18003E838
0x18003e814  lea     r8, [rsp+200h+pv]; pv
0x18003e819  lea     rdx, [rsp+200h+rgIndices]; rgIndices
0x18003e81e  mov     rcx, [rsp+200h+propvar+8]; psa
0x18003e823  call    cs:__imp_SafeArrayGetElement
0x18003e82a  nop     dword ptr [rax+rax+00h]
0x18003e82f  mov     ebx, eax
0x18003e831  mov     rcx, [rsp+200h+pv]
0x18003e836  jmp     short loc_18003E84B
0x18003e838  test    eax, 0FFFFF000h
0x18003e83d  jnz     short loc_18003E84B
0x18003e83f  mov     rcx, [rsp+200h+propvar+8]; unsigned __int16 *
0x18003e844  xor     ebx, ebx
0x18003e846  mov     [rsp+200h+pv], rcx
0x18003e84b  test    ebx, ebx
0x18003e84d  js      loc_18003E8F2
0x18003e853  mov     qword ptr [rsp+200h+rgIndices], 0
0x18003e85c  lea     rdx, [rsp+200h+rgIndices]; ppwsz
0x18003e861  call    ?_EscapeField@@YAJPEBGPEAPEAG@Z; _EscapeField(ushort const *,ushort * *)
0x18003e866  mov     ebx, eax
0x18003e868  test    eax, eax
0x18003e86a  js      short loc_18003E8E1
0x18003e86c  xor     eax, eax
0x18003e86e  mov     [rbp+100h+var_E0], ax
0x18003e872  lea     rax, [rbp+100h+var_E0]
0x18003e876  mov     [rbp+100h+lpString], rax
0x18003e87d  mov     [rbp+100h+var_50], 41h ; 'A'
0x18003e887  mov     rax, qword ptr [rsp+200h+rgIndices]
0x18003e88c  mov     qword ptr [rsp+200h+var_1E0], rax
0x18003e891  lea     r9, [rbp+100h+Buffer]
0x18003e898  mov     r8, [rsp+200h+bstrString]
0x18003e89d  lea     rdx, aSSS; "%s%s=%s&"
0x18003e8a4  lea     rcx, [rbp+100h+var_E0]; this
0x18003e8a8  call    ?Printf@ShStrW@@QEAAJPEBGZZ; ShStrW::Printf(ushort const *,...)
0x18003e8ad  mov     ebx, eax
0x18003e8af  test    eax, eax
0x18003e8b1  js      short loc_18003E8C5
0x18003e8b3  mov     rdx, [rbp+100h+lpString]; lpString
0x18003e8ba  lea     rcx, [rbp+100h+var_180]; this
0x18003e8be  call    ?Append@ShStrW@@QEAAJPEBG@Z; ShStrW::Append(ushort const *)
0x18003e8c3  mov     ebx, eax
0x18003e8c5  mov     rcx, qword ptr [rsp+200h+rgIndices]; pv
0x18003e8ca  call    cs:__imp_CoTaskMemFree
0x18003e8d1  nop     dword ptr [rax+rax+00h]
0x18003e8d6  nop
0x18003e8d7  lea     rcx, [rbp+100h+var_E0]; this
0x18003e8db  call    ?Reset@ShStrW@@QEAAXXZ; ShStrW::Reset(void)
0x18003e8e0  nop
0x18003e8e1  mov     rcx, [rsp+200h+ppszOut]; pv
0x18003e8e6  call    cs:__imp_CoTaskMemFree
0x18003e8ed  nop     dword ptr [rax+rax+00h]
0x18003e8f2  lea     rcx, [rsp+200h+propvar]; pvar
0x18003e8f7  call    cs:__imp_PropVariantClear
0x18003e8fe  nop     dword ptr [rax+rax+00h]
0x18003e903  mov     rcx, [rsp+200h+bstrString]; bstrString
0x18003e908  call    cs:__imp_SysFreeString
0x18003e90f  nop     dword ptr [rax+rax+00h]
0x18003e914  inc     edi
0x18003e916  cmp     edi, [rsp+200h+var_1C0]
0x18003e91a  jb      loc_18003E6F7
0x18003e920  test    ebx, ebx
0x18003e922  js      short loc_18003E939
0x18003e924  mov     rdx, r14; ppwsz
0x18003e927  mov     rcx, [rbp+100h+psz]; psz
0x18003e92b  call    cs:__imp_SHStrDupW
0x18003e932  nop     dword ptr [rax+rax+00h]
0x18003e937  mov     ebx, eax
0x18003e939  lea     rcx, [rbp+100h+var_180]; this
0x18003e93d  call    ?Reset@ShStrW@@QEAAXXZ; ShStrW::Reset(void)
0x18003e942  nop
0x18003e943  mov     eax, ebx
0x18003e945  mov     rcx, [rbp+100h+var_30]
0x18003e94c  xor     rcx, rsp; StackCookie
0x18003e94f  call    __security_check_cookie
0x18003e954  lea     r11, [rsp+200h+var_20]
0x18003e95c  mov     rbx, [r11+30h]
0x18003e960  mov     rsi, [r11+48h]
0x18003e964  mov     rsp, r11
0x18003e967  pop     r14
0x18003e969  pop     r13
0x18003e96b  pop     r12
0x18003e96d  pop     rdi
0x18003e96e  pop     rbp
0x18003e96f  retn
```
