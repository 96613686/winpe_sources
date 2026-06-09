# YReader::ParseDeclAttlistEnumeratedType(DeclAttDef *)

- ea: `0x1004058d0`
- end: `0x1004059ee`
- name: `?ParseDeclAttlistEnumeratedType@YReader@@AEAAXPEAVDeclAttDef@@@Z`
- size: `286`
- prototype: `void __fastcall(YReader *__hidden this, struct DeclAttDef *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x100405a00`

## callees

- `0x100401780`
- `0x1004018f0`
- `0x100401ab0`
- `0x1004058d0`
- `0x10040a020`
- `0x100415490`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseDeclAttlistEnumeratedType(YReader *this, struct DeclAttDef *a2)
{
  char *v2; // rbx
  YReader *v3; // rdi
  wchar_t i; // dx
  unsigned int v5; // esi
  signed int v6; // r8d
  char *v7; // rax
  __int64 v8; // rcx
  char *v9; // rax
  __int64 v10; // rcx
  int v11; // eax
  char *v12; // [rsp+20h] [rbp-18h] BYREF
  int v13; // [rsp+28h] [rbp-10h]

  v2 = (char *)a2 + 96;
  v3 = this;
  v12 = 0;
  v13 = 0;
  for ( i = 40; ; i = 124 )
  {
    YReader::SetTokenData3(this, i, (struct StringPtr *)v2);
    if ( (unsigned int)YReader::GetTokenDeclInner(v3) != 12 )
    {
      MXRRaiseException(-1072894407);
      __debugbreak();
    }
    if ( *(_QWORD *)v2 )
    {
      v5 = *((_DWORD *)v2 + 2);
      if ( v5 > 0x3FFFFFFF
        || (v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v3 + 13) + 96LL))(*((_QWORD *)v3 + 13)) + 2 * v5,
            v6 < 0) )
      {
        MXRRaiseException(-2147024882);
        JUMPOUT(0x1004059EDLL);
      }
      _mm_lfence();
      v7 = BlockAlloc::ReallocData((YReader *)((char *)v3 + 416), *(char **)v2, v6);
      v8 = *((unsigned int *)v2 + 2);
      *(_QWORD *)v2 = v7;
      v9 = &v7[2 * v8];
      v10 = *((_QWORD *)v3 + 13);
      v12 = v9;
      (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v10 + 104LL))(v10, &v12);
      *((_DWORD *)v2 + 2) += v13;
    }
    else
    {
      YReader::GetTokenData(v3, (struct StringPtr *)v2);
    }
    v11 = YReader::GetTokenDeclInner(v3) - 56;
    if ( !v11 )
      break;
    if ( v11 != 1 )
    {
      MXRRaiseException(-1072894419);
      __debugbreak();
    }
    this = v3;
  }
  YReader::SetTokenData3(v3, 0x29u, (struct StringPtr *)v2);
}

```

## disassembly

```asm
0x1004058d0  mov     [rsp+arg_0], rbx
0x1004058d5  mov     [rsp+arg_8], rsi
0x1004058da  push    rdi
0x1004058db  sub     rsp, 30h
0x1004058df  xor     eax, eax
0x1004058e1  lea     rbx, [rdx+60h]
0x1004058e5  mov     rdi, rcx
0x1004058e8  mov     [rsp+38h+var_18], rax
0x1004058ed  mov     [rsp+38h+var_10], eax
0x1004058f1  lea     edx, [rax+28h]; wchar_t
0x1004058f4  mov     r8, rbx; struct StringPtr *
0x1004058f7  call    ?SetTokenData3@YReader@@AEAAX_WPEAUStringPtr@@@Z; YReader::SetTokenData3(wchar_t,StringPtr *)
0x1004058fc  mov     rcx, rdi; this
0x1004058ff  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100405904  cmp     eax, 0Ch
0x100405907  jnz     loc_1004059CD
0x10040590d  cmp     qword ptr [rbx], 0
0x100405911  jnz     short loc_100405920
0x100405913  mov     rdx, rbx; struct StringPtr *
0x100405916  mov     rcx, rdi; this
0x100405919  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x10040591e  jmp     short loc_100405990
0x100405920  mov     esi, [rbx+8]
0x100405923  cmp     esi, 3FFFFFFFh
0x100405929  ja      loc_1004059E3
0x10040592f  mov     rcx, [rdi+68h]
0x100405933  mov     rax, [rcx]
0x100405936  mov     rax, [rax+60h]
0x10040593a  call    cs:__guard_dispatch_icall_fptr
0x100405940  lea     r8d, [rax+rsi*2]; unsigned int
0x100405944  test    r8d, r8d
0x100405947  js      loc_1004059E3
0x10040594d  lfence
0x100405950  mov     rdx, [rbx]; void *
0x100405953  lea     rcx, [rdi+1A0h]; this
0x10040595a  call    ?ReallocData@BlockAlloc@@QEAAPEAXPEAXK@Z; BlockAlloc::ReallocData(void *,ulong)
0x10040595f  mov     ecx, [rbx+8]
0x100405962  lea     rdx, [rsp+38h+var_18]
0x100405967  mov     [rbx], rax
0x10040596a  lea     rax, [rax+rcx*2]
0x10040596e  mov     rcx, [rdi+68h]
0x100405972  mov     [rsp+38h+var_18], rax
0x100405977  mov     rax, [rcx]
0x10040597a  mov     rax, [rax+68h]
0x10040597e  call    cs:__guard_dispatch_icall_fptr
0x100405984  mov     eax, [rsp+38h+var_10]
0x100405988  add     [rbx+8], eax
0x10040598b  nop     dword ptr [rax+rax+00h]
0x100405990  mov     rcx, rdi; this
0x100405993  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100405998  sub     eax, 38h ; '8'
0x10040599b  jz      short loc_1004059AD
0x10040599d  cmp     eax, 1
0x1004059a0  jnz     short loc_1004059D8
0x1004059a2  lea     edx, [rax+7Bh]
0x1004059a5  mov     rcx, rdi
0x1004059a8  jmp     loc_1004058F4
0x1004059ad  mov     edx, 29h ; ')'; wchar_t
0x1004059b2  mov     r8, rbx; struct StringPtr *
0x1004059b5  mov     rcx, rdi; this
0x1004059b8  call    ?SetTokenData3@YReader@@AEAAX_WPEAUStringPtr@@@Z; YReader::SetTokenData3(wchar_t,StringPtr *)
0x1004059bd  mov     rbx, [rsp+38h+arg_0]
0x1004059c2  mov     rsi, [rsp+38h+arg_8]
0x1004059c7  add     rsp, 30h
0x1004059cb  pop     rdi
0x1004059cc  retn
0x1004059cd  mov     ecx, 0C00CEE39h; int
0x1004059d2  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004059d7  int     3; Trap to Debugger
0x1004059d8  mov     ecx, 0C00CEE2Dh; int
0x1004059dd  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004059e2  int     3; Trap to Debugger
0x1004059e3  mov     ecx, 8007000Eh; int
0x1004059e8  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
