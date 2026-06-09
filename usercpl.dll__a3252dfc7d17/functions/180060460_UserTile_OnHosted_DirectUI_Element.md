# UserTile::OnHosted(DirectUI::Element *)

- ea: `0x180060460`
- end: `0x1800605db`
- name: `?OnHosted@UserTile@@MEAAXPEAVElement@DirectUI@@@Z`
- size: `379`
- prototype: `void __fastcall(UserTile *__hidden this, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180060460`
- `0x180061158`

## import_xrefs

- `SHELL32!__imp_SHChangeNotifyRegister` at `0x18006054f`
- `SHELL32!__imp_SHChangeNotifyRegister` at `0x18006054f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800604d8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800604d8`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x18006056e`
- `DUI70!?SetAccRole@Element@DirectUI@@QEAAJH@Z` at `0x18006056e`
- `DUI70!?Destroy@Layout@DirectUI@@QEAAXXZ` at `0x1800605ca`
- `DUI70!?Destroy@Layout@DirectUI@@QEAAXXZ` at `0x1800605ca`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x180060560`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x180060560`
- `DUI70!?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z` at `0x1800605bb`
- `DUI70!?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z` at `0x1800605bb`
- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x1800605a9`
- `DUI70!?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z` at `0x1800605a9`
- `DUI70!?OnHosted@Element@DirectUI@@MEAAXPEAV12@@Z` at `0x18006046d`
- `DUI70!?OnHosted@Element@DirectUI@@MEAAXPEAV12@@Z` at `0x18006046d`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18006057e`
- `DUI70!?SetAccName@Element@DirectUI@@QEAAJPEBG@Z` at `0x18006057e`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x1800604b6`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x180060505`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x1800604b6`
- `SHCORE!__imp_SHCreateWorkerWindowW` at `0x180060505`

## pseudocode

```c
void __fastcall UserTile::OnHosted(HANDLE *this, struct DirectUI::Element *a2)
{
  __int64 v3; // rax
  HWND v4; // rcx
  SHChangeNotifyEntry pshcne; // [rsp+30h] [rbp-18h] BYREF
  struct DirectUI::Layout *v6; // [rsp+50h] [rbp+8h] BYREF

  DirectUI::Element::OnHosted((DirectUI::Element *)this, a2);
  if ( this[28] )
    goto LABEL_12;
  if ( *((_BYTE *)this + 232) )
  {
    if ( this[31]
      && this[30]
      && (v3 = SHCreateWorkerWindowW(CImpWorkerWndProc::s_WndProc, 0, 0, 0, 0, this + 27), (this[28] = (HANDLE)v3) != 0) )
    {
      if ( *((_BYTE *)this + 232) )
      {
        if ( ++*((_DWORD *)this + 59) == 1 )
        {
          ResetEvent(this[30]);
          v3 = (__int64)this[28];
        }
      }
    }
    else
    {
      v3 = 0;
    }
  }
  else
  {
    v3 = SHCreateWorkerWindowW(CImpWorkerWndProc::s_WndProc, 0, 0, 0, 0, this + 27);
    this[28] = (HANDLE)v3;
  }
  if ( v3 )
  {
LABEL_12:
    v4 = (HWND)this[28];
    pshcne.pidl = 0;
    pshcne.fRecursive = 0;
    *((_DWORD *)this + 72) = SHChangeNotifyRegister(v4, 32770, 0x4000000, 0x401u, 1, &pshcne);
  }
  DirectUI::Element::SetAccessible((DirectUI::Element *)this, 1);
  DirectUI::Element::SetAccRole((DirectUI::Element *)this, 40);
  DirectUI::Element::SetAccName((DirectUI::Element *)this, L"UserTile");
  if ( ((_BYTE)this[32] & 1) == 0 )
    UserTile::_UpdateTile((UserTile *)this, 1, 1);
  v6 = 0;
  if ( (int)DirectUI::FillLayout::Create(&v6) >= 0
    && (int)DirectUI::Element::SetLayout((DirectUI::Element *)this, v6) < 0 )
  {
    DirectUI::Layout::Destroy(v6);
  }
}

```

## disassembly

