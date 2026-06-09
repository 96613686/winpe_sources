# SummarizeDesktopSubscriptionDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800182c0`
- end: `0x18001855d`
- name: `?SummarizeDesktopSubscriptionDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `669`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180003950`
- `0x1800170c8`
- `0x1800182c0`
- `0x18001d0c0`
- `0x18001de94`
- `0x18002924e`
- `0x180029280`
- `0x180029310`

## import_xrefs

- `USER32!RemovePropW` at `0x18001852e`
- `USER32!RemovePropW` at `0x18001852e`
- `USER32!SetPropW` at `0x1800183d6`
- `USER32!SetPropW` at `0x1800183d6`
- `USER32!GetPropW` at `0x180018306`
- `USER32!GetPropW` at `0x180018306`
- `USER32!GetDlgItem` at `0x180018399`
- `USER32!GetDlgItem` at `0x18001844f`
- `USER32!GetDlgItem` at `0x180018479`
- `USER32!GetDlgItem` at `0x1800184ec`
- `USER32!GetDlgItem` at `0x180018399`
- `USER32!GetDlgItem` at `0x18001844f`
- `USER32!GetDlgItem` at `0x180018479`
- `USER32!GetDlgItem` at `0x1800184ec`
- `USER32!EndDialog` at `0x1800183be`
- `USER32!EndDialog` at `0x1800183be`
- `USER32!SetDlgItemTextW` at `0x180018431`
- `USER32!SetDlgItemTextW` at `0x180018431`
- `USER32!SendMessageW` at `0x1800183ab`
- `USER32!SendMessageW` at `0x180018502`
- `USER32!SendMessageW` at `0x1800183ab`
- `USER32!SendMessageW` at `0x180018502`
- `USER32!LoadStringW` at `0x18001841c`
- `USER32!LoadStringW` at `0x18001841c`

## pseudocode

```c
__int64 __fastcall SummarizeDesktopSubscriptionDlgProc(HWND a1, int a2, __int16 a3, __int64 a4)
{
  HANDLE PropW; // rax
  INT_PTR v9; // rdx
  int v10; // edi
  int v11; // edi
  int v12; // edi
  HWND v13; // rax
  HWND DlgItem; // rax
  HWND v15; // rax
  HWND v16; // rax
  LPARAM lParam[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+60h] [rbp-A0h]
  WCHAR Buffer[2088]; // [rsp+A0h] [rbp-60h] BYREF

  PropW = GetPropW(a1, L"SADIP");
  v9 = 2;
  v10 = a2 - 2;
  if ( v10 )
  {
    v11 = v10 - 76;
    if ( v11 )
    {
      v12 = v11 - 194;
      if ( !v12 )
      {
        SetPropW(a1, L"SADIP", (HANDLE)a4);
        LoadIconMUI(a1);
        if ( *(_DWORD *)(a4 + 32) == 4
          && LoadStringW(g_hinstMUI, (*(_DWORD *)(*(_QWORD *)(a4 + 24) + 60LL) != 0) + 8047, Buffer, 2084) )
        {
          SetDlgItemTextW(a1, 2053, Buffer);
        }
        StringCchCopyW(Buffer, 0x824u, *(const unsigned __int16 **)(a4 + 8));
        DlgItem = GetDlgItem(a1, 2112);
        SetListViewToString(DlgItem);
        StringCchCopyW(Buffer, 0x824u, *(const unsigned __int16 **)(a4 + 16));
        v15 = GetDlgItem(a1, 2113);
        SetListViewToString(v15);
        return 0;
      }
      if ( v12 == 1 )
      {
        if ( a3 == 1 )
        {
          v9 = 1;
        }
        else if ( a3 != 2 )
        {
          if ( a3 == 2114
            && *(_QWORD *)PropW
            && !(unsigned int)CSubscriptionMgr::CreateSubscriptionNoSummary(
                                *(CSubscriptionMgr **)PropW,
                                a1,
                                *((const unsigned __int16 **)PropW + 2),
                                *((unsigned __int16 **)PropW + 1),
                                *((_BYTE *)PropW + 36) | 8u,
                                (enum SUBSCRIPTIONTYPE)*((_DWORD *)PropW + 8),
                                *((struct _tagSubscriptionInfo **)PropW + 3)) )
          {
            v13 = GetDlgItem(a1, 1);
            SendMessageW(a1, 0x28u, (WPARAM)v13, 1);
          }
          return 0;
        }
        EndDialog(a1, v9);
      }
    }
    else if ( a3 == 2113 && *(_DWORD *)(a4 + 16) == -158 )
    {
      memset_0(Buffer, 0, 0x1048u);
      memset_0(lParam, 0, 0x58u);
      LODWORD(lParam[0]) = 1;
      lParam[3] = (LPARAM)Buffer;
      v19 = 2084;
      v16 = GetDlgItem(a1, 2113);
      if ( (unsigned int)SendMessageW(v16, 0x104Bu, 0, (LPARAM)lParam) )
      {
        StringCchCopyW(*(unsigned __int16 **)(a4 + 32), *(int *)(a4 + 40), Buffer);
        return 1;
      }
    }
  }
  else
  {
    RemovePropW(a1, L"SADIP");
  }
  return 0;
}

```

