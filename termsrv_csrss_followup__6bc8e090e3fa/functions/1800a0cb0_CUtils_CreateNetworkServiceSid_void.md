# CUtils::CreateNetworkServiceSid(void * *)

- ea: `0x1800a0cb0`
- end: `0x1800a0d63`
- name: `?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800a235c`

## callees

- `0x180009940`
- `0x1800a0cb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0d1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0ccb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a0ccb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0d3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0d3e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800a0d0c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800a0d0c`

## string_xrefs

- `0x1800a0cee`: `new pLocalNetworkServiceSid failed: 0x%x in %s`
- `0x1800a0ce4`: `CUtils::CreateNetworkServiceSid`

## pseudocode

```c
__int64 __fastcall CUtils::CreateNetworkServiceSid(void **a1)
{
  HLOCAL v1; // rax
  void *v2; // rdi
  signed int v3; // ebx
  signed int LastError; // eax
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF
  int v7; // [rsp+34h] [rbp+Ch]

  v7 = HIDWORD(a1);
  cbSid = 68;
  v1 = LocalAlloc(0x40u, 0x44u);
  v2 = v1;
  if ( v1 )
  {
    if ( CreateWellKnownSid(WinNetworkServiceSid, 0, v1, &cbSid) )
    {
      CUtils::pNetworkServiceSid = v2;
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 < 0 )
        LocalFree(v2);
    }
  }
  else
  {
    v3 = -2147024882;
    _DbgPrintMessage(
      8,
      "new pLocalNetworkServiceSid failed: 0x%x in %s",
      -2147024882,
      "CUtils::CreateNetworkServiceSid");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800a0cb0  mov     [rsp+arg_8], rbx
0x1800a0cb5  mov     qword ptr [rsp+cbSid], rcx
0x1800a0cba  push    rdi
0x1800a0cbb  sub     rsp, 20h
0x1800a0cbf  mov     edx, 44h ; 'D'; uBytes
0x1800a0cc4  mov     [rsp+28h+cbSid], edx
0x1800a0cc8  lea     ecx, [rdx-4]; uFlags
0x1800a0ccb  call    cs:__imp_LocalAlloc
0x1800a0cd2  nop     dword ptr [rax+rax+00h]
0x1800a0cd7  mov     rdi, rax
0x1800a0cda  test    rax, rax
0x1800a0cdd  jnz     short loc_1800A0CFF
0x1800a0cdf  mov     ebx, 8007000Eh
0x1800a0ce4  lea     r9, aCutilsCreatene_0; "CUtils::CreateNetworkServiceSid"
0x1800a0ceb  mov     r8d, ebx
0x1800a0cee  lea     rdx, aNewPlocalnetwo; "new pLocalNetworkServiceSid failed: 0x%"...
0x1800a0cf5  lea     ecx, [rax+8]; int
0x1800a0cf8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800a0cfd  jmp     short loc_1800A0D55
0x1800a0cff  xor     edx, edx; DomainSid
0x1800a0d01  lea     r9, [rsp+28h+cbSid]; cbSid
0x1800a0d06  mov     r8, rdi; pSid
0x1800a0d09  lea     ecx, [rdx+18h]; WellKnownSidType
0x1800a0d0c  call    cs:__imp_CreateWellKnownSid
0x1800a0d13  nop     dword ptr [rax+rax+00h]
0x1800a0d18  test    eax, eax
0x1800a0d1a  jnz     short loc_1800A0D4C
0x1800a0d1c  call    cs:__imp_GetLastError
0x1800a0d23  nop     dword ptr [rax+rax+00h]
0x1800a0d28  mov     ebx, eax
0x1800a0d2a  test    eax, eax
0x1800a0d2c  jle     short loc_1800A0D37
0x1800a0d2e  movzx   ebx, ax
0x1800a0d31  or      ebx, 80070000h
0x1800a0d37  test    ebx, ebx
0x1800a0d39  jns     short loc_1800A0D55
0x1800a0d3b  mov     rcx, rdi; hMem
0x1800a0d3e  call    cs:__imp_LocalFree
0x1800a0d45  nop     dword ptr [rax+rax+00h]
0x1800a0d4a  jmp     short loc_1800A0D55
0x1800a0d4c  mov     cs:?pNetworkServiceSid@CUtils@@0PEAXEA, rdi; void * CUtils::pNetworkServiceSid
0x1800a0d53  xor     ebx, ebx
0x1800a0d55  mov     eax, ebx
0x1800a0d57  mov     rbx, [rsp+28h+arg_8]
0x1800a0d5c  add     rsp, 20h
0x1800a0d60  pop     rdi
0x1800a0d61  retn
```
