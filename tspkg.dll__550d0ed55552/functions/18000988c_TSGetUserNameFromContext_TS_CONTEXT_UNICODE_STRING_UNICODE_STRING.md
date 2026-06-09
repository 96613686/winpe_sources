# TSGetUserNameFromContext(_TS_CONTEXT *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x18000988c`
- end: `0x1800099a1`
- name: `?TSGetUserNameFromContext@@YAJPEAU_TS_CONTEXT@@PEAU_UNICODE_STRING@@1@Z`
- size: `277`
- prototype: `int(struct _TS_CONTEXT *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019958`

## callees

- `0x18000988c`
- `0x180009cac`
- `0x18000b550`
- `0x18000c1a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009945`
- `SspiCli!ImpersonateSecurityContext` at `0x1800098ea`
- `SspiCli!ImpersonateSecurityContext` at `0x1800098ea`
- `SspiCli!GetUserNameExW` at `0x18000990d`
- `SspiCli!GetUserNameExW` at `0x18000993b`
- `SspiCli!GetUserNameExW` at `0x18000990d`
- `SspiCli!GetUserNameExW` at `0x18000993b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009978`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009978`
- `ntdll!RtlGetLastNtStatus` at `0x18000994f`
- `ntdll!RtlGetLastNtStatus` at `0x18000994f`

## pseudocode

```c
__int64 __fastcall TSGetUserNameFromContext(
        struct _TS_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3)
{
  NTSTATUS LastNtStatus; // ebx
  struct _UNICODE_STRING *v7; // r8
  DWORD LastError; // eax
  ULONG nSize[4]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR NameBuffer[520]; // [rsp+30h] [rbp-428h] BYREF

  memset_0(NameBuffer, 0, 0x404u);
  nSize[0] = 514;
  if ( !a1 )
    return 3221225485LL;
  if ( !a2 )
    return 0;
  if ( ImpersonateSecurityContext((PCtxtHandle)((char *)a1 + 24)) >= 0 )
  {
    if ( GetUserNameExW(NameDnsDomain, NameBuffer, nSize) )
      goto LABEL_14;
    LastError = GetLastError();
    if ( LastError == 1332 )
    {
      nSize[0] = 514;
      if ( GetUserNameExW(NameSamCompatible, NameBuffer, nSize) )
        goto LABEL_14;
      LastError = GetLastError();
    }
    if ( LastError )
    {
      LastNtStatus = RtlGetLastNtStatus();
      if ( LastNtStatus < 0 )
      {
LABEL_16:
        RevertToSelf();
        return (unsigned int)LastNtStatus;
      }
LABEL_13:
      LastNtStatus = -1073741823;
      goto LABEL_16;
    }
LABEL_14:
    if ( nSize[0] )
    {
      LastNtStatus = TSSplitName(NameBuffer, a2, v7);
      goto LABEL_16;
    }
    goto LABEL_13;
  }
  return (unsigned int)-1073741823;
}

```

## disassembly

```asm
0x18000988c  mov     [rsp+arg_10], rbx
0x180009891  push    rdi
0x180009892  sub     rsp, 450h
0x180009899  mov     rax, cs:__security_cookie
0x1800098a0  xor     rax, rsp
0x1800098a3  mov     [rsp+458h+var_18], rax
0x1800098ab  mov     rbx, rdx
0x1800098ae  mov     rdi, rcx
0x1800098b1  xor     edx, edx; Val
0x1800098b3  lea     rcx, [rsp+458h+NameBuffer]; void *
0x1800098b8  mov     r8d, 404h; Size
0x1800098be  call    memset_0
0x1800098c3  mov     [rsp+458h+nSize], 202h
0x1800098cb  test    rdi, rdi
0x1800098ce  jnz     short loc_1800098DA
0x1800098d0  mov     eax, 0C000000Dh
0x1800098d5  jmp     loc_180009980
0x1800098da  test    rbx, rbx
0x1800098dd  jnz     short loc_1800098E6
0x1800098df  xor     eax, eax
0x1800098e1  jmp     loc_180009980
0x1800098e6  lea     rcx, [rdi+18h]; phContext
0x1800098ea  call    cs:__imp_ImpersonateSecurityContext
0x1800098f0  test    eax, eax
0x1800098f2  jns     short loc_1800098FE
0x1800098f4  mov     ebx, 0C0000001h
0x1800098f9  jmp     loc_18000997E
0x1800098fe  lea     r8, [rsp+458h+nSize]; nSize
0x180009903  mov     ecx, 0Ch; NameFormat
0x180009908  lea     rdx, [rsp+458h+NameBuffer]; lpNameBuffer
0x18000990d  call    cs:__imp_GetUserNameExW
0x180009913  test    al, al
0x180009915  jnz     short loc_180009962
0x180009917  call    cs:__imp_GetLastError
0x18000991d  cmp     eax, 534h
0x180009922  jnz     short loc_18000994B
0x180009924  lea     r8, [rsp+458h+nSize]; nSize
0x180009929  mov     [rsp+458h+nSize], 202h
0x180009931  lea     rdx, [rsp+458h+NameBuffer]; lpNameBuffer
0x180009936  mov     ecx, 2; NameFormat
0x18000993b  call    cs:__imp_GetUserNameExW
0x180009941  test    al, al
0x180009943  jnz     short loc_180009962
0x180009945  call    cs:__imp_GetLastError
0x18000994b  test    eax, eax
0x18000994d  jz      short loc_180009962
0x18000994f  call    cs:__imp_RtlGetLastNtStatus
0x180009955  mov     ebx, eax
0x180009957  test    eax, eax
0x180009959  js      short loc_180009978
0x18000995b  mov     ebx, 0C0000001h
0x180009960  jmp     short loc_180009978
0x180009962  cmp     [rsp+458h+nSize], 0
0x180009967  jz      short loc_18000995B
0x180009969  mov     rdx, rbx; struct _UNICODE_STRING *
0x18000996c  lea     rcx, [rsp+458h+NameBuffer]; Src
0x180009971  call    ?TSSplitName@@YAJPEAGPEAU_UNICODE_STRING@@1@Z; TSSplitName(ushort *,_UNICODE_STRING *,_UNICODE_STRING *)
0x180009976  mov     ebx, eax
0x180009978  call    cs:__imp_RevertToSelf
0x18000997e  mov     eax, ebx
0x180009980  mov     rcx, [rsp+458h+var_18]
0x180009988  xor     rcx, rsp; StackCookie
0x18000998b  call    __security_check_cookie
0x180009990  mov     rbx, [rsp+458h+arg_10]
0x180009998  add     rsp, 450h
0x18000999f  pop     rdi
0x1800099a0  retn
```
