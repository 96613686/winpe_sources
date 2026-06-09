# CATUtils::IsMachineOOBERunning(void)

- ea: `0x14001ccd0`
- end: `0x14001cd13`
- name: `?IsMachineOOBERunning@CATUtils@@SA_NXZ`
- size: `67`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140015fb8`
- `0x14001cfa0`

## callees

- `0x14001ccd0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001ccfe`
- `KERNEL32!CloseHandle` at `0x14001ccfe`
- `KERNEL32!OpenMutexW` at `0x14001cce4`
- `KERNEL32!OpenMutexW` at `0x14001cce4`

## pseudocode

```c
bool CATUtils::IsMachineOOBERunning(void)
{
  HANDLE v0; // rax
  bool v1; // bl

  v0 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
  v1 = v0 != 0;
  if ( v0 )
    CloseHandle(v0);
  return v1;
}

```

## disassembly

```asm
0x14001ccd0  push    rbx
0x14001ccd2  sub     rsp, 20h
0x14001ccd6  lea     r8, aGlobalWindowsM_0; "Global\\Windows.Machine.OOBE"
0x14001ccdd  xor     edx, edx; bInheritHandle
0x14001ccdf  mov     ecx, 100000h; dwDesiredAccess
0x14001cce4  call    cs:__imp_OpenMutexW
0x14001cceb  nop     dword ptr [rax+rax+00h]
0x14001ccf0  test    rax, rax
0x14001ccf3  setnz   bl
0x14001ccf6  test    rax, rax
0x14001ccf9  jz      short loc_14001CD0A
0x14001ccfb  mov     rcx, rax; hObject
0x14001ccfe  call    cs:__imp_CloseHandle
0x14001cd05  nop     dword ptr [rax+rax+00h]
0x14001cd0a  mov     al, bl
0x14001cd0c  add     rsp, 20h
0x14001cd10  pop     rbx
0x14001cd11  retn
```
