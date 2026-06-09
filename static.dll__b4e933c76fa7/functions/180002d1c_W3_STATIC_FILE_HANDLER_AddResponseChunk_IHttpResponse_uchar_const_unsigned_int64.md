# W3_STATIC_FILE_HANDLER::AddResponseChunk(IHttpResponse *,uchar const *,unsigned __int64)

- ea: `0x180002d1c`
- end: `0x180002da6`
- name: `?AddResponseChunk@W3_STATIC_FILE_HANDLER@@CAJPEAVIHttpResponse@@PEBE_K@Z`
- size: `138`
- prototype: `__int64 __fastcall(struct IHttpResponse *, const unsigned __int8 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002dd8`

## callees

- `0x180002d1c`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall W3_STATIC_FILE_HANDLER::AddResponseChunk(
        struct IHttpResponse *a1,
        const unsigned __int8 *a2,
        unsigned __int64 a3)
{
  __int64 result; // rax
  __int64 v7; // rax
  _QWORD v8[2]; // [rsp+20h] [rbp-48h] BYREF
  int v9; // [rsp+30h] [rbp-38h]
  __int64 v10; // [rsp+34h] [rbp-34h]
  int v11; // [rsp+3Ch] [rbp-2Ch]

  v8[0] = 0;
  v10 = 0;
  v11 = 0;
  while ( a3 )
  {
    v8[1] = a2;
    v9 = -1;
    if ( a3 <= 0xFFFFFFFF )
      v9 = a3;
    result = (*(__int64 (__fastcall **)(struct IHttpResponse *, _QWORD *, __int64))(*(_QWORD *)a1 + 160LL))(
               a1,
               v8,
               0xFFFFFFFFLL);
    if ( (int)result < 0 )
      return result;
    if ( a3 <= 0xFFFFFFFF )
    {
      v7 = a3;
      a2 += a3;
    }
    else
    {
      v7 = 0xFFFFFFFFLL;
      a2 += 0xFFFFFFFFLL;
    }
    a3 -= v7;
  }
  return 0;
}

```

## disassembly

```asm
0x180002d1c  push    rbx
0x180002d1e  push    rbp
0x180002d1f  push    rsi
0x180002d20  push    rdi
0x180002d21  sub     rsp, 48h
0x180002d25  mov     rbx, r8
0x180002d28  mov     [rsp+68h+var_48], 0
0x180002d31  mov     rdi, rdx
0x180002d34  mov     [rsp+68h+var_34], 0
0x180002d3d  mov     rsi, rcx
0x180002d40  mov     [rsp+68h+var_2C], 0
0x180002d48  mov     ebp, 0FFFFFFFFh
0x180002d4d  test    rbx, rbx
0x180002d50  jz      short loc_180002D9B
0x180002d52  mov     [rsp+68h+var_40], rdi
0x180002d57  mov     [rsp+68h+var_38], ebp
0x180002d5b  cmp     rbx, rbp
0x180002d5e  ja      short loc_180002D64
0x180002d60  mov     [rsp+68h+var_38], ebx
0x180002d64  mov     rax, [rsi]
0x180002d67  lea     rdx, [rsp+68h+var_48]
0x180002d6c  or      r8d, 0FFFFFFFFh
0x180002d70  mov     rcx, rsi
0x180002d73  mov     rax, [rax+0A0h]
0x180002d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d7f  test    eax, eax
0x180002d81  js      short loc_180002D9D
0x180002d83  cmp     rbx, rbp
0x180002d86  jbe     short loc_180002D90
0x180002d88  mov     rax, rbp
0x180002d8b  add     rdi, rbp
0x180002d8e  jmp     short loc_180002D96
0x180002d90  mov     rax, rbx
0x180002d93  add     rdi, rbx
0x180002d96  sub     rbx, rax
0x180002d99  jmp     short loc_180002D4D
0x180002d9b  xor     eax, eax
0x180002d9d  add     rsp, 48h
0x180002da1  pop     rdi
0x180002da2  pop     rsi
0x180002da3  pop     rbp
0x180002da4  pop     rbx
0x180002da5  retn
```
