# FindInETagList(char const *,char const *,int)

- ea: `0x180005230`
- end: `0x18000534e`
- name: `?FindInETagList@@YAHPEBD0H@Z`
- size: `286`
- prototype: `__int64 __fastcall(const char *, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ed8`

## callees

- `0x180005230`

## import_xrefs

- `msvcrt!isspace` at `0x18000526d`
- `msvcrt!isspace` at `0x1800052ab`
- `msvcrt!isspace` at `0x180005319`
- `msvcrt!isspace` at `0x18000526d`
- `msvcrt!isspace` at `0x1800052ab`
- `msvcrt!isspace` at `0x180005319`

## pseudocode

```c
__int64 __fastcall FindInETagList(const char *a1, const char *a2, int a3)
{
  const char *v4; // rbx
  const char *v5; // rdi
  unsigned __int8 v6; // al
  int i; // ecx
  char v8; // al
  int v9; // ecx
  const char *v10; // rdx
  int v11; // r8d
  int v12; // eax
  char v13; // r9
  int v14; // eax

  v4 = a2;
  v5 = a1;
  if ( *(_WORD *)a1 == 12119 )
  {
    if ( !a3 )
      return 0;
    v5 = a1 + 2;
  }
  v6 = *a2;
LABEL_5:
  for ( i = v6; isspace(i); i = *(unsigned __int8 *)v4 )
    ++v4;
  v8 = *v4;
  if ( !*v4 )
    return 0;
  if ( v8 != 42 )
  {
    if ( v8 != 87 )
      goto LABEL_17;
    if ( v4[1] == 47 )
    {
      if ( a3 )
      {
        for ( v4 += 2; isspace(*(unsigned __int8 *)v4); ++v4 )
          ;
        v8 = *v4;
        if ( *v4 )
        {
LABEL_17:
          if ( v8 == 34 )
          {
            v9 = 0;
            v10 = v5;
            v11 = 1;
            while ( 1 )
            {
              v12 = v9 + 1;
              v13 = *v10;
              if ( *v4 != 34 )
                v12 = v9;
              v9 = v12;
              v14 = 0;
              if ( v13 == *v4 )
                v14 = v11;
              v11 = v14;
              if ( !*v4 )
                break;
              ++v4;
              if ( v13 )
              {
                ++v10;
                if ( v9 != 2 )
                  continue;
              }
              if ( v14 )
                return 1;
              while ( v9 != 2 )
              {
                if ( *v4 == 34 )
                {
                  ++v9;
                }
                else if ( !*v4 )
                {
                  return 0;
                }
                ++v4;
              }
              while ( isspace(*(unsigned __int8 *)v4) )
                ++v4;
              if ( *v4 == 44 )
              {
                v6 = *++v4;
                if ( *v4 )
                  goto LABEL_5;
              }
              return 0;
            }
          }
        }
      }
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180005230  mov     [rsp+arg_0], rbx
0x180005235  mov     [rsp+arg_8], rsi
0x18000523a  push    rdi
0x18000523b  sub     rsp, 20h
0x18000523f  cmp     byte ptr [rcx], 57h ; 'W'
0x180005242  mov     esi, r8d
0x180005245  mov     rbx, rdx
0x180005248  mov     rdi, rcx
0x18000524b  jnz     short loc_180005260
0x18000524d  cmp     byte ptr [rcx+1], 2Fh ; '/'
0x180005251  jnz     short loc_180005260
0x180005253  test    r8d, r8d
0x180005256  jz      loc_180005335
0x18000525c  add     rdi, 2
0x180005260  mov     al, [rdx]
0x180005262  movzx   ecx, al
0x180005265  jmp     short loc_18000526D
0x180005267  inc     rbx
0x18000526a  movzx   ecx, byte ptr [rbx]; C
0x18000526d  call    cs:__imp_isspace
0x180005273  test    eax, eax
0x180005275  jnz     short loc_180005267
0x180005277  mov     al, [rbx]
0x180005279  test    al, al
0x18000527b  jz      loc_180005335
0x180005281  cmp     al, 2Ah ; '*'
0x180005283  jz      loc_180005347
0x180005289  cmp     al, 57h ; 'W'
0x18000528b  jnz     short loc_1800052BB
0x18000528d  cmp     byte ptr [rbx+1], 2Fh ; '/'
0x180005291  jnz     loc_180005335
0x180005297  test    esi, esi
0x180005299  jz      loc_180005335
0x18000529f  add     rbx, 2
0x1800052a3  jmp     short loc_1800052A8
0x1800052a5  inc     rbx
0x1800052a8  movzx   ecx, byte ptr [rbx]; C
0x1800052ab  call    cs:__imp_isspace
0x1800052b1  test    eax, eax
0x1800052b3  jnz     short loc_1800052A5
0x1800052b5  mov     al, [rbx]
0x1800052b7  test    al, al
0x1800052b9  jz      short loc_180005335
0x1800052bb  cmp     al, 22h ; '"'
0x1800052bd  jnz     short loc_180005335
0x1800052bf  xor     ecx, ecx
0x1800052c1  mov     rdx, rdi
0x1800052c4  lea     r8d, [rcx+1]
0x1800052c8  cmp     byte ptr [rbx], 22h ; '"'
0x1800052cb  lea     eax, [rcx+1]
0x1800052ce  mov     r9b, [rdx]
0x1800052d1  cmovnz  eax, ecx
0x1800052d4  mov     ecx, eax
0x1800052d6  xor     eax, eax
0x1800052d8  cmp     r9b, [rbx]
0x1800052db  cmovz   eax, r8d
0x1800052df  cmp     byte ptr [rbx], 0
0x1800052e2  mov     r8d, eax
0x1800052e5  jz      short loc_180005335
0x1800052e7  inc     rbx
0x1800052ea  test    r9b, r9b
0x1800052ed  jz      short loc_1800052F7
0x1800052ef  inc     rdx
0x1800052f2  cmp     ecx, 2
0x1800052f5  jnz     short loc_1800052C8
0x1800052f7  test    eax, eax
0x1800052f9  jnz     short loc_180005347
0x1800052fb  cmp     ecx, 2
0x1800052fe  jz      short loc_180005316
0x180005300  mov     al, [rbx]
0x180005302  cmp     al, 22h ; '"'
0x180005304  jnz     short loc_18000530A
0x180005306  inc     ecx
0x180005308  jmp     short loc_18000530E
0x18000530a  test    al, al
0x18000530c  jz      short loc_180005335
0x18000530e  inc     rbx
0x180005311  jmp     short loc_1800052FB
0x180005313  inc     rbx
0x180005316  movzx   ecx, byte ptr [rbx]; C
0x180005319  call    cs:__imp_isspace
0x18000531f  test    eax, eax
0x180005321  jnz     short loc_180005313
0x180005323  cmp     byte ptr [rbx], 2Ch ; ','
0x180005326  jnz     short loc_180005335
0x180005328  inc     rbx
0x18000532b  mov     al, [rbx]
0x18000532d  test    al, al
0x18000532f  jnz     loc_180005262
0x180005335  xor     eax, eax
0x180005337  mov     rbx, [rsp+28h+arg_0]
0x18000533c  mov     rsi, [rsp+28h+arg_8]
0x180005341  add     rsp, 20h
0x180005345  pop     rdi
0x180005346  retn
0x180005347  mov     eax, 1
0x18000534c  jmp     short loc_180005337
```
