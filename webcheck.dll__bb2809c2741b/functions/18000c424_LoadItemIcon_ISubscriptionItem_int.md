# LoadItemIcon(ISubscriptionItem *,int)

- ea: `0x18000c424`
- end: `0x18000c73a`
- name: `?LoadItemIcon@@YAPEAUHICON__@@PEAUISubscriptionItem@@H@Z`
- size: `790`
- prototype: `HICON __fastcall(struct ISubscriptionItem *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800115e0`
- `0x180014644`

## callees

- `0x18000c424`
- `0x18001d944`
- `0x180029280`
- `0x180029310`
- `0x18002a010`

## import_xrefs

- `USER32!LoadImageW` at `0x18000c709`
- `USER32!LoadImageW` at `0x18000c709`
- `USER32!DestroyIcon` at `0x18000c649`
- `USER32!DestroyIcon` at `0x18000c649`
- `USER32!GetSystemMetrics` at `0x18000c5cc`
- `USER32!GetSystemMetrics` at `0x18000c5da`
- `USER32!GetSystemMetrics` at `0x18000c69e`
- `USER32!GetSystemMetrics` at `0x18000c5cc`
- `USER32!GetSystemMetrics` at `0x18000c5da`
- `USER32!GetSystemMetrics` at `0x18000c69e`
- `ole32!CoCreateInstance` at `0x18000c4d9`
- `ole32!CoCreateInstance` at `0x18000c4d9`
- `SHELL32!ExtractIconW` at `0x18000c621`
- `SHELL32!ExtractIconW` at `0x18000c621`

## string_xrefs

- `0x18000c6c2`: `DesktopComponent`

## pseudocode

```c
HICON __fastcall LoadItemIcon(struct ISubscriptionItem *a1, int a2)
{
  struct ISubscriptionItemVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetCookie)(ISubscriptionItem *, SUBSCRIPTIONCOOKIE *); // rax
  int v6; // ebx
  HICON *p_hIcon; // r15
  HICON *v8; // r12
  __int64 (__fastcall *v9)(__int64, WCHAR *, _QWORD, HICON *, HICON *, int); // rdi
  int SystemMetrics; // ebx
  unsigned __int16 v11; // ax
  int v13; // ecx
  int v14; // ebx
  __int64 v15; // rdx
  UINT nIconIndex; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v17; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  HICON IconW; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  HICON hIcon; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v22; // [rsp+68h] [rbp-98h] BYREF
  IID v23[3]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR pszExeFileName[2088]; // [rsp+B0h] [rbp-50h] BYREF

  lpVtbl = a1->lpVtbl;
  IconW = 0;
  memset(v23, 0, 44);
  GetCookie = lpVtbl->GetCookie;
  v23[0].Data1 = 44;
  v22 = 0;
  ((void (__fastcall *)(struct ISubscriptionItem *, __int128 *))GetCookie)(a1, &v22);
  if ( ((int (__fastcall *)(struct ISubscriptionItem *, IID *))a1->lpVtbl->GetSubscriptionItemInfo)(a1, v23) >= 0 )
  {
    ppv = 0;
    if ( CoCreateInstance((const IID *const)&v23[1].Data4[4], 0, 1u, &IID_ISubscriptionAgentShellExt, &ppv) >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, const WCHAR *, const WCHAR *, int))(*(_QWORD *)ppv + 24LL))(
             ppv,
             &v22,
             &Default,
             &Default,
             -1);
      if ( v6 >= 0 )
      {
        v18 = 0;
        v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IExtractIconW, &v18);
        if ( v6 >= 0 )
        {
          nIconIndex = 0;
          v17 = 0;
          p_hIcon = &hIcon;
          if ( a2 )
            p_hIcon = &IconW;
          hIcon = 0;
          v8 = &IconW;
          if ( a2 )
            v8 = &hIcon;
          v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, WCHAR *, __int64, UINT *, unsigned int *))(*(_QWORD *)v18 + 24LL))(
                 v18,
                 0,
                 pszExeFileName,
                 2084,
                 &nIconIndex,
                 &v17);
          if ( v6 >= 0 )
          {
            v9 = *(__int64 (__fastcall **)(__int64, WCHAR *, _QWORD, HICON *, HICON *, int))(*(_QWORD *)v18 + 32LL);
            SystemMetrics = (unsigned __int16)GetSystemMetrics(11);
            v11 = GetSystemMetrics(49);
            v6 = v9(v18, pszExeFileName, nIconIndex, p_hIcon, v8, SystemMetrics | (v11 << 16));
            if ( v6 == 1 )
            {
              IconW = ExtractIconW(g_hInst, pszExeFileName, nIconIndex);
              if ( !IconW )
                v6 = -2147467259;
            }
            else if ( hIcon && IconW != hIcon )
            {
              DestroyIcon(hIcon);
            }
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v6 >= 0 )
        return IconW;
    }
  }
  v17 = 0;
  v13 = 11;
  nIconIndex = 0;
  if ( !a2 )
    v13 = 49;
  v14 = GetSystemMetrics(v13);
  ReadDWORD(a1, L"Channel", &v17);
  ReadDWORD(a1, L"DesktopComponent", &nIconIndex);
  if ( nIconIndex == 1 )
  {
    v15 = 160;
  }
  else
  {
    v15 = 121;
    if ( v17 != 1 )
      v15 = 400;
  }
  return (HICON)LoadImageW(g_hInst, (LPCWSTR)v15, 1u, v14, v14, 0);
}

```

