# FreeBufferToPool

- ea: `0x180002f80`
- end: `0x180003007`
- name: `FreeBufferToPool`
- size: `135`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012b0`
- `0x180001b40`
- `0x180001fe0`
- `0x180002320`
- `0x180002aac`
- `0x180003010`
- `0x180004950`
- `0x180004fb0`
- `0x1800071cc`
- `0x180009c3c`
- `0x18000a300`
- `0x18000afb0`
- `0x18000c768`
- `0x18000d730`

## callees

- `0x180002f80`
- `0x180007f48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002f98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002fe2`

## pseudocode

```c
void __fastcall FreeBufferToPool(__int64 a1, __int64 a2, char a3)
{
  _QWORD *v4; // rdi
  __int64 v6; // rax

  v4 = (_QWORD *)(a2 - 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  if ( (_QWORD *)*v4 == v4 )
  {
    v6 = *(_QWORD *)(a1 + 40);
    *v4 = v6;
    v4[1] = a1 + 40;
    *(_QWORD *)(v6 + 8) = v4;
    *(_QWORD *)(a1 + 40) = v4;
    ++*(_DWORD *)(v4[2] + 28LL);
    if ( a3 )
    {
      if ( ++*(_DWORD *)(a1 + 20) >= *(_DWORD *)(a1 + 16) )
      {
        FreeUnusedBufferPoolBlocks(a1);
        *(_DWORD *)(a1 + 20) = 0;
      }
    }
  }
  else
  {
    ++g_ulDoubleBufferFrees;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
}

```

## disassembly

```asm
0x180002f80  push    rbx
0x180002f82  push    rbp
0x180002f83  push    rsi
0x180002f84  push    rdi
0x180002f85  sub     rsp, 28h
0x180002f89  mov     rbx, rcx
0x180002f8c  lea     rdi, [rdx-18h]
0x180002f90  add     rcx, 40h ; '@'; lpCriticalSection
0x180002f94  movzx   ebp, r8b
0x180002f98  call    cs:__imp_EnterCriticalSection
0x180002f9f  nop     dword ptr [rax+rax+00h]
0x180002fa4  cmp     [rdi], rdi
0x180002fa7  jnz     short loc_180002FEE
0x180002fa9  mov     rax, [rbx+28h]
0x180002fad  lea     rcx, [rbx+28h]
0x180002fb1  mov     [rdi], rax
0x180002fb4  mov     [rdi+8], rcx
0x180002fb8  mov     [rax+8], rdi
0x180002fbc  mov     [rcx], rdi
0x180002fbf  mov     rax, [rdi+10h]
0x180002fc3  inc     dword ptr [rax+1Ch]
0x180002fc6  test    bpl, bpl
0x180002fc9  jz      short loc_180002FD6
0x180002fcb  inc     dword ptr [rbx+14h]
0x180002fce  mov     eax, [rbx+14h]
0x180002fd1  cmp     eax, [rbx+10h]
0x180002fd4  jnb     short loc_180002FF6
0x180002fd6  lea     rcx, [rbx+40h]
0x180002fda  add     rsp, 28h
0x180002fde  pop     rdi
0x180002fdf  pop     rsi
0x180002fe0  pop     rbp
0x180002fe1  pop     rbx
0x180002fe2  jmp     cs:__imp_LeaveCriticalSection
0x180002fee  inc     cs:g_ulDoubleBufferFrees
0x180002ff4  jmp     short loc_180002FD6
0x180002ff6  mov     rcx, rbx
0x180002ff9  call    FreeUnusedBufferPoolBlocks
0x180002ffe  mov     dword ptr [rbx+14h], 0
0x180003005  jmp     short loc_180002FD6
```
