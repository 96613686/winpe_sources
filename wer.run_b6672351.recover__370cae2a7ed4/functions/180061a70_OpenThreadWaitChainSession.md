# OpenThreadWaitChainSession

- ea: `0x180061a70`
- end: `0x180061bfb`
- name: `OpenThreadWaitChainSession`
- size: `395`
- prototype: `HWCT __stdcall(DWORD Flags, PWAITCHAINCALLBACK callback)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180004c64`
- `0x180008004`
- `0x180020680`
- `0x180051124`
- `0x18005eca8`
- `0x18005ed5c`
- `0x180061330`
- `0x180061a70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061ae9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061ae9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061b96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061b7a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061b55`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061b55`

## pseudocode

```c
HWCT __stdcall OpenThreadWaitChainSession(DWORD Flags, PWAITCHAINCALLBACK callback)
{
  DWORD LastError; // ebx
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  HANDLE EventW; // rax
  __int64 v8; // rcx
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  if ( (Flags & 0xFFFFFFFE) != 0 || (Flags & 1) != 0 && !callback )
  {
    LastError = 87;
LABEL_18:
    SetLastError(LastError);
    v6 = 0;
    goto LABEL_20;
  }
  if ( !(unsigned int)WctInitPackage() )
  {
    LastError = 1359;
    goto LABEL_18;
  }
  v5 = HeapAlloc(g_hWerheap, 0, 0x30u);
  v6 = v5;
  if ( v5 )
  {
    v5[3] = 0;
    *(_OWORD *)v5 = 0;
    v5[2] = 0;
    v5[4] = 0;
    v5[5] = 0;
  }
  else
  {
    v6 = 0;
  }
  v10 = 0;
  utl::unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>::~unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>(&v10);
  if ( !v6 )
  {
    LastError = 8;
    goto LABEL_18;
  }
  *((_DWORD *)v6 + 6) = Flags;
  v6[4] = callback;
  EventW = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(v6 + 5, EventW);
  if ( v6[5] != -1 && v6[5] != 0 )
  {
    LastError = 0;
    WctAddEntry((struct WCT_ENTRY *)v6);
    goto LABEL_20;
  }
  LastError = GetLastError();
  if ( LastError )
  {
    utl::default_delete<WCT_ENTRY>::operator()(v8, v6);
    goto LABEL_18;
  }
LABEL_20:
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, LastError);
  v10 = 0;
  utl::unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>::~unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>(&v10);
  return v6;
}

