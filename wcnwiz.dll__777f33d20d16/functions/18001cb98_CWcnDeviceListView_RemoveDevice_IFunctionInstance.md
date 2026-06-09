# CWcnDeviceListView::RemoveDevice(IFunctionInstance *)

- ea: `0x18001cb98`
- end: `0x18001cca0`
- name: `?RemoveDevice@CWcnDeviceListView@@AEAAXPEAUIFunctionInstance@@@Z`
- size: `264`
- prototype: `void __fastcall(CWcnDeviceListView *__hidden this, struct IFunctionInstance *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c580`

## callees

- `0x18000e19c`
- `0x18001b3b0`
- `0x18001bd48`
- `0x18001be00`
- `0x18001bfa8`
- `0x18001c968`
- `0x18001cb98`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cc91`
- `USER32!SendMessageW` at `0x18001cc12`
- `USER32!SendMessageW` at `0x18001cc71`
- `USER32!SendMessageW` at `0x18001cc12`
- `USER32!SendMessageW` at `0x18001cc71`

## pseudocode

```c
void __fastcall CWcnDeviceListView::RemoveDevice(HWND *this, struct IFunctionInstance *a2)
{
  struct IFunctionInstanceVtbl *lpVtbl; // rax
  int v4; // eax
  int v5; // ebp
  int i; // ebx
  struct CWcnwizDevice *Item; // rdi
  __int64 v8; // rax
  __int64 v9; // r8
  _QWORD *v10; // rcx
  unsigned int v11; // edx
  LPVOID pv; // [rsp+58h] [rbp+10h] BYREF

  lpVtbl = a2->lpVtbl;
  pv = 0;
  v4 = ((__int64 (__fastcall *)(struct IFunctionInstance *, LPVOID *))lpVtbl->GetID)(a2, &pv);
  if ( v4 >= 0 )
  {
    v5 = SendMessageW(this[2], 0x1004u, 0, 0);
    for ( i = 0; i < v5; ++i )
    {
      Item = CWcnDeviceListView::GetItem((CWcnDeviceListView *)this, i);
      if ( Item )
      {
        v8 = std::_WChar_traits<unsigned short>::length(pv);
        v10 = (_QWORD *)((char *)Item + 16);
        if ( *((_QWORD *)Item + 5) > 7u )
          v10 = (_QWORD *)*v10;
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v10, *((_QWORD *)Item + 4), v9, v8) )
        {
          SendMessageW(this[2], 0x1008u, i, 0);
          CWcnwizDevice::`scalar deleting destructor'(Item, v11);
          break;
        }
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids, (unsigned int)v4);
  }
  CWcnDeviceListView::RecalculateSubtitles((CWcnDeviceListView *)this);
  if ( pv )
    CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x18001cb98  push    rbx
0x18001cb9a  push    rbp
0x18001cb9b  push    rsi
0x18001cb9c  push    rdi
0x18001cb9d  sub     rsp, 28h
0x18001cba1  mov     rax, [rdx]
0x18001cba4  mov     r8, rdx
0x18001cba7  mov     rsi, rcx
0x18001cbaa  mov     [rsp+48h+pv], 0
0x18001cbb3  lea     rdx, [rsp+48h+pv]
0x18001cbb8  mov     rcx, r8
0x18001cbbb  mov     rax, [rax+20h]
0x18001cbbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbc4  test    eax, eax
0x18001cbc6  jns     short loc_18001CC03
0x18001cbc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbcf  lea     rdx, WPP_GLOBAL_Control
0x18001cbd6  cmp     rcx, rdx
0x18001cbd9  jz      loc_18001CC7F
0x18001cbdf  cmp     byte ptr [rcx+19h], 2
0x18001cbe3  jb      loc_18001CC7F
0x18001cbe9  mov     rcx, [rcx+10h]
0x18001cbed  lea     r8, WPP_ff656d6b686334ea73da68649ad2b7cf_Traceguids
0x18001cbf4  mov     edx, 21h ; '!'
0x18001cbf9  mov     r9d, eax
0x18001cbfc  call    WPP_SF_d
0x18001cc01  jmp     short loc_18001CC7F
0x18001cc03  mov     rcx, [rsi+10h]; hWnd
0x18001cc07  xor     r9d, r9d; lParam
0x18001cc0a  xor     r8d, r8d; wParam
0x18001cc0d  mov     edx, 1004h; Msg
0x18001cc12  call    cs:__imp_SendMessageW
0x18001cc18  mov     rbp, rax
0x18001cc1b  xor     ebx, ebx
0x18001cc1d  cmp     ebx, ebp
0x18001cc1f  jge     short loc_18001CC7F
0x18001cc21  mov     edx, ebx; int
0x18001cc23  mov     rcx, rsi; this
0x18001cc26  call    ?GetItem@CWcnDeviceListView@@AEAAPEAVCWcnwizDevice@@H@Z; CWcnDeviceListView::GetItem(int)
0x18001cc2b  mov     rdi, rax
0x18001cc2e  test    rax, rax
0x18001cc31  jz      short loc_18001CC5E
0x18001cc33  mov     r8, [rsp+48h+pv]
0x18001cc38  mov     rcx, r8
0x18001cc3b  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001cc40  cmp     qword ptr [rdi+28h], 7
0x18001cc45  lea     rcx, [rdi+10h]
0x18001cc49  jbe     short loc_18001CC4E
0x18001cc4b  mov     rcx, [rcx]
0x18001cc4e  mov     rdx, [rdi+20h]
0x18001cc52  mov     r9, rax
0x18001cc55  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001cc5a  test    al, al
0x18001cc5c  jnz     short loc_18001CC62
0x18001cc5e  inc     ebx
0x18001cc60  jmp     short loc_18001CC1D
0x18001cc62  mov     rcx, [rsi+10h]; hWnd
0x18001cc66  xor     r9d, r9d; lParam
0x18001cc69  movsxd  r8, ebx; wParam
0x18001cc6c  mov     edx, 1008h; Msg
0x18001cc71  call    cs:__imp_SendMessageW
0x18001cc77  mov     rcx, rdi; this
0x18001cc7a  call    ??_GCWcnwizDevice@@QEAAPEAXI@Z; CWcnwizDevice::`scalar deleting destructor'(uint)
0x18001cc7f  mov     rcx, rsi; this
0x18001cc82  call    ?RecalculateSubtitles@CWcnDeviceListView@@AEAAXXZ; CWcnDeviceListView::RecalculateSubtitles(void)
0x18001cc87  mov     rcx, [rsp+48h+pv]; pv
0x18001cc8c  test    rcx, rcx
0x18001cc8f  jz      short loc_18001CC97
0x18001cc91  call    cs:__imp_CoTaskMemFree
0x18001cc97  add     rsp, 28h
0x18001cc9b  pop     rdi
0x18001cc9c  pop     rsi
0x18001cc9d  pop     rbp
0x18001cc9e  pop     rbx
0x18001cc9f  retn
```
