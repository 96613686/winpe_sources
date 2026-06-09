# StrTrimLeft_Sys(char *,unsigned __int64,unsigned __int64 *,char const *,int)

- ea: `0x38387d8a0`
- end: `0x38387d960`
- name: `?StrTrimLeft_Sys@@YAKPEAD_KPEA_KPEBDH@Z`
- size: `192`
- prototype: `unsigned int __fastcall(char *Source, rsize_t DestinationSize, unsigned __int64 *, const char *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x38387d850`
- `0x38387fbb0`
- `0x383ac25f0`

## callees

- `0x38387d8a0`

## import_xrefs

- `MSVCR100!memmove_s` at `0x3838f830b`
- `MSVCR100!memmove_s` at `0x3838f830b`
- `USER32!CharNextExA` at `0x38387d90d`
- `USER32!CharNextExA` at `0x3838f82cd`
- `USER32!CharNextExA` at `0x38387d90d`
- `USER32!CharNextExA` at `0x3838f82cd`

## pseudocode

```c
__int64 __fastcall StrTrimLeft_Sys(char *Source, rsize_t DestinationSize, unsigned __int64 *a3, const char *a4)
{
  LPSTR v7; // rsi
  CHAR v8; // di
  const CHAR *v9; // rdx
  int v10; // ebx
  LPSTR v11; // rax
  int v12; // eax
  __int64 v14; // rax
  unsigned __int64 v15; // rbx

  v7 = Source;
  if ( *Source )
  {
    if ( Source[DestinationSize - 1] )
      return 87;
LABEL_3:
    v8 = *v7;
    v9 = " \t";
    v10 = 0;
    while ( *v9 )
    {
      if ( *v9 == v8 )
      {
        v7 = CharNextExA(0, v7, 0);
        if ( !*v7 )
          break;
        goto LABEL_3;
      }
      v11 = CharNextExA(0, v9, 0);
      v9 = v11;
      if ( v11 )
      {
        v12 = (_DWORD)v11 - (unsigned int)" \t";
        if ( v12 > v10 )
        {
          v10 = v12;
          if ( v12 < 3 )
            continue;
        }
      }
      break;
    }
    if ( v7 == Source )
    {
      if ( a3 )
        *a3 = DestinationSize;
    }
    else
    {
      v14 = v7 - Source;
      if ( v7 - Source >= DestinationSize )
        return 111;
      v15 = DestinationSize - v14;
      memmove_s(Source, DestinationSize, v7, DestinationSize - v14);
      Source[v15] = 0;
      if ( a3 )
        *a3 = v15;
    }
    return 0;
  }
  else
  {
    if ( a3 )
      *a3 = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x38387d8a0  mov     [rsp+arg_10], rbp
0x38387d8a5  mov     [rsp+arg_18], rsi
0x38387d8aa  push    r12
0x38387d8ac  push    r14
0x38387d8ae  push    r15
0x38387d8b0  sub     rsp, 20h
0x38387d8b4  cmp     byte ptr [rcx], 0
0x38387d8b7  mov     r14, r8
0x38387d8ba  mov     r15, rdx
0x38387d8bd  mov     rbp, rcx
0x38387d8c0  lea     r12, CurrentChar; " \t"
0x38387d8c7  mov     rsi, rcx
0x38387d8ca  jz      loc_3838F82A8
0x38387d8d0  cmp     byte ptr [rdx+rcx-1], 0
0x38387d8d5  jnz     loc_3838F82BB
0x38387d8db  mov     [rsp+38h+arg_0], rbx
0x38387d8e0  mov     [rsp+38h+arg_8], rdi
0x38387d8e5  nop     word ptr [rax+rax+00000000h]
0x38387d8f0  movzx   edi, byte ptr [rsi]
0x38387d8f3  mov     rdx, r12; lpCurrentChar
0x38387d8f6  xor     ebx, ebx
0x38387d8f8  movzx   eax, byte ptr [rdx]
0x38387d8fb  test    al, al
0x38387d8fd  jz      short loc_38387D92E
0x38387d8ff  xor     ecx, ecx; CodePage
0x38387d901  xor     r8d, r8d; dwFlags
0x38387d904  cmp     al, dil
0x38387d907  jz      loc_3838F82CA
0x38387d90d  call    cs:__imp_CharNextExA
0x38387d913  mov     rdx, rax
0x38387d916  test    rax, rax
0x38387d919  jz      short loc_38387D92E
0x38387d91b  sub     eax, r12d
0x38387d91e  cmp     eax, ebx
0x38387d920  jle     short loc_38387D92E
0x38387d922  mov     ebx, eax
0x38387d924  cmp     eax, 3
0x38387d927  jl      short loc_38387D8F8
0x38387d929  jmp     loc_3838F82C5
0x38387d92e  mov     rdi, [rsp+38h+arg_8]
0x38387d933  cmp     rsi, rbp
0x38387d936  jnz     loc_3838F82E4
0x38387d93c  test    r14, r14
0x38387d93f  jz      short loc_38387D944
0x38387d941  mov     [r14], r15
0x38387d944  xor     eax, eax
0x38387d946  mov     rbx, [rsp+38h+arg_0]
0x38387d94b  mov     rbp, [rsp+38h+arg_10]
0x38387d950  mov     rsi, [rsp+38h+arg_18]
0x38387d955  add     rsp, 20h
0x38387d959  pop     r15
0x38387d95b  pop     r14
0x38387d95d  pop     r12
0x38387d95f  retn
0x3838f82a8  test    r8, r8
0x3838f82ab  jz      short loc_3838F82B4
0x3838f82ad  mov     qword ptr [r8], 1
0x3838f82b4  xor     eax, eax
0x3838f82b6  jmp     loc_38387D94B
0x3838f82bb  mov     eax, 57h ; 'W'
0x3838f82c0  jmp     loc_38387D94B
0x3838f82c5  jmp     loc_38387D92E
0x3838f82ca  mov     rdx, rsi; lpCurrentChar
0x3838f82cd  call    cs:__imp_CharNextExA
0x3838f82d3  mov     rsi, rax
0x3838f82d6  cmp     byte ptr [rax], 0
0x3838f82d9  jz      loc_38387D92E
0x3838f82df  jmp     loc_38387D8F0
0x3838f82e4  mov     rax, rsi
0x3838f82e7  sub     rax, rbp
0x3838f82ea  cmp     rax, r15
0x3838f82ed  jb      short loc_3838F82F9
0x3838f82ef  mov     eax, 6Fh ; 'o'
0x3838f82f4  jmp     loc_38387D946
0x3838f82f9  mov     rbx, r15
0x3838f82fc  mov     r8, rsi; Source
0x3838f82ff  mov     rdx, r15; DestinationSize
0x3838f8302  sub     rbx, rax
0x3838f8305  mov     rcx, rbp; Destination
0x3838f8308  mov     r9, rbx; SourceSize
0x3838f830b  call    cs:__imp_memmove_s
0x3838f8311  mov     byte ptr [rbx+rbp], 0
0x3838f8315  test    r14, r14
0x3838f8318  jz      loc_38387D944
0x3838f831e  mov     [r14], rbx
0x3838f8321  jmp     loc_38387D944
```
