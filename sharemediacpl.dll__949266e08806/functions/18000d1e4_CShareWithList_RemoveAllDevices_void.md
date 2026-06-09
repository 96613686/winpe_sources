# CShareWithList::RemoveAllDevices(void)

- ea: `0x18000d1e4`
- end: `0x18000d32f`
- name: `?RemoveAllDevices@CShareWithList@@QEAAJXZ`
- size: `331`
- prototype: `__int64 __fastcall(CShareWithList *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009900`
- `0x180010bec`

## callees

- `0x180001d60`
- `0x180003860`
- `0x180003888`
- `0x18000d1e4`
- `0x180012c58`
- `0x180016374`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000d2ac`
- `KERNEL32!LeaveCriticalSection` at `0x18000d2ac`
- `KERNEL32!EnterCriticalSection` at `0x18000d26f`
- `KERNEL32!EnterCriticalSection` at `0x18000d26f`
- `DUI70!?DestroyAll@Element@DirectUI@@QEAAJ_N@Z` at `0x18000d299`
- `DUI70!?DestroyAll@Element@DirectUI@@QEAAJ_N@Z` at `0x18000d299`

## pseudocode

```c
__int64 __fastcall CShareWithList::RemoveAllDevices(CShareWithList *this, __int64 a2, __int64 a3)
{
  void *v4; // rcx
  DirectUI::Element *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // r8
  int v9; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+38h] [rbp-30h] BYREF
  int *v11; // [rsp+48h] [rbp-20h]
  __int64 v12; // [rsp+50h] [rbp-18h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
  {
    v9 = 0;
    v11 = &v9;
    v12 = 4;
    McGenEventWrite_EventWriteTransfer(
      (__int64)v4,
      (const EVENT_DESCRIPTOR *)ShareMediaCPL_RemoveAllDevices_Start,
      a3,
      2u,
      &v10);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( *((_QWORD *)this + 3) )
  {
    v5 = (DirectUI::Element *)*((_QWORD *)this + 2);
    if ( v5 && (*((_BYTE *)v5 + 151) & 4) == 0 && (*((_BYTE *)v5 + 149) & 2) != 0 )
      DirectUI::Element::DestroyAll(v5, 0);
    DPA_DeleteAllPtrs(*((HDPA *)this + 3));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
  {
    v9 = 0;
    v11 = &v9;
    v12 = 4;
    McGenEventWrite_EventWriteTransfer(v6, (const EVENT_DESCRIPTOR *)ShareMediaCPL_RemoveAllDevices_Stop, v7, 2u, &v10);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18000d1e4  push    rbp
0x18000d1e6  push    rbx
0x18000d1e7  push    rdi
0x18000d1e8  push    r12
0x18000d1ea  mov     rbp, rsp
0x18000d1ed  sub     rsp, 68h
0x18000d1f1  mov     rax, cs:__security_cookie
0x18000d1f8  xor     rax, rsp
0x18000d1fb  mov     [rbp+var_10], rax
0x18000d1ff  mov     rbx, rcx
0x18000d202  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d209  lea     r12, WPP_GLOBAL_Control
0x18000d210  cmp     rcx, r12
0x18000d213  jz      short loc_18000D230
0x18000d215  test    byte ptr [rcx+1Ch], 20h
0x18000d219  jz      short loc_18000D230
0x18000d21b  mov     rcx, [rcx+10h]
0x18000d21f  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000d226  mov     edx, 91h
0x18000d22b  call    WPP_SF_
0x18000d230  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x18000d237  jz      short loc_18000D26B
0x18000d239  lea     rax, [rbp+var_38]
0x18000d23d  mov     [rbp+var_38], 0
0x18000d244  mov     [rbp+var_20], rax
0x18000d248  lea     rdx, ShareMediaCPL_RemoveAllDevices_Start
0x18000d24f  lea     rax, [rbp+var_30]
0x18000d253  mov     [rbp+var_18], 4
0x18000d25b  mov     r9d, 2
0x18000d261  mov     [rsp+68h+var_48], rax
0x18000d266  call    McGenEventWrite_EventWriteTransfer
0x18000d26b  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000d26f  call    cs:__imp_EnterCriticalSection
0x18000d275  cmp     qword ptr [rbx+18h], 0
0x18000d27a  jz      short loc_18000D2A8
0x18000d27c  mov     rcx, [rbx+10h]
0x18000d280  test    rcx, rcx
0x18000d283  jz      short loc_18000D29F
0x18000d285  test    byte ptr [rcx+97h], 4
0x18000d28c  jnz     short loc_18000D29F
0x18000d28e  test    byte ptr [rcx+95h], 2
0x18000d295  jz      short loc_18000D29F
0x18000d297  xor     edx, edx
0x18000d299  call    cs:__imp_?DestroyAll@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::DestroyAll(bool)
0x18000d29f  mov     rcx, [rbx+18h]; hdpa
0x18000d2a3  call    DPA_DeleteAllPtrs
0x18000d2a8  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000d2ac  call    cs:__imp_LeaveCriticalSection
0x18000d2b2  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x18000d2b9  jz      short loc_18000D2ED
0x18000d2bb  lea     rax, [rbp+var_38]
0x18000d2bf  mov     [rbp+var_38], 0
0x18000d2c6  mov     [rbp+var_20], rax
0x18000d2ca  lea     rdx, ShareMediaCPL_RemoveAllDevices_Stop
0x18000d2d1  lea     rax, [rbp+var_30]
0x18000d2d5  mov     [rbp+var_18], 4
0x18000d2dd  mov     r9d, 2
0x18000d2e3  mov     [rsp+68h+var_48], rax
0x18000d2e8  call    McGenEventWrite_EventWriteTransfer
0x18000d2ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2f4  cmp     rcx, r12
0x18000d2f7  jz      short loc_18000D317
0x18000d2f9  test    byte ptr [rcx+1Ch], 20h
0x18000d2fd  jz      short loc_18000D317
0x18000d2ff  mov     rcx, [rcx+10h]
0x18000d303  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000d30a  mov     edx, 92h
0x18000d30f  xor     r9d, r9d
0x18000d312  call    WPP_SF_d
0x18000d317  xor     eax, eax
0x18000d319  mov     rcx, [rbp+var_10]
0x18000d31d  xor     rcx, rsp; StackCookie
0x18000d320  call    __security_check_cookie
0x18000d325  add     rsp, 68h
0x18000d329  pop     r12
0x18000d32b  pop     rdi
0x18000d32c  pop     rbx
0x18000d32d  pop     rbp
0x18000d32e  retn
```
