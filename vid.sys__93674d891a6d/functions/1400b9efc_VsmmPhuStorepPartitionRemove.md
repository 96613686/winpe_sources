# VsmmPhuStorepPartitionRemove

- ea: `0x1400b9efc`
- end: `0x1400b9fa6`
- name: `VsmmPhuStorepPartitionRemove`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400b674c`

## callees

- `0x1400347a4`
- `0x140034b64`
- `0x1400b9efc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400b9f5f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b9f5f`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x1400b9f89`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x1400b9f89`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400b9f2f`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400b9f2f`

## pseudocode

```c
__int64 __fastcall VsmmPhuStorepPartitionRemove(__int64 a1)
{
  char *v2; // rdi
  __int64 v3; // rax
  _QWORD *v4; // rbx

  v2 = (char *)VidDeviceExtension + 1672;
  VidObjectLockAcquireExclusive((char *)VidDeviceExtension + 1672);
  RtlRbRemoveNode(v2 + 16, a1 + 24);
  v3 = *((_QWORD *)v2 + 2);
  if ( (v2[24] & 1) != 0 )
  {
    if ( !v3 )
    {
LABEL_5:
      v4 = VidDeviceExtension;
      ObfDereferenceObject(*((PVOID *)VidDeviceExtension + 215));
      v4[215] = 0;
      goto LABEL_6;
    }
    v3 ^= (unsigned __int64)(v2 + 16);
  }
  if ( !v3 )
    goto LABEL_5;
LABEL_6:
  VidObjectLockRelease(v2);
  _InterlockedIncrement64((volatile signed __int64 *)v2 + 4);
  return ExUnblockOnAddressPushLockEx(v2 + 40, 0);
}

```

## disassembly

```asm
0x1400b9efc  mov     [rsp+arg_0], rbx
0x1400b9f01  mov     [rsp+arg_8], rsi
0x1400b9f06  push    rdi
0x1400b9f07  sub     rsp, 20h
0x1400b9f0b  mov     rdi, cs:VidDeviceExtension
0x1400b9f12  mov     rbx, rcx
0x1400b9f15  add     rdi, 688h
0x1400b9f1c  mov     rcx, rdi
0x1400b9f1f  call    VidObjectLockAcquireExclusive
0x1400b9f24  lea     rsi, [rdi+10h]
0x1400b9f28  mov     rcx, rsi
0x1400b9f2b  lea     rdx, [rbx+18h]
0x1400b9f2f  call    cs:__imp_RtlRbRemoveNode
0x1400b9f36  nop     dword ptr [rax+rax+00h]
0x1400b9f3b  test    byte ptr [rsi+8], 1
0x1400b9f3f  mov     rax, [rsi]
0x1400b9f42  jz      short loc_1400B9F4C
0x1400b9f44  test    rax, rax
0x1400b9f47  jz      short loc_1400B9F51
0x1400b9f49  xor     rax, rsi
0x1400b9f4c  test    rax, rax
0x1400b9f4f  jnz     short loc_1400B9F76
0x1400b9f51  mov     rbx, cs:VidDeviceExtension
0x1400b9f58  mov     rcx, [rbx+6B8h]; Object
0x1400b9f5f  call    cs:__imp_ObfDereferenceObject
0x1400b9f66  nop     dword ptr [rax+rax+00h]
0x1400b9f6b  mov     qword ptr [rbx+6B8h], 0
0x1400b9f76  mov     rcx, rdi
0x1400b9f79  call    VidObjectLockRelease
0x1400b9f7e  lock inc qword ptr [rdi+20h]
0x1400b9f83  lea     rcx, [rdi+28h]
0x1400b9f87  xor     edx, edx
0x1400b9f89  call    cs:__imp_ExUnblockOnAddressPushLockEx
0x1400b9f90  nop     dword ptr [rax+rax+00h]
0x1400b9f95  mov     rbx, [rsp+28h+arg_0]
0x1400b9f9a  mov     rsi, [rsp+28h+arg_8]
0x1400b9f9f  add     rsp, 20h
0x1400b9fa3  pop     rdi
0x1400b9fa4  retn
```
