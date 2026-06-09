# Smb2RefreshSrvCredHandle

- ea: `0x140062dc4`
- end: `0x140062ea5`
- name: `Smb2RefreshSrvCredHandle`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14007667c`

## callees

- `0x140062dc4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140062e1f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140062e1f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140062e07`
- `ntoskrnl!ExReleaseResourceLite` at `0x140062e90`
- `ntoskrnl!ExReleaseResourceLite` at `0x140062e07`
- `ntoskrnl!ExReleaseResourceLite` at `0x140062e90`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140062de4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140062e52`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140062de4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140062e52`
- `srvnet!SrvLibCreateCredentialHandle` at `0x140062e37`
- `srvnet!SrvLibCreateCredentialHandle` at `0x140062e37`
- `srvnet!SrvLibCloseCredentialHandle` at `0x140062e6a`
- `srvnet!SrvLibCloseCredentialHandle` at `0x140062e6a`

## pseudocode

```c
__int64 Smb2RefreshSrvCredHandle()
{
  unsigned int v0; // ebx
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  __int64 v3; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0;
  DestinationString = 0;
  ExAcquireResourceExclusiveLite(&Smb2ExtensibleCredHandleLock, 1u);
  if ( Smb2CredHandleRefreshed )
  {
    v0 = 0;
  }
  else
  {
    ExReleaseResourceLite(&Smb2ExtensibleCredHandleLock);
    RtlInitUnicodeString(&DestinationString, L"Negotiate");
    result = SrvLibCreateCredentialHandle(&DestinationString, 0, &v3);
    v0 = result;
    if ( (int)result < 0 )
      return result;
    ExAcquireResourceExclusiveLite(&Smb2ExtensibleCredHandleLock, 1u);
    if ( Smb2ExtensibleCredentialHandle )
      SrvLibCloseCredentialHandle(Smb2ExtensibleCredentialHandle);
    Smb2ExtensibleCredentialHandle = v3;
    Smb2CredHandleRefreshed = 1;
  }
  ExReleaseResourceLite(&Smb2ExtensibleCredHandleLock);
  return v0;
}

```

## disassembly

```asm
0x140062dc4  push    rbx
0x140062dc6  sub     rsp, 30h
0x140062dca  xorps   xmm0, xmm0
0x140062dcd  mov     [rsp+38h+arg_0], 0
0x140062dd6  mov     dl, 1; Wait
0x140062dd8  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x140062ddf  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140062de4  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140062deb  nop     dword ptr [rax+rax+00h]
0x140062df0  cmp     cs:Smb2CredHandleRefreshed, 0
0x140062df7  jz      short loc_140062E00
0x140062df9  xor     ebx, ebx
0x140062dfb  jmp     loc_140062E89
0x140062e00  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x140062e07  call    cs:__imp_ExReleaseResourceLite
0x140062e0e  nop     dword ptr [rax+rax+00h]
0x140062e13  lea     rdx, aNegotiate; "Negotiate"
0x140062e1a  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140062e1f  call    cs:__imp_RtlInitUnicodeString
0x140062e26  nop     dword ptr [rax+rax+00h]
0x140062e2b  lea     r8, [rsp+38h+arg_0]
0x140062e30  xor     edx, edx
0x140062e32  lea     rcx, [rsp+38h+DestinationString]
0x140062e37  call    cs:__imp_SrvLibCreateCredentialHandle
0x140062e3e  nop     dword ptr [rax+rax+00h]
0x140062e43  mov     ebx, eax
0x140062e45  test    eax, eax
0x140062e47  js      short loc_140062E9E
0x140062e49  mov     dl, 1; Wait
0x140062e4b  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x140062e52  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140062e59  nop     dword ptr [rax+rax+00h]
0x140062e5e  mov     rcx, cs:Smb2ExtensibleCredentialHandle
0x140062e65  test    rcx, rcx
0x140062e68  jz      short loc_140062E76
0x140062e6a  call    cs:__imp_SrvLibCloseCredentialHandle
0x140062e71  nop     dword ptr [rax+rax+00h]
0x140062e76  mov     rax, [rsp+38h+arg_0]
0x140062e7b  mov     cs:Smb2ExtensibleCredentialHandle, rax
0x140062e82  mov     cs:Smb2CredHandleRefreshed, 1
0x140062e89  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x140062e90  call    cs:__imp_ExReleaseResourceLite
0x140062e97  nop     dword ptr [rax+rax+00h]
0x140062e9c  mov     eax, ebx
0x140062e9e  add     rsp, 30h
0x140062ea2  pop     rbx
0x140062ea3  retn
```
