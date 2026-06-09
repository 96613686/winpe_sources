# write_text_utf8_nolock

- ea: `0x100434b8c`
- end: `0x100434cfc`
- name: `write_text_utf8_nolock`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x100434e28`

## callees

- `0x100426580`
- `0x100430244`
- `0x100434b8c`
- `0x100439280`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100434cc5`
- `KERNEL32!GetLastError` at `0x100434cc5`
- `KERNEL32!WriteFile` at `0x100434ca3`
- `KERNEL32!WriteFile` at `0x100434ca3`

## pseudocode

```c
__int64 __fastcall write_text_utf8_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // r14
  int v6; // r15d
  __int16 *v7; // rdi
  void *v8; // r12
  bool v9; // cf
  char *v10; // rax
  __int16 v11; // cx
  unsigned int v12; // ebp
  unsigned int v13; // esi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-1458h] BYREF
  _BYTE v16[1704]; // [rsp+50h] [rbp-1448h] BYREF
  char v17; // [rsp+6F8h] [rbp-DA0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+700h] [rbp-D98h] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = (int)a3;
  v7 = a3;
  v8 = *(void **)(_pioinfo[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  v9 = (unsigned __int64)a3 < v5;
  *(_DWORD *)(a1 + 8) = 0;
LABEL_2:
  if ( v9 )
  {
    v10 = v16;
    do
    {
      if ( (unsigned __int64)v7 >= v5 )
        break;
      v11 = *v7++;
      if ( v11 == 10 )
      {
        *(_WORD *)v10 = 13;
        v10 += 2;
      }
      *(_WORD *)v10 = v11;
      v10 += 2;
    }
    while ( v10 < &v17 );
    v12 = _acrt_WideCharToMultiByte(
            65001,
            0,
            (unsigned int)v16,
            (v10 - v16) >> 1,
            (unsigned int)&Overlapped,
            3413,
            0,
            0);
    if ( v12 )
    {
      v13 = 0;
      while ( WriteFile(v8, (char *)&Overlapped + v13, v12 - v13, &NumberOfBytesWritten, 0) )
      {
        v13 += NumberOfBytesWritten;
        if ( v13 >= v12 )
        {
          *(_DWORD *)(a1 + 4) = (_DWORD)v7 - v6;
          v9 = (unsigned __int64)v7 < v5;
          goto LABEL_2;
        }
      }
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x100434b8c  mov     [rsp+arg_0], rbx
0x100434b91  mov     [rsp+arg_10], rbp
0x100434b96  push    rsi
0x100434b97  push    rdi
0x100434b98  push    r12
0x100434b9a  push    r14
0x100434b9c  push    r15
0x100434b9e  mov     eax, 1470h
0x100434ba3  call    _alloca_probe
0x100434ba8  sub     rsp, rax
0x100434bab  mov     rax, cs:__security_cookie
0x100434bb2  xor     rax, rsp
0x100434bb5  mov     [rsp+1498h+var_38], rax
0x100434bbd  movsxd  r10, edx
0x100434bc0  mov     rbx, rcx
0x100434bc3  mov     rax, r10
0x100434bc6  mov     r14d, r9d
0x100434bc9  sar     rax, 6
0x100434bcd  lea     rcx, __pioinfo
0x100434bd4  and     r10d, 3Fh
0x100434bd8  add     r14, r8
0x100434bdb  mov     r15, r8
0x100434bde  mov     rdi, r8
0x100434be1  mov     rax, [rcx+rax*8]
0x100434be5  lea     rdx, [r10+r10*8]
0x100434be9  mov     r12, [rax+rdx*8+28h]
0x100434bee  xor     eax, eax
0x100434bf0  mov     [rbx], rax
0x100434bf3  cmp     r8, r14
0x100434bf6  mov     [rbx+8], eax
0x100434bf9  jnb     loc_100434CCD
0x100434bff  lea     rax, [rsp+1498h+var_1448]
0x100434c04  cmp     rdi, r14
0x100434c07  jnb     short loc_100434C36
0x100434c09  movzx   ecx, word ptr [rdi]
0x100434c0c  add     rdi, 2
0x100434c10  cmp     cx, 0Ah
0x100434c14  jnz     short loc_100434C22
0x100434c16  mov     edx, 0Dh
0x100434c1b  mov     [rax], dx
0x100434c1e  add     rax, 2
0x100434c22  mov     [rax], cx
0x100434c25  add     rax, 2
0x100434c29  lea     rcx, [rsp+1498h+var_DA0]
0x100434c31  cmp     rax, rcx
0x100434c34  jb      short loc_100434C04
0x100434c36  and     [rsp+1498h+var_1460], 0
0x100434c3c  lea     rcx, [rsp+1498h+var_1448]
0x100434c41  and     [rsp+1498h+var_1468], 0
0x100434c47  lea     r8, [rsp+1498h+var_1448]
0x100434c4c  sub     rax, rcx
0x100434c4f  mov     [rsp+1498h+var_1470], 0D55h
0x100434c57  lea     rcx, [rsp+1498h+Overlapped]
0x100434c5f  sar     rax, 1
0x100434c62  mov     [rsp+1498h+lpOverlapped], rcx; lpOverlapped
0x100434c67  mov     r9d, eax
0x100434c6a  mov     ecx, 0FDE9h
0x100434c6f  xor     edx, edx
0x100434c71  call    __acrt_WideCharToMultiByte
0x100434c76  mov     ebp, eax
0x100434c78  test    eax, eax
0x100434c7a  jz      short loc_100434CC5
0x100434c7c  xor     esi, esi
0x100434c7e  test    eax, eax
0x100434c80  jz      short loc_100434CB5
0x100434c82  and     [rsp+1498h+lpOverlapped], 0
0x100434c88  lea     rdx, [rsp+1498h+Overlapped]
0x100434c90  mov     ecx, esi
0x100434c92  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100434c97  mov     r8d, ebp
0x100434c9a  add     rdx, rcx; lpBuffer
0x100434c9d  mov     rcx, r12; hFile
0x100434ca0  sub     r8d, esi; nNumberOfBytesToWrite
0x100434ca3  call    cs:__imp_WriteFile
0x100434ca9  test    eax, eax
0x100434cab  jz      short loc_100434CC5
0x100434cad  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x100434cb1  cmp     esi, ebp
0x100434cb3  jb      short loc_100434C82
0x100434cb5  mov     eax, edi
0x100434cb7  sub     eax, r15d
0x100434cba  mov     [rbx+4], eax
0x100434cbd  cmp     rdi, r14
0x100434cc0  jmp     loc_100434BF9
0x100434cc5  call    cs:__imp_GetLastError
0x100434ccb  mov     [rbx], eax
0x100434ccd  mov     rax, rbx
0x100434cd0  mov     rcx, [rsp+1498h+var_38]
0x100434cd8  xor     rcx, rsp; StackCookie
0x100434cdb  call    __security_check_cookie
0x100434ce0  lea     r11, [rsp+1498h+var_28]
0x100434ce8  mov     rbx, [r11+30h]
0x100434cec  mov     rbp, [r11+40h]
0x100434cf0  mov     rsp, r11
0x100434cf3  pop     r15
0x100434cf5  pop     r14
0x100434cf7  pop     r12
0x100434cf9  pop     rdi
0x100434cfa  pop     rsi
0x100434cfb  retn
```
