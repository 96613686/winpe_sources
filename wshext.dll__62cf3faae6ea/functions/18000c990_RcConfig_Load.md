# RcConfig_Load

- ea: `0x18000c990`
- end: `0x18000c9ca`
- name: `RcConfig_Load`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ca88`

## callees

- `0x18000c990`

## import_xrefs

- `KERNEL32!LoadResource` at `0x18000c9c3`
- `KERNEL32!FindResourceExW` at `0x18000c9a7`
- `KERNEL32!FindResourceExW` at `0x18000c9a7`

## pseudocode

```c
HRSRC __fastcall RcConfig_Load(HMODULE a1)
{
  HRSRC result; // rax

  result = FindResourceExW(a1, L"MUI", (LPCWSTR)1, 0);
  if ( result )
    return (HRSRC)LoadResource(a1, result);
  return result;
}

```

## disassembly

```asm
0x18000c990  push    rbx
0x18000c992  sub     rsp, 20h
0x18000c996  xor     r9d, r9d; wLanguage
0x18000c999  lea     rdx, Type; "MUI"
0x18000c9a0  mov     rbx, rcx
0x18000c9a3  lea     r8d, [r9+1]; lpName
0x18000c9a7  call    cs:__imp_FindResourceExW
0x18000c9ad  test    rax, rax
0x18000c9b0  jnz     short loc_18000C9B8
0x18000c9b2  add     rsp, 20h
0x18000c9b6  pop     rbx
0x18000c9b7  retn
0x18000c9b8  mov     rdx, rax
0x18000c9bb  mov     rcx, rbx
0x18000c9be  add     rsp, 20h
0x18000c9c2  pop     rbx
0x18000c9c3  jmp     cs:__imp_LoadResource
```
