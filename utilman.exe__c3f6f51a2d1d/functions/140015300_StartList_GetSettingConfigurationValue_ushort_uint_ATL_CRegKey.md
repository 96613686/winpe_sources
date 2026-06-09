# StartList::GetSettingConfigurationValue(ushort *,uint,ATL::CRegKey &)

- ea: `0x140015300`
- end: `0x1400153dc`
- name: `?GetSettingConfigurationValue@StartList@@AEAAXPEAGIAEAVCRegKey@ATL@@@Z`
- size: `220`
- prototype: `void(StartList *__hidden this, unsigned __int16 *, unsigned int, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015fb8`

## callees

- `0x14000e550`
- `0x14000ea8c`
- `0x14000ecdc`
- `0x140015300`
- `0x14001827c`

## string_xrefs

- `0x140015390`: `SettingConfiguration`
- `0x14001532d`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`
- `0x140015326`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\OOBE`

## pseudocode

```c
void __fastcall StartList::GetSettingConfigurationValue(
        StartList *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct ATL::CRegKey *a4)
{
  int v6; // eax
  const WCHAR *v7; // r8
  unsigned int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // [rsp+40h] [rbp+18h] BYREF

  v12 = a3;
  *a2 = 0;
  v6 = IsInteractiveUser();
  v7 = StartList::_accessibilityKeyString;
  if ( !v6 )
    v7 = StartList::_oobeAccessibilityKeyString;
  v8 = ATL::CRegKey::Open(a4, (HKEY)(-(__int64)(v6 != 0) - 2147483646), v7, 0x2001Fu);
  if ( v8 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v9, v8);
  v12 = 1024;
  v10 = ATL::CRegKey::QueryStringValue(a4, StartList::_settingConfiguration, a2, &v12);
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v11, v10);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x140015300  mov     [rsp+arg_0], rbx
0x140015305  mov     [rsp+arg_8], rsi
0x14001530a  mov     [rsp+arg_10], r8d
0x14001530f  push    rdi
0x140015310  sub     rsp, 20h
0x140015314  xor     eax, eax
0x140015316  mov     rdi, r9
0x140015319  mov     [rdx], ax
0x14001531c  mov     rbx, rdx
0x14001531f  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x140015324  test    eax, eax
0x140015326  lea     rcx, ?_oobeAccessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001532d  lea     r8, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140015334  mov     r9d, 2001Fh; unsigned int
0x14001533a  cmovz   r8, rcx; lpSubKey
0x14001533e  neg     eax
0x140015340  mov     rcx, rdi; this
0x140015343  sbb     rdx, rdx
0x140015346  add     rdx, 0FFFFFFFF80000002h; hKey
0x14001534d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140015352  lea     rsi, WPP_GLOBAL_Control
0x140015359  test    eax, eax
0x14001535b  jz      short loc_140015380
0x14001535d  mov     rcx, cs:WPP_GLOBAL_Control
0x140015364  cmp     rcx, rsi
0x140015367  jz      short loc_140015380
0x140015369  test    byte ptr [rcx+1Ch], 8
0x14001536d  jz      short loc_140015380
0x14001536f  mov     rcx, [rcx+10h]
0x140015373  mov     edx, 22h ; '"'
0x140015378  mov     r9d, eax
0x14001537b  call    WPP_SF_d
0x140015380  lea     r9, [rsp+28h+arg_10]; unsigned int *
0x140015385  mov     [rsp+28h+arg_10], 400h
0x14001538d  mov     r8, rbx; unsigned __int16 *
0x140015390  lea     rdx, ?_settingConfiguration@StartList@@0PAGA; "SettingConfiguration"
0x140015397  mov     rcx, rdi; this
0x14001539a  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14001539f  test    eax, eax
0x1400153a1  jz      short loc_1400153CB
0x1400153a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400153aa  cmp     rcx, rsi
0x1400153ad  jz      short loc_1400153C6
0x1400153af  test    byte ptr [rcx+1Ch], 8
0x1400153b3  jz      short loc_1400153C6
0x1400153b5  mov     rcx, [rcx+10h]
0x1400153b9  mov     edx, 23h ; '#'
0x1400153be  mov     r9d, eax
0x1400153c1  call    WPP_SF_d
0x1400153c6  xor     eax, eax
0x1400153c8  mov     [rbx], ax
0x1400153cb  mov     rbx, [rsp+28h+arg_0]
0x1400153d0  mov     rsi, [rsp+28h+arg_8]
0x1400153d5  add     rsp, 20h
0x1400153d9  pop     rdi
0x1400153da  retn
```
