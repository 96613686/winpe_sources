# IsUtilmanRunning(void)

- ea: `0x14000e6e4`
- end: `0x14000e725`
- name: `?IsUtilmanRunning@@YA_NXZ`
- size: `65`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e2a0`
- `0x140012f54`

## callees

- `0x14000e6e4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000e710`
- `KERNEL32!CloseHandle` at `0x14000e710`
- `KERNEL32!OpenEventW` at `0x14000e6fa`
- `KERNEL32!OpenEventW` at `0x14000e6fa`

## string_xrefs

- `0x14000e6ea`: `Local\EaseOfAccessDialog`

## pseudocode

```c
char IsUtilmanRunning(void)
{
  char v0; // bl
  HANDLE v1; // rax

  v0 = 0;
  v1 = OpenEventW(0x1F0003u, 0, L"Local\\EaseOfAccessDialog");
  if ( v1 )
  {
    v0 = 1;
    CloseHandle(v1);
  }
  return v0;
}

```

## disassembly

```asm
0x14000e6e4  push    rbx
0x14000e6e6  sub     rsp, 20h
0x14000e6ea  lea     r8, aLocalEaseofacc; "Local\\EaseOfAccessDialog"
0x14000e6f1  xor     edx, edx; bInheritHandle
0x14000e6f3  mov     ecx, 1F0003h; dwDesiredAccess
0x14000e6f8  xor     bl, bl
0x14000e6fa  call    cs:__imp_OpenEventW
0x14000e701  nop     dword ptr [rax+rax+00h]
0x14000e706  test    rax, rax
0x14000e709  jz      short loc_14000E71C
0x14000e70b  mov     rcx, rax; hObject
0x14000e70e  mov     bl, 1
0x14000e710  call    cs:__imp_CloseHandle
0x14000e717  nop     dword ptr [rax+rax+00h]
0x14000e71c  mov     al, bl
0x14000e71e  add     rsp, 20h
0x14000e722  pop     rbx
0x14000e723  retn
```
