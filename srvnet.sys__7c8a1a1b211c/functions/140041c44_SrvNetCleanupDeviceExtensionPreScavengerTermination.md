# SrvNetCleanupDeviceExtensionPreScavengerTermination

- ea: `0x140041c44`
- end: `0x140041d1b`
- name: `SrvNetCleanupDeviceExtensionPreScavengerTermination`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140056be0`

## callees

- `0x14000b480`
- `0x14000ec20`
- `0x1400105e0`
- `0x140041ae0`
- `0x140041c44`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140041c81`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140041c81`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140041cac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140041cd9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140041cac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140041cd9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140041c70`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140041c70`
- `ntoskrnl!KeDelayExecutionThread` at `0x140041cfe`
- `ntoskrnl!KeDelayExecutionThread` at `0x140041cfe`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041ca0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041ccd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041ca0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041ccd`

## pseudocode

```c
NTSTATUS SrvNetCleanupDeviceExtensionPreScavengerTermination()
{
  PERESOURCE v0; // rbx
  struct _ERESOURCE *v1; // rdi
  __int64 **p_Reserved2; // r14
  __int64 *v3; // rsi
  NTSTATUS result; // eax
  union _LARGE_INTEGER Interval; // [rsp+50h] [rbp+8h] BYREF

  v0 = SrvNetDeviceExtension;
  Interval.QuadPart = 0;
  v1 = (PERESOURCE)((char *)SrvNetDeviceExtension + 288);
  p_Reserved2 = (__int64 **)&SrvNetDeviceExtension[3].Reserved2;
  while ( 1 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(v1, 1u);
    v3 = *p_Reserved2;
    if ( *p_Reserved2 == (__int64 *)p_Reserved2 )
      break;
    SrvNetReferenceEndpoint(*p_Reserved2);
    ExReleaseResourceLite(v1);
    KeLeaveCriticalRegion();
    SrvNetCloseEndpoint(v3);
    SrvNetDereferenceEndpoint(v3);
  }
  ExReleaseResourceLite(v1);
  KeLeaveCriticalRegion();
  result = SrvNetCleanupClientList();
  while ( LODWORD(v0[1].SystemResourcesList.Blink) )
  {
    Interval.QuadPart = -2000000;
    result = KeDelayExecutionThread(0, 1u, &Interval);
  }
  return result;
}

```

## disassembly

```asm
0x140041c44  mov     qword ptr [rsp+Interval], rcx
0x140041c49  push    rbx
0x140041c4a  push    rsi
0x140041c4b  push    rdi
0x140041c4c  push    r14
0x140041c4e  sub     rsp, 28h
0x140041c52  mov     rbx, cs:SrvNetDeviceExtension
0x140041c59  mov     qword ptr [rsp+48h+Interval], 0
0x140041c62  lea     rdi, [rbx+120h]
0x140041c69  lea     r14, [rbx+188h]
0x140041c70  call    cs:__imp_KeEnterCriticalRegion
0x140041c77  nop     dword ptr [rax+rax+00h]
0x140041c7c  mov     dl, 1; Wait
0x140041c7e  mov     rcx, rdi; Resource
0x140041c81  call    cs:__imp_ExAcquireResourceSharedLite
0x140041c88  nop     dword ptr [rax+rax+00h]
0x140041c8d  mov     rsi, [r14]
0x140041c90  cmp     rsi, r14
0x140041c93  jz      short loc_140041CCA
0x140041c95  mov     rcx, rsi
0x140041c98  call    SrvNetReferenceEndpoint
0x140041c9d  mov     rcx, rdi; Resource
0x140041ca0  call    cs:__imp_ExReleaseResourceLite
0x140041ca7  nop     dword ptr [rax+rax+00h]
0x140041cac  call    cs:__imp_KeLeaveCriticalRegion
0x140041cb3  nop     dword ptr [rax+rax+00h]
0x140041cb8  mov     rcx, rsi
0x140041cbb  call    SrvNetCloseEndpoint
0x140041cc0  mov     rcx, rsi
0x140041cc3  call    SrvNetDereferenceEndpoint
0x140041cc8  jmp     short loc_140041C70
0x140041cca  mov     rcx, rdi; Resource
0x140041ccd  call    cs:__imp_ExReleaseResourceLite
0x140041cd4  nop     dword ptr [rax+rax+00h]
0x140041cd9  call    cs:__imp_KeLeaveCriticalRegion
0x140041ce0  nop     dword ptr [rax+rax+00h]
0x140041ce5  call    SrvNetCleanupClientList
0x140041cea  jmp     short loc_140041D0A
0x140041cec  lea     r8, [rsp+48h+Interval]; Interval
0x140041cf1  mov     qword ptr [rsp+48h+Interval], 0FFFFFFFFFFE17B80h
0x140041cfa  mov     dl, 1; Alertable
0x140041cfc  xor     ecx, ecx; WaitMode
0x140041cfe  call    cs:__imp_KeDelayExecutionThread
0x140041d05  nop     dword ptr [rax+rax+00h]
0x140041d0a  cmp     dword ptr [rbx+70h], 0
0x140041d0e  jnz     short loc_140041CEC
0x140041d10  add     rsp, 28h
0x140041d14  pop     r14
0x140041d16  pop     rdi
0x140041d17  pop     rsi
0x140041d18  pop     rbx
0x140041d19  retn
```
