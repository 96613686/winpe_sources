# FreeAliasStructure(_ALIAS_GENERAL_INFORMATION *,int)

- ea: `0x1800106d0`
- end: `0x18001073d`
- name: `?FreeAliasStructure@@YAJPEAU_ALIAS_GENERAL_INFORMATION@@H@Z`
- size: `109`
- prototype: `__int64 __fastcall(struct _ALIAS_GENERAL_INFORMATION *pv, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005e60`
- `0x180014d90`

## callees

- `0x1800106d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001072c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001072c`

## pseudocode

```c
__int64 __fastcall FreeAliasStructure(struct _ALIAS_GENERAL_INFORMATION *pv, int a2)
{
  unsigned int v4; // edi
  void *v5; // rcx
  void *v6; // rcx

  if ( pv )
  {
    v4 = 0;
    if ( *((_WORD *)pv + 1) )
    {
      v5 = (void *)*((_QWORD *)pv + 1);
      if ( v5 )
        CoTaskMemFree(v5);
    }
    *(_DWORD *)pv = 0;
    *((_QWORD *)pv + 1) = 0;
    if ( *((_WORD *)pv + 13) )
    {
      v6 = (void *)*((_QWORD *)pv + 4);
      if ( v6 )
        CoTaskMemFree(v6);
    }
    *((_DWORD *)pv + 6) = 0;
    *((_QWORD *)pv + 4) = 0;
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
0x1800106d0  push    rbx
0x1800106d2  push    rbp
0x1800106d3  push    rsi
0x1800106d4  push    rdi
0x1800106d5  sub     rsp, 28h
0x1800106d9  xor     ebp, ebp
0x1800106db  mov     esi, edx
0x1800106dd  mov     rbx, rcx
0x1800106e0  test    rcx, rcx
0x1800106e3  jnz     short loc_1800106EC
0x1800106e5  mov     edi, 80004003h
0x1800106ea  jmp     short loc_180010732
0x1800106ec  mov     edi, ebp
0x1800106ee  cmp     [rcx+2], bp
0x1800106f2  jbe     short loc_180010703
0x1800106f4  mov     rcx, [rcx+8]; pv
0x1800106f8  test    rcx, rcx
0x1800106fb  jz      short loc_180010703
0x1800106fd  call    cs:__imp_CoTaskMemFree
0x180010703  mov     [rbx], ebp
0x180010705  mov     [rbx+8], rbp
0x180010709  cmp     [rbx+1Ah], bp
0x18001070d  jbe     short loc_18001071E
0x18001070f  mov     rcx, [rbx+20h]; pv
0x180010713  test    rcx, rcx
0x180010716  jz      short loc_18001071E
0x180010718  call    cs:__imp_CoTaskMemFree
0x18001071e  mov     [rbx+18h], ebp
0x180010721  mov     [rbx+20h], rbp
0x180010725  test    esi, esi
0x180010727  jz      short loc_180010732
0x180010729  mov     rcx, rbx; pv
0x18001072c  call    cs:__imp_CoTaskMemFree
0x180010732  mov     eax, edi
0x180010734  add     rsp, 28h
0x180010738  pop     rdi
0x180010739  pop     rsi
0x18001073a  pop     rbp
0x18001073b  pop     rbx
0x18001073c  retn
```
