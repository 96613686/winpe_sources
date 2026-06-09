# WiaService::~WiaService(void)

- ea: `0x180045844`
- end: `0x180045973`
- name: `??1WiaService@@UEAA@XZ`
- size: `303`
- prototype: `void __fastcall(WiaService *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180045980`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x180021fc0`
- `0x18002c868`
- `0x18002c8b0`
- `0x180045844`
- `0x180047054`
- `0x180050bc8`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004592c`
- `KERNEL32!GetLastError` at `0x18004592c`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1800458f0`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1800458f0`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180045922`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180045922`

## string_xrefs

- `0x18004585d`: `~WiaService (%p)`
- `0x18004589c`: `~WiaService (%p)`
- `0x180045883`: `WiaService::~WiaService`
- `0x1800458b9`: `WiaService::~WiaService`

## pseudocode

```c
void __fastcall WiaService::~WiaService(WiaService *this)
{
  char *v1; // rdi
  char *v3; // rbx
  void *v4; // rdx
  void **lpMem; // rax
  void *v6; // rdx
  __int64 v7; // rcx
  struct _FACTORY_DATA near **v8; // rbx
  DWORD v9; // ecx
  struct _FACTORY_DATA near *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx

  v1 = (char *)this - 40;
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this - 5) + 4LL) - 40) = &WiaService::`vftable';
  v3 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(1, 0, "~WiaService (%p)", (char *)this - 40);
  WriteDbgTraceInfoWI("WiaService::~WiaService", v3);
  WiaTrcLib::Free((WiaTrcLib *)v3, v4);
  lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(1, 0, "~WiaService (%p)", v1);
  WiaTrace_ProcessTrace_Ex(v7, v6, (void *)"WiaService::~WiaService", 4, lpMem);
  *((_DWORD *)this - 8) = 1147369043;
  *((_DWORD *)this - 7) = -1;
  ShutdownWSDChallenge(1);
  SchedulerTerminate();
  v8 = &g_IWiaDevMgrFactoryData;
  do
  {
    v9 = *((_DWORD *)v8 + 4);
    if ( v9 )
      CoRevokeClassObject(v9);
    v10 = v8[1];
    if ( v10 )
      (*(void (__fastcall **)(struct _FACTORY_DATA near *))(*(_QWORD *)v10 + 16LL))(v10);
    v8 += 5;
  }
  while ( v8 <= (struct _FACTORY_DATA near **)&off_1800AE050 );
  if ( !DestroyPrivateObjectSecurity(&sdApiObject) )
    GetLastError();
  FreeWellKnownSids();
  v11 = *((_QWORD *)this - 1);
  if ( v11 )
  {
    v12 = v11 + 8 + *(int *)(*(_QWORD *)(v11 + 8) + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)this - 1) = 0;
  }
}

```

## disassembly

```asm
0x180045844  mov     [rsp+arg_0], rbx
0x180045849  mov     [rsp+arg_8], rsi
0x18004584e  push    rdi
0x18004584f  sub     rsp, 30h
0x180045853  lea     rdi, [rcx-28h]
0x180045857  mov     rsi, rcx
0x18004585a  mov     rax, [rdi]
0x18004585d  lea     r8, aWiaserviceP; "~WiaService (%p)"
0x180045864  mov     r9, rdi
0x180045867  movsxd  rdx, dword ptr [rax+4]
0x18004586b  lea     rax, ??_7WiaService@@6B@; const WiaService::`vftable'
0x180045872  mov     [rdx+rdi], rax
0x180045876  xor     edx, edx
0x180045878  lea     ecx, [rdx+1]
0x18004587b  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180045880  mov     rdx, rax; char *
0x180045883  lea     rcx, aWiaserviceWias; "WiaService::~WiaService"
0x18004588a  mov     rbx, rax
0x18004588d  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180045892  mov     rcx, rbx; this
0x180045895  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004589a  xor     edx, edx
0x18004589c  lea     r8, aWiaserviceP; "~WiaService (%p)"
0x1800458a3  mov     r9, rdi
0x1800458a6  lea     ecx, [rdx+1]
0x1800458a9  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800458ae  mov     r9d, 4; int
0x1800458b4  mov     [rsp+38h+lpMem], rax; lpMem
0x1800458b9  lea     r8, aWiaserviceWias; "WiaService::~WiaService"
0x1800458c0  call    WiaTrace_ProcessTrace_Ex
0x1800458c5  mov     ecx, 1; int
0x1800458ca  mov     dword ptr [rsi-20h], 44637653h
0x1800458d1  mov     dword ptr [rsi-1Ch], 0FFFFFFFFh
0x1800458d8  call    ?ShutdownWSDChallenge@@YAJH@Z; ShutdownWSDChallenge(int)
0x1800458dd  call    ?SchedulerTerminate@@YAXXZ; SchedulerTerminate(void)
0x1800458e2  lea     rbx, ?g_IWiaDevMgrFactoryData@@3PAU_FACTORY_DATA@@A; _FACTORY_DATA near * g_IWiaDevMgrFactoryData
0x1800458e9  mov     ecx, [rbx+10h]; dwRegister
0x1800458ec  test    ecx, ecx
0x1800458ee  jz      short loc_1800458F6
0x1800458f0  call    cs:__imp_CoRevokeClassObject
0x1800458f6  mov     rcx, [rbx+8]
0x1800458fa  test    rcx, rcx
0x1800458fd  jz      short loc_18004590B
0x1800458ff  mov     rax, [rcx]
0x180045902  mov     rax, [rax+10h]
0x180045906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004590b  add     rbx, 28h ; '('
0x18004590f  lea     rax, off_1800AE050
0x180045916  cmp     rbx, rax
0x180045919  jbe     short loc_1800458E9
0x18004591b  lea     rcx, ?sdApiObject@@3PEAXEA; ObjectDescriptor
0x180045922  call    cs:__imp_DestroyPrivateObjectSecurity
0x180045928  test    eax, eax
0x18004592a  jnz     short loc_180045932
0x18004592c  call    cs:__imp_GetLastError
0x180045932  call    ?FreeWellKnownSids@@YAXXZ; FreeWellKnownSids(void)
0x180045937  mov     rdx, [rsi-8]
0x18004593b  test    rdx, rdx
0x18004593e  jz      short loc_180045963
0x180045940  mov     rax, [rdx+8]
0x180045944  add     rdx, 8
0x180045948  movsxd  rcx, dword ptr [rax+4]
0x18004594c  add     rcx, rdx
0x18004594f  mov     rax, [rcx]
0x180045952  mov     rax, [rax+10h]
0x180045956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004595b  mov     qword ptr [rsi-8], 0
0x180045963  mov     rbx, [rsp+38h+arg_0]
0x180045968  mov     rsi, [rsp+38h+arg_8]
0x18004596d  add     rsp, 30h
0x180045971  pop     rdi
0x180045972  retn
```
