# SrvLibLogError

- ea: `0x140029310`
- end: `0x14002948f`
- name: `SrvLibLogError`
- size: `383`
- prototype: `__int64 __usercall@<rax>(PVOID IoObject@<rcx>, __int16, __int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140029310`
- `0x14002a540`

## import_xrefs

- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400293b8`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x1400293b8`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140029471`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x140029471`

## pseudocode

```c
void __fastcall SrvLibLogError(
        PVOID IoObject,
        int a2,
        int a3,
        const void *a4,
        unsigned __int16 a5,
        __int64 a6,
        unsigned int a7)
{
  unsigned int v10; // r10d
  unsigned int v12; // edx
  int v13; // ecx
  unsigned int v14; // ecx
  __int64 v15; // rdi
  char *ErrorLogEntry; // rax
  char *v17; // rbx
  unsigned int v18; // ebp
  char *i; // rdi

  v10 = 0;
  v12 = 48;
  while ( v10 < a7 )
  {
    v13 = *(unsigned __int16 *)(a6 + 16LL * v10);
    if ( (_WORD)v13 )
    {
      if ( (v13 & 1) != 0 )
        return;
      v14 = v12 + v13;
      if ( v14 < v12 )
        return;
      v12 = v14;
    }
    if ( v12 + 2 < v12 )
      return;
    v12 += 2;
    ++v10;
  }
  if ( a4 )
  {
    v15 = (a5 + 1) & 0xFFFFFFFE;
    if ( (unsigned int)v15 + v12 < v12 )
      return;
    v12 += v15;
  }
  else
  {
    v15 = 0;
  }
  if ( v12 <= 0xF0 )
  {
    ErrorLogEntry = (char *)IoAllocateErrorLogEntry(IoObject, v12);
    v17 = ErrorLogEntry;
    if ( ErrorLogEntry )
    {
      *((_DWORD *)ErrorLogEntry + 3) = a2;
      *(_WORD *)ErrorLogEntry = 0;
      *((_DWORD *)ErrorLogEntry + 4) = 0;
      *((_DWORD *)ErrorLogEntry + 7) = 0;
      *((_QWORD *)ErrorLogEntry + 4) = 0;
      *((_DWORD *)ErrorLogEntry + 5) = a3;
      *((_WORD *)ErrorLogEntry + 2) = a7;
      *((_DWORD *)ErrorLogEntry + 6) = 0;
      *((_WORD *)ErrorLogEntry + 3) = v15 + 40;
      *((_WORD *)ErrorLogEntry + 1) = a4 != 0 ? a5 : 0;
      if ( a4 )
        memmove(ErrorLogEntry + 40, a4, a5);
      v18 = 0;
      for ( i = &v17[v15 + 40]; v18 < a7; i += 2 )
      {
        if ( *(_WORD *)(a6 + 16LL * v18) )
        {
          memmove(i, *(const void **)(a6 + 16LL * v18 + 8), *(unsigned __int16 *)(a6 + 16LL * v18));
          i += 2 * ((unsigned __int64)*(unsigned __int16 *)(a6 + 16LL * v18) >> 1);
        }
        *(_WORD *)i = 0;
        ++v18;
      }
      IoWriteErrorLogEntry(v17);
    }
  }
}

```

## disassembly

