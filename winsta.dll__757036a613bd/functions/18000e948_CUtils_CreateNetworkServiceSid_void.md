# CUtils::CreateNetworkServiceSid(void * *)

- ea: `0x18000e948`
- end: `0x18000e9e6`
- name: `?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z`
- size: `158`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e8b8`

## callees

- `0x180007890`
- `0x18000e948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e963`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e963`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e9a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e9a5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e97e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000e97e`

## string_xrefs

- `0x18000e9c9`: `CUtils::CreateNetworkServiceSid`
- `0x18000e9d3`: `new pLocalNetworkServiceSid failed: 0x%x in %s`

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
      CPublicBinding::pNetsrvSid = v2;
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
0x18000e948  mov     [rsp+arg_8], rbx
0x18000e94d  mov     qword ptr [rsp+cbSid], rcx
0x18000e952  push    rdi
0x18000e953  sub     rsp, 20h
0x18000e957  mov     edx, 44h ; 'D'; uBytes
0x18000e95c  mov     [rsp+28h+cbSid], edx
0x18000e960  lea     ecx, [rdx-4]; uFlags
0x18000e963  call    cs:__imp_LocalAlloc
0x18000e969  mov     rdi, rax
0x18000e96c  test    rax, rax
0x18000e96f  jz      short loc_18000E9C4
0x18000e971  xor     edx, edx; DomainSid
0x18000e973  lea     r9, [rsp+28h+cbSid]; cbSid
0x18000e978  mov     r8, rax; pSid
0x18000e97b  lea     ecx, [rdx+18h]; WellKnownSidType
0x18000e97e  call    cs:__imp_CreateWellKnownSid
0x18000e984  test    eax, eax
0x18000e986  jz      short loc_18000E9AD
0x18000e988  mov     cs:?pNetsrvSid@CPublicBinding@@1PEAXEA, rdi; void * CPublicBinding::pNetsrvSid
0x18000e98f  xor     ebx, ebx
0x18000e991  mov     eax, ebx
0x18000e993  mov     rbx, [rsp+28h+arg_8]
0x18000e998  add     rsp, 20h
0x18000e99c  pop     rdi
0x18000e99d  retn
0x18000e99e  test    ebx, ebx
0x18000e9a0  jns     short loc_18000E991
0x18000e9a2  mov     rcx, rdi; hMem
0x18000e9a5  call    cs:__imp_LocalFree
0x18000e9ab  jmp     short loc_18000E991
0x18000e9ad  call    cs:__imp_GetLastError
0x18000e9b3  mov     ebx, eax
0x18000e9b5  test    eax, eax
0x18000e9b7  jle     short loc_18000E99E
0x18000e9b9  movzx   ebx, ax
0x18000e9bc  or      ebx, 80070000h
0x18000e9c2  jmp     short loc_18000E99E
0x18000e9c4  mov     ebx, 8007000Eh
0x18000e9c9  lea     r9, aCutilsCreatene_0; "CUtils::CreateNetworkServiceSid"
0x18000e9d0  mov     r8d, ebx
0x18000e9d3  lea     rdx, aNewPlocalnetwo; "new pLocalNetworkServiceSid failed: 0x%"...
0x18000e9da  mov     ecx, 8; int
0x18000e9df  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000e9e4  jmp     short loc_18000E991
```
