# CFinishPage::OnSetActive(void)

- ea: `0x18003f5f0`
- end: `0x18003faac`
- name: `?OnSetActive@CFinishPage@@UEAAJXZ`
- size: `1212`
- prototype: `__int64 __fastcall(CFinishPage *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000d9a4`
- `0x180024c3c`
- `0x18003d010`
- `0x18003f5f0`
- `0x18003fc94`
- `0x18003ff0c`
- `0x18006088c`
- `0x1800608f0`
- `0x180063bc8`
- `0x180063d40`
- `0x18006de1c`
- `0x18007510c`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f72a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f7e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f7f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f98f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f72a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f7e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f7f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f98f`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003f8af`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x18003f8af`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f7de`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f821`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f864`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f8c0`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f8d0`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f8f7`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f910`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f9a3`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f9b0`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f9bd`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003fa50`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f7de`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f821`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f864`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f8c0`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f8d0`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f8f7`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f910`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f9a3`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f9b0`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003f9bd`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18003fa50`
- `DUI70!StrToID` at `0x18003f878`
- `DUI70!StrToID` at `0x18003f878`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003f884`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003f884`

## pseudocode

```c
__int64 __fastcall CFinishPage::OnSetActive(CFinishPage *this)
{
  CFinishPage *v1; // r15
  int TextWithBrandName; // esi
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // r10
  _DWORD *v7; // r12
  __int64 v8; // r13
  int v9; // esi
  unsigned int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // edx
  __int64 v15; // rcx
  DirectUI::Element *v16; // rcx
  DirectUI::Element *v17; // rbx
  unsigned __int16 v18; // ax
  struct DirectUI::Element *Descendent; // rax
  struct DirectUI::Element *v20; // rax
  unsigned __int16 *v21; // r14
  DirectUI::Element *v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rcx
  UserTile *v27; // rcx
  unsigned __int16 *v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // r8
  void *v33; // [rsp+20h] [rbp-E0h]
  void *v34; // [rsp+20h] [rbp-E0h]
  char v35; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v36[7]; // [rsp+31h] [rbp-CFh] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v38; // [rsp+40h] [rbp-C0h] BYREF
  int v39[5]; // [rsp+48h] [rbp-B8h]
  __int64 v40; // [rsp+5Ch] [rbp-A4h]
  int v41; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 *v42[3]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v43[264]; // [rsp+80h] [rbp-80h] BYREF

  v1 = (CFinishPage *)((char *)this - 8);
  TextWithBrandName = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 1) + 112LL))((char *)this - 8);
  if ( TextWithBrandName < 0 )
    return (unsigned int)TextWithBrandName;
  v4 = *((_QWORD *)this + 8);
  *((_WORD *)this + 80) = 0;
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4);
  v6 = *((_QWORD *)this + 8);
  v7 = (_DWORD *)((char *)this + 56);
  v8 = *((unsigned int *)this + 14);
  v9 = v5;
  v35 = 0;
  v10 = `CFinishPage::OnSetActive'::`5'::s_rgSubtitleData[v8];
  (*(void (__fastcall **)(__int64, char *, char *, char *))(*(_QWORD *)v6 + 104LL))(
    v6,
    (char *)this + 56,
    &v35,
    (char *)this + 60);
  if ( *((_DWORD *)this + 14) == 2 )
  {
    if ( !v35 )
      v10 = 3246;
LABEL_25:
    v14 = -3;
LABEL_26:
    DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 15), v14);
    goto LABEL_27;
  }
  if ( *v7 )
  {
    if ( *v7 == 7 && *((_BYTE *)this + 60) )
      v10 = 3246 - (v35 != 0);
    goto LABEL_25;
  }
  if ( v9 == 3 )
    v10 = 3255;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 120LL))(*((_QWORD *)this + 8)) )
  {
    if ( v9 == 2 || (v12 = 3336, v9 == 3) )
      v12 = 3337;
    pv = 0;
    if ( (int)TResourceStringAllocCopyEx<unsigned short *>(
                g_hinst,
                v12,
                v11,
                (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
                v33,
                (char *)&pv) >= 0 )
    {
      (*(void (__fastcall **)(_QWORD, LPVOID))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2), pv);
      CoTaskMemFree(pv);
    }
    v10 = 3338;
    pv = 0;
    if ( (int)TResourceStringAllocCopyEx<unsigned short *>(
                g_hinst,
                3351,
                v13,
                (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
                v34,
                (char *)&pv) >= 0 )
    {
      SetElementContentStringAndAccName(*((struct DirectUI::Element **)this + 15), (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
    v14 = 1;
    goto LABEL_26;
  }
  v15 = *((_QWORD *)this + 8);
  v38 = 0;
  if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v15 + 24LL))(v15, &v38) >= 0 )
  {
    pv = 0;
    if ( (int)ResourceStringCoAllocFormatMessage(g_hinst, 3314, &pv, v38) >= 0 )
    {
      SetElementContentStringAndAccName(*((struct DirectUI::Element **)this + 14), (const unsigned __int16 *)pv);
      DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 13), 1);
      CoTaskMemFree(pv);
    }
    CoTaskMemFree(v38);
  }
