# pSetupBeginSynchronizedAccess

- ea: `0x18000a210`
- end: `0x18000a242`
- name: `pSetupBeginSynchronizedAccess`
- size: `50`
- prototype: `_BOOL8 __fastcall(HANDLE *lpHandles)`
- caller_count: `11`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800086c0`
- `0x180008d20`
- `0x180009d70`
- `0x18000a248`
- `0x18000a2f8`
- `0x18000a3a0`
- `0x18000aba0`
- `0x18000ea20`
- `0x180011d7c`
- `0x180012dac`
- `0x180013498`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a22d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a22d`

## pseudocode

```c
_BOOL8 __fastcall pSetupBeginSynchronizedAccess(HANDLE *lpHandles)
{
  return WaitForMultipleObjectsEx(2u, lpHandles, 0, 0xFFFFFFFF, 0) == 1;
}

```

## disassembly

```asm
0x18000a210  sub     rsp, 38h
0x18000a214  mov     rdx, rcx; lpHandles
0x18000a217  mov     [rsp+38h+bAlertable], 0; bAlertable
0x18000a21f  mov     ecx, 2; nCount
0x18000a224  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000a22a  xor     r8d, r8d; bWaitAll
0x18000a22d  call    cs:__imp_WaitForMultipleObjectsEx
0x18000a233  xor     ecx, ecx
0x18000a235  cmp     eax, 1
0x18000a238  setz    cl
0x18000a23b  mov     eax, ecx
0x18000a23d  add     rsp, 38h
0x18000a241  retn
```
