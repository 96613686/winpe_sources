# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x1800297e0`
- end: `0x180029a45`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180027ef8`

## callees

- `0x180023f88`
- `0x180024e34`
- `0x1800297e0`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800299a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800299f9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800299a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800299f9`
- `OLEAUT32!__imp_SysStringLen` at `0x1800299ba`
- `OLEAUT32!__imp_SysStringLen` at `0x1800299ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rsi
  OLECHAR *v4; // rdi
  unsigned __int64 v5; // rcx
  _DWORD *v6; // r14
  __int64 v7; // r15
  __int64 v8; // rax
  bool v9; // cf
  size_t v10; // rax
  _QWORD *v11; // rax
  unsigned int i; // r15d
  OLECHAR *v14; // r13
  char *v15; // [rsp+40h] [rbp-48h]
  OLECHAR **v16; // [rsp+48h] [rbp-40h]
  struct ITypeInfo *v17; // [rsp+98h] [rbp+10h] BYREF
  BSTR pbstr; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+20h] BYREF

  v17 = a2;
  v2 = a2;
  v19 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v19) >= 0 )
  {
    v4 = 0;
    pbstr = 0;
    v5 = *(unsigned __int16 *)(v19 + 48);
    v6 = (_DWORD *)((char *)this + 48);
    v15 = (char *)this + 48;
    *((_DWORD *)this + 12) = v5;
    v16 = (OLECHAR **)((char *)this + 40);
    *((_QWORD *)this + 5) = 0;
    if ( (_DWORD)v5 )
    {
      v7 = (unsigned int)v5;
      v8 = 16 * v5;
      if ( !is_mul_ok(v5, 0x10u) )
        v8 = -1;
      v9 = __CFADD__(v8, 8);
      v10 = v8 + 8;
      if ( v9 )
        v10 = -1;
      try
      {
        v11 = operator new(v10);
        if ( v11 )
        {
          *v11 = v7;
          v4 = (OLECHAR *)(v11 + 1);
          `eh vector constructor iterator'(
            v11 + 1,
            0x10u,
            (unsigned int)v7,
            (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
            (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        }
        else
        {
          v4 = 0;
        }
        pbstr = v4;
      }
      catch ( ... )
      {
        v2 = v17;
        v4 = pbstr;
        v6 = v15;
      }
      if ( !v4 )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v19);
        return 2147942414LL;
      }
    }
    for ( i = 0; (signed int)i < *v6; ++i )
    {
      v17 = 0;
      *(_QWORD *)&v4[8 * i + 4] = 0;
      if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v2->lpVtbl->GetFuncDesc)(v2, i, &v17) >= 0 )
      {
        pbstr = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v2->lpVtbl->GetDocumentation)(
               v2,
               LODWORD(v17->lpVtbl),
               &pbstr,
               0,
               0,
               0) >= 0 )
        {
          v14 = pbstr;
          pbstr = 0;
          if ( *(OLECHAR **)&v4[8 * i] == v14 )
          {
            v14 = *(OLECHAR **)&v4[8 * i];
          }
          else
          {
            SysFreeString(*(BSTR *)&v4[8 * i]);
            *(_QWORD *)&v4[8 * i] = v14;
          }
          *(_DWORD *)&v4[8 * i + 4] = SysStringLen(v14);
          *(_DWORD *)&v4[8 * i + 6] = v17->lpVtbl;
        }
        ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
        SysFreeString(pbstr);
      }
    }
    *v16 = v4;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v19);
  }
  return 0;
}

