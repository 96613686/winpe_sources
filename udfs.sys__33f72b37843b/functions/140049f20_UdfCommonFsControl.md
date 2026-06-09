# UdfCommonFsControl

- ea: `0x140049f20`
- end: `0x140049f70`
- name: `UdfCommonFsControl`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x140003148`
- `0x140049f20`
- `0x140049f80`
- `0x14004b594`

## pseudocode

```c
__int64 __fastcall UdfCommonFsControl(void *a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  unsigned int v4; // ebx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->MinorFunction )
  {
    if ( CurrentStackLocation->MinorFunction == 1 )
    {
      return (unsigned int)UdfMountVolume((__int64)a1, (__int64)a2);
    }
    else
    {
      if ( CurrentStackLocation->MinorFunction != 2 )
      {
        v4 = -1073741808;
        UdfCompleteRequest(a1, a2, -1073741808);
        return v4;
      }
      return (unsigned int)UdfVerifyVolume((__int64)a1, a2);
    }
  }
  else
  {
    return (unsigned int)UdfUserFsctl((__int64)a1, a2);
  }
}

```

## disassembly

```asm
0x140049f20  push    rbx
0x140049f22  sub     rsp, 20h
0x140049f26  mov     rax, [rdx+0B8h]
0x140049f2d  movzx   r8d, byte ptr [rax+1]
0x140049f32  test    r8d, r8d
0x140049f35  jz      short loc_140049F4D
0x140049f37  sub     r8d, 1
0x140049f3b  jnz     short loc_140049F54
0x140049f3d  call    UdfMountVolume
0x140049f42  mov     ebx, eax
0x140049f44  mov     eax, ebx
0x140049f46  add     rsp, 20h
0x140049f4a  pop     rbx
0x140049f4b  retn
0x140049f4d  call    UdfUserFsctl
0x140049f52  jmp     short loc_140049F42
0x140049f54  cmp     r8d, 1
0x140049f58  jz      short loc_140049F69
0x140049f5a  mov     ebx, 0C0000010h
0x140049f5f  mov     r8d, ebx
0x140049f62  call    UdfCompleteRequest
0x140049f67  jmp     short loc_140049F44
0x140049f69  call    UdfVerifyVolume
0x140049f6e  jmp     short loc_140049F42
```
