# ConfigureProxySecurityBlanket(IUnknown *)

- ea: `0x18001a448`
- end: `0x18001a64c`
- name: `?ConfigureProxySecurityBlanket@@YAJPEAUIUnknown@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f370`
- `0x18000fda0`
- `0x180011cb8`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001a448`
- `0x180022010`

## string_xrefs

- `0x18001a463`: `ConfigureProxySecurityBlanket`

## pseudocode

```c
__int64 __fastcall ConfigureProxySecurityBlanket(struct IUnknown *a1)
{
  int v2; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  __int16 v4; // ax
  __int64 v5; // rcx
  int v7; // [rsp+50h] [rbp+7h] BYREF
  __int16 v8; // [rsp+54h] [rbp+Bh]
  __int16 v9; // [rsp+56h] [rbp+Dh]
  __int64 v10; // [rsp+B0h] [rbp+67h] BYREF
  __int64 v11; // [rsp+B8h] [rbp+6Fh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v7, "ConfigureProxySecurityBlanket", 32, 1);
  v10 = 0;
  v11 = 0;
  if ( a1 )
  {
    v8 = 36;
    lpVtbl = a1->lpVtbl;
    v7 = 0;
    v2 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(a1, &IID_IUnknown, &v11);
    v7 = v2;
    v4 = 39;
    if ( v2 < 0 )
      goto LABEL_4;
    v8 = 39;
    v2 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v11)(v11, &IID_IClientSecurity, &v10);
    v7 = v2;
    v4 = 40;
    if ( v2 < 0 )
      goto LABEL_4;
    v8 = 40;
    v2 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, __int64))(*(_QWORD *)v10 + 32LL))(v10, a1, 0xFFFFFFFFLL);
    v7 = v2;
    v4 = 41;
    if ( v2 < 0 )
      goto LABEL_4;
    v5 = v10;
    v8 = 41;
    if ( v10 )
    {
      v10 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    v2 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
           a1,
           &IID_IClientSecurity,
           &v10);
    v7 = v2;
    v4 = 45;
    if ( v2 < 0
      || (v8 = 45,
          v2 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, __int64))(*(_QWORD *)v10 + 32LL))(
                 v10,
                 a1,
                 0xFFFFFFFFLL),
          v7 = v2,
          v4 = 46,
          v2 < 0) )
    {
LABEL_4:
      v9 = v4;
    }
    else
    {
      v8 = 46;
    }
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  else
  {
    v2 = -2147024809;
    v9 = 36;
    v7 = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v7);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001a448  mov     [rsp-8+arg_10], rbx
