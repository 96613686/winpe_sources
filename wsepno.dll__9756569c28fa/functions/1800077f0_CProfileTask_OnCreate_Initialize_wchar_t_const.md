# CProfileTask_OnCreate::Initialize(wchar_t const *)

- ea: `0x1800077f0`
- end: `0x1800078df`
- name: `?Initialize@CProfileTask_OnCreate@@QEAAJPEB_W@Z`
- size: `239`
- prototype: `__int64 __fastcall(CProfileTask_OnCreate *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180007fd0`

## callees

- `0x180001794`
- `0x180001b9c`
- `0x1800077f0`

## pseudocode

```c
__int64 __fastcall CProfileTask_OnCreate::Initialize(CProfileTask_OnCreate *this, const wchar_t *a2)
{
  const wchar_t *v3; // rsi
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rax
  void *v7; // rax
  char *v8; // r14
  void *v9; // rcx
  _WORD *v10; // rdx
  unsigned int v11; // ecx
  _WORD *v12; // rcx
  char v14; // [rsp+20h] [rbp-38h] BYREF

  v3 = a2;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = v4 + 1;
  v6 = 2 * (v4 + 1);
  if ( !is_mul_ok(v4 + 1, 2u) )
    v6 = -1;
  v7 = operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v8 = (char *)this + 8;
  if ( v8 == &v14 )
  {
    if ( !v7 )
      goto LABEL_11;
    v9 = v7;
  }
  else
  {
    v9 = *(void **)v8;
    *(_QWORD *)v8 = v7;
    if ( !v9 )
      goto LABEL_11;
  }
  operator delete(v9);
LABEL_11:
  v10 = *(_WORD **)v8;
  if ( *(_QWORD *)v8 )
  {
    if ( v4 == -1 )
    {
      return (unsigned int)-2147024809;
    }
    else if ( v5 > 0x7FFFFFFF || v4 > 0x7FFFFFFE )
    {
      v11 = -2147024809;
      *v10 = 0;
    }
    else
    {
      do
      {
        if ( !v4 )
          break;
        if ( !*v3 )
          break;
        *v10++ = *v3++;
        --v4;
        --v5;
      }
      while ( v5 );
      v12 = v10 - 1;
      if ( v5 )
        v12 = v10;
      *v12 = 0;
      return v5 == 0 ? 0x8007007A : 0;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v11;
}

```

## disassembly

```asm
0x1800077f0  push    rbx
0x1800077f2  push    rbp
0x1800077f3  push    rsi
0x1800077f4  push    rdi
0x1800077f5  push    r14
0x1800077f7  sub     rsp, 30h
0x1800077fb  mov     r14, rcx
0x1800077fe  mov     rsi, rdx
0x180007801  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007805  mov     rdi, rcx
0x180007808  xor     ebp, ebp
0x18000780a  inc     rdi
0x18000780d  cmp     [rdx+rdi*2], bp
0x180007811  jnz     short loc_18000780A
0x180007813  lea     rbx, [rdi+1]
0x180007817  mov     eax, 2
0x18000781c  mul     rbx
0x18000781f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007826  cmovb   rax, rcx
0x18000782a  mov     rcx, rax; unsigned __int64
0x18000782d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007832  lea     rcx, [rsp+58h+var_38]
0x180007837  add     r14, 8
0x18000783b  cmp     r14, rcx
0x18000783e  jz      short loc_18000784D
0x180007840  mov     rcx, [r14]
0x180007843  mov     [r14], rax
0x180007846  test    rcx, rcx
0x180007849  jz      short loc_18000785A
0x18000784b  jmp     short loc_180007855
0x18000784d  test    rax, rax
0x180007850  jz      short loc_18000785A
0x180007852  mov     rcx, rax; Block
0x180007855  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000785a  mov     rdx, [r14]
0x18000785d  test    rdx, rdx
0x180007860  jz      short loc_1800078CD
0x180007862  test    rbx, rbx
0x180007865  jz      short loc_1800078BE
0x180007867  cmp     rbx, 7FFFFFFFh
0x18000786e  jbe     short loc_180007877
0x180007870  mov     ecx, 80070057h
0x180007875  jmp     short loc_1800078C8
0x180007877  cmp     rdi, 7FFFFFFEh
0x18000787e  ja      short loc_180007870
0x180007880  test    rdi, rdi
0x180007883  jz      short loc_1800078A1
0x180007885  movzx   eax, word ptr [rsi]
0x180007888  test    ax, ax
0x18000788b  jz      short loc_1800078A1
0x18000788d  mov     [rdx], ax
0x180007890  add     rsi, 2
0x180007894  add     rdx, 2
0x180007898  dec     rdi
0x18000789b  sub     rbx, 1
0x18000789f  jnz     short loc_180007880
0x1800078a1  test    rbx, rbx
0x1800078a4  lea     rcx, [rdx-2]
0x1800078a8  cmovnz  rcx, rdx
0x1800078ac  neg     rbx
0x1800078af  mov     [rcx], bp
0x1800078b2  sbb     ecx, ecx
0x1800078b4  not     ecx
0x1800078b6  and     ecx, 8007007Ah
0x1800078bc  jmp     short loc_1800078D2
0x1800078be  mov     ecx, 80070057h
0x1800078c3  test    rbx, rbx
0x1800078c6  jz      short loc_1800078D2
0x1800078c8  mov     [rdx], bp
0x1800078cb  jmp     short loc_1800078D2
0x1800078cd  mov     ecx, 8007000Eh
0x1800078d2  mov     eax, ecx
0x1800078d4  add     rsp, 30h
0x1800078d8  pop     r14
0x1800078da  pop     rdi
0x1800078db  pop     rsi
0x1800078dc  pop     rbp
0x1800078dd  pop     rbx
0x1800078de  retn
```
