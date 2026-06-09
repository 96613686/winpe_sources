# WinUsb_IsUpperFilterPresent

- ea: `0x14001bfdc`
- end: `0x14001c0a2`
- name: `WinUsb_IsUpperFilterPresent`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001b870`

## callees

- `0x140010700`
- `0x14001bfdc`

## import_xrefs

- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001c00d`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x14001c00d`
- `ntoskrnl!RtlCompareMemory` at `0x14001c040`
- `ntoskrnl!RtlCompareMemory` at `0x14001c040`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c06b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c087`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c06b`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c087`
- `ntoskrnl!IoGetLowerDeviceObject` at `0x14001c054`
- `ntoskrnl!IoGetLowerDeviceObject` at `0x14001c054`

## pseudocode

```c
char __fastcall WinUsb_IsUpperFilterPresent(__int64 a1)
{
  char v1; // si
  struct _DEVICE_OBJECT *v2; // rbp
  PDEVICE_OBJECT AttachedDeviceReference; // rbx
  _DRIVER_OBJECT *DriverObject; // rdx
  PDEVICE_OBJECT LowerDeviceObject; // rdi

  v1 = 0;
  v2 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 248))(
                                  WdfDriverGlobals,
                                  a1);
  AttachedDeviceReference = IoGetAttachedDeviceReference(v2);
  if ( v2 != AttachedDeviceReference )
  {
    while ( 1 )
    {
      DriverObject = AttachedDeviceReference->DriverObject;
      if ( DriverObject->DriverName.Length < 0x20u
        || RtlCompareMemory(L"\\DRIVER\\VERIFIER", DriverObject->DriverName.Buffer, 0x20u) != 32 )
      {
        break;
      }
      LowerDeviceObject = IoGetLowerDeviceObject(AttachedDeviceReference);
      if ( LowerDeviceObject )
      {
        ObfDereferenceObject(AttachedDeviceReference);
        AttachedDeviceReference = LowerDeviceObject;
        if ( v2 != LowerDeviceObject )
          continue;
      }
      goto LABEL_8;
    }
    v1 = 1;
  }
LABEL_8:
  ObfDereferenceObject(AttachedDeviceReference);
  return v1;
}

```

## disassembly

```asm
0x14001bfdc  push    rbx
0x14001bfde  push    rbp
0x14001bfdf  push    rsi
0x14001bfe0  push    rdi
0x14001bfe1  push    r14
0x14001bfe3  sub     rsp, 20h
0x14001bfe7  mov     rax, cs:WdfFunctions_01015
0x14001bfee  mov     rdx, rcx
0x14001bff1  mov     rcx, cs:WdfDriverGlobals
0x14001bff8  xor     sil, sil
0x14001bffb  mov     rax, [rax+0F8h]
0x14001c002  call    _guard_dispatch_icall
0x14001c007  mov     rcx, rax; DeviceObject
0x14001c00a  mov     rbp, rax
0x14001c00d  call    cs:__imp_IoGetAttachedDeviceReference
0x14001c014  nop     dword ptr [rax+rax+00h]
0x14001c019  mov     rbx, rax
0x14001c01c  cmp     rbp, rax
0x14001c01f  jz      short loc_14001C084
0x14001c021  mov     r14d, 20h ; ' '
0x14001c027  mov     rdx, [rbx+8]
0x14001c02b  cmp     [rdx+38h], r14w
0x14001c030  jb      short loc_14001C081
0x14001c032  mov     rdx, [rdx+40h]; Source2
0x14001c036  lea     rcx, aDriverVerifier; "\\DRIVER\\VERIFIER"
0x14001c03d  mov     r8, r14; Length
0x14001c040  call    cs:__imp_RtlCompareMemory
0x14001c047  nop     dword ptr [rax+rax+00h]
0x14001c04c  cmp     rax, r14
0x14001c04f  jnz     short loc_14001C081
0x14001c051  mov     rcx, rbx; DeviceObject
0x14001c054  call    cs:__imp_IoGetLowerDeviceObject
0x14001c05b  nop     dword ptr [rax+rax+00h]
0x14001c060  mov     rdi, rax
0x14001c063  test    rax, rax
0x14001c066  jz      short loc_14001C084
0x14001c068  mov     rcx, rbx; Object
0x14001c06b  call    cs:__imp_ObfDereferenceObject
0x14001c072  nop     dword ptr [rax+rax+00h]
0x14001c077  mov     rbx, rdi
0x14001c07a  cmp     rbp, rdi
0x14001c07d  jnz     short loc_14001C027
0x14001c07f  jmp     short loc_14001C084
0x14001c081  mov     sil, 1
0x14001c084  mov     rcx, rbx; Object
0x14001c087  call    cs:__imp_ObfDereferenceObject
0x14001c08e  nop     dword ptr [rax+rax+00h]
0x14001c093  mov     al, sil
0x14001c096  add     rsp, 20h
0x14001c09a  pop     r14
0x14001c09c  pop     rdi
0x14001c09d  pop     rsi
0x14001c09e  pop     rbp
0x14001c09f  pop     rbx
0x14001c0a0  retn
```
