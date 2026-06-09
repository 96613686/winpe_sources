# AddExtendedSendMailToItems(IAddrBook *,HWND__ *,HMENU__ *,int)

- ea: `0x180061df4`
- end: `0x1800620a6`
- name: `?AddExtendedSendMailToItems@@YAXPEAUIAddrBook@@PEAUHWND__@@PEAUHMENU__@@H@Z`
- size: `690`
- prototype: `void __fastcall __noreturn(struct IAddrBook *, HWND hWnd, HMENU hMenu, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007ff8`

## callees

- `0x18001d778`
- `0x18002fe40`
- `0x180061df4`
- `0x1800637cc`
- `0x1800648b0`
- `0x180066ea8`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180061fa2`
- `KERNEL32!lstrcmpiW` at `0x180061fa2`
- `USER32!LoadStringW` at `0x180061fc3`
- `USER32!LoadStringW` at `0x180061fc3`
- `USER32!SendMessageW` at `0x180061e43`
- `USER32!SendMessageW` at `0x180061eb2`
- `USER32!SendMessageW` at `0x180061e43`
- `USER32!SendMessageW` at `0x180061eb2`
- `USER32!GetMenuItemCount` at `0x180061e60`
- `USER32!GetMenuItemCount` at `0x180061e60`
- `USER32!InsertMenuW` at `0x180062049`
- `USER32!InsertMenuW` at `0x180062049`
- `USER32!EnableMenuItem` at `0x180062076`
- `USER32!EnableMenuItem` at `0x180062076`
- `USER32!GetSubMenu` at `0x180061e54`
- `USER32!GetSubMenu` at `0x180061e54`
- `USER32!RemoveMenu` at `0x180061e7f`
- `USER32!RemoveMenu` at `0x180061e7f`

## pseudocode

```c
void __fastcall __noreturn AddExtendedSendMailToItems(struct IAddrBook *a1, HWND hWnd, HMENU hMenu, int a4)
{
  int v8; // r14d
  HMENU SubMenu; // r12
  int MenuItemCount; // eax
  int v11; // r13d
  signed int i; // ebx
  int v13; // ebx
  int v14; // eax
  struct _RecipientInfo *ItemFromLV; // rax
  struct ENTRYID *v16; // r9
  unsigned int v17; // r8d
  _QWORD *v18; // rdi
  const WCHAR *v19; // rsi
  unsigned int v20; // ebx
  unsigned __int16 *lpNewItem; // r14
  __int64 v22; // rax
  unsigned int v23; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  HMENU hMenua; // [rsp+50h] [rbp-B0h]
  struct _SPropTagArray v26; // [rsp+58h] [rbp-A8h] BYREF
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v30[520]; // [rsp+280h] [rbp+180h] BYREF

  hMenua = hMenu;
  v8 = SendMessageW(hWnd, 0x1032u, 0, 0);
  SubMenu = GetSubMenu(hMenu, 1);
  MenuItemCount = GetMenuItemCount(SubMenu);
  v11 = MenuItemCount;
  if ( MenuItemCount > 0 )
  {
    for ( i = MenuItemCount - 1; i >= 0; --i )
      RemoveMenu(SubMenu, i, 0x400u);
  }
  v13 = 1;
  if ( a4 )
  {
    if ( v8 == 1 )
    {
      v14 = SendMessageW(hWnd, 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
      ItemFromLV = GetItemFromLV(hWnd, v14);
      if ( ItemFromLV )
      {
        v16 = (struct ENTRYID *)*((_QWORD *)ItemFromLV + 1);
        v17 = *(_DWORD *)ItemFromLV;
        v23 = 0;
        pv = 0;
        v26.cValues = 3;
        v26.aulPropTag[0] = 978718751;
        v27 = 268304387;
        v28 = 805503007;
        if ( (int)HrGetPropArray(a1, &v26, v17, v16, 0x80000000, &v23, (struct _SPropValue **)&pv) >= 0 )
        {
          if ( v23 )
          {
            v18 = pv;
            if ( pv )
            {
              if ( *((_DWORD *)pv + 6) == 268304387
                && *((_DWORD *)pv + 8) == 6
                && *(_DWORD *)pv == 978718751
                && *((_DWORD *)pv + 2) > 1u )
              {
                if ( *((_DWORD *)pv + 12) == 805503007 )
                  v19 = (const WCHAR *)*((_QWORD *)pv + 7);
                else
                  v19 = &szNULL;
                v20 = 0;
                do
                {
                  lpNewItem = *(unsigned __int16 **)(v18[2] + 8LL * v20);
                  if ( !lstrcmpiW(lpNewItem, v19) )
                  {
                    LoadStringW(hinstMapiX, 0xFB7u, Buffer, 260);
                    v22 = -1;
                    do
                      ++v22;
                    while ( Buffer[v22] );
                    CopyTruncate(v30, lpNewItem, 510 - v22);
                    StringCchCatW(v30, 0x208u, L"  ");
                    StringCchCatW(v30, 0x208u, Buffer);
                    lpNewItem = v30;
                  }
                  if ( v20 < 0x40 )
                    InsertMenuW(SubMenu, v11 + 1, 0x400u, v20 + 8533, lpNewItem);
                  ++v20;
                }
                while ( v20 < *((_DWORD *)v18 + 2) );
                v13 = 0;
              }
              MAPIFreeBuffer(v18);
            }
          }
        }
      }
    }
  }
  EnableMenuItem(hMenua, 1u, v13 | 0x400);
}

```

## disassembly

```asm
0x180061df4  mov     [rsp-8+arg_18], rbx
0x180061df9  push    rbp
0x180061dfa  push    rsi
0x180061dfb  push    rdi
0x180061dfc  push    r12
0x180061dfe  push    r13
0x180061e00  push    r14
0x180061e02  push    r15
0x180061e04  lea     rbp, [rsp-5A0h]
0x180061e0c  sub     rsp, 6A0h
0x180061e13  mov     rax, cs:__security_cookie
0x180061e1a  xor     rax, rsp
0x180061e1d  mov     [rbp+5D0h+var_40], rax
0x180061e24  mov     rdi, rdx
0x180061e27  mov     rbx, r8
0x180061e2a  mov     esi, r9d
0x180061e2d  mov     [rsp+6D0h+hMenu], rbx
0x180061e32  mov     r15, rcx
0x180061e35  xor     r9d, r9d; lParam
0x180061e38  mov     rcx, rdi; hWnd
0x180061e3b  xor     r8d, r8d; wParam
0x180061e3e  mov     edx, 1032h; Msg
0x180061e43  call    cs:__imp_SendMessageW
0x180061e49  mov     edx, 1; nPos
0x180061e4e  mov     rcx, rbx; hMenu
0x180061e51  mov     r14, rax
0x180061e54  call    cs:__imp_GetSubMenu
0x180061e5a  mov     rcx, rax; hMenu
0x180061e5d  mov     r12, rax
0x180061e60  call    cs:__imp_GetMenuItemCount
0x180061e66  mov     r13d, eax
0x180061e69  test    eax, eax
0x180061e6b  jle     short loc_180061E8A
0x180061e6d  lea     ebx, [rax-1]
0x180061e70  test    ebx, ebx
0x180061e72  js      short loc_180061E8A
0x180061e74  mov     r8d, 400h; uFlags
0x180061e7a  mov     edx, ebx; uPosition
0x180061e7c  mov     rcx, r12; hMenu
0x180061e7f  call    cs:__imp_RemoveMenu
0x180061e85  sub     ebx, 1
0x180061e88  jns     short loc_180061E74
0x180061e8a  mov     ebx, 1
0x180061e8f  test    esi, esi
0x180061e91  jz      loc_180062065
0x180061e97  mov     esi, ebx
0x180061e99  cmp     r14d, ebx
0x180061e9c  jnz     loc_180062065
0x180061ea2  lea     r9d, [rbx+1]; lParam
0x180061ea6  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180061eaa  mov     edx, 100Ch; Msg
0x180061eaf  mov     rcx, rdi; hWnd
0x180061eb2  call    cs:__imp_SendMessageW
0x180061eb8  mov     rdx, rax; int
0x180061ebb  mov     rcx, rdi; hWnd
0x180061ebe  call    ?GetItemFromLV@@YAPEAU_RecipientInfo@@PEAUHWND__@@H@Z
0x180061ec3  xor     r14d, r14d
0x180061ec6  test    rax, rax
0x180061ec9  jz      loc_180062065
0x180061ecf  mov     r9, [rax+8]; struct ENTRYID *
0x180061ed3  lea     rcx, [rsp+6D0h+pv]
0x180061ed8  mov     r8d, [rax]; unsigned int
0x180061edb  lea     rdx, [rsp+6D0h+var_678]; struct _SPropTagArray *
0x180061ee0  mov     [rsp+6D0h+var_6A0], rcx; struct _SPropValue **
0x180061ee5  lea     rcx, [rsp+6D0h+var_690]
0x180061eea  mov     [rsp+6D0h+var_6A8], rcx; unsigned int *
0x180061eef  mov     rcx, r15; struct IAddrBook *
0x180061ef2  mov     [rsp+6D0h+var_690], r14d
0x180061ef7  mov     [rsp+6D0h+pv], r14
0x180061efc  mov     [rsp+6D0h+var_678.cValues], 3
0x180061f04  mov     [rsp+6D0h+var_678.aulPropTag], 3A56101Fh
0x180061f0c  mov     [rsp+6D0h+var_670], 0FFE0003h
0x180061f14  mov     [rsp+6D0h+var_66C], 3003001Fh
0x180061f1c  mov     dword ptr [rsp+6D0h+lpNewItem], 80000000h; unsigned int
0x180061f24  call    ?HrGetPropArray@@YAJPEAUIAddrBook@@PEAU_SPropTagArray@@KPEAUENTRYID@@KPEAKPEAPEAU_SPropValue@@@Z
0x180061f29  test    eax, eax
0x180061f2b  js      loc_180062065
0x180061f31  cmp     [rsp+6D0h+var_690], r14d
0x180061f36  jz      loc_180062065
0x180061f3c  mov     rdi, [rsp+6D0h+pv]
0x180061f41  test    rdi, rdi
0x180061f44  jz      loc_180062065
0x180061f4a  cmp     dword ptr [rdi+18h], 0FFE0003h
0x180061f51  jnz     loc_18006205D
0x180061f57  cmp     dword ptr [rdi+20h], 6
0x180061f5b  jnz     loc_18006205D
0x180061f61  cmp     dword ptr [rdi], 3A56101Fh
0x180061f67  jnz     loc_18006205D
0x180061f6d  cmp     [rdi+8], ebx
0x180061f70  jbe     loc_18006205D
0x180061f76  cmp     dword ptr [rdi+30h], 3003001Fh
0x180061f7d  jnz     short loc_180061F85
0x180061f7f  mov     rsi, [rdi+38h]
0x180061f83  jmp     short loc_180061F8C
0x180061f85  lea     rsi, ?szNULL@@3QBGB
0x180061f8c  mov     ebx, r14d
0x180061f8f  xor     r15d, r15d
0x180061f92  mov     rax, [rdi+10h]
0x180061f96  mov     rdx, rsi; lpString2
0x180061f99  mov     ecx, ebx
0x180061f9b  mov     r14, [rax+rcx*8]
0x180061f9f  mov     rcx, r14; lpString1
0x180061fa2  call    cs:__imp_lstrcmpiW
0x180061fa8  test    eax, eax
0x180061faa  jnz     short loc_18006202B
0x180061fac  mov     rcx, cs:hinstMapiX; hInstance
0x180061fb3  lea     r8, [rsp+6D0h+Buffer]; lpBuffer
0x180061fb8  mov     r9d, 104h; cchBufferMax
0x180061fbe  mov     edx, 0FB7h; uID
0x180061fc3  call    cs:__imp_LoadStringW
0x180061fc9  lea     rcx, [rsp+6D0h+Buffer]
0x180061fce  or      rax, 0FFFFFFFFFFFFFFFFh
0x180061fd2  inc     rax
0x180061fd5  cmp     [rcx+rax*2], r15w
0x180061fda  jnz     short loc_180061FD2
0x180061fdc  mov     r8d, 1FEh
0x180061fe2  lea     rcx, [rbp+5D0h+var_450]; unsigned __int16 *
0x180061fe9  sub     r8d, eax; int
0x180061fec  mov     rdx, r14; unsigned __int16 *
0x180061fef  call    ?CopyTruncate@@YAXPEAG0H@Z
0x180061ff4  mov     r14d, 208h
0x180061ffa  lea     r8, asc_18009D1B4
0x180062001  mov     edx, r14d; unsigned __int64
0x180062004  lea     rcx, [rbp+5D0h+var_450]; unsigned __int16 *
0x18006200b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x180062010  lea     r8, [rsp+6D0h+Buffer]; unsigned __int16 *
0x180062015  mov     edx, r14d; unsigned __int64
0x180062018  lea     rcx, [rbp+5D0h+var_450]; unsigned __int16 *
0x18006201f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z
0x180062024  lea     r14, [rbp+5D0h+var_450]
0x18006202b  cmp     ebx, 40h ; '@'
0x18006202e  jnb     short loc_18006204F
0x180062030  lea     r9d, [rbx+2155h]; uIDNewItem
0x180062037  mov     [rsp+6D0h+lpNewItem], r14; lpNewItem
0x18006203c  lea     edx, [r13+1]; uPosition
0x180062040  mov     r8d, 400h; uFlags
0x180062046  mov     rcx, r12; hMenu
0x180062049  call    cs:__imp_InsertMenuW
0x18006204f  inc     ebx
0x180062051  cmp     ebx, [rdi+8]
0x180062054  jb      loc_180061F92
0x18006205a  mov     ebx, r15d
0x18006205d  mov     rcx, rdi; pv
0x180062060  call    MAPIFreeBuffer
0x180062065  mov     rcx, [rsp+6D0h+hMenu]; hMenu
0x18006206a  bts     ebx, 0Ah
0x18006206e  mov     r8d, ebx; uEnable
0x180062071  mov     edx, 1; uIDEnableItem
0x180062076  call    cs:__imp_EnableMenuItem
0x18006207c  mov     rcx, [rbp+5D0h+var_40]
0x180062083  xor     rcx, rsp; StackCookie
0x180062086  call    __security_check_cookie
0x18006208b  mov     rbx, [rsp+6D0h+arg_18]
0x180062093  add     rsp, 6A0h
0x18006209a  pop     r15
0x18006209c  pop     r14
0x18006209e  pop     r13
0x1800620a0  pop     r12
0x1800620a2  pop     rdi
0x1800620a3  pop     rsi
0x1800620a4  pop     rbp
0x1800620a5  retn
```
