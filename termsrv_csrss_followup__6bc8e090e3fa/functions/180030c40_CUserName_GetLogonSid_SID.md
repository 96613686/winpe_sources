# CUserName::GetLogonSid(_SID * *)

- ea: `0x180030c40`
- end: `0x180030dfc`
- name: `?GetLogonSid@CUserName@@UEAAJPEAPEAU_SID@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(CUserName *__hidden this, struct _SID **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009940`
- `0x180030c40`
- `0x1800caedc`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180030d55`
- `ntdll!RtlLengthSid` at `0x180030d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030da2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030da2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030ca7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030d10`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030ca7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180030d10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030cd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030cd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030d94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030d94`

## string_xrefs

- `0x180030d3e`: `GetTokenInformation failed: 0x%x`
- `0x180030dc0`: `Cannot get the TOKEN_GROUPS length: 0x%x`
- `0x180030c78`: `No token`
- `0x180030dd3`: `Cannot get the TOKEN_GROUPS length`

## pseudocode

```c
__int64 __fastcall CUserName::GetLogonSid(CUserName *this, struct _SID **a2)
{
  unsigned int v4; // ebx
  void *v5; // rcx
  PSID *v6; // rdi
  signed int LastError; // eax
  SIZE_T v8; // rsi
  struct _SID *v9; // rax
  signed int v10; // eax
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  if ( a2 )
  {
    v5 = (void *)*((_QWORD *)this + 199);
    if ( v5 )
    {
      if ( GetTokenInformation(v5, TokenLogonSid, 0, 0, &TokenInformationLength) )
      {
        v4 = -2147024809;
        _DbgPrintMessage(8, "Cannot get the TOKEN_GROUPS length");
      }
      else if ( GetLastError() == 122 )
      {
        v6 = (PSID *)CoTaskMemAlloc(TokenInformationLength);
        if ( v6 )
        {
          if ( GetTokenInformation(
                 *((HANDLE *)this + 199),
                 TokenLogonSid,
                 v6,
                 TokenInformationLength,
                 &TokenInformationLength) )
          {
            v8 = RtlLengthSid(v6[1]);
            v9 = (struct _SID *)CoTaskMemAlloc(v8);
            *a2 = v9;
            if ( v9 )
            {
              memcpy_0(v9, v6[1], v8);
              v4 = 0;
            }
            else
            {
              v4 = -2147024882;
            }
          }
          else
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x", v4);
          }
          CoTaskMemFree(v6);
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
      else
      {
        v10 = GetLastError();
        v4 = v10;
        if ( v10 > 0 )
          v4 = (unsigned __int16)v10 | 0x80070000;
        _DbgPrintMessage(8, "Cannot get the TOKEN_GROUPS length: 0x%x", v4);
      }
    }
    else
    {
      _DbgPrintMessage(8, "No token");
      return (unsigned int)-2147023888;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x180030c40  mov     [rsp+arg_0], rbx
0x180030c45  mov     [rsp+arg_10], rsi
0x180030c4a  push    rdi
0x180030c4b  sub     rsp, 30h
0x180030c4f  mov     [rsp+38h+TokenInformationLength], 0
0x180030c57  mov     rbx, rdx
0x180030c5a  mov     rsi, rcx
0x180030c5d  test    rdx, rdx
0x180030c60  jnz     short loc_180030C6C
0x180030c62  mov     ebx, 80070057h
0x180030c67  jmp     loc_180030DE9
0x180030c6c  mov     rcx, [rcx+638h]; TokenHandle
0x180030c73  test    rcx, rcx
0x180030c76  jnz     short loc_180030C93
0x180030c78  lea     rdx, aNoToken; "No token"
0x180030c7f  mov     ecx, 8; int
0x180030c84  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180030c89  mov     ebx, 800703F0h
0x180030c8e  jmp     loc_180030DE9
0x180030c93  xor     r9d, r9d; TokenInformationLength
0x180030c96  lea     rax, [rsp+38h+TokenInformationLength]
0x180030c9b  xor     r8d, r8d; TokenInformation
0x180030c9e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180030ca3  lea     edx, [r9+1Ch]; TokenInformationClass
0x180030ca7  call    cs:__imp_GetTokenInformation
0x180030cae  nop     dword ptr [rax+rax+00h]
0x180030cb3  test    eax, eax
0x180030cb5  jnz     loc_180030DD3
0x180030cbb  call    cs:__imp_GetLastError
0x180030cc2  nop     dword ptr [rax+rax+00h]
0x180030cc7  cmp     eax, 7Ah ; 'z'
0x180030cca  jnz     loc_180030DA2
0x180030cd0  mov     ecx, [rsp+38h+TokenInformationLength]; cb
0x180030cd4  call    cs:__imp_CoTaskMemAlloc
0x180030cdb  nop     dword ptr [rax+rax+00h]
0x180030ce0  mov     rdi, rax
0x180030ce3  test    rax, rax
0x180030ce6  jnz     short loc_180030CF2
0x180030ce8  mov     ebx, 8007000Eh
0x180030ced  jmp     loc_180030DE9
0x180030cf2  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180030cf7  lea     rax, [rsp+38h+TokenInformationLength]
0x180030cfc  mov     rcx, [rsi+638h]; TokenHandle
0x180030d03  mov     r8, rdi; TokenInformation
0x180030d06  mov     edx, 1Ch; TokenInformationClass
0x180030d0b  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180030d10  call    cs:__imp_GetTokenInformation
0x180030d17  nop     dword ptr [rax+rax+00h]
0x180030d1c  test    eax, eax
0x180030d1e  jnz     short loc_180030D51
0x180030d20  call    cs:__imp_GetLastError
0x180030d27  nop     dword ptr [rax+rax+00h]
0x180030d2c  mov     ebx, eax
0x180030d2e  test    eax, eax
0x180030d30  jle     short loc_180030D3B
0x180030d32  movzx   ebx, ax
0x180030d35  or      ebx, 80070000h
0x180030d3b  mov     r8d, ebx
0x180030d3e  lea     rdx, aGettokeninform; "GetTokenInformation failed: 0x%x"
0x180030d45  mov     ecx, 8; int
0x180030d4a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180030d4f  jmp     short loc_180030D91
0x180030d51  mov     rcx, [rdi+8]; Sid
0x180030d55  call    cs:__imp_RtlLengthSid
0x180030d5c  nop     dword ptr [rax+rax+00h]
0x180030d61  mov     ecx, eax; cb
0x180030d63  mov     esi, eax
0x180030d65  call    cs:__imp_CoTaskMemAlloc
0x180030d6c  nop     dword ptr [rax+rax+00h]
0x180030d71  mov     [rbx], rax
0x180030d74  test    rax, rax
0x180030d77  jnz     short loc_180030D80
0x180030d79  mov     ebx, 8007000Eh
0x180030d7e  jmp     short loc_180030D91
0x180030d80  mov     rdx, [rdi+8]; Src
0x180030d84  mov     r8, rsi; Size
0x180030d87  mov     rcx, rax; void *
0x180030d8a  call    memcpy_0
0x180030d8f  xor     ebx, ebx
0x180030d91  mov     rcx, rdi; pv
0x180030d94  call    cs:__imp_CoTaskMemFree
0x180030d9b  nop     dword ptr [rax+rax+00h]
0x180030da0  jmp     short loc_180030DE9
0x180030da2  call    cs:__imp_GetLastError
0x180030da9  nop     dword ptr [rax+rax+00h]
0x180030dae  mov     ebx, eax
0x180030db0  test    eax, eax
0x180030db2  jle     short loc_180030DBD
0x180030db4  movzx   ebx, ax
0x180030db7  or      ebx, 80070000h
0x180030dbd  mov     r8d, ebx
0x180030dc0  lea     rdx, aCannotGetTheTo; "Cannot get the TOKEN_GROUPS length: 0x%"...
0x180030dc7  mov     ecx, 8; int
0x180030dcc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180030dd1  jmp     short loc_180030DE9
0x180030dd3  lea     rdx, aCannotGetTheTo_0; "Cannot get the TOKEN_GROUPS length"
0x180030dda  mov     ecx, 8; int
0x180030ddf  mov     ebx, 80070057h
0x180030de4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180030de9  mov     rsi, [rsp+38h+arg_10]
0x180030dee  mov     eax, ebx
0x180030df0  mov     rbx, [rsp+38h+arg_0]
0x180030df5  add     rsp, 30h
0x180030df9  pop     rdi
0x180030dfa  retn
```
