# write_text_ansi_nolock

- ea: `0x1004213b4`
- end: `0x1004214b6`
- name: `write_text_ansi_nolock`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100421878`

## callees

- `0x100416590`
- `0x1004213b4`
- `0x100423b30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100421483`
- `KERNEL32!GetLastError` at `0x100421483`
- `KERNEL32!WriteFile` at `0x100421467`
- `KERNEL32!WriteFile` at `0x100421467`

## pseudocode

```c
__int64 __fastcall write_text_ansi_nolock(__int64 a1, int a2, char *a3, int a4)
{
  unsigned __int64 v5; // rbp
  char *v6; // rsi
  void *v7; // r14
  char *v8; // rbx
  char v9; // al
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5119]; // [rsp+40h] [rbp-1428h] BYREF
  char v15; // [rsp+143Fh] [rbp-29h] BYREF

  v5 = (unsigned __int64)&a3[a4];
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
          ++*(_DWORD *)(a1 + 8);
          *v8++ = 13;
        }
        *v8++ = v9;
      }
      while ( v8 < &v15 );
      v10 = (_DWORD)v8 - (unsigned int)Buffer;
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
0x1004213b4  mov     [rsp+arg_0], rbx
0x1004213b9  mov     [rsp+arg_10], rbp
0x1004213be  push    rsi
0x1004213bf  push    rdi
0x1004213c0  push    r14
0x1004213c2  mov     eax, 1450h
0x1004213c7  call    _alloca_probe
0x1004213cc  sub     rsp, rax
0x1004213cf  mov     rax, cs:__security_cookie
0x1004213d6  xor     rax, rsp
0x1004213d9  mov     [rsp+1468h+var_28], rax
0x1004213e1  movsxd  r10, edx
0x1004213e4  mov     rdi, rcx
0x1004213e7  mov     rax, r10
0x1004213ea  mov     ebp, r9d
0x1004213ed  sar     rax, 6
0x1004213f1  lea     rcx, __pioinfo
0x1004213f8  and     r10d, 3Fh
0x1004213fc  add     rbp, r8
0x1004213ff  mov     rsi, r8
0x100421402  mov     rax, [rcx+rax*8]
0x100421406  lea     rdx, [r10+r10*8]
0x10042140a  mov     r14, [rax+rdx*8+28h]
0x10042140f  xor     eax, eax
0x100421411  mov     [rdi], rax
0x100421414  mov     [rdi+8], eax
0x100421417  cmp     r8, rbp
0x10042141a  jnb     short loc_10042148B
0x10042141c  lea     rbx, [rsp+1468h+Buffer]
0x100421421  cmp     rsi, rbp
0x100421424  jnb     short loc_10042144A
0x100421426  mov     al, [rsi]
0x100421428  inc     rsi
0x10042142b  cmp     al, 0Ah
0x10042142d  jnz     short loc_100421438
0x10042142f  inc     dword ptr [rdi+8]
0x100421432  mov     byte ptr [rbx], 0Dh
0x100421435  inc     rbx
0x100421438  mov     [rbx], al
0x10042143a  inc     rbx
0x10042143d  lea     rax, [rsp+1468h+var_29]
0x100421445  cmp     rbx, rax
0x100421448  jb      short loc_100421421
0x10042144a  and     [rsp+1468h+var_1448], 0
0x100421450  lea     rax, [rsp+1468h+Buffer]
0x100421455  sub     ebx, eax
0x100421457  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x10042145c  mov     r8d, ebx; nNumberOfBytesToWrite
0x10042145f  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x100421464  mov     rcx, r14; hFile
0x100421467  call    cs:__imp_WriteFile
0x10042146d  test    eax, eax
0x10042146f  jz      short loc_100421483
0x100421471  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x100421475  add     [rdi+4], eax
0x100421478  cmp     eax, ebx
0x10042147a  jb      short loc_10042148B
0x10042147c  cmp     rsi, rbp
0x10042147f  jb      short loc_10042141C
0x100421481  jmp     short loc_10042148B
0x100421483  call    cs:__imp_GetLastError
0x100421489  mov     [rdi], eax
0x10042148b  mov     rax, rdi
0x10042148e  mov     rcx, [rsp+1468h+var_28]
0x100421496  xor     rcx, rsp; StackCookie
0x100421499  call    __security_check_cookie
0x10042149e  lea     r11, [rsp+1468h+var_18]
0x1004214a6  mov     rbx, [r11+20h]
0x1004214aa  mov     rbp, [r11+30h]
0x1004214ae  mov     rsp, r11
0x1004214b1  pop     r14
0x1004214b3  pop     rdi
0x1004214b4  pop     rsi
0x1004214b5  retn
```