```

## disassembly

```asm
0x180061a70  push    rbx
0x180061a72  push    rsi
0x180061a73  push    rdi
0x180061a74  push    r14
0x180061a76  sub     rsp, 28h
0x180061a7a  mov     rsi, rdx
0x180061a7d  mov     ebx, ecx
0x180061a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180061a86  lea     r14, WPP_GLOBAL_Control
0x180061a8d  cmp     rcx, r14
0x180061a90  jz      short loc_180061AAD
0x180061a92  test    byte ptr [rcx+1Ch], 4
0x180061a96  jz      short loc_180061AAD
0x180061a98  mov     rcx, [rcx+10h]
0x180061a9c  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180061aa3  mov     edx, 3Dh ; '='
0x180061aa8  call    WPP_SF_
0x180061aad  test    ebx, 0FFFFFFFEh
0x180061ab3  jz      short loc_180061ABF
0x180061ab5  mov     ebx, 57h ; 'W'
0x180061aba  jmp     loc_180061B94
0x180061abf  test    bl, 1
0x180061ac2  jz      short loc_180061AC9
0x180061ac4  test    rsi, rsi
0x180061ac7  jz      short loc_180061AB5
0x180061ac9  call    ?WctInitPackage@@YAHXZ; WctInitPackage(void)
0x180061ace  test    eax, eax
0x180061ad0  jnz     short loc_180061ADC
0x180061ad2  mov     ebx, 54Fh
0x180061ad7  jmp     loc_180061B94
0x180061adc  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180061ae3  xor     edx, edx; dwFlags
0x180061ae5  lea     r8d, [rdx+30h]; dwBytes
0x180061ae9  call    cs:__imp_HeapAlloc
0x180061af0  nop     dword ptr [rax+rax+00h]
0x180061af5  mov     rdi, rax
0x180061af8  test    rax, rax
0x180061afb  jz      short loc_180061B25
0x180061afd  mov     qword ptr [rax+18h], 0
0x180061b05  xorps   xmm0, xmm0
0x180061b08  movups  xmmword ptr [rax], xmm0
0x180061b0b  mov     qword ptr [rax+10h], 0
0x180061b13  mov     qword ptr [rax+20h], 0
0x180061b1b  mov     qword ptr [rax+28h], 0
0x180061b23  jmp     short loc_180061B27
0x180061b25  xor     edi, edi
0x180061b27  lea     rcx, [rsp+48h+arg_10]
0x180061b2c  mov     [rsp+48h+arg_10], 0
0x180061b35  call    ??1?$unique_ptr@UWCT_ENTRY@@U?$default_delete@UWCT_ENTRY@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>::~unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>(void)
0x180061b3a  test    rdi, rdi
0x180061b3d  jnz     short loc_180061B44
0x180061b3f  lea     ebx, [rdi+8]
0x180061b42  jmp     short loc_180061B94
0x180061b44  mov     [rdi+18h], ebx
0x180061b47  xor     r9d, r9d; lpName
0x180061b4a  xor     r8d, r8d; bInitialState
0x180061b4d  mov     [rdi+20h], rsi
0x180061b51  xor     edx, edx; bManualReset
0x180061b53  xor     ecx, ecx; lpEventAttributes
0x180061b55  call    cs:__imp_CreateEventW
0x180061b5c  nop     dword ptr [rax+rax+00h]
0x180061b61  mov     rdx, rax
0x180061b64  lea     rcx, [rdi+28h]
0x180061b68  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180061b6d  mov     rax, [rdi+28h]
0x180061b71  inc     rax
0x180061b74  cmp     rax, 1
0x180061b78  ja      short loc_180061BA6
0x180061b7a  call    cs:__imp_GetLastError
0x180061b81  nop     dword ptr [rax+rax+00h]
0x180061b86  mov     ebx, eax
0x180061b88  test    eax, eax
0x180061b8a  jz      short loc_180061BB0
0x180061b8c  mov     rdx, rdi
0x180061b8f  call    ??R?$default_delete@UWCT_ENTRY@@@utl@@QEBAXPEAUWCT_ENTRY@@@Z; utl::default_delete<WCT_ENTRY>::operator()(WCT_ENTRY *)
0x180061b94  mov     ecx, ebx; dwErrCode
0x180061b96  call    cs:__imp_SetLastError
0x180061b9d  nop     dword ptr [rax+rax+00h]
0x180061ba2  xor     edi, edi
0x180061ba4  jmp     short loc_180061BB0
0x180061ba6  xor     ebx, ebx
0x180061ba8  mov     rcx, rdi; struct WCT_ENTRY *
0x180061bab  call    ?WctAddEntry@@YAXPEAUWCT_ENTRY@@@Z; WctAddEntry(WCT_ENTRY *)
0x180061bb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180061bb7  cmp     rcx, r14
0x180061bba  jz      short loc_180061BDA
0x180061bbc  test    byte ptr [rcx+1Ch], 4
0x180061bc0  jz      short loc_180061BDA
0x180061bc2  mov     rcx, [rcx+10h]
0x180061bc6  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x180061bcd  mov     edx, 3Eh ; '>'
0x180061bd2  mov     r9d, ebx
0x180061bd5  call    WPP_SF_d
0x180061bda  lea     rcx, [rsp+48h+arg_10]
0x180061bdf  mov     [rsp+48h+arg_10], 0
0x180061be8  call    ??1?$unique_ptr@UWCT_ENTRY@@U?$default_delete@UWCT_ENTRY@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>::~unique_ptr<WCT_ENTRY,utl::default_delete<WCT_ENTRY>>(void)
0x180061bed  mov     rax, rdi
0x180061bf0  add     rsp, 28h
0x180061bf4  pop     r14
0x180061bf6  pop     rdi
0x180061bf7  pop     rsi
0x180061bf8  pop     rbx
0x180061bf9  retn
```
