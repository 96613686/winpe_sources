# MYmktemp

- ea: `0x1800cf368`
- end: `0x1800cf48f`
- name: `MYmktemp`
- size: `295`
- prototype: `__int64 __fastcall(char *FileName)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18009fc00`
- `0x1800a98e4`

## callees

- `0x1800cf368`

## import_xrefs

- `msvcrt!_errno` at `0x1800cf3fe`
- `msvcrt!_errno` at `0x1800cf40c`
- `msvcrt!_errno` at `0x1800cf433`
- `msvcrt!_errno` at `0x1800cf444`
- `msvcrt!_errno` at `0x1800cf462`
- `msvcrt!_errno` at `0x1800cf475`
- `msvcrt!_errno` at `0x1800cf3fe`
- `msvcrt!_errno` at `0x1800cf40c`
- `msvcrt!_errno` at `0x1800cf433`
- `msvcrt!_errno` at `0x1800cf444`
- `msvcrt!_errno` at `0x1800cf462`
- `msvcrt!_errno` at `0x1800cf475`
- `msvcrt!_ismbstrail` at `0x1800cf39c`
- `msvcrt!_ismbstrail` at `0x1800cf39c`
- `msvcrt!_access` at `0x1800cf423`
- `msvcrt!_access` at `0x1800cf423`
- `KERNEL32!GetCurrentThreadId` at `0x1800cf379`
- `KERNEL32!GetCurrentThreadId` at `0x1800cf379`

## pseudocode

```c
char *__fastcall MYmktemp(char *FileName)
{
  unsigned __int8 *v2; // rbx
  int v3; // esi
  DWORD i; // ebp
  int v5; // esi
  int v6; // ebp

  v2 = (unsigned __int8 *)FileName;
  v3 = 0;
  for ( i = GetCurrentThreadId(); *v2; ++v2 )
    ;
  while ( --v2 >= (unsigned __int8 *)FileName && !_ismbstrail((const unsigned __int8 *)FileName, v2) )
  {
    if ( *v2 != 88 )
      return 0;
    if ( v3 >= 5 )
      break;
    ++v3;
    *v2 = i % 0xA + 48;
    i /= 0xAu;
  }
  if ( *v2 == 88 && v3 >= 5 )
  {
    *v2 = 97;
    v5 = 98;
    v6 = *_errno();
    *_errno() = 0;
    while ( 1 )
    {
      if ( _access(FileName, 0) && *_errno() != 13 )
      {
        *_errno() = v6;
        return FileName;
      }
      *_errno() = 0;
      if ( v5 == 123 )
        break;
      *v2 = v5++;
    }
    *_errno() = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x1800cf368  push    rbx
0x1800cf36a  push    rbp
0x1800cf36b  push    rsi
0x1800cf36c  push    rdi
0x1800cf36d  sub     rsp, 28h
0x1800cf371  mov     rdi, rcx
0x1800cf374  mov     rbx, rcx
0x1800cf377  xor     esi, esi
0x1800cf379  call    cs:__imp_GetCurrentThreadId
0x1800cf380  nop     dword ptr [rax+rax+00h]
0x1800cf385  mov     ebp, eax
0x1800cf387  cmp     [rbx], sil
0x1800cf38a  jz      short loc_1800CF3DC
0x1800cf38c  inc     rbx
0x1800cf38f  cmp     [rbx], sil
0x1800cf392  jnz     short loc_1800CF38C
0x1800cf394  jmp     short loc_1800CF3DC
0x1800cf396  mov     rdx, rbx; Pos
0x1800cf399  mov     rcx, rdi; String
0x1800cf39c  call    cs:__imp__ismbstrail
0x1800cf3a3  nop     dword ptr [rax+rax+00h]
0x1800cf3a8  test    eax, eax
0x1800cf3aa  jnz     short loc_1800CF3E4
0x1800cf3ac  cmp     byte ptr [rbx], 58h ; 'X'
0x1800cf3af  jnz     loc_1800CF483
0x1800cf3b5  cmp     esi, 5
0x1800cf3b8  jge     short loc_1800CF3E4
0x1800cf3ba  mov     eax, 0CCCCCCCDh
0x1800cf3bf  inc     esi
0x1800cf3c1  mul     ebp
0x1800cf3c3  shr     edx, 3
0x1800cf3c6  mov     al, dl
0x1800cf3c8  shl     al, 2
0x1800cf3cb  lea     ecx, [rax+rdx]
0x1800cf3ce  add     cl, cl
0x1800cf3d0  sub     bpl, cl
0x1800cf3d3  add     bpl, 30h ; '0'
0x1800cf3d7  mov     [rbx], bpl
0x1800cf3da  mov     ebp, edx
0x1800cf3dc  dec     rbx
0x1800cf3df  cmp     rbx, rdi
0x1800cf3e2  jnb     short loc_1800CF396
0x1800cf3e4  cmp     byte ptr [rbx], 58h ; 'X'
0x1800cf3e7  jnz     loc_1800CF483
0x1800cf3ed  cmp     esi, 5
0x1800cf3f0  jl      loc_1800CF483
0x1800cf3f6  mov     byte ptr [rbx], 61h ; 'a'
0x1800cf3f9  mov     esi, 62h ; 'b'
0x1800cf3fe  call    cs:__imp__errno
0x1800cf405  nop     dword ptr [rax+rax+00h]
0x1800cf40a  mov     ebp, [rax]
0x1800cf40c  call    cs:__imp__errno
0x1800cf413  nop     dword ptr [rax+rax+00h]
0x1800cf418  mov     dword ptr [rax], 0
0x1800cf41e  xor     edx, edx; AccessMode
0x1800cf420  mov     rcx, rdi; FileName
0x1800cf423  call    cs:__imp__access
0x1800cf42a  nop     dword ptr [rax+rax+00h]
0x1800cf42f  test    eax, eax
0x1800cf431  jz      short loc_1800CF444
0x1800cf433  call    cs:__imp__errno
0x1800cf43a  nop     dword ptr [rax+rax+00h]
0x1800cf43f  cmp     dword ptr [rax], 0Dh
0x1800cf442  jnz     short loc_1800CF462
0x1800cf444  call    cs:__imp__errno
0x1800cf44b  nop     dword ptr [rax+rax+00h]
0x1800cf450  mov     dword ptr [rax], 0
0x1800cf456  cmp     esi, 7Bh ; '{'
0x1800cf459  jz      short loc_1800CF475
0x1800cf45b  mov     [rbx], sil
0x1800cf45e  inc     esi
0x1800cf460  jmp     short loc_1800CF41E
0x1800cf462  call    cs:__imp__errno
0x1800cf469  nop     dword ptr [rax+rax+00h]
0x1800cf46e  mov     [rax], ebp
0x1800cf470  mov     rax, rdi
0x1800cf473  jmp     short loc_1800CF485
0x1800cf475  call    cs:__imp__errno
0x1800cf47c  nop     dword ptr [rax+rax+00h]
0x1800cf481  mov     [rax], ebp
0x1800cf483  xor     eax, eax
0x1800cf485  add     rsp, 28h
0x1800cf489  pop     rdi
0x1800cf48a  pop     rsi
0x1800cf48b  pop     rbp
0x1800cf48c  pop     rbx
0x1800cf48d  retn
```
