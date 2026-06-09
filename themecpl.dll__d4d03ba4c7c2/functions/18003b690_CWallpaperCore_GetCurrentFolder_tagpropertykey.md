# CWallpaperCore::GetCurrentFolder(_tagpropertykey *)

- ea: `0x18003b690`
- end: `0x18003b80f`
- name: `?GetCurrentFolder@CWallpaperCore@@AEBAPEAU_ITEMIDLIST_ABSOLUTE@@PEAU_tagpropertykey@@@Z`
- size: `383`
- prototype: `struct _ITEMIDLIST_ABSOLUTE *__fastcall(CWallpaperCore *__hidden this, struct _tagpropertykey *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003d150`
- `0x180042c08`
- `0x180043624`

## callees

- `0x18003b690`
- `0x18005501c`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x18003b7ac`
- `SHELL32!__imp_ILClone` at `0x18003b7d0`
- `SHELL32!__imp_ILClone` at `0x18003b7ac`
- `SHELL32!__imp_ILClone` at `0x18003b7d0`
- `USER32!SendMessageW` at `0x18003b743`
- `USER32!SendMessageW` at `0x18003b767`
- `USER32!SendMessageW` at `0x18003b743`
- `USER32!SendMessageW` at `0x18003b767`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003b6d1`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003b6d1`
- `DUI70!StrToID` at `0x18003b6bf`
- `DUI70!StrToID` at `0x18003b6bf`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18003b6e9`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18003b6e9`

## string_xrefs

- `0x18003b6a9`: `ComboBox_PictureFolder`

## pseudocode

```c
struct _ITEMIDLIST_ABSOLUTE *__fastcall CWallpaperCore::GetCurrentFolder(
        CWallpaperCore *this,
        struct _tagpropertykey *a2)
{
  DirectUI::Element *v2; // rbx
  GUID fmtid; // xmm6
  DWORD pid; // r15d
  LPITEMIDLIST v7; // rdi
  unsigned __int16 v8; // ax
  struct DirectUI::Element *Descendent; // r14
  __int64 ClassInfoPtr; // rbx
  HWND v11; // rbx
  LRESULT v12; // rax
  int v13; // eax
  struct _DPA *v14; // rcx
  PVOID Ptr; // rbx
  LPITEMIDLIST v16; // rax
  LPCITEMIDLIST *v17; // rax

  v2 = (DirectUI::Element *)*((_QWORD *)this + 4);
  fmtid = GUID_NULL;
  pid = 0;
  v7 = 0;
  v8 = StrToID(L"ComboBox_PictureFolder");
  Descendent = DirectUI::Element::FindDescendent(v2, v8);
  if ( Descendent )
  {
    ClassInfoPtr = DirectUI::Combobox::GetClassInfoPtr();
    if ( (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 280LL))(Descendent) == ClassInfoPtr )
    {
      if ( *((_QWORD *)this + 21) )
      {
        v11 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 360LL))(Descendent);
        v12 = SendMessageW(v11, 0x147u, 0, 0);
        if ( v12 != -1 )
        {
          v13 = SendMessageW(v11, 0x150u, v12, 0);
          if ( HIWORD(v13) )
          {
            if ( HIWORD(v13) == 1 )
              goto LABEL_14;
            if ( HIWORD(v13) == 2 )
            {
              Ptr = DPA_GetPtr(*((HDPA *)this + 12), (unsigned __int16)v13);
              v16 = ILClone(*((LPCITEMIDLIST *)Ptr + 134));
              fmtid = *(GUID *)Ptr;
              pid = *((_DWORD *)Ptr + 4);
LABEL_13:
              v7 = v16;
              goto LABEL_14;
            }
            if ( HIWORD(v13) != 3 )
              goto LABEL_14;
            v14 = (struct _DPA *)*((_QWORD *)this + 11);
          }
          else
          {
            v14 = (struct _DPA *)*((_QWORD *)this + 10);
          }
          v17 = (LPCITEMIDLIST *)DPA_GetPtr(v14, (unsigned __int16)v13);
          v16 = ILClone(*v17);
          pid = PKEY_ItemFolderPathDisplay.pid;
          fmtid = PKEY_ItemFolderPathDisplay.fmtid;
          goto LABEL_13;
        }
      }
    }
  }
LABEL_14:
  if ( a2 )
  {
    a2->fmtid = fmtid;
    a2->pid = pid;
  }
  return (struct _ITEMIDLIST_ABSOLUTE *)v7;
}

