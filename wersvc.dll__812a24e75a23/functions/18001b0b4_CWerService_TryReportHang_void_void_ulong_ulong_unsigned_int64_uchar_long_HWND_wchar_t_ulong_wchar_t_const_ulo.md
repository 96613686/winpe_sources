# CWerService::TryReportHang(void *,void *,ulong *,ulong,unsigned __int64 *,uchar *,long *,HWND__ *,wchar_t *,ulong,wchar_t const *,ulong,HWND__ * *,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18001b0b4`
- end: `0x18001b3ef`
- name: `?TryReportHang@CWerService@@AEAAJPEAX0PEAKKPEA_KPEAEPEAJPEAUHWND__@@PEA_WKPEB_WKPEAPEAU2@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@9@Z`
- size: `827`
- prototype: `__int64 __fastcall(__int64, void *, void *, unsigned int *, unsigned int, unsigned __int64 *, unsigned __int8 *, int *, HWND, void *, unsigned int, wchar_t *, unsigned int, _QWORD *, void **, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180019fc8`

## callees

- `0x180006a80`
- `0x180011ef8`
- `0x18001b0b4`
- `0x1800248f4`
- `0x18002de2c`
- `0x18002df50`
- `0x18002e034`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b11f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b354`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b3b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b3cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b11f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b354`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b3b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b3cc`

## pseudocode

```c
__int64 __fastcall CWerService::TryReportHang(
        __int64 a1,
        void *a2,
        void *a3,
        unsigned int *a4,
        unsigned int a5,
        unsigned __int64 *a6,
        unsigned __int8 *a7,
        int *a8,
        HWND a9,
        void *a10,
        unsigned int a11,
        wchar_t *a12,
        unsigned int a13,
        _QWORD *a14,
        void **a15,
        void **a16)
{
  int v17; // r15d
  void *v18; // rcx
  void *v19; // rcx
  CHandleMonitor *v20; // rdi
  int Reservation; // eax
  int v22; // ebx
  int v23; // eax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  HANDLE v27; // rcx
  HANDLE v28; // rax
  void *v29; // rcx
  int v31; // [rsp+98h] [rbp-19h] BYREF
  int v32; // [rsp+9Ch] [rbp-15h]
  HANDLE hObject; // [rsp+A0h] [rbp-11h] BYREF
  HANDLE v34; // [rsp+A8h] [rbp-9h] BYREF

  v17 = 0;
  v31 = 0;
  v32 = 0;
  hObject = 0;
  v34 = 0;
  if ( a14 )
    *a14 = 0;
  if ( a15 )
  {
    v18 = *a15;
    *a15 = 0;
    if ( (unsigned __int64)v18 + 1 > 1 )
      CloseHandle(v18);
  }
  if ( a16 )
  {
    v19 = *a16;
    *a16 = 0;
    if ( (unsigned __int64)v19 + 1 > 1 )
      CloseHandle(v19);
  }
  if ( !a14 || !a15 || !a16 )
  {
    v22 = -2147024809;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_43;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    v20 = (CHandleMonitor *)(a1 + 80);
    goto LABEL_40;
  }
  v20 = (CHandleMonitor *)(a1 + 80);
  Reservation = CHandleMonitor::GetReservation((CHandleMonitor *)(a1 + 80), &v31);
  v22 = Reservation;
  if ( Reservation < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        164,
        WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
        (unsigned int)Reservation);
    v17 = v31;
    goto LABEL_40;
  }
  v17 = v31;
  if ( v31 )
  {
    v23 = CHangrepServer::ReportHang(
            (struct _RTL_CRITICAL_SECTION *)(a1 + 416),
            a2,
            a3,
            a4,
            a5,
            a6,
            a7,
            a8,
            a9,
            a10,
            a11,
            a12,
            a13,
            a14,
            a15,
            &hObject,
            &v34);
    v22 = v23;
    if ( v23 < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v25 = 166;
        v26 = (unsigned int)v23;
LABEL_25:
        WPP_SF_d(v24[2], v25, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v26);
        goto LABEL_40;
      }
      goto LABEL_40;
    }
    if ( (unsigned __int64)hObject + 1 > 1 )
    {
      v22 = CHandleMonitor::DupeAndAddHandle((CHandleMonitor *)(a1 + 80), hObject, *a4);
      v27 = hObject;
      hObject = 0;
      if ( (unsigned __int64)v27 + 1 > 1 )
        CloseHandle(v27);
      if ( v22 < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = 167;
          v26 = (unsigned int)v22;
          goto LABEL_25;
        }
LABEL_40:
        if ( v17 && !v32 )
          CHandleMonitor::CancelReservation(v20);
        goto LABEL_43;
      }
      v32 = 1;
    }
    v28 = v34;
    v34 = 0;
    v29 = *a16;
    *a16 = v28;
    if ( (unsigned __int64)v29 + 1 > 1 )
      CloseHandle(v29);
    v22 = 0;
    goto LABEL_40;
  }
  v22 = 1769483;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