## disassembly

```asm
0x18000c424  mov     [rsp-8+arg_8], rbx
0x18000c429  mov     [rsp-8+arg_10], rsi
0x18000c42e  push    rbp
0x18000c42f  push    rdi
0x18000c430  push    r12
0x18000c432  push    r14
0x18000c434  push    r15
0x18000c436  lea     rbp, [rsp-1010h]
0x18000c43e  mov     eax, 1110h
0x18000c443  call    _alloca_probe
0x18000c448  sub     rsp, rax
0x18000c44b  mov     rax, cs:__security_cookie
0x18000c452  xor     rax, rsp
0x18000c455  mov     [rbp+1030h+var_30], rax
0x18000c45c  mov     rax, [rcx]
0x18000c45f  xorps   xmm0, xmm0
0x18000c462  mov     r14d, edx
0x18000c465  mov     [rsp+1130h+var_10E0], 0
0x18000c46e  movups  [rsp+1130h+var_10B8], xmm0
0x18000c473  lea     rdx, [rsp+1130h+var_10C8]
0x18000c478  mov     rsi, rcx
0x18000c47b  mov     rax, [rax+18h]
0x18000c47f  movups  xmmword ptr [rbp+1030h+rclsid], xmm0
0x18000c483  mov     dword ptr [rsp+1130h+var_10B8], 2Ch ; ','
0x18000c48b  movups  xmmword ptr [rbp+1030h+rclsid+0Ch], xmm0
0x18000c48f  movups  [rsp+1130h+var_10C8], xmm0
0x18000c494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c499  mov     rax, [rsi]
0x18000c49c  lea     rdx, [rsp+1130h+var_10B8]
0x18000c4a1  mov     rcx, rsi
0x18000c4a4  mov     rax, [rax+20h]
0x18000c4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4ad  test    eax, eax
0x18000c4af  js      loc_18000C67F
0x18000c4b5  xor     edx, edx; pUnkOuter
0x18000c4b7  mov     [rsp+1130h+var_10D8], 0
0x18000c4c0  lea     rax, [rsp+1130h+var_10D8]
0x18000c4c5  lea     r9, IID_ISubscriptionAgentShellExt; riid
0x18000c4cc  mov     [rsp+1130h+ppv], rax; ppv
0x18000c4d1  lea     rcx, [rbp+1030h+rclsid+0Ch]; rclsid
0x18000c4d5  lea     r8d, [rdx+1]; dwClsContext
0x18000c4d9  call    cs:__imp_CoCreateInstance
0x18000c4df  test    eax, eax
0x18000c4e1  js      loc_18000C67F
0x18000c4e7  mov     rcx, [rsp+1130h+var_10D8]
0x18000c4ec  lea     r8, Default
0x18000c4f3  mov     r9, r8
0x18000c4f6  mov     dword ptr [rsp+1130h+ppv], 0FFFFFFFFh
0x18000c4fe  lea     rdx, [rsp+1130h+var_10C8]
0x18000c503  mov     rax, [rcx]
0x18000c506  mov     rax, [rax+18h]
0x18000c50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c50f  mov     ebx, eax
0x18000c511  test    eax, eax
0x18000c513  js      loc_18000C660
0x18000c519  mov     rcx, [rsp+1130h+var_10D8]
0x18000c51e  lea     r8, [rsp+1130h+var_10E8]
0x18000c523  mov     [rsp+1130h+var_10E8], 0
0x18000c52c  lea     rdx, IID_IExtractIconW
0x18000c533  mov     rax, [rcx]
0x18000c536  mov     rax, [rax]
0x18000c539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c53e  mov     ebx, eax
0x18000c540  test    eax, eax
0x18000c542  js      loc_18000C660
0x18000c548  mov     rcx, [rsp+1130h+var_10E8]
0x18000c54d  lea     rax, [rsp+1130h+var_10E0]
0x18000c552  test    r14d, r14d
0x18000c555  mov     [rsp+1130h+nIconIndex], 0
0x18000c55d  mov     [rsp+1130h+var_10EC], 0
0x18000c565  lea     rdx, [rsp+1130h+var_10EC]
0x18000c56a  mov     qword ptr [rsp+1130h+fuLoad], rdx
0x18000c56f  lea     r15, [rsp+1130h+hIcon]
0x18000c574  cmovnz  r15, rax
0x18000c578  mov     [rsp+1130h+hIcon], 0
0x18000c581  lea     rdx, [rsp+1130h+nIconIndex]
0x18000c586  mov     r9d, 824h
0x18000c58c  lea     rax, [rsp+1130h+hIcon]
0x18000c591  mov     [rsp+1130h+ppv], rdx
0x18000c596  lea     r12, [rsp+1130h+var_10E0]
0x18000c59b  cmovnz  r12, rax
0x18000c59f  lea     r8, [rbp+1030h+pszExeFileName]
0x18000c5a3  mov     rax, [rcx]
0x18000c5a6  xor     edx, edx
0x18000c5a8  mov     rax, [rax+18h]
0x18000c5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5b1  mov     ebx, eax
0x18000c5b3  test    eax, eax
0x18000c5b5  js      loc_18000C64F
0x18000c5bb  mov     rax, [rsp+1130h+var_10E8]
0x18000c5c0  mov     rcx, [rax]
0x18000c5c3  mov     rdi, [rcx+20h]
0x18000c5c7  mov     ecx, 0Bh; nIndex
0x18000c5cc  call    cs:__imp_GetSystemMetrics
0x18000c5d2  mov     ecx, 31h ; '1'; nIndex
0x18000c5d7  movzx   ebx, ax
0x18000c5da  call    cs:__imp_GetSystemMetrics
0x18000c5e0  mov     r8d, [rsp+1130h+nIconIndex]
0x18000c5e5  lea     rdx, [rbp+1030h+pszExeFileName]
0x18000c5e9  movzx   ecx, ax
0x18000c5ec  mov     r9, r15
0x18000c5ef  shl     ecx, 10h
0x18000c5f2  mov     rax, rdi
0x18000c5f5  or      ecx, ebx
0x18000c5f7  mov     [rsp+1130h+fuLoad], ecx
0x18000c5fb  mov     rcx, [rsp+1130h+var_10E8]
0x18000c600  mov     [rsp+1130h+ppv], r12
0x18000c605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c60a  mov     ebx, eax
0x18000c60c  cmp     eax, 1
0x18000c60f  jnz     short loc_18000C638
0x18000c611  mov     r8d, [rsp+1130h+nIconIndex]; nIconIndex
0x18000c616  lea     rdx, [rbp+1030h+pszExeFileName]; pszExeFileName
0x18000c61a  mov     rcx, cs:g_hInst; hInst
0x18000c621  call    cs:__imp_ExtractIconW
0x18000c627  mov     [rsp+1130h+var_10E0], rax
0x18000c62c  test    rax, rax
0x18000c62f  jnz     short loc_18000C64F
0x18000c631  mov     ebx, 80004005h
0x18000c636  jmp     short loc_18000C64F
0x18000c638  mov     rcx, [rsp+1130h+hIcon]; hIcon
0x18000c63d  test    rcx, rcx
0x18000c640  jz      short loc_18000C64F
0x18000c642  cmp     [rsp+1130h+var_10E0], rcx
0x18000c647  jz      short loc_18000C64F
0x18000c649  call    cs:__imp_DestroyIcon
0x18000c64f  mov     rcx, [rsp+1130h+var_10E8]
0x18000c654  mov     rax, [rcx]
0x18000c657  mov     rax, [rax+10h]
0x18000c65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c660  mov     rcx, [rsp+1130h+var_10D8]
0x18000c665  mov     rax, [rcx]
0x18000c668  mov     rax, [rax+10h]
0x18000c66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c671  test    ebx, ebx
0x18000c673  js      short loc_18000C67F
0x18000c675  mov     rax, [rsp+1130h+var_10E0]
0x18000c67a  jmp     loc_18000C70F
0x18000c67f  mov     [rsp+1130h+var_10EC], 0
0x18000c687  mov     ecx, 0Bh
0x18000c68c  mov     [rsp+1130h+nIconIndex], 0
0x18000c694  test    r14d, r14d
0x18000c697  jnz     short loc_18000C69E
0x18000c699  mov     ecx, 31h ; '1'; nIndex
0x18000c69e  call    cs:__imp_GetSystemMetrics
0x18000c6a4  lea     r8, [rsp+1130h+var_10EC]; unsigned int *
0x18000c6a9  mov     rcx, rsi; struct ISubscriptionItem *
0x18000c6ac  lea     rdx, ?c_szPropChannel@@3QBGB; "Channel"
0x18000c6b3  mov     ebx, eax
0x18000c6b5  call    ?ReadDWORD@@YAJPEAUISubscriptionItem@@PEBGPEAK@Z; ReadDWORD(ISubscriptionItem *,ushort const *,ulong *)
0x18000c6ba  lea     r8, [rsp+1130h+nIconIndex]; unsigned int *
0x18000c6bf  mov     rcx, rsi; struct ISubscriptionItem *
0x18000c6c2  lea     rdx, ?c_szPropDesktopComponent@@3QBGB; "DesktopComponent"
0x18000c6c9  call    ?ReadDWORD@@YAJPEAUISubscriptionItem@@PEBGPEAK@Z; ReadDWORD(ISubscriptionItem *,ushort const *,ulong *)
0x18000c6ce  cmp     [rsp+1130h+nIconIndex], 1
0x18000c6d3  jnz     short loc_18000C6DC
0x18000c6d5  mov     edx, 0A0h
0x18000c6da  jmp     short loc_18000C6ED
0x18000c6dc  cmp     [rsp+1130h+var_10EC], 1
0x18000c6e1  mov     edx, 79h ; 'y'
0x18000c6e6  jz      short loc_18000C6ED
0x18000c6e8  mov     edx, 190h; name
0x18000c6ed  mov     rcx, cs:g_hInst; hInst
0x18000c6f4  mov     r9d, ebx; cx
0x18000c6f7  mov     [rsp+1130h+fuLoad], 0; fuLoad
0x18000c6ff  mov     r8d, 1; type
0x18000c705  mov     dword ptr [rsp+1130h+ppv], ebx; cy
0x18000c709  call    cs:__imp_LoadImageW
0x18000c70f  mov     rcx, [rbp+1030h+var_30]
0x18000c716  xor     rcx, rsp; StackCookie
0x18000c719  call    __security_check_cookie
0x18000c71e  lea     r11, [rsp+1130h+var_20]
0x18000c726  mov     rbx, [r11+38h]
0x18000c72a  mov     rsi, [r11+40h]
0x18000c72e  mov     rsp, r11
0x18000c731  pop     r15
0x18000c733  pop     r14
0x18000c735  pop     r12
0x18000c737  pop     rdi
0x18000c738  pop     rbp
0x18000c739  retn
```
