# TetheringSettingsSaveSettingPrivate(_TETHERING_SETTING &,ushort const *,void *,ulong)

- ea: `0x18002c0fc`
- end: `0x18002c2d2`
- name: `?TetheringSettingsSaveSettingPrivate@@YAJAEAU_TETHERING_SETTING@@PEBGPEAXK@Z`
- size: `470`
- prototype: `__int64 __fastcall(struct _TETHERING_SETTING *, const unsigned __int16 *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18002c034`

## callees

- `0x18000304c`
- `0x180003058`
- `0x18000bf74`
- `0x18000ea08`
- `0x180029ec8`
- `0x18002c0fc`
- `0x18002c2d8`
- `0x1800315f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c2bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c2bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c24a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c24a`

## pseudocode

```c
__int64 __fastcall TetheringSettingsSaveSettingPrivate(
        struct _TETHERING_SETTING *a1,
        unsigned __int16 *a2,
        void *a3,
        unsigned int a4)
{
  size_t cbData; // rbp
  int v7; // eax
  unsigned int v8; // edi
  TetheringServiceTelemetry *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  char *v12; // rcx
  void *v13; // rcx
  char *v14; // rax
  LSTATUS v15; // eax
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = (HKEY)a2;
  cbData = a4;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, *(_QWORD *)a1);
  }
  hKey = 0;
  v7 = OpenSettingRegKey(0, 0, &hKey);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_37;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_34;
    v10 = 78;
    goto LABEL_8;
  }
  v7 = ValidateSetting(a1, a3, cbData);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_37;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_34;
    v10 = 79;
LABEL_8:
    v11 = (unsigned int)v7;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v11);
LABEL_33:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_34;
  }
  if ( *((_DWORD *)a1 + 3) && g_fTetheringSettingsLoaded )
  {
    if ( ((*((_DWORD *)a1 + 2) - 1) & 0xFFFFFFFD) != 0 )
    {
      v12 = (char *)a1 + 16;
    }
    else
    {
      v13 = (void *)*((_QWORD *)a1 + 2);
      if ( v13 )
        free(v13);
      v14 = (char *)o_malloc_0(cbData);
      *((_QWORD *)a1 + 2) = v14;
      if ( !v14 )
      {
        v8 = -2147024882;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
          goto LABEL_37;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_34;
        v10 = 80;
        goto LABEL_31;
      }
      v12 = v14;
    }
    memcpy_0(v12, a3, cbData);
  }
  v15 = RegSetValueExW(hKey, *(LPCWSTR *)a1, 0, *((_DWORD *)a1 + 2), (const BYTE *)a3, cbData);
  v8 = v15;
  if ( v15 > 0 )
    v8 = (unsigned __int16)v15 | 0x80070000;
  if ( (v8 & 0x80000000) == 0 )
    goto LABEL_33;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_37;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 81;
LABEL_31:
    v11 = v8;
    goto LABEL_32;
  }
LABEL_34:
  if ( v9 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v9 + 2), 82, &WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids, v8);
LABEL_37:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x18002c0fc  mov     [rsp+hKey], rdx
0x18002c101  push    rbp
0x18002c102  push    rsi
0x18002c103  push    rdi
0x18002c104  push    r12
0x18002c106  push    r13
0x18002c108  push    r14
0x18002c10a  sub     rsp, 38h
0x18002c10e  mov     ebp, r9d
0x18002c111  mov     r14, r8
0x18002c114  mov     rsi, rcx
0x18002c117  lea     r12, WPP_GLOBAL_Control
0x18002c11e  lea     r13, WPP_526e2569a9333f836f2472508a4e2fa1_Traceguids
0x18002c125  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c12c  cmp     rcx, r12
0x18002c12f  jz      short loc_18002C14B
0x18002c131  test    byte ptr [rcx+1Ch], 8
0x18002c135  jz      short loc_18002C14B
0x18002c137  mov     edx, 4Dh ; 'M'
0x18002c13c  mov     r9, [rsi]
0x18002c13f  mov     r8, r13
0x18002c142  mov     rcx, [rcx+10h]
0x18002c146  call    WPP_SF_S
0x18002c14b  mov     [rsp+68h+hKey], 0
0x18002c154  lea     r8, [rsp+68h+hKey]; HKEY *
0x18002c159  xor     edx, edx; bool
0x18002c15b  xor     ecx, ecx; unsigned __int16 *
0x18002c15d  call    ?OpenSettingRegKey@@YAJPEBG_NPEAPEAUHKEY__@@@Z; OpenSettingRegKey(ushort const *,bool,HKEY__ * *)
0x18002c162  mov     edi, eax
0x18002c164  test    eax, eax
0x18002c166  jns     short loc_18002C18F
0x18002c168  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c16f  cmp     rcx, r12
0x18002c172  jz      loc_18002C2AF
0x18002c178  test    byte ptr [rcx+1Ch], 1
0x18002c17c  jz      loc_18002C290
0x18002c182  mov     edx, 4Eh ; 'N'
0x18002c187  mov     r9d, eax
0x18002c18a  jmp     loc_18002C27D
0x18002c18f  mov     r8d, ebp; unsigned int
0x18002c192  mov     rdx, r14; void *
0x18002c195  mov     rcx, rsi; struct _TETHERING_SETTING *
0x18002c198  call    ?ValidateSetting@@YAJAEBU_TETHERING_SETTING@@PEAXK@Z; ValidateSetting(_TETHERING_SETTING const &,void *,ulong)
0x18002c19d  mov     edi, eax
0x18002c19f  test    eax, eax
0x18002c1a1  jns     short loc_18002C1C4
0x18002c1a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c1aa  cmp     rcx, r12
0x18002c1ad  jz      loc_18002C2AF
0x18002c1b3  test    byte ptr [rcx+1Ch], 1
0x18002c1b7  jz      loc_18002C290
0x18002c1bd  mov     edx, 4Fh ; 'O'
0x18002c1c2  jmp     short loc_18002C187
0x18002c1c4  cmp     dword ptr [rsi+0Ch], 0
0x18002c1c8  jz      short loc_18002C232
0x18002c1ca  cmp     cs:?g_fTetheringSettingsLoaded@@3HA, 0; int g_fTetheringSettingsLoaded
0x18002c1d1  jz      short loc_18002C232
0x18002c1d3  mov     eax, [rsi+8]
0x18002c1d6  dec     eax
0x18002c1d8  test    eax, 0FFFFFFFDh
0x18002c1dd  jz      short loc_18002C1E5
0x18002c1df  lea     rcx, [rsi+10h]
0x18002c1e3  jmp     short loc_18002C227
0x18002c1e5  mov     rcx, [rsi+10h]; Block
0x18002c1e9  test    rcx, rcx
0x18002c1ec  jz      short loc_18002C1F3
0x18002c1ee  call    free
0x18002c1f3  mov     rcx, rbp; Size
0x18002c1f6  call    _o_malloc_0
0x18002c1fb  mov     [rsi+10h], rax
0x18002c1ff  test    rax, rax
0x18002c202  jnz     short loc_18002C224
0x18002c204  mov     edi, 8007000Eh
0x18002c209  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c210  cmp     rcx, r12
0x18002c213  jz      loc_18002C2AF
0x18002c219  test    byte ptr [rcx+1Ch], 1
0x18002c21d  jz      short loc_18002C290
0x18002c21f  lea     edx, [rax+50h]
0x18002c222  jmp     short loc_18002C27A
0x18002c224  mov     rcx, rax; void *
0x18002c227  mov     r8, rbp; Size
0x18002c22a  mov     rdx, r14; Src
0x18002c22d  call    memcpy_0
0x18002c232  mov     [rsp+68h+cbData], ebp; cbData
0x18002c236  mov     [rsp+68h+lpData], r14; lpData
0x18002c23b  mov     r9d, [rsi+8]; dwType
0x18002c23f  xor     r8d, r8d; Reserved
0x18002c242  mov     rdx, [rsi]; lpValueName
0x18002c245  mov     rcx, [rsp+68h+hKey]; hKey
0x18002c24a  call    cs:__imp_RegSetValueExW
0x18002c250  mov     edi, eax
0x18002c252  test    eax, eax
0x18002c254  jle     short loc_18002C25F
0x18002c256  movzx   edi, ax
0x18002c259  or      edi, 80070000h
0x18002c25f  test    edi, edi
0x18002c261  jns     short loc_18002C289
0x18002c263  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c26a  cmp     rcx, r12
0x18002c26d  jz      short loc_18002C2AF
0x18002c26f  test    byte ptr [rcx+1Ch], 1
0x18002c273  jz      short loc_18002C290
0x18002c275  mov     edx, 51h ; 'Q'
0x18002c27a  mov     r9d, edi
0x18002c27d  mov     r8, r13
0x18002c280  mov     rcx, [rcx+10h]
0x18002c284  call    WPP_SF_d
0x18002c289  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c290  cmp     rcx, r12
0x18002c293  jz      short loc_18002C2AF
0x18002c295  test    byte ptr [rcx+1Ch], 8
0x18002c299  jz      short loc_18002C2AF
0x18002c29b  mov     edx, 52h ; 'R'
0x18002c2a0  mov     r9d, edi
0x18002c2a3  mov     r8, r13
0x18002c2a6  mov     rcx, [rcx+10h]
0x18002c2aa  call    WPP_SF_d
0x18002c2af  cmp     [rsp+68h+hKey], 0
0x18002c2b5  jz      short loc_18002C2C2
0x18002c2b7  mov     rcx, [rsp+68h+hKey]; hKey
0x18002c2bc  call    cs:__imp_RegCloseKey
0x18002c2c2  mov     eax, edi
0x18002c2c4  add     rsp, 38h
0x18002c2c8  pop     r14
0x18002c2ca  pop     r13
0x18002c2cc  pop     r12
0x18002c2ce  pop     rdi
0x18002c2cf  pop     rsi
0x18002c2d0  pop     rbp
0x18002c2d1  retn
```
