# SessionDataUtil::WUOptionalSessionInfo2::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo2 * *)

- ea: `0x140016318`
- end: `0x140016438`
- name: `?CreateInstance@WUOptionalSessionInfo2@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z`
- size: `288`
- prototype: `static int(unsigned int, const void *, unsigned int, struct IUnknown *, struct SessionDataUtil::WUOptionalSessionInfo2 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1400168cc`
- `0x140017b48`

## callees

- `0x140002ac0`
- `0x140013e54`
- `0x140016318`
- `0x1400164c8`
- `0x14001acf4`
- `0x14001ad2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo2::CreateInstance(
        unsigned int a1,
        const void *a2,
        unsigned int a3,
        struct IUnknown *a4,
        wchar_t **a5)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  wchar_t *v12; // rax
  wchar_t *v13; // rdi
  SessionDataUtil::WUOptionalSessionInfo2 *v14; // rbx
  unsigned int v15; // esi
  __int64 v16; // rdx
  int v17; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !a2 )
  {
    v9 = -2147024809;
    v10 = 339;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)v9,
      v17);
    return v9;
  }
  if ( !a5 )
  {
    v9 = -2147467261;
    v10 = 340;
    goto LABEL_3;
  }
  v12 = (wchar_t *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  if ( v12 )
  {
    *(_QWORD *)v12 = 0;
    *((_QWORD *)v12 + 1) = 0;
    *((_QWORD *)v12 + 2) = 0;
  }
  else
  {
    v13 = 0;
  }
  v14 = (SessionDataUtil::WUOptionalSessionInfo2 *)v13;
  v15 = v13 == 0 ? 0x8007000E : 0;
  if ( v13 )
  {
    v15 = SessionDataUtil::WUOptionalSessionInfo2::Initialize(v13, a1, a2, a3, a4);
    if ( (v15 & 0x80000000) == 0 )
    {
      v14 = 0;
      *a5 = v13;
      v15 = 0;
      goto LABEL_15;
    }
    v16 = 348;
  }
  else
  {
    v16 = 343;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
    (const char *)v15,
    v17);
LABEL_15:
  if ( v14 )
  {
    SessionDataUtil::WUOptionalSessionInfo2::~WUOptionalSessionInfo2(v14);
    operator delete(v14, (const struct std::nothrow_t *)0x18);
  }
  return v15;
}

```

## disassembly

```asm
0x140016318  push    rbx
0x14001631a  push    rbp
0x14001631b  push    rsi
0x14001631c  push    rdi
0x14001631d  push    r12
0x14001631f  push    r13
0x140016321  push    r14
0x140016323  push    r15
0x140016325  sub     rsp, 48h
0x140016329  mov     r13, r9
0x14001632c  mov     r12d, r8d
0x14001632f  mov     rbp, rdx
0x140016332  mov     r15d, ecx
0x140016335  mov     r14, [rsp+88h+arg_20]
0x14001633d  xor     ebx, ebx
0x14001633f  test    rdx, rdx
0x140016342  jnz     short loc_14001636C
0x140016344  mov     ebx, 80070057h
0x140016349  mov     edx, 153h; void *
0x14001634e  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140016355  mov     r9d, ebx; char *
0x140016358  mov     rcx, [rsp+88h]; this
0x140016360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016365  mov     eax, ebx
0x140016367  jmp     loc_140016427
0x14001636c  test    r14, r14
0x14001636f  jnz     short loc_14001637D
0x140016371  mov     ebx, 80004003h
0x140016376  mov     edx, 154h
0x14001637b  jmp     short loc_14001634E
0x14001637d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140016384  mov     ecx, 18h; unsigned __int64
0x140016389  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001638e  mov     rdi, rax
0x140016391  test    rax, rax
0x140016394  jz      short loc_1400163A3
0x140016396  mov     [rax], rbx
0x140016399  mov     [rax+8], rbx
0x14001639d  mov     [rax+10h], rbx
0x1400163a1  jmp     short loc_1400163A6
0x1400163a3  mov     rdi, rbx
0x1400163a6  mov     rbx, rdi
0x1400163a9  mov     [rsp+88h+var_58], rbx
0x1400163ae  mov     rax, rdi
0x1400163b1  neg     rax
0x1400163b4  sbb     esi, esi
0x1400163b6  not     esi
0x1400163b8  and     esi, 8007000Eh
0x1400163be  test    rdi, rdi
0x1400163c1  jnz     short loc_1400163CA
0x1400163c3  mov     edx, 157h
0x1400163c8  jmp     short loc_1400163EB
0x1400163ca  mov     qword ptr [rsp+88h+var_68], r13; int
0x1400163cf  mov     r9d, r12d; unsigned int
0x1400163d2  mov     r8, rbp; void *
0x1400163d5  mov     edx, r15d; unsigned int
0x1400163d8  mov     rcx, rdi; this
0x1400163db  call    ?Initialize@WUOptionalSessionInfo2@SessionDataUtil@@AEAAJKPEBXKPEAUIUnknown@@@Z; SessionDataUtil::WUOptionalSessionInfo2::Initialize(ulong,void const *,ulong,IUnknown *)
0x1400163e0  mov     esi, eax
0x1400163e2  test    eax, eax
0x1400163e4  jns     short loc_140016404
0x1400163e6  mov     edx, 15Ch; void *
0x1400163eb  mov     rcx, [rsp+88h]; this
0x1400163f3  mov     r9d, esi; char *
0x1400163f6  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400163fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016402  jmp     short loc_14001640B
0x140016404  xor     ebx, ebx
0x140016406  mov     [r14], rdi
0x140016409  xor     esi, esi
0x14001640b  test    rbx, rbx
0x14001640e  jz      short loc_140016425
0x140016410  mov     rcx, rbx; this
0x140016413  call    ??1WUOptionalSessionInfo2@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfo2::~WUOptionalSessionInfo2(void)
0x140016418  mov     edx, 18h; struct std::nothrow_t *
0x14001641d  mov     rcx, rbx; void *
0x140016420  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016425  mov     eax, esi
0x140016427  add     rsp, 48h
0x14001642b  pop     r15
0x14001642d  pop     r14
0x14001642f  pop     r13
0x140016431  pop     r12
0x140016433  pop     rdi
0x140016434  pop     rsi
0x140016435  pop     rbp
0x140016436  pop     rbx
0x140016437  retn
```
