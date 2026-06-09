# WinStationGetUserProfile

- ea: `0x1800215e0`
- end: `0x1800216f0`
- name: `WinStationGetUserProfile`
- size: `272`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800041a0`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x1800215e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021639`
- `RPCRT4!NdrClientCall3` at `0x180021695`
- `RPCRT4!NdrClientCall3` at `0x180021695`

## string_xrefs

- `0x18002162a`: `Failed to open binding`

## pseudocode

```c
__int64 __fastcall WinStationGetUserProfile(__int64 a1, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  signed int LastError; // eax
  unsigned int Pointer; // ebx
  void *v10; // rax
  unsigned __int16 v12[32]; // [rsp+48h] [rbp-40h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v12, 0, 1);
  if ( CSmartPublicBinding::operator void *(v12) )
  {
    v10 = CSmartPublicBinding::operator void *(v12);
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800351A0, 2u, 0, v10, a1, a2, a3, a4).Pointer;
  }
  else
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError > 0 )
      Pointer = (unsigned __int16)LastError | 0x80070000;
  }
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v12);
  return Pointer;
}

```

## disassembly

```asm
0x1800215e0  push    rbx
0x1800215e2  push    rsi
0x1800215e3  push    rdi
0x1800215e4  push    r14
0x1800215e6  sub     rsp, 68h
0x1800215ea  mov     rbx, r9
0x1800215ed  mov     rdi, r8
0x1800215f0  mov     rsi, rdx
0x1800215f3  mov     r14, rcx
0x1800215f6  mov     qword ptr [rdx], 0
0x1800215fd  mov     qword ptr [r8], 0
0x180021604  mov     qword ptr [r9], 0
0x18002160b  xor     edx, edx; void *
0x18002160d  lea     r8d, [rdx+1]; int
0x180021611  lea     rcx, [rsp+88h+var_40]; this
0x180021616  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x18002161b  lea     rcx, [rsp+88h+var_40]; unsigned __int16 *
0x180021620  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021625  test    rax, rax
0x180021628  jnz     short loc_18002165A
0x18002162a  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180021631  lea     ecx, [rax+8]; int
0x180021634  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021639  call    cs:__imp_GetLastError
0x180021640  nop     dword ptr [rax+rax+00h]
0x180021645  mov     ebx, eax
0x180021647  test    eax, eax
0x180021649  jle     loc_1800216D9
0x18002164f  movzx   ebx, ax
0x180021652  or      ebx, 80070000h
0x180021658  jmp     short loc_1800216D9
0x18002165a  lea     rcx, [rsp+88h+var_40]; unsigned __int16 *
0x18002165f  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021664  mov     [rsp+88h+arg_0], 0
0x180021670  mov     [rsp+88h+var_50], rbx
0x180021675  mov     [rsp+88h+var_58], rdi
0x18002167a  mov     [rsp+88h+var_60], rsi
0x18002167f  mov     [rsp+88h+var_68], r14
0x180021684  mov     r9, rax
0x180021687  xor     r8d, r8d; pReturnValue
0x18002168a  lea     edx, [r8+2]; nProcNum
0x18002168e  lea     rcx, stru_1800351A0; pProxyInfo
0x180021695  call    cs:__imp_NdrClientCall3
0x18002169c  nop     dword ptr [rax+rax+00h]
0x1800216a1  mov     rbx, rax
0x1800216a4  mov     [rsp+88h+arg_0], rax
0x1800216ac  mov     [rsp+88h+var_48], eax
0x1800216b0  jmp     short loc_1800216D9
0x1800216b2  test    eax, eax
0x1800216b4  jle     short loc_1800216BE
0x1800216b6  movzx   eax, ax
0x1800216b9  or      eax, 80070000h
0x1800216be  mov     ebx, eax
0x1800216c0  mov     [rsp+88h+var_48], eax
0x1800216c4  mov     r8d, eax
0x1800216c7  lea     rdx, aRpcgetuserprof; "RpcGetUserProfile threw an exception: 0"...
0x1800216ce  mov     ecx, 8; int
0x1800216d3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800216d8  nop
0x1800216d9  lea     rcx, [rsp+88h+var_40]; this
0x1800216de  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800216e3  mov     eax, ebx
0x1800216e5  add     rsp, 68h
0x1800216e9  pop     r14
0x1800216eb  pop     rdi
0x1800216ec  pop     rsi
0x1800216ed  pop     rbx
0x1800216ee  retn
0x18003377f  push    rbp
0x180033781  sub     rsp, 40h
0x180033785  mov     rbp, rdx
0x180033788  mov     rcx, [rcx]
0x18003378b  mov     ecx, [rcx]; ExceptionCode
0x18003378d  call    cs:__imp_I_RpcExceptionFilter
0x180033794  nop     dword ptr [rax+rax+00h]
0x180033799  nop
0x18003379a  add     rsp, 40h
0x18003379e  pop     rbp
0x18003379f  retn
```
