# CWallpaperCore::_SelectFromPathCombo(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180042ab4`
- end: `0x180042c02`
- name: `?_SelectFromPathCombo@CWallpaperCore@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(CWallpaperCore *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003c52c`
- `0x18003d500`
- `0x18003f0d8`
- `0x1800423e0`

## callees

- `0x180042154`
- `0x180042ab4`
- `0x18004f6cc`
- `0x18005501c`
- `0x180057010`

## import_xrefs

- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180042ba7`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180042ba7`
- `DUI70!StrToID` at `0x180042b95`
- `DUI70!StrToID` at `0x180042b95`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x180042be6`
- `DUI70!?SetSelection@Combobox@DirectUI@@QEAAJH@Z` at `0x180042be6`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180042bbb`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180042bbb`

## string_xrefs

- `0x180042b84`: `ComboBox_PictureFolder`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::_SelectFromPathCombo(CWallpaperCore *this, const ITEMIDLIST *a2)
{
  int v4; // ebx
  int i; // edi
  struct _DPA *v6; // rcx
  int v7; // eax
  LPCITEMIDLIST *v8; // rax
  LPCITEMIDLIST *v9; // r14
  char v10; // r15
  int j; // edi
  struct _DPA *v12; // rcx
  int v13; // eax
  LPCITEMIDLIST *Ptr; // rax
  LPCITEMIDLIST *v15; // r14
  int v16; // ebp
  DirectUI::Element *v17; // rbx
  unsigned __int16 v18; // ax
  DirectUI::Combobox *Descendent; // rdi
  __int64 ClassInfoPtr; // rbx

  if ( a2 )
  {
    v4 = -1;
    for ( i = 0; ; ++i )
    {
      v6 = (struct _DPA *)*((_QWORD *)this + 10);
      v7 = v6 ? *(_DWORD *)v6 : 0;
      if ( v4 != -1 )
        break;
      if ( i >= v7 )
      {
        v4 = -1;
        v10 = 0;
        for ( j = 0; ; ++j )
        {
          v12 = (struct _DPA *)*((_QWORD *)this + 11);
          v13 = v12 ? *(_DWORD *)v12 : 0;
          if ( j >= v13 || v10 )
            break;
          Ptr = (LPCITEMIDLIST *)DPA_GetPtr(v12, j);
          v15 = Ptr;
          if ( Ptr && (unsigned int)ILIsEqualByAliasOrPath(a2, *Ptr) )
          {
            v4 = *((_DWORD *)v15 + 132);
            v10 = 1;
          }
        }
        if ( v4 == -1 )
          v4 = CWallpaperCore::_MatchToRegPaths(this, (const struct _ITEMIDLIST_ABSOLUTE *)a2);
        break;
      }
      v8 = (LPCITEMIDLIST *)DPA_GetPtr(v6, i);
      v9 = v8;
      if ( v8 )
      {
        if ( (unsigned int)ILIsEqualByAliasOrPath(a2, *v8) )
          v4 = *((_DWORD *)v9 + 132);
      }
    }
  }
  else
  {
    v4 = *((_DWORD *)this + 54);
  }
  v16 = 0;
  if ( v4 != -1 )
    v16 = v4;
  v17 = (DirectUI::Element *)*((_QWORD *)this + 4);
  v18 = StrToID(L"ComboBox_PictureFolder");
  Descendent = DirectUI::Element::FindDescendent(v17, v18);
  if ( Descendent )
  {
    ClassInfoPtr = DirectUI::Combobox::GetClassInfoPtr();
    if ( (*(__int64 (__fastcall **)(DirectUI::Combobox *))(*(_QWORD *)Descendent + 280LL))(Descendent) == ClassInfoPtr )
      DirectUI::Combobox::SetSelection(Descendent, v16);
  }
  return 0;
}

```

## disassembly

