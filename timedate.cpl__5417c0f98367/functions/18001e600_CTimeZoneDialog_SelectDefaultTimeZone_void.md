# CTimeZoneDialog::_SelectDefaultTimeZone(void)

- ea: `0x18001e600`
- end: `0x18001e743`
- name: `?_SelectDefaultTimeZone@CTimeZoneDialog@@AEAAXXZ`
- size: `323`
- prototype: `void __fastcall(CTimeZoneDialog *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001de28`

## callees

- `0x18001c978`
- `0x18001cbc4`
- `0x18001dd50`
- `0x18001e600`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e67a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001e67a`
- `USER32!CheckDlgButton` at `0x18001e70e`
- `USER32!CheckDlgButton` at `0x18001e70e`
- `USER32!ShowWindow` at `0x18001e6ee`
- `USER32!ShowWindow` at `0x18001e71c`
- `USER32!ShowWindow` at `0x18001e6ee`
- `USER32!ShowWindow` at `0x18001e71c`
- `USER32!SendMessageW` at `0x18001e698`
- `USER32!SendMessageW` at `0x18001e6c1`
- `USER32!SendMessageW` at `0x18001e698`
- `USER32!SendMessageW` at `0x18001e6c1`

## pseudocode

```c
void __fastcall CTimeZoneDialog::_SelectDefaultTimeZone(CTimeZoneDialog *this)
{
  unsigned int v2; // r8d
  signed int i; // edi
  const WCHAR *PTZ; // rax
  const unsigned __int16 *v5; // rdi
  WCHAR String2[128]; // [rsp+30h] [rbp-118h] BYREF

  memset_0(String2, 0, sizeof(String2));
  if ( CDateTimeOm::get_UITimeZone(*((CDateTimeOm **)this + 4), String2, v2) )
  {
    for ( i = 0; i < *((_DWORD *)this + 10); ++i )
    {
      PTZ = CTimeZoneDialog::GetPTZ(this, i);
      if ( PTZ && CompareStringW(0x7Fu, 0, PTZ, -1, String2, -1) == 2 )
      {
        SendMessageW(*((HWND *)this + 1), 0x14Eu, i, 0);
        goto LABEL_10;
      }
    }
  }
  v5 = CTimeZoneDialog::GetPTZ(this, 0);
  if ( v5 )
  {
    SendMessageW(*((HWND *)this + 1), 0x14Eu, 0, 0);
    CDateTimeOm::_set_UITimeZone(*((CDateTimeOm **)this + 4), v5, 1);
LABEL_10:
    ShowWindow(*((HWND *)this + 2), *(_DWORD *)(*((_QWORD *)this + 4) + 436LL) != 0 ? 5 : 0);
    CheckDlgButton(*(HWND *)this, 127, *(_DWORD *)(*((_QWORD *)this + 4) + 428LL) != 0);
  }
  else
  {
    ShowWindow(*((HWND *)this + 2), 0);
  }
}

