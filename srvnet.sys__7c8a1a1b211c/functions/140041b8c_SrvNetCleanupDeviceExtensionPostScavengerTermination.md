# SrvNetCleanupDeviceExtensionPostScavengerTermination

- ea: `0x140041b8c`
- end: `0x140041c3b`
- name: `SrvNetCleanupDeviceExtensionPostScavengerTermination`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140056be0`

## callees

- `0x140014104`
- `0x140043b14`
- `0x140048bfc`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140041bd0`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041bdf`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041bef`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041c02`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041c15`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041c28`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041bd0`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041bdf`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041bef`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041c02`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041c15`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041c28`

## pseudocode

```c
NTSTATUS SrvNetCleanupDeviceExtensionPostScavengerTermination()
{
  PERESOURCE v0; // rbx

  v0 = SrvNetDeviceExtension;
  SrvNetCleanupUniqueStringList(&SrvNetDeviceExtension[4].SystemResourcesList.Blink);
  SrvNetCleanupUniqueStringList(&v0[3].SpinLock);
  SrvNetCleanupCertsList(&v0[10].SystemResourcesList.Blink);
  SrvNetCleanupListenerRuleList(&v0[10].ActiveCount);
  ExDeleteResourceLite((PERESOURCE)((char *)v0 + 288));
  ExDeleteResourceLite(v0);
  ExDeleteResourceLite((PERESOURCE)((char *)v0 + 120));
  ExDeleteResourceLite((PERESOURCE)((char *)v0 + 528));
  ExDeleteResourceLite((PERESOURCE)((char *)v0 + 840));
  return ExDeleteResourceLite((PERESOURCE)((char *)v0 + 944));
}

```

## disassembly

```asm
0x140041b8c  push    rbx
0x140041b8e  sub     rsp, 20h
0x140041b92  mov     rbx, cs:SrvNetDeviceExtension
0x140041b99  lea     rcx, [rbx+1A8h]
0x140041ba0  call    SrvNetCleanupUniqueStringList
0x140041ba5  lea     rcx, [rbx+198h]
0x140041bac  call    SrvNetCleanupUniqueStringList
0x140041bb1  lea     rcx, [rbx+418h]
0x140041bb8  call    SrvNetCleanupCertsList
0x140041bbd  lea     rcx, [rbx+428h]
0x140041bc4  call    SrvNetCleanupListenerRuleList
0x140041bc9  lea     rcx, [rbx+120h]; Resource
0x140041bd0  call    cs:__imp_ExDeleteResourceLite
0x140041bd7  nop     dword ptr [rax+rax+00h]
0x140041bdc  mov     rcx, rbx; Resource
0x140041bdf  call    cs:__imp_ExDeleteResourceLite
0x140041be6  nop     dword ptr [rax+rax+00h]
0x140041beb  lea     rcx, [rbx+78h]; Resource
0x140041bef  call    cs:__imp_ExDeleteResourceLite
0x140041bf6  nop     dword ptr [rax+rax+00h]
0x140041bfb  lea     rcx, [rbx+210h]; Resource
0x140041c02  call    cs:__imp_ExDeleteResourceLite
0x140041c09  nop     dword ptr [rax+rax+00h]
0x140041c0e  lea     rcx, [rbx+348h]; Resource
0x140041c15  call    cs:__imp_ExDeleteResourceLite
0x140041c1c  nop     dword ptr [rax+rax+00h]
0x140041c21  lea     rcx, [rbx+3B0h]; Resource
0x140041c28  call    cs:__imp_ExDeleteResourceLite
0x140041c2f  nop     dword ptr [rax+rax+00h]
0x140041c34  add     rsp, 20h
0x140041c38  pop     rbx
0x140041c39  retn
```
