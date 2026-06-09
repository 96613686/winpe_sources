# CLocalFileResMapGenerator::_ValidateFileAccessAndCreateStorageFile(ushort const *,_GUID const &,void * *)

- ea: `0x180064d70`
- end: `0x180064e39`
- name: `?_ValidateFileAccessAndCreateStorageFile@CLocalFileResMapGenerator@@AEAAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `201`
- prototype: `int(CLocalFileResMapGenerator *__hidden this, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180062d00`

## callees

- `0x180064d70`
- `0x18007b454`
- `0x18007b5ac`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180064db6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180064db6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180064d90`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180064d90`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180064d9d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180064d9d`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromPath_PartialTrustCaller` at `0x180064e26`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromPath_PartialTrustCaller` at `0x180064e26`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromPath_FullTrustCaller` at `0x180064dec`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromPath_FullTrustCaller` at `0x180064dec`

## pseudocode

```c
__int64 __fastcall CLocalFileResMapGenerator::_ValidateFileAccessAndCreateStorageFile(
        CLocalFileResMapGenerator *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v7; // ebx
  void *v8; // rcx
  int v9; // eax
  const struct _GUID *v12; // [rsp+60h] [rbp+18h] BYREF

  v12 = a3;
  *a4 = 0;
  if ( !PathIsUNCW(a2) && (PathGetDriveNumberW(a2) == -1 || a2[2] != 92) )
  {
    RoOriginateError(2147942405LL, 0);
    return (unsigned int)-2147024891;
  }
  v8 = (void *)*((_QWORD *)this + 1);
  LOBYTE(v12) = 0;
  v9 = CheckTokenAccessOnFile(v8, a2);
  v7 = v9;
  if ( v9 >= 0 )
    return (unsigned int)STORAGE_CreateStorageItemFromPath_FullTrustCaller(
                           a2,
                           8256,
                           &GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea,
                           a4);
  if ( v9 == -2147024891 && (int)IsAppContainerToken(*((void **)this + 1), (bool *)&v12) >= 0 && (_BYTE)v12 )
    return (unsigned int)STORAGE_CreateStorageItemFromPath_PartialTrustCaller(
                           a2,
                           9,
                           &GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea,
                           a4);
  return v7;
}

```

## disassembly

```asm
0x180064d70  mov     [rsp+arg_10], r8
0x180064d75  push    rbx
0x180064d76  push    rbp
0x180064d77  push    rsi
0x180064d78  push    rdi
0x180064d79  sub     rsp, 28h
0x180064d7d  mov     rbp, rcx
0x180064d80  mov     qword ptr [r9], 0
0x180064d87  mov     rcx, rdx; pszPath
0x180064d8a  mov     rsi, r9
0x180064d8d  mov     rdi, rdx
0x180064d90  call    cs:__imp_PathIsUNCW
0x180064d96  test    eax, eax
0x180064d98  jnz     short loc_180064DC3
0x180064d9a  mov     rcx, rdi; pszPath
0x180064d9d  call    cs:__imp_PathGetDriveNumberW
0x180064da3  cmp     eax, 0FFFFFFFFh
0x180064da6  jz      short loc_180064DAF
0x180064da8  cmp     word ptr [rdi+4], 5Ch ; '\'
0x180064dad  jz      short loc_180064DC3
0x180064daf  xor     edx, edx
0x180064db1  mov     ecx, 80070005h
0x180064db6  call    cs:__imp_RoOriginateError
0x180064dbc  mov     ebx, 80070005h
0x180064dc1  jmp     short loc_180064E2E
0x180064dc3  mov     rcx, [rbp+8]; ClientToken
0x180064dc7  mov     rdx, rdi; pObjectName
0x180064dca  mov     byte ptr [rsp+48h+arg_10], 0
0x180064dcf  call    ?CheckTokenAccessOnFile@@YAJPEAXPEBGK@Z; CheckTokenAccessOnFile(void *,ushort const *,ulong)
0x180064dd4  mov     ebx, eax
0x180064dd6  test    eax, eax
0x180064dd8  js      short loc_180064DF4
0x180064dda  mov     r9, rsi
0x180064ddd  lea     r8, _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea
0x180064de4  mov     edx, 2040h
0x180064de9  mov     rcx, rdi
0x180064dec  call    cs:__imp_STORAGE_CreateStorageItemFromPath_FullTrustCaller
0x180064df2  jmp     short loc_180064E2C
0x180064df4  cmp     eax, 80070005h
0x180064df9  jnz     short loc_180064E2E
0x180064dfb  mov     rcx, [rbp+8]; void *
0x180064dff  lea     rdx, [rsp+48h+arg_10]; bool *
0x180064e04  call    ?IsAppContainerToken@@YAJPEAXPEA_N@Z; IsAppContainerToken(void *,bool *)
0x180064e09  test    eax, eax
0x180064e0b  js      short loc_180064E2E
0x180064e0d  cmp     byte ptr [rsp+48h+arg_10], 0
0x180064e12  jz      short loc_180064E2E
0x180064e14  mov     r9, rsi
0x180064e17  lea     r8, _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea
0x180064e1e  mov     edx, 9
0x180064e23  mov     rcx, rdi
0x180064e26  call    cs:__imp_STORAGE_CreateStorageItemFromPath_PartialTrustCaller
0x180064e2c  mov     ebx, eax
0x180064e2e  mov     eax, ebx
0x180064e30  add     rsp, 28h
0x180064e34  pop     rdi
0x180064e35  pop     rsi
0x180064e36  pop     rbp
0x180064e37  pop     rbx
0x180064e38  retn
```
