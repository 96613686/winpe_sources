# TracerptFPutwc(ushort,_iobuf *)

- ea: `0x1400162b4`
- end: `0x14001635a`
- name: `?TracerptFPutwc@@YAKGPEAU_iobuf@@@Z`
- size: `166`
- prototype: `unsigned int __fastcall(unsigned __int16, struct _iobuf *)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140011ff8`
- `0x1400131c8`
- `0x140013a04`
- `0x140016ae0`
- `0x1400192b4`

## callees

- `0x1400162b4`
- `0x1400400be`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140016319`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140016319`

## pseudocode

```c
__int64 __fastcall TracerptFPutwc(__int16 a1, struct _iobuf *a2)
{
  bool v2; // zf
  unsigned int v4; // edi
  __int16 *v5; // rsi
  __int64 flag; // rcx
  __int16 v8; // [rsp+50h] [rbp+8h] BYREF
  char v9; // [rsp+58h] [rbp+10h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+18h] BYREF

  v8 = a1;
  v2 = LOBYTE(a2[1365]._charbuf) == 0;
  NumberOfBytesWritten = 0;
  v9 = 0;
  if ( v2 )
  {
    v4 = 1;
    v9 = a1;
    v5 = (__int16 *)&v9;
  }
  else
  {
    v4 = 2;
    v5 = &v8;
  }
  flag = (unsigned int)a2[1365]._flag;
  if ( (unsigned int)flag + v4 > 0xFFFF )
  {
    WriteFile(a2->_ptr, &a2->_cnt, flag, &NumberOfBytesWritten, 0);
    a2[1365]._file += NumberOfBytesWritten;
    flag = 0;
    a2[1365]._flag = 0;
  }
  memcpy_0((char *)&a2->_cnt + flag, v5, v4);
  a2[1365]._flag += v4;
  return 1;
}

```

## disassembly

```asm
0x1400162b4  mov     rax, rsp
0x1400162b7  mov     [rax+8], cx
0x1400162bb  push    rbx
0x1400162bc  push    rsi
0x1400162bd  push    rdi
0x1400162be  sub     rsp, 30h
0x1400162c2  cmp     byte ptr [rdx+10010h], 0
0x1400162c9  mov     rbx, rdx
0x1400162cc  mov     dword ptr [rax+18h], 0
0x1400162d3  mov     byte ptr [rax+10h], 0
0x1400162d7  jnz     short loc_1400162E7
0x1400162d9  mov     edi, 1
0x1400162de  mov     [rax+10h], cl
0x1400162e1  lea     rsi, [rax+10h]
0x1400162e5  jmp     short loc_1400162F1
0x1400162e7  mov     edi, 2
0x1400162ec  lea     rsi, [rsp+48h+arg_0]
0x1400162f1  mov     ecx, [rdx+10008h]
0x1400162f7  lea     eax, [rcx+rdi]
0x1400162fa  cmp     eax, 0FFFFh
0x1400162ff  jbe     short loc_140016335
0x140016301  mov     r8d, ecx; nNumberOfBytesToWrite
0x140016304  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x14001630d  mov     rcx, [rbx]; hFile
0x140016310  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140016315  add     rdx, 8; lpBuffer
0x140016319  call    cs:__imp_WriteFile
0x14001631f  mov     eax, [rsp+48h+NumberOfBytesWritten]
0x140016323  add     [rbx+1000Ch], eax
0x140016329  xor     ecx, ecx
0x14001632b  mov     dword ptr [rbx+10008h], 0
0x140016335  add     rcx, 8
0x140016339  mov     r8d, edi; Size
0x14001633c  add     rcx, rbx; void *
0x14001633f  mov     rdx, rsi; Src
0x140016342  call    memcpy_0
0x140016347  add     [rbx+10008h], edi
0x14001634d  mov     eax, 1
0x140016352  add     rsp, 30h
0x140016356  pop     rdi
0x140016357  pop     rsi
0x140016358  pop     rbx
0x140016359  retn
```
