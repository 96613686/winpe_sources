# CCapsLockWarningBehavior::_UpdateWarning(DirectUI::Element *)

- ea: `0x180054258`
- end: `0x1800543a1`
- name: `?_UpdateWarning@CCapsLockWarningBehavior@@AEAAXPEAVElement@DirectUI@@@Z`
- size: `329`
- prototype: `void __fastcall(CCapsLockWarningBehavior *__hidden this, struct DirectUI::Element *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800541f0`
- `0x180054240`

## callees

- `0x180053fa8`
- `0x180054014`
- `0x180054258`
- `0x180063bc8`
- `0x18007510c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054390`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054390`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054356`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054356`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18005433a`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x18005433a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18005437d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18005437d`
- `DUI70!StrToID` at `0x1800542bd`
- `DUI70!StrToID` at `0x1800542f4`
- `DUI70!StrToID` at `0x180054320`
- `DUI70!StrToID` at `0x1800542bd`
- `DUI70!StrToID` at `0x1800542f4`
- `DUI70!StrToID` at `0x180054320`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800542c9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180054300`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18005432c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800542c9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180054300`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18005432c`
- `USER32!GetKeyState` at `0x18005429f`
- `USER32!GetKeyState` at `0x18005429f`

## pseudocode

```c
void __fastcall CCapsLockWarningBehavior::_UpdateWarning(
        CCapsLockWarningBehavior *this,
        struct DirectUI::Element *a2,
        __int64 a3)
{
  DirectUI::Element *v5; // rbx
  unsigned __int16 v6; // ax
  struct DirectUI::Element *Descendent; // rax
  struct DirectUI::Element *v8; // rdx
  DirectUI::Element *v9; // rbx
  unsigned __int16 v10; // ax
  DirectUI::Element *v11; // rbx
  unsigned __int16 v12; // ax
  DirectUI::Element *v13; // rax
  const WCHAR *ContentString; // rax
  struct DirectUI::Element *v15; // rdx
  DirectUI::Value *v16; // rcx
  void *bIgnoreCase; // [rsp+20h] [rbp-38h]
  LPCWCH lpString2[5]; // [rsp+30h] [rbp-28h] BYREF
  struct DirectUI::Value *v19; // [rsp+70h] [rbp+18h] BYREF

  lpString2[0] = 0;
  if ( (int)TResourceStringAllocCopyEx<unsigned short *>(
              g_hinst,
              3312,
              a3,
              (__int64 (__fastcall *)(_QWORD, size_t, char **))&ResourceStringAllocCopyExCoAlloc,
              bIgnoreCase,
              (char *)lpString2) >= 0 )
  {
    if ( (GetKeyState(20) & 1) != 0 && (*((_BYTE *)a2 + 148) & 1) != 0 )
    {
      v5 = (DirectUI::Element *)*((_QWORD *)this + 3);
      v6 = StrToID(L"idStatusErrorText");
      Descendent = DirectUI::Element::FindDescendent(v5, v6);
      SetElementContentStringAndAccName(Descendent, lpString2[0]);
      DisplayStatusHelper::DisplayError(v5, v8);
    }
    else
    {
      v9 = (DirectUI::Element *)*((_QWORD *)this + 3);
      v10 = StrToID(L"idStatusError");
      if ( *((_DWORD *)DirectUI::Element::FindDescendent(v9, v10) + 30) != -3 )
      {
        v11 = (DirectUI::Element *)*((_QWORD *)this + 3);
        v19 = 0;
        v12 = StrToID(L"idStatusErrorText");
        v13 = DirectUI::Element::FindDescendent(v11, v12);
        ContentString = DirectUI::Element::GetContentString(v13, &v19);
        if ( CompareStringOrdinal(ContentString, -1, lpString2[0], -1, 1) == 2 )
          DisplayStatusHelper::ClearStatus(*((DisplayStatusHelper **)this + 3), v15);
        v16 = v19;
        if ( v19 )
        {
          v19 = 0;
          DirectUI::Value::Release(v16);
        }
      }
    }
  }
  if ( lpString2[0] )
    CoTaskMemFree((LPVOID)lpString2[0]);
}

```

## disassembly

