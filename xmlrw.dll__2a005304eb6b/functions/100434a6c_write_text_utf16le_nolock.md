# write_text_utf16le_nolock

- ea: `0x100434a6c`
- end: `0x100434b85`
- name: `write_text_utf16le_nolock`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100434e28`

## callees

- `0x100426580`
- `0x100434a6c`
- `0x100439280`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100434b52`
- `KERNEL32!GetLastError` at `0x100434b52`
- `KERNEL32!WriteFile` at `0x100434b36`
- `KERNEL32!WriteFile` at `0x100434b36`

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
0x100434a6c  mov     [rsp+arg_0], rbx
0x100434a71  mov     [rsp+arg_10], rbp
0x100434a76  push    rsi
0x100434a77  push    rdi
0x100434a78  push    r14
0x100434a7a  mov     eax, 1450h
0x100434a7f  call    _alloca_probe
0x100434a84  sub     rsp, rax
0x100434a87  mov     rax, cs:__security_cookie
0x100434a8e  xor     rax, rsp
0x100434a91  mov     [rsp+1468h+var_28], rax
0x100434a99  movsxd  r10, edx
0x100434a9c  mov     rdi, rcx
0x100434a9f  mov     rax, r10
0x100434aa2  mov     ebp, r9d
0x100434aa5  sar     rax, 6
0x100434aa9  lea     rcx, __pioinfo
0x100434ab0  and     r10d, 3Fh
0x100434ab4  add     rbp, r8
0x100434ab7  mov     rsi, r8
0x100434aba  mov     rax, [rcx+rax*8]
0x100434abe  lea     rdx, [r10+r10*8]
0x100434ac2  mov     r14, [rax+rdx*8+28h]
0x100434ac7  xor     eax, eax
0x100434ac9  mov     [rdi], rax
0x100434acc  mov     [rdi+8], eax
0x100434acf  cmp     r8, rbp
0x100434ad2  jnb     loc_100434B5A
0x100434ad8  lea     rbx, [rsp+1468h+Buffer]
0x100434add  cmp     rsi, rbp
0x100434ae0  jnb     short loc_100434B13
0x100434ae2  movzx   eax, word ptr [rsi]
0x100434ae5  add     rsi, 2
0x100434ae9  cmp     ax, 0Ah
0x100434aed  jnz     short loc_100434AFF
0x100434aef  add     dword ptr [rdi+8], 2
0x100434af3  mov     ecx, 0Dh
0x100434af8  mov     [rbx], cx
0x100434afb  add     rbx, 2
0x100434aff  mov     [rbx], ax
0x100434b02  add     rbx, 2
0x100434b06  lea     rax, [rsp+1468h+var_2A]
0x100434b0e  cmp     rbx, rax
0x100434b11  jb      short loc_100434ADD
0x100434b13  and     [rsp+1468h+var_1448], 0
0x100434b19  lea     rax, [rsp+1468h+Buffer]
0x100434b1e  sub     rbx, rax
0x100434b21  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100434b26  sar     rbx, 1
0x100434b29  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x100434b2e  add     ebx, ebx
0x100434b30  mov     rcx, r14; hFile
0x100434b33  mov     r8d, ebx; nNumberOfBytesToWrite
0x100434b36  call    cs:__imp_WriteFile
0x100434b3c  test    eax, eax
0x100434b3e  jz      short loc_100434B52
0x100434b40  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x100434b44  add     [rdi+4], eax
0x100434b47  cmp     eax, ebx
0x100434b49  jb      short loc_100434B5A
0x100434b4b  cmp     rsi, rbp
0x100434b4e  jb      short loc_100434AD8
0x100434b50  jmp     short loc_100434B5A
0x100434b52  call    cs:__imp_GetLastError
0x100434b58  mov     [rdi], eax
0x100434b5a  mov     rax, rdi
0x100434b5d  mov     rcx, [rsp+1468h+var_28]
0x100434b65  xor     rcx, rsp; StackCookie
0x100434b68  call    __security_check_cookie
0x100434b6d  lea     r11, [rsp+1468h+var_18]
0x100434b75  mov     rbx, [r11+20h]
0x100434b79  mov     rbp, [r11+30h]
0x100434b7d  mov     rsp, r11
0x100434b80  pop     r14
0x100434b82  pop     rdi
0x100434b83  pop     rsi
0x100434b84  retn
```
