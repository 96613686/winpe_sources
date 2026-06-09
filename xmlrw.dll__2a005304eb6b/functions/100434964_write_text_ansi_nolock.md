# write_text_ansi_nolock

- ea: `0x100434964`
- end: `0x100434a66`
- name: `write_text_ansi_nolock`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100434e28`

## callees

- `0x100426580`
- `0x100434964`
- `0x100439280`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100434a33`
- `KERNEL32!GetLastError` at `0x100434a33`
- `KERNEL32!WriteFile` at `0x100434a17`
- `KERNEL32!WriteFile` at `0x100434a17`

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
0x100434964  mov     [rsp+arg_0], rbx
0x100434969  mov     [rsp+arg_10], rbp
0x10043496e  push    rsi
0x10043496f  push    rdi
0x100434970  push    r14
0x100434972  mov     eax, 1450h
0x100434977  call    _alloca_probe
0x10043497c  sub     rsp, rax
0x10043497f  mov     rax, cs:__security_cookie
0x100434986  xor     rax, rsp
0x100434989  mov     [rsp+1468h+var_28], rax
0x100434991  movsxd  r10, edx
0x100434994  mov     rdi, rcx
0x100434997  mov     rax, r10
0x10043499a  mov     ebp, r9d
0x10043499d  sar     rax, 6
0x1004349a1  lea     rcx, __pioinfo
0x1004349a8  and     r10d, 3Fh
0x1004349ac  add     rbp, r8
0x1004349af  mov     rsi, r8
0x1004349b2  mov     rax, [rcx+rax*8]
0x1004349b6  lea     rdx, [r10+r10*8]
0x1004349ba  mov     r14, [rax+rdx*8+28h]
0x1004349bf  xor     eax, eax
0x1004349c1  mov     [rdi], rax
0x1004349c4  mov     [rdi+8], eax
0x1004349c7  cmp     r8, rbp
0x1004349ca  jnb     short loc_100434A3B
0x1004349cc  lea     rbx, [rsp+1468h+Buffer]
0x1004349d1  cmp     rsi, rbp
0x1004349d4  jnb     short loc_1004349FA
0x1004349d6  mov     al, [rsi]
0x1004349d8  inc     rsi
0x1004349db  cmp     al, 0Ah
0x1004349dd  jnz     short loc_1004349E8
0x1004349df  inc     dword ptr [rdi+8]
0x1004349e2  mov     byte ptr [rbx], 0Dh
0x1004349e5  inc     rbx
0x1004349e8  mov     [rbx], al
0x1004349ea  inc     rbx
0x1004349ed  lea     rax, [rsp+1468h+var_29]
0x1004349f5  cmp     rbx, rax
0x1004349f8  jb      short loc_1004349D1
0x1004349fa  and     [rsp+1468h+var_1448], 0
0x100434a00  lea     rax, [rsp+1468h+Buffer]
0x100434a05  sub     ebx, eax
0x100434a07  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100434a0c  mov     r8d, ebx; nNumberOfBytesToWrite
0x100434a0f  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x100434a14  mov     rcx, r14; hFile
0x100434a17  call    cs:__imp_WriteFile
0x100434a1d  test    eax, eax
0x100434a1f  jz      short loc_100434A33
0x100434a21  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x100434a25  add     [rdi+4], eax
0x100434a28  cmp     eax, ebx
0x100434a2a  jb      short loc_100434A3B
0x100434a2c  cmp     rsi, rbp
0x100434a2f  jb      short loc_1004349CC
0x100434a31  jmp     short loc_100434A3B
0x100434a33  call    cs:__imp_GetLastError
0x100434a39  mov     [rdi], eax
0x100434a3b  mov     rax, rdi
0x100434a3e  mov     rcx, [rsp+1468h+var_28]
0x100434a46  xor     rcx, rsp; StackCookie
0x100434a49  call    __security_check_cookie
0x100434a4e  lea     r11, [rsp+1468h+var_18]
0x100434a56  mov     rbx, [r11+20h]
0x100434a5a  mov     rbp, [r11+30h]
0x100434a5e  mov     rsp, r11
0x100434a61  pop     r14
0x100434a63  pop     rdi
0x100434a64  pop     rsi
0x100434a65  retn
```
