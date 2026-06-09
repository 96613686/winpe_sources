# WsDeleteLinkedConnection

- ea: `0x180008734`
- end: `0x180008898`
- name: `WsDeleteLinkedConnection`
- size: `356`
- prototype: `__int64 __fastcall(void *, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002988c`

## callees

- `0x180008734`
- `0x1800088a0`
- `0x180008950`
- `0x18000dd94`
- `0x18001e420`
- `0x18002a4ec`
- `0x18002ecc0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800087fa`
- `RPCRT4!RpcImpersonateClient` at `0x1800087fa`

## pseudocode

```c
__int64 __fastcall WsDeleteLinkedConnection(void *a1, const wchar_t *a2)
{
  int v2; // ebx
  __int64 v4; // rcx
  __int64 v5; // r9
  const wchar_t *v6; // r10
  wchar_t *v7; // rax
  wchar_t *v8; // rcx
  size_t v9; // rdx
  RPC_STATUS v11; // eax
  int v12; // r8d
  unsigned int v13; // ebx
  size_t pcbLength[2]; // [rsp+40h] [rbp-B8h] BYREF
  int v15; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+54h] [rbp-A4h]
  int v17; // [rsp+64h] [rbp-94h]
  wchar_t pszDest[60]; // [rsp+68h] [rbp-90h] BYREF

  v2 = 0;
  pcbLength[0] = 0;
  if ( a2 )
  {
    v4 = 2147483646;
    v5 = 32;
    v6 = L"\\??\\";
    v7 = pszDest;
    do
    {
      if ( !v4 )
        break;
      if ( !*v6 )
        break;
      *v7++ = *v6++;
      --v4;
      --v5;
    }
    while ( v5 );
    v8 = v7 - 1;
    if ( v5 )
      v8 = v7;
    *v8 = 0;
    if ( StringCchCatW(pszDest, 0x20u, a2) < 0 )
      return 2123;
    StringCbLengthW(pszDest, v9, pcbLength);
    v2 = pcbLength[0];
  }
  v17 = v2;
  v15 = 4;
  v16 = 6;
  v11 = RpcImpersonateClient(0);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v12, (unsigned int)"unknown", 0, v11);
    }
    return 5;
  }
  else
  {
    v13 = WsRedirFsControl(a1, 0x1401D8u, &v15, v2 + 36, 0, 0);
    WsRevertToSelf2(0, 0);
    return v13;
  }
}

```

## disassembly

```asm
0x180008734  mov     [rsp+arg_10], rbx
0x180008739  mov     [rsp+arg_18], rsi
0x18000873e  push    rdi
0x18000873f  sub     rsp, 0F0h
0x180008746  mov     rax, cs:__security_cookie
0x18000874d  xor     rax, rsp
0x180008750  mov     [rsp+0F8h+var_18], rax
0x180008758  xor     esi, esi
0x18000875a  mov     r8, rdx; pszSrc
0x18000875d  mov     ebx, esi
0x18000875f  mov     rdi, rcx
0x180008762  mov     [rsp+0F8h+pcbLength], rbx
0x180008767  test    rdx, rdx
0x18000876a  jz      short loc_1800087E3
0x18000876c  lea     r11d, [rsi+20h]
0x180008770  mov     ecx, 7FFFFFFEh
0x180008775  mov     r9d, r11d
0x180008778  lea     r10, asc_18003AA90; "\\??\\"
0x18000877f  lea     rax, [rsp+0F8h+pszDest]
0x180008784  test    rcx, rcx
0x180008787  jz      short loc_1800087A6
0x180008789  movzx   edx, word ptr [r10]
0x18000878d  test    dx, dx
0x180008790  jz      short loc_1800087A6
0x180008792  mov     [rax], dx
0x180008795  add     r10, 2
0x180008799  add     rax, 2
0x18000879d  dec     rcx
0x1800087a0  sub     r9, 1
0x1800087a4  jnz     short loc_180008784
0x1800087a6  test    r9, r9
0x1800087a9  lea     rcx, [rax-2]
0x1800087ad  mov     rdx, r11; cchDest
0x1800087b0  cmovnz  rcx, rax
0x1800087b4  mov     [rcx], si
0x1800087b7  lea     rcx, [rsp+0F8h+pszDest]; pszDest
0x1800087bc  call    StringCchCatW
0x1800087c1  test    eax, eax
0x1800087c3  jns     short loc_1800087CF
0x1800087c5  mov     eax, 84Bh
0x1800087ca  jmp     loc_180008873
0x1800087cf  lea     r8, [rsp+0F8h+pcbLength]; pcbLength
0x1800087d4  lea     rcx, [rsp+0F8h+pszDest]; psz
0x1800087d9  call    StringCbLengthW
0x1800087de  mov     rbx, [rsp+0F8h+pcbLength]
0x1800087e3  xor     ecx, ecx; BindingHandle
0x1800087e5  mov     [rsp+0F8h+var_94], ebx
0x1800087e9  mov     [rsp+0F8h+var_A8], 4
0x1800087f1  mov     [rsp+0F8h+var_A4], 6
0x1800087fa  call    cs:__imp_RpcImpersonateClient
0x180008800  test    eax, eax
0x180008802  jz      short loc_180008847
0x180008804  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000880b  lea     rdx, WPP_GLOBAL_Control
0x180008812  cmp     rcx, rdx
0x180008815  jz      short loc_180008840
0x180008817  test    byte ptr [rcx+1Ch], 4
0x18000881b  jz      short loc_180008840
0x18000881d  cmp     byte ptr [rcx+19h], 1
0x180008821  jb      short loc_180008840
0x180008823  mov     rcx, [rcx+10h]
0x180008827  lea     r9, aUnknown; "unknown"
0x18000882e  mov     [rsp+0F8h+var_D0], eax
0x180008832  mov     edx, 0Ah
0x180008837  mov     dword ptr [rsp+0F8h+var_D8], esi
0x18000883b  call    WPP_SF_sdL
0x180008840  mov     eax, 5
0x180008845  jmp     short loc_180008873
0x180008847  lea     r9d, [rbx+24h]
0x18000884b  mov     [rsp+0F8h+var_D0], esi
0x18000884f  lea     r8, [rsp+0F8h+var_A8]
0x180008854  mov     [rsp+0F8h+var_D8], rsi
0x180008859  mov     edx, 1401D8h
0x18000885e  mov     rcx, rdi
0x180008861  call    WsRedirFsControl
0x180008866  xor     edx, edx
0x180008868  xor     ecx, ecx
0x18000886a  mov     ebx, eax
0x18000886c  call    WsRevertToSelf2
0x180008871  mov     eax, ebx
0x180008873  mov     rcx, [rsp+0F8h+var_18]
0x18000887b  xor     rcx, rsp; StackCookie
0x18000887e  call    __security_check_cookie
0x180008883  lea     r11, [rsp+0F8h+var_8]
0x18000888b  mov     rbx, [r11+20h]
0x18000888f  mov     rsi, [r11+28h]
0x180008893  mov     rsp, r11
0x180008896  pop     rdi
0x180008897  retn
```
