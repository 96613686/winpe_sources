# WinSetupMonPreCreate

- ea: `0x14001fdc0`
- end: `0x14001fe20`
- name: `WinSetupMonPreCreate`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x14001e808`
- `0x14001fdc0`

## pseudocode

```c
__int64 __fastcall WinSetupMonPreCreate(struct _FLT_CALLBACK_DATA *a1, struct _UNICODE_STRING *a2)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // r9
  unsigned int v3; // r10d
  struct _UNICODE_STRING v5; // [rsp+50h] [rbp+8h] BYREF

  Iopb = a1->Iopb;
  v3 = 1;
  *(_DWORD *)&v5.Length = 1;
  if ( Iopb && (Iopb->Parameters.Create.Options & 0x1000) != 0 )
  {
    HandleOperation(
      a1,
      a2,
      (Iopb->OperationFlags & 2) != 0,
      (HIBYTE(Iopb->Parameters.SetVolumeInformation.FsInformationClass) & 2) != 0,
      0,
      &v5,
      0);
    return *(unsigned int *)&v5.Length;
  }
  return v3;
}

```

## disassembly

```asm
0x14001fdc0  mov     r11, rsp
0x14001fdc3  sub     rsp, 48h
0x14001fdc7  mov     r9, [rcx+10h]
0x14001fdcb  mov     r10d, 1
0x14001fdd1  mov     [r11+8], r10d
0x14001fdd5  test    r9, r9
0x14001fdd8  jz      short loc_14001FE17
0x14001fdda  mov     r8b, [r9+6]
0x14001fdde  shr     r8b, 1
0x14001fde1  and     r8b, r10b
0x14001fde4  test    dword ptr [r9+20h], 1000h
0x14001fdec  jz      short loc_14001FE17
0x14001fdee  mov     r9b, [r9+23h]
0x14001fdf2  lea     rax, [r11+8]
0x14001fdf6  mov     qword ptr [r11-18h], 0
0x14001fdfe  shr     r9b, 1
0x14001fe01  mov     [r11-20h], rax
0x14001fe05  and     r9b, r10b
0x14001fe08  mov     [rsp+48h+var_28], 0
0x14001fe0d  call    HandleOperation
0x14001fe12  mov     r10d, dword ptr [rsp+48h+arg_0]
0x14001fe17  mov     eax, r10d
0x14001fe1a  add     rsp, 48h
0x14001fe1e  retn
```
