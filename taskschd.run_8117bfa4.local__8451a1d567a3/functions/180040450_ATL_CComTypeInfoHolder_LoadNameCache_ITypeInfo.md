# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x180040450`
- end: `0x1800406b5`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003bcdc`

## callees

- `0x180007e90`
- `0x18002eee0`
- `0x18003e7b4`
- `0x180040450`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180040666`
- `OLEAUT32!__imp_SysFreeString` at `0x180040666`
- `OLEAUT32!__imp_SysStringLen` at `0x180040623`
- `OLEAUT32!__imp_SysStringLen` at `0x180040623`

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
0x180040450  mov     r11, rsp
0x180040453  mov     [r11+8], rsi
0x180040457  mov     [r11+10h], rdx
0x18004045b  push    rdi
0x18004045c  push    r12
0x18004045e  push    r13
0x180040460  push    r14
0x180040462  push    r15
0x180040464  sub     rsp, 60h
0x180040468  mov     rdi, rdx
0x18004046b  mov     r12, rcx
0x18004046e  mov     qword ptr [r11+20h], 0
0x180040476  mov     rax, [rdx]
0x180040479  lea     rdx, [r11+20h]
0x18004047d  mov     rcx, rdi
0x180040480  mov     rax, [rax+18h]
0x180040484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040489  test    eax, eax
0x18004048b  js      loc_18004069C
0x180040491  xor     esi, esi
0x180040493  mov     [rsp+88h+bstrString], rsi
0x18004049b  mov     rax, [rsp+88h+arg_18]
0x1800404a3  movzx   ecx, word ptr [rax+30h]
0x1800404a7  lea     r14, [r12+30h]
0x1800404ac  mov     [rsp+88h+var_48], r14
0x1800404b1  mov     [r14], ecx
0x1800404b4  add     r12, 28h ; '('
0x1800404b8  mov     [rsp+88h+var_40], r12
0x1800404bd  mov     [r12], rsi
0x1800404c1  test    ecx, ecx
0x1800404c3  jz      loc_180040571
0x1800404c9  mov     r15d, ecx
0x1800404cc  lea     r13d, [rsi+10h]
0x1800404d0  mov     eax, r13d
0x1800404d3  mul     rcx
0x1800404d6  lea     rcx, [rsi-1]
0x1800404da  cmovb   rax, rcx
0x1800404de  add     rax, 8
0x1800404e2  cmovb   rax, rcx
0x1800404e6  mov     rcx, rax; unsigned __int64
0x1800404e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800404ee  mov     [rsp+88h+var_38], rax
0x1800404f3  test    rax, rax
0x1800404f6  jz      short loc_180040522
0x1800404f8  mov     [rax], r15
0x1800404fb  lea     rsi, [rax+8]
0x1800404ff  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180040506  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x18004050b  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x180040512  mov     r8d, r15d; unsigned __int64
0x180040515  mov     edx, r13d; unsigned __int64
0x180040518  mov     rcx, rsi; void *
0x18004051b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180040520  jmp     short loc_180040524
0x180040522  xor     esi, esi
0x180040524  mov     [rsp+88h+bstrString], rsi
0x18004052c  jmp     short loc_180040548
0x18004052e  mov     rdi, [rsp+88h+arg_8]
0x180040536  mov     rsi, [rsp+88h+bstrString]
0x18004053e  mov     r14, [rsp+88h+var_48]
0x180040543  mov     r12, [rsp+88h+var_40]
0x180040548  test    rsi, rsi
0x18004054b  jnz     short loc_180040571
0x18004054d  mov     rax, [rdi]
0x180040550  mov     rdx, [rsp+88h+arg_18]
0x180040558  mov     rcx, rdi
0x18004055b  mov     rax, [rax+98h]
0x180040562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040567  mov     eax, 8007000Eh
0x18004056c  jmp     loc_18004069E
0x180040571  xor     r15d, r15d
0x180040574  cmp     [r14], r15d
0x180040577  jle     loc_18004067E
0x18004057d  mov     [rsp+88h+arg_8], 0
0x180040589  movsxd  r13, r15d
0x18004058c  shl     r13, 4
0x180040590  add     r13, rsi
0x180040593  mov     qword ptr [r13+8], 0
0x18004059b  mov     rax, [rdi]
0x18004059e  lea     r8, [rsp+88h+arg_8]
0x1800405a6  mov     edx, r15d
0x1800405a9  mov     rcx, rdi
0x1800405ac  mov     rax, [rax+28h]
0x1800405b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405b5  test    eax, eax
0x1800405b7  js      loc_180040672
0x1800405bd  mov     [rsp+88h+bstrString], 0
0x1800405c9  mov     rax, [rdi]
0x1800405cc  mov     [rsp+88h+var_60], 0
0x1800405d5  mov     [rsp+88h+var_68], 0
0x1800405de  xor     r9d, r9d
0x1800405e1  lea     r8, [rsp+88h+bstrString]
0x1800405e9  mov     rdx, [rsp+88h+arg_8]
0x1800405f1  mov     edx, [rdx]
0x1800405f3  mov     rcx, rdi
0x1800405f6  mov     rax, [rax+60h]
0x1800405fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405ff  test    eax, eax
0x180040601  js      short loc_180040643
0x180040603  mov     rdx, [rsp+88h+bstrString]; unsigned __int16 *
0x18004060b  mov     [rsp+88h+bstrString], 0
0x180040617  mov     rcx, r13; this
0x18004061a  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x18004061f  mov     rcx, [r13+0]; pbstr
0x180040623  call    cs:__imp_SysStringLen
0x18004062a  nop     dword ptr [rax+rax+00h]
0x18004062f  mov     [r13+8], eax
0x180040633  mov     rdx, [rsp+88h+arg_8]
0x18004063b  mov     eax, [rdx]
0x18004063d  mov     [r13+0Ch], eax
0x180040641  jmp     short loc_18004064B
0x180040643  mov     rdx, [rsp+88h+arg_8]
0x18004064b  mov     rax, [rdi]
0x18004064e  mov     rcx, rdi
0x180040651  mov     rax, [rax+0A0h]
0x180040658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004065d  nop
0x18004065e  mov     rcx, [rsp+88h+bstrString]; bstrString
0x180040666  call    cs:__imp_SysFreeString
0x18004066d  nop     dword ptr [rax+rax+00h]
0x180040672  inc     r15d
0x180040675  cmp     r15d, [r14]
0x180040678  jl      loc_18004057D
0x18004067e  mov     [r12], rsi
0x180040682  mov     rax, [rdi]
0x180040685  mov     rdx, [rsp+88h+arg_18]
0x18004068d  mov     rcx, rdi
0x180040690  mov     rax, [rax+98h]
0x180040697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004069c  xor     eax, eax
0x18004069e  mov     rsi, [rsp+88h+arg_0]
0x1800406a6  add     rsp, 60h
0x1800406aa  pop     r15
0x1800406ac  pop     r14
0x1800406ae  pop     r13
0x1800406b0  pop     r12
0x1800406b2  pop     rdi
0x1800406b3  retn
```
