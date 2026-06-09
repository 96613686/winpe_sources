# Radio::CRadioSwitchManager::_UpdateIfSliderSwitchChanged(bool)

- ea: `0x18002b2f4`
- end: `0x18002b4e2`
- name: `?_UpdateIfSliderSwitchChanged@CRadioSwitchManager@Radio@@AEAAX_N@Z`
- size: `494`
- prototype: `void __fastcall(Radio::CRadioSwitchManager *this, unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1800142b0`
- `0x18002aa14`

## callees

- `0x18002b2f4`
- `0x18002b4e8`
- `0x18002b5bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b472`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002b472`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b34b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b34b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b4a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b4a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b448`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b448`
- `Rmapi!__imp_?SystemRadioChanged@@YAXW4RADIO_SWITCH_CHANGE@@@Z` at `0x18002b414`
- `Rmapi!__imp_?SystemRadioChanged@@YAXW4RADIO_SWITCH_CHANGE@@@Z` at `0x18002b414`

## pseudocode

```c
void __fastcall Radio::CRadioSwitchManager::_UpdateIfSliderSwitchChanged(
        Radio::CRadioSwitchManager *this,
        unsigned __int8 a2)
{
  unsigned int v2; // ebx
  int v3; // r8d
  char v4; // si
  _QWORD *v5; // rcx
  const char *v6; // r9
  const char *v7; // rax
  unsigned int Data; // [rsp+60h] [rbp+8h] BYREF
  int v9; // [rsp+64h] [rbp+Ch]
  DWORD v10; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  v9 = HIDWORD(this);
  v2 = a2;
  Data = 0;
  v10 = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\RadioManagement\\SystemRadioState",
         L"ABSliderPosition",
         0x18u,
         0,
         &Data,
         &v10) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18);
    }
    if ( !(_BYTE)v2 )
      goto LABEL_20;
  }
  else
  {
    v4 = Data != 0;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v6 = "on";
      v7 = "on";
      if ( !(_BYTE)v2 )
        v7 = "off";
      if ( !Data )
        v6 = "off";
      WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)"off", v3, (_DWORD)v6, (__int64)v7);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v4 != (_BYTE)v2 )
    {
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 && *((_BYTE *)v5 + 25) >= 4u )
        WPP_SF_(v5[2], 17);
LABEL_20:
      SystemRadioChanged(v2);
      Data = v2;
      hKey = 0;
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\RadioManagement\\SystemRadioState",
             0,
             2u,
             &hKey) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20);
        }
      }
      else
      {
        if ( RegSetValueExW(hKey, L"ABSliderPosition", 0, 4u, (const BYTE *)&Data, 4u)
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19);
        }
        RegCloseKey(hKey);
      }
    }
  }
}