```asm
0x140029310  push    rbx
0x140029312  push    rbp
0x140029313  push    rsi
0x140029314  push    rdi
0x140029315  push    r12
0x140029317  push    r13
0x140029319  push    r14
0x14002931b  push    r15
0x14002931d  sub     rsp, 28h
0x140029321  mov     r15, [rsp+68h+arg_28]
0x140029329  mov     r12d, r8d
0x14002932c  mov     r14d, [rsp+68h+arg_30]
0x140029334  xor     r8d, r8d
0x140029337  mov     rbp, r9
0x14002933a  mov     r13d, edx
0x14002933d  mov     r10d, r8d
0x140029340  mov     r9, rcx
0x140029343  mov     edx, 30h ; '0'; EntrySize
0x140029348  cmp     r10d, r14d
0x14002934b  jnb     short loc_140029384
0x14002934d  mov     eax, r10d
0x140029350  add     rax, rax
0x140029353  movzx   ecx, word ptr [r15+rax*8]
0x140029358  test    cx, cx
0x14002935b  jz      short loc_140029372
0x14002935d  test    cl, 1
0x140029360  jnz     loc_14002947D
0x140029366  add     ecx, edx
0x140029368  cmp     ecx, edx
0x14002936a  jb      loc_14002947D
0x140029370  mov     edx, ecx
0x140029372  lea     eax, [rdx+2]
0x140029375  cmp     eax, edx
0x140029377  jb      loc_14002947D
0x14002937d  mov     edx, eax
0x14002937f  inc     r10d
0x140029382  jmp     short loc_140029348
0x140029384  movzx   esi, [rsp+68h+arg_20]
0x14002938c  test    rbp, rbp
0x14002938f  jz      short loc_1400293A6
0x140029391  lea     edi, [rsi+1]
0x140029394  and     edi, 0FFFFFFFEh
0x140029397  lea     eax, [rdi+rdx]
0x14002939a  cmp     eax, edx
0x14002939c  jb      loc_14002947D
0x1400293a2  mov     edx, eax
0x1400293a4  jmp     short loc_1400293A9
0x1400293a6  mov     edi, r8d
0x1400293a9  cmp     edx, 0F0h
0x1400293af  ja      loc_14002947D
0x1400293b5  mov     rcx, r9; IoObject
0x1400293b8  call    cs:__imp_IoAllocateErrorLogEntry
0x1400293bf  nop     dword ptr [rax+rax+00h]
0x1400293c4  mov     rbx, rax
0x1400293c7  test    rax, rax
0x1400293ca  jz      loc_14002947D
0x1400293d0  mov     [rax+0Ch], r13d
0x1400293d4  xor     r13d, r13d
0x1400293d7  mov     [rax], r13w
0x1400293db  mov     [rax+10h], r13d
0x1400293df  mov     [rax+1Ch], r13d
0x1400293e3  mov     [rax+20h], r13
0x1400293e7  mov     [rax+14h], r12d
0x1400293eb  mov     rax, rbp
0x1400293ee  neg     rax
0x1400293f1  mov     [rbx+4], r14w
0x1400293f6  lea     eax, [rdi+28h]
0x1400293f9  mov     [rbx+18h], r13d
0x1400293fd  sbb     cx, cx
0x140029400  mov     [rbx+6], ax
0x140029404  and     cx, si
0x140029407  mov     [rbx+2], cx
0x14002940b  test    rbp, rbp
0x14002940e  jz      short loc_140029425
0x140029410  movzx   r8d, [rsp+68h+arg_20]; Size
0x140029419  lea     rcx, [rbx+28h]; void *
0x14002941d  mov     rdx, rbp; Src
0x140029420  call    memmove
0x140029425  add     rdi, 28h ; '('
0x140029429  mov     ebp, r13d
0x14002942c  add     rdi, rbx
0x14002942f  test    r14d, r14d
0x140029432  jz      short loc_14002946E
0x140029434  mov     esi, ebp
0x140029436  add     rsi, rsi
0x140029439  movzx   eax, word ptr [r15+rsi*8]
0x14002943e  test    ax, ax
0x140029441  jz      short loc_14002945F
0x140029443  mov     rdx, [r15+rsi*8+8]; Src
0x140029448  mov     r8d, eax; Size
0x14002944b  mov     rcx, rdi; void *
0x14002944e  call    memmove
0x140029453  movzx   eax, word ptr [r15+rsi*8]
0x140029458  shr     rax, 1
0x14002945b  lea     rdi, [rdi+rax*2]
0x14002945f  mov     [rdi], r13w
0x140029463  inc     ebp
0x140029465  add     rdi, 2
0x140029469  cmp     ebp, r14d
0x14002946c  jb      short loc_140029434
0x14002946e  mov     rcx, rbx; ElEntry
0x140029471  call    cs:__imp_IoWriteErrorLogEntry
0x140029478  nop     dword ptr [rax+rax+00h]
0x14002947d  add     rsp, 28h
0x140029481  pop     r15
0x140029483  pop     r14
0x140029485  pop     r13
0x140029487  pop     r12
0x140029489  pop     rdi
0x14002948a  pop     rsi
0x14002948b  pop     rbp
0x14002948c  pop     rbx
0x14002948d  retn
```
