# DigestSsiUpdateLogonStatistics

- ea: `0x1800298f4`
- end: `0x180029bc1`
- name: `DigestSsiUpdateLogonStatistics`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18002940c`

## callees

- `0x180011fec`
- `0x180012880`
- `0x1800185b8`
- `0x180018b18`
- `0x1800298f4`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180029987`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180029987`

## pseudocode

```c
__int64 __fastcall DigestSsiUpdateLogonStatistics(__int64 a1, int a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned int v11; // eax
  int v13; // [rsp+30h] [rbp-59h] BYREF
  __int64 v14; // [rsp+38h] [rbp-51h] BYREF
  __int64 v15; // [rsp+40h] [rbp-49h] BYREF
  struct _FILETIME *p_SystemTimeAsFileTime; // [rsp+48h] [rbp-41h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-39h] BYREF
  __int128 v18; // [rsp+58h] [rbp-31h] BYREF
  int v19; // [rsp+68h] [rbp-21h]
  __int64 *v20; // [rsp+70h] [rbp-19h]
  __int128 v21; // [rsp+80h] [rbp-9h] BYREF
  int v22; // [rsp+90h] [rbp+7h]
  __int128 *v23; // [rsp+98h] [rbp+Fh]
  __int128 v24; // [rsp+A0h] [rbp+17h]
  int v25; // [rsp+B0h] [rbp+27h]
  __int64 *v26; // [rsp+B8h] [rbp+2Fh]

  v14 = 0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    SystemTimeAsFileTime = 0;
    v13 = 0;
    v18 = 0;
    HIDWORD(v15) = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v22 = 1;
    v23 = &v18;
    v21 = SSIGUID_BAD_PASSWORD_COUNT;
    LODWORD(v18) = 4;
    *((_QWORD *)&v18 + 1) = &v13;
    v25 = 1;
    v26 = &v15;
    v24 = SSIGUID_LAST_LOGON;
    LODWORD(v15) = 8;
    p_SystemTimeAsFileTime = &SystemTimeAsFileTime;
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int128 *, __int64 *))(*(_QWORD *)(*(_QWORD *)(a1 + 624)
                                                                                               + 24LL)
                                                                                   + 56LL))(
           *(_QWORD *)(a1 + 632),
           0,
           2,
           &v21,
           &v14);
    v6 = v5;
    if ( v5 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v5);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      v7 = v14;
      v6 = -1073741595;
      v8 = HIDWORD(v14);
      if ( (_DWORD)v14 == 3 )
        v6 = HIDWORD(v14);
      if ( v4 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v4 + 28) & 1) != 0 )
        {
          v9 = 199;
LABEL_14:
          WPP_SF_dd(v4[2], v9, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v7, v8);
          goto LABEL_28;
        }
        goto LABEL_29;
      }
      return v6;
    }
LABEL_28:
    v4 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  if ( a2 != -1073741718 )
  {
    v6 = -1073741811;
    if ( v4 == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)v4 + 28) & 1) == 0 )
      goto LABEL_29;
    WPP_SF_d(v4[2], 202, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, 3221225485LL);
    goto LABEL_28;
  }
  v15 = 4;
  v20 = &v15;
  v13 = 1;
  p_SystemTimeAsFileTime = (struct _FILETIME *)&v13;
  v10 = *(_QWORD *)(a1 + 624);
  v18 = SSIGUID_INCREMENT_BAD_PASSWORD;
  v19 = 1;
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int128 *, __int64 *))(*(_QWORD *)(v10 + 24) + 56LL))(
          *(_QWORD *)(a1 + 632),
          0,
          1,
          &v18,
          &v14);
  v6 = v11;
  if ( !v11 )
    goto LABEL_28;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v11);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = v14;
  v6 = -1073741595;
  v8 = HIDWORD(v14);
  if ( (_DWORD)v14 == 3 )
    v6 = HIDWORD(v14);
  if ( v4 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v4 + 28) & 1) != 0 )
    {
      v9 = 201;
      goto LABEL_14;
    }
