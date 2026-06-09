# SHGetDefaultConnectedIdentityProvider(_GUID *)

- ea: `0x1800e5344`
- end: `0x1800e5455`
- name: `?SHGetDefaultConnectedIdentityProvider@@YAJPEAU_GUID@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800cbe20`

## callees

- `0x180054130`
- `0x1800e5344`
- `0x1800e545c`
- `0x1800e54ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e53c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e53c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5408`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e5408`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1800e53ad`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1800e53e6`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1800e53ad`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x1800e53e6`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x1800e5389`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x1800e5389`

## pseudocode

```c
__int64 __fastcall SHGetDefaultConnectedIdentityProvider(struct _GUID *a1)
{
  int IdentityProviderInfoByGUID; // ebx
  _BYTE *v3; // rax
  _BYTE *v4; // rdi
  char v5; // si
  SIZE_T cb; // [rsp+20h] [rbp-48h] BYREF
  struct _GUID v8; // [rsp+28h] [rbp-40h] BYREF

  LOWORD(IdentityProviderInfoByGUID) = 1168;
  *a1 = GUID_NULL;
  if ( (unsigned __int8)ConnectedIdentityDisabledByRegistry() )
    return (unsigned __int16)IdentityProviderInfoByGUID | 0x80070000;
  v8 = 0;
  if ( (unsigned int)GetDefaultIdentityProvider(&v8) )
    goto LABEL_10;
  LODWORD(cb) = 0;
  if ( (unsigned int)GetIdentityProviderInfoByGUID(&v8, 0, &cb) != 122 )
    goto LABEL_10;
  v3 = CoTaskMemAlloc((unsigned int)cb);
  v4 = v3;
  if ( !v3 )
    goto LABEL_10;
  v5 = 0;
  IdentityProviderInfoByGUID = GetIdentityProviderInfoByGUID(&v8, v3, &cb);
  if ( !IdentityProviderInfoByGUID )
  {
    v5 = 0;
    if ( (v4[32] & 1) != 0 )
      v5 = IdentityProviderInfoByGUID + 1;
  }
  CoTaskMemFree(v4);
  if ( v5 )
    *a1 = v8;
  else
LABEL_10:
    IdentityProviderInfoByGUID = GetFirstConnectedIdentityProvider(a1);
  if ( IdentityProviderInfoByGUID > 0 )
    return (unsigned __int16)IdentityProviderInfoByGUID | 0x80070000;
  return (unsigned int)IdentityProviderInfoByGUID;
}

```

## disassembly

```asm
0x1800e5344  push    rbx
0x1800e5346  push    rbp
0x1800e5347  push    rsi
0x1800e5348  push    rdi
0x1800e5349  sub     rsp, 48h
0x1800e534d  mov     rax, cs:__security_cookie
0x1800e5354  xor     rax, rsp
0x1800e5357  mov     [rsp+68h+var_30], rax
0x1800e535c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800e5363  mov     rbp, rcx
0x1800e5366  mov     ebx, 490h
0x1800e536b  movdqu  xmmword ptr [rcx], xmm0
0x1800e536f  call    _ConnectedIdentityDisabledByRegistry
0x1800e5374  test    al, al
0x1800e5376  jnz     loc_1800E5433
0x1800e537c  xorps   xmm0, xmm0
0x1800e537f  lea     rcx, [rsp+68h+var_40]
0x1800e5384  movups  [rsp+68h+var_40], xmm0
0x1800e5389  call    cs:__imp_GetDefaultIdentityProvider
0x1800e5390  nop     dword ptr [rax+rax+00h]
0x1800e5395  test    eax, eax
0x1800e5397  jnz     loc_1800E5425
0x1800e539d  lea     r8, [rsp+68h+cb]
0x1800e53a2  mov     dword ptr [rsp+68h+cb], eax
0x1800e53a6  xor     edx, edx
0x1800e53a8  lea     rcx, [rsp+68h+var_40]
0x1800e53ad  call    cs:__imp_GetIdentityProviderInfoByGUID
0x1800e53b4  nop     dword ptr [rax+rax+00h]
0x1800e53b9  cmp     eax, 7Ah ; 'z'
0x1800e53bc  jnz     short loc_1800E5425
0x1800e53be  mov     ecx, dword ptr [rsp+68h+cb]; cb
0x1800e53c2  call    cs:__imp_CoTaskMemAlloc
0x1800e53c9  nop     dword ptr [rax+rax+00h]
0x1800e53ce  mov     rdi, rax
0x1800e53d1  test    rax, rax
0x1800e53d4  jz      short loc_1800E5425
0x1800e53d6  lea     r8, [rsp+68h+cb]
0x1800e53db  mov     rdx, rax
0x1800e53de  lea     rcx, [rsp+68h+var_40]
0x1800e53e3  xor     sil, sil
0x1800e53e6  call    cs:__imp_GetIdentityProviderInfoByGUID
0x1800e53ed  nop     dword ptr [rax+rax+00h]
0x1800e53f2  mov     ebx, eax
0x1800e53f4  test    eax, eax
0x1800e53f6  jnz     short loc_1800E5405
0x1800e53f8  lea     eax, [rbx+1]
0x1800e53fb  movzx   esi, sil
0x1800e53ff  test    [rdi+20h], al
0x1800e5402  cmovnz  esi, eax
0x1800e5405  mov     rcx, rdi; pv
0x1800e5408  call    cs:__imp_CoTaskMemFree
0x1800e540f  nop     dword ptr [rax+rax+00h]
0x1800e5414  test    sil, sil
0x1800e5417  jz      short loc_1800E5425
0x1800e5419  movups  xmm0, [rsp+68h+var_40]
0x1800e541e  movdqu  xmmword ptr [rbp+0], xmm0
0x1800e5423  jmp     short loc_1800E542F
0x1800e5425  mov     rcx, rbp
0x1800e5428  call    _GetFirstConnectedIdentityProvider
0x1800e542d  mov     ebx, eax
0x1800e542f  test    ebx, ebx
0x1800e5431  jle     short loc_1800E543C
0x1800e5433  movzx   ebx, bx
0x1800e5436  or      ebx, 80070000h
0x1800e543c  mov     eax, ebx
0x1800e543e  mov     rcx, [rsp+68h+var_30]
0x1800e5443  xor     rcx, rsp; StackCookie
0x1800e5446  call    __security_check_cookie
0x1800e544b  add     rsp, 48h
0x1800e544f  pop     rdi
0x1800e5450  pop     rsi
0x1800e5451  pop     rbp
0x1800e5452  pop     rbx
0x1800e5453  retn
```
