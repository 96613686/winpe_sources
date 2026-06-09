# URI_LOCK_LIST::FindNextLock(CPubIterator *)

- ea: `0x1800038f0`
- end: `0x180003934`
- name: `?FindNextLock@URI_LOCK_LIST@@UEAAPEAVIPubLock@@PEAVCPubIterator@@@Z`
- size: `68`
- prototype: `struct IPubLock *__fastcall(URI_LOCK_LIST *__hidden this, struct CPubIterator *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800038f0`

## pseudocode

```c
struct IPubLock *__fastcall URI_LOCK_LIST::FindNextLock(URI_LOCK_LIST *this, struct CPubIterator *a2)
{
  __int64 v2; // r8
  unsigned int v3; // r9d
  struct IPubLock *result; // rax

  v2 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 )
  {
    v3 = *((_DWORD *)a2 + 2);
    if ( v3 < *(_DWORD *)(v2 + 648) )
    {
LABEL_5:
      result = *(struct IPubLock **)(v2 + 40LL * v3);
      *((_DWORD *)a2 + 2) = v3 + 1;
      return result;
    }
    v2 = *(_QWORD *)(v2 + 640);
    *(_QWORD *)a2 = v2;
    *((_DWORD *)a2 + 2) = 0;
    if ( v2 )
    {
      v3 = 0;
      goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800038f0  mov     r8, [rdx]
0x1800038f3  test    r8, r8
0x1800038f6  jz      short loc_180003931
0x1800038f8  mov     r9d, [rdx+8]
0x1800038fc  cmp     r9d, [r8+288h]
0x180003903  jb      short loc_18000391E
0x180003905  mov     r8, [r8+280h]
0x18000390c  mov     [rdx], r8
0x18000390f  mov     dword ptr [rdx+8], 0
0x180003916  test    r8, r8
0x180003919  jz      short loc_180003931
0x18000391b  xor     r9d, r9d
0x18000391e  mov     eax, r9d
0x180003921  lea     rcx, [rax+rax*4]
0x180003925  mov     rax, [r8+rcx*8]
0x180003929  lea     ecx, [r9+1]
0x18000392d  mov     [rdx+8], ecx
0x180003930  retn
0x180003931  xor     eax, eax
0x180003933  retn
```
