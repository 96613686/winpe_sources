# LogEncryptionStatus(void)

- ea: `0x1800075e4`
- end: `0x18000774e`
- name: `?LogEncryptionStatus@@YAXXZ`
- size: `362`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x180005da0`

## callees

- `0x180001294`
- `0x180001990`
- `0x180002410`
- `0x180002e6e`
- `0x180002edc`
- `0x180003a80`
- `0x1800075e4`
- `0x180008020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000772c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000772c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007636`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180007636`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18000766b`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18000766b`
- `ext-ms-win-fveapi-query-l1-1-0!FveGetStatusW` at `0x1800076ae`
- `ext-ms-win-fveapi-query-l1-1-0!FveGetStatusW` at `0x1800076ae`

## pseudocode

```c
void LogEncryptionStatus(void)
{
  int StatusW; // eax
  __int64 v1; // rdx
  __int64 v2; // r9
  __int64 v3; // r8
  __int64 v4; // r9
  DWORD LastError; // eax
  _DWORD v6[4]; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v7[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v8[136]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Dst; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR szVolumeMountPoint; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR szVolumeName[264]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(v7, 0, 0x90u);
  if ( (unsigned __int8)IsFveGetStatusWPresent() )
  {
    if ( ExpandEnvironmentStringsW(L"%SystemDrive%", &Dst, 3u) != 3 )
      CException::ThrowException(2147500037LL, 1, 0);
    StringCchPrintfW(&szVolumeMountPoint, 4u, L"%c:\\", Dst);
    if ( !GetVolumeNameForVolumeMountPointW(&szVolumeMountPoint, szVolumeName, 0x105u) && GetLastError() )
    {
      LastError = GetLastError();
      CException::ThrowException(LastError, 0, 0);
    }
    memset_0(v8, 0, sizeof(v8));
    v7[0] = 144;
    v7[1] = 10;
    StatusW = FveGetStatusW(szVolumeName, v7);
    if ( StatusW < 0 )
      CException::ThrowException((unsigned int)StatusW, 1, 0);
    if ( (unsigned int)dword_18001C000 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18001C000, v1, v8[4] & 1, v2) )
      {
        v6[0] = v3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18001C000,
          (__int64)byte_180017E15,
          v3,
          v4,
          (__int64)v6);
      }
    }
  }
}

```

## disassembly

```asm
0x1800075e4  push    rbp
0x1800075e6  lea     rbp, [rsp-200h]
0x1800075ee  sub     rsp, 300h
0x1800075f5  mov     rax, cs:__security_cookie
0x1800075fc  xor     rax, rsp
0x1800075ff  mov     [rbp+200h+var_10], rax
0x180007606  xor     edx, edx; Val
0x180007608  lea     rcx, [rsp+300h+var_2C0]; void *
0x18000760d  mov     r8d, 90h; Size
0x180007613  call    memset_0
0x180007618  call    IsFveGetStatusWPresent
0x18000761d  test    al, al
0x18000761f  jz      loc_180007702
0x180007625  mov     r8d, 3; nSize
0x18000762b  lea     rdx, [rbp+200h+Dst]; lpDst
0x18000762f  lea     rcx, Src; "%SystemDrive%"
0x180007636  call    cs:__imp_ExpandEnvironmentStringsW
0x18000763c  cmp     eax, 3
0x18000763f  jnz     loc_18000771A
0x180007645  movzx   r9d, [rbp+200h+Dst]
0x18000764a  lea     r8, aC_0; "%c:\\"
0x180007651  lea     edx, [rax+1]; unsigned __int64
0x180007654  lea     rcx, [rbp+200h+szVolumeMountPoint]; unsigned __int16 *
0x180007658  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000765d  mov     r8d, 105h; cchBufferLength
0x180007663  lea     rdx, [rbp+200h+szVolumeName]; lpszVolumeName
0x180007667  lea     rcx, [rbp+200h+szVolumeMountPoint]; lpszVolumeMountPoint
0x18000766b  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180007671  test    eax, eax
0x180007673  jnz     short loc_180007683
0x180007675  call    cs:__imp_GetLastError
0x18000767b  test    eax, eax
0x18000767d  jnz     loc_18000772C
0x180007683  xor     edx, edx; Val
0x180007685  lea     rcx, [rsp+300h+var_2B8]; void *
0x18000768a  mov     r8d, 88h; Size
0x180007690  call    memset_0
0x180007695  lea     rdx, [rsp+300h+var_2C0]
0x18000769a  mov     [rsp+300h+var_2C0], 90h
0x1800076a2  lea     rcx, [rbp+200h+szVolumeName]
0x1800076a6  mov     [rsp+300h+var_2BC], 0Ah
0x1800076ae  call    cs:__imp_FveGetStatusW
0x1800076b4  test    eax, eax
0x1800076b6  js      loc_18000773F
0x1800076bc  mov     r8d, [rsp+300h+var_2B4]
0x1800076c1  mov     eax, cs:dword_18001C000
0x1800076c7  and     r8d, 1
0x1800076cb  cmp     eax, 5
0x1800076ce  jbe     short loc_180007702
0x1800076d0  lea     rcx, dword_18001C000
0x1800076d7  call    _tlgKeywordOn
0x1800076dc  test    al, al
0x1800076de  jz      short loc_180007702
0x1800076e0  lea     rax, [rsp+300h+var_2D0]
0x1800076e5  mov     [rsp+300h+var_2D0], r8d
0x1800076ea  lea     rdx, byte_180017E15
0x1800076f1  mov     [rsp+300h+var_2E0], rax
0x1800076f6  lea     rcx, dword_18001C000
0x1800076fd  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180007702  mov     rcx, [rbp+200h+var_10]
0x180007709  xor     rcx, rsp; StackCookie
0x18000770c  call    __security_check_cookie
0x180007711  add     rsp, 300h
0x180007718  pop     rbp
0x180007719  retn
0x18000771a  xor     r8d, r8d
0x18000771d  mov     ecx, 80004005h
0x180007722  lea     edx, [r8+1]
0x180007726  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000772c  call    cs:__imp_GetLastError
0x180007732  xor     r8d, r8d
0x180007735  xor     edx, edx
0x180007737  mov     ecx, eax
0x180007739  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000773f  xor     r8d, r8d
0x180007742  mov     ecx, eax
0x180007744  lea     edx, [r8+1]
0x180007748  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
```
