# CUtils::IsTokenSid(void *,void *)

- ea: `0x18002e78c`
- end: `0x18002e910`
- name: `?IsTokenSid@CUtils@@CAJPEAX0@Z`
- size: `388`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d8d8`

## callees

- `0x18000a210`
- `0x18002e78c`
- `0x1800321f0`
- `0x180033058`
- `0x1800c4da0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18002e8e4`
- `ntdll!RtlEqualSid` at `0x18002e8e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e7f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e8bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e7f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e8bd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002e7eb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002e8b3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002e7eb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002e8b3`

## string_xrefs

- `0x18002e80d`: `IsTokenSid: Error %x Getting TokenInformation`
- `0x18002e8d2`: `IsTokenSid: Error %x Getting TokenInformation on buffer\n`
- `0x18002e886`: `IsTokenSid: Error allocating %d bytes memory\n`

## pseudocode

```c
__int64 __fastcall CUtils::IsTokenSid(HANDLE TokenHandle, void *a2)
{
  PSID v3; // rsi
  unsigned int v4; // ebx
  signed int v5; // eax
  unsigned __int64 v6; // rcx
  void *v7; // rsp
  void *v8; // rsp
  signed int LastError; // eax
  PSID TokenInformation; // [rsp+30h] [rbp+0h] BYREF
  PSID *p_TokenInformation; // [rsp+38h] [rbp+8h]
  PSID v13; // [rsp+40h] [rbp+10h]

  v3 = CUtils::pAnonymousSid;
  v13 = CUtils::pAnonymousSid;
  if ( CUtils::pAnonymousSid )
  {
    LODWORD(TokenInformation) = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&TokenInformation);
    if ( (_DWORD)TokenInformation )
    {
      HIDWORD(TokenInformation) = (_DWORD)TokenInformation;
      v6 = (unsigned int)TokenInformation + 15LL;
      if ( v6 < (unsigned int)TokenInformation )
        v6 = 0xFFFFFFFFFFFFFF0LL;
      v7 = alloca(v6 & 0xFFFFFFFFFFFFFFF0uLL);
      v8 = alloca(v6 & 0xFFFFFFFFFFFFFFF0uLL);
      p_TokenInformation = &TokenInformation;
      if ( &TokenInformation )
      {
        if ( GetTokenInformation(
               TokenHandle,
               TokenUser,
               &TokenInformation,
               (DWORD)TokenInformation,
               (PDWORD)&TokenInformation) )
        {
          return RtlEqualSid(TokenInformation, v3) == 0;
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          _DbgPrintMessage(8, "IsTokenSid: Error %x Getting TokenInformation on buffer\n", v4);
        }
      }
      else
      {
        _DbgPrintMessage(8, "IsTokenSid: Error allocating %d bytes memory\n", (_DWORD)TokenInformation);
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      _DbgPrintMessage(8, "IsTokenSid: Error %x Getting TokenInformation", v4);
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v4;
}

```

## disassembly

```asm
0x18002e78c  mov     [rsp-8+arg_0], rcx
0x18002e791  push    rbp
0x18002e792  push    rdi
0x18002e793  push    r14
0x18002e795  sub     rsp, 50h
0x18002e799  lea     rbp, [rsp+30h]
0x18002e79e  mov     [rbp+30h+arg_8], rbx
0x18002e7a2  mov     [rbp+30h+arg_10], rsi
0x18002e7a6  mov     rax, cs:__security_cookie
0x18002e7ad  xor     rax, rbp
0x18002e7b0  mov     [rbp+30h+var_18], rax
0x18002e7b4  mov     r14, rcx
0x18002e7b7  mov     rsi, cs:?pAnonymousSid@CUtils@@0PEAXEA; void * CUtils::pAnonymousSid
0x18002e7be  mov     [rbp+30h+var_20], rsi
0x18002e7c2  test    rsi, rsi
0x18002e7c5  jnz     short loc_18002E7D1
0x18002e7c7  mov     ebx, 8000FFFFh
0x18002e7cc  jmp     loc_18002E8F1
0x18002e7d1  mov     [rbp+30h+TokenInformation], 0
0x18002e7d8  lea     rax, [rbp+30h+TokenInformation]
0x18002e7dc  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18002e7e1  xor     r9d, r9d; TokenInformationLength
0x18002e7e4  xor     r8d, r8d; TokenInformation
0x18002e7e7  lea     edx, [r9+1]; TokenInformationClass
0x18002e7eb  call    cs:__imp_GetTokenInformation
0x18002e7f1  mov     ebx, [rbp+30h+TokenInformation]
0x18002e7f4  test    ebx, ebx
0x18002e7f6  jnz     short loc_18002E826
0x18002e7f8  call    cs:__imp_GetLastError
0x18002e7fe  mov     ebx, eax
0x18002e800  test    eax, eax
0x18002e802  jle     short loc_18002E80D
0x18002e804  movzx   ebx, ax
0x18002e807  or      ebx, 80070000h
0x18002e80d  lea     rdx, aIstokensidErro_1; "IsTokenSid: Error %x Getting TokenInfor"...
0x18002e814  mov     r8d, ebx
0x18002e817  mov     ecx, 8; int
0x18002e81c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002e821  jmp     loc_18002E8F1
0x18002e826  mov     [rbp+30h+var_2C], ebx
0x18002e829  lea     rcx, [rbx+0Fh]
0x18002e82d  cmp     rcx, rbx
0x18002e830  ja      short loc_18002E83C
0x18002e832  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002e83c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002e840  mov     rax, rcx
0x18002e843  call    _alloca_probe
0x18002e848  sub     rsp, rcx
0x18002e84b  lea     rdi, [rsp+60h+TokenInformation]
0x18002e850  mov     [rbp+30h+var_28], rdi
0x18002e854  jmp     short loc_18002E87E
0x18002e856  call    _o__resetstkoflw_0
0x18002e85b  xor     edi, edi
0x18002e85d  mov     [rbp+30h+var_28], rdi
0x18002e861  mov     ebx, [rbp+30h+var_2C]
0x18002e864  mov     r8d, ebx
0x18002e867  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x18002e86e  lea     ecx, [rdi+8]; int
0x18002e871  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002e876  mov     rsi, [rbp+30h+var_20]
0x18002e87a  mov     r14, [rbp+30h+arg_0]
0x18002e87e  test    rdi, rdi
0x18002e881  jnz     short loc_18002E89C
0x18002e883  mov     r8d, ebx
0x18002e886  lea     rdx, aIstokensidErro; "IsTokenSid: Error allocating %d bytes m"...
0x18002e88d  lea     ecx, [rdi+8]; int
0x18002e890  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002e895  mov     ebx, 8007000Eh
0x18002e89a  jmp     short loc_18002E8F1
0x18002e89c  lea     rax, [rbp+30h+TokenInformation]
0x18002e8a0  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18002e8a5  mov     r9d, ebx; TokenInformationLength
0x18002e8a8  mov     r8, rdi; TokenInformation
0x18002e8ab  mov     edx, 1; TokenInformationClass
0x18002e8b0  mov     rcx, r14; TokenHandle
0x18002e8b3  call    cs:__imp_GetTokenInformation
0x18002e8b9  test    eax, eax
0x18002e8bb  jnz     short loc_18002E8DE
0x18002e8bd  call    cs:__imp_GetLastError
0x18002e8c3  mov     ebx, eax
0x18002e8c5  test    eax, eax
0x18002e8c7  jle     short loc_18002E8D2
0x18002e8c9  movzx   ebx, ax
0x18002e8cc  or      ebx, 80070000h
0x18002e8d2  lea     rdx, aIstokensidErro_0; "IsTokenSid: Error %x Getting TokenInfor"...
0x18002e8d9  jmp     loc_18002E814
0x18002e8de  mov     rdx, rsi; Sid2
0x18002e8e1  mov     rcx, [rdi]; Sid1
0x18002e8e4  call    cs:__imp_RtlEqualSid
0x18002e8ea  xor     ebx, ebx
0x18002e8ec  test    al, al
0x18002e8ee  setz    bl
0x18002e8f1  mov     eax, ebx
0x18002e8f3  mov     rcx, [rbp+30h+var_18]
0x18002e8f7  xor     rcx, rbp; StackCookie
0x18002e8fa  call    __security_check_cookie
0x18002e8ff  mov     rbx, [rbp+30h+arg_8]
0x18002e903  mov     rsi, [rbp+30h+arg_10]
0x18002e907  lea     rsp, [rbp+20h]
0x18002e90b  pop     r14
0x18002e90d  pop     rdi
0x18002e90e  pop     rbp
0x18002e90f  retn
0x1800c5432  push    rbp
0x1800c5434  sub     rsp, 30h
0x1800c5438  lea     rbp, [rdx+30h]
0x1800c543c  mov     rax, [rcx]
0x1800c543f  xor     ecx, ecx
0x1800c5441  cmp     dword ptr [rax], 0C00000FDh
0x1800c5447  setz    cl
0x1800c544a  mov     eax, ecx
0x1800c544c  add     rsp, 30h
0x1800c5450  pop     rbp
0x1800c5451  retn
```
