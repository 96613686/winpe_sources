# mciSeparateCommandParts(ushort const * *,int,ushort * *,ushort * *)

- ea: `0x180010de8`
- end: `0x180010ef5`
- name: `?mciSeparateCommandParts@@YAKPEAPEBGHPEAPEAG1@Z`
- size: `269`
- prototype: `unsigned int __fastcall(const unsigned __int16 **, int, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010504`

## callees

- `0x180010de8`
- `0x180014ca8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010eca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010eca`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010e84`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010e84`

## pseudocode

```c
__int64 __fastcall mciSeparateCommandParts(
        const unsigned __int16 **a1,
        int a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  __int16 *v4; // rax
  __int16 v9; // r10
  __int64 result; // rax
  __int16 *v11; // rbx
  __int16 v12; // ax
  unsigned int v13; // ebx
  const unsigned __int16 *v14; // [rsp+50h] [rbp+8h] BYREF

  v4 = (__int16 *)*a1;
  v14 = (const unsigned __int16 *)v4;
  v9 = *v4;
  if ( *v4 == 32 )
  {
    do
      v9 = *++v4;
    while ( *v4 == 32 );
    v14 = (const unsigned __int16 *)v4;
  }
  if ( !v9 )
    return 267;
  result = mciEatToken((__int16 **)&v14, 32, (__int64 *)a3, 0);
  if ( !(_DWORD)result )
  {
    v11 = (__int16 *)v14;
    if ( *v14 == 32 )
    {
      do
        ++v11;
      while ( *v11 == 32 );
      v14 = (const unsigned __int16 *)v11;
    }
    if ( a2 && lstrcmpiW(wszOpen, *a3) )
    {
      while ( 1 )
      {
        v12 = *v11;
        if ( !*v11 )
          break;
        ++v11;
        if ( v12 == 33 )
        {
          v14 = (const unsigned __int16 *)v11;
          break;
        }
      }
    }
    v13 = mciEatToken((__int16 **)&v14, 32, (__int64 *)a4, 0);
    if ( v13 )
    {
      HeapFree(hHeap, 0, *a3);
      return v13;
    }
    else
    {
      *a1 = v14;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010de8  mov     [rsp+arg_8], rbx
0x180010ded  mov     [rsp+arg_10], rbp
0x180010df2  push    rsi
0x180010df3  push    rdi
0x180010df4  push    r12
0x180010df6  push    r14
0x180010df8  push    r15
0x180010dfa  sub     rsp, 20h
0x180010dfe  mov     rax, [rcx]
0x180010e01  mov     r12d, 20h ; ' '
0x180010e07  mov     r14, r9
0x180010e0a  mov     [rsp+48h+arg_0], rax
0x180010e0f  mov     rdi, r8
0x180010e12  mov     ebp, edx
0x180010e14  mov     rsi, rcx
0x180010e17  movzx   r10d, word ptr [rax]
0x180010e1b  cmp     r10w, r12w
0x180010e1f  jnz     short loc_180010E34
0x180010e21  add     rax, 2
0x180010e25  movzx   r10d, word ptr [rax]
0x180010e29  cmp     r10w, r12w
0x180010e2d  jz      short loc_180010E21
0x180010e2f  mov     [rsp+48h+arg_0], rax
0x180010e34  test    r10w, r10w
0x180010e38  jnz     short loc_180010E44
0x180010e3a  mov     eax, 10Bh
0x180010e3f  jmp     loc_180010EDE
0x180010e44  mov     edx, r12d
0x180010e47  lea     rcx, [rsp+48h+arg_0]
0x180010e4c  xor     r9d, r9d
0x180010e4f  call    mciEatToken
0x180010e54  test    eax, eax
0x180010e56  jnz     loc_180010EDE
0x180010e5c  mov     rbx, [rsp+48h+arg_0]
0x180010e61  cmp     [rbx], r12w
0x180010e65  jnz     short loc_180010E76
0x180010e67  add     rbx, 2
0x180010e6b  cmp     [rbx], r12w
0x180010e6f  jz      short loc_180010E67
0x180010e71  mov     [rsp+48h+arg_0], rbx
0x180010e76  test    ebp, ebp
0x180010e78  jz      short loc_180010EA5
0x180010e7a  mov     rdx, [rdi]; lpString2
0x180010e7d  lea     rcx, ?wszOpen@@3PAGA; "open"
0x180010e84  call    cs:__imp_lstrcmpiW
0x180010e8a  test    eax, eax
0x180010e8c  jz      short loc_180010EA5
0x180010e8e  movzx   eax, word ptr [rbx]
0x180010e91  test    ax, ax
0x180010e94  jz      short loc_180010EA5
0x180010e96  add     rbx, 2
0x180010e9a  cmp     ax, 21h ; '!'
0x180010e9e  jnz     short loc_180010E8E
0x180010ea0  mov     [rsp+48h+arg_0], rbx
0x180010ea5  mov     edx, r12d
0x180010ea8  lea     rcx, [rsp+48h+arg_0]
0x180010ead  xor     r9d, r9d
0x180010eb0  mov     r8, r14
0x180010eb3  call    mciEatToken
0x180010eb8  mov     ebx, eax
0x180010eba  test    eax, eax
0x180010ebc  jz      short loc_180010ED4
0x180010ebe  mov     r8, [rdi]; lpMem
0x180010ec1  xor     edx, edx; dwFlags
0x180010ec3  mov     rcx, cs:hHeap; hHeap
0x180010eca  call    cs:__imp_HeapFree
0x180010ed0  mov     eax, ebx
0x180010ed2  jmp     short loc_180010EDE
0x180010ed4  mov     rax, [rsp+48h+arg_0]
0x180010ed9  mov     [rsi], rax
0x180010edc  xor     eax, eax
0x180010ede  mov     rbx, [rsp+48h+arg_8]
0x180010ee3  mov     rbp, [rsp+48h+arg_10]
0x180010ee8  add     rsp, 20h
0x180010eec  pop     r15
0x180010eee  pop     r14
0x180010ef0  pop     r12
0x180010ef2  pop     rdi
0x180010ef3  pop     rsi
0x180010ef4  retn
```
