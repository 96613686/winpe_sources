# WTSGetListenerSecurityA

- ea: `0x18000af60`
- end: `0x18000b027`
- name: `WTSGetListenerSecurityA`
- size: `199`
- prototype: `BOOL __stdcall(HANDLE hServer, PVOID pReserved, DWORD Reserved, LPSTR pListenerName, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD nLength, LPDWORD lpnLengthNeeded)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008acc`
- `0x18000af60`
- `0x18000b030`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000afa2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b015`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000afa2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000affd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000affd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b00d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b00d`

## pseudocode

```c
BOOL __stdcall WTSGetListenerSecurityA(
        HANDLE hServer,
        PVOID pReserved,
        DWORD Reserved,
        LPSTR pListenerName,
        SECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        DWORD nLength,
        LPDWORD lpnLengthNeeded)
{
  BOOL v8; // esi
  DWORD v12; // ecx
  DWORD LastError; // ebx
  LPWSTR pListenerNamea; // [rsp+88h] [rbp+20h] BYREF

  v8 = 0;
  pListenerNamea = 0;
  if ( !pListenerName )
  {
    v12 = 87;
LABEL_8:
    SetLastError(v12);
    return v8;
  }
  if ( (unsigned int)CopyStringA((__int64)pListenerName, &pListenerNamea, 0) )
    v8 = WTSGetListenerSecurityW(
           hServer,
           pReserved,
           Reserved,
           pListenerNamea,
           SecurityInformation,
           pSecurityDescriptor,
           nLength,
           lpnLengthNeeded);
  else
    SetLastError(0x57u);
  if ( pListenerNamea )
  {
    LastError = GetLastError();
    LocalFree(pListenerNamea);
    v12 = LastError;
    goto LABEL_8;
  }
  return v8;
}

```

## disassembly

```asm
0x18000af60  mov     rax, rsp
0x18000af63  push    rbx
0x18000af64  push    rbp
0x18000af65  push    rsi
0x18000af66  push    r14
0x18000af68  sub     rsp, 48h
0x18000af6c  xor     esi, esi
0x18000af6e  mov     ebx, r8d
0x18000af71  mov     [rax+20h], rsi
0x18000af75  mov     rbp, rdx
0x18000af78  mov     r14, rcx
0x18000af7b  test    r9, r9
0x18000af7e  jnz     short loc_18000AF88
0x18000af80  lea     ecx, [rsi+57h]
0x18000af83  jmp     loc_18000B015
0x18000af88  xor     r8d, r8d
0x18000af8b  lea     rdx, [rsp+68h+pListenerName]
0x18000af93  mov     rcx, r9
0x18000af96  call    _CopyStringA
0x18000af9b  test    eax, eax
0x18000af9d  jnz     short loc_18000AFAA
0x18000af9f  lea     ecx, [rax+57h]; dwErrCode
0x18000afa2  call    cs:__imp_SetLastError
0x18000afa8  jmp     short loc_18000AFF2
0x18000afaa  mov     rax, [rsp+68h+lpnLengthNeeded]
0x18000afb2  mov     r8d, ebx; Reserved
0x18000afb5  mov     r9, [rsp+68h+pListenerName]; pListenerName
0x18000afbd  mov     rdx, rbp; pReserved
0x18000afc0  mov     [rsp+68h+var_30], rax; lpnLengthNeeded
0x18000afc5  mov     rcx, r14; hServer
0x18000afc8  mov     eax, [rsp+68h+nLength]
0x18000afcf  mov     [rsp+68h+var_38], eax; nLength
0x18000afd3  mov     rax, [rsp+68h+pSecurityDescriptor]
0x18000afdb  mov     [rsp+68h+var_40], rax; pSecurityDescriptor
0x18000afe0  mov     eax, [rsp+68h+SecurityInformation]
0x18000afe7  mov     [rsp+68h+var_48], eax; SecurityInformation
0x18000afeb  call    WTSGetListenerSecurityW
0x18000aff0  mov     esi, eax
0x18000aff2  cmp     [rsp+68h+pListenerName], 0
0x18000affb  jz      short loc_18000B01B
0x18000affd  call    cs:__imp_GetLastError
0x18000b003  mov     rcx, [rsp+68h+pListenerName]; hMem
0x18000b00b  mov     ebx, eax
0x18000b00d  call    cs:__imp_LocalFree
0x18000b013  mov     ecx, ebx; dwErrCode
0x18000b015  call    cs:__imp_SetLastError
0x18000b01b  mov     eax, esi
0x18000b01d  add     rsp, 48h
0x18000b021  pop     r14
0x18000b023  pop     rsi
0x18000b024  pop     rbp
0x18000b025  pop     rbx
0x18000b026  retn
```
