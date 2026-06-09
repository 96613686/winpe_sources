# SclRegCopySecurityInfo

- ea: `0x180008be0`
- end: `0x180008d3d`
- name: `SclRegCopySecurityInfo`
- size: `349`
- prototype: `__int64 __fastcall(__int64, __int64, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007fb0`
- `0x18000c73c`

## callees

- `0x180001b98`
- `0x180001bc0`
- `0x180008be0`
- `0x18000a524`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180008c3e`
- `ntdll!RtlAllocateHeap` at `0x180008c3e`
- `ntdll!RtlFreeHeap` at `0x180008d28`
- `ntdll!RtlFreeHeap` at `0x180008d28`

## string_xrefs

- `0x180008ca9`: `(%lx): Failed to query object security for size.`
- `0x180008c17`: `SclRegCopySecurityInfo`
- `0x180008cf8`: `(%lx): Failed to create destination child key.`

## pseudocode

```c
__int64 __fastcall SclRegCopySecurityInfo(__int64 a1, __int64 a2, void *a3)
{
  int Descriptor; // eax
  int v7; // ebx
  PVOID Heap; // rax
  void *v9; // rdi
  __int64 v10; // rsi
  __int64 v11; // rcx
  _DWORD v13[18]; // [rsp+40h] [rbp-48h] BYREF
  SIZE_T Size; // [rsp+A8h] [rbp+20h] BYREF

  v13[0] = 0;
  LODWORD(Size) = 0;
  Descriptor = SclSecurityGetDescriptor(a2, 0, 0, &Size);
  v7 = Descriptor;
  if ( Descriptor == -1073741789 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
    v9 = Heap;
    if ( Heap )
      v7 = SclSecurityGetDescriptor(a2, Heap, (unsigned int)Size, v13);
    else
      v7 = -1073741801;
    if ( v7 >= 0 )
    {
      v10 = a1 + 1152;
LABEL_12:
      v7 = SclSecuritySetDescriptor(a3, v9);
      if ( v7 < 0 )
      {
        if ( !a1 )
          v10 = 0;
        SclLogGenericMessage(
          v10,
          3,
          (int)SclEvent_Generic_Error,
          1283,
          (__int64)"SclRegCopySecurityInfo",
          "(%lx): Failed to create destination child key.",
          v7);
      }
      goto LABEL_16;
    }
  }
  else
  {
    v9 = 0;
    if ( Descriptor >= 0 )
      v7 = -1073741823;
  }
  v10 = a1 + 1152;
  v11 = a1 + 1152;
  if ( !a1 )
    v11 = 0;
  SclLogGenericMessage(
    v11,
    3,
    (int)SclEvent_Generic_Error,
    1276,
    (__int64)"SclRegCopySecurityInfo",
    "(%lx): Failed to query object security for size.",
    v7);
  if ( v7 >= 0 )
    goto LABEL_12;
LABEL_16:
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008be0  mov     rax, rsp
0x180008be3  push    rbx
0x180008be4  push    rbp
0x180008be5  push    rsi
0x180008be6  push    rdi
0x180008be7  push    r12
0x180008be9  push    r14
0x180008beb  sub     rsp, 58h
0x180008bef  mov     rsi, rdx
0x180008bf2  mov     dword ptr [rax-48h], 0
0x180008bf9  mov     r14, r8
0x180008bfc  mov     dword ptr [rax+20h], 0
0x180008c03  mov     rbp, rcx
0x180008c06  lea     r9, [rax+20h]
0x180008c0a  mov     rcx, rsi
0x180008c0d  xor     r8d, r8d
0x180008c10  xor     edx, edx
0x180008c12  call    SclSecurityGetDescriptor
0x180008c17  lea     r12, aSclregcopysecu; "SclRegCopySecurityInfo"
0x180008c1e  mov     ebx, eax
0x180008c20  cmp     eax, 0C0000023h
0x180008c25  jnz     short loc_180008C7A
0x180008c27  mov     rcx, gs:60h
0x180008c30  xor     edx, edx; Flags
0x180008c32  mov     r8d, dword ptr [rsp+88h+Size]; Size
0x180008c3a  mov     rcx, [rcx+30h]; HeapHandle
0x180008c3e  call    cs:__imp_RtlAllocateHeap
0x180008c44  mov     rdi, rax
0x180008c47  test    rax, rax
0x180008c4a  jz      short loc_180008C68
0x180008c4c  mov     r8d, dword ptr [rsp+88h+Size]
0x180008c54  lea     r9, [rsp+88h+var_48]
0x180008c59  mov     rdx, rax
0x180008c5c  mov     rcx, rsi
0x180008c5f  call    SclSecurityGetDescriptor
0x180008c64  mov     ebx, eax
0x180008c66  jmp     short loc_180008C6D
0x180008c68  mov     ebx, 0C0000017h
0x180008c6d  test    ebx, ebx
0x180008c6f  js      short loc_180008C85
0x180008c71  lea     rsi, [rbp+480h]
0x180008c78  jmp     short loc_180008CC8
0x180008c7a  xor     edi, edi
0x180008c7c  test    eax, eax
0x180008c7e  js      short loc_180008C85
0x180008c80  mov     ebx, 0C0000001h
0x180008c85  xor     eax, eax
0x180008c87  mov     [rsp+88h+var_58], ebx
0x180008c8b  lea     rsi, [rbp+480h]
0x180008c92  test    rbp, rbp
0x180008c95  mov     rcx, rsi
0x180008c98  lea     r8, SclEvent_Generic_Error
0x180008c9f  cmovz   rcx, rax
0x180008ca3  mov     r9d, 4FCh
0x180008ca9  lea     rax, aLxFailedToQuer; "(%lx): Failed to query object security "...
0x180008cb0  mov     edx, 3
0x180008cb5  mov     [rsp+88h+var_60], rax
0x180008cba  mov     [rsp+88h+var_68], r12
0x180008cbf  call    SclLogGenericMessage
0x180008cc4  test    ebx, ebx
0x180008cc6  js      short loc_180008D11
0x180008cc8  mov     rdx, rdi; SecurityDescriptor
0x180008ccb  mov     rcx, r14; Handle
0x180008cce  call    SclSecuritySetDescriptor
0x180008cd3  mov     ebx, eax
0x180008cd5  test    eax, eax
0x180008cd7  jns     short loc_180008D11
0x180008cd9  xor     eax, eax
0x180008cdb  mov     [rsp+88h+var_58], ebx
0x180008cdf  test    rbp, rbp
0x180008ce2  lea     r8, SclEvent_Generic_Error
0x180008ce9  mov     r9d, 503h
0x180008cef  mov     edx, 3
0x180008cf4  cmovz   rsi, rax
0x180008cf8  lea     rax, aLxFailedToCrea_4; "(%lx): Failed to create destination chi"...
0x180008cff  mov     [rsp+88h+var_60], rax
0x180008d04  mov     rcx, rsi
0x180008d07  mov     [rsp+88h+var_68], r12
0x180008d0c  call    SclLogGenericMessage
0x180008d11  test    rdi, rdi
0x180008d14  jz      short loc_180008D2E
0x180008d16  mov     rcx, gs:60h
0x180008d1f  mov     r8, rdi; P
0x180008d22  xor     edx, edx; Flags
0x180008d24  mov     rcx, [rcx+30h]; HeapHandle
0x180008d28  call    cs:__imp_RtlFreeHeap
0x180008d2e  mov     eax, ebx
0x180008d30  add     rsp, 58h
0x180008d34  pop     r14
0x180008d36  pop     r12
0x180008d38  pop     rdi
0x180008d39  pop     rsi
0x180008d3a  pop     rbp
0x180008d3b  pop     rbx
0x180008d3c  retn
```
