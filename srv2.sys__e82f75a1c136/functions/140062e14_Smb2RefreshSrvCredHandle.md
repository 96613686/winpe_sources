# Smb2RefreshSrvCredHandle

- ea: `0x140062e14`
- end: `0x140062ef5`
- name: `Smb2RefreshSrvCredHandle`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14007667c`

## callees

- `0x140062e14`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140062e6f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140062e6f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140062e57`
- `ntoskrnl!ExReleaseResourceLite` at `0x140062ee0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140062e57`
- `ntoskrnl!ExReleaseResourceLite` at `0x140062ee0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140062e34`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140062ea2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140062e34`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140062ea2`
- `srvnet!SrvLibCreateCredentialHandle` at `0x140062e87`
- `srvnet!SrvLibCreateCredentialHandle` at `0x140062e87`
- `srvnet!SrvLibCloseCredentialHandle` at `0x140062eba`
- `srvnet!SrvLibCloseCredentialHandle` at `0x140062eba`

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
0x140062e14  push    rbx
0x140062e16  sub     rsp, 30h
0x140062e1a  xorps   xmm0, xmm0
0x140062e1d  mov     [rsp+38h+arg_0], 0
0x140062e26  mov     dl, 1; Wait
0x140062e28  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x140062e2f  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140062e34  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140062e3b  nop     dword ptr [rax+rax+00h]
0x140062e40  cmp     cs:Smb2CredHandleRefreshed, 0
0x140062e47  jz      short loc_140062E50
0x140062e49  xor     ebx, ebx
0x140062e4b  jmp     loc_140062ED9
0x140062e50  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x140062e57  call    cs:__imp_ExReleaseResourceLite
0x140062e5e  nop     dword ptr [rax+rax+00h]
0x140062e63  lea     rdx, aNegotiate; "Negotiate"
0x140062e6a  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x140062e6f  call    cs:__imp_RtlInitUnicodeString
0x140062e76  nop     dword ptr [rax+rax+00h]
0x140062e7b  lea     r8, [rsp+38h+arg_0]
0x140062e80  xor     edx, edx
0x140062e82  lea     rcx, [rsp+38h+DestinationString]
0x140062e87  call    cs:__imp_SrvLibCreateCredentialHandle
0x140062e8e  nop     dword ptr [rax+rax+00h]
0x140062e93  mov     ebx, eax
0x140062e95  test    eax, eax
0x140062e97  js      short loc_140062EEE
0x140062e99  mov     dl, 1; Wait
0x140062e9b  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x140062ea2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140062ea9  nop     dword ptr [rax+rax+00h]
0x140062eae  mov     rcx, cs:Smb2ExtensibleCredentialHandle
0x140062eb5  test    rcx, rcx
0x140062eb8  jz      short loc_140062EC6
0x140062eba  call    cs:__imp_SrvLibCloseCredentialHandle
0x140062ec1  nop     dword ptr [rax+rax+00h]
0x140062ec6  mov     rax, [rsp+38h+arg_0]
0x140062ecb  mov     cs:Smb2ExtensibleCredentialHandle, rax
0x140062ed2  mov     cs:Smb2CredHandleRefreshed, 1
0x140062ed9  lea     rcx, Smb2ExtensibleCredHandleLock; Resource
0x140062ee0  call    cs:__imp_ExReleaseResourceLite
0x140062ee7  nop     dword ptr [rax+rax+00h]
0x140062eec  mov     eax, ebx
0x140062eee  add     rsp, 30h
0x140062ef2  pop     rbx
0x140062ef3  retn
```
