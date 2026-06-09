# YReader::GetTokenDeclLiteral(void)

- ea: `0x10040a270`
- end: `0x10040a4b2`
- name: `?GetTokenDeclLiteral@YReader@@AEAAHXZ`
- size: `578`
- prototype: `__int64 __fastcall(YReader *__hidden this)`
- caller_count: `6`
- callee_count: `8`
- tags: ``

## callers

- `0x1004055d0`
- `0x1004069e0`
- `0x100407100`
- `0x100408760`
- `0x100408ea0`
- `0x100409110`

## callees

- `0x100401780`
- `0x100409390`
- `0x10040a270`
- `0x10040a750`
- `0x10040aa00`
- `0x100415560`
- `0x100416bc0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall YReader::GetTokenDeclLiteral(YReader *this)
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
      (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
      result = *((unsigned int *)this + 28);
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
        JUMPOUT(0x10040A4B1LL);
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
0x10040a270  mov     [rsp+arg_0], rbx
0x10040a275  mov     [rsp+arg_8], rbp
0x10040a27a  mov     [rsp+arg_10], rsi
0x10040a27f  mov     [rsp+arg_18], rdi
0x10040a284  push    r12
0x10040a286  push    r14
0x10040a288  push    r15
0x10040a28a  sub     rsp, 30h
0x10040a28e  mov     rdi, rcx
0x10040a291  lea     r12, ?ParseSubsetExternal@YReader@@AEAAXXZ; YReader::ParseSubsetExternal(void)
0x10040a298  xor     r15d, r15d
0x10040a29b  nop     dword ptr [rax+rax+00h]
0x10040a2a0  mov     rax, [rdi+0D8h]
0x10040a2a7  lea     rcx, [rdi+28h]
0x10040a2ab  call    cs:__guard_dispatch_icall_fptr
0x10040a2b1  mov     eax, [rdi+70h]
0x10040a2b4  cmp     eax, 13h
0x10040a2b7  jz      short loc_10040A2DC
0x10040a2b9  cmp     eax, 3Bh ; ';'
0x10040a2bc  jnz     loc_10040A472
0x10040a2c2  mov     rdx, rdi; void *
0x10040a2c5  mov     rcx, rdi; this
0x10040a2c8  call    ?HandleEntityEnd@YReader@@AEAAPEAVDeclEntity@@PEAX@Z; YReader::HandleEntityEnd(void *)
0x10040a2cd  cmp     [rax+81h], r15b
0x10040a2d4  jz      loc_10040A491
0x10040a2da  jmp     short loc_10040A2A0
0x10040a2dc  mov     rax, [rdi+1B8h]
0x10040a2e3  mov     [rsp+48h+var_28], r15
0x10040a2e8  mov     [rsp+48h+var_20], r15d
0x10040a2ed  mov     rsi, [rax+10h]
0x10040a2f1  mov     rax, [rdi+5E0h]
0x10040a2f8  cmp     rax, r12
0x10040a2fb  jnz     loc_10040A4A7
0x10040a301  test    rax, rax
0x10040a304  jz      short loc_10040A313
0x10040a306  cmp     [rdi+5E8h], r15d
0x10040a30d  jnz     loc_10040A4A7
0x10040a313  mov     rcx, [rdi+68h]
0x10040a317  mov     rax, [rcx]
0x10040a31a  mov     rax, [rax+60h]
0x10040a31e  call    cs:__guard_dispatch_icall_fptr
0x10040a324  mov     rbx, [rdi+1B8h]
0x10040a32b  mov     ebp, eax
0x10040a32d  mov     rdx, [rbx+10h]
0x10040a331  mov     ecx, [rbx+18h]
0x10040a334  sub     ecx, edx
0x10040a336  cmp     ecx, eax
0x10040a338  jnb     short loc_10040A385
0x10040a33a  mov     rcx, [rbx+8]
0x10040a33e  test    rcx, rcx
0x10040a341  jz      short loc_10040A35F
0x10040a343  mov     eax, [rcx+18h]
0x10040a346  mov     rbx, rcx
0x10040a349  sub     eax, ecx
0x10040a34b  sub     eax, 20h ; ' '
0x10040a34e  cmp     eax, ebp
0x10040a350  jnb     loc_10040A3E8
0x10040a356  mov     rcx, [rcx+8]
0x10040a35a  test    rcx, rcx
0x10040a35d  jnz     short loc_10040A343
0x10040a35f  lfence
0x10040a362  mov     r8, rbx; struct BlockAlloc::Header *
0x10040a365  lea     rcx, [rdi+1A0h]; this
0x10040a36c  mov     edx, ebp; unsigned int
0x10040a36e  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x10040a373  mov     [rbx+8], rax
0x10040a377  mov     rbx, rax
0x10040a37a  mov     [rdi+1B8h], rbx
0x10040a381  mov     rdx, [rbx+10h]
0x10040a385  add     [rbx+10h], rbp
0x10040a389  mov     rcx, [rdi+68h]
0x10040a38d  mov     [rsp+48h+var_28], rdx
0x10040a392  lea     rdx, [rsp+48h+var_28]
0x10040a397  mov     rax, [rcx]
0x10040a39a  mov     rax, [rax+68h]
0x10040a39e  call    cs:__guard_dispatch_icall_fptr
0x10040a3a4  lea     rcx, [rdi+560h]
0x10040a3ab  lea     rdx, [rsp+48h+var_28]
0x10040a3b0  call    ?lookup@?$_htable@VDeclEntity@@@@QEAAPEAVDeclEntity@@PEAUStringPtr@@@Z; _htable<DeclEntity>::lookup(StringPtr *)
0x10040a3b5  mov     rbx, rax
0x10040a3b8  mov     rax, [rdi+1B8h]
0x10040a3bf  cmp     rax, rsi
0x10040a3c2  jnb     short loc_10040A3CA
0x10040a3c4  cmp     rsi, [rax+10h]
0x10040a3c8  jbe     short loc_10040A3F2
0x10040a3ca  mov     rax, [rax]
0x10040a3cd  mov     [rdi+1B8h], rax
0x10040a3d4  test    rax, rax
0x10040a3d7  jz      loc_10040A49C
0x10040a3dd  cmp     rax, rsi
0x10040a3e0  jnb     short loc_10040A3CA
0x10040a3e2  cmp     rsi, [rax+18h]
0x10040a3e6  jmp     short loc_10040A3C8
0x10040a3e8  lea     rax, [rcx+20h]
0x10040a3ec  mov     [rcx+10h], rax
0x10040a3f0  jmp     short loc_10040A37A
0x10040a3f2  mov     r8, rdi; void *
0x10040a3f5  mov     [rax+10h], rsi
0x10040a3f9  mov     rdx, rbx; struct DeclEntity *
0x10040a3fc  mov     rcx, rdi; this
0x10040a3ff  call    ?HandleEntity@YReader@@AEAAPEAVDeclEntity@@PEAV2@PEAX@Z; YReader::HandleEntity(DeclEntity *,void *)
0x10040a404  test    rax, rax
0x10040a407  jz      short loc_10040A459
0x10040a409  mov     byte ptr [rbx+81h], 1
0x10040a410  cmp     [rbx+60h], r15
0x10040a414  jnz     loc_10040A2A0
0x10040a41a  mov     rax, [rdi+0D8h]
0x10040a421  lea     rcx, [rdi+28h]
0x10040a425  call    cs:__guard_dispatch_icall_fptr
0x10040a42b  mov     ecx, [rdi+70h]
0x10040a42e  sub     ecx, 1
0x10040a431  jz      short loc_10040A44C
0x10040a433  cmp     ecx, 3Ah ; ':'
0x10040a436  jnz     loc_10040A2A0
0x10040a43c  mov     rdx, rdi; void *
0x10040a43f  mov     rcx, rdi; this
0x10040a442  call    ?HandleEntityEnd@YReader@@AEAAPEAVDeclEntity@@PEAX@Z; YReader::HandleEntityEnd(void *)
0x10040a447  jmp     loc_10040A2A0
0x10040a44c  mov     rcx, rdi; this
0x10040a44f  call    ?ParseTextDecl@YReader@@AEAAXXZ; YReader::ParseTextDecl(void)
0x10040a454  jmp     loc_10040A2A0
0x10040a459  cmp     [rdi+6FBh], r15b
0x10040a460  jnz     loc_10040A2A0
0x10040a466  mov     byte ptr [rdi+703h], 1
0x10040a46d  jmp     loc_10040A2A0
0x10040a472  mov     rbx, [rsp+48h+arg_0]
0x10040a477  mov     rbp, [rsp+48h+arg_8]
0x10040a47c  mov     rsi, [rsp+48h+arg_10]
0x10040a481  mov     rdi, [rsp+48h+arg_18]
0x10040a486  add     rsp, 30h
0x10040a48a  pop     r15
0x10040a48c  pop     r14
0x10040a48e  pop     r12
0x10040a490  retn
0x10040a491  mov     ecx, 0C00CEE44h; int
0x10040a496  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040a49b  int     3; Trap to Debugger
0x10040a49c  mov     ecx, 80004005h; int
0x10040a4a1  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040a4a6  int     3; Trap to Debugger
0x10040a4a7  mov     ecx, 0C00CEE43h; int
0x10040a4ac  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
