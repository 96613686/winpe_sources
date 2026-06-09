# CreateAssemblyNameObject

- ea: `0x180053110`
- end: `0x180053301`
- name: `CreateAssemblyNameObject`
- size: `497`
- prototype: `HRESULT __stdcall(LPASSEMBLYNAME *ppAssemblyNameObj, LPCWSTR szAssemblyName, DWORD dwFlags, LPVOID pvReserved)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180052c98`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18002e98c`
- `0x18002ff90`
- `0x180053110`
- `0x180053308`
- `0x18005bf78`
- `0x18005cc58`
- `0x18005d2b0`
- `0x180061640`
- `0x180061f6c`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800531d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053222`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005325c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800531d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053222`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005325c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800531ef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800531ef`

## pseudocode

```c
HRESULT __stdcall CreateAssemblyNameObject(
        LPASSEMBLYNAME *ppAssemblyNameObj,
        LPCWSTR szAssemblyName,
        DWORD dwFlags,
        LPVOID pvReserved)
{
  const char *v8; // rcx
  CAssemblyName *v9; // rax
  int v10; // eax
  int v11; // edi
  int v12; // edx
  int v13; // eax
  int v14; // ebx
  HRESULT v15; // ebx
  CAssemblyName *v17; // [rsp+20h] [rbp-50h] BYREF
  char v18; // [rsp+28h] [rbp-48h]
  int v19; // [rsp+30h] [rbp-40h] BYREF
  int v20; // [rsp+38h] [rbp-38h] BYREF
  __int64 v21; // [rsp+40h] [rbp-30h]
  __int64 *v22; // [rsp+48h] [rbp-28h]
  __int64 v23; // [rsp+50h] [rbp-20h]
  int v24; // [rsp+58h] [rbp-18h]
  int *v25; // [rsp+60h] [rbp-10h]

  v19 = -1;
  v22 = &qword_180072350;
  v20 = 1;
  v25 = &v19;
  v21 = 0;
  v23 = 544438355;
  v24 = 41;
  CFrame::BaseEnter((CFrame *)&v20);
  v17 = 0;
  v18 = 0;
  if ( ppAssemblyNameObj )
    *ppAssemblyNameObj = 0;
  if ( dwFlags != 1 )
  {
    v24 = 52;
LABEL_5:
    FusionpTraceParameterCheck(v8);
    *v25 = -2147024809;
    goto LABEL_19;
  }
  if ( !ppAssemblyNameObj )
  {
    v24 = 53;
    goto LABEL_5;
  }
  if ( pvReserved )
  {
    v24 = 54;
    goto LABEL_5;
  }
  SetLastError(0);
  v9 = (CAssemblyName *)HeapAlloc(g_hHeap, 0, 0x20u);
  if ( !v9 || (v17 = CAssemblyName::CAssemblyName(v9)) == 0 )
  {
    CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v20);
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180076660);
    goto LABEL_19;
  }
  v18 = 1;
  SetLastError(0);
  v10 = CAssemblyName::Parse(v17, szAssemblyName);
  v11 = v10;
  if ( v10 >= 0 )
  {
    SetLastError(0);
    v13 = (**(__int64 (__fastcall ***)(CAssemblyName *, GUID *, LPASSEMBLYNAME *))v17)(
            v17,
            &IID_IAssemblyName,
            ppAssemblyNameObj);
    v14 = v13;
    if ( v13 >= 0 )
    {
      v17 = 0;
      v18 = 0;
      *v25 = 0;
      goto LABEL_19;
    }
    FusionpTraceCOMFailure(v13, byte_18008517D);
    v12 = v14;
  }
  else
  {
    FusionpTraceCOMFailure(v10, byte_18008517D);
    v12 = v11;
  }
  CFnTracerHR::MarkCOMFailure((CFnTracerHR *)&v20, v12);
LABEL_19:
  v15 = *v25;
  CSmartPtr<CAssemblyName,CSmartPtrBaseTypeHelper<CAssemblyName>>::~CSmartPtr<CAssemblyName,CSmartPtrBaseTypeHelper<CAssemblyName>>(&v17);
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v20);
  return v15;
}

```

## disassembly

