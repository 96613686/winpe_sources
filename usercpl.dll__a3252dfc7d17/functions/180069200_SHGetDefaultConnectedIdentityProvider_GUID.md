# SHGetDefaultConnectedIdentityProvider(_GUID *)

- ea: `0x180069200`
- end: `0x1800692ee`
- name: `?SHGetDefaultConnectedIdentityProvider@@YAJPEAU_GUID@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180056b00`
- `0x1800574f0`
- `0x180058830`
- `0x18005f23c`
- `0x18005f3e8`
- `0x180074b10`

## callees

- `0x180069200`
- `0x1800694d8`
- `0x180069520`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006926e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006926e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800692a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800692a8`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x180069245`
- `api-ms-win-security-lsalookup-l1-1-1!GetDefaultIdentityProvider` at `0x180069245`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18006925f`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18006928c`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18006925f`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18006928c`

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
0x180069200  push    rbx
0x180069202  push    rbp
0x180069203  push    rsi
0x180069204  push    rdi
0x180069205  sub     rsp, 48h
0x180069209  mov     rax, cs:__security_cookie
0x180069210  xor     rax, rsp
0x180069213  mov     [rsp+68h+var_30], rax
0x180069218  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006921f  mov     rbp, rcx
0x180069222  mov     ebx, 490h
0x180069227  movdqu  xmmword ptr [rcx], xmm0
0x18006922b  call    _ConnectedIdentityDisabledByRegistry
0x180069230  test    al, al
0x180069232  jnz     loc_1800692CD
0x180069238  xorps   xmm0, xmm0
0x18006923b  lea     rcx, [rsp+68h+var_40]
0x180069240  movups  [rsp+68h+var_40], xmm0
0x180069245  call    cs:__imp_GetDefaultIdentityProvider
0x18006924b  test    eax, eax
0x18006924d  jnz     short loc_1800692BF
0x18006924f  lea     r8, [rsp+68h+cb]
0x180069254  mov     dword ptr [rsp+68h+cb], eax
0x180069258  xor     edx, edx
0x18006925a  lea     rcx, [rsp+68h+var_40]
0x18006925f  call    cs:__imp_GetIdentityProviderInfoByGUID
0x180069265  cmp     eax, 7Ah ; 'z'
0x180069268  jnz     short loc_1800692BF
0x18006926a  mov     ecx, dword ptr [rsp+68h+cb]; cb
0x18006926e  call    cs:__imp_CoTaskMemAlloc
0x180069274  mov     rdi, rax
0x180069277  test    rax, rax
0x18006927a  jz      short loc_1800692BF
0x18006927c  lea     r8, [rsp+68h+cb]
0x180069281  mov     rdx, rax
0x180069284  lea     rcx, [rsp+68h+var_40]
0x180069289  xor     sil, sil
0x18006928c  call    cs:__imp_GetIdentityProviderInfoByGUID
0x180069292  mov     ebx, eax
0x180069294  test    eax, eax
0x180069296  jnz     short loc_1800692A5
0x180069298  lea     eax, [rbx+1]
0x18006929b  movzx   esi, sil
0x18006929f  test    [rdi+20h], al
0x1800692a2  cmovnz  esi, eax
0x1800692a5  mov     rcx, rdi; pv
0x1800692a8  call    cs:__imp_CoTaskMemFree
0x1800692ae  test    sil, sil
0x1800692b1  jz      short loc_1800692BF
0x1800692b3  movups  xmm0, [rsp+68h+var_40]
0x1800692b8  movdqu  xmmword ptr [rbp+0], xmm0
0x1800692bd  jmp     short loc_1800692C9
0x1800692bf  mov     rcx, rbp
0x1800692c2  call    _GetFirstConnectedIdentityProvider
0x1800692c7  mov     ebx, eax
0x1800692c9  test    ebx, ebx
0x1800692cb  jle     short loc_1800692D6
0x1800692cd  movzx   ebx, bx
0x1800692d0  or      ebx, 80070000h
0x1800692d6  mov     eax, ebx
0x1800692d8  mov     rcx, [rsp+68h+var_30]
0x1800692dd  xor     rcx, rsp; StackCookie
0x1800692e0  call    __security_check_cookie
0x1800692e5  add     rsp, 48h
0x1800692e9  pop     rdi
0x1800692ea  pop     rsi
0x1800692eb  pop     rbp
0x1800692ec  pop     rbx
0x1800692ed  retn
```
