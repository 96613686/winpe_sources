# CSetImageFeedDialog::_SetDialogDUI(DirectUI::Element *)

- ea: `0x1800d6b9c`
- end: `0x1800d6d03`
- name: `?_SetDialogDUI@CSetImageFeedDialog@@AEAAJPEAVElement@DirectUI@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(CSetImageFeedDialog *__hidden this, struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d596c`

## callees

- `0x180054130`
- `0x1800d6b9c`
- `0x1800e19f8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d6be6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800d6be6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6ccf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6ccf`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800d6c2d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800d6cbc`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800d6c2d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800d6cbc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800d6c19`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800d6ca8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800d6c19`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800d6ca8`
- `DUI70!StrToID` at `0x1800d6c07`
- `DUI70!StrToID` at `0x1800d6c96`
- `DUI70!StrToID` at `0x1800d6c07`
- `DUI70!StrToID` at `0x1800d6c96`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSetImageFeedDialog::_SetDialogDUI(CSetImageFeedDialog *this, struct DirectUI::Element *a2)
{
  int v4; // ebx
  unsigned __int16 v5; // ax
  DirectUI::Element *Descendent; // rax
  int v7; // r8d
  unsigned __int16 v8; // ax
  DirectUI::Element *v9; // rax
  void *v11; // [rsp+20h] [rbp-248h]
  LPVOID pv[2]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( *((_DWORD *)this + 6) == 38918 )
  {
    if ( LoadStringW(&_ImageBase, 0x95B7u, Buffer, 260) > 0 )
    {
      v5 = StrToID(L"idContent");
      Descendent = DirectUI::Element::FindDescendent(a2, v5);
      return (unsigned int)DirectUI::Element::SetContentString(Descendent, Buffer);
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    v4 = -2147467259;
    if ( *((_DWORD *)this + 6) == 38919 )
    {
      pv[0] = 0;
      CoTaskMemFree(0);
      v4 = TResourceStringAllocCopyEx<unsigned short *>(
             (int)&_ImageBase,
             *((_DWORD *)this + 9),
             v7,
             (int)&ResourceStringAllocCopyExCoAlloc,
             v11,
             pv);
      if ( v4 >= 0 )
      {
        v8 = StrToID(L"idContent");
        v9 = DirectUI::Element::FindDescendent(a2, v8);
        v4 = DirectUI::Element::SetContentString(v9, (const unsigned __int16 *)pv[0]);
      }
      CoTaskMemFree(pv[0]);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800d6b9c  mov     [rsp+arg_10], rbx
0x1800d6ba1  mov     [rsp+arg_18], rsi
0x1800d6ba6  push    rdi
0x1800d6ba7  sub     rsp, 260h
0x1800d6bae  mov     rax, cs:__security_cookie
0x1800d6bb5  xor     rax, rsp
0x1800d6bb8  mov     [rsp+268h+var_18], rax
0x1800d6bc0  mov     rsi, rdx
0x1800d6bc3  mov     rdi, rcx
0x1800d6bc6  cmp     dword ptr [rcx+18h], 9806h
0x1800d6bcd  jnz     short loc_1800D6C40
0x1800d6bcf  mov     r9d, 104h; cchBufferMax
0x1800d6bd5  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x1800d6bda  mov     edx, 95B7h; uID
0x1800d6bdf  lea     rcx, __ImageBase; hInstance
0x1800d6be6  call    cs:__imp_LoadStringW
0x1800d6bed  nop     dword ptr [rax+rax+00h]
0x1800d6bf2  test    eax, eax
0x1800d6bf4  jg      short loc_1800D6C00
0x1800d6bf6  mov     ebx, 80004005h
0x1800d6bfb  jmp     loc_1800D6CDB
0x1800d6c00  lea     rcx, aIdcontent; "idContent"
0x1800d6c07  call    cs:__imp_StrToID
0x1800d6c0e  nop     dword ptr [rax+rax+00h]
0x1800d6c13  movzx   edx, ax
0x1800d6c16  mov     rcx, rsi
0x1800d6c19  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800d6c20  nop     dword ptr [rax+rax+00h]
0x1800d6c25  lea     rdx, [rsp+268h+Buffer]
0x1800d6c2a  mov     rcx, rax
0x1800d6c2d  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800d6c34  nop     dword ptr [rax+rax+00h]
0x1800d6c39  mov     ebx, eax
0x1800d6c3b  jmp     loc_1800D6CDB
0x1800d6c40  mov     ebx, 80004005h
0x1800d6c45  cmp     dword ptr [rcx+18h], 9807h
0x1800d6c4c  jnz     loc_1800D6CDB
0x1800d6c52  mov     [rsp+268h+pv], 0
0x1800d6c5b  xor     ecx, ecx; pv
0x1800d6c5d  call    cs:__imp_CoTaskMemFree
0x1800d6c64  nop     dword ptr [rax+rax+00h]
0x1800d6c69  lea     rax, [rsp+268h+pv]
0x1800d6c6e  mov     [rsp+268h+var_240], rax; void *
0x1800d6c73  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x1800d6c7a  mov     edx, [rdi+24h]; int
0x1800d6c7d  lea     rcx, __ImageBase; int
0x1800d6c84  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x1800d6c89  mov     ebx, eax
0x1800d6c8b  test    eax, eax
0x1800d6c8d  js      short loc_1800D6CCA
0x1800d6c8f  lea     rcx, aIdcontent; "idContent"
0x1800d6c96  call    cs:__imp_StrToID
0x1800d6c9d  nop     dword ptr [rax+rax+00h]
0x1800d6ca2  movzx   edx, ax
0x1800d6ca5  mov     rcx, rsi
0x1800d6ca8  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800d6caf  nop     dword ptr [rax+rax+00h]
0x1800d6cb4  mov     rdx, [rsp+268h+pv]
0x1800d6cb9  mov     rcx, rax
0x1800d6cbc  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x1800d6cc3  nop     dword ptr [rax+rax+00h]
0x1800d6cc8  mov     ebx, eax
0x1800d6cca  mov     rcx, [rsp+268h+pv]; pv
0x1800d6ccf  call    cs:__imp_CoTaskMemFree
0x1800d6cd6  nop     dword ptr [rax+rax+00h]
0x1800d6cdb  mov     eax, ebx
0x1800d6cdd  mov     rcx, [rsp+268h+var_18]
0x1800d6ce5  xor     rcx, rsp; StackCookie
0x1800d6ce8  call    __security_check_cookie
0x1800d6ced  lea     r11, [rsp+268h+var_8]
0x1800d6cf5  mov     rbx, [r11+20h]
0x1800d6cf9  mov     rsi, [r11+28h]
0x1800d6cfd  mov     rsp, r11
0x1800d6d00  pop     rdi
0x1800d6d01  retn
```
