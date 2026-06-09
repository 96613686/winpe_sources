# FreeUserExtStructure(_USER_EXTENDED_INFORMATION *,int)

- ea: `0x180010744`
- end: `0x1800107cc`
- name: `?FreeUserExtStructure@@YAJPEAU_USER_EXTENDED_INFORMATION@@H@Z`
- size: `136`
- prototype: `__int64 __fastcall(struct _USER_EXTENDED_INFORMATION *pv, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180005e60`
- `0x180014d90`

## callees

- `0x180010744`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001078c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800107a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800107bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001078c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800107a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800107bb`

## pseudocode

```c
__int64 __fastcall FreeUserExtStructure(struct _USER_EXTENDED_INFORMATION *pv, int a2)
{
  unsigned int v4; // edi
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  if ( pv )
  {
    v4 = 0;
    if ( *((_WORD *)pv + 13) )
    {
      v5 = (void *)*((_QWORD *)pv + 4);
      if ( v5 )
        CoTaskMemFree(v5);
    }
    *((_DWORD *)pv + 6) = 0;
    *((_QWORD *)pv + 4) = 0;
    if ( *((_DWORD *)pv + 2) )
    {
      v6 = (void *)*((_QWORD *)pv + 2);
      if ( v6 )
        CoTaskMemFree(v6);
    }
    *((_DWORD *)pv + 2) = 0;
    *((_QWORD *)pv + 2) = 0;
    if ( *((_DWORD *)pv + 12) )
    {
      v7 = (void *)*((_QWORD *)pv + 7);
      if ( v7 )
        CoTaskMemFree(v7);
    }
    *((_DWORD *)pv + 12) = 0;
    *((_QWORD *)pv + 7) = 0;
    if ( a2 )
      CoTaskMemFree(pv);
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v4;
}

```

## disassembly

```asm
0x180010744  push    rbx
0x180010746  push    rbp
0x180010747  push    rsi
0x180010748  push    rdi
0x180010749  sub     rsp, 28h
0x18001074d  xor     ebp, ebp
0x18001074f  mov     esi, edx
0x180010751  mov     rbx, rcx
0x180010754  test    rcx, rcx
0x180010757  jnz     short loc_180010760
0x180010759  mov     edi, 80004003h
0x18001075e  jmp     short loc_1800107C1
0x180010760  mov     edi, ebp
0x180010762  cmp     [rcx+1Ah], bp
0x180010766  jbe     short loc_180010777
0x180010768  mov     rcx, [rcx+20h]; pv
0x18001076c  test    rcx, rcx
0x18001076f  jz      short loc_180010777
0x180010771  call    cs:__imp_CoTaskMemFree
0x180010777  mov     [rbx+18h], ebp
0x18001077a  mov     [rbx+20h], rbp
0x18001077e  cmp     [rbx+8], ebp
0x180010781  jbe     short loc_180010792
0x180010783  mov     rcx, [rbx+10h]; pv
0x180010787  test    rcx, rcx
0x18001078a  jz      short loc_180010792
0x18001078c  call    cs:__imp_CoTaskMemFree
0x180010792  mov     [rbx+8], ebp
0x180010795  mov     [rbx+10h], rbp
0x180010799  cmp     [rbx+30h], ebp
0x18001079c  jbe     short loc_1800107AD
0x18001079e  mov     rcx, [rbx+38h]; pv
0x1800107a2  test    rcx, rcx
0x1800107a5  jz      short loc_1800107AD
0x1800107a7  call    cs:__imp_CoTaskMemFree
0x1800107ad  mov     [rbx+30h], ebp
0x1800107b0  mov     [rbx+38h], rbp
0x1800107b4  test    esi, esi
0x1800107b6  jz      short loc_1800107C1
0x1800107b8  mov     rcx, rbx; pv
0x1800107bb  call    cs:__imp_CoTaskMemFree
0x1800107c1  mov     eax, edi
0x1800107c3  add     rsp, 28h
0x1800107c7  pop     rdi
0x1800107c8  pop     rsi
0x1800107c9  pop     rbp
0x1800107ca  pop     rbx
0x1800107cb  retn
```
