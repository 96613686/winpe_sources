# CSusSortedArrayListItemOpsPtrCCategory::Compare(CCategory const * const &,CCategory const * const &)

- ea: `0x180008b18`
- end: `0x180008c2e`
- name: `?Compare@CSusSortedArrayListItemOpsPtrCCategory@@SAHAEBQEBVCCategory@@0@Z`
- size: `278`
- prototype: `__int64 __fastcall(const struct CCategory *const *, const struct CCategory *const *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009b30`
- `0x18000a400`

## callees

- `0x180008b18`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008b8d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008bda`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008b8d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180008bda`
- `OLEAUT32!__imp_SysStringLen` at `0x180008b54`
- `OLEAUT32!__imp_SysStringLen` at `0x180008b6a`
- `OLEAUT32!__imp_SysStringLen` at `0x180008ba1`
- `OLEAUT32!__imp_SysStringLen` at `0x180008bb7`
- `OLEAUT32!__imp_SysStringLen` at `0x180008b54`
- `OLEAUT32!__imp_SysStringLen` at `0x180008b6a`
- `OLEAUT32!__imp_SysStringLen` at `0x180008ba1`
- `OLEAUT32!__imp_SysStringLen` at `0x180008bb7`

## pseudocode

```c
__int64 __fastcall CSusSortedArrayListItemOpsPtrCCategory::Compare(
        const struct CCategory *const *a1,
        const struct CCategory *const *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // r9
  int v6; // r8d
  UINT cchCount2; // edi
  const WCHAR *lpString2; // rbx
  UINT v9; // eax
  int v10; // ecx
  UINT v11; // edi
  const WCHAR *v12; // rbx
  UINT v13; // eax
  int v14; // ecx
  int v15; // ecx
  __int64 result; // rax

  v4 = *a2;
  v5 = (__int64)*a1;
  if ( *a1 == *a2 )
    return 0;
  v6 = *((_DWORD *)v4 + 22);
  if ( *(_DWORD *)(v5 + 88) == v6 )
  {
    cchCount2 = SysStringLen((BSTR)v4[9]);
    lpString2 = (const WCHAR *)*((_QWORD *)*a2 + 9);
    v9 = SysStringLen(*((BSTR *)*a1 + 9));
    v10 = CompareStringW(0x400u, 0x10001u, *((PCNZWCH *)*a1 + 9), v9, lpString2, cchCount2);
    if ( v10 == 2 )
    {
      v11 = SysStringLen(*((BSTR *)*a2 + 7));
      v12 = (const WCHAR *)*((_QWORD *)*a2 + 7);
      v13 = SysStringLen(*((BSTR *)*a1 + 7));
      v10 = CompareStringW(0x400u, 0x10001u, *((PCNZWCH *)*a1 + 7), v13, v12, v11);
    }
    if ( !v10 )
      return 4294967294LL;
    v14 = v10 - 1;
    if ( !v14 )
      return 0xFFFFFFFFLL;
    v15 = v14 - 1;
    if ( v15 )
    {
      if ( v15 == 1 )
        return 1;
      return 4294967294LL;
    }
    return 0;
  }
  result = 1;
  if ( *(_DWORD *)(v5 + 88) < v6 )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x180008b18  mov     [rsp+arg_0], rbx
0x180008b1d  mov     [rsp+arg_8], rsi
0x180008b22  mov     [rsp+arg_10], rdi
0x180008b27  push    r14
0x180008b29  sub     rsp, 30h
0x180008b2d  mov     rsi, rcx
0x180008b30  mov     r14, rdx
0x180008b33  mov     rcx, [rdx]
0x180008b36  mov     r9, [rsi]
0x180008b39  cmp     r9, rcx
0x180008b3c  jz      loc_180008C16
0x180008b42  mov     r8d, [rcx+58h]
0x180008b46  cmp     [r9+58h], r8d
0x180008b4a  jnz     loc_180008C05
0x180008b50  mov     rcx, [rcx+48h]; pbstr
0x180008b54  call    cs:__imp_SysStringLen
0x180008b5a  mov     rcx, [r14]
0x180008b5d  mov     edi, eax
0x180008b5f  mov     rbx, [rcx+48h]
0x180008b63  mov     rcx, [rsi]
0x180008b66  mov     rcx, [rcx+48h]; pbstr
0x180008b6a  call    cs:__imp_SysStringLen
0x180008b70  mov     r8, [rsi]
0x180008b73  mov     edx, 10001h; dwCmpFlags
0x180008b78  mov     [rsp+38h+cchCount2], edi; cchCount2
0x180008b7c  mov     r9d, eax; cchCount1
0x180008b7f  mov     ecx, 400h; Locale
0x180008b84  mov     [rsp+38h+lpString2], rbx; lpString2
0x180008b89  mov     r8, [r8+48h]; lpString1
0x180008b8d  call    cs:__imp_CompareStringW
0x180008b93  mov     ecx, eax
0x180008b95  cmp     eax, 2
0x180008b98  jnz     short loc_180008BE2
0x180008b9a  mov     rcx, [r14]
0x180008b9d  mov     rcx, [rcx+38h]; pbstr
0x180008ba1  call    cs:__imp_SysStringLen
0x180008ba7  mov     rcx, [rsi]
0x180008baa  mov     edi, eax
0x180008bac  mov     r8, [r14]
0x180008baf  mov     rcx, [rcx+38h]; pbstr
0x180008bb3  mov     rbx, [r8+38h]
0x180008bb7  call    cs:__imp_SysStringLen
0x180008bbd  mov     r8, [rsi]
0x180008bc0  mov     edx, 10001h; dwCmpFlags
0x180008bc5  mov     [rsp+38h+cchCount2], edi; cchCount2
0x180008bc9  mov     r9d, eax; cchCount1
0x180008bcc  mov     ecx, 400h; Locale
0x180008bd1  mov     [rsp+38h+lpString2], rbx; lpString2
0x180008bd6  mov     r8, [r8+38h]; lpString1
0x180008bda  call    cs:__imp_CompareStringW
0x180008be0  mov     ecx, eax
0x180008be2  test    ecx, ecx
0x180008be4  jz      short loc_180008BFE
0x180008be6  sub     ecx, 1
0x180008be9  jz      short loc_180008BF9
0x180008beb  sub     ecx, 1
0x180008bee  jz      short loc_180008C16
0x180008bf0  cmp     ecx, 1
0x180008bf3  jnz     short loc_180008BFE
0x180008bf5  mov     eax, ecx
0x180008bf7  jmp     short loc_180008C18
0x180008bf9  or      eax, 0FFFFFFFFh
0x180008bfc  jmp     short loc_180008C18
0x180008bfe  mov     eax, 0FFFFFFFEh
0x180008c03  jmp     short loc_180008C18
0x180008c05  or      ecx, 0FFFFFFFFh
0x180008c08  mov     eax, 1
0x180008c0d  cmp     [r9+58h], r8d
0x180008c11  cmovl   eax, ecx
0x180008c14  jmp     short loc_180008C18
0x180008c16  xor     eax, eax
0x180008c18  mov     rbx, [rsp+38h+arg_0]
0x180008c1d  mov     rsi, [rsp+38h+arg_8]
0x180008c22  mov     rdi, [rsp+38h+arg_10]
0x180008c27  add     rsp, 30h
0x180008c2b  pop     r14
0x180008c2d  retn
```
