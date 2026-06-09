# CIlKernel32::CopyFileW(ushort const *,ushort const *,int)

- ea: `0x18000e2a0`
- end: `0x18000e2da`
- name: `?CopyFileW@CIlKernel32@@UEAAHPEBG0H@Z`
- size: `58`
- prototype: `int(CIlKernel32 *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18000e2c8`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18000e2c8`

## pseudocode

```c
BOOL __fastcall CIlKernel32::CopyFileW(
        CIlKernel32 *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  return CopyFileExW(a2, a3, 0, 0, 0, a4 != 0);
}

```

## disassembly

```asm
0x18000e2a0  sub     rsp, 38h
0x18000e2a4  xor     eax, eax
0x18000e2a6  mov     r10, r8
0x18000e2a9  test    r9d, r9d
0x18000e2ac  mov     rcx, rdx; lpExistingFileName
0x18000e2af  mov     rdx, r10; lpNewFileName
0x18000e2b2  setnz   al
0x18000e2b5  xor     r9d, r9d; lpData
0x18000e2b8  mov     [rsp+38h+dwCopyFlags], eax; dwCopyFlags
0x18000e2bc  xor     r8d, r8d; lpProgressRoutine
0x18000e2bf  mov     [rsp+38h+pbCancel], 0; pbCancel
0x18000e2c8  call    cs:__imp_CopyFileExW
0x18000e2cf  nop     dword ptr [rax+rax+00h]
0x18000e2d4  add     rsp, 38h
0x18000e2d8  retn
```
