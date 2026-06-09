# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x18001907c`
- end: `0x1800192e9`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `621`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800189a0`

## callees

- `0x180013370`
- `0x180013dd8`
- `0x18001907c`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001924b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001929d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001924b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001929d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001925e`
- `OLEAUT32!__imp_SysStringLen` at `0x18001925e`

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
        v11 = operator new[](v10);
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
0x18001907c  mov     r11, rsp
0x18001907f  mov     [r11+10h], rdx
0x180019083  push    rdi
0x180019084  push    r12
0x180019086  push    r13
0x180019088  push    r14
0x18001908a  push    r15
0x18001908c  sub     rsp, 60h
0x180019090  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x180019098  mov     [r11+8], rsi
0x18001909c  mov     rsi, rdx
0x18001909f  mov     r15, rcx
0x1800190a2  mov     qword ptr [r11+20h], 0
0x1800190aa  mov     rax, [rdx]
0x1800190ad  lea     rdx, [r11+20h]
0x1800190b1  mov     rcx, rsi
0x1800190b4  mov     rax, [rax+18h]
0x1800190b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190bd  test    eax, eax
0x1800190bf  js      loc_1800192D1
0x1800190c5  xor     edi, edi
0x1800190c7  mov     [rsp+88h+pbstr], rdi
0x1800190cf  mov     rax, [rsp+88h+arg_18]
0x1800190d7  movzx   ecx, word ptr [rax+30h]
0x1800190db  lea     r14, [r15+30h]
0x1800190df  mov     [rsp+88h+var_48], r14
0x1800190e4  mov     [r14], ecx
0x1800190e7  lea     rax, [r15+28h]
0x1800190eb  mov     [rsp+88h+var_40], rax
0x1800190f0  mov     [rax], rdi
0x1800190f3  test    ecx, ecx
0x1800190f5  jz      loc_18001919E
0x1800190fb  mov     r15d, ecx
0x1800190fe  lea     r12d, [rdi+10h]
0x180019102  mov     eax, r12d
0x180019105  mul     rcx
0x180019108  lea     rcx, [rdi-1]
0x18001910c  cmovb   rax, rcx
0x180019110  add     rax, 8
0x180019114  cmovb   rax, rcx
0x180019118  mov     rcx, rax; unsigned __int64
0x18001911b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019120  mov     [rsp+88h+var_30], rax
0x180019125  test    rax, rax
0x180019128  jz      short loc_180019154
0x18001912a  mov     [rax], r15
0x18001912d  lea     rdi, [rax+8]
0x180019131  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180019138  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x18001913d  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x180019144  mov     r8d, r15d; unsigned __int64
0x180019147  mov     edx, r12d; unsigned __int64
0x18001914a  mov     rcx, rdi; void *
0x18001914d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180019152  jmp     short loc_180019156
0x180019154  xor     edi, edi
0x180019156  mov     [rsp+88h+pbstr], rdi
0x18001915e  jmp     short loc_180019175
0x180019160  mov     rsi, [rsp+88h+arg_8]
0x180019168  mov     rdi, [rsp+88h+pbstr]
0x180019170  mov     r14, [rsp+88h+var_48]
0x180019175  test    rdi, rdi
0x180019178  jnz     short loc_18001919E
0x18001917a  mov     rax, [rsi]
0x18001917d  mov     rdx, [rsp+88h+arg_18]
0x180019185  mov     rcx, rsi
0x180019188  mov     rax, [rax+98h]
0x18001918f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019194  mov     eax, 8007000Eh
0x180019199  jmp     loc_1800192D3
0x18001919e  xor     r15d, r15d
0x1800191a1  cmp     [r14], r15d
0x1800191a4  jle     loc_1800192AF
0x1800191aa  mov     [rsp+88h+arg_8], 0
0x1800191b6  movsxd  r12, r15d
0x1800191b9  add     r12, r12
0x1800191bc  mov     qword ptr [rdi+r12*8+8], 0
0x1800191c5  mov     rax, [rsi]
0x1800191c8  lea     r8, [rsp+88h+arg_8]
0x1800191d0  mov     edx, r15d
0x1800191d3  mov     rcx, rsi
0x1800191d6  mov     rax, [rax+28h]
0x1800191da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191df  test    eax, eax
0x1800191e1  js      loc_1800192A3
0x1800191e7  mov     [rsp+88h+pbstr], 0
0x1800191f3  mov     rax, [rsi]
0x1800191f6  mov     [rsp+88h+var_60], 0
0x1800191ff  mov     [rsp+88h+var_68], 0
0x180019208  xor     r9d, r9d
0x18001920b  lea     r8, [rsp+88h+pbstr]
0x180019213  mov     rdx, [rsp+88h+arg_8]
0x18001921b  mov     edx, [rdx]
0x18001921d  mov     rcx, rsi
0x180019220  mov     rax, [rax+60h]
0x180019224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019229  test    eax, eax
0x18001922b  js      short loc_18001927A
0x18001922d  mov     r13, [rsp+88h+pbstr]
0x180019235  mov     [rsp+88h+pbstr], 0
0x180019241  cmp     [rdi+r12*8], r13
0x180019245  jz      short loc_180019257
0x180019247  mov     rcx, [rdi+r12*8]; bstrString
0x18001924b  call    cs:__imp_SysFreeString
0x180019251  mov     [rdi+r12*8], r13
0x180019255  jmp     short loc_18001925B
0x180019257  mov     r13, [rdi+r12*8]
0x18001925b  mov     rcx, r13; pbstr
0x18001925e  call    cs:__imp_SysStringLen
0x180019264  mov     [rdi+r12*8+8], eax
0x180019269  mov     rdx, [rsp+88h+arg_8]
0x180019271  mov     eax, [rdx]
0x180019273  mov     [rdi+r12*8+0Ch], eax
0x180019278  jmp     short loc_180019282
0x18001927a  mov     rdx, [rsp+88h+arg_8]
0x180019282  mov     rax, [rsi]
0x180019285  mov     rcx, rsi
0x180019288  mov     rax, [rax+0A0h]
0x18001928f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019294  nop
0x180019295  mov     rcx, [rsp+88h+pbstr]; bstrString
0x18001929d  call    cs:__imp_SysFreeString
0x1800192a3  inc     r15d
0x1800192a6  cmp     r15d, [r14]
0x1800192a9  jl      loc_1800191AA
0x1800192af  mov     rax, [rsp+88h+var_40]
0x1800192b4  mov     [rax], rdi
0x1800192b7  mov     rax, [rsi]
0x1800192ba  mov     rdx, [rsp+88h+arg_18]
0x1800192c2  mov     rcx, rsi
0x1800192c5  mov     rax, [rax+98h]
0x1800192cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192d1  xor     eax, eax
0x1800192d3  mov     rsi, [rsp+88h+arg_0]
0x1800192db  add     rsp, 60h
0x1800192df  pop     r15
0x1800192e1  pop     r14
0x1800192e3  pop     r13
0x1800192e5  pop     r12
0x1800192e7  pop     rdi
0x1800192e8  retn
```