```asm
0x180054258  mov     r11, rsp
0x18005425b  mov     [r11+8], rbx
0x18005425f  push    rsi
0x180054260  sub     rsp, 50h
0x180054264  mov     rbx, rdx
0x180054267  mov     qword ptr [r11-28h], 0
0x18005426f  mov     rsi, rcx
0x180054272  lea     rax, [r11-28h]
0x180054276  mov     rcx, cs:g_hinst; int
0x18005427d  lea     r9, _ResourceStringAllocCopyExCoAlloc; int
0x180054284  mov     edx, 0CF0h; int
0x180054289  mov     [r11-30h], rax
0x18005428d  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x180054292  test    eax, eax
0x180054294  js      loc_180054383
0x18005429a  mov     ecx, 14h; nVirtKey
0x18005429f  call    cs:__imp_GetKeyState
0x1800542a5  test    al, 1
0x1800542a7  jz      short loc_1800542E9
0x1800542a9  test    byte ptr [rbx+94h], 1
0x1800542b0  jz      short loc_1800542E9
0x1800542b2  mov     rbx, [rsi+18h]
0x1800542b6  lea     rcx, aIdstatuserrort; "idStatusErrorText"
0x1800542bd  call    cs:__imp_StrToID
0x1800542c3  movzx   edx, ax
0x1800542c6  mov     rcx, rbx
0x1800542c9  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800542cf  mov     rdx, [rsp+58h+lpString2]; unsigned __int16 *
0x1800542d4  mov     rcx, rax; struct DirectUI::Element *
0x1800542d7  call    ?SetElementContentStringAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; SetElementContentStringAndAccName(DirectUI::Element *,ushort const *)
0x1800542dc  mov     rcx, rbx; this
0x1800542df  call    ?DisplayError@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@@Z; DisplayStatusHelper::DisplayError(DirectUI::Element *)
0x1800542e4  jmp     loc_180054383
0x1800542e9  mov     rbx, [rsi+18h]
0x1800542ed  lea     rcx, aIdstatuserror; "idStatusError"
0x1800542f4  call    cs:__imp_StrToID
0x1800542fa  movzx   edx, ax
0x1800542fd  mov     rcx, rbx
0x180054300  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180054306  cmp     dword ptr [rax+78h], 0FFFFFFFDh
0x18005430a  jz      short loc_180054383
0x18005430c  mov     rbx, [rsi+18h]
0x180054310  lea     rcx, aIdstatuserrort; "idStatusErrorText"
0x180054317  mov     [rsp+58h+arg_10], 0
0x180054320  call    cs:__imp_StrToID
0x180054326  movzx   edx, ax
0x180054329  mov     rcx, rbx
0x18005432c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180054332  mov     rcx, rax
0x180054335  lea     rdx, [rsp+58h+arg_10]
0x18005433a  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x180054340  mov     r8, [rsp+58h+lpString2]; lpString2
0x180054345  or      edx, 0FFFFFFFFh; cchCount1
0x180054348  mov     r9d, edx; cchCount2
0x18005434b  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180054353  mov     rcx, rax; lpString1
0x180054356  call    cs:__imp_CompareStringOrdinal
0x18005435c  cmp     eax, 2
0x18005435f  jnz     short loc_18005436A
0x180054361  mov     rcx, [rsi+18h]; this
0x180054365  call    ?ClearStatus@DisplayStatusHelper@@YAXPEAVElement@DirectUI@@@Z; DisplayStatusHelper::ClearStatus(DirectUI::Element *)
0x18005436a  mov     rcx, [rsp+58h+arg_10]
0x18005436f  test    rcx, rcx
0x180054372  jz      short loc_180054383
0x180054374  mov     [rsp+58h+arg_10], 0
0x18005437d  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180054383  cmp     [rsp+58h+lpString2], 0
0x180054389  jz      short loc_180054396
0x18005438b  mov     rcx, [rsp+58h+lpString2]; pv
0x180054390  call    cs:__imp_CoTaskMemFree
0x180054396  mov     rbx, [rsp+58h+arg_0]
0x18005439b  add     rsp, 50h
0x18005439f  pop     rsi
0x1800543a0  retn
```
