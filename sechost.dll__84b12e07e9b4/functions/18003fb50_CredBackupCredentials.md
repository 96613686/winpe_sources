# CredBackupCredentials

- ea: `0x18003fb50`
- end: `0x18003fcb7`
- name: `CredBackupCredentials`
- size: `359`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x18000f6d0`
- `0x180015c1c`
- `0x18003fb50`
- `0x180041a54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fc97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fc97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003fbdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003fbdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fc58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fc8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fc58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fc8b`
- `RPCRT4!NdrClientCall3` at `0x18003fc2e`
- `RPCRT4!NdrClientCall3` at `0x18003fc2e`

## pseudocode

```c
__int64 __fastcall CredBackupCredentials(__int64 a1, __int64 a2, void *a3, unsigned int a4, char a5)
{
  DWORD v7; // ebx
  int v8; // eax
  _BYTE *v9; // rax
  __int64 v10; // rcx
  HLOCAL hMem; // [rsp+58h] [rbp-30h] BYREF
  CLIENT_CALL_RETURN v13; // [rsp+60h] [rbp-28h]
  HLOCAL v14; // [rsp+A0h] [rbp+18h] BYREF
  ULONG v15; // [rsp+A8h] [rbp+20h] BYREF

  hMem = 0;
  v14 = a3;
  v15 = a4;
  v7 = CredpAllocStrFromStr(3, a2, 0, &hMem);
  if ( !v7 )
  {
    if ( (a5 & 1) != 0 || (v8 = CredpEncodeSecretEx(0, 0, a3, a4, &v14, &v15, 0), v8 >= 0) )
    {
      GetCurrentProcessId();
      v13.Simple = 0;
      v13.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800524F0, 0x5Eu, 0).Pointer;
      v7 = CredpNtStatusToWinStatus(LODWORD(v13.Pointer));
    }
    else
    {
      v7 = CredpNtStatusToWinStatus((unsigned int)v8);
    }
  }
  if ( hMem )
    LocalFree(hMem);
  v9 = v14;
  if ( v14 )
  {
    v10 = v15;
    if ( v15 )
    {
      do
      {
        *v9++ = 0;
        --v10;
      }
      while ( v10 );
    }
    LocalFree(v14);
  }
  if ( !v7 )
    return 1;
  SetLastError(v7);
  return 0;
}

