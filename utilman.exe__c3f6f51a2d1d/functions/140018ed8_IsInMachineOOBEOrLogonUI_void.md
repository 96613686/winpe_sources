# IsInMachineOOBEOrLogonUI(void)

- ea: `0x140018ed8`
- end: `0x140018f22`
- name: `?IsInMachineOOBEOrLogonUI@@YA_NXZ`
- size: `74`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140019090`
- `0x1400191d0`

## callees

- `0x14000e624`
- `0x140018ed8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140018f0d`
- `KERNEL32!CloseHandle` at `0x140018f0d`
- `KERNEL32!OpenMutexW` at `0x140018ef7`
- `KERNEL32!OpenMutexW` at `0x140018ef7`

## pseudocode

```c
char IsInMachineOOBEOrLogonUI(void)
{
  char v0; // bl
  HANDLE v1; // rax

  v0 = IsLogonUI();
  if ( !v0 )
  {
    v1 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
    if ( v1 )
    {
      v0 = 1;
      CloseHandle(v1);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x140018ed8  push    rbx
0x140018eda  sub     rsp, 20h
0x140018ede  call    ?IsLogonUI@@YA_NXZ; IsLogonUI(void)
0x140018ee3  mov     bl, al
0x140018ee5  test    al, al
0x140018ee7  jnz     short loc_140018F19
0x140018ee9  lea     r8, aGlobalWindowsM; "Global\\Windows.Machine.OOBE"
0x140018ef0  xor     edx, edx; bInheritHandle
0x140018ef2  mov     ecx, 100000h; dwDesiredAccess
0x140018ef7  call    cs:__imp_OpenMutexW
0x140018efe  nop     dword ptr [rax+rax+00h]
0x140018f03  test    rax, rax
0x140018f06  jz      short loc_140018F19
0x140018f08  mov     rcx, rax; hObject
0x140018f0b  mov     bl, 1
0x140018f0d  call    cs:__imp_CloseHandle
0x140018f14  nop     dword ptr [rax+rax+00h]
0x140018f19  mov     al, bl
0x140018f1b  add     rsp, 20h
0x140018f1f  pop     rbx
0x140018f20  retn
```
