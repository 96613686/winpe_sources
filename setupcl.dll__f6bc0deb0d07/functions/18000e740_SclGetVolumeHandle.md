# SclGetVolumeHandle

- ea: `0x18000e740`
- end: `0x18000e82e`
- name: `SclGetVolumeHandle`
- size: `238`
- prototype: `__int64 __fastcall(const WCHAR *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800108d0`
- `0x18001188c`

## callees

- `0x180001c74`
- `0x18000a524`
- `0x18000e740`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000e7c3`
- `ntdll!NtOpenFile` at `0x18000e7c3`

## string_xrefs

- `0x18000e7e5`: `(%lx): Failed NtOpenFile on [%ws]`

## pseudocode

```c
__int64 __fastcall SclGetVolumeHandle(const WCHAR *a1, void **a2)
{
  NTSTATUS v3; // edi
  struct _UNICODE_STRING v5; // [rsp+40h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-38h] BYREF

  v5 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !a1 || !a2 )
    return 3221225485LL;
  INIT_OBJA_EX((__int64)&ObjectAttributes, &v5, a1, 64, 0);
  v3 = NtOpenFile(a2, 0x100003u, &ObjectAttributes, &IoStatusBlock, 3u, 0x10u);
  if ( v3 < 0 )
  {
    SclLogGenericMessage(0, 3, (unsigned int)SclEvent_Generic_Error, 498, (__int64)"SclGetVolumeHandle");
    *a2 = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e740  mov     r11, rsp
0x18000e743  mov     [r11+8], rbx
0x18000e747  mov     [r11+10h], rsi
0x18000e74b  push    rdi
0x18000e74c  sub     rsp, 90h
0x18000e753  xorps   xmm0, xmm0
0x18000e756  xor     eax, eax
0x18000e758  mov     rbx, rdx
0x18000e75b  mov     rsi, rcx
0x18000e75e  movups  xmmword ptr [rsp+98h+ObjectAttributes.ObjectName], xmm0
0x18000e763  movups  xmmword ptr [rsp+98h+ObjectAttributes+1Ch], xmm0
0x18000e768  movups  [rsp+98h+var_58], xmm0
0x18000e76d  movups  xmmword ptr [rsp+98h+ObjectAttributes.Length], xmm0
0x18000e772  movups  xmmword ptr [rsp+98h+IoStatusBlock], xmm0
0x18000e777  test    rcx, rcx
0x18000e77a  jz      loc_18000E814
0x18000e780  test    rdx, rdx
0x18000e783  jz      loc_18000E814
0x18000e789  mov     r8, rcx
0x18000e78c  mov     [r11-78h], rax
0x18000e790  lea     rcx, [r11-38h]
0x18000e794  lea     r9d, [rax+40h]
0x18000e798  lea     rdx, [r11-58h]
0x18000e79c  call    INIT_OBJA_EX
0x18000e7a1  lea     r9, [rsp+98h+IoStatusBlock]; IoStatusBlock
0x18000e7a6  mov     [rsp+98h+OpenOptions], 10h; OpenOptions
0x18000e7ae  lea     r8, [rsp+98h+ObjectAttributes]; ObjectAttributes
0x18000e7b3  mov     [rsp+98h+ShareAccess], 3; ShareAccess
0x18000e7bb  mov     edx, 100003h; DesiredAccess
0x18000e7c0  mov     rcx, rbx; FileHandle
0x18000e7c3  call    cs:__imp_NtOpenFile
0x18000e7c9  mov     edi, eax
0x18000e7cb  test    eax, eax
0x18000e7cd  jns     short loc_18000E810
0x18000e7cf  mov     [rsp+98h+var_60], rsi
0x18000e7d4  lea     r8, SclEvent_Generic_Error
0x18000e7db  mov     [rsp+98h+var_68], eax
0x18000e7df  mov     r9d, 1F2h
0x18000e7e5  lea     rax, aLxFailedNtopen; "(%lx): Failed NtOpenFile on [%ws]"
0x18000e7ec  mov     edx, 3
0x18000e7f1  mov     qword ptr [rsp+98h+OpenOptions], rax
0x18000e7f6  xor     ecx, ecx
0x18000e7f8  lea     rax, aSclgetvolumeha; "SclGetVolumeHandle"
0x18000e7ff  mov     qword ptr [rsp+98h+ShareAccess], rax
0x18000e804  call    SclLogGenericMessage
0x18000e809  mov     qword ptr [rbx], 0
0x18000e810  mov     eax, edi
0x18000e812  jmp     short loc_18000E819
0x18000e814  mov     eax, 0C000000Dh
0x18000e819  lea     r11, [rsp+98h+var_8]
0x18000e821  mov     rbx, [r11+10h]
0x18000e825  mov     rsi, [r11+18h]
0x18000e829  mov     rsp, r11
0x18000e82c  pop     rdi
0x18000e82d  retn
```
