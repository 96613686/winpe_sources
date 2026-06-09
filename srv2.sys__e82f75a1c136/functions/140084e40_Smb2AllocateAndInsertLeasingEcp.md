# Smb2AllocateAndInsertLeasingEcp

- ea: `0x140084e40`
- end: `0x140084f1b`
- name: `Smb2AllocateAndInsertLeasingEcp`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14007a84c`

## callees

- `0x140084e40`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140084f02`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140084f02`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140084edd`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140084edd`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140084e81`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140084e81`

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
0x140084e40  mov     [rsp+arg_8], rbx
0x140084e45  push    rdi
0x140084e46  sub     rsp, 30h
0x140084e4a  mov     rbx, [rcx+230h]
0x140084e51  lea     rax, [rsp+38h+arg_0]
0x140084e56  mov     rdi, rdx
0x140084e59  mov     [rsp+38h+EcpContext], rax; EcpContext
0x140084e5e  xor     r9d, r9d; CleanupCallback
0x140084e61  mov     [rsp+38h+PoolTag], 5324534Ch; PoolTag
0x140084e69  xor     r8d, r8d; Flags
0x140084e6c  mov     [rsp+38h+arg_0], 0
0x140084e75  mov     edx, 24h ; '$'; SizeOfContext
0x140084e7a  lea     rcx, GUID_ECP_DUAL_OPLOCK_KEY; EcpType
0x140084e81  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x140084e88  nop     dword ptr [rax+rax+00h]
0x140084e8d  test    eax, eax
0x140084e8f  js      short loc_140084EF1
0x140084e91  mov     rax, [rbx+68h]
0x140084e95  mov     rcx, [rsp+38h+arg_0]
0x140084e9a  movups  xmm0, xmmword ptr [rax+50h]
0x140084e9e  movups  xmmword ptr [rcx+10h], xmm0
0x140084ea2  mov     rax, [rsp+38h+arg_0]
0x140084ea7  mov     byte ptr [rax+21h], 1
0x140084eab  mov     rax, [rsp+38h+arg_0]
0x140084eb0  mov     byte ptr [rax+20h], 0
0x140084eb4  cmp     byte ptr [rbx+12Dh], 0
0x140084ebb  jz      short loc_140084ED5
0x140084ebd  mov     rax, [rsp+38h+arg_0]
0x140084ec2  movups  xmm0, xmmword ptr [rbx+118h]
0x140084ec9  movups  xmmword ptr [rax], xmm0
0x140084ecc  mov     rax, [rsp+38h+arg_0]
0x140084ed1  mov     byte ptr [rax+20h], 1
0x140084ed5  mov     rdx, [rsp+38h+arg_0]; EcpContext
0x140084eda  mov     rcx, rdi; EcpList
0x140084edd  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x140084ee4  nop     dword ptr [rax+rax+00h]
0x140084ee9  mov     ebx, eax
0x140084eeb  test    eax, eax
0x140084eed  js      short loc_140084EFD
0x140084eef  xor     eax, eax
0x140084ef1  mov     rbx, [rsp+38h+arg_8]
0x140084ef6  add     rsp, 30h
0x140084efa  pop     rdi
0x140084efb  retn
0x140084efd  mov     rcx, [rsp+38h+arg_0]; EcpContext
0x140084f02  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x140084f09  nop     dword ptr [rax+rax+00h]
0x140084f0e  xor     eax, eax
0x140084f10  cmp     ebx, 0C000000Dh
0x140084f16  cmovnz  eax, ebx
0x140084f19  jmp     short loc_140084EF1
```
