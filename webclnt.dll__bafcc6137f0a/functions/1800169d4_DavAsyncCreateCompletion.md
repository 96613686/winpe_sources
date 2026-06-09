# DavAsyncCreateCompletion

- ea: `0x1800169d4`
- end: `0x180016d1b`
- name: `DavAsyncCreateCompletion`
- size: `839`
- prototype: `__int64 __fastcall(_QWORD *pvCallbackContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800196d0`

## callees

- `0x18000b7dc`
- `0x180010770`
- `0x180011360`
- `0x1800169d4`
- `0x1800196d0`
- `0x18002be24`

## import_xrefs

- `ntdll!NtClose` at `0x180016cce`
- `ntdll!NtClose` at `0x180016cce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016bcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016bcb`
- `KERNEL32!LocalFree` at `0x180016a02`
- `KERNEL32!LocalFree` at `0x180016a97`
- `KERNEL32!LocalFree` at `0x180016ae4`
- `KERNEL32!LocalFree` at `0x180016b31`
- `KERNEL32!LocalFree` at `0x180016b7e`
- `KERNEL32!LocalFree` at `0x180016c7c`
- `KERNEL32!LocalFree` at `0x180016a02`
- `KERNEL32!LocalFree` at `0x180016a97`
- `KERNEL32!LocalFree` at `0x180016ae4`
- `KERNEL32!LocalFree` at `0x180016b31`
- `KERNEL32!LocalFree` at `0x180016b7e`
- `KERNEL32!LocalFree` at `0x180016c7c`
- `WINHTTP!WinHttpCloseHandle` at `0x180016be4`
- `WINHTTP!WinHttpCloseHandle` at `0x180016c30`
- `WINHTTP!WinHttpCloseHandle` at `0x180016be4`
- `WINHTTP!WinHttpCloseHandle` at `0x180016c30`

## pseudocode

```c
__int64 __fastcall DavAsyncCreateCompletion(_QWORD *pvCallbackContext)
{
  void *v2; // rcx
  unsigned int v3; // esi
  __int64 v4; // rbx
  DWORD LastError; // eax
  unsigned int v6; // eax
  void *v7; // rcx
  __int64 v8; // rbx
  DWORD v9; // eax
  void *v10; // rcx
  __int64 v11; // rbx
  DWORD v12; // eax
  void *v13; // rcx
  __int64 v14; // rbx
  DWORD v15; // eax
  void *v16; // rcx
  __int64 v17; // rbx
  DWORD v18; // eax
  void *v19; // rcx
  void *v20; // rcx
  __int64 v21; // rbx
  DWORD v22; // eax
  void *v23; // rcx
  __int64 v24; // rbx
  DWORD v25; // eax
  void *v26; // rcx
  __int64 v27; // rbx
  DWORD v28; // eax
  void *v29; // rcx

  v2 = (void *)pvCallbackContext[71];
  v3 = 0;
  if ( v2 )
  {
    if ( LocalFree(v2)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v4, 214, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, LastError);
    }
    pvCallbackContext[71] = 0;
  }
  if ( pvCallbackContext[76] )
  {
    if ( *((_DWORD *)pvCallbackContext + 8) )
    {
      v6 = TfsReleaseEntry(v2, pvCallbackContext[73]);
      v3 = v6;
      if ( v6 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v6);
        v3 = 0;
      }
    }
  }
  v7 = (void *)pvCallbackContext[73];
  if ( v7 )
  {
    if ( LocalFree(v7)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v9 = GetLastError();
      WPP_SF_d(v8, 216, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v9);
    }
    pvCallbackContext[73] = 0;
  }
  v10 = (void *)pvCallbackContext[65];
  if ( v10 )
  {
    if ( LocalFree(v10)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v12 = GetLastError();
      WPP_SF_d(v11, 217, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v12);
    }
    pvCallbackContext[65] = 0;
  }
  v13 = (void *)pvCallbackContext[66];
  if ( v13 )
  {
    if ( LocalFree(v13)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v15 = GetLastError();
      WPP_SF_d(v14, 218, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v15);
    }
    pvCallbackContext[66] = 0;
  }
  v16 = (void *)pvCallbackContext[72];
  if ( v16 )
  {
    if ( LocalFree(v16)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v18 = GetLastError();
      WPP_SF_d(v17, 219, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v18);
    }
    pvCallbackContext[72] = 0;
  }
  v19 = (void *)pvCallbackContext[67];
  if ( v19 )
  {
    CloseHandle(v19);
    pvCallbackContext[67] = 0;
  }
  v20 = (void *)pvCallbackContext[74];
  if ( v20 )
  {
    if ( WinHttpCloseHandle(v20)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v21 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v22 = GetLastError();
      WPP_SF_d(v21, 220, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v22);
    }
    pvCallbackContext[74] = 0;
  }
  v23 = (void *)pvCallbackContext[75];
  if ( v23 )
  {
    if ( WinHttpCloseHandle(v23)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v25 = GetLastError();
      WPP_SF_d(v24, 221, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v25);
    }
    pvCallbackContext[75] = 0;
  }
  v26 = (void *)pvCallbackContext[76];
  if ( v26 )
  {
    if ( LocalFree(v26)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v27 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v28 = GetLastError();
      WPP_SF_d(v27, 222, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids, v28);
    }
    pvCallbackContext[76] = 0;
  }
  if ( *((_DWORD *)pvCallbackContext + 8) )
  {
    v29 = (void *)pvCallbackContext[682];
    if ( v29 )
    {
      NtClose(v29);
      pvCallbackContext[682] = 0;
      pvCallbackContext[683] = 0;
    }
  }
  if ( *((_DWORD *)pvCallbackContext + 156) )
    v3 = DavFsCreate((char *)pvCallbackContext);
  else
    DavFsFinalizeTheDavCallBackContext((__int64)pvCallbackContext);
  if ( pvCallbackContext[62] )
    DavFinalizePerUserEntry();
  return v3;
}

```

