# CGallery::_AddElementToGallery(DirectUI::Element *,DirectUI::Element *,int)

- ea: `0x180020dd0`
- end: `0x180020e91`
- name: `?_AddElementToGallery@CGallery@@AEAAJPEAVElement@DirectUI@@0H@Z`
- size: `193`
- prototype: `int(CGallery *__hidden this, struct DirectUI::Element *, struct DirectUI::Element *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800214d8`

## callees

- `0x180020dd0`
- `0x180055074`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e30`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020e1e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020e1e`
- `DUI70!StrToID` at `0x180020e0c`
- `DUI70!StrToID` at `0x180020e0c`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180020e55`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180020e55`

## pseudocode

```c
__int64 __fastcall CGallery::_AddElementToGallery(
        CGallery *this,
        struct DirectUI::Element *a2,
        struct DirectUI::Element *a3,
        int a4)
{
  __int64 v8; // rax
  void *v9; // rbp
  unsigned __int16 v10; // ax
  DirectUI::Element *Descendent; // rbx
  int v12; // ecx
  int inserted; // eax

  if ( a3 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1), 2);
    v9 = (void *)v8;
    if ( v8 )
    {
      v10 = StrToID(v8);
      Descendent = DirectUI::Element::FindDescendent(a3, v10);
      CoTaskMemFree(v9);
    }
    else
    {
      Descendent = 0;
    }
  }
  else
  {
    Descendent = *(DirectUI::Element **)this;
  }
  v12 = -2147467259;
  if ( Descendent )
  {
    v12 = DirectUI::Element::Add(Descendent, a2);
    if ( v12 >= 0 )
    {
      inserted = DPA_InsertPtr(*((HDPA *)this + 4), a4, a2);
      v12 = 0;
      if ( inserted == -1 )
        return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180020dd0  push    rbx
0x180020dd2  push    rbp
0x180020dd3  push    rsi
0x180020dd4  push    rdi
0x180020dd5  push    r14
0x180020dd7  sub     rsp, 20h
0x180020ddb  mov     r14d, r9d
0x180020dde  mov     rbx, r8
0x180020de1  mov     rsi, rdx
0x180020de4  mov     rdi, rcx
0x180020de7  test    r8, r8
0x180020dea  jz      short loc_180020E42
0x180020dec  mov     rcx, [rcx+8]
0x180020df0  mov     edx, 2
0x180020df5  mov     rax, [rcx]
0x180020df8  mov     rax, [rax+8]
0x180020dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e01  mov     rbp, rax
0x180020e04  test    rax, rax
0x180020e07  jz      short loc_180020E3E
0x180020e09  mov     rcx, rax
0x180020e0c  call    cs:__imp_StrToID
0x180020e13  nop     dword ptr [rax+rax+00h]
0x180020e18  movzx   edx, ax
0x180020e1b  mov     rcx, rbx
0x180020e1e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180020e25  nop     dword ptr [rax+rax+00h]
0x180020e2a  mov     rcx, rbp; pv
0x180020e2d  mov     rbx, rax
0x180020e30  call    cs:__imp_CoTaskMemFree
0x180020e37  nop     dword ptr [rax+rax+00h]
0x180020e3c  jmp     short loc_180020E45
0x180020e3e  xor     ebx, ebx
0x180020e40  jmp     short loc_180020E45
0x180020e42  mov     rbx, [rcx]
0x180020e45  mov     ecx, 80004005h
0x180020e4a  test    rbx, rbx
0x180020e4d  jz      short loc_180020E83
0x180020e4f  mov     rdx, rsi
0x180020e52  mov     rcx, rbx
0x180020e55  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180020e5c  nop     dword ptr [rax+rax+00h]
0x180020e61  mov     ecx, eax
0x180020e63  test    eax, eax
0x180020e65  js      short loc_180020E83
0x180020e67  mov     rcx, [rdi+20h]; hdpa
0x180020e6b  mov     r8, rsi; p
0x180020e6e  mov     edx, r14d; i
0x180020e71  call    DPA_InsertPtr
0x180020e76  xor     ecx, ecx
0x180020e78  mov     edx, 8007000Eh
0x180020e7d  cmp     eax, 0FFFFFFFFh
0x180020e80  cmovz   ecx, edx
0x180020e83  mov     eax, ecx
0x180020e85  add     rsp, 20h
0x180020e89  pop     r14
0x180020e8b  pop     rdi
0x180020e8c  pop     rsi
0x180020e8d  pop     rbp
0x180020e8e  pop     rbx
0x180020e8f  retn
```
