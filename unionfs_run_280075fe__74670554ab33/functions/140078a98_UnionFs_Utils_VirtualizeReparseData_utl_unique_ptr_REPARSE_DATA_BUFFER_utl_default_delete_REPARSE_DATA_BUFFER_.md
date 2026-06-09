# UnionFs::Utils::VirtualizeReparseData(utl::unique_ptr<_REPARSE_DATA_BUFFER,utl::default_delete<_REPARSE_DATA_BUFFER>> &,ulong &,UnionFs::UfsUnionCtx const &,UnionFs::StackEventTracer &)

- ea: `0x140078a98`
- end: `0x140078dc0`
- name: `?VirtualizeReparseData@Utils@UnionFs@@YAJAEAV?$unique_ptr@U_REPARSE_DATA_BUFFER@@U?$default_delete@U_REPARSE_DATA_BUFFER@@@utl@@@utl@@AEAKAEBVUfsUnionCtx@2@AEAVStackEventTracer@2@@Z`
- size: `808`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14006c1fc`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140067958`
- `0x140076fd8`
- `0x140078a98`
- `0x140079c48`
- `0x14007b900`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140078d37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078d8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078d37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078d8c`

## string_xrefs

- `0x140078b70`: `UnionFs::Utils::VirtualizeReparseData`
- `0x140078bd7`: `UnionFs::Utils::VirtualizeReparseData`
- `0x140078c53`: `UnionFs::Utils::VirtualizeReparseData`
- `0x140078d69`: `UnionFs::Utils::VirtualizeReparseData`
- `0x140078b5f`: `PUSH: Computing munged substitute name`
- `0x140078c40`: `ORIGIN: Allocating virtualized reparse buffer`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::VirtualizeReparseData(
        int **a1,
        unsigned int *a2,
        __int64 a3,
        struct UnionFs::StackEventTracer *a4)
{
  int *v4; // r10
  int v5; // esi
  int v7; // r14d
  unsigned __int64 v8; // rax
  struct _UNICODE_STRING *v9; // rdx
  int v10; // ebx
  int v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // r8
  unsigned __int16 v14; // r13
  _WORD *v15; // rdi
  unsigned __int16 v16; // bx
  _DWORD *v17; // rcx
  size_t v18; // r8
  __int64 v19; // rcx
  int *v20; // rcx
  const char *v22; // [rsp+28h] [rbp-38h]
  unsigned int v23; // [rsp+30h] [rbp-30h]
  PVOID P; // [rsp+38h] [rbp-28h] BYREF
  void *Src[2]; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING String2; // [rsp+50h] [rbp-10h] BYREF
  int v27; // [rsp+A0h] [rbp+40h]

  v4 = *a1;
  v5 = (int)a4;
  v7 = **a1;
  String2 = 0;
  if ( v7 == -1610612724 )
  {
    v27 = v4[4];
    if ( (v27 & 1) == 0 )
    {
      String2.Length = *((_WORD *)v4 + 5);
      String2.MaximumLength = *((_WORD *)v4 + 5);
      v8 = ((unsigned __int64)*((unsigned __int16 *)v4 + 4) >> 1) + 10;
      goto LABEL_6;
    }
  }
  else if ( v7 == -1610612733 )
  {
    String2.Length = *((_WORD *)v4 + 5);
    String2.MaximumLength = *((_WORD *)v4 + 5);
    v8 = ((unsigned __int64)*((unsigned __int16 *)v4 + 4) >> 1) + 8;
    v27 = 0;
LABEL_6:
    String2.Buffer = (PWSTR)v4 + v8;
    *(_OWORD *)Src = 0;
    v10 = UnionFs::Utils::ScratchRelativizeSubstituteName(&String2, a3, (PUNICODE_STRING)Src, a4);
    if ( v10 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v10,
        v5,
        (struct UnionFs::StackEventTracer *)0x6C700210C30LL,
        (unsigned __int64)"UnionFs::Utils::VirtualizeReparseData",
        "PUSH: Computing munged substitute name",
        v22);
LABEL_30:
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)Src, v9);
      return (unsigned int)v10;
    }
    if ( !Src[1] )
    {
LABEL_9:
      v10 = 0;
      goto LABEL_30;
    }
    v11 = 20;
    if ( v7 == -1610612724 )
    {
      v12 = 2 * LOWORD(Src[0]);
      if ( v12 > 0xFFFF )
      {
        v13 = 0x6C900210C43LL;
LABEL_14:
        v10 = -1073741675;
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)0xC0000095LL,
          v5,
          (struct UnionFs::StackEventTracer *)v13,
          (unsigned __int64)"UnionFs::Utils::VirtualizeReparseData",
          "API: Arithmetic error",
          v22);
        goto LABEL_30;
      }
    }
    else
    {
      v11 = 16;
      if ( (unsigned __int16)(LOWORD(Src[0]) + 2) < LOWORD(Src[0]) )
      {
        v13 = 0x6CA00210C4DLL;
        goto LABEL_14;
      }
      v12 = 2 * (unsigned __int16)(LOWORD(Src[0]) + 2);
      if ( v12 > 0xFFFF )
      {
        v13 = 0x6CB00210C52LL;
        goto LABEL_14;
      }
    }
    v14 = v12;
    v23 = v11 + (unsigned __int16)v12;
    utl::make_unique_pool<enum gsl::byte [0],256,1651656277,0>(&P, v23);
    v15 = P;
    if ( !P )
    {
      v10 = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        v5,
        (struct UnionFs::StackEventTracer *)0x6C800210C60LL,
        (unsigned __int64)"UnionFs::Utils::VirtualizeReparseData",
        "ORIGIN: Allocating virtualized reparse buffer",
        v22);
      goto LABEL_30;
    }
    *(_DWORD *)P = v7;
    v16 = v14 + v11 - 8;
    if ( v16 < v14 )
    {
      v15[2] = -1;
      v10 = -1073741675;
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)0xC0000095LL,
        v5,
        (struct UnionFs::StackEventTracer *)0x6CF00210C6BLL,
        (unsigned __int64)"UnionFs::Utils::VirtualizeReparseData",
        "API: Arithmetic error",
        v22);
      if ( v15 )
        ExFreePoolWithTag(v15, 0);
      goto LABEL_30;
    }
    v15[2] = v16;
    v15[3] = *((_WORD *)*a1 + 3);
    v17 = v15 + 8;
    if ( v7 == -1610612724 )
    {
      *v17 = v27;
      v15[6] = 0;
      v15[7] = Src[0];
      v15[4] = Src[0];
      v15[5] = Src[0];
      memmove(v15 + 10, Src[1], LOWORD(Src[0]));
      v18 = LOWORD(Src[0]);
      v19 = LOWORD(Src[0]) + 20LL;
    }
    else
    {
      v15[4] = 0;
      v15[5] = Src[0];
      v15[6] = LOWORD(Src[0]) + 2;
      v15[7] = Src[0];
      memmove(v17, Src[1], LOWORD(Src[0]));
      v18 = LOWORD(Src[0]);
      v19 = LOWORD(Src[0]) + 18LL;
    }
    memmove((char *)v15 + v19, Src[1], v18);
    v20 = *a1;
    *a1 = (int *)v15;
    if ( v20 )
      ExFreePoolWithTag(v20, 0);
    *a2 = v23;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x140078a98  mov     [rsp-38h+arg_10], rbx
0x140078a9d  mov     [rsp-38h+arg_8], rdx
0x140078aa2  push    rbp
0x140078aa3  push    rsi
0x140078aa4  push    rdi
0x140078aa5  push    r12
0x140078aa7  push    r13
0x140078aa9  push    r14
0x140078aab  push    r15
0x140078aad  mov     rbp, rsp
0x140078ab0  sub     rsp, 60h
0x140078ab4  mov     r10, [rcx]
0x140078ab7  mov     edi, 0A000000Ch
0x140078abc  xorps   xmm0, xmm0
0x140078abf  mov     rsi, r9
0x140078ac2  mov     r11, r8
0x140078ac5  mov     r12, rcx
0x140078ac8  mov     r14d, [r10]
0x140078acb  movdqa  xmmword ptr [rbp+String2.Length], xmm0
0x140078ad0  cmp     r14d, edi
0x140078ad3  jnz     short loc_140078B0B
0x140078ad5  mov     edi, [r10+10h]
0x140078ad9  mov     [rbp+arg_0], edi
0x140078adc  test    dil, 1
0x140078ae0  jnz     loc_140078DA5
0x140078ae6  movzx   eax, word ptr [r10+0Ah]
0x140078aeb  mov     edi, 0A000000Ch
0x140078af0  mov     [rbp+String2.Length], ax
0x140078af4  movzx   eax, word ptr [r10+0Ah]
0x140078af9  mov     [rbp+String2.MaximumLength], ax
0x140078afd  movzx   eax, word ptr [r10+8]
0x140078b02  shr     rax, 1
0x140078b05  add     rax, 0Ah
0x140078b09  jmp     short loc_140078B3D
0x140078b0b  cmp     r14d, 0A0000003h
0x140078b12  jnz     loc_140078DA5
0x140078b18  movzx   eax, word ptr [r10+0Ah]
0x140078b1d  mov     [rbp+String2.Length], ax
0x140078b21  movzx   eax, word ptr [r10+0Ah]
0x140078b26  mov     [rbp+String2.MaximumLength], ax
0x140078b2a  movzx   eax, word ptr [r10+8]
0x140078b2f  shr     rax, 1
0x140078b32  add     rax, 8
0x140078b36  mov     [rbp+arg_0], 0
0x140078b3d  lea     rax, [r10+rax*2]
0x140078b41  mov     rdx, r11; int
0x140078b44  lea     r8, [rbp+Src]; UnicodeString
0x140078b48  mov     [rbp+String2.Buffer], rax
0x140078b4c  lea     rcx, [rbp+String2]; String2
0x140078b50  movups  xmmword ptr [rbp+Src], xmm0
0x140078b54  call    ?ScratchRelativizeSubstituteName@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBVUfsUnionCtx@2@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::ScratchRelativizeSubstituteName(_UNICODE_STRING const &,UnionFs::UfsUnionCtx const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x140078b59  mov     ebx, eax
0x140078b5b  test    eax, eax
0x140078b5d  jns     short loc_140078B8B
0x140078b5f  lea     rax, aPushComputingM; "PUSH: Computing munged substitute name"
0x140078b66  mov     r8, 6C700210C30h; struct UnionFs::StackEventTracer *
0x140078b70  lea     r9, aUnionfsUtilsVi_0; "UnionFs::Utils::VirtualizeReparseData"
0x140078b77  mov     [rsp+60h+var_40], rax; char *
0x140078b7c  mov     rdx, rsi; int
0x140078b7f  mov     ecx, ebx; this
0x140078b81  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140078b86  jmp     loc_140078D98
0x140078b8b  cmp     [rbp+Src+8], 0
0x140078b90  jnz     short loc_140078B99
0x140078b92  xor     ebx, ebx
0x140078b94  jmp     loc_140078D98
0x140078b99  mov     ebx, 14h
0x140078b9e  cmp     r14d, edi
0x140078ba1  lea     eax, [rbx-4]
0x140078ba4  cmovnz  ebx, eax
0x140078ba7  jnz     short loc_140078BEB
0x140078ba9  movzx   eax, word ptr [rbp+Src]
0x140078bad  mov     r15d, 0FFFFh
0x140078bb3  add     eax, eax
0x140078bb5  cmp     eax, r15d
0x140078bb8  jbe     short loc_140078C21
0x140078bba  mov     r8, 6C900210C43h; struct UnionFs::StackEventTracer *
0x140078bc4  lea     rax, aApiArithmeticE; "API: Arithmetic error"
0x140078bcb  mov     ebx, 0C0000095h
0x140078bd0  mov     ecx, ebx; this
0x140078bd2  mov     [rsp+60h+var_40], rax; char *
0x140078bd7  lea     r9, aUnionfsUtilsVi_0; "UnionFs::Utils::VirtualizeReparseData"
0x140078bde  mov     rdx, rsi; int
0x140078be1  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140078be6  jmp     loc_140078D98
0x140078beb  movzx   eax, word ptr [rbp+Src]
0x140078bef  add     ax, 2
0x140078bf3  cmp     ax, word ptr [rbp+Src]
0x140078bf7  jnb     short loc_140078C05
0x140078bf9  mov     r8, 6CA00210C4Dh
0x140078c03  jmp     short loc_140078BC4
0x140078c05  movzx   eax, ax
0x140078c08  mov     r15d, 0FFFFh
0x140078c0e  add     eax, eax
0x140078c10  cmp     eax, r15d
0x140078c13  jbe     short loc_140078C21
0x140078c15  mov     r8, 6CB00210C52h
0x140078c1f  jmp     short loc_140078BC4
0x140078c21  movzx   r13d, ax
0x140078c25  lea     rcx, [rbp+P]
0x140078c29  lea     eax, [rbx+r13]
0x140078c2d  mov     edx, eax
0x140078c2f  mov     [rbp+var_30], eax
0x140078c32  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GCHCEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1651656277,0>(unsigned __int64)
0x140078c37  mov     rdi, [rbp+P]
0x140078c3b  test    rdi, rdi
0x140078c3e  jnz     short loc_140078C71
0x140078c40  lea     rax, aOriginAllocati_54; "ORIGIN: Allocating virtualized reparse "...
0x140078c47  mov     ebx, 0C000009Ah
0x140078c4c  mov     ecx, ebx; this
0x140078c4e  mov     [rsp+60h+var_40], rax; char *
0x140078c53  lea     r9, aUnionfsUtilsVi_0; "UnionFs::Utils::VirtualizeReparseData"
0x140078c5a  mov     r8, 6C800210C60h; struct UnionFs::StackEventTracer *
0x140078c64  mov     rdx, rsi; int
0x140078c67  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140078c6c  jmp     loc_140078D98
0x140078c71  sub     bx, 8
0x140078c75  mov     [rdi], r14d
0x140078c78  add     bx, r13w
0x140078c7c  cmp     bx, r13w
0x140078c80  jb      loc_140078D51
0x140078c86  mov     [rdi+4], bx
0x140078c8a  mov     rax, [r12]
0x140078c8e  movzx   ecx, word ptr [rax+6]
0x140078c92  mov     [rdi+6], cx
0x140078c96  lea     rcx, [rdi+10h]; void *
0x140078c9a  cmp     r14d, 0A000000Ch
0x140078ca1  jnz     short loc_140078CE3
0x140078ca3  mov     eax, [rbp+arg_0]
0x140078ca6  mov     [rcx], eax
0x140078ca8  xor     eax, eax
0x140078caa  mov     [rdi+0Ch], ax
0x140078cae  lea     rcx, [rdi+14h]; void *
0x140078cb2  movzx   eax, word ptr [rbp+Src]
0x140078cb6  mov     [rdi+0Eh], ax
0x140078cba  movzx   eax, word ptr [rbp+Src]
0x140078cbe  mov     [rdi+8], ax
0x140078cc2  movzx   eax, word ptr [rbp+Src]
0x140078cc6  mov     [rdi+0Ah], ax
0x140078cca  movzx   r8d, word ptr [rbp+Src]; Size
0x140078ccf  mov     rdx, [rbp+Src+8]; Src
0x140078cd3  call    memmove
0x140078cd8  movzx   r8d, word ptr [rbp+Src]
0x140078cdd  lea     rcx, [r8+14h]
0x140078ce1  jmp     short loc_140078D1C
0x140078ce3  xor     eax, eax
0x140078ce5  mov     [rdi+8], ax
0x140078ce9  movzx   eax, word ptr [rbp+Src]
0x140078ced  mov     [rdi+0Ah], ax
0x140078cf1  movzx   eax, word ptr [rbp+Src]
0x140078cf5  add     ax, 2
0x140078cf9  mov     [rdi+0Ch], ax
0x140078cfd  movzx   eax, word ptr [rbp+Src]
0x140078d01  mov     [rdi+0Eh], ax
0x140078d05  movzx   r8d, word ptr [rbp+Src]; Size
0x140078d0a  mov     rdx, [rbp+Src+8]; Src
0x140078d0e  call    memmove
0x140078d13  movzx   r8d, word ptr [rbp+Src]; Size
0x140078d18  lea     rcx, [r8+12h]
0x140078d1c  mov     rdx, [rbp+Src+8]; Src
0x140078d20  add     rcx, rdi; void *
0x140078d23  call    memmove
0x140078d28  mov     rcx, [r12]; P
0x140078d2c  mov     [r12], rdi
0x140078d30  test    rcx, rcx
0x140078d33  jz      short loc_140078D43
0x140078d35  xor     edx, edx; Tag
0x140078d37  call    cs:__imp_ExFreePoolWithTag
0x140078d3e  nop     dword ptr [rax+rax+00h]
0x140078d43  mov     rcx, [rbp+arg_8]
0x140078d47  mov     eax, [rbp+var_30]
0x140078d4a  mov     [rcx], eax
0x140078d4c  jmp     loc_140078B92
0x140078d51  lea     rax, aApiArithmeticE; "API: Arithmetic error"
0x140078d58  mov     [rdi+4], r15w
0x140078d5d  mov     ebx, 0C0000095h
0x140078d62  mov     [rsp+60h+var_40], rax; char *
0x140078d67  mov     ecx, ebx; this
0x140078d69  lea     r9, aUnionfsUtilsVi_0; "UnionFs::Utils::VirtualizeReparseData"
0x140078d70  mov     r8, 6CF00210C6Bh; struct UnionFs::StackEventTracer *
0x140078d7a  mov     rdx, rsi; int
0x140078d7d  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140078d82  test    rdi, rdi
0x140078d85  jz      short loc_140078D98
0x140078d87  xor     edx, edx; Tag
0x140078d89  mov     rcx, rdi; P
0x140078d8c  call    cs:__imp_ExFreePoolWithTag
0x140078d93  nop     dword ptr [rax+rax+00h]
0x140078d98  lea     rcx, [rbp+Src]; UnicodeString
0x140078d9c  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140078da1  mov     eax, ebx
0x140078da3  jmp     short loc_140078DA7
0x140078da5  xor     eax, eax
0x140078da7  mov     rbx, [rsp+60h+arg_10]
0x140078daf  add     rsp, 60h
0x140078db3  pop     r15
0x140078db5  pop     r14
0x140078db7  pop     r13
0x140078db9  pop     r12
0x140078dbb  pop     rdi
0x140078dbc  pop     rsi
0x140078dbd  pop     rbp
0x140078dbe  retn
```
