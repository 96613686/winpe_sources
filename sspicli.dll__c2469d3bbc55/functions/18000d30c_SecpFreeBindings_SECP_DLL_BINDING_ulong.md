# SecpFreeBindings(_SECP_DLL_BINDING * *,ulong)

- ea: `0x18000d30c`
- end: `0x18000d351`
- name: `?SecpFreeBindings@@YAXPEAPEAU_SECP_DLL_BINDING@@K@Z`
- size: `69`
- prototype: `void __fastcall(struct _SECP_DLL_BINDING **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d0f0`

## callees

- `0x18000d2b0`
- `0x18000d30c`

## pseudocode

```c
void __fastcall SecpFreeBindings(struct _SECP_DLL_BINDING **a1)
{
  unsigned int v1; // edi
  __int64 v2; // rbx
  _QWORD *i; // r14
  HLOCAL *v4; // rcx

  v1 = SecPackageDllCount;
  v2 = 0;
  for ( i = SecPackageDllList; (unsigned int)v2 < v1; v2 = (unsigned int)(v2 + 1) )
  {
    v4 = (HLOCAL *)i[v2];
    if ( v4 )
    {
      SecpDerefDll(v4);
      i[v2] = 0;
    }
  }
}

```

## disassembly

```asm
0x18000d30c  push    rbx
0x18000d30e  push    rsi
0x18000d30f  push    rdi
0x18000d310  push    r14
0x18000d312  sub     rsp, 28h
0x18000d316  mov     edi, cs:?SecPackageDllCount@@3KA; ulong SecPackageDllCount
0x18000d31c  xor     ebx, ebx
0x18000d31e  mov     r14, cs:?SecPackageDllList@@3PEAPEAU_SECP_DLL_BINDING@@EA; _SECP_DLL_BINDING * * SecPackageDllList
0x18000d325  test    edi, edi
0x18000d327  jz      short loc_18000D338
0x18000d329  mov     rcx, [r14+rbx*8]; hMem
0x18000d32d  test    rcx, rcx
0x18000d330  jnz     short loc_18000D342
0x18000d332  inc     ebx
0x18000d334  cmp     ebx, edi
0x18000d336  jb      short loc_18000D329
0x18000d338  add     rsp, 28h
0x18000d33c  pop     r14
0x18000d33e  pop     rdi
0x18000d33f  pop     rsi
0x18000d340  pop     rbx
0x18000d341  retn
0x18000d342  call    ?SecpDerefDll@@YAXPEAU_SECP_DLL_BINDING@@@Z; SecpDerefDll(_SECP_DLL_BINDING *)
0x18000d347  mov     qword ptr [r14+rbx*8], 0
0x18000d34f  jmp     short loc_18000D332
```