```asm
0x180060460  mov     [rsp+arg_8], rbx
0x180060465  push    rdi
0x180060466  sub     rsp, 40h
0x18006046a  mov     rdi, rcx
0x18006046d  call    cs:__imp_?OnHosted@Element@DirectUI@@MEAAXPEAV12@@Z; DirectUI::Element::OnHosted(DirectUI::Element *)
0x180060473  lea     rbx, [rdi+0D8h]
0x18006047a  cmp     qword ptr [rbx+8], 0
0x18006047f  jnz     loc_180060514
0x180060485  cmp     byte ptr [rbx+10h], 0
0x180060489  jz      short loc_1800604E8
0x18006048b  cmp     qword ptr [rbx+20h], 0
0x180060490  jz      short loc_1800604E4
0x180060492  cmp     qword ptr [rbx+18h], 0
0x180060497  jz      short loc_1800604E4
0x180060499  mov     [rsp+48h+pshcne], rbx
0x18006049e  lea     rcx, ?s_WndProc@CImpWorkerWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWorkerWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800604a5  xor     r9d, r9d
0x1800604a8  mov     qword ptr [rsp+48h+cEntries], 0
0x1800604b1  xor     r8d, r8d
0x1800604b4  xor     edx, edx
0x1800604b6  call    cs:__imp_SHCreateWorkerWindowW
0x1800604bc  mov     [rbx+8], rax
0x1800604c0  test    rax, rax
0x1800604c3  jz      short loc_1800604E4
0x1800604c5  cmp     byte ptr [rbx+10h], 0
0x1800604c9  jz      short loc_18006050F
0x1800604cb  inc     dword ptr [rbx+14h]
0x1800604ce  cmp     dword ptr [rbx+14h], 1
0x1800604d2  jnz     short loc_18006050F
0x1800604d4  mov     rcx, [rbx+18h]; hEvent
0x1800604d8  call    cs:__imp_ResetEvent
0x1800604de  mov     rax, [rbx+8]
0x1800604e2  jmp     short loc_18006050F
0x1800604e4  xor     eax, eax
0x1800604e6  jmp     short loc_18006050F
0x1800604e8  mov     [rsp+48h+pshcne], rbx
0x1800604ed  lea     rcx, ?s_WndProc@CImpWorkerWndProc@@KA_JPEAUHWND__@@I_K_J@Z; CImpWorkerWndProc::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800604f4  xor     r9d, r9d
0x1800604f7  mov     qword ptr [rsp+48h+cEntries], 0
0x180060500  xor     r8d, r8d
0x180060503  xor     edx, edx
0x180060505  call    cs:__imp_SHCreateWorkerWindowW
0x18006050b  mov     [rbx+8], rax
0x18006050f  test    rax, rax
0x180060512  jz      short loc_18006055B
0x180060514  mov     rcx, [rdi+0E0h]; hwnd
0x18006051b  lea     rax, [rsp+48h+var_18]
0x180060520  mov     [rsp+48h+pshcne], rax; pshcne
0x180060525  mov     edx, 8002h; fSources
0x18006052a  mov     r9d, 401h; wMsg
0x180060530  mov     [rsp+48h+cEntries], 1; cEntries
0x180060538  mov     r8d, 4000000h; fEvents
0x18006053e  mov     [rsp+48h+var_18.pidl], 0
0x180060547  mov     [rsp+48h+var_18.fRecursive], 0
0x18006054f  call    cs:__imp_SHChangeNotifyRegister
0x180060555  mov     [rdi+120h], eax
0x18006055b  mov     dl, 1
0x18006055d  mov     rcx, rdi
0x180060560  call    cs:__imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x180060566  mov     edx, 28h ; '('
0x18006056b  mov     rcx, rdi
0x18006056e  call    cs:__imp_?SetAccRole@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccRole(int)
0x180060574  lea     rdx, aUsertile; "UserTile"
0x18006057b  mov     rcx, rdi
0x18006057e  call    cs:__imp_?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x180060584  test    byte ptr [rdi+100h], 1
0x18006058b  jnz     short loc_18006059B
0x18006058d  mov     r8b, 1; bool
0x180060590  mov     rcx, rdi; this
0x180060593  mov     dl, r8b; bool
0x180060596  call    ?_UpdateTile@UserTile@@AEAAJ_N0@Z; UserTile::_UpdateTile(bool,bool)
0x18006059b  lea     rcx, [rsp+48h+arg_0]
0x1800605a0  mov     [rsp+48h+arg_0], 0
0x1800605a9  call    cs:__imp_?Create@FillLayout@DirectUI@@SAJPEAPEAVLayout@2@@Z; DirectUI::FillLayout::Create(DirectUI::Layout * *)
0x1800605af  test    eax, eax
0x1800605b1  js      short loc_1800605D0
0x1800605b3  mov     rdx, [rsp+48h+arg_0]
0x1800605b8  mov     rcx, rdi
0x1800605bb  call    cs:__imp_?SetLayout@Element@DirectUI@@QEAAJPEAVLayout@2@@Z; DirectUI::Element::SetLayout(DirectUI::Layout *)
0x1800605c1  test    eax, eax
0x1800605c3  jns     short loc_1800605D0
0x1800605c5  mov     rcx, [rsp+48h+arg_0]
0x1800605ca  call    cs:__imp_?Destroy@Layout@DirectUI@@QEAAXXZ; DirectUI::Layout::Destroy(void)
0x1800605d0  mov     rbx, [rsp+48h+arg_8]
0x1800605d5  add     rsp, 40h
0x1800605d9  pop     rdi
0x1800605da  retn
```
