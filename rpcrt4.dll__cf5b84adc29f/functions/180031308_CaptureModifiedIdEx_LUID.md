# CaptureModifiedIdEx(_LUID *)

- ea: `0x180031308`
- end: `0x180031471`
- name: `?CaptureModifiedIdEx@@YAJPEAU_LUID@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(struct _LUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002b520`
- `0x18002f480`

## callees

- `0x1800295d8`
- `0x180031308`
- `0x1800ceda0`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x180031367`
- `ntdll!NtOpenThreadToken` at `0x180031367`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003141a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003141a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800313fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800313fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003134a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003134a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800313e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800313e6`

## pseudocode

```c
__int64 __fastcall CaptureModifiedIdEx(struct _LUID *a1)
{
  HANDLE CurrentThread; // rax
  unsigned int v3; // edi
  NTSTATUS v4; // eax
  DWORD LastError; // esi
  void *TokenHandle; // [rsp+30h] [rbp-39h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-31h] BYREF
  _DWORD v9[6]; // [rsp+40h] [rbp-29h] BYREF
  _OWORD TokenInformation[3]; // [rsp+58h] [rbp-11h] BYREF
  struct _LUID v11; // [rsp+88h] [rbp+1Fh]

  TokenHandle = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v11 = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  v3 = 14;
  v4 = NtOpenThreadToken(CurrentThread, 0xEu, 1u, &TokenHandle);
  if ( v4 == -1073741790 )
  {
    v3 = 5;
    goto LABEL_17;
  }
  if ( v4 != -1073741700 )
  {
    if ( v4 == -1073741658 )
      goto LABEL_15;
    if ( !v4 )
    {
      if ( TokenHandle == (void *)4294967293LL )
        goto LABEL_3;
      if ( TokenHandle != (void *)4294967294LL )
      {
        if ( GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
          LastError = 0;
        else
          LastError = GetLastError();
        CloseHandle(TokenHandle);
        if ( !LastError )
        {
          v3 = 0;
          *a1 = v11;
          return v3;
        }
LABEL_18:
        *a1 = 0;
        return v3;
      }
LABEL_15:
      a1->LowPart = -2;
      goto LABEL_4;
    }
LABEL_17:
    v9[2] = v4;
    TokenHandle = 0;
    v9[0] = 3;
    RpcpErrorAddRecord(2u, v3, 0x460u, 1, (struct tagParam *)v9);
    goto LABEL_18;
  }
LABEL_3:
  a1->LowPart = -3;
LABEL_4:
  a1->HighPart = 0;
  return 0;
}

```

## disassembly

```asm
0x180031308  push    rbp
0x18003130a  push    rbx
0x18003130b  push    rsi
0x18003130c  push    rdi
0x18003130d  lea     rbp, [rsp-3Fh]
0x180031312  sub     rsp, 0A8h
0x180031319  mov     rax, cs:__security_cookie
0x180031320  xor     rax, rsp
0x180031323  mov     [rbp+57h+var_30], rax
0x180031327  xorps   xmm0, xmm0
0x18003132a  mov     [rbp+57h+TokenHandle], 0
0x180031332  xor     eax, eax
0x180031334  mov     rbx, rcx
0x180031337  movups  [rbp+57h+TokenInformation], xmm0
0x18003133b  mov     [rbp+57h+var_38], rax
0x18003133f  movups  [rbp+57h+var_58], xmm0
0x180031343  mov     [rbp+57h+var_88], eax
0x180031346  movups  [rbp+57h+var_48], xmm0
0x18003134a  call    cs:__imp_GetCurrentThread
0x180031351  nop     dword ptr [rax+rax+00h]
0x180031356  mov     edi, 0Eh
0x18003135b  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18003135f  mov     edx, edi; DesiredAccess
0x180031361  mov     rcx, rax; ThreadHandle
0x180031364  mov     r8b, 1; OpenAsSelf
0x180031367  call    cs:__imp_NtOpenThreadToken
0x18003136e  nop     dword ptr [rax+rax+00h]
0x180031373  cmp     eax, 0C0000022h
0x180031378  jz      loc_180031432
0x18003137e  mov     edx, 0FFFFFFFDh
0x180031383  cmp     eax, 0C000007Ch
0x180031388  jnz     short loc_1800313B0
0x18003138a  mov     [rbx], edx
0x18003138c  mov     dword ptr [rbx+4], 0
0x180031393  xor     edi, edi
0x180031395  mov     eax, edi
0x180031397  mov     rcx, [rbp+57h+var_30]
0x18003139b  xor     rcx, rsp; StackCookie
0x18003139e  call    __security_check_cookie
0x1800313a3  add     rsp, 0A8h
0x1800313aa  pop     rdi
0x1800313ab  pop     rsi
0x1800313ac  pop     rbx
0x1800313ad  pop     rbp
0x1800313ae  retn
0x1800313b0  mov     r8d, 0FFFFFFFEh
0x1800313b6  cmp     eax, 0C00000A6h
0x1800313bb  jz      short loc_18003142A
0x1800313bd  test    eax, eax
0x1800313bf  jnz     short loc_180031437
0x1800313c1  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800313c5  cmp     rcx, rdx
0x1800313c8  jz      short loc_18003138A
0x1800313ca  cmp     rcx, r8
0x1800313cd  jz      short loc_18003142A
0x1800313cf  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800313d5  lea     rax, [rbp+57h+var_88]
0x1800313d9  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800313dd  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x1800313e2  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800313e6  call    cs:__imp_GetTokenInformation
0x1800313ed  nop     dword ptr [rax+rax+00h]
0x1800313f2  test    eax, eax
0x1800313f4  jz      short loc_18003141A
0x1800313f6  xor     esi, esi
0x1800313f8  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800313fc  call    cs:__imp_CloseHandle
0x180031403  nop     dword ptr [rax+rax+00h]
0x180031408  test    esi, esi
0x18003140a  jnz     short loc_180031465
0x18003140c  mov     rax, [rbp+57h+var_38]
0x180031410  xor     edi, edi
0x180031412  mov     [rbx], rax
0x180031415  jmp     loc_180031395
0x18003141a  call    cs:__imp_GetLastError
0x180031421  nop     dword ptr [rax+rax+00h]
0x180031426  mov     esi, eax
0x180031428  jmp     short loc_1800313F8
0x18003142a  mov     [rbx], r8d
0x18003142d  jmp     loc_18003138C
0x180031432  mov     edi, 5
0x180031437  xor     ecx, ecx
0x180031439  mov     [rbp+57h+var_78], eax
0x18003143c  mov     [rbp+57h+TokenHandle], rcx
0x180031440  lea     rax, [rbp+57h+var_80]
0x180031444  mov     r8d, 460h; unsigned __int16
0x18003144a  mov     [rbp+57h+var_80], 3
0x180031451  mov     edx, edi; int
0x180031453  mov     [rsp+0C0h+ReturnLength], rax; struct tagParam *
0x180031458  lea     r9d, [rcx+1]; int
0x18003145c  lea     ecx, [r9+1]; unsigned int
0x180031460  call    ?RpcpErrorAddRecord@@YAXKJGHPEAUtagParam@@@Z; RpcpErrorAddRecord(ulong,long,ushort,int,tagParam *)
0x180031465  mov     qword ptr [rbx], 0
0x18003146c  jmp     loc_180031395
```
