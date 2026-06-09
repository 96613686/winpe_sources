# CDeliveryAgent::SubscriptionControl(IUnknown *,ulong)

- ea: `0x1800058f0`
- end: `0x180005975`
- name: `?SubscriptionControl@CDeliveryAgent@@UEAAJPEAUIUnknown@@K@Z`
- size: `133`
- prototype: `__int64 __fastcall(CDeliveryAgent *__hidden this, struct IUnknown *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800058f0`
- `0x18001d9bc`
- `0x18002a010`

## import_xrefs

- `WININET!DeleteUrlCacheGroup` at `0x180005957`
- `WININET!DeleteUrlCacheGroup` at `0x180005957`

## pseudocode

```c
__int64 __fastcall CDeliveryAgent::SubscriptionControl(CDeliveryAgent *this, struct IUnknown *a2, char a3)
{
  struct IUnknownVtbl *lpVtbl; // rax
  GROUPID GroupId[3]; // [rsp+20h] [rbp-18h] BYREF
  struct ISubscriptionItem *v6; // [rsp+58h] [rbp+20h] BYREF

  if ( (a3 & 1) != 0 )
  {
    lpVtbl = a2->lpVtbl;
    GroupId[0] = 0;
    v6 = 0;
    ((void (__fastcall *)(struct IUnknown *, GUID *, struct ISubscriptionItem **))lpVtbl->QueryInterface)(
      a2,
      &IID_ISubscriptionItem,
      &v6);
    if ( v6 )
    {
      if ( (int)ReadLONGLONG(v6, L"GroupID", GroupId) >= 0 && GroupId[0] )
        DeleteUrlCacheGroup(GroupId[0], 0, 0);
      ((void (__fastcall *)(struct ISubscriptionItem *))v6->lpVtbl->Release)(v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800058f0  sub     rsp, 38h
0x1800058f4  mov     r9, rdx
0x1800058f7  test    r8b, 1
0x1800058fb  jz      short loc_18000596E
0x1800058fd  mov     rax, [rdx]
0x180005900  lea     r8, [rsp+38h+arg_18]
0x180005905  lea     rdx, IID_ISubscriptionItem
0x18000590c  mov     [rsp+38h+GroupId], 0
0x180005915  mov     rcx, r9
0x180005918  mov     [rsp+38h+arg_18], 0
0x180005921  mov     rax, [rax]
0x180005924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005929  mov     rcx, [rsp+38h+arg_18]; struct ISubscriptionItem *
0x18000592e  test    rcx, rcx
0x180005931  jz      short loc_18000596E
0x180005933  lea     r8, [rsp+38h+GroupId]; __int64 *
0x180005938  lea     rdx, ?c_szPropCrawlGroupID@@3QBGB; "GroupID"
0x18000593f  call    ?ReadLONGLONG@@YAJPEAUISubscriptionItem@@PEBGPEA_J@Z; ReadLONGLONG(ISubscriptionItem *,ushort const *,__int64 *)
0x180005944  test    eax, eax
0x180005946  js      short loc_18000595D
0x180005948  mov     rcx, [rsp+38h+GroupId]; GroupId
0x18000594d  test    rcx, rcx
0x180005950  jz      short loc_18000595D
0x180005952  xor     r8d, r8d; lpReserved
0x180005955  xor     edx, edx; dwFlags
0x180005957  call    cs:__imp_DeleteUrlCacheGroup
0x18000595d  mov     rcx, [rsp+38h+arg_18]
0x180005962  mov     rax, [rcx]
0x180005965  mov     rax, [rax+10h]
0x180005969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000596e  xor     eax, eax
0x180005970  add     rsp, 38h
0x180005974  retn
```
