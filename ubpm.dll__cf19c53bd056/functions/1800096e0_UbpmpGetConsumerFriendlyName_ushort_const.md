# UbpmpGetConsumerFriendlyName(ushort const *)

- ea: `0x1800096e0`
- end: `0x180009747`
- name: `?UbpmpGetConsumerFriendlyName@@YAPEBGPEBG@Z`
- size: `103`
- prototype: `const unsigned __int16 *__fastcall(PCNZWCH lpString1)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004f40`
- `0x180008f30`
- `0x18001a8a8`
- `0x18002e764`
- `0x18002ecd8`

## callees

- `0x1800096e0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009734`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009734`

## string_xrefs

- `0x18000970d`: `NT TASK`

## pseudocode

```c
PCNZWCH __fastcall UbpmpGetConsumerFriendlyName(PCNZWCH lpString1)
{
  PCNZWCH v1; // rbx
  __int64 v2; // rax

  v1 = lpString1;
  if ( lpString1 )
  {
    v2 = -1;
    do
      ++v2;
    while ( lpString1[v2] );
    if ( (unsigned int)v2 > 8 && CompareStringW(0x7Fu, 1u, lpString1, 7, L"NT TASK", 7) == 2 )
      v1 += 7;
  }
  return v1;
}

```

## disassembly

```asm
0x1800096e0  push    rbx
0x1800096e2  sub     rsp, 30h
0x1800096e6  mov     rbx, rcx
0x1800096e9  test    rcx, rcx
0x1800096ec  jz      short loc_180009704
0x1800096ee  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800096f5  inc     rax
0x1800096f8  cmp     word ptr [rcx+rax*2], 0
0x1800096fd  jnz     short loc_1800096F5
0x1800096ff  cmp     eax, 8
0x180009702  ja      short loc_18000970D
0x180009704  mov     rax, rbx
0x180009707  add     rsp, 30h
0x18000970b  pop     rbx
0x18000970c  retn
0x18000970d  lea     rax, String2; "NT TASK"
0x180009714  mov     [rsp+38h+cchCount2], 7; cchCount2
0x18000971c  mov     r9d, 7; cchCount1
0x180009722  mov     [rsp+38h+lpString2], rax; lpString2
0x180009727  mov     r8, rbx; lpString1
0x18000972a  mov     edx, 1; dwCmpFlags
0x18000972f  mov     ecx, 7Fh; Locale
0x180009734  call    cs:__imp_CompareStringW
0x18000973a  cmp     eax, 2
0x18000973d  lea     rcx, [rbx+0Eh]
0x180009741  cmovz   rbx, rcx
0x180009745  jmp     short loc_180009704
```
