# UdfSeqCacheRaiseHardError

- ea: `0x14003bdf8`
- end: `0x14003be83`
- name: `UdfSeqCacheRaiseHardError`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006680`
- `0x14000cce0`

## callees

- `0x14003bdf8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003be6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003be6b`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14003be16`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x14003be16`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x14003be54`
- `ntoskrnl!IoRaiseInformationalHardError` at `0x14003be54`

## pseudocode

```c
void __fastcall UdfSeqCacheRaiseHardError(__int64 a1)
{
  void *v2; // rcx
  char v3; // bl
  __int64 v4; // rcx
  struct _UNICODE_STRING DosName; // [rsp+20h] [rbp-18h] BYREF

  v2 = *(void **)(a1 + 24);
  DosName = 0;
  if ( IoVolumeDeviceToDosName(v2, &DosName) < 0 )
  {
    v4 = *(_QWORD *)(a1 + 8);
    v3 = 0;
    DosName.MaximumLength = *(_WORD *)(v4 + 6);
    DosName.Length = DosName.MaximumLength;
    DosName.Buffer = (PWSTR)(v4 + 32);
  }
  else
  {
    v3 = 1;
  }
  IoRaiseInformationalHardError(-1073741278, &DosName, 0);
  if ( v3 )
    ExFreePoolWithTag(DosName.Buffer, 0);
}

```

## disassembly

```asm
0x14003bdf8  mov     [rsp+arg_0], rbx
0x14003bdfd  push    rdi
0x14003bdfe  sub     rsp, 30h
0x14003be02  mov     rdi, rcx
0x14003be05  lea     rdx, [rsp+38h+DosName]; DosName
0x14003be0a  mov     rcx, [rcx+18h]; VolumeDeviceObject
0x14003be0e  xorps   xmm0, xmm0
0x14003be11  movups  xmmword ptr [rsp+38h+DosName.Length], xmm0
0x14003be16  call    cs:__imp_IoVolumeDeviceToDosName
0x14003be1d  nop     dword ptr [rax+rax+00h]
0x14003be22  test    eax, eax
0x14003be24  js      short loc_14003BE2A
0x14003be26  mov     bl, 1
0x14003be28  jmp     short loc_14003BE47
0x14003be2a  mov     rcx, [rdi+8]
0x14003be2e  xor     bl, bl
0x14003be30  movzx   eax, word ptr [rcx+6]
0x14003be34  mov     [rsp+38h+DosName.MaximumLength], ax
0x14003be39  mov     [rsp+38h+DosName.Length], ax
0x14003be3e  lea     rax, [rcx+20h]
0x14003be42  mov     [rsp+38h+DosName.Buffer], rax
0x14003be47  xor     r8d, r8d; Thread
0x14003be4a  lea     rdx, [rsp+38h+DosName]; String
0x14003be4f  mov     ecx, 0C0000222h; ErrorStatus
0x14003be54  call    cs:__imp_IoRaiseInformationalHardError
0x14003be5b  nop     dword ptr [rax+rax+00h]
0x14003be60  test    bl, bl
0x14003be62  jz      short loc_14003BE77
0x14003be64  mov     rcx, [rsp+38h+DosName.Buffer]; P
0x14003be69  xor     edx, edx; Tag
0x14003be6b  call    cs:__imp_ExFreePoolWithTag
0x14003be72  nop     dword ptr [rax+rax+00h]
0x14003be77  mov     rbx, [rsp+38h+arg_0]
0x14003be7c  add     rsp, 30h
0x14003be80  pop     rdi
0x14003be81  retn
```