```

## disassembly

```asm
0x18003fb50  mov     rax, rsp
0x18003fb53  mov     [rax+8], rbx
0x18003fb57  push    rsi
0x18003fb58  push    rdi
0x18003fb59  push    r14
0x18003fb5b  sub     rsp, 70h
0x18003fb5f  mov     edi, r9d
0x18003fb62  mov     rsi, r8
0x18003fb65  mov     r14, rcx
0x18003fb68  mov     qword ptr [rax-30h], 0
0x18003fb70  mov     [rax+18h], r8
0x18003fb74  mov     [rax+20h], r9d
0x18003fb78  lea     r9, [rax-30h]
0x18003fb7c  xor     r8d, r8d
0x18003fb7f  lea     ecx, [r8+3]
0x18003fb83  call    CredpAllocStrFromStr
0x18003fb88  mov     ebx, eax
0x18003fb8a  test    eax, eax
0x18003fb8c  jnz     loc_18003FC4E
0x18003fb92  mov     ebx, [rsp+88h+arg_20]
0x18003fb99  test    bl, 1
0x18003fb9c  jnz     short loc_18003FBDF
0x18003fb9e  mov     [rsp+88h+var_58], 0
0x18003fba7  lea     rax, [rsp+88h+arg_18]
0x18003fbaf  mov     [rsp+88h+var_60], rax
0x18003fbb4  lea     rax, [rsp+88h+arg_10]
0x18003fbbc  mov     [rsp+88h+var_68], rax
0x18003fbc1  mov     r9d, edi
0x18003fbc4  mov     r8, rsi
0x18003fbc7  xor     edx, edx
0x18003fbc9  xor     ecx, ecx
0x18003fbcb  call    CredpEncodeSecretEx
0x18003fbd0  test    eax, eax
0x18003fbd2  jns     short loc_18003FBDF
0x18003fbd4  mov     ecx, eax
0x18003fbd6  call    CredpNtStatusToWinStatus
0x18003fbdb  mov     ebx, eax
0x18003fbdd  jmp     short loc_18003FC4E
0x18003fbdf  call    cs:__imp_GetCurrentProcessId
0x18003fbe5  mov     [rsp+88h+var_28], 0
0x18003fbee  mov     [rsp+88h+var_40], ebx
0x18003fbf2  mov     ecx, [rsp+88h+arg_18]
0x18003fbf9  mov     [rsp+88h+var_48], ecx
0x18003fbfd  mov     rcx, [rsp+88h+arg_10]
0x18003fc05  mov     [rsp+88h+var_50], rcx
0x18003fc0a  mov     rcx, [rsp+88h+hMem]
0x18003fc0f  mov     [rsp+88h+var_58], rcx
0x18003fc14  mov     dword ptr [rsp+88h+var_60], eax
0x18003fc18  mov     [rsp+88h+var_68], r14
0x18003fc1d  xor     r9d, r9d
0x18003fc20  xor     r8d, r8d; pReturnValue
0x18003fc23  lea     edx, [r9+5Eh]; nProcNum
0x18003fc27  lea     rcx, stru_1800524F0; pProxyInfo
0x18003fc2e  call    cs:__imp_NdrClientCall3
0x18003fc34  mov     [rsp+88h+var_28], rax
0x18003fc39  mov     ecx, eax
0x18003fc3b  call    CredpNtStatusToWinStatus
0x18003fc40  mov     ebx, eax
0x18003fc42  mov     [rsp+88h+var_38], eax
0x18003fc46  jmp     short loc_18003FC4E
0x18003fc48  mov     ebx, eax
0x18003fc4a  mov     [rsp+88h+var_38], eax
0x18003fc4e  mov     rcx, [rsp+88h+hMem]; hMem
0x18003fc53  test    rcx, rcx
0x18003fc56  jz      short loc_18003FC5E
0x18003fc58  call    cs:__imp_LocalFree
0x18003fc5e  mov     rax, [rsp+88h+arg_10]
0x18003fc66  test    rax, rax
0x18003fc69  jz      short loc_18003FC91
0x18003fc6b  mov     ecx, [rsp+88h+arg_18]
0x18003fc72  test    rcx, rcx
0x18003fc75  jz      short loc_18003FC83
0x18003fc77  mov     byte ptr [rax], 0
0x18003fc7a  inc     rax
0x18003fc7d  sub     rcx, 1
0x18003fc81  jnz     short loc_18003FC77
0x18003fc83  mov     rcx, [rsp+88h+arg_10]; hMem
0x18003fc8b  call    cs:__imp_LocalFree
0x18003fc91  test    ebx, ebx
0x18003fc93  jz      short loc_18003FCA1
0x18003fc95  mov     ecx, ebx; dwErrCode
0x18003fc97  call    cs:__imp_SetLastError
0x18003fc9d  xor     eax, eax
0x18003fc9f  jmp     short loc_18003FCA6
0x18003fca1  mov     eax, 1
0x18003fca6  mov     rbx, [rsp+88h+arg_0]
0x18003fcae  add     rsp, 70h
0x18003fcb2  pop     r14
0x18003fcb4  pop     rdi
0x18003fcb5  pop     rsi
0x18003fcb6  retn
0x1800506cc  push    rbp
0x1800506ce  sub     rsp, 50h
0x1800506d2  mov     rbp, rdx
0x1800506d5  mov     rcx, [rcx]
0x1800506d8  mov     ecx, [rcx]; ExceptionCode
0x1800506da  call    cs:__imp_I_RpcExceptionFilter
0x1800506e0  nop
0x1800506e1  add     rsp, 50h
0x1800506e5  pop     rbp
0x1800506e6  retn
```