```

## disassembly

```asm
0x18003b690  push    rbx
0x18003b692  push    rbp
0x18003b693  push    rsi
0x18003b694  push    rdi
0x18003b695  push    r14
0x18003b697  push    r15
0x18003b699  sub     rsp, 38h
0x18003b69d  mov     rbx, [rcx+20h]
0x18003b6a1  mov     rbp, rcx
0x18003b6a4  movaps  [rsp+68h+var_48], xmm6
0x18003b6a9  lea     rcx, aComboboxPictur; "ComboBox_PictureFolder"
0x18003b6b0  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18003b6b7  mov     rsi, rdx
0x18003b6ba  xor     r15d, r15d
0x18003b6bd  xor     edi, edi
0x18003b6bf  call    cs:__imp_StrToID
0x18003b6c6  nop     dword ptr [rax+rax+00h]
0x18003b6cb  movzx   edx, ax
0x18003b6ce  mov     rcx, rbx
0x18003b6d1  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003b6d8  nop     dword ptr [rax+rax+00h]
0x18003b6dd  mov     r14, rax
0x18003b6e0  test    rax, rax
0x18003b6e3  jz      loc_18003B7ED
0x18003b6e9  call    cs:__imp_?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Combobox::GetClassInfoPtr(void)
0x18003b6f0  nop     dword ptr [rax+rax+00h]
0x18003b6f5  mov     rcx, [r14]
0x18003b6f8  mov     rbx, rax
0x18003b6fb  mov     rax, [rcx+118h]
0x18003b702  mov     rcx, r14
0x18003b705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b70a  cmp     rax, rbx
0x18003b70d  jnz     loc_18003B7ED
0x18003b713  cmp     [rbp+0A8h], rdi
0x18003b71a  jz      loc_18003B7ED
0x18003b720  mov     rax, [r14]
0x18003b723  mov     rcx, r14
0x18003b726  mov     rax, [rax+168h]
0x18003b72d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b732  xor     r9d, r9d; lParam
0x18003b735  xor     r8d, r8d; wParam
0x18003b738  mov     edx, 147h; Msg
0x18003b73d  mov     rcx, rax; hWnd
0x18003b740  mov     rbx, rax
0x18003b743  call    cs:__imp_SendMessageW
0x18003b74a  nop     dword ptr [rax+rax+00h]
0x18003b74f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003b753  jz      loc_18003B7ED
0x18003b759  xor     r9d, r9d; lParam
0x18003b75c  mov     r8, rax; wParam
0x18003b75f  mov     edx, 150h; Msg
0x18003b764  mov     rcx, rbx; hWnd
0x18003b767  call    cs:__imp_SendMessageW
0x18003b76e  nop     dword ptr [rax+rax+00h]
0x18003b773  mov     rcx, rax
0x18003b776  shr     rcx, 10h
0x18003b77a  movzx   edx, cx
0x18003b77d  test    edx, edx
0x18003b77f  jz      short loc_18003B7C1
0x18003b781  sub     edx, 1
0x18003b784  jz      short loc_18003B7ED
0x18003b786  sub     edx, 1
0x18003b789  jz      short loc_18003B796
0x18003b78b  cmp     edx, 1
0x18003b78e  jnz     short loc_18003B7ED
0x18003b790  mov     rcx, [rbp+58h]
0x18003b794  jmp     short loc_18003B7C5
0x18003b796  mov     rcx, [rbp+60h]; hdpa
0x18003b79a  movzx   edx, ax; i
0x18003b79d  call    DPA_GetPtr
0x18003b7a2  mov     rbx, rax
0x18003b7a5  mov     rcx, [rax+430h]; pidl
0x18003b7ac  call    cs:__imp_ILClone
0x18003b7b3  nop     dword ptr [rax+rax+00h]
0x18003b7b8  movups  xmm6, xmmword ptr [rbx]
0x18003b7bb  mov     r15d, [rbx+10h]
0x18003b7bf  jmp     short loc_18003B7EA
0x18003b7c1  mov     rcx, [rbp+50h]; hdpa
0x18003b7c5  movzx   edx, ax; i
0x18003b7c8  call    DPA_GetPtr
0x18003b7cd  mov     rcx, [rax]; pidl
0x18003b7d0  call    cs:__imp_ILClone
0x18003b7d7  nop     dword ptr [rax+rax+00h]
0x18003b7dc  mov     r15d, cs:PKEY_ItemFolderPathDisplay.pid
0x18003b7e3  movups  xmm6, xmmword ptr cs:PKEY_ItemFolderPathDisplay.fmtid.Data1
0x18003b7ea  mov     rdi, rax
0x18003b7ed  test    rsi, rsi
0x18003b7f0  jz      short loc_18003B7F9
0x18003b7f2  movups  xmmword ptr [rsi], xmm6
0x18003b7f5  mov     [rsi+10h], r15d
0x18003b7f9  movaps  xmm6, [rsp+68h+var_48]
0x18003b7fe  mov     rax, rdi
0x18003b801  add     rsp, 38h
0x18003b805  pop     r15
0x18003b807  pop     r14
0x18003b809  pop     rdi
0x18003b80a  pop     rsi
0x18003b80b  pop     rbp
0x18003b80c  pop     rbx
0x18003b80d  retn
```
