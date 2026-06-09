# TracerptFPuts(char const *,_iobuf *)

- ea: `0x1400161b0`
- end: `0x1400162ab`
- name: `?TracerptFPuts@@YAKPEBDPEAU_iobuf@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(const char *Src, struct _iobuf *)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000faa4`
- `0x14000fd88`
- `0x14000ffcc`
- `0x1400104f0`
- `0x140010594`
- `0x140010a88`
- `0x140013304`

## callees

- `0x1400161b0`
- `0x1400400be`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140016200`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140016231`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140016265`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140016200`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140016231`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140016265`

## pseudocode

```c
__int64 __fastcall TracerptFPuts(const char *Src, struct _iobuf *a2)
{
  __int64 v4; // rdi
  __int64 flag; // rcx
  char *ptr; // rcx
  __int64 result; // rax
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp+10h] BYREF

  v4 = -1;
  do
    ++v4;
  while ( Src[v4] );
  flag = (unsigned int)a2[1365]._flag;
  NumberOfBytesWritten = 0;
  if ( (unsigned int)v4 <= 0x10000 )
  {
    if ( (unsigned int)(flag + v4) > 0xFFFF )
    {
      WriteFile(a2->_ptr, &a2->_cnt, flag, &NumberOfBytesWritten, 0);
      a2[1365]._file += NumberOfBytesWritten;
      flag = 0;
      a2[1365]._flag = 0;
    }
    memcpy_0((char *)&a2->_cnt + flag, Src, (unsigned int)v4);
    a2[1365]._flag += v4;
    return (unsigned int)v4;
  }
  else
  {
    WriteFile(a2->_ptr, &a2->_cnt, flag, &NumberOfBytesWritten, 0);
    ptr = a2->_ptr;
    a2[1365]._file += NumberOfBytesWritten;
    a2[1365]._flag = 0;
    WriteFile(ptr, Src, v4, &NumberOfBytesWritten, 0);
    result = NumberOfBytesWritten;
    a2[1365]._file += NumberOfBytesWritten;
  }
  return result;
}

```

## disassembly

```asm
0x1400161b0  mov     [rsp+arg_0], rbx
0x1400161b5  mov     [rsp+arg_10], rsi
0x1400161ba  push    rdi
0x1400161bb  sub     rsp, 30h
0x1400161bf  mov     rbx, rdx
0x1400161c2  mov     rsi, rcx
0x1400161c5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400161c9  inc     rdi
0x1400161cc  cmp     byte ptr [rcx+rdi], 0
0x1400161d0  jnz     short loc_1400161C9
0x1400161d2  mov     ecx, [rdx+10008h]
0x1400161d8  mov     [rsp+38h+NumberOfBytesWritten], 0
0x1400161e0  cmp     edi, 10000h
0x1400161e6  jbe     short loc_140016243
0x1400161e8  mov     r8d, ecx; nNumberOfBytesToWrite
0x1400161eb  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1400161f4  mov     rcx, [rbx]; hFile
0x1400161f7  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400161fc  add     rdx, 8; lpBuffer
0x140016200  call    cs:__imp_WriteFile
0x140016206  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x14001620a  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001620f  mov     rcx, [rbx]; hFile
0x140016212  mov     r8d, edi; nNumberOfBytesToWrite
0x140016215  add     [rbx+1000Ch], eax
0x14001621b  mov     rdx, rsi; lpBuffer
0x14001621e  mov     dword ptr [rbx+10008h], 0
0x140016228  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x140016231  call    cs:__imp_WriteFile
0x140016237  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x14001623b  add     [rbx+1000Ch], eax
0x140016241  jmp     short loc_14001629B
0x140016243  lea     eax, [rcx+rdi]
0x140016246  cmp     eax, 0FFFFh
0x14001624b  jbe     short loc_140016281
0x14001624d  mov     r8d, ecx; nNumberOfBytesToWrite
0x140016250  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x140016259  mov     rcx, [rbx]; hFile
0x14001625c  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140016261  add     rdx, 8; lpBuffer
0x140016265  call    cs:__imp_WriteFile
0x14001626b  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x14001626f  add     [rbx+1000Ch], eax
0x140016275  xor     ecx, ecx
0x140016277  mov     dword ptr [rbx+10008h], 0
0x140016281  add     rcx, 8
0x140016285  mov     r8d, edi; Size
0x140016288  add     rcx, rbx; void *
0x14001628b  mov     rdx, rsi; Src
0x14001628e  call    memcpy_0
0x140016293  add     [rbx+10008h], edi
0x140016299  mov     eax, edi
0x14001629b  mov     rbx, [rsp+38h+arg_0]
0x1400162a0  mov     rsi, [rsp+38h+arg_10]
0x1400162a5  add     rsp, 30h
0x1400162a9  pop     rdi
0x1400162aa  retn
```