```asm
0x180053110  mov     [rsp-18h+arg_10], rbx
0x180053115  mov     [rsp-18h+arg_18], rsi
0x18005311a  push    rbp
0x18005311b  push    rdi
0x18005311c  push    r14
0x18005311e  mov     rbp, rsp
0x180053121  sub     rsp, 70h
0x180053125  mov     rax, cs:__security_cookie
0x18005312c  xor     rax, rsp
0x18005312f  mov     [rbp+var_8], rax
0x180053133  lea     rax, qword_180072350
0x18005313a  mov     [rbp+var_40], 0FFFFFFFFh
0x180053141  mov     [rbp+var_28], rax
0x180053145  mov     rsi, rcx
0x180053148  lea     rax, [rbp+var_40]
0x18005314c  mov     [rbp+var_38], 1
0x180053153  lea     rcx, [rbp+var_38]; this
0x180053157  mov     [rbp+var_10], rax
0x18005315b  mov     rdi, r9
0x18005315e  mov     [rbp+var_30], 0
0x180053166  mov     ebx, r8d
0x180053169  mov     [rbp+var_20], 20737853h
0x180053171  mov     r14, rdx
0x180053174  mov     [rbp+var_18], 29h ; ')'
0x18005317b  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180053180  mov     [rbp+var_50], 0
0x180053188  mov     [rbp+var_48], 0
0x18005318c  test    rsi, rsi
0x18005318f  jz      short loc_180053198
0x180053191  mov     qword ptr [rsi], 0
0x180053198  cmp     ebx, 1
0x18005319b  jz      short loc_1800531B8
0x18005319d  mov     [rbp+var_18], 34h ; '4'
0x1800531a4  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x1800531a9  mov     rax, [rbp+var_10]
0x1800531ad  mov     dword ptr [rax], 80070057h
0x1800531b3  jmp     loc_1800532C5
0x1800531b8  test    rsi, rsi
0x1800531bb  jnz     short loc_1800531C6
0x1800531bd  mov     [rbp+var_18], 35h ; '5'
0x1800531c4  jmp     short loc_1800531A4
0x1800531c6  test    rdi, rdi
0x1800531c9  jz      short loc_1800531D4
0x1800531cb  mov     [rbp+var_18], 36h ; '6'
0x1800531d2  jmp     short loc_1800531A4
0x1800531d4  xor     ecx, ecx; dwErrCode
0x1800531d6  call    cs:__imp_SetLastError
0x1800531dd  nop     dword ptr [rax+rax+00h]
0x1800531e2  mov     rcx, cs:g_hHeap; hHeap
0x1800531e9  xor     edx, edx; dwFlags
0x1800531eb  lea     r8d, [rdx+20h]; dwBytes
0x1800531ef  call    cs:__imp_HeapAlloc
0x1800531f6  nop     dword ptr [rax+rax+00h]
0x1800531fb  test    rax, rax
0x1800531fe  jz      loc_1800532B0
0x180053204  mov     rcx, rax; this
0x180053207  call    ??0CAssemblyName@@QEAA@XZ; CAssemblyName::CAssemblyName(void)
0x18005320c  mov     [rbp+var_50], rax
0x180053210  mov     rbx, rax
0x180053213  test    rax, rax
0x180053216  jz      loc_1800532B0
0x18005321c  mov     [rbp+var_48], 1
0x180053220  xor     ecx, ecx; dwErrCode
0x180053222  call    cs:__imp_SetLastError
0x180053229  nop     dword ptr [rax+rax+00h]
0x18005322e  mov     rdx, r14; unsigned __int16 *
0x180053231  mov     rcx, rbx; this
0x180053234  call    ?Parse@CAssemblyName@@QEAAJPEBG@Z; CAssemblyName::Parse(ushort const *)
0x180053239  mov     edi, eax
0x18005323b  test    eax, eax
0x18005323d  jns     short loc_18005325A
0x18005323f  lea     rdx, byte_18008517D; char *
0x180053246  mov     ecx, eax; int
0x180053248  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18005324d  mov     edx, edi; int
0x18005324f  lea     rcx, [rbp+var_38]; this
0x180053253  call    ?MarkCOMFailure@CFnTracerHR@@QEAAXJ@Z; CFnTracerHR::MarkCOMFailure(long)
0x180053258  jmp     short loc_1800532C5
0x18005325a  xor     ecx, ecx; dwErrCode
0x18005325c  call    cs:__imp_SetLastError
0x180053263  nop     dword ptr [rax+rax+00h]
0x180053268  mov     rax, [rbx]
0x18005326b  lea     rdx, IID_IAssemblyName
0x180053272  mov     r8, rsi
0x180053275  mov     rcx, rbx
0x180053278  mov     rax, [rax]
0x18005327b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053280  mov     ebx, eax
0x180053282  test    eax, eax
0x180053284  jns     short loc_180053298
0x180053286  lea     rdx, byte_18008517D; char *
0x18005328d  mov     ecx, eax; int
0x18005328f  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x180053294  mov     edx, ebx
0x180053296  jmp     short loc_18005324F
0x180053298  mov     rax, [rbp+var_10]
0x18005329c  mov     [rbp+var_50], 0
0x1800532a4  mov     [rbp+var_48], 0
0x1800532a8  mov     dword ptr [rax], 0
0x1800532ae  jmp     short loc_1800532C5
0x1800532b0  lea     rcx, [rbp+var_38]; this
0x1800532b4  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x1800532b9  lea     rcx, off_180076660; struct _CALL_SITE_INFO *
0x1800532c0  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800532c5  mov     rax, [rbp+var_10]
0x1800532c9  lea     rcx, [rbp+var_50]
0x1800532cd  mov     ebx, [rax]
0x1800532cf  call    ??1?$CSmartPtr@VCAssemblyName@@V?$CSmartPtrBaseTypeHelper@VCAssemblyName@@@@@@QEAA@XZ; CSmartPtr<CAssemblyName,CSmartPtrBaseTypeHelper<CAssemblyName>>::~CSmartPtr<CAssemblyName,CSmartPtrBaseTypeHelper<CAssemblyName>>(void)
0x1800532d4  lea     rcx, [rbp+var_38]; this
0x1800532d8  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x1800532dd  mov     eax, ebx
0x1800532df  mov     rcx, [rbp+var_8]
0x1800532e3  xor     rcx, rsp; StackCookie
0x1800532e6  call    __security_check_cookie
0x1800532eb  lea     r11, [rsp+70h+var_s0]
0x1800532f0  mov     rbx, [r11+30h]
0x1800532f4  mov     rsi, [r11+38h]
0x1800532f8  mov     rsp, r11
0x1800532fb  pop     r14
0x1800532fd  pop     rdi
0x1800532fe  pop     rbp
0x1800532ff  retn
```
