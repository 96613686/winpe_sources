# CTaskPageHost::_CreateUniqueElement(DirectUI::Element * *)

- ea: `0x18003a344`
- end: `0x18003a463`
- name: `?_CreateUniqueElement@CTaskPageHost@@AEAAJPEAPEAVElement@DirectUI@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(CTaskPageHost *__hidden this, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003a21c`

## callees

- `0x18003a344`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003a3eb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003a3eb`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003a3cf`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003a3cf`
- `DUI70!?Destroy@Layout@DirectUI@@QEAAXXZ` at `0x18003a428`
- `DUI70!?Destroy@Layout@DirectUI@@QEAAXXZ` at `0x18003a428`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003a415`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003a415`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x18003a407`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x18003a407`
- `DUI70!?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z` at `0x18003a3ad`
- `DUI70!?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z` at `0x18003a3ad`
- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x18003a395`
- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x18003a395`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x18003a377`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x18003a377`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18003a433`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18003a433`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18003a3fc`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18003a3fc`

## pseudocode

```c
__int64 __fastcall CTaskPageHost::_CreateUniqueElement(CTaskPageHost *this, struct DirectUI::Element **a2)
{
  HRESULT v3; // ebx
  struct DirectUI::Layout *v5; // [rsp+20h] [rbp-A8h] BYREF
  GUID pguid; // [rsp+28h] [rbp-A0h] BYREF
  OLECHAR sz[56]; // [rsp+40h] [rbp-88h] BYREF

  *a2 = 0;
  v3 = DirectUI::Element::Create(0, 0, 0, a2);
  if ( v3 < 0 )
    return (unsigned int)v3;
  v5 = 0;
  v3 = DirectUI::FillLayout::Create(&v5);
  if ( v3 < 0 )
  {
LABEL_9:
    DirectUI::Element::Destroy(*a2, 1);
    *a2 = 0;
    return (unsigned int)v3;
  }
  v3 = DirectUI::Element::SetLayout(*a2, v5);
  if ( v3 < 0 )
  {
    DirectUI::Layout::Destroy(v5);
    goto LABEL_9;
  }
  v5 = 0;
  pguid = 0;
  v3 = CoCreateGuid(&pguid);
  if ( v3 < 0 )
    goto LABEL_9;
  v3 = StringFromGUID2(&pguid, sz, 50);
  if ( v3 < 0 )
    goto LABEL_9;
  DirectUI::Element::SetVisible(*a2, 1);
  DirectUI::Element::SetAccessible(*a2, 1);
  v3 = DirectUI::Element::SetID(*a2, sz);
  if ( v3 < 0 )
    goto LABEL_9;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003a344  mov     [rsp+arg_0], rbx
0x18003a349  push    rdi
0x18003a34a  sub     rsp, 0C0h
0x18003a351  mov     rax, cs:__security_cookie
0x18003a358  xor     rax, rsp
0x18003a35b  mov     [rsp+0C8h+var_18], rax
0x18003a363  mov     rdi, rdx
0x18003a366  mov     qword ptr [rdx], 0
0x18003a36d  mov     r9, rdx
0x18003a370  xor     r8d, r8d
0x18003a373  xor     edx, edx
0x18003a375  xor     ecx, ecx
0x18003a377  call    cs:__imp_?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z; DirectUI::Element::Create(uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18003a37d  mov     ebx, eax
0x18003a37f  test    eax, eax
0x18003a381  js      loc_18003A440
0x18003a387  lea     rcx, [rsp+0C8h+var_A8]
0x18003a38c  mov     [rsp+0C8h+var_A8], 0
0x18003a395  call    cs:__imp_?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z; DirectUI::FillLayout::Create(DirectUI::Layout * *)
0x18003a39b  mov     ebx, eax
0x18003a39d  test    eax, eax
0x18003a39f  js      loc_18003A42E
0x18003a3a5  mov     rdx, [rsp+0C8h+var_A8]
0x18003a3aa  mov     rcx, [rdi]
0x18003a3ad  call    cs:__imp_?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z; DirectUI::Element::SetLayout(DirectUI::Layout *)
0x18003a3b3  mov     ebx, eax
0x18003a3b5  test    eax, eax
0x18003a3b7  js      short loc_18003A423
0x18003a3b9  xorps   xmm0, xmm0
0x18003a3bc  mov     [rsp+0C8h+var_A8], 0
0x18003a3c5  lea     rcx, [rsp+0C8h+pguid]; pguid
0x18003a3ca  movups  xmmword ptr [rsp+0C8h+pguid.Data1], xmm0
0x18003a3cf  call    cs:__imp_CoCreateGuid
0x18003a3d5  mov     ebx, eax
0x18003a3d7  test    eax, eax
0x18003a3d9  js      short loc_18003A42E
0x18003a3db  mov     r8d, 32h ; '2'; cchMax
0x18003a3e1  lea     rdx, [rsp+0C8h+sz]; lpsz
0x18003a3e6  lea     rcx, [rsp+0C8h+pguid]; rguid
0x18003a3eb  call    cs:__imp_StringFromGUID2
0x18003a3f1  mov     ebx, eax
0x18003a3f3  test    eax, eax
0x18003a3f5  js      short loc_18003A42E
0x18003a3f7  mov     rcx, [rdi]
0x18003a3fa  mov     dl, 1
0x18003a3fc  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18003a402  mov     rcx, [rdi]
0x18003a405  mov     dl, 1
0x18003a407  call    cs:__imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x18003a40d  mov     rcx, [rdi]
0x18003a410  lea     rdx, [rsp+0C8h+sz]
0x18003a415  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x18003a41b  mov     ebx, eax
0x18003a41d  test    eax, eax
0x18003a41f  jns     short loc_18003A440
0x18003a421  jmp     short loc_18003A42E
0x18003a423  mov     rcx, [rsp+0C8h+var_A8]
0x18003a428  call    cs:__imp_?Destroy@Layout@DirectUI@@QEAAXXZ; DirectUI::Layout::Destroy(void)
0x18003a42e  mov     rcx, [rdi]
0x18003a431  mov     dl, 1
0x18003a433  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18003a439  mov     qword ptr [rdi], 0
0x18003a440  mov     eax, ebx
0x18003a442  mov     rcx, [rsp+0C8h+var_18]
0x18003a44a  xor     rcx, rsp; StackCookie
0x18003a44d  call    __security_check_cookie
0x18003a452  mov     rbx, [rsp+0C8h+arg_0]
0x18003a45a  add     rsp, 0C0h
0x18003a461  pop     rdi
0x18003a462  retn
```
