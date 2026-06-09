# CWcnDeviceListView::OnUpdate(tagQueryUpdateAction,unsigned __int64,IFunctionInstance *)

- ea: `0x18001c580`
- end: `0x18001c8e8`
- name: `?OnUpdate@CWcnDeviceListView@@UEAAJW4tagQueryUpdateAction@@_KPEAUIFunctionInstance@@@Z`
- size: `872`
- prototype: `__int64 __fastcall(CWcnDeviceListView *__hidden this, enum tagQueryUpdateAction, unsigned __int64, struct IFunctionInstance *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update`

## callees

- `0x180001870`
- `0x180002294`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18001ad04`
- `0x18001af24`
- `0x18001be00`
- `0x18001bfa8`
- `0x18001c580`
- `0x18001c968`
- `0x18001cb98`
- `0x18001cd24`
- `0x18002de1c`

## import_xrefs

- `USER32!SendMessageW` at `0x18001c6b8`
- `USER32!SendMessageW` at `0x18001c722`
- `USER32!SendMessageW` at `0x18001c768`
- `USER32!SendMessageW` at `0x18001c7ae`
- `USER32!SendMessageW` at `0x18001c823`
- `USER32!SendMessageW` at `0x18001c85f`
- `USER32!SendMessageW` at `0x18001c6b8`
- `USER32!SendMessageW` at `0x18001c722`
- `USER32!SendMessageW` at `0x18001c768`
- `USER32!SendMessageW` at `0x18001c7ae`
- `USER32!SendMessageW` at `0x18001c823`
- `USER32!SendMessageW` at `0x18001c85f`

## pseudocode

```c
__int64 __fastcall CWcnDeviceListView::OnUpdate(HWND *this, int a2, __int64 a3, struct IFunctionInstance *a4)
{
  _QWORD *v7; // r10
  const char *Indent; // rax
  __int64 v9; // r10
  int v11; // ebx
  CWcnwizDevice *v12; // rax
  struct IFunctionInstance *v13; // rdx
  GUID *v14; // rcx
  int v15; // eax
  __int64 *v16; // rdx
  _BYTE *v17; // r10
  int v18; // r13d
  int i; // r15d
  struct CWcnwizDevice *Item; // rax
  __int64 v21; // rcx
  CWcnDeviceListView *v22; // rcx
  CWcnwizDevice *v23; // rdi
  CWcnDeviceListView *v24; // rcx
  unsigned int v25; // edx
  const char *v26; // rax
  __int64 v27; // r10
  unsigned int v28; // eax
  __int64 v29; // r10
  __int64 v30; // rax
  __int64 v31; // [rsp+0h] [rbp-C8h] BYREF
  CWcnwizDevice *v32; // [rsp+30h] [rbp-98h]
  std::bad_alloc *v33; // [rsp+38h] [rbp-90h] BYREF
  struct tagLVITEMW lParam; // [rsp+40h] [rbp-88h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v9 + 16), 10, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids, Indent);
    v7 = WPP_GLOBAL_Control;
  }
  if ( a4 )
  {
    v32 = 0;
    if ( a2 == 1 )
    {
      v11 = 0;
      CWcnDeviceListView::RemoveDevice(this, a4);
LABEL_41:
      v17 = WPP_GLOBAL_Control;
      goto LABEL_42;
    }
    try
    {
      v12 = (CWcnwizDevice *)operator new(0x70u);
      v23 = CWcnwizDevice::CWcnwizDevice(v12);
      v32 = v23;
      v13 = a4;
      v14 = (GUID *)v23;
    }
    catch ( std::bad_alloc *v33 )
    {
      v16 = &v31;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v33 + 8LL))(v33);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids, v30);
      }
      v11 = -2147024882;
      v23 = v32;
      goto LABEL_38;
    }
    v15 = CWcnwizDevice::PopulateFromFunctionInstance(v14, v13);
    v11 = v15;
    if ( v15 >= 0 )
    {
      if ( v15 != 1 )
      {
        v18 = SendMessageW(this[2], 0x1004u, 0, 0);
        for ( i = 0; i < v18; ++i )
        {
          Item = CWcnDeviceListView::GetItem((CWcnDeviceListView *)this, i);
          if ( Item )
          {
            v21 = *(_QWORD *)Item - *(_QWORD *)v23;
            if ( *(_QWORD *)Item == *(_QWORD *)v23 )
              v21 = *((_QWORD *)Item + 1) - *((_QWORD *)v23 + 1);
            if ( !v21 )
            {
              if ( a2 )
              {
                if ( a2 != 2 )
                  break;
              }
              else
              {
                a2 = 2;
              }
              memset_0(&lParam, 0, sizeof(lParam));
              CWcnDeviceListView::UpdateListViewItem(v22, &lParam, v23);
              v23 = 0;
              lParam.iItem = i;
              SendMessageW(this[2], 0x104Cu, 0, (LPARAM)&lParam);
              CWcnDeviceListView::RecalculateSubtitles((CWcnDeviceListView *)this);
              break;
            }
          }
        }
        if ( !a2 )
        {
          memset_0(&lParam, 0, sizeof(lParam));
          CWcnDeviceListView::UpdateListViewItem(v24, &lParam, v23);
          if ( (unsigned int)SendMessageW(this[2], 0x104Du, 0, (LPARAM)&lParam) == -1 )
          {
            if ( v23 )
              CWcnwizDevice::`scalar deleting destructor'(v23, v25);
            v11 = -2147024882;
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              return (unsigned int)v11;
            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v26 = GetIndent(0);
              WPP_SF_s(*(_QWORD *)(v27 + 16), 14, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids, v26);
              goto LABEL_41;
            }
LABEL_42:
            if ( v17 != (_BYTE *)&WPP_GLOBAL_Control && (v11 < 0 || v17[25] >= 6u) )
            {
              v28 = (unsigned int)GetIndent(-1);
              WPP_SF_sd(
                *(_QWORD *)(v29 + 16),
                15,
                (unsigned int)WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids,
                v28,
                v11);
            }
            return (unsigned int)v11;
          }
          v23 = 0;
          CWcnDeviceListView::RecalculateSubtitles((CWcnDeviceListView *)this);
        }
        if ( (unsigned int)SendMessageW(this[2], 0x1004u, 0, 0) == 1 )
        {
          memset_0(&lParam, 0, sizeof(lParam));
          lParam.stateMask = 2;
          lParam.state = 2;
          SendMessageW(this[2], 0x102Bu, 0, (LPARAM)&lParam);
        }
      }
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_39:
        if ( v23 )
        {
          CWcnwizDevice::`scalar deleting destructor'(v23, (unsigned int)v16);
          goto LABEL_41;
        }
        goto LABEL_42;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids,
        (unsigned int)v15);
    }
LABEL_38:
    v17 = WPP_GLOBAL_Control;
    goto LABEL_39;
  }
  if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 2u )
    WPP_SF_s(v7[2], 11, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids, "pIFunctionInstance");
  return 2147500035LL;
}

