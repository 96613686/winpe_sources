# CWdsSimpleDeviceController::SetMetadata(ushort const *,CWdsMetadata const *)

- ea: `0x180006a60`
- end: `0x180006b2e`
- name: `?SetMetadata@CWdsSimpleDeviceController@@AEAAKPEBGPEBVCWdsMetadata@@@Z`
- size: `206`
- prototype: `unsigned int(CWdsSimpleDeviceController *__hidden this, const unsigned __int16 *, const struct CWdsMetadata *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800055b0`
- `0x1800068d0`

## callees

- `0x1800015d4`
- `0x180005508`
- `0x180005fe8`
- `0x180006a60`
- `0x180006dd8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006ada`
- `KERNEL32!GetLastError` at `0x180006ada`
- `KERNEL32!WritePrivateProfileSectionW` at `0x180006aca`
- `KERNEL32!WritePrivateProfileSectionW` at `0x180006aca`
- `KERNEL32!EnterCriticalSection` at `0x180006a81`
- `KERNEL32!EnterCriticalSection` at `0x180006a81`

## pseudocode

```c
__int64 __fastcall CWdsSimpleDeviceController::SetMetadata(
        CWdsSimpleDeviceController *this,
        const unsigned __int16 *a2,
        const struct CWdsMetadata *a3)
{
  CWdsSimpleDeviceController *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  DWORD LastError; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  char *v14; // [rsp+20h] [rbp-18h] BYREF
  int v15; // [rsp+28h] [rbp-10h]
  LPCWSTR lpString; // [rsp+40h] [rbp+8h] BYREF

  v14 = (char *)this + 72;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v15 = 1;
  lpString = 0;
  v7 = CWdsSimpleDeviceController::MetadataToMultiSz(v6, a3, (unsigned __int16 **)&lpString);
  if ( !(unsigned int)ElValidateWin32(v7, v8, v9, 425)
    && !WritePrivateProfileSectionW(a2, lpString, *((LPCWSTR *)this + 14)) )
  {
    LastError = GetLastError();
    v7 = ElValidateWin32(LastError, v11, v12, 431);
    if ( !v7 )
      v7 = 31;
  }
  if ( lpString )
    operator delete((void *)lpString);
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(&v14);
  return v7;
}

```

## disassembly

```asm
0x180006a60  mov     [rsp+arg_8], rbx
0x180006a65  mov     [rsp+arg_10], rbp
0x180006a6a  push    rsi
0x180006a6b  sub     rsp, 30h
0x180006a6f  mov     rsi, rcx
0x180006a72  mov     rbx, r8
0x180006a75  add     rcx, 48h ; 'H'; lpCriticalSection
0x180006a79  mov     rbp, rdx
0x180006a7c  mov     [rsp+38h+var_18], rcx
0x180006a81  call    cs:__imp_EnterCriticalSection
0x180006a88  nop     dword ptr [rax+rax+00h]
0x180006a8d  lea     r8, [rsp+38h+lpString]; unsigned __int16 **
0x180006a92  mov     [rsp+38h+var_10], 1
0x180006a9a  mov     rdx, rbx; struct CWdsMetadata *
0x180006a9d  mov     [rsp+38h+lpString], 0
0x180006aa6  call    ?MetadataToMultiSz@CWdsSimpleDeviceController@@AEAAKPEBVCWdsMetadata@@PEAPEAG@Z; CWdsSimpleDeviceController::MetadataToMultiSz(CWdsMetadata const *,ushort * *)
0x180006aab  mov     r9d, 1A9h
0x180006ab1  mov     ecx, eax
0x180006ab3  mov     ebx, eax
0x180006ab5  call    ElValidateWin32
0x180006aba  test    eax, eax
0x180006abc  jnz     short loc_180006AFF
0x180006abe  mov     r8, [rsi+70h]; lpFileName
0x180006ac2  mov     rcx, rbp; lpAppName
0x180006ac5  mov     rdx, [rsp+38h+lpString]; lpString
0x180006aca  call    cs:__imp_WritePrivateProfileSectionW
0x180006ad1  nop     dword ptr [rax+rax+00h]
0x180006ad6  test    eax, eax
0x180006ad8  jnz     short loc_180006AFF
0x180006ada  call    cs:__imp_GetLastError
0x180006ae1  nop     dword ptr [rax+rax+00h]
0x180006ae6  mov     ecx, eax
0x180006ae8  mov     r9d, 1AFh
0x180006aee  call    ElValidateWin32
0x180006af3  mov     ebx, eax
0x180006af5  mov     eax, 1Fh
0x180006afa  test    ebx, ebx
0x180006afc  cmovz   ebx, eax
0x180006aff  cmp     [rsp+38h+lpString], 0
0x180006b05  jz      short loc_180006B11
0x180006b07  mov     rcx, [rsp+38h+lpString]; Block
0x180006b0c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006b11  lea     rcx, [rsp+38h+var_18]
0x180006b16  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180006b1b  mov     rbp, [rsp+38h+arg_10]
0x180006b20  mov     eax, ebx
0x180006b22  mov     rbx, [rsp+38h+arg_8]
0x180006b27  add     rsp, 30h
0x180006b2b  pop     rsi
0x180006b2c  retn
```