LABEL_27:
  v42[0] = 0;
  TextWithBrandName = CCloudRampBrandServices::GetTextWithBrandName(g_hinst, v10, v42);
  if ( TextWithBrandName < 0 )
    return (unsigned int)TextWithBrandName;
  v16 = (DirectUI::Element *)*((_QWORD *)this + 9);
  if ( BYTE4(`CFinishPage::OnSetActive'::`5'::s_rgSubtitleData[v8]) )
  {
    DirectUI::Element::SetLayoutPos(v16, -3);
    v17 = (DirectUI::Element *)*((_QWORD *)this + 16);
    v18 = StrToID(L"idErrorMessageText");
    Descendent = DirectUI::Element::FindDescendent(v17, v18);
    v20 = (struct DirectUI::Element *)element_cast<DirectUI::RichText>(Descendent);
    v21 = v42[0];
    v22 = v20;
    SetElementContentStringAndAccName(v20, v42[0]);
    DirectUI::Element::SetClass(v22, L"content_text");
    DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 16), 3);
    DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 17), -3);
  }
  else
  {
    v21 = v42[0];
    SetElementContentStringAndAccName(v16, v42[0]);
    DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 16), -3);
  }
  CoTaskMemFree(v21);
  DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 18), -3);
  v23 = *((unsigned int *)this + 14);
  v39[1] = 3273;
  v41 = 3273;
  v39[0] = 3272;
  v39[2] = 3274;
  v39[3] = 3275;
  v39[4] = 3276;
  v40 = 3277;
  v24 = (unsigned int)v39[v23];
  v42[0] = 0;
  if ( (int)TResourceStringAllocCopyEx<unsigned short *>(
              g_hinst,
              v24,
              v25,
              (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
              v33,
              (char *)v42) >= 0 )
  {
    SetElementContentStringAndAccName(*((struct DirectUI::Element **)this + 19), v42[0]);
    CoTaskMemFree(v42[0]);
  }
  if ( *v7 != 4 )
  {
    v26 = *((_QWORD *)this + 8);
    v42[0] = 0;
    v36[0] = 0;
    if ( (*(int (__fastcall **)(__int64, unsigned __int16 **, _BYTE *))(*(_QWORD *)v26 + 32LL))(v26, v42, v36) < 0 )
    {
      if ( *v7 || _GetDefaultUserPicturePath(v43) < 0 )
        goto LABEL_42;
      v27 = (UserTile *)*((_QWORD *)this + 10);
      v28 = v43;
    }
    else
    {
      v27 = (UserTile *)*((_QWORD *)this + 10);
      v28 = v42[0];
      if ( v36[0] )
      {
        UserTile::SetImageURL(v27, v42[0]);
LABEL_42:
        CFinishPage::_UpdateUsernameInfo(v1);
        goto LABEL_43;
      }
    }
    UserTile::SetImagePath(v27, v28);
    goto LABEL_42;
  }
  DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 10), -3);
  DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 11), -3);
  DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 12), -3);
