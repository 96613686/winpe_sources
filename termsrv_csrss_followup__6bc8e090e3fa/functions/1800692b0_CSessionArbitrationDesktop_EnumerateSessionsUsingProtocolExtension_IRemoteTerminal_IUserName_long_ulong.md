# CSessionArbitrationDesktop::EnumerateSessionsUsingProtocolExtension(IRemoteTerminal *,IUserName *,long * *,ulong *)

- ea: `0x1800692b0`
- end: `0x180069429`
- name: `?EnumerateSessionsUsingProtocolExtension@CSessionArbitrationDesktop@@IEAAJPEAVIRemoteTerminal@@PEAUIUserName@@PEAPEAJPEAK@Z`
- size: `377`
- prototype: `__int64 __fastcall(CSessionArbitrationDesktop *__hidden this, struct IRemoteTerminal *, struct IUserName *, int **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006a49c`

## callees

- `0x180009940`
- `0x1800146c8`
- `0x1800692b0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006932a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006932a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006940c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006940c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800693a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800693a2`

## string_xrefs

- `0x18006934e`: `DuplicateTokenInPid failed: 0x%x in %s`
- `0x1800692c6`: `CSessionArbitrationDesktop::EnumerateSessionsUsingProtocolExtension`

## pseudocode

```c
__int64 __fastcall CSessionArbitrationDesktop::EnumerateSessionsUsingProtocolExtension(
        CSessionArbitrationDesktop *this,
        struct IRemoteTerminal *a2,
        struct IUserName *a3,
        int **a4,
        unsigned int *a5)
{
  __int64 (__fastcall *v9)(struct IUserName *, _QWORD, HANDLE *); // rbx
  DWORD CurrentProcessId; // eax
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int *v13; // rdi
  HANDLE v14; // rdx
  int *v15; // rax
  int v16; // eax
  unsigned int *v18; // [rsp+20h] [rbp-78h]
  HANDLE hObject; // [rsp+40h] [rbp-58h] BYREF
  const char *v20; // [rsp+48h] [rbp-50h] BYREF
  const char *v21; // [rsp+50h] [rbp-48h] BYREF
  int v22; // [rsp+B0h] [rbp+18h] BYREF

  hObject = 0;
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v22 = *((_DWORD *)this + 416);
    v21 = "Status";
    v20 = "CSessionArbitrationDesktop::EnumerateSessionsUsingProtocolExtension";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)word_18010FFA2,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v22);
  }
  v9 = *(__int64 (__fastcall **)(struct IUserName *, _QWORD, HANDLE *))(*(_QWORD *)a3 + 80LL);
  CurrentProcessId = GetCurrentProcessId();
  v11 = v9(a3, CurrentProcessId, &hObject);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v13 = a5;
    v14 = hObject;
    v18 = a5;
    *a5 = 0;
    v12 = (*(__int64 (__fastcall **)(struct IRemoteTerminal *, HANDLE, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)a2 + 384LL))(
            a2,
            v14,
            *((unsigned int *)this + 415),
            0,
            v18);
    if ( v12 == -2147024774 && *v13 )
    {
      v15 = (int *)CoTaskMemAlloc(4LL * *v13);
      *a4 = v15;
      if ( v15 )
      {
        v16 = (*(__int64 (__fastcall **)(struct IRemoteTerminal *, HANDLE, _QWORD, int *, unsigned int *))(*(_QWORD *)a2 + 384LL))(
                a2,
                hObject,
                *((unsigned int *)this + 415),
                v15,
                v13);
        v12 = v16;
        if ( v16 < 0 )
          _DbgPrintMessage(
            8,
            "SessionArbitrationEnumeration failed: 0x%x in %s",
            (unsigned int)v16,
            "CSessionArbitrationDesktop::EnumerateSessionsUsingProtocolExtension");
      }
      else
      {
        v12 = -2147024882;
        *v13 = 0;
      }
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "DuplicateTokenInPid failed: 0x%x in %s",
      (unsigned int)v11,
      "CSessionArbitrationDesktop::EnumerateSessionsUsingProtocolExtension");
  }
  if ( hObject )
    CloseHandle(hObject);
  return v12;
}

```

## disassembly

