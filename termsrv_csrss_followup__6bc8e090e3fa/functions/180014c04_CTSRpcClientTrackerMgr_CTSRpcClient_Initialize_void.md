# CTSRpcClientTrackerMgr::CTSRpcClient::Initialize(void *)

- ea: `0x180014c04`
- end: `0x180014cea`
- name: `?Initialize@CTSRpcClient@CTSRpcClientTrackerMgr@@QEAAJPEAX@Z`
- size: `230`
- prototype: `int(CTSRpcClientTrackerMgr::CTSRpcClient *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800500a0`

## callees

- `0x180009940`
- `0x180014c04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c9d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014c59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014c59`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014c1c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014c1c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180014c8d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180014c8d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014c40`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014c40`

## string_xrefs

- `0x180014c31`: `IsValidSid(pSid) failed: 0x%x in %s`
- `0x180014cbc`: `CopySid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSRpcClientTrackerMgr::CTSRpcClient::Initialize(
        CTSRpcClientTrackerMgr::CTSRpcClient *this,
        void *a2)
{
  unsigned int v4; // ebx
  DWORD LengthSid; // eax
  HLOCAL v6; // rax
  signed int LastError; // eax

  if ( IsValidSid(a2) )
  {
    LengthSid = GetLengthSid(a2);
    *((_DWORD *)this + 400) = LengthSid;
    v6 = LocalAlloc(0x40u, LengthSid);
    *((_QWORD *)this + 199) = v6;
    if ( v6 )
    {
      v4 = 0;
      if ( !CopySid(*((_DWORD *)this + 400), v6, a2) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( (v4 & 0x80000000) != 0 )
          _DbgPrintMessage(8, "CopySid failed: 0x%x in %s", v4, "CTSRpcClientTrackerMgr::CTSRpcClient::Initialize");
      }
    }
    else
    {
      v4 = -2147024882;
      _DbgPrintMessage(
        8,
        "LocalAlloc failed: 0x%x in %s",
        2147942414LL,
        "CTSRpcClientTrackerMgr::CTSRpcClient::Initialize");
    }
  }
  else
  {
    v4 = -2147024809;
    _DbgPrintMessage(
      8,
      "IsValidSid(pSid) failed: 0x%x in %s",
      2147942487LL,
      "CTSRpcClientTrackerMgr::CTSRpcClient::Initialize");
  }
  return v4;
}

```

## disassembly

```asm
0x180014c04  mov     [rsp+arg_0], rbx
0x180014c09  mov     [rsp+arg_8], rsi
0x180014c0e  push    rdi
0x180014c0f  sub     rsp, 20h
0x180014c13  mov     rsi, rcx
0x180014c16  mov     rdi, rdx
0x180014c19  mov     rcx, rdx; pSid
0x180014c1c  call    cs:__imp_IsValidSid
0x180014c23  nop     dword ptr [rax+rax+00h]
0x180014c28  test    eax, eax
0x180014c2a  jnz     short loc_180014C3D
0x180014c2c  mov     ebx, 80070057h
0x180014c31  lea     rdx, aIsvalidsidPsid; "IsValidSid(pSid) failed: 0x%x in %s"
0x180014c38  jmp     loc_180014CC3
0x180014c3d  mov     rcx, rdi; pSid
0x180014c40  call    cs:__imp_GetLengthSid
0x180014c47  nop     dword ptr [rax+rax+00h]
0x180014c4c  mov     edx, eax; uBytes
0x180014c4e  mov     ecx, 40h ; '@'; uFlags
0x180014c53  mov     [rsi+640h], edx
0x180014c59  call    cs:__imp_LocalAlloc
0x180014c60  nop     dword ptr [rax+rax+00h]
0x180014c65  mov     [rsi+638h], rax
0x180014c6c  test    rax, rax
0x180014c6f  jnz     short loc_180014C7F
0x180014c71  mov     ebx, 8007000Eh
0x180014c76  lea     rdx, aLocalallocFail_1; "LocalAlloc failed: 0x%x in %s"
0x180014c7d  jmp     short loc_180014CC3
0x180014c7f  mov     ecx, [rsi+640h]; nDestinationSidLength
0x180014c85  mov     r8, rdi; pSourceSid
0x180014c88  mov     rdx, rax; pDestinationSid
0x180014c8b  xor     ebx, ebx
0x180014c8d  call    cs:__imp_CopySid
0x180014c94  nop     dword ptr [rax+rax+00h]
0x180014c99  test    eax, eax
0x180014c9b  jnz     short loc_180014CD7
0x180014c9d  call    cs:__imp_GetLastError
0x180014ca4  nop     dword ptr [rax+rax+00h]
0x180014ca9  mov     ebx, eax
0x180014cab  test    eax, eax
0x180014cad  jle     short loc_180014CB8
0x180014caf  movzx   ebx, ax
0x180014cb2  or      ebx, 80070000h
0x180014cb8  test    ebx, ebx
0x180014cba  jns     short loc_180014CD7
0x180014cbc  lea     rdx, aCopysidFailed0; "CopySid failed: 0x%x in %s"
0x180014cc3  lea     r9, aCtsrpcclienttr; "CTSRpcClientTrackerMgr::CTSRpcClient::I"...
0x180014cca  mov     r8d, ebx
0x180014ccd  mov     ecx, 8; int
0x180014cd2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180014cd7  mov     rsi, [rsp+28h+arg_8]
0x180014cdc  mov     eax, ebx
0x180014cde  mov     rbx, [rsp+28h+arg_0]
0x180014ce3  add     rsp, 20h
0x180014ce7  pop     rdi
0x180014ce8  retn
```
