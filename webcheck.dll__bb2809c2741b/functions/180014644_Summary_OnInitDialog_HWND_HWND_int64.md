# Summary_OnInitDialog(HWND__ *,HWND__ *,__int64)

- ea: `0x180014644`
- end: `0x180014848`
- name: `?Summary_OnInitDialog@@YAHPEAUHWND__@@0_J@Z`
- size: `516`
- prototype: `__int64 __fastcall(HWND, HWND, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180014450`

## callees

- `0x18000c424`
- `0x180014530`
- `0x180014644`
- `0x180014924`
- `0x180019ae0`
- `0x18001cd88`
- `0x180029280`
- `0x180029310`
- `0x18002a010`

## import_xrefs

- `msvcrt!_itow_s` at `0x1800147cb`
- `msvcrt!_itow_s` at `0x1800147cb`
- `IEFRAME!__imp_SHRestricted2W` at `0x180014735`
- `IEFRAME!__imp_SHRestricted2W` at `0x180014735`
- `USER32!CheckDlgButton` at `0x180014783`
- `USER32!CheckDlgButton` at `0x180014783`
- `USER32!EnableWindow` at `0x18001474f`
- `USER32!EnableWindow` at `0x18001474f`
- `USER32!LoadIconW` at `0x1800146e1`
- `USER32!LoadIconW` at `0x1800146e1`
- `USER32!SendDlgItemMessageW` at `0x180014704`
- `USER32!SendDlgItemMessageW` at `0x180014704`
- `USER32!GetDlgItem` at `0x180014744`
- `USER32!GetDlgItem` at `0x180014744`
- `USER32!SetDlgItemTextW` at `0x180014764`
- `USER32!SetDlgItemTextW` at `0x180014775`
- `USER32!SetDlgItemTextW` at `0x180014807`
- `USER32!SetDlgItemTextW` at `0x180014764`
- `USER32!SetDlgItemTextW` at `0x180014775`
- `USER32!SetDlgItemTextW` at `0x180014807`
- `USER32!SetWindowLongPtrW` at `0x18001467d`
- `USER32!SetWindowLongPtrW` at `0x18001467d`
- `USER32!LoadStringW` at `0x1800147f4`
- `USER32!LoadStringW` at `0x1800147f4`
- `WININET!GetUrlCacheEntryInfoW` at `0x1800147a9`
- `WININET!GetUrlCacheEntryInfoW` at `0x1800147a9`

## pseudocode

```c
__int64 __fastcall Summary_OnInitDialog(HWND a1, HWND a2, __int64 a3)
{
  struct OOEBuf *Buf; // r14
  struct ISubscriptionItem *v5; // rbx
  UINT v6; // esi
  HICON IconW; // rbp
  __int64 v8; // rcx
  HWND DlgItem; // rax
  DWORD cbCacheEntryInfo; // [rsp+30h] [rbp-1A38h] BYREF
  struct ISubscriptionItem *v12; // [rsp+38h] [rbp-1A30h] BYREF
  wchar_t Buffer[256]; // [rsp+40h] [rbp-1A28h] BYREF
  _INTERNET_CACHE_ENTRY_INFOW CacheEntryInfo; // [rsp+240h] [rbp-1828h] BYREF

  SetWindowLongPtrW(a1, 16, *(_QWORD *)(a3 + 48));
  v12 = 0;
  Buf = Summary_GetBuf(a1);
  if ( (int)SubscriptionItemFromCookie(0, (const struct _GUID *)((char *)Buf + 116), &v12) < 0 )
  {
    v6 = 0;
    IconW = LoadIconW(g_hInst, (LPCWSTR)0x190);
  }
  else
  {
    v5 = v12;
    v6 = 1;
    IconW = LoadItemIcon(v12, 1);
    ((void (__fastcall *)(struct ISubscriptionItem *))v5->lpVtbl->Release)(v5);
  }
  SendDlgItemMessageW(a1, 2161, 0x170u, (WPARAM)IconW, 0);
  if ( !(unsigned int)IsHTTPPrefixed((char *)Buf + 556)
    || (!v6 ? (v8 = 1342177285) : (v8 = 1342177287), (unsigned int)SHRestricted2W(v8, (char *)Buf + 556, 0)) )
  {
    DlgItem = GetDlgItem(a1, 2165);
    EnableWindow(DlgItem, 0);
  }
  SetDlgItemTextW(a1, 2091, (LPCWSTR)Buf + 2363);
  SetDlgItemTextW(a1, 2121, (LPCWSTR)Buf + 278);
  CheckDlgButton(a1, 2165, v6);
  cbCacheEntryInfo = 6144;
  CacheEntryInfo.dwStructSize = 6144;
  if ( GetUrlCacheEntryInfoW((LPCWSTR)Buf + 278, &CacheEntryInfo, &cbCacheEntryInfo) )
    _itow_s(CacheEntryInfo.dwHitRate, Buffer, 0x100u, 10);
  else
    LoadStringW(g_hinstMUI, 0x2030u, Buffer, 256);
  SetDlgItemTextW(a1, 2164, Buffer);
  Summary_ShowOfflineSummary(a1, Buf, v6);
  return 1;
}

```

