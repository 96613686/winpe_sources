# CImpersonationStream::SetSize(_ULARGE_INTEGER)

- ea: `0x1800712f0`
- end: `0x1800713e7`
- name: `?SetSize@CImpersonationStream@@UEAAJT_ULARGE_INTEGER@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(CImpersonationStream *__hidden this, union _ULARGE_INTEGER)`
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
- `0x1800712f0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180071305`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180071305`

## string_xrefs

- `0x18007133f`: `CImpersonationStream::SetSize`
- `0x18007136f`: `CImpersonationStream::SetSize`
- `0x180071397`: `CImpersonationStream::SetSize`
- `0x1800713c7`: `CImpersonationStream::SetSize`
- `0x180071330`: `CImpersonationStream::SetSize failed (0x%08X)`
- `0x180071358`: `CImpersonationStream::SetSize failed (0x%08X)`

## pseudocode

```c
__int64 __fastcall CImpersonationStream::SetSize(CImpersonationStream *this, union _ULARGE_INTEGER a2)
{
  HRESULT v4; // edi
  char *v5; // rbx
  void *v6; // rdx
  void **lpMem; // rax
  void *v8; // rdx
  __int64 v9; // rcx
  int v10; // esi
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx

  v4 = CoImpersonateClient();
  if ( !v4 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, union _ULARGE_INTEGER))(**((_QWORD **)this + 2) + 48LL))(
           *((_QWORD *)this + 2),
           a2);
    if ( v4 < 0 )
    {
      v5 = (char *)WiaTrace_TraceLog("CImpersonationStream::SetSize failed (0x%08X)");
      WriteDbgTraceErrorWI("CImpersonationStream::SetSize", v5);
      WiaTrcLib::Free((WiaTrcLib *)v5, v6);
      lpMem = (void **)WiaTrace_Trace("CImpersonationStream::SetSize failed (0x%08X)", v4);
      WiaTrace_ProcessTrace_Ex(v9, v8, (void *)"CImpersonationStream::SetSize", 1, lpMem);
    }
    v10 = SafeCoRevertToSelf();
    if ( v10 < 0 )
    {
      v11 = (char *)WiaTrace_TraceLog("SafeCoRevertToSelf failed (0x%X)");
      WriteDbgTraceErrorWI("CImpersonationStream::SetSize", v11);
      WiaTrcLib::Free((WiaTrcLib *)v11, v12);
      v13 = (void **)WiaTrace_Trace("SafeCoRevertToSelf failed (0x%X)", v10);
      WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"CImpersonationStream::SetSize", 1, v13);
      return (unsigned int)v10;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800712f0  mov     [rsp+arg_0], rbx
0x1800712f5  mov     [rsp+arg_8], rsi
0x1800712fa  push    rdi
0x1800712fb  sub     rsp, 30h
0x1800712ff  mov     rbx, rdx
0x180071302  mov     rsi, rcx
0x180071305  call    cs:__imp_CoImpersonateClient
0x18007130b  mov     edi, eax
0x18007130d  test    eax, eax
0x18007130f  jnz     loc_1800713D5
0x180071315  mov     rcx, [rsi+10h]
0x180071319  mov     rdx, rbx
0x18007131c  mov     rax, [rcx]
0x18007131f  mov     rax, [rax+30h]
0x180071323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071328  mov     edi, eax
0x18007132a  test    eax, eax
0x18007132c  jns     short loc_18007137B
0x18007132e  mov     edx, eax
0x180071330  lea     rcx, aCimpersonation_4; "CImpersonationStream::SetSize failed (0"...
0x180071337  call    WiaTrace_TraceLog
0x18007133c  mov     rdx, rax; char *
0x18007133f  lea     rcx, aCimpersonation; "CImpersonationStream::SetSize"
0x180071346  mov     rbx, rax
0x180071349  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18007134e  mov     rcx, rbx; this
0x180071351  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180071356  mov     edx, edi
0x180071358  lea     rcx, aCimpersonation_4; "CImpersonationStream::SetSize failed (0"...
0x18007135f  call    WiaTrace_Trace
0x180071364  mov     r9d, 1; int
0x18007136a  mov     [rsp+38h+lpMem], rax; lpMem
0x18007136f  lea     r8, aCimpersonation; "CImpersonationStream::SetSize"
0x180071376  call    WiaTrace_ProcessTrace_Ex
0x18007137b  call    ?SafeCoRevertToSelf@@YAJXZ; SafeCoRevertToSelf(void)
0x180071380  mov     esi, eax
0x180071382  test    eax, eax
0x180071384  jns     short loc_1800713D5
0x180071386  mov     edx, eax
0x180071388  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x18007138f  call    WiaTrace_TraceLog
0x180071394  mov     rdx, rax; char *
0x180071397  lea     rcx, aCimpersonation; "CImpersonationStream::SetSize"
0x18007139e  mov     rbx, rax
0x1800713a1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800713a6  mov     rcx, rbx; this
0x1800713a9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800713ae  mov     edx, esi
0x1800713b0  lea     rcx, aSafecorevertto_1; "SafeCoRevertToSelf failed (0x%X)"
0x1800713b7  call    WiaTrace_Trace
0x1800713bc  mov     r9d, 1; int
0x1800713c2  mov     [rsp+38h+lpMem], rax; lpMem
0x1800713c7  lea     r8, aCimpersonation; "CImpersonationStream::SetSize"
0x1800713ce  call    WiaTrace_ProcessTrace_Ex
0x1800713d3  mov     edi, esi
0x1800713d5  mov     rbx, [rsp+38h+arg_0]
0x1800713da  mov     eax, edi
0x1800713dc  mov     rsi, [rsp+38h+arg_8]
0x1800713e1  add     rsp, 30h
0x1800713e5  pop     rdi
0x1800713e6  retn
```
