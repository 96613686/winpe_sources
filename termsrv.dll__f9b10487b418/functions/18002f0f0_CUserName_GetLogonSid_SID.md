# CUserName::GetLogonSid(_SID * *)

- ea: `0x18002f0f0`
- end: `0x18002f275`
- name: `?GetLogonSid@CUserName@@UEAAJPEAPEAU_SID@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(CUserName *__hidden this, struct _SID **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a210`
- `0x18002f0f0`
- `0x1800c4e0c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002f1e7`
- `ntdll!RtlLengthSid` at `0x18002f1e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f222`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f222`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f157`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f1ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f157`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002f1ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f1f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f1f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f21a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f21a`

## string_xrefs

- `0x18002f1d0`: `GetTokenInformation failed: 0x%x`
- `0x18002f23a`: `Cannot get the TOKEN_GROUPS length: 0x%x`
- `0x18002f128`: `No token`
- `0x18002f24d`: `Cannot get the TOKEN_GROUPS length`

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
0x18002f0f0  mov     [rsp+arg_0], rbx
0x18002f0f5  mov     [rsp+arg_10], rsi
0x18002f0fa  push    rdi
0x18002f0fb  sub     rsp, 30h
0x18002f0ff  mov     [rsp+38h+TokenInformationLength], 0
0x18002f107  mov     rbx, rdx
0x18002f10a  mov     rsi, rcx
0x18002f10d  test    rdx, rdx
0x18002f110  jnz     short loc_18002F11C
0x18002f112  mov     ebx, 80070057h
0x18002f117  jmp     loc_18002F263
0x18002f11c  mov     rcx, [rcx+638h]; TokenHandle
0x18002f123  test    rcx, rcx
0x18002f126  jnz     short loc_18002F143
0x18002f128  lea     rdx, aNoToken; "No token"
0x18002f12f  mov     ecx, 8; int
0x18002f134  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f139  mov     ebx, 800703F0h
0x18002f13e  jmp     loc_18002F263
0x18002f143  xor     r9d, r9d; TokenInformationLength
0x18002f146  lea     rax, [rsp+38h+TokenInformationLength]
0x18002f14b  xor     r8d, r8d; TokenInformation
0x18002f14e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002f153  lea     edx, [r9+1Ch]; TokenInformationClass
0x18002f157  call    cs:__imp_GetTokenInformation
0x18002f15d  test    eax, eax
0x18002f15f  jnz     loc_18002F24D
0x18002f165  call    cs:__imp_GetLastError
0x18002f16b  cmp     eax, 7Ah ; 'z'
0x18002f16e  jnz     loc_18002F222
0x18002f174  mov     ecx, [rsp+38h+TokenInformationLength]; cb
0x18002f178  call    cs:__imp_CoTaskMemAlloc
0x18002f17e  mov     rdi, rax
0x18002f181  test    rax, rax
0x18002f184  jnz     short loc_18002F190
0x18002f186  mov     ebx, 8007000Eh
0x18002f18b  jmp     loc_18002F263
0x18002f190  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18002f195  lea     rax, [rsp+38h+TokenInformationLength]
0x18002f19a  mov     rcx, [rsi+638h]; TokenHandle
0x18002f1a1  mov     r8, rdi; TokenInformation
0x18002f1a4  mov     edx, 1Ch; TokenInformationClass
0x18002f1a9  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002f1ae  call    cs:__imp_GetTokenInformation
0x18002f1b4  test    eax, eax
0x18002f1b6  jnz     short loc_18002F1E3
0x18002f1b8  call    cs:__imp_GetLastError
0x18002f1be  mov     ebx, eax
0x18002f1c0  test    eax, eax
0x18002f1c2  jle     short loc_18002F1CD
0x18002f1c4  movzx   ebx, ax
0x18002f1c7  or      ebx, 80070000h
0x18002f1cd  mov     r8d, ebx
0x18002f1d0  lea     rdx, aGettokeninform; "GetTokenInformation failed: 0x%x"
0x18002f1d7  mov     ecx, 8; int
0x18002f1dc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f1e1  jmp     short loc_18002F217
0x18002f1e3  mov     rcx, [rdi+8]; Sid
0x18002f1e7  call    cs:__imp_RtlLengthSid
0x18002f1ed  mov     ecx, eax; cb
0x18002f1ef  mov     esi, eax
0x18002f1f1  call    cs:__imp_CoTaskMemAlloc
0x18002f1f7  mov     [rbx], rax
0x18002f1fa  test    rax, rax
0x18002f1fd  jnz     short loc_18002F206
0x18002f1ff  mov     ebx, 8007000Eh
0x18002f204  jmp     short loc_18002F217
0x18002f206  mov     rdx, [rdi+8]; Src
0x18002f20a  mov     r8, rsi; Size
0x18002f20d  mov     rcx, rax; void *
0x18002f210  call    memcpy_0
0x18002f215  xor     ebx, ebx
0x18002f217  mov     rcx, rdi; pv
0x18002f21a  call    cs:__imp_CoTaskMemFree
0x18002f220  jmp     short loc_18002F263
0x18002f222  call    cs:__imp_GetLastError
0x18002f228  mov     ebx, eax
0x18002f22a  test    eax, eax
0x18002f22c  jle     short loc_18002F237
0x18002f22e  movzx   ebx, ax
0x18002f231  or      ebx, 80070000h
0x18002f237  mov     r8d, ebx
0x18002f23a  lea     rdx, aCannotGetTheTo; "Cannot get the TOKEN_GROUPS length: 0x%"...
0x18002f241  mov     ecx, 8; int
0x18002f246  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f24b  jmp     short loc_18002F263
0x18002f24d  lea     rdx, aCannotGetTheTo_0; "Cannot get the TOKEN_GROUPS length"
0x18002f254  mov     ecx, 8; int
0x18002f259  mov     ebx, 80070057h
0x18002f25e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002f263  mov     rsi, [rsp+38h+arg_10]
0x18002f268  mov     eax, ebx
0x18002f26a  mov     rbx, [rsp+38h+arg_0]
0x18002f26f  add     rsp, 30h
0x18002f273  pop     rdi
0x18002f274  retn
```
