# CGallery::_ChangeFocus(int)

- ea: `0x1800213e8`
- end: `0x1800214d1`
- name: `?_ChangeFocus@CGallery@@AEAAJH@Z`
- size: `233`
- prototype: `__int64 __fastcall(CGallery *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180036314`
- `0x180038590`

## callees

- `0x1800213e8`
- `0x180021ea8`
- `0x18005501c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021488`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021488`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180021477`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180021477`

## pseudocode

```c
__int64 __fastcall CGallery::_ChangeFocus(CGallery *this, unsigned int a2)
{
  int updated; // ebx
  DirectUI::Element *Ptr; // rbx
  const unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rsi
  int v9; // [rsp+50h] [rbp+8h] BYREF

  v9 = 0;
  updated = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), &v9);
  if ( updated >= 0 && v9 != a2 )
  {
    if ( v9 == -1 )
      goto LABEL_11;
    Ptr = (DirectUI::Element *)DPA_GetPtr(*((HDPA *)this + 4), v9);
    if ( Ptr )
    {
      v6 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 8LL))(
                                       *((_QWORD *)this + 1),
                                       4);
      v7 = (unsigned __int16 *)v6;
      updated = v6 ? DirectUI::Element::SetClass(Ptr, v6) : -2147467259;
      CoTaskMemFree(v7);
    }
    else
    {
      updated = -2147467259;
    }
    if ( updated >= 0 )
    {
LABEL_11:
      updated = CGallery::_UpdateItemStatus((__int64)this, a2, 5u);
      if ( updated >= 0 )
        return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 136LL))(
                               *((_QWORD *)this + 1),
                               a2);
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800213e8  push    rbx
0x1800213ea  push    rbp
0x1800213eb  push    rsi
0x1800213ec  push    rdi
0x1800213ed  sub     rsp, 28h
0x1800213f1  mov     rdi, rcx
0x1800213f4  mov     [rsp+48h+arg_0], 0
0x1800213fc  mov     rcx, [rcx+8]
0x180021400  mov     ebp, edx
0x180021402  lea     rdx, [rsp+48h+arg_0]
0x180021407  mov     rax, [rcx]
0x18002140a  mov     rax, [rax+90h]
0x180021411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021416  mov     ebx, eax
0x180021418  test    eax, eax
0x18002141a  js      loc_1800214C5
0x180021420  movsxd  rax, [rsp+48h+arg_0]
0x180021425  cmp     eax, ebp
0x180021427  jz      loc_1800214C5
0x18002142d  cmp     eax, 0FFFFFFFFh
0x180021430  jz      short loc_180021498
0x180021432  mov     rcx, [rdi+20h]; hdpa
0x180021436  mov     rdx, rax; i
0x180021439  call    DPA_GetPtr
0x18002143e  mov     rbx, rax
0x180021441  test    rax, rax
0x180021444  jnz     short loc_18002144D
0x180021446  mov     ebx, 80004005h
0x18002144b  jmp     short loc_180021494
0x18002144d  mov     rcx, [rdi+8]
0x180021451  mov     edx, 4
0x180021456  mov     rax, [rcx]
0x180021459  mov     rax, [rax+8]
0x18002145d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021462  mov     rsi, rax
0x180021465  test    rax, rax
0x180021468  jnz     short loc_180021471
0x18002146a  mov     ebx, 80004005h
0x18002146f  jmp     short loc_180021485
0x180021471  mov     rdx, rsi
0x180021474  mov     rcx, rbx
0x180021477  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x18002147e  nop     dword ptr [rax+rax+00h]
0x180021483  mov     ebx, eax
0x180021485  mov     rcx, rsi; pv
0x180021488  call    cs:__imp_CoTaskMemFree
0x18002148f  nop     dword ptr [rax+rax+00h]
0x180021494  test    ebx, ebx
0x180021496  js      short loc_1800214C5
0x180021498  mov     r8d, 5
0x18002149e  mov     edx, ebp
0x1800214a0  mov     rcx, rdi
0x1800214a3  call    ?_UpdateItemStatus@CGallery@@AEAAJHW4GALLERY_RES_TYPE@@@Z; CGallery::_UpdateItemStatus(int,GALLERY_RES_TYPE)
0x1800214a8  mov     ebx, eax
0x1800214aa  test    eax, eax
0x1800214ac  js      short loc_1800214C5
0x1800214ae  mov     rcx, [rdi+8]
0x1800214b2  mov     edx, ebp
0x1800214b4  mov     rax, [rcx]
0x1800214b7  mov     rax, [rax+88h]
0x1800214be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214c3  mov     ebx, eax
0x1800214c5  mov     eax, ebx
0x1800214c7  add     rsp, 28h
0x1800214cb  pop     rdi
0x1800214cc  pop     rsi
0x1800214cd  pop     rbp
0x1800214ce  pop     rbx
0x1800214cf  retn
```
