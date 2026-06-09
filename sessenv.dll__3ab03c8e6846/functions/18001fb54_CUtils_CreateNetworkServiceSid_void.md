# CUtils::CreateNetworkServiceSid(void * *)

- ea: `0x18001fb54`
- end: `0x18001fbee`
- name: `?CreateNetworkServiceSid@CUtils@@SAJPEAPEAX@Z`
- size: `154`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180020acc`

## callees

- `0x180003f30`
- `0x18001fb54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbb4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001fbaa`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001fbaa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fb6f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fb6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fbd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fbd0`

## string_xrefs

- `0x18001fb82`: `CUtils::CreateNetworkServiceSid`
- `0x18001fb8c`: `new pLocalNetworkServiceSid failed: 0x%x in %s`

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
0x18001fb54  mov     [rsp+arg_8], rbx
0x18001fb59  mov     qword ptr [rsp+cbSid], rcx
0x18001fb5e  push    rdi
0x18001fb5f  sub     rsp, 20h
0x18001fb63  mov     edx, 44h ; 'D'; uBytes
0x18001fb68  mov     [rsp+28h+cbSid], edx
0x18001fb6c  lea     ecx, [rdx-4]; uFlags
0x18001fb6f  call    cs:__imp_LocalAlloc
0x18001fb75  mov     rdi, rax
0x18001fb78  test    rax, rax
0x18001fb7b  jnz     short loc_18001FB9D
0x18001fb7d  mov     ebx, 8007000Eh
0x18001fb82  lea     r9, aCutilsCreatene_0; "CUtils::CreateNetworkServiceSid"
0x18001fb89  mov     r8d, ebx
0x18001fb8c  lea     rdx, aNewPlocalnetwo; "new pLocalNetworkServiceSid failed: 0x%"...
0x18001fb93  lea     ecx, [rax+8]; int
0x18001fb96  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001fb9b  jmp     short loc_18001FBE1
0x18001fb9d  xor     edx, edx; DomainSid
0x18001fb9f  lea     r9, [rsp+28h+cbSid]; cbSid
0x18001fba4  mov     r8, rdi; pSid
0x18001fba7  lea     ecx, [rdx+18h]; WellKnownSidType
0x18001fbaa  call    cs:__imp_CreateWellKnownSid
0x18001fbb0  test    eax, eax
0x18001fbb2  jnz     short loc_18001FBD8
0x18001fbb4  call    cs:__imp_GetLastError
0x18001fbba  mov     ebx, eax
0x18001fbbc  test    eax, eax
0x18001fbbe  jle     short loc_18001FBC9
0x18001fbc0  movzx   ebx, ax
0x18001fbc3  or      ebx, 80070000h
0x18001fbc9  test    ebx, ebx
0x18001fbcb  jns     short loc_18001FBE1
0x18001fbcd  mov     rcx, rdi; hMem
0x18001fbd0  call    cs:__imp_LocalFree
0x18001fbd6  jmp     short loc_18001FBE1
0x18001fbd8  mov     cs:?pNetworkServiceSid@CUtils@@0PEAXEA, rdi; void * CUtils::pNetworkServiceSid
0x18001fbdf  xor     ebx, ebx
0x18001fbe1  mov     eax, ebx
0x18001fbe3  mov     rbx, [rsp+28h+arg_8]
0x18001fbe8  add     rsp, 20h
0x18001fbec  pop     rdi
0x18001fbed  retn
```