## disassembly

```asm
0x180014644  mov     [rsp+arg_8], rbx
0x180014649  mov     [rsp+arg_18], rbp
0x18001464e  push    rsi
0x18001464f  push    rdi
0x180014650  push    r14
0x180014652  mov     eax, 1A50h
0x180014657  call    _alloca_probe
0x18001465c  sub     rsp, rax
0x18001465f  mov     rax, cs:__security_cookie
0x180014666  xor     rax, rsp
0x180014669  mov     [rsp+1A68h+var_28], rax
0x180014671  mov     r8, [r8+30h]; dwNewLong
0x180014675  mov     edx, 10h; nIndex
0x18001467a  mov     rdi, rcx
0x18001467d  call    cs:__imp_SetWindowLongPtrW
0x180014683  mov     rcx, rdi; HWND
0x180014686  call    ?Summary_GetBuf@@YAPEAUOOEBuf@@PEAUHWND__@@@Z; Summary_GetBuf(HWND__ *)
0x18001468b  lea     r8, [rsp+1A68h+var_1A30]; struct ISubscriptionItem **
0x180014690  mov     [rsp+1A68h+var_1A30], 0
0x180014699  xor     ecx, ecx; int
0x18001469b  mov     r14, rax
0x18001469e  lea     rdx, [rax+74h]; struct _GUID *
0x1800146a2  call    ?SubscriptionItemFromCookie@@YAJHPEFBU_GUID@@PEAPEAUISubscriptionItem@@@Z; SubscriptionItemFromCookie(int,_GUID const *,ISubscriptionItem * *)
0x1800146a7  test    eax, eax
0x1800146a9  js      short loc_1800146D3
0x1800146ab  mov     rbx, [rsp+1A68h+var_1A30]
0x1800146b0  mov     esi, 1
0x1800146b5  mov     edx, esi; int
0x1800146b7  mov     rcx, rbx; struct ISubscriptionItem *
0x1800146ba  call    ?LoadItemIcon@@YAPEAUHICON__@@PEAUISubscriptionItem@@H@Z; LoadItemIcon(ISubscriptionItem *,int)
0x1800146bf  mov     rcx, [rbx]
0x1800146c2  mov     rbp, rax
0x1800146c5  mov     rax, [rcx+10h]
0x1800146c9  mov     rcx, rbx
0x1800146cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146d1  jmp     short loc_1800146EA
0x1800146d3  mov     rcx, cs:g_hInst; hInstance
0x1800146da  xor     esi, esi
0x1800146dc  mov     edx, 190h; lpIconName
0x1800146e1  call    cs:__imp_LoadIconW
0x1800146e7  mov     rbp, rax
0x1800146ea  mov     r9, rbp; wParam
0x1800146ed  mov     [rsp+1A68h+lParam], 0; lParam
0x1800146f6  mov     edx, 871h; nIDDlgItem
0x1800146fb  mov     r8d, 170h; Msg
0x180014701  mov     rcx, rdi; hDlg
0x180014704  call    cs:__imp_SendDlgItemMessageW
0x18001470a  lea     rbx, [r14+22Ch]
0x180014711  mov     rcx, rbx
0x180014714  call    IsHTTPPrefixed
0x180014719  mov     ebp, 875h
0x18001471e  test    eax, eax
0x180014720  jz      short loc_18001473F
0x180014722  xor     r8d, r8d
0x180014725  mov     rdx, rbx
0x180014728  test    esi, esi
0x18001472a  jz      loc_1800147D3
0x180014730  mov     ecx, 50000007h
0x180014735  call    cs:__imp_SHRestricted2W
0x18001473b  test    eax, eax
0x18001473d  jz      short loc_180014755
0x18001473f  mov     edx, ebp; nIDDlgItem
0x180014741  mov     rcx, rdi; hDlg
0x180014744  call    cs:__imp_GetDlgItem
0x18001474a  mov     rcx, rax; hWnd
0x18001474d  xor     edx, edx; bEnable
0x18001474f  call    cs:__imp_EnableWindow
0x180014755  lea     r8, [r14+1276h]; lpString
0x18001475c  mov     edx, 82Bh; nIDDlgItem
0x180014761  mov     rcx, rdi; hDlg
0x180014764  call    cs:__imp_SetDlgItemTextW
0x18001476a  mov     r8, rbx; lpString
0x18001476d  mov     edx, 849h; nIDDlgItem
0x180014772  mov     rcx, rdi; hDlg
0x180014775  call    cs:__imp_SetDlgItemTextW
0x18001477b  mov     r8d, esi; uCheck
0x18001477e  mov     edx, ebp; nIDButton
0x180014780  mov     rcx, rdi; hDlg
0x180014783  call    cs:__imp_CheckDlgButton
0x180014789  mov     eax, 1800h
0x18001478e  lea     r8, [rsp+1A68h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180014793  lea     rdx, [rsp+1A68h+CacheEntryInfo]; lpCacheEntryInfo
0x18001479b  mov     [rsp+1A68h+cbCacheEntryInfo], eax
0x18001479f  mov     rcx, rbx; lpszUrlName
0x1800147a2  mov     [rsp+1A68h+CacheEntryInfo.dwStructSize], eax
0x1800147a9  call    cs:__imp_GetUrlCacheEntryInfoW
0x1800147af  test    eax, eax
0x1800147b1  jz      short loc_1800147DD
0x1800147b3  mov     ecx, [rsp+1A68h+CacheEntryInfo.dwHitRate]; Value
0x1800147ba  lea     rdx, [rsp+1A68h+Buffer]; Buffer
0x1800147bf  mov     r9d, 0Ah; Radix
0x1800147c5  mov     r8d, 100h; BufferCount
0x1800147cb  call    cs:__imp__itow_s
0x1800147d1  jmp     short loc_1800147FA
0x1800147d3  mov     ecx, 50000005h
0x1800147d8  jmp     loc_180014735
0x1800147dd  mov     rcx, cs:g_hinstMUI; hInstance
0x1800147e4  lea     r8, [rsp+1A68h+Buffer]; lpBuffer
0x1800147e9  mov     r9d, 100h; cchBufferMax
0x1800147ef  mov     edx, 2030h; uID
0x1800147f4  call    cs:__imp_LoadStringW
0x1800147fa  lea     r8, [rsp+1A68h+Buffer]; lpString
0x1800147ff  mov     edx, 874h; nIDDlgItem
0x180014804  mov     rcx, rdi; hDlg
0x180014807  call    cs:__imp_SetDlgItemTextW
0x18001480d  mov     r8d, esi; int
0x180014810  mov     rdx, r14; struct OOEBuf *
0x180014813  mov     rcx, rdi; hDlg
0x180014816  call    ?Summary_ShowOfflineSummary@@YAXPEAUHWND__@@PEBUOOEBuf@@H@Z; Summary_ShowOfflineSummary(HWND__ *,OOEBuf const *,int)
0x18001481b  mov     eax, 1
0x180014820  mov     rcx, [rsp+1A68h+var_28]
0x180014828  xor     rcx, rsp; StackCookie
0x18001482b  call    __security_check_cookie
0x180014830  lea     r11, [rsp+1A68h+var_18]
0x180014838  mov     rbx, [r11+28h]
0x18001483c  mov     rbp, [r11+38h]
0x180014840  mov     rsp, r11
0x180014843  pop     r14
0x180014845  pop     rdi
0x180014846  pop     rsi
0x180014847  retn
```
