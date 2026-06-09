# SdbReadDWORDTag

- ea: `0x140013cb8`
- end: `0x140013d4d`
- name: `SdbReadDWORDTag`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `4`
- tags: ``

## callers

- `0x14001651c`
- `0x140018840`
- `0x14001a24c`
- `0x14001b4b0`
- `0x14001c290`
- `0x14001c730`
- `0x14001d494`
- `0x14001d808`
- `0x1400242ac`
- `0x14002b138`

## callees

- `0x14001008c`
- `0x140013cb8`
- `0x1400142e0`
- `0x140016148`

## string_xrefs

- `0x140013d03`: `SdbReadDWORDTag`

## pseudocode

```c
__int64 __fastcall SdbReadDWORDTag(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v4; // ebx
  unsigned __int16 TagFromTagID; // ax
  int v8; // eax
  unsigned int v9; // ecx
  unsigned int v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = a3;
  v4 = a2;
  if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) == 0x4000 )
  {
    v8 = SdbpReadTagData(a1, v4, &v10, 4u);
    v9 = v10;
    if ( !v8 )
      return a3;
    return v9;
  }
  else
  {
    TagFromTagID = SdbGetTagFromTagID(a1, v4);
    AslLogCallPrintf(1, "SdbReadDWORDTag", 179, "TagID 0x%X, Tag 0x%X not of the expected type", v4, TagFromTagID);
    return a3;
  }
}

```

## disassembly

```asm
0x140013cb8  mov     [rsp+arg_0], rbx
0x140013cbd  mov     [rsp+arg_8], rsi
0x140013cc2  push    rdi
0x140013cc3  sub     rsp, 30h
0x140013cc7  mov     edi, r8d
0x140013cca  mov     [rsp+38h+arg_10], r8d
0x140013ccf  mov     ebx, edx
0x140013cd1  mov     rsi, rcx
0x140013cd4  call    SdbGetTagFromTagID
0x140013cd9  mov     ecx, 0F000h
0x140013cde  mov     edx, ebx
0x140013ce0  and     ax, cx
0x140013ce3  mov     ecx, 4000h
0x140013ce8  cmp     ax, cx
0x140013ceb  mov     rcx, rsi
0x140013cee  jz      short loc_140013D22
0x140013cf0  call    SdbGetTagFromTagID
0x140013cf5  movzx   eax, ax
0x140013cf8  lea     r9, aTagid0xXTag0xX; "TagID 0x%X, Tag 0x%X not of the expecte"...
0x140013cff  mov     [rsp+38h+var_10], eax
0x140013d03  lea     rdx, aSdbreaddwordta; "SdbReadDWORDTag"
0x140013d0a  mov     r8d, 0B3h
0x140013d10  mov     [rsp+38h+var_18], ebx
0x140013d14  mov     ecx, 1
0x140013d19  call    AslLogCallPrintf
0x140013d1e  mov     eax, edi
0x140013d20  jmp     short loc_140013D3D
0x140013d22  mov     r9d, 4
0x140013d28  lea     r8, [rsp+38h+arg_10]
0x140013d2d  call    SdbpReadTagData
0x140013d32  mov     ecx, [rsp+38h+arg_10]
0x140013d36  test    eax, eax
0x140013d38  cmovz   ecx, edi
0x140013d3b  mov     eax, ecx
0x140013d3d  mov     rbx, [rsp+38h+arg_0]
0x140013d42  mov     rsi, [rsp+38h+arg_8]
0x140013d47  add     rsp, 30h
0x140013d4b  pop     rdi
0x140013d4c  retn
```
