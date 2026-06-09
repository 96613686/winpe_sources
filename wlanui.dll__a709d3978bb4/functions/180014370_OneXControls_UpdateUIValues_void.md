# OneXControls::UpdateUIValues(void)

- ea: `0x180014370`
- end: `0x1800145be`
- name: `?UpdateUIValues@OneXControls@@QEAAXXZ`
- size: `590`
- prototype: `void __fastcall(OneXControls *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013570`
- `0x1800136f4`

## callees

- `0x180005e64`
- `0x180005ec0`
- `0x1800060d4`
- `0x18000901c`
- `0x180013e54`
- `0x180014370`
- `0x18001d010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001444e`
- `KERNEL32!HeapAlloc` at `0x18001444e`
- `KERNEL32!GetProcessHeap` at `0x18001443c`
- `KERNEL32!GetProcessHeap` at `0x1800144d3`
- `KERNEL32!GetProcessHeap` at `0x18001454a`
- `KERNEL32!GetProcessHeap` at `0x18001443c`
- `KERNEL32!GetProcessHeap` at `0x1800144d3`
- `KERNEL32!GetProcessHeap` at `0x18001454a`
- `KERNEL32!HeapFree` at `0x1800144e1`
- `KERNEL32!HeapFree` at `0x180014558`
- `KERNEL32!HeapFree` at `0x1800144e1`
- `KERNEL32!HeapFree` at `0x180014558`
- `USER32!CheckDlgButton` at `0x1800143c3`
- `USER32!CheckDlgButton` at `0x1800143dd`
- `USER32!CheckDlgButton` at `0x1800143c3`
- `USER32!CheckDlgButton` at `0x1800143dd`
- `USER32!GetDlgItem` at `0x1800143a5`
- `USER32!GetDlgItem` at `0x1800143a5`

## pseudocode

```c
void __fastcall OneXControls::UpdateUIValues(OneXControls *this)
{
  __int64 v1; // rax
  HWND v3; // rcx
  HWND DlgItem; // rax
  HWND v5; // rcx
  bool v6; // zf
  int v7; // r12d
  __int64 v8; // rax
  LPARAM v9; // rbx
  HANDLE ProcessHeap; // rax
  _OWORD *v11; // rax
  __int64 v12; // rdx
  int v13; // edi
  __int64 v14; // r14
  int v15; // eax
  int v16; // eax
  void *v17; // rdi
  HANDLE v18; // rax
  _DWORD *v19; // rdi
  _BYTE *v20; // rcx
  __int64 v21; // rdx
  void *v22; // rbx
  HANDLE v23; // rax
  CACDot1XPage *v24; // rcx
  _DWORD v25[4]; // [rsp+20h] [rbp-20h]
  __m128i si128; // [rsp+30h] [rbp-10h]
  LPARAM lParam; // [rsp+70h] [rbp+30h] BYREF

  v1 = *((_QWORD *)this + 5);
  v3 = *(HWND *)(v1 + 8);
  *((_QWORD *)this + 1) = v3;
  *((_QWORD *)this + 4) = *(_QWORD *)(v1 + 88);
  DlgItem = GetDlgItem(v3, 16002);
  v5 = (HWND)*((_QWORD *)this + 1);
  v6 = *((_DWORD *)this + 13) == 0;
  *((_QWORD *)this + 2) = DlgItem;
  CheckDlgButton(v5, 16001, !v6);
  CheckDlgButton(*((HWND *)this + 1), 16028, *((_DWORD *)this + 27) != 0);
  v7 = *((_DWORD *)this + 14);
  *((_DWORD *)this + 28) = *((_DWORD *)this + 27);
  v8 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v6 = *((_QWORD *)this + 3) == 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v9 = v8 + 24;
  v25[0] = 17316;
  lParam = v8 + 24;
  v25[1] = 17317;
  v25[2] = 17315;
  v25[3] = 17318;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    v11 = HeapAlloc(ProcessHeap, 8u, 0x10u);
    *((_QWORD *)this + 3) = v11;
    if ( !v11 )
      goto LABEL_11;
    v12 = 0;
    *v11 = 0;
    do
    {
      *(_DWORD *)(*((_QWORD *)this + 3) + 4 * v12) = si128.m128i_i32[v12];
      ++v12;
    }
    while ( v12 != 4 );
  }
  v13 = 0;
  v14 = 0;
  while ( 1 )
  {
    v15 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
            &lParam,
            (unsigned int)v25[v14]);
    v9 = lParam;
    if ( !v15 )
      break;
    v16 = ComboBox_AddItem(*((HWND *)this + 2), lParam, *((_QWORD *)this + 3) + 4 * v14);
    if ( v7 == si128.m128i_i32[v14] )
      v13 = v16;
    v14 = (unsigned int)(v14 + 1);
    if ( (unsigned int)v14 >= 4 )
    {
      ComboBox_SetCurSelNotify(*((HWND *)this + 2), v13);
      ComboBox_AutoSizeDroppedWidth(*((HWND *)this + 2));
      goto LABEL_12;
    }
  }
LABEL_11:
  v17 = (void *)*((_QWORD *)this + 3);
  v18 = GetProcessHeap();
  HeapFree(v18, 0, v17);
  *((_QWORD *)this + 3) = 0;
LABEL_12:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v9 - 24) + 8LL))(*(_QWORD *)(v9 - 24));
  v19 = (_DWORD *)((char *)this + 60);
  v20 = (_BYTE *)*((_QWORD *)this + 12);
  *((_DWORD *)this + 15) = *((_DWORD *)this + 13);
  *((_DWORD *)this + 16) = *((_DWORD *)this + 14);
  if ( v20 )
  {
    v21 = ((2580 * *((_DWORD *)this + 23)) & 0xFFFFFFF0) + 16;
    if ( ((2580 * *((_DWORD *)this + 23)) & 0xFFFFFFF0) != 0xFFFFFFF0 )
    {
      do
      {
        *v20++ = 0;
        --v21;
      }
      while ( v21 );
      v19 = (_DWORD *)((char *)this + 60);
    }
    v22 = (void *)*((_QWORD *)this + 12);
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v22);
    *((_QWORD *)this + 12) = 0;
  }
  v6 = *v19 == 0;
  *((_DWORD *)this + 23) = 0;
  *(_DWORD *)(*((_QWORD *)this + 5) + 60LL) = v6 || ((*((_DWORD *)this + 16) - 1) & 0xFFFFFFFD) != 0;
  v24 = (CACDot1XPage *)*((_QWORD *)this + 5);
  *((_DWORD *)this + 26) = 0;
  CACDot1XPage::RefreshControls(v24);
}

```

