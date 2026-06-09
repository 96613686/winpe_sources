# YReader::GetTokenDeclInner(void)

- ea: `0x10040a020`
- end: `0x10040a25f`
- name: `?GetTokenDeclInner@YReader@@AEAAHXZ`
- size: `575`
- prototype: `__int64 __fastcall(YReader *__hidden this)`
- caller_count: `12`
- callee_count: `9`
- tags: ``

## callers

- `0x100405110`
- `0x1004055d0`
- `0x1004058d0`
- `0x100405a00`
- `0x100405c80`
- `0x100405fc0`
- `0x1004062a0`
- `0x1004064a0`
- `0x100406cc0`
- `0x100407100`
- `0x100408ea0`
- `0x100409110`

## callees

- `0x100401780`
- `0x100409390`
- `0x10040a020`
- `0x10040a750`
- `0x10040aa00`
- `0x10040f330`
- `0x100415560`
- `0x100416bc0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall YReader::GetTokenDeclInner(YReader *this)
{
  __int64 result; // rax
  __int64 v3; // rax
  unsigned __int64 v4; // rsi
  void (__fastcall *v5)(YReader *__hidden); // rax
  unsigned int v6; // eax
  struct BlockAlloc::Header *v7; // rbx
  __int64 v8; // rbp
  __int64 v9; // rdx
  __int64 v10; // rcx
  struct BlockAlloc::Header *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rbx
  _QWORD *v14; // rax
  bool v15; // cc
  __int64 v16; // [rsp+20h] [rbp-28h] BYREF
  int v17; // [rsp+28h] [rbp-20h]

  while ( 1 )
  {
    while ( 1 )
    {
      result = Scanner::GetTokenDeclInner((YReader *)((char *)this + 40));
      if ( (_DWORD)result != 19 )
        break;
      v3 = *((_QWORD *)this + 55);
      v16 = 0;
      v17 = 0;
      v4 = *(_QWORD *)(v3 + 16);
      v5 = (void (__fastcall *)(YReader *__hidden))*((_QWORD *)this + 188);
      if ( v5 != YReader::ParseSubsetExternal || v5 && *((_DWORD *)this + 378) )
      {
        MXRRaiseException(-1072894397);
        JUMPOUT(0x10040A25ELL);
      }
      v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
      v7 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
      v8 = v6;
      v9 = *((_QWORD *)v7 + 2);
      if ( *((_DWORD *)v7 + 6) - (int)v9 < v6 )
      {
        v10 = *((_QWORD *)v7 + 1);
        if ( v10 )
        {
          while ( 1 )
          {
            v7 = (struct BlockAlloc::Header *)v10;
            if ( *(_DWORD *)(v10 + 24) - (int)v10 - 32 >= v6 )
              break;
            v10 = *(_QWORD *)(v10 + 8);
            if ( !v10 )
              goto LABEL_12;
          }
          *(_QWORD *)(v10 + 16) = v10 + 32;
        }
        else
        {
LABEL_12:
          _mm_lfence();
          v11 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v6, v7);
          *((_QWORD *)v7 + 1) = v11;
          v7 = v11;
        }
        *((_QWORD *)this + 55) = v7;
        v9 = *((_QWORD *)v7 + 2);
      }
      *((_QWORD *)v7 + 2) += v8;
      v12 = *((_QWORD *)this + 13);
      v16 = v9;
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 104LL))(v12, &v16);
      v13 = _htable<DeclEntity>::lookup((char *)this + 1376, &v16);
      v14 = (_QWORD *)*((_QWORD *)this + 55);
      if ( (unsigned __int64)v14 < v4 )
      {
        v15 = v4 <= v14[2];
        goto LABEL_16;
      }
      do
      {
        do
        {
          v14 = (_QWORD *)*v14;
          *((_QWORD *)this + 55) = v14;
          if ( !v14 )
          {
            MXRRaiseException(-2147467259);
            __debugbreak();
          }
        }
        while ( (unsigned __int64)v14 >= v4 );
        v15 = v4 <= v14[3];
LABEL_16:
        ;
      }
      while ( !v15 );
      v14[2] = v4;
      if ( YReader::HandleEntity(this, (struct DeclEntity *)v13, this) )
      {
        *(_BYTE *)(v13 + 129) = 1;
        if ( !*(_QWORD *)(v13 + 96) )
        {
          (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
          if ( *((_DWORD *)this + 28) == 1 )
          {
            YReader::ParseTextDecl(this);
          }
          else if ( *((_DWORD *)this + 28) == 59 )
          {
            YReader::HandleEntityEnd(this, this);
          }
        }
      }
      else if ( !*((_BYTE *)this + 1787) )
      {
        *((_BYTE *)this + 1795) = 1;
      }
    }
    if ( (_DWORD)result != 59 )
      return result;
    if ( !*((_BYTE *)YReader::HandleEntityEnd(this, this) + 129) )
    {
      MXRRaiseException(-1072894396);
      __debugbreak();
    }
  }
}

```

