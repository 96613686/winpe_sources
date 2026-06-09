# std::deque<std::unique_ptr<OrchestratorSingleton::HeavyModuleData,std::default_delete<OrchestratorSingleton::HeavyModuleData>>,std::allocator<std::unique_ptr<OrchestratorSingleton::HeavyModuleData,std::default_delete<OrchestratorSingleton::HeavyModuleData>>>>::_Growmap(unsigned __int64)

- ea: `0x180016d44`
- end: `0x180016f13`
- name: `?_Growmap@?$deque@V?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@V?$allocator@V?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@@2@@std@@AEAAX_K@Z`
- size: `463`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180014f94`

## callees

- `0x180003304`
- `0x180003be4`
- `0x180003da4`
- `0x180004581`
- `0x180016d44`
- `0x180017158`
- `0x1800172f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::deque<std::unique_ptr<OrchestratorSingleton::HeavyModuleData>>::_Growmap(_QWORD *a1)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  size_t v5; // rcx
  _QWORD *v6; // r14
  void *v7; // rax
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rax
  __int64 v10; // r15
  __int64 v11; // rax
  unsigned __int64 v12; // rsi
  size_t v13; // rbx
  const void *v14; // rdx
  char *v15; // rbx
  size_t v16; // r8
  char *v17; // rcx
  __int64 v18; // rcx
  void *v19; // rax

  v2 = 1;
  v3 = a1[2];
  if ( v3 )
    v2 = v3;
  while ( v2 == v3 || v2 < 8 )
  {
    if ( 0xFFFFFFFFFFFFFFFLL - v2 < v2 )
      std::deque<std::unique_ptr<OrchestratorSingleton::HeavyModuleData>>::_Xlen();
    v2 *= 2LL;
  }
  v4 = a1[3];
  if ( v2 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_28;
  v5 = 8 * v2;
  if ( !(8 * v2) )
  {
    v6 = 0;
    goto LABEL_15;
  }
  if ( v5 < 0x1000 )
  {
    v6 = operator new(v5);
    goto LABEL_15;
  }
  if ( v5 + 39 < v5 )
LABEL_28:
    __scrt_throw_std_bad_array_new_length();
  v7 = operator new(v5 + 39);
  if ( !v7 )
    goto LABEL_24;
  v6 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v6 - 1) = v7;
LABEL_15:
  v8 = v4 >> 1;
  v9 = v2 >> 1;
  v10 = 8 * v8;
  while ( v2 <= v9 )
    v2 *= 2LL;
  v11 = a1[2];
  v12 = v2 - v11;
  v13 = 8 * v11 - v10;
  memmove_0(&v6[v8], (const void *)(a1[1] + v10), v13);
  v14 = (const void *)a1[1];
  v15 = (char *)&v6[v8] + v13;
  if ( v8 > v12 )
  {
    memmove_0(v15, v14, 8 * v12);
    memmove_0(v6, (const void *)(8 * v12 + a1[1]), v10 - 8 * v12);
    v17 = (char *)v6 + v10 - 8 * v12;
    v16 = 8 * v12;
  }
  else
  {
    memmove_0(v15, v14, 8 * v8);
    memset_0(&v15[v10], 0, 8 * (v12 - v8));
    v16 = 8 * v8;
    v17 = (char *)v6;
  }
  memset_0(v17, 0, v16);
  v18 = a1[1];
  if ( v18 )
  {
    if ( (unsigned __int64)(8LL * a1[2]) < 0x1000 )
    {
      v19 = (void *)a1[1];
    }
    else
    {
      v19 = *(void **)(v18 - 8);
      if ( (unsigned __int64)(v18 - (_QWORD)v19 - 8) > 0x1F )
LABEL_24:
        __fastfail(5u);
    }
    operator delete(v19);
  }
  a1[2] += v12;
  a1[1] = v6;
}