```asm
0x1800692b0  mov     r11, rsp
0x1800692b3  push    rbx
0x1800692b4  push    rsi
0x1800692b5  push    rdi
0x1800692b6  push    r12
0x1800692b8  push    r14
0x1800692ba  push    r15
0x1800692bc  sub     rsp, 68h
0x1800692c0  mov     eax, cs:dword_18012E170
0x1800692c6  lea     r12, aCsessionarbitr; "CSessionArbitrationDesktop::EnumerateSe"...
0x1800692cd  mov     qword ptr [r11-58h], 0
0x1800692d5  mov     r15, r9
0x1800692d8  mov     rdi, r8
0x1800692db  mov     r14, rdx
0x1800692de  mov     rsi, rcx
0x1800692e1  cmp     eax, 4
0x1800692e4  jbe     short loc_180069323
0x1800692e6  mov     eax, [rcx+680h]
0x1800692ec  lea     rdx, word_18010FFA2
0x1800692f3  mov     [r11+18h], eax
0x1800692f7  lea     rax, aStatus; "Status"
0x1800692fe  mov     [r11-48h], rax
0x180069302  lea     rax, [r11+18h]
0x180069306  mov     [r11-68h], rax
0x18006930a  lea     rax, [r11-50h]
0x18006930e  mov     [r11-70h], rax
0x180069312  lea     rax, [r11-48h]
0x180069316  mov     [r11-78h], rax
0x18006931a  mov     [r11-50h], r12
0x18006931e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180069323  mov     rax, [rdi]
0x180069326  mov     rbx, [rax+50h]
0x18006932a  call    cs:__imp_GetCurrentProcessId
0x180069331  nop     dword ptr [rax+rax+00h]
0x180069336  lea     r8, [rsp+98h+hObject]
0x18006933b  mov     rcx, rdi
0x18006933e  mov     edx, eax
0x180069340  mov     rax, rbx
0x180069343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069348  mov     ebx, eax
0x18006934a  test    eax, eax
0x18006934c  jns     short loc_18006935A
0x18006934e  lea     rdx, aDuplicatetoken; "DuplicateTokenInPid failed: 0x%x in %s"
0x180069355  jmp     loc_1800693F2
0x18006935a  mov     rdi, [rsp+98h+arg_20]
0x180069362  xor     r9d, r9d
0x180069365  mov     rdx, [rsp+98h+hObject]
0x18006936a  mov     rcx, r14
0x18006936d  mov     [rsp+98h+var_78], rdi
0x180069372  mov     dword ptr [rdi], 0
0x180069378  mov     rax, [r14]
0x18006937b  mov     r8d, [rsi+67Ch]
0x180069382  mov     rax, [rax+180h]
0x180069389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006938e  mov     ebx, eax
0x180069390  cmp     eax, 8007007Ah
0x180069395  jnz     short loc_180069402
0x180069397  cmp     dword ptr [rdi], 0
0x18006939a  jz      short loc_180069402
0x18006939c  mov     ecx, [rdi]
0x18006939e  shl     rcx, 2; cb
0x1800693a2  call    cs:__imp_CoTaskMemAlloc
0x1800693a9  nop     dword ptr [rax+rax+00h]
0x1800693ae  mov     [r15], rax
0x1800693b1  mov     r9, rax
0x1800693b4  test    rax, rax
0x1800693b7  jnz     short loc_1800693C2
0x1800693b9  mov     ebx, 8007000Eh
0x1800693be  mov     [rdi], eax
0x1800693c0  jmp     short loc_180069402
0x1800693c2  mov     rax, [r14]
0x1800693c5  mov     rcx, r14
0x1800693c8  mov     r8d, [rsi+67Ch]
0x1800693cf  mov     rdx, [rsp+98h+hObject]
0x1800693d4  mov     [rsp+98h+var_78], rdi
0x1800693d9  mov     rax, [rax+180h]
0x1800693e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800693e5  mov     ebx, eax
0x1800693e7  test    eax, eax
0x1800693e9  jns     short loc_180069402
0x1800693eb  lea     rdx, aSessionarbitra_0; "SessionArbitrationEnumeration failed: 0"...
0x1800693f2  mov     r9, r12
0x1800693f5  mov     r8d, eax
0x1800693f8  mov     ecx, 8; int
0x1800693fd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180069402  mov     rcx, [rsp+98h+hObject]; hObject
0x180069407  test    rcx, rcx
0x18006940a  jz      short loc_180069418
0x18006940c  call    cs:__imp_CloseHandle
0x180069413  nop     dword ptr [rax+rax+00h]
0x180069418  mov     eax, ebx
0x18006941a  add     rsp, 68h
0x18006941e  pop     r15
0x180069420  pop     r14
0x180069422  pop     r12
0x180069424  pop     rdi
0x180069425  pop     rsi
0x180069426  pop     rbx
0x180069427  retn
```
