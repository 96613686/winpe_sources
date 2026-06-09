# ShouldEnumerateReparsePoint

- ea: `0x18000c1fc`
- end: `0x18000c24d`
- name: `ShouldEnumerateReparsePoint`
- size: `81`
- prototype: `__int64 __fastcall(const WCHAR *, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x18000b380`
- `0x18000bb18`

## callees

- `0x18000c048`
- `0x18000c1fc`

## pseudocode

```c
__int64 __fastcall ShouldEnumerateReparsePoint(const WCHAR *a1, _DWORD *a2)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( (unsigned int)GetReparseTag(a1) )
  {
    v3 = 1;
    *a2 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x18000c1fc  mov     [rsp+arg_0], rbx
0x18000c201  push    rdi
0x18000c202  sub     rsp, 20h
0x18000c206  mov     rdi, rdx
0x18000c209  xor     ebx, ebx
0x18000c20b  lea     rdx, [rsp+28h+arg_10]
0x18000c210  mov     [rsp+28h+arg_10], ebx
0x18000c214  call    GetReparseTag
0x18000c219  test    eax, eax
0x18000c21b  jz      short loc_18000C240
0x18000c21d  mov     eax, [rsp+28h+arg_10]
0x18000c221  mov     ebx, 1
0x18000c226  test    eax, eax
0x18000c228  jns     short loc_18000C23C
0x18000c22a  cmp     eax, 0A0000003h
0x18000c22f  jz      short loc_18000C23C
0x18000c231  cmp     eax, 0A000000Ch
0x18000c236  jz      short loc_18000C23C
0x18000c238  mov     eax, ebx
0x18000c23a  jmp     short loc_18000C23E
0x18000c23c  xor     eax, eax
0x18000c23e  mov     [rdi], eax
0x18000c240  mov     eax, ebx
0x18000c242  mov     rbx, [rsp+28h+arg_0]
0x18000c247  add     rsp, 20h
0x18000c24b  pop     rdi
0x18000c24c  retn
```
