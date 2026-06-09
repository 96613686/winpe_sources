# UpdateTimeZone(HWND__ *)

- ea: `0x18000d0ac`
- end: `0x18000d1bb`
- name: `?UpdateTimeZone@@YAXPEAUHWND__@@@Z`
- size: `271`
- prototype: `void __fastcall(HWND hDlg)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000a670`
- `0x18000cf98`

## callees

- `0x18000d0ac`
- `0x18000d1c4`
- `0x18000e1e4`
- `0x18001cbc4`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `USER32!SetWindowTextW` at `0x18000d15e`
- `USER32!SetWindowTextW` at `0x18000d15e`
- `USER32!ShowWindow` at `0x18000d194`
- `USER32!ShowWindow` at `0x18000d194`
- `USER32!GetDlgItem` at `0x18000d13e`
- `USER32!GetDlgItem` at `0x18000d14e`
- `USER32!GetDlgItem` at `0x18000d189`
- `USER32!GetDlgItem` at `0x18000d13e`
- `USER32!GetDlgItem` at `0x18000d14e`
- `USER32!GetDlgItem` at `0x18000d189`

## pseudocode

```c
void __fastcall UpdateTimeZone(HWND hDlg)
{
  unsigned int v2; // r8d
  int UITimeZone; // eax
  int v4; // ebx
  HWND DlgItem; // rax
  unsigned __int16 *v6; // rdx
  BOOL v7; // ebx
  HWND v8; // rax
  int v9; // [rsp+20h] [rbp-338h]
  unsigned __int16 v10[128]; // [rsp+30h] [rbp-328h] BYREF
  unsigned __int16 v11; // [rsp+130h] [rbp-228h] BYREF
  _BYTE v12[526]; // [rsp+132h] [rbp-226h] BYREF

  UpdateTimeZoneDisplayName(hDlg);
  UITimeZone = CDateTimeOm::get_UITimeZone(g_pom, v10, v2);
  v11 = 0;
  v4 = UITimeZone;
  memset_0(v12, 0, 0x206u);
  if ( (unsigned int)FormatNextDstNotification(v10, &v11, 0x104u, *((_DWORD *)g_pom + 107) == 0, v9) )
  {
    DlgItem = GetDlgItem(hDlg, 125);
    v6 = &v11;
  }
  else
  {
    DlgItem = GetDlgItem(hDlg, 125);
    v6 = (unsigned __int16 *)&String;
  }
  SetWindowTextW(DlgItem, v6);
  v7 = v4 && *((_DWORD *)g_pom + 109);
  v8 = GetDlgItem(hDlg, 127);
  ShowWindow(v8, v7);
}

```

## disassembly

```asm
0x18000d0ac  mov     [rsp+arg_8], rbx
0x18000d0b1  push    rdi
0x18000d0b2  sub     rsp, 350h
0x18000d0b9  mov     rax, cs:__security_cookie
0x18000d0c0  xor     rax, rsp
0x18000d0c3  mov     [rsp+358h+var_18], rax
0x18000d0cb  mov     rdi, rcx
0x18000d0ce  call    ?UpdateTimeZoneDisplayName@@YAXPEAUHWND__@@@Z; UpdateTimeZoneDisplayName(HWND__ *)
0x18000d0d3  mov     rcx, cs:?g_pom@@3PEAVCDateTimeOm@@EA; this
0x18000d0da  lea     rdx, [rsp+358h+var_328]; unsigned __int16 *
0x18000d0df  call    ?get_UITimeZone@CDateTimeOm@@QEAAHPEAGK@Z; CDateTimeOm::get_UITimeZone(ushort *,ulong)
0x18000d0e4  xor     ecx, ecx
0x18000d0e6  xor     edx, edx; Val
0x18000d0e8  mov     [rsp+358h+var_228], cx
0x18000d0f0  mov     r8d, 206h; Size
0x18000d0f6  lea     rcx, [rsp+358h+var_226]; void *
0x18000d0fe  mov     ebx, eax
0x18000d100  call    memset_0
0x18000d105  mov     rcx, cs:?g_pom@@3PEAVCDateTimeOm@@EA; CDateTimeOm * g_pom
0x18000d10c  lea     rdx, [rsp+358h+var_228]; unsigned __int16 *
0x18000d114  xor     r9d, r9d
0x18000d117  mov     r8d, 104h; unsigned int
0x18000d11d  cmp     [rcx+1ACh], r9d
0x18000d124  lea     rcx, [rsp+358h+var_328]; unsigned __int16 *
0x18000d129  setz    r9b; int
0x18000d12d  call    ?FormatNextDstNotification@@YAHPEBGPEAGIHH@Z; FormatNextDstNotification(ushort const *,ushort *,uint,int,int)
0x18000d132  mov     edx, 7Dh ; '}'; nIDDlgItem
0x18000d137  mov     rcx, rdi; hDlg
0x18000d13a  test    eax, eax
0x18000d13c  jz      short loc_18000D14E
0x18000d13e  call    cs:__imp_GetDlgItem
0x18000d144  lea     rdx, [rsp+358h+var_228]
0x18000d14c  jmp     short loc_18000D15B
0x18000d14e  call    cs:__imp_GetDlgItem
0x18000d154  lea     rdx, String; lpString
0x18000d15b  mov     rcx, rax; hWnd
0x18000d15e  call    cs:__imp_SetWindowTextW
0x18000d164  test    ebx, ebx
0x18000d166  jz      short loc_18000D17F
0x18000d168  mov     rax, cs:?g_pom@@3PEAVCDateTimeOm@@EA; CDateTimeOm * g_pom
0x18000d16f  cmp     dword ptr [rax+1B4h], 0
0x18000d176  jz      short loc_18000D17F
0x18000d178  mov     ebx, 1
0x18000d17d  jmp     short loc_18000D181
0x18000d17f  xor     ebx, ebx
0x18000d181  mov     edx, 7Fh; nIDDlgItem
0x18000d186  mov     rcx, rdi; hDlg
0x18000d189  call    cs:__imp_GetDlgItem
0x18000d18f  mov     rcx, rax; hWnd
0x18000d192  mov     edx, ebx; nCmdShow
0x18000d194  call    cs:__imp_ShowWindow
0x18000d19a  mov     rcx, [rsp+358h+var_18]
0x18000d1a2  xor     rcx, rsp; StackCookie
0x18000d1a5  call    __security_check_cookie
0x18000d1aa  mov     rbx, [rsp+358h+arg_8]
0x18000d1b2  add     rsp, 350h
0x18000d1b9  pop     rdi
0x18000d1ba  retn
```
