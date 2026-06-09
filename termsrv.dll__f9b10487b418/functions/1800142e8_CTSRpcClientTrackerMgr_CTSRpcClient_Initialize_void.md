# CTSRpcClientTrackerMgr::CTSRpcClient::Initialize(void *)

- ea: `0x1800142e8`
- end: `0x1800143ac`
- name: `?Initialize@CTSRpcClient@CTSRpcClientTrackerMgr@@QEAAJPEAX@Z`
- size: `196`
- prototype: `int(CTSRpcClientTrackerMgr::CTSRpcClient *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004da60`

## callees

- `0x18000a210`
- `0x1800142e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014366`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001432e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001432e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014300`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180014300`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001435c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001435c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001431b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001431b`

## string_xrefs

- `0x18001430f`: `IsValidSid(pSid) failed: 0x%x in %s`
- `0x18001437f`: `CopySid failed: 0x%x in %s`

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
0x1800142e8  mov     [rsp+arg_0], rbx
0x1800142ed  mov     [rsp+arg_8], rsi
0x1800142f2  push    rdi
0x1800142f3  sub     rsp, 20h
0x1800142f7  mov     rsi, rcx
0x1800142fa  mov     rdi, rdx
0x1800142fd  mov     rcx, rdx; pSid
0x180014300  call    cs:__imp_IsValidSid
0x180014306  test    eax, eax
0x180014308  jnz     short loc_180014318
0x18001430a  mov     ebx, 80070057h
0x18001430f  lea     rdx, aIsvalidsidPsid; "IsValidSid(pSid) failed: 0x%x in %s"
0x180014316  jmp     short loc_180014386
0x180014318  mov     rcx, rdi; pSid
0x18001431b  call    cs:__imp_GetLengthSid
0x180014321  mov     edx, eax; uBytes
0x180014323  mov     ecx, 40h ; '@'; uFlags
0x180014328  mov     [rsi+640h], edx
0x18001432e  call    cs:__imp_LocalAlloc
0x180014334  mov     [rsi+638h], rax
0x18001433b  test    rax, rax
0x18001433e  jnz     short loc_18001434E
0x180014340  mov     ebx, 8007000Eh
0x180014345  lea     rdx, aLocalallocFail_1; "LocalAlloc failed: 0x%x in %s"
0x18001434c  jmp     short loc_180014386
0x18001434e  mov     ecx, [rsi+640h]; nDestinationSidLength
0x180014354  mov     r8, rdi; pSourceSid
0x180014357  mov     rdx, rax; pDestinationSid
0x18001435a  xor     ebx, ebx
0x18001435c  call    cs:__imp_CopySid
0x180014362  test    eax, eax
0x180014364  jnz     short loc_18001439A
0x180014366  call    cs:__imp_GetLastError
0x18001436c  mov     ebx, eax
0x18001436e  test    eax, eax
0x180014370  jle     short loc_18001437B
0x180014372  movzx   ebx, ax
0x180014375  or      ebx, 80070000h
0x18001437b  test    ebx, ebx
0x18001437d  jns     short loc_18001439A
0x18001437f  lea     rdx, aCopysidFailed0; "CopySid failed: 0x%x in %s"
0x180014386  lea     r9, aCtsrpcclienttr; "CTSRpcClientTrackerMgr::CTSRpcClient::I"...
0x18001438d  mov     r8d, ebx
0x180014390  mov     ecx, 8; int
0x180014395  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001439a  mov     rsi, [rsp+28h+arg_8]
0x18001439f  mov     eax, ebx
0x1800143a1  mov     rbx, [rsp+28h+arg_0]
0x1800143a6  add     rsp, 20h
0x1800143aa  pop     rdi
0x1800143ab  retn
```
