# CFlyout::UpdateLayout(ulong *)

- ea: `0x180011950`
- end: `0x180011b8c`
- name: `?UpdateLayout@CFlyout@@UEAAJPEAK@Z`
- size: `572`
- prototype: `__int64 __fastcall(CFlyout *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180009890`
- `0x180011950`
- `0x180011b94`
- `0x180011ff0`
- `0x1800124c8`
- `0x180028f2e`
- `0x180028f60`
- `0x18002a010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180011a91`
- `msvcrt!wcsstr` at `0x180011a91`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800119c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800119c9`
- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoW` at `0x180011a30`
- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoW` at `0x180011a30`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800119e1`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x1800119e1`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180011abc`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180011abc`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180011aa8`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180011ae2`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180011b05`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180011b27`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180011aa8`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180011ae2`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180011b05`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180011b27`

## pseudocode

```c
__int64 __fastcall CFlyout::UpdateLayout(DirectUI::Element **this, unsigned int *a2)
{
  int ElementPointers; // edi
  int v5; // edi
  unsigned int v6; // ecx
  WCHAR LCData[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Str; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v11[510]; // [rsp+52h] [rbp-AEh] BYREF
  WCHAR CalData[256]; // [rsp+250h] [rbp+150h] BYREF

  ElementPointers = CFlyout::_GetElementPointers((CFlyout *)this);
  if ( ElementPointers >= 0 )
  {
    v5 = 2;
    if ( this[45] )
    {
      memset_0(CalData, 0, sizeof(CalData));
      wcscpy(LCData, L"\x01");
      SystemTime = 0;
      GetLocalTime(&SystemTime);
      GetLocaleInfoW(0x400u, 0x20001009u, LCData, 2);
      GetCalendarInfoW(0x400u, *(CALID *)LCData, ((unsigned int)SystemTime.wDayOfWeek + 6) % 7 + 7, CalData, 256, 0);
      if ( *((_DWORD *)this + 64)
        || *((_DWORD *)this + 65)
        || (Str = 0, memset_0(v11, 0, sizeof(v11)), !(unsigned int)wrap_GetDateFormat(v6, 0x42u, 0, 0, &Str, 256))
        || !wcsstr(&Str, CalData) )
      {
        DirectUI::Element::SetLayoutPos(this[45], 3);
        DirectUI::Element::SetContentString(this[45], CalData);
      }
    }
    if ( !*((_DWORD *)this + 64) && !*((_DWORD *)this + 65) )
      v5 = -3;
    ElementPointers = DirectUI::Element::SetLayoutPos(this[35], v5);
    if ( ElementPointers >= 0 )
    {
      ElementPointers = DirectUI::Element::SetLayoutPos(this[39], *((_DWORD *)this + 65) != 0 ? 2 : -3);
      if ( ElementPointers >= 0 )
      {
        ElementPointers = DirectUI::Element::SetLayoutPos(this[38], *((_DWORD *)this + 64) == 0 ? 0xFFFFFFFD : 0);
        if ( ElementPointers >= 0 )
        {
          ElementPointers = CFlyout::_UpdateLayoutForClocks((CFlyout *)this);
          if ( ElementPointers >= 0 )
          {
            ElementPointers = CFlyout::_AddFlyoutNotifications((CFlyout *)this, a2);
            if ( ElementPointers >= 0 )
              (*(void (__fastcall **)(DirectUI::Element *))(*(_QWORD *)this[40] + 168LL))(this[40]);
          }
        }
      }
    }
  }
  return (unsigned int)ElementPointers;
}

```

## disassembly

```asm
0x180011950  mov     [rsp-8+arg_10], rbx
0x180011955  push    rbp
0x180011956  push    rsi
0x180011957  push    rdi
0x180011958  lea     rbp, [rsp-360h]
0x180011960  sub     rsp, 460h
0x180011967  mov     rax, cs:__security_cookie
0x18001196e  xor     rax, rsp
0x180011971  mov     [rbp+370h+var_20], rax
0x180011978  mov     rsi, rdx
0x18001197b  mov     rbx, rcx
0x18001197e  call    ?_GetElementPointers@CFlyout@@AEAAJXZ; CFlyout::_GetElementPointers(void)
0x180011983  mov     edi, eax
0x180011985  test    eax, eax
0x180011987  js      loc_180011B68
0x18001198d  cmp     qword ptr [rbx+168h], 0
0x180011995  mov     edi, 2
0x18001199a  jz      loc_180011AC2
0x1800119a0  xor     edx, edx; Val
0x1800119a2  lea     rcx, [rbp+370h+CalData]; void *
0x1800119a9  mov     r8d, 200h; Size
0x1800119af  call    memset_0
0x1800119b4  xorps   xmm0, xmm0
0x1800119b7  mov     dword ptr [rsp+470h+LCData], 1
0x1800119bf  lea     rcx, [rsp+470h+SystemTime]; lpSystemTime
0x1800119c4  movups  xmmword ptr [rsp+470h+SystemTime.wYear], xmm0
0x1800119c9  call    cs:__imp_GetLocalTime
0x1800119cf  mov     r9d, edi; cchData
0x1800119d2  lea     r8, [rsp+470h+LCData]; lpLCData
0x1800119d7  mov     edx, 20001009h; LCType
0x1800119dc  mov     ecx, 400h; Locale
0x1800119e1  call    cs:__imp_GetLocaleInfoW
0x1800119e7  movzx   r8d, [rsp+470h+SystemTime.wDayOfWeek]
0x1800119ed  lea     r9, [rbp+370h+CalData]; lpCalData
0x1800119f4  add     r8d, 6
0x1800119f8  mov     [rsp+470h+lpValue], 0; lpValue
0x180011a01  mov     eax, 24924925h
0x180011a06  mov     [rsp+470h+cchData], 100h; cchData
0x180011a0e  mul     r8d
0x180011a11  mov     eax, r8d
0x180011a14  mov     ecx, 400h; Locale
0x180011a19  sub     eax, edx
0x180011a1b  shr     eax, 1
0x180011a1d  add     eax, edx
0x180011a1f  mov     edx, dword ptr [rsp+470h+LCData]; Calendar
0x180011a23  shr     eax, 2
0x180011a26  imul    eax, 7
0x180011a29  sub     r8d, eax
0x180011a2c  add     r8d, 7; CalType
0x180011a30  call    cs:__imp_GetCalendarInfoW
0x180011a36  cmp     dword ptr [rbx+100h], 0
0x180011a3d  jnz     short loc_180011A9C
0x180011a3f  cmp     dword ptr [rbx+104h], 0
0x180011a46  jnz     short loc_180011A9C
0x180011a48  xor     eax, eax
0x180011a4a  lea     rcx, [rsp+470h+var_41E]; void *
0x180011a4f  xor     edx, edx; Val
0x180011a51  mov     [rsp+470h+Str], ax
0x180011a56  mov     r8d, 1FEh; Size
0x180011a5c  call    memset_0
0x180011a61  lea     rax, [rsp+470h+Str]
0x180011a66  mov     dword ptr [rsp+470h+lpValue], 100h; cchBufferMax
0x180011a6e  xor     r9d, r9d; unsigned __int16 *
0x180011a71  mov     qword ptr [rsp+470h+cchData], rax; lpBuffer
0x180011a76  xor     r8d, r8d; struct _SYSTEMTIME *
0x180011a79  lea     edx, [rdi+40h]; unsigned int
0x180011a7c  call    ?wrap_GetDateFormat@@YAHKKPEBU_SYSTEMTIME@@PEBGPEAGH@Z; wrap_GetDateFormat(ulong,ulong,_SYSTEMTIME const *,ushort const *,ushort *,int)
0x180011a81  test    eax, eax
0x180011a83  jz      short loc_180011A9C
0x180011a85  lea     rdx, [rbp+370h+CalData]; SubStr
0x180011a8c  lea     rcx, [rsp+470h+Str]; Str
0x180011a91  call    cs:__imp_wcsstr
0x180011a97  test    rax, rax
0x180011a9a  jnz     short loc_180011AC2
0x180011a9c  mov     rcx, [rbx+168h]
0x180011aa3  mov     edx, 3
0x180011aa8  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180011aae  mov     rcx, [rbx+168h]
0x180011ab5  lea     rdx, [rbp+370h+CalData]
0x180011abc  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180011ac2  cmp     dword ptr [rbx+100h], 0
0x180011ac9  jnz     short loc_180011AD9
0x180011acb  cmp     dword ptr [rbx+104h], 0
0x180011ad2  jnz     short loc_180011AD9
0x180011ad4  mov     edi, 0FFFFFFFDh
0x180011ad9  mov     rcx, [rbx+118h]
0x180011ae0  mov     edx, edi
0x180011ae2  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180011ae8  mov     edi, eax
0x180011aea  test    eax, eax
0x180011aec  js      short loc_180011B68
0x180011aee  mov     eax, [rbx+104h]
0x180011af4  mov     rcx, [rbx+138h]
0x180011afb  neg     eax
0x180011afd  sbb     edx, edx
0x180011aff  and     edx, 5
0x180011b02  add     edx, 0FFFFFFFDh
0x180011b05  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180011b0b  mov     edi, eax
0x180011b0d  test    eax, eax
0x180011b0f  js      short loc_180011B68
0x180011b11  mov     eax, [rbx+100h]
0x180011b17  mov     rcx, [rbx+130h]
0x180011b1e  neg     eax
0x180011b20  sbb     edx, edx
0x180011b22  not     edx
0x180011b24  and     edx, 0FFFFFFFDh
0x180011b27  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180011b2d  mov     edi, eax
0x180011b2f  test    eax, eax
0x180011b31  js      short loc_180011B68
0x180011b33  mov     rcx, rbx; this
0x180011b36  call    ?_UpdateLayoutForClocks@CFlyout@@AEAAJXZ; CFlyout::_UpdateLayoutForClocks(void)
0x180011b3b  mov     edi, eax
0x180011b3d  test    eax, eax
0x180011b3f  js      short loc_180011B68
0x180011b41  mov     rdx, rsi; unsigned int *
0x180011b44  mov     rcx, rbx; this
0x180011b47  call    ?_AddFlyoutNotifications@CFlyout@@AEAAJPEAK@Z; CFlyout::_AddFlyoutNotifications(ulong *)
0x180011b4c  mov     edi, eax
0x180011b4e  test    eax, eax
0x180011b50  js      short loc_180011B68
0x180011b52  mov     rcx, [rbx+140h]
0x180011b59  mov     rax, [rcx]
0x180011b5c  mov     rax, [rax+0A8h]
0x180011b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b68  mov     eax, edi
0x180011b6a  mov     rcx, [rbp+370h+var_20]
0x180011b71  xor     rcx, rsp; StackCookie
0x180011b74  call    __security_check_cookie
0x180011b79  mov     rbx, [rsp+470h+arg_10]
0x180011b81  add     rsp, 460h
0x180011b88  pop     rdi
0x180011b89  pop     rsi
0x180011b8a  pop     rbp
0x180011b8b  retn
```
