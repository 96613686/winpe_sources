# EcbTraceSaveTrace

- ea: `0x1800b37dc`
- end: `0x1800b398c`
- name: `EcbTraceSaveTrace`
- size: `432`
- prototype: `HRESULT __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001c230`

## callees

- `0x18001b9cc`
- `0x180020ee8`
- `0x180021e0c`
- `0x1800637e4`
- `0x1800b3330`
- `0x1800b37dc`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b38f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3960`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b38f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3960`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b388e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b3956`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b388e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b3956`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800b38ea`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800b38ea`

## string_xrefs

- `0x1800b38a1`: `ERROR: Failed to delete %ws, error %d\n`
- `0x1800b3902`: `ERROR: Failed to move %ws to %ws, error %d\n`

## pseudocode

```c
HRESULT __fastcall EcbTraceSaveTrace(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT result; // eax
  const WCHAR *v7; // rbx
  __int64 v8; // rcx
  DWORD LastError; // eax
  __int64 v10; // [rsp+20h] [rbp-E0h]
  int v11; // [rsp+34h] [rbp-CCh] BYREF
  int v12; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF

  v11 = 0;
  v12 = 0;
  result = EcbTraceGetNextFileWriteIndex(a1, &v11, pszDest);
  if ( !result )
  {
    EcbUtilsOut(16, "INFO: Saving into %ws\n", pszDest);
    result = EcbFileExtentsSave(a1 + 664, pszDest, a1, a2, a3);
    if ( !result )
    {
      v7 = (const WCHAR *)(a1 + 64);
      if ( (*(_DWORD *)(*(_QWORD *)&PfSvcGlobals + 244LL) & 0x4000000) != 0 )
      {
        result = StringCchPrintfW(pszDest, 0x104u, L"%ws.old", v7);
        if ( result < 0 )
          return (unsigned __int16)result;
        if ( !MoveFileExW(v7, pszDest, 1u) )
        {
          LODWORD(v10) = GetLastError();
          EcbUtilsOut(1, "ERROR: Failed to move %ws to %ws, error %d\n", v7, pszDest, v10);
        }
      }
      else if ( !DeleteFileW(v7) )
      {
        LastError = GetLastError();
        EcbUtilsOut(1, "ERROR: Failed to delete %ws, error %d\n", v7, LastError);
      }
      EcbTraceGetNextFileReadIndex(v8, 0, &v12, pszDest);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800b37dc  mov     [rsp-8+arg_18], rbx
0x1800b37e1  push    rbp
0x1800b37e2  push    rsi
0x1800b37e3  push    rdi
0x1800b37e4  lea     rbp, [rsp-160h]
0x1800b37ec  sub     rsp, 260h
0x1800b37f3  mov     rax, cs:__security_cookie
0x1800b37fa  xor     rax, rsp
0x1800b37fd  mov     [rbp+170h+var_20], rax
0x1800b3804  mov     rsi, r8
0x1800b3807  mov     [rsp+270h+var_23C], 0
0x1800b380f  mov     rdi, rdx
0x1800b3812  mov     [rsp+270h+var_238], 0
0x1800b381a  lea     r8, [rsp+270h+pszDest]
0x1800b381f  mov     [rsp+270h+var_240], 0
0x1800b3827  lea     rdx, [rsp+270h+var_23C]
0x1800b382c  mov     rbx, rcx
0x1800b382f  call    EcbTraceGetNextFileWriteIndex
0x1800b3834  test    eax, eax
0x1800b3836  jnz     loc_1800B396A
0x1800b383c  lea     r8, [rsp+270h+pszDest]
0x1800b3841  lea     rdx, aInfoSavingInto; "INFO: Saving into %ws\n"
0x1800b3848  lea     ecx, [rax+10h]
0x1800b384b  call    EcbUtilsOut
0x1800b3850  lea     rcx, [rbx+298h]
0x1800b3857  mov     [rsp+270h+var_250], rsi
0x1800b385c  mov     r9, rdi
0x1800b385f  lea     rdx, [rsp+270h+pszDest]
0x1800b3864  mov     r8, rbx
0x1800b3867  call    EcbFileExtentsSave
0x1800b386c  test    eax, eax
0x1800b386e  jnz     loc_1800B396A
0x1800b3874  mov     rax, cs:PfSvcGlobals
0x1800b387b  add     rbx, 40h ; '@'
0x1800b387f  test    dword ptr [rax+0F4h], 4000000h
0x1800b3889  jnz     short loc_1800B38B7
0x1800b388b  mov     rcx, rbx; lpFileName
0x1800b388e  call    cs:__imp_DeleteFileW
0x1800b3894  test    eax, eax
0x1800b3896  jnz     short loc_1800B3917
0x1800b3898  call    cs:__imp_GetLastError
0x1800b389e  mov     r8, rbx
0x1800b38a1  lea     rdx, aErrorFailedToD; "ERROR: Failed to delete %ws, error %d\n"
0x1800b38a8  mov     r9d, eax
0x1800b38ab  mov     ecx, 1
0x1800b38b0  call    EcbUtilsOut
0x1800b38b5  jmp     short loc_1800B3917
0x1800b38b7  mov     r9, rbx
0x1800b38ba  lea     r8, aWsOld; "%ws.old"
0x1800b38c1  mov     edx, 104h; cchDest
0x1800b38c6  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800b38cb  call    StringCchPrintfW
0x1800b38d0  test    eax, eax
0x1800b38d2  jns     short loc_1800B38DC
0x1800b38d4  movzx   eax, ax
0x1800b38d7  jmp     loc_1800B396A
0x1800b38dc  mov     r8d, 1; dwFlags
0x1800b38e2  lea     rdx, [rsp+270h+pszDest]; lpNewFileName
0x1800b38e7  mov     rcx, rbx; lpExistingFileName
0x1800b38ea  call    cs:__imp_MoveFileExW
0x1800b38f0  test    eax, eax
0x1800b38f2  jnz     short loc_1800B3917
0x1800b38f4  call    cs:__imp_GetLastError
0x1800b38fa  lea     r9, [rsp+270h+pszDest]
0x1800b38ff  mov     r8, rbx
0x1800b3902  lea     rdx, aErrorFailedToM; "ERROR: Failed to move %ws to %ws, error"...
0x1800b3909  mov     dword ptr [rsp+270h+var_250], eax
0x1800b390d  mov     ecx, 1
0x1800b3912  call    EcbUtilsOut
0x1800b3917  lea     rax, [rsp+270h+var_240]
0x1800b391c  xor     edx, edx
0x1800b391e  lea     r9, [rsp+270h+pszDest]
0x1800b3923  mov     [rsp+270h+var_248], rax
0x1800b3928  lea     r8, [rsp+270h+var_238]
0x1800b392d  call    EcbTraceGetNextFileReadIndex
0x1800b3932  test    eax, eax
0x1800b3934  jnz     short loc_1800B3968
0x1800b3936  cmp     [rsp+270h+var_240], 5
0x1800b393b  jbe     short loc_1800B3968
0x1800b393d  lea     r8, [rsp+270h+pszDest]
0x1800b3942  lea     rdx, aInfoDeletingFi; "INFO: Deleting file %ws\n"
0x1800b3949  lea     ecx, [rax+10h]
0x1800b394c  call    EcbUtilsOut
0x1800b3951  lea     rcx, [rsp+270h+pszDest]; lpFileName
0x1800b3956  call    cs:__imp_DeleteFileW
0x1800b395c  test    eax, eax
0x1800b395e  jnz     short loc_1800B3968
0x1800b3960  call    cs:__imp_GetLastError
0x1800b3966  jmp     short loc_1800B396A
0x1800b3968  xor     eax, eax
0x1800b396a  mov     rcx, [rbp+170h+var_20]
0x1800b3971  xor     rcx, rsp; StackCookie
0x1800b3974  call    __security_check_cookie
0x1800b3979  mov     rbx, [rsp+270h+arg_18]
0x1800b3981  add     rsp, 260h
0x1800b3988  pop     rdi
0x1800b3989  pop     rsi
0x1800b398a  pop     rbp
0x1800b398b  retn
```
