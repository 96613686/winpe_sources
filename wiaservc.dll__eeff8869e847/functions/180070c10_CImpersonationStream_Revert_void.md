# CImpersonationStream::Revert(void)

- ea: `0x180070c10`
- end: `0x180070d01`
- name: `?Revert@CImpersonationStream@@UEAAJXZ`
- size: `241`
- prototype: `__int64 __fastcall(CImpersonationStream *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x1800202b8`
- `0x18002de18`
- `0x18002def8`
- `0x180070c10`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180070c22`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180070c22`

## string_xrefs

- `0x180070c59`: `CImpersonationStream::Revert`
- `0x180070c89`: `CImpersonationStream::Revert`
- `0x180070cb1`: `CImpersonationStream::Revert`
- `0x180070ce1`: `CImpersonationStream::Revert`
- `0x180070c4a`: `CImpersonationStream::Revert failed (0x%08X)`
- `0x180070c72`: `CImpersonationStream::Revert failed (0x%08X)`

## pseudocode

```c
__int64 __fastcall CImpersonationStream::Revert(CImpersonationStream *this)
{
  HRESULT v2; // edi
  char *v3; // rbx
  void *v4; // rdx
  void **lpMem; // rax
  void *v6; // rdx
  __int64 v7; // rcx
  int v8; // esi
  char *v9; // rbx
  void *v10; // rdx
  void **v11; // rax
  void *v12; // rdx
  __int64 v13; // rcx

  v2 = CoImpersonateClient();
  if ( !v2 )
  {
    v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 72LL))(*((_QWORD *)this + 2));
    if ( v2 < 0 )
    {
      v3 = (char *)WiaTrace_TraceLog("CImpersonationStream::Revert failed (0x%08X)");
      WriteDbgTraceErrorWI("CImpersonationStream::Revert", v3);
      WiaTrcLib::Free((WiaTrcLib *)v3, v4);
      lpMem = (void **)WiaTrace_Trace("CImpersonationStream::Revert failed (0x%08X)", v2);
      WiaTrace_ProcessTrace_Ex(v7, v6, (void *)"CImpersonationStream::Revert", 1, lpMem);
    }
    v8 = SafeCoRevertToSelf();
    if ( v8 < 0 )
    {
      v9 = (char *)WiaTrace_TraceLog("SafeCoRevertToSelf failed (0x%X)");
      WriteDbgTraceErrorWI("CImpersonationStream::Revert", v9);
      WiaTrcLib::Free((WiaTrcLib *)v9, v10);
      v11 = (void **)WiaTrace_Trace("SafeCoRevertToSelf failed (0x%X)", v8);
      WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"CImpersonationStream::Revert", 1, v11);
      return (unsigned int)v8;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180070c10  mov     [rsp+arg_0], rbx
0x180070c15  mov     [rsp+arg_8], rsi
0x180070c1a  push    rdi
0x180070c1b  sub     rsp, 30h
0x180070c1f  mov     rbx, rcx
0x180070c22  call    cs:__imp_CoImpersonateClient
0x180070c28  mov     edi, eax
0x180070c2a  test    eax, eax
0x180070c2c  jnz     loc_180070CEF
0x180070c32  mov     rcx, [rbx+10h]
0x180070c36  mov     rax, [rcx]
0x180070c39  mov     rax, [rax+48h]
0x180070c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070c42  mov     edi, eax
0x180070c44  test    eax, eax
0x180070c46  jns     short loc_180070C95
0x180070c48  mov     edx, eax
0x180070c4a  lea     rcx, aCimpersonation_20; "CImpersonationStream::Revert failed (0x"...
0x180070c51  call    WiaTrace_TraceLog
0x180070c56  mov     rdx, rax; char *
0x180070c59  lea     rcx, aCimpersonation_18; "CImpersonationStream::Revert"
0x180070c60  mov     rbx, rax
0x180070c63  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180070c68  mov     rcx, rbx; this
0x180070c6b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180070c70  mov     edx, edi
0x180070c72  lea     rcx, aCimpersonation_20; "CImpersonationStream::Revert failed (0x"...
0x180070c79  call    WiaTrace_Trace
0x180070c7e  mov     r9d, 1; int
0x180070c84  mov     [rsp+38h+lpMem], rax; lpMem
0x180070c89  lea     r8, aCimpersonation_18; "CImpersonationStream::Revert"
0x180070c90  call    WiaTrace_ProcessTrace_Ex
0x180070c95  call    ?SafeCoRevertToSelf@@YAJXZ; SafeCoRevertToSelf(void)
0x180070c9a  mov     esi, eax
0x180070c9c  test    eax, eax
0x180070c9e  jns     short loc_180070CEF
0x180070ca0  mov     edx, eax
0x180070ca2  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x180070ca9  call    WiaTrace_TraceLog
0x180070cae  mov     rdx, rax; char *
0x180070cb1  lea     rcx, aCimpersonation_18; "CImpersonationStream::Revert"
0x180070cb8  mov     rbx, rax
0x180070cbb  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180070cc0  mov     rcx, rbx; this
0x180070cc3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180070cc8  mov     edx, esi
0x180070cca  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x180070cd1  call    WiaTrace_Trace
0x180070cd6  mov     r9d, 1; int
0x180070cdc  mov     [rsp+38h+lpMem], rax; lpMem
0x180070ce1  lea     r8, aCimpersonation_18; "CImpersonationStream::Revert"
0x180070ce8  call    WiaTrace_ProcessTrace_Ex
0x180070ced  mov     edi, esi
0x180070cef  mov     rbx, [rsp+38h+arg_0]
0x180070cf4  mov     eax, edi
0x180070cf6  mov     rsi, [rsp+38h+arg_8]
0x180070cfb  add     rsp, 30h
0x180070cff  pop     rdi
0x180070d00  retn
```
