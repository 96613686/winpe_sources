# CGallery::_UpdateSelectedItemStatus(DirectUI::Element *)

- ea: `0x180021f4c`
- end: `0x18002202a`
- name: `?_UpdateSelectedItemStatus@CGallery@@AEAAJPEAVElement@DirectUI@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(CGallery *__hidden this, struct DirectUI::Element *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180020424`
- `0x1800214d8`
- `0x180021ea8`

## callees

- `0x180021f4c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002200b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002200b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180021fdc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180021fdc`
- `DUI70!StrToID` at `0x180021fca`
- `DUI70!StrToID` at `0x180021fca`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180021f84`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180021ff5`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180021f84`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x180021ff5`

## pseudocode

```c
__int64 __fastcall CGallery::_UpdateSelectedItemStatus(CGallery *this, struct DirectUI::Element *a2)
{
  const unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rdi
  unsigned __int16 *v6; // rdi
  unsigned int v7; // ebx
  unsigned __int16 v8; // ax
  DirectUI::Element *Descendent; // rax

  v4 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 8LL))(
                                   *((_QWORD *)this + 1),
                                   5);
  v5 = (unsigned __int16 *)v4;
  if ( v4
    && (DirectUI::Element::SetClass(a2, v4),
        CoTaskMemFree(v5),
        (v6 = (unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 8LL))(
                                    *((_QWORD *)this + 1),
                                    11)) != 0) )
  {
    v8 = StrToID(L"Name");
    Descendent = DirectUI::Element::FindDescendent(a2, v8);
    if ( Descendent )
    {
      v7 = 0;
      DirectUI::Element::SetClass(Descendent, v6);
    }
    else
    {
      v7 = -2147467259;
    }
    CoTaskMemFree(v6);
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
0x180021f4c  mov     [rsp+arg_0], rbx
0x180021f51  mov     [rsp+arg_8], rsi
0x180021f56  push    rdi
0x180021f57  sub     rsp, 20h
0x180021f5b  mov     rsi, rcx
0x180021f5e  mov     rbx, rdx
0x180021f61  mov     rcx, [rcx+8]
0x180021f65  mov     edx, 5
0x180021f6a  mov     rax, [rcx]
0x180021f6d  mov     rax, [rax+8]
0x180021f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f76  mov     rdi, rax
0x180021f79  test    rax, rax
0x180021f7c  jz      short loc_180021FBC
0x180021f7e  mov     rdx, rax
0x180021f81  mov     rcx, rbx
0x180021f84  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x180021f8b  nop     dword ptr [rax+rax+00h]
0x180021f90  mov     rcx, rdi; pv
0x180021f93  call    cs:__imp_CoTaskMemFree
0x180021f9a  nop     dword ptr [rax+rax+00h]
0x180021f9f  mov     rcx, [rsi+8]
0x180021fa3  mov     edx, 0Bh
0x180021fa8  mov     rax, [rcx]
0x180021fab  mov     rax, [rax+8]
0x180021faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fb4  mov     rdi, rax
0x180021fb7  test    rax, rax
0x180021fba  jnz     short loc_180021FC3
0x180021fbc  mov     ebx, 80004005h
0x180021fc1  jmp     short loc_180022017
0x180021fc3  lea     rcx, aName; "Name"
0x180021fca  call    cs:__imp_StrToID
0x180021fd1  nop     dword ptr [rax+rax+00h]
0x180021fd6  movzx   edx, ax
0x180021fd9  mov     rcx, rbx
0x180021fdc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180021fe3  nop     dword ptr [rax+rax+00h]
0x180021fe8  test    rax, rax
0x180021feb  jz      short loc_180022003
0x180021fed  xor     ebx, ebx
0x180021fef  mov     rdx, rdi
0x180021ff2  mov     rcx, rax
0x180021ff5  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x180021ffc  nop     dword ptr [rax+rax+00h]
0x180022001  jmp     short loc_180022008
0x180022003  mov     ebx, 80004005h
0x180022008  mov     rcx, rdi; pv
0x18002200b  call    cs:__imp_CoTaskMemFree
0x180022012  nop     dword ptr [rax+rax+00h]
0x180022017  mov     rsi, [rsp+28h+arg_8]
0x18002201c  mov     eax, ebx
0x18002201e  mov     rbx, [rsp+28h+arg_0]
0x180022023  add     rsp, 20h
0x180022027  pop     rdi
0x180022028  retn
```