```

## disassembly

```asm
0x1800297e0  mov     r11, rsp
0x1800297e3  mov     [r11+8], rsi
0x1800297e7  mov     [r11+10h], rdx
0x1800297eb  push    rdi
0x1800297ec  push    r12
0x1800297ee  push    r13
0x1800297f0  push    r14
0x1800297f2  push    r15
0x1800297f4  sub     rsp, 60h
0x1800297f8  mov     rsi, rdx
0x1800297fb  mov     r15, rcx
0x1800297fe  mov     qword ptr [r11+20h], 0
0x180029806  mov     rax, [rdx]
0x180029809  lea     rdx, [r11+20h]
0x18002980d  mov     rcx, rsi
0x180029810  mov     rax, [rax+18h]
0x180029814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029819  test    eax, eax
0x18002981b  js      loc_180029A2D
0x180029821  xor     edi, edi
0x180029823  mov     [rsp+88h+pbstr], rdi
0x18002982b  mov     rax, [rsp+88h+arg_18]
0x180029833  movzx   ecx, word ptr [rax+30h]
0x180029837  lea     r14, [r15+30h]
0x18002983b  mov     [rsp+88h+var_48], r14
0x180029840  mov     [r14], ecx
0x180029843  lea     rax, [r15+28h]
0x180029847  mov     [rsp+88h+var_40], rax
0x18002984c  mov     [rax], rdi
0x18002984f  test    ecx, ecx
0x180029851  jz      loc_1800298FA
0x180029857  mov     r15d, ecx
0x18002985a  lea     r12d, [rdi+10h]
0x18002985e  mov     eax, r12d
0x180029861  mul     rcx
0x180029864  lea     rcx, [rdi-1]
0x180029868  cmovb   rax, rcx
0x18002986c  add     rax, 8
0x180029870  cmovb   rax, rcx
0x180029874  mov     rcx, rax; Size
0x180029877  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002987c  mov     [rsp+88h+var_38], rax
0x180029881  test    rax, rax
0x180029884  jz      short loc_1800298B0
0x180029886  mov     [rax], r15
0x180029889  lea     rdi, [rax+8]
0x18002988d  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180029894  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x180029899  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x1800298a0  mov     r8d, r15d; unsigned __int64
0x1800298a3  mov     edx, r12d; unsigned __int64
0x1800298a6  mov     rcx, rdi; void *
0x1800298a9  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800298ae  jmp     short loc_1800298B2
0x1800298b0  xor     edi, edi
0x1800298b2  mov     [rsp+88h+pbstr], rdi
0x1800298ba  jmp     short loc_1800298D1
0x1800298bc  mov     rsi, [rsp+88h+arg_8]
0x1800298c4  mov     rdi, [rsp+88h+pbstr]
0x1800298cc  mov     r14, [rsp+88h+var_48]
0x1800298d1  test    rdi, rdi
0x1800298d4  jnz     short loc_1800298FA
0x1800298d6  mov     rax, [rsi]
0x1800298d9  mov     rdx, [rsp+88h+arg_18]
0x1800298e1  mov     rcx, rsi
0x1800298e4  mov     rax, [rax+98h]
0x1800298eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298f0  mov     eax, 8007000Eh
0x1800298f5  jmp     loc_180029A2F
0x1800298fa  xor     r15d, r15d
0x1800298fd  cmp     [r14], r15d
0x180029900  jle     loc_180029A0B
0x180029906  mov     [rsp+88h+arg_8], 0
0x180029912  movsxd  r12, r15d
0x180029915  add     r12, r12
0x180029918  mov     qword ptr [rdi+r12*8+8], 0
0x180029921  mov     rax, [rsi]
0x180029924  lea     r8, [rsp+88h+arg_8]
0x18002992c  mov     edx, r15d
0x18002992f  mov     rcx, rsi
0x180029932  mov     rax, [rax+28h]
0x180029936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002993b  test    eax, eax
0x18002993d  js      loc_1800299FF
0x180029943  mov     [rsp+88h+pbstr], 0
0x18002994f  mov     rax, [rsi]
0x180029952  mov     [rsp+88h+var_60], 0
0x18002995b  mov     [rsp+88h+var_68], 0
0x180029964  xor     r9d, r9d
0x180029967  lea     r8, [rsp+88h+pbstr]
0x18002996f  mov     rdx, [rsp+88h+arg_8]
0x180029977  mov     edx, [rdx]
0x180029979  mov     rcx, rsi
0x18002997c  mov     rax, [rax+60h]
0x180029980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029985  test    eax, eax
0x180029987  js      short loc_1800299D6
0x180029989  mov     r13, [rsp+88h+pbstr]
0x180029991  mov     [rsp+88h+pbstr], 0
0x18002999d  cmp     [rdi+r12*8], r13
0x1800299a1  jz      short loc_1800299B3
0x1800299a3  mov     rcx, [rdi+r12*8]; bstrString
0x1800299a7  call    cs:__imp_SysFreeString
0x1800299ad  mov     [rdi+r12*8], r13
0x1800299b1  jmp     short loc_1800299B7
0x1800299b3  mov     r13, [rdi+r12*8]
0x1800299b7  mov     rcx, r13; pbstr
0x1800299ba  call    cs:__imp_SysStringLen
0x1800299c0  mov     [rdi+r12*8+8], eax
0x1800299c5  mov     rdx, [rsp+88h+arg_8]
0x1800299cd  mov     eax, [rdx]
0x1800299cf  mov     [rdi+r12*8+0Ch], eax
0x1800299d4  jmp     short loc_1800299DE
0x1800299d6  mov     rdx, [rsp+88h+arg_8]
0x1800299de  mov     rax, [rsi]
0x1800299e1  mov     rcx, rsi
0x1800299e4  mov     rax, [rax+0A0h]
0x1800299eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299f0  nop
0x1800299f1  mov     rcx, [rsp+88h+pbstr]; bstrString
0x1800299f9  call    cs:__imp_SysFreeString
0x1800299ff  inc     r15d
0x180029a02  cmp     r15d, [r14]
0x180029a05  jl      loc_180029906
0x180029a0b  mov     rax, [rsp+88h+var_40]
0x180029a10  mov     [rax], rdi
0x180029a13  mov     rax, [rsi]
0x180029a16  mov     rdx, [rsp+88h+arg_18]
0x180029a1e  mov     rcx, rsi
0x180029a21  mov     rax, [rax+98h]
0x180029a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a2d  xor     eax, eax
0x180029a2f  mov     rsi, [rsp+88h+arg_0]
0x180029a37  add     rsp, 60h
0x180029a3b  pop     r15
0x180029a3d  pop     r14
0x180029a3f  pop     r13
0x180029a41  pop     r12
0x180029a43  pop     rdi
0x180029a44  retn
```
