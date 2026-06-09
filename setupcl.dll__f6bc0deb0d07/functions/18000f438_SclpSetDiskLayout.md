# SclpSetDiskLayout

- ea: `0x18000f438`
- end: `0x18000f4dd`
- name: `SclpSetDiskLayout`
- size: `165`
- prototype: `__int64 __fastcall(__int64, void *, void *, ULONG)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f22c`

## callees

- `0x18000a524`
- `0x18000f438`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x18000f485`
- `ntdll!NtDeviceIoControlFile` at `0x18000f485`

## string_xrefs

- `0x18000f493`: `Successfully updated layout`

## pseudocode

```c
__int64 __fastcall SclpSetDiskLayout(__int64 a1, void *a2, void *a3, ULONG a4)
{
  NTSTATUS v5; // ebx
  __int64 v6; // rcx
  struct _IO_STATUS_BLOCK v8; // [rsp+50h] [rbp-18h] BYREF

  v8 = 0;
  v5 = NtDeviceIoControlFile(a2, 0, 0, 0, &v8, 0x7C054u, a3, a4, 0, 0);
  if ( v5 >= 0 )
  {
    v6 = a1 + 1152;
    if ( !a1 )
      v6 = 0;
    SclLogGenericMessage(
      v6,
      1,
      (int)SclEvent_Generic_Info,
      437,
      (__int64)"SclpSetDiskLayout",
      "Successfully updated layout");
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f438  mov     r11, rsp
0x18000f43b  mov     [r11+8], rbx
0x18000f43f  push    rdi
0x18000f440  sub     rsp, 60h
0x18000f444  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x18000f44c  mov     rdi, rcx
0x18000f44f  mov     qword ptr [r11-28h], 0
0x18000f457  lea     rcx, [r11-18h]
0x18000f45b  mov     [r11-30h], r9d
0x18000f45f  mov     rax, rdx
0x18000f462  mov     [r11-38h], r8
0x18000f466  xorps   xmm0, xmm0
0x18000f469  mov     [rsp+68h+IoControlCode], 7C054h; IoControlCode
0x18000f471  xor     r9d, r9d; ApcContext
0x18000f474  mov     [r11-48h], rcx
0x18000f478  xor     r8d, r8d; ApcRoutine
0x18000f47b  mov     rcx, rax; FileHandle
0x18000f47e  xor     edx, edx; Event
0x18000f480  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x18000f485  call    cs:__imp_NtDeviceIoControlFile
0x18000f48b  mov     ebx, eax
0x18000f48d  test    eax, eax
0x18000f48f  js      short loc_18000F4D0
0x18000f491  xor     edx, edx
0x18000f493  lea     rax, aSuccessfullyUp; "Successfully updated layout"
0x18000f49a  mov     qword ptr [rsp+68h+IoControlCode], rax
0x18000f49f  lea     rcx, [rdi+480h]
0x18000f4a6  test    rdi, rdi
0x18000f4a9  lea     rax, aSclpsetdisklay; "SclpSetDiskLayout"
0x18000f4b0  mov     r9d, 1B5h
0x18000f4b6  mov     [rsp+68h+var_48], rax
0x18000f4bb  cmovz   rcx, rdx
0x18000f4bf  lea     r8, SclEvent_Generic_Info
0x18000f4c6  mov     edx, 1
0x18000f4cb  call    SclLogGenericMessage
0x18000f4d0  mov     eax, ebx
0x18000f4d2  mov     rbx, [rsp+68h+arg_0]
0x18000f4d7  add     rsp, 60h
0x18000f4db  pop     rdi
0x18000f4dc  retn
```
