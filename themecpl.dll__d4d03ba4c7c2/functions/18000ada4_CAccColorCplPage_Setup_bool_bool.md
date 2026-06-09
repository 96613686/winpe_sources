# CAccColorCplPage::_Setup(bool,bool)

- ea: `0x18000ada4`
- end: `0x18000aea2`
- name: `?_Setup@CAccColorCplPage@@AEAAJ_N0@Z`
- size: `254`
- prototype: `__int64 __fastcall(CAccColorCplPage *__hidden this, bool, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180009190`

## callees

- `0x18000a120`
- `0x18000a20c`
- `0x18000a638`
- `0x18000ada4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ae5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ae5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ade3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ade3`

## pseudocode

```c
__int64 __fastcall CAccColorCplPage::_Setup(CAccColorCplPage *this, bool a2, bool a3)
{
  CAccColorCplPage *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rbx
  CAccColorCplPage *v9; // rcx
  unsigned int v10; // edi
  unsigned int v11; // ebx
  int v12; // eax
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Colors", 0, 0x20019u, &hKey) )
  {
    v7 = 0;
    v8 = 0;
    do
    {
      CAccColorCplPage::_LoadColor(
        v6,
        hKey,
        *(const unsigned __int16 **)((char *)&CAccColorCplPage::s_rgSystemColorRows + v8 * 8 + 24),
        (bool *)&qword_18006F230[v8 + 1],
        (unsigned int *)&qword_18006F230[v8] + 1);
      CAccColorCplPage::_LoadColor(
        v9,
        hKey,
        *(const unsigned __int16 **)((char *)&CAccColorCplPage::s_rgSystemColorRows + v8 * 8 + 48),
        (bool *)&qword_18006F230[v8 + 4],
        (unsigned int *)&qword_18006F230[v8 + 3] + 1);
      ++v7;
      v8 += 9;
    }
    while ( v7 != 8 );
    RegCloseKey(hKey);
  }
  v10 = 0;
  v11 = 0;
  do
  {
    if ( v11 >= 8 )
      break;
    v12 = CAccColorCplPage::_InitializeSystemColorRow(this, v11++, a2, a3);
    v10 = v12;
  }
  while ( v12 >= 0 );
  CAccColorCplPage::_ColorizeBackgrounds(this);
  return v10;
}

```

## disassembly

```asm
0x18000ada4  mov     r11, rsp
0x18000ada7  push    rbx
0x18000ada8  push    rbp
0x18000ada9  push    rsi
0x18000adaa  push    rdi
0x18000adab  push    r14
0x18000adad  push    r15
0x18000adaf  sub     rsp, 38h
0x18000adb3  mov     bpl, r8b
0x18000adb6  mov     qword ptr [r11+20h], 0
0x18000adbe  mov     r14b, dl
0x18000adc1  lea     rax, [r11+20h]
0x18000adc5  mov     rsi, rcx
0x18000adc8  mov     [r11-48h], rax
0x18000adcc  xor     r8d, r8d; ulOptions
0x18000adcf  lea     rdx, aControlPanelCo; "Control Panel\\Colors"
0x18000add6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000addd  mov     r9d, 20019h; samDesired
0x18000ade3  call    cs:__imp_RegOpenKeyExW
0x18000adea  nop     dword ptr [rax+rax+00h]
0x18000adef  test    eax, eax
0x18000adf1  jnz     short loc_18000AE69
0x18000adf3  xor     edi, edi
0x18000adf5  lea     r15, ?s_rgSystemColorRows@CAccColorCplPage@@0PAUCPL_SYSTEM_COLOR_ROW@@A; CPL_SYSTEM_COLOR_ROW near * CAccColorCplPage::s_rgSystemColorRows
0x18000adfc  xor     ebx, ebx
0x18000adfe  mov     r8, [rbx+r15+18h]; unsigned __int16 *
0x18000ae03  lea     rax, [r15+24h]
0x18000ae07  mov     rdx, [rsp+68h+hKey]; HKEY
0x18000ae0f  lea     r9, [r15+28h]
0x18000ae13  add     rax, rbx
0x18000ae16  add     r9, rbx; bool *
0x18000ae19  mov     [rsp+68h+var_48], rax; unsigned int *
0x18000ae1e  call    ?_LoadColor@CAccColorCplPage@@AEAAXPEAUHKEY__@@PEBGPEA_NPEAK@Z; CAccColorCplPage::_LoadColor(HKEY__ *,ushort const *,bool *,ulong *)
0x18000ae23  mov     r8, [rbx+r15+30h]; unsigned __int16 *
0x18000ae28  lea     rax, [r15+3Ch]
0x18000ae2c  mov     rdx, [rsp+68h+hKey]; HKEY
0x18000ae34  lea     r9, [r15+40h]
0x18000ae38  add     rax, rbx
0x18000ae3b  add     r9, rbx; bool *
0x18000ae3e  mov     [rsp+68h+var_48], rax; unsigned int *
0x18000ae43  call    ?_LoadColor@CAccColorCplPage@@AEAAXPEAUHKEY__@@PEBGPEA_NPEAK@Z; CAccColorCplPage::_LoadColor(HKEY__ *,ushort const *,bool *,ulong *)
0x18000ae48  inc     rdi
0x18000ae4b  add     rbx, 48h ; 'H'
0x18000ae4f  cmp     rdi, 8
0x18000ae53  jnz     short loc_18000ADFE
0x18000ae55  mov     rcx, [rsp+68h+hKey]; hKey
0x18000ae5d  call    cs:__imp_RegCloseKey
0x18000ae64  nop     dword ptr [rax+rax+00h]
0x18000ae69  xor     edi, edi
0x18000ae6b  xor     ebx, ebx
0x18000ae6d  cmp     ebx, 8
0x18000ae70  jnb     short loc_18000AE8A
0x18000ae72  mov     r9b, bpl; bool
0x18000ae75  mov     r8b, r14b; bool
0x18000ae78  mov     edx, ebx; unsigned int
0x18000ae7a  mov     rcx, rsi; this
0x18000ae7d  call    ?_InitializeSystemColorRow@CAccColorCplPage@@AEAAJI_N0@Z; CAccColorCplPage::_InitializeSystemColorRow(uint,bool,bool)
0x18000ae82  inc     ebx
0x18000ae84  mov     edi, eax
0x18000ae86  test    eax, eax
0x18000ae88  jns     short loc_18000AE6D
0x18000ae8a  mov     rcx, rsi; this
0x18000ae8d  call    ?_ColorizeBackgrounds@CAccColorCplPage@@AEAAXXZ; CAccColorCplPage::_ColorizeBackgrounds(void)
0x18000ae92  mov     eax, edi
0x18000ae94  add     rsp, 38h
0x18000ae98  pop     r15
0x18000ae9a  pop     r14
0x18000ae9c  pop     rdi
0x18000ae9d  pop     rsi
0x18000ae9e  pop     rbp
0x18000ae9f  pop     rbx
0x18000aea0  retn
```