0x18001a44d  push    rbp
0x18001a44e  push    rdi
0x18001a44f  push    r15
0x18001a451  lea     rbp, [rsp-47h]
0x18001a456  sub     rsp, 90h
0x18001a45d  mov     r9d, 1; unsigned __int16
0x18001a463  lea     rdx, aConfigureproxy; "ConfigureProxySecurityBlanket"
0x18001a46a  mov     rdi, rcx
0x18001a46d  lea     rcx, [rbp+57h+var_50]; this
0x18001a471  lea     r8d, [r9+1Fh]; unsigned __int16
0x18001a475  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001a47a  mov     [rbp+57h+arg_0], 0
0x18001a482  mov     eax, 24h ; '$'
0x18001a487  mov     [rbp+57h+arg_8], 0
0x18001a48f  test    rdi, rdi
0x18001a492  jnz     short loc_18001A4A5
0x18001a494  mov     ebx, 80070057h
0x18001a499  mov     [rbp+57h+var_4A], ax
0x18001a49d  mov     [rbp+57h+var_50], ebx
0x18001a4a0  jmp     loc_18001A62D
0x18001a4a5  mov     [rbp+57h+var_4C], ax
0x18001a4a9  lea     r8, [rbp+57h+arg_8]
0x18001a4ad  mov     rax, [rdi]
0x18001a4b0  lea     rdx, IID_IUnknown
0x18001a4b7  mov     rcx, rdi
0x18001a4ba  mov     [rbp+57h+var_50], 0
0x18001a4c1  mov     rax, [rax]
0x18001a4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4c9  mov     ebx, eax
0x18001a4cb  mov     [rbp+57h+var_50], eax
0x18001a4ce  test    eax, eax
0x18001a4d0  mov     eax, 27h ; '''
0x18001a4d5  jns     short loc_18001A4E0
0x18001a4d7  mov     [rbp+57h+var_4A], ax
0x18001a4db  jmp     loc_18001A603
0x18001a4e0  mov     rcx, [rbp+57h+arg_8]
0x18001a4e4  lea     r8, [rbp+57h+arg_0]
0x18001a4e8  mov     [rbp+57h+var_4C], ax
0x18001a4ec  lea     rdx, IID_IClientSecurity
0x18001a4f3  mov     rax, [rcx]
0x18001a4f6  mov     rax, [rax]
0x18001a4f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4fe  mov     ebx, eax
0x18001a500  mov     [rbp+57h+var_50], eax
0x18001a503  test    eax, eax
0x18001a505  mov     eax, 28h ; '('
0x18001a50a  js      short loc_18001A4D7
0x18001a50c  mov     rcx, [rbp+57h+arg_0]
0x18001a510  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001a514  mov     [rsp+0A0h+var_60], 20h ; ' '
0x18001a51c  or      r9d, 0FFFFFFFFh
0x18001a520  mov     [rbp+57h+var_4C], ax
0x18001a524  or      r8d, r9d
0x18001a527  mov     [rsp+0A0h+var_68], r15
0x18001a52c  mov     rdx, rdi
0x18001a52f  mov     rax, [rcx]
0x18001a532  mov     [rsp+0A0h+var_70], 2
0x18001a53a  mov     [rsp+0A0h+var_78], 6
0x18001a542  mov     [rsp+0A0h+var_80], r15
0x18001a547  mov     rax, [rax+20h]
0x18001a54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a550  mov     ebx, eax
0x18001a552  mov     [rbp+57h+var_50], eax
0x18001a555  test    eax, eax
0x18001a557  lea     eax, [r15+2Ah]
0x18001a55b  js      loc_18001A4D7
0x18001a561  mov     rcx, [rbp+57h+arg_0]
0x18001a565  mov     [rbp+57h+var_4C], ax
0x18001a569  test    rcx, rcx
0x18001a56c  jz      short loc_18001A582
0x18001a56e  mov     [rbp+57h+arg_0], 0
0x18001a576  mov     rax, [rcx]
0x18001a579  mov     rax, [rax+10h]
0x18001a57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a582  mov     rax, [rdi]
0x18001a585  lea     r8, [rbp+57h+arg_0]
0x18001a589  lea     rdx, IID_IClientSecurity
0x18001a590  mov     rcx, rdi
0x18001a593  mov     rax, [rax]
0x18001a596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a59b  mov     ebx, eax
0x18001a59d  mov     [rbp+57h+var_50], eax
0x18001a5a0  test    eax, eax
0x18001a5a2  mov     eax, 2Dh ; '-'
0x18001a5a7  js      loc_18001A4D7
0x18001a5ad  mov     rcx, [rbp+57h+arg_0]
0x18001a5b1  or      r9d, 0FFFFFFFFh
0x18001a5b5  mov     [rsp+0A0h+var_60], 20h ; ' '
0x18001a5bd  or      r8d, r9d
0x18001a5c0  mov     [rbp+57h+var_4C], ax
0x18001a5c4  mov     rdx, rdi
0x18001a5c7  mov     [rsp+0A0h+var_68], r15
0x18001a5cc  mov     rax, [rcx]
0x18001a5cf  mov     [rsp+0A0h+var_70], 2
0x18001a5d7  mov     [rsp+0A0h+var_78], 6
0x18001a5df  mov     [rsp+0A0h+var_80], r15
0x18001a5e4  mov     rax, [rax+20h]
0x18001a5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5ed  mov     ebx, eax
0x18001a5ef  mov     [rbp+57h+var_50], eax
0x18001a5f2  test    eax, eax
0x18001a5f4  mov     eax, 2Eh ; '.'
0x18001a5f9  js      loc_18001A4D7
0x18001a5ff  mov     [rbp+57h+var_4C], ax
0x18001a603  mov     rcx, [rbp+57h+arg_8]
0x18001a607  test    rcx, rcx
0x18001a60a  jz      short loc_18001A618
0x18001a60c  mov     rax, [rcx]
0x18001a60f  mov     rax, [rax+10h]
0x18001a613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a618  mov     rcx, [rbp+57h+arg_0]
0x18001a61c  test    rcx, rcx
0x18001a61f  jz      short loc_18001A62D
0x18001a621  mov     rdx, [rcx]
0x18001a624  mov     rax, [rdx+10h]
0x18001a628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a62d  lea     rcx, [rbp+57h+var_50]; this
0x18001a631  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001a636  mov     eax, ebx
0x18001a638  mov     rbx, [rsp+0A0h+arg_10]
0x18001a640  add     rsp, 90h
0x18001a647  pop     r15
0x18001a649  pop     rdi
0x18001a64a  pop     rbp
0x18001a64b  retn
```
