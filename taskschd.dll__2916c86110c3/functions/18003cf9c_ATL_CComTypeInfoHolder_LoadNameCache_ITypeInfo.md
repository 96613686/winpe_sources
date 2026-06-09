# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x18003cf9c`
- end: `0x18003d1f4`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180038c08`

## callees

- `0x180007aa0`
- `0x18002cc10`
- `0x18003b444`
- `0x18003cf9c`
- `0x180054010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003d1ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18003d1ac`
- `OLEAUT32!__imp_SysStringLen` at `0x18003d16f`
- `OLEAUT32!__imp_SysStringLen` at `0x18003d16f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rdi
  OLECHAR *v4; // rsi
  unsigned __int64 v5; // rcx
  _DWORD *v6; // r14
  OLECHAR **v7; // r12
  __int64 v8; // r15
  __int64 v9; // rax
  bool v10; // cf
  unsigned __int64 v11; // rax
  _QWORD *v12; // rax
  unsigned int i; // r15d
  OLECHAR *v15; // r13
  unsigned __int16 *v16; // rdx
  char *v17; // [rsp+40h] [rbp-48h]
  struct ITypeInfo *v18; // [rsp+98h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+20h] BYREF

  v18 = a2;
  v2 = a2;
  v20 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v20) >= 0 )
  {
    v4 = 0;
    bstrString = 0;
    v5 = *(unsigned __int16 *)(v20 + 48);
    v6 = (_DWORD *)((char *)this + 48);
    v17 = (char *)this + 48;
    *((_DWORD *)this + 12) = v5;
    v7 = (OLECHAR **)((char *)this + 40);
    *v7 = 0;
    if ( (_DWORD)v5 )
    {
      v8 = (unsigned int)v5;
      v9 = 16 * v5;
      if ( !is_mul_ok(v5, 0x10u) )
        v9 = -1;
      v10 = __CFADD__(v9, 8);
      v11 = v9 + 8;
      if ( v10 )
        v11 = -1;
      try
      {
        v12 = operator new(v11);
        if ( v12 )
        {
          *v12 = v8;
          v4 = (OLECHAR *)(v12 + 1);
          `eh vector constructor iterator'(
            v12 + 1,
            0x10u,
            (unsigned int)v8,
            (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
            (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        }
        else
        {
          v4 = 0;
        }
        bstrString = v4;
      }
      catch ( ... )
      {
        v2 = v18;
        v4 = bstrString;
        v6 = v17;
      }
      if ( !v4 )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v20);
        return 2147942414LL;
      }
    }
    for ( i = 0; (signed int)i < *v6; ++i )
    {
      v18 = 0;
      v15 = &v4[8 * i];
      *((_QWORD *)v15 + 1) = 0;
      if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v2->lpVtbl->GetFuncDesc)(v2, i, &v18) >= 0 )
      {
        bstrString = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v2->lpVtbl->GetDocumentation)(
               v2,
               LODWORD(v18->lpVtbl),
               &bstrString,
               0,
               0,
               0) >= 0 )
        {
          v16 = bstrString;
          bstrString = 0;
          ATL::CComBSTR::Attach((ATL::CComBSTR *)v15, v16);
          *((_DWORD *)v15 + 2) = SysStringLen(*(BSTR *)v15);
          *((_DWORD *)v15 + 3) = v18->lpVtbl;
        }
        ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
        SysFreeString(bstrString);
      }
    }
    *v7 = v4;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v20);
  }
  return 0;
}

```

## disassembly

```asm
0x18003cf9c  mov     r11, rsp
0x18003cf9f  mov     [r11+8], rsi
0x18003cfa3  mov     [r11+10h], rdx
0x18003cfa7  push    rdi
0x18003cfa8  push    r12
0x18003cfaa  push    r13
0x18003cfac  push    r14
0x18003cfae  push    r15
0x18003cfb0  sub     rsp, 60h
0x18003cfb4  mov     rdi, rdx
0x18003cfb7  mov     r12, rcx
0x18003cfba  mov     qword ptr [r11+20h], 0
0x18003cfc2  mov     rax, [rdx]
0x18003cfc5  lea     rdx, [r11+20h]
0x18003cfc9  mov     rcx, rdi
0x18003cfcc  mov     rax, [rax+18h]
0x18003cfd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cfd5  test    eax, eax
0x18003cfd7  js      loc_18003D1DC
0x18003cfdd  xor     esi, esi
0x18003cfdf  mov     [rsp+88h+bstrString], rsi
0x18003cfe7  mov     rax, [rsp+88h+arg_18]
0x18003cfef  movzx   ecx, word ptr [rax+30h]
0x18003cff3  lea     r14, [r12+30h]
0x18003cff8  mov     [rsp+88h+var_48], r14
0x18003cffd  mov     [r14], ecx
0x18003d000  add     r12, 28h ; '('
0x18003d004  mov     [rsp+88h+var_40], r12
0x18003d009  mov     [r12], rsi
0x18003d00d  test    ecx, ecx
0x18003d00f  jz      loc_18003D0BD
0x18003d015  mov     r15d, ecx
0x18003d018  lea     r13d, [rsi+10h]
0x18003d01c  mov     eax, r13d
0x18003d01f  mul     rcx
0x18003d022  lea     rcx, [rsi-1]
0x18003d026  cmovb   rax, rcx
0x18003d02a  add     rax, 8
0x18003d02e  cmovb   rax, rcx
0x18003d032  mov     rcx, rax; unsigned __int64
0x18003d035  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d03a  mov     [rsp+88h+var_38], rax
0x18003d03f  test    rax, rax
0x18003d042  jz      short loc_18003D06E
0x18003d044  mov     [rax], r15
0x18003d047  lea     rsi, [rax+8]
0x18003d04b  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18003d052  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x18003d057  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x18003d05e  mov     r8d, r15d; unsigned __int64
0x18003d061  mov     edx, r13d; unsigned __int64
0x18003d064  mov     rcx, rsi; void *
0x18003d067  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18003d06c  jmp     short loc_18003D070
0x18003d06e  xor     esi, esi
0x18003d070  mov     [rsp+88h+bstrString], rsi
0x18003d078  jmp     short loc_18003D094
0x18003d07a  mov     rdi, [rsp+88h+arg_8]
0x18003d082  mov     rsi, [rsp+88h+bstrString]
0x18003d08a  mov     r14, [rsp+88h+var_48]
0x18003d08f  mov     r12, [rsp+88h+var_40]
0x18003d094  test    rsi, rsi
0x18003d097  jnz     short loc_18003D0BD
0x18003d099  mov     rax, [rdi]
0x18003d09c  mov     rdx, [rsp+88h+arg_18]
0x18003d0a4  mov     rcx, rdi
0x18003d0a7  mov     rax, [rax+98h]
0x18003d0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0b3  mov     eax, 8007000Eh
0x18003d0b8  jmp     loc_18003D1DE
0x18003d0bd  xor     r15d, r15d
0x18003d0c0  cmp     [r14], r15d
0x18003d0c3  jle     loc_18003D1BE
0x18003d0c9  mov     [rsp+88h+arg_8], 0
0x18003d0d5  movsxd  r13, r15d
0x18003d0d8  shl     r13, 4
0x18003d0dc  add     r13, rsi
0x18003d0df  mov     qword ptr [r13+8], 0
0x18003d0e7  mov     rax, [rdi]
0x18003d0ea  lea     r8, [rsp+88h+arg_8]
0x18003d0f2  mov     edx, r15d
0x18003d0f5  mov     rcx, rdi
0x18003d0f8  mov     rax, [rax+28h]
0x18003d0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d101  test    eax, eax
0x18003d103  js      loc_18003D1B2
0x18003d109  mov     [rsp+88h+bstrString], 0
0x18003d115  mov     rax, [rdi]
0x18003d118  mov     [rsp+88h+var_60], 0
0x18003d121  mov     [rsp+88h+var_68], 0
0x18003d12a  xor     r9d, r9d
0x18003d12d  lea     r8, [rsp+88h+bstrString]
0x18003d135  mov     rdx, [rsp+88h+arg_8]
0x18003d13d  mov     edx, [rdx]
0x18003d13f  mov     rcx, rdi
0x18003d142  mov     rax, [rax+60h]
0x18003d146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d14b  test    eax, eax
0x18003d14d  js      short loc_18003D189
0x18003d14f  mov     rdx, [rsp+88h+bstrString]; unsigned __int16 *
0x18003d157  mov     [rsp+88h+bstrString], 0
0x18003d163  mov     rcx, r13; this
0x18003d166  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x18003d16b  mov     rcx, [r13+0]; pbstr
0x18003d16f  call    cs:__imp_SysStringLen
0x18003d175  mov     [r13+8], eax
0x18003d179  mov     rdx, [rsp+88h+arg_8]
0x18003d181  mov     eax, [rdx]
0x18003d183  mov     [r13+0Ch], eax
0x18003d187  jmp     short loc_18003D191
0x18003d189  mov     rdx, [rsp+88h+arg_8]
0x18003d191  mov     rax, [rdi]
0x18003d194  mov     rcx, rdi
0x18003d197  mov     rax, [rax+0A0h]
0x18003d19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1a3  nop
0x18003d1a4  mov     rcx, [rsp+88h+bstrString]; bstrString
0x18003d1ac  call    cs:__imp_SysFreeString
0x18003d1b2  inc     r15d
0x18003d1b5  cmp     r15d, [r14]
0x18003d1b8  jl      loc_18003D0C9
0x18003d1be  mov     [r12], rsi
0x18003d1c2  mov     rax, [rdi]
0x18003d1c5  mov     rdx, [rsp+88h+arg_18]
0x18003d1cd  mov     rcx, rdi
0x18003d1d0  mov     rax, [rax+98h]
0x18003d1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1dc  xor     eax, eax
0x18003d1de  mov     rsi, [rsp+88h+arg_0]
0x18003d1e6  add     rsp, 60h
0x18003d1ea  pop     r15
0x18003d1ec  pop     r14
0x18003d1ee  pop     r13
0x18003d1f0  pop     r12
0x18003d1f2  pop     rdi
0x18003d1f3  retn
```
