# StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x18000a6bc`
- end: `0x18000a777`
- name: `?StringCchCatW@@YAJPEA_W_KPEB_W@Z`
- size: `187`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e08`
- `0x180006040`
- `0x18000ab28`
- `0x18000caa8`

## callees

- `0x18000a6bc`

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
0x18000a6bc  mov     [rsp+arg_0], rbx
0x18000a6c1  mov     [rsp+arg_8], rdi
0x18000a6c6  lea     rax, [rdx-1]
0x18000a6ca  mov     r10d, 7FFFFFFEh
0x18000a6d0  mov     r9, rdx
0x18000a6d3  mov     rbx, rcx
0x18000a6d6  cmp     rax, r10
0x18000a6d9  ja      loc_18000A765
0x18000a6df  mov     r11, rdx
0x18000a6e2  mov     rax, rcx
0x18000a6e5  xor     edi, edi
0x18000a6e7  cmp     [rax], di
0x18000a6ea  jz      short loc_18000A6F6
0x18000a6ec  add     rax, 2
0x18000a6f0  sub     r11, 1
0x18000a6f4  jnz     short loc_18000A6E7
0x18000a6f6  mov     rax, r11
0x18000a6f9  mov     rcx, r9
0x18000a6fc  neg     rax
0x18000a6ff  mov     rax, r11
0x18000a702  sbb     edx, edx
0x18000a704  sub     rcx, r11
0x18000a707  not     edx
0x18000a709  and     edx, 80070057h
0x18000a70f  neg     rax
0x18000a712  sbb     rax, rax
0x18000a715  and     rax, rcx
0x18000a718  test    r11, r11
0x18000a71b  jz      short loc_18000A76A
0x18000a71d  sub     r9, rax
0x18000a720  lea     rax, [rbx+rax*2]
0x18000a724  jz      short loc_18000A748
0x18000a726  test    r10, r10
0x18000a729  jz      short loc_18000A748
0x18000a72b  movzx   ecx, word ptr [r8]
0x18000a72f  test    cx, cx
0x18000a732  jz      short loc_18000A748
0x18000a734  mov     [rax], cx
0x18000a737  add     r8, 2
0x18000a73b  add     rax, 2
0x18000a73f  dec     r10
0x18000a742  sub     r9, 1
0x18000a746  jnz     short loc_18000A726
0x18000a748  test    r9, r9
0x18000a74b  lea     rcx, [rax-2]
0x18000a74f  cmovnz  rcx, rax
0x18000a753  neg     r9
0x18000a756  sbb     edx, edx
0x18000a758  not     edx
0x18000a75a  and     edx, 8007007Ah
0x18000a760  mov     [rcx], di
0x18000a763  jmp     short loc_18000A76A
0x18000a765  mov     edx, 80070057h
0x18000a76a  mov     rbx, [rsp+arg_0]
0x18000a76f  mov     eax, edx
0x18000a771  mov     rdi, [rsp+arg_8]
0x18000a776  retn
```
