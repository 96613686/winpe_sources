# AutBlock::ReplaceText(long,long,long *,ushort const *)

- ea: `0x18004e7bc`
- end: `0x18004e962`
- name: `?ReplaceText@AutBlock@@QEAAJJJPEAJPEBG@Z`
- size: `422`
- prototype: `__int64 __fastcall(AutBlock *__hidden this, int, int, int *, wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004ecc0`

## callees

- `0x18003d310`
- `0x180040a9c`
- `0x180042108`
- `0x18004ac54`
- `0x18004e7bc`
- `0x18007941e`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18004e82f`
- `msvcrt!wcsncpy_s` at `0x18004e82f`
- `msvcrt!free` at `0x18004e8d1`
- `msvcrt!free` at `0x18004e8d1`

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
0x18004e7bc  mov     [rsp-38h+arg_0], rbx
0x18004e7c1  mov     [rsp-38h+arg_18], r9
0x18004e7c6  push    rbp
0x18004e7c7  push    rsi
0x18004e7c8  push    rdi
0x18004e7c9  push    r12
0x18004e7cb  push    r13
0x18004e7cd  push    r14
0x18004e7cf  push    r15
0x18004e7d1  mov     rbp, rsp
0x18004e7d4  sub     rsp, 40h
0x18004e7d8  mov     r13, [rbp+Source]
0x18004e7dc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004e7e0  mov     rdi, rcx
0x18004e7e3  movsxd  rsi, r8d
0x18004e7e6  xor     ecx, ecx
0x18004e7e8  mov     r12d, edx
0x18004e7eb  inc     rbx
0x18004e7ee  cmp     [r13+rbx*2+0], cx
0x18004e7f4  jnz     short loc_18004E7EB
0x18004e7f6  cmp     ebx, 1
0x18004e7f9  jge     short loc_18004E805
0x18004e7fb  mov     eax, 80004003h
0x18004e800  jmp     loc_18004E949
0x18004e805  mov     eax, [r9]
0x18004e808  mov     r14d, eax
0x18004e80b  sub     r14d, esi
0x18004e80e  mov     [rbp+arg_10], eax
0x18004e811  cmp     ebx, r14d
0x18004e814  jnz     short loc_18004E84A
0x18004e816  mov     eax, [rdi+48h]
0x18004e819  cmp     eax, esi
0x18004e81b  jb      short loc_18004E840
0x18004e81d  sub     eax, esi
0x18004e81f  movsxd  r9, ebx; MaxCount
0x18004e822  mov     edx, eax; SizeInWords
0x18004e824  mov     r8, r13; Source
0x18004e827  mov     rax, [rdi+40h]
0x18004e82b  lea     rcx, [rax+rsi*2]; Destination
0x18004e82f  call    cs:__imp_wcsncpy_s
0x18004e836  nop     dword ptr [rax+rax+00h]
0x18004e83b  jmp     loc_18004E947
0x18004e840  mov     eax, 80070216h
0x18004e845  jmp     loc_18004E949
0x18004e84a  mov     rdx, [rdi+40h]; unsigned __int16 *
0x18004e84e  mov     r8d, esi; int
0x18004e851  mov     [rbp+var_20], rcx
0x18004e855  mov     [rbp+var_18], rcx
0x18004e859  mov     [rbp+var_10], rcx
0x18004e85d  mov     [rbp+var_8], ecx
0x18004e860  lea     rcx, [rbp+var_18]; this
0x18004e864  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004e869  lea     rcx, [rbp+var_18]; this
0x18004e86d  mov     r15d, eax
0x18004e870  test    eax, eax
0x18004e872  jns     short loc_18004E881
0x18004e874  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x18004e879  mov     eax, r15d
0x18004e87c  jmp     loc_18004E949
0x18004e881  mov     r8d, ebx; int
0x18004e884  mov     rdx, r13; unsigned __int16 *
0x18004e887  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004e88c  mov     r15d, eax
0x18004e88f  test    eax, eax
0x18004e891  jns     short loc_18004E899
0x18004e893  lea     rcx, [rbp+var_18]
0x18004e897  jmp     short loc_18004E874
0x18004e899  movsxd  rax, [rbp+arg_10]
0x18004e89d  mov     r8d, [rdi+48h]
0x18004e8a1  mov     rcx, rax
0x18004e8a4  sub     r8d, eax; int
0x18004e8a7  mov     rax, [rdi+40h]
0x18004e8ab  lea     rdx, [rax+rcx*2]; unsigned __int16 *
0x18004e8af  lea     rcx, [rbp+var_18]; this
0x18004e8b3  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x18004e8b8  mov     r15d, eax
0x18004e8bb  test    eax, eax
0x18004e8bd  js      short loc_18004E893
0x18004e8bf  cmp     [rbp+var_8], 0
0x18004e8c3  jz      short loc_18004E8CD
0x18004e8c5  mov     r15d, 8007000Eh
0x18004e8cb  jmp     short loc_18004E893
0x18004e8cd  mov     rcx, [rdi+40h]; Block
0x18004e8d1  call    cs:__imp_free
0x18004e8d8  nop     dword ptr [rax+rax+00h]
0x18004e8dd  lea     rcx, [rbp+var_18]; this
0x18004e8e1  call    ?PszReset@BuildString@@QEAAPEAGXZ; BuildString::PszReset(void)
0x18004e8e6  mov     rcx, [rbp+arg_18]
0x18004e8ea  inc     r12d
0x18004e8ed  mov     [rdi+40h], rax
0x18004e8f1  mov     eax, ebx
0x18004e8f3  sub     eax, r14d
0x18004e8f6  add     [rdi+48h], eax
0x18004e8f9  lea     eax, [rbx+rsi]
0x18004e8fc  mov     [rcx], eax
0x18004e8fe  mov     rcx, [rdi+20h]
0x18004e902  cmp     r12d, [rcx+1Ch]
0x18004e906  jge     short loc_18004E93E
0x18004e908  sub     ebx, r14d
0x18004e90b  movsxd  rax, dword ptr [rcx+0Ch]
0x18004e90f  mov     r8, rax; Size
0x18004e912  imul    eax, r12d
0x18004e916  movsxd  rdx, eax
0x18004e919  add     rdx, [rcx+10h]; Src
0x18004e91d  lea     rcx, [rbp+var_20]; void *
0x18004e921  call    memcpy_0
0x18004e926  mov     rcx, [rbp+var_20]; this
0x18004e92a  mov     edx, ebx; int
0x18004e92c  call    ?AdjustOffsets@AutEntry@@QEAAXJ@Z; AutEntry::AdjustOffsets(long)
0x18004e931  mov     rcx, [rdi+20h]
0x18004e935  inc     r12d
0x18004e938  cmp     r12d, [rcx+1Ch]
0x18004e93c  jl      short loc_18004E90B
0x18004e93e  lea     rcx, [rbp+var_18]; this
0x18004e942  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x18004e947  xor     eax, eax
0x18004e949  mov     rbx, [rsp+40h+arg_0]
0x18004e951  add     rsp, 40h
0x18004e955  pop     r15
0x18004e957  pop     r14
0x18004e959  pop     r13
0x18004e95b  pop     r12
0x18004e95d  pop     rdi
0x18004e95e  pop     rsi
0x18004e95f  pop     rbp
0x18004e960  retn
```
