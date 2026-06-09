# ScFullTrustCapabilitiesAreDisabledByDefault(ushort const *,int *)

- ea: `0x140082bd0`
- end: `0x140082dc7`
- name: `?ScFullTrustCapabilitiesAreDisabledByDefault@@YAJPEBGPEAH@Z`
- size: `503`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14003ae4c`

## callees

- `0x140004c58`
- `0x1400575b0`
- `0x140082bd0`
- `0x140083878`
- `0x140092060`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140082d7a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140082d7a`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x140082d22`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x140082d22`
- `ntdll!RtlInitUnicodeString` at `0x140082cef`
- `ntdll!RtlInitUnicodeString` at `0x140082cef`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x140082c6b`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x140082c6b`

## string_xrefs

- `0x140082ce4`: `Microsoft.appCategory.chatAgent_8wekyb3d8bbwe`

## pseudocode

```c
__int64 __fastcall ScFullTrustCapabilitiesAreDisabledByDefault(const unsigned __int16 *a1, int *a2)
{
  __int64 v4; // r9
  int v5; // ebx
  unsigned int v6; // edi
  __int64 v8; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v9; // [rsp+68h] [rbp-98h]
  __int64 *v10; // [rsp+70h] [rbp-90h]
  unsigned int v11; // [rsp+78h] [rbp-88h] BYREF
  char v12; // [rsp+7Ch] [rbp-84h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pSid2[80]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v15[80]; // [rsp+E0h] [rbp-20h] BYREF

  v12 = 1;
  v8 = 0;
  v9 = 0;
  *a2 = 0;
  v10 = &v8;
  DestinationString = 0;
  v11 = 0;
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v8);
  v4 = (unsigned int)QueryApplicationCapabilitiesEx(a1, 0, 0, 0, 0, &v8, &v11, 0, 0, 0, 0);
  if ( v12 )
    v10[1] = v11;
  if ( (int)(v4 + 0x80000000) < 0 || (_DWORD)v4 == -2147024444 )
  {
    v5 = 0;
    if ( v9 )
    {
      RtlInitUnicodeString(&DestinationString, L"Microsoft.appCategory.chatAgent_8wekyb3d8bbwe");
      memset(pSid2, 0, 0x44u);
      memset(v15, 0, 0x44u);
      v5 = RtlDeriveCapabilitySidsFromName(&DestinationString, v15, pSid2);
      if ( v5 >= 0 )
      {
        v6 = 0;
        if ( v9 )
        {
          while ( !EqualSid(*(PSID *)(v8 + 8LL * v6), pSid2) )
          {
            if ( ++v6 >= v9 )
              goto LABEL_19;
          }
          *a2 = 1;
        }
      }
      else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
             && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 113, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, (unsigned int)v5);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 112, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, v4);
    v5 = -1073741823;
  }
LABEL_19:
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140082bd0  mov     [rsp-8+arg_10], rbx
0x140082bd5  mov     [rsp-8+arg_18], rsi
0x140082bda  push    rbp
0x140082bdb  push    rdi
0x140082bdc  push    r14
0x140082bde  lea     rbp, [rsp-40h]
0x140082be3  sub     rsp, 140h
0x140082bea  mov     rax, cs:__security_cookie
0x140082bf1  xor     rax, rsp
0x140082bf4  mov     [rbp+50h+var_20], rax
0x140082bf8  xor     r14d, r14d
0x140082bfb  mov     [rsp+150h+var_D4], 1
0x140082c00  mov     rbx, rcx
0x140082c03  mov     [rsp+150h+var_F0], r14
0x140082c08  xorps   xmm0, xmm0
0x140082c0b  mov     [rsp+150h+var_E8], r14
0x140082c10  lea     rax, [rsp+150h+var_F0]
0x140082c15  mov     [rdx], r14d
0x140082c18  lea     rcx, [rsp+150h+var_F0]
0x140082c1d  mov     [rsp+150h+var_E0], rax
0x140082c22  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x140082c26  mov     [rsp+150h+var_D8], r14d
0x140082c2b  mov     rsi, rdx
0x140082c2e  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x140082c33  mov     [rsp+150h+var_100], r14
0x140082c38  lea     rax, [rsp+150h+var_D8]
0x140082c3d  mov     [rsp+150h+var_108], r14
0x140082c42  xor     r9d, r9d
0x140082c45  mov     [rsp+150h+var_110], r14
0x140082c4a  xor     r8d, r8d
0x140082c4d  mov     [rsp+150h+var_118], r14
0x140082c52  xor     edx, edx
0x140082c54  mov     [rsp+150h+var_120], rax
0x140082c59  mov     rcx, rbx
0x140082c5c  lea     rax, [rsp+150h+var_F0]
0x140082c61  mov     [rsp+150h+var_128], rax
0x140082c66  mov     [rsp+150h+var_130], r14
0x140082c6b  call    cs:__imp_QueryApplicationCapabilitiesEx
0x140082c71  mov     r9d, eax
0x140082c74  cmp     [rsp+150h+var_D4], r14b
0x140082c79  jz      short loc_140082C88
0x140082c7b  mov     rcx, [rsp+150h+var_E0]
0x140082c80  mov     edx, [rsp+150h+var_D8]
0x140082c84  mov     [rcx+8], rdx
0x140082c88  mov     eax, 80000000h
0x140082c8d  lea     ecx, [r9+rax]
0x140082c91  test    eax, ecx
0x140082c93  jnz     short loc_140082CD6
0x140082c95  cmp     r9d, 800701C4h
0x140082c9c  jz      short loc_140082CD6
0x140082c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140082ca5  lea     rax, WPP_GLOBAL_Control
0x140082cac  cmp     rcx, rax
0x140082caf  jz      short loc_140082CCC
0x140082cb1  test    byte ptr [rcx+1Ch], 1
0x140082cb5  jz      short loc_140082CCC
0x140082cb7  mov     rcx, [rcx+10h]
0x140082cbb  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x140082cc2  mov     edx, 70h ; 'p'
0x140082cc7  call    WPP_SF_d
0x140082ccc  mov     ebx, 0C0000001h
0x140082cd1  jmp     loc_140082D97
0x140082cd6  mov     ebx, r14d
0x140082cd9  cmp     [rsp+150h+var_E8], r14
0x140082cde  jbe     loc_140082D97
0x140082ce4  lea     rdx, aMicrosoftAppca; "Microsoft.appCategory.chatAgent_8wekyb3"...
0x140082ceb  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140082cef  call    cs:__imp_RtlInitUnicodeString
0x140082cf5  mov     ebx, 44h ; 'D'
0x140082cfa  lea     rcx, [rbp+50h+pSid2]; void *
0x140082cfe  mov     r8d, ebx; Size
0x140082d01  xor     edx, edx; Val
0x140082d03  call    memset
0x140082d08  mov     r8d, ebx; Size
0x140082d0b  lea     rcx, [rbp+50h+var_70]; void *
0x140082d0f  xor     edx, edx; Val
0x140082d11  call    memset
0x140082d16  lea     r8, [rbp+50h+pSid2]
0x140082d1a  lea     rdx, [rbp+50h+var_70]
0x140082d1e  lea     rcx, [rbp+50h+DestinationString]
0x140082d22  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x140082d28  mov     ebx, eax
0x140082d2a  test    eax, eax
0x140082d2c  jns     short loc_140082D61
0x140082d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140082d35  lea     rax, WPP_GLOBAL_Control
0x140082d3c  cmp     rcx, rax
0x140082d3f  jz      short loc_140082D97
0x140082d41  test    byte ptr [rcx+1Ch], 1
0x140082d45  jz      short loc_140082D97
0x140082d47  mov     rcx, [rcx+10h]
0x140082d4b  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x140082d52  mov     edx, 71h ; 'q'
0x140082d57  mov     r9d, ebx
0x140082d5a  call    WPP_SF_d
0x140082d5f  jmp     short loc_140082D97
0x140082d61  mov     edi, r14d
0x140082d64  cmp     [rsp+150h+var_E8], r14
0x140082d69  jbe     short loc_140082D97
0x140082d6b  mov     rcx, [rsp+150h+var_F0]
0x140082d70  lea     rdx, [rbp+50h+pSid2]; pSid2
0x140082d74  mov     eax, edi
0x140082d76  mov     rcx, [rcx+rax*8]; pSid1
0x140082d7a  call    cs:__imp_EqualSid
0x140082d80  test    eax, eax
0x140082d82  jnz     short loc_140082D91
0x140082d84  inc     edi
0x140082d86  mov     eax, edi
0x140082d88  cmp     rax, [rsp+150h+var_E8]
0x140082d8d  jb      short loc_140082D6B
0x140082d8f  jmp     short loc_140082D97
0x140082d91  mov     dword ptr [rsi], 1
0x140082d97  lea     rcx, [rsp+150h+var_F0]
0x140082d9c  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x140082da1  mov     eax, ebx
0x140082da3  mov     rcx, [rbp+50h+var_20]
0x140082da7  xor     rcx, rsp; StackCookie
0x140082daa  call    __security_check_cookie
0x140082daf  lea     r11, [rsp+150h+var_10]
0x140082db7  mov     rbx, [r11+30h]
0x140082dbb  mov     rsi, [r11+38h]
0x140082dbf  mov     rsp, r11
0x140082dc2  pop     r14
0x140082dc4  pop     rdi
0x140082dc5  pop     rbp
0x140082dc6  retn
```
