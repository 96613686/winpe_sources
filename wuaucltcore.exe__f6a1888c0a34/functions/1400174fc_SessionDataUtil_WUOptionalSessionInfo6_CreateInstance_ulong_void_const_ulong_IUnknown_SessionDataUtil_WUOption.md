# SessionDataUtil::WUOptionalSessionInfo6::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo6 * *)

- ea: `0x1400174fc`
- end: `0x14001761c`
- name: `?CreateInstance@WUOptionalSessionInfo6@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z`
- size: `288`
- prototype: `static int(unsigned int, const void *, unsigned int, struct IUnknown *, struct SessionDataUtil::WUOptionalSessionInfo6 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140017b48`

## callees

- `0x140002ac0`
- `0x140013d70`
- `0x1400174fc`
- `0x140017624`
- `0x14001acf4`
- `0x14001ad2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo6::CreateInstance(
        unsigned int a1,
        const void *a2,
        unsigned int a3,
        struct IUnknown *a4,
        struct SessionDataUtil::WUOptionalSessionInfo6 **a5)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  SessionDataUtil::WUOptionalSessionInfo6 *v12; // rax
  SessionDataUtil::WUOptionalSessionInfo6 *v13; // rdi
  SessionDataUtil::WUOptionalSessionInfo6 *v14; // rbx
  unsigned int v15; // esi
  __int64 v16; // rdx
  int v17; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !a2 )
  {
    v9 = -2147024809;
    v10 = 721;
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
    v10 = 722;
    goto LABEL_3;
  }
  v12 = (SessionDataUtil::WUOptionalSessionInfo6 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
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
  v14 = v13;
  v15 = v13 == 0 ? 0x8007000E : 0;
  if ( v13 )
  {
    v15 = SessionDataUtil::WUOptionalSessionInfo6::Initialize(v13, a1, a2, a3, a4);
    if ( (v15 & 0x80000000) == 0 )
    {
      v14 = 0;
      *a5 = v13;
      v15 = 0;
      goto LABEL_15;
    }
    v16 = 730;
  }
  else
  {
    v16 = 725;
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
    SessionDataUtil::WUOptionalSessionInfo6::~WUOptionalSessionInfo6(v14);
    operator delete(v14, (const struct std::nothrow_t *)0x18);
  }
  return v15;
}

```

## disassembly

```asm
0x1400174fc  push    rbx
0x1400174fe  push    rbp
0x1400174ff  push    rsi
0x140017500  push    rdi
0x140017501  push    r12
0x140017503  push    r13
0x140017505  push    r14
0x140017507  push    r15
0x140017509  sub     rsp, 48h
0x14001750d  mov     r13, r9
0x140017510  mov     r12d, r8d
0x140017513  mov     rbp, rdx
0x140017516  mov     r15d, ecx
0x140017519  mov     r14, [rsp+88h+arg_20]
0x140017521  xor     ebx, ebx
0x140017523  test    rdx, rdx
0x140017526  jnz     short loc_140017550
0x140017528  mov     ebx, 80070057h
0x14001752d  mov     edx, 2D1h; void *
0x140017532  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140017539  mov     r9d, ebx; char *
0x14001753c  mov     rcx, [rsp+88h]; this
0x140017544  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017549  mov     eax, ebx
0x14001754b  jmp     loc_14001760B
0x140017550  test    r14, r14
0x140017553  jnz     short loc_140017561
0x140017555  mov     ebx, 80004003h
0x14001755a  mov     edx, 2D2h
0x14001755f  jmp     short loc_140017532
0x140017561  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140017568  mov     ecx, 18h; unsigned __int64
0x14001756d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140017572  mov     rdi, rax
0x140017575  test    rax, rax
0x140017578  jz      short loc_140017587
0x14001757a  mov     [rax], rbx
0x14001757d  mov     [rax+8], rbx
0x140017581  mov     [rax+10h], rbx
0x140017585  jmp     short loc_14001758A
0x140017587  mov     rdi, rbx
0x14001758a  mov     rbx, rdi
0x14001758d  mov     [rsp+88h+var_58], rbx
0x140017592  mov     rax, rdi
0x140017595  neg     rax
0x140017598  sbb     esi, esi
0x14001759a  not     esi
0x14001759c  and     esi, 8007000Eh
0x1400175a2  test    rdi, rdi
0x1400175a5  jnz     short loc_1400175AE
0x1400175a7  mov     edx, 2D5h
0x1400175ac  jmp     short loc_1400175CF
0x1400175ae  mov     qword ptr [rsp+88h+var_68], r13; int
0x1400175b3  mov     r9d, r12d; unsigned int
0x1400175b6  mov     r8, rbp; void *
0x1400175b9  mov     edx, r15d; unsigned int
0x1400175bc  mov     rcx, rdi; this
0x1400175bf  call    ?Initialize@WUOptionalSessionInfo6@SessionDataUtil@@AEAAJKPEBXKPEAUIUnknown@@@Z; SessionDataUtil::WUOptionalSessionInfo6::Initialize(ulong,void const *,ulong,IUnknown *)
0x1400175c4  mov     esi, eax
0x1400175c6  test    eax, eax
0x1400175c8  jns     short loc_1400175E8
0x1400175ca  mov     edx, 2DAh; void *
0x1400175cf  mov     rcx, [rsp+88h]; this
0x1400175d7  mov     r9d, esi; char *
0x1400175da  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1400175e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400175e6  jmp     short loc_1400175EF
0x1400175e8  xor     ebx, ebx
0x1400175ea  mov     [r14], rdi
0x1400175ed  xor     esi, esi
0x1400175ef  test    rbx, rbx
0x1400175f2  jz      short loc_140017609
0x1400175f4  mov     rcx, rbx; this
0x1400175f7  call    ??1WUOptionalSessionInfo6@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfo6::~WUOptionalSessionInfo6(void)
0x1400175fc  mov     edx, 18h; struct std::nothrow_t *
0x140017601  mov     rcx, rbx; void *
0x140017604  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017609  mov     eax, esi
0x14001760b  add     rsp, 48h
0x14001760f  pop     r15
0x140017611  pop     r14
0x140017613  pop     r13
0x140017615  pop     r12
0x140017617  pop     rdi
0x140017618  pop     rsi
0x140017619  pop     rbp
0x14001761a  pop     rbx
0x14001761b  retn
```
