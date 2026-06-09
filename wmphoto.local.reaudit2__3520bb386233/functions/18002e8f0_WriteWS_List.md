# WriteWS_List

- ea: `0x18002e8f0`
- end: `0x18002e9c1`
- name: `WriteWS_List`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002e8f0`
- `0x180043e40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18002e964`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18002e964`

## pseudocode

```c
__int64 __fastcall WriteWS_List(__int64 *a1, char *a2, unsigned __int64 a3)
{
  size_t v5; // r8
  unsigned int v7; // ecx
  size_t v8; // rsi
  __int64 v9; // r14
  _QWORD *v10; // rax

  v5 = a1[2];
  if ( v5 + a3 < v5 || a1[1] < v5 + a3 )
    return (unsigned int)-103;
  v7 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      v8 = a3;
      if ( 4096 - v5 <= a3 )
        v8 = 4096 - v5;
      memcpy_0((void *)(v5 + *a1), a2, v8);
      v5 = v8 + a1[2];
      a1[2] = v5;
      if ( v5 == 4096 )
      {
        v9 = *a1;
        v10 = calloc(1u, 0x1008u);
        if ( !v10 )
          return (unsigned int)-101;
        *(_QWORD *)(v9 - 8) = v10;
        a1[1] += 4096;
        v7 = 0;
        *a1 = (__int64)(v10 + 1);
        *v10 = 0;
        ++a1[3];
        v5 = 0;
        a1[2] = 0;
      }
      else
      {
        v7 = 0;
      }
      a3 -= v8;
      if ( !a3 )
        return v7;
      a2 += v8;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18002e8f0  push    rbx
0x18002e8f2  push    rbp
0x18002e8f3  push    rsi
0x18002e8f4  push    rdi
0x18002e8f5  push    r14
0x18002e8f7  push    r15
0x18002e8f9  sub     rsp, 28h
0x18002e8fd  mov     rdi, r8
0x18002e900  mov     rbp, rdx
0x18002e903  mov     r8, [rcx+10h]
0x18002e907  mov     rbx, rcx
0x18002e90a  lea     rax, [r8+rdi]
0x18002e90e  cmp     rax, r8
0x18002e911  jb      short loc_18002E98B
0x18002e913  cmp     [rcx+8], rax
0x18002e917  jb      short loc_18002E98B
0x18002e919  xor     ecx, ecx
0x18002e91b  test    rdi, rdi
0x18002e91e  jz      short loc_18002E97B
0x18002e920  mov     r15d, 1000h
0x18002e926  mov     rcx, [rbx]
0x18002e929  mov     rax, r15
0x18002e92c  sub     rax, r8
0x18002e92f  mov     rsi, rdi
0x18002e932  cmp     rax, rdi
0x18002e935  mov     rdx, rbp; Src
0x18002e938  cmovbe  rsi, rax
0x18002e93c  add     rcx, r8; void *
0x18002e93f  mov     r8, rsi; Size
0x18002e942  call    memcpy_0
0x18002e947  mov     r8, [rbx+10h]
0x18002e94b  add     r8, rsi
0x18002e94e  mov     [rbx+10h], r8
0x18002e952  cmp     r8, r15
0x18002e955  jnz     short loc_18002E992
0x18002e957  mov     r14, [rbx]
0x18002e95a  mov     edx, 1008h; Size
0x18002e95f  mov     ecx, 1; Count
0x18002e964  call    cs:__imp_calloc
0x18002e96b  nop     dword ptr [rax+rax+00h]
0x18002e970  mov     rdx, rax
0x18002e973  test    rax, rax
0x18002e976  jnz     short loc_18002E99E
0x18002e978  lea     ecx, [rax-65h]
0x18002e97b  mov     eax, ecx
0x18002e97d  add     rsp, 28h
0x18002e981  pop     r15
0x18002e983  pop     r14
0x18002e985  pop     rdi
0x18002e986  pop     rsi
0x18002e987  pop     rbp
0x18002e988  pop     rbx
0x18002e989  retn
0x18002e98b  mov     ecx, 0FFFFFF99h
0x18002e990  jmp     short loc_18002E97B
0x18002e992  xor     ecx, ecx
0x18002e994  sub     rdi, rsi
0x18002e997  jz      short loc_18002E97B
0x18002e999  add     rbp, rsi
0x18002e99c  jmp     short loc_18002E926
0x18002e99e  mov     [r14-8], rdx
0x18002e9a2  add     rax, 8
0x18002e9a6  add     [rbx+8], r15
0x18002e9aa  xor     ecx, ecx
0x18002e9ac  mov     [rbx], rax
0x18002e9af  xor     eax, eax
0x18002e9b1  mov     [rdx], rax
0x18002e9b4  inc     qword ptr [rbx+18h]
0x18002e9b8  xor     r8d, r8d
0x18002e9bb  mov     [rbx+10h], rax
0x18002e9bf  jmp     short loc_18002E994
```
