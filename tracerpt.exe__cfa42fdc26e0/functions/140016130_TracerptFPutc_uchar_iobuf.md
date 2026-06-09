# TracerptFPutc(uchar,_iobuf *)

- ea: `0x140016130`
- end: `0x1400161aa`
- name: `?TracerptFPutc@@YAKEPEAU_iobuf@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(char, struct _iobuf *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140011a0c`
- `0x1400131c8`

## callees

- `0x140016130`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001616f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001616f`

## pseudocode

```c
__int64 __fastcall TracerptFPutc(char a1, struct _iobuf *a2)
{
  DWORD flag; // r8d
  __int64 result; // rax
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp+10h] BYREF

  flag = a2[1365]._flag;
  NumberOfBytesWritten = 0;
  if ( flag + 1 > 0xFFFF )
  {
    WriteFile(a2->_ptr, &a2->_cnt, flag, &NumberOfBytesWritten, 0);
    a2[1365]._file += NumberOfBytesWritten;
    flag = 0;
    a2[1365]._flag = 0;
  }
  *((_BYTE *)&a2->_cnt + flag) = a1;
  result = 1;
  ++a2[1365]._flag;
  return result;
}

```

## disassembly

```asm
0x140016130  mov     [rsp+arg_0], rbx
0x140016135  push    rdi
0x140016136  sub     rsp, 30h
0x14001613a  mov     r8d, [rdx+10008h]; nNumberOfBytesToWrite
0x140016141  mov     rbx, rdx
0x140016144  mov     dil, cl
0x140016147  mov     [rsp+38h+NumberOfBytesWritten], 0
0x14001614f  lea     eax, [r8+1]
0x140016153  cmp     eax, 0FFFFh
0x140016158  jbe     short loc_14001618C
0x14001615a  mov     rcx, [rbx]; hFile
0x14001615d  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140016162  add     rdx, 8; lpBuffer
0x140016166  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x14001616f  call    cs:__imp_WriteFile
0x140016175  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x140016179  add     [rbx+1000Ch], eax
0x14001617f  xor     r8d, r8d
0x140016182  mov     dword ptr [rbx+10008h], 0
0x14001618c  mov     eax, r8d
0x14001618f  mov     [rax+rbx+8], dil
0x140016194  mov     eax, 1
0x140016199  add     [rbx+10008h], eax
0x14001619f  mov     rbx, [rsp+38h+arg_0]
0x1400161a4  add     rsp, 30h
0x1400161a8  pop     rdi
0x1400161a9  retn
```
