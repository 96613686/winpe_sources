# RcConfig_Load

- ea: `0x18000fa6c`
- end: `0x18000faa6`
- name: `RcConfig_Load`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000fb64`

## callees

- `0x18000fa6c`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x18000fa83`
- `KERNEL32!FindResourceExW` at `0x18000fa83`
- `KERNEL32!LoadResource` at `0x18000fa9f`

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
0x18000fa6c  push    rbx
0x18000fa6e  sub     rsp, 20h
0x18000fa72  xor     r9d, r9d; wLanguage
0x18000fa75  lea     rdx, Type; "MUI"
0x18000fa7c  mov     rbx, rcx
0x18000fa7f  lea     r8d, [r9+1]; lpName
0x18000fa83  call    cs:__imp_FindResourceExW
0x18000fa89  test    rax, rax
0x18000fa8c  jnz     short loc_18000FA94
0x18000fa8e  add     rsp, 20h
0x18000fa92  pop     rbx
0x18000fa93  retn
0x18000fa94  mov     rdx, rax
0x18000fa97  mov     rcx, rbx
0x18000fa9a  add     rsp, 20h
0x18000fa9e  pop     rbx
0x18000fa9f  jmp     cs:__imp_LoadResource
```
