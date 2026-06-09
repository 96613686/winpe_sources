# WiaService::Stop(void)

- ea: `0x18002e72c`
- end: `0x18002e8f8`
- name: `?Stop@WiaService@@QEAAJXZ`
- size: `460`
- prototype: `__int64 __fastcall(WiaService *__hidden this)`
- caller_count: `4`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ecf0`
- `0x1800202b8`
- `0x180045e40`
- `0x180059d34`

## callees

- `0x180006b88`
- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000f4fc`
- `0x180011a94`
- `0x1800174c4`
- `0x18002de18`
- `0x18002def8`
- `0x18002e72c`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002e832`
- `KERNEL32!GetLastError` at `0x18002e832`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002e824`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002e824`

## string_xrefs

- `0x18002e758`: `ServiceStatus`
- `0x18002e84e`: `Could not signal the service to shut down! (SetEvent failed with 0x%X)`
- `0x18002e876`: `Could not signal the service to shut down! (SetEvent failed with 0x%X)`
- `0x18002e7da`: `We cannot let the controller know that the service is Stopping`
- `0x18002e7fc`: `We cannot let the controller know that the service is Stopping`
- `0x18002e799`: `WiaService::Stop`
- `0x18002e887`: `Could not signal the service to shut down, the service may be already shutting down`
- `0x18002e8ac`: `Could not signal the service to shut down, the service may be already shutting down`

## pseudocode

```c
__int64 __fastcall WiaService::Stop(WiaService *this)
{
  unsigned int v1; // edi
  __int64 v2; // rbx
  __int64 v3; // rcx
  char *v4; // rbx
  void *v5; // rdx
  void **lpMem; // rax
  void *v7; // rdx
  __int64 v8; // rcx
  signed int LastError; // eax
  signed int v10; // esi
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  char *v16; // rbx
  void *v17; // rdx
  _BYTE v19[16]; // [rsp+30h] [rbp-178h] BYREF
  _QWORD v20[38]; // [rsp+40h] [rbp-168h] BYREF

  v1 = 0;
  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v19);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v20, L"ServiceStatus");
  v2 = ServiceComponentHolder::Get<ServiceStatus>(v19, v20);
  v20[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v20);
  v20[34] = 0;
  if ( v2 )
  {
    (**(void (__fastcall ***)(__int64, __int64, _QWORD))v2)(v2, 3, 0);
    v3 = v2 + *(int *)(*(_QWORD *)(v2 + 8) + 4LL) + 8LL;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  else
  {
    v4 = (char *)WiaTrace_TraceLog("We cannot let the controller know that the service is Stopping");
    WriteDbgTraceErrorWI("WiaService::Stop", v4);
    WiaTrcLib::Free((WiaTrcLib *)v4, v5);
    lpMem = (void **)WiaTrace_Trace("We cannot let the controller know that the service is Stopping");
    WiaTrace_ProcessTrace_Ex(v8, v7, (void *)"WiaService::Stop", 1, lpMem);
  }
  if ( !g_hShutdownEvent )
  {
    v16 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "Could not signal the service to shut down, the service may be already shutting down");
    WriteDbgTraceWarningWI("WiaService::Stop", v16);
    WiaTrcLib::Free((WiaTrcLib *)v16, v17);
    v13 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "Could not signal the service to shut down, the service may be already shutting down");
LABEL_11:
    WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"WiaService::Stop", 2, v13);
    goto LABEL_12;
  }
  if ( !SetEvent(g_hShutdownEvent) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    else
      v1 = LastError;
    v11 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "Could not signal the service to shut down! (SetEvent failed with 0x%X)",
                    LastError);
    WriteDbgTraceWarningWI("WiaService::Stop", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    v13 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "Could not signal the service to shut down! (SetEvent failed with 0x%X)",
                     v10);
    goto LABEL_11;
  }
LABEL_12:
  ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v19);
  return v1;
}

