# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x140005ee4`
- end: `0x14000613a`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400050b8`

## callees

- `0x140001054`
- `0x1400013b4`
- `0x140001ff4`
- `0x140002410`
- `0x140005ee4`
- `0x14000f010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140006033`
- `OLEAUT32!__imp_SysFreeString` at `0x1400060b1`
- `OLEAUT32!__imp_SysFreeString` at `0x140006033`
- `OLEAUT32!__imp_SysFreeString` at `0x1400060b1`
- `OLEAUT32!__imp_SysStringLen` at `0x140006009`
- `OLEAUT32!__imp_SysStringLen` at `0x140006009`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfoVtbl *lpVtbl; // rax
  int v5; // r12d
  _QWORD *v6; // rdi
  unsigned int v7; // eax
  __int64 v8; // rbx
  __int64 v9; // rax
  unsigned __int64 v10; // kr00_8
  bool v11; // cf
  unsigned __int64 v12; // rax
  _QWORD *v13; // rax
  ATL::CComTypeInfoHolder::stringdispid *v14; // r15
  int v15; // eax
  unsigned int v17; // r15d
  struct ITypeInfoVtbl *v18; // rax
  struct ITypeInfoVtbl *v19; // rax
  OLECHAR *v20; // rcx
  UINT v21; // eax
  _DWORD *v22; // rdx
  __int64 v23; // r15
  ATL::CComTypeInfoHolder::stringdispid *i; // rbx
  unsigned int *v25; // rdx
  __int64 v26; // r15
  ATL::CComTypeInfoHolder::stringdispid *j; // rbx
  __int64 v28; // rdx
  BSTR pbstr; // [rsp+88h] [rbp+48h] BYREF
  unsigned int *v30; // [rsp+90h] [rbp+50h] BYREF
  __int64 v31; // [rsp+98h] [rbp+58h] BYREF

  lpVtbl = a2->lpVtbl;
  v31 = 0;
  v5 = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *))lpVtbl->GetTypeAttr)(a2, &v31);
  if ( v5 >= 0 )
  {
    v6 = 0;
    v7 = *(unsigned __int16 *)(v31 + 48);
    *((_DWORD *)this + 12) = v7;
    if ( v7 )
    {
      v8 = v7;
      v10 = v7;
      v9 = 16LL * v7;
      if ( !is_mul_ok(v10, 0x10u) )
        v9 = -1;
      v11 = __CFADD__(v9, 8);
      v12 = v9 + 8;
      if ( v11 )
        v12 = -1;
      v13 = operator new[](v12);
      if ( v13 )
      {
        v6 = v13 + 1;
        *v13 = v8;
        v14 = (ATL::CComTypeInfoHolder::stringdispid *)(v13 + 1);
        do
        {
          ATL::CComTypeInfoHolder::stringdispid::stringdispid(v14);
          v14 = (ATL::CComTypeInfoHolder::stringdispid *)((char *)v14 + 16);
          --v8;
        }
        while ( v8 );
      }
    }
    v15 = *((_DWORD *)this + 12);
    if ( v15 && !v6 )
    {
      *((_DWORD *)this + 12) = 0;
      return 2147942414LL;
    }
    v17 = 0;
    if ( v15 > 0 )
    {
      while ( 1 )
      {
        v18 = a2->lpVtbl;
        v30 = 0;
        v5 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, unsigned int **))v18->GetFuncDesc)(a2, v17, &v30);
        if ( v5 < 0 )
          break;
        v19 = a2->lpVtbl;
        pbstr = 0;
        v5 = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v19->GetDocumentation)(
               a2,
               *v30,
               &pbstr,
               0,
               0,
               0);
        if ( v5 < 0 )
        {
          if ( v6 )
          {
            v23 = *(v6 - 1);
            for ( i = (ATL::CComTypeInfoHolder::stringdispid *)&v6[2 * v23]; v23; --v23 )
            {
              i = (ATL::CComTypeInfoHolder::stringdispid *)((char *)i - 16);
              ATL::CComTypeInfoHolder::stringdispid::~stringdispid(i);
            }
            operator delete[](v6 - 1, 16LL * *(v6 - 1) + 8);
          }
          v25 = v30;
          *((_DWORD *)this + 12) = 0;
          v6 = 0;
          ((void (__fastcall *)(struct ITypeInfo *, unsigned int *))a2->lpVtbl->ReleaseFuncDesc)(a2, v25);
          SysFreeString(pbstr);
          goto LABEL_28;
        }
        v20 = pbstr;
        pbstr = 0;
        v6[2 * (int)v17] = v20;
        v21 = SysStringLen(v20);
        v22 = v30;
        LODWORD(v6[2 * (int)v17 + 1]) = v21;
        HIDWORD(v6[2 * (int)v17 + 1]) = *v22;
        ((void (__fastcall *)(struct ITypeInfo *))a2->lpVtbl->ReleaseFuncDesc)(a2);
        SysFreeString(pbstr);
        if ( (signed int)++v17 >= *((_DWORD *)this + 12) )
          goto LABEL_28;
      }
      if ( v6 )
      {
        v26 = *(v6 - 1);
        for ( j = (ATL::CComTypeInfoHolder::stringdispid *)&v6[2 * v26]; v26; --v26 )
        {
          j = (ATL::CComTypeInfoHolder::stringdispid *)((char *)j - 16);
          ATL::CComTypeInfoHolder::stringdispid::~stringdispid(j);
        }
        operator delete[](v6 - 1, 16LL * *(v6 - 1) + 8);
      }
      v6 = 0;
      *((_DWORD *)this + 12) = 0;
    }
LABEL_28:
    v28 = v31;
    *((_QWORD *)this + 5) = v6;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))a2->lpVtbl->ReleaseTypeAttr)(a2, v28);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140005ee4  mov     [rsp-38h+arg_0], rbx
0x140005ee9  push    rbp
0x140005eea  push    rsi
0x140005eeb  push    rdi
0x140005eec  push    r12
0x140005eee  push    r13
0x140005ef0  push    r14
0x140005ef2  push    r15
0x140005ef4  mov     rbp, rsp
0x140005ef7  sub     rsp, 40h
0x140005efb  mov     rax, [rdx]
0x140005efe  mov     rsi, rdx
0x140005f01  mov     r14, rcx
0x140005f04  lea     rdx, [rbp+arg_18]
0x140005f08  xor     r13d, r13d
0x140005f0b  mov     rcx, rsi
0x140005f0e  mov     [rbp+arg_18], r13
0x140005f12  mov     rax, [rax+18h]
0x140005f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f1b  mov     r12d, eax
0x140005f1e  test    eax, eax
0x140005f20  js      loc_14000611F
0x140005f26  mov     rcx, [rbp+arg_18]
0x140005f2a  mov     edi, r13d
0x140005f2d  movzx   eax, word ptr [rcx+30h]
0x140005f31  mov     [r14+30h], eax
0x140005f35  test    eax, eax
0x140005f37  jz      short loc_140005F7B
0x140005f39  mov     ebx, eax
0x140005f3b  lea     rcx, [r13-1]
0x140005f3f  lea     eax, [r13+10h]
0x140005f43  mul     rbx
0x140005f46  cmovb   rax, rcx
0x140005f4a  add     rax, 8
0x140005f4e  cmovb   rax, rcx
0x140005f52  mov     rcx, rax; unsigned __int64
0x140005f55  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140005f5a  test    rax, rax
0x140005f5d  jz      short loc_140005F7B
0x140005f5f  lea     rdi, [rax+8]
0x140005f63  mov     [rax], rbx
0x140005f66  mov     r15, rdi
0x140005f69  mov     rcx, r15; this
0x140005f6c  call    ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::stringdispid(void)
0x140005f71  add     r15, 10h
0x140005f75  sub     rbx, 1
0x140005f79  jnz     short loc_140005F69
0x140005f7b  mov     eax, [r14+30h]
0x140005f7f  test    eax, eax
0x140005f81  jz      short loc_140005F96
0x140005f83  test    rdi, rdi
0x140005f86  jnz     short loc_140005F96
0x140005f88  mov     [r14+30h], r13d
0x140005f8c  mov     eax, 8007000Eh
0x140005f91  jmp     loc_140006122
0x140005f96  mov     r15d, r13d
0x140005f99  test    eax, eax
0x140005f9b  jle     loc_140006105
0x140005fa1  mov     rax, [rsi]
0x140005fa4  lea     r8, [rbp+arg_10]
0x140005fa8  mov     edx, r15d
0x140005fab  mov     [rbp+arg_10], r13
0x140005faf  mov     rcx, rsi
0x140005fb2  mov     rax, [rax+28h]
0x140005fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fbb  mov     r12d, eax
0x140005fbe  test    eax, eax
0x140005fc0  js      loc_1400060B9
0x140005fc6  mov     rax, [rsi]
0x140005fc9  lea     r8, [rbp+pbstr]
0x140005fcd  mov     rdx, [rbp+arg_10]
0x140005fd1  xor     r9d, r9d
0x140005fd4  mov     [rbp+pbstr], r13
0x140005fd8  mov     rcx, rsi
0x140005fdb  mov     [rsp+40h+var_18], r13
0x140005fe0  mov     rax, [rax+60h]
0x140005fe4  mov     edx, [rdx]
0x140005fe6  mov     [rsp+40h+var_20], r13
0x140005feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ff0  mov     r12d, eax
0x140005ff3  test    eax, eax
0x140005ff5  js      short loc_14000604B
0x140005ff7  mov     rcx, [rbp+pbstr]; pbstr
0x140005ffb  movsxd  rbx, r15d
0x140005ffe  add     rbx, rbx
0x140006001  mov     [rbp+pbstr], r13
0x140006005  mov     [rdi+rbx*8], rcx
0x140006009  call    cs:__imp_SysStringLen
0x14000600f  mov     rdx, [rbp+arg_10]
0x140006013  mov     rcx, rsi
0x140006016  mov     [rdi+rbx*8+8], eax
0x14000601a  mov     eax, [rdx]
0x14000601c  mov     [rdi+rbx*8+0Ch], eax
0x140006020  mov     rax, [rsi]
0x140006023  mov     rax, [rax+0A0h]
0x14000602a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000602f  mov     rcx, [rbp+pbstr]; bstrString
0x140006033  call    cs:__imp_SysFreeString
0x140006039  inc     r15d
0x14000603c  cmp     r15d, [r14+30h]
0x140006040  jl      loc_140005FA1
0x140006046  jmp     loc_140006105
0x14000604b  test    rdi, rdi
0x14000604e  jz      short loc_140006090
0x140006050  lea     r13, [rdi-8]
0x140006054  mov     r15, [r13+0]
0x140006058  mov     rbx, r15
0x14000605b  shl     rbx, 4
0x14000605f  add     rbx, rdi
0x140006062  test    r15, r15
0x140006065  jz      short loc_140006079
0x140006067  sub     rbx, 10h
0x14000606b  mov     rcx, rbx; this
0x14000606e  call    ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x140006073  sub     r15, 1
0x140006077  jnz     short loc_140006067
0x140006079  mov     rdx, [r13+0]
0x14000607d  mov     rcx, r13; void *
0x140006080  shl     rdx, 4
0x140006084  add     rdx, 8; unsigned __int64
0x140006088  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x14000608d  xor     r13d, r13d
0x140006090  mov     rdx, [rbp+arg_10]
0x140006094  mov     rcx, rsi
0x140006097  mov     [r14+30h], r13d
0x14000609b  mov     rdi, r13
0x14000609e  mov     rax, [rsi]
0x1400060a1  mov     rax, [rax+0A0h]
0x1400060a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060ad  mov     rcx, [rbp+pbstr]; bstrString
0x1400060b1  call    cs:__imp_SysFreeString
0x1400060b7  jmp     short loc_140006105
0x1400060b9  test    rdi, rdi
0x1400060bc  jz      short loc_1400060FE
0x1400060be  lea     r13, [rdi-8]
0x1400060c2  mov     r15, [r13+0]
0x1400060c6  mov     rbx, r15
0x1400060c9  shl     rbx, 4
0x1400060cd  add     rbx, rdi
0x1400060d0  test    r15, r15
0x1400060d3  jz      short loc_1400060E7
0x1400060d5  sub     rbx, 10h
0x1400060d9  mov     rcx, rbx; this
0x1400060dc  call    ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x1400060e1  sub     r15, 1
0x1400060e5  jnz     short loc_1400060D5
0x1400060e7  mov     rdx, [r13+0]
0x1400060eb  mov     rcx, r13; void *
0x1400060ee  shl     rdx, 4
0x1400060f2  add     rdx, 8; unsigned __int64
0x1400060f6  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x1400060fb  xor     r13d, r13d
0x1400060fe  mov     rdi, r13
0x140006101  mov     [r14+30h], r13d
0x140006105  mov     rdx, [rbp+arg_18]
0x140006109  mov     rcx, rsi
0x14000610c  mov     [r14+28h], rdi
0x140006110  mov     rax, [rsi]
0x140006113  mov     rax, [rax+98h]
0x14000611a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000611f  mov     eax, r12d
0x140006122  mov     rbx, [rsp+40h+arg_0]
0x14000612a  add     rsp, 40h
0x14000612e  pop     r15
0x140006130  pop     r14
0x140006132  pop     r13
0x140006134  pop     r12
0x140006136  pop     rdi
0x140006137  pop     rsi
0x140006138  pop     rbp
0x140006139  retn
```
