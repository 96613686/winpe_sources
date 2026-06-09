# StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x18000f1ac`
- end: `0x18000f267`
- name: `?StringCchCatW@@YAJPEA_W_KPEB_W@Z`
- size: `187`
- prototype: `__int64 __fastcall(wchar_t *, __int64, wchar_t *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bf5c`
- `0x18000f648`
- `0x180010448`
- `0x180010750`

## callees

- `0x18000f1ac`

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
0x18000f1ac  mov     [rsp+arg_0], rbx
0x18000f1b1  mov     [rsp+arg_8], rdi
0x18000f1b6  lea     rax, [rdx-1]
0x18000f1ba  mov     r10d, 7FFFFFFEh
0x18000f1c0  mov     r9, rdx
0x18000f1c3  mov     rbx, rcx
0x18000f1c6  cmp     rax, r10
0x18000f1c9  ja      loc_18000F255
0x18000f1cf  mov     r11, rdx
0x18000f1d2  mov     rax, rcx
0x18000f1d5  xor     edi, edi
0x18000f1d7  cmp     [rax], di
0x18000f1da  jz      short loc_18000F1E6
0x18000f1dc  add     rax, 2
0x18000f1e0  sub     r11, 1
0x18000f1e4  jnz     short loc_18000F1D7
0x18000f1e6  mov     rax, r11
0x18000f1e9  mov     rcx, r9
0x18000f1ec  neg     rax
0x18000f1ef  mov     rax, r11
0x18000f1f2  sbb     edx, edx
0x18000f1f4  sub     rcx, r11
0x18000f1f7  not     edx
0x18000f1f9  and     edx, 80070057h
0x18000f1ff  neg     rax
0x18000f202  sbb     rax, rax
0x18000f205  and     rax, rcx
0x18000f208  test    r11, r11
0x18000f20b  jz      short loc_18000F25A
0x18000f20d  sub     r9, rax
0x18000f210  lea     rax, [rbx+rax*2]
0x18000f214  jz      short loc_18000F238
0x18000f216  test    r10, r10
0x18000f219  jz      short loc_18000F238
0x18000f21b  movzx   ecx, word ptr [r8]
0x18000f21f  test    cx, cx
0x18000f222  jz      short loc_18000F238
0x18000f224  mov     [rax], cx
0x18000f227  add     r8, 2
0x18000f22b  add     rax, 2
0x18000f22f  dec     r10
0x18000f232  sub     r9, 1
0x18000f236  jnz     short loc_18000F216
0x18000f238  test    r9, r9
0x18000f23b  lea     rcx, [rax-2]
0x18000f23f  cmovnz  rcx, rax
0x18000f243  neg     r9
0x18000f246  sbb     edx, edx
0x18000f248  not     edx
0x18000f24a  and     edx, 8007007Ah
0x18000f250  mov     [rcx], di
0x18000f253  jmp     short loc_18000F25A
0x18000f255  mov     edx, 80070057h
0x18000f25a  mov     rbx, [rsp+arg_0]
0x18000f25f  mov     eax, edx
0x18000f261  mov     rdi, [rsp+arg_8]
0x18000f266  retn
```
