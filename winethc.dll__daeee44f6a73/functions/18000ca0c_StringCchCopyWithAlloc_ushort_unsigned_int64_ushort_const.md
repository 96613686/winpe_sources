# StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)

- ea: `0x18000ca0c`
- end: `0x18000caa4`
- name: `?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z`
- size: `152`
- prototype: `int(unsigned __int16 **, unsigned __int64, const unsigned __int16 *)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002ba8`
- `0x180002c54`
- `0x180002ccc`
- `0x180002d4c`
- `0x180004330`
- `0x180004c20`
- `0x180005b30`
- `0x18000c6cc`
- `0x180011ef0`
- `0x180012940`
- `0x1800129e8`

## callees

- `0x18000c998`
- `0x18000ca0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca62`

## pseudocode

```c
__int64 __fastcall StringCchCopyWithAlloc(unsigned __int16 **a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rdx
  const unsigned __int16 *v7; // rax
  __int64 result; // rax
  __int64 v9; // rbx
  unsigned __int16 *v10; // rax

  if ( !a1 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v5 = a2 - 1;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFF )
    return 2147942487LL;
  v6 = a2 - 1;
  v7 = a3;
  if ( v5 )
  {
    while ( *v7 )
    {
      ++v7;
      if ( !--v6 )
        goto LABEL_7;
    }
    result = 0;
    v9 = v5 - v6;
  }
  else
  {
LABEL_7:
    result = 2147942487LL;
    v9 = 0;
  }
  if ( (int)result >= 0 )
  {
    v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * v9 + 2);
    *a1 = v10;
    if ( v10 )
      return StringCchCopyW(v10, v9 + 1, a3);
    else
      return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000ca0c  push    rbx
0x18000ca0e  push    rbp
0x18000ca0f  push    rsi
0x18000ca10  push    rdi
0x18000ca11  sub     rsp, 28h
0x18000ca15  xor     ebp, ebp
0x18000ca17  mov     rdi, r8
0x18000ca1a  mov     rsi, rcx
0x18000ca1d  test    rcx, rcx
0x18000ca20  jz      short loc_18000CA95
0x18000ca22  test    r8, r8
0x18000ca25  jz      short loc_18000CA95
0x18000ca27  lea     rbx, [rdx-1]
0x18000ca2b  cmp     rbx, 7FFFFFFFh
0x18000ca32  ja      short loc_18000CA95
0x18000ca34  mov     rdx, rbx
0x18000ca37  mov     rax, r8
0x18000ca3a  test    rbx, rbx
0x18000ca3d  jz      short loc_18000CA4E
0x18000ca3f  cmp     [rax], bp
0x18000ca42  jz      short loc_18000CA7D
0x18000ca44  add     rax, 2
0x18000ca48  sub     rdx, 1
0x18000ca4c  jnz     short loc_18000CA3F
0x18000ca4e  mov     eax, 80070057h
0x18000ca53  mov     rbx, rbp
0x18000ca56  test    eax, eax
0x18000ca58  js      short loc_18000CA9A
0x18000ca5a  lea     rcx, ds:2[rbx*2]; cb
0x18000ca62  call    cs:__imp_CoTaskMemAlloc
0x18000ca69  nop     dword ptr [rax+rax+00h]
0x18000ca6e  mov     [rsi], rax
0x18000ca71  test    rax, rax
0x18000ca74  jnz     short loc_18000CA84
0x18000ca76  mov     eax, 8007000Eh
0x18000ca7b  jmp     short loc_18000CA9A
0x18000ca7d  mov     eax, ebp
0x18000ca7f  sub     rbx, rdx
0x18000ca82  jmp     short loc_18000CA56
0x18000ca84  lea     rdx, [rbx+1]; unsigned __int64
0x18000ca88  mov     r8, rdi; unsigned __int16 *
0x18000ca8b  mov     rcx, rax; unsigned __int16 *
0x18000ca8e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ca93  jmp     short loc_18000CA9A
0x18000ca95  mov     eax, 80070057h
0x18000ca9a  add     rsp, 28h
0x18000ca9e  pop     rdi
0x18000ca9f  pop     rsi
0x18000caa0  pop     rbp
0x18000caa1  pop     rbx
0x18000caa2  retn
```
