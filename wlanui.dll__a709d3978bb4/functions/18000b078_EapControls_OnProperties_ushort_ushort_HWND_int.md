# EapControls::OnProperties(ushort,ushort,HWND__ *,int &)

- ea: `0x18000b078`
- end: `0x18000b2df`
- name: `?OnProperties@EapControls@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `615`
- prototype: `__int64 __fastcall(EapControls *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c290`

## callees

- `0x180001e26`
- `0x1800060a0`
- `0x180006134`
- `0x180007df0`
- `0x18000833c`
- `0x18000b078`
- `0x18000c824`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000b251`
- `KERNEL32!HeapAlloc` at `0x18000b251`
- `KERNEL32!GetProcessHeap` at `0x18000b20c`
- `KERNEL32!GetProcessHeap` at `0x18000b240`
- `KERNEL32!GetProcessHeap` at `0x18000b20c`
- `KERNEL32!GetProcessHeap` at `0x18000b240`
- `KERNEL32!HeapFree` at `0x18000b21a`
- `KERNEL32!HeapFree` at `0x18000b21a`
- `USER32!IsWindowEnabled` at `0x18000b0d0`
- `USER32!IsWindowEnabled` at `0x18000b0d0`
- `USER32!IsWindowVisible` at `0x18000b0b3`
- `USER32!IsWindowVisible` at `0x18000b0b3`
- `USER32!GetDlgItem` at `0x18000b0aa`
- `USER32!GetDlgItem` at `0x18000b0c7`
- `USER32!GetDlgItem` at `0x18000b0aa`
- `USER32!GetDlgItem` at `0x18000b0c7`
- `USER32!SendMessageW` at `0x18000b10e`
- `USER32!SendMessageW` at `0x18000b10e`
- `USER32!GetParent` at `0x18000b185`
- `USER32!GetParent` at `0x18000b185`
- `eappcfg!EapHostPeerInvokeConfigUI` at `0x18000b1bf`
- `eappcfg!EapHostPeerInvokeConfigUI` at `0x18000b1bf`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18000b28d`
- `eappcfg!EapHostPeerFreeErrorMemory` at `0x18000b28d`
- `eappcfg!EapHostPeerFreeMemory` at `0x18000b1e0`
- `eappcfg!EapHostPeerFreeMemory` at `0x18000b2bb`
- `eappcfg!EapHostPeerFreeMemory` at `0x18000b1e0`
- `eappcfg!EapHostPeerFreeMemory` at `0x18000b2bb`

## pseudocode

```c
__int64 __fastcall EapControls::OnProperties(HWND *this, __int64 a2, __int16 a3, HWND a4, int *a5)
{
  HWND DlgItem; // rax
  HWND v7; // rax
  HWND v8; // rcx
  int v9; // eax
  void *ItemDataPtr; // r15
  signed int v11; // edi
  struct _AUI_AUTH_INFO *CurrentlySelectedAuth; // rax
  int v13; // r12d
  HWND v14; // rcx
  const BYTE *pConfigIn; // rdi
  DWORD v16; // ebx
  bool v17; // cf
  int v18; // esi
  EAP_METHOD_TYPE v19; // xmm6
  HWND Parent; // rax
  BYTE *v21; // rcx
  void *v22; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v24; // ebx
  HANDLE v25; // rax
  void *v26; // rax
  __int64 v27; // rax
  BYTE *v28; // rcx
  __int64 v29; // rbx
  EAP_METHOD_TYPE eapMethodType; // [rsp+40h] [rbp-40h] BYREF
  void **p_Src; // [rsp+50h] [rbp-30h]
  BYTE *ppConfigOut; // [rsp+58h] [rbp-28h] BYREF
  char v34; // [rsp+60h] [rbp-20h]
  EAP_ERROR *pEapError; // [rsp+C0h] [rbp+40h] BYREF
  DWORD pdwSizeOfConfigOut; // [rsp+D0h] [rbp+50h] BYREF
  void *Src; // [rsp+D8h] [rbp+58h] BYREF

  Src = a4;
  LOWORD(pdwSizeOfConfigOut) = a3;
  DlgItem = GetDlgItem(this[2], 1120);
  if ( !IsWindowVisible(DlgItem) )
    return 0;
  v7 = GetDlgItem(this[2], 1120);
  if ( !IsWindowEnabled(v7) )
    return 0;
  v8 = this[4];
  pdwSizeOfConfigOut = 0;
  Src = 0;
  *a5 = 1;
  pEapError = 0;
  v9 = SendMessageW(v8, 0x147u, 0, 0);
  ItemDataPtr = ComboBox_GetItemDataPtr(this[4], v9);
  if ( ItemDataPtr )
  {
    CurrentlySelectedAuth = CACSecurityPage::GetCurrentlySelectedAuth((CACSecurityPage *)*this);
    if ( *((_DWORD *)CurrentlySelectedAuth + 1) == 8 || (v13 = 128, *((_DWORD *)CurrentlySelectedAuth + 1) == 11) )
      v13 = 33554560;
    v14 = *this;
    pConfigIn = (const BYTE *)*((_QWORD *)ItemDataPtr + 2);
    v16 = *((_DWORD *)ItemDataPtr + 2);
    ppConfigOut = 0;
    v17 = *((_DWORD *)v14 + 23) != 0;
    v34 = 1;
    p_Src = &Src;
    v18 = v17 ? 0x80000 : 0;
    v19 = *(EAP_METHOD_TYPE *)*(_QWORD *)ItemDataPtr;
    Parent = GetParent(*((HWND *)v14 + 1));
    eapMethodType = v19;
    v11 = EapHostPeerInvokeConfigUI(
            Parent,
            v13 | v18,
            &eapMethodType,
            v16,
            pConfigIn,
            &pdwSizeOfConfigOut,
            &ppConfigOut,
            &pEapError);
    if ( v34 )
    {
      v21 = (BYTE *)*p_Src;
      *p_Src = ppConfigOut;
      if ( v21 )
        EapHostPeerFreeMemory(v21);
    }
    if ( v11 )
    {
      if ( v11 != 1223 )
        CACSecurityPage::DisplayErrorMessage((CACSecurityPage *)*this, 0x3AF0u, v11);
      goto LABEL_20;
    }
    v22 = (void *)*((_QWORD *)ItemDataPtr + 2);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
    *((_QWORD *)ItemDataPtr + 2) = 0;
    *((_DWORD *)ItemDataPtr + 2) = 0;
    if ( Src && pdwSizeOfConfigOut )
    {
      v24 = pdwSizeOfConfigOut;
      v25 = GetProcessHeap();
      v26 = HeapAlloc(v25, 8u, v24);
      *((_QWORD *)ItemDataPtr + 2) = v26;
      if ( !v26 )
      {
        v11 = 14;
        goto LABEL_20;
      }
      memcpy_0(v26, Src, pdwSizeOfConfigOut);
      *((_DWORD *)ItemDataPtr + 2) = pdwSizeOfConfigOut;
    }
    CACSecurityPage::RefreshControls((CACSecurityPage *)*this);
    goto LABEL_20;
  }
  v11 = 1003;
LABEL_20:
  if ( pEapError )
    EapHostPeerFreeErrorMemory(pEapError);
  if ( v11 > 0 )
    v11 = (unsigned __int16)v11 | 0x80070000;
  v27 = LresFromHr(v11);
  v28 = (BYTE *)Src;
  v29 = v27;
  Src = 0;
  if ( v28 )
    EapHostPeerFreeMemory(v28);
  return v29;
}

```

## disassembly

```asm
0x18000b078  mov     [rsp-38h+Src], r9
0x18000b07d  mov     word ptr [rsp-38h+arg_10], r8w
0x18000b083  push    rbp
0x18000b084  push    rbx
0x18000b085  push    rsi
0x18000b086  push    rdi
0x18000b087  push    r12
0x18000b089  push    r14
0x18000b08b  push    r15
0x18000b08d  mov     rbp, rsp
0x18000b090  sub     rsp, 80h
0x18000b097  mov     r14, rcx
0x18000b09a  movaps  [rsp+80h+var_10], xmm6
0x18000b09f  mov     rcx, [rcx+10h]; hDlg
0x18000b0a3  mov     ebx, 460h
0x18000b0a8  mov     edx, ebx; nIDDlgItem
0x18000b0aa  call    cs:__imp_GetDlgItem
0x18000b0b0  mov     rcx, rax; hWnd
0x18000b0b3  call    cs:__imp_IsWindowVisible
0x18000b0b9  test    eax, eax
0x18000b0bb  jz      loc_18000B2C6
0x18000b0c1  mov     rcx, [r14+10h]; hDlg
0x18000b0c5  mov     edx, ebx; nIDDlgItem
0x18000b0c7  call    cs:__imp_GetDlgItem
0x18000b0cd  mov     rcx, rax; hWnd
0x18000b0d0  call    cs:__imp_IsWindowEnabled
0x18000b0d6  test    eax, eax
0x18000b0d8  jz      loc_18000B2C6
0x18000b0de  mov     rax, [rbp+arg_20]
0x18000b0e2  xor     r9d, r9d; lParam
0x18000b0e5  mov     rcx, [r14+20h]; hWnd
0x18000b0e9  xor     r8d, r8d; wParam
0x18000b0ec  mov     edx, 147h; Msg
0x18000b0f1  mov     [rbp+arg_10], 0
0x18000b0f8  mov     [rbp+Src], 0
0x18000b100  mov     dword ptr [rax], 1
0x18000b106  mov     [rbp+pEapError], 0
0x18000b10e  call    cs:__imp_SendMessageW
0x18000b114  mov     rcx, [r14+20h]; HWND
0x18000b118  mov     edx, eax; int
0x18000b11a  call    ?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z; ComboBox_GetItemDataPtr(HWND__ *,int)
0x18000b11f  mov     r15, rax
0x18000b122  test    rax, rax
0x18000b125  jnz     short loc_18000B12F
0x18000b127  lea     edi, [rbx-75h]
0x18000b12a  jmp     loc_18000B284
0x18000b12f  mov     rcx, [r14]; this
0x18000b132  call    ?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ; CACSecurityPage::GetCurrentlySelectedAuth(void)
0x18000b137  cmp     dword ptr [rax+4], 8
0x18000b13b  jz      short loc_18000B149
0x18000b13d  cmp     dword ptr [rax+4], 0Bh
0x18000b141  mov     r12d, 80h
0x18000b147  jnz     short loc_18000B14F
0x18000b149  mov     r12d, 2000080h
0x18000b14f  mov     rcx, [r14]
0x18000b152  mov     rdi, [r15+10h]
0x18000b156  mov     ebx, [r15+8]
0x18000b15a  mov     [rbp+var_28], 0
0x18000b162  mov     eax, [rcx+5Ch]
0x18000b165  neg     eax
0x18000b167  mov     [rbp+var_20], 1
0x18000b16b  lea     rax, [rbp+Src]
0x18000b16f  mov     [rbp+var_30], rax
0x18000b173  sbb     esi, esi
0x18000b175  mov     rax, [r15]
0x18000b178  and     esi, 80000h
0x18000b17e  mov     rcx, [rcx+8]; hWnd
0x18000b182  movups  xmm6, xmmword ptr [rax]
0x18000b185  call    cs:__imp_GetParent
0x18000b18b  lea     rcx, [rbp+pEapError]
0x18000b18f  or      esi, r12d
0x18000b192  mov     [rsp+80h+ppEapError], rcx; ppEapError
0x18000b197  lea     r8, [rbp+eapMethodType]; eapMethodType
0x18000b19b  lea     rcx, [rbp+var_28]
0x18000b19f  mov     r9d, ebx; dwSizeOfConfigIn
0x18000b1a2  mov     [rsp+80h+ppConfigOut], rcx; ppConfigOut
0x18000b1a7  mov     edx, esi; dwFlags
0x18000b1a9  lea     rcx, [rbp+arg_10]
0x18000b1ad  mov     [rsp+80h+pdwSizeOfConfigOut], rcx; pdwSizeOfConfigOut
0x18000b1b2  mov     rcx, rax; hwndParent
0x18000b1b5  movdqu  xmmword ptr [rbp+eapMethodType.eapType.type], xmm6
0x18000b1ba  mov     [rsp+80h+pConfigIn], rdi; pConfigIn
0x18000b1bf  call    cs:__imp_EapHostPeerInvokeConfigUI
0x18000b1c5  cmp     [rbp+var_20], 0
0x18000b1c9  mov     edi, eax
0x18000b1cb  jz      short loc_18000B1E6
0x18000b1cd  mov     rdx, [rbp+var_30]
0x18000b1d1  mov     rax, [rbp+var_28]
0x18000b1d5  mov     rcx, [rdx]; pData
0x18000b1d8  mov     [rdx], rax
0x18000b1db  test    rcx, rcx
0x18000b1de  jz      short loc_18000B1E6
0x18000b1e0  call    cs:__imp_EapHostPeerFreeMemory
0x18000b1e6  test    edi, edi
0x18000b1e8  jz      short loc_18000B208
0x18000b1ea  cmp     edi, 4C7h
0x18000b1f0  jz      loc_18000B284
0x18000b1f6  mov     rcx, [r14]; this
0x18000b1f9  mov     r8d, edi; unsigned int
0x18000b1fc  mov     edx, 3AF0h; unsigned int
0x18000b201  call    ?DisplayErrorMessage@CACSecurityPage@@AEAAXKK@Z; CACSecurityPage::DisplayErrorMessage(ulong,ulong)
0x18000b206  jmp     short loc_18000B284
0x18000b208  mov     rbx, [r15+10h]
0x18000b20c  call    cs:__imp_GetProcessHeap
0x18000b212  mov     r8, rbx; lpMem
0x18000b215  xor     edx, edx; dwFlags
0x18000b217  mov     rcx, rax; hHeap
0x18000b21a  call    cs:__imp_HeapFree
0x18000b220  mov     qword ptr [r15+10h], 0
0x18000b228  mov     dword ptr [r15+8], 0
0x18000b230  cmp     [rbp+Src], 0
0x18000b235  jz      short loc_18000B27C
0x18000b237  mov     eax, [rbp+arg_10]
0x18000b23a  test    eax, eax
0x18000b23c  jz      short loc_18000B27C
0x18000b23e  mov     ebx, eax
0x18000b240  call    cs:__imp_GetProcessHeap
0x18000b246  mov     r8d, ebx; dwBytes
0x18000b249  mov     edx, 8; dwFlags
0x18000b24e  mov     rcx, rax; hHeap
0x18000b251  call    cs:__imp_HeapAlloc
0x18000b257  mov     [r15+10h], rax
0x18000b25b  test    rax, rax
0x18000b25e  jnz     short loc_18000B265
0x18000b260  lea     edi, [rax+0Eh]
0x18000b263  jmp     short loc_18000B284
0x18000b265  mov     r8d, [rbp+arg_10]; Size
0x18000b269  mov     rcx, rax; void *
0x18000b26c  mov     rdx, [rbp+Src]; Src
0x18000b270  call    memcpy_0
0x18000b275  mov     eax, [rbp+arg_10]
0x18000b278  mov     [r15+8], eax
0x18000b27c  mov     rcx, [r14]; this
0x18000b27f  call    ?RefreshControls@CACSecurityPage@@AEAA_JXZ; CACSecurityPage::RefreshControls(void)
0x18000b284  mov     rcx, [rbp+pEapError]; pEapError
0x18000b288  test    rcx, rcx
0x18000b28b  jz      short loc_18000B293
0x18000b28d  call    cs:__imp_EapHostPeerFreeErrorMemory
0x18000b293  test    edi, edi
0x18000b295  jle     short loc_18000B2A0
0x18000b297  movzx   edi, di
0x18000b29a  or      edi, 80070000h
0x18000b2a0  mov     ecx, edi; int
0x18000b2a2  call    ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
0x18000b2a7  mov     rcx, [rbp+Src]; pData
0x18000b2ab  mov     rbx, rax
0x18000b2ae  mov     [rbp+Src], 0
0x18000b2b6  test    rcx, rcx
0x18000b2b9  jz      short loc_18000B2C1
0x18000b2bb  call    cs:__imp_EapHostPeerFreeMemory
0x18000b2c1  mov     rax, rbx
0x18000b2c4  jmp     short loc_18000B2C8
0x18000b2c6  xor     eax, eax
0x18000b2c8  movaps  xmm6, [rsp+80h+var_10]
0x18000b2cd  add     rsp, 80h
0x18000b2d4  pop     r15
0x18000b2d6  pop     r14
0x18000b2d8  pop     r12
0x18000b2da  pop     rdi
0x18000b2db  pop     rsi
0x18000b2dc  pop     rbx
0x18000b2dd  pop     rbp
0x18000b2de  retn
```
