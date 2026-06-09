# GetPackageFamilyNameForPackage(ushort * *)

- ea: `0x180009f64`
- end: `0x18000a08e`
- name: `?GetPackageFamilyNameForPackage@@YAJPEAPEAG@Z`
- size: `298`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180008fb4`
- `0x1800098b0`
- `0x180009b00`

## callees

- `0x180009f64`
- `0x180080f94`
- `0x1800814bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009fa0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009fa0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009fb7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a062`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a062`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a02e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a02e`
- `RPCRT4!RpcRevertToSelf` at `0x180009fca`
- `RPCRT4!RpcRevertToSelf` at `0x180009fca`
- `RPCRT4!RpcImpersonateClient` at `0x180009f88`
- `RPCRT4!RpcImpersonateClient` at `0x180009f88`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x180009fe7`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18000a01c`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x180009fe7`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageFamilyNameFromToken` at `0x18000a01c`

## pseudocode

```c
__int64 __fastcall GetPackageFamilyNameForPackage(unsigned __int16 **a1)
{
  void *v2; // rdi
  RPC_STATUS v3; // eax
  int v4; // ebx
  HANDLE CurrentThread; // rax
  LONG PackageFamilyNameFromToken; // eax
  WCHAR *v7; // rsi
  signed int LastError; // eax
  UINT32 packageFamilyNameLength; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  TokenHandle = (void *)-1LL;
  v2 = 0;
  v3 = RpcImpersonateClient(0);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
    {
      v2 = TokenHandle;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    RpcRevertToSelf();
    if ( v4 >= 0 )
    {
      packageFamilyNameLength = 0;
      PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(v2, &packageFamilyNameLength, 0);
      v4 = PackageFamilyNameFromToken;
      if ( PackageFamilyNameFromToken )
      {
        if ( PackageFamilyNameFromToken == 122 )
        {
          v7 = (WCHAR *)operator new(saturated_mul(packageFamilyNameLength, (unsigned int)(PackageFamilyNameFromToken
                                                                                         - 120)));
          v4 = GetPackageFamilyNameFromToken(v2, &packageFamilyNameLength, v7);
          if ( !v4 )
          {
            *a1 = v7;
LABEL_11:
            CloseHandle(v2);
            return (unsigned int)v4;
          }
          operator delete(v7);
        }
        if ( v4 > 0 )
          v4 = (unsigned __int16)v4 | 0x80070000;
        goto LABEL_11;
      }
      v4 = -2147467259;
      goto LABEL_11;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009f64  mov     [rsp+arg_10], rbx
0x180009f69  push    rsi
0x180009f6a  push    rdi
0x180009f6b  push    r14
0x180009f6d  sub     rsp, 20h
0x180009f71  mov     r14, rcx
0x180009f74  mov     qword ptr [rcx], 0
0x180009f7b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009f7f  xor     ecx, ecx; BindingHandle
0x180009f81  mov     [rsp+38h+TokenHandle], rsi
0x180009f86  xor     edi, edi
0x180009f88  call    cs:__imp_RpcImpersonateClient
0x180009f8e  mov     ebx, eax
0x180009f90  test    eax, eax
0x180009f92  jg      loc_18000A080
0x180009f98  test    ebx, ebx
0x180009f9a  js      loc_18000A034
0x180009fa0  call    cs:__imp_GetCurrentThread
0x180009fa6  mov     edx, 0Eh; DesiredAccess
0x180009fab  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180009fb0  mov     rcx, rax; ThreadHandle
0x180009fb3  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180009fb7  call    cs:__imp_OpenThreadToken
0x180009fbd  test    eax, eax
0x180009fbf  jz      loc_18000A062
0x180009fc5  mov     rdi, [rsp+38h+TokenHandle]
0x180009fca  call    cs:__imp_RpcRevertToSelf
0x180009fd0  test    ebx, ebx
0x180009fd2  js      short loc_18000A034
0x180009fd4  xor     r8d, r8d; packageFamilyName
0x180009fd7  mov     [rsp+38h+packageFamilyNameLength], 0
0x180009fdf  lea     rdx, [rsp+38h+packageFamilyNameLength]; packageFamilyNameLength
0x180009fe4  mov     rcx, rdi; token
0x180009fe7  call    cs:__imp_GetPackageFamilyNameFromToken
0x180009fed  mov     ebx, eax
0x180009fef  test    eax, eax
0x180009ff1  jz      short loc_18000A044
0x180009ff3  cmp     eax, 7Ah ; 'z'
0x180009ff6  jnz     short loc_18000A053
0x180009ff8  mov     ecx, [rsp+38h+packageFamilyNameLength]
0x180009ffc  lea     eax, [rbx-78h]
0x180009fff  mul     rcx
0x18000a002  cmovb   rax, rsi
0x18000a006  mov     rcx, rax; Size
0x18000a009  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a00e  mov     r8, rax; packageFamilyName
0x18000a011  lea     rdx, [rsp+38h+packageFamilyNameLength]; packageFamilyNameLength
0x18000a016  mov     rcx, rdi; token
0x18000a019  mov     rsi, rax
0x18000a01c  call    cs:__imp_GetPackageFamilyNameFromToken
0x18000a022  mov     ebx, eax
0x18000a024  test    eax, eax
0x18000a026  jnz     short loc_18000A04B
0x18000a028  mov     [r14], rsi
0x18000a02b  mov     rcx, rdi; hObject
0x18000a02e  call    cs:__imp_CloseHandle
0x18000a034  mov     eax, ebx
0x18000a036  mov     rbx, [rsp+38h+arg_10]
0x18000a03b  add     rsp, 20h
0x18000a03f  pop     r14
0x18000a041  pop     rdi
0x18000a042  pop     rsi
0x18000a043  retn
0x18000a044  mov     ebx, 80004005h
0x18000a049  jmp     short loc_18000A02B
0x18000a04b  mov     rcx, rsi; Block
0x18000a04e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a053  test    ebx, ebx
0x18000a055  jle     short loc_18000A02B
0x18000a057  movzx   ebx, bx
0x18000a05a  or      ebx, 80070000h
0x18000a060  jmp     short loc_18000A02B
0x18000a062  call    cs:__imp_GetLastError
0x18000a068  mov     ebx, eax
0x18000a06a  test    eax, eax
0x18000a06c  jle     loc_180009FCA
0x18000a072  movzx   ebx, ax
0x18000a075  or      ebx, 80070000h
0x18000a07b  jmp     loc_180009FCA
0x18000a080  movzx   ebx, ax
0x18000a083  or      ebx, 80070000h
0x18000a089  jmp     loc_180009F98
```