```

## disassembly

```asm
0x18002e72c  push    rbx
0x18002e72e  push    rbp
0x18002e72f  push    rsi
0x18002e730  push    rdi
0x18002e731  push    r14
0x18002e733  sub     rsp, 180h
0x18002e73a  mov     rax, cs:__security_cookie
0x18002e741  xor     rax, rsp
0x18002e744  mov     [rsp+1A8h+var_38], rax
0x18002e74c  lea     rcx, [rsp+1A8h+var_178]; this
0x18002e751  xor     edi, edi
0x18002e753  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x18002e758  lea     rdx, aServicestatus; "ServiceStatus"
0x18002e75f  lea     rcx, [rsp+1A8h+var_168]
0x18002e764  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18002e769  lea     rdx, [rsp+1A8h+var_168]
0x18002e76e  lea     rcx, [rsp+1A8h+var_178]
0x18002e773  call    ??$Get@VServiceStatus@@@ServiceComponentHolder@@QEAAPEAVServiceStatus@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<ServiceStatus>(CSimpleStringBase<ushort> const &)
0x18002e778  mov     rbx, rax
0x18002e77b  lea     rcx, [rsp+1A8h+var_168]
0x18002e780  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18002e787  mov     [rsp+1A8h+var_168], rax
0x18002e78c  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18002e791  mov     [rsp+1A8h+var_58], rdi
0x18002e799  lea     rbp, aWiaserviceStop; "WiaService::Stop"
0x18002e7a0  lea     r14d, [rdi+1]
0x18002e7a4  test    rbx, rbx
0x18002e7a7  jz      short loc_18002E7DA
0x18002e7a9  mov     rax, [rbx]
0x18002e7ac  lea     edx, [rdi+3]
0x18002e7af  xor     r8d, r8d
0x18002e7b2  mov     rcx, rbx
0x18002e7b5  mov     rax, [rax]
0x18002e7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7bd  mov     rax, [rbx+8]
0x18002e7c1  movsxd  rcx, dword ptr [rax+4]
0x18002e7c5  add     rcx, 8
0x18002e7c9  add     rcx, rbx
0x18002e7cc  mov     rax, [rcx]
0x18002e7cf  mov     rax, [rax+10h]
0x18002e7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7d8  jmp     short loc_18002E818
0x18002e7da  lea     rcx, aWeCannotLetThe_1; "We cannot let the controller know that "...
0x18002e7e1  call    WiaTrace_TraceLog
0x18002e7e6  mov     rdx, rax; char *
0x18002e7e9  mov     rcx, rbp; char *
0x18002e7ec  mov     rbx, rax
0x18002e7ef  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002e7f4  mov     rcx, rbx; this
0x18002e7f7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002e7fc  lea     rcx, aWeCannotLetThe_1; "We cannot let the controller know that "...
0x18002e803  call    WiaTrace_Trace
0x18002e808  mov     r9d, r14d; int
0x18002e80b  mov     [rsp+1A8h+lpMem], rax; lpMem
0x18002e810  mov     r8, rbp; int
0x18002e813  call    WiaTrace_ProcessTrace_Ex
0x18002e818  mov     rcx, cs:?g_hShutdownEvent@@3PEAXEA; hEvent
0x18002e81f  test    rcx, rcx
0x18002e822  jz      short loc_18002E887
0x18002e824  call    cs:__imp_SetEvent
0x18002e82a  test    eax, eax
0x18002e82c  jnz     loc_18002E8CE
0x18002e832  call    cs:__imp_GetLastError
0x18002e838  mov     esi, eax
0x18002e83a  test    eax, eax
0x18002e83c  jg      short loc_18002E842
0x18002e83e  mov     edi, eax
0x18002e840  jmp     short loc_18002E84B
0x18002e842  movzx   edi, si
0x18002e845  or      edi, 80070000h
0x18002e84b  mov     r8d, esi
0x18002e84e  lea     rdx, aCouldNotSignal; "Could not signal the service to shut do"...
0x18002e855  mov     ecx, r14d
0x18002e858  call    WiaTrace_TraceLogWithSubComp
0x18002e85d  mov     rdx, rax; char *
0x18002e860  mov     rcx, rbp; char *
0x18002e863  mov     rbx, rax
0x18002e866  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18002e86b  mov     rcx, rbx; this
0x18002e86e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002e873  mov     r8d, esi
0x18002e876  lea     rdx, aCouldNotSignal; "Could not signal the service to shut do"...
0x18002e87d  mov     ecx, r14d
0x18002e880  call    WiaTrace_TraceWithSubComp
0x18002e885  jmp     short loc_18002E8BB
0x18002e887  lea     rdx, aCouldNotSignal_0; "Could not signal the service to shut do"...
0x18002e88e  mov     ecx, r14d
0x18002e891  call    WiaTrace_TraceLogWithSubComp
0x18002e896  mov     rdx, rax; char *
0x18002e899  mov     rcx, rbp; char *
0x18002e89c  mov     rbx, rax
0x18002e89f  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18002e8a4  mov     rcx, rbx; this
0x18002e8a7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002e8ac  lea     rdx, aCouldNotSignal_0; "Could not signal the service to shut do"...
0x18002e8b3  mov     ecx, r14d
0x18002e8b6  call    WiaTrace_TraceWithSubComp
0x18002e8bb  mov     r9d, 2; int
0x18002e8c1  mov     [rsp+1A8h+lpMem], rax; lpMem
0x18002e8c6  mov     r8, rbp; int
0x18002e8c9  call    WiaTrace_ProcessTrace_Ex
0x18002e8ce  lea     rcx, [rsp+1A8h+var_178]; this
0x18002e8d3  call    ??1ServiceComponentHolder@@UEAA@XZ; ServiceComponentHolder::~ServiceComponentHolder(void)
0x18002e8d8  mov     eax, edi
0x18002e8da  mov     rcx, [rsp+1A8h+var_38]
0x18002e8e2  xor     rcx, rsp; StackCookie
0x18002e8e5  call    __security_check_cookie
0x18002e8ea  add     rsp, 180h
0x18002e8f1  pop     r14
0x18002e8f3  pop     rdi
0x18002e8f4  pop     rsi
0x18002e8f5  pop     rbp
0x18002e8f6  pop     rbx
0x18002e8f7  retn
```
