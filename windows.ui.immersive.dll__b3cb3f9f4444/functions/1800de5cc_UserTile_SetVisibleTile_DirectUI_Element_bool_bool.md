# UserTile::_SetVisibleTile(DirectUI::Element *,bool,bool)

- ea: `0x1800de5cc`
- end: `0x1800de886`
- name: `?_SetVisibleTile@UserTile@@AEAAXPEAVElement@DirectUI@@_N1@Z`
- size: `698`
- prototype: `void __fastcall(UserTile *this, struct DirectUI::Element *, char, char)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800d4464`
- `0x1800de0ec`
- `0x1800de8c4`

## callees

- `0x18003a074`
- `0x180064dd0`
- `0x1800dd940`
- `0x1800de504`
- `0x1800de5cc`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800de6b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800de6b5`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800de683`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800de695`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800de683`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800de695`
- `DUI70!?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800de604`
- `DUI70!?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800de647`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800de632`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800de66f`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800de632`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800de66f`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800de777`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800de7e9`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800de7f9`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800de777`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800de7e9`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800de7f9`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800de80f`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800de860`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800de80f`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800de860`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800de6d1`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800de6e0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800de6d1`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800de6e0`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800de615`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800de658`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800de615`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800de658`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800de749`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800de749`

## pseudocode

```c
void __fastcall UserTile::_SetVisibleTile(UserTile *this, struct DirectUI::Element *a2, char a3, char a4)
{
  DirectUI::Element *v4; // rbp
  DirectUI::Value *Value; // rax
  DirectUI::Value *v9; // r14
  int v10; // ebx
  DirectUI::Value *v11; // rax
  DirectUI::Value *v12; // r15
  const WCHAR *String; // rbx
  const WCHAR *v14; // rax
  int v15; // eax
  __int64 v16; // r9
  struct DirectUI::IClassInfo *v17; // rbx
  __int64 v18; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  __int64 v20; // [rsp+80h] [rbp+8h] BYREF

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
      v9 = Value;
      if ( Value )
      {
        v10 = 0;
        if ( DirectUI::Value::GetType(Value) == 5 )
        {
          v11 = DirectUI::Element::GetValue(
                  a2,
                  (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::CustomProp,
                  1,
                  0);
          v12 = v11;
          if ( v11 )
          {
            if ( DirectUI::Value::GetType(v11) == 5 )
            {
              String = DirectUI::Value::GetString(v12);
              v14 = DirectUI::Value::GetString(v9);
              v15 = CompareStringOrdinal(v14, -1, String, -1, 1);
              v10 = 0;
              if ( v15 == 2 )
                v10 = -2147467259;
            }
            DirectUI::Value::Release(v12);
          }
        }
        DirectUI::Value::Release(v9);
        if ( v10 < 0 )
          goto LABEL_27;
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
LABEL_27:
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
        v20 = 0;
        if ( (int)DirectUI::DuiPVLTrigger::EnsureObject((DirectUI::DuiPVLTrigger *)&v20) >= 0 )
        {
          LOBYTE(v16) = 1;
          LOBYTE(bIgnoreCase) = 1;
          (*(void (__fastcall **)(__int64, DirectUI::Element *, struct DirectUI::Element *, __int64, BOOL, char, _BYTE, _QWORD))(*(_QWORD *)v20 + 176LL))(
            v20,
            v4,
            a2,
            v16,
            bIgnoreCase,
            1,
            0,
            0);
        }
        DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)&v20);
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
    v17 = LowResourceVideo::Class;
    if ( (struct DirectUI::IClassInfo *)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)a2 + 280LL))(a2) == v17 )
    {
      v18 = element_cast<LowResourceVideo>(a2);
      if ( v18 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v18 + 216) + 24LL))(*(_QWORD *)(v18 + 216));
    }
  }
}

```

## disassembly

