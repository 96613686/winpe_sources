# CGallery::_AddLinksToGallery(DirectUI::DUIXmlParser *,bool)

- ea: `0x180021138`
- end: `0x1800213e2`
- name: `?_AddLinksToGallery@CGallery@@AEAAJPEAVDUIXmlParser@DirectUI@@_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(CGallery *__hidden this, struct DirectUI::DUIXmlParser *, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020e98`

## callees

- `0x180002280`
- `0x180021138`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021228`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800212f4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180021228`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800212f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002123d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002123d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021304`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021278`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002135a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800213ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021278`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002135a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800213ac`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180021203`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800212ca`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180021203`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800212ca`
- `DUI70!StrToID` at `0x1800211ef`
- `DUI70!StrToID` at `0x1800212b6`
- `DUI70!StrToID` at `0x1800211ef`
- `DUI70!StrToID` at `0x1800212b6`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800211b5`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800211b5`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180021372`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180021372`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18002139d`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18002139d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180021267`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180021333`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180021267`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180021333`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18002134b`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18002134b`

## pseudocode

```c
__int64 __fastcall CGallery::_AddLinksToGallery(CGallery *this, struct DirectUI::DUIXmlParser *a2, char a3)
{
  unsigned __int16 *v6; // r14
  signed int v7; // ebx
  __int64 v8; // rax
  void *v9; // rdi
  unsigned __int16 v10; // ax
  DirectUI::Element *Descendent; // rbx
  signed int LastError; // eax
  __int64 v13; // rax
  void *v14; // rbp
  unsigned __int16 v15; // ax
  DirectUI::Element *v16; // rax
  DirectUI::Element *v17; // rdi
  signed int v18; // eax
  struct DirectUI::Element *v20; // [rsp+30h] [rbp-148h] BYREF
  WCHAR Buffer[128]; // [rsp+40h] [rbp-138h] BYREF

  v6 = (unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 8LL))(
                             *((_QWORD *)this + 1),
                             8);
  if ( v6 )
  {
    v20 = 0;
    v7 = DirectUI::DUIXmlParser::CreateElement(a2, v6, 0, 0, 0, &v20);
    if ( v7 < 0 )
    {
LABEL_29:
      CoTaskMemFree(v6);
      return (unsigned int)v7;
    }
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1), 10);
    v9 = (void *)v8;
    if ( !v8 )
      goto LABEL_14;
    v10 = StrToID(v8);
    Descendent = DirectUI::Element::FindDescendent(v20, v10);
    if ( LoadStringW(g_hinst, 0x1Du, Buffer, 128) )
    {
      v7 = DirectUI::Element::SetContentString(Descendent, Buffer);
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 >= 0 )
        v7 = -2147467259;
    }
    CoTaskMemFree(v9);
    if ( v7 < 0 )
      goto LABEL_27;
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1), 9);
    v14 = (void *)v13;
    if ( v13 )
    {
      v15 = StrToID(v13);
      v16 = DirectUI::Element::FindDescendent(v20, v15);
      v17 = v16;
      if ( a3 )
      {
        if ( LoadStringW(g_hinst, 0x1Cu, Buffer, 128) )
        {
          v7 = DirectUI::Element::SetContentString(v17, Buffer);
        }
        else
        {
          v18 = GetLastError();
          v7 = v18;
          if ( v18 > 0 )
            v7 = (unsigned __int16)v18 | 0x80070000;
          if ( v7 >= 0 )
            v7 = -2147467259;
        }
      }
      else
      {
        v7 = 0;
        DirectUI::Element::SetLayoutPos(v16, -3);
      }
      CoTaskMemFree(v14);
      if ( v7 >= 0 )
      {
        v7 = DirectUI::Element::Add(*(DirectUI::Element **)this, v20);
        if ( v7 >= 0 )
        {
          *((_QWORD *)this + 8) = v17;
          v20 = 0;
        }
      }
    }
    else
    {
LABEL_14:
      v7 = -2147024882;
    }
