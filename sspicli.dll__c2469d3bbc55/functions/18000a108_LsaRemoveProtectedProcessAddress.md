# LsaRemoveProtectedProcessAddress

- ea: `0x18000a108`
- end: `0x18000a167`
- name: `LsaRemoveProtectedProcessAddress`
- size: `95`
- prototype: `NTSTATUS __stdcall(PVOID BufferAddress, ULONG BufferSize)`
- caller_count: `12`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001090`
- `0x1800012d0`
- `0x180003ca4`
- `0x180004290`
- `0x1800049c0`
- `0x180005190`
- `0x180009460`
- `0x1800095f0`
- `0x18000a3e8`
- `0x180010f00`
- `0x18001c380`
- `0x1800219ec`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x18000a15c`
- `ntdll!NtDeviceIoControlFile` at `0x18000a15c`

## pseudocode

```c
NTSTATUS __stdcall LsaRemoveProtectedProcessAddress(PVOID BufferAddress, ULONG BufferSize)
{
  PVOID v3; // [rsp+50h] [rbp-28h] BYREF
  ULONG v4; // [rsp+58h] [rbp-20h]
  int v5; // [rsp+5Ch] [rbp-1Ch]
  struct _IO_STATUS_BLOCK v6; // [rsp+60h] [rbp-18h] BYREF

  v5 = 0;
  v3 = BufferAddress;
  v4 = BufferSize;
  v6 = 0;
  return NtDeviceIoControlFile(KsecddHandle, 0, 0, 0, &v6, 0x390060u, &v3, 0x10u, 0, 0);
}

```

## disassembly

```asm
0x18000a108  mov     r11, rsp
0x18000a10b  sub     rsp, 78h
0x18000a10f  xor     eax, eax
0x18000a111  xorps   xmm0, xmm0
0x18000a114  mov     [rsp+78h+OutputBufferLength], eax; OutputBufferLength
0x18000a118  xor     r9d, r9d; ApcContext
0x18000a11b  mov     [r11-38h], rax
0x18000a11f  xor     r8d, r8d; ApcRoutine
0x18000a122  mov     [rsp+78h+var_1C], eax
0x18000a126  lea     rax, [r11-28h]
0x18000a12a  mov     [rsp+78h+InputBufferLength], 10h; InputBufferLength
0x18000a132  mov     [r11-48h], rax
0x18000a136  lea     rax, [r11-18h]
0x18000a13a  mov     [r11-28h], rcx
0x18000a13e  mov     rcx, cs:KsecddHandle; FileHandle
0x18000a145  mov     [rsp+78h+var_20], edx
0x18000a149  xor     edx, edx; Event
0x18000a14b  mov     [rsp+78h+IoControlCode], 390060h; IoControlCode
0x18000a153  mov     [r11-58h], rax
0x18000a157  movups  xmmword ptr [rsp+78h+var_18], xmm0
0x18000a15c  call    cs:__imp_NtDeviceIoControlFile
0x18000a162  add     rsp, 78h
0x18000a166  retn
```
