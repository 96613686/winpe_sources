# MYmktemp

- ea: `0x1800c9614`
- end: `0x1800c96fc`
- name: `MYmktemp`
- size: `232`
- prototype: `__int64 __fastcall(char *FileName)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18009b494`
- `0x1800a47a8`

## callees

- `0x1800c9614`

## import_xrefs

- `msvcrt!_errno` at `0x1800c9696`
- `msvcrt!_errno` at `0x1800c969e`
- `msvcrt!_errno` at `0x1800c96b9`
- `msvcrt!_errno` at `0x1800c96c4`
- `msvcrt!_errno` at `0x1800c96dc`
- `msvcrt!_errno` at `0x1800c96e9`
- `msvcrt!_errno` at `0x1800c9696`
- `msvcrt!_errno` at `0x1800c969e`
- `msvcrt!_errno` at `0x1800c96b9`
- `msvcrt!_errno` at `0x1800c96c4`
- `msvcrt!_errno` at `0x1800c96dc`
- `msvcrt!_errno` at `0x1800c96e9`
- `msvcrt!_ismbstrail` at `0x1800c9642`
- `msvcrt!_ismbstrail` at `0x1800c9642`
- `msvcrt!_access` at `0x1800c96af`
- `msvcrt!_access` at `0x1800c96af`
- `KERNEL32!GetCurrentThreadId` at `0x1800c9625`
- `KERNEL32!GetCurrentThreadId` at `0x1800c9625`

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
0x1800c9614  push    rbx
0x1800c9616  push    rbp
0x1800c9617  push    rsi
0x1800c9618  push    rdi
0x1800c9619  sub     rsp, 28h
0x1800c961d  mov     rdi, rcx
0x1800c9620  mov     rbx, rcx
0x1800c9623  xor     esi, esi
0x1800c9625  call    cs:__imp_GetCurrentThreadId
0x1800c962b  mov     ebp, eax
0x1800c962d  cmp     [rbx], sil
0x1800c9630  jz      short loc_1800C967C
0x1800c9632  inc     rbx
0x1800c9635  cmp     [rbx], sil
0x1800c9638  jnz     short loc_1800C9632
0x1800c963a  jmp     short loc_1800C967C
0x1800c963c  mov     rdx, rbx; Pos
0x1800c963f  mov     rcx, rdi; String
0x1800c9642  call    cs:__imp__ismbstrail
0x1800c9648  test    eax, eax
0x1800c964a  jnz     short loc_1800C9684
0x1800c964c  cmp     byte ptr [rbx], 58h ; 'X'
0x1800c964f  jnz     loc_1800C96F1
0x1800c9655  cmp     esi, 5
0x1800c9658  jge     short loc_1800C9684
0x1800c965a  mov     eax, 0CCCCCCCDh
0x1800c965f  inc     esi
0x1800c9661  mul     ebp
0x1800c9663  shr     edx, 3
0x1800c9666  mov     al, dl
0x1800c9668  shl     al, 2
0x1800c966b  lea     ecx, [rax+rdx]
0x1800c966e  add     cl, cl
0x1800c9670  sub     bpl, cl
0x1800c9673  add     bpl, 30h ; '0'
0x1800c9677  mov     [rbx], bpl
0x1800c967a  mov     ebp, edx
0x1800c967c  dec     rbx
0x1800c967f  cmp     rbx, rdi
0x1800c9682  jnb     short loc_1800C963C
0x1800c9684  cmp     byte ptr [rbx], 58h ; 'X'
0x1800c9687  jnz     short loc_1800C96F1
0x1800c9689  cmp     esi, 5
0x1800c968c  jl      short loc_1800C96F1
0x1800c968e  mov     byte ptr [rbx], 61h ; 'a'
0x1800c9691  mov     esi, 62h ; 'b'
0x1800c9696  call    cs:__imp__errno
0x1800c969c  mov     ebp, [rax]
0x1800c969e  call    cs:__imp__errno
0x1800c96a4  mov     dword ptr [rax], 0
0x1800c96aa  xor     edx, edx; AccessMode
0x1800c96ac  mov     rcx, rdi; FileName
0x1800c96af  call    cs:__imp__access
0x1800c96b5  test    eax, eax
0x1800c96b7  jz      short loc_1800C96C4
0x1800c96b9  call    cs:__imp__errno
0x1800c96bf  cmp     dword ptr [rax], 0Dh
0x1800c96c2  jnz     short loc_1800C96DC
0x1800c96c4  call    cs:__imp__errno
0x1800c96ca  mov     dword ptr [rax], 0
0x1800c96d0  cmp     esi, 7Bh ; '{'
0x1800c96d3  jz      short loc_1800C96E9
0x1800c96d5  mov     [rbx], sil
0x1800c96d8  inc     esi
0x1800c96da  jmp     short loc_1800C96AA
0x1800c96dc  call    cs:__imp__errno
0x1800c96e2  mov     [rax], ebp
0x1800c96e4  mov     rax, rdi
0x1800c96e7  jmp     short loc_1800C96F3
0x1800c96e9  call    cs:__imp__errno
0x1800c96ef  mov     [rax], ebp
0x1800c96f1  xor     eax, eax
0x1800c96f3  add     rsp, 28h
0x1800c96f7  pop     rdi
0x1800c96f8  pop     rsi
0x1800c96f9  pop     rbp
0x1800c96fa  pop     rbx
0x1800c96fb  retn
```
