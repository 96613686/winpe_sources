# SessionDataUtil::WUOptionalSessionInfo3::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo3 * *)

- ea: `0x14001671c`
- end: `0x14001683c`
- name: `?CreateInstance@WUOptionalSessionInfo3@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z`
- size: `288`
- prototype: `static int(unsigned int, const void *, unsigned int, struct IUnknown *, struct SessionDataUtil::WUOptionalSessionInfo3 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140016cd4`
- `0x140017b48`

## callees

- `0x140002ac0`
- `0x140013de4`
- `0x14001671c`
- `0x1400168cc`
- `0x14001acf4`
- `0x14001ad2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo3::CreateInstance(
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
  SessionDataUtil::WUOptionalSessionInfo3 *v14; // rbx
  unsigned int v15; // esi
  __int64 v16; // rdx
  int v17; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !a2 )
  {
    v9 = -2147024809;
    v10 = 419;
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
    v10 = 420;
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
  v14 = (SessionDataUtil::WUOptionalSessionInfo3 *)v13;
  v15 = v13 == 0 ? 0x8007000E : 0;
  if ( v13 )
  {
    v15 = SessionDataUtil::WUOptionalSessionInfo3::Initialize(v13, a1, a2, a3, a4);
    if ( (v15 & 0x80000000) == 0 )
    {
      v14 = 0;
      *a5 = v13;
      v15 = 0;
      goto LABEL_15;
    }
    v16 = 428;
  }
  else
  {
    v16 = 423;
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
    SessionDataUtil::WUOptionalSessionInfo3::~WUOptionalSessionInfo3(v14);
    operator delete(v14, (const struct std::nothrow_t *)0x18);
  }
  return v15;
}

```

## disassembly

```asm
0x14001671c  push    rbx
0x14001671e  push    rbp
0x14001671f  push    rsi
0x140016720  push    rdi
0x140016721  push    r12
0x140016723  push    r13
0x140016725  push    r14
0x140016727  push    r15
0x140016729  sub     rsp, 48h
0x14001672d  mov     r13, r9
0x140016730  mov     r12d, r8d
0x140016733  mov     rbp, rdx
0x140016736  mov     r15d, ecx
0x140016739  mov     r14, [rsp+88h+arg_20]
0x140016741  xor     ebx, ebx
0x140016743  test    rdx, rdx
0x140016746  jnz     short loc_140016770
0x140016748  mov     ebx, 80070057h
0x14001674d  mov     edx, 1A3h; void *
0x140016752  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140016759  mov     r9d, ebx; char *
0x14001675c  mov     rcx, [rsp+88h]; this
0x140016764  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016769  mov     eax, ebx
0x14001676b  jmp     loc_14001682B
0x140016770  test    r14, r14
0x140016773  jnz     short loc_140016781
0x140016775  mov     ebx, 80004003h
0x14001677a  mov     edx, 1A4h
0x14001677f  jmp     short loc_140016752
0x140016781  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140016788  mov     ecx, 18h; unsigned __int64
0x14001678d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140016792  mov     rdi, rax
0x140016795  test    rax, rax
0x140016798  jz      short loc_1400167A7
0x14001679a  mov     [rax], rbx
0x14001679d  mov     [rax+8], rbx
0x1400167a1  mov     [rax+10h], rbx
0x1400167a5  jmp     short loc_1400167AA
0x1400167a7  mov     rdi, rbx
0x1400167aa  mov     rbx, rdi
0x1400167ad  mov     [rsp+88h+var_58], rbx
0x1400167b2  mov     rax, rdi
0x1400167b5  neg     rax
0x1400167b8  sbb     esi, esi
0x1400167ba  not     esi
0x1400167bc  and     esi, 8007000Eh
0x1400167c2  test    rdi, rdi
0x1400167c5  jnz     short loc_1400167CE
0x1400167c7  mov     edx, 1A7h
0x1400167cc  jmp     short loc_1400167EF
0x1400167ce  mov     qword ptr [rsp+88h+var_68], r13; int
0x1400167d3  mov     r9d, r12d; unsigned int
0x1400167d6  mov     r8, rbp; void *
0x1400167d9  mov     edx, r15d; unsigned int
0x1400167dc  mov     rcx, rdi; this
0x1400167df  call    ?Initialize@WUOptionalSessionInfo3@SessionDataUtil@@AEAAJKPEBXKPEAUIUnknown@@@Z; SessionDataUtil::WUOptionalSessionInfo3::Initialize(ulong,void const *,ulong,IUnknown *)
0x1400167e4  mov     esi, eax
0x1400167e6  test    eax, eax
0x1400167e8  jns     short loc_140016808
0x1400167ea  mov     edx, 1ACh; void *
0x1400167ef  mov     rcx, [rsp+88h]; this
0x1400167f7  mov     r9d, esi; char *
0x1400167fa  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140016801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016806  jmp     short loc_14001680F
0x140016808  xor     ebx, ebx
0x14001680a  mov     [r14], rdi
0x14001680d  xor     esi, esi
0x14001680f  test    rbx, rbx
0x140016812  jz      short loc_140016829
0x140016814  mov     rcx, rbx; this
0x140016817  call    ??1WUOptionalSessionInfo3@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfo3::~WUOptionalSessionInfo3(void)
0x14001681c  mov     edx, 18h; struct std::nothrow_t *
0x140016821  mov     rcx, rbx; void *
0x140016824  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140016829  mov     eax, esi
0x14001682b  add     rsp, 48h
0x14001682f  pop     r15
0x140016831  pop     r14
0x140016833  pop     r13
0x140016835  pop     r12
0x140016837  pop     rdi
0x140016838  pop     rsi
0x140016839  pop     rbp
0x14001683a  pop     rbx
0x14001683b  retn
```
