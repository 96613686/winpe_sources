# SessionDataUtil::WUOptionalSessionInfo5::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo5 * *)

- ea: `0x140016ef8`
- end: `0x14001703e`
- name: `?CreateInstance@WUOptionalSessionInfo5@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z`
- size: `326`
- prototype: `static int(unsigned int, const void *, unsigned int, struct IUnknown *, struct SessionDataUtil::WUOptionalSessionInfo5 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x140017624`
- `0x140017b48`

## callees

- `0x140002ac0`
- `0x14000d4cc`
- `0x140013cf0`
- `0x140016ef8`
- `0x1400170dc`
- `0x14001acf4`
- `0x14001ad2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo5::CreateInstance(
        unsigned int a1,
        char *a2,
        unsigned int a3,
        struct IUnknown *a4,
        struct SessionDataUtil::WUOptionalSessionInfo5 **a5)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  SessionDataUtil::WUOptionalSessionInfo5 *v12; // rax
  SessionDataUtil::WUOptionalSessionInfo5 *v13; // rdi
  SessionDataUtil::WUOptionalSessionInfo5 *v14; // rbx
  unsigned int v15; // esi
  __int64 v16; // rdx
  void *v17; // rcx
  int v18; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !a2 )
  {
    v9 = -2147024809;
    v10 = 573;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)v9,
      v18);
    return v9;
  }
  if ( !a5 )
  {
    v9 = -2147467261;
    v10 = 574;
    goto LABEL_3;
  }
  v12 = (SessionDataUtil::WUOptionalSessionInfo5 *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  if ( v12 )
  {
    *((_DWORD *)v12 + 9) = 0;
    *(_OWORD *)v12 = 0;
    *((_OWORD *)v12 + 1) = 0;
    *((_DWORD *)v12 + 8) = 0;
    *((_QWORD *)v12 + 5) = 0;
    *((_QWORD *)v12 + 6) = 0;
  }
  else
  {
    v13 = 0;
  }
  v14 = v13;
  v15 = v13 == 0 ? 0x8007000E : 0;
  if ( v13 )
  {
    v15 = SessionDataUtil::WUOptionalSessionInfo5::Initialize(v13, a1, a2, a3, a4);
    if ( (v15 & 0x80000000) == 0 )
    {
      v14 = 0;
      *a5 = v13;
      v15 = 0;
      goto LABEL_15;
    }
    v16 = 582;
  }
  else
  {
    v16 = 577;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
    (const char *)v15,
    v18);
LABEL_15:
  if ( v14 )
  {
    v17 = (void *)*((_QWORD *)v14 + 6);
    if ( v17 )
    {
      SusFree(v17);
      *((_QWORD *)v14 + 6) = 0;
    }
    WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease((char *)v14 + 40);
    operator delete(v14, (const struct std::nothrow_t *)0x38);
  }
  return v15;
}

```

## disassembly

```asm
0x140016ef8  push    rbx
0x140016efa  push    rbp
0x140016efb  push    rsi
0x140016efc  push    rdi
0x140016efd  push    r12
0x140016eff  push    r13
0x140016f01  push    r14
0x140016f03  push    r15
0x140016f05  sub     rsp, 48h
0x140016f09  mov     r13, r9
0x140016f0c  mov     r12d, r8d
0x140016f0f  mov     rbp, rdx
0x140016f12  mov     r15d, ecx
0x140016f15  mov     r14, [rsp+88h+arg_20]
0x140016f1d  xor     ebx, ebx
0x140016f1f  test    rdx, rdx
0x140016f22  jnz     short loc_140016F4C
0x140016f24  mov     ebx, 80070057h
0x140016f29  mov     edx, 23Dh; void *
0x140016f2e  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140016f35  mov     r9d, ebx; char *
0x140016f38  mov     rcx, [rsp+88h]; this
0x140016f40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016f45  mov     eax, ebx
0x140016f47  jmp     loc_14001702D
0x140016f4c  test    r14, r14
0x140016f4f  jnz     short loc_140016F5D
0x140016f51  mov     ebx, 80004003h
0x140016f56  mov     edx, 23Eh
0x140016f5b  jmp     short loc_140016F2E
0x140016f5d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140016f64  mov     ecx, 38h ; '8'; unsigned __int64
0x140016f69  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140016f6e  mov     rdi, rax
0x140016f71  test    rax, rax
0x140016f74  jz      short loc_140016F92
0x140016f76  mov     [rax+24h], ebx
0x140016f79  xorps   xmm0, xmm0
0x140016f7c  xor     eax, eax
0x140016f7e  movups  xmmword ptr [rdi], xmm0
0x140016f81  movups  xmmword ptr [rdi+10h], xmm0
0x140016f85  mov     [rdi+20h], eax
0x140016f88  mov     [rdi+28h], rbx
0x140016f8c  mov     [rdi+30h], rbx
0x140016f90  jmp     short loc_140016F95
0x140016f92  mov     rdi, rbx
0x140016f95  mov     rbx, rdi
0x140016f98  mov     [rsp+88h+var_58], rbx
0x140016f9d  mov     rax, rdi
0x140016fa0  neg     rax
0x140016fa3  sbb     esi, esi
0x140016fa5  not     esi
0x140016fa7  and     esi, 8007000Eh
0x140016fad  test    rdi, rdi
0x140016fb0  jnz     short loc_140016FB9
0x140016fb2  mov     edx, 241h
0x140016fb7  jmp     short loc_140016FDA
0x140016fb9  mov     qword ptr [rsp+88h+var_68], r13; int
0x140016fbe  mov     r9d, r12d; unsigned int
0x140016fc1  mov     r8, rbp; void *
0x140016fc4  mov     edx, r15d; unsigned int
0x140016fc7  mov     rcx, rdi; this
0x140016fca  call    ?Initialize@WUOptionalSessionInfo5@SessionDataUtil@@AEAAJKPEBXKPEAUIUnknown@@@Z; SessionDataUtil::WUOptionalSessionInfo5::Initialize(ulong,void const *,ulong,IUnknown *)
0x140016fcf  mov     esi, eax
0x140016fd1  test    eax, eax
0x140016fd3  jns     short loc_140016FF3
0x140016fd5  mov     edx, 246h; void *
0x140016fda  mov     rcx, [rsp+88h]; this
0x140016fe2  mov     r9d, esi; char *
0x140016fe5  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140016fec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016ff1  jmp     short loc_140016FFA
0x140016ff3  xor     ebx, ebx
0x140016ff5  mov     [r14], rdi
0x140016ff8  xor     esi, esi
0x140016ffa  test    rbx, rbx
0x140016ffd  jz      short loc_14001702B
0x140016fff  mov     rcx, [rbx+30h]; lpMem
0x140017003  test    rcx, rcx
0x140017006  jz      short loc_140017015
0x140017008  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14001700d  mov     qword ptr [rbx+30h], 0
0x140017015  lea     rcx, [rbx+28h]
0x140017019  call    ?InternalRelease@?$XPtrBase@VWUOptionalSessionInfo4@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo4@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease(void)
0x14001701e  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x140017023  mov     rcx, rbx; void *
0x140017026  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001702b  mov     eax, esi
0x14001702d  add     rsp, 48h
0x140017031  pop     r15
0x140017033  pop     r14
0x140017035  pop     r13
0x140017037  pop     r12
0x140017039  pop     rdi
0x14001703a  pop     rsi
0x14001703b  pop     rbp
0x14001703c  pop     rbx
0x14001703d  retn
```
