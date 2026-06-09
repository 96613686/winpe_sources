# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x180008238`
- end: `0x18000847b`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007b3c`

## callees

- `0x180001300`
- `0x180001d9c`
- `0x180008238`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800083e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180008434`
- `OLEAUT32!__imp_SysFreeString` at `0x1800083e2`
- `OLEAUT32!__imp_SysFreeString` at `0x180008434`
- `OLEAUT32!__imp_SysStringLen` at `0x1800083f5`
- `OLEAUT32!__imp_SysStringLen` at `0x1800083f5`

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
  BSTR pbstr; // [rsp+80h] [rbp+8h] BYREF
  struct ITypeInfo *v14; // [rsp+88h] [rbp+10h] BYREF
  __int64 v15; // [rsp+90h] [rbp+18h] BYREF
  _QWORD *v16; // [rsp+98h] [rbp+20h]

  v14 = a2;
  pbstr = this;
  v2 = a2;
  v15 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v15) >= 0 )
  {
    v3 = 0;
    pbstr = 0;
    v4 = *(unsigned __int16 *)(v15 + 48);
    dword_18003F550 = v4;
    qword_18003F548 = 0;
    if ( (_WORD)v4 )
    {
      v5 = (unsigned int)v4;
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
        v16 = v9;
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
      LODWORD(v4) = dword_18003F550;
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
      while ( v11 < dword_18003F550 );
    }
    qword_18003F548 = (__int64)v3;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180008238  mov     r11, rsp
0x18000823b  mov     [r11+10h], rdx
0x18000823f  mov     [r11+8], rcx
0x180008243  push    rbx
0x180008244  push    rsi
0x180008245  push    rdi
0x180008246  push    r12
0x180008248  push    r14
0x18000824a  push    r15
0x18000824c  sub     rsp, 48h
0x180008250  mov     rsi, rdx
0x180008253  xor     ebx, ebx
0x180008255  mov     [r11+18h], rbx
0x180008259  mov     rax, [rdx]
0x18000825c  lea     rdx, [r11+18h]
0x180008260  mov     rcx, rsi
0x180008263  mov     rax, [rax+18h]
0x180008267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000826c  test    eax, eax
0x18000826e  js      loc_18000846B
0x180008274  mov     edi, ebx
0x180008276  mov     [rsp+78h+pbstr], rbx
0x18000827e  mov     rax, [rsp+78h+arg_10]
0x180008286  movzx   ecx, word ptr [rax+30h]
0x18000828a  mov     cs:dword_18003F550, ecx
0x180008290  mov     cs:qword_18003F548, rbx
0x180008297  test    cx, cx
0x18000829a  jz      loc_18000834A
0x1800082a0  mov     r14d, ecx
0x1800082a3  lea     r15d, [rbx+10h]
0x1800082a7  mov     eax, r15d
0x1800082aa  mul     rcx
0x1800082ad  lea     rcx, [rbx-1]
0x1800082b1  cmovb   rax, rcx
0x1800082b5  add     rax, 8
0x1800082b9  cmovb   rax, rcx
0x1800082bd  mov     rcx, rax; unsigned __int64
0x1800082c0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800082c5  mov     [rsp+78h+arg_18], rax
0x1800082cd  test    rax, rax
0x1800082d0  jz      short loc_1800082FC
0x1800082d2  mov     [rax], r14
0x1800082d5  lea     rdi, [rax+8]
0x1800082d9  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x1800082e0  mov     [rsp+78h+var_58], rax; void (*)(void *)
0x1800082e5  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x1800082ec  mov     r8d, r14d; unsigned __int64
0x1800082ef  mov     edx, r15d; unsigned __int64
0x1800082f2  mov     rcx, rdi; void *
0x1800082f5  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800082fa  jmp     short loc_1800082FF
0x1800082fc  mov     rdi, rbx
0x1800082ff  mov     [rsp+78h+pbstr], rdi
0x180008307  jmp     short loc_18000831B
0x180008309  xor     ebx, ebx
0x18000830b  mov     rsi, [rsp+78h+arg_8]
0x180008313  mov     rdi, [rsp+78h+pbstr]
0x18000831b  test    rdi, rdi
0x18000831e  jnz     short loc_180008344
0x180008320  mov     rax, [rsi]
0x180008323  mov     rdx, [rsp+78h+arg_10]
0x18000832b  mov     rcx, rsi
0x18000832e  mov     rax, [rax+98h]
0x180008335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000833a  mov     eax, 8007000Eh
0x18000833f  jmp     loc_18000846D
0x180008344  mov     ecx, cs:dword_18003F550
0x18000834a  mov     r14d, ebx
0x18000834d  test    ecx, ecx
0x18000834f  jle     loc_18000844A
0x180008355  mov     [rsp+78h+arg_8], rbx
0x18000835d  movsxd  r15, r14d
0x180008360  add     r15, r15
0x180008363  mov     qword ptr [rdi+r15*8+8], 0
0x18000836c  mov     rax, [rsi]
0x18000836f  lea     r8, [rsp+78h+arg_8]
0x180008377  mov     edx, r14d
0x18000837a  mov     rcx, rsi
0x18000837d  mov     rax, [rax+28h]
0x180008381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008386  test    eax, eax
0x180008388  js      loc_18000843A
0x18000838e  mov     [rsp+78h+pbstr], rbx
0x180008396  mov     rax, [rsi]
0x180008399  mov     [rsp+78h+var_50], rbx
0x18000839e  mov     [rsp+78h+var_58], rbx
0x1800083a3  xor     r9d, r9d
0x1800083a6  lea     r8, [rsp+78h+pbstr]
0x1800083ae  mov     rdx, [rsp+78h+arg_8]
0x1800083b6  mov     edx, [rdx]
0x1800083b8  mov     rcx, rsi
0x1800083bb  mov     rax, [rax+60h]
0x1800083bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083c4  test    eax, eax
0x1800083c6  js      short loc_180008411
0x1800083c8  mov     r12, [rsp+78h+pbstr]
0x1800083d0  mov     [rsp+78h+pbstr], rbx
0x1800083d8  cmp     [rdi+r15*8], r12
0x1800083dc  jz      short loc_1800083EE
0x1800083de  mov     rcx, [rdi+r15*8]; bstrString
0x1800083e2  call    cs:__imp_SysFreeString
0x1800083e8  mov     [rdi+r15*8], r12
0x1800083ec  jmp     short loc_1800083F2
0x1800083ee  mov     r12, [rdi+r15*8]
0x1800083f2  mov     rcx, r12; pbstr
0x1800083f5  call    cs:__imp_SysStringLen
0x1800083fb  mov     [rdi+r15*8+8], eax
0x180008400  mov     rdx, [rsp+78h+arg_8]
0x180008408  mov     eax, [rdx]
0x18000840a  mov     [rdi+r15*8+0Ch], eax
0x18000840f  jmp     short loc_180008419
0x180008411  mov     rdx, [rsp+78h+arg_8]
0x180008419  mov     rax, [rsi]
0x18000841c  mov     rcx, rsi
0x18000841f  mov     rax, [rax+0A0h]
0x180008426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000842b  nop
0x18000842c  mov     rcx, [rsp+78h+pbstr]; bstrString
0x180008434  call    cs:__imp_SysFreeString
0x18000843a  inc     r14d
0x18000843d  cmp     r14d, cs:dword_18003F550
0x180008444  jl      loc_180008355
0x18000844a  mov     cs:qword_18003F548, rdi
0x180008451  mov     rax, [rsi]
0x180008454  mov     rdx, [rsp+78h+arg_10]
0x18000845c  mov     rcx, rsi
0x18000845f  mov     rax, [rax+98h]
0x180008466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000846b  xor     eax, eax
0x18000846d  add     rsp, 48h
0x180008471  pop     r15
0x180008473  pop     r14
0x180008475  pop     r12
0x180008477  pop     rdi
0x180008478  pop     rsi
0x180008479  pop     rbx
0x18000847a  retn
```
