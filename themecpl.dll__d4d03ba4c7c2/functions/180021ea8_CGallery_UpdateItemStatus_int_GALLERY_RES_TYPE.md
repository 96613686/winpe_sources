# CGallery::_UpdateItemStatus(int,GALLERY_RES_TYPE)

- ea: `0x180021ea8`
- end: `0x180021f43`
- name: `?_UpdateItemStatus@CGallery@@AEAAJHW4GALLERY_RES_TYPE@@@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800213e8`

## callees

- `0x180021ea8`
- `0x180021f4c`
- `0x18005501c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f24`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180021f13`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180021f13`

## pseudocode

```c
__int64 __fastcall CGallery::_UpdateItemStatus(__int64 a1, int a2, unsigned int a3)
{
  struct DirectUI::Element *Ptr; // rax
  DirectUI::Element *v6; // rsi
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi

  Ptr = (struct DirectUI::Element *)DPA_GetPtr(*(HDPA *)(a1 + 32), a2);
  v6 = Ptr;
  if ( Ptr )
  {
    if ( a3 == 5 )
    {
      v7 = 0;
      CGallery::_UpdateSelectedItemStatus((CGallery *)a1, Ptr);
    }
    else
    {
      v8 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(
                                       *(_QWORD *)(a1 + 8),
                                       a3);
      v9 = (unsigned __int16 *)v8;
      if ( v8 )
        v7 = DirectUI::Element::SetClass(v6, v8);
      else
        v7 = -2147467259;
      CoTaskMemFree(v9);
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v7;
}

```

## disassembly

```asm
0x180021ea8  mov     [rsp+arg_0], rbx
0x180021ead  mov     [rsp+arg_8], rsi
0x180021eb2  push    rdi
0x180021eb3  sub     rsp, 20h
0x180021eb7  mov     rdi, rcx
0x180021eba  movsxd  rdx, edx; i
0x180021ebd  mov     rcx, [rcx+20h]; hdpa
0x180021ec1  mov     ebx, r8d
0x180021ec4  call    DPA_GetPtr
0x180021ec9  mov     rsi, rax
0x180021ecc  test    rax, rax
0x180021ecf  jnz     short loc_180021ED8
0x180021ed1  mov     ebx, 80004005h
0x180021ed6  jmp     short loc_180021F30
0x180021ed8  cmp     ebx, 5
0x180021edb  jnz     short loc_180021EEC
0x180021edd  xor     ebx, ebx
0x180021edf  mov     rdx, rsi; struct DirectUI::Element *
0x180021ee2  mov     rcx, rdi; this
0x180021ee5  call    ?_UpdateSelectedItemStatus@CGallery@@AEAAJPEAVElement@DirectUI@@@Z; CGallery::_UpdateSelectedItemStatus(DirectUI::Element *)
0x180021eea  jmp     short loc_180021F30
0x180021eec  mov     rcx, [rdi+8]
0x180021ef0  mov     edx, ebx
0x180021ef2  mov     rax, [rcx]
0x180021ef5  mov     rax, [rax+8]
0x180021ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021efe  mov     rdi, rax
0x180021f01  test    rax, rax
0x180021f04  jnz     short loc_180021F0D
0x180021f06  mov     ebx, 80004005h
0x180021f0b  jmp     short loc_180021F21
0x180021f0d  mov     rdx, rdi
0x180021f10  mov     rcx, rsi
0x180021f13  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x180021f1a  nop     dword ptr [rax+rax+00h]
0x180021f1f  mov     ebx, eax
0x180021f21  mov     rcx, rdi; pv
0x180021f24  call    cs:__imp_CoTaskMemFree
0x180021f2b  nop     dword ptr [rax+rax+00h]
0x180021f30  mov     rsi, [rsp+28h+arg_8]
0x180021f35  mov     eax, ebx
0x180021f37  mov     rbx, [rsp+28h+arg_0]
0x180021f3c  add     rsp, 20h
0x180021f40  pop     rdi
0x180021f41  retn
```
