# MYmktemp

- ea: `0x18001d554`
- end: `0x18001d658`
- name: `MYmktemp`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d3c4`

## callees

- `0x18001d554`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ismbstrail` at `0x18001d584`
- `api-ms-win-crt-private-l1-1-0!_o__ismbstrail` at `0x18001d584`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d5aa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d5b2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d5cd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d5de`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d636`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d641`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d5aa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d5b2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d5cd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d5de`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d636`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d641`
- `api-ms-win-crt-private-l1-1-0!_o__access` at `0x18001d5c3`
- `api-ms-win-crt-private-l1-1-0!_o__access` at `0x18001d5c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d565`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d565`

## pseudocode

```c
_BYTE *__fastcall MYmktemp(_BYTE *a1)
{
  _BYTE *v2; // rbx
  int v3; // esi
  DWORD i; // ebp
  _BYTE *v5; // rbx
  int v6; // esi
  int v7; // ebp

  v2 = a1;
  v3 = 0;
  for ( i = GetCurrentThreadId(); *v2; ++v2 )
    ;
  v5 = v2 - 1;
  if ( v5 < a1 )
    return 0;
  while ( !(unsigned int)_o__ismbstrail(a1, v5) )
  {
    if ( v3 < 5 && *v5 == 88 )
    {
      ++v3;
      *v5-- = i % 0xA + 48;
      i /= 0xAu;
      if ( v5 >= a1 )
        continue;
    }
    if ( v5 < a1 )
      return 0;
    break;
  }
  if ( v3 < 5 || *v5 != 88 )
    return 0;
  *v5 = 97;
  v6 = 98;
  v7 = *(_DWORD *)_o__errno();
  *(_DWORD *)_o__errno() = 0;
  while ( !(unsigned int)_o__access(a1, 0) || *(_DWORD *)_o__errno() == 13 )
  {
    *(_DWORD *)_o__errno() = 0;
    if ( v6 == 123 )
    {
      *(_DWORD *)_o__errno() = v7;
      return 0;
    }
    *v5 = v6++;
  }
  *(_DWORD *)_o__errno() = v7;
  return a1;
}

```

## disassembly

```asm
0x18001d554  push    rbx
0x18001d556  push    rbp
0x18001d557  push    rsi
0x18001d558  push    rdi
0x18001d559  sub     rsp, 28h
0x18001d55d  mov     rdi, rcx
0x18001d560  mov     rbx, rcx
0x18001d563  xor     esi, esi
0x18001d565  call    cs:__imp_GetCurrentThreadId
0x18001d56b  mov     ebp, eax
0x18001d56d  cmp     [rbx], sil
0x18001d570  jnz     loc_18001D629
0x18001d576  dec     rbx
0x18001d579  cmp     rbx, rdi
0x18001d57c  jb      short loc_18001D5E6
0x18001d57e  mov     rdx, rbx
0x18001d581  mov     rcx, rdi
0x18001d584  call    cs:__imp__o__ismbstrail
0x18001d58a  test    eax, eax
0x18001d58c  jnz     short loc_18001D598
0x18001d58e  cmp     esi, 5
0x18001d591  jl      short loc_18001D5F1
0x18001d593  cmp     rbx, rdi
0x18001d596  jb      short loc_18001D5E6
0x18001d598  cmp     esi, 5
0x18001d59b  jl      short loc_18001D5E6
0x18001d59d  cmp     byte ptr [rbx], 58h ; 'X'
0x18001d5a0  jnz     short loc_18001D5E6
0x18001d5a2  mov     byte ptr [rbx], 61h ; 'a'
0x18001d5a5  mov     esi, 62h ; 'b'
0x18001d5aa  call    cs:__imp__o__errno
0x18001d5b0  mov     ebp, [rax]
0x18001d5b2  call    cs:__imp__o__errno
0x18001d5b8  mov     dword ptr [rax], 0
0x18001d5be  xor     edx, edx
0x18001d5c0  mov     rcx, rdi
0x18001d5c3  call    cs:__imp__o__access
0x18001d5c9  test    eax, eax
0x18001d5cb  jnz     short loc_18001D636
0x18001d5cd  call    cs:__imp__o__errno
0x18001d5d3  mov     dword ptr [rax], 0
0x18001d5d9  cmp     esi, 7Bh ; '{'
0x18001d5dc  jnz     short loc_18001D64E
0x18001d5de  call    cs:__imp__o__errno
0x18001d5e4  mov     [rax], ebp
0x18001d5e6  xor     eax, eax
0x18001d5e8  add     rsp, 28h
0x18001d5ec  pop     rdi
0x18001d5ed  pop     rsi
0x18001d5ee  pop     rbp
0x18001d5ef  pop     rbx
0x18001d5f0  retn
0x18001d5f1  cmp     byte ptr [rbx], 58h ; 'X'
0x18001d5f4  jnz     short loc_18001D593
0x18001d5f6  mov     eax, 0CCCCCCCDh
0x18001d5fb  inc     esi
0x18001d5fd  mul     ebp
0x18001d5ff  shr     edx, 3
0x18001d602  mov     al, dl
0x18001d604  shl     al, 2
0x18001d607  lea     ecx, [rax+rdx]
0x18001d60a  add     cl, cl
0x18001d60c  sub     bpl, cl
0x18001d60f  add     bpl, 30h ; '0'
0x18001d613  mov     [rbx], bpl
0x18001d616  dec     rbx
0x18001d619  mov     ebp, edx
0x18001d61b  cmp     rbx, rdi
0x18001d61e  jnb     loc_18001D57E
0x18001d624  jmp     loc_18001D593
0x18001d629  inc     rbx
0x18001d62c  cmp     [rbx], sil
0x18001d62f  jnz     short loc_18001D629
0x18001d631  jmp     loc_18001D576
0x18001d636  call    cs:__imp__o__errno
0x18001d63c  cmp     dword ptr [rax], 0Dh
0x18001d63f  jz      short loc_18001D5CD
0x18001d641  call    cs:__imp__o__errno
0x18001d647  mov     [rax], ebp
0x18001d649  mov     rax, rdi
0x18001d64c  jmp     short loc_18001D5E8
0x18001d64e  mov     [rbx], sil
0x18001d651  inc     esi
0x18001d653  jmp     loc_18001D5BE
```