## disassembly

```asm
0x1800182c0  mov     [rsp-8+arg_8], rbx
0x1800182c5  mov     [rsp-8+arg_10], rsi
0x1800182ca  push    rbp
0x1800182cb  push    rdi
0x1800182cc  push    r14
0x1800182ce  lea     rbp, [rsp-1000h]
0x1800182d6  mov     eax, 1100h
0x1800182db  call    _alloca_probe
0x1800182e0  sub     rsp, rax
0x1800182e3  mov     rax, cs:__security_cookie
0x1800182ea  xor     rax, rsp
0x1800182ed  mov     [rbp+1010h+var_20], rax
0x1800182f4  mov     edi, edx
0x1800182f6  mov     rsi, r9
0x1800182f9  lea     rdx, String; "SADIP"
0x180018300  mov     r14, r8
0x180018303  mov     rbx, rcx
0x180018306  call    cs:__imp_GetPropW
0x18001830c  mov     edx, 2
0x180018311  mov     r8, rax
0x180018314  sub     edi, edx
0x180018316  jz      loc_180018524
0x18001831c  sub     edi, 4Ch ; 'L'
0x18001831f  jz      loc_180018490
0x180018325  sub     edi, 0C2h
0x18001832b  jz      loc_1800183C9
0x180018331  cmp     edi, 1
0x180018334  jnz     loc_180018534
0x18001833a  movzx   ecx, r14w
0x18001833e  sub     ecx, edi
0x180018340  jz      short loc_1800183B6
0x180018342  sub     ecx, edi
0x180018344  jz      short loc_1800183BB
0x180018346  cmp     ecx, 840h
0x18001834c  jnz     loc_180018534
0x180018352  mov     r10, [rax]
0x180018355  test    r10, r10
0x180018358  jz      loc_180018534
0x18001835e  mov     ecx, [rax+24h]
0x180018361  mov     rdx, rbx; HWND
0x180018364  mov     rax, [rax+18h]
0x180018368  or      ecx, 8
0x18001836b  mov     r9, [r8+8]; unsigned __int16 *
0x18001836f  mov     [rsp+1110h+var_10E0], rax; struct _tagSubscriptionInfo *
0x180018374  mov     eax, [r8+20h]
0x180018378  mov     r8, [r8+10h]; unsigned __int16 *
0x18001837c  mov     [rsp+1110h+var_10E8], eax; enum SUBSCRIPTIONTYPE
0x180018380  mov     dword ptr [rsp+1110h+var_10F0], ecx; char
0x180018384  mov     rcx, r10; this
0x180018387  call    ?CreateSubscriptionNoSummary@CSubscriptionMgr@@IEAAJPEAUHWND__@@PEBG1KW4SUBSCRIPTIONTYPE@@PEAU_tagSubscriptionInfo@@@Z; CSubscriptionMgr::CreateSubscriptionNoSummary(HWND__ *,ushort const *,ushort const *,ulong,SUBSCRIPTIONTYPE,_tagSubscriptionInfo *)
0x18001838c  test    eax, eax
0x18001838e  jnz     loc_180018534
0x180018394  mov     edx, edi; nIDDlgItem
0x180018396  mov     rcx, rbx; hDlg
0x180018399  call    cs:__imp_GetDlgItem
0x18001839f  lea     edx, [rdi+27h]; Msg
0x1800183a2  mov     r9d, edi; lParam
0x1800183a5  mov     r8, rax; wParam
0x1800183a8  mov     rcx, rbx; hWnd
0x1800183ab  call    cs:__imp_SendMessageW
0x1800183b1  jmp     loc_180018534
0x1800183b6  mov     edx, 1; nResult
0x1800183bb  mov     rcx, rbx; hDlg
0x1800183be  call    cs:__imp_EndDialog
0x1800183c4  jmp     loc_180018534
0x1800183c9  mov     r8, rsi; hData
0x1800183cc  lea     rdx, String; "SADIP"
0x1800183d3  mov     rcx, rbx; hWnd
0x1800183d6  call    cs:__imp_SetPropW
0x1800183dc  mov     edx, 0A0h
0x1800183e1  mov     r8d, 2328h
0x1800183e7  mov     rcx, rbx; hDlg
0x1800183ea  call    LoadIconMUI
0x1800183ef  cmp     dword ptr [rsi+20h], 4
0x1800183f3  mov     r14d, 824h
0x1800183f9  jnz     short loc_180018437
0x1800183fb  mov     rax, [rsi+18h]
0x1800183ff  lea     r8, [rbp+1010h+Buffer]; lpBuffer
0x180018403  mov     r9d, r14d; cchBufferMax
0x180018406  mov     ecx, [rax+3Ch]
0x180018409  neg     ecx
0x18001840b  mov     rcx, cs:g_hinstMUI; hInstance
0x180018412  sbb     edx, edx
0x180018414  neg     edx
0x180018416  add     edx, 1F6Fh; uID
0x18001841c  call    cs:__imp_LoadStringW
0x180018422  test    eax, eax
0x180018424  jz      short loc_180018437
0x180018426  lea     r8, [rbp+1010h+Buffer]; lpString
0x18001842a  mov     rcx, rbx; hDlg
0x18001842d  lea     edx, [r14-1Fh]; nIDDlgItem
0x180018431  call    cs:__imp_SetDlgItemTextW
0x180018437  mov     r8, [rsi+8]; unsigned __int16 *
0x18001843b  lea     rcx, [rbp+1010h+Buffer]; unsigned __int16 *
0x18001843f  mov     rdx, r14; unsigned __int64
0x180018442  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018447  mov     edx, 840h; nIDDlgItem
0x18001844c  mov     rcx, rbx; hDlg
0x18001844f  call    cs:__imp_GetDlgItem
0x180018455  mov     rcx, rax; hWnd
0x180018458  lea     rdx, [rbp+1010h+Buffer]
0x18001845c  call    SetListViewToString
0x180018461  mov     r8, [rsi+10h]; unsigned __int16 *
0x180018465  lea     rcx, [rbp+1010h+Buffer]; unsigned __int16 *
0x180018469  mov     rdx, r14; unsigned __int64
0x18001846c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018471  mov     edx, 841h; nIDDlgItem
0x180018476  mov     rcx, rbx; hDlg
0x180018479  call    cs:__imp_GetDlgItem
0x18001847f  mov     rcx, rax; hWnd
0x180018482  lea     rdx, [rbp+1010h+Buffer]
0x180018486  call    SetListViewToString
0x18001848b  jmp     loc_180018534
0x180018490  mov     edi, 841h
0x180018495  cmp     r14w, di
0x180018499  jnz     loc_180018534
0x18001849f  cmp     dword ptr [rsi+10h], 0FFFFFF62h
0x1800184a6  jnz     loc_180018534
0x1800184ac  xor     edx, edx; Val
0x1800184ae  lea     rcx, [rbp+1010h+Buffer]; void *
0x1800184b2  mov     r8d, 1048h; Size
0x1800184b8  call    memset_0
0x1800184bd  xor     edx, edx; Val
0x1800184bf  lea     rcx, [rsp+1110h+lParam]; void *
0x1800184c4  lea     r8d, [rdx+58h]; Size
0x1800184c8  call    memset_0
0x1800184cd  lea     rax, [rbp+1010h+Buffer]
0x1800184d1  mov     dword ptr [rsp+1110h+lParam], 1
0x1800184d9  lea     r14d, [rdi-1Dh]
0x1800184dd  mov     [rsp+1110h+var_10B8], rax
0x1800184e2  mov     edx, edi; nIDDlgItem
0x1800184e4  mov     [rsp+1110h+var_10B0], r14d
0x1800184e9  mov     rcx, rbx; hDlg
0x1800184ec  call    cs:__imp_GetDlgItem
0x1800184f2  lea     r9, [rsp+1110h+lParam]; lParam
0x1800184f7  xor     r8d, r8d; wParam
0x1800184fa  mov     rcx, rax; hWnd
0x1800184fd  mov     edx, 104Bh; Msg
0x180018502  call    cs:__imp_SendMessageW
0x180018508  test    eax, eax
0x18001850a  jz      short loc_180018534
0x18001850c  movsxd  rdx, dword ptr [rsi+28h]; unsigned __int64
0x180018510  lea     r8, [rbp+1010h+Buffer]; unsigned __int16 *
0x180018514  mov     rcx, [rsi+20h]; unsigned __int16 *
0x180018518  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001851d  mov     eax, 1
0x180018522  jmp     short loc_180018536
0x180018524  lea     rdx, String; "SADIP"
0x18001852b  mov     rcx, rbx; hWnd
0x18001852e  call    cs:__imp_RemovePropW
0x180018534  xor     eax, eax
0x180018536  mov     rcx, [rbp+1010h+var_20]
0x18001853d  xor     rcx, rsp; StackCookie
0x180018540  call    __security_check_cookie
0x180018545  lea     r11, [rsp+1110h+var_10]
0x18001854d  mov     rbx, [r11+28h]
0x180018551  mov     rsi, [r11+30h]
0x180018555  mov     rsp, r11
0x180018558  pop     r14
0x18001855a  pop     rdi
0x18001855b  pop     rbp
0x18001855c  retn
```
