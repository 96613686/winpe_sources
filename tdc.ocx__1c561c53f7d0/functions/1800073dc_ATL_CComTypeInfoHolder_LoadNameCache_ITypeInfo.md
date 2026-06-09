# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x1800073dc`
- end: `0x1800075a8`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005e28`

## callees

- `0x1800011ac`
- `0x1800026a4`
- `0x1800073dc`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180007525`
- `OLEAUT32!__imp_SysFreeString` at `0x18000756a`
- `OLEAUT32!__imp_SysFreeString` at `0x180007525`
- `OLEAUT32!__imp_SysFreeString` at `0x18000756a`
- `OLEAUT32!__imp_SysStringLen` at `0x180007538`
- `OLEAUT32!__imp_SysStringLen` at `0x180007538`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfoVtbl *lpVtbl; // rax
  _QWORD *v5; // rdi
  unsigned __int64 v6; // rcx
  __int64 v7; // r14
  __int64 v8; // rax
  bool v9; // cf
  unsigned __int64 v10; // rax
  _QWORD *v11; // rax
  ATL::CComTypeInfoHolder::stringdispid *v12; // r15
  unsigned int i; // r14d
  struct ITypeInfoVtbl *v15; // rax
  OLECHAR *v16; // r12
  UINT v17; // eax
  _DWORD *v18; // rdx
  __int64 v19; // rdx
  unsigned int *v20; // [rsp+88h] [rbp+48h] BYREF
  BSTR pbstr; // [rsp+90h] [rbp+50h] BYREF
  __int64 v22; // [rsp+98h] [rbp+58h] BYREF

  lpVtbl = a2->lpVtbl;
  v22 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))lpVtbl->GetTypeAttr)(a2, &v22) >= 0 )
  {
    v5 = 0;
    v6 = *(unsigned __int16 *)(v22 + 48);
    *((_DWORD *)this + 12) = v6;
    *((_QWORD *)this + 5) = 0;
    if ( (_DWORD)v6 )
    {
      v7 = (unsigned int)v6;
      v8 = 16 * v6;
      if ( !is_mul_ok(v6, 0x10u) )
        v8 = -1;
      v9 = __CFADD__(v8, 8);
      v10 = v8 + 8;
      if ( v9 )
        v10 = -1;
      v11 = operator new[](v10);
      if ( !v11 )
        goto LABEL_11;
      v5 = v11 + 1;
      *v11 = v7;
      v12 = (ATL::CComTypeInfoHolder::stringdispid *)(v11 + 1);
      do
      {
        ATL::CComTypeInfoHolder::stringdispid::stringdispid(v12);
        v12 = (ATL::CComTypeInfoHolder::stringdispid *)((char *)v12 + 16);
        --v7;
      }
      while ( v7 );
      if ( !v5 )
      {
LABEL_11:
        ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v22);
        return 2147942414LL;
      }
    }
    for ( i = 0; (signed int)i < *((_DWORD *)this + 12); ++i )
    {
      v20 = 0;
      v5[2 * (int)i + 1] = 0;
      if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, unsigned int **))a2->lpVtbl->GetFuncDesc)(a2, i, &v20) >= 0 )
      {
        v15 = a2->lpVtbl;
        pbstr = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v15->GetDocumentation)(
               a2,
               *v20,
               &pbstr,
               0,
               0,
               0) < 0 )
        {
          v18 = v20;
        }
        else
        {
          v16 = pbstr;
          pbstr = 0;
          if ( (OLECHAR *)v5[2 * (int)i] == v16 )
          {
            v16 = (OLECHAR *)v5[2 * (int)i];
          }
          else
          {
            SysFreeString((BSTR)v5[2 * (int)i]);
            v5[2 * (int)i] = v16;
          }
          v17 = SysStringLen(v16);
          v18 = v20;
          LODWORD(v5[2 * (int)i + 1]) = v17;
          HIDWORD(v5[2 * (int)i + 1]) = *v18;
        }
        ((void (__fastcall *)(struct ITypeInfo *, _DWORD *))a2->lpVtbl->ReleaseFuncDesc)(a2, v18);
        SysFreeString(pbstr);
      }
    }
    v19 = v22;
    *((_QWORD *)this + 5) = v5;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v19);
  }
  return 0;
}

