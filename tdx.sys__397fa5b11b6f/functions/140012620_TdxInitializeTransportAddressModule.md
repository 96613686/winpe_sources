# TdxInitializeTransportAddressModule

- ea: `0x140012620`
- end: `0x1400126de`
- name: `TdxInitializeTransportAddressModule`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140014184`

## callees

- `0x1400119d0`
- `0x140018900`

## import_xrefs

- `ntoskrnl!ExCreateCallback` at `0x1400126b7`
- `ntoskrnl!ExCreateCallback` at `0x1400126b7`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001265d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001265d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012674`
- `ntoskrnl!RtlInitUnicodeString` at `0x140012674`

## pseudocode

```c
__int64 TdxInitializeTransportAddressModule()
{
  unsigned int v0; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  memset(TdxAcceptIrpHashTable, 0, sizeof(TdxAcceptIrpHashTable));
  KeInitializeSpinLock(&TdxAcceptIrpHashTableLock);
  RtlInitUnicodeString(&DestinationString, L"\\Callback\\AfdTdxCallback");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 592;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ExCreateCallback((PCALLBACK_OBJECT *)&TdxAfdCallbackObject, &ObjectAttributes, 1u, 0);
  TdxPrematureConnectIndDisabled = TdxIsPrematureConnectIndDisabled();
  return v0;
}

```

## disassembly

```asm
0x140012620  mov     [rsp-8+arg_0], rbx
0x140012625  push    rbp
0x140012626  mov     rbp, rsp
0x140012629  sub     rsp, 60h
0x14001262d  xorps   xmm0, xmm0
0x140012630  lea     rcx, TdxAcceptIrpHashTable; void *
0x140012637  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14001263b  xor     eax, eax
0x14001263d  xor     edx, edx; Val
0x14001263f  mov     r8d, 800h; Size
0x140012645  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140012649  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14001264d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140012651  call    memset
0x140012656  lea     rcx, TdxAcceptIrpHashTableLock; SpinLock
0x14001265d  call    cs:__imp_KeInitializeSpinLock
0x140012664  nop     dword ptr [rax+rax+00h]
0x140012669  lea     rdx, aCallbackAfdtdx; "\\Callback\\AfdTdxCallback"
0x140012670  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012674  call    cs:__imp_RtlInitUnicodeString
0x14001267b  nop     dword ptr [rax+rax+00h]
0x140012680  lea     rax, [rbp+DestinationString]
0x140012684  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001268b  xorps   xmm0, xmm0
0x14001268e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140012692  xor     r9d, r9d; AllowMultipleCallbacks
0x140012695  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14001269d  mov     r8b, 1; Create
0x1400126a0  mov     [rbp+ObjectAttributes.Attributes], 250h
0x1400126a7  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1400126ab  lea     rcx, TdxAfdCallbackObject; CallbackObject
0x1400126b2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400126b7  call    cs:__imp_ExCreateCallback
0x1400126be  nop     dword ptr [rax+rax+00h]
0x1400126c3  mov     ebx, eax
0x1400126c5  call    TdxIsPrematureConnectIndDisabled
0x1400126ca  mov     cs:TdxPrematureConnectIndDisabled, al
0x1400126d0  mov     eax, ebx
0x1400126d2  mov     rbx, [rsp+60h+arg_0]
0x1400126d7  add     rsp, 60h
0x1400126db  pop     rbp
0x1400126dc  retn
```
