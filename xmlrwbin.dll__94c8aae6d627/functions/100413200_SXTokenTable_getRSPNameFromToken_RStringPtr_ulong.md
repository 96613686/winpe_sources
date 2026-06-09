# SXTokenTable::getRSPNameFromToken(RStringPtr *,ulong)

- ea: `0x100413200`
- end: `0x10041324a`
- name: `?getRSPNameFromToken@SXTokenTable@@QEAAXPEAVRStringPtr@@K@Z`
- size: `74`
- prototype: `void __fastcall(SXTokenTable *this, struct RStringPtr *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x100410010`

## callees

- `0x100401350`
- `0x100406550`
- `0x100413200`

## pseudocode

```c
void __fastcall SXTokenTable::getRSPNameFromToken(SXTokenTable *this, struct RStringPtr *a2, unsigned int a3)
{
  if ( a3 )
  {
    if ( a3 >= *((_DWORD *)this + 9) )
    {
      MXRRaiseException(-2147467259);
      JUMPOUT(0x100413249LL);
    }
    _mm_lfence();
    RStringPtr::assign(a2, *(struct CStringPtr **)(*((_QWORD *)this + 5) + 8LL * a3));
  }
  else
  {
    RStringPtr::assign(a2, rspNull);
  }
}

```

## disassembly

```asm
0x100413200  sub     rsp, 28h
0x100413204  mov     r9, rdx
0x100413207  test    r8d, r8d
0x10041320a  jnz     short loc_10041321F
0x10041320c  mov     rdx, cs:?rspNull@@3VRStringPtr@@A; struct CStringPtr *
0x100413213  mov     rcx, r9; this
0x100413216  add     rsp, 28h
0x10041321a  jmp     ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10041321f  cmp     r8d, [rcx+24h]
0x100413223  jnb     short loc_10041323F
0x100413225  lfence
0x100413228  mov     rdx, [rcx+28h]
0x10041322c  mov     rcx, r9; this
0x10041322f  mov     eax, r8d
0x100413232  mov     rdx, [rdx+rax*8]; struct CStringPtr *
0x100413236  add     rsp, 28h
0x10041323a  jmp     ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10041323f  mov     ecx, 80004005h; int
0x100413244  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