LABEL_29:
    if ( v4 != &WPP_GLOBAL_Control && *((char *)v4 + 28) < 0 )
      WPP_SF_d(v4[2], 203, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1800298f4  mov     [rsp-8+arg_8], rbx
0x1800298f9  mov     [rsp-8+arg_10], rsi
0x1800298fe  push    rbp
0x1800298ff  push    r14
0x180029901  push    r15
0x180029903  lea     rbp, [rsp-47h]
0x180029908  sub     rsp, 0D0h
0x18002990f  mov     rax, cs:__security_cookie
0x180029916  xor     rax, rsp
0x180029919  mov     [rbp+57h+var_20], rax
0x18002991d  mov     ebx, edx
0x18002991f  mov     [rbp+57h+var_A8], 0
0x180029927  mov     rsi, rcx
0x18002992a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029931  lea     r14, WPP_GLOBAL_Control
0x180029938  lea     r15, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002993f  cmp     rcx, r14
0x180029942  jz      short loc_180029962
0x180029944  test    byte ptr [rcx+1Ch], 80h
0x180029948  jz      short loc_180029962
0x18002994a  mov     rcx, [rcx+10h]
0x18002994e  mov     edx, 0C5h
0x180029953  mov     r8, r15
0x180029956  call    WPP_SF_
0x18002995b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029962  test    ebx, ebx
0x180029964  jnz     loc_180029A86
0x18002996a  xorps   xmm0, xmm0
0x18002996d  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180029975  xorps   xmm1, xmm1
0x180029978  mov     [rbp+57h+var_B0], ebx
0x18002997b  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002997f  movups  [rbp+57h+var_88], xmm0
0x180029983  movups  [rbp+57h+var_A0], xmm1
0x180029987  call    cs:__imp_GetSystemTimeAsFileTime
0x18002998d  movups  xmm0, cs:SSIGUID_BAD_PASSWORD_COUNT
0x180029994  mov     [rbp+57h+var_50], 1
0x18002999b  lea     rax, [rbp+57h+var_88]
0x18002999f  mov     [rbp+57h+var_48], rax
0x1800299a3  lea     rcx, [rbp+57h+var_A8]
0x1800299a7  movdqu  [rbp+57h+var_60], xmm0
0x1800299ac  mov     dword ptr [rbp+57h+var_88], 4
0x1800299b3  lea     rax, [rbp+57h+var_B0]
0x1800299b7  movups  xmm0, cs:SSIGUID_LAST_LOGON
0x1800299be  mov     qword ptr [rbp+57h+var_88+8], rax
0x1800299c2  lea     r9, [rbp+57h+var_60]
0x1800299c6  mov     [rbp+57h+var_30], 1
0x1800299cd  lea     rax, [rbp+57h+var_A0]
0x1800299d1  mov     [rbp+57h+var_28], rax
0x1800299d5  lea     r8d, [rbx+2]
0x1800299d9  movdqu  [rbp+57h+var_40], xmm0
0x1800299de  mov     dword ptr [rbp+57h+var_A0], 8
0x1800299e5  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x1800299e9  mov     qword ptr [rbp+57h+var_A0+8], rax
0x1800299ed  mov     rax, [rsi+270h]
0x1800299f4  mov     [rsp+0E0h+var_C0], rcx
0x1800299f9  mov     rcx, [rsi+278h]
0x180029a00  mov     rdx, [rax+18h]
0x180029a04  mov     rax, [rdx+38h]
0x180029a08  xor     edx, edx
0x180029a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a0f  mov     ebx, eax
0x180029a11  test    eax, eax
0x180029a13  jz      loc_180029B74
0x180029a19  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a20  cmp     rcx, r14
0x180029a23  jz      short loc_180029A46
0x180029a25  test    byte ptr [rcx+1Ch], 1
0x180029a29  jz      short loc_180029A46
0x180029a2b  mov     rcx, [rcx+10h]
0x180029a2f  mov     edx, 0C6h
0x180029a34  mov     r9d, eax
0x180029a37  mov     r8, r15
0x180029a3a  call    WPP_SF_d
0x180029a3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a46  mov     r9, [rbp+57h+var_A8]
0x180029a4a  mov     ebx, 0C00000E5h
0x180029a4f  mov     eax, dword ptr [rbp+57h+var_A8+4]
0x180029a52  cmp     r9d, 3
0x180029a56  cmovz   ebx, eax
0x180029a59  cmp     rcx, r14
0x180029a5c  jz      loc_180029B9A
0x180029a62  test    byte ptr [rcx+1Ch], 1
0x180029a66  jz      loc_180029B7B
0x180029a6c  mov     edx, 0C7h
0x180029a71  mov     rcx, [rcx+10h]
0x180029a75  mov     r8, r15
0x180029a78  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180029a7c  call    WPP_SF_dd
0x180029a81  jmp     loc_180029B74
0x180029a86  cmp     ebx, 0C000006Ah
0x180029a8c  jnz     loc_180029B4D
0x180029a92  movups  xmm0, cs:SSIGUID_INCREMENT_BAD_PASSWORD
0x180029a99  mov     qword ptr [rbp+57h+var_A0], 4
0x180029aa1  lea     rax, [rbp+57h+var_A0]
0x180029aa5  mov     [rbp+57h+var_70], rax
0x180029aa9  lea     r9, [rbp+57h+var_88]
0x180029aad  mov     [rbp+57h+var_B0], 1
0x180029ab4  lea     rax, [rbp+57h+var_B0]
0x180029ab8  mov     qword ptr [rbp+57h+var_A0+8], rax
0x180029abc  xor     edx, edx
0x180029abe  mov     rax, [rsi+270h]
0x180029ac5  movdqu  [rbp+57h+var_88], xmm0
0x180029aca  mov     [rbp+57h+var_78], 1
0x180029ad1  lea     r8d, [rdx+1]
0x180029ad5  mov     rcx, [rax+18h]
0x180029ad9  mov     rax, [rcx+38h]
0x180029add  lea     rcx, [rbp+57h+var_A8]
0x180029ae1  mov     [rsp+0E0h+var_C0], rcx
0x180029ae6  mov     rcx, [rsi+278h]
0x180029aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029af2  mov     ebx, eax
0x180029af4  test    eax, eax
0x180029af6  jz      short loc_180029B74
0x180029af8  mov     rcx, cs:WPP_GLOBAL_Control
0x180029aff  cmp     rcx, r14
0x180029b02  jz      short loc_180029B25
0x180029b04  test    byte ptr [rcx+1Ch], 1
0x180029b08  jz      short loc_180029B25
0x180029b0a  mov     rcx, [rcx+10h]
0x180029b0e  mov     edx, 0C8h
0x180029b13  mov     r9d, eax
0x180029b16  mov     r8, r15
0x180029b19  call    WPP_SF_d
0x180029b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b25  mov     r9, [rbp+57h+var_A8]
0x180029b29  mov     ebx, 0C00000E5h
0x180029b2e  mov     eax, dword ptr [rbp+57h+var_A8+4]
0x180029b31  cmp     r9d, 3
0x180029b35  cmovz   ebx, eax
0x180029b38  cmp     rcx, r14
0x180029b3b  jz      short loc_180029B9A
0x180029b3d  test    byte ptr [rcx+1Ch], 1
0x180029b41  jz      short loc_180029B7B
0x180029b43  mov     edx, 0C9h
0x180029b48  jmp     loc_180029A71
0x180029b4d  mov     ebx, 0C000000Dh
0x180029b52  cmp     rcx, r14
0x180029b55  jz      short loc_180029B9A
0x180029b57  test    byte ptr [rcx+1Ch], 1
0x180029b5b  jz      short loc_180029B7B
0x180029b5d  mov     rcx, [rcx+10h]
0x180029b61  mov     edx, 0CAh
0x180029b66  mov     r9d, 0C000000Dh
0x180029b6c  mov     r8, r15
0x180029b6f  call    WPP_SF_d
0x180029b74  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b7b  cmp     rcx, r14
0x180029b7e  jz      short loc_180029B9A
0x180029b80  test    byte ptr [rcx+1Ch], 80h
0x180029b84  jz      short loc_180029B9A
0x180029b86  mov     rcx, [rcx+10h]
0x180029b8a  mov     edx, 0CBh
0x180029b8f  mov     r9d, ebx
0x180029b92  mov     r8, r15
0x180029b95  call    WPP_SF_d
0x180029b9a  mov     eax, ebx
0x180029b9c  mov     rcx, [rbp+57h+var_20]
0x180029ba0  xor     rcx, rsp; StackCookie
0x180029ba3  call    __security_check_cookie
0x180029ba8  lea     r11, [rsp+0E0h+var_10]
0x180029bb0  mov     rbx, [r11+28h]
0x180029bb4  mov     rsi, [r11+30h]
0x180029bb8  mov     rsp, r11
0x180029bbb  pop     r15
0x180029bbd  pop     r14
0x180029bbf  pop     rbp
0x180029bc0  retn
```
