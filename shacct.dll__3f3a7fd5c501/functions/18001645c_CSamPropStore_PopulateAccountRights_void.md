# CSamPropStore::_PopulateAccountRights(void)

- ea: `0x18001645c`
- end: `0x1800164bf`
- name: `?_PopulateAccountRights@CSamPropStore@@AEAAJXZ`
- size: `99`
- prototype: `__int64 __fastcall(CSamPropStore *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003e20`
- `0x180015660`

## callees

- `0x180001e70`
- `0x180011ca4`
- `0x18001645c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800164ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800164ac`

## pseudocode

```c
__int64 __fastcall CSamPropStore::_PopulateAccountRights(CSamPropStore *this)
{
  int v1; // edi
  unsigned int v3; // edx
  void *v4; // rcx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  if ( !*((_DWORD *)this + 17) )
  {
    v3 = *((_DWORD *)this + 20);
    v4 = (void *)*((_QWORD *)this + 11);
    pv = 0;
    v1 = CSGetAccountSIDByRID(v4, v3, &pv);
    if ( v1 >= 0 )
    {
      v1 = CSGetAccountRights(pv, (_DWORD *)this + 16);
      if ( v1 >= 0 )
        *((_DWORD *)this + 17) = 1;
      CoTaskMemFree(pv);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001645c  mov     [rsp+arg_8], rbx
0x180016461  push    rdi
0x180016462  sub     rsp, 20h
0x180016466  xor     edi, edi
0x180016468  mov     rbx, rcx
0x18001646b  cmp     [rcx+44h], edi
0x18001646e  jnz     short loc_1800164B2
0x180016470  mov     edx, [rcx+50h]
0x180016473  lea     r8, [rsp+28h+pv]
0x180016478  mov     rcx, [rcx+58h]
0x18001647c  mov     [rsp+28h+pv], rdi
0x180016481  call    CSGetAccountSIDByRID
0x180016486  mov     edi, eax
0x180016488  test    eax, eax
0x18001648a  js      short loc_1800164B2
0x18001648c  mov     rcx, [rsp+28h+pv]; AccountSid
0x180016491  lea     rdx, [rbx+40h]
0x180016495  call    CSGetAccountRights
0x18001649a  mov     edi, eax
0x18001649c  test    eax, eax
0x18001649e  js      short loc_1800164A7
0x1800164a0  mov     dword ptr [rbx+44h], 1
0x1800164a7  mov     rcx, [rsp+28h+pv]; pv
0x1800164ac  call    cs:__imp_CoTaskMemFree
0x1800164b2  mov     rbx, [rsp+28h+arg_8]
0x1800164b7  mov     eax, edi
0x1800164b9  add     rsp, 20h
0x1800164bd  pop     rdi
0x1800164be  retn
```
