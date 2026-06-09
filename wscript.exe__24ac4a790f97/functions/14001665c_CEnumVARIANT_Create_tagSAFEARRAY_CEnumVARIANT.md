# CEnumVARIANT::Create(tagSAFEARRAY *,CEnumVARIANT * *)

- ea: `0x14001665c`
- end: `0x140016718`
- name: `?Create@CEnumVARIANT@@SAJPEAUtagSAFEARRAY@@PEAPEAV1@@Z`
- size: `188`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, struct CEnumVARIANT **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140013b00`
- `0x140013b90`
- `0x140013c20`
- `0x140016620`

## callees

- `0x140001008`
- `0x14001665c`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1400166c8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1400166c8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1400166b0`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1400166b0`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1400166e1`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1400166e1`

## pseudocode

```c
__int64 __fastcall CEnumVARIANT::Create(SAFEARRAY *psa, struct CEnumVARIANT **a2)
{
  void *v4; // rbx
  HRESULT LBound; // edi

  v4 = operator new(0x20u);
  if ( v4 )
  {
    *((_DWORD *)v4 + 2) = 1;
    *(_QWORD *)v4 = &CEnumVARIANT::`vftable';
    *((_DWORD *)v4 + 3) = -1;
    *((_QWORD *)v4 + 3) = 0;
    LBound = SafeArrayGetLBound(psa, 1u, (LONG *)v4 + 4);
    if ( LBound < 0
      || (LBound = SafeArrayGetUBound(psa, 1u, (LONG *)v4 + 5), LBound < 0)
      || (*((_DWORD *)v4 + 3) = *((_DWORD *)v4 + 4), LBound = SafeArrayCopy(psa, (SAFEARRAY **)v4 + 3), LBound < 0) )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
    }
    else
    {
      *a2 = (struct CEnumVARIANT *)v4;
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
0x14001665c  push    rbx
0x14001665e  push    rsi
0x14001665f  push    rdi
0x140016660  push    r14
0x140016662  push    r15
0x140016664  sub     rsp, 20h
0x140016668  mov     rsi, rcx
0x14001666b  mov     r14, rdx
0x14001666e  mov     ecx, 20h ; ' '; Size
0x140016673  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140016678  mov     rbx, rax
0x14001667b  test    rax, rax
0x14001667e  jz      loc_140016705
0x140016684  lea     rax, ??_7CEnumVARIANT@@6B@; const CEnumVARIANT::`vftable'
0x14001668b  mov     dword ptr [rbx+8], 1
0x140016692  lea     r8, [rbx+10h]; plLbound
0x140016696  mov     [rbx], rax
0x140016699  mov     edx, 1; nDim
0x14001669e  mov     dword ptr [rbx+0Ch], 0FFFFFFFFh
0x1400166a5  mov     rcx, rsi; psa
0x1400166a8  mov     qword ptr [rbx+18h], 0
0x1400166b0  call    cs:__imp_SafeArrayGetLBound
0x1400166b6  mov     edi, eax
0x1400166b8  test    eax, eax
0x1400166ba  js      short loc_1400166F4
0x1400166bc  lea     r8, [rbx+14h]; plUbound
0x1400166c0  mov     edx, 1; nDim
0x1400166c5  mov     rcx, rsi; psa
0x1400166c8  call    cs:__imp_SafeArrayGetUBound
0x1400166ce  mov     edi, eax
0x1400166d0  test    eax, eax
0x1400166d2  js      short loc_1400166F4
0x1400166d4  mov     eax, [rbx+10h]
0x1400166d7  lea     rdx, [rbx+18h]; ppsaOut
0x1400166db  mov     rcx, rsi; psa
0x1400166de  mov     [rbx+0Ch], eax
0x1400166e1  call    cs:__imp_SafeArrayCopy
0x1400166e7  mov     edi, eax
0x1400166e9  test    eax, eax
0x1400166eb  js      short loc_1400166F4
0x1400166ed  mov     [r14], rbx
0x1400166f0  xor     edi, edi
0x1400166f2  jmp     short loc_14001670A
0x1400166f4  mov     rax, [rbx]
0x1400166f7  mov     rcx, rbx
0x1400166fa  mov     rax, [rax+10h]
0x1400166fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016703  jmp     short loc_14001670A
0x140016705  mov     edi, 8007000Eh
0x14001670a  mov     eax, edi
0x14001670c  add     rsp, 20h
0x140016710  pop     r15
0x140016712  pop     r14
0x140016714  pop     rdi
0x140016715  pop     rsi
0x140016716  pop     rbx
0x140016717  retn
```
