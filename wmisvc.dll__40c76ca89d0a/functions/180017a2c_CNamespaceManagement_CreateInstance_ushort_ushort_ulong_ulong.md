# CNamespaceManagement::CreateInstance(ushort *,ushort *,ulong,ulong)

- ea: `0x180017a2c`
- end: `0x180017ca7`
- name: `?CreateInstance@CNamespaceManagement@@QEAAHPEAG0KK@Z`
- size: `635`
- prototype: `__int64 __fastcall(CNamespaceManagement *this, unsigned __int16 *, unsigned __int16 *, LONG, LONG)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800178d8`

## callees

- `0x180001c54`
- `0x180017a2c`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180017a61`
- `OLEAUT32!__imp_VariantInit` at `0x180017b02`
- `OLEAUT32!__imp_VariantInit` at `0x180017b0d`
- `OLEAUT32!__imp_VariantInit` at `0x180017b18`
- `OLEAUT32!__imp_VariantInit` at `0x180017b23`
- `OLEAUT32!__imp_VariantInit` at `0x180017a61`
- `OLEAUT32!__imp_VariantInit` at `0x180017b02`
- `OLEAUT32!__imp_VariantInit` at `0x180017b0d`
- `OLEAUT32!__imp_VariantInit` at `0x180017b18`
- `OLEAUT32!__imp_VariantInit` at `0x180017b23`
- `OLEAUT32!__imp_VariantClear` at `0x180017b46`
- `OLEAUT32!__imp_VariantClear` at `0x180017b5c`
- `OLEAUT32!__imp_VariantClear` at `0x180017c57`
- `OLEAUT32!__imp_VariantClear` at `0x180017c62`
- `OLEAUT32!__imp_VariantClear` at `0x180017c6d`
- `OLEAUT32!__imp_VariantClear` at `0x180017c78`
- `OLEAUT32!__imp_VariantClear` at `0x180017c8f`
- `OLEAUT32!__imp_VariantClear` at `0x180017b46`
- `OLEAUT32!__imp_VariantClear` at `0x180017b5c`
- `OLEAUT32!__imp_VariantClear` at `0x180017c57`
- `OLEAUT32!__imp_VariantClear` at `0x180017c62`
- `OLEAUT32!__imp_VariantClear` at `0x180017c6d`
- `OLEAUT32!__imp_VariantClear` at `0x180017c78`
- `OLEAUT32!__imp_VariantClear` at `0x180017c8f`

## pseudocode

```c
__int64 __fastcall CNamespaceManagement::CreateInstance(
        CNamespaceManagement *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        LONG a4,
        LONG a5)
{
  LONGLONG llVal; // r10
  int v10; // ebx
  int v11; // ebx
  unsigned int v12; // ebx
  __int64 v14; // [rsp+40h] [rbp-61h] BYREF
  VARIANTARG v15; // [rsp+48h] [rbp-59h] BYREF
  VARIANTARG v16; // [rsp+60h] [rbp-41h] BYREF
  VARIANTARG v17; // [rsp+78h] [rbp-29h] BYREF
  VARIANTARG v18; // [rsp+90h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp+7h] BYREF
  __int64 v20; // [rsp+100h] [rbp+5Fh] BYREF

  v20 = 0;
  v14 = 0;
  VariantInit(&pvarg);
  CVARIANT::SetStr(&pvarg, (OLECHAR *)L"WDMClassesOfDriver");
  llVal = 0;
  if ( pvarg.vt == 8 )
    llVal = pvarg.llVal;
  if ( (*(int (__fastcall **)(_QWORD, LONGLONG, _QWORD, _QWORD, __int64 *, _QWORD))(**(_QWORD **)(*(_QWORD *)(*((_QWORD *)this + 8) + 24LL)
                                                                                                + 16LL)
                                                                                  + 48LL))(
         *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 24LL) + 16LL),
         llVal,
         0,
         *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 24LL) + 24LL),
         &v14,
         0) < 0 )
    goto LABEL_14;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 120LL))(v14, 0, &v20);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v14 = 0;
  if ( v10 < 0 )
    goto LABEL_14;
  VariantInit(&v18);
  VariantInit(&v17);
  VariantInit(&v16);
  VariantInit(&v15);
  CVARIANT::SetStr(&v18, a3);
  CVARIANT::SetStr(&v17, a2);
  VariantClear(&v16);
  v16.vt = 3;
  v16.lVal = a4;
  VariantClear(&v15);
  v15.vt = 3;
  v15.lVal = a5;
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v20 + 40LL))(
          v20,
          L"Driver",
          0,
          &v17,
          0);
  if ( !v11 )
  {
    (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v20 + 40LL))(
      v20,
      L"ClassName",
      0,
      &v18,
      0);
    (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v20 + 40LL))(
      v20,
      L"LowDateTime",
      0,
      &v16,
      0);
    v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v20 + 40LL))(
            v20,
            L"HighDateTime",
            0,
            &v15,
            0);
    if ( !v11 )
      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(*((_QWORD *)this + 8) + 24LL)
                                                                                             + 16LL)
                                                                               + 112LL))(
              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 24LL) + 16LL),
              v20,
              0,
              *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 8) + 24LL) + 24LL),
              0);
  }
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v20 = 0;
  VariantClear(&v15);
  VariantClear(&v16);
  VariantClear(&v17);
  VariantClear(&v18);
  if ( v11 )
