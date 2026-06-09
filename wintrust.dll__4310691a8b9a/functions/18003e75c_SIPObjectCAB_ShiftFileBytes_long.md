# SIPObjectCAB_::ShiftFileBytes(long)

- ea: `0x18003e75c`
- end: `0x18003e89e`
- name: `?ShiftFileBytes@SIPObjectCAB_@@AEAAHJ@Z`
- size: `322`
- prototype: `__int64 __fastcall(SIPObjectCAB_ *__hidden this, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18003e548`

## callees

- `0x180014eac`
- `0x18003e75c`
- `0x18003ee30`
- `0x180051010`

## import_xrefs

- `msvcrt!free` at `0x18003e7fd`
- `msvcrt!free` at `0x18003e7fd`
- `msvcrt!malloc` at `0x18003e7a0`
- `msvcrt!malloc` at `0x18003e7a0`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18003e87f`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18003e87f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003e782`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003e85a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003e782`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003e85a`

## pseudocode

```c
__int64 __fastcall SIPObjectCAB_::ShiftFileBytes(HANDLE *this, int a2)
{
  DWORD v4; // eax
  unsigned int v5; // r12d
  unsigned int v6; // r14d
  int v7; // ebp
  LONG v8; // r13d
  unsigned __int8 *v9; // rsi
  DWORD v10; // ebx
  unsigned int v11; // ebx

  v4 = SetFilePointer(this[1], 0, 0, 1u);
  v5 = *((_DWORD *)this + 48);
  v6 = v4;
  v7 = v5 - v4;
  v8 = v5 + a2;
  v9 = (unsigned __int8 *)malloc(0x2000u);
  if ( v9 )
  {
    while ( v7 )
    {
      v10 = 0x2000;
      if ( v7 < 0x2000 )
        v10 = v7;
      if ( a2 <= 0 )
      {
        if ( a2 < 0 )
        {
          if ( !SIPObject_::SeekAndReadFile(this, v6, v9, v10) || !SIPObject_::SeekAndWriteFile(this, v6 + a2, v9, v10) )
            goto LABEL_8;
          v6 += v10;
        }
      }
      else
      {
        v5 -= v10;
        if ( !SIPObject_::SeekAndReadFile(this, v5, v9, v10) || !SIPObject_::SeekAndWriteFile(this, v5 + a2, v9, v10) )
          goto LABEL_8;
      }
      v7 -= v10;
    }
    if ( SetFilePointer(this[1], v8, 0, 0) == -1 )
    {
      v11 = 0;
    }
    else
    {
      (*((void (__fastcall **)(HANDLE *))*this + 19))(this);
      SetEndOfFile(this[1]);
      v11 = (*((__int64 (__fastcall **)(HANDLE *))*this + 18))(this);
    }
    goto LABEL_9;
  }
LABEL_8:
  v11 = 0;
  if ( v9 )
LABEL_9:
    free(v9);
  return v11;
}

```

## disassembly

