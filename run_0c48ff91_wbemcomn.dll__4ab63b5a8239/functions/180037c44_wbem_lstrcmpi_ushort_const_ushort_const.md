# wbem_lstrcmpi(ushort const *,ushort const *)

- ea: `0x180037c44`
- end: `0x180037c89`
- name: `?wbem_lstrcmpi@@YAHPEBG0@Z`
- size: `69`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f4c0`
- `0x18000f990`
- `0x180037950`

## callees

- `0x180037c44`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180037c68`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180037c68`

## pseudocode

```c
__int64 __fastcall wbem_lstrcmpi(PCNZWCH lpString1, PCNZWCH lpString2)
{
  unsigned int v2; // ebx
  int v3; // eax

  v2 = 1;
  v3 = CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1);
  if ( v3 == 2 )
    return 0;
  if ( v3 == 1 )
    return (unsigned int)-1;
  return v2;
}

```

## disassembly

```asm
0x180037c44  mov     [rsp+arg_0], rbx
0x180037c49  push    rdi
0x180037c4a  sub     rsp, 30h
0x180037c4e  or      edi, 0FFFFFFFFh
0x180037c51  mov     r8, rcx; lpString1
0x180037c54  mov     [rsp+38h+cchCount2], edi; cchCount2
0x180037c58  mov     r9d, edi; cchCount1
0x180037c5b  mov     [rsp+38h+lpString2], rdx; lpString2
0x180037c60  lea     ebx, [rdi+2]
0x180037c63  mov     edx, ebx; dwCmpFlags
0x180037c65  lea     ecx, [rbx+7Eh]; Locale
0x180037c68  call    cs:__imp_CompareStringW
0x180037c6e  cmp     eax, 2
0x180037c71  jnz     short loc_180037C77
0x180037c73  xor     eax, eax
0x180037c75  jmp     short loc_180037C7E
0x180037c77  cmp     eax, ebx
0x180037c79  cmovz   ebx, edi
0x180037c7c  mov     eax, ebx
0x180037c7e  mov     rbx, [rsp+38h+arg_0]
0x180037c83  add     rsp, 30h
0x180037c87  pop     rdi
0x180037c88  retn
```
