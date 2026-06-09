# CWallpaperCore::_AddPath(CDPANewMem<CWallpaperCore::WALLPAPER_PATH> *,CWallpaperCore::PATHTYPE,ushort const *,_ITEMIDLIST_ABSOLUTE const *,int)

- ea: `0x18003ef34`
- end: `0x18003f0d0`
- name: `?_AddPath@CWallpaperCore@@AEAAJPEAV?$CDPANewMem@UWALLPAPER_PATH@CWallpaperCore@@@@W4PATHTYPE@1@PEBGPEBU_ITEMIDLIST_ABSOLUTE@@H@Z`
- size: `412`
- prototype: `__int64 __fastcall(int, int, int, int, LPCITEMIDLIST pidl)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003f4dc`
- `0x180041df8`

## callees

- `0x180002650`
- `0x18000268c`
- `0x18003ef34`
- `0x180040788`
- `0x180054e70`
- `0x180055074`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x18003efe9`
- `SHELL32!__imp_ILClone` at `0x18003efe9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003f04d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003f04d`
- `DUI70!StrToID` at `0x18003f03b`
- `DUI70!StrToID` at `0x18003f03b`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18003f061`
- `DUI70!?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18003f061`

## string_xrefs

- `0x18003f034`: `ComboBox_PictureFolder`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::_AddPath(__int64 a1, struct _DPA **a2, int a3, _WORD *a4, LPCITEMIDLIST pidl)
{
  HDPA v9; // rax
  _DWORD *v10; // rsi
  __int64 v11; // rax
  _WORD *v12; // r8
  __int64 v13; // rdx
  _WORD *v14; // rcx
  int inserted; // edi
  struct _DPA *v16; // rcx
  unsigned int v17; // ebp
  DirectUI::Element *v18; // rbx
  unsigned __int16 v19; // ax
  struct DirectUI::Element *Descendent; // r14
  __int64 ClassInfoPtr; // rbx
  __int64 v22; // rcx
  int v23; // eax

  if ( (*a2 || (v9 = DPA_Create(5), (*a2 = v9) != 0))
    && (v10 = operator new(0x218u, (const struct std::nothrow_t *)&std::nothrow)) != 0 )
  {
    v11 = 2147483646;
    v12 = v10 + 2;
    v13 = 260;
    do
    {
      if ( !v11 )
        break;
      if ( !*a4 )
        break;
      *v12++ = *a4++;
      --v11;
      --v13;
    }
    while ( v13 );
    v14 = v12 - 1;
    inserted = v13 == 0 ? 0x8007007A : 0;
    if ( v13 )
      v14 = v12;
    *v14 = 0;
    if ( v13
      && ((*(_QWORD *)v10 = ILClone(pidl), (v16 = *a2) == 0) ? (v17 = 0) : (v17 = *(_DWORD *)v16),
          inserted = DPA_InsertPtr(v16, 0x7FFFFFFF, v10),
          inserted >= 0) )
    {
      if ( v17 != -1 && !a3 )
      {
        v18 = *(DirectUI::Element **)(a1 + 32);
        v19 = StrToID(L"ComboBox_PictureFolder");
        Descendent = DirectUI::Element::FindDescendent(v18, v19);
        if ( Descendent )
        {
          ClassInfoPtr = DirectUI::Combobox::GetClassInfoPtr();
          if ( (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)Descendent + 280LL))(Descendent) == ClassInfoPtr )
          {
            v23 = CWallpaperCore::_FillComboItem(v22, Descendent, v10 + 2, v17, 0);
            if ( v23 != -1 )
              v10[132] = v23;
          }
        }
      }
    }
    else
    {
      operator delete(v10, (const struct std::nothrow_t *)0x218);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18003ef34  push    rbx
0x18003ef36  push    rbp
0x18003ef37  push    rsi
0x18003ef38  push    rdi
0x18003ef39  push    r12
0x18003ef3b  push    r13
0x18003ef3d  push    r14
0x18003ef3f  push    r15
0x18003ef41  sub     rsp, 38h
0x18003ef45  xor     r12d, r12d
0x18003ef48  mov     rdi, r9
0x18003ef4b  mov     r14d, r8d
0x18003ef4e  mov     rbx, rdx
0x18003ef51  mov     r13, rcx
0x18003ef54  cmp     [rdx], r12
0x18003ef57  jnz     short loc_18003EF6F
0x18003ef59  lea     ecx, [r12+5]; cItemGrow
0x18003ef5e  call    DPA_Create
0x18003ef63  mov     [rbx], rax
0x18003ef66  test    rax, rax
0x18003ef69  jz      loc_18003F0B7
0x18003ef6f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003ef76  mov     ecx, 218h; unsigned __int64
0x18003ef7b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003ef80  mov     rsi, rax
0x18003ef83  test    rax, rax
0x18003ef86  jz      loc_18003F0B7
0x18003ef8c  mov     eax, 7FFFFFFEh
0x18003ef91  lea     r8, [rsi+8]
0x18003ef95  mov     edx, 104h
0x18003ef9a  test    rax, rax
0x18003ef9d  jz      short loc_18003EFBC
0x18003ef9f  movzx   ecx, word ptr [rdi]
0x18003efa2  test    cx, cx
0x18003efa5  jz      short loc_18003EFBC
0x18003efa7  mov     [r8], cx
0x18003efab  add     rdi, 2
0x18003efaf  add     r8, 2
0x18003efb3  dec     rax
0x18003efb6  sub     rdx, 1
0x18003efba  jnz     short loc_18003EF9A
0x18003efbc  mov     rax, rdx
0x18003efbf  lea     rcx, [r8-2]
0x18003efc3  neg     rax
0x18003efc6  sbb     edi, edi
0x18003efc8  not     edi
0x18003efca  and     edi, 8007007Ah
0x18003efd0  test    rdx, rdx
0x18003efd3  cmovnz  rcx, r8
0x18003efd7  mov     [rcx], r12w
0x18003efdb  jz      loc_18003F0A8
0x18003efe1  mov     rcx, [rsp+78h+pidl]; pidl
0x18003efe9  call    cs:__imp_ILClone
0x18003eff0  nop     dword ptr [rax+rax+00h]
0x18003eff5  mov     [rsi], rax
0x18003eff8  mov     rcx, [rbx]; hdpa
0x18003effb  test    rcx, rcx
0x18003effe  jz      short loc_18003F004
0x18003f000  mov     ebp, [rcx]
0x18003f002  jmp     short loc_18003F007
0x18003f004  mov     ebp, r12d
0x18003f007  mov     r8, rsi; p
0x18003f00a  mov     edx, 7FFFFFFFh; i
0x18003f00f  call    DPA_InsertPtr
0x18003f014  mov     edi, eax
0x18003f016  test    eax, eax
0x18003f018  js      loc_18003F0A8
0x18003f01e  cmp     ebp, 0FFFFFFFFh
0x18003f021  jz      loc_18003F0BC
0x18003f027  test    r14d, r14d
0x18003f02a  jnz     loc_18003F0BC
0x18003f030  mov     rbx, [r13+20h]
0x18003f034  lea     rcx, aComboboxPictur; "ComboBox_PictureFolder"
0x18003f03b  call    cs:__imp_StrToID
0x18003f042  nop     dword ptr [rax+rax+00h]
0x18003f047  movzx   edx, ax
0x18003f04a  mov     rcx, rbx
0x18003f04d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003f054  nop     dword ptr [rax+rax+00h]
0x18003f059  mov     r14, rax
0x18003f05c  test    rax, rax
0x18003f05f  jz      short loc_18003F0BC
0x18003f061  call    cs:__imp_?GetClassInfoPtr@Combobox@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Combobox::GetClassInfoPtr(void)
0x18003f068  nop     dword ptr [rax+rax+00h]
0x18003f06d  mov     rcx, [r14]
0x18003f070  mov     rbx, rax
0x18003f073  mov     rax, [rcx+118h]
0x18003f07a  mov     rcx, r14
0x18003f07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f082  cmp     rax, rbx
0x18003f085  jnz     short loc_18003F0BC
0x18003f087  mov     r9d, ebp
0x18003f08a  mov     [rsp+78h+var_58], r12d
0x18003f08f  lea     r8, [rsi+8]
0x18003f093  mov     rdx, r14
0x18003f096  call    ?_FillComboItem@CWallpaperCore@@AEAAHPEAVCombobox@DirectUI@@PEBGHW4PATHTYPE@1@@Z; CWallpaperCore::_FillComboItem(DirectUI::Combobox *,ushort const *,int,CWallpaperCore::PATHTYPE)
0x18003f09b  cmp     eax, 0FFFFFFFFh
0x18003f09e  jz      short loc_18003F0BC
0x18003f0a0  mov     [rsi+210h], eax
0x18003f0a6  jmp     short loc_18003F0BC
0x18003f0a8  mov     edx, 218h; struct std::nothrow_t *
0x18003f0ad  mov     rcx, rsi; void *
0x18003f0b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003f0b5  jmp     short loc_18003F0BC
0x18003f0b7  mov     edi, 8007000Eh
0x18003f0bc  mov     eax, edi
0x18003f0be  add     rsp, 38h
0x18003f0c2  pop     r15
0x18003f0c4  pop     r14
0x18003f0c6  pop     r13
0x18003f0c8  pop     r12
0x18003f0ca  pop     rdi
0x18003f0cb  pop     rsi
0x18003f0cc  pop     rbp
0x18003f0cd  pop     rbx
0x18003f0ce  retn
```
