# CBaseAppearancePage::UpdateCharsetChanges(void)

- ea: `0x18003c840`
- end: `0x18003c95b`
- name: `?UpdateCharsetChanges@CBaseAppearancePage@@UEAAJXZ`
- size: `283`
- prototype: `__int64 __fastcall(CBaseAppearancePage *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x18003c840`
- `0x18003cb0c`
- `0x18003cc00`
- `0x18006018c`
- `0x18006d010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x18003c932`
- `SHCORE!IUnknown_SetSite` at `0x18003c932`
- `SHCORE!SHDeleteKeyW` at `0x18003c925`
- `SHCORE!SHDeleteKeyW` at `0x18003c925`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18003c852`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18003c852`

## pseudocode

```c
__int64 __fastcall CBaseAppearancePage::UpdateCharsetChanges(CBaseAppearancePage *this)
{
  HKEY v2; // rcx
  int State; // ebx
  struct IThemeSize *v4; // rdx
  bool v5; // zf
  __int64 (__fastcall ***v6)(_QWORD, GUID *, IUnknown **); // rcx
  LANGID UserDefaultUILanguage; // [rsp+48h] [rbp+10h] BYREF
  IUnknown *punk; // [rsp+50h] [rbp+18h] BYREF

  UserDefaultUILanguage = GetUserDefaultUILanguage();
  State = HrSHSetValue(v2, L"Control Panel\\Appearance", L"SchemeLangID", 3u, &UserDefaultUILanguage, 2u);
  if ( State >= 0 )
  {
    State = CBaseAppearancePage::_LoadState((CBaseAppearancePage *)((char *)this - 64));
    if ( State >= 0 )
    {
      *((_DWORD *)this + 204) |= 1u;
      v5 = *((_QWORD *)this + 7) == 0;
      *((_DWORD *)this + 5) = 1;
      if ( v5
        || (State = CBaseAppearancePage::_LoadSizeFonts(
                      (CBaseAppearancePage *)((char *)this - 64),
                      v4,
                      (CBaseAppearancePage *)((char *)this + 820)),
            State >= 0) )
      {
        v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, IUnknown **))*((_QWORD *)this - 7);
        if ( v6 )
        {
          punk = 0;
          State = (**v6)(v6, &GUID_bfaf1e27_72b8_4491_a4cd_2762d6137a59, &punk);
          if ( State >= 0 )
          {
            State = ((__int64 (__fastcall *)(IUnknown *, __int64))punk->lpVtbl[1].Release)(punk, 4);
            SHDeleteKeyW(HKEY_CURRENT_USER, L"Control Panel\\Appearance\\New Schemes\\Current Settings SaveAll");
            IUnknown_SetSite(punk, 0);
            ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
          }
        }
      }
    }
  }
  return (unsigned int)State;
}

```

## disassembly

```asm
0x18003c840  mov     [rsp+arg_0], rbx
0x18003c845  mov     [rsp+arg_18], rsi
0x18003c84a  push    rdi
0x18003c84b  sub     rsp, 30h
0x18003c84f  mov     rdi, rcx
0x18003c852  call    cs:__imp_GetUserDefaultUILanguage
0x18003c858  mov     [rsp+38h+var_10], 2; DWORD
0x18003c860  lea     r8, aSchemelangid; "SchemeLangID"
0x18003c867  mov     [rsp+38h+arg_8], ax
0x18003c86c  lea     rdx, aControlPanelAp_0; "Control Panel\\Appearance"
0x18003c873  lea     rax, [rsp+38h+arg_8]
0x18003c878  mov     r9d, 3; unsigned int
0x18003c87e  mov     [rsp+38h+var_18], rax; LPCVOID
0x18003c883  call    ?HrSHSetValue@@YAJPEAUHKEY__@@PEBG1KPEBXK@Z; HrSHSetValue(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong)
0x18003c888  mov     ebx, eax
0x18003c88a  test    eax, eax
0x18003c88c  js      loc_18003C949
0x18003c892  lea     rcx, [rdi-40h]; this
0x18003c896  call    ?_LoadState@CBaseAppearancePage@@AEAAJXZ; CBaseAppearancePage::_LoadState(void)
0x18003c89b  mov     ebx, eax
0x18003c89d  test    eax, eax
0x18003c89f  js      loc_18003C949
0x18003c8a5  or      dword ptr [rdi+330h], 1
0x18003c8ac  cmp     qword ptr [rdi+38h], 0
0x18003c8b1  mov     dword ptr [rdi+14h], 1
0x18003c8b8  jz      short loc_18003C8D0
0x18003c8ba  lea     r8, [rdi+334h]; struct SCHEMEDATA *
0x18003c8c1  lea     rcx, [rdi-40h]; this
0x18003c8c5  call    ?_LoadSizeFonts@CBaseAppearancePage@@AEAAJPEAUIThemeSize@@PEAUSCHEMEDATA@@@Z; CBaseAppearancePage::_LoadSizeFonts(IThemeSize *,SCHEMEDATA *)
0x18003c8ca  mov     ebx, eax
0x18003c8cc  test    eax, eax
0x18003c8ce  js      short loc_18003C949
0x18003c8d0  mov     rcx, [rdi-38h]
0x18003c8d4  test    rcx, rcx
0x18003c8d7  jz      short loc_18003C949
0x18003c8d9  mov     [rsp+38h+punk], 0
0x18003c8e2  lea     r8, [rsp+38h+punk]
0x18003c8e7  mov     rax, [rcx]
0x18003c8ea  lea     rdx, _GUID_bfaf1e27_72b8_4491_a4cd_2762d6137a59
0x18003c8f1  mov     rax, [rax]
0x18003c8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8f9  mov     ebx, eax
0x18003c8fb  test    eax, eax
0x18003c8fd  js      short loc_18003C949
0x18003c8ff  mov     rcx, [rsp+38h+punk]
0x18003c904  mov     edx, 4
0x18003c909  mov     rax, [rcx]
0x18003c90c  mov     rax, [rax+28h]
0x18003c910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c915  lea     rdx, aControlPanelAp; "Control Panel\\Appearance\\New Schemes"...
0x18003c91c  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18003c923  mov     ebx, eax
0x18003c925  call    cs:__imp_SHDeleteKeyW
0x18003c92b  mov     rcx, [rsp+38h+punk]; punk
0x18003c930  xor     edx, edx; punkSite
0x18003c932  call    cs:__imp_IUnknown_SetSite
0x18003c938  mov     rcx, [rsp+38h+punk]
0x18003c93d  mov     rax, [rcx]
0x18003c940  mov     rax, [rax+10h]
0x18003c944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c949  mov     rsi, [rsp+38h+arg_18]
0x18003c94e  mov     eax, ebx
0x18003c950  mov     rbx, [rsp+38h+arg_0]
0x18003c955  add     rsp, 30h
0x18003c959  pop     rdi
0x18003c95a  retn
```
