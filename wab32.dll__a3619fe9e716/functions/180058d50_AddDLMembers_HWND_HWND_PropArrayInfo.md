# AddDLMembers(HWND__ *,HWND__ *,_PropArrayInfo *)

- ea: `0x180058d50`
- end: `0x1800590a8`
- name: `?AddDLMembers@@YAXPEAUHWND__@@0PEAU_PropArrayInfo@@@Z`
- size: `856`
- prototype: `void __fastcall(HWND, HWND, struct _PropArrayInfo *)`
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x18005abf0`

## callees

- `0x180002818`
- `0x180006f7c`
- `0x180008f74`
- `0x18000ca5c`
- `0x1800133d0`
- `0x1800135a8`
- `0x180016268`
- `0x180034b60`
- `0x180058d50`
- `0x1800590b0`
- `0x180059d88`
- `0x180061820`
- `0x180062928`
- `0x180069f38`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `USER32!LoadStringW` at `0x180058e1d`
- `USER32!LoadStringW` at `0x180058e1d`
- `USER32!SendMessageW` at `0x180058fe3`
- `USER32!SendMessageW` at `0x180058fe3`
- `USER32!EnableWindow` at `0x180058e5a`
- `USER32!EnableWindow` at `0x180058fcf`
- `USER32!EnableWindow` at `0x180059003`
- `USER32!EnableWindow` at `0x180059011`
- `USER32!EnableWindow` at `0x180058e5a`
- `USER32!EnableWindow` at `0x180058fcf`
- `USER32!EnableWindow` at `0x180059003`
- `USER32!EnableWindow` at `0x180059011`
- `USER32!GetDlgItem` at `0x180058ff5`
- `USER32!GetDlgItem` at `0x180058ff5`
- `USER32!UpdateWindow` at `0x18005901a`
- `USER32!UpdateWindow` at `0x18005901a`
- `USER32!LoadCursorW` at `0x180058e67`
- `USER32!LoadCursorW` at `0x180058e67`
- `USER32!SetCursor` at `0x180058e70`
- `USER32!SetCursor` at `0x180059028`
- `USER32!SetCursor` at `0x180058e70`
- `USER32!SetCursor` at `0x180059028`

## pseudocode

```c
void __fastcall AddDLMembers(HWND a1, HWND a2, struct _PropArrayInfo *a3)
{
  HCURSOR v6; // r13
  HCURSOR CursorW; // rax
  HCURSOR v8; // rax
  struct _ADRLIST *v9; // r12
  unsigned __int16 *v10; // rcx
  struct ENTRYID *v11; // rbx
  ULONG v12; // r14d
  int v13; // eax
  HWND DlgItem; // rax
  size_t Size; // [rsp+20h] [rbp-E0h]
  struct IContact *v16; // [rsp+30h] [rbp-D0h] BYREF
  struct IContactCollection *v17; // [rsp+38h] [rbp-C8h] BYREF
  struct _ADRLIST *v18; // [rsp+40h] [rbp-C0h] BYREF
  struct _SBinary v19; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v20[2]; // [rsp+58h] [rbp-A8h] BYREF
  void *v21; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v22[3]; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+88h] [rbp-78h] BYREF
  struct ENTRYID *v24; // [rsp+90h] [rbp-70h] BYREF
  int v25; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v26; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[200]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v28[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v29[264]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v30[264]; // [rsp+680h] [rbp+580h] BYREF

  v18 = 0;
  *(_QWORD *)&v19.cb = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  v6 = 0;
  v17 = 0;
  v16 = 0;
  STRW::STRW((STRW *)&v25, v28, 0x104u);
  STRW::STRW((STRW *)&v23, v29, 0x104u);
  STRW::STRW((STRW *)&v21, v30, 0x104u);
  v20[0] = &CGroupList::`vftable';
  v20[1] = 0;
  LoadStringW(hinstMapiX, 0xFBEu, Buffer, 200);
  if ( (int)CPeoplePicker::SelectContacts(a1, Buffer, &v17) >= 0
    && (int)HrCreateAdrListFromLV(*((struct IAddrBook **)a3 + 12), a2, &v18) >= 0 )
  {
    EnableWindow(a1, 0);
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    v8 = SetCursor(CursorW);
    v9 = v18;
    v6 = v8;
    while ( !((unsigned int (__fastcall *)(struct IContactCollection *))v17->lpVtbl->Next)(v17) )
    {
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v16);
      if ( ((int (__fastcall *)(struct IContactCollection *, struct IContact **))v17->lpVtbl->GetCurrent)(v17, &v16) < 0
        || GetIDFromContact(v16, (struct STRW *)&v25) < 0 )
      {
        break;
      }
      v10 = (unsigned __int16 *)&Str;
      if ( v25 )
        v10 = v26;
      if ( (int)GenerateEntryIDFromContactID(v10, (struct STRW *)&v23) < 0 )
        break;
      v11 = (struct ENTRYID *)&Str;
      if ( v23 )
        v11 = v24;
      v19.lpb = (LPBYTE)v11;
      v12 = 2 * v23 + 2;
      v19.cb = v12;
      if ( !v9 || !(unsigned int)CheckForDupes(v9, v9->cEntries, &v19) )
      {
        LODWORD(Size) = *(_DWORD *)a3;
        v13 = CheckForCycle(
                *((struct IAddrBook **)a3 + 12),
                v11,
                v12,
                *((struct ENTRYID *const *)a3 + 1),
                Size,
                (struct CGroupList *)v20);
        if ( v13 < 0 )
          break;
        if ( v13 == 1 )
        {
          GetDisplayNameFromContact(v16, &v21);
          if ( (_DWORD)v21 )
            ShowMessageBoxParam(a1, 0xFC1u, 16, v22[0]);
        }
        else
        {
          AddWABEntryToListView(*((struct IAddrBook **)a3 + 12), a2, v12, v11, (struct _RecipientInfo **)a3 + 22);
          *((_DWORD *)a3 + 9) = 1;
        }
      }
    }
  }
  EnableWindow(a1, 1);
  if ( (int)SendMessageW(a2, 0x1004u, 0, 0) > 0 )
  {
    DlgItem = GetDlgItem(a1, 2364);
    EnableWindow(DlgItem, 1);
    EnableWindow(a2, 1);
  }
  UpdateWindow(a2);
  if ( v6 )
    SetCursor(v6);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v17);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v16);
  CGroupList::~CGroupList((CGroupList *)v20);
  LODWORD(v21) = 0;
  BUFFER::ReleaseStorage((BUFFER *)v22);
  v23 = 0;
  BUFFER::ReleaseStorage((BUFFER *)&v24);
  v25 = 0;
  BUFFER::ReleaseStorage((BUFFER *)&v26);
}

```

## disassembly

```asm
0x180058d50  mov     [rsp-8+arg_18], rbx
0x180058d55  push    rbp
0x180058d56  push    rsi
0x180058d57  push    rdi
0x180058d58  push    r12
0x180058d5a  push    r13
0x180058d5c  push    r14
0x180058d5e  push    r15
0x180058d60  lea     rbp, [rsp-7A0h]
0x180058d68  sub     rsp, 8A0h
0x180058d6f  mov     rax, cs:__security_cookie
0x180058d76  xor     rax, rsp
0x180058d79  mov     [rbp+7D0h+var_40], rax
0x180058d80  mov     rdi, r8
0x180058d83  mov     [rsp+8D0h+var_890], 0
0x180058d8c  mov     rsi, rdx
0x180058d8f  mov     qword ptr [rsp+8D0h+var_888.cb], 0
0x180058d98  mov     r15, rcx
0x180058d9b  xor     edx, edx; Val
0x180058d9d  mov     r8d, 190h; Size
0x180058da3  lea     rcx, [rbp+7D0h+Buffer]; void *
0x180058da7  call    memset_0
0x180058dac  xor     r13d, r13d
0x180058daf  lea     rdx, [rbp+7D0h+var_670]; unsigned __int16 *
0x180058db6  mov     ebx, 104h
0x180058dbb  mov     [rsp+8D0h+var_898], r13
0x180058dc0  mov     r8d, ebx; unsigned int
0x180058dc3  mov     [rsp+8D0h+var_8A0], r13
0x180058dc8  lea     rcx, [rbp+7D0h+var_828]; this
0x180058dcc  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180058dd1  mov     r8d, ebx; unsigned int
0x180058dd4  lea     rcx, [rbp+7D0h+var_848]; this
0x180058dd8  lea     rdx, [rbp+7D0h+var_460]; unsigned __int16 *
0x180058ddf  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180058de4  mov     r8d, ebx; unsigned int
0x180058de7  lea     rcx, [rsp+8D0h+var_868]; this
0x180058dec  lea     rdx, [rbp+7D0h+var_250]; unsigned __int16 *
0x180058df3  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x180058df8  mov     rcx, cs:hinstMapiX; hInstance
0x180058dff  lea     rdx, ??_7CGroupList@@6B@; const CGroupList::`vftable'
0x180058e06  mov     [rsp+8D0h+var_878], rdx
0x180058e0b  lea     r9d, [rbx-3Ch]; cchBufferMax
0x180058e0f  mov     edx, 0FBEh; uID
0x180058e14  mov     [rsp+8D0h+var_870], r13
0x180058e19  lea     r8, [rbp+7D0h+Buffer]; lpBuffer
0x180058e1d  call    cs:__imp_LoadStringW
0x180058e23  lea     r8, [rsp+8D0h+var_898]; struct IContactCollection **
0x180058e28  mov     rcx, r15; HWND
0x180058e2b  lea     rdx, [rbp+7D0h+Buffer]; unsigned __int16 *
0x180058e2f  call    ?SelectContacts@CPeoplePicker@@SAJPEAUHWND__@@PEBGPEAPEAUIContactCollection@@@Z; CPeoplePicker::SelectContacts(HWND__ *,ushort const *,IContactCollection * *)
0x180058e34  test    eax, eax
0x180058e36  js      loc_180058FC7
0x180058e3c  mov     rcx, [rdi+60h]; struct IAddrBook *
0x180058e40  lea     r8, [rsp+8D0h+var_890]; struct _ADRLIST **
0x180058e45  mov     rdx, rsi; hWnd
0x180058e48  call    ?HrCreateAdrListFromLV@@YAJPEAUIAddrBook@@PEAUHWND__@@PEAPEAU_ADRLIST@@@Z; HrCreateAdrListFromLV(IAddrBook *,HWND__ *,_ADRLIST * *)
0x180058e4d  test    eax, eax
0x180058e4f  js      loc_180058FC7
0x180058e55  xor     edx, edx; bEnable
0x180058e57  mov     rcx, r15; hWnd
0x180058e5a  call    cs:__imp_EnableWindow
0x180058e60  mov     edx, 7F02h; lpCursorName
0x180058e65  xor     ecx, ecx; hInstance
0x180058e67  call    cs:__imp_LoadCursorW
0x180058e6d  mov     rcx, rax; hCursor
0x180058e70  call    cs:__imp_SetCursor
0x180058e76  mov     r12, [rsp+8D0h+var_890]
0x180058e7b  mov     r13, rax
0x180058e7e  mov     rdx, [rsp+8D0h+var_898]
0x180058e83  mov     rcx, [rdx]
0x180058e86  mov     rax, [rcx+20h]
0x180058e8a  mov     rcx, rdx
0x180058e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e92  test    eax, eax
0x180058e94  jnz     loc_180058FC7
0x180058e9a  lea     rcx, [rsp+8D0h+var_8A0]
0x180058e9f  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180058ea4  mov     rcx, [rsp+8D0h+var_898]
0x180058ea9  lea     rdx, [rsp+8D0h+var_8A0]
0x180058eae  mov     rax, [rcx]
0x180058eb1  mov     rax, [rax+28h]
0x180058eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058eba  test    eax, eax
0x180058ebc  js      loc_180058FC7
0x180058ec2  mov     rcx, [rsp+8D0h+var_8A0]; struct IContact *
0x180058ec7  lea     rdx, [rbp+7D0h+var_828]; struct STRW *
0x180058ecb  call    ?GetIDFromContact@@YAJPEAUIContact@@PEAVSTRW@@@Z; GetIDFromContact(IContact *,STRW *)
0x180058ed0  test    eax, eax
0x180058ed2  js      loc_180058FC7
0x180058ed8  cmp     [rbp+7D0h+var_828], 0
0x180058edc  lea     rcx, Str
0x180058ee3  lea     rdx, [rbp+7D0h+var_848]; this
0x180058ee7  cmovnz  rcx, [rbp+7D0h+var_820]; unsigned __int16 *
0x180058eec  call    ?GenerateEntryIDFromContactID@@YAJPEBGPEAVSTRW@@@Z; GenerateEntryIDFromContactID(ushort const *,STRW *)
0x180058ef1  test    eax, eax
0x180058ef3  js      loc_180058FC7
0x180058ef9  mov     eax, [rbp+7D0h+var_848]
0x180058efc  lea     rbx, Str
0x180058f03  test    eax, eax
0x180058f05  cmovnz  rbx, [rbp+7D0h+var_840]
0x180058f0a  mov     [rsp+8D0h+var_888.lpb], rbx
0x180058f0f  lea     r14d, ds:2[rax*2]
0x180058f17  mov     [rsp+8D0h+var_888.cb], r14d
0x180058f1c  test    r12, r12
0x180058f1f  jz      short loc_180058F3A
0x180058f21  mov     edx, [r12]; int
0x180058f25  lea     r8, [rsp+8D0h+var_888]; struct _SBinary *
0x180058f2a  mov     rcx, r12; struct _ADRLIST *
0x180058f2d  call    ?CheckForDupes@@YAHPEAU_ADRLIST@@HPEAU_SBinary@@@Z; CheckForDupes(_ADRLIST *,int,_SBinary *)
0x180058f32  test    eax, eax
0x180058f34  jnz     loc_180058E7E
0x180058f3a  mov     r9, [rdi+8]; struct ENTRYID *
0x180058f3e  lea     rax, [rsp+8D0h+var_878]
0x180058f43  mov     rcx, [rdi+60h]; struct IAddrBook *
0x180058f47  mov     r8d, r14d; unsigned int
0x180058f4a  mov     [rsp+8D0h+var_8A8], rax; struct CGroupList *
0x180058f4f  mov     rdx, rbx; struct ENTRYID *
0x180058f52  mov     eax, [rdi]
0x180058f54  mov     dword ptr [rsp+8D0h+Size], eax; Size
0x180058f58  call    ?CheckForCycle@@YAJPEAUIAddrBook@@QEAUENTRYID@@K1KPEAVCGroupList@@@Z; CheckForCycle(IAddrBook *,ENTRYID * const,ulong,ENTRYID * const,ulong,CGroupList *)
0x180058f5d  test    eax, eax
0x180058f5f  js      short loc_180058FC7
0x180058f61  cmp     eax, 1
0x180058f64  jnz     short loc_180058F9D
0x180058f66  mov     rcx, [rsp+8D0h+var_8A0]; struct IContact *
0x180058f6b  lea     rdx, [rsp+8D0h+var_868]; struct STRW *
0x180058f70  call    ?GetDisplayNameFromContact@@YAJPEAUIContact@@PEAVSTRW@@@Z; GetDisplayNameFromContact(IContact *,STRW *)
0x180058f75  cmp     dword ptr [rsp+8D0h+var_868], 0
0x180058f7a  jz      loc_180058E7E
0x180058f80  mov     r9, [rsp+8D0h+var_860]
0x180058f85  mov     edx, 0FC1h; uID
0x180058f8a  mov     r8d, 10h; int
0x180058f90  mov     rcx, r15; hWnd
0x180058f93  call    ?ShowMessageBoxParam@@YAHPEAUHWND__@@HHZZ; ShowMessageBoxParam(HWND__ *,int,int,...)
0x180058f98  jmp     loc_180058E7E
0x180058f9d  mov     rcx, [rdi+60h]; struct IAddrBook *
0x180058fa1  lea     rax, [rdi+0B0h]
0x180058fa8  mov     r9, rbx; struct ENTRYID *
0x180058fab  mov     [rsp+8D0h+Size], rax; struct _RecipientInfo **
0x180058fb0  mov     r8d, r14d; unsigned int
0x180058fb3  mov     rdx, rsi; HWND
0x180058fb6  call    ?AddWABEntryToListView@@YAHPEAUIAddrBook@@PEAUHWND__@@KPEAUENTRYID@@PEAPEAU_RecipientInfo@@@Z; AddWABEntryToListView(IAddrBook *,HWND__ *,ulong,ENTRYID *,_RecipientInfo * *)
0x180058fbb  mov     dword ptr [rdi+24h], 1
0x180058fc2  jmp     loc_180058E7E
0x180058fc7  mov     edx, 1; bEnable
0x180058fcc  mov     rcx, r15; hWnd
0x180058fcf  call    cs:__imp_EnableWindow
0x180058fd5  xor     r9d, r9d; lParam
0x180058fd8  xor     r8d, r8d; wParam
0x180058fdb  mov     edx, 1004h; Msg
0x180058fe0  mov     rcx, rsi; hWnd
0x180058fe3  call    cs:__imp_SendMessageW
0x180058fe9  test    eax, eax
0x180058feb  jle     short loc_180059017
0x180058fed  mov     edx, 93Ch; nIDDlgItem
0x180058ff2  mov     rcx, r15; hDlg
0x180058ff5  call    cs:__imp_GetDlgItem
0x180058ffb  mov     rcx, rax; hWnd
0x180058ffe  mov     edx, 1; bEnable
0x180059003  call    cs:__imp_EnableWindow
0x180059009  mov     edx, 1; bEnable
0x18005900e  mov     rcx, rsi; hWnd
0x180059011  call    cs:__imp_EnableWindow
0x180059017  mov     rcx, rsi; hWnd
0x18005901a  call    cs:__imp_UpdateWindow
0x180059020  test    r13, r13
0x180059023  jz      short loc_18005902E
0x180059025  mov     rcx, r13; hCursor
0x180059028  call    cs:__imp_SetCursor
0x18005902e  lea     rcx, [rsp+8D0h+var_898]
0x180059033  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180059038  lea     rcx, [rsp+8D0h+var_8A0]
0x18005903d  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180059042  lea     rcx, [rsp+8D0h+var_878]; this
0x180059047  call    ??1CGroupList@@UEAA@XZ; CGroupList::~CGroupList(void)
0x18005904c  lea     rcx, [rsp+8D0h+var_860]; this
0x180059051  mov     dword ptr [rsp+8D0h+var_868], 0
0x180059059  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18005905e  lea     rcx, [rbp+7D0h+var_840]; this
0x180059062  mov     [rbp+7D0h+var_848], 0
0x180059069  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18005906e  lea     rcx, [rbp+7D0h+var_820]; this
0x180059072  mov     [rbp+7D0h+var_828], 0
0x180059079  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18005907e  mov     rcx, [rbp+7D0h+var_40]
0x180059085  xor     rcx, rsp; StackCookie
0x180059088  call    __security_check_cookie
0x18005908d  mov     rbx, [rsp+8D0h+arg_18]
0x180059095  add     rsp, 8A0h
0x18005909c  pop     r15
0x18005909e  pop     r14
0x1800590a0  pop     r13
0x1800590a2  pop     r12
0x1800590a4  pop     rdi
0x1800590a5  pop     rsi
0x1800590a6  pop     rbp
0x1800590a7  retn
```