```asm
0x1800de5cc  mov     [rsp+arg_8], rbx
0x1800de5d1  mov     [rsp+arg_10], rbp
0x1800de5d6  push    rsi
0x1800de5d7  push    rdi
0x1800de5d8  push    r12
0x1800de5da  push    r14
0x1800de5dc  push    r15
0x1800de5de  sub     rsp, 50h
0x1800de5e2  mov     rbp, [rcx+140h]
0x1800de5e9  mov     r12b, r8b
0x1800de5ec  mov     rdi, rdx
0x1800de5ef  mov     rsi, rcx
0x1800de5f2  test    r9b, r9b
0x1800de5f5  jnz     loc_1800DE6F4
0x1800de5fb  test    rbp, rbp
0x1800de5fe  jz      loc_1800DE6F4
0x1800de604  mov     rdx, cs:__imp_?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::CustomProp(void)
0x1800de60b  xor     r9d, r9d
0x1800de60e  mov     rcx, rbp
0x1800de611  lea     r8d, [r9+1]
0x1800de615  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800de61c  nop     dword ptr [rax+rax+00h]
0x1800de621  mov     r14, rax
0x1800de624  test    rax, rax
0x1800de627  jz      loc_1800DE6F4
0x1800de62d  mov     rcx, rax
0x1800de630  xor     ebx, ebx
0x1800de632  call    cs:__imp_?GetType@Value@DirectUI@@QEBAHXZ; DirectUI::Value::GetType(void)
0x1800de639  nop     dword ptr [rax+rax+00h]
0x1800de63e  cmp     eax, 5
0x1800de641  jnz     loc_1800DE6DD
0x1800de647  mov     rdx, cs:__imp_?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::CustomProp(void)
0x1800de64e  lea     r8d, [rbx+1]
0x1800de652  xor     r9d, r9d
0x1800de655  mov     rcx, rdi
0x1800de658  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800de65f  nop     dword ptr [rax+rax+00h]
0x1800de664  mov     r15, rax
0x1800de667  test    rax, rax
0x1800de66a  jz      short loc_1800DE6DD
0x1800de66c  mov     rcx, rax
0x1800de66f  call    cs:__imp_?GetType@Value@DirectUI@@QEBAHXZ; DirectUI::Value::GetType(void)
0x1800de676  nop     dword ptr [rax+rax+00h]
0x1800de67b  cmp     eax, 5
0x1800de67e  jnz     short loc_1800DE6CE
0x1800de680  mov     rcx, r15
0x1800de683  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x1800de68a  nop     dword ptr [rax+rax+00h]
0x1800de68f  mov     rcx, r14
0x1800de692  mov     rbx, rax
0x1800de695  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x1800de69c  nop     dword ptr [rax+rax+00h]
0x1800de6a1  or      edx, 0FFFFFFFFh; cchCount1
0x1800de6a4  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x1800de6ac  mov     r9d, edx; cchCount2
0x1800de6af  mov     r8, rbx; lpString2
0x1800de6b2  mov     rcx, rax; lpString1
0x1800de6b5  call    cs:__imp_CompareStringOrdinal
0x1800de6bc  nop     dword ptr [rax+rax+00h]
0x1800de6c1  xor     ebx, ebx
0x1800de6c3  mov     ecx, 80004005h
0x1800de6c8  cmp     eax, 2
0x1800de6cb  cmovz   ebx, ecx
0x1800de6ce  mov     rcx, r15
0x1800de6d1  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800de6d8  nop     dword ptr [rax+rax+00h]
0x1800de6dd  mov     rcx, r14
0x1800de6e0  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800de6e7  nop     dword ptr [rax+rax+00h]
0x1800de6ec  test    ebx, ebx
0x1800de6ee  js      loc_1800DE85B
0x1800de6f4  test    r12b, r12b
0x1800de6f7  jz      short loc_1800DE743
0x1800de6f9  cmp     byte ptr [rsi+148h], 0
0x1800de700  jnz     short loc_1800DE731
0x1800de702  lea     r8, aAnimationtrap; "AnimationTrap"
0x1800de709  mov     rdx, rsi; struct DirectUI::Element *
0x1800de70c  mov     rcx, rsi; this
0x1800de70f  call    ?_SetBehaviorHelper@UserTile@@AEAAXPEAVElement@DirectUI@@PEBG@Z; UserTile::_SetBehaviorHelper(DirectUI::Element *,ushort const *)
0x1800de714  mov     rdx, [rsi+140h]; struct DirectUI::Element *
0x1800de71b  lea     r8, aImplicitanimat; "ImplicitAnimation"
0x1800de722  mov     rcx, rsi; this
0x1800de725  call    ?_SetBehaviorHelper@UserTile@@AEAAXPEAVElement@DirectUI@@PEBG@Z; UserTile::_SetBehaviorHelper(DirectUI::Element *,ushort const *)
0x1800de72a  mov     byte ptr [rsi+148h], 1
0x1800de731  lea     r8, aImplicitanimat; "ImplicitAnimation"
0x1800de738  mov     rdx, rdi; struct DirectUI::Element *
0x1800de73b  mov     rcx, rsi; this
0x1800de73e  call    ?_SetBehaviorHelper@UserTile@@AEAAXPEAVElement@DirectUI@@PEBG@Z; UserTile::_SetBehaviorHelper(DirectUI::Element *,ushort const *)
0x1800de743  mov     rdx, rdi
0x1800de746  mov     rcx, rsi
0x1800de749  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x1800de750  nop     dword ptr [rax+rax+00h]
0x1800de755  test    eax, eax
0x1800de757  js      loc_1800DE85B
0x1800de75d  mov     [rsi+140h], rdi
0x1800de764  mov     rcx, rdi
0x1800de767  test    r12b, r12b
0x1800de76a  jz      loc_1800DE7F7
0x1800de770  test    rbp, rbp
0x1800de773  jz      short loc_1800DE7E7
0x1800de775  xor     edx, edx
0x1800de777  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800de77e  nop     dword ptr [rax+rax+00h]
0x1800de783  lea     rcx, [rsp+78h+arg_0]; this
0x1800de78b  mov     [rsp+78h+arg_0], 0
0x1800de797  call    ?EnsureObject@DuiPVLTrigger@DirectUI@@IEAAJXZ; DirectUI::DuiPVLTrigger::EnsureObject(void)
0x1800de79c  test    eax, eax
0x1800de79e  js      short loc_1800DE7D8
0x1800de7a0  mov     rcx, [rsp+78h+arg_0]
0x1800de7a8  mov     r9b, 1
0x1800de7ab  mov     [rsp+78h+var_40], 0
0x1800de7b4  mov     r8, rdi
0x1800de7b7  mov     [rsp+78h+var_48], 0
0x1800de7bc  mov     rdx, rbp
0x1800de7bf  mov     [rsp+78h+var_50], 1
0x1800de7c4  mov     rax, [rcx]
0x1800de7c7  mov     byte ptr [rsp+78h+bIgnoreCase], 1
0x1800de7cc  mov     rax, [rax+0B0h]
0x1800de7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de7d8  lea     rcx, [rsp+78h+arg_0]; this
0x1800de7e0  call    ??1DuiPVLTrigger@DirectUI@@QEAA@XZ; DirectUI::DuiPVLTrigger::~DuiPVLTrigger(void)
0x1800de7e5  jmp     short loc_1800DE81B
0x1800de7e7  mov     dl, 1
0x1800de7e9  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800de7f0  nop     dword ptr [rax+rax+00h]
0x1800de7f5  jmp     short loc_1800DE81B
0x1800de7f7  mov     dl, 1
0x1800de7f9  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800de800  nop     dword ptr [rax+rax+00h]
0x1800de805  test    rbp, rbp
0x1800de808  jz      short loc_1800DE81B
0x1800de80a  mov     dl, 1
0x1800de80c  mov     rcx, rbp
0x1800de80f  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800de816  nop     dword ptr [rax+rax+00h]
0x1800de81b  mov     rax, [rdi]
0x1800de81e  mov     rcx, rdi
0x1800de821  mov     rbx, cs:?Class@LowResourceVideo@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * LowResourceVideo::Class
0x1800de828  mov     rax, [rax+118h]
0x1800de82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de834  cmp     rax, rbx
0x1800de837  jnz     short loc_1800DE86C
0x1800de839  mov     rcx, rdi
0x1800de83c  call    ??$element_cast@VLowResourceVideo@@@@YAPEAVLowResourceVideo@@PEAVElement@DirectUI@@@Z; element_cast<LowResourceVideo>(DirectUI::Element *)
0x1800de841  test    rax, rax
0x1800de844  jz      short loc_1800DE86C
0x1800de846  mov     rcx, [rax+0D8h]
0x1800de84d  mov     rax, [rcx]
0x1800de850  mov     rax, [rax+18h]
0x1800de854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de859  jmp     short loc_1800DE86C
0x1800de85b  mov     dl, 1
0x1800de85d  mov     rcx, rdi
0x1800de860  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800de867  nop     dword ptr [rax+rax+00h]
0x1800de86c  lea     r11, [rsp+78h+var_28]
0x1800de871  mov     rbx, [r11+38h]
0x1800de875  mov     rbp, [r11+40h]
0x1800de879  mov     rsp, r11
0x1800de87c  pop     r15
0x1800de87e  pop     r14
0x1800de880  pop     r12
0x1800de882  pop     rdi
0x1800de883  pop     rsi
0x1800de884  retn
```
