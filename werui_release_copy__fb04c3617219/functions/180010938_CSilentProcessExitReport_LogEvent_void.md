# CSilentProcessExitReport::LogEvent(void)

- ea: `0x180010938`
- end: `0x180010cc3`
- name: `?LogEvent@CSilentProcessExitReport@@AEAAJXZ`
- size: `907`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180010234`

## callees

- `0x180003038`
- `0x18000322c`
- `0x1800035dc`
- `0x180003604`
- `0x180003fe4`
- `0x180005718`
- `0x180005c58`
- `0x180005ddc`
- `0x18000983c`
- `0x180010938`
- `0x180013814`
- `0x180013948`
- `0x180013adc`
- `0x180016c1e`
- `0x180016c50`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x1800109e8`
- `ADVAPI32!OpenProcessToken` at `0x1800109e8`
- `ADVAPI32!GetTokenInformation` at `0x180010a5f`
- `ADVAPI32!GetTokenInformation` at `0x180010aad`
- `ADVAPI32!GetTokenInformation` at `0x180010a5f`
- `ADVAPI32!GetTokenInformation` at `0x180010aad`
- `KERNEL32!GetProcessTimes` at `0x180010bbc`
- `KERNEL32!GetProcessTimes` at `0x180010bbc`
- `KERNEL32!GetLastError` at `0x1800109fc`
- `KERNEL32!GetLastError` at `0x180010a6d`
- `KERNEL32!GetLastError` at `0x180010abb`
- `KERNEL32!GetLastError` at `0x180010b2a`
- `KERNEL32!GetLastError` at `0x1800109fc`
- `KERNEL32!GetLastError` at `0x180010a6d`
- `KERNEL32!GetLastError` at `0x180010abb`
- `KERNEL32!GetLastError` at `0x180010b2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSilentProcessExitReport::LogEvent(HANDLE *this)
{
  __int64 v1; // r9
  __int64 v3; // r9
  __int64 v4; // r9
  void *v5; // rsi
  void **v6; // rax
  signed int LastError; // eax
  signed int v8; // eax
  DWORD v9; // eax
  unsigned int v10; // eax
  HANDLE v11; // rcx
  int v12; // edx
  int v13; // ecx
  __int64 v14; // r8
  signed int v15; // eax
  signed int v16; // ebx
  DWORD TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME CreationTime; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME UserTime; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME KernelTime; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ExitTime; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v24[8]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v25; // [rsp+80h] [rbp-80h]
  unsigned __int16 v26[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v27; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v28[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v29; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v30[32]; // [rsp+D0h] [rbp-30h] BYREF

  v1 = *((unsigned int *)this + 3);
  *(_OWORD *)v26 = 0;
  v27 = 0;
  StringCchPrintfW(v26, 0x10u, L"%u", v1);
  v3 = *((unsigned int *)this + 1);
  *(_OWORD *)v24 = 0;
  v25 = 0;
  StringCchPrintfW(v24, 0x10u, L"%u", v3);
  v4 = *(unsigned int *)this;
  *(_OWORD *)v28 = 0;
  v29 = 0;
  StringCchPrintfW(v28, 0x10u, L"%u", v4);
  TokenHandle = 0;
  v5 = 0;
  v6 = (void **)tlx::replace<tlx::file_handle_traits>(&TokenHandle);
  if ( !OpenProcessToken(this[2], 0x20008u, v6) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        &WPP_0b9f8713f655331c3edd713292668335_Traceguids,
        (unsigned int)LastError);
  }
  if ( (unsigned __int64)TokenHandle + 1 > 1 )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    {
      v9 = GetLastError();
      v10 = ERROR_HR_FROM_WIN32(v9);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_0b9f8713f655331c3edd713292668335_Traceguids, v10);
    }
    else
    {
      v5 = operator new[](TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
      if ( v5 )
      {
        if ( !GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
        {
          v8 = GetLastError();
          if ( v8 > 0 )
            v8 = (unsigned __int16)v8 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              40,
              &WPP_0b9f8713f655331c3edd713292668335_Traceguids,
              (unsigned int)v8);
          operator delete(v5);
          v5 = 0;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_0b9f8713f655331c3edd713292668335_Traceguids);
      }
    }
    tlx::unique_any<tlx::file_handle_traits>::reset(&TokenHandle, 0);
  }
  memset_0(v30, 0, sizeof(v30));
  v11 = this[3];
  CreationTime = 0;
  ExitTime = 0;
  KernelTime = 0;
  UserTime = 0;
  if ( GetProcessTimes(v11, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
    StringCchPrintfW(v30, 0x20u, L"%016I64x", CreationTime);
  if ( *((_DWORD *)this + 1) == *(_DWORD *)this )
  {
    if ( (Microsoft_Windows_ProcessExitMonitorEnableBits & 1) == 0 )
    {
      v16 = 0;
      goto LABEL_34;
    }
    v15 = McTemplateU0zzzz_EventWriteTransfer(
            v13,
            v12,
            (unsigned int)this[4],
            (unsigned int)v26,
            (__int64)v30,
            (__int64)v24);
  }
  else
  {
    if ( (Microsoft_Windows_ProcessExitMonitorEnableBits & 1) == 0 )
    {
      v16 = 0;
      goto LABEL_37;
    }
    v15 = McTemplateU0zzzzzz_EventWriteTransfer(
            v13,
            v12,
            (unsigned int)this[4],
            (unsigned int)this[8],
            (__int64)v26,
            (__int64)v30,
            (__int64)v24,
            (__int64)v28);
  }
  v16 = v15;
LABEL_34:
  if ( v16 > 0 )
    v16 = (unsigned __int16)v16 | 0x80070000;
LABEL_37:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_DDd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((unsigned int *)this + 1),
      v14,
      *(unsigned int *)this,
      *((_DWORD *)this + 1),
      v16);
  operator delete(v5);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&TokenHandle);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180010938  mov     [rsp-8+arg_8], rbx
0x18001093d  mov     [rsp-8+arg_10], rsi
0x180010942  push    rbp
0x180010943  push    rdi
0x180010944  push    r15
0x180010946  lea     rbp, [rsp-20h]
0x18001094b  sub     rsp, 120h
0x180010952  mov     rax, cs:__security_cookie
0x180010959  xor     rax, rsp
0x18001095c  mov     [rbp+30h+var_20], rax
0x180010960  mov     r9d, [rcx+0Ch]
0x180010964  lea     rsi, aU; "%u"
0x18001096b  xorps   xmm0, xmm0
0x18001096e  mov     rdi, rcx
0x180010971  mov     ebx, 10h
0x180010976  lea     rcx, [rbp+30h+var_A0]; unsigned __int16 *
0x18001097a  mov     r8, rsi; unsigned __int16 *
0x18001097d  mov     edx, ebx; unsigned __int64
0x18001097f  movups  xmmword ptr [rbp+30h+var_A0], xmm0
0x180010983  movups  [rbp+30h+var_90], xmm0
0x180010987  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001098c  mov     r9d, [rdi+4]
0x180010990  lea     rcx, [rsp+130h+var_C0]; unsigned __int16 *
0x180010995  xorps   xmm0, xmm0
0x180010998  mov     r8, rsi; unsigned __int16 *
0x18001099b  mov     edx, ebx; unsigned __int64
0x18001099d  movups  xmmword ptr [rsp+130h+var_C0], xmm0
0x1800109a2  movups  [rbp+30h+var_B0], xmm0
0x1800109a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800109ab  mov     r9d, [rdi]
0x1800109ae  lea     rcx, [rbp+30h+var_80]; unsigned __int16 *
0x1800109b2  xorps   xmm0, xmm0
0x1800109b5  mov     r8, rsi; unsigned __int16 *
0x1800109b8  mov     edx, ebx; unsigned __int64
0x1800109ba  movups  xmmword ptr [rbp+30h+var_80], xmm0
0x1800109be  movups  [rbp+30h+var_70], xmm0
0x1800109c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800109c7  lea     rcx, [rsp+130h+TokenHandle]
0x1800109cc  mov     [rsp+130h+TokenHandle], 0
0x1800109d5  xor     esi, esi
0x1800109d7  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800109dc  mov     rcx, [rdi+10h]; ProcessHandle
0x1800109e0  mov     r8, rax; TokenHandle
0x1800109e3  mov     edx, 20008h; DesiredAccess
0x1800109e8  call    cs:__imp_OpenProcessToken
0x1800109ee  lea     ebx, [rsi+1]
0x1800109f1  lea     r15, WPP_GLOBAL_Control
0x1800109f8  test    eax, eax
0x1800109fa  jnz     short loc_180010A37
0x1800109fc  call    cs:__imp_GetLastError
0x180010a02  test    eax, eax
0x180010a04  jle     short loc_180010A0E
0x180010a06  movzx   eax, ax
0x180010a09  or      eax, 80070000h
0x180010a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a15  cmp     rcx, r15
0x180010a18  jz      short loc_180010A37
0x180010a1a  test    [rcx+1Ch], bl
0x180010a1d  jz      short loc_180010A37
0x180010a1f  mov     rcx, [rcx+10h]
0x180010a23  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x180010a2a  mov     edx, 27h ; '''
0x180010a2f  mov     r9d, eax
0x180010a32  call    WPP_SF_d
0x180010a37  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x180010a3c  lea     rax, [rcx+1]
0x180010a40  cmp     rax, rbx
0x180010a43  jbe     loc_180010B6C
0x180010a49  lea     rax, [rsp+130h+TokenInformationLength]
0x180010a4e  mov     [rsp+130h+TokenInformationLength], esi
0x180010a52  xor     r9d, r9d; TokenInformationLength
0x180010a55  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x180010a5a  xor     r8d, r8d; TokenInformation
0x180010a5d  mov     edx, ebx; TokenInformationClass
0x180010a5f  call    cs:__imp_GetTokenInformation
0x180010a65  test    eax, eax
0x180010a67  jnz     loc_180010B2A
0x180010a6d  call    cs:__imp_GetLastError
0x180010a73  cmp     eax, 7Ah ; 'z'
0x180010a76  jnz     loc_180010B2A
0x180010a7c  mov     ecx, [rsp+130h+TokenInformationLength]; unsigned __int64
0x180010a80  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010a87  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180010a8c  mov     rsi, rax
0x180010a8f  test    rax, rax
0x180010a92  jz      short loc_180010B02
0x180010a94  mov     r9d, [rsp+130h+TokenInformationLength]; TokenInformationLength
0x180010a99  lea     rax, [rsp+130h+TokenInformationLength]
0x180010a9e  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x180010aa3  mov     r8, rsi; TokenInformation
0x180010aa6  mov     edx, ebx; TokenInformationClass
0x180010aa8  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x180010aad  call    cs:__imp_GetTokenInformation
0x180010ab3  test    eax, eax
0x180010ab5  jnz     loc_180010B60
0x180010abb  call    cs:__imp_GetLastError
0x180010ac1  test    eax, eax
0x180010ac3  jle     short loc_180010ACD
0x180010ac5  movzx   eax, ax
0x180010ac8  or      eax, 80070000h
0x180010acd  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ad4  cmp     rcx, r15
0x180010ad7  jz      short loc_180010AF6
0x180010ad9  test    [rcx+1Ch], bl
0x180010adc  jz      short loc_180010AF6
0x180010ade  mov     rcx, [rcx+10h]
0x180010ae2  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x180010ae9  mov     edx, 28h ; '('
0x180010aee  mov     r9d, eax
0x180010af1  call    WPP_SF_d
0x180010af6  mov     rcx, rsi; Block
0x180010af9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010afe  xor     esi, esi
0x180010b00  jmp     short loc_180010B60
0x180010b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b09  cmp     rcx, r15
0x180010b0c  jz      short loc_180010B60
0x180010b0e  test    [rcx+1Ch], bl
0x180010b11  jz      short loc_180010B60
0x180010b13  mov     rcx, [rcx+10h]
0x180010b17  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x180010b1e  mov     edx, 29h ; ')'
0x180010b23  call    WPP_SF_
0x180010b28  jmp     short loc_180010B60
0x180010b2a  call    cs:__imp_GetLastError
0x180010b30  mov     ecx, eax; unsigned int
0x180010b32  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180010b37  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b3e  cmp     rcx, r15
0x180010b41  jz      short loc_180010B60
0x180010b43  test    [rcx+1Ch], bl
0x180010b46  jz      short loc_180010B60
0x180010b48  mov     rcx, [rcx+10h]
0x180010b4c  lea     r8, WPP_0b9f8713f655331c3edd713292668335_Traceguids
0x180010b53  mov     edx, 2Ah ; '*'
0x180010b58  mov     r9d, eax
0x180010b5b  call    WPP_SF_d
0x180010b60  xor     edx, edx
0x180010b62  lea     rcx, [rsp+130h+TokenHandle]
0x180010b67  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180010b6c  xor     edx, edx; Val
0x180010b6e  lea     rcx, [rbp+30h+var_60]; void *
0x180010b72  lea     r8d, [rdx+40h]; Size
0x180010b76  call    memset_0
0x180010b7b  mov     rcx, [rdi+18h]; hProcess
0x180010b7f  lea     rax, [rsp+130h+UserTime]
0x180010b84  lea     r9, [rsp+130h+KernelTime]; lpKernelTime
0x180010b89  mov     [rsp+130h+ReturnLength], rax; lpUserTime
0x180010b8e  lea     r8, [rsp+130h+ExitTime]; lpExitTime
0x180010b93  mov     qword ptr [rsp+130h+CreationTime.dwLowDateTime], 0
0x180010b9c  lea     rdx, [rsp+130h+CreationTime]; lpCreationTime
0x180010ba1  mov     qword ptr [rsp+130h+ExitTime.dwLowDateTime], 0
0x180010baa  mov     qword ptr [rsp+130h+KernelTime.dwLowDateTime], 0
0x180010bb3  mov     qword ptr [rsp+130h+UserTime.dwLowDateTime], 0
0x180010bbc  call    cs:__imp_GetProcessTimes
0x180010bc2  test    eax, eax
0x180010bc4  jz      short loc_180010BE0
0x180010bc6  mov     r9, qword ptr [rsp+130h+CreationTime.dwLowDateTime]
0x180010bcb  lea     r8, a016i64x; "%016I64x"
0x180010bd2  mov     edx, 20h ; ' '; unsigned __int64
0x180010bd7  lea     rcx, [rbp+30h+var_60]; unsigned __int16 *
0x180010bdb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010be0  mov     eax, [rdi]
0x180010be2  cmp     [rdi+4], eax
0x180010be5  jnz     short loc_180010C15
0x180010be7  test    cs:Microsoft_Windows_ProcessExitMonitorEnableBits, bl
0x180010bed  jz      short loc_180010C11
0x180010bef  mov     r8, [rdi+20h]
0x180010bf3  lea     rax, [rsp+130h+var_C0]
0x180010bf8  mov     [rsp+130h+var_108], rax
0x180010bfd  lea     r9, [rbp+30h+var_A0]
0x180010c01  lea     rax, [rbp+30h+var_60]
0x180010c05  mov     [rsp+130h+ReturnLength], rax
0x180010c0a  call    McTemplateU0zzzz_EventWriteTransfer
0x180010c0f  jmp     short loc_180010C4F
0x180010c11  xor     ebx, ebx
0x180010c13  jmp     short loc_180010C51
0x180010c15  test    cs:Microsoft_Windows_ProcessExitMonitorEnableBits, bl
0x180010c1b  jz      short loc_180010C60
0x180010c1d  mov     r9, [rdi+40h]
0x180010c21  lea     rax, [rbp+30h+var_80]
0x180010c25  mov     r8, [rdi+20h]
0x180010c29  mov     [rsp+130h+var_F8], rax
0x180010c2e  lea     rax, [rsp+130h+var_C0]
0x180010c33  mov     [rsp+130h+var_100], rax
0x180010c38  lea     rax, [rbp+30h+var_60]
0x180010c3c  mov     [rsp+130h+var_108], rax
0x180010c41  lea     rax, [rbp+30h+var_A0]
0x180010c45  mov     [rsp+130h+ReturnLength], rax
0x180010c4a  call    McTemplateU0zzzzzz_EventWriteTransfer
0x180010c4f  mov     ebx, eax
0x180010c51  test    ebx, ebx
0x180010c53  jle     short loc_180010C62
0x180010c55  movzx   ebx, bx
0x180010c58  or      ebx, 80070000h
0x180010c5e  jmp     short loc_180010C62
0x180010c60  xor     ebx, ebx
0x180010c62  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c69  cmp     rcx, r15
0x180010c6c  jz      short loc_180010C8B
0x180010c6e  test    byte ptr [rcx+1Ch], 4
0x180010c72  jz      short loc_180010C8B
0x180010c74  mov     edx, [rdi+4]
0x180010c77  mov     r9d, [rdi]
0x180010c7a  mov     rcx, [rcx+10h]
0x180010c7e  mov     dword ptr [rsp+130h+var_108], ebx
0x180010c82  mov     dword ptr [rsp+130h+ReturnLength], edx
0x180010c86  call    WPP_SF_DDd
0x180010c8b  mov     rcx, rsi; Block
0x180010c8e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010c93  lea     rcx, [rsp+130h+TokenHandle]
0x180010c98  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180010c9d  mov     eax, ebx
0x180010c9f  mov     rcx, [rbp+30h+var_20]
0x180010ca3  xor     rcx, rsp; StackCookie
0x180010ca6  call    __security_check_cookie
0x180010cab  lea     r11, [rsp+130h+var_10]
0x180010cb3  mov     rbx, [r11+28h]
0x180010cb7  mov     rsi, [r11+30h]
0x180010cbb  mov     rsp, r11
0x180010cbe  pop     r15
0x180010cc0  pop     rdi
0x180010cc1  pop     rbp
0x180010cc2  retn
```
