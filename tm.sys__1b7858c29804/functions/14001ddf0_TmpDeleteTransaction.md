# TmpDeleteTransaction

- ea: `0x14001ddf0`
- end: `0x14001def5`
- name: `TmpDeleteTransaction`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000c664`
- `0x14001ddf0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001deb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001deb6`
- `ntoskrnl!ObfDereferenceObject` at `0x14001de9e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ded9`
- `ntoskrnl!ObfDereferenceObject` at `0x14001de9e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001ded9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001de90`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001de90`

## pseudocode

```c
void __fastcall TmpDeleteTransaction(__int64 a1)
{
  __int64 v2; // rdx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  _InterlockedOr((volatile signed __int32 *)(a1 + 196), 0x80000000);
  if ( *(_DWORD *)(a1 + 192) )
  {
    if ( *(_QWORD *)(a1 + 136) )
    {
      v2 = *(_QWORD *)(a1 + 512);
      if ( v2 )
      {
        TmpNamespaceRemove((PRTL_AVL_TABLE)(v2 + 176), (PVOID)v2, a1);
        *(_QWORD *)(a1 + 512) = 0;
      }
    }
    if ( *(_QWORD *)(a1 + 96) )
      TmpNamespaceRemove(&TmpTransactionsNamespace, 0, a1);
    if ( *(_QWORD *)(a1 + 312) )
      RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 304));
    v3 = *(void **)(a1 + 88);
    if ( v3 != (void *)a1 )
    {
      ObfDereferenceObject(v3);
      *(_QWORD *)(a1 + 88) = 0;
    }
    v4 = *(void **)(a1 + 616);
    if ( v4 )
    {
      ExFreePoolWithTag(v4, 0);
      *(_QWORD *)(a1 + 616) = 0;
      *(_DWORD *)(a1 + 624) = 0;
    }
    v5 = *(void **)(a1 + 272);
    if ( v5 )
    {
      ObfDereferenceObject(v5);
      *(_QWORD *)(a1 + 272) = 0;
    }
  }
}

```

## disassembly

```asm
0x14001ddf0  push    rbx
0x14001ddf2  sub     rsp, 20h
0x14001ddf6  mov     rbx, rcx
0x14001ddf9  lock or dword ptr [rcx+0C4h], 80000000h
0x14001de04  cmp     dword ptr [rcx+0C0h], 0
0x14001de0b  jz      short loc_14001DE6F
0x14001de0d  cmp     qword ptr [rcx+88h], 0
0x14001de15  jz      short loc_14001DE3D
0x14001de17  mov     rdx, [rcx+200h]; Object
0x14001de1e  test    rdx, rdx
0x14001de21  jz      short loc_14001DE3D
0x14001de23  lea     rcx, [rdx+0B0h]; Table
0x14001de2a  mov     r8, rbx
0x14001de2d  call    TmpNamespaceRemove
0x14001de32  mov     qword ptr [rbx+200h], 0
0x14001de3d  cmp     qword ptr [rbx+60h], 0
0x14001de42  jnz     short loc_14001DE76
0x14001de44  cmp     qword ptr [rbx+138h], 0
0x14001de4c  jnz     short loc_14001DE89
0x14001de4e  mov     rcx, [rbx+58h]; Object
0x14001de52  cmp     rcx, rbx
0x14001de55  jnz     short loc_14001DE9E
0x14001de57  mov     rcx, [rbx+268h]; P
0x14001de5e  test    rcx, rcx
0x14001de61  jnz     short loc_14001DEB4
0x14001de63  mov     rcx, [rbx+110h]; Object
0x14001de6a  test    rcx, rcx
0x14001de6d  jnz     short loc_14001DED9
0x14001de6f  add     rsp, 20h
0x14001de73  pop     rbx
0x14001de74  retn
0x14001de76  mov     r8, rbx
0x14001de79  lea     rcx, TmpTransactionsNamespace; Table
0x14001de80  xor     edx, edx; Object
0x14001de82  call    TmpNamespaceRemove
0x14001de87  jmp     short loc_14001DE44
0x14001de89  lea     rcx, [rbx+130h]; UnicodeString
0x14001de90  call    cs:__imp_RtlFreeUnicodeString
0x14001de97  nop     dword ptr [rax+rax+00h]
0x14001de9c  jmp     short loc_14001DE4E
0x14001de9e  call    cs:__imp_ObfDereferenceObject
0x14001dea5  nop     dword ptr [rax+rax+00h]
0x14001deaa  mov     qword ptr [rbx+58h], 0
0x14001deb2  jmp     short loc_14001DE57
0x14001deb4  xor     edx, edx; Tag
0x14001deb6  call    cs:__imp_ExFreePoolWithTag
0x14001debd  nop     dword ptr [rax+rax+00h]
0x14001dec2  mov     qword ptr [rbx+268h], 0
0x14001decd  mov     dword ptr [rbx+270h], 0
0x14001ded7  jmp     short loc_14001DE63
0x14001ded9  call    cs:__imp_ObfDereferenceObject
0x14001dee0  nop     dword ptr [rax+rax+00h]
0x14001dee5  mov     qword ptr [rbx+110h], 0
0x14001def0  jmp     loc_14001DE6F
```
