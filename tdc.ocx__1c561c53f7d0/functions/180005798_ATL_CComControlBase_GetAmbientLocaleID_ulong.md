# ATL::CComControlBase::GetAmbientLocaleID(ulong &)

- ea: `0x180005798`
- end: `0x180005846`
- name: `?GetAmbientLocaleID@CComControlBase@ATL@@QEAAJAEAK@Z`
- size: `174`
- prototype: `__int64 __fastcall(ATL::CComControlBase *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004ba0`
- `0x180006c40`

## callees

- `0x180005798`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800057b5`
- `OLEAUT32!__imp_VariantInit` at `0x1800057b5`
- `OLEAUT32!__imp_VariantClear` at `0x180005829`
- `OLEAUT32!__imp_VariantClear` at `0x180005829`

## pseudocode

```c
__int64 __fastcall ATL::CComControlBase::GetAmbientLocaleID(ATL::CComControlBase *this, unsigned int *a2)
{
  __int64 *v4; // rcx
  unsigned int v5; // edi
  __int64 v6; // rax
  __int64 (__fastcall *v7)(__int64 *, __int64, GUID *, __int64, __int16, __int128 *, VARIANTARG *, _QWORD, _QWORD); // rax
  __int16 v9; // [rsp+20h] [rbp-68h]
  __int128 v10; // [rsp+50h] [rbp-38h] BYREF
  __int64 v11; // [rsp+60h] [rbp-28h]
  VARIANTARG pvarg; // [rsp+68h] [rbp-20h] BYREF

  VariantInit(&pvarg);
  v4 = (__int64 *)*((_QWORD *)this + 6);
  v5 = -2147467259;
  if ( v4 )
  {
    v6 = *v4;
    v11 = 0;
    v7 = *(__int64 (__fastcall **)(__int64 *, __int64, GUID *, __int64, __int16, __int128 *, VARIANTARG *, _QWORD, _QWORD))(v6 + 48);
    v10 = 0;
    v9 = 2;
    v5 = v7(v4, 4294966591LL, &GUID_NULL, 1024, v9, &v10, &pvarg, 0, 0);
  }
  *a2 = pvarg.cyVal.Lo;
  VariantClear(&pvarg);
  return v5;
}

```

## disassembly

```asm
0x180005798  mov     [rsp+arg_0], rbx
0x18000579d  mov     [rsp+arg_8], rsi
0x1800057a2  push    rdi
0x1800057a3  sub     rsp, 80h
0x1800057aa  mov     rbx, rcx
0x1800057ad  mov     rsi, rdx
0x1800057b0  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1800057b5  call    cs:__imp_VariantInit
0x1800057bb  mov     rcx, [rbx+30h]
0x1800057bf  xor     edx, edx
0x1800057c1  mov     edi, 80004005h
0x1800057c6  test    rcx, rcx
0x1800057c9  jz      short loc_18000581E
0x1800057cb  mov     rax, [rcx]
0x1800057ce  lea     r8, GUID_NULL
0x1800057d5  mov     [rsp+88h+var_48], rdx
0x1800057da  xorps   xmm0, xmm0
0x1800057dd  mov     [rsp+88h+var_50], rdx
0x1800057e2  mov     r9d, 400h
0x1800057e8  mov     [rsp+88h+var_28], rdx
0x1800057ed  lea     rdx, [rsp+88h+pvarg]
0x1800057f2  mov     rax, [rax+30h]
0x1800057f6  mov     [rsp+88h+var_58], rdx
0x1800057fb  lea     rdx, [rsp+88h+var_38]
0x180005800  mov     [rsp+88h+var_60], rdx
0x180005805  mov     edx, 0FFFFFD3Fh
0x18000580a  movdqu  [rsp+88h+var_38], xmm0
0x180005810  mov     [rsp+88h+var_68], 2
0x180005817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000581c  mov     edi, eax
0x18000581e  mov     ecx, dword ptr [rsp+88h+pvarg+8]
0x180005822  mov     [rsi], ecx
0x180005824  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180005829  call    cs:__imp_VariantClear
0x18000582f  lea     r11, [rsp+88h+var_8]
0x180005837  mov     eax, edi
0x180005839  mov     rbx, [r11+10h]
0x18000583d  mov     rsi, [r11+18h]
0x180005841  mov     rsp, r11
0x180005844  pop     rdi
0x180005845  retn
```
