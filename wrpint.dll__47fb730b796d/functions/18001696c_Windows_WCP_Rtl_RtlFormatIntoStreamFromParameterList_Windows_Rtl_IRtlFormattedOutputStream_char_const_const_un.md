# Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)

- ea: `0x18001696c`
- end: `0x180016b2a`
- name: `?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z`
- size: `446`
- prototype: `void __fastcall(Windows::WCP::Rtl *this, struct Windows::Rtl::IRtlFormattedOutputStream *, const char *const, __int64)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x1800020d0`
- `0x1800022c4`
- `0x18000a384`
- `0x18000a570`
- `0x1800118a4`
- `0x1800119e8`
- `0x1800134c0`
- `0x1800136a0`

## callees

- `0x18001696c`
- `0x18001b786`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `msvcrt!sprintf_s` at `0x180016a71`
- `msvcrt!sprintf_s` at `0x180016a71`

## pseudocode

```c
void __fastcall Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(
        Windows::WCP::Rtl *this,
        struct Windows::Rtl::IRtlFormattedOutputStream *a2,
        const char *const a3,
        __int64 a4)
{
  char v4; // al
  const char *v5; // rbx
  const char *v8; // rdi
  unsigned __int64 v10; // r12
  __int64 v11; // rdx
  unsigned __int64 v12; // rsi
  char *v13; // rdx
  void (__fastcall *v14)(Windows::WCP::Rtl *, _QWORD); // rax
  char Buffer[16]; // [rsp+20h] [rbp-68h] BYREF
  __int128 v16; // [rsp+30h] [rbp-58h]

  v4 = *(_BYTE *)a2;
  v5 = (char *)a2 + 1;
  v8 = (const char *)a2;
  v10 = 0;
  while ( v4 )
  {
    switch ( v4 )
    {
      case '%':
        if ( ((*v5 - 123) & 0xFD) != 0 )
          goto LABEL_23;
        if ( v5 - 1 != v8 )
          (*(void (__fastcall **)(Windows::WCP::Rtl *, signed __int64, const char *))(*(_QWORD *)this + 280LL))(
            this,
            v5 - v8 - 1,
            v8);
        (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64, const char *))(*(_QWORD *)this + 280LL))(this, 1, v5++);
        break;
      case '{':
        if ( v5 - 1 != v8 )
        {
          v11 = v5 - v8 - 1;
LABEL_21:
          (*(void (__fastcall **)(Windows::WCP::Rtl *, __int64, const char *))(*(_QWORD *)this + 280LL))(this, v11, v8);
        }
        break;
      case '}':
        v12 = v10++;
        if ( v5 - v8 == 1 )
        {
LABEL_17:
          if ( v12 >= (unsigned __int64)a3 )
            goto LABEL_20;
        }
        else
        {
          v12 = 0;
          if ( !a3 )
            goto LABEL_20;
          while ( 1 )
          {
            v13 = *(char **)(a4 + 24 * v12);
            *(_OWORD *)Buffer = 0;
            v16 = 0;
            if ( !v13 )
            {
              sprintf_s(Buffer, 0x20u, "%zu", v12);
              v13 = Buffer;
            }
            if ( !strncmp_0(v8, v13, (unsigned int)((_DWORD)v5 - (_DWORD)v8 - 1)) )
              break;
            if ( ++v12 >= (unsigned __int64)a3 )
              goto LABEL_17;
          }
        }
        v14 = *(void (__fastcall **)(Windows::WCP::Rtl *, _QWORD))(a4 + 24 * v12 + 8);
        if ( !v14 )
        {
LABEL_20:
          v11 = v5 - v8 - 1;
          goto LABEL_21;
        }
        v14(this, *(_QWORD *)(a4 + 24 * v12 + 16));
        break;
      default:
        goto LABEL_23;
    }
    v8 = v5;
LABEL_23:
    v4 = *v5++;
  }
  if ( v5 - 1 != v8 )
    (*(void (__fastcall **)(Windows::WCP::Rtl *, signed __int64, const char *))(*(_QWORD *)this + 280LL))(
      this,
      v5 - v8 - 1,
      v8);
}

```

## disassembly

