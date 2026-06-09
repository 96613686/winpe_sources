# GetTaskGuidFromRegistryForAppForUser(ushort const *,ushort const *,_GUID *)

- ea: `0x18002c5c0`
- end: `0x18002c7b4`
- name: `?GetTaskGuidFromRegistryForAppForUser@@YAJPEBG0PEAU_GUID@@@Z`
- size: `500`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000dfd8`
- `0x18002d868`

## callees

- `0x180002590`
- `0x180003088`
- `0x1800094bc`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18002c5c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c66e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c66e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c681`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002c681`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c679`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c75c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c679`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c75c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c6bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c6bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c714`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002c714`

## string_xrefs

- `0x18002c646`: `%s\Software\Microsoft\IcsSvc\Tasks`
- `0x18002c69e`: `Software\Microsoft\IcsSvc\Tasks`

## pseudocode

```c
__int64 __fastcall GetTaskGuidFromRegistryForAppForUser(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct _GUID *a3)
{
  int v6; // eax
  unsigned __int16 *v7; // rdx
  __int64 v8; // rcx
  bool v9; // sf
  LSTATUS ValueW; // eax
  unsigned int v11; // ebx
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID pvData; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v16[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids);
  }
  hKey = 0;
  if ( a1 )
  {
    memset_0(v16, 0, 0x208u);
    v6 = StringCchPrintfW(v16, 0x104u, L"%s\\Software\\Microsoft\\IcsSvc\\Tasks", a1);
    if ( v6 < 0 )
      goto LABEL_17;
    hKey = 0;
    v7 = v16;
    v8 = -2147483645;
  }
  else
  {
    v7 = L"Software\\Microsoft\\IcsSvc\\Tasks";
    v8 = -2147483647;
  }
  v6 = RegOpenKeyExW((HKEY)v8, v7, 0, 1u, &hKey);
  v9 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    v9 = v6 < 0;
  }
  if ( !v9 )
  {
    pvData = 0;
    pcbData = 16;
    ValueW = RegGetValueW(hKey, 0, a2, 8u, 0, &pvData, &pcbData);
    v11 = ValueW;
    if ( ValueW > 0 )
      v11 = (unsigned __int16)ValueW | 0x80070000;
    if ( (v11 & 0x80000000) != 0 )
    {
      if ( v11 == -2147024894 )
        v11 = -2095972329;
    }
    else
    {
      *a3 = pvData;
    }
    goto LABEL_20;
  }
LABEL_17:
  if ( v6 == -2147024894 )
    v6 = -2095972329;
  v11 = v6;
