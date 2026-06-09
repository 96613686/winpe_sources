# WdsCreateExtendedPath

- ea: `0x18001b050`
- end: `0x18001b1af`
- name: `WdsCreateExtendedPath`
- size: `351`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800192f8`
- `0x18001b1c0`
- `0x18001b7a0`
- `0x18001b830`

## callees

- `0x1800165a0`
- `0x180019a40`
- `0x18001a28c`
- `0x18001b050`
- `0x18002e468`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001b0f1`
- `msvcrt!_wcsnicmp` at `0x18001b0f1`

## pseudocode

```c
__int64 __fastcall WdsCreateExtendedPath(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rcx
  unsigned __int16 *v5; // rax
  __int64 v6; // rcx
  signed int v7; // ebx
  unsigned __int64 v8; // rbp
  wchar_t *v9; // r14
  signed int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned __int16 *v14; // [rsp+60h] [rbp+18h] BYREF

  v3 = 0;
  v14 = 0;
  if ( !a1 || !a2 )
  {
    v7 = -2147024809;
LABEL_26:
    if ( v3 )
      operator delete(v3);
    return (unsigned int)v7;
  }
  v5 = a1;
  v6 = 0x7FFFFFFF;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v7 = v6 == 0 ? 0x80070057 : 0;
  v8 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
  if ( v6 )
  {
    if ( v8 < 2 )
      return (unsigned int)-2147024735;
    v9 = (wchar_t *)L"\\\\?\\";
    if ( v8 >= 4 && !_wcsnicmp(a1, L"\\\\?\\", 4u) )
    {
      if ( v8 == 4 )
        return (unsigned int)-2147024735;
      v7 = WcsDupHr(a1, &v14);
      if ( v7 >= 0 )
      {
LABEL_13:
        *a2 = v14;
        return (unsigned int)v7;
      }
LABEL_24:
      v3 = v14;
      goto LABEL_26;
    }
    if ( *a1 == 92 )
    {
      if ( a1[1] != 92 )
        return (unsigned int)-2147024809;
      v9 = (wchar_t *)L"\\\\?\\UNC";
      a1 += 2;
    }
    else if ( a1[1] != 58 )
    {
      return (unsigned int)-2147024809;
    }
    v10 = ConcatenatePaths(v9, (__int64)a1, &v14);
    if ( !(unsigned int)ElValidateWin32_8(v10, v11, v12, 0xDA7u) )
      goto LABEL_13;
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    else
      v7 = v10;
    if ( v7 < 0 )
      goto LABEL_24;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b050  mov     [rsp+arg_8], rbx
0x18001b055  push    rbp
0x18001b056  push    rdi
0x18001b057  push    r12
0x18001b059  push    r14
0x18001b05b  push    r15
0x18001b05d  sub     rsp, 20h
0x18001b061  xor     r12d, r12d
0x18001b064  mov     rdi, rcx
0x18001b067  mov     ecx, r12d; lpMem
0x18001b06a  mov     r15, rdx
0x18001b06d  mov     [rsp+48h+arg_10], rcx
0x18001b072  test    rdi, rdi
0x18001b075  jz      loc_18001B18B
0x18001b07b  test    rdx, rdx
0x18001b07e  jz      loc_18001B18B
0x18001b084  mov     r8d, 7FFFFFFFh
0x18001b08a  mov     rax, rdi
0x18001b08d  mov     ecx, r8d
0x18001b090  cmp     [rax], r12w
0x18001b094  jz      short loc_18001B0A0
0x18001b096  add     rax, 2
0x18001b09a  sub     rcx, 1
0x18001b09e  jnz     short loc_18001B090
0x18001b0a0  mov     rax, rcx
0x18001b0a3  neg     rax
0x18001b0a6  mov     rax, rcx
0x18001b0a9  sbb     ebx, ebx
0x18001b0ab  sub     r8, rcx
0x18001b0ae  not     ebx
0x18001b0b0  and     ebx, 80070057h
0x18001b0b6  neg     rax
0x18001b0b9  sbb     rbp, rbp
0x18001b0bc  and     rbp, r8
0x18001b0bf  test    rcx, rcx
0x18001b0c2  jz      loc_18001B19A
0x18001b0c8  cmp     rbp, 2
0x18001b0cc  jnb     short loc_18001B0D8
0x18001b0ce  mov     ebx, 800700A1h
0x18001b0d3  jmp     loc_18001B19A
0x18001b0d8  lea     r14, asc_180034528; "\\\\?\\"
0x18001b0df  cmp     rbp, 4
0x18001b0e3  jb      short loc_18001B124
0x18001b0e5  mov     r8d, 4; MaxCount
0x18001b0eb  mov     rdx, r14; String2
0x18001b0ee  mov     rcx, rdi; String1
0x18001b0f1  call    cs:__imp__wcsnicmp
0x18001b0f8  nop     dword ptr [rax+rax+00h]
0x18001b0fd  test    eax, eax
0x18001b0ff  jnz     short loc_18001B124
0x18001b101  cmp     rbp, 4
0x18001b105  jz      short loc_18001B0CE
0x18001b107  lea     rdx, [rsp+48h+arg_10]; unsigned __int16 **
0x18001b10c  mov     rcx, rdi; unsigned __int16 *
0x18001b10f  call    ?WcsDupHr@@YAJPEBGPEAPEAG@Z; WcsDupHr(ushort const *,ushort * *)
0x18001b114  mov     ebx, eax
0x18001b116  test    eax, eax
0x18001b118  js      short loc_18001B184
0x18001b11a  mov     rax, [rsp+48h+arg_10]
0x18001b11f  mov     [r15], rax
0x18001b122  jmp     short loc_18001B19A
0x18001b124  cmp     word ptr [rdi], 5Ch ; '\'
0x18001b128  jnz     short loc_18001B145
0x18001b12a  cmp     word ptr [rdi+2], 5Ch ; '\'
0x18001b12f  jz      short loc_18001B138
0x18001b131  mov     ebx, 80070057h
0x18001b136  jmp     short loc_18001B19A
0x18001b138  lea     r14, aUnc; "\\\\?\\UNC"
0x18001b13f  add     rdi, 4
0x18001b143  jmp     short loc_18001B14C
0x18001b145  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18001b14a  jnz     short loc_18001B131
0x18001b14c  lea     r8, [rsp+48h+arg_10]
0x18001b151  mov     rdx, rdi
0x18001b154  mov     rcx, r14
0x18001b157  call    ConcatenatePaths
0x18001b15c  mov     r9d, 0DA7h
0x18001b162  mov     ecx, eax
0x18001b164  mov     edi, eax
0x18001b166  call    ElValidateWin32_8
0x18001b16b  test    eax, eax
0x18001b16d  jz      short loc_18001B11A
0x18001b16f  test    edi, edi
0x18001b171  jg      short loc_18001B177
0x18001b173  mov     ebx, edi
0x18001b175  jmp     short loc_18001B180
0x18001b177  movzx   ebx, di
0x18001b17a  or      ebx, 80070000h
0x18001b180  test    ebx, ebx
0x18001b182  jns     short loc_18001B19A
0x18001b184  mov     rcx, [rsp+48h+arg_10]
0x18001b189  jmp     short loc_18001B190
0x18001b18b  mov     ebx, 80070057h
0x18001b190  test    rcx, rcx
0x18001b193  jz      short loc_18001B19A
0x18001b195  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b19a  mov     eax, ebx
0x18001b19c  mov     rbx, [rsp+48h+arg_8]
0x18001b1a1  add     rsp, 20h
0x18001b1a5  pop     r15
0x18001b1a7  pop     r14
0x18001b1a9  pop     r12
0x18001b1ab  pop     rdi
0x18001b1ac  pop     rbp
0x18001b1ad  retn
```