## disassembly

```asm
0x180014370  mov     [rsp-28h+arg_8], rbx
0x180014375  mov     [rsp-28h+arg_10], rsi
0x18001437a  push    rbp
0x18001437b  push    rdi
0x18001437c  push    r12
0x18001437e  push    r14
0x180014380  push    r15
0x180014382  mov     rbp, rsp
0x180014385  sub     rsp, 40h
0x180014389  mov     rax, [rcx+28h]
0x18001438d  mov     rsi, rcx
0x180014390  mov     edx, 3E82h; nIDDlgItem
0x180014395  mov     rcx, [rax+8]; hDlg
0x180014399  mov     [rsi+8], rcx
0x18001439d  mov     rax, [rax+58h]
0x1800143a1  mov     [rsi+20h], rax
0x1800143a5  call    cs:__imp_GetDlgItem
0x1800143ab  mov     rcx, [rsi+8]; hDlg
0x1800143af  xor     r8d, r8d
0x1800143b2  cmp     [rsi+34h], r8d
0x1800143b6  mov     edx, 3E81h; nIDButton
0x1800143bb  mov     [rsi+10h], rax
0x1800143bf  setnz   r8b; uCheck
0x1800143c3  call    cs:__imp_CheckDlgButton
0x1800143c9  mov     rcx, [rsi+8]; hDlg
0x1800143cd  xor     r8d, r8d
0x1800143d0  cmp     [rsi+6Ch], r8d
0x1800143d4  mov     edx, 3E9Ch; nIDButton
0x1800143d9  setnz   r8b; uCheck
0x1800143dd  call    cs:__imp_CheckDlgButton
0x1800143e3  mov     eax, [rsi+6Ch]
0x1800143e6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800143ed  mov     r12d, [rsi+38h]
0x1800143f1  mov     [rsi+70h], eax
0x1800143f4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800143fb  mov     rax, [rax+18h]
0x1800143ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014404  cmp     qword ptr [rsi+18h], 0
0x180014409  movdqa  xmm0, cs:__xmm@00000003000000020000000100000000
0x180014411  movdqu  [rbp+var_10], xmm0
0x180014416  lea     rbx, [rax+18h]
0x18001441a  mov     [rbp+var_20], 43A4h
0x180014421  mov     [rbp+lParam], rbx
0x180014425  mov     [rbp+var_1C], 43A5h
0x18001442c  mov     [rbp+var_18], 43A3h
0x180014433  mov     [rbp+var_14], 43A6h
0x18001443a  jnz     short loc_180014479
0x18001443c  call    cs:__imp_GetProcessHeap
0x180014442  mov     edx, 8; dwFlags
0x180014447  mov     rcx, rax; hHeap
0x18001444a  lea     r8d, [rdx+8]; dwBytes
0x18001444e  call    cs:__imp_HeapAlloc
0x180014454  mov     [rsi+18h], rax
0x180014458  test    rax, rax
0x18001445b  jz      short loc_1800144CF
0x18001445d  xorps   xmm0, xmm0
0x180014460  xor     edx, edx
0x180014462  movups  xmmword ptr [rax], xmm0
0x180014465  mov     eax, dword ptr [rbp+rdx*4+var_10]
0x180014469  mov     rcx, [rsi+18h]
0x18001446d  mov     [rcx+rdx*4], eax
0x180014470  inc     rdx
0x180014473  cmp     rdx, 4
0x180014477  jnz     short loc_180014465
0x180014479  xor     edi, edi
0x18001447b  xor     r14d, r14d
0x18001447e  mov     edx, [rbp+r14*4+var_20]
0x180014483  lea     rcx, [rbp+lParam]
0x180014487  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18001448c  mov     rbx, [rbp+lParam]
0x180014490  test    eax, eax
0x180014492  jz      short loc_1800144CF
0x180014494  mov     rax, [rsi+18h]
0x180014498  mov     rdx, rbx; lParam
0x18001449b  mov     rcx, [rsi+10h]; hWnd
0x18001449f  lea     r8, [rax+r14*4]; LPARAM
0x1800144a3  call    ?ComboBox_AddItem@@YAHPEAUHWND__@@PEBGPEAX@Z; ComboBox_AddItem(HWND__ *,ushort const *,void *)
0x1800144a8  cmp     r12d, dword ptr [rbp+r14*4+var_10]
0x1800144ad  cmovz   edi, eax
0x1800144b0  inc     r14d
0x1800144b3  cmp     r14d, 4
0x1800144b7  jb      short loc_18001447E
0x1800144b9  mov     rcx, [rsi+10h]; hWnd
0x1800144bd  mov     edx, edi; int
0x1800144bf  call    ?ComboBox_SetCurSelNotify@@YAXPEAUHWND__@@H@Z; ComboBox_SetCurSelNotify(HWND__ *,int)
0x1800144c4  mov     rcx, [rsi+10h]; hWnd
0x1800144c8  call    ?ComboBox_AutoSizeDroppedWidth@@YAXPEAUHWND__@@@Z; ComboBox_AutoSizeDroppedWidth(HWND__ *)
0x1800144cd  jmp     short loc_1800144EF
0x1800144cf  mov     rdi, [rsi+18h]
0x1800144d3  call    cs:__imp_GetProcessHeap
0x1800144d9  mov     r8, rdi; lpMem
0x1800144dc  xor     edx, edx; dwFlags
0x1800144de  mov     rcx, rax; hHeap
0x1800144e1  call    cs:__imp_HeapFree
0x1800144e7  mov     qword ptr [rsi+18h], 0
0x1800144ef  lea     rdx, [rbx-18h]
0x1800144f3  or      eax, 0FFFFFFFFh
0x1800144f6  lock xadd [rdx+10h], eax
0x1800144fb  sub     eax, 1
0x1800144fe  jg      short loc_18001450F
0x180014500  mov     rcx, [rdx]
0x180014503  mov     rax, [rcx]
0x180014506  mov     rax, [rax+8]
0x18001450a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001450f  mov     eax, [rsi+34h]
0x180014512  lea     rdi, [rsi+3Ch]
0x180014516  mov     rcx, [rsi+60h]
0x18001451a  mov     [rdi], eax
0x18001451c  mov     eax, [rsi+38h]
0x18001451f  mov     [rsi+40h], eax
0x180014522  test    rcx, rcx
0x180014525  jz      short loc_180014566
0x180014527  imul    edx, [rsi+5Ch], 0A14h
0x18001452e  and     edx, 0FFFFFFF0h
0x180014531  add     edx, 10h
0x180014534  jz      short loc_180014546
0x180014536  mov     byte ptr [rcx], 0
0x180014539  inc     rcx
0x18001453c  sub     rdx, 1
0x180014540  jnz     short loc_180014536
0x180014542  lea     rdi, [rsi+3Ch]
0x180014546  mov     rbx, [rsi+60h]
0x18001454a  call    cs:__imp_GetProcessHeap
0x180014550  mov     r8, rbx; lpMem
0x180014553  xor     edx, edx; dwFlags
0x180014555  mov     rcx, rax; hHeap
0x180014558  call    cs:__imp_HeapFree
0x18001455e  mov     qword ptr [rsi+60h], 0
0x180014566  cmp     dword ptr [rdi], 0
0x180014569  mov     dword ptr [rsi+5Ch], 0
0x180014570  jz      short loc_18001458B
0x180014572  mov     eax, [rsi+40h]
0x180014575  dec     eax
0x180014577  test    eax, 0FFFFFFFDh
0x18001457c  jnz     short loc_18001458B
0x18001457e  mov     rax, [rsi+28h]
0x180014582  mov     dword ptr [rax+3Ch], 0
0x180014589  jmp     short loc_180014596
0x18001458b  mov     rax, [rsi+28h]
0x18001458f  mov     dword ptr [rax+3Ch], 1
0x180014596  mov     rcx, [rsi+28h]; this
0x18001459a  mov     dword ptr [rsi+68h], 0
0x1800145a1  lea     r11, [rsp+40h+var_s0]
0x1800145a6  mov     rbx, [r11+38h]
0x1800145aa  mov     rsi, [r11+40h]
0x1800145ae  mov     rsp, r11
0x1800145b1  pop     r15
0x1800145b3  pop     r14
0x1800145b5  pop     r12
0x1800145b7  pop     rdi
0x1800145b8  pop     rbp
0x1800145b9  jmp     ?RefreshControls@CACDot1XPage@@QEAA_JXZ; CACDot1XPage::RefreshControls(void)
```
