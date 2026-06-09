# SessionDataUtil::WUOptionalSessionInfo::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo * *)

- ea: `0x140015c4c`
- end: `0x140015d7c`
- name: `?CreateInstance@WUOptionalSessionInfo@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z`
- size: `304`
- prototype: `static int(unsigned int, const void *, unsigned int, struct IUnknown *, struct SessionDataUtil::WUOptionalSessionInfo **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1400164c8`
- `0x140017b48`

## callees

- `0x140002ac0`
- `0x140013ec4`
- `0x140015c4c`
- `0x14001601c`
- `0x14001acf4`
- `0x14001ad2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo::CreateInstance(
        unsigned int a1,
        const wchar_t **a2,
        int a3,
        struct IUnknown *a4,
        wchar_t **a5)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  wchar_t *v12; // rax
  wchar_t *v13; // rdi
  SessionDataUtil::WUOptionalSessionInfo *v14; // rbx
  unsigned int v15; // esi
  __int64 v16; // rdx
  int v17; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !a2 )
  {
    v9 = -2147024809;
    v10 = 228;
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
    v10 = 229;
    goto LABEL_3;
  }
  v12 = (wchar_t *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  if ( v12 )
  {
    *(_QWORD *)v12 = 0;
    *((_QWORD *)v12 + 1) = 0;
    *((_QWORD *)v12 + 2) = 0;
    *((_QWORD *)v12 + 3) = 0;
    *((_QWORD *)v12 + 4) = 0;
    *((_QWORD *)v12 + 5) = 0;
    *((_QWORD *)v12 + 6) = 0;
  }
  else
  {
    v13 = 0;
  }
  v14 = (SessionDataUtil::WUOptionalSessionInfo *)v13;
  v15 = v13 == 0 ? 0x8007000E : 0;
  if ( v13 )
  {
    v15 = SessionDataUtil::WUOptionalSessionInfo::Initialize(v13, a1, a2, a3, a4);
    if ( (v15 & 0x80000000) == 0 )
    {
      v14 = 0;
      *a5 = v13;
      v15 = 0;
      goto LABEL_15;
    }
    v16 = 237;
  }
  else
  {
    v16 = 232;
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
    SessionDataUtil::WUOptionalSessionInfo::~WUOptionalSessionInfo(v14);
    operator delete(v14, (const struct std::nothrow_t *)0x38);
  }
  return v15;
}

```

## disassembly

```asm
0x140015c4c  push    rbx
0x140015c4e  push    rbp
0x140015c4f  push    rsi
0x140015c50  push    rdi
0x140015c51  push    r12
0x140015c53  push    r13
0x140015c55  push    r14
0x140015c57  push    r15
0x140015c59  sub     rsp, 48h
0x140015c5d  mov     r13, r9
0x140015c60  mov     r12d, r8d
0x140015c63  mov     rbp, rdx
0x140015c66  mov     r15d, ecx
0x140015c69  mov     r14, [rsp+88h+arg_20]
0x140015c71  xor     ebx, ebx
0x140015c73  test    rdx, rdx
0x140015c76  jnz     short loc_140015CA0
0x140015c78  mov     ebx, 80070057h
0x140015c7d  mov     edx, 0E4h; void *
0x140015c82  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140015c89  mov     r9d, ebx; char *
0x140015c8c  mov     rcx, [rsp+88h]; this
0x140015c94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015c99  mov     eax, ebx
0x140015c9b  jmp     loc_140015D6B
0x140015ca0  test    r14, r14
0x140015ca3  jnz     short loc_140015CB1
0x140015ca5  mov     ebx, 80004003h
0x140015caa  mov     edx, 0E5h
0x140015caf  jmp     short loc_140015C82
0x140015cb1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140015cb8  mov     ecx, 38h ; '8'; unsigned __int64
0x140015cbd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140015cc2  mov     rdi, rax
0x140015cc5  test    rax, rax
0x140015cc8  jz      short loc_140015CE7
0x140015cca  mov     [rax], rbx
0x140015ccd  mov     [rax+8], rbx
0x140015cd1  mov     [rax+10h], rbx
0x140015cd5  mov     [rax+18h], rbx
0x140015cd9  mov     [rax+20h], rbx
0x140015cdd  mov     [rax+28h], rbx
0x140015ce1  mov     [rax+30h], rbx
0x140015ce5  jmp     short loc_140015CEA
0x140015ce7  mov     rdi, rbx
0x140015cea  mov     rbx, rdi
0x140015ced  mov     [rsp+88h+var_58], rbx
0x140015cf2  mov     rax, rdi
0x140015cf5  neg     rax
0x140015cf8  sbb     esi, esi
0x140015cfa  not     esi
0x140015cfc  and     esi, 8007000Eh
0x140015d02  test    rdi, rdi
0x140015d05  jnz     short loc_140015D0E
0x140015d07  mov     edx, 0E8h
0x140015d0c  jmp     short loc_140015D2F
0x140015d0e  mov     qword ptr [rsp+88h+var_68], r13; int
0x140015d13  mov     r9d, r12d; unsigned int
0x140015d16  mov     r8, rbp; void *
0x140015d19  mov     edx, r15d; unsigned int
0x140015d1c  mov     rcx, rdi; this
0x140015d1f  call    ?Initialize@WUOptionalSessionInfo@SessionDataUtil@@AEAAJKPEBXKPEAUIUnknown@@@Z; SessionDataUtil::WUOptionalSessionInfo::Initialize(ulong,void const *,ulong,IUnknown *)
0x140015d24  mov     esi, eax
0x140015d26  test    eax, eax
0x140015d28  jns     short loc_140015D48
0x140015d2a  mov     edx, 0EDh; void *
0x140015d2f  mov     rcx, [rsp+88h]; this
0x140015d37  mov     r9d, esi; char *
0x140015d3a  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140015d41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015d46  jmp     short loc_140015D4F
0x140015d48  xor     ebx, ebx
0x140015d4a  mov     [r14], rdi
0x140015d4d  xor     esi, esi
0x140015d4f  test    rbx, rbx
0x140015d52  jz      short loc_140015D69
0x140015d54  mov     rcx, rbx; this
0x140015d57  call    ??1WUOptionalSessionInfo@SessionDataUtil@@QEAA@XZ; SessionDataUtil::WUOptionalSessionInfo::~WUOptionalSessionInfo(void)
0x140015d5c  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x140015d61  mov     rcx, rbx; void *
0x140015d64  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140015d69  mov     eax, esi
0x140015d6b  add     rsp, 48h
0x140015d6f  pop     r15
0x140015d71  pop     r14
0x140015d73  pop     r13
0x140015d75  pop     r12
0x140015d77  pop     rdi
0x140015d78  pop     rsi
0x140015d79  pop     rbp
0x140015d7a  pop     rbx
0x140015d7b  retn
```