```

## disassembly

```asm
0x18001c580  mov     [rsp+arg_0], rbx
0x18001c585  mov     [rsp+arg_8], rsi
0x18001c58a  push    rdi
0x18001c58b  push    r12
0x18001c58d  push    r13
0x18001c58f  push    r14
0x18001c591  push    r15
0x18001c593  sub     rsp, 0A0h
0x18001c59a  mov     r15, r9
0x18001c59d  mov     r12d, edx
0x18001c5a0  mov     rsi, rcx
0x18001c5a3  lea     r14, WPP_GLOBAL_Control
0x18001c5aa  mov     r10, cs:WPP_GLOBAL_Control
0x18001c5b1  cmp     r10, r14
0x18001c5b4  jz      short loc_18001C5E6
0x18001c5b6  cmp     byte ptr [r10+19h], 6
0x18001c5bb  jb      short loc_18001C5E6
0x18001c5bd  mov     ecx, 1; int
0x18001c5c2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001c5c7  mov     edx, 0Ah
0x18001c5cc  mov     r9, rax
0x18001c5cf  lea     r8, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids
0x18001c5d6  mov     rcx, [r10+10h]
0x18001c5da  call    WPP_SF_s
0x18001c5df  mov     r10, cs:WPP_GLOBAL_Control
0x18001c5e6  test    r15, r15
0x18001c5e9  jnz     short loc_18001C61C
0x18001c5eb  cmp     r10, r14
0x18001c5ee  jz      short loc_18001C612
0x18001c5f0  cmp     byte ptr [r10+19h], 2
0x18001c5f5  jb      short loc_18001C612
0x18001c5f7  lea     edx, [r15+0Bh]
0x18001c5fb  lea     r9, aPifunctioninst; "pIFunctionInstance"
0x18001c602  lea     r8, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids
0x18001c609  mov     rcx, [r10+10h]
0x18001c60d  call    WPP_SF_s
0x18001c612  mov     eax, 80004003h
0x18001c617  jmp     loc_18001C8CB
0x18001c61c  mov     [rsp+0C8h+var_98], 0
0x18001c625  cmp     r12d, 1
0x18001c629  jnz     short loc_18001C63D
0x18001c62b  xor     ebx, ebx
0x18001c62d  mov     rdx, r15; struct IFunctionInstance *
0x18001c630  mov     rcx, rsi; this
0x18001c633  call    ?RemoveDevice@CWcnDeviceListView@@AEAAXPEAUIFunctionInstance@@@Z; CWcnDeviceListView::RemoveDevice(IFunctionInstance *)
0x18001c638  jmp     loc_18001C88E
0x18001c63d  mov     ecx, 70h ; 'p'; Size
0x18001c642  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c647  mov     rcx, rax; this
0x18001c64a  call    ??0CWcnwizDevice@@QEAA@XZ; CWcnwizDevice::CWcnwizDevice(void)
0x18001c64f  mov     rdi, rax
0x18001c652  mov     [rsp+0C8h+var_98], rax
0x18001c657  mov     rdx, r15; struct IFunctionInstance *
0x18001c65a  mov     rcx, rdi; this
0x18001c65d  call    ?PopulateFromFunctionInstance@CWcnwizDevice@@QEAAJPEAUIFunctionInstance@@@Z; CWcnwizDevice::PopulateFromFunctionInstance(IFunctionInstance *)
0x18001c662  mov     ebx, eax
0x18001c664  test    eax, eax
0x18001c666  jns     short loc_18001C6A0
0x18001c668  mov     r10, cs:WPP_GLOBAL_Control
0x18001c66f  cmp     r10, r14
0x18001c672  jz      loc_18001C881
0x18001c678  cmp     byte ptr [r10+19h], 2
0x18001c67d  jb      loc_18001C881
0x18001c683  mov     edx, 0Dh
0x18001c688  mov     r9d, eax
0x18001c68b  lea     r8, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids
0x18001c692  mov     rcx, [r10+10h]
0x18001c696  call    WPP_SF_d
0x18001c69b  jmp     loc_18001C87A
0x18001c6a0  cmp     eax, 1
0x18001c6a3  jz      loc_18001C87A
0x18001c6a9  xor     r9d, r9d; lParam
0x18001c6ac  xor     r8d, r8d; wParam
0x18001c6af  mov     edx, 1004h; Msg
0x18001c6b4  mov     rcx, [rsi+10h]; hWnd
0x18001c6b8  call    cs:__imp_SendMessageW
0x18001c6be  mov     r13, rax
0x18001c6c1  xor     r15d, r15d
0x18001c6c4  cmp     r15d, r13d
0x18001c6c7  jge     loc_18001C776
0x18001c6cd  mov     edx, r15d; int
0x18001c6d0  mov     rcx, rsi; this
0x18001c6d3  call    ?GetItem@CWcnDeviceListView@@AEAAPEAVCWcnwizDevice@@H@Z; CWcnDeviceListView::GetItem(int)
0x18001c6d8  test    rax, rax
0x18001c6db  jz      short loc_18001C6F2
0x18001c6dd  mov     rcx, [rax]
0x18001c6e0  sub     rcx, [rdi]
0x18001c6e3  jnz     short loc_18001C6ED
0x18001c6e5  mov     rcx, [rax+8]
0x18001c6e9  sub     rcx, [rdi+8]
0x18001c6ed  test    rcx, rcx
0x18001c6f0  jz      short loc_18001C6F7
0x18001c6f2  inc     r15d
0x18001c6f5  jmp     short loc_18001C6C4
0x18001c6f7  mov     ecx, r12d
0x18001c6fa  test    r12d, r12d
0x18001c6fd  jz      short loc_18001C72D
0x18001c6ff  sub     ecx, 1
0x18001c702  jz      short loc_18001C70B
0x18001c704  cmp     ecx, 1
0x18001c707  jnz     short loc_18001C776
0x18001c709  jmp     short loc_18001C733
0x18001c70b  mov     rcx, rax; this
0x18001c70e  call    ??_GCWcnwizDevice@@QEAAPEAXI@Z; CWcnwizDevice::`scalar deleting destructor'(uint)
0x18001c713  movsxd  r8, r15d; wParam
0x18001c716  xor     r9d, r9d; lParam
0x18001c719  mov     edx, 1008h; Msg
0x18001c71e  mov     rcx, [rsi+10h]; hWnd
0x18001c722  call    cs:__imp_SendMessageW
0x18001c728  jmp     loc_18001C814
0x18001c72d  mov     r12d, 2
0x18001c733  xor     edx, edx; Val
0x18001c735  lea     r8d, [rdx+58h]; Size
0x18001c739  lea     rcx, [rsp+0C8h+lParam]; void *
0x18001c73e  call    memset_0
0x18001c743  mov     r8, rdi; struct CWcnwizDevice *
0x18001c746  lea     rdx, [rsp+0C8h+lParam]; struct tagLVITEMW *
0x18001c74b  call    ?UpdateListViewItem@CWcnDeviceListView@@AEAAXPEAUtagLVITEMW@@PEAVCWcnwizDevice@@@Z; CWcnDeviceListView::UpdateListViewItem(tagLVITEMW *,CWcnwizDevice *)
0x18001c750  xor     edi, edi
0x18001c752  mov     dword ptr [rsp+0C8h+lParam+4], r15d
0x18001c757  lea     r9, [rsp+0C8h+lParam]; lParam
0x18001c75c  xor     r8d, r8d; wParam
0x18001c75f  mov     edx, 104Ch; Msg
0x18001c764  mov     rcx, [rsi+10h]; hWnd
0x18001c768  call    cs:__imp_SendMessageW
0x18001c76e  mov     rcx, rsi; this
0x18001c771  call    ?RecalculateSubtitles@CWcnDeviceListView@@AEAAXXZ; CWcnDeviceListView::RecalculateSubtitles(void)
0x18001c776  test    r12d, r12d
0x18001c779  jnz     loc_18001C814
0x18001c77f  xor     edx, edx; Val
0x18001c781  lea     r8d, [r12+58h]; Size
0x18001c786  lea     rcx, [rsp+0C8h+lParam]; void *
0x18001c78b  call    memset_0
0x18001c790  mov     r8, rdi; struct CWcnwizDevice *
0x18001c793  lea     rdx, [rsp+0C8h+lParam]; struct tagLVITEMW *
0x18001c798  call    ?UpdateListViewItem@CWcnDeviceListView@@AEAAXPEAUtagLVITEMW@@PEAVCWcnwizDevice@@@Z; CWcnDeviceListView::UpdateListViewItem(tagLVITEMW *,CWcnwizDevice *)
0x18001c79d  lea     r9, [rsp+0C8h+lParam]; lParam
0x18001c7a2  xor     r8d, r8d; wParam
0x18001c7a5  mov     edx, 104Dh; Msg
0x18001c7aa  mov     rcx, [rsi+10h]; hWnd
0x18001c7ae  call    cs:__imp_SendMessageW
0x18001c7b4  cmp     eax, 0FFFFFFFFh
0x18001c7b7  jnz     short loc_18001C80A
0x18001c7b9  test    rdi, rdi
0x18001c7bc  jz      short loc_18001C7C6
0x18001c7be  mov     rcx, rdi; this
0x18001c7c1  call    ??_GCWcnwizDevice@@QEAAPEAXI@Z; CWcnwizDevice::`scalar deleting destructor'(uint)
0x18001c7c6  mov     ebx, 8007000Eh
0x18001c7cb  mov     r10, cs:WPP_GLOBAL_Control
0x18001c7d2  cmp     r10, r14
0x18001c7d5  jz      loc_18001C8C9
0x18001c7db  cmp     byte ptr [r10+19h], 2
0x18001c7e0  jb      loc_18001C895
0x18001c7e6  xor     ecx, ecx; int
0x18001c7e8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001c7ed  mov     edx, 0Eh
0x18001c7f2  mov     r9, rax
0x18001c7f5  lea     r8, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids
0x18001c7fc  mov     rcx, [r10+10h]
0x18001c800  call    WPP_SF_s
0x18001c805  jmp     loc_18001C88E
0x18001c80a  xor     edi, edi
0x18001c80c  mov     rcx, rsi; this
0x18001c80f  call    ?RecalculateSubtitles@CWcnDeviceListView@@AEAAXXZ; CWcnDeviceListView::RecalculateSubtitles(void)
0x18001c814  xor     r9d, r9d; lParam
0x18001c817  xor     r8d, r8d; wParam
0x18001c81a  mov     edx, 1004h; Msg
0x18001c81f  mov     rcx, [rsi+10h]; hWnd
0x18001c823  call    cs:__imp_SendMessageW
0x18001c829  cmp     eax, 1
0x18001c82c  jnz     short loc_18001C87A
0x18001c82e  xor     edx, edx; Val
0x18001c830  lea     r8d, [rax+57h]; Size
0x18001c834  lea     rcx, [rsp+0C8h+lParam]; void *
0x18001c839  call    memset_0
0x18001c83e  mov     [rsp+0C8h+var_78], 2
0x18001c846  mov     [rsp+0C8h+var_7C], 2
0x18001c84e  lea     r9, [rsp+0C8h+lParam]; lParam
0x18001c853  xor     r8d, r8d; wParam
0x18001c856  mov     edx, 102Bh; Msg
0x18001c85b  mov     rcx, [rsi+10h]; hWnd
0x18001c85f  call    cs:__imp_SendMessageW
0x18001c865  jmp     short loc_18001C87A
0x18001c867  lea     r14, WPP_GLOBAL_Control
0x18001c86e  mov     ebx, [rsp+0C8h+arg_18]
0x18001c875  mov     rdi, [rsp+0C8h+var_98]
0x18001c87a  mov     r10, cs:WPP_GLOBAL_Control
0x18001c881  test    rdi, rdi
0x18001c884  jz      short loc_18001C895
0x18001c886  mov     rcx, rdi; this
0x18001c889  call    ??_GCWcnwizDevice@@QEAAPEAXI@Z; CWcnwizDevice::`scalar deleting destructor'(uint)
0x18001c88e  mov     r10, cs:WPP_GLOBAL_Control
0x18001c895  cmp     r10, r14
0x18001c898  jz      short loc_18001C8C9
0x18001c89a  test    ebx, ebx
0x18001c89c  js      short loc_18001C8A5
0x18001c89e  cmp     byte ptr [r10+19h], 6
0x18001c8a3  jb      short loc_18001C8C9
0x18001c8a5  or      ecx, 0FFFFFFFFh; int
0x18001c8a8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001c8ad  mov     edx, 0Fh
0x18001c8b2  mov     [rsp+0C8h+var_A8], ebx
0x18001c8b6  mov     r9, rax
0x18001c8b9  lea     r8, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids
0x18001c8c0  mov     rcx, [r10+10h]
0x18001c8c4  call    WPP_SF_sd
0x18001c8c9  mov     eax, ebx
0x18001c8cb  lea     r11, [rsp+0C8h+var_28]
0x18001c8d3  mov     rbx, [r11+30h]
0x18001c8d7  mov     rsi, [r11+38h]
0x18001c8db  mov     rsp, r11
0x18001c8de  pop     r15
0x18001c8e0  pop     r14
0x18001c8e2  pop     r13
0x18001c8e4  pop     r12
0x18001c8e6  pop     rdi
0x18001c8e7  retn
```