```asm
0x18001696c  mov     [rsp+arg_10], rbx
0x180016971  push    rbp
0x180016972  push    rsi
0x180016973  push    rdi
0x180016974  push    r12
0x180016976  push    r13
0x180016978  push    r14
0x18001697a  push    r15
0x18001697c  sub     rsp, 50h
0x180016980  mov     rax, cs:__security_cookie
0x180016987  xor     rax, rsp
0x18001698a  mov     [rsp+88h+var_48], rax
0x18001698f  mov     al, [rdx]
0x180016991  lea     rbx, [rdx+1]
0x180016995  mov     r13, r9
0x180016998  mov     r15, r8
0x18001699b  mov     rdi, rdx
0x18001699e  mov     r14, rcx
0x1800169a1  xor     r12d, r12d
0x1800169a4  jmp     loc_180016AD8
0x1800169a9  cmp     al, 25h ; '%'
0x1800169ab  jnz     short loc_180016A02
0x1800169ad  mov     al, [rbx]
0x1800169af  sub     al, 7Bh ; '{'
0x1800169b1  test    al, 0FDh
0x1800169b3  jnz     loc_180016AD0
0x1800169b9  lea     rax, [rbx-1]
0x1800169bd  cmp     rax, rdi
0x1800169c0  jz      short loc_1800169E0
0x1800169c2  mov     rax, [r14]
0x1800169c5  mov     rdx, rbx
0x1800169c8  sub     rdx, rdi
0x1800169cb  mov     r8, rdi
0x1800169ce  dec     rdx
0x1800169d1  mov     rcx, r14
0x1800169d4  mov     rax, [rax+118h]
0x1800169db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169e0  mov     rax, [r14]
0x1800169e3  mov     r8, rbx
0x1800169e6  mov     edx, 1
0x1800169eb  mov     rcx, r14
0x1800169ee  mov     rax, [rax+118h]
0x1800169f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169fa  inc     rbx
0x1800169fd  jmp     loc_180016ACD
0x180016a02  cmp     al, 7Bh ; '{'
0x180016a04  jnz     short loc_180016A21
0x180016a06  lea     rax, [rbx-1]
0x180016a0a  cmp     rax, rdi
0x180016a0d  jz      loc_180016ACD
0x180016a13  mov     rdx, rbx
0x180016a16  sub     rdx, rdi
0x180016a19  dec     rdx
0x180016a1c  jmp     loc_180016AB8
0x180016a21  cmp     al, 7Dh ; '}'
0x180016a23  jnz     loc_180016AD0
0x180016a29  mov     rbp, rbx
0x180016a2c  mov     rsi, r12
0x180016a2f  sub     rbp, rdi
0x180016a32  inc     r12
0x180016a35  sub     rbp, 1
0x180016a39  jz      short loc_180016A93
0x180016a3b  xor     esi, esi
0x180016a3d  test    r15, r15
0x180016a40  jz      short loc_180016AB5
0x180016a42  xorps   xmm0, xmm0
0x180016a45  lea     rax, [rsi+rsi*2]
0x180016a49  mov     rdx, [r13+rax*8+0]
0x180016a4e  movups  xmmword ptr [rsp+88h+Buffer], xmm0
0x180016a53  movups  [rsp+88h+var_58], xmm0
0x180016a58  test    rdx, rdx
0x180016a5b  jnz     short loc_180016A7C
0x180016a5d  mov     r9, rsi
0x180016a60  lea     r8, Format; "%zu"
0x180016a67  mov     edx, 20h ; ' '; BufferCount
0x180016a6c  lea     rcx, [rsp+88h+Buffer]; Buffer
0x180016a71  call    cs:__imp_sprintf_s
0x180016a77  lea     rdx, [rsp+88h+Buffer]; Str2
0x180016a7c  mov     r8d, ebp; MaxCount
0x180016a7f  mov     rcx, rdi; Str1
0x180016a82  call    strncmp_0
0x180016a87  test    eax, eax
0x180016a89  jz      short loc_180016A98
0x180016a8b  inc     rsi
0x180016a8e  cmp     rsi, r15
0x180016a91  jb      short loc_180016A42
0x180016a93  cmp     rsi, r15
0x180016a96  jnb     short loc_180016AB5
0x180016a98  lea     rdx, [rsi+rsi*2]
0x180016a9c  mov     rax, [r13+rdx*8+8]
0x180016aa1  test    rax, rax
0x180016aa4  jz      short loc_180016AB5
0x180016aa6  mov     rdx, [r13+rdx*8+10h]
0x180016aab  mov     rcx, r14
0x180016aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ab3  jmp     short loc_180016ACD
0x180016ab5  mov     rdx, rbp
0x180016ab8  mov     rax, [r14]
0x180016abb  mov     r8, rdi
0x180016abe  mov     rcx, r14
0x180016ac1  mov     rax, [rax+118h]
0x180016ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016acd  mov     rdi, rbx
0x180016ad0  mov     rax, rbx
0x180016ad3  mov     al, [rbx]
0x180016ad5  inc     rbx
0x180016ad8  test    al, al
0x180016ada  jnz     loc_1800169A9
0x180016ae0  lea     rax, [rbx-1]
0x180016ae4  cmp     rax, rdi
0x180016ae7  jz      short loc_180016B05
0x180016ae9  mov     rax, [r14]
0x180016aec  sub     rbx, rdi
0x180016aef  mov     r8, rdi
0x180016af2  mov     rcx, r14
0x180016af5  mov     rax, [rax+118h]
0x180016afc  lea     rdx, [rbx-1]
0x180016b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b05  mov     rcx, [rsp+88h+var_48]
0x180016b0a  xor     rcx, rsp; StackCookie
0x180016b0d  call    __security_check_cookie
0x180016b12  mov     rbx, [rsp+88h+arg_10]
0x180016b1a  add     rsp, 50h
0x180016b1e  pop     r15
0x180016b20  pop     r14
0x180016b22  pop     r13
0x180016b24  pop     r12
0x180016b26  pop     rdi
0x180016b27  pop     rsi
0x180016b28  pop     rbp
0x180016b29  retn
```