## disassembly

```asm
0x10040a020  mov     [rsp+arg_0], rbx
0x10040a025  mov     [rsp+arg_8], rbp
0x10040a02a  mov     [rsp+arg_10], rsi
0x10040a02f  mov     [rsp+arg_18], rdi
0x10040a034  push    r12
0x10040a036  push    r14
0x10040a038  push    r15
0x10040a03a  sub     rsp, 30h
0x10040a03e  mov     rdi, rcx
0x10040a041  lea     r12, ?ParseSubsetExternal@YReader@@AEAAXXZ; YReader::ParseSubsetExternal(void)
0x10040a048  xor     r15d, r15d
0x10040a04b  nop     dword ptr [rax+rax+00h]
0x10040a050  lea     rcx, [rdi+28h]; this
0x10040a054  call    ?GetTokenDeclInner@Scanner@@QEAAHXZ; Scanner::GetTokenDeclInner(void)
0x10040a059  cmp     eax, 13h
0x10040a05c  jz      short loc_10040A081
0x10040a05e  cmp     eax, 3Bh ; ';'
0x10040a061  jnz     loc_10040A21F
0x10040a067  mov     rdx, rdi; void *
0x10040a06a  mov     rcx, rdi; this
0x10040a06d  call    ?HandleEntityEnd@YReader@@AEAAPEAVDeclEntity@@PEAX@Z; YReader::HandleEntityEnd(void *)
0x10040a072  cmp     [rax+81h], r15b
0x10040a079  jz      loc_10040A23E
0x10040a07f  jmp     short loc_10040A050
0x10040a081  mov     rax, [rdi+1B8h]
0x10040a088  mov     [rsp+48h+var_28], r15
0x10040a08d  mov     [rsp+48h+var_20], r15d
0x10040a092  mov     rsi, [rax+10h]
0x10040a096  mov     rax, [rdi+5E0h]
0x10040a09d  cmp     rax, r12
0x10040a0a0  jnz     loc_10040A254
0x10040a0a6  test    rax, rax
0x10040a0a9  jz      short loc_10040A0B8
0x10040a0ab  cmp     [rdi+5E8h], r15d
0x10040a0b2  jnz     loc_10040A254
0x10040a0b8  mov     rcx, [rdi+68h]
0x10040a0bc  mov     rax, [rcx]
0x10040a0bf  mov     rax, [rax+60h]
0x10040a0c3  call    cs:__guard_dispatch_icall_fptr
0x10040a0c9  mov     rbx, [rdi+1B8h]
0x10040a0d0  mov     ebp, eax
0x10040a0d2  mov     rdx, [rbx+10h]
0x10040a0d6  mov     ecx, [rbx+18h]
0x10040a0d9  sub     ecx, edx
0x10040a0db  cmp     ecx, eax
0x10040a0dd  jnb     short loc_10040A132
0x10040a0df  mov     rcx, [rbx+8]
0x10040a0e3  test    rcx, rcx
0x10040a0e6  jz      short loc_10040A10C
0x10040a0e8  nop     dword ptr [rax+rax+00000000h]
0x10040a0f0  mov     eax, [rcx+18h]
0x10040a0f3  mov     rbx, rcx
0x10040a0f6  sub     eax, ecx
0x10040a0f8  sub     eax, 20h ; ' '
0x10040a0fb  cmp     eax, ebp
0x10040a0fd  jnb     loc_10040A195
0x10040a103  mov     rcx, [rcx+8]
0x10040a107  test    rcx, rcx
0x10040a10a  jnz     short loc_10040A0F0
0x10040a10c  lfence
0x10040a10f  mov     r8, rbx; struct BlockAlloc::Header *
0x10040a112  lea     rcx, [rdi+1A0h]; this
0x10040a119  mov     edx, ebp; unsigned int
0x10040a11b  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x10040a120  mov     [rbx+8], rax
0x10040a124  mov     rbx, rax
0x10040a127  mov     [rdi+1B8h], rbx
0x10040a12e  mov     rdx, [rbx+10h]
0x10040a132  add     [rbx+10h], rbp
0x10040a136  mov     rcx, [rdi+68h]
0x10040a13a  mov     [rsp+48h+var_28], rdx
0x10040a13f  lea     rdx, [rsp+48h+var_28]
0x10040a144  mov     rax, [rcx]
0x10040a147  mov     rax, [rax+68h]
0x10040a14b  call    cs:__guard_dispatch_icall_fptr
0x10040a151  lea     rcx, [rdi+560h]
0x10040a158  lea     rdx, [rsp+48h+var_28]
0x10040a15d  call    ?lookup@?$_htable@VDeclEntity@@@@QEAAPEAVDeclEntity@@PEAUStringPtr@@@Z; _htable<DeclEntity>::lookup(StringPtr *)
0x10040a162  mov     rbx, rax
0x10040a165  mov     rax, [rdi+1B8h]
0x10040a16c  cmp     rax, rsi
0x10040a16f  jnb     short loc_10040A177
0x10040a171  cmp     rsi, [rax+10h]
0x10040a175  jbe     short loc_10040A19F
0x10040a177  mov     rax, [rax]
0x10040a17a  mov     [rdi+1B8h], rax
0x10040a181  test    rax, rax
0x10040a184  jz      loc_10040A249
0x10040a18a  cmp     rax, rsi
0x10040a18d  jnb     short loc_10040A177
0x10040a18f  cmp     rsi, [rax+18h]
0x10040a193  jmp     short loc_10040A175
0x10040a195  lea     rax, [rcx+20h]
0x10040a199  mov     [rcx+10h], rax
0x10040a19d  jmp     short loc_10040A127
0x10040a19f  mov     r8, rdi; void *
0x10040a1a2  mov     [rax+10h], rsi
0x10040a1a6  mov     rdx, rbx; struct DeclEntity *
0x10040a1a9  mov     rcx, rdi; this
0x10040a1ac  call    ?HandleEntity@YReader@@AEAAPEAVDeclEntity@@PEAV2@PEAX@Z; YReader::HandleEntity(DeclEntity *,void *)
0x10040a1b1  test    rax, rax
0x10040a1b4  jz      short loc_10040A206
0x10040a1b6  mov     byte ptr [rbx+81h], 1
0x10040a1bd  cmp     [rbx+60h], r15
0x10040a1c1  jnz     loc_10040A050
0x10040a1c7  mov     rax, [rdi+0D8h]
0x10040a1ce  lea     rcx, [rdi+28h]
0x10040a1d2  call    cs:__guard_dispatch_icall_fptr
0x10040a1d8  mov     ecx, [rdi+70h]
0x10040a1db  sub     ecx, 1
0x10040a1de  jz      short loc_10040A1F9
0x10040a1e0  cmp     ecx, 3Ah ; ':'
0x10040a1e3  jnz     loc_10040A050
0x10040a1e9  mov     rdx, rdi; void *
0x10040a1ec  mov     rcx, rdi; this
0x10040a1ef  call    ?HandleEntityEnd@YReader@@AEAAPEAVDeclEntity@@PEAX@Z; YReader::HandleEntityEnd(void *)
0x10040a1f4  jmp     loc_10040A050
0x10040a1f9  mov     rcx, rdi; this
0x10040a1fc  call    ?ParseTextDecl@YReader@@AEAAXXZ; YReader::ParseTextDecl(void)
0x10040a201  jmp     loc_10040A050
0x10040a206  cmp     [rdi+6FBh], r15b
0x10040a20d  jnz     loc_10040A050
0x10040a213  mov     byte ptr [rdi+703h], 1
0x10040a21a  jmp     loc_10040A050
0x10040a21f  mov     rbx, [rsp+48h+arg_0]
0x10040a224  mov     rbp, [rsp+48h+arg_8]
0x10040a229  mov     rsi, [rsp+48h+arg_10]
0x10040a22e  mov     rdi, [rsp+48h+arg_18]
0x10040a233  add     rsp, 30h
0x10040a237  pop     r15
0x10040a239  pop     r14
0x10040a23b  pop     r12
0x10040a23d  retn
0x10040a23e  mov     ecx, 0C00CEE44h; int
0x10040a243  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040a248  int     3; Trap to Debugger
0x10040a249  mov     ecx, 80004005h; int
0x10040a24e  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040a253  int     3; Trap to Debugger
0x10040a254  mov     ecx, 0C00CEE43h; int
0x10040a259  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
