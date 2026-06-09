# VmpRemove(VM_VOLUME_EXTENSION *)

- ea: `0x14000443c`
- end: `0x140004497`
- name: `?VmpRemove@@YAXPEAVVM_VOLUME_EXTENSION@@@Z`
- size: `91`
- prototype: `void __fastcall(struct VM_VOLUME_EXTENSION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140016aa0`

## callees

- `0x1400033a0`
- `0x14000443c`
- `0x140015238`

## import_xrefs

- `ntoskrnl!IoSetDevicePropertyData` at `0x140004474`
- `ntoskrnl!IoSetDevicePropertyData` at `0x140004474`

## pseudocode

```c
void __fastcall VmpRemove(struct VM_VOLUME_EXTENSION *a1)
{
  if ( *((_BYTE *)a1 + 156) )
  {
    *((_BYTE *)a1 + 156) = 0;
    IoSetDevicePropertyData(*(PDEVICE_OBJECT *)a1, &DEVPKEY_Device_SessionId, 0, 0, 0, 0, 0);
    VmpDeregisterDevice(*(_QWORD *)a1);
    VmpReleaseInterfaces(a1);
  }
}

```

## disassembly

```asm
0x14000443c  push    rbx
0x14000443e  sub     rsp, 40h
0x140004442  mov     al, [rcx+9Ch]
0x140004448  mov     rbx, rcx
0x14000444b  xor     ecx, ecx
0x14000444d  test    al, al
0x14000444f  jz      short loc_140004490
0x140004451  mov     [rsp+48h+Data], rcx; Data
0x140004456  lea     rdx, DEVPKEY_Device_SessionId; PropertyKey
0x14000445d  mov     [rsp+48h+Size], ecx; Size
0x140004461  xor     r9d, r9d; Flags
0x140004464  mov     [rsp+48h+Type], ecx; Type
0x140004468  xor     r8d, r8d; Lcid
0x14000446b  mov     [rbx+9Ch], cl
0x140004471  mov     rcx, [rbx]; Pdo
0x140004474  call    cs:__imp_IoSetDevicePropertyData
0x14000447b  nop     dword ptr [rax+rax+00h]
0x140004480  mov     rcx, [rbx]
0x140004483  call    VmpDeregisterDevice
0x140004488  mov     rcx, rbx
0x14000448b  call    VmpReleaseInterfaces
0x140004490  add     rsp, 40h
0x140004494  pop     rbx
0x140004495  retn
```
