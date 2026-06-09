# StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x18000b288`
- end: `0x18000b343`
- name: `?StringCchCatW@@YAJPEA_W_KPEB_W@Z`
- size: `187`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800057f0`
- `0x18000920c`
- `0x180009490`
- `0x180009e20`
- `0x18000b7e8`
- `0x18000ba74`

## callees

- `0x18000b288`

## pseudocode

```c
__int64 __fastcall StringCchCatW(wchar_t *a1, __int64 a2, wchar_t *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  wchar_t *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r9
  wchar_t *i; // rax
  wchar_t *v11; // rcx

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (a2 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = a2 - v8;
      for ( i = &a1[v8]; v9; --v9 )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *i++ = *a3++;
        --v3;
      }
      v11 = i - 1;
      if ( v9 )
        v11 = i;
      v7 = v9 == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000b288  mov     [rsp+arg_0], rbx
0x18000b28d  mov     [rsp+arg_8], rdi
0x18000b292  lea     rax, [rdx-1]
0x18000b296  mov     r10d, 7FFFFFFEh
0x18000b29c  mov     r9, rdx
0x18000b29f  mov     rbx, rcx
0x18000b2a2  cmp     rax, r10
0x18000b2a5  ja      loc_18000B331
0x18000b2ab  mov     r11, rdx
0x18000b2ae  mov     rax, rcx
0x18000b2b1  xor     edi, edi
0x18000b2b3  cmp     [rax], di
0x18000b2b6  jz      short loc_18000B2C2
0x18000b2b8  add     rax, 2
0x18000b2bc  sub     r11, 1
0x18000b2c0  jnz     short loc_18000B2B3
0x18000b2c2  mov     rax, r11
0x18000b2c5  mov     rcx, r9
0x18000b2c8  neg     rax
0x18000b2cb  mov     rax, r11
0x18000b2ce  sbb     edx, edx
0x18000b2d0  sub     rcx, r11
0x18000b2d3  not     edx
0x18000b2d5  and     edx, 80070057h
0x18000b2db  neg     rax
0x18000b2de  sbb     rax, rax
0x18000b2e1  and     rax, rcx
0x18000b2e4  test    r11, r11
0x18000b2e7  jz      short loc_18000B336
0x18000b2e9  sub     r9, rax
0x18000b2ec  lea     rax, [rbx+rax*2]
0x18000b2f0  jz      short loc_18000B314
0x18000b2f2  test    r10, r10
0x18000b2f5  jz      short loc_18000B314
0x18000b2f7  movzx   ecx, word ptr [r8]
0x18000b2fb  test    cx, cx
0x18000b2fe  jz      short loc_18000B314
0x18000b300  mov     [rax], cx
0x18000b303  add     r8, 2
0x18000b307  add     rax, 2
0x18000b30b  dec     r10
0x18000b30e  sub     r9, 1
0x18000b312  jnz     short loc_18000B2F2
0x18000b314  test    r9, r9
0x18000b317  lea     rcx, [rax-2]
0x18000b31b  cmovnz  rcx, rax
0x18000b31f  neg     r9
0x18000b322  sbb     edx, edx
0x18000b324  not     edx
0x18000b326  and     edx, 8007007Ah
0x18000b32c  mov     [rcx], di
0x18000b32f  jmp     short loc_18000B336
0x18000b331  mov     edx, 80070057h
0x18000b336  mov     rbx, [rsp+arg_0]
0x18000b33b  mov     eax, edx
0x18000b33d  mov     rdi, [rsp+arg_8]
0x18000b342  retn
```
