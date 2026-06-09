# CEnumVARIANT::Create(tagSAFEARRAY *,CEnumVARIANT * *)

- ea: `0x18000df6c`
- end: `0x18000e011`
- name: `?Create@CEnumVARIANT@@SAJPEAUtagSAFEARRAY@@PEAPEAV1@@Z`
- size: `165`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, struct CEnumVARIANT **)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180007560`
- `0x18000ba20`
- `0x18000bc60`
- `0x18000df30`

## callees

- `0x1800060e4`
- `0x18000ded8`
- `0x18000df6c`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000dfc1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000dfc1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000dfa9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000dfa9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000dfda`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000dfda`

## pseudocode

```c
__int64 __fastcall CEnumVARIANT::Create(SAFEARRAY *psa, struct CEnumVARIANT **a2)
{
  CEnumVARIANT *v4; // rax
  CEnumVARIANT *v5; // rax
  CEnumVARIANT *v6; // rbx
  HRESULT LBound; // edi

  v4 = (CEnumVARIANT *)operator new(0x20u);
  if ( v4 && (v5 = CEnumVARIANT::CEnumVARIANT(v4), (v6 = v5) != 0) )
  {
    LBound = SafeArrayGetLBound(psa, 1u, (LONG *)v5 + 4);
    if ( LBound < 0
      || (LBound = SafeArrayGetUBound(psa, 1u, (LONG *)v6 + 5), LBound < 0)
      || (*((_DWORD *)v6 + 3) = *((_DWORD *)v6 + 4), LBound = SafeArrayCopy(psa, (SAFEARRAY **)v6 + 3), LBound < 0) )
    {
      (*(void (__fastcall **)(CEnumVARIANT *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    else
    {
      *a2 = v6;
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x18000df6c  push    rbx
0x18000df6e  push    rsi
0x18000df6f  push    rdi
0x18000df70  push    r14
0x18000df72  push    r15
0x18000df74  sub     rsp, 20h
0x18000df78  mov     rsi, rcx
0x18000df7b  mov     r14, rdx
0x18000df7e  mov     ecx, 20h ; ' '; Size
0x18000df83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000df88  test    rax, rax
0x18000df8b  jz      short loc_18000DFFE
0x18000df8d  mov     rcx, rax; this
0x18000df90  call    ??0CEnumVARIANT@@AEAA@XZ; CEnumVARIANT::CEnumVARIANT(void)
0x18000df95  mov     rbx, rax
0x18000df98  test    rax, rax
0x18000df9b  jz      short loc_18000DFFE
0x18000df9d  lea     r8, [rax+10h]; plLbound
0x18000dfa1  mov     edx, 1; nDim
0x18000dfa6  mov     rcx, rsi; psa
0x18000dfa9  call    cs:__imp_SafeArrayGetLBound
0x18000dfaf  mov     edi, eax
0x18000dfb1  test    eax, eax
0x18000dfb3  js      short loc_18000DFED
0x18000dfb5  lea     r8, [rbx+14h]; plUbound
0x18000dfb9  mov     edx, 1; nDim
0x18000dfbe  mov     rcx, rsi; psa
0x18000dfc1  call    cs:__imp_SafeArrayGetUBound
0x18000dfc7  mov     edi, eax
0x18000dfc9  test    eax, eax
0x18000dfcb  js      short loc_18000DFED
0x18000dfcd  mov     eax, [rbx+10h]
0x18000dfd0  lea     rdx, [rbx+18h]; ppsaOut
0x18000dfd4  mov     rcx, rsi; psa
0x18000dfd7  mov     [rbx+0Ch], eax
0x18000dfda  call    cs:__imp_SafeArrayCopy
0x18000dfe0  mov     edi, eax
0x18000dfe2  test    eax, eax
0x18000dfe4  js      short loc_18000DFED
0x18000dfe6  mov     [r14], rbx
0x18000dfe9  xor     edi, edi
0x18000dfeb  jmp     short loc_18000E003
0x18000dfed  mov     rax, [rbx]
0x18000dff0  mov     rcx, rbx
0x18000dff3  mov     rax, [rax+10h]
0x18000dff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dffc  jmp     short loc_18000E003
0x18000dffe  mov     edi, 8007000Eh
0x18000e003  mov     eax, edi
0x18000e005  add     rsp, 20h
0x18000e009  pop     r15
0x18000e00b  pop     r14
0x18000e00d  pop     rdi
0x18000e00e  pop     rsi
0x18000e00f  pop     rbx
0x18000e010  retn
```
