# WsDeleteLinkedConnection

- ea: `0x180008ddc`
- end: `0x180008f47`
- name: `WsDeleteLinkedConnection`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002bd5c`

## callees

- `0x180008ddc`
- `0x180008f50`
- `0x180009010`
- `0x18000eb1c`
- `0x18001fbd0`
- `0x18002ca68`
- `0x180031878`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180008ea2`
- `RPCRT4!RpcImpersonateClient` at `0x180008ea2`

## pseudocode

```c
__int64 __fastcall WsDeleteLinkedConnection(__int64 a1, const wchar_t *a2)
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
    v13 = WsRedirFsControl(a1, 1311192, &v15, (unsigned int)(v2 + 36), 0, 0);
    WsRevertToSelf2(0, 0);
    return v13;
  }
}

```

## disassembly

```asm
0x180008ddc  mov     [rsp+arg_10], rbx
0x180008de1  mov     [rsp+arg_18], rsi
0x180008de6  push    rdi
0x180008de7  sub     rsp, 0F0h
0x180008dee  mov     rax, cs:__security_cookie
0x180008df5  xor     rax, rsp
0x180008df8  mov     [rsp+0F8h+var_18], rax
0x180008e00  xor     esi, esi
0x180008e02  mov     r8, rdx; pszSrc
0x180008e05  mov     ebx, esi
0x180008e07  mov     rdi, rcx
0x180008e0a  mov     [rsp+0F8h+pcbLength], rbx
0x180008e0f  test    rdx, rdx
0x180008e12  jz      short loc_180008E8B
0x180008e14  lea     r11d, [rsi+20h]
0x180008e18  mov     ecx, 7FFFFFFEh
0x180008e1d  mov     r9d, r11d
0x180008e20  lea     r10, asc_18003DA90; "\\??\\"
0x180008e27  lea     rax, [rsp+0F8h+pszDest]
0x180008e2c  test    rcx, rcx
0x180008e2f  jz      short loc_180008E4E
0x180008e31  movzx   edx, word ptr [r10]
0x180008e35  test    dx, dx
0x180008e38  jz      short loc_180008E4E
0x180008e3a  mov     [rax], dx
0x180008e3d  add     r10, 2
0x180008e41  add     rax, 2
0x180008e45  dec     rcx
0x180008e48  sub     r9, 1
0x180008e4c  jnz     short loc_180008E2C
0x180008e4e  test    r9, r9
0x180008e51  lea     rcx, [rax-2]
0x180008e55  mov     rdx, r11; cchDest
0x180008e58  cmovnz  rcx, rax
0x180008e5c  mov     [rcx], si
0x180008e5f  lea     rcx, [rsp+0F8h+pszDest]; pszDest
0x180008e64  call    StringCchCatW
0x180008e69  test    eax, eax
0x180008e6b  jns     short loc_180008E77
0x180008e6d  mov     eax, 84Bh
0x180008e72  jmp     loc_180008F21
0x180008e77  lea     r8, [rsp+0F8h+pcbLength]; pcbLength
0x180008e7c  lea     rcx, [rsp+0F8h+pszDest]; psz
0x180008e81  call    StringCbLengthW
0x180008e86  mov     rbx, [rsp+0F8h+pcbLength]
0x180008e8b  xor     ecx, ecx; BindingHandle
0x180008e8d  mov     [rsp+0F8h+var_94], ebx
0x180008e91  mov     [rsp+0F8h+var_A8], 4
0x180008e99  mov     [rsp+0F8h+var_A4], 6
0x180008ea2  call    cs:__imp_RpcImpersonateClient
0x180008ea9  nop     dword ptr [rax+rax+00h]
0x180008eae  test    eax, eax
0x180008eb0  jz      short loc_180008EF5
0x180008eb2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180008eb9  lea     rdx, WPP_GLOBAL_Control
0x180008ec0  cmp     rcx, rdx
0x180008ec3  jz      short loc_180008EEE
0x180008ec5  test    byte ptr [rcx+1Ch], 4
0x180008ec9  jz      short loc_180008EEE
0x180008ecb  cmp     byte ptr [rcx+19h], 1
0x180008ecf  jb      short loc_180008EEE
0x180008ed1  mov     rcx, [rcx+10h]
0x180008ed5  lea     r9, aUnknown; "unknown"
0x180008edc  mov     [rsp+0F8h+var_D0], eax
0x180008ee0  mov     edx, 0Ah
0x180008ee5  mov     dword ptr [rsp+0F8h+var_D8], esi
0x180008ee9  call    WPP_SF_sdL
0x180008eee  mov     eax, 5
0x180008ef3  jmp     short loc_180008F21
0x180008ef5  lea     r9d, [rbx+24h]
0x180008ef9  mov     [rsp+0F8h+var_D0], esi
0x180008efd  lea     r8, [rsp+0F8h+var_A8]
0x180008f02  mov     [rsp+0F8h+var_D8], rsi
0x180008f07  mov     edx, 1401D8h
0x180008f0c  mov     rcx, rdi
0x180008f0f  call    WsRedirFsControl
0x180008f14  xor     edx, edx
0x180008f16  xor     ecx, ecx
0x180008f18  mov     ebx, eax
0x180008f1a  call    WsRevertToSelf2
0x180008f1f  mov     eax, ebx
0x180008f21  mov     rcx, [rsp+0F8h+var_18]
0x180008f29  xor     rcx, rsp; StackCookie
0x180008f2c  call    __security_check_cookie
0x180008f31  lea     r11, [rsp+0F8h+var_8]
0x180008f39  mov     rbx, [r11+20h]
0x180008f3d  mov     rsi, [r11+28h]
0x180008f41  mov     rsp, r11
0x180008f44  pop     rdi
0x180008f45  retn
```
