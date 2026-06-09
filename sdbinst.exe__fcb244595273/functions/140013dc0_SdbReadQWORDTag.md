# SdbReadQWORDTag

- ea: `0x140013dc0`
- end: `0x140013e59`
- name: `SdbReadQWORDTag`
- size: `153`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x14001a24c`
- `0x14001c290`
- `0x14001c730`
- `0x14001d808`
- `0x14002b138`

## callees

- `0x14001008c`
- `0x140013dc0`
- `0x1400142e0`
- `0x140016148`

## string_xrefs

- `0x140013e0b`: `SdbReadQWORDTag`

## pseudocode

```c
__int64 __fastcall SdbReadQWORDTag(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // ebx
  unsigned __int16 TagFromTagID; // ax
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = a3;
  v4 = a2;
  if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) == 0x5000 )
  {
    v8 = SdbpReadTagData(a1, v4, &v10, 8u);
    v9 = v10;
    if ( !v8 )
      return a3;
    return v9;
  }
  else
  {
    TagFromTagID = SdbGetTagFromTagID(a1, v4);
    AslLogCallPrintf(1, "SdbReadQWORDTag", 186, "TagID 0x%X, Tag 0x%X not of the expected type", v4, TagFromTagID);
    return a3;
  }
}

```

## disassembly

```asm
0x140013dc0  mov     [rsp+arg_0], rbx
0x140013dc5  mov     [rsp+arg_8], rsi
0x140013dca  push    rdi
0x140013dcb  sub     rsp, 30h
0x140013dcf  mov     rdi, r8
0x140013dd2  mov     [rsp+38h+arg_10], r8
0x140013dd7  mov     ebx, edx
0x140013dd9  mov     rsi, rcx
0x140013ddc  call    SdbGetTagFromTagID
0x140013de1  mov     ecx, 0F000h
0x140013de6  mov     edx, ebx
0x140013de8  and     ax, cx
0x140013deb  mov     ecx, 5000h
0x140013df0  cmp     ax, cx
0x140013df3  mov     rcx, rsi
0x140013df6  jz      short loc_140013E2B
0x140013df8  call    SdbGetTagFromTagID
0x140013dfd  movzx   eax, ax
0x140013e00  lea     r9, aTagid0xXTag0xX; "TagID 0x%X, Tag 0x%X not of the expecte"...
0x140013e07  mov     [rsp+38h+var_10], eax
0x140013e0b  lea     rdx, aSdbreadqwordta; "SdbReadQWORDTag"
0x140013e12  mov     r8d, 0BAh
0x140013e18  mov     [rsp+38h+var_18], ebx
0x140013e1c  mov     ecx, 1
0x140013e21  call    AslLogCallPrintf
0x140013e26  mov     rax, rdi
0x140013e29  jmp     short loc_140013E49
0x140013e2b  mov     r9d, 8
0x140013e31  lea     r8, [rsp+38h+arg_10]
0x140013e36  call    SdbpReadTagData
0x140013e3b  mov     rcx, [rsp+38h+arg_10]
0x140013e40  test    eax, eax
0x140013e42  cmovz   rcx, rdi
0x140013e46  mov     rax, rcx
0x140013e49  mov     rbx, [rsp+38h+arg_0]
0x140013e4e  mov     rsi, [rsp+38h+arg_8]
0x140013e53  add     rsp, 30h
0x140013e57  pop     rdi
0x140013e58  retn
```
