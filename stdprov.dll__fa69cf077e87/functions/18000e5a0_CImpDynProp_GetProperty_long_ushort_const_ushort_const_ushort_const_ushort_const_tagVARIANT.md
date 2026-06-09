# CImpDynProp::GetProperty(long,ushort * const,ushort * const,ushort * const,ushort * const,tagVARIANT *)

- ea: `0x18000e5a0`
- end: `0x18000e748`
- name: `?GetProperty@CImpDynProp@@UEAAJJQEAG000PEAUtagVARIANT@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(CImpDynProp *this, unsigned int, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, unsigned __int16 *const, struct tagVARIANT *pvargDest)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001490`
- `0x180002e90`
- `0x180004260`
- `0x180007ca8`
- `0x1800091e0`
- `0x18000e4c0`
- `0x18000e5a0`
- `0x180017010`

## import_xrefs

- `wbemcomn!IsNT` at `0x18000e5b6`
- `wbemcomn!IsNT` at `0x18000e5b6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000e659`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000e6f4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000e659`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000e6f4`
- `OLEAUT32!__imp_VariantCopy` at `0x18000e6e9`
- `OLEAUT32!__imp_VariantCopy` at `0x18000e6e9`

## pseudocode

```c
__int64 __fastcall CImpDynProp::GetProperty(
        CImpDynProp *this,
        unsigned int a2,
        unsigned __int16 *const a3,
        unsigned __int16 *const a4,
        unsigned __int16 *const a5,
        unsigned __int16 *const a6,
        struct tagVARIANT *pvargDest)
{
  CImpDynProp *v10; // rcx
  __int64 result; // rax
  unsigned __int16 *v12; // rdi
  __int64 v13; // rax
  unsigned int v14; // ebx
  char v15; // al
  unsigned int v16; // ebp
  __int64 v17; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE v18[8]; // [rsp+58h] [rbp-C0h] BYREF
  VARIANTARG pvargSrc; // [rsp+60h] [rbp-B8h] BYREF
  _BYTE v20[152]; // [rsp+80h] [rbp-98h] BYREF

  if ( !IsNT() || (result = WbemCoImpersonateClient(), (int)result >= 0) )
  {
    v12 = CImpDynProp::BuildString(v10, a4, a5, a6);
    pvargDest->llVal = 0;
    if ( !v12 )
      return 2147749894LL;
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    if ( v13 == 3 )
    {
      v14 = -2147217400;
LABEL_11:
      CWin32DefaultArena::WbemMemFree(v12);
      return v14;
    }
    v17 = 0;
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *, int))(**((_QWORD **)this + 12) + 256LL))(
           *((_QWORD *)this + 12),
           0,
           0,
           &v17,
           1) )
    {
      v14 = -2147217402;
      goto LABEL_11;
    }
    CVariant::CVariant((CVariant *)v18);
    v15 = (*(__int64 (__fastcall **)(CImpDynProp *))(*(_QWORD *)this + 48LL))(this);
    CProvObj::CProvObj((CProvObj *)v20, v12, 0x7Cu, v15);
    v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _BYTE *, __int64, _BYTE *, _DWORD))(**((_QWORD **)this + 12) + 240LL))(
            *((_QWORD *)this + 12),
            a2,
            0,
            0,
            v20,
            v17,
            v18,
            0);
    if ( !v16 )
      v16 = VariantCopy(pvargDest, &pvargSrc);
    CWin32DefaultArena::WbemMemFree(v12);
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int))(**((_QWORD **)this + 12) + 264LL))(
      *((_QWORD *)this + 12),
      0,
      0,
      v17,
      1);
    CProvObj::~CProvObj((CProvObj *)v20);
    CVariant::~CVariant((CVariant *)v18);
    return v16;
  }
  return result;
}

```

## disassembly