LABEL_43:
  if ( (unsigned __int64)v34 + 1 > 1 )
    CloseHandle(v34);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18001b0b4  mov     rax, rsp
0x18001b0b7  mov     [rax+8], rbx
0x18001b0bb  mov     [rax+20h], r9
0x18001b0bf  mov     [rax+18h], r8
0x18001b0c3  mov     [rax+10h], rdx
0x18001b0c7  push    rbp
0x18001b0c8  push    rsi
0x18001b0c9  push    rdi
0x18001b0ca  push    r12
0x18001b0cc  push    r13
0x18001b0ce  push    r14
0x18001b0d0  push    r15
0x18001b0d2  lea     rbp, [rax-3Fh]
0x18001b0d6  sub     rsp, 0B0h
0x18001b0dd  mov     r13, rcx
0x18001b0e0  xor     ebx, ebx
0x18001b0e2  mov     r15d, ebx
0x18001b0e5  mov     [rbp+37h+var_50], ebx
0x18001b0e8  mov     [rbp+37h+var_4C], ebx
0x18001b0eb  mov     [rbp+37h+hObject], rbx
0x18001b0ef  mov     [rbp+37h+var_40], rbx
0x18001b0f3  mov     r12, [rbp+37h+arg_68]
0x18001b0fa  test    r12, r12
0x18001b0fd  jz      short loc_18001B103
0x18001b0ff  mov     [r12], rbx
0x18001b103  mov     r14, [rbp+37h+arg_70]
0x18001b10a  test    r14, r14
0x18001b10d  jz      short loc_18001B125
0x18001b10f  mov     rcx, [r14]; hObject
0x18001b112  mov     [r14], rbx
0x18001b115  lea     rax, [rcx+1]
0x18001b119  cmp     rax, 1
0x18001b11d  jbe     short loc_18001B125
0x18001b11f  call    cs:__imp_CloseHandle
0x18001b125  mov     rsi, [rbp+37h+arg_78]
0x18001b12c  test    rsi, rsi
0x18001b12f  jz      short loc_18001B147
0x18001b131  mov     rcx, [rsi]; hObject
0x18001b134  mov     [rsi], rbx
0x18001b137  lea     rax, [rcx+1]
0x18001b13b  cmp     rax, 1
0x18001b13f  jbe     short loc_18001B147
0x18001b141  call    cs:__imp_CloseHandle
0x18001b147  test    r12, r12
0x18001b14a  jz      loc_18001B35E
0x18001b150  test    r14, r14
0x18001b153  jz      loc_18001B35E
0x18001b159  test    rsi, rsi
0x18001b15c  jz      loc_18001B35E
0x18001b162  lea     rdi, [r13+50h]
0x18001b166  lea     rdx, [rbp+37h+var_50]; int *
0x18001b16a  mov     rcx, rdi; this
0x18001b16d  call    ?GetReservation@CHandleMonitor@@QEAAJPEAH@Z; CHandleMonitor::GetReservation(int *)
0x18001b172  mov     ebx, eax
0x18001b174  test    eax, eax
0x18001b176  jns     short loc_18001B1B2
0x18001b178  lea     rdx, WPP_GLOBAL_Control
0x18001b17f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b186  cmp     rcx, rdx
0x18001b189  jz      short loc_18001B1A9
0x18001b18b  test    byte ptr [rcx+1Ch], 1
0x18001b18f  jz      short loc_18001B1A9
0x18001b191  mov     edx, 0A4h
0x18001b196  mov     r9d, eax
0x18001b199  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001b1a0  mov     rcx, [rcx+10h]
0x18001b1a4  call    WPP_SF_d
0x18001b1a9  mov     r15d, [rbp+37h+var_50]
0x18001b1ad  jmp     loc_18001B395
0x18001b1b2  mov     r15d, [rbp+37h+var_50]
0x18001b1b6  test    r15d, r15d
0x18001b1b9  jnz     short loc_18001B1FB
0x18001b1bb  mov     ebx, 1B000Bh
0x18001b1c0  lea     rdx, WPP_GLOBAL_Control
0x18001b1c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1ce  cmp     rcx, rdx
0x18001b1d1  jz      loc_18001B3A9
0x18001b1d7  test    byte ptr [rcx+1Ch], 4
0x18001b1db  jz      loc_18001B3A9
0x18001b1e1  mov     edx, 0A5h
0x18001b1e6  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001b1ed  mov     rcx, [rcx+10h]
0x18001b1f1  call    WPP_SF_
0x18001b1f6  jmp     loc_18001B3A9
0x18001b1fb  lea     rcx, [r13+1A0h]; this
0x18001b202  lea     rax, [rbp+37h+var_40]
0x18001b206  mov     [rsp+80h], rax; __int64
0x18001b20e  lea     rax, [rbp+37h+hObject]
0x18001b212  mov     [rsp+0E0h+var_68], rax; __int64
0x18001b217  mov     [rsp+0E0h+var_70], r14; __int64
0x18001b21c  mov     [rsp+0E0h+var_78], r12; __int64
0x18001b221  mov     eax, [rbp+37h+arg_60]
0x18001b227  mov     [rsp+0E0h+var_80], eax; unsigned int
0x18001b22b  mov     rax, [rbp+37h+arg_58]
0x18001b232  mov     [rsp+0E0h+var_88], rax; __int64
0x18001b237  mov     eax, [rbp+37h+arg_50]
0x18001b23d  mov     [rsp+0E0h+var_90], eax; unsigned int
0x18001b241  mov     rax, [rbp+37h+arg_48]
0x18001b248  mov     [rsp+0E0h+var_98], rax; __int64
0x18001b24d  mov     rax, [rbp+37h+arg_40]
0x18001b254  mov     [rsp+0E0h+var_A0], rax; HWND
0x18001b259  mov     rax, [rbp+37h+arg_38]
0x18001b25d  mov     [rsp+0E0h+var_A8], rax; int *
0x18001b262  mov     rax, [rbp+37h+arg_30]
0x18001b266  mov     [rsp+0E0h+var_B0], rax; unsigned __int8 *
0x18001b26b  mov     rax, [rbp+37h+arg_28]
0x18001b26f  mov     [rsp+0E0h+var_B8], rax; unsigned __int64 *
0x18001b274  mov     eax, [rbp+37h+arg_20]
0x18001b277  mov     [rsp+0E0h+var_C0], eax; int
0x18001b27b  mov     r14, [rbp+37h+arg_18]
0x18001b27f  mov     r9, r14
0x18001b282  mov     r8, [rbp+37h+arg_10]
0x18001b286  mov     rdx, [rbp+37h+Process]; Process
0x18001b28a  call    ?ReportHang@CHangrepServer@@QEAAJPEAX0PEAKKPEA_KPEAEPEAJPEAUHWND__@@PEA_WKPEB_WKPEAPEAU2@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@99@Z; CHangrepServer::ReportHang(void *,void *,ulong *,ulong,unsigned __int64 *,uchar *,long *,HWND__ *,wchar_t *,ulong,wchar_t const *,ulong,HWND__ * *,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *,tlx::unique_any<tlx::file_handle_traits> *)
0x18001b28f  mov     ebx, eax
0x18001b291  test    eax, eax
0x18001b293  jns     short loc_18001B2D3
0x18001b295  lea     rdx, WPP_GLOBAL_Control
0x18001b29c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2a3  cmp     rcx, rdx
0x18001b2a6  jz      loc_18001B395
0x18001b2ac  test    byte ptr [rcx+1Ch], 1
0x18001b2b0  jz      loc_18001B395
0x18001b2b6  mov     edx, 0A6h
0x18001b2bb  mov     r9d, eax
0x18001b2be  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001b2c5  mov     rcx, [rcx+10h]
0x18001b2c9  call    WPP_SF_d
0x18001b2ce  jmp     loc_18001B395
0x18001b2d3  mov     rdx, [rbp+37h+hObject]; void *
0x18001b2d7  lea     rax, [rdx+1]
0x18001b2db  cmp     rax, 1
0x18001b2df  jbe     short loc_18001B338
0x18001b2e1  mov     r8d, [r14]; unsigned int
0x18001b2e4  mov     rcx, rdi; this
0x18001b2e7  call    ?DupeAndAddHandle@CHandleMonitor@@QEAAJPEAXK@Z; CHandleMonitor::DupeAndAddHandle(void *,ulong)
0x18001b2ec  mov     ebx, eax
0x18001b2ee  mov     rcx, [rbp+37h+hObject]; hObject
0x18001b2f2  mov     [rbp+37h+hObject], 0
0x18001b2fa  lea     rax, [rcx+1]
0x18001b2fe  cmp     rax, 1
0x18001b302  jbe     short loc_18001B30A
0x18001b304  call    cs:__imp_CloseHandle
0x18001b30a  test    ebx, ebx
0x18001b30c  jns     short loc_18001B331
0x18001b30e  lea     rdx, WPP_GLOBAL_Control
0x18001b315  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b31c  cmp     rcx, rdx
0x18001b31f  jz      short loc_18001B395
0x18001b321  test    byte ptr [rcx+1Ch], 1
0x18001b325  jz      short loc_18001B395
0x18001b327  mov     edx, 0A7h
0x18001b32c  mov     r9d, ebx
0x18001b32f  jmp     short loc_18001B2BE
0x18001b331  mov     [rbp+37h+var_4C], 1
0x18001b338  mov     rax, [rbp+37h+var_40]
0x18001b33c  mov     [rbp+37h+var_40], 0
0x18001b344  mov     rcx, [rsi]; hObject
0x18001b347  mov     [rsi], rax
0x18001b34a  lea     rax, [rcx+1]
0x18001b34e  cmp     rax, 1
0x18001b352  jbe     short loc_18001B35A
0x18001b354  call    cs:__imp_CloseHandle
0x18001b35a  xor     ebx, ebx
0x18001b35c  jmp     short loc_18001B395
0x18001b35e  mov     ebx, 80070057h
0x18001b363  lea     rdx, WPP_GLOBAL_Control
0x18001b36a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b371  cmp     rcx, rdx
0x18001b374  jz      short loc_18001B3A9
0x18001b376  test    byte ptr [rcx+1Ch], 1
0x18001b37a  jz      short loc_18001B3A9
0x18001b37c  mov     edx, 0A3h
0x18001b381  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001b388  mov     rcx, [rcx+10h]
0x18001b38c  call    WPP_SF_
0x18001b391  lea     rdi, [r13+50h]
0x18001b395  test    r15d, r15d
0x18001b398  jz      short loc_18001B3A9
0x18001b39a  cmp     [rbp+37h+var_4C], 0
0x18001b39e  jnz     short loc_18001B3A9
0x18001b3a0  mov     rcx, rdi; this
0x18001b3a3  call    ?CancelReservation@CHandleMonitor@@QEAAJXZ; CHandleMonitor::CancelReservation(void)
0x18001b3a8  nop
0x18001b3a9  mov     rcx, [rbp+37h+var_40]; hObject
0x18001b3ad  lea     rax, [rcx+1]
0x18001b3b1  cmp     rax, 1
0x18001b3b5  jbe     short loc_18001B3BE
0x18001b3b7  call    cs:__imp_CloseHandle
0x18001b3bd  nop
0x18001b3be  mov     rcx, [rbp+37h+hObject]; hObject
0x18001b3c2  lea     rax, [rcx+1]
0x18001b3c6  cmp     rax, 1
0x18001b3ca  jbe     short loc_18001B3D2
0x18001b3cc  call    cs:__imp_CloseHandle
0x18001b3d2  mov     eax, ebx
0x18001b3d4  mov     rbx, [rsp+0E0h+arg_0]
0x18001b3dc  add     rsp, 0B0h
0x18001b3e3  pop     r15
0x18001b3e5  pop     r14
0x18001b3e7  pop     r13
0x18001b3e9  pop     r12
0x18001b3eb  pop     rdi
0x18001b3ec  pop     rsi
0x18001b3ed  pop     rbp
0x18001b3ee  retn
```
