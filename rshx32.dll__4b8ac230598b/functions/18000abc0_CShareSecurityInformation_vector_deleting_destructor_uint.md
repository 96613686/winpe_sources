# CShareSecurityInformation::`vector deleting destructor'(uint)

- ea: `0x18000abc0`
- end: `0x18000abf0`
- name: `??_ECShareSecurityInformation@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CShareSecurityInformation *__fastcall(CShareSecurityInformation *hMem, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000abc0`
- `0x18000aef8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000abdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000abdc`

## pseudocode

```c
CShareSecurityInformation *__fastcall CShareSecurityInformation::`vector deleting destructor'(
        CShareSecurityInformation *hMem,
        char a2)
{
  CShareSecurityInformation::~CShareSecurityInformation(hMem);
  if ( (a2 & 1) != 0 )
    LocalFree(hMem);
  return hMem;
}

```

## disassembly

```asm
0x18000abc0  mov     [rsp+arg_0], rbx
0x18000abc5  push    rdi
0x18000abc6  sub     rsp, 20h
0x18000abca  mov     ebx, edx
0x18000abcc  mov     rdi, rcx
0x18000abcf  call    ??1CShareSecurityInformation@@UEAA@XZ; CShareSecurityInformation::~CShareSecurityInformation(void)
0x18000abd4  test    bl, 1
0x18000abd7  jz      short loc_18000ABE2
0x18000abd9  mov     rcx, rdi; hMem
0x18000abdc  call    cs:__imp_LocalFree
0x18000abe2  mov     rbx, [rsp+28h+arg_0]
0x18000abe7  mov     rax, rdi
0x18000abea  add     rsp, 20h
0x18000abee  pop     rdi
0x18000abef  retn
```
