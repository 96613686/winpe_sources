# WsCreateLinkedConnection

- ea: `0x180008c3c`
- end: `0x180008dd5`
- name: `WsCreateLinkedConnection`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180001750`

## callees

- `0x180008c3c`
- `0x180008f50`
- `0x18000bff8`
- `0x18000eb1c`
- `0x18001fbd0`
- `0x18002ca68`
- `0x180031878`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180008c89`
- `RPCRT4!RpcImpersonateClient` at `0x180008c89`
- `RPCRT4!RpcRevertToSelf` at `0x180008cc2`
- `RPCRT4!RpcRevertToSelf` at `0x180008cc2`

## pseudocode

```c
__int64 __fastcall WsCreateLinkedConnection(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // ebx
  RPC_STATUS v6; // eax
  int v7; // r8d
  unsigned int v8; // ebx
  RPC_STATUS v9; // eax
  int v10; // r8d
  STRSAFE_LPCWSTR v12; // r11
  size_t v13; // rdx
  size_t pcbLength[2]; // [rsp+40h] [rbp-C8h] BYREF
  int v15; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+54h] [rbp-B4h]
  int v17; // [rsp+64h] [rbp-A4h]
  wchar_t pszDest[60]; // [rsp+68h] [rbp-A0h] BYREF

  v3 = 0;
  pcbLength[0] = 0;
  if ( a2 )
  {
    StringCchCopyW(pszDest, 0x20u, L"\\??\\");
    if ( StringCchCatW(pszDest, 0x20u, v12) < 0 )
      return 2123;
    StringCbLengthW(pszDest, v13, pcbLength);
    v3 = pcbLength[0];
  }
  v17 = v3;
  v15 = 3;
  v16 = 6;
  v6 = RpcImpersonateClient(0);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v7, (unsigned int)"unknown", 0, v6);
    }
    return 5;
  }
  else
  {
    v8 = WsRedirFsControl(a1, 1311192, &v15, (unsigned int)(v3 + 36), a3, 8);
    v9 = RpcRevertToSelf();
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v10, (unsigned int)"unknown", 0, v9);
      }
      __fastfail(7u);
    }
    return v8;
  }
}

```

## disassembly

```asm
0x180008c3c  push    rbx
0x180008c3e  push    rsi
0x180008c3f  push    rdi
0x180008c40  sub     rsp, 0F0h
0x180008c47  mov     rax, cs:__security_cookie
0x180008c4e  xor     rax, rsp
0x180008c51  mov     [rsp+108h+var_28], rax
0x180008c59  xor     ebx, ebx
0x180008c5b  mov     rsi, r8
0x180008c5e  mov     [rsp+108h+pcbLength], rbx
0x180008c63  mov     r11, rdx
0x180008c66  mov     rdi, rcx
0x180008c69  test    rdx, rdx
0x180008c6c  jnz     loc_180008CF4
0x180008c72  xor     ecx, ecx; BindingHandle
0x180008c74  mov     [rsp+108h+var_A4], ebx
0x180008c78  mov     [rsp+108h+var_B8], 3
0x180008c80  mov     [rsp+108h+var_B4], 6
0x180008c89  call    cs:__imp_RpcImpersonateClient
0x180008c90  nop     dword ptr [rax+rax+00h]
0x180008c95  test    eax, eax
0x180008c97  jnz     loc_180008D3F
0x180008c9d  lea     r9d, [rbx+24h]
0x180008ca1  mov     [rsp+108h+var_E0], 8
0x180008ca9  lea     r8, [rsp+108h+var_B8]
0x180008cae  mov     [rsp+108h+var_E8], rsi
0x180008cb3  mov     edx, 1401D8h
0x180008cb8  mov     rcx, rdi
0x180008cbb  call    WsRedirFsControl
0x180008cc0  mov     ebx, eax
0x180008cc2  call    cs:__imp_RpcRevertToSelf
0x180008cc9  nop     dword ptr [rax+rax+00h]
0x180008cce  test    eax, eax
0x180008cd0  jnz     loc_180008D89
0x180008cd6  mov     eax, ebx
0x180008cd8  mov     rcx, [rsp+108h+var_28]
0x180008ce0  xor     rcx, rsp; StackCookie
0x180008ce3  call    __security_check_cookie
0x180008ce8  add     rsp, 0F0h
0x180008cef  pop     rdi
0x180008cf0  pop     rsi
0x180008cf1  pop     rbx
0x180008cf2  retn
0x180008cf4  mov     ebx, 20h ; ' '
0x180008cf9  lea     r8, asc_18003DA90; "\\??\\"
0x180008d00  mov     edx, ebx; cchDest
0x180008d02  lea     rcx, [rsp+108h+pszDest]; pszDest
0x180008d07  call    StringCchCopyW
0x180008d0c  mov     r8, r11; pszSrc
0x180008d0f  lea     rcx, [rsp+108h+pszDest]; pszDest
0x180008d14  mov     edx, ebx; cchDest
0x180008d16  call    StringCchCatW
0x180008d1b  test    eax, eax
0x180008d1d  jns     short loc_180008D26
0x180008d1f  mov     eax, 84Bh
0x180008d24  jmp     short loc_180008CD8
0x180008d26  lea     r8, [rsp+108h+pcbLength]; pcbLength
0x180008d2b  lea     rcx, [rsp+108h+pszDest]; psz
0x180008d30  call    StringCbLengthW
0x180008d35  mov     rbx, [rsp+108h+pcbLength]
0x180008d3a  jmp     loc_180008C72
0x180008d3f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180008d46  lea     rdx, WPP_GLOBAL_Control
0x180008d4d  cmp     rcx, rdx
0x180008d50  jz      short loc_180008D7F
0x180008d52  test    byte ptr [rcx+1Ch], 4
0x180008d56  jz      short loc_180008D7F
0x180008d58  cmp     byte ptr [rcx+19h], 1
0x180008d5c  jb      short loc_180008D7F
0x180008d5e  mov     rcx, [rcx+10h]
0x180008d62  lea     r9, aUnknown; "unknown"
0x180008d69  mov     [rsp+108h+var_E0], eax
0x180008d6d  mov     edx, 0Ah
0x180008d72  mov     dword ptr [rsp+108h+var_E8], 0
0x180008d7a  call    WPP_SF_sdL
0x180008d7f  mov     eax, 5
0x180008d84  jmp     loc_180008CD8
0x180008d89  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180008d90  lea     rdx, WPP_GLOBAL_Control
0x180008d97  cmp     rcx, rdx
0x180008d9a  jz      short loc_180008DC9
0x180008d9c  test    byte ptr [rcx+1Ch], 4
0x180008da0  jz      short loc_180008DC9
0x180008da2  cmp     byte ptr [rcx+19h], 1
0x180008da6  jb      short loc_180008DC9
0x180008da8  mov     rcx, [rcx+10h]
0x180008dac  lea     r9, aUnknown; "unknown"
0x180008db3  mov     [rsp+108h+var_E0], eax
0x180008db7  mov     edx, 0Bh
0x180008dbc  mov     dword ptr [rsp+108h+var_E8], 0
0x180008dc4  call    WPP_SF_sdL
0x180008dc9  mov     ecx, 7
0x180008dce  int     29h; Win8: RtlFailFast(ecx)
0x180008dd0  jmp     loc_180008CD6
```