LABEL_14:
    v12 = 0;
  else
    v12 = 1;
  VariantClear(&pvarg);
  return v12;
}

```

## disassembly

```asm
0x180017a2c  push    rbp
0x180017a2e  push    rbx
0x180017a2f  push    rsi
0x180017a30  push    rdi
0x180017a31  push    r14
0x180017a33  push    r15
0x180017a35  lea     rbp, [rsp-27h]
0x180017a3a  sub     rsp, 0C8h
0x180017a41  mov     esi, r9d
0x180017a44  mov     r14, r8
0x180017a47  mov     r15, rdx
0x180017a4a  mov     rdi, rcx
0x180017a4d  mov     [rbp+4Fh+arg_0], 0
0x180017a55  mov     [rbp+4Fh+var_B0], 0
0x180017a5d  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180017a61  call    cs:__imp_VariantInit
0x180017a67  nop
0x180017a68  lea     rdx, aWdmclassesofdr_0; "WDMClassesOfDriver"
0x180017a6f  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180017a73  call    ?SetStr@CVARIANT@@QEAAXPEAG@Z; CVARIANT::SetStr(ushort *)
0x180017a78  mov     rax, [rdi+40h]
0x180017a7c  mov     rdx, [rax+18h]
0x180017a80  mov     rcx, [rdx+10h]
0x180017a84  mov     rax, [rcx]
0x180017a87  xor     r10d, r10d
0x180017a8a  cmp     word ptr [rbp+4Fh+pvarg], 8
0x180017a8f  cmovz   r10, qword ptr [rbp+4Fh+pvarg+8]
0x180017a94  mov     [rsp+0F0h+var_C8], 0
0x180017a9d  lea     r8, [rbp+4Fh+var_B0]
0x180017aa1  mov     [rsp+0F0h+var_D0], r8
0x180017aa6  mov     r9, [rdx+18h]
0x180017aaa  xor     r8d, r8d
0x180017aad  mov     rdx, r10
0x180017ab0  mov     rax, [rax+30h]
0x180017ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ab9  test    eax, eax
0x180017abb  js      loc_180017C89
0x180017ac1  mov     rcx, [rbp+4Fh+var_B0]
0x180017ac5  mov     rax, [rcx]
0x180017ac8  lea     r8, [rbp+4Fh+arg_0]
0x180017acc  xor     edx, edx
0x180017ace  mov     rax, [rax+78h]
0x180017ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ad7  mov     ebx, eax
0x180017ad9  mov     rcx, [rbp+4Fh+var_B0]
0x180017add  test    rcx, rcx
0x180017ae0  jz      short loc_180017AEE
0x180017ae2  mov     rdx, [rcx]
0x180017ae5  mov     rax, [rdx+10h]
0x180017ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017aee  mov     [rbp+4Fh+var_B0], 0
0x180017af6  test    ebx, ebx
0x180017af8  js      loc_180017C89
0x180017afe  lea     rcx, [rbp+4Fh+var_60]; pvarg
0x180017b02  call    cs:__imp_VariantInit
0x180017b08  nop
0x180017b09  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x180017b0d  call    cs:__imp_VariantInit
0x180017b13  nop
0x180017b14  lea     rcx, [rbp+4Fh+var_90]; pvarg
0x180017b18  call    cs:__imp_VariantInit
0x180017b1e  nop
0x180017b1f  lea     rcx, [rbp+4Fh+var_A8]; pvarg
0x180017b23  call    cs:__imp_VariantInit
0x180017b29  nop
0x180017b2a  mov     rdx, r14; psz
0x180017b2d  lea     rcx, [rbp+4Fh+var_60]; pvarg
0x180017b31  call    ?SetStr@CVARIANT@@QEAAXPEAG@Z; CVARIANT::SetStr(ushort *)
0x180017b36  mov     rdx, r15; psz
0x180017b39  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x180017b3d  call    ?SetStr@CVARIANT@@QEAAXPEAG@Z; CVARIANT::SetStr(ushort *)
0x180017b42  lea     rcx, [rbp+4Fh+var_90]; pvarg
0x180017b46  call    cs:__imp_VariantClear
0x180017b4c  mov     ebx, 3
0x180017b51  mov     word ptr [rbp+4Fh+var_90], bx
0x180017b55  mov     dword ptr [rbp+4Fh+var_90+8], esi
0x180017b58  lea     rcx, [rbp+4Fh+var_A8]; pvarg
0x180017b5c  call    cs:__imp_VariantClear
0x180017b62  mov     word ptr [rbp+4Fh+var_A8], bx
0x180017b66  mov     eax, [rbp+4Fh+arg_20]
0x180017b69  mov     dword ptr [rbp+4Fh+var_A8+8], eax
0x180017b6c  mov     rcx, [rbp+4Fh+arg_0]
0x180017b70  mov     rax, [rcx]
0x180017b73  mov     dword ptr [rsp+0F0h+var_D0], 0
0x180017b7b  lea     r9, [rbp+4Fh+var_78]
0x180017b7f  xor     r8d, r8d
0x180017b82  lea     rdx, aDriver; "Driver"
0x180017b89  mov     rax, [rax+28h]
0x180017b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b92  mov     ebx, eax
0x180017b94  test    eax, eax
0x180017b96  jnz     loc_180017C36
0x180017b9c  mov     rcx, [rbp+4Fh+arg_0]
0x180017ba0  mov     rax, [rcx]
0x180017ba3  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180017ba7  lea     r9, [rbp+4Fh+var_60]
0x180017bab  xor     r8d, r8d
0x180017bae  lea     rdx, aClassname; "ClassName"
0x180017bb5  mov     rax, [rax+28h]
0x180017bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bbe  mov     rcx, [rbp+4Fh+arg_0]
0x180017bc2  mov     rax, [rcx]
0x180017bc5  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180017bc9  lea     r9, [rbp+4Fh+var_90]
0x180017bcd  xor     r8d, r8d
0x180017bd0  lea     rdx, aLowdatetime; "LowDateTime"
0x180017bd7  mov     rax, [rax+28h]
0x180017bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017be0  mov     rcx, [rbp+4Fh+arg_0]
0x180017be4  mov     rax, [rcx]
0x180017be7  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180017beb  lea     r9, [rbp+4Fh+var_A8]
0x180017bef  xor     r8d, r8d
0x180017bf2  lea     rdx, aHighdatetime; "HighDateTime"
0x180017bf9  mov     rax, [rax+28h]
0x180017bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c02  mov     ebx, eax
0x180017c04  test    eax, eax
0x180017c06  jnz     short loc_180017C36
0x180017c08  mov     rax, [rdi+40h]
0x180017c0c  mov     r9, [rax+18h]
0x180017c10  mov     rcx, [r9+10h]
0x180017c14  mov     rax, [rcx]
0x180017c17  mov     [rsp+0F0h+var_D0], 0
0x180017c20  mov     r9, [r9+18h]
0x180017c24  xor     r8d, r8d
0x180017c27  mov     rdx, [rbp+4Fh+arg_0]
0x180017c2b  mov     rax, [rax+70h]
0x180017c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c34  mov     ebx, eax
0x180017c36  mov     rcx, [rbp+4Fh+arg_0]
0x180017c3a  test    rcx, rcx
0x180017c3d  jz      short loc_180017C4B
0x180017c3f  mov     rax, [rcx]
0x180017c42  mov     rax, [rax+10h]
0x180017c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c4b  mov     [rbp+4Fh+arg_0], 0
0x180017c53  lea     rcx, [rbp+4Fh+var_A8]; pvarg
0x180017c57  call    cs:__imp_VariantClear
0x180017c5d  nop
0x180017c5e  lea     rcx, [rbp+4Fh+var_90]; pvarg
0x180017c62  call    cs:__imp_VariantClear
0x180017c68  nop
0x180017c69  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x180017c6d  call    cs:__imp_VariantClear
0x180017c73  nop
0x180017c74  lea     rcx, [rbp+4Fh+var_60]; pvarg
0x180017c78  call    cs:__imp_VariantClear
0x180017c7e  test    ebx, ebx
0x180017c80  jnz     short loc_180017C89
0x180017c82  mov     ebx, 1
0x180017c87  jmp     short loc_180017C8B
0x180017c89  xor     ebx, ebx
0x180017c8b  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180017c8f  call    cs:__imp_VariantClear
0x180017c95  mov     eax, ebx
0x180017c97  add     rsp, 0C8h
0x180017c9e  pop     r15
0x180017ca0  pop     r14
0x180017ca2  pop     rdi
0x180017ca3  pop     rsi
0x180017ca4  pop     rbx
0x180017ca5  pop     rbp
0x180017ca6  retn
```