## disassembly

```asm
0x1800169d4  push    rbx
0x1800169d6  push    rbp
0x1800169d7  push    rsi
0x1800169d8  push    rdi
0x1800169d9  push    r12
0x1800169db  push    r14
0x1800169dd  sub     rsp, 28h
0x1800169e1  xor     ebp, ebp
0x1800169e3  lea     r14, WPP_GLOBAL_Control
0x1800169ea  mov     rdi, rcx
0x1800169ed  lea     r12, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x1800169f4  mov     rcx, [rcx+238h]; hMem
0x1800169fb  mov     esi, ebp
0x1800169fd  test    rcx, rcx
0x180016a00  jz      short loc_180016A43
0x180016a02  call    cs:__imp_LocalFree
0x180016a08  test    rax, rax
0x180016a0b  jz      short loc_180016A3C
0x180016a0d  mov     rbx, cs:WPP_GLOBAL_Control
0x180016a14  cmp     rbx, r14
0x180016a17  jz      short loc_180016A3C
0x180016a19  test    byte ptr [rbx+1Ch], 1
0x180016a1d  jz      short loc_180016A3C
0x180016a1f  mov     rbx, [rbx+10h]
0x180016a23  call    cs:__imp_GetLastError
0x180016a29  mov     edx, 0D6h
0x180016a2e  mov     r8, r12
0x180016a31  mov     r9d, eax
0x180016a34  mov     rcx, rbx
0x180016a37  call    WPP_SF_d
0x180016a3c  mov     [rdi+238h], rbp
0x180016a43  cmp     [rdi+260h], rbp
0x180016a4a  jz      short loc_180016A8B
0x180016a4c  cmp     [rdi+20h], ebp
0x180016a4f  jz      short loc_180016A8B
0x180016a51  mov     rdx, [rdi+248h]
0x180016a58  call    TfsReleaseEntry
0x180016a5d  mov     esi, eax
0x180016a5f  test    eax, eax
0x180016a61  jz      short loc_180016A8B
0x180016a63  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a6a  cmp     rcx, r14
0x180016a6d  jz      short loc_180016A89
0x180016a6f  test    byte ptr [rcx+1Ch], 1
0x180016a73  jz      short loc_180016A89
0x180016a75  mov     rcx, [rcx+10h]
0x180016a79  mov     edx, 0D7h
0x180016a7e  mov     r9d, eax
0x180016a81  mov     r8, r12
0x180016a84  call    WPP_SF_d
0x180016a89  mov     esi, ebp
0x180016a8b  mov     rcx, [rdi+248h]; hMem
0x180016a92  test    rcx, rcx
0x180016a95  jz      short loc_180016AD8
0x180016a97  call    cs:__imp_LocalFree
0x180016a9d  test    rax, rax
0x180016aa0  jz      short loc_180016AD1
0x180016aa2  mov     rbx, cs:WPP_GLOBAL_Control
0x180016aa9  cmp     rbx, r14
0x180016aac  jz      short loc_180016AD1
0x180016aae  test    byte ptr [rbx+1Ch], 1
0x180016ab2  jz      short loc_180016AD1
0x180016ab4  mov     rbx, [rbx+10h]
0x180016ab8  call    cs:__imp_GetLastError
0x180016abe  mov     edx, 0D8h
0x180016ac3  mov     r8, r12
0x180016ac6  mov     r9d, eax
0x180016ac9  mov     rcx, rbx
0x180016acc  call    WPP_SF_d
0x180016ad1  mov     [rdi+248h], rbp
0x180016ad8  mov     rcx, [rdi+208h]; hMem
0x180016adf  test    rcx, rcx
0x180016ae2  jz      short loc_180016B25
0x180016ae4  call    cs:__imp_LocalFree
0x180016aea  test    rax, rax
0x180016aed  jz      short loc_180016B1E
0x180016aef  mov     rbx, cs:WPP_GLOBAL_Control
0x180016af6  cmp     rbx, r14
0x180016af9  jz      short loc_180016B1E
0x180016afb  test    byte ptr [rbx+1Ch], 1
0x180016aff  jz      short loc_180016B1E
0x180016b01  mov     rbx, [rbx+10h]
0x180016b05  call    cs:__imp_GetLastError
0x180016b0b  mov     edx, 0D9h
0x180016b10  mov     r8, r12
0x180016b13  mov     r9d, eax
0x180016b16  mov     rcx, rbx
0x180016b19  call    WPP_SF_d
0x180016b1e  mov     [rdi+208h], rbp
0x180016b25  mov     rcx, [rdi+210h]; hMem
0x180016b2c  test    rcx, rcx
0x180016b2f  jz      short loc_180016B72
0x180016b31  call    cs:__imp_LocalFree
0x180016b37  test    rax, rax
0x180016b3a  jz      short loc_180016B6B
0x180016b3c  mov     rbx, cs:WPP_GLOBAL_Control
0x180016b43  cmp     rbx, r14
0x180016b46  jz      short loc_180016B6B
0x180016b48  test    byte ptr [rbx+1Ch], 1
0x180016b4c  jz      short loc_180016B6B
0x180016b4e  mov     rbx, [rbx+10h]
0x180016b52  call    cs:__imp_GetLastError
0x180016b58  mov     edx, 0DAh
0x180016b5d  mov     r8, r12
0x180016b60  mov     r9d, eax
0x180016b63  mov     rcx, rbx
0x180016b66  call    WPP_SF_d
0x180016b6b  mov     [rdi+210h], rbp
0x180016b72  mov     rcx, [rdi+240h]; hMem
0x180016b79  test    rcx, rcx
0x180016b7c  jz      short loc_180016BBF
0x180016b7e  call    cs:__imp_LocalFree
0x180016b84  test    rax, rax
0x180016b87  jz      short loc_180016BB8
0x180016b89  mov     rbx, cs:WPP_GLOBAL_Control
0x180016b90  cmp     rbx, r14
0x180016b93  jz      short loc_180016BB8
0x180016b95  test    byte ptr [rbx+1Ch], 1
0x180016b99  jz      short loc_180016BB8
0x180016b9b  mov     rbx, [rbx+10h]
0x180016b9f  call    cs:__imp_GetLastError
0x180016ba5  mov     edx, 0DBh
0x180016baa  mov     r8, r12
0x180016bad  mov     r9d, eax
0x180016bb0  mov     rcx, rbx
0x180016bb3  call    WPP_SF_d
0x180016bb8  mov     [rdi+240h], rbp
0x180016bbf  mov     rcx, [rdi+218h]; hObject
0x180016bc6  test    rcx, rcx
0x180016bc9  jz      short loc_180016BD8
0x180016bcb  call    cs:__imp_CloseHandle
0x180016bd1  mov     [rdi+218h], rbp
0x180016bd8  mov     rcx, [rdi+250h]; hInternet
0x180016bdf  test    rcx, rcx
0x180016be2  jz      short loc_180016C24
0x180016be4  call    cs:__imp_WinHttpCloseHandle
0x180016bea  test    eax, eax
0x180016bec  jz      short loc_180016C1D
0x180016bee  mov     rbx, cs:WPP_GLOBAL_Control
0x180016bf5  cmp     rbx, r14
0x180016bf8  jz      short loc_180016C1D
0x180016bfa  test    byte ptr [rbx+1Ch], 1
0x180016bfe  jz      short loc_180016C1D
0x180016c00  mov     rbx, [rbx+10h]
0x180016c04  call    cs:__imp_GetLastError
0x180016c0a  mov     edx, 0DCh
0x180016c0f  mov     r8, r12
0x180016c12  mov     r9d, eax
0x180016c15  mov     rcx, rbx
0x180016c18  call    WPP_SF_d
0x180016c1d  mov     [rdi+250h], rbp
0x180016c24  mov     rcx, [rdi+258h]; hInternet
0x180016c2b  test    rcx, rcx
0x180016c2e  jz      short loc_180016C70
0x180016c30  call    cs:__imp_WinHttpCloseHandle
0x180016c36  test    eax, eax
0x180016c38  jz      short loc_180016C69
0x180016c3a  mov     rbx, cs:WPP_GLOBAL_Control
0x180016c41  cmp     rbx, r14
0x180016c44  jz      short loc_180016C69
0x180016c46  test    byte ptr [rbx+1Ch], 1
0x180016c4a  jz      short loc_180016C69
0x180016c4c  mov     rbx, [rbx+10h]
0x180016c50  call    cs:__imp_GetLastError
0x180016c56  mov     edx, 0DDh
0x180016c5b  mov     r8, r12
0x180016c5e  mov     r9d, eax
0x180016c61  mov     rcx, rbx
0x180016c64  call    WPP_SF_d
0x180016c69  mov     [rdi+258h], rbp
0x180016c70  mov     rcx, [rdi+260h]; hMem
0x180016c77  test    rcx, rcx
0x180016c7a  jz      short loc_180016CBD
0x180016c7c  call    cs:__imp_LocalFree
0x180016c82  test    rax, rax
0x180016c85  jz      short loc_180016CB6
0x180016c87  mov     rbx, cs:WPP_GLOBAL_Control
0x180016c8e  cmp     rbx, r14
0x180016c91  jz      short loc_180016CB6
0x180016c93  test    byte ptr [rbx+1Ch], 1
0x180016c97  jz      short loc_180016CB6
0x180016c99  mov     rbx, [rbx+10h]
0x180016c9d  call    cs:__imp_GetLastError
0x180016ca3  mov     edx, 0DEh
0x180016ca8  mov     r8, r12
0x180016cab  mov     r9d, eax
0x180016cae  mov     rcx, rbx
0x180016cb1  call    WPP_SF_d
0x180016cb6  mov     [rdi+260h], rbp
0x180016cbd  cmp     [rdi+20h], ebp
0x180016cc0  jz      short loc_180016CE2
0x180016cc2  mov     rcx, [rdi+1550h]; Handle
0x180016cc9  test    rcx, rcx
0x180016ccc  jz      short loc_180016CE2
0x180016cce  call    cs:__imp_NtClose
0x180016cd4  mov     [rdi+1550h], rbp
0x180016cdb  mov     [rdi+1558h], rbp
0x180016ce2  mov     rcx, rdi; pvCallbackContext
0x180016ce5  cmp     [rdi+270h], ebp
0x180016ceb  jnz     short loc_180016CF4
0x180016ced  call    DavFsFinalizeTheDavCallBackContext
0x180016cf2  jmp     short loc_180016CFB
0x180016cf4  call    DavFsCreate
0x180016cf9  mov     esi, eax
0x180016cfb  lea     rcx, [rdi+1F0h]
0x180016d02  cmp     [rcx], rbp
0x180016d05  jz      short loc_180016D0C
0x180016d07  call    DavFinalizePerUserEntry
0x180016d0c  mov     eax, esi
0x180016d0e  add     rsp, 28h
0x180016d12  pop     r14
0x180016d14  pop     r12
0x180016d16  pop     rdi
0x180016d17  pop     rsi
0x180016d18  pop     rbp
0x180016d19  pop     rbx
0x180016d1a  retn
```
