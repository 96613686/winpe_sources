# SvcCopyUnicodeStringToBuffer1

- ea: `0x14002561c`
- end: `0x1400256cb`
- name: `SvcCopyUnicodeStringToBuffer1`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400116b0`
- `0x14005721c`

## callees

- `0x14002561c`
- `0x14002a410`
- `0x14004196c`
- `0x140041a98`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x140025663`
- `ntoskrnl!ExGetPreviousMode` at `0x140025690`
- `ntoskrnl!ExGetPreviousMode` at `0x140025663`
- `ntoskrnl!ExGetPreviousMode` at `0x140025690`

## pseudocode

```c
unsigned __int64 __fastcall SvcCopyUnicodeStringToBuffer1(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        _DWORD *a3,
        _QWORD *a4)
{
  unsigned __int64 result; // rax
  int v6; // esi
  unsigned __int64 v8; // rbx
  __int64 v9; // rdi
  char *v10; // rbx
  KPROCESSOR_MODE PreviousMode; // al
  void *v12; // rdx
  size_t v13; // r8
  char *v14; // rdi

  result = (unsigned __int64)(unsigned int)*a3 >> 1;
  v6 = a2;
  v8 = a2 + 2 * result;
  if ( *((_QWORD *)a1 + 1) )
  {
    v9 = *a1 >> 1;
    v10 = (char *)(v8 - 2LL * (unsigned int)(v9 + 1));
  }
  else
  {
    v9 = 0;
    v10 = (char *)(v8 - 2);
  }
  if ( (unsigned __int64)v10 < a2 )
  {
    *a4 = 0;
  }
  else
  {
    *a4 = v10;
    if ( (_DWORD)v9 )
    {
      PreviousMode = ExGetPreviousMode();
      v12 = (void *)*((_QWORD *)a1 + 1);
      v13 = 2LL * (unsigned int)v9;
      if ( PreviousMode )
        RtlCopyToUser(v10, v12, v13);
      else
        RtlCopyVolatileMemory(v10, v12, v13);
    }
    v14 = &v10[2 * v9];
    if ( ExGetPreviousMode() )
    {
      result = RtlWriteUShortToUser(v14, 0);
    }
    else
    {
      result = 0;
      *(_WORD *)v14 = 0;
    }
    *a3 = (_DWORD)v10 - v6;
  }
  return result;
}

```

## disassembly

```asm
0x14002561c  push    rbx
0x14002561e  push    rbp
0x14002561f  push    rsi
0x140025620  push    rdi
0x140025621  push    r14
0x140025623  sub     rsp, 20h
0x140025627  mov     eax, [r8]
0x14002562a  mov     r14, r8
0x14002562d  shr     rax, 1
0x140025630  mov     rsi, rdx
0x140025633  cmp     qword ptr [rcx+8], 0
0x140025638  mov     rbp, rcx
0x14002563b  lea     rbx, [rdx+rax*2]
0x14002563f  jz      short loc_140025651
0x140025641  movzx   edi, word ptr [rcx]
0x140025644  shr     edi, 1
0x140025646  lea     ecx, [rdi+1]
0x140025649  add     rcx, rcx
0x14002564c  sub     rbx, rcx
0x14002564f  jmp     short loc_140025657
0x140025651  xor     edi, edi
0x140025653  add     rbx, 0FFFFFFFFFFFFFFFEh
0x140025657  cmp     rbx, rsi
0x14002565a  jb      short loc_1400256B8
0x14002565c  mov     [r9], rbx
0x14002565f  test    edi, edi
0x140025661  jz      short loc_14002568C
0x140025663  call    cs:__imp_ExGetPreviousMode
0x14002566a  nop     dword ptr [rax+rax+00h]
0x14002566f  mov     rdx, [rbp+8]; Src
0x140025673  mov     rcx, rbx; void *
0x140025676  mov     r8d, edi
0x140025679  add     r8, r8; Size
0x14002567c  test    al, al
0x14002567e  jz      short loc_140025687
0x140025680  call    RtlCopyToUser
0x140025685  jmp     short loc_14002568C
0x140025687  call    RtlCopyVolatileMemory
0x14002568c  lea     rdi, [rbx+rdi*2]
0x140025690  call    cs:__imp_ExGetPreviousMode
0x140025697  nop     dword ptr [rax+rax+00h]
0x14002569c  test    al, al
0x14002569e  jz      short loc_1400256AC
0x1400256a0  xor     edx, edx
0x1400256a2  mov     rcx, rdi
0x1400256a5  call    RtlWriteUShortToUser
0x1400256aa  jmp     short loc_1400256B1
0x1400256ac  xor     eax, eax
0x1400256ae  mov     [rdi], ax
0x1400256b1  sub     ebx, esi
0x1400256b3  mov     [r14], ebx
0x1400256b6  jmp     short loc_1400256BF
0x1400256b8  mov     qword ptr [r9], 0
0x1400256bf  add     rsp, 20h
0x1400256c3  pop     r14
0x1400256c5  pop     rdi
0x1400256c6  pop     rsi
0x1400256c7  pop     rbp
0x1400256c8  pop     rbx
0x1400256c9  retn
```
