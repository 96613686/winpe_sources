# AutBlock::ReplaceText(long,long,long *,ushort const *)

- ea: `0x18004d15c`
- end: `0x18004d2f5`
- name: `?ReplaceText@AutBlock@@QEAAJJJPEAJPEBG@Z`
- size: `409`
- prototype: `__int64 __fastcall(AutBlock *__hidden this, int, int, int *, wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004d5a0`

## callees

- `0x18003bc44`
- `0x18003f1fc`
- `0x180040a6c`
- `0x180049678`
- `0x18004d15c`
- `0x18007672e`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18004d1cf`
- `msvcrt!wcsncpy_s` at `0x18004d1cf`
- `msvcrt!free` at `0x18004d26b`
- `msvcrt!free` at `0x18004d26b`

## pseudocode

```c
__int64 __fastcall AutBlock::ReplaceText(AutBlock *this, int a2, int a3, int *a4, wchar_t *Source)
{
  __int64 v5; // rbx
  int v10; // r14d
  unsigned int v11; // eax
  const unsigned __int16 *v12; // rdx
  int appended; // r15d
  int v14; // r12d
  __int64 v15; // rcx
  int v16; // ebx
  AutEntry *v17; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v18[2]; // [rsp+28h] [rbp-18h] BYREF
  int v19; // [rsp+38h] [rbp-8h]
  int v20; // [rsp+90h] [rbp+50h]

  v5 = -1;
  do
    ++v5;
  while ( Source[v5] );
  if ( (int)v5 < 1 )
    return 2147500035LL;
  v10 = *a4 - a3;
  v20 = *a4;
  if ( (_DWORD)v5 == v10 )
  {
    v11 = *((_DWORD *)this + 18);
    if ( v11 < a3 )
      return 2147942934LL;
    wcsncpy_s((wchar_t *)(*((_QWORD *)this + 8) + 2LL * a3), v11 - a3, Source, (int)v5);
    return 0;
  }
  v12 = (const unsigned __int16 *)*((_QWORD *)this + 8);
  v17 = 0;
  v18[0] = 0;
  v18[1] = 0;
  v19 = 0;
  appended = BuildString::AppendSz((BuildString *)v18, v12, a3);
  if ( appended < 0
    || (appended = BuildString::AppendSz((BuildString *)v18, Source, v5), appended < 0)
    || (appended = BuildString::AppendSz(
                     (BuildString *)v18,
                     (const unsigned __int16 *)(*((_QWORD *)this + 8) + 2LL * v20),
                     *((_DWORD *)this + 18) - v20),
        appended < 0) )
  {
LABEL_10:
    BuildString::Reset((BuildString *)v18);
    return (unsigned int)appended;
  }
  if ( v19 )
  {
    appended = -2147024882;
    goto LABEL_10;
  }
  free(*((void **)this + 8));
  v14 = a2 + 1;
  *((_QWORD *)this + 8) = BuildString::PszReset((BuildString *)v18);
  *((_DWORD *)this + 18) += v5 - v10;
  *a4 = v5 + a3;
  v15 = *((_QWORD *)this + 4);
  if ( v14 < *(_DWORD *)(v15 + 28) )
  {
    v16 = v5 - v10;
    do
    {
      memcpy_0(&v17, (const void *)(*(_QWORD *)(v15 + 16) + v14 * *(_DWORD *)(v15 + 12)), *(int *)(v15 + 12));
      AutEntry::AdjustOffsets(v17, v16);
      v15 = *((_QWORD *)this + 4);
      ++v14;
    }
    while ( v14 < *(_DWORD *)(v15 + 28) );
  }
  BuildString::Reset((BuildString *)v18);
  return 0;
}