LABEL_43:
  v29 = *((_QWORD *)this + 8);
  LODWORD(pv) = 0;
  (*(void (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v29 + 112LL))(v29, &pv);
  if ( (int)pv < 0 )
  {
    DirectUI::Element::SetLayoutPos(*((DirectUI::Element **)this + 15), -3);
    CFinishPage::_ShowError(v1, (int)pv);
  }
  if ( (Microsoft_Windows_User_ControlPanelEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v30, UserAccount_Taskflow_FinishPage_Active, v31, 1, v42);
  return (unsigned int)TextWithBrandName;
}

```

## disassembly

```asm
0x18003f5f0  push    rbp
0x18003f5f2  push    rbx
0x18003f5f3  push    rsi
0x18003f5f4  push    rdi
0x18003f5f5  push    r12
0x18003f5f7  push    r13
0x18003f5f9  push    r14
0x18003f5fb  push    r15
0x18003f5fd  lea     rbp, [rsp-1A8h]
0x18003f605  sub     rsp, 2A8h
0x18003f60c  mov     rax, cs:__security_cookie
0x18003f613  xor     rax, rsp
0x18003f616  mov     [rbp+1E0h+var_50], rax
0x18003f61d  lea     r15, [rcx-8]
0x18003f621  mov     rdi, rcx
0x18003f624  mov     rax, [r15]
0x18003f627  mov     rcx, r15
0x18003f62a  mov     rax, [rax+70h]
0x18003f62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f633  xor     r14d, r14d
0x18003f636  mov     esi, eax
0x18003f638  test    eax, eax
0x18003f63a  js      loc_18003FA87
0x18003f640  mov     rcx, [rdi+40h]
0x18003f644  mov     [rdi+0A0h], r14w
0x18003f64c  mov     rax, [rcx]
0x18003f64f  mov     rax, [rax+48h]
0x18003f653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f658  mov     r10, [rdi+40h]
0x18003f65c  lea     r12, [rdi+38h]
0x18003f660  mov     r13d, [r12]
0x18003f664  lea     r9, [rdi+3Ch]
0x18003f668  mov     esi, eax
0x18003f66a  mov     [rsp+2E0h+var_2B0], r14b
0x18003f66f  lea     rax, ?s_rgSubtitleData@?4??OnSetActive@CFinishPage@@UEAAJXZ@4QBU_unnamed_type_s_rgSubtitleData_@?4??12@UEAAJXZ@B; `CFinishPage::OnSetActive(void)'::`5'::_unnamed_type_s_rgSubtitleData_ const near * const `CFinishPage::OnSetActive(void)'::`5'::s_rgSubtitleData
0x18003f676  mov     rdx, r12
0x18003f679  mov     rcx, [r10]
0x18003f67c  lea     r8, [rsp+2E0h+var_2B0]
0x18003f681  mov     ebx, [rax+r13*8]
0x18003f685  mov     rax, [rcx+68h]
0x18003f689  mov     rcx, r10
0x18003f68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f691  cmp     dword ptr [r12], 2
0x18003f696  jnz     short loc_18003F6AA
0x18003f698  cmp     [rsp+2E0h+var_2B0], r14b
0x18003f69d  mov     eax, 0CAEh
0x18003f6a2  cmovz   ebx, eax
0x18003f6a5  jmp     loc_18003F818
0x18003f6aa  cmp     [r12], r14d
0x18003f6ae  jnz     loc_18003F7FC
0x18003f6b4  cmp     esi, 3
0x18003f6b7  jnz     short loc_18003F6BE
0x18003f6b9  mov     ebx, 0CB7h
0x18003f6be  mov     rcx, [rdi+40h]
0x18003f6c2  mov     rax, [rcx]
0x18003f6c5  mov     rax, [rax+78h]
0x18003f6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6ce  test    al, al
0x18003f6d0  jz      loc_18003F781
0x18003f6d6  cmp     esi, 2
0x18003f6d9  jz      short loc_18003F6E5
0x18003f6db  mov     edx, 0D08h
0x18003f6e0  cmp     esi, 3
0x18003f6e3  jnz     short loc_18003F6EA
0x18003f6e5  mov     edx, 0D09h; int
0x18003f6ea  mov     rcx, cs:g_hinst; int
0x18003f6f1  lea     rax, [rsp+2E0h+pv]
0x18003f6f6  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x18003f6fd  mov     [rsp+2E0h+var_2B8], rax; void *
0x18003f702  mov     [rsp+2E0h+pv], r14
0x18003f707  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18003f70c  test    eax, eax
0x18003f70e  js      short loc_18003F730
0x18003f710  mov     rcx, [rdi+10h]
0x18003f714  mov     rdx, [rsp+2E0h+pv]
0x18003f719  mov     rax, [rcx]
0x18003f71c  mov     rax, [rax+40h]
0x18003f720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f725  mov     rcx, [rsp+2E0h+pv]; pv
0x18003f72a  call    cs:__imp_CoTaskMemFree
0x18003f730  mov     rcx, cs:g_hinst; int
0x18003f737  lea     rax, [rsp+2E0h+pv]
0x18003f73c  mov     ebx, 0D0Ah
0x18003f741  mov     [rsp+2E0h+pv], r14
0x18003f746  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x18003f74d  mov     [rsp+2E0h+var_2B8], rax; void *
0x18003f752  lea     edx, [rbx+0Dh]; int
0x18003f755  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18003f75a  test    eax, eax
0x18003f75c  js      short loc_18003F777
0x18003f75e  mov     rdx, [rsp+2E0h+pv]; unsigned __int16 *
0x18003f763  mov     rcx, [rdi+78h]; struct DirectUI::Element *
0x18003f767  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x18003f76c  mov     rcx, [rsp+2E0h+pv]; pv
0x18003f771  call    cs:__imp_CoTaskMemFree
0x18003f777  mov     edx, 1
0x18003f77c  jmp     loc_18003F81D
0x18003f781  mov     rcx, [rdi+40h]
0x18003f785  lea     rdx, [rsp+2E0h+var_2A0]
0x18003f78a  mov     [rsp+2E0h+var_2A0], r14
0x18003f78f  mov     rax, [rcx]
0x18003f792  mov     rax, [rax+18h]
0x18003f796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f79b  test    eax, eax
0x18003f79d  js      loc_18003F827
0x18003f7a3  mov     r9, [rsp+2E0h+var_2A0]
0x18003f7a8  lea     r8, [rsp+2E0h+pv]
0x18003f7ad  mov     rcx, cs:g_hinst
0x18003f7b4  mov     edx, 0CF2h
0x18003f7b9  mov     [rsp+2E0h+pv], r14
0x18003f7be  call    ResourceStringCoAllocFormatMessage
0x18003f7c3  test    eax, eax
0x18003f7c5  js      short loc_18003F7EF
0x18003f7c7  mov     rdx, [rsp+2E0h+pv]; unsigned __int16 *
0x18003f7cc  mov     rcx, [rdi+70h]; struct DirectUI::Element *
0x18003f7d0  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x18003f7d5  mov     rcx, [rdi+68h]
0x18003f7d9  mov     edx, 1
0x18003f7de  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003f7e4  mov     rcx, [rsp+2E0h+pv]; pv
0x18003f7e9  call    cs:__imp_CoTaskMemFree
0x18003f7ef  mov     rcx, [rsp+2E0h+var_2A0]; pv
0x18003f7f4  call    cs:__imp_CoTaskMemFree
0x18003f7fa  jmp     short loc_18003F827
0x18003f7fc  cmp     dword ptr [r12], 7
0x18003f801  jnz     short loc_18003F818
0x18003f803  cmp     [rdi+3Ch], r14b
0x18003f807  jz      short loc_18003F818
0x18003f809  mov     al, [rsp+2E0h+var_2B0]
0x18003f80d  neg     al
0x18003f80f  mov     eax, 0CAEh
0x18003f814  sbb     ebx, ebx
0x18003f816  add     ebx, eax
0x18003f818  mov     edx, 0FFFFFFFDh
0x18003f81d  mov     rcx, [rdi+78h]
0x18003f821  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003f827  mov     rcx, cs:g_hinst; hModule
0x18003f82e  lea     r8, [rsp+2E0h+var_278]; unsigned __int16 **
0x18003f833  mov     edx, ebx; unsigned int
0x18003f835  mov     [rsp+2E0h+var_278], r14
0x18003f83a  call    ?GetTextWithBrandName@CCloudRampBrandServices@@SAJPEAUHINSTANCE__@@KPEAPEAG@Z; CCloudRampBrandServices::GetTextWithBrandName(HINSTANCE__ *,ulong,ushort * *)
0x18003f83f  xor     ebx, ebx
0x18003f841  mov     esi, eax
0x18003f843  test    eax, eax
0x18003f845  js      loc_18003FA87
0x18003f84b  mov     rcx, [rdi+48h]; struct DirectUI::Element *
0x18003f84f  lea     rax, ?s_rgSubtitleData@?4??OnSetActive@CFinishPage@@UEAAJXZ@4QBU_unnamed_type_s_rgSubtitleData_@?4??12@UEAAJXZ@B; `CFinishPage::OnSetActive(void)'::`5'::_unnamed_type_s_rgSubtitleData_ const near * const `CFinishPage::OnSetActive(void)'::`5'::s_rgSubtitleData
0x18003f856  cmp     [rax+r13*8+4], bl
0x18003f85b  jz      short loc_18003F8DA
0x18003f85d  lea     r13d, [rbx-3]
0x18003f861  mov     edx, r13d
0x18003f864  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003f86a  mov     rbx, [rdi+80h]
0x18003f871  lea     rcx, aIderrormessage; "idErrorMessageText"
0x18003f878  call    cs:__imp_StrToID
0x18003f87e  movzx   edx, ax
0x18003f881  mov     rcx, rbx
0x18003f884  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003f88a  mov     rcx, rax
0x18003f88d  call    ??$element_cast@VRichText@DirectUI@@@@YAPEAVRichText@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::RichText>(DirectUI::Element *)
0x18003f892  mov     r14, [rsp+2E0h+var_278]
0x18003f897  mov     rcx, rax; struct DirectUI::Element *
0x18003f89a  mov     rdx, r14; unsigned __int16 *
0x18003f89d  mov     rbx, rax
0x18003f8a0  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x18003f8a5  lea     rdx, aContentText; "content_text"
0x18003f8ac  mov     rcx, rbx
0x18003f8af  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x18003f8b5  mov     rcx, [rdi+80h]
0x18003f8bc  lea     edx, [r13+6]
0x18003f8c0  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003f8c6  mov     rcx, [rdi+88h]
0x18003f8cd  mov     edx, r13d
0x18003f8d0  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003f8d6  xor     ebx, ebx
0x18003f8d8  jmp     short loc_18003F8FD
0x18003f8da  mov     r14, [rsp+2E0h+var_278]
0x18003f8df  mov     rdx, r14; unsigned __int16 *
0x18003f8e2  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x18003f8e7  mov     rcx, [rdi+80h]
0x18003f8ee  mov     r13d, 0FFFFFFFDh
0x18003f8f4  mov     edx, r13d
0x18003f8f7  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003f8fd  mov     rcx, r14; pv
0x18003f900  call    cs:__imp_CoTaskMemFree
0x18003f906  mov     rcx, [rdi+90h]
0x18003f90d  mov     edx, r13d
0x18003f910  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003f916  mov     edx, [rdi+38h]
0x18003f919  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x18003f920  mov     rcx, cs:g_hinst; int
0x18003f927  mov     eax, 0CC9h
0x18003f92c  mov     [rsp+2E0h+var_294], eax
0x18003f930  mov     [rsp+2E0h+var_27C], eax
0x18003f934  lea     rax, [rsp+2E0h+var_278]
0x18003f939  mov     [rsp+2E0h+var_298], 0CC8h
0x18003f941  mov     [rsp+2E0h+var_290], 0CCAh
0x18003f949  mov     [rsp+2E0h+var_28C], 0CCBh
0x18003f951  mov     [rsp+2E0h+var_288], 0CCCh
0x18003f959  mov     [rsp+2E0h+var_284], 0CCDh
0x18003f962  mov     edx, [rsp+rdx*4+2E0h+var_298]; int
0x18003f966  mov     [rsp+2E0h+var_278], rbx
0x18003f96b  mov     [rsp+2E0h+var_2B8], rax; void *
0x18003f970  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18003f975  test    eax, eax
0x18003f977  js      short loc_18003F995
0x18003f979  mov     rdx, [rsp+2E0h+var_278]; unsigned __int16 *
0x18003f97e  mov     rcx, [rdi+98h]; struct DirectUI::Element *
0x18003f985  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x18003f98a  mov     rcx, [rsp+2E0h+var_278]; pv
0x18003f98f  call    cs:__imp_CoTaskMemFree
0x18003f995  cmp     dword ptr [r12], 4
0x18003f99a  jnz     short loc_18003F9C5
0x18003f99c  mov     rcx, [rdi+50h]
0x18003f9a0  mov     edx, r13d
0x18003f9a3  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003f9a9  mov     rcx, [rdi+58h]
0x18003f9ad  mov     edx, r13d
0x18003f9b0  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003f9b6  mov     rcx, [rdi+60h]
0x18003f9ba  mov     edx, r13d
0x18003f9bd  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003f9c3  jmp     short loc_18003FA2A
0x18003f9c5  mov     rcx, [rdi+40h]
0x18003f9c9  lea     r8, [rsp+2E0h+var_2AF]
0x18003f9ce  mov     [rsp+2E0h+var_278], rbx
0x18003f9d3  lea     rdx, [rsp+2E0h+var_278]
0x18003f9d8  mov     [rsp+2E0h+var_2AF], bl
0x18003f9dc  mov     rax, [rcx]
0x18003f9df  mov     rax, [rax+20h]
0x18003f9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9e8  test    eax, eax
0x18003f9ea  js      short loc_18003FA02
0x18003f9ec  mov     rcx, [rdi+50h]; this
0x18003f9f0  mov     rdx, [rsp+2E0h+var_278]; unsigned __int16 *
0x18003f9f5  cmp     [rsp+2E0h+var_2AF], bl
0x18003f9f9  jz      short loc_18003FA1D
0x18003f9fb  call    ?SetImageURL@UserTile@@QEAAJPEBG@Z; UserTile::SetImageURL(ushort const *)
0x18003fa00  jmp     short loc_18003FA22
0x18003fa02  cmp     [r12], ebx
0x18003fa06  jnz     short loc_18003FA22
0x18003fa08  lea     rcx, [rbp+1E0h+var_260]; unsigned __int16 *
0x18003fa0c  call    ?_GetDefaultUserPicturePath@@YAJPEAGK@Z; _GetDefaultUserPicturePath(ushort *,ulong)
0x18003fa11  test    eax, eax
0x18003fa13  js      short loc_18003FA22
0x18003fa15  mov     rcx, [rdi+50h]; this
0x18003fa19  lea     rdx, [rbp+1E0h+var_260]; unsigned __int16 *
0x18003fa1d  call    ?SetImagePath@UserTile@@QEAAJPEBG@Z; UserTile::SetImagePath(ushort const *)
0x18003fa22  mov     rcx, r15; this
0x18003fa25  call    ?_UpdateUsernameInfo@CFinishPage@@AEAAXXZ; CFinishPage::_UpdateUsernameInfo(void)
0x18003fa2a  mov     rcx, [rdi+40h]
0x18003fa2e  lea     rdx, [rsp+2E0h+pv]
0x18003fa33  mov     dword ptr [rsp+2E0h+pv], ebx
0x18003fa37  mov     rax, [rcx]
0x18003fa3a  mov     rax, [rax+70h]
0x18003fa3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa43  cmp     dword ptr [rsp+2E0h+pv], ebx
0x18003fa47  jge     short loc_18003FA62
0x18003fa49  mov     rcx, [rdi+78h]
0x18003fa4d  mov     edx, r13d
0x18003fa50  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x18003fa56  mov     edx, dword ptr [rsp+2E0h+pv]; int
0x18003fa5a  mov     rcx, r15; this
0x18003fa5d  call    ?_ShowError@CFinishPage@@AEAAXJ@Z; CFinishPage::_ShowError(long)
0x18003fa62  test    cs:Microsoft_Windows_User_ControlPanelEnableBits, 2
0x18003fa69  jz      short loc_18003FA87
0x18003fa6b  lea     rax, [rsp+2E0h+var_278]
0x18003fa70  mov     r9d, 1
0x18003fa76  lea     rdx, UserAccount_Taskflow_FinishPage_Active
0x18003fa7d  mov     [rsp+2E0h+var_2C0], rax
0x18003fa82  call    McGenEventWrite_EventWriteTransfer
0x18003fa87  mov     eax, esi
0x18003fa89  mov     rcx, [rbp+1E0h+var_50]
0x18003fa90  xor     rcx, rsp; StackCookie
0x18003fa93  call    __security_check_cookie
0x18003fa98  add     rsp, 2A8h
0x18003fa9f  pop     r15
0x18003faa1  pop     r14
0x18003faa3  pop     r13
0x18003faa5  pop     r12
0x18003faa7  pop     rdi
0x18003faa8  pop     rsi
0x18003faa9  pop     rbx
0x18003faaa  pop     rbp
0x18003faab  retn
```
