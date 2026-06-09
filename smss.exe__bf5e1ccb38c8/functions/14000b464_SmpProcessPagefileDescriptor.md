# SmpProcessPagefileDescriptor

- ea: `0x14000b464`
- end: `0x14000b4a4`
- name: `SmpProcessPagefileDescriptor`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000f5b0`
- `0x14000fcf8`

## callees

- `0x14000af6c`
- `0x14000b464`
- `0x14000d7ec`
- `0x14000ea5c`

## pseudocode

```c
__int64 __fastcall SmpProcessPagefileDescriptor(__int64 a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  if ( (*(_BYTE *)(a1 + 92) & 2) != 0 )
    SmpMakeSystemManagedPagingFileDescriptor(a1);
  SmpValidatePagingFileSizes(a1);
  if ( (*(_BYTE *)(a1 + 92) & 4) == 0 )
    return SmpCreatePagefileFromDescriptor(a1, 1);
  result = SmpCreatePagefileFromDescriptor(v2, 0);
  if ( (int)result < 0 )
    return SmpCreatePagefileFromDescriptor(a1, 1);
  return result;
}

```

## disassembly

```asm
0x14000b464  push    rbx
0x14000b466  sub     rsp, 20h
0x14000b46a  test    byte ptr [rcx+5Ch], 2
0x14000b46e  mov     rbx, rcx
0x14000b471  jz      short loc_14000B478
0x14000b473  call    SmpMakeSystemManagedPagingFileDescriptor
0x14000b478  mov     rcx, rbx
0x14000b47b  call    SmpValidatePagingFileSizes
0x14000b480  test    byte ptr [rbx+5Ch], 4
0x14000b484  jz      short loc_14000B491
0x14000b486  xor     edx, edx
0x14000b488  call    SmpCreatePagefileFromDescriptor
0x14000b48d  test    eax, eax
0x14000b48f  jns     short loc_14000B49E
0x14000b491  mov     edx, 1
0x14000b496  mov     rcx, rbx
0x14000b499  call    SmpCreatePagefileFromDescriptor
0x14000b49e  add     rsp, 20h
0x14000b4a2  pop     rbx
0x14000b4a3  retn
```