LABEL_20:
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x18002c5c0  mov     [rsp-8+arg_18], rbx
0x18002c5c5  push    rbp
0x18002c5c6  push    rsi
0x18002c5c7  push    rdi
0x18002c5c8  push    r12
0x18002c5ca  push    r14
0x18002c5cc  lea     rbp, [rsp-180h]
0x18002c5d4  sub     rsp, 280h
0x18002c5db  mov     rax, cs:__security_cookie
0x18002c5e2  xor     rax, rsp
0x18002c5e5  mov     [rbp+1A0h+var_30], rax
0x18002c5ec  mov     rsi, r8
0x18002c5ef  mov     r14, rdx
0x18002c5f2  mov     rbx, rcx
0x18002c5f5  lea     r12, WPP_GLOBAL_Control
0x18002c5fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c603  cmp     rcx, r12
0x18002c606  jz      short loc_18002C623
0x18002c608  test    byte ptr [rcx+1Ch], 8
0x18002c60c  jz      short loc_18002C623
0x18002c60e  mov     edx, 40h ; '@'
0x18002c613  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002c61a  mov     rcx, [rcx+10h]
0x18002c61e  call    WPP_SF_
0x18002c623  mov     [rsp+2A0h+hKey], 0
0x18002c62c  test    rbx, rbx
0x18002c62f  jz      short loc_18002C69E
0x18002c631  xor     edx, edx; Val
0x18002c633  mov     r8d, 208h; Size
0x18002c639  lea     rcx, [rsp+2A0h+var_240]; void *
0x18002c63e  call    memset_0
0x18002c643  mov     r9, rbx
0x18002c646  lea     r8, aSSoftwareMicro; "%s\\Software\\Microsoft\\IcsSvc\\Tasks"
0x18002c64d  mov     edx, 104h; unsigned __int64
0x18002c652  lea     rcx, [rsp+2A0h+var_240]; unsigned __int16 *
0x18002c657  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c65c  test    eax, eax
0x18002c65e  js      loc_18002C743
0x18002c664  mov     rdi, [rsp+2A0h+hKey]
0x18002c669  test    rdi, rdi
0x18002c66c  jz      short loc_18002C687
0x18002c66e  call    cs:__imp_GetLastError
0x18002c674  mov     ebx, eax
0x18002c676  mov     rcx, rdi; hKey
0x18002c679  call    cs:__imp_RegCloseKey
0x18002c67f  mov     ecx, ebx; dwErrCode
0x18002c681  call    cs:__imp_SetLastError
0x18002c687  mov     [rsp+2A0h+hKey], 0
0x18002c690  lea     rdx, [rsp+2A0h+var_240]
0x18002c695  mov     rcx, 0FFFFFFFF80000003h
0x18002c69c  jmp     short loc_18002C6AC
0x18002c69e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\IcsSvc\\Tasks"
0x18002c6a5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002c6ac  lea     rax, [rsp+2A0h+hKey]
0x18002c6b1  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18002c6b6  mov     r9d, 1; samDesired
0x18002c6bc  xor     r8d, r8d; ulOptions
0x18002c6bf  call    cs:__imp_RegOpenKeyExW
0x18002c6c5  test    eax, eax
0x18002c6c7  mov     edi, 80070000h
0x18002c6cc  jle     short loc_18002C6D5
0x18002c6ce  movzx   eax, ax
0x18002c6d1  or      eax, edi
0x18002c6d3  test    eax, eax
0x18002c6d5  js      short loc_18002C743
0x18002c6d7  xorps   xmm0, xmm0
0x18002c6da  movups  [rsp+2A0h+var_250], xmm0
0x18002c6df  mov     [rsp+2A0h+var_258], 10h
0x18002c6e7  lea     rax, [rsp+2A0h+var_258]
0x18002c6ec  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18002c6f1  lea     rax, [rsp+2A0h+var_250]
0x18002c6f6  mov     [rsp+2A0h+pvData], rax; pvData
0x18002c6fb  mov     [rsp+2A0h+phkResult], 0; pdwType
0x18002c704  mov     r9d, 8; dwFlags
0x18002c70a  mov     r8, r14; lpValue
0x18002c70d  xor     edx, edx; lpSubKey
0x18002c70f  mov     rcx, [rsp+2A0h+hKey]; hkey
0x18002c714  call    cs:__imp_RegGetValueW
0x18002c71a  mov     ebx, eax
0x18002c71c  test    eax, eax
0x18002c71e  jle     short loc_18002C725
0x18002c720  movzx   ebx, ax
0x18002c723  or      ebx, edi
0x18002c725  test    ebx, ebx
0x18002c727  js      short loc_18002C734
0x18002c729  movups  xmm0, [rsp+2A0h+var_250]
0x18002c72e  movdqu  xmmword ptr [rsi], xmm0
0x18002c732  jmp     short loc_18002C752
0x18002c734  cmp     ebx, 80070002h
0x18002c73a  jnz     short loc_18002C752
0x18002c73c  mov     ebx, 83120017h
0x18002c741  jmp     short loc_18002C752
0x18002c743  mov     ebx, 83120017h
0x18002c748  cmp     eax, 80070002h
0x18002c74d  cmovz   eax, ebx
0x18002c750  mov     ebx, eax
0x18002c752  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18002c757  test    rcx, rcx
0x18002c75a  jz      short loc_18002C762
0x18002c75c  call    cs:__imp_RegCloseKey
0x18002c762  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c769  cmp     rcx, r12
0x18002c76c  jz      short loc_18002C78C
0x18002c76e  test    byte ptr [rcx+1Ch], 8
0x18002c772  jz      short loc_18002C78C
0x18002c774  mov     edx, 41h ; 'A'
0x18002c779  mov     r9d, ebx
0x18002c77c  lea     r8, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002c783  mov     rcx, [rcx+10h]
0x18002c787  call    WPP_SF_d
0x18002c78c  mov     eax, ebx
0x18002c78e  mov     rcx, [rbp+1A0h+var_30]
0x18002c795  xor     rcx, rsp; StackCookie
0x18002c798  call    __security_check_cookie
0x18002c79d  mov     rbx, [rsp+2A0h+arg_18]
0x18002c7a5  add     rsp, 280h
0x18002c7ac  pop     r14
0x18002c7ae  pop     r12
0x18002c7b0  pop     rdi
0x18002c7b1  pop     rsi
0x18002c7b2  pop     rbp
0x18002c7b3  retn
```
