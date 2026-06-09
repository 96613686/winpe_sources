# SrvNetCompressData

- ea: `0x1400539b8`
- end: `0x140053a65`
- name: `SrvNetCompressData`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400010f0`

## callees

- `0x140018728`
- `0x1400539b8`
- `0x140053a6c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140053a2b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140053a2b`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall SrvNetCompressData(__int64 a1, _DWORD *a2)
{
  __int64 v4; // rcx
  PDEVICE_OBJECT *result; // rax

  v4 = *((_QWORD *)a2 + 1);
  if ( (*(_BYTE *)(v4 + 10) & 5) != 0 )
    result = *(PDEVICE_OBJECT **)(v4 + 24);
  else
    result = (PDEVICE_OBJECT *)MmMapLockedPagesSpecifyCache((PMDL)v4, 0, MmCached, 0, 0, 0x40000010u);
  if ( *((_WORD *)result + 6) )
  {
    result = (PDEVICE_OBJECT *)SrvNetCompressDataEx(a2);
    if ( (int)result < 0 )
    {
      result = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        return (PDEVICE_OBJECT *)WPP_SF_qdq(
                                   WPP_GLOBAL_Control->AttachedDevice,
                                   16,
                                   WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids,
                                   *((_QWORD *)a2 + 1),
                                   *a2,
                                   a1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400539b8  mov     [rsp+arg_0], rbx
0x1400539bd  push    rdi
0x1400539be  sub     rsp, 30h
0x1400539c2  mov     rdi, rcx
0x1400539c5  mov     rbx, rdx
0x1400539c8  mov     rcx, [rdx+8]; MemoryDescriptorList
0x1400539cc  test    byte ptr [rcx+0Ah], 5
0x1400539d0  jz      short loc_140053A12
0x1400539d2  mov     rax, [rcx+18h]
0x1400539d6  xor     ecx, ecx
0x1400539d8  cmp     cx, [rax+0Ch]
0x1400539dc  jz      short loc_140053A06
0x1400539de  mov     rcx, rbx
0x1400539e1  call    SrvNetCompressDataEx
0x1400539e6  test    eax, eax
0x1400539e8  jns     short loc_140053A06
0x1400539ea  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400539f1  lea     rax, WPP_GLOBAL_Control
0x1400539f8  cmp     rcx, rax
0x1400539fb  jz      short loc_140053A06
0x1400539fd  test    dword ptr [rcx+2Ch], 2000h
0x140053a04  jnz     short loc_140053A39
0x140053a06  mov     rbx, [rsp+38h+arg_0]
0x140053a0b  add     rsp, 30h
0x140053a0f  pop     rdi
0x140053a10  retn
0x140053a12  xor     r9d, r9d; RequestedAddress
0x140053a15  mov     [rsp+38h+Priority], 40000010h; Priority
0x140053a1d  xor     edx, edx; AccessMode
0x140053a1f  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140053a27  lea     r8d, [r9+1]; CacheType
0x140053a2b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140053a32  nop     dword ptr [rax+rax+00h]
0x140053a37  jmp     short loc_1400539D6
0x140053a39  cmp     byte ptr [rcx+29h], 2
0x140053a3d  jb      short loc_140053A06
0x140053a3f  mov     eax, [rbx]
0x140053a41  lea     r8, WPP_13dfc6c10cd0357b2fe0dd4f6ff3f414_Traceguids
0x140053a48  mov     r9, [rbx+8]
0x140053a4c  mov     edx, 10h
0x140053a51  mov     rcx, [rcx+18h]
0x140053a55  mov     qword ptr [rsp+38h+Priority], rdi
0x140053a5a  mov     [rsp+38h+BugCheckOnFailure], eax
0x140053a5e  call    WPP_SF_qdq
0x140053a63  jmp     short loc_140053A06
```