LABEL_27:
    if ( v20 )
      DirectUI::Element::Destroy(v20, 1);
    goto LABEL_29;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180021138  mov     [rsp+arg_10], rbx
0x18002113d  push    rbp
0x18002113e  push    rsi
0x18002113f  push    rdi
0x180021140  push    r14
0x180021142  push    r15
0x180021144  sub     rsp, 150h
0x18002114b  mov     rax, cs:__security_cookie
0x180021152  xor     rax, rsp
0x180021155  mov     [rsp+178h+var_38], rax
0x18002115d  mov     rsi, rcx
0x180021160  mov     rbx, rdx
0x180021163  mov     rcx, [rcx+8]
0x180021167  mov     edx, 8
0x18002116c  mov     r15b, r8b
0x18002116f  mov     rax, [rcx]
0x180021172  mov     rax, [rax+8]
0x180021176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002117b  mov     r14, rax
0x18002117e  test    rax, rax
0x180021181  jnz     short loc_18002118D
0x180021183  mov     ebx, 8007000Eh
0x180021188  jmp     loc_1800213B8
0x18002118d  lea     rax, [rsp+178h+var_148]
0x180021192  mov     [rsp+178h+var_148], 0
0x18002119b  mov     [rsp+178h+var_150], rax
0x1800211a0  xor     r9d, r9d
0x1800211a3  xor     r8d, r8d
0x1800211a6  mov     [rsp+178h+var_158], 0
0x1800211af  mov     rdx, r14
0x1800211b2  mov     rcx, rbx
0x1800211b5  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800211bc  nop     dword ptr [rax+rax+00h]
0x1800211c1  mov     ebx, eax
0x1800211c3  test    eax, eax
0x1800211c5  js      loc_1800213A9
0x1800211cb  mov     rcx, [rsi+8]
0x1800211cf  mov     edx, 0Ah
0x1800211d4  mov     rax, [rcx]
0x1800211d7  mov     rax, [rax+8]
0x1800211db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211e0  mov     rdi, rax
0x1800211e3  test    rax, rax
0x1800211e6  jz      loc_1800212A9
0x1800211ec  mov     rcx, rax
0x1800211ef  call    cs:__imp_StrToID
0x1800211f6  nop     dword ptr [rax+rax+00h]
0x1800211fb  mov     rcx, [rsp+178h+var_148]
0x180021200  movzx   edx, ax
0x180021203  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18002120a  nop     dword ptr [rax+rax+00h]
0x18002120f  mov     rcx, cs:g_hinst; hInstance
0x180021216  lea     r8, [rsp+178h+Buffer]; lpBuffer
0x18002121b  mov     r9d, 80h; cchBufferMax
0x180021221  mov     rbx, rax
0x180021224  lea     edx, [r9-63h]; uID
0x180021228  call    cs:__imp_LoadStringW
0x18002122f  nop     dword ptr [rax+rax+00h]
0x180021234  mov     ebp, 80004005h
0x180021239  test    eax, eax
0x18002123b  jnz     short loc_18002125F
0x18002123d  call    cs:__imp_GetLastError
0x180021244  nop     dword ptr [rax+rax+00h]
0x180021249  mov     ebx, eax
0x18002124b  test    eax, eax
0x18002124d  jle     short loc_180021258
0x18002124f  movzx   ebx, ax
0x180021252  or      ebx, 80070000h
0x180021258  test    ebx, ebx
0x18002125a  cmovns  ebx, ebp
0x18002125d  jmp     short loc_180021275
0x18002125f  lea     rdx, [rsp+178h+Buffer]
0x180021264  mov     rcx, rbx
0x180021267  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18002126e  nop     dword ptr [rax+rax+00h]
0x180021273  mov     ebx, eax
0x180021275  mov     rcx, rdi; pv
0x180021278  call    cs:__imp_CoTaskMemFree
0x18002127f  nop     dword ptr [rax+rax+00h]
0x180021284  test    ebx, ebx
0x180021286  js      loc_180021391
0x18002128c  mov     rcx, [rsi+8]
0x180021290  mov     edx, 9
0x180021295  mov     rax, [rcx]
0x180021298  mov     rax, [rax+8]
0x18002129c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212a1  mov     rbp, rax
0x1800212a4  test    rax, rax
0x1800212a7  jnz     short loc_1800212B3
0x1800212a9  mov     ebx, 8007000Eh
0x1800212ae  jmp     loc_180021391
0x1800212b3  mov     rcx, rbp
0x1800212b6  call    cs:__imp_StrToID
0x1800212bd  nop     dword ptr [rax+rax+00h]
0x1800212c2  mov     rcx, [rsp+178h+var_148]
0x1800212c7  movzx   edx, ax
0x1800212ca  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800212d1  nop     dword ptr [rax+rax+00h]
0x1800212d6  mov     rdi, rax
0x1800212d9  test    r15b, r15b
0x1800212dc  jz      short loc_180021343
0x1800212de  mov     rcx, cs:g_hinst; hInstance
0x1800212e5  lea     r8, [rsp+178h+Buffer]; lpBuffer
0x1800212ea  mov     r9d, 80h; cchBufferMax
0x1800212f0  lea     edx, [r9-64h]; uID
0x1800212f4  call    cs:__imp_LoadStringW
0x1800212fb  nop     dword ptr [rax+rax+00h]
0x180021300  test    eax, eax
0x180021302  jnz     short loc_18002132B
0x180021304  call    cs:__imp_GetLastError
0x18002130b  nop     dword ptr [rax+rax+00h]
0x180021310  mov     ebx, eax
0x180021312  test    eax, eax
0x180021314  jle     short loc_18002131F
0x180021316  movzx   ebx, ax
0x180021319  or      ebx, 80070000h
0x18002131f  test    ebx, ebx
0x180021321  mov     eax, 80004005h
0x180021326  cmovns  ebx, eax
0x180021329  jmp     short loc_180021357
0x18002132b  lea     rdx, [rsp+178h+Buffer]
0x180021330  mov     rcx, rdi
0x180021333  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18002133a  nop     dword ptr [rax+rax+00h]
0x18002133f  mov     ebx, eax
0x180021341  jmp     short loc_180021357
0x180021343  xor     ebx, ebx
0x180021345  mov     rcx, rdi
0x180021348  lea     edx, [rbx-3]
0x18002134b  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180021352  nop     dword ptr [rax+rax+00h]
0x180021357  mov     rcx, rbp; pv
0x18002135a  call    cs:__imp_CoTaskMemFree
0x180021361  nop     dword ptr [rax+rax+00h]
0x180021366  test    ebx, ebx
0x180021368  js      short loc_180021391
0x18002136a  mov     rdx, [rsp+178h+var_148]
0x18002136f  mov     rcx, [rsi]
0x180021372  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180021379  nop     dword ptr [rax+rax+00h]
0x18002137e  mov     ebx, eax
0x180021380  test    eax, eax
0x180021382  js      short loc_180021391
0x180021384  mov     [rsi+40h], rdi
0x180021388  mov     [rsp+178h+var_148], 0
0x180021391  mov     rcx, [rsp+178h+var_148]
0x180021396  test    rcx, rcx
0x180021399  jz      short loc_1800213A9
0x18002139b  mov     dl, 1
0x18002139d  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800213a4  nop     dword ptr [rax+rax+00h]
0x1800213a9  mov     rcx, r14; pv
0x1800213ac  call    cs:__imp_CoTaskMemFree
0x1800213b3  nop     dword ptr [rax+rax+00h]
0x1800213b8  mov     eax, ebx
0x1800213ba  mov     rcx, [rsp+178h+var_38]
0x1800213c2  xor     rcx, rsp; StackCookie
0x1800213c5  call    __security_check_cookie
0x1800213ca  mov     rbx, [rsp+178h+arg_10]
0x1800213d2  add     rsp, 150h
0x1800213d9  pop     r15
0x1800213db  pop     r14
0x1800213dd  pop     rdi
0x1800213de  pop     rsi
0x1800213df  pop     rbp
0x1800213e0  retn
```
