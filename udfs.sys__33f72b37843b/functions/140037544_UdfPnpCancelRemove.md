# UdfPnpCancelRemove

- ea: `0x140037544`
- end: `0x1400375d1`
- name: `UdfPnpCancelRemove`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400590b0`

## callees

- `0x1400030e0`
- `0x1400133ac`
- `0x14004ce50`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140037572`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003758c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037572`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003758c`
- `ntoskrnl!IofCallDriver` at `0x1400375aa`
- `ntoskrnl!IofCallDriver` at `0x1400375aa`

## pseudocode

```c
__int64 __fastcall UdfPnpCancelRemove(void *a1, IRP *a2, __int64 a3)
{
  struct _ERESOURCE *v3; // rbx
  __int64 v7; // rcx

  v3 = (struct _ERESOURCE *)(a3 + 1480);
  UdfAcquireResource(a1, a3 + 1480, 0, 0);
  ExReleaseResourceLite(&Resource);
  UdfUnlockVolumeInternal(v7, a3, 0);
  ExReleaseResourceLite(v3);
  ++a2->CurrentLocation;
  ++a2->Tail.Overlay.CurrentStackLocation;
  LODWORD(v3) = IofCallDriver(*(PDEVICE_OBJECT *)(a3 + 24), a2);
  UdfCompleteRequest(a1, 0, 0);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140037544  push    rbx
0x140037546  push    rbp
0x140037547  push    rsi
0x140037548  push    rdi
0x140037549  sub     rsp, 28h
0x14003754d  lea     rbx, [r8+5C8h]
0x140037554  mov     rsi, r8
0x140037557  mov     rdi, rdx
0x14003755a  xor     r9d, r9d
0x14003755d  mov     rdx, rbx
0x140037560  xor     r8d, r8d
0x140037563  mov     rbp, rcx
0x140037566  call    UdfAcquireResource
0x14003756b  lea     rcx, Resource; Resource
0x140037572  call    cs:__imp_ExReleaseResourceLite
0x140037579  nop     dword ptr [rax+rax+00h]
0x14003757e  xor     r8d, r8d
0x140037581  mov     rdx, rsi
0x140037584  call    UdfUnlockVolumeInternal
0x140037589  mov     rcx, rbx; Resource
0x14003758c  call    cs:__imp_ExReleaseResourceLite
0x140037593  nop     dword ptr [rax+rax+00h]
0x140037598  inc     byte ptr [rdi+43h]
0x14003759b  mov     rdx, rdi; Irp
0x14003759e  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x1400375a6  mov     rcx, [rsi+18h]; DeviceObject
0x1400375aa  call    cs:__imp_IofCallDriver
0x1400375b1  nop     dword ptr [rax+rax+00h]
0x1400375b6  xor     r8d, r8d
0x1400375b9  xor     edx, edx
0x1400375bb  mov     rcx, rbp
0x1400375be  mov     ebx, eax
0x1400375c0  call    UdfCompleteRequest
0x1400375c5  mov     eax, ebx
0x1400375c7  add     rsp, 28h
0x1400375cb  pop     rdi
0x1400375cc  pop     rsi
0x1400375cd  pop     rbp
0x1400375ce  pop     rbx
0x1400375cf  retn
```