```asm
0x18003e75c  push    rbx
0x18003e75e  push    rbp
0x18003e75f  push    rsi
0x18003e760  push    rdi
0x18003e761  push    r12
0x18003e763  push    r13
0x18003e765  push    r14
0x18003e767  push    r15
0x18003e769  sub     rsp, 28h
0x18003e76d  mov     r15d, edx
0x18003e770  mov     rdi, rcx
0x18003e773  mov     rcx, [rcx+8]; hFile
0x18003e777  xor     edx, edx; lDistanceToMove
0x18003e779  mov     r9d, 1; dwMoveMethod
0x18003e77f  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003e782  call    cs:__imp_SetFilePointer
0x18003e788  mov     r12d, [rdi+0C0h]
0x18003e78f  mov     ecx, 2000h; Size
0x18003e794  mov     ebp, r12d
0x18003e797  mov     r14d, eax
0x18003e79a  sub     ebp, eax
0x18003e79c  lea     r13d, [r12+r15]
0x18003e7a0  call    cs:__imp_malloc
0x18003e7a6  mov     rsi, rax
0x18003e7a9  test    rax, rax
0x18003e7ac  jz      short loc_18003E7F3
0x18003e7ae  test    ebp, ebp
0x18003e7b0  jz      loc_18003E84D
0x18003e7b6  mov     ebx, 2000h
0x18003e7bb  cmp     ebp, ebx
0x18003e7bd  cmovl   ebx, ebp
0x18003e7c0  test    r15d, r15d
0x18003e7c3  jle     short loc_18003E816
0x18003e7c5  sub     r12d, ebx
0x18003e7c8  mov     r9d, ebx; unsigned int
0x18003e7cb  mov     edx, r12d; unsigned int
0x18003e7ce  mov     r8, rsi; unsigned __int8 *
0x18003e7d1  mov     rcx, rdi; this
0x18003e7d4  call    ?SeekAndReadFile@SIPObject_@@IEAAHKPEAEK@Z; SIPObject_::SeekAndReadFile(ulong,uchar *,ulong)
0x18003e7d9  test    eax, eax
0x18003e7db  jz      short loc_18003E7F3
0x18003e7dd  lea     edx, [r12+r15]; unsigned int
0x18003e7e1  mov     r9d, ebx; unsigned int
0x18003e7e4  mov     r8, rsi; unsigned __int8 *
0x18003e7e7  mov     rcx, rdi; this
0x18003e7ea  call    ?SeekAndWriteFile@SIPObject_@@IEAAHKPEAEK@Z; SIPObject_::SeekAndWriteFile(ulong,uchar *,ulong)
0x18003e7ef  test    eax, eax
0x18003e7f1  jnz     short loc_18003E846
0x18003e7f3  xor     ebx, ebx
0x18003e7f5  test    rsi, rsi
0x18003e7f8  jz      short loc_18003E803
0x18003e7fa  mov     rcx, rsi; Block
0x18003e7fd  call    cs:__imp_free
0x18003e803  mov     eax, ebx
0x18003e805  add     rsp, 28h
0x18003e809  pop     r15
0x18003e80b  pop     r14
0x18003e80d  pop     r13
0x18003e80f  pop     r12
0x18003e811  pop     rdi
0x18003e812  pop     rsi
0x18003e813  pop     rbp
0x18003e814  pop     rbx
0x18003e815  retn
0x18003e816  jns     short loc_18003E846
0x18003e818  mov     r9d, ebx; unsigned int
0x18003e81b  mov     r8, rsi; unsigned __int8 *
0x18003e81e  mov     edx, r14d; unsigned int
0x18003e821  mov     rcx, rdi; this
0x18003e824  call    ?SeekAndReadFile@SIPObject_@@IEAAHKPEAEK@Z; SIPObject_::SeekAndReadFile(ulong,uchar *,ulong)
0x18003e829  test    eax, eax
0x18003e82b  jz      short loc_18003E7F3
0x18003e82d  lea     edx, [r14+r15]; unsigned int
0x18003e831  mov     r9d, ebx; unsigned int
0x18003e834  mov     r8, rsi; unsigned __int8 *
0x18003e837  mov     rcx, rdi; this
0x18003e83a  call    ?SeekAndWriteFile@SIPObject_@@IEAAHKPEAEK@Z; SIPObject_::SeekAndWriteFile(ulong,uchar *,ulong)
0x18003e83f  test    eax, eax
0x18003e841  jz      short loc_18003E7F3
0x18003e843  add     r14d, ebx
0x18003e846  sub     ebp, ebx
0x18003e848  jmp     loc_18003E7AE
0x18003e84d  mov     rcx, [rdi+8]; hFile
0x18003e851  xor     r9d, r9d; dwMoveMethod
0x18003e854  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003e857  mov     edx, r13d; lDistanceToMove
0x18003e85a  call    cs:__imp_SetFilePointer
0x18003e860  cmp     eax, 0FFFFFFFFh
0x18003e863  jnz     short loc_18003E869
0x18003e865  xor     ebx, ebx
0x18003e867  jmp     short loc_18003E7FA
0x18003e869  mov     rax, [rdi]
0x18003e86c  mov     rcx, rdi
0x18003e86f  mov     rax, [rax+98h]
0x18003e876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e87b  mov     rcx, [rdi+8]; hFile
0x18003e87f  call    cs:__imp_SetEndOfFile
0x18003e885  mov     rax, [rdi]
0x18003e888  mov     rcx, rdi
0x18003e88b  mov     rax, [rax+90h]
0x18003e892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e897  mov     ebx, eax
0x18003e899  jmp     loc_18003E7FA
```
