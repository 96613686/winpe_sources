# DllUnregisterServer

- ea: `0x1800071e0`
- end: `0x18000725d`
- name: `DllUnregisterServer`
- size: `125`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180005980`
- `0x1800071e0`
- `0x18000e010`

## import_xrefs

- `CRYPT32!CryptSIPRemoveProvider` at `0x1800071f1`
- `CRYPT32!CryptSIPRemoveProvider` at `0x1800071fe`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18000720b`
- `CRYPT32!CryptSIPRemoveProvider` at `0x1800071f1`
- `CRYPT32!CryptSIPRemoveProvider` at `0x1800071fe`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18000720b`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  int v0; // edi
  struct TaClassTable near **v1; // rbx
  struct TaClassTable near *v2; // rax

  CryptSIPRemoveProvider((GUID *)&OID_VBSSIP);
  CryptSIPRemoveProvider((GUID *)&OID_JSSIP);
  CryptSIPRemoveProvider((GUID *)&OID_WSFSIP);
  UnregisterSignControl();
  v0 = 0;
  v1 = &g_TaClassTable;
  if ( (_DWORD)g_TaClassTable )
  {
    do
    {
      v2 = v1[1];
      if ( v2 && ((int (__fastcall *)(struct TaClassTable near *, _QWORD))v2)(v1[2], 0) < 0 )
        ++v0;
      v1 += 3;
    }
    while ( *(_DWORD *)v1 );
  }
  return v0 >= 1;
}

```

## disassembly

```asm
0x1800071e0  mov     [rsp+arg_0], rbx
0x1800071e5  push    rdi
0x1800071e6  sub     rsp, 20h
0x1800071ea  lea     rcx, OID_VBSSIP; pgProv
0x1800071f1  call    cs:__imp_CryptSIPRemoveProvider
0x1800071f7  lea     rcx, OID_JSSIP; pgProv
0x1800071fe  call    cs:__imp_CryptSIPRemoveProvider
0x180007204  lea     rcx, OID_WSFSIP; pgProv
0x18000720b  call    cs:__imp_CryptSIPRemoveProvider
0x180007211  call    ?UnregisterSignControl@@YAJXZ; UnregisterSignControl(void)
0x180007216  xor     edi, edi
0x180007218  lea     rbx, ?g_TaClassTable@@3PAUTaClassTable@@A; TaClassTable near * g_TaClassTable
0x18000721f  cmp     cs:?g_TaClassTable@@3PAUTaClassTable@@A, edi; TaClassTable near * g_TaClassTable
0x180007225  jz      short loc_18000724A
0x180007227  mov     rax, [rbx+8]
0x18000722b  test    rax, rax
0x18000722e  jz      short loc_180007241
0x180007230  mov     rcx, [rbx+10h]
0x180007234  xor     edx, edx
0x180007236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000723b  test    eax, eax
0x18000723d  jns     short loc_180007241
0x18000723f  inc     edi
0x180007241  add     rbx, 18h
0x180007245  cmp     dword ptr [rbx], 0
0x180007248  jnz     short loc_180007227
0x18000724a  mov     rbx, [rsp+28h+arg_0]
0x18000724f  xor     eax, eax
0x180007251  cmp     edi, 1
0x180007254  setnl   al
0x180007257  add     rsp, 20h
0x18000725b  pop     rdi
0x18000725c  retn
```
