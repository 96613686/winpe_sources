# CUserName::GetLogonSid(_SID * *)

- ea: `0x180016140`
- end: `0x1800162c5`
- name: `?GetLogonSid@CUserName@@UEAAJPEAPEAU_SID@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(CUserName *__hidden this, struct _SID **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003f30`
- `0x180016140`
- `0x18001b46d`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180016237`
- `ntdll!RtlLengthSid` at `0x180016237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800161b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016272`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001626a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001626a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800161c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016241`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800161c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016241`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800161a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800161fe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800161a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800161fe`

## string_xrefs

- `0x18001628a`: `Cannot get the TOKEN_GROUPS length: 0x%x`
- `0x180016220`: `GetTokenInformation failed: 0x%x`
- `0x180016178`: `No token`
- `0x18001629d`: `Cannot get the TOKEN_GROUPS length`

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
0x180016140  mov     [rsp+arg_0], rbx
0x180016145  mov     [rsp+arg_10], rsi
0x18001614a  push    rdi
0x18001614b  sub     rsp, 30h
0x18001614f  mov     [rsp+38h+TokenInformationLength], 0
0x180016157  mov     rbx, rdx
0x18001615a  mov     rsi, rcx
0x18001615d  test    rdx, rdx
0x180016160  jnz     short loc_18001616C
0x180016162  mov     ebx, 80070057h
0x180016167  jmp     loc_1800162B3
0x18001616c  mov     rcx, [rcx+638h]; TokenHandle
0x180016173  test    rcx, rcx
0x180016176  jnz     short loc_180016193
0x180016178  lea     rdx, aNoToken; "No token"
0x18001617f  mov     ecx, 8; int
0x180016184  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180016189  mov     ebx, 800703F0h
0x18001618e  jmp     loc_1800162B3
0x180016193  xor     r9d, r9d; TokenInformationLength
0x180016196  lea     rax, [rsp+38h+TokenInformationLength]
0x18001619b  xor     r8d, r8d; TokenInformation
0x18001619e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800161a3  lea     edx, [r9+1Ch]; TokenInformationClass
0x1800161a7  call    cs:__imp_GetTokenInformation
0x1800161ad  test    eax, eax
0x1800161af  jnz     loc_18001629D
0x1800161b5  call    cs:__imp_GetLastError
0x1800161bb  cmp     eax, 7Ah ; 'z'
0x1800161be  jnz     loc_180016272
0x1800161c4  mov     ecx, [rsp+38h+TokenInformationLength]; cb
0x1800161c8  call    cs:__imp_CoTaskMemAlloc
0x1800161ce  mov     rdi, rax
0x1800161d1  test    rax, rax
0x1800161d4  jnz     short loc_1800161E0
0x1800161d6  mov     ebx, 8007000Eh
0x1800161db  jmp     loc_1800162B3
0x1800161e0  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800161e5  lea     rax, [rsp+38h+TokenInformationLength]
0x1800161ea  mov     rcx, [rsi+638h]; TokenHandle
0x1800161f1  mov     r8, rdi; TokenInformation
0x1800161f4  mov     edx, 1Ch; TokenInformationClass
0x1800161f9  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800161fe  call    cs:__imp_GetTokenInformation
0x180016204  test    eax, eax
0x180016206  jnz     short loc_180016233
0x180016208  call    cs:__imp_GetLastError
0x18001620e  mov     ebx, eax
0x180016210  test    eax, eax
0x180016212  jle     short loc_18001621D
0x180016214  movzx   ebx, ax
0x180016217  or      ebx, 80070000h
0x18001621d  mov     r8d, ebx
0x180016220  lea     rdx, aGettokeninform; "GetTokenInformation failed: 0x%x"
0x180016227  mov     ecx, 8; int
0x18001622c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180016231  jmp     short loc_180016267
0x180016233  mov     rcx, [rdi+8]; Sid
0x180016237  call    cs:__imp_RtlLengthSid
0x18001623d  mov     ecx, eax; cb
0x18001623f  mov     esi, eax
0x180016241  call    cs:__imp_CoTaskMemAlloc
0x180016247  mov     [rbx], rax
0x18001624a  test    rax, rax
0x18001624d  jnz     short loc_180016256
0x18001624f  mov     ebx, 8007000Eh
0x180016254  jmp     short loc_180016267
0x180016256  mov     rdx, [rdi+8]; Src
0x18001625a  mov     r8, rsi; Size
0x18001625d  mov     rcx, rax; void *
0x180016260  call    memcpy_0
0x180016265  xor     ebx, ebx
0x180016267  mov     rcx, rdi; pv
0x18001626a  call    cs:__imp_CoTaskMemFree
0x180016270  jmp     short loc_1800162B3
0x180016272  call    cs:__imp_GetLastError
0x180016278  mov     ebx, eax
0x18001627a  test    eax, eax
0x18001627c  jle     short loc_180016287
0x18001627e  movzx   ebx, ax
0x180016281  or      ebx, 80070000h
0x180016287  mov     r8d, ebx
0x18001628a  lea     rdx, aCannotGetTheTo; "Cannot get the TOKEN_GROUPS length: 0x%"...
0x180016291  mov     ecx, 8; int
0x180016296  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001629b  jmp     short loc_1800162B3
0x18001629d  lea     rdx, aCannotGetTheTo_0; "Cannot get the TOKEN_GROUPS length"
0x1800162a4  mov     ecx, 8; int
0x1800162a9  mov     ebx, 80070057h
0x1800162ae  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800162b3  mov     rsi, [rsp+38h+arg_10]
0x1800162b8  mov     eax, ebx
0x1800162ba  mov     rbx, [rsp+38h+arg_0]
0x1800162bf  add     rsp, 30h
0x1800162c3  pop     rdi
0x1800162c4  retn
```