```

## disassembly

```asm
0x1800073dc  push    rbp
0x1800073de  push    rbx
0x1800073df  push    rsi
0x1800073e0  push    rdi
0x1800073e1  push    r12
0x1800073e3  push    r14
0x1800073e5  push    r15
0x1800073e7  mov     rbp, rsp
0x1800073ea  sub     rsp, 40h
0x1800073ee  mov     rax, [rdx]
0x1800073f1  mov     rbx, rdx
0x1800073f4  mov     rsi, rcx
0x1800073f7  mov     [rbp+arg_18], 0
0x1800073ff  lea     rdx, [rbp+arg_18]
0x180007403  mov     rcx, rbx
0x180007406  mov     rax, [rax+18h]
0x18000740a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000740f  test    eax, eax
0x180007411  js      loc_180007597
0x180007417  mov     rax, [rbp+arg_18]
0x18000741b  xor     edi, edi
0x18000741d  movzx   ecx, word ptr [rax+30h]
0x180007421  mov     [rsi+30h], ecx
0x180007424  mov     [rsi+28h], rdi
0x180007428  test    ecx, ecx
0x18000742a  jz      short loc_180007493
0x18000742c  mov     r14d, ecx
0x18000742f  lea     eax, [rdi+10h]
0x180007432  mul     rcx
0x180007435  lea     rcx, [rdi-1]
0x180007439  cmovb   rax, rcx
0x18000743d  add     rax, 8
0x180007441  cmovb   rax, rcx
0x180007445  mov     rcx, rax; unsigned __int64
0x180007448  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000744d  test    rax, rax
0x180007450  jz      short loc_180007473
0x180007452  lea     rdi, [rax+8]
0x180007456  mov     [rax], r14
0x180007459  mov     r15, rdi
0x18000745c  mov     rcx, r15; this
0x18000745f  call    ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::stringdispid(void)
0x180007464  add     r15, 10h
0x180007468  sub     r14, 1
0x18000746c  jnz     short loc_18000745C
0x18000746e  test    rdi, rdi
0x180007471  jnz     short loc_180007493
0x180007473  mov     rax, [rbx]
0x180007476  mov     rcx, rbx
0x180007479  mov     rdx, [rbp+arg_18]
0x18000747d  mov     rax, [rax+98h]
0x180007484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007489  mov     eax, 8007000Eh
0x18000748e  jmp     loc_180007599
0x180007493  xor     r14d, r14d
0x180007496  cmp     [rsi+30h], r14d
0x18000749a  jle     loc_18000757D
0x1800074a0  movsxd  r15, r14d
0x1800074a3  lea     r8, [rbp+arg_8]
0x1800074a7  add     r15, r15
0x1800074aa  mov     [rbp+arg_8], 0
0x1800074b2  mov     edx, r14d
0x1800074b5  mov     rcx, rbx
0x1800074b8  mov     qword ptr [rdi+r15*8+8], 0
0x1800074c1  mov     rax, [rbx]
0x1800074c4  mov     rax, [rax+28h]
0x1800074c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074cd  test    eax, eax
0x1800074cf  js      loc_180007570
0x1800074d5  mov     rax, [rbx]
0x1800074d8  lea     r8, [rbp+pbstr]
0x1800074dc  mov     rdx, [rbp+arg_8]
0x1800074e0  xor     r9d, r9d
0x1800074e3  mov     [rbp+pbstr], 0
0x1800074eb  mov     rcx, rbx
0x1800074ee  mov     [rsp+40h+var_18], 0
0x1800074f7  mov     rax, [rax+60h]
0x1800074fb  mov     edx, [rdx]
0x1800074fd  mov     [rsp+40h+var_20], 0
0x180007506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000750b  test    eax, eax
0x18000750d  js      short loc_180007550
0x18000750f  mov     r12, [rbp+pbstr]
0x180007513  mov     [rbp+pbstr], 0
0x18000751b  cmp     [rdi+r15*8], r12
0x18000751f  jz      short loc_180007531
0x180007521  mov     rcx, [rdi+r15*8]; bstrString
0x180007525  call    cs:__imp_SysFreeString
0x18000752b  mov     [rdi+r15*8], r12
0x18000752f  jmp     short loc_180007535
0x180007531  mov     r12, [rdi+r15*8]
0x180007535  mov     rcx, r12; pbstr
0x180007538  call    cs:__imp_SysStringLen
0x18000753e  mov     rdx, [rbp+arg_8]
0x180007542  mov     [rdi+r15*8+8], eax
0x180007547  mov     eax, [rdx]
0x180007549  mov     [rdi+r15*8+0Ch], eax
0x18000754e  jmp     short loc_180007554
0x180007550  mov     rdx, [rbp+arg_8]
0x180007554  mov     rax, [rbx]
0x180007557  mov     rcx, rbx
0x18000755a  mov     rax, [rax+0A0h]
0x180007561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007566  mov     rcx, [rbp+pbstr]; bstrString
0x18000756a  call    cs:__imp_SysFreeString
0x180007570  inc     r14d
0x180007573  cmp     r14d, [rsi+30h]
0x180007577  jl      loc_1800074A0
0x18000757d  mov     rdx, [rbp+arg_18]
0x180007581  mov     rcx, rbx
0x180007584  mov     [rsi+28h], rdi
0x180007588  mov     rax, [rbx]
0x18000758b  mov     rax, [rax+98h]
0x180007592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007597  xor     eax, eax
0x180007599  add     rsp, 40h
0x18000759d  pop     r15
0x18000759f  pop     r14
0x1800075a1  pop     r12
0x1800075a3  pop     rdi
0x1800075a4  pop     rsi
0x1800075a5  pop     rbx
0x1800075a6  pop     rbp
0x1800075a7  retn
```
