# FreeAliasExtStructure(_ALIAS_EXTENDED_INFORMATION *,int)

- ea: `0x18001066c`
- end: `0x1800106c8`
- name: `?FreeAliasExtStructure@@YAJPEAU_ALIAS_EXTENDED_INFORMATION@@H@Z`
- size: `92`
- prototype: `__int64 __fastcall(struct _ALIAS_EXTENDED_INFORMATION *pv, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005e60`
- `0x180014d90`

## callees

- `0x18001066c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001069c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001069c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106b0`

## pseudocode

```c
__int64 __fastcall FreeAliasExtStructure(struct _ALIAS_EXTENDED_INFORMATION *pv, int a2)
{
  unsigned int v4; // edi
  void *v5; // rcx

  if ( pv )
  {
    v4 = 0;
    if ( *((_DWORD *)pv + 2) )
    {
      v5 = (void *)*((_QWORD *)pv + 2);
      if ( v5 )
        CoTaskMemFree(v5);
    }
    *((_DWORD *)pv + 2) = 0;
    *((_QWORD *)pv + 2) = 0;
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
0x18001066c  mov     [rsp+arg_0], rbx
0x180010671  mov     [rsp+arg_8], rsi
0x180010676  push    rdi
0x180010677  sub     rsp, 20h
0x18001067b  mov     esi, edx
0x18001067d  mov     rbx, rcx
0x180010680  test    rcx, rcx
0x180010683  jnz     short loc_18001068C
0x180010685  mov     edi, 80004003h
0x18001068a  jmp     short loc_1800106B6
0x18001068c  xor     edi, edi
0x18001068e  cmp     [rcx+8], edi
0x180010691  jbe     short loc_1800106A2
0x180010693  mov     rcx, [rcx+10h]; pv
0x180010697  test    rcx, rcx
0x18001069a  jz      short loc_1800106A2
0x18001069c  call    cs:__imp_CoTaskMemFree
0x1800106a2  mov     [rbx+8], edi
0x1800106a5  mov     [rbx+10h], rdi
0x1800106a9  test    esi, esi
0x1800106ab  jz      short loc_1800106B6
0x1800106ad  mov     rcx, rbx; pv
0x1800106b0  call    cs:__imp_CoTaskMemFree
0x1800106b6  mov     rbx, [rsp+28h+arg_0]
0x1800106bb  mov     eax, edi
0x1800106bd  mov     rsi, [rsp+28h+arg_8]
0x1800106c2  add     rsp, 20h
0x1800106c6  pop     rdi
0x1800106c7  retn
```
