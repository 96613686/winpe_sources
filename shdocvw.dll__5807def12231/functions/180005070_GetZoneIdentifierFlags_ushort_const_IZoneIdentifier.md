# GetZoneIdentifierFlags(ushort const *,IZoneIdentifier * *)

- ea: `0x180005070`
- end: `0x180005145`
- name: `?GetZoneIdentifierFlags@@YA?AW4ZONE_ID_FLAGS@@PEBGPEAPEAUIZoneIdentifier@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018824`

## callees

- `0x180005070`
- `0x18001a3f0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800050b3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800050b3`

## pseudocode

```c
__int64 __fastcall GetZoneIdentifierFlags(const unsigned __int16 *a1, void **a2)
{
  unsigned int v4; // edi
  unsigned int v5; // r8d
  const struct _GUID *v6; // r9
  int v7; // ebx
  void *v8; // rcx
  struct IUnknown *ppv; // [rsp+58h] [rbp+10h] BYREF
  void *v11; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  v4 = 0;
  v11 = 0;
  ppv = 0;
  if ( CoCreateInstance(
         &CLSID_PersistentZoneIdentifier,
         0,
         0x4001u,
         &GUID_cd45f185_1b21_48e2_967b_ead743a8914e,
         (LPVOID *)&ppv) < 0
    || (v7 = _AndLoadFromFile(ppv, a1, v5, v6, &v11),
        ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv),
        v7 < 0)
    || (LODWORD(ppv) = 0, (*(int (__fastcall **)(void *, struct IUnknown **))(*(_QWORD *)v11 + 24LL))(v11, &ppv) < 0) )
  {
    v8 = v11;
  }
  else
  {
    v4 = 1;
    v8 = 0;
    *a2 = v11;
  }
  if ( v8 )
  {
    v11 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return v4;
}

```

## disassembly

```asm
0x180005070  mov     [rsp+arg_0], rbx
0x180005075  push    rbp
0x180005076  push    rsi
0x180005077  push    rdi
0x180005078  sub     rsp, 30h
0x18000507c  mov     rsi, rdx
0x18000507f  mov     rbx, rcx
0x180005082  xor     ebp, ebp
0x180005084  mov     [rdx], rbp
0x180005087  mov     edi, ebp
0x180005089  mov     [rsp+48h+arg_10], rbp
0x18000508e  mov     [rsp+48h+arg_8], rbp
0x180005093  lea     rax, [rsp+48h+arg_8]
0x180005098  mov     [rsp+48h+ppv], rax; ppv
0x18000509d  lea     r9, _GUID_cd45f185_1b21_48e2_967b_ead743a8914e; riid
0x1800050a4  xor     edx, edx; pUnkOuter
0x1800050a6  mov     r8d, 4001h; dwClsContext
0x1800050ac  lea     rcx, CLSID_PersistentZoneIdentifier; rclsid
0x1800050b3  call    cs:__imp_CoCreateInstance
0x1800050b9  test    eax, eax
0x1800050bb  js      short loc_18000511A
0x1800050bd  lea     rax, [rsp+48h+arg_10]
0x1800050c2  mov     [rsp+48h+ppv], rax; void **
0x1800050c7  mov     rdx, rbx; unsigned __int16 *
0x1800050ca  mov     rcx, [rsp+48h+arg_8]; struct IUnknown *
0x1800050cf  call    ?_AndLoadFromFile@@YAJPEAUIUnknown@@PEBGKAEBU_GUID@@PEAPEAX@Z; _AndLoadFromFile(IUnknown *,ushort const *,ulong,_GUID const &,void * *)
0x1800050d4  mov     ebx, eax
0x1800050d6  mov     rcx, [rsp+48h+arg_8]
0x1800050db  mov     rdx, [rcx]
0x1800050de  mov     rax, [rdx+10h]
0x1800050e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e7  test    ebx, ebx
0x1800050e9  js      short loc_18000511A
0x1800050eb  mov     dword ptr [rsp+48h+arg_8], ebp
0x1800050ef  mov     rcx, [rsp+48h+arg_10]
0x1800050f4  mov     rax, [rcx]
0x1800050f7  lea     rdx, [rsp+48h+arg_8]
0x1800050fc  mov     rax, [rax+18h]
0x180005100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005105  test    eax, eax
0x180005107  js      short loc_18000511A
0x180005109  mov     edi, 1
0x18000510e  mov     rax, [rsp+48h+arg_10]
0x180005113  mov     ecx, ebp
0x180005115  mov     [rsi], rax
0x180005118  jmp     short loc_18000511F
0x18000511a  mov     rcx, [rsp+48h+arg_10]
0x18000511f  test    rcx, rcx
0x180005122  jz      short loc_180005136
0x180005124  mov     [rsp+48h+arg_10], rbp
0x180005129  mov     rdx, [rcx]
0x18000512c  mov     rax, [rdx+10h]
0x180005130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005135  nop
0x180005136  mov     eax, edi
0x180005138  mov     rbx, [rsp+48h+arg_0]
0x18000513d  add     rsp, 30h
0x180005141  pop     rdi
0x180005142  pop     rsi
0x180005143  pop     rbp
0x180005144  retn
```
