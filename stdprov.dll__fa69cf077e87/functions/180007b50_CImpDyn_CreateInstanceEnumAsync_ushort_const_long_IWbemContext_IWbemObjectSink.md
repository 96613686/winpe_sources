# CImpDyn::CreateInstanceEnumAsync(ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x180007b50`
- end: `0x180007ca2`
- name: `?CreateInstanceEnumAsync@CImpDyn@@UEAAJQEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(CImpDyn *this, unsigned __int16 *const, unsigned int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007b50`
- `0x180007ca8`
- `0x180017010`

## import_xrefs

- `wbemcomn!IsNT` at `0x180007b8a`
- `wbemcomn!IsNT` at `0x180007b8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CImpDyn::CreateInstanceEnumAsync(
        CImpDyn *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct IWbemObjectSink *a5)
{
  struct IWbemObjectSink *v5; // rbx
  unsigned int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // eax
  __int64 *v14; // rdi
  __int64 v15; // rax
  int v16; // eax
  struct IWbemObjectSinkVtbl *lpVtbl; // r10
  __int64 i; // [rsp+30h] [rbp-38h] BYREF
  __int64 *v19; // [rsp+38h] [rbp-30h] BYREF

  v5 = a5;
  v19 = 0;
  if ( !a5 || !a2 )
    return 2147749896LL;
  if ( IsNT() && (v10 = WbemCoImpersonateClient(), (v11 = v10) != 0)
    || (v12 = (*(__int64 (__fastcall **)(CImpDyn *, unsigned __int16 *const, _QWORD, struct IWbemContext *, __int64 **))(*(_QWORD *)this + 144LL))(
                this,
                a2,
                a3,
                a4,
                &v19),
        (v11 = v12) != 0) )
  {
    ((void (__fastcall *)(struct IWbemObjectSink *, _QWORD, __int64, _QWORD, _QWORD))v5->lpVtbl->SetStatus)(
      v5,
      0,
      v11,
      0,
      0);
  }
  else
  {
    v14 = v19;
    for ( i = 0; ; (*(void (__fastcall **)(__int64))(*(_QWORD *)i + 16LL))(i) )
    {
      v15 = *v14;
      LODWORD(a5) = 0;
      v16 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *, struct IWbemObjectSink **))(v15 + 32))(
              v14,
              0xFFFFFFFFLL,
              1,
              &i,
              &a5);
      lpVtbl = v5->lpVtbl;
      if ( v16 )
        break;
      ((void (__fastcall *)(struct IWbemObjectSink *, __int64, __int64 *))lpVtbl->Indicate)(v5, 1, &i);
    }
    ((void (__fastcall *)(struct IWbemObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))lpVtbl->SetStatus)(v5, 0, 0, 0, 0);
    (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x180007b50  push    rbx
0x180007b52  push    rbp
0x180007b53  push    rsi
0x180007b54  push    rdi
0x180007b55  push    r14
0x180007b57  sub     rsp, 40h
0x180007b5b  mov     rbx, [rsp+68h+arg_20]
0x180007b63  mov     rbp, r9
0x180007b66  mov     [rsp+68h+var_30], 0
0x180007b6f  mov     r14d, r8d
0x180007b72  mov     rdi, rdx
0x180007b75  mov     rsi, rcx
0x180007b78  test    rbx, rbx
0x180007b7b  jz      loc_180007C92
0x180007b81  test    rdx, rdx
0x180007b84  jz      loc_180007C92
0x180007b8a  call    cs:__imp_?IsNT@@YAHXZ; IsNT(void)
0x180007b90  test    eax, eax
0x180007b92  jz      short loc_180007BA0
0x180007b94  call    ?WbemCoImpersonateClient@@YAJXZ; WbemCoImpersonateClient(void)
0x180007b99  mov     r8d, eax
0x180007b9c  test    eax, eax
0x180007b9e  jnz     short loc_180007BCC
0x180007ba0  mov     rax, [rsi]
0x180007ba3  lea     rcx, [rsp+68h+var_30]
0x180007ba8  mov     [rsp+68h+var_48], rcx
0x180007bad  mov     r9, rbp
0x180007bb0  mov     r8d, r14d
0x180007bb3  mov     rdx, rdi
0x180007bb6  mov     rcx, rsi
0x180007bb9  mov     rax, [rax+90h]
0x180007bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bc5  mov     r8d, eax
0x180007bc8  test    eax, eax
0x180007bca  jz      short loc_180007BF0
0x180007bcc  mov     rax, [rbx]
0x180007bcf  xor     r9d, r9d
0x180007bd2  xor     edx, edx
0x180007bd4  mov     [rsp+68h+var_48], 0
0x180007bdd  mov     rcx, rbx
0x180007be0  mov     rax, [rax+20h]
0x180007be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007be9  xor     eax, eax
0x180007beb  jmp     loc_180007C97
0x180007bf0  mov     rdi, [rsp+68h+var_30]
0x180007bf5  mov     esi, 1
0x180007bfa  mov     [rsp+68h+var_38], 0
0x180007c03  mov     rax, [rdi]
0x180007c06  lea     rcx, [rsp+68h+arg_20]
0x180007c0e  mov     [rsp+68h+var_48], rcx
0x180007c13  lea     r9, [rsp+68h+var_38]
0x180007c18  mov     r8d, esi
0x180007c1b  mov     dword ptr [rsp+68h+arg_20], 0
0x180007c26  or      edx, 0FFFFFFFFh
0x180007c29  mov     rcx, rdi
0x180007c2c  mov     rax, [rax+20h]
0x180007c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c35  mov     r10, [rbx]
0x180007c38  mov     rcx, rbx
0x180007c3b  test    eax, eax
0x180007c3d  jnz     short loc_180007C62
0x180007c3f  mov     rax, [r10+18h]
0x180007c43  lea     r8, [rsp+68h+var_38]
0x180007c48  mov     edx, esi
0x180007c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c4f  mov     rcx, [rsp+68h+var_38]
0x180007c54  mov     rax, [rcx]
0x180007c57  mov     rax, [rax+10h]
0x180007c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c60  jmp     short loc_180007C03
0x180007c62  mov     rax, [r10+20h]
0x180007c66  xor     r9d, r9d
0x180007c69  xor     r8d, r8d
0x180007c6c  mov     [rsp+68h+var_48], 0
0x180007c75  xor     edx, edx
0x180007c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c7c  mov     rcx, [rsp+68h+var_30]
0x180007c81  mov     rax, [rcx]
0x180007c84  mov     rax, [rax+10h]
0x180007c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c8d  jmp     loc_180007BE9
0x180007c92  mov     eax, 80041008h
0x180007c97  add     rsp, 40h
0x180007c9b  pop     r14
0x180007c9d  pop     rdi
0x180007c9e  pop     rsi
0x180007c9f  pop     rbp
0x180007ca0  pop     rbx
0x180007ca1  retn
```
