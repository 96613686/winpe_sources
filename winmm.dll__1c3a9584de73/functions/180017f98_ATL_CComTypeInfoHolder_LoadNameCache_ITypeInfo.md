# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x180017f98`
- end: `0x1800181e0`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `584`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001795c`

## callees

- `0x18000c588`
- `0x18000ce8c`
- `0x180017f98`
- `0x18001b010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180018147`
- `OLEAUT32!__imp_SysFreeString` at `0x180018199`
- `OLEAUT32!__imp_SysFreeString` at `0x180018147`
- `OLEAUT32!__imp_SysFreeString` at `0x180018199`
- `OLEAUT32!__imp_SysStringLen` at `0x18001815a`
- `OLEAUT32!__imp_SysStringLen` at `0x18001815a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(OLECHAR *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rsi
  OLECHAR *v3; // rdi
  unsigned __int64 v4; // rcx
  __int64 v5; // r14
  __int64 v6; // rax
  bool v7; // cf
  unsigned __int64 v8; // rax
  _QWORD *v9; // rax
  int v11; // r14d
  OLECHAR *v12; // r12
  BSTR pbstr; // [rsp+90h] [rbp+8h] BYREF
  struct ITypeInfo *v14; // [rsp+98h] [rbp+10h] BYREF
  __int64 v15; // [rsp+A0h] [rbp+18h] BYREF
  unsigned __int64 v16; // [rsp+A8h] [rbp+20h]

  v14 = a2;
  pbstr = this;
  v2 = a2;
  v15 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v15) >= 0 )
  {
    v3 = 0;
    pbstr = 0;
    v4 = *(unsigned __int16 *)(v15 + 48);
    dword_180025090 = v4;
    qword_180025088 = 0;
    if ( (_WORD)v4 )
    {
      v5 = (unsigned int)v4;
      v16 = v4;
      v6 = 16 * v4;
      if ( !is_mul_ok(v4, 0x10u) )
        v6 = -1;
      v7 = __CFADD__(v6, 8);
      v8 = v6 + 8;
      if ( v7 )
        v8 = -1;
      try
      {
        v9 = operator new[](v8);
        if ( v9 )
        {
          *v9 = v5;
          v3 = (OLECHAR *)(v9 + 1);
          `eh vector constructor iterator'(
            v9 + 1,
            0x10u,
            (unsigned int)v5,
            (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
            (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        }
        else
        {
          v3 = 0;
        }
        pbstr = v3;
      }
      catch ( ... )
      {
        v2 = v14;
        v3 = pbstr;
      }
      if ( !v3 )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v15);
        return 2147942414LL;
      }
      LODWORD(v4) = dword_180025090;
    }
    v11 = 0;
    if ( (int)v4 > 0 )
    {
      do
      {
        v14 = 0;
        *(_QWORD *)&v3[8 * v11 + 4] = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v2->lpVtbl->GetFuncDesc)(
               v2,
               (unsigned int)v11,
               &v14) >= 0 )
        {
          pbstr = 0;
          if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v2->lpVtbl->GetDocumentation)(
                 v2,
                 LODWORD(v14->lpVtbl),
                 &pbstr,
                 0,
                 0,
                 0) >= 0 )
          {
            v12 = pbstr;
            pbstr = 0;
            if ( *(OLECHAR **)&v3[8 * v11] == v12 )
            {
              v12 = *(OLECHAR **)&v3[8 * v11];
            }
            else
            {
              SysFreeString(*(BSTR *)&v3[8 * v11]);
              *(_QWORD *)&v3[8 * v11] = v12;
            }
            *(_DWORD *)&v3[8 * v11 + 4] = SysStringLen(v12);
            *(_DWORD *)&v3[8 * v11 + 6] = v14->lpVtbl;
          }
          ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
          SysFreeString(pbstr);
        }
        ++v11;
      }
      while ( v11 < dword_180025090 );
    }
    qword_180025088 = (__int64)v3;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180017f98  mov     r11, rsp
0x180017f9b  mov     [r11+10h], rdx
0x180017f9f  mov     [r11+8], rcx
0x180017fa3  push    rbx
0x180017fa4  push    rsi
0x180017fa5  push    rdi
0x180017fa6  push    r12
0x180017fa8  push    r14
0x180017faa  push    r15
0x180017fac  sub     rsp, 58h
0x180017fb0  mov     rsi, rdx
0x180017fb3  xor     ebx, ebx
0x180017fb5  mov     [r11+18h], rbx
0x180017fb9  mov     rax, [rdx]
0x180017fbc  lea     rdx, [r11+18h]
0x180017fc0  mov     rcx, rsi
0x180017fc3  mov     rax, [rax+18h]
0x180017fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fcc  test    eax, eax
0x180017fce  js      loc_1800181D0
0x180017fd4  mov     edi, ebx
0x180017fd6  mov     [rsp+88h+pbstr], rbx
0x180017fde  mov     rax, [rsp+88h+arg_10]
0x180017fe6  movzx   ecx, word ptr [rax+30h]
0x180017fea  mov     cs:dword_180025090, ecx
0x180017ff0  mov     cs:qword_180025088, rbx
0x180017ff7  test    cx, cx
0x180017ffa  jz      loc_1800180AF
0x180018000  mov     r14d, ecx
0x180018003  mov     [rsp+88h+arg_18], rcx
0x18001800b  lea     r15d, [rbx+10h]
0x18001800f  mov     eax, r15d
0x180018012  mul     rcx
0x180018015  lea     rcx, [rbx-1]
0x180018019  cmovb   rax, rcx
0x18001801d  add     rax, 8
0x180018021  cmovb   rax, rcx
0x180018025  mov     rcx, rax; unsigned __int64
0x180018028  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001802d  mov     [rsp+88h+var_48], rax
0x180018032  test    rax, rax
0x180018035  jz      short loc_180018061
0x180018037  mov     [rax], r14
0x18001803a  lea     rdi, [rax+8]
0x18001803e  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180018045  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x18001804a  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x180018051  mov     r8d, r14d; unsigned __int64
0x180018054  mov     edx, r15d; unsigned __int64
0x180018057  mov     rcx, rdi; void *
0x18001805a  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18001805f  jmp     short loc_180018064
0x180018061  mov     rdi, rbx
0x180018064  mov     [rsp+88h+pbstr], rdi
0x18001806c  jmp     short loc_180018080
0x18001806e  xor     ebx, ebx
0x180018070  mov     rsi, [rsp+88h+arg_8]
0x180018078  mov     rdi, [rsp+88h+pbstr]
0x180018080  test    rdi, rdi
0x180018083  jnz     short loc_1800180A9
0x180018085  mov     rax, [rsi]
0x180018088  mov     rdx, [rsp+88h+arg_10]
0x180018090  mov     rcx, rsi
0x180018093  mov     rax, [rax+98h]
0x18001809a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001809f  mov     eax, 8007000Eh
0x1800180a4  jmp     loc_1800181D2
0x1800180a9  mov     ecx, cs:dword_180025090
0x1800180af  mov     r14d, ebx
0x1800180b2  test    ecx, ecx
0x1800180b4  jle     loc_1800181AF
0x1800180ba  mov     [rsp+88h+arg_8], rbx
0x1800180c2  movsxd  r15, r14d
0x1800180c5  add     r15, r15
0x1800180c8  mov     qword ptr [rdi+r15*8+8], 0
0x1800180d1  mov     rax, [rsi]
0x1800180d4  lea     r8, [rsp+88h+arg_8]
0x1800180dc  mov     edx, r14d
0x1800180df  mov     rcx, rsi
0x1800180e2  mov     rax, [rax+28h]
0x1800180e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180eb  test    eax, eax
0x1800180ed  js      loc_18001819F
0x1800180f3  mov     [rsp+88h+pbstr], rbx
0x1800180fb  mov     rax, [rsi]
0x1800180fe  mov     [rsp+88h+var_60], rbx
0x180018103  mov     [rsp+88h+var_68], rbx
0x180018108  xor     r9d, r9d
0x18001810b  lea     r8, [rsp+88h+pbstr]
0x180018113  mov     rdx, [rsp+88h+arg_8]
0x18001811b  mov     edx, [rdx]
0x18001811d  mov     rcx, rsi
0x180018120  mov     rax, [rax+60h]
0x180018124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018129  test    eax, eax
0x18001812b  js      short loc_180018176
0x18001812d  mov     r12, [rsp+88h+pbstr]
0x180018135  mov     [rsp+88h+pbstr], rbx
0x18001813d  cmp     [rdi+r15*8], r12
0x180018141  jz      short loc_180018153
0x180018143  mov     rcx, [rdi+r15*8]; bstrString
0x180018147  call    cs:__imp_SysFreeString
0x18001814d  mov     [rdi+r15*8], r12
0x180018151  jmp     short loc_180018157
0x180018153  mov     r12, [rdi+r15*8]
0x180018157  mov     rcx, r12; pbstr
0x18001815a  call    cs:__imp_SysStringLen
0x180018160  mov     [rdi+r15*8+8], eax
0x180018165  mov     rdx, [rsp+88h+arg_8]
0x18001816d  mov     eax, [rdx]
0x18001816f  mov     [rdi+r15*8+0Ch], eax
0x180018174  jmp     short loc_18001817E
0x180018176  mov     rdx, [rsp+88h+arg_8]
0x18001817e  mov     rax, [rsi]
0x180018181  mov     rcx, rsi
0x180018184  mov     rax, [rax+0A0h]
0x18001818b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018190  nop
0x180018191  mov     rcx, [rsp+88h+pbstr]; bstrString
0x180018199  call    cs:__imp_SysFreeString
0x18001819f  inc     r14d
0x1800181a2  cmp     r14d, cs:dword_180025090
0x1800181a9  jl      loc_1800180BA
0x1800181af  mov     cs:qword_180025088, rdi
0x1800181b6  mov     rax, [rsi]
0x1800181b9  mov     rdx, [rsp+88h+arg_10]
0x1800181c1  mov     rcx, rsi
0x1800181c4  mov     rax, [rax+98h]
0x1800181cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181d0  xor     eax, eax
0x1800181d2  add     rsp, 58h
0x1800181d6  pop     r15
0x1800181d8  pop     r14
0x1800181da  pop     r12
0x1800181dc  pop     rdi
0x1800181dd  pop     rsi
0x1800181de  pop     rbx
0x1800181df  retn
```
