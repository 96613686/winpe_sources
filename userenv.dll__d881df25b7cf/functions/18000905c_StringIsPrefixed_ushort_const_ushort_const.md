# StringIsPrefixed(ushort const *,ushort const *)

- ea: `0x18000905c`
- end: `0x1800090b1`
- name: `?StringIsPrefixed@@YAHPEBG0@Z`
- size: `85`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008fe4`
- `0x18000bd3c`
- `0x18001b334`

## callees

- `0x18000905c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000909e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000909e`

## pseudocode

```c
__int64 __fastcall StringIsPrefixed(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rdx
  unsigned int v4; // ebx

  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  if ( v3 > 0x7FFFFFFF )
    return 0;
  v4 = 1;
  if ( CompareStringOrdinal(a1, v3, a2, v3, 1) != 2 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18000905c  mov     [rsp+arg_0], rbx
0x180009061  push    rdi
0x180009062  sub     rsp, 30h
0x180009066  mov     r8, rdx; lpString2
0x180009069  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000906d  xor     edi, edi
0x18000906f  inc     rdx; cchCount1
0x180009072  cmp     [r8+rdx*2], di
0x180009077  jnz     short loc_18000906F
0x180009079  cmp     rdx, 7FFFFFFFh
0x180009080  jbe     short loc_180009092
0x180009082  mov     ebx, edi
0x180009084  mov     eax, ebx
0x180009086  mov     rbx, [rsp+38h+arg_0]
0x18000908b  add     rsp, 30h
0x18000908f  pop     rdi
0x180009090  retn
0x180009092  mov     ebx, 1
0x180009097  mov     r9d, edx; cchCount2
0x18000909a  mov     [rsp+38h+bIgnoreCase], ebx; bIgnoreCase
0x18000909e  call    cs:__imp_CompareStringOrdinal
0x1800090a5  nop     dword ptr [rax+rax+00h]
0x1800090aa  cmp     eax, 2
0x1800090ad  jz      short loc_180009084
0x1800090af  jmp     short loc_180009082
```
