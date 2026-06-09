# YReader::GetTokenDeclOuter(void)

- ea: `0x10040a4c0`
- end: `0x10040a749`
- name: `?GetTokenDeclOuter@YReader@@AEAAHXZ`
- size: `649`
- prototype: `__int64 __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x100408ea0`
- `0x100409110`

## callees

- `0x100401780`
- `0x100409390`
- `0x10040a4c0`
- `0x10040a750`
- `0x10040aa00`
- `0x100415560`
- `0x100416bc0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall YReader::GetTokenDeclOuter(YReader *this)
{
  __int64 result; // rax
  void (__fastcall *v3)(const void **); // rax
  __int64 v4; // rax
  unsigned __int64 v5; // rsi
  void (__fastcall *v6)(const void **); // rax
  unsigned int v7; // eax
  struct BlockAlloc::Header *v8; // rbx
  __int64 v9; // rbp
  __int64 v10; // rdx
  __int64 v11; // rcx
  struct BlockAlloc::Header *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rbx
  _QWORD *v15; // rax
  bool v16; // cc
  __int128 v17; // xmm0
  _OWORD v18[3]; // [rsp+20h] [rbp-38h] BYREF

  do
  {
    while ( 1 )
    {
      (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
      result = *((unsigned int *)this + 28);
      if ( (_DWORD)result != 19 )
        break;
      v4 = *((_QWORD *)this + 55);
      *(_QWORD *)&v18[0] = 0;
      DWORD2(v18[0]) = 0;
      v5 = *(_QWORD *)(v4 + 16);
      v6 = (void (__fastcall *)(const void **))*((_QWORD *)this + 188);
      if ( (v6 != YReader::ParseSubsetInternal || v6 && *((_DWORD *)this + 378))
        && (v6 != YReader::ParseSubsetExternal || v6 && *((_DWORD *)this + 378)) )
      {
        MXRRaiseException(-1072894419);
        __debugbreak();
      }
      v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
      v8 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
      v9 = v7;
      v10 = *((_QWORD *)v8 + 2);
      if ( *((_DWORD *)v8 + 6) - (int)v10 < v7 )
      {
        v11 = *((_QWORD *)v8 + 1);
        if ( v11 )
        {
          while ( 1 )
          {
            v8 = (struct BlockAlloc::Header *)v11;
            if ( *(_DWORD *)(v11 + 24) - (int)v11 - 32 >= v7 )
              break;
            v11 = *(_QWORD *)(v11 + 8);
            if ( !v11 )
              goto LABEL_22;
          }
          *(_QWORD *)(v11 + 16) = v11 + 32;
        }
        else
        {
LABEL_22:
          _mm_lfence();
          v12 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v7, v8);
          *((_QWORD *)v8 + 1) = v12;
          v8 = v12;
        }
        *((_QWORD *)this + 55) = v8;
        v10 = *((_QWORD *)v8 + 2);
      }
      *((_QWORD *)v8 + 2) += v9;
      v13 = *((_QWORD *)this + 13);
      *(_QWORD *)&v18[0] = v10;
      (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v13 + 104LL))(v13, v18);
      v14 = _htable<DeclEntity>::lookup((char *)this + 1376, v18);
      v15 = (_QWORD *)*((_QWORD *)this + 55);
      if ( (unsigned __int64)v15 < v5 )
      {
        v16 = v5 <= v15[2];
        goto LABEL_26;
      }
      do
      {
        do
        {
          v15 = (_QWORD *)*v15;
          *((_QWORD *)this + 55) = v15;
          if ( !v15 )
          {
            MXRRaiseException(-2147467259);
            JUMPOUT(0x10040A748LL);
          }
        }
        while ( (unsigned __int64)v15 >= v5 );
        v16 = v5 <= v15[3];
LABEL_26:
        ;
      }
      while ( !v16 );
      v15[2] = v5;
      if ( YReader::HandleEntity(this, (struct DeclEntity *)v14, this) )
      {
        v17 = *(_OWORD *)(v14 + 80);
        *(_BYTE *)(v14 + 129) = 0;
        v18[0] = v17;
        if ( *(_QWORD *)(v14 + 96) )
          return 19;
        (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
        if ( *((_DWORD *)this + 28) == 1 )
        {
          YReader::ParseTextDecl(this);
          return 19;
        }
        if ( *((_DWORD *)this + 28) != 59 )
          return 19;
        YReader::HandleEntityEnd(this, this);
      }
      else if ( !*((_BYTE *)this + 1787) )
      {
        *((_BYTE *)this + 1795) = 1;
      }
    }
    if ( (_DWORD)result != 59 )
      return result;
  }
  while ( *((_BYTE *)YReader::HandleEntityEnd(this, this) + 129) );
  v3 = (void (__fastcall *)(const void **))*((_QWORD *)this + 188);
  if ( (v3 != YReader::ParseSubsetInternal || v3 && *((_DWORD *)this + 378))
    && (v3 != YReader::ParseSubsetExternal || v3 && *((_DWORD *)this + 378)) )
  {
    MXRRaiseException(-1072894396);
    __debugbreak();
  }
  return 59;
}

```

