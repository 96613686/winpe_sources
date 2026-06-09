# UserTile::_SetVisibleTile(DirectUI::Element *,bool,bool)

- ea: `0x180060ea8`
- end: `0x180061101`
- name: `?_SetVisibleTile@UserTile@@AEAAXPEAVElement@DirectUI@@_N1@Z`
- size: `601`
- prototype: `void __fastcall(UserTile *__hidden this, struct DirectUI::Element *, bool, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006088c`
- `0x180061158`

## callees

- `0x18005fbf8`
- `0x180060c98`
- `0x180060ea8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180060f4a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180060f4a`
- `DUI70!?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180060ee0`
- `DUI70!?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180060f0b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180060ef1`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180060f1c`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180060ef1`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180060f1c`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180060fca`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180060fca`
- `DUI70!DuiCreateObject` at `0x18006101e`
- `DUI70!DuiCreateObject` at `0x18006101e`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180061097`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800610e2`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180061097`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800610e2`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180060ff6`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18006107d`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180061087`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180060ff6`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18006107d`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x180061087`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180060f5e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180060f67`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180060f5e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180060f67`

## pseudocode

```c
void __fastcall UserTile::_SetVisibleTile(UserTile *this, struct DirectUI::Element *a2, char a3, char a4)
{
  DirectUI::Element *v4; // rsi
  struct DirectUI::Value *Value; // rax
  LPCWCH *v9; // r14
  int v10; // ebp
  struct DirectUI::Value *v11; // rax
  DirectUI::Value *v12; // r15
  __int64 v13; // r9
  struct DirectUI::IClassInfo *v14; // rbx
  __int64 v15; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  void *v17; // [rsp+80h] [rbp+8h] BYREF

  v4 = (DirectUI::Element *)*((_QWORD *)this + 40);
  if ( !a4 )
  {
    if ( v4 )
    {
      Value = DirectUI::Element::GetValue(
                *((DirectUI::Element **)this + 40),
                (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::CustomProp,
                1,
                0);
      v9 = (LPCWCH *)Value;
      if ( Value )
      {
        v10 = 0;
        if ( (*(_BYTE *)Value & 0x3F) == 5 )
        {
          v11 = DirectUI::Element::GetValue(
                  a2,
                  (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::CustomProp,
                  1,
                  0);
          v12 = v11;
          if ( v11 )
          {
            if ( (*(_BYTE *)v11 & 0x3F) == 5 && CompareStringOrdinal(v9[1], -1, *((LPCWCH *)v11 + 1), -1, 1) == 2 )
              v10 = -2147467259;
            DirectUI::Value::Release(v12);
          }
        }
        DirectUI::Value::Release((DirectUI::Value *)v9);
        if ( v10 < 0 )
          goto LABEL_28;
      }
    }
  }
  if ( a3 )
  {
    if ( !*((_BYTE *)this + 328) )
    {
      UserTile::_SetBehaviorHelper(this, this, L"AnimationTrap");
      UserTile::_SetBehaviorHelper(this, *((struct DirectUI::Element **)this + 40), L"ImplicitAnimation");
      *((_BYTE *)this + 328) = 1;
    }
    UserTile::_SetBehaviorHelper(this, a2, L"ImplicitAnimation");
  }
  if ( (int)DirectUI::Element::Add(this, a2) < 0 )
  {
LABEL_28:
    DirectUI::Element::Destroy(a2, 1);
  }
  else
  {
    *((_QWORD *)this + 40) = a2;
    if ( a3 )
    {
      if ( v4 )
      {
        DirectUI::Element::SetVisible(a2, 0);
        v17 = 0;
        if ( (int)DuiCreateObject(
                    &GUID_7627b482_f285_41e7_996d_368ed0052602,
                    &GUID_0372c617_aeb1_4bcc_8703_dad13e0c7d8a,
                    &v17) >= 0 )
        {
          LOBYTE(v13) = 1;
          LOBYTE(bIgnoreCase) = 1;
          (*(void (__fastcall **)(void *, DirectUI::Element *, struct DirectUI::Element *, __int64, BOOL, char, _BYTE, _QWORD))(*(_QWORD *)v17 + 176LL))(
            v17,
            v4,
            a2,
            v13,
            bIgnoreCase,
            1,
            0,
            0);
        }
        if ( v17 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v17 + 16LL))(v17);
      }
      else
      {
        DirectUI::Element::SetVisible(a2, 1);
      }
    }
    else
    {
      DirectUI::Element::SetVisible(a2, 1);
      if ( v4 )
        DirectUI::Element::Destroy(v4, 1);
    }
    v14 = LowResourceVideo::Class;
    if ( (struct DirectUI::IClassInfo *)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)a2 + 280LL))(a2) == v14 )
    {
      v15 = element_cast<LowResourceVideo>(a2);
      if ( v15 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v15 + 216) + 24LL))(*(_QWORD *)(v15 + 216));
    }
  }
}

