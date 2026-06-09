# CACSecurityPage::OnSecurityKey(ushort,ushort,HWND__ *,int &)

- ea: `0x18000b2e8`
- end: `0x18000b3a1`
- name: `?OnSecurityKey@CACSecurityPage@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `185`
- prototype: `__int64 __fastcall(CACSecurityPage *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x180006134`
- `0x18000b2e8`
- `0x18000cd48`

## import_xrefs

- `USER32!ShowWindow` at `0x18000b37e`
- `USER32!ShowWindow` at `0x18000b37e`
- `USER32!IsWindowEnabled` at `0x18000b32a`
- `USER32!IsWindowEnabled` at `0x18000b32a`
- `USER32!IsWindowVisible` at `0x18000b311`
- `USER32!IsWindowVisible` at `0x18000b311`
- `USER32!GetDlgItem` at `0x18000b308`
- `USER32!GetDlgItem` at `0x18000b321`
- `USER32!GetDlgItem` at `0x18000b373`
- `USER32!GetDlgItem` at `0x18000b308`
- `USER32!GetDlgItem` at `0x18000b321`
- `USER32!GetDlgItem` at `0x18000b373`

## pseudocode

```c
__int64 __fastcall CACSecurityPage::OnSecurityKey(HWND *this, __int16 a2, __int64 a3, HWND a4, int *a5)
{
  HWND DlgItem; // rax
  HWND v8; // rax
  NetworkKeyControls *v9; // rcx
  HWND v10; // rax

  DlgItem = GetDlgItem(this[1], 1115);
  if ( !IsWindowVisible(DlgItem) )
    return 0;
  v8 = GetDlgItem(this[1], 1115);
  if ( !IsWindowEnabled(v8) )
    return 0;
  *a5 = 0;
  if ( a2 != 256 )
    return 0;
  v9 = (NetworkKeyControls *)this[166];
  if ( !*((_DWORD *)v9 + 17) )
  {
    NetworkKeyControls::ResetNetworkKeyField(v9);
    *((_DWORD *)this[166] + 17) = 1;
    v10 = GetDlgItem(this[1], 1134);
    ShowWindow(v10, 0);
    *a5 = 1;
  }
  return LresFromHr(0);
}

```

## disassembly

```asm
0x18000b2e8  mov     [rsp+arg_0], rbx
0x18000b2ed  mov     [rsp+arg_8], rsi
0x18000b2f2  push    rdi
0x18000b2f3  sub     rsp, 20h
0x18000b2f7  movzx   esi, dx
0x18000b2fa  mov     rbx, rcx
0x18000b2fd  mov     rcx, [rcx+8]; hDlg
0x18000b301  mov     edi, 45Bh
0x18000b306  mov     edx, edi; nIDDlgItem
0x18000b308  call    cs:__imp_GetDlgItem
0x18000b30e  mov     rcx, rax; hWnd
0x18000b311  call    cs:__imp_IsWindowVisible
0x18000b317  test    eax, eax
0x18000b319  jz      short loc_18000B38F
0x18000b31b  mov     rcx, [rbx+8]; hDlg
0x18000b31f  mov     edx, edi; nIDDlgItem
0x18000b321  call    cs:__imp_GetDlgItem
0x18000b327  mov     rcx, rax; hWnd
0x18000b32a  call    cs:__imp_IsWindowEnabled
0x18000b330  test    eax, eax
0x18000b332  jz      short loc_18000B38F
0x18000b334  mov     rdi, [rsp+28h+arg_20]
0x18000b339  mov     eax, 100h
0x18000b33e  mov     dword ptr [rdi], 0
0x18000b344  cmp     si, ax
0x18000b347  jnz     short loc_18000B38F
0x18000b349  mov     rcx, [rbx+530h]; this
0x18000b350  cmp     dword ptr [rcx+44h], 0
0x18000b354  jnz     short loc_18000B386
0x18000b356  call    ?ResetNetworkKeyField@NetworkKeyControls@@QEAAXXZ; NetworkKeyControls::ResetNetworkKeyField(void)
0x18000b35b  mov     rax, [rbx+530h]
0x18000b362  mov     esi, 1
0x18000b367  mov     edx, 46Eh; nIDDlgItem
0x18000b36c  mov     [rax+44h], esi
0x18000b36f  mov     rcx, [rbx+8]; hDlg
0x18000b373  call    cs:__imp_GetDlgItem
0x18000b379  mov     rcx, rax; hWnd
0x18000b37c  xor     edx, edx; nCmdShow
0x18000b37e  call    cs:__imp_ShowWindow
0x18000b384  mov     [rdi], esi
0x18000b386  xor     ecx, ecx; int
0x18000b388  call    ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
0x18000b38d  jmp     short loc_18000B391
0x18000b38f  xor     eax, eax
0x18000b391  mov     rbx, [rsp+28h+arg_0]
0x18000b396  mov     rsi, [rsp+28h+arg_8]
0x18000b39b  add     rsp, 20h
0x18000b39f  pop     rdi
0x18000b3a0  retn
```
