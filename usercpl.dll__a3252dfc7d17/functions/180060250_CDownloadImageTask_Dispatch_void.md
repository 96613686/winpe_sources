# CDownloadImageTask::Dispatch(void)

- ea: `0x180060250`
- end: `0x180060343`
- name: `?Dispatch@CDownloadImageTask@@UEAAJXZ`
- size: `243`
- prototype: `__int64 __fastcall(CDownloadImageTask *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update`

## callees

- `0x18001315c`
- `0x180060250`
- `0x18006088c`
- `0x180078010`

## import_xrefs

- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x1800602e3`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180060331`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x1800602e3`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180060331`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180060298`
- `DUI70!?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180060298`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180060302`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180060302`

## pseudocode

```c
__int64 __fastcall CDownloadImageTask::Dispatch(CDownloadImageTask *this)
{
  __int64 v2; // rax
  __int64 v3; // r14
  __int64 v4; // rdi
  unsigned __int8 (__fastcall *v5)(__int64, __int64); // rbx
  __int64 ClassInfoPtr; // rax
  UserTile *v7; // rax
  DirectUI::Element *v8; // rcx
  void **v10; // [rsp+20h] [rbp-38h] BYREF
  UserTile *v11; // [rsp+28h] [rbp-30h]

  if ( !*((_BYTE *)this + 64) )
  {
    v2 = *((_QWORD *)this + 9);
    *((_BYTE *)this + 64) = 1;
    v3 = *(_QWORD *)(v2 + 16);
    if ( v3 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v3 + 280LL))(*(_QWORD *)(v2 + 16));
      v5 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 80LL);
      ClassInfoPtr = DirectUI::Element::GetClassInfoPtr();
      if ( v5(v4, ClassInfoPtr) )
      {
        v11 = 0;
        v10 = &CSafeElementPtr<UserTile>::`vftable';
        v7 = (UserTile *)element_cast<UserTile>(v3);
        v8 = 0;
        if ( v7 )
        {
          v11 = v7;
          if ( (int)DirectUI::Element::AddListener(v7, (struct DirectUI::IElementListener *)&v10) < 0 )
            return 0;
          UserTile::SetImagePath(v11, (const unsigned __int16 *)this + 2124);
          v8 = v11;
        }
        v10 = &CSafeElementPtr<UserTile>::`vftable';
        if ( v8 )
          DirectUI::Element::RemoveListener(v8, (struct DirectUI::IElementListener *)&v10);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180060250  push    rbx
0x180060252  push    rsi
0x180060253  push    rdi
0x180060254  push    r14
0x180060256  sub     rsp, 38h
0x18006025a  cmp     byte ptr [rcx+40h], 0
0x18006025e  mov     rsi, rcx
0x180060261  jnz     loc_180060337
0x180060267  mov     rax, [rcx+48h]
0x18006026b  mov     byte ptr [rcx+40h], 1
0x18006026f  mov     r14, [rax+10h]
0x180060273  test    r14, r14
0x180060276  jz      loc_180060337
0x18006027c  mov     rax, [r14]
0x18006027f  mov     rcx, r14
0x180060282  mov     rax, [rax+118h]
0x180060289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006028e  mov     rdi, rax
0x180060291  mov     rcx, [rax]
0x180060294  mov     rbx, [rcx+50h]
0x180060298  call    cs:__imp_?GetClassInfoPtr@Element@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::Element::GetClassInfoPtr(void)
0x18006029e  mov     rdx, rax
0x1800602a1  mov     rcx, rdi
0x1800602a4  mov     rax, rbx
0x1800602a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800602ac  test    al, al
0x1800602ae  jz      loc_180060337
0x1800602b4  lea     rdi, ??_7?$CSafeElementPtr@VUserTile@@@@6B@; const CSafeElementPtr<UserTile>::`vftable'
0x1800602bb  mov     [rsp+58h+var_30], 0
0x1800602c4  mov     rcx, r14
0x1800602c7  mov     [rsp+58h+var_38], rdi
0x1800602cc  call    ??$element_cast@VUserTile@@@@YAPEAVUserTile@@PEAVElement@DirectUI@@@Z; element_cast<UserTile>(DirectUI::Element *)
0x1800602d1  mov     rcx, [rsp+58h+var_30]
0x1800602d6  mov     rbx, rax
0x1800602d9  test    rcx, rcx
0x1800602dc  jz      short loc_1800602F0
0x1800602de  lea     rdx, [rsp+58h+var_38]
0x1800602e3  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x1800602e9  xor     ecx, ecx
0x1800602eb  mov     [rsp+58h+var_30], rcx
0x1800602f0  test    rbx, rbx
0x1800602f3  jz      short loc_180060322
0x1800602f5  lea     rdx, [rsp+58h+var_38]
0x1800602fa  mov     [rsp+58h+var_30], rbx
0x1800602ff  mov     rcx, rbx
0x180060302  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180060308  test    eax, eax
0x18006030a  js      short loc_180060337
0x18006030c  mov     rcx, [rsp+58h+var_30]; this
0x180060311  lea     rdx, [rsi+1098h]; unsigned __int16 *
0x180060318  call    ?SetImagePath@UserTile@@QEAAJPEBG@Z; UserTile::SetImagePath(ushort const *)
0x18006031d  mov     rcx, [rsp+58h+var_30]
0x180060322  mov     [rsp+58h+var_38], rdi
0x180060327  test    rcx, rcx
0x18006032a  jz      short loc_180060337
0x18006032c  lea     rdx, [rsp+58h+var_38]
0x180060331  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x180060337  xor     eax, eax
0x180060339  add     rsp, 38h
0x18006033d  pop     r14
0x18006033f  pop     rdi
0x180060340  pop     rsi
0x180060341  pop     rbx
0x180060342  retn
```