```

## disassembly

```asm
0x180060ea8  mov     [rsp+arg_8], rbx
0x180060ead  mov     [rsp+arg_10], rbp
0x180060eb2  push    rsi
0x180060eb3  push    rdi
0x180060eb4  push    r12
0x180060eb6  push    r14
0x180060eb8  push    r15
0x180060eba  sub     rsp, 50h
0x180060ebe  mov     rsi, [rcx+140h]
0x180060ec5  mov     r12b, r8b
0x180060ec8  mov     rdi, rdx
0x180060ecb  mov     rbx, rcx
0x180060ece  test    r9b, r9b
0x180060ed1  jnz     loc_180060F75
0x180060ed7  test    rsi, rsi
0x180060eda  jz      loc_180060F75
0x180060ee0  mov     rdx, cs:__imp_?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::CustomProp(void)
0x180060ee7  xor     r9d, r9d
0x180060eea  mov     rcx, rsi
0x180060eed  lea     r8d, [r9+1]
0x180060ef1  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180060ef7  mov     r14, rax
0x180060efa  test    rax, rax
0x180060efd  jz      short loc_180060F75
0x180060eff  mov     ecx, [rax]
0x180060f01  xor     ebp, ebp
0x180060f03  and     ecx, 3Fh
0x180060f06  cmp     cl, 5
0x180060f09  jnz     short loc_180060F64
0x180060f0b  mov     rdx, cs:__imp_?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::CustomProp(void)
0x180060f12  lea     r8d, [rbp+1]
0x180060f16  xor     r9d, r9d
0x180060f19  mov     rcx, rdi
0x180060f1c  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180060f22  mov     r15, rax
0x180060f25  test    rax, rax
0x180060f28  jz      short loc_180060F64
0x180060f2a  mov     ecx, [rax]
0x180060f2c  and     ecx, 3Fh
0x180060f2f  cmp     cl, 5
0x180060f32  jnz     short loc_180060F5B
0x180060f34  mov     r8, [rax+8]; lpString2
0x180060f38  or      edx, 0FFFFFFFFh; cchCount1
0x180060f3b  mov     rcx, [r14+8]; lpString1
0x180060f3f  mov     r9d, edx; cchCount2
0x180060f42  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180060f4a  call    cs:__imp_CompareStringOrdinal
0x180060f50  cmp     eax, 2
0x180060f53  mov     ecx, 80004005h
0x180060f58  cmovz   ebp, ecx
0x180060f5b  mov     rcx, r15
0x180060f5e  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180060f64  mov     rcx, r14
0x180060f67  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180060f6d  test    ebp, ebp
0x180060f6f  js      loc_1800610DD
0x180060f75  test    r12b, r12b
0x180060f78  jz      short loc_180060FC4
0x180060f7a  cmp     byte ptr [rbx+148h], 0
0x180060f81  jnz     short loc_180060FB2
0x180060f83  lea     r8, aAnimationtrap; "AnimationTrap"
0x180060f8a  mov     rdx, rbx; struct DirectUI::Element *
0x180060f8d  mov     rcx, rbx; this
0x180060f90  call    ?_SetBehaviorHelper@UserTile@@AEAAXPEAVElement@DirectUI@@PEBG@Z; UserTile::_SetBehaviorHelper(DirectUI::Element *,ushort const *)
0x180060f95  mov     rdx, [rbx+140h]; struct DirectUI::Element *
0x180060f9c  lea     r8, aImplicitanimat; "ImplicitAnimation"
0x180060fa3  mov     rcx, rbx; this
0x180060fa6  call    ?_SetBehaviorHelper@UserTile@@AEAAXPEAVElement@DirectUI@@PEBG@Z; UserTile::_SetBehaviorHelper(DirectUI::Element *,ushort const *)
0x180060fab  mov     byte ptr [rbx+148h], 1
0x180060fb2  lea     r8, aImplicitanimat; "ImplicitAnimation"
0x180060fb9  mov     rdx, rdi; struct DirectUI::Element *
0x180060fbc  mov     rcx, rbx; this
0x180060fbf  call    ?_SetBehaviorHelper@UserTile@@AEAAXPEAVElement@DirectUI@@PEBG@Z; UserTile::_SetBehaviorHelper(DirectUI::Element *,ushort const *)
0x180060fc4  mov     rdx, rdi
0x180060fc7  mov     rcx, rbx
0x180060fca  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180060fd0  test    eax, eax
0x180060fd2  js      loc_1800610DD
0x180060fd8  mov     [rbx+140h], rdi
0x180060fdf  mov     rcx, rdi
0x180060fe2  test    r12b, r12b
0x180060fe5  jz      loc_180061085
0x180060feb  test    rsi, rsi
0x180060fee  jz      loc_18006107B
0x180060ff4  xor     edx, edx
0x180060ff6  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180060ffc  lea     r8, [rsp+78h+arg_0]
0x180061004  mov     [rsp+78h+arg_0], 0
0x180061010  lea     rdx, _GUID_0372c617_aeb1_4bcc_8703_dad13e0c7d8a
0x180061017  lea     rcx, _GUID_7627b482_f285_41e7_996d_368ed0052602
0x18006101e  call    cs:__imp_?DuiCreateObject@@YAJAEBU_GUID@@0PEAPEAX@Z; DuiCreateObject(_GUID const &,_GUID const &,void * *)
0x180061024  test    eax, eax
0x180061026  js      short loc_180061060
0x180061028  mov     rcx, [rsp+78h+arg_0]
0x180061030  mov     r9b, 1
0x180061033  mov     [rsp+78h+var_40], 0
0x18006103c  mov     r8, rdi
0x18006103f  mov     [rsp+78h+var_48], 0
0x180061044  mov     rdx, rsi
0x180061047  mov     [rsp+78h+var_50], 1
0x18006104c  mov     rax, [rcx]
0x18006104f  mov     byte ptr [rsp+78h+bIgnoreCase], 1
0x180061054  mov     rax, [rax+0B0h]
0x18006105b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061060  mov     rcx, [rsp+78h+arg_0]
0x180061068  test    rcx, rcx
0x18006106b  jz      short loc_18006109D
0x18006106d  mov     rax, [rcx]
0x180061070  mov     rax, [rax+10h]
0x180061074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061079  jmp     short loc_18006109D
0x18006107b  mov     dl, 1
0x18006107d  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180061083  jmp     short loc_18006109D
0x180061085  mov     dl, 1
0x180061087  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x18006108d  test    rsi, rsi
0x180061090  jz      short loc_18006109D
0x180061092  mov     dl, 1
0x180061094  mov     rcx, rsi
0x180061097  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18006109d  mov     rax, [rdi]
0x1800610a0  mov     rcx, rdi
0x1800610a3  mov     rbx, cs:?Class@LowResourceVideo@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * LowResourceVideo::Class
0x1800610aa  mov     rax, [rax+118h]
0x1800610b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800610b6  cmp     rax, rbx
0x1800610b9  jnz     short loc_1800610E8
0x1800610bb  mov     rcx, rdi
0x1800610be  call    ??$element_cast@VLowResourceVideo@@@@YAPEAVLowResourceVideo@@PEAVElement@DirectUI@@@Z; element_cast<LowResourceVideo>(DirectUI::Element *)
0x1800610c3  test    rax, rax
0x1800610c6  jz      short loc_1800610E8
0x1800610c8  mov     rcx, [rax+0D8h]
0x1800610cf  mov     rax, [rcx]
0x1800610d2  mov     rax, [rax+18h]
0x1800610d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800610db  jmp     short loc_1800610E8
0x1800610dd  mov     dl, 1
0x1800610df  mov     rcx, rdi
0x1800610e2  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800610e8  lea     r11, [rsp+78h+var_28]
0x1800610ed  mov     rbx, [r11+38h]
0x1800610f1  mov     rbp, [r11+40h]
0x1800610f5  mov     rsp, r11
0x1800610f8  pop     r15
0x1800610fa  pop     r14
0x1800610fc  pop     r12
0x1800610fe  pop     rdi
0x1800610ff  pop     rsi
0x180061100  retn
```
