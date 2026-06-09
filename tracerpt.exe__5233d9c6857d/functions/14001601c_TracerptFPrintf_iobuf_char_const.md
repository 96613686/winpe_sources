# TracerptFPrintf(_iobuf *,char const *,...)

- ea: `0x14001601c`
- end: `0x14001612a`
- name: `?TracerptFPrintf@@YAKPEAU_iobuf@@PEBDZZ`
- size: `270`
- prototype: `unsigned int(struct _iobuf *, const char *, ...)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000faa4`
- `0x14000fd88`
- `0x14000ffcc`
- `0x1400104f0`
- `0x140010594`
- `0x140010a88`
- `0x140016ae0`
- `0x140018d04`

## callees

- `0x14001601c`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x140016084`
- `msvcrt!_vsnprintf` at `0x140016084`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400160cf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400160cf`

## pseudocode

```c
__int64 TracerptFPrintf(struct _iobuf *a1, const char *a2, ...)
{
  int *p_cnt; // r14
  char v4; // bp
  __int64 flag; // rcx
  unsigned __int64 v6; // rdi
  _BYTE *v7; // rsi
  size_t v8; // rdi
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 result; // rax
  DWORD NumberOfBytesWritten[18]; // [rsp+30h] [rbp-48h] BYREF
  const char *v15; // [rsp+88h] [rbp+10h]
  va_list va; // [rsp+90h] [rbp+18h] BYREF

  va_start(va, a2);
  v15 = a2;
  *(_QWORD *)NumberOfBytesWritten = 0;
  p_cnt = &a1->_cnt;
  v4 = 0;
  while ( 1 )
  {
    flag = (unsigned int)a1[1365]._flag;
    v6 = (unsigned int)(0x10000 - flag);
    if ( (_DWORD)flag == 0x10000 )
      goto LABEL_11;
    v7 = (char *)p_cnt + flag;
    if ( v6 > 0x7FFFFFFF )
    {
      *v7 = 0;
      goto LABEL_11;
    }
    v8 = v6 - 1;
    v9 = _vsnprintf((char *const)p_cnt + flag, v8, a2, va);
    if ( v9 < 0 || (v10 = v9, v9 > v8) )
    {
      v7[v8] = 0;
      v11 = -2147024774;
    }
    else
    {
      v11 = 0;
      if ( v10 == v8 )
        v7[v8] = 0;
    }
    if ( v11 >= 0 )
      break;
LABEL_11:
    if ( v4 )
      return 0;
    WriteFile(a1->_ptr, p_cnt, a1[1365]._flag, NumberOfBytesWritten, 0);
    v4 = 1;
    a1[1365]._file += NumberOfBytesWritten[0];
    a2 = v15;
    a1[1365]._flag = 0;
  }
  v12 = (unsigned int)a1[1365]._flag;
  result = -1;
  do
    ++result;
  while ( *((_BYTE *)&a1->_cnt + v12 + result) );
  a1[1365]._flag = result + v12;
  return result;
}

```

## disassembly

```asm
0x14001601c  mov     rax, rsp
0x14001601f  mov     [rax+10h], rdx
0x140016023  mov     [rax+18h], r8
0x140016027  mov     [rax+20h], r9
0x14001602b  push    rbx
0x14001602c  push    rbp
0x14001602d  push    rsi
0x14001602e  push    rdi
0x14001602f  push    r12
0x140016031  push    r14
0x140016033  sub     rsp, 48h
0x140016037  mov     qword ptr [rax-48h], 0
0x14001603f  lea     r12, [rax+18h]
0x140016043  mov     dword ptr [rax-48h], 0
0x14001604a  lea     r14, [rcx+8]
0x14001604e  mov     rbx, rcx
0x140016051  xor     bpl, bpl
0x140016054  mov     ecx, [rbx+10008h]
0x14001605a  mov     edi, 10000h
0x14001605f  sub     edi, ecx
0x140016061  jz      short loc_1400160AF
0x140016063  lea     rsi, [r14+rcx]
0x140016067  cmp     rdi, 7FFFFFFFh
0x14001606e  jbe     short loc_140016075
0x140016070  mov     byte ptr [rsi], 0
0x140016073  jmp     short loc_1400160AF
0x140016075  mov     r8, rdx; Format
0x140016078  dec     rdi
0x14001607b  mov     rdx, rdi; BufferCount
0x14001607e  mov     r9, r12; ArgList
0x140016081  mov     rcx, rsi; Buffer
0x140016084  call    cs:__imp__vsnprintf
0x14001608a  test    eax, eax
0x14001608c  js      short loc_1400160A2
0x14001608e  movsxd  rcx, eax
0x140016091  cmp     rcx, rdi
0x140016094  ja      short loc_1400160A2
0x140016096  xor     eax, eax
0x140016098  cmp     rcx, rdi
0x14001609b  jnz     short loc_1400160AB
0x14001609d  mov     [rdi+rsi], al
0x1400160a0  jmp     short loc_1400160AB
0x1400160a2  mov     byte ptr [rdi+rsi], 0
0x1400160a6  mov     eax, 8007007Ah
0x1400160ab  test    eax, eax
0x1400160ad  jns     short loc_1400160F9
0x1400160af  test    bpl, bpl
0x1400160b2  jnz     short loc_14001611B
0x1400160b4  mov     r8d, [rbx+10008h]; nNumberOfBytesToWrite
0x1400160bb  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400160c0  mov     rcx, [rbx]; hFile
0x1400160c3  mov     rdx, r14; lpBuffer
0x1400160c6  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1400160cf  call    cs:__imp_WriteFile
0x1400160d5  mov     eax, [rsp+78h+NumberOfBytesWritten]
0x1400160d9  mov     bpl, 1
0x1400160dc  add     [rbx+1000Ch], eax
0x1400160e2  mov     rdx, [rsp+78h+arg_8]
0x1400160ea  mov     dword ptr [rbx+10008h], 0
0x1400160f4  jmp     loc_140016054
0x1400160f9  mov     ecx, [rbx+10008h]
0x1400160ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016103  lea     rdx, [rcx+rbx]
0x140016107  inc     rax
0x14001610a  cmp     byte ptr [rdx+rax+8], 0
0x14001610f  jnz     short loc_140016107
0x140016111  add     ecx, eax
0x140016113  mov     [rbx+10008h], ecx
0x140016119  jmp     short loc_14001611D
0x14001611b  xor     eax, eax
0x14001611d  add     rsp, 48h
0x140016121  pop     r14
0x140016123  pop     r12
0x140016125  pop     rdi
0x140016126  pop     rsi
0x140016127  pop     rbp
0x140016128  pop     rbx
0x140016129  retn
```
