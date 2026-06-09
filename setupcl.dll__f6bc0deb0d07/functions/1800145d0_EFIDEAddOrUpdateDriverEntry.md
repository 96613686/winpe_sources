# EFIDEAddOrUpdateDriverEntry

- ea: `0x1800145d0`
- end: `0x18001477d`
- name: `EFIDEAddOrUpdateDriverEntry`
- size: `429`
- prototype: `__int64 __fastcall(_DWORD *, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800149e0`

## callees

- `0x180012d4c`
- `0x180014094`
- `0x1800145d0`
- `0x1800179ad`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall EFIDEAddOrUpdateDriverEntry(_DWORD *a1, char a2)
{
  __int64 v2; // rax
  _WORD *v3; // r13
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned int v8; // ebp
  int v9; // r12d
  _DWORD *v10; // rax
  _DWORD *v11; // rsi
  _DWORD *v12; // rdi
  bool v13; // zf
  unsigned int v14; // eax
  unsigned int v16; // [rsp+20h] [rbp-58h]
  int v18; // [rsp+90h] [rbp+18h]
  unsigned int Size; // [rsp+98h] [rbp+20h]

  v2 = -1;
  v3 = a1 + 131;
  v5 = -1;
  v6 = -1073741823;
  do
    ++v5;
  while ( v3[v5] );
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)a1 + v7 + 522) );
  do
    ++v2;
  while ( *((_WORD *)a1 + v2 + 782) );
  v8 = 2 * v2 + 2;
  v9 = (2 * v2 + 5) & 0xFFFFFFFC;
  if ( AllocRoutine )
  {
    Size = 2 * v5 + 2;
    v16 = 2 * v7 + 2;
    v18 = 2 * v7 + 14 + Size;
    v10 = (_DWORD *)AllocRoutine();
    v11 = v10;
    if ( v10 )
    {
      *v10 = 1;
      v10[1] = v9 + v18 + 20;
      v10[4] = v9 + 20;
      v10[3] = 20;
      memcpy_0(v10 + 5, a1 + 391, v8);
      v12 = (_DWORD *)((char *)v11 + (unsigned int)v11[4]);
      *v12 = 1;
      v12[1] = v18;
      v12[2] = 3;
      memcpy_0(v12 + 3, v3, Size);
      memcpy_0((char *)v12 + Size + 12, a1 + 261, v16);
      if ( a2 )
      {
        v13 = EfipApisInitialized == 0;
        v11[2] = *a1;
        if ( v13 )
          EfiApiInitialize();
        if ( EfipModifyDriverEntry )
        {
          v14 = EfipModifyDriverEntry(v11);
LABEL_17:
          v6 = v14;
LABEL_19:
          SBE_FREE(v11);
          return v6;
        }
      }
      else
      {
        if ( !EfipApisInitialized )
          EfiApiInitialize();
        if ( EfipAddDriverEntry )
        {
          v14 = EfipAddDriverEntry(v11, a1);
          goto LABEL_17;
        }
      }
      v6 = -1073741822;
      goto LABEL_19;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800145d0  mov     [rsp+arg_8], dl
0x1800145d4  push    rbx
0x1800145d5  push    rbp
0x1800145d6  push    rsi
0x1800145d7  push    rdi
0x1800145d8  push    r12
0x1800145da  push    r13
0x1800145dc  push    r14
0x1800145de  push    r15
0x1800145e0  sub     rsp, 38h
0x1800145e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800145e8  lea     r13, [rcx+20Ch]
0x1800145ef  mov     r14, rcx
0x1800145f2  xor     r8d, r8d
0x1800145f5  mov     rcx, rax
0x1800145f8  mov     ebx, 0C0000001h
0x1800145fd  inc     rcx
0x180014600  cmp     [r13+rcx*2+0], r8w
0x180014606  jnz     short loc_1800145FD
0x180014608  lea     r15, [r14+414h]
0x18001460f  mov     rdx, rax
0x180014612  inc     rdx
0x180014615  cmp     [r15+rdx*2], r8w
0x18001461a  jnz     short loc_180014612
0x18001461c  lea     rdi, [r14+61Ch]
0x180014623  inc     rax
0x180014626  cmp     [rdi+rax*2], r8w
0x18001462b  jnz     short loc_180014623
0x18001462d  lea     ebp, ds:2[rax*2]
0x180014634  mov     rax, cs:AllocRoutine
0x18001463b  lea     r12d, [rbp+3]
0x18001463f  and     r12d, 0FFFFFFFCh
0x180014643  test    rax, rax
0x180014646  jz      loc_18001476A
0x18001464c  lea     ecx, ds:2[rcx*2]
0x180014653  mov     dword ptr [rsp+78h+Size], ecx
0x18001465a  lea     edx, ds:2[rdx*2]
0x180014661  mov     [rsp+78h+var_58], edx
0x180014665  add     edx, 0Ch
0x180014668  add     ecx, edx
0x18001466a  mov     [rsp+78h+arg_10], ecx
0x180014671  add     ecx, 14h
0x180014674  add     ecx, r12d
0x180014677  mov     [rsp+78h+arg_0], ecx
0x18001467e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014683  mov     rsi, rax
0x180014686  test    rax, rax
0x180014689  jz      loc_18001476A
0x18001468f  mov     ebx, 1
0x180014694  mov     r8d, ebp; Size
0x180014697  mov     [rax], ebx
0x180014699  lea     rcx, [rsi+14h]; void *
0x18001469d  mov     eax, [rsp+78h+arg_0]
0x1800146a4  mov     rdx, rdi; Src
0x1800146a7  mov     [rsi+4], eax
0x1800146aa  lea     eax, [r12+14h]
0x1800146af  mov     [rsi+10h], eax
0x1800146b2  mov     dword ptr [rsi+0Ch], 14h
0x1800146b9  call    memcpy_0
0x1800146be  mov     edi, [rsi+10h]
0x1800146c1  mov     rdx, r13; Src
0x1800146c4  mov     eax, [rsp+78h+arg_10]
0x1800146cb  add     rdi, rsi
0x1800146ce  mov     [rdi], ebx
0x1800146d0  lea     rcx, [rdi+0Ch]; void *
0x1800146d4  mov     ebx, dword ptr [rsp+78h+Size]
0x1800146db  mov     r8d, ebx; Size
0x1800146de  mov     [rdi+4], eax
0x1800146e1  mov     dword ptr [rdi+8], 3
0x1800146e8  call    memcpy_0
0x1800146ed  mov     r8d, [rsp+78h+var_58]; Size
0x1800146f2  lea     rcx, [rbx+0Ch]
0x1800146f6  add     rcx, rdi; void *
0x1800146f9  mov     rdx, r15; Src
0x1800146fc  call    memcpy_0
0x180014701  xor     ebx, ebx
0x180014703  cmp     [rsp+78h+arg_8], bl
0x18001470a  jz      short loc_180014735
0x18001470c  cmp     cs:EfipApisInitialized, bl
0x180014712  mov     eax, [r14]
0x180014715  mov     [rsi+8], eax
0x180014718  jnz     short loc_18001471F
0x18001471a  call    EfiApiInitialize
0x18001471f  mov     rax, cs:EfipModifyDriverEntry
0x180014726  test    rax, rax
0x180014729  jz      short loc_18001475D
0x18001472b  mov     rcx, rsi
0x18001472e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014733  jmp     short loc_180014759
0x180014735  cmp     cs:EfipApisInitialized, bl
0x18001473b  jnz     short loc_180014742
0x18001473d  call    EfiApiInitialize
0x180014742  mov     rax, cs:EfipAddDriverEntry
0x180014749  test    rax, rax
0x18001474c  jz      short loc_18001475D
0x18001474e  mov     rdx, r14
0x180014751  mov     rcx, rsi
0x180014754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014759  mov     ebx, eax
0x18001475b  jmp     short loc_180014762
0x18001475d  mov     ebx, 0C0000002h
0x180014762  mov     rcx, rsi
0x180014765  call    SBE_FREE
0x18001476a  mov     eax, ebx
0x18001476c  add     rsp, 38h
0x180014770  pop     r15
0x180014772  pop     r14
0x180014774  pop     r13
0x180014776  pop     r12
0x180014778  pop     rdi
0x180014779  pop     rsi
0x18001477a  pop     rbp
0x18001477b  pop     rbx
0x18001477c  retn
```
