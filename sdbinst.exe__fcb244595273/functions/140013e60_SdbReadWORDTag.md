# SdbReadWORDTag

- ea: `0x140013e60`
- end: `0x140013efb`
- name: `SdbReadWORDTag`
- size: `155`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140018840`
- `0x14001a878`
- `0x14001c730`
- `0x14001f90c`

## callees

- `0x14001008c`
- `0x140013e60`
- `0x1400142e0`
- `0x140016148`

## string_xrefs

- `0x140013ead`: `SdbReadWORDTag`

## pseudocode

```c
__int64 __fastcall SdbReadWORDTag(__int64 a1, __int64 a2, unsigned __int16 a3)
{
  unsigned int v4; // ebx
  unsigned __int16 TagFromTagID; // ax
  int v8; // eax
  unsigned __int16 v9; // cx
  unsigned __int16 v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = a3;
  v4 = a2;
  if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) == 0x3000 )
  {
    v8 = SdbpReadTagData(a1, v4, &v10, 2u);
    v9 = v10;
    if ( !v8 )
      return a3;
    return v9;
  }
  else
  {
    TagFromTagID = SdbGetTagFromTagID(a1, v4);
    AslLogCallPrintf(1, "SdbReadWORDTag", 172, "TagID 0x%X, Tag 0x%X not of the expected type", v4, TagFromTagID);
    return a3;
  }
}

```

## disassembly

```asm
0x140013e60  mov     [rsp+arg_0], rbx
0x140013e65  mov     [rsp+arg_8], rsi
0x140013e6a  push    rdi
0x140013e6b  sub     rsp, 30h
0x140013e6f  movzx   edi, r8w
0x140013e73  mov     [rsp+38h+arg_10], r8w
0x140013e79  mov     ebx, edx
0x140013e7b  mov     rsi, rcx
0x140013e7e  call    SdbGetTagFromTagID
0x140013e83  mov     ecx, 0F000h
0x140013e88  mov     edx, ebx
0x140013e8a  and     ax, cx
0x140013e8d  mov     ecx, 3000h
0x140013e92  cmp     ax, cx
0x140013e95  mov     rcx, rsi
0x140013e98  jz      short loc_140013ECD
0x140013e9a  call    SdbGetTagFromTagID
0x140013e9f  movzx   eax, ax
0x140013ea2  lea     r9, aTagid0xXTag0xX; "TagID 0x%X, Tag 0x%X not of the expecte"...
0x140013ea9  mov     [rsp+38h+var_10], eax
0x140013ead  lea     rdx, aSdbreadwordtag; "SdbReadWORDTag"
0x140013eb4  mov     r8d, 0ACh
0x140013eba  mov     [rsp+38h+var_18], ebx
0x140013ebe  mov     ecx, 1
0x140013ec3  call    AslLogCallPrintf
0x140013ec8  movzx   eax, di
0x140013ecb  jmp     short loc_140013EEB
0x140013ecd  mov     r9d, 2
0x140013ed3  lea     r8, [rsp+38h+arg_10]
0x140013ed8  call    SdbpReadTagData
0x140013edd  movzx   ecx, [rsp+38h+arg_10]
0x140013ee2  test    eax, eax
0x140013ee4  cmovz   cx, di
0x140013ee8  movzx   eax, cx
0x140013eeb  mov     rbx, [rsp+38h+arg_0]
0x140013ef0  mov     rsi, [rsp+38h+arg_8]
0x140013ef5  add     rsp, 30h
0x140013ef9  pop     rdi
0x140013efa  retn
```
