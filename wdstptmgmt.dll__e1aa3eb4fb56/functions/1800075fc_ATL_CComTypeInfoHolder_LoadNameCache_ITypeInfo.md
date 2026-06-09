# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x1800075fc`
- end: `0x180007872`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `630`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007044`

## callees

- `0x1800011b0`
- `0x180002580`
- `0x1800075fc`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800077c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000781d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800077c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000781d`
- `OLEAUT32!__imp_SysStringLen` at `0x1800077db`
- `OLEAUT32!__imp_SysStringLen` at `0x1800077db`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rdi
  ATL::CComTypeInfoHolder *v3; // r15
  ATL::CComTypeInfoHolder *v4; // r13
  OLECHAR *v5; // rsi
  unsigned __int64 v6; // rcx
  int *v7; // r14
  __int64 v8; // r12
  __int64 v9; // rax
  bool v10; // cf
  unsigned __int64 v11; // rax
  _QWORD *v12; // rax
  unsigned int v14; // r12d
  _DWORD *v15; // r14
  BSTR v16; // r13
  OLECHAR *v17; // rcx
  _DWORD *v18; // [rsp+40h] [rbp-58h]
  int *v20; // [rsp+50h] [rbp-48h]
  struct ITypeInfo *v22; // [rsp+A8h] [rbp+10h] BYREF
  BSTR pbstr; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v24; // [rsp+B8h] [rbp+20h] BYREF

  v22 = a2;
  v2 = a2;
  v3 = this;
  v4 = this;
  v24 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v24) >= 0 )
  {
    v5 = 0;
    pbstr = 0;
    v6 = *(unsigned __int16 *)(v24 + 48);
    v7 = (int *)((char *)v4 + 48);
    v20 = (int *)((char *)v4 + 48);
    *((_DWORD *)v4 + 12) = v6;
    *((_QWORD *)v4 + 5) = 0;
    v18 = (_DWORD *)((char *)v4 + 48);
    if ( (_WORD)v6 )
    {
      v8 = (unsigned int)v6;
      v9 = 16 * v6;
      if ( !is_mul_ok(v6, 0x10u) )
        v9 = -1;
      v10 = __CFADD__(v9, 8);
      v11 = v9 + 8;
      if ( v10 )
        v11 = -1;
      try
      {
        v12 = operator new[](v11);
        if ( v12 )
        {
          *v12 = v8;
          v5 = (OLECHAR *)(v12 + 1);
          `eh vector constructor iterator'(
            v12 + 1,
            0x10u,
            (unsigned int)v8,
            (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
            (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        }
        else
        {
          v5 = 0;
        }
        pbstr = v5;
      }
      catch ( ... )
      {
        v3 = this;
        v2 = v22;
        v5 = pbstr;
        v4 = this;
        v7 = v20;
      }
      if ( !v5 )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v24);
        return 2147942414LL;
      }
      v18 = (_DWORD *)((char *)v4 + 48);
    }
    v14 = 0;
    if ( *v7 > 0 )
    {
      v15 = v5 + 6;
      do
      {
        v22 = 0;
        *(_QWORD *)(v15 - 1) = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v2->lpVtbl->GetFuncDesc)(
               v2,
               v14,
               &v22) >= 0 )
        {
          pbstr = 0;
          if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v2->lpVtbl->GetDocumentation)(
                 v2,
                 LODWORD(v22->lpVtbl),
                 &pbstr,
                 0,
                 0,
                 0) >= 0 )
          {
            v16 = pbstr;
            pbstr = 0;
            v17 = *(OLECHAR **)(v15 - 3);
            if ( v17 != v16 )
            {
              SysFreeString(v17);
              *(_QWORD *)(v15 - 3) = v16;
              v17 = v16;
            }
            *(v15 - 1) = SysStringLen(v17);
            *v15 = v22->lpVtbl;
          }
          ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
          SysFreeString(pbstr);
        }
        ++v14;
        v15 += 4;
      }
      while ( (signed int)v14 < *v18 );
      v3 = this;
    }
    *((_QWORD *)v3 + 5) = v5;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v24);
  }
  return 0;
}

```

## disassembly

```asm
0x1800075fc  mov     r11, rsp
0x1800075ff  mov     [r11+10h], rdx
0x180007603  mov     [r11+8], rcx
0x180007607  push    rbx
0x180007608  push    rsi
0x180007609  push    rdi
0x18000760a  push    r12
0x18000760c  push    r13
0x18000760e  push    r14
0x180007610  push    r15
0x180007612  sub     rsp, 60h
0x180007616  mov     rdi, rdx
0x180007619  mov     r15, rcx
0x18000761c  mov     r13, rcx
0x18000761f  mov     [rsp+98h+var_50], rcx
0x180007624  xor     ebx, ebx
0x180007626  mov     [r11+20h], rbx
0x18000762a  mov     rax, [rdx]
0x18000762d  lea     rdx, [r11+20h]
0x180007631  mov     rcx, rdi
0x180007634  mov     rax, [rax+18h]
0x180007638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000763d  test    eax, eax
0x18000763f  js      loc_18000785F
0x180007645  mov     esi, ebx
0x180007647  mov     [rsp+98h+pbstr], rbx
0x18000764f  mov     rax, [rsp+98h+arg_18]
0x180007657  movzx   ecx, word ptr [rax+30h]
0x18000765b  lea     r14, [r13+30h]
0x18000765f  mov     [rsp+98h+var_48], r14
0x180007664  mov     [r14], ecx
0x180007667  mov     [r13+28h], rbx
0x18000766b  mov     [rsp+98h+var_58], r14
0x180007670  test    cx, cx
0x180007673  jz      loc_180007731
0x180007679  mov     r12d, ecx
0x18000767c  lea     eax, [rbx+10h]
0x18000767f  mul     rcx
0x180007682  lea     rcx, [rbx-1]
0x180007686  cmovo   rax, rcx
0x18000768a  add     rax, 8
0x18000768e  cmovb   rax, rcx
0x180007692  mov     rcx, rax; unsigned __int64
0x180007695  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000769a  mov     [rsp+98h+var_58], rax
0x18000769f  test    rax, rax
0x1800076a2  jz      short loc_1800076CE
0x1800076a4  mov     [rax], r12
0x1800076a7  lea     rsi, [rax+8]
0x1800076ab  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x1800076b2  mov     [rsp+98h+var_78], rax; void (*)(void *)
0x1800076b7  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x1800076be  mov     r8d, r12d; unsigned __int64
0x1800076c1  lea     edx, [rbx+10h]; unsigned __int64
0x1800076c4  mov     rcx, rsi; void *
0x1800076c7  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800076cc  jmp     short loc_1800076D1
0x1800076ce  mov     rsi, rbx
0x1800076d1  mov     [rsp+98h+pbstr], rsi
0x1800076d9  jmp     short loc_1800076FF
0x1800076db  xor     ebx, ebx
0x1800076dd  mov     r15, [rsp+98h+arg_0]
0x1800076e5  mov     rdi, [rsp+98h+arg_8]
0x1800076ed  mov     rsi, [rsp+98h+pbstr]
0x1800076f5  mov     r13, [rsp+98h+var_50]
0x1800076fa  mov     r14, [rsp+98h+var_48]
0x1800076ff  test    rsi, rsi
0x180007702  jnz     short loc_180007728
0x180007704  mov     rax, [rdi]
0x180007707  mov     rdx, [rsp+98h+arg_18]
0x18000770f  mov     rcx, rdi
0x180007712  mov     rax, [rax+98h]
0x180007719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000771e  mov     eax, 8007000Eh
0x180007723  jmp     loc_180007861
0x180007728  lea     rax, [r13+30h]
0x18000772c  mov     [rsp+98h+var_58], rax
0x180007731  mov     r12d, ebx
0x180007734  cmp     [r14], ebx
0x180007737  jle     loc_180007841
0x18000773d  lea     r14, [rsi+0Ch]
0x180007741  mov     r15, [rsp+98h+var_58]
0x180007746  mov     [rsp+98h+arg_8], rbx
0x18000774e  and     qword ptr [r14-4], 0
0x180007753  mov     rax, [rdi]
0x180007756  lea     r8, [rsp+98h+arg_8]
0x18000775e  mov     edx, r12d
0x180007761  mov     rcx, rdi
0x180007764  mov     rax, [rax+28h]
0x180007768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000776d  test    eax, eax
0x18000776f  js      loc_180007829
0x180007775  mov     [rsp+98h+pbstr], rbx
0x18000777d  mov     rax, [rdi]
0x180007780  mov     rcx, [rsp+98h+arg_8]
0x180007788  mov     [rsp+98h+var_70], rbx
0x18000778d  mov     [rsp+98h+var_78], rbx
0x180007792  xor     r9d, r9d
0x180007795  lea     r8, [rsp+98h+pbstr]
0x18000779d  mov     edx, [rcx]
0x18000779f  mov     rcx, rdi
0x1800077a2  mov     rax, [rax+60h]
0x1800077a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ab  test    eax, eax
0x1800077ad  js      short loc_1800077FA
0x1800077af  mov     r13, [rsp+98h+pbstr]
0x1800077b7  mov     [rsp+98h+pbstr], rbx
0x1800077bf  mov     rcx, [r14-0Ch]; bstrString
0x1800077c3  cmp     rcx, r13
0x1800077c6  jz      short loc_1800077DB
0x1800077c8  call    cs:__imp_SysFreeString
0x1800077cf  nop     dword ptr [rax+rax+00h]
0x1800077d4  mov     [r14-0Ch], r13
0x1800077d8  mov     rcx, r13; pbstr
0x1800077db  call    cs:__imp_SysStringLen
0x1800077e2  nop     dword ptr [rax+rax+00h]
0x1800077e7  mov     [r14-4], eax
0x1800077eb  mov     rdx, [rsp+98h+arg_8]
0x1800077f3  mov     eax, [rdx]
0x1800077f5  mov     [r14], eax
0x1800077f8  jmp     short loc_180007802
0x1800077fa  mov     rdx, [rsp+98h+arg_8]
0x180007802  mov     rax, [rdi]
0x180007805  mov     rcx, rdi
0x180007808  mov     rax, [rax+0A0h]
0x18000780f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007814  nop
0x180007815  mov     rcx, [rsp+98h+pbstr]; bstrString
0x18000781d  call    cs:__imp_SysFreeString
0x180007824  nop     dword ptr [rax+rax+00h]
0x180007829  inc     r12d
0x18000782c  add     r14, 10h
0x180007830  cmp     r12d, [r15]
0x180007833  jl      loc_180007746
0x180007839  mov     r15, [rsp+98h+arg_0]
0x180007841  mov     [r15+28h], rsi
0x180007845  mov     rax, [rdi]
0x180007848  mov     rdx, [rsp+98h+arg_18]
0x180007850  mov     rcx, rdi
0x180007853  mov     rax, [rax+98h]
0x18000785a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785f  xor     eax, eax
0x180007861  add     rsp, 60h
0x180007865  pop     r15
0x180007867  pop     r14
0x180007869  pop     r13
0x18000786b  pop     r12
0x18000786d  pop     rdi
0x18000786e  pop     rsi
0x18000786f  pop     rbx
0x180007870  retn
```
