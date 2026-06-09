# write_text_utf8_nolock

- ea: `0x1004215dc`
- end: `0x10042174c`
- name: `write_text_utf8_nolock`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x100421878`

## callees

- `0x100416590`
- `0x10041dcb4`
- `0x1004215dc`
- `0x100423b30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100421715`
- `KERNEL32!GetLastError` at `0x100421715`
- `KERNEL32!WriteFile` at `0x1004216f3`
- `KERNEL32!WriteFile` at `0x1004216f3`

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
0x1004215dc  mov     [rsp+arg_0], rbx
0x1004215e1  mov     [rsp+arg_10], rbp
0x1004215e6  push    rsi
0x1004215e7  push    rdi
0x1004215e8  push    r12
0x1004215ea  push    r14
0x1004215ec  push    r15
0x1004215ee  mov     eax, 1470h
0x1004215f3  call    _alloca_probe
0x1004215f8  sub     rsp, rax
0x1004215fb  mov     rax, cs:__security_cookie
0x100421602  xor     rax, rsp
0x100421605  mov     [rsp+1498h+var_38], rax
0x10042160d  movsxd  r10, edx
0x100421610  mov     rbx, rcx
0x100421613  mov     rax, r10
0x100421616  mov     r14d, r9d
0x100421619  sar     rax, 6
0x10042161d  lea     rcx, __pioinfo
0x100421624  and     r10d, 3Fh
0x100421628  add     r14, r8
0x10042162b  mov     r15, r8
0x10042162e  mov     rdi, r8
0x100421631  mov     rax, [rcx+rax*8]
0x100421635  lea     rdx, [r10+r10*8]
0x100421639  mov     r12, [rax+rdx*8+28h]
0x10042163e  xor     eax, eax
0x100421640  mov     [rbx], rax
0x100421643  cmp     r8, r14
0x100421646  mov     [rbx+8], eax
0x100421649  jnb     loc_10042171D
0x10042164f  lea     rax, [rsp+1498h+var_1448]
0x100421654  cmp     rdi, r14
0x100421657  jnb     short loc_100421686
0x100421659  movzx   ecx, word ptr [rdi]
0x10042165c  add     rdi, 2
0x100421660  cmp     cx, 0Ah
0x100421664  jnz     short loc_100421672
0x100421666  mov     edx, 0Dh
0x10042166b  mov     [rax], dx
0x10042166e  add     rax, 2
0x100421672  mov     [rax], cx
0x100421675  add     rax, 2
0x100421679  lea     rcx, [rsp+1498h+var_DA0]
0x100421681  cmp     rax, rcx
0x100421684  jb      short loc_100421654
0x100421686  and     [rsp+1498h+var_1460], 0
0x10042168c  lea     rcx, [rsp+1498h+var_1448]
0x100421691  and     [rsp+1498h+var_1468], 0
0x100421697  lea     r8, [rsp+1498h+var_1448]
0x10042169c  sub     rax, rcx
0x10042169f  mov     [rsp+1498h+var_1470], 0D55h
0x1004216a7  lea     rcx, [rsp+1498h+Overlapped]
0x1004216af  sar     rax, 1
0x1004216b2  mov     [rsp+1498h+lpOverlapped], rcx; lpOverlapped
0x1004216b7  mov     r9d, eax
0x1004216ba  mov     ecx, 0FDE9h
0x1004216bf  xor     edx, edx
0x1004216c1  call    __acrt_WideCharToMultiByte
0x1004216c6  mov     ebp, eax
0x1004216c8  test    eax, eax
0x1004216ca  jz      short loc_100421715
0x1004216cc  xor     esi, esi
0x1004216ce  test    eax, eax
0x1004216d0  jz      short loc_100421705
0x1004216d2  and     [rsp+1498h+lpOverlapped], 0
0x1004216d8  lea     rdx, [rsp+1498h+Overlapped]
0x1004216e0  mov     ecx, esi
0x1004216e2  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1004216e7  mov     r8d, ebp
0x1004216ea  add     rdx, rcx; lpBuffer
0x1004216ed  mov     rcx, r12; hFile
0x1004216f0  sub     r8d, esi; nNumberOfBytesToWrite
0x1004216f3  call    cs:__imp_WriteFile
0x1004216f9  test    eax, eax
0x1004216fb  jz      short loc_100421715
0x1004216fd  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x100421701  cmp     esi, ebp
0x100421703  jb      short loc_1004216D2
0x100421705  mov     eax, edi
0x100421707  sub     eax, r15d
0x10042170a  mov     [rbx+4], eax
0x10042170d  cmp     rdi, r14
0x100421710  jmp     loc_100421649
0x100421715  call    cs:__imp_GetLastError
0x10042171b  mov     [rbx], eax
0x10042171d  mov     rax, rbx
0x100421720  mov     rcx, [rsp+1498h+var_38]
0x100421728  xor     rcx, rsp; StackCookie
0x10042172b  call    __security_check_cookie
0x100421730  lea     r11, [rsp+1498h+var_28]
0x100421738  mov     rbx, [r11+30h]
0x10042173c  mov     rbp, [r11+40h]
0x100421740  mov     rsp, r11
0x100421743  pop     r15
0x100421745  pop     r14
0x100421747  pop     r12
0x100421749  pop     rdi
0x10042174a  pop     rsi
0x10042174b  retn
```