```asm
0x18000e5a0  push    rbx
0x18000e5a2  push    rbp
0x18000e5a3  push    rsi
0x18000e5a4  push    rdi
0x18000e5a5  push    r14
0x18000e5a7  sub     rsp, 0F0h
0x18000e5ae  mov     rdi, r9
0x18000e5b1  mov     ebp, edx
0x18000e5b3  mov     rbx, rcx
0x18000e5b6  call    cs:__imp_?IsNT@@YAHXZ; IsNT(void)
0x18000e5bc  xor     r14d, r14d
0x18000e5bf  test    eax, eax
0x18000e5c1  jz      short loc_18000E5D0
0x18000e5c3  call    ?WbemCoImpersonateClient@@YAJXZ; WbemCoImpersonateClient(void)
0x18000e5c8  test    eax, eax
0x18000e5ca  js      loc_18000E73A
0x18000e5d0  mov     r9, [rsp+118h+arg_28]; unsigned __int16 *
0x18000e5d8  mov     r8, [rsp+118h+arg_20]; unsigned __int16 *
0x18000e5e0  mov     rdx, rdi; unsigned __int16 *
0x18000e5e3  call    ?BuildString@CImpDynProp@@IEAAPEAGPEAG00@Z; CImpDynProp::BuildString(ushort *,ushort *,ushort *)
0x18000e5e8  mov     rdi, rax
0x18000e5eb  mov     rsi, [rsp+118h+pvargDest]
0x18000e5f3  xor     eax, eax
0x18000e5f5  mov     [rsi+8], rax
0x18000e5f9  test    rdi, rdi
0x18000e5fc  jnz     short loc_18000E608
0x18000e5fe  mov     eax, 80041006h
0x18000e603  jmp     loc_18000E73A
0x18000e608  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e60c  inc     rax
0x18000e60f  cmp     [rdi+rax*2], r14w
0x18000e614  jnz     short loc_18000E60C
0x18000e616  cmp     rax, 3
0x18000e61a  jnz     short loc_18000E623
0x18000e61c  mov     ebx, 80041008h
0x18000e621  jmp     short loc_18000E656
0x18000e623  mov     [rsp+118h+var_C8], r14
0x18000e628  mov     rcx, [rbx+60h]
0x18000e62c  mov     rax, [rcx]
0x18000e62f  mov     dword ptr [rsp+118h+var_F8], 1
0x18000e637  lea     r9, [rsp+118h+var_C8]
0x18000e63c  xor     r8d, r8d
0x18000e63f  xor     edx, edx
0x18000e641  mov     rax, [rax+100h]
0x18000e648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e64d  test    eax, eax
0x18000e64f  jz      short loc_18000E666
0x18000e651  mov     ebx, 80041006h
0x18000e656  mov     rcx, rdi
0x18000e659  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000e65f  mov     eax, ebx
0x18000e661  jmp     loc_18000E73A
0x18000e666  lea     rcx, [rsp+118h+var_C0]; this
0x18000e66b  call    ??0CVariant@@QEAA@XZ; CVariant::CVariant(void)
0x18000e670  nop
0x18000e671  mov     rax, [rbx]
0x18000e674  mov     rcx, rbx
0x18000e677  mov     rax, [rax+30h]
0x18000e67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e680  mov     r9b, al; bool
0x18000e683  mov     r8d, 7Ch ; '|'; unsigned __int16
0x18000e689  mov     rdx, rdi; unsigned __int16 *
0x18000e68c  lea     rcx, [rsp+118h+var_98]; this
0x18000e694  call    ??0CProvObj@@QEAA@PEBGG_N@Z; CProvObj::CProvObj(ushort const *,ushort,bool)
0x18000e699  nop
0x18000e69a  mov     rcx, [rbx+60h]
0x18000e69e  mov     rax, [rcx]
0x18000e6a1  mov     [rsp+118h+var_E0], r14d
0x18000e6a6  lea     rdx, [rsp+118h+var_C0]
0x18000e6ab  mov     [rsp+118h+var_E8], rdx
0x18000e6b0  mov     rdx, [rsp+118h+var_C8]
0x18000e6b5  mov     [rsp+118h+var_F0], rdx
0x18000e6ba  lea     rdx, [rsp+118h+var_98]
0x18000e6c2  mov     [rsp+118h+var_F8], rdx
0x18000e6c7  xor     r9d, r9d
0x18000e6ca  xor     r8d, r8d
0x18000e6cd  mov     edx, ebp
0x18000e6cf  mov     rax, [rax+0F0h]
0x18000e6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6db  mov     ebp, eax
0x18000e6dd  test    eax, eax
0x18000e6df  jnz     short loc_18000E6F1
0x18000e6e1  lea     rdx, [rsp+118h+pvargSrc]; pvargSrc
0x18000e6e6  mov     rcx, rsi; pvargDest
0x18000e6e9  call    cs:__imp_VariantCopy
0x18000e6ef  mov     ebp, eax
0x18000e6f1  mov     rcx, rdi
0x18000e6f4  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000e6fa  mov     rcx, [rbx+60h]
0x18000e6fe  mov     rax, [rcx]
0x18000e701  mov     dword ptr [rsp+118h+var_F8], 1
0x18000e709  mov     r9, [rsp+118h+var_C8]
0x18000e70e  xor     r8d, r8d
0x18000e711  xor     edx, edx
0x18000e713  mov     rax, [rax+108h]
0x18000e71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e71f  nop
0x18000e720  lea     rcx, [rsp+118h+var_98]; this
0x18000e728  call    ??1CProvObj@@UEAA@XZ; CProvObj::~CProvObj(void)
0x18000e72d  nop
0x18000e72e  lea     rcx, [rsp+118h+var_C0]; this
0x18000e733  call    ??1CVariant@@UEAA@XZ; CVariant::~CVariant(void)
0x18000e738  mov     eax, ebp
0x18000e73a  add     rsp, 0F0h
0x18000e741  pop     r14
0x18000e743  pop     rdi
0x18000e744  pop     rsi
0x18000e745  pop     rbp
0x18000e746  pop     rbx
0x18000e747  retn
```
