# TdipIsSzInMultiSzSafe

- ea: `0x140001cb0`
- end: `0x140001d1b`
- name: `TdipIsSzInMultiSzSafe`
- size: `107`
- prototype: `__int64 __fastcall(wchar_t *Str2, wchar_t *Str1)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140001340`
- `0x140001540`

## callees

- `0x140001cb0`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x140001cdc`
- `ntoskrnl!_wcsicmp` at `0x140001cdc`

## pseudocode

```c
char __fastcall TdipIsSzInMultiSzSafe(wchar_t *Str2, wchar_t *Str1)
{
  const wchar_t *v2; // rbx
  __int64 v4; // rax

  v2 = Str1;
  if ( Str1 && Str2 )
  {
    while ( *v2 )
    {
      if ( !_wcsicmp(v2, Str2) )
        return 1;
      v4 = -1;
      while ( v2[++v4] != 0 )
        ;
      v2 += v4 + 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140001cb0  mov     [rsp+arg_0], rbx
0x140001cb5  push    rdi
0x140001cb6  sub     rsp, 20h
0x140001cba  mov     rbx, rdx
0x140001cbd  mov     rdi, rcx
0x140001cc0  test    rdx, rdx
0x140001cc3  jz      short loc_140001D09
0x140001cc5  test    rcx, rcx
0x140001cc8  jz      short loc_140001D09
0x140001cca  nop     word ptr [rax+rax+00h]
0x140001cd0  cmp     word ptr [rbx], 0
0x140001cd4  jz      short loc_140001D09
0x140001cd6  mov     rdx, rdi; Str2
0x140001cd9  mov     rcx, rbx; Str1
0x140001cdc  call    cs:__imp__wcsicmp
0x140001ce3  nop     dword ptr [rax+rax+00h]
0x140001ce8  test    eax, eax
0x140001cea  jz      short loc_140001D17
0x140001cec  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140001cf3  cmp     word ptr [rbx+rax*2+2], 0
0x140001cf9  lea     rax, [rax+1]
0x140001cfd  jnz     short loc_140001CF3
0x140001cff  lea     rbx, [rbx+rax*2]
0x140001d03  add     rbx, 2
0x140001d07  jmp     short loc_140001CD0
0x140001d09  xor     al, al
0x140001d0b  mov     rbx, [rsp+28h+arg_0]
0x140001d10  add     rsp, 20h
0x140001d14  pop     rdi
0x140001d15  retn
0x140001d17  mov     al, 1
0x140001d19  jmp     short loc_140001D0B
```
