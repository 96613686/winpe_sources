# SdbReadBYTETag

- ea: `0x140013b84`
- end: `0x140013c0e`
- name: `SdbReadBYTETag`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001c730`

## callees

- `0x14001008c`
- `0x140013b84`
- `0x1400142e0`
- `0x140016148`

## string_xrefs

- `0x140013bcc`: `SdbReadBYTETag`

## pseudocode

```c
char __fastcall SdbReadBYTETag(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  unsigned __int16 TagFromTagID; // ax
  int v6; // eax
  char v7; // [rsp+50h] [rbp+18h] BYREF

  v2 = a2;
  v7 = 0;
  if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) == 0x2000 )
  {
    v6 = SdbpReadTagData(a1, v2, &v7, 1u);
    return v6 != 0 ? v7 : 0;
  }
  else
  {
    TagFromTagID = SdbGetTagFromTagID(a1, v2);
    AslLogCallPrintf(1, "SdbReadBYTETag", 165, "TagID 0x%X, Tag 0x%X not of the expected type", v2, TagFromTagID);
    return 0;
  }
}

```

## disassembly

```asm
0x140013b84  mov     [rsp+arg_0], rbx
0x140013b89  mov     [rsp+arg_10], r8b
0x140013b8e  push    rdi
0x140013b8f  sub     rsp, 30h
0x140013b93  mov     ebx, edx
0x140013b95  mov     [rsp+38h+arg_10], 0
0x140013b9a  mov     rdi, rcx
0x140013b9d  call    SdbGetTagFromTagID
0x140013ba2  mov     ecx, 0F000h
0x140013ba7  mov     edx, ebx
0x140013ba9  and     ax, cx
0x140013bac  mov     ecx, 2000h
0x140013bb1  cmp     ax, cx
0x140013bb4  mov     rcx, rdi
0x140013bb7  jz      short loc_140013BEB
0x140013bb9  call    SdbGetTagFromTagID
0x140013bbe  movzx   eax, ax
0x140013bc1  lea     r9, aTagid0xXTag0xX; "TagID 0x%X, Tag 0x%X not of the expecte"...
0x140013bc8  mov     [rsp+38h+var_10], eax
0x140013bcc  lea     rdx, aSdbreadbytetag; "SdbReadBYTETag"
0x140013bd3  mov     r8d, 0A5h
0x140013bd9  mov     [rsp+38h+var_18], ebx
0x140013bdd  mov     ecx, 1
0x140013be2  call    AslLogCallPrintf
0x140013be7  xor     al, al
0x140013be9  jmp     short loc_140013C03
0x140013beb  mov     r9d, 1
0x140013bf1  lea     r8, [rsp+38h+arg_10]
0x140013bf6  call    SdbpReadTagData
0x140013bfb  neg     eax
0x140013bfd  sbb     al, al
0x140013bff  and     al, [rsp+38h+arg_10]
0x140013c03  mov     rbx, [rsp+38h+arg_0]
0x140013c08  add     rsp, 30h
0x140013c0c  pop     rdi
0x140013c0d  retn
```
