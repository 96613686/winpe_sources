# CExtensionList::IsStale(ExtensionListStalenessFlags,int *)

- ea: `0x18007b720`
- end: `0x18007b892`
- name: `?IsStale@CExtensionList@@UEAAJW4ExtensionListStalenessFlags@@PEAH@Z`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18002b1b0`
- `0x18004b430`
- `0x18007b720`
- `0x18007c8a0`
- `0x18007dcd0`
- `0x18007df6c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007b775`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007b7cd`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007b857`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007b775`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007b7cd`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007b857`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007b816`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007b816`

## pseudocode

```c
__int64 __fastcall CExtensionList::IsStale(FILETIME *a1, char a2, _DWORD *a3)
{
  __int64 *v6; // rsi
  __int64 v7; // r8
  const unsigned __int16 *v8; // rcx
  FILETIME FileTime1; // [rsp+30h] [rbp-30h] BYREF
  FILETIME v11; // [rsp+38h] [rbp-28h] BYREF
  IID rclsid; // [rsp+40h] [rbp-20h] BYREF

  *a3 = 0;
  if ( (a2 & 1) == 0 )
    goto LABEL_5;
  FileTime1 = 0;
  if ( (int)CExtensionList::_GetLastExtensionCatalogWriteTime((CExtensionList *)a1, &FileTime1) >= 0 )
    *a3 = CompareFileTime(&FileTime1, a1 + 12) != 0;
  if ( !*a3 )
  {
LABEL_5:
    v6 = (__int64 *)&a1[9];
    if ( (a2 & 2) != 0 )
    {
      v7 = *v6;
      FileTime1 = 0;
      if ( (int)_GetRegKeyLastWriteTime(
                  HKEY_CURRENT_USER,
                  (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AppContract",
                  v7,
                  0,
                  &FileTime1) >= 0 )
        *a3 = CompareFileTime(&FileTime1, a1 + 13) != 0;
    }
    if ( !*a3 && (a2 & 4) != 0 )
    {
      v8 = (const unsigned __int16 *)*v6;
      rclsid = 0;
      if ( (int)UAGetLoggerIDByContractID(v8, &rclsid) >= 0 )
      {
        FileTime1 = 0;
        if ( StringFromCLSID(&rclsid, (LPOLESTR *)&FileTime1) >= 0 )
        {
          v11 = 0;
          if ( (int)_GetRegKeyLastWriteTime(
                      HKEY_CURRENT_USER,
                      (__int64)L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\UserAssist",
                      *(_QWORD *)&FileTime1,
                      0,
                      &v11) >= 0 )
            *a3 = CompareFileTime(&v11, a1 + 14) != 0;
        }
        CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&FileTime1);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18007b720  mov     [rsp-18h+arg_8], rbx
0x18007b725  mov     [rsp-18h+arg_18], rsi
0x18007b72a  push    rbp
0x18007b72b  push    rdi
0x18007b72c  push    r14
0x18007b72e  mov     rbp, rsp
0x18007b731  sub     rsp, 60h
0x18007b735  mov     rax, cs:__security_cookie
0x18007b73c  xor     rax, rsp
0x18007b73f  mov     [rbp+var_10], rax
0x18007b743  mov     dword ptr [r8], 0
0x18007b74a  mov     rbx, r8
0x18007b74d  mov     r14d, edx
0x18007b750  mov     rdi, rcx
0x18007b753  test    dl, 1
0x18007b756  jz      short loc_18007B78D
0x18007b758  lea     rdx, [rbp+FileTime1]; struct _FILETIME *
0x18007b75c  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x18007b764  call    ?_GetLastExtensionCatalogWriteTime@CExtensionList@@AEAAJPEAU_FILETIME@@@Z; CExtensionList::_GetLastExtensionCatalogWriteTime(_FILETIME *)
0x18007b769  test    eax, eax
0x18007b76b  js      short loc_18007B784
0x18007b76d  lea     rdx, [rdi+60h]; lpFileTime2
0x18007b771  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18007b775  call    cs:__imp_CompareFileTime
0x18007b77b  xor     ecx, ecx
0x18007b77d  test    eax, eax
0x18007b77f  setnz   cl
0x18007b782  mov     [rbx], ecx
0x18007b784  cmp     dword ptr [rbx], 0
0x18007b787  jnz     loc_18007B86F
0x18007b78d  lea     rsi, [rdi+48h]
0x18007b791  test    r14b, 2
0x18007b795  jz      short loc_18007B7DC
0x18007b797  mov     r8, [rsi]
0x18007b79a  lea     rax, [rbp+FileTime1]
0x18007b79e  xor     r9d, r9d
0x18007b7a1  mov     [rsp+60h+var_40], rax
0x18007b7a6  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18007b7ad  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x18007b7b5  mov     rcx, 0FFFFFFFF80000001h
0x18007b7bc  call    ?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z; _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)
0x18007b7c1  test    eax, eax
0x18007b7c3  js      short loc_18007B7DC
0x18007b7c5  lea     rdx, [rdi+68h]; lpFileTime2
0x18007b7c9  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x18007b7cd  call    cs:__imp_CompareFileTime
0x18007b7d3  xor     ecx, ecx
0x18007b7d5  test    eax, eax
0x18007b7d7  setnz   cl
0x18007b7da  mov     [rbx], ecx
0x18007b7dc  cmp     dword ptr [rbx], 0
0x18007b7df  jnz     loc_18007B86F
0x18007b7e5  test    r14b, 4
0x18007b7e9  jz      loc_18007B86F
0x18007b7ef  mov     rcx, [rsi]; unsigned __int16 *
0x18007b7f2  lea     rdx, [rbp+rclsid]; struct _GUID *
0x18007b7f6  xorps   xmm0, xmm0
0x18007b7f9  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x18007b7fd  call    ?UAGetLoggerIDByContractID@@YAJPEBGPEAU_GUID@@@Z; UAGetLoggerIDByContractID(ushort const *,_GUID *)
0x18007b802  test    eax, eax
0x18007b804  js      short loc_18007B86F
0x18007b806  lea     rdx, [rbp+FileTime1]; lplpsz
0x18007b80a  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x18007b812  lea     rcx, [rbp+rclsid]; rclsid
0x18007b816  call    cs:__imp_StringFromCLSID
0x18007b81c  test    eax, eax
0x18007b81e  js      short loc_18007B866
0x18007b820  mov     r8, qword ptr [rbp+FileTime1.dwLowDateTime]
0x18007b824  lea     rax, [rbp+var_28]
0x18007b828  xor     r9d, r9d
0x18007b82b  mov     [rsp+60h+var_40], rax
0x18007b830  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18007b837  mov     qword ptr [rbp+var_28.dwLowDateTime], 0
0x18007b83f  mov     rcx, 0FFFFFFFF80000001h
0x18007b846  call    ?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z; _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)
0x18007b84b  test    eax, eax
0x18007b84d  js      short loc_18007B866
0x18007b84f  lea     rdx, [rdi+70h]; lpFileTime2
0x18007b853  lea     rcx, [rbp+var_28]; lpFileTime1
0x18007b857  call    cs:__imp_CompareFileTime
0x18007b85d  xor     ecx, ecx
0x18007b85f  test    eax, eax
0x18007b861  setnz   cl
0x18007b864  mov     [rbx], ecx
0x18007b866  lea     rcx, [rbp+FileTime1]
0x18007b86a  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18007b86f  xor     eax, eax
0x18007b871  mov     rcx, [rbp+var_10]
0x18007b875  xor     rcx, rsp; StackCookie
0x18007b878  call    __security_check_cookie
0x18007b87d  lea     r11, [rsp+60h+var_s0]
0x18007b882  mov     rbx, [r11+28h]
0x18007b886  mov     rsi, [r11+38h]
0x18007b88a  mov     rsp, r11
0x18007b88d  pop     r14
0x18007b88f  pop     rdi
0x18007b890  pop     rbp
0x18007b891  retn
```
