# SvcCopyUnicodeStringToBuffer

- ea: `0x140011ba0`
- end: `0x140011cb2`
- name: `SvcCopyUnicodeStringToBuffer`
- size: `274`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x140026390`
- `0x140026790`
- `0x140026ac8`
- `0x140026f40`
- `0x140027490`
- `0x140027870`

## callees

- `0x140011ba0`
- `0x14002a410`
- `0x14004196c`
- `0x140041a0c`
- `0x140041a98`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x140011be0`
- `ntoskrnl!ExGetPreviousMode` at `0x140011c0d`
- `ntoskrnl!ExGetPreviousMode` at `0x140011c3a`
- `ntoskrnl!ExGetPreviousMode` at `0x140011be0`
- `ntoskrnl!ExGetPreviousMode` at `0x140011c0d`
- `ntoskrnl!ExGetPreviousMode` at `0x140011c3a`

## pseudocode

```c
KPROCESSOR_MODE __fastcall SvcCopyUnicodeStringToBuffer(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        _DWORD *a3,
        _QWORD *a4)
{
  unsigned __int64 v8; // rbx
  __int64 v9; // rsi
  char *v10; // rbx
  KPROCESSOR_MODE result; // al
  KPROCESSOR_MODE PreviousMode; // al
  void *v13; // rdx
  size_t v14; // r8

  v8 = a2 + 2 * ((unsigned __int64)(unsigned int)*a3 >> 1);
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
  result = ExGetPreviousMode();
  if ( (unsigned __int64)v10 < a2 )
  {
    if ( result )
      return RtlWriteULong64ToUser(a4, 0);
    else
      *a4 = 0;
  }
  else
  {
    if ( result )
      RtlWriteULong64ToUser(a4, v10);
    else
      *a4 = v10;
    if ( (_DWORD)v9 )
    {
      PreviousMode = ExGetPreviousMode();
      v13 = (void *)*((_QWORD *)a1 + 1);
      v14 = 2LL * (unsigned int)v9;
      if ( PreviousMode )
        RtlCopyToUser(v10, v13, v14);
      else
        RtlCopyVolatileMemory(v10, v13, v14);
    }
    if ( ExGetPreviousMode() )
    {
      result = RtlWriteUShortToUser(&v10[2 * v9], 0);
    }
    else
    {
      result = 0;
      *(_WORD *)&v10[2 * v9] = 0;
    }
    *a3 = (_DWORD)v10 - a2;
  }
  return result;
}

```

## disassembly

```asm
0x140011ba0  push    rbx
0x140011ba2  push    rbp
0x140011ba3  push    rsi
0x140011ba4  push    rdi
0x140011ba5  push    r14
0x140011ba7  push    r15
0x140011ba9  sub     rsp, 28h
0x140011bad  mov     eax, [r8]
0x140011bb0  mov     rdi, r9
0x140011bb3  shr     rax, 1
0x140011bb6  mov     r15, r8
0x140011bb9  cmp     qword ptr [rcx+8], 0
0x140011bbe  mov     r14, rdx
0x140011bc1  mov     rbp, rcx
0x140011bc4  lea     rbx, [rdx+rax*2]
0x140011bc8  jz      short loc_140011BDA
0x140011bca  movzx   esi, word ptr [rcx]
0x140011bcd  shr     esi, 1
0x140011bcf  lea     ecx, [rsi+1]
0x140011bd2  add     rcx, rcx
0x140011bd5  sub     rbx, rcx
0x140011bd8  jmp     short loc_140011BE0
0x140011bda  xor     esi, esi
0x140011bdc  add     rbx, 0FFFFFFFFFFFFFFFEh
0x140011be0  call    cs:__imp_ExGetPreviousMode
0x140011be7  nop     dword ptr [rax+rax+00h]
0x140011bec  cmp     rbx, r14
0x140011bef  jb      loc_140011C81
0x140011bf5  test    al, al
0x140011bf7  jz      short loc_140011C06
0x140011bf9  mov     rdx, rbx
0x140011bfc  mov     rcx, rdi
0x140011bff  call    RtlWriteULong64ToUser
0x140011c04  jmp     short loc_140011C09
0x140011c06  mov     [rdi], rbx
0x140011c09  test    esi, esi
0x140011c0b  jz      short loc_140011C36
0x140011c0d  call    cs:__imp_ExGetPreviousMode
0x140011c14  nop     dword ptr [rax+rax+00h]
0x140011c19  mov     rdx, [rbp+8]; Src
0x140011c1d  mov     rcx, rbx; void *
0x140011c20  mov     r8d, esi
0x140011c23  add     r8, r8; Size
0x140011c26  test    al, al
0x140011c28  jz      short loc_140011C31
0x140011c2a  call    RtlCopyToUser
0x140011c2f  jmp     short loc_140011C36
0x140011c31  call    RtlCopyVolatileMemory
0x140011c36  lea     rdi, [rbx+rsi*2]
0x140011c3a  call    cs:__imp_ExGetPreviousMode
0x140011c41  nop     dword ptr [rax+rax+00h]
0x140011c46  test    al, al
0x140011c48  jz      short loc_140011C68
0x140011c4a  xor     edx, edx
0x140011c4c  mov     rcx, rdi
0x140011c4f  call    RtlWriteUShortToUser
0x140011c54  sub     ebx, r14d
0x140011c57  mov     [r15], ebx
0x140011c5a  add     rsp, 28h
0x140011c5e  pop     r15
0x140011c60  pop     r14
0x140011c62  pop     rdi
0x140011c63  pop     rsi
0x140011c64  pop     rbp
0x140011c65  pop     rbx
0x140011c66  retn
0x140011c68  xor     eax, eax
0x140011c6a  sub     ebx, r14d
0x140011c6d  mov     [rdi], ax
0x140011c70  mov     [r15], ebx
0x140011c73  add     rsp, 28h
0x140011c77  pop     r15
0x140011c79  pop     r14
0x140011c7b  pop     rdi
0x140011c7c  pop     rsi
0x140011c7d  pop     rbp
0x140011c7e  pop     rbx
0x140011c7f  retn
0x140011c81  test    al, al
0x140011c83  jz      short loc_140011C9D
0x140011c85  xor     edx, edx
0x140011c87  mov     rcx, rdi
0x140011c8a  call    RtlWriteULong64ToUser
0x140011c8f  add     rsp, 28h
0x140011c93  pop     r15
0x140011c95  pop     r14
0x140011c97  pop     rdi
0x140011c98  pop     rsi
0x140011c99  pop     rbp
0x140011c9a  pop     rbx
0x140011c9b  retn
0x140011c9d  mov     qword ptr [rdi], 0
0x140011ca4  add     rsp, 28h
0x140011ca8  pop     r15
0x140011caa  pop     r14
0x140011cac  pop     rdi
0x140011cad  pop     rsi
0x140011cae  pop     rbp
0x140011caf  pop     rbx
0x140011cb0  retn
```
