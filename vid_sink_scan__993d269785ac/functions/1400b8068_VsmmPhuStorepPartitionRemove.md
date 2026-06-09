# VsmmPhuStorepPartitionRemove

- ea: `0x1400b8068`
- end: `0x1400b8112`
- name: `VsmmPhuStorepPartitionRemove`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400b484c`

## callees

- `0x140034554`
- `0x140034914`
- `0x1400b8068`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400b80cb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b80cb`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x1400b80f5`
- `ntoskrnl!ExUnblockOnAddressPushLockEx` at `0x1400b80f5`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400b809b`
- `ntoskrnl!RtlRbRemoveNode` at `0x1400b809b`

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
0x1400b8068  mov     [rsp+arg_0], rbx
0x1400b806d  mov     [rsp+arg_8], rsi
0x1400b8072  push    rdi
0x1400b8073  sub     rsp, 20h
0x1400b8077  mov     rdi, cs:VidDeviceExtension
0x1400b807e  mov     rbx, rcx
0x1400b8081  add     rdi, 688h
0x1400b8088  mov     rcx, rdi
0x1400b808b  call    VidObjectLockAcquireExclusive
0x1400b8090  lea     rsi, [rdi+10h]
0x1400b8094  mov     rcx, rsi
0x1400b8097  lea     rdx, [rbx+18h]
0x1400b809b  call    cs:__imp_RtlRbRemoveNode
0x1400b80a2  nop     dword ptr [rax+rax+00h]
0x1400b80a7  test    byte ptr [rsi+8], 1
0x1400b80ab  mov     rax, [rsi]
0x1400b80ae  jz      short loc_1400B80B8
0x1400b80b0  test    rax, rax
0x1400b80b3  jz      short loc_1400B80BD
0x1400b80b5  xor     rax, rsi
0x1400b80b8  test    rax, rax
0x1400b80bb  jnz     short loc_1400B80E2
0x1400b80bd  mov     rbx, cs:VidDeviceExtension
0x1400b80c4  mov     rcx, [rbx+6B8h]; Object
0x1400b80cb  call    cs:__imp_ObfDereferenceObject
0x1400b80d2  nop     dword ptr [rax+rax+00h]
0x1400b80d7  mov     qword ptr [rbx+6B8h], 0
0x1400b80e2  mov     rcx, rdi
0x1400b80e5  call    VidObjectLockRelease
0x1400b80ea  lock inc qword ptr [rdi+20h]
0x1400b80ef  lea     rcx, [rdi+28h]
0x1400b80f3  xor     edx, edx
0x1400b80f5  call    cs:__imp_ExUnblockOnAddressPushLockEx
0x1400b80fc  nop     dword ptr [rax+rax+00h]
0x1400b8101  mov     rbx, [rsp+28h+arg_0]
0x1400b8106  mov     rsi, [rsp+28h+arg_8]
0x1400b810b  add     rsp, 20h
0x1400b810f  pop     rdi
0x1400b8110  retn
```
