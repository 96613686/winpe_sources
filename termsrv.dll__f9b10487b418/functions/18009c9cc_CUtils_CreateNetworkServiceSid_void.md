# CUtils::CreateNetworkServiceSid(void * *)

- ea: `0x18009c9cc`
- end: `0x18009ca66`
- name: `?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z`
- size: `154`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18009d4cc`

## callees

- `0x18000a210`
- `0x18009c9cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ca2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ca2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c9e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c9e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ca48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ca48`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18009ca22`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18009ca22`

## string_xrefs

- `0x18009c9fa`: `CUtils::CreateNetworkServiceSid`
- `0x18009ca04`: `new pLocalNetworkServiceSid failed: 0x%x in %s`

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
0x18009c9cc  mov     [rsp+arg_8], rbx
0x18009c9d1  mov     qword ptr [rsp+cbSid], rcx
0x18009c9d6  push    rdi
0x18009c9d7  sub     rsp, 20h
0x18009c9db  mov     edx, 44h ; 'D'; uBytes
0x18009c9e0  mov     [rsp+28h+cbSid], edx
0x18009c9e4  lea     ecx, [rdx-4]; uFlags
0x18009c9e7  call    cs:__imp_LocalAlloc
0x18009c9ed  mov     rdi, rax
0x18009c9f0  test    rax, rax
0x18009c9f3  jnz     short loc_18009CA15
0x18009c9f5  mov     ebx, 8007000Eh
0x18009c9fa  lea     r9, aCutilsCreatene_0; "CUtils::CreateNetworkServiceSid"
0x18009ca01  mov     r8d, ebx
0x18009ca04  lea     rdx, aNewPlocalnetwo; "new pLocalNetworkServiceSid failed: 0x%"...
0x18009ca0b  lea     ecx, [rax+8]; int
0x18009ca0e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009ca13  jmp     short loc_18009CA59
0x18009ca15  xor     edx, edx; DomainSid
0x18009ca17  lea     r9, [rsp+28h+cbSid]; cbSid
0x18009ca1c  mov     r8, rdi; pSid
0x18009ca1f  lea     ecx, [rdx+18h]; WellKnownSidType
0x18009ca22  call    cs:__imp_CreateWellKnownSid
0x18009ca28  test    eax, eax
0x18009ca2a  jnz     short loc_18009CA50
0x18009ca2c  call    cs:__imp_GetLastError
0x18009ca32  mov     ebx, eax
0x18009ca34  test    eax, eax
0x18009ca36  jle     short loc_18009CA41
0x18009ca38  movzx   ebx, ax
0x18009ca3b  or      ebx, 80070000h
0x18009ca41  test    ebx, ebx
0x18009ca43  jns     short loc_18009CA59
0x18009ca45  mov     rcx, rdi; hMem
0x18009ca48  call    cs:__imp_LocalFree
0x18009ca4e  jmp     short loc_18009CA59
0x18009ca50  mov     cs:?pNetworkServiceSid@CUtils@@0PEAXEA, rdi; void * CUtils::pNetworkServiceSid
0x18009ca57  xor     ebx, ebx
0x18009ca59  mov     eax, ebx
0x18009ca5b  mov     rbx, [rsp+28h+arg_8]
0x18009ca60  add     rsp, 20h
0x18009ca64  pop     rdi
0x18009ca65  retn
```