## disassembly

```asm
0x10040a4c0  mov     [rsp+arg_0], rbx
0x10040a4c5  mov     [rsp+arg_8], rbp
0x10040a4ca  mov     [rsp+arg_10], rsi
0x10040a4cf  push    rdi
0x10040a4d0  push    r12
0x10040a4d2  push    r13
0x10040a4d4  push    r14
0x10040a4d6  push    r15
0x10040a4d8  sub     rsp, 30h
0x10040a4dc  mov     rdi, rcx
0x10040a4df  lea     r13, ?ParseSubsetInternal@YReader@@AEAAXXZ; YReader::ParseSubsetInternal(void)
0x10040a4e6  xor     r15d, r15d
0x10040a4e9  lea     r12, ?ParseSubsetExternal@YReader@@AEAAXXZ; YReader::ParseSubsetExternal(void)
0x10040a4f0  mov     rax, [rdi+0D8h]
0x10040a4f7  lea     rcx, [rdi+28h]
0x10040a4fb  call    cs:__guard_dispatch_icall_fptr
0x10040a501  mov     eax, [rdi+70h]
0x10040a504  cmp     eax, 13h
0x10040a507  jz      short loc_10040A579
0x10040a509  cmp     eax, 3Bh ; ';'
0x10040a50c  jnz     short loc_10040A55C
0x10040a50e  mov     rdx, rdi; void *
0x10040a511  mov     rcx, rdi; this
0x10040a514  call    ?HandleEntityEnd@YReader@@AEAAPEAVDeclEntity@@PEAX@Z; YReader::HandleEntityEnd(void *)
0x10040a519  cmp     [rax+81h], r15b
0x10040a520  jnz     short loc_10040A4F0
0x10040a522  mov     rax, [rdi+5E0h]
0x10040a529  cmp     rax, r13
0x10040a52c  jnz     short loc_10040A53C
0x10040a52e  test    rax, rax
0x10040a531  jz      short loc_10040A557
0x10040a533  cmp     [rdi+5E8h], r15d
0x10040a53a  jz      short loc_10040A557
0x10040a53c  cmp     rax, r12
0x10040a53f  jnz     loc_10040A733
0x10040a545  test    rax, rax
0x10040a548  jz      short loc_10040A557
0x10040a54a  cmp     [rdi+5E8h], r15d
0x10040a551  jnz     loc_10040A733
0x10040a557  mov     eax, 3Bh ; ';'
0x10040a55c  mov     rbx, [rsp+58h+arg_0]
0x10040a561  mov     rbp, [rsp+58h+arg_8]
0x10040a566  mov     rsi, [rsp+58h+arg_10]
0x10040a56b  add     rsp, 30h
0x10040a56f  pop     r15
0x10040a571  pop     r14
0x10040a573  pop     r13
0x10040a575  pop     r12
0x10040a577  pop     rdi
0x10040a578  retn
0x10040a579  mov     rax, [rdi+1B8h]
0x10040a580  mov     qword ptr [rsp+58h+var_38], r15
0x10040a585  mov     dword ptr [rsp+58h+var_38+8], r15d
0x10040a58a  mov     rsi, [rax+10h]
0x10040a58e  mov     rax, [rdi+5E0h]
0x10040a595  cmp     rax, r13
0x10040a598  jnz     short loc_10040A5A8
0x10040a59a  test    rax, rax
0x10040a59d  jz      short loc_10040A5C3
0x10040a59f  cmp     [rdi+5E8h], r15d
0x10040a5a6  jz      short loc_10040A5C3
0x10040a5a8  cmp     rax, r12
0x10040a5ab  jnz     loc_10040A728
0x10040a5b1  test    rax, rax
0x10040a5b4  jz      short loc_10040A5C3
0x10040a5b6  cmp     [rdi+5E8h], r15d
0x10040a5bd  jnz     loc_10040A728
0x10040a5c3  mov     rcx, [rdi+68h]
0x10040a5c7  mov     rax, [rcx]
0x10040a5ca  mov     rax, [rax+60h]
0x10040a5ce  call    cs:__guard_dispatch_icall_fptr
0x10040a5d4  mov     rbx, [rdi+1B8h]
0x10040a5db  mov     ebp, eax
0x10040a5dd  mov     rdx, [rbx+10h]
0x10040a5e1  mov     ecx, [rbx+18h]
0x10040a5e4  sub     ecx, edx
0x10040a5e6  cmp     ecx, eax
0x10040a5e8  jnb     short loc_10040A635
0x10040a5ea  mov     rcx, [rbx+8]
0x10040a5ee  test    rcx, rcx
0x10040a5f1  jz      short loc_10040A60F
0x10040a5f3  mov     eax, [rcx+18h]
0x10040a5f6  mov     rbx, rcx
0x10040a5f9  sub     eax, ecx
0x10040a5fb  sub     eax, 20h ; ' '
0x10040a5fe  cmp     eax, ebp
0x10040a600  jnb     loc_10040A698
0x10040a606  mov     rcx, [rcx+8]
0x10040a60a  test    rcx, rcx
0x10040a60d  jnz     short loc_10040A5F3
0x10040a60f  lfence
0x10040a612  mov     r8, rbx; struct BlockAlloc::Header *
0x10040a615  lea     rcx, [rdi+1A0h]; this
0x10040a61c  mov     edx, ebp; unsigned int
0x10040a61e  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x10040a623  mov     [rbx+8], rax
0x10040a627  mov     rbx, rax
0x10040a62a  mov     [rdi+1B8h], rbx
0x10040a631  mov     rdx, [rbx+10h]
0x10040a635  add     [rbx+10h], rbp
0x10040a639  mov     rcx, [rdi+68h]
0x10040a63d  mov     qword ptr [rsp+58h+var_38], rdx
0x10040a642  lea     rdx, [rsp+58h+var_38]
0x10040a647  mov     rax, [rcx]
0x10040a64a  mov     rax, [rax+68h]
0x10040a64e  call    cs:__guard_dispatch_icall_fptr
0x10040a654  lea     rcx, [rdi+560h]
0x10040a65b  lea     rdx, [rsp+58h+var_38]
0x10040a660  call    ?lookup@?$_htable@VDeclEntity@@@@QEAAPEAVDeclEntity@@PEAUStringPtr@@@Z; _htable<DeclEntity>::lookup(StringPtr *)
0x10040a665  mov     rbx, rax
0x10040a668  mov     rax, [rdi+1B8h]
0x10040a66f  cmp     rax, rsi
0x10040a672  jnb     short loc_10040A67A
0x10040a674  cmp     rsi, [rax+10h]
0x10040a678  jbe     short loc_10040A6A2
0x10040a67a  mov     rax, [rax]
0x10040a67d  mov     [rdi+1B8h], rax
0x10040a684  test    rax, rax
0x10040a687  jz      loc_10040A73E
0x10040a68d  cmp     rax, rsi
0x10040a690  jnb     short loc_10040A67A
0x10040a692  cmp     rsi, [rax+18h]
0x10040a696  jmp     short loc_10040A678
0x10040a698  lea     rax, [rcx+20h]
0x10040a69c  mov     [rcx+10h], rax
0x10040a6a0  jmp     short loc_10040A62A
0x10040a6a2  mov     r8, rdi; void *
0x10040a6a5  mov     [rax+10h], rsi
0x10040a6a9  mov     rdx, rbx; struct DeclEntity *
0x10040a6ac  mov     rcx, rdi; this
0x10040a6af  call    ?HandleEntity@YReader@@AEAAPEAVDeclEntity@@PEAV2@PEAX@Z; YReader::HandleEntity(DeclEntity *,void *)
0x10040a6b4  test    rax, rax
0x10040a6b7  jz      short loc_10040A6FD
0x10040a6b9  movups  xmm0, xmmword ptr [rbx+50h]
0x10040a6bd  mov     [rbx+81h], r15b
0x10040a6c4  movups  [rsp+58h+var_38], xmm0
0x10040a6c9  cmp     [rbx+60h], r15
0x10040a6cd  jnz     short loc_10040A71E
0x10040a6cf  mov     rax, [rdi+0D8h]
0x10040a6d6  lea     rcx, [rdi+28h]
0x10040a6da  call    cs:__guard_dispatch_icall_fptr
0x10040a6e0  mov     ecx, [rdi+70h]
0x10040a6e3  sub     ecx, 1
0x10040a6e6  jz      short loc_10040A716
0x10040a6e8  cmp     ecx, 3Ah ; ':'
0x10040a6eb  jnz     short loc_10040A71E
0x10040a6ed  mov     rdx, rdi; void *
0x10040a6f0  mov     rcx, rdi; this
0x10040a6f3  call    ?HandleEntityEnd@YReader@@AEAAPEAVDeclEntity@@PEAX@Z; YReader::HandleEntityEnd(void *)
0x10040a6f8  jmp     loc_10040A4F0
0x10040a6fd  cmp     [rdi+6FBh], r15b
0x10040a704  jnz     loc_10040A4F0
0x10040a70a  mov     byte ptr [rdi+703h], 1
0x10040a711  jmp     loc_10040A4F0
0x10040a716  mov     rcx, rdi; this
0x10040a719  call    ?ParseTextDecl@YReader@@AEAAXXZ; YReader::ParseTextDecl(void)
0x10040a71e  mov     eax, 13h
0x10040a723  jmp     loc_10040A55C
0x10040a728  mov     ecx, 0C00CEE2Dh; int
0x10040a72d  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040a732  int     3; Trap to Debugger
0x10040a733  mov     ecx, 0C00CEE44h; int
0x10040a738  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040a73d  int     3; Trap to Debugger
0x10040a73e  mov     ecx, 80004005h; int
0x10040a743  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
