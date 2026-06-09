# CPrintSecurity::`vector deleting destructor'(uint)

- ea: `0x180008d50`
- end: `0x180008d80`
- name: `??_ECPrintSecurity@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CSecurityInformation *__fastcall(CSecurityInformation *hMem, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008d50`
- `0x18000befc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008d6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008d6c`

## pseudocode

```c
CSecurityInformation *__fastcall CPrintSecurity::`vector deleting destructor'(CSecurityInformation *hMem, char a2)
{
  CSecurityInformation::~CSecurityInformation(hMem);
  if ( (a2 & 1) != 0 )
    LocalFree(hMem);
  return hMem;
}

```

## disassembly

```asm
0x180008d50  mov     [rsp+arg_0], rbx
0x180008d55  push    rdi
0x180008d56  sub     rsp, 20h
0x180008d5a  mov     ebx, edx
0x180008d5c  mov     rdi, rcx
0x180008d5f  call    ??1CSecurityInformation@@UEAA@XZ; CSecurityInformation::~CSecurityInformation(void)
0x180008d64  test    bl, 1
0x180008d67  jz      short loc_180008D72
0x180008d69  mov     rcx, rdi; hMem
0x180008d6c  call    cs:__imp_LocalFree
0x180008d72  mov     rbx, [rsp+28h+arg_0]
0x180008d77  mov     rax, rdi
0x180008d7a  add     rsp, 20h
0x180008d7e  pop     rdi
0x180008d7f  retn
```