```asm
0x180042ab4  push    rbx
0x180042ab6  push    rbp
0x180042ab7  push    rsi
0x180042ab8  push    rdi
0x180042ab9  push    r14
0x180042abb  push    r15
0x180042abd  sub     rsp, 28h
0x180042ac1  mov     rbp, rdx
0x180042ac4  mov     rsi, rcx
0x180042ac7  test    rdx, rdx
0x180042aca  jz      loc_180042B7C
0x180042ad0  or      ebx, 0FFFFFFFFh
0x180042ad3  xor     edi, edi
0x180042ad5  mov     rcx, [rsi+50h]; hdpa
0x180042ad9  test    rcx, rcx
0x180042adc  jz      short loc_180042AE2
0x180042ade  mov     eax, [rcx]
0x180042ae0  jmp     short loc_180042AE4
0x180042ae2  xor     eax, eax
0x180042ae4  cmp     ebx, 0FFFFFFFFh
0x180042ae7  jnz     loc_180042B82
0x180042aed  cmp     edi, eax
0x180042aef  jge     short loc_180042B1B
0x180042af1  movsxd  rdx, edi; i
0x180042af4  call    DPA_GetPtr
0x180042af9  mov     r14, rax
0x180042afc  test    rax, rax
0x180042aff  jz      short loc_180042B17
0x180042b01  mov     rdx, [rax]; LPCITEMIDLIST
0x180042b04  mov     rcx, rbp; pidl
0x180042b07  call    ILIsEqualByAliasOrPath
0x180042b0c  test    eax, eax
0x180042b0e  jz      short loc_180042B17
0x180042b10  mov     ebx, [r14+210h]
0x180042b17  inc     edi
0x180042b19  jmp     short loc_180042AD5
0x180042b1b  or      ebx, 0FFFFFFFFh
0x180042b1e  xor     r15b, r15b
0x180042b21  xor     edi, edi
0x180042b23  mov     rcx, [rsi+58h]; hdpa
0x180042b27  test    rcx, rcx
0x180042b2a  jz      short loc_180042B30
0x180042b2c  mov     eax, [rcx]
0x180042b2e  jmp     short loc_180042B32
0x180042b30  xor     eax, eax
0x180042b32  cmp     edi, eax
0x180042b34  jge     short loc_180042B68
0x180042b36  test    r15b, r15b
0x180042b39  jnz     short loc_180042B68
0x180042b3b  movsxd  rdx, edi; i
0x180042b3e  call    DPA_GetPtr
0x180042b43  mov     r14, rax
0x180042b46  test    rax, rax
0x180042b49  jz      short loc_180042B64
0x180042b4b  mov     rdx, [rax]; LPCITEMIDLIST
0x180042b4e  mov     rcx, rbp; pidl
0x180042b51  call    ILIsEqualByAliasOrPath
0x180042b56  test    eax, eax
0x180042b58  jz      short loc_180042B64
0x180042b5a  mov     ebx, [r14+210h]
0x180042b61  mov     r15b, 1
0x180042b64  inc     edi
0x180042b66  jmp     short loc_180042B23
0x180042b68  cmp     ebx, 0FFFFFFFFh
0x180042b6b  jnz     short loc_180042B82
0x180042b6d  mov     rdx, rbp; struct _ITEMIDLIST_ABSOLUTE *
0x180042b70  mov     rcx, rsi; this
0x180042b73  call    ?_MatchToRegPaths@CWallpaperCore@@AEAAHPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CWallpaperCore::_MatchToRegPaths(_ITEMIDLIST_ABSOLUTE const *)
0x180042b78  mov     ebx, eax
0x180042b7a  jmp     short loc_180042B82
0x180042b7c  mov     ebx, [rcx+0D8h]
0x180042b82  xor     ebp, ebp
0x180042b84  lea     rcx, aComboboxPictur; "ComboBox_PictureFolder"
0x180042b8b  cmp     ebx, 0FFFFFFFFh
0x180042b8e  cmovnz  ebp, ebx
0x180042b91  mov     rbx, [rsi+20h]
0x180042b95  call    cs:__imp_StrToID
0x180042b9c  nop     dword ptr [rax+rax+00h]
0x180042ba1  movzx   edx, ax
0x180042ba4  mov     rcx, rbx
0x180042ba7  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180042bae  nop     dword ptr [rax+rax+00h]
0x180042bb3  mov     rdi, rax
0x180042bb6  test    rax, rax
0x180042bb9  jz      short loc_180042BF2
0x180042bbb  call    cs:__imp_?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Combobox::GetClassInfoPtr(void)
0x180042bc2  nop     dword ptr [rax+rax+00h]
0x180042bc7  mov     rcx, [rdi]
0x180042bca  mov     rbx, rax
0x180042bcd  mov     rax, [rcx+118h]
0x180042bd4  mov     rcx, rdi
0x180042bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042bdc  cmp     rax, rbx
0x180042bdf  jnz     short loc_180042BF2
0x180042be1  mov     edx, ebp
0x180042be3  mov     rcx, rdi
0x180042be6  call    cs:__imp_?SetSelection@Combobox@DirectUI@@QEAAJH@Z; DirectUI::Combobox::SetSelection(int)
0x180042bed  nop     dword ptr [rax+rax+00h]
0x180042bf2  xor     eax, eax
0x180042bf4  add     rsp, 28h
0x180042bf8  pop     r15
0x180042bfa  pop     r14
0x180042bfc  pop     rdi
0x180042bfd  pop     rsi
0x180042bfe  pop     rbp
0x180042bff  pop     rbx
0x180042c00  retn
```