```

## disassembly

```asm
0x18001e600  mov     [rsp+arg_8], rbx
0x18001e605  push    rdi
0x18001e606  sub     rsp, 140h
0x18001e60d  mov     rax, cs:__security_cookie
0x18001e614  xor     rax, rsp
0x18001e617  mov     [rsp+148h+var_18], rax
0x18001e61f  mov     rbx, rcx
0x18001e622  xor     edx, edx; Val
0x18001e624  lea     rcx, [rsp+148h+String2]; void *
0x18001e629  mov     r8d, 100h; Size
0x18001e62f  call    memset_0
0x18001e634  mov     rcx, [rbx+20h]; this
0x18001e638  lea     rdx, [rsp+148h+String2]; unsigned __int16 *
0x18001e63d  call    ?get_UITimeZone@CDateTimeOm@@QEAAHPEAGK@Z; CDateTimeOm::get_UITimeZone(ushort *,ulong)
0x18001e642  test    eax, eax
0x18001e644  jz      short loc_18001E6A0
0x18001e646  xor     edi, edi
0x18001e648  cmp     edi, [rbx+28h]
0x18001e64b  jge     short loc_18001E6A0
0x18001e64d  mov     edx, edi; unsigned int
0x18001e64f  mov     rcx, rbx; this
0x18001e652  call    ?GetPTZ@CTimeZoneDialog@@QEAAPEAGI@Z; CTimeZoneDialog::GetPTZ(uint)
0x18001e657  test    rax, rax
0x18001e65a  jz      short loc_18001E685
0x18001e65c  lea     rcx, [rsp+148h+String2]
0x18001e661  mov     [rsp+148h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001e669  xor     edx, edx; dwCmpFlags
0x18001e66b  mov     [rsp+148h+lpString2], rcx; lpString2
0x18001e670  or      r9d, 0FFFFFFFFh; cchCount1
0x18001e674  mov     r8, rax; lpString1
0x18001e677  lea     ecx, [rdx+7Fh]; Locale
0x18001e67a  call    cs:__imp_CompareStringW
0x18001e680  cmp     eax, 2
0x18001e683  jz      short loc_18001E689
0x18001e685  inc     edi
0x18001e687  jmp     short loc_18001E648
0x18001e689  mov     rcx, [rbx+8]; hWnd
0x18001e68d  xor     r9d, r9d; lParam
0x18001e690  movsxd  r8, edi; wParam
0x18001e693  mov     edx, 14Eh; Msg
0x18001e698  call    cs:__imp_SendMessageW
0x18001e69e  jmp     short loc_18001E6D9
0x18001e6a0  xor     edx, edx; unsigned int
0x18001e6a2  mov     rcx, rbx; this
0x18001e6a5  call    ?GetPTZ@CTimeZoneDialog@@QEAAPEAGI@Z; CTimeZoneDialog::GetPTZ(uint)
0x18001e6aa  mov     rdi, rax
0x18001e6ad  test    rax, rax
0x18001e6b0  jz      short loc_18001E716
0x18001e6b2  mov     rcx, [rbx+8]; hWnd
0x18001e6b6  xor     r9d, r9d; lParam
0x18001e6b9  xor     r8d, r8d; wParam
0x18001e6bc  mov     edx, 14Eh; Msg
0x18001e6c1  call    cs:__imp_SendMessageW
0x18001e6c7  mov     rcx, [rbx+20h]; this
0x18001e6cb  mov     r8d, 1; int
0x18001e6d1  mov     rdx, rdi; unsigned __int16 *
0x18001e6d4  call    ?_set_UITimeZone@CDateTimeOm@@AEAAHPEBGH@Z; CDateTimeOm::_set_UITimeZone(ushort const *,int)
0x18001e6d9  mov     rax, [rbx+20h]
0x18001e6dd  mov     ecx, [rax+1B4h]
0x18001e6e3  neg     ecx
0x18001e6e5  mov     rcx, [rbx+10h]; hWnd
0x18001e6e9  sbb     edx, edx
0x18001e6eb  and     edx, 5; nCmdShow
0x18001e6ee  call    cs:__imp_ShowWindow
0x18001e6f4  mov     rax, [rbx+20h]
0x18001e6f8  xor     r8d, r8d
0x18001e6fb  mov     rcx, [rbx]; hDlg
0x18001e6fe  mov     edx, 7Fh; nIDButton
0x18001e703  cmp     [rax+1ACh], r8d
0x18001e70a  setnz   r8b; uCheck
0x18001e70e  call    cs:__imp_CheckDlgButton
0x18001e714  jmp     short loc_18001E722
0x18001e716  mov     rcx, [rbx+10h]; hWnd
0x18001e71a  xor     edx, edx; nCmdShow
0x18001e71c  call    cs:__imp_ShowWindow
0x18001e722  mov     rcx, [rsp+148h+var_18]
0x18001e72a  xor     rcx, rsp; StackCookie
0x18001e72d  call    __security_check_cookie
0x18001e732  mov     rbx, [rsp+148h+arg_8]
0x18001e73a  add     rsp, 140h
0x18001e741  pop     rdi
0x18001e742  retn
```
