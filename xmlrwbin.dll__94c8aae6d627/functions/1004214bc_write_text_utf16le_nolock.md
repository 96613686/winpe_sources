# write_text_utf16le_nolock

- ea: `0x1004214bc`
- end: `0x1004215d5`
- name: `write_text_utf16le_nolock`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100421878`

## callees

- `0x100416590`
- `0x1004214bc`
- `0x100423b30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1004215a2`
- `KERNEL32!GetLastError` at `0x1004215a2`
- `KERNEL32!WriteFile` at `0x100421586`
- `KERNEL32!WriteFile` at `0x100421586`

## pseudocode

```c
__int64 __fastcall write_text_utf16le_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // rbp
  __int16 *v6; // rsi
  void *v7; // r14
  char *v8; // rbx
  __int16 v9; // ax
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5118]; // [rsp+40h] [rbp-1428h] BYREF
  __int16 v15; // [rsp+143Eh] [rbp-2Ah] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = a3;
  v7 = *(void **)(_pioinfo[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
    while ( 1 )
    {
      v8 = Buffer;
      do
      {
        if ( (unsigned __int64)v6 >= v5 )
          break;
        v9 = *v6++;
        if ( v9 == 10 )
        {
          *(_DWORD *)(a1 + 8) += 2;
          *(_WORD *)v8 = 13;
          v8 += 2;
        }
        *(_WORD *)v8 = v9;
        v8 += 2;
      }
      while ( v8 < (char *)&v15 );
      v10 = 2 * ((v8 - Buffer) >> 1);
      if ( !WriteFile(v7, Buffer, v10, &NumberOfBytesWritten, 0) )
        break;
      v11 = NumberOfBytesWritten;
      *(_DWORD *)(a1 + 4) += NumberOfBytesWritten;
      if ( v11 < v10 || (unsigned __int64)v6 >= v5 )
        return a1;
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x1004214bc  mov     [rsp+arg_0], rbx
0x1004214c1  mov     [rsp+arg_10], rbp
0x1004214c6  push    rsi
0x1004214c7  push    rdi
0x1004214c8  push    r14
0x1004214ca  mov     eax, 1450h
0x1004214cf  call    _alloca_probe
0x1004214d4  sub     rsp, rax
0x1004214d7  mov     rax, cs:__security_cookie
0x1004214de  xor     rax, rsp
0x1004214e1  mov     [rsp+1468h+var_28], rax
0x1004214e9  movsxd  r10, edx
0x1004214ec  mov     rdi, rcx
0x1004214ef  mov     rax, r10
0x1004214f2  mov     ebp, r9d
0x1004214f5  sar     rax, 6
0x1004214f9  lea     rcx, __pioinfo
0x100421500  and     r10d, 3Fh
0x100421504  add     rbp, r8
0x100421507  mov     rsi, r8
0x10042150a  mov     rax, [rcx+rax*8]
0x10042150e  lea     rdx, [r10+r10*8]
0x100421512  mov     r14, [rax+rdx*8+28h]
0x100421517  xor     eax, eax
0x100421519  mov     [rdi], rax
0x10042151c  mov     [rdi+8], eax
0x10042151f  cmp     r8, rbp
0x100421522  jnb     loc_1004215AA
0x100421528  lea     rbx, [rsp+1468h+Buffer]
0x10042152d  cmp     rsi, rbp
0x100421530  jnb     short loc_100421563
0x100421532  movzx   eax, word ptr [rsi]
0x100421535  add     rsi, 2
0x100421539  cmp     ax, 0Ah
0x10042153d  jnz     short loc_10042154F
0x10042153f  add     dword ptr [rdi+8], 2
0x100421543  mov     ecx, 0Dh
0x100421548  mov     [rbx], cx
0x10042154b  add     rbx, 2
0x10042154f  mov     [rbx], ax
0x100421552  add     rbx, 2
0x100421556  lea     rax, [rsp+1468h+var_2A]
0x10042155e  cmp     rbx, rax
0x100421561  jb      short loc_10042152D
0x100421563  and     [rsp+1468h+var_1448], 0
0x100421569  lea     rax, [rsp+1468h+Buffer]
0x10042156e  sub     rbx, rax
0x100421571  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100421576  sar     rbx, 1
0x100421579  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x10042157e  add     ebx, ebx
0x100421580  mov     rcx, r14; hFile
0x100421583  mov     r8d, ebx; nNumberOfBytesToWrite
0x100421586  call    cs:__imp_WriteFile
0x10042158c  test    eax, eax
0x10042158e  jz      short loc_1004215A2
0x100421590  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x100421594  add     [rdi+4], eax
0x100421597  cmp     eax, ebx
0x100421599  jb      short loc_1004215AA
0x10042159b  cmp     rsi, rbp
0x10042159e  jb      short loc_100421528
0x1004215a0  jmp     short loc_1004215AA
0x1004215a2  call    cs:__imp_GetLastError
0x1004215a8  mov     [rdi], eax
0x1004215aa  mov     rax, rdi
0x1004215ad  mov     rcx, [rsp+1468h+var_28]
0x1004215b5  xor     rcx, rsp; StackCookie
0x1004215b8  call    __security_check_cookie
0x1004215bd  lea     r11, [rsp+1468h+var_18]
0x1004215c5  mov     rbx, [r11+20h]
0x1004215c9  mov     rbp, [r11+30h]
0x1004215cd  mov     rsp, r11
0x1004215d0  pop     r14
0x1004215d2  pop     rdi
0x1004215d3  pop     rsi
0x1004215d4  retn
```
