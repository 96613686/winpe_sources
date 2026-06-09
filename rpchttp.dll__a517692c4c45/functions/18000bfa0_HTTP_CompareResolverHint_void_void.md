# HTTP_CompareResolverHint(void *,void *)

- ea: `0x18000bfa0`
- end: `0x18000bfd3`
- name: `?HTTP_CompareResolverHint@@YAHPEAX0@Z`
- size: `51`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000bfa0`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP_CompareResolverHint(_DWORD *a1, _DWORD *a2)
{
  int v2; // eax

  v2 = a1[7];
  if ( v2 != a2[7] )
    return 0;
  if ( v2 )
    return a1[8] == a2[8];
  return (*((__int64 (__fastcall **)(_DWORD *, _DWORD *, _DWORD *))pRuntimeImportTable + 98))(a1, a2, a1);
}

```

## disassembly

```asm
0x18000bfa0  mov     eax, [rcx+1Ch]
0x18000bfa3  mov     r8, rcx
0x18000bfa6  cmp     eax, [rdx+1Ch]
0x18000bfa9  jz      short loc_18000BFAF
0x18000bfab  xor     eax, eax
0x18000bfad  jmp     short locret_18000BFD2
0x18000bfaf  test    eax, eax
0x18000bfb1  jnz     short loc_18000BFC6
0x18000bfb3  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000bfba  mov     rax, [rax+310h]
0x18000bfc1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfc6  mov     ecx, [rdx+20h]
0x18000bfc9  xor     eax, eax
0x18000bfcb  cmp     [r8+20h], ecx
0x18000bfcf  setz    al
0x18000bfd2  retn
```
