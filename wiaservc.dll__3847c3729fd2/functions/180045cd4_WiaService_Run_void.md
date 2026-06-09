# WiaService::Run(void)

- ea: `0x180045cd4`
- end: `0x180045e35`
- name: `?Run@WiaService@@QEAAJXZ`
- size: `353`
- prototype: `__int64 __fastcall(WiaService *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038de0`

## callees

- `0x18000557c`
- `0x180006b88`
- `0x18000a974`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000f4fc`
- `0x180011a94`
- `0x1800174c4`
- `0x18002c868`
- `0x18002c8b0`
- `0x180033cc0`
- `0x180045cd4`
- `0x180078010`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x180045de5`
- `KERNEL32!WaitForSingleObjectEx` at `0x180045de5`

## string_xrefs

- `0x180045cff`: `ServiceStatus`
- `0x180045d79`: `The WIA service is now running.`
- `0x180045da6`: `The WIA service is now running.`
- `0x180045d8f`: `WiaService::Run`
- `0x180045dc4`: `WiaService::Run`

## pseudocode

```c
__int64 __fastcall WiaService::Run(WiaService *this)
{
  __int64 v2; // rdi
  unsigned int v3; // esi
  char *v4; // rbx
  void *v5; // rdx
  void **lpMem; // rax
  void *v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  _BYTE v11[16]; // [rsp+30h] [rbp-178h] BYREF
  _QWORD v12[38]; // [rsp+40h] [rbp-168h] BYREF

  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v11);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v12, L"ServiceStatus");
  v2 = ServiceComponentHolder::Get<ServiceStatus>(v11, v12);
  v12[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v12);
  v3 = 0;
  v12[34] = 0;
  if ( v2 )
  {
    if ( *((_DWORD *)this + 2) == 1231255123 )
    {
      (**(void (__fastcall ***)(__int64, __int64))v2)(v2, 4);
      v4 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0x80000000LL, 0, "The WIA service is now running.");
      WriteDbgTraceInfoWI("WiaService::Run", v4);
      WiaTrcLib::Free((WiaTrcLib *)v4, v5);
      lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(0x80000000, 0, "The WIA service is now running.");
      WiaTrace_ProcessTrace_Ex(v8, v7, (void *)"WiaService::Run", 4, lpMem);
      WiaService::CheckForActivityAndShutdown(this);
      WaitForSingleObjectEx(g_hShutdownEvent, 0xFFFFFFFF, 0);
    }
    else
    {
      v3 = -2147418113;
    }
    v9 = v2 + *(int *)(*(_QWORD *)(v2 + 8) + 4LL) + 8LL;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  else
  {
    v3 = -2147467259;
  }
  *((_DWORD *)this + 2) = 1415804499;
  ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v11);
  return v3;
}

```

## disassembly

```asm
0x180045cd4  push    rbx
0x180045cd6  push    rbp
0x180045cd7  push    rsi
0x180045cd8  push    rdi
0x180045cd9  sub     rsp, 188h
0x180045ce0  mov     rax, cs:__security_cookie
0x180045ce7  xor     rax, rsp
0x180045cea  mov     [rsp+1A8h+var_38], rax
0x180045cf2  mov     rbp, rcx
0x180045cf5  lea     rcx, [rsp+1A8h+var_178]; this
0x180045cfa  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x180045cff  lea     rdx, aServicestatus; "ServiceStatus"
0x180045d06  lea     rcx, [rsp+1A8h+var_168]
0x180045d0b  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180045d10  lea     rdx, [rsp+1A8h+var_168]
0x180045d15  lea     rcx, [rsp+1A8h+var_178]
0x180045d1a  call    ??$Get@VServiceStatus@@@ServiceComponentHolder@@QEAAPEAVServiceStatus@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<ServiceStatus>(CSimpleStringBase<ushort> const &)
0x180045d1f  mov     rdi, rax
0x180045d22  lea     rcx, [rsp+1A8h+var_168]
0x180045d27  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180045d2e  mov     [rsp+1A8h+var_168], rax
0x180045d33  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180045d38  xor     esi, esi
0x180045d3a  mov     [rsp+1A8h+var_58], rsi
0x180045d42  test    rdi, rdi
0x180045d45  jnz     short loc_180045D51
0x180045d47  mov     esi, 80004005h
0x180045d4c  jmp     loc_180045E06
0x180045d51  cmp     dword ptr [rbp+8], 49637653h
0x180045d58  jz      short loc_180045D64
0x180045d5a  mov     esi, 8000FFFFh
0x180045d5f  jmp     loc_180045DEB
0x180045d64  mov     rax, [rdi]
0x180045d67  xor     r8d, r8d
0x180045d6a  mov     rcx, rdi
0x180045d6d  mov     rax, [rax]
0x180045d70  lea     edx, [r8+4]
0x180045d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d79  lea     r8, aTheWiaServiceI_3; "The WIA service is now running."
0x180045d80  xor     edx, edx
0x180045d82  mov     ecx, 80000000h
0x180045d87  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180045d8c  mov     rdx, rax; char *
0x180045d8f  lea     rcx, aWiaserviceRun; "WiaService::Run"
0x180045d96  mov     rbx, rax
0x180045d99  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180045d9e  mov     rcx, rbx; this
0x180045da1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180045da6  lea     r8, aTheWiaServiceI_3; "The WIA service is now running."
0x180045dad  xor     edx, edx
0x180045daf  mov     ecx, 80000000h
0x180045db4  call    WiaTrace_TraceWithSubCompTraceLevel
0x180045db9  mov     r9d, 4; int
0x180045dbf  mov     [rsp+1A8h+lpMem], rax; lpMem
0x180045dc4  lea     r8, aWiaserviceRun; "WiaService::Run"
0x180045dcb  call    WiaTrace_ProcessTrace_Ex
0x180045dd0  mov     rcx, rbp; this
0x180045dd3  call    ?CheckForActivityAndShutdown@WiaService@@QEAAJXZ; WiaService::CheckForActivityAndShutdown(void)
0x180045dd8  mov     rcx, cs:?g_hShutdownEvent@@3PEAXEA; hHandle
0x180045ddf  xor     r8d, r8d; bAlertable
0x180045de2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180045de5  call    cs:__imp_WaitForSingleObjectEx
0x180045deb  mov     rcx, [rdi+8]
0x180045def  movsxd  rcx, dword ptr [rcx+4]
0x180045df3  add     rcx, 8
0x180045df7  add     rcx, rdi
0x180045dfa  mov     rdx, [rcx]
0x180045dfd  mov     rax, [rdx+10h]
0x180045e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e06  lea     rcx, [rsp+1A8h+var_178]; this
0x180045e0b  mov     dword ptr [rbp+8], 54637653h
0x180045e12  call    ??1ServiceComponentHolder@@UEAA@XZ; ServiceComponentHolder::~ServiceComponentHolder(void)
0x180045e17  mov     eax, esi
0x180045e19  mov     rcx, [rsp+1A8h+var_38]
0x180045e21  xor     rcx, rsp; StackCookie
0x180045e24  call    __security_check_cookie
0x180045e29  add     rsp, 188h
0x180045e30  pop     rdi
0x180045e31  pop     rsi
0x180045e32  pop     rbp
0x180045e33  pop     rbx
0x180045e34  retn
```
