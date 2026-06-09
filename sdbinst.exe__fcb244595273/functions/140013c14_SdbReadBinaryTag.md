# SdbReadBinaryTag

- ea: `0x140013c14`
- end: `0x140013cb1`
- name: `SdbReadBinaryTag`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1400045e0`
- `0x140008500`
- `0x140013d54`
- `0x140015a18`

## callees

- `0x14001008c`
- `0x140013c14`
- `0x1400142e0`
- `0x140016148`

## string_xrefs

- `0x140013c57`: `SdbReadBinaryTag`
- `0x140013c92`: `SdbReadBinaryTag`
- `0x140013c85`: `Error reading buffer`

## pseudocode

```c
__int64 __fastcall SdbReadBinaryTag(__int64 a1, __int64 a2, void *a3, unsigned int a4)
{
  unsigned int v6; // ebx
  unsigned __int16 TagFromTagID; // ax

  v6 = a2;
  if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) != 0x9000 )
  {
    TagFromTagID = SdbGetTagFromTagID(a1, v6);
    AslLogCallPrintf(1, "SdbReadBinaryTag", 1005, "TagID 0x%08X, Tag %04X not BINARY type", v6, TagFromTagID);
    return 0;
  }
  if ( !(unsigned int)SdbpReadTagData(a1, v6, a3, a4) )
  {
    AslLogCallPrintf(1, "SdbReadBinaryTag", 1010, "Error reading buffer");
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x140013c14  push    rbx
0x140013c16  push    rbp
0x140013c17  push    rsi
0x140013c18  push    rdi
0x140013c19  sub     rsp, 38h
0x140013c1d  mov     esi, r9d
0x140013c20  mov     rbp, r8
0x140013c23  mov     ebx, edx
0x140013c25  mov     rdi, rcx
0x140013c28  call    SdbGetTagFromTagID
0x140013c2d  mov     ecx, 0F000h
0x140013c32  mov     edx, ebx
0x140013c34  and     ax, cx
0x140013c37  mov     ecx, 9000h
0x140013c3c  cmp     ax, cx
0x140013c3f  mov     rcx, rdi
0x140013c42  jz      short loc_140013C76
0x140013c44  call    SdbGetTagFromTagID
0x140013c49  movzx   eax, ax
0x140013c4c  lea     r9, aTagid0x08xTag0_0; "TagID 0x%08X, Tag %04X not BINARY type"
0x140013c53  mov     [rsp+58h+var_30], eax
0x140013c57  lea     rdx, aSdbreadbinaryt; "SdbReadBinaryTag"
0x140013c5e  mov     r8d, 3EDh
0x140013c64  mov     [rsp+58h+var_38], ebx
0x140013c68  mov     ecx, 1
0x140013c6d  call    AslLogCallPrintf
0x140013c72  xor     eax, eax
0x140013c74  jmp     short loc_140013CA8
0x140013c76  mov     r9d, esi
0x140013c79  mov     r8, rbp
0x140013c7c  call    SdbpReadTagData
0x140013c81  test    eax, eax
0x140013c83  jnz     short loc_140013CA3
0x140013c85  lea     r9, aErrorReadingBu; "Error reading buffer"
0x140013c8c  mov     r8d, 3F2h
0x140013c92  lea     rdx, aSdbreadbinaryt; "SdbReadBinaryTag"
0x140013c99  lea     ecx, [rax+1]
0x140013c9c  call    AslLogCallPrintf
0x140013ca1  jmp     short loc_140013C72
0x140013ca3  mov     eax, 1
0x140013ca8  add     rsp, 38h
0x140013cac  pop     rdi
0x140013cad  pop     rsi
0x140013cae  pop     rbp
0x140013caf  pop     rbx
0x140013cb0  retn
```