```

## disassembly

```asm
0x180016d44  push    rbx
0x180016d46  push    rbp
0x180016d47  push    rsi
0x180016d48  push    rdi
0x180016d49  push    r12
0x180016d4b  push    r14
0x180016d4d  push    r15
0x180016d4f  sub     rsp, 20h
0x180016d53  mov     rbp, rcx
0x180016d56  mov     esi, 1
0x180016d5b  mov     rcx, [rcx+10h]
0x180016d5f  test    rcx, rcx
0x180016d62  cmovnz  rsi, rcx
0x180016d66  mov     rax, rsi
0x180016d69  sub     rax, rcx
0x180016d6c  cmp     rax, 1
0x180016d70  jb      short loc_180016D78
0x180016d72  cmp     rsi, 8
0x180016d76  jnb     short loc_180016D93
0x180016d78  mov     rax, 0FFFFFFFFFFFFFFFh
0x180016d82  sub     rax, rsi
0x180016d85  cmp     rax, rsi
0x180016d88  jb      loc_180016F0D
0x180016d8e  add     rsi, rsi
0x180016d91  jmp     short loc_180016D66
0x180016d93  mov     rdi, [rbp+18h]
0x180016d97  mov     rax, 1FFFFFFFFFFFFFFFh
0x180016da1  cmp     rsi, rax
0x180016da4  ja      loc_180016F07
0x180016daa  lea     rcx, ds:0[rsi*8]; Size
0x180016db2  test    rcx, rcx
0x180016db5  jnz     short loc_180016DBC
0x180016db7  xor     r14d, r14d
0x180016dba  jmp     short loc_180016DF9
0x180016dbc  cmp     rcx, 1000h
0x180016dc3  jb      short loc_180016DF1
0x180016dc5  lea     rax, [rcx+27h]
0x180016dc9  cmp     rax, rcx
0x180016dcc  jbe     loc_180016F07
0x180016dd2  mov     rcx, rax; Size
0x180016dd5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016dda  test    rax, rax
0x180016ddd  jz      loc_180016EDE
0x180016de3  lea     r14, [rax+27h]
0x180016de7  and     r14, 0FFFFFFFFFFFFFFE0h
0x180016deb  mov     [r14-8], rax
0x180016def  jmp     short loc_180016DF9
0x180016df1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016df6  mov     r14, rax
0x180016df9  shr     rdi, 1
0x180016dfc  mov     rax, rsi
0x180016dff  shr     rax, 1
0x180016e02  lea     r15, ds:0[rdi*8]
0x180016e0a  lea     r12, [r15+r14]
0x180016e0e  jmp     short loc_180016E13
0x180016e10  add     rsi, rsi
0x180016e13  cmp     rsi, rax
0x180016e16  jbe     short loc_180016E10
0x180016e18  mov     rcx, [rbp+8]
0x180016e1c  mov     rax, [rbp+10h]
0x180016e20  sub     rsi, rax
0x180016e23  shl     rax, 3
0x180016e27  lea     rdx, [rcx+r15]; Src
0x180016e2b  sub     rax, rdx
0x180016e2e  lea     rbx, [rax+rcx]
0x180016e32  mov     rcx, r12; void *
0x180016e35  mov     r8, rbx; Size
0x180016e38  call    memmove_0
0x180016e3d  mov     rdx, [rbp+8]; Src
0x180016e41  add     rbx, r12
0x180016e44  mov     rcx, rbx; void *
0x180016e47  cmp     rdi, rsi
0x180016e4a  ja      short loc_180016E71
0x180016e4c  mov     r8, r15; Size
0x180016e4f  call    memmove_0
0x180016e54  mov     r8, rsi
0x180016e57  lea     rcx, [rbx+r15]; void *
0x180016e5b  sub     r8, rdi
0x180016e5e  xor     edx, edx; Val
0x180016e60  shl     r8, 3; Size
0x180016e64  call    memset_0
0x180016e69  mov     r8, r15
0x180016e6c  mov     rcx, r14
0x180016e6f  jmp     short loc_180016EA2
0x180016e71  lea     rdi, ds:0[rsi*8]
0x180016e79  mov     r8, rdi; Size
0x180016e7c  call    memmove_0
0x180016e81  mov     rax, [rbp+8]
0x180016e85  mov     rcx, r14; void *
0x180016e88  lea     rdx, [rdi+rax]; Src
0x180016e8c  sub     rax, rdx
0x180016e8f  lea     rbx, [rax+r15]
0x180016e93  mov     r8, rbx; Size
0x180016e96  call    memmove_0
0x180016e9b  lea     rcx, [rbx+r14]; void *
0x180016e9f  mov     r8, rdi; Size
0x180016ea2  xor     edx, edx; Val
0x180016ea4  call    memset_0
0x180016ea9  mov     rcx, [rbp+8]
0x180016ead  test    rcx, rcx
0x180016eb0  jz      short loc_180016EF0
0x180016eb2  mov     rax, [rbp+10h]
0x180016eb6  lea     rdx, ds:0[rax*8]; unsigned __int64
0x180016ebe  cmp     rdx, 1000h
0x180016ec5  jb      short loc_180016EE5
0x180016ec7  mov     rax, [rcx-8]
0x180016ecb  sub     rcx, rax
0x180016ece  sub     rcx, 8
0x180016ed2  cmp     rcx, 1Fh
0x180016ed6  ja      short loc_180016EDE
0x180016ed8  add     rdx, 27h ; '''
0x180016edc  jmp     short loc_180016EE8
0x180016ede  mov     ecx, 5
0x180016ee3  int     29h; Win8: RtlFailFast(ecx)
0x180016ee5  mov     rax, rcx
0x180016ee8  mov     rcx, rax; void *
0x180016eeb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016ef0  add     [rbp+10h], rsi
0x180016ef4  mov     [rbp+8], r14
0x180016ef8  add     rsp, 20h
0x180016efc  pop     r15
0x180016efe  pop     r14
0x180016f00  pop     r12
0x180016f02  pop     rdi
0x180016f03  pop     rsi
0x180016f04  pop     rbp
0x180016f05  pop     rbx
0x180016f06  retn
0x180016f07  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180016f0d  call    ?_Xlen@?$deque@V?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@V?$allocator@V?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@@2@@std@@CAXXZ; std::deque<std::unique_ptr<OrchestratorSingleton::HeavyModuleData>>::_Xlen(void)
```
