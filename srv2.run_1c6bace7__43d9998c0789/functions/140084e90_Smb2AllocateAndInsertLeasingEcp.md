# Smb2AllocateAndInsertLeasingEcp

- ea: `0x140084e90`
- end: `0x140084f6b`
- name: `Smb2AllocateAndInsertLeasingEcp`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14007a89c`

## callees

- `0x140084e90`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140084f52`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140084f52`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140084f2d`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140084f2d`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140084ed1`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140084ed1`

## pseudocode

```c
NTSTATUS __fastcall Smb2AllocateAndInsertLeasingEcp(__int64 a1, struct _ECP_LIST *a2)
{
  __int64 v2; // rbx
  NTSTATUS result; // eax
  NTSTATUS Parameter; // ebx
  PVOID EcpContext; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 560);
  EcpContext = 0;
  result = FsRtlAllocateExtraCreateParameter(&GUID_ECP_DUAL_OPLOCK_KEY, 0x24u, 0, 0, 0x5324534Cu, &EcpContext);
  if ( result >= 0 )
  {
    *((_OWORD *)EcpContext + 1) = *(_OWORD *)(*(_QWORD *)(v2 + 104) + 80LL);
    *((_BYTE *)EcpContext + 33) = 1;
    *((_BYTE *)EcpContext + 32) = 0;
    if ( *(_BYTE *)(v2 + 301) )
    {
      *(_OWORD *)EcpContext = *(_OWORD *)(v2 + 280);
      *((_BYTE *)EcpContext + 32) = 1;
    }
    Parameter = FsRtlInsertExtraCreateParameter(a2, EcpContext);
    if ( Parameter < 0 )
    {
      FsRtlFreeExtraCreateParameter(EcpContext);
      result = 0;
      if ( Parameter != -1073741811 )
        return Parameter;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140084e90  mov     [rsp+arg_8], rbx
0x140084e95  push    rdi
0x140084e96  sub     rsp, 30h
0x140084e9a  mov     rbx, [rcx+230h]
0x140084ea1  lea     rax, [rsp+38h+arg_0]
0x140084ea6  mov     rdi, rdx
0x140084ea9  mov     [rsp+38h+EcpContext], rax; EcpContext
0x140084eae  xor     r9d, r9d; CleanupCallback
0x140084eb1  mov     [rsp+38h+PoolTag], 5324534Ch; PoolTag
0x140084eb9  xor     r8d, r8d; Flags
0x140084ebc  mov     [rsp+38h+arg_0], 0
0x140084ec5  mov     edx, 24h ; '$'; SizeOfContext
0x140084eca  lea     rcx, GUID_ECP_DUAL_OPLOCK_KEY; EcpType
0x140084ed1  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x140084ed8  nop     dword ptr [rax+rax+00h]
0x140084edd  test    eax, eax
0x140084edf  js      short loc_140084F41
0x140084ee1  mov     rax, [rbx+68h]
0x140084ee5  mov     rcx, [rsp+38h+arg_0]
0x140084eea  movups  xmm0, xmmword ptr [rax+50h]
0x140084eee  movups  xmmword ptr [rcx+10h], xmm0
0x140084ef2  mov     rax, [rsp+38h+arg_0]
0x140084ef7  mov     byte ptr [rax+21h], 1
0x140084efb  mov     rax, [rsp+38h+arg_0]
0x140084f00  mov     byte ptr [rax+20h], 0
0x140084f04  cmp     byte ptr [rbx+12Dh], 0
0x140084f0b  jz      short loc_140084F25
0x140084f0d  mov     rax, [rsp+38h+arg_0]
0x140084f12  movups  xmm0, xmmword ptr [rbx+118h]
0x140084f19  movups  xmmword ptr [rax], xmm0
0x140084f1c  mov     rax, [rsp+38h+arg_0]
0x140084f21  mov     byte ptr [rax+20h], 1
0x140084f25  mov     rdx, [rsp+38h+arg_0]; EcpContext
0x140084f2a  mov     rcx, rdi; EcpList
0x140084f2d  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x140084f34  nop     dword ptr [rax+rax+00h]
0x140084f39  mov     ebx, eax
0x140084f3b  test    eax, eax
0x140084f3d  js      short loc_140084F4D
0x140084f3f  xor     eax, eax
0x140084f41  mov     rbx, [rsp+38h+arg_8]
0x140084f46  add     rsp, 30h
0x140084f4a  pop     rdi
0x140084f4b  retn
0x140084f4d  mov     rcx, [rsp+38h+arg_0]; EcpContext
0x140084f52  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x140084f59  nop     dword ptr [rax+rax+00h]
0x140084f5e  xor     eax, eax
0x140084f60  cmp     ebx, 0C000000Dh
0x140084f66  cmovnz  eax, ebx
0x140084f69  jmp     short loc_140084F41
```
