# StartList::Stop(Accommodation *)

- ea: `0x140017904`
- end: `0x1400179ea`
- name: `?Stop@StartList@@QEAAJPEAVAccommodation@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(StartList *__hidden this, struct Accommodation *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140017b08`
- `0x140022b10`

## callees

- `0x14000e550`
- `0x140014d0c`
- `0x140015fb8`
- `0x1400169e8`
- `0x140016b24`
- `0x140016e8c`
- `0x140017904`
- `0x140019090`
- `0x14001ccb0`
- `0x140026a44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140017976`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140017976`

## pseudocode

```c
__int64 __fastcall StartList::Stop(StartList *this, const wchar_t **a2)
{
  __int64 result; // rax
  signed int v5; // edi
  unsigned int v6; // eax
  __int64 v7; // r8
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r11

  if ( !a2 )
    return 2147942487LL;
  if ( CATUtils::IsDesktopOOBEUserSessionActive() && !wcscmp_0(a2[5], L"SystemSetting") )
    StartList::Remove(this, (struct Accommodation *)a2);
  result = StartList::LoadSettings(this);
  v5 = result;
  if ( (int)result >= 0 )
  {
    if ( !wcscmp_0(a2[5], L"SystemSetting") )
    {
      v6 = _o__wtoi(a2[3]);
      if ( v6 < 0x16 )
        v5 = SystemSettings::TurnOff(a2, v6, v7, *((_DWORD *)this + 73));
    }
    v8 = (-(__int64)((unsigned int)IsInteractiveUser() != 0) & 0xFFFFFFFFFFFFFFD0uLL) + 96;
    if ( v5 >= 0 )
    {
      v9 = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Find(
             (char *)this + v8,
             *a2);
      if ( v9 )
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAt(
          v10,
          v9);
      StartList::SaveSessionKey(this);
    }
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x140017904  mov     [rsp+arg_0], rbx
0x140017909  mov     [rsp+arg_8], rsi
0x14001790e  push    rdi
0x14001790f  sub     rsp, 20h
0x140017913  mov     rbx, rdx
0x140017916  mov     rsi, rcx
0x140017919  test    rdx, rdx
0x14001791c  jnz     short loc_140017928
0x14001791e  mov     eax, 80070057h
0x140017923  jmp     loc_1400179D9
0x140017928  call    ?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ; CATUtils::IsDesktopOOBEUserSessionActive(void)
0x14001792d  test    al, al
0x14001792f  jz      short loc_140017950
0x140017931  mov     rcx, [rbx+28h]; String1
0x140017935  lea     rdx, aSystemsetting; "SystemSetting"
0x14001793c  call    wcscmp_0
0x140017941  test    eax, eax
0x140017943  jnz     short loc_140017950
0x140017945  mov     rdx, rbx; struct Accommodation *
0x140017948  mov     rcx, rsi; this
0x14001794b  call    ?Remove@StartList@@QEAAJPEAVAccommodation@@@Z; StartList::Remove(Accommodation *)
0x140017950  mov     rcx, rsi; this
0x140017953  call    ?LoadSettings@StartList@@AEAAJXZ; StartList::LoadSettings(void)
0x140017958  mov     edi, eax
0x14001795a  test    eax, eax
0x14001795c  js      short loc_1400179D9
0x14001795e  mov     rcx, [rbx+28h]; String1
0x140017962  lea     rdx, aSystemsetting; "SystemSetting"
0x140017969  call    wcscmp_0
0x14001796e  test    eax, eax
0x140017970  jnz     short loc_14001799A
0x140017972  mov     rcx, [rbx+18h]
0x140017976  call    cs:__imp__o__wtoi
0x14001797d  nop     dword ptr [rax+rax+00h]
0x140017982  cmp     eax, 16h
0x140017985  jnb     short loc_14001799A
0x140017987  mov     r9d, [rsi+124h]
0x14001798e  mov     edx, eax
0x140017990  mov     rcx, rbx
0x140017993  call    ?TurnOff@SystemSettings@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@IPEAXH@Z; SystemSettings::TurnOff(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint,void *,int)
0x140017998  mov     edi, eax
0x14001799a  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x14001799f  neg     eax
0x1400179a1  sbb     rcx, rcx
0x1400179a4  and     rcx, 0FFFFFFFFFFFFFFD0h
0x1400179a8  add     rcx, 60h ; '`'
0x1400179ac  test    edi, edi
0x1400179ae  js      short loc_1400179D7
0x1400179b0  mov     rdx, [rbx]
0x1400179b3  lea     r11, [rcx+rsi]
0x1400179b7  mov     rcx, r11
0x1400179ba  call    ?Find@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAPEAU__POSITION@@PEBGPEAU3@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Find(ushort const *,__POSITION *)
0x1400179bf  test    rax, rax
0x1400179c2  jz      short loc_1400179CF
0x1400179c4  mov     rdx, rax
0x1400179c7  mov     rcx, r11
0x1400179ca  call    ?RemoveAt@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAt(__POSITION *)
0x1400179cf  mov     rcx, rsi; this
0x1400179d2  call    ?SaveSessionKey@StartList@@AEAAXXZ; StartList::SaveSessionKey(void)
0x1400179d7  mov     eax, edi
0x1400179d9  mov     rbx, [rsp+28h+arg_0]
0x1400179de  mov     rsi, [rsp+28h+arg_8]
0x1400179e3  add     rsp, 20h
0x1400179e7  pop     rdi
0x1400179e8  retn
```