```

## disassembly

```asm
0x18002b2f4  mov     r11, rsp
0x18002b2f7  mov     [r11+10h], rbx
0x18002b2fb  mov     [r11+8], rcx
0x18002b2ff  push    rbp
0x18002b300  push    rsi
0x18002b301  push    rdi
0x18002b302  sub     rsp, 40h
0x18002b306  lea     rax, [r11+18h]
0x18002b30a  movzx   ebx, dl
0x18002b30d  mov     [r11-28h], rax
0x18002b311  lea     r8, Value; "ABSliderPosition"
0x18002b318  mov     ebp, 4
0x18002b31d  mov     [rsp+58h+Data], 0
0x18002b325  lea     rax, [r11+8]
0x18002b329  mov     [rsp+58h+arg_10], ebp
0x18002b32d  mov     [r11-30h], rax
0x18002b331  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Rad"...
0x18002b338  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002b33f  mov     qword ptr [r11-38h], 0
0x18002b347  lea     r9d, [rbp+14h]; dwFlags
0x18002b34b  call    cs:__imp_RegGetValueW
0x18002b351  test    eax, eax
0x18002b353  jnz     loc_18002B3DD
0x18002b359  cmp     [rsp+58h+Data], eax
0x18002b35d  setnz   sil
0x18002b361  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b368  lea     rdi, WPP_GLOBAL_Control
0x18002b36f  cmp     rcx, rdi
0x18002b372  jz      short loc_18002B3B3
0x18002b374  test    [rcx+1Ch], bpl
0x18002b378  jz      short loc_18002B3B3
0x18002b37a  cmp     [rcx+19h], bpl
0x18002b37e  jb      short loc_18002B3B3
0x18002b380  mov     rcx, [rcx+10h]
0x18002b384  lea     rdx, aOff; "off"
0x18002b38b  test    bl, bl
0x18002b38d  lea     r9, aOn; "on"
0x18002b394  mov     rax, r9
0x18002b397  cmovz   rax, rdx
0x18002b39b  test    sil, sil
0x18002b39e  mov     [rsp+58h+phkResult], rax
0x18002b3a3  cmovz   r9, rdx
0x18002b3a7  call    WPP_SF_ss
0x18002b3ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3b3  cmp     sil, bl
0x18002b3b6  jz      loc_18002B4D5
0x18002b3bc  cmp     rcx, rdi
0x18002b3bf  jz      short loc_18002B412
0x18002b3c1  test    [rcx+1Ch], bpl
0x18002b3c5  jz      short loc_18002B412
0x18002b3c7  cmp     [rcx+19h], bpl
0x18002b3cb  jb      short loc_18002B412
0x18002b3cd  mov     rcx, [rcx+10h]
0x18002b3d1  mov     edx, 11h
0x18002b3d6  call    WPP_SF_
0x18002b3db  jmp     short loc_18002B412
0x18002b3dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3e4  lea     rdi, WPP_GLOBAL_Control
0x18002b3eb  cmp     rcx, rdi
0x18002b3ee  jz      short loc_18002B40A
0x18002b3f0  test    [rcx+1Ch], bpl
0x18002b3f4  jz      short loc_18002B40A
0x18002b3f6  cmp     byte ptr [rcx+19h], 2
0x18002b3fa  jb      short loc_18002B40A
0x18002b3fc  mov     rcx, [rcx+10h]
0x18002b400  mov     edx, 12h
0x18002b405  call    WPP_SF_
0x18002b40a  test    bl, bl
0x18002b40c  jnz     loc_18002B4D5
0x18002b412  mov     ecx, ebx
0x18002b414  call    cs:__imp_?SystemRadioChanged@@YAXW4RADIO_SWITCH_CHANGE@@@Z; SystemRadioChanged(RADIO_SWITCH_CHANGE)
0x18002b41a  lea     rax, [rsp+58h+hKey]
0x18002b41f  mov     [rsp+58h+Data], ebx
0x18002b423  mov     r9d, 2; samDesired
0x18002b429  mov     [rsp+58h+phkResult], rax; phkResult
0x18002b42e  xor     r8d, r8d; ulOptions
0x18002b431  mov     [rsp+58h+hKey], 0
0x18002b43a  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Rad"...
0x18002b441  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b448  call    cs:__imp_RegOpenKeyExW
0x18002b44e  test    eax, eax
0x18002b450  jnz     short loc_18002B4AF
0x18002b452  mov     rcx, [rsp+58h+hKey]; hKey
0x18002b457  lea     rax, [rsp+58h+Data]
0x18002b45c  mov     [rsp+58h+cbData], ebp; cbData
0x18002b460  lea     rdx, Value; "ABSliderPosition"
0x18002b467  mov     r9d, ebp; dwType
0x18002b46a  mov     [rsp+58h+phkResult], rax; lpData
0x18002b46f  xor     r8d, r8d; Reserved
0x18002b472  call    cs:__imp_RegSetValueExW
0x18002b478  test    eax, eax
0x18002b47a  jz      short loc_18002B4A2
0x18002b47c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b483  cmp     rcx, rdi
0x18002b486  jz      short loc_18002B4A2
0x18002b488  test    [rcx+1Ch], bpl
0x18002b48c  jz      short loc_18002B4A2
0x18002b48e  cmp     byte ptr [rcx+19h], 2
0x18002b492  jb      short loc_18002B4A2
0x18002b494  mov     rcx, [rcx+10h]
0x18002b498  mov     edx, 13h
0x18002b49d  call    WPP_SF_
0x18002b4a2  mov     rcx, [rsp+58h+hKey]; hKey
0x18002b4a7  call    cs:__imp_RegCloseKey
0x18002b4ad  jmp     short loc_18002B4D5
0x18002b4af  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4b6  cmp     rcx, rdi
0x18002b4b9  jz      short loc_18002B4D5
0x18002b4bb  test    [rcx+1Ch], bpl
0x18002b4bf  jz      short loc_18002B4D5
0x18002b4c1  cmp     byte ptr [rcx+19h], 2
0x18002b4c5  jb      short loc_18002B4D5
0x18002b4c7  mov     rcx, [rcx+10h]
0x18002b4cb  mov     edx, 14h
0x18002b4d0  call    WPP_SF_
0x18002b4d5  mov     rbx, [rsp+58h+arg_8]
0x18002b4da  add     rsp, 40h
0x18002b4de  pop     rdi
0x18002b4df  pop     rsi
0x18002b4e0  pop     rbp
0x18002b4e1  retn
```
