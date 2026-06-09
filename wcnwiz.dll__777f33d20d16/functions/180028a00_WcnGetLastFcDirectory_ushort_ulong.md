# WcnGetLastFcDirectory(ushort *,ulong)

- ea: `0x180028a00`
- end: `0x180028b29`
- name: `?WcnGetLastFcDirectory@@YAJPEAGK@Z`
- size: `297`
- prototype: `__int64 __fastcall(wchar_t *Buffer, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028c68`
- `0x18002bfb8`

## callees

- `0x180002a58`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x180028a00`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028ad6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028ad6`
- `SHELL32!SHGetKnownFolderPath` at `0x180028a68`
- `SHELL32!SHGetKnownFolderPath` at `0x180028a68`

## string_xrefs

- `0x180028aa6`: `%s\Microsoft\LastFlashConfig.wfc`

## pseudocode

```c
__int64 __fastcall WcnGetLastFcDirectory(wchar_t *Buffer)
{
  const char *Indent; // rax
  __int64 v3; // r10
  HRESULT v4; // eax
  int v5; // ebx
  _BYTE *v6; // r10
  unsigned int v7; // eax
  __int64 v8; // r10
  PWSTR ppszPath; // [rsp+50h] [rbp+18h] BYREF

  ppszPath = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 24, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, Indent);
  }
  v4 = SHGetKnownFolderPath(&FOLDERID_RoamingAppData, 0, 0, &ppszPath);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( swprintf_s(Buffer, 0x104u, L"%s\\Microsoft\\LastFlashConfig.wfc", ppszPath) == -1 )
      v5 = -2147418113;
    goto LABEL_10;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, (unsigned int)v4);
LABEL_10:
    v6 = WPP_GLOBAL_Control;
  }
  if ( ppszPath )
  {
    CoTaskMemFree(ppszPath);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (_BYTE *)&WPP_GLOBAL_Control && (v5 < 0 || v6[25] >= 6u) )
  {
    v7 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v8 + 16), 26, (unsigned int)WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids, v7, v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180028a00  mov     [rsp+arg_0], rbx
0x180028a05  mov     [rsp+arg_8], rsi
0x180028a0a  push    rdi
0x180028a0b  sub     rsp, 30h
0x180028a0f  mov     rdi, rcx
0x180028a12  mov     [rsp+38h+ppszPath], 0
0x180028a1b  mov     r10, cs:WPP_GLOBAL_Control
0x180028a22  lea     rsi, WPP_GLOBAL_Control
0x180028a29  cmp     r10, rsi
0x180028a2c  jz      short loc_180028A57
0x180028a2e  cmp     byte ptr [r10+19h], 6
0x180028a33  jb      short loc_180028A57
0x180028a35  mov     ecx, 1; int
0x180028a3a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180028a3f  mov     rcx, [r10+10h]
0x180028a43  lea     r8, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x180028a4a  mov     edx, 18h
0x180028a4f  mov     r9, rax
0x180028a52  call    WPP_SF_s
0x180028a57  lea     r9, [rsp+38h+ppszPath]; ppszPath
0x180028a5c  xor     r8d, r8d; hToken
0x180028a5f  xor     edx, edx; dwFlags
0x180028a61  lea     rcx, FOLDERID_RoamingAppData; rfid
0x180028a68  call    cs:__imp_SHGetKnownFolderPath
0x180028a6e  mov     ebx, eax
0x180028a70  test    eax, eax
0x180028a72  jns     short loc_180028AA1
0x180028a74  mov     r10, cs:WPP_GLOBAL_Control
0x180028a7b  cmp     r10, rsi
0x180028a7e  jz      short loc_180028ACC
0x180028a80  cmp     byte ptr [r10+19h], 2
0x180028a85  jb      short loc_180028ACC
0x180028a87  mov     rcx, [r10+10h]
0x180028a8b  lea     r8, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x180028a92  mov     edx, 19h
0x180028a97  mov     r9d, eax
0x180028a9a  call    WPP_SF_d
0x180028a9f  jmp     short loc_180028AC5
0x180028aa1  mov     r9, [rsp+38h+ppszPath]
0x180028aa6  lea     r8, aSMicrosoftLast; "%s\\Microsoft\\LastFlashConfig.wfc"
0x180028aad  mov     edx, 104h; BufferCount
0x180028ab2  mov     rcx, rdi; Buffer
0x180028ab5  call    swprintf_s
0x180028aba  cmp     eax, 0FFFFFFFFh
0x180028abd  mov     ecx, 8000FFFFh
0x180028ac2  cmovz   ebx, ecx
0x180028ac5  mov     r10, cs:WPP_GLOBAL_Control
0x180028acc  mov     rcx, [rsp+38h+ppszPath]; pv
0x180028ad1  test    rcx, rcx
0x180028ad4  jz      short loc_180028AE3
0x180028ad6  call    cs:__imp_CoTaskMemFree
0x180028adc  mov     r10, cs:WPP_GLOBAL_Control
0x180028ae3  cmp     r10, rsi
0x180028ae6  jz      short loc_180028B17
0x180028ae8  test    ebx, ebx
0x180028aea  js      short loc_180028AF3
0x180028aec  cmp     byte ptr [r10+19h], 6
0x180028af1  jb      short loc_180028B17
0x180028af3  or      ecx, 0FFFFFFFFh; int
0x180028af6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180028afb  mov     rcx, [r10+10h]
0x180028aff  lea     r8, WPP_d86a235b51753f579bf51b43ee4d8f7d_Traceguids
0x180028b06  mov     edx, 1Ah
0x180028b0b  mov     [rsp+38h+var_18], ebx
0x180028b0f  mov     r9, rax
0x180028b12  call    WPP_SF_sd
0x180028b17  mov     rsi, [rsp+38h+arg_8]
0x180028b1c  mov     eax, ebx
0x180028b1e  mov     rbx, [rsp+38h+arg_0]
0x180028b23  add     rsp, 30h
0x180028b27  pop     rdi
0x180028b28  retn
```
