# RpcpLookupAccountSid(void *,ushort * *)

- ea: `0x1800a7374`
- end: `0x1800a74e4`
- name: `?RpcpLookupAccountSid@@YAJPEAXPEAPEAG@Z`
- size: `368`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bae38`

## callees

- `0x180023020`
- `0x180023a40`
- `0x1800295d8`
- `0x1800a7374`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7443`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800a7423`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800a7423`

## pseudocode

```c
__int64 __fastcall RpcpLookupAccountSid(PSID Sid, unsigned __int16 **a2)
{
  DWORD v2; // eax
  void *v3; // rdi
  int v4; // esi
  WCHAR *v7; // rax
  WCHAR *v8; // rbx
  DWORD LastError; // eax
  unsigned int v10; // ebx
  enum _SID_NAME_USE peUse; // [rsp+30h] [rbp-48h] BYREF
  _DWORD v13[16]; // [rsp+38h] [rbp-40h] BYREF
  DWORD cchReferencedDomainName; // [rsp+90h] [rbp+18h] BYREF
  DWORD cchName; // [rsp+98h] [rbp+20h] BYREF

  v2 = 256;
  peUse = 0;
  v3 = 0;
  cchName = 256;
  v4 = 0;
  cchReferencedDomainName = 256;
  while ( 1 )
  {
    if ( v4 >= 2 )
      goto LABEL_13;
    v3 = AllocWrapper(saturated_mul(v2, 2u));
    v7 = (WCHAR *)AllocWrapper(saturated_mul(cchReferencedDomainName, 2u));
    v8 = v7;
    if ( !v3 || !v7 )
    {
      FreeWrapper(v3);
      FreeWrapper(v8);
      return 14;
    }
    if ( LookupAccountSidLocalW(Sid, (LPWSTR)v3, &cchName, v7, &cchReferencedDomainName, &peUse) )
    {
      FreeWrapper(v8);
LABEL_13:
      *a2 = (unsigned __int16 *)v3;
      return 0;
    }
    FreeWrapper(v3);
    FreeWrapper(v8);
    LastError = GetLastError();
    if ( LastError != 122 )
      break;
    v2 = cchName;
    ++v4;
  }
  v10 = 14;
  if ( LastError != 14 )
  {
    v10 = 1332;
    if ( LastError != 1332 )
      v10 = 5;
  }
  v13[2] = LastError;
  v13[0] = 3;
  RpcpErrorAddRecord(2u, v10, 0x30Cu, 1, (struct tagParam *)v13);
  return v10;
}

```

## disassembly

```asm
0x1800a7374  mov     r11, rsp
0x1800a7377  mov     [r11+8], rbx
0x1800a737b  push    rbp
0x1800a737c  push    rsi
0x1800a737d  push    rdi
0x1800a737e  push    r12
0x1800a7380  push    r14
0x1800a7382  sub     rsp, 50h
0x1800a7386  mov     eax, 100h
0x1800a738b  mov     [rsp+78h+var_48], 0
0x1800a7393  xor     edi, edi
0x1800a7395  mov     [r11+20h], eax
0x1800a7399  xor     esi, esi
0x1800a739b  mov     [r11+18h], eax
0x1800a739f  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800a73a3  mov     r14, rdx
0x1800a73a6  mov     rbp, rcx
0x1800a73a9  cmp     esi, 2
0x1800a73ac  jge     loc_1800A74B3
0x1800a73b2  mov     ecx, eax
0x1800a73b4  mov     eax, 2
0x1800a73b9  mul     rcx
0x1800a73bc  cmovb   rax, r12
0x1800a73c0  mov     rcx, rax; dwBytes
0x1800a73c3  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a73c8  mov     ecx, [rsp+78h+arg_10]
0x1800a73cf  mov     rdi, rax
0x1800a73d2  mov     eax, 2
0x1800a73d7  mul     rcx
0x1800a73da  cmovb   rax, r12
0x1800a73de  mov     rcx, rax; dwBytes
0x1800a73e1  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a73e6  mov     rbx, rax
0x1800a73e9  test    rdi, rdi
0x1800a73ec  jz      loc_1800A74CD
0x1800a73f2  test    rax, rax
0x1800a73f5  jz      loc_1800A74CD
0x1800a73fb  lea     rax, [rsp+78h+var_48]
0x1800a7400  mov     r9, rbx; ReferencedDomainName
0x1800a7403  mov     [rsp+78h+peUse], rax; peUse
0x1800a7408  lea     r8, [rsp+78h+cchName]; cchName
0x1800a7410  lea     rax, [rsp+78h+arg_10]
0x1800a7418  mov     rdx, rdi; Name
0x1800a741b  mov     rcx, rbp; Sid
0x1800a741e  mov     [rsp+78h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800a7423  call    cs:__imp_LookupAccountSidLocalW
0x1800a742a  nop     dword ptr [rax+rax+00h]
0x1800a742f  test    eax, eax
0x1800a7431  jnz     short loc_1800A74AB
0x1800a7433  mov     rcx, rdi; lpMem
0x1800a7436  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a743b  mov     rcx, rbx; lpMem
0x1800a743e  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a7443  call    cs:__imp_GetLastError
0x1800a744a  nop     dword ptr [rax+rax+00h]
0x1800a744f  cmp     eax, 7Ah ; 'z'
0x1800a7452  jnz     short loc_1800A7462
0x1800a7454  mov     eax, [rsp+78h+cchName]
0x1800a745b  inc     esi
0x1800a745d  jmp     loc_1800A73A9
0x1800a7462  mov     ebx, 0Eh
0x1800a7467  cmp     eax, ebx
0x1800a7469  jz      short loc_1800A747A
0x1800a746b  mov     ebx, 534h
0x1800a7470  mov     ecx, 5
0x1800a7475  cmp     eax, ebx
0x1800a7477  cmovnz  ebx, ecx
0x1800a747a  mov     r9d, 1; int
0x1800a7480  mov     [rsp+78h+var_38], eax
0x1800a7484  lea     rax, [rsp+78h+var_40]
0x1800a7489  mov     [rsp+78h+var_40], 3
0x1800a7491  mov     r8d, 30Ch; unsigned __int16
0x1800a7497  mov     [rsp+78h+cchReferencedDomainName], rax; struct tagParam *
0x1800a749c  mov     edx, ebx; int
0x1800a749e  lea     ecx, [r9+1]; unsigned int
0x1800a74a2  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x1800a74a7  mov     eax, ebx
0x1800a74a9  jmp     short loc_1800A74B8
0x1800a74ab  mov     rcx, rbx; lpMem
0x1800a74ae  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a74b3  mov     [r14], rdi
0x1800a74b6  xor     eax, eax
0x1800a74b8  mov     rbx, [rsp+78h+arg_0]
0x1800a74c0  add     rsp, 50h
0x1800a74c4  pop     r14
0x1800a74c6  pop     r12
0x1800a74c8  pop     rdi
0x1800a74c9  pop     rsi
0x1800a74ca  pop     rbp
0x1800a74cb  retn
0x1800a74cd  mov     rcx, rdi; lpMem
0x1800a74d0  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a74d5  mov     rcx, rbx; lpMem
0x1800a74d8  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a74dd  mov     eax, 0Eh
0x1800a74e2  jmp     short loc_1800A74B8
```
