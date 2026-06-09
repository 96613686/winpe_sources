# CSWbemNamedValueSet::SetValueIntoContext(ushort *,tagVARIANT *,ulong)

- ea: `0x180023e20`
- end: `0x180023f1d`
- name: `?SetValueIntoContext@CSWbemNamedValueSet@@AEAAJPEAGPEAUtagVARIANT@@K@Z`
- size: `253`
- prototype: `int(CSWbemNamedValueSet *__hidden this, unsigned __int16 *, struct tagVARIANT *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180023320`

## callees

- `0x180023e20`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180023e67`
- `OLEAUT32!__imp_VariantInit` at `0x180023e67`
- `OLEAUT32!__imp_VariantClear` at `0x180023ed7`
- `OLEAUT32!__imp_VariantClear` at `0x180023ed7`
- `OLEAUT32!__imp_VariantChangeType` at `0x180023ea9`
- `OLEAUT32!__imp_VariantChangeType` at `0x180023ea9`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180023e96`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180023e96`

## pseudocode

```c
__int64 __fastcall CSWbemNamedValueSet::SetValueIntoContext(
        CSWbemNamedValueSet *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  __int64 v5; // rcx
  unsigned int v7; // ebx
  SAFEARRAY **pparray; // rcx
  HRESULT v9; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF

  v5 = *((_QWORD *)this + 6);
  v7 = -2147217407;
  if ( v5 )
  {
    if ( (a3->vt & 0x4000) != 0 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      if ( (a3->vt & 0x2000) != 0 )
      {
        pparray = a3->pparray;
        pvarg.vt = a3->vt & 0xBFFF;
        v9 = SafeArrayCopy(*pparray, &pvarg.parray);
      }
      else
      {
        v9 = VariantChangeType(&pvarg, a3, 0, a3->vt & 0xBFFF);
      }
      v7 = v9;
      if ( v9 >= 0 )
        v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, VARIANTARG *))(**((_QWORD **)this + 6) + 64LL))(
               *((_QWORD *)this + 6),
               a2,
               0,
               &pvarg);
      VariantClear(&pvarg);
    }
    else
    {
      if ( a3->vt == 10 && a3->lVal == -2147352572 )
      {
        a3->vt = 1;
        v5 = *((_QWORD *)this + 6);
      }
      return (*(unsigned int (__fastcall **)(__int64, unsigned __int16 *, _QWORD, struct tagVARIANT *))(*(_QWORD *)v5 + 64LL))(
               v5,
               a2,
               0,
               a3);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180023e20  push    rbx
0x180023e22  push    rbp
0x180023e23  push    rsi
0x180023e24  push    rdi
0x180023e25  sub     rsp, 58h
0x180023e29  mov     rsi, rcx
0x180023e2c  mov     rdi, r8
0x180023e2f  mov     rcx, [rcx+30h]
0x180023e33  mov     rbp, rdx
0x180023e36  mov     ebx, 80041001h
0x180023e3b  test    rcx, rcx
0x180023e3e  jz      loc_180023F12
0x180023e44  mov     eax, 4000h
0x180023e49  test    [r8], ax
0x180023e4d  jz      loc_180023EDF
0x180023e53  xorps   xmm0, xmm0
0x180023e56  lea     rcx, [rsp+78h+pvarg]; pvarg
0x180023e5b  xor     eax, eax
0x180023e5d  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x180023e62  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x180023e67  call    cs:__imp_VariantInit
0x180023e6d  movzx   r9d, word ptr [rdi]
0x180023e71  mov     eax, 0BFFFh
0x180023e76  and     r9w, ax; vt
0x180023e7a  mov     eax, 2000h
0x180023e7f  test    [rdi], ax
0x180023e82  jz      short loc_180023E9E
0x180023e84  mov     rcx, [rdi+8]
0x180023e88  lea     rdx, [rsp+78h+pvarg+8]; ppsaOut
0x180023e8d  mov     word ptr [rsp+78h+pvarg], r9w
0x180023e93  mov     rcx, [rcx]; psa
0x180023e96  call    cs:__imp_SafeArrayCopy
0x180023e9c  jmp     short loc_180023EAF
0x180023e9e  xor     r8d, r8d; wFlags
0x180023ea1  lea     rcx, [rsp+78h+pvarg]; pvargDest
0x180023ea6  mov     rdx, rdi; pvarSrc
0x180023ea9  call    cs:__imp_VariantChangeType
0x180023eaf  mov     ebx, eax
0x180023eb1  test    eax, eax
0x180023eb3  js      short loc_180023ED2
0x180023eb5  mov     rcx, [rsi+30h]
0x180023eb9  lea     r9, [rsp+78h+pvarg]
0x180023ebe  xor     r8d, r8d
0x180023ec1  mov     rdx, rbp
0x180023ec4  mov     rax, [rcx]
0x180023ec7  mov     rax, [rax+40h]
0x180023ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ed0  mov     ebx, eax
0x180023ed2  lea     rcx, [rsp+78h+pvarg]; pvarg
0x180023ed7  call    cs:__imp_VariantClear
0x180023edd  jmp     short loc_180023F12
0x180023edf  mov     eax, 0Ah
0x180023ee4  cmp     ax, [r8]
0x180023ee8  jnz     short loc_180023EFE
0x180023eea  cmp     dword ptr [r8+8], 80020004h
0x180023ef2  jnz     short loc_180023EFE
0x180023ef4  mov     word ptr [r8], 1
0x180023efa  mov     rcx, [rsi+30h]
0x180023efe  mov     rax, [rcx]
0x180023f01  mov     r9, rdi
0x180023f04  xor     r8d, r8d
0x180023f07  mov     rax, [rax+40h]
0x180023f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f10  mov     ebx, eax
0x180023f12  mov     eax, ebx
0x180023f14  add     rsp, 58h
0x180023f18  pop     rdi
0x180023f19  pop     rsi
0x180023f1a  pop     rbp
0x180023f1b  pop     rbx
0x180023f1c  retn
```