```

## disassembly

```asm
0x18004d15c  mov     [rsp-38h+arg_0], rbx
0x18004d161  mov     [rsp-38h+arg_18], r9
0x18004d166  push    rbp
0x18004d167  push    rsi
0x18004d168  push    rdi
0x18004d169  push    r12
0x18004d16b  push    r13
0x18004d16d  push    r14
0x18004d16f  push    r15
0x18004d171  mov     rbp, rsp
0x18004d174  sub     rsp, 40h
0x18004d178  mov     r13, [rbp+Source]
0x18004d17c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004d180  mov     rdi, rcx
0x18004d183  movsxd  rsi, r8d
0x18004d186  xor     ecx, ecx
0x18004d188  mov     r12d, edx
0x18004d18b  inc     rbx
0x18004d18e  cmp     [r13+rbx*2+0], cx
0x18004d194  jnz     short loc_18004D18B
0x18004d196  cmp     ebx, 1
0x18004d199  jge     short loc_18004D1A5
0x18004d19b  mov     eax, 80004003h
0x18004d1a0  jmp     loc_18004D2DD
0x18004d1a5  mov     eax, [r9]
0x18004d1a8  mov     r14d, eax
0x18004d1ab  sub     r14d, esi
0x18004d1ae  mov     [rbp+arg_10], eax
0x18004d1b1  cmp     ebx, r14d
0x18004d1b4  jnz     short loc_18004D1E4
0x18004d1b6  mov     eax, [rdi+48h]
0x18004d1b9  cmp     eax, esi
0x18004d1bb  jb      short loc_18004D1DA
0x18004d1bd  sub     eax, esi
0x18004d1bf  movsxd  r9, ebx; MaxCount
0x18004d1c2  mov     edx, eax; SizeInWords
0x18004d1c4  mov     r8, r13; Source
0x18004d1c7  mov     rax, [rdi+40h]
0x18004d1cb  lea     rcx, [rax+rsi*2]; Destination
0x18004d1cf  call    cs:__imp_wcsncpy_s
0x18004d1d5  jmp     loc_18004D2DB
0x18004d1da  mov     eax, 80070216h
0x18004d1df  jmp     loc_18004D2DD
0x18004d1e4  mov     rdx, [rdi+40h]; unsigned __int16 *
0x18004d1e8  mov     r8d, esi; int
0x18004d1eb  mov     [rbp+var_20], rcx
0x18004d1ef  mov     [rbp+var_18], rcx
0x18004d1f3  mov     [rbp+var_10], rcx
0x18004d1f7  mov     [rbp+var_8], ecx
0x18004d1fa  lea     rcx, [rbp+var_18]; this
0x18004d1fe  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004d203  lea     rcx, [rbp+var_18]; this
0x18004d207  mov     r15d, eax
0x18004d20a  test    eax, eax
0x18004d20c  jns     short loc_18004D21B
0x18004d20e  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x18004d213  mov     eax, r15d
0x18004d216  jmp     loc_18004D2DD
0x18004d21b  mov     r8d, ebx; int
0x18004d21e  mov     rdx, r13; unsigned __int16 *
0x18004d221  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004d226  mov     r15d, eax
0x18004d229  test    eax, eax
0x18004d22b  jns     short loc_18004D233
0x18004d22d  lea     rcx, [rbp+var_18]
0x18004d231  jmp     short loc_18004D20E
0x18004d233  movsxd  rax, [rbp+arg_10]
0x18004d237  mov     r8d, [rdi+48h]
0x18004d23b  mov     rcx, rax
0x18004d23e  sub     r8d, eax; int
0x18004d241  mov     rax, [rdi+40h]
0x18004d245  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x18004d249  lea     rcx, [rbp+var_18]; this
0x18004d24d  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004d252  mov     r15d, eax
0x18004d255  test    eax, eax
0x18004d257  js      short loc_18004D22D
0x18004d259  cmp     [rbp+var_8], 0
0x18004d25d  jz      short loc_18004D267
0x18004d25f  mov     r15d, 8007000Eh
0x18004d265  jmp     short loc_18004D22D
0x18004d267  mov     rcx, [rdi+40h]; Block
0x18004d26b  call    cs:__imp_free
0x18004d271  lea     rcx, [rbp+var_18]; this
0x18004d275  call    ?PszReset@BuildString@@QEAAPEAGXZ; BuildString::PszReset(void)
0x18004d27a  mov     rcx, [rbp+arg_18]
0x18004d27e  inc     r12d
0x18004d281  mov     [rdi+40h], rax
0x18004d285  mov     eax, ebx
0x18004d287  sub     eax, r14d
0x18004d28a  add     [rdi+48h], eax
0x18004d28d  lea     eax, [rbx+rsi]
0x18004d290  mov     [rcx], eax
0x18004d292  mov     rcx, [rdi+20h]
0x18004d296  cmp     r12d, [rcx+1Ch]
0x18004d29a  jge     short loc_18004D2D2
0x18004d29c  sub     ebx, r14d
0x18004d29f  movsxd  rax, dword ptr [rcx+0Ch]
0x18004d2a3  mov     r8, rax; Size
0x18004d2a6  imul    eax, r12d
0x18004d2aa  movsxd  rdx, eax
0x18004d2ad  add     rdx, [rcx+10h]; Src
0x18004d2b1  lea     rcx, [rbp+var_20]; void *
0x18004d2b5  call    memcpy_0
0x18004d2ba  mov     rcx, [rbp+var_20]; this
0x18004d2be  mov     edx, ebx; int
0x18004d2c0  call    ?AdjustOffsets@AutEntry@@QEAAXJ@Z; AutEntry::AdjustOffsets(long)
0x18004d2c5  mov     rcx, [rdi+20h]
0x18004d2c9  inc     r12d
0x18004d2cc  cmp     r12d, [rcx+1Ch]
0x18004d2d0  jl      short loc_18004D29F
0x18004d2d2  lea     rcx, [rbp+var_18]; this
0x18004d2d6  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x18004d2db  xor     eax, eax
0x18004d2dd  mov     rbx, [rsp+40h+arg_0]
0x18004d2e5  add     rsp, 40h
0x18004d2e9  pop     r15
0x18004d2eb  pop     r14
0x18004d2ed  pop     r13
0x18004d2ef  pop     r12
0x18004d2f1  pop     rdi
0x18004d2f2  pop     rsi
0x18004d2f3  pop     rbp
0x18004d2f4  retn
```
