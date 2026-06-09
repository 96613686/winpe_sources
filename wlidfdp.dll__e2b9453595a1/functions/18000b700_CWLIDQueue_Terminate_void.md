# CWLIDQueue::Terminate(void)

- ea: `0x18000b700`
- end: `0x18000b81a`
- name: `?Terminate@CWLIDQueue@@QEAAJXZ`
- size: `282`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *pv, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006410`

## callees

- `0x180003700`
- `0x18000505c`
- `0x1800054dc`
- `0x180008edc`
- `0x18000a26c`
- `0x18000a3bc`
- `0x18000b700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7d3`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000b7c9`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000b7c9`

## pseudocode

```c
__int64 __fastcall CWLIDQueue::Terminate(struct _RTL_CRITICAL_SECTION *pv, __int64 a2, __int64 a3, unsigned int a4)
{
  volatile signed __int32 *v5; // rbx
  _QWORD *p_Type; // rdi
  _QWORD *v7; // rsi
  __int64 v8; // rdx
  int v9; // r8d
  signed int LastError; // eax
  unsigned int v11; // ebx
  const unsigned __int16 *v13[2]; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v14[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+20h] BYREF
  CRefCounted *v16; // [rsp+78h] [rbp+28h] BYREF

  v15 = 0;
  v5 = 0;
  v16 = 0;
  v14[0] = "CWLIDQueue::Terminate";
  v14[1] = &v15;
  v14[2] = 0;
  v14[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"\\wlidqueue.cpp",
    "CWLIDQueue::Terminate",
    (const char *)0x192,
    a4,
    v13[0]);
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v13, pv);
  if ( pv[1].OwningThread )
  {
    p_Type = &pv[1].DebugInfo->Type;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !p_Type )
          goto LABEL_9;
        v7 = p_Type;
        p_Type = (_QWORD *)*p_Type;
        if ( v5 != (volatile signed __int32 *)v7[2] )
          break;
LABEL_6:
        if ( v5 )
        {
          CWLIDItem::Cancel((CWLIDItem *)v5);
          CAutoRefPtr<CWLIDItem>::Deinit(&v16);
          v5 = 0;
          v16 = 0;
        }
      }
      CAutoRefPtr<CWLIDItem>::Deinit(&v16);
      v5 = (volatile signed __int32 *)v7[2];
      v16 = (CRefCounted *)v5;
      if ( v5 )
      {
        _InterlockedIncrement(v5 + 2);
        goto LABEL_6;
      }
    }
  }
LABEL_9:
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v13);
  if ( TrySubmitThreadpoolCallback(CWLIDQueue::WLIDTerminateThreadFunc, pv, 0) )
  {
    v11 = v15;
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v15 = v11;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v14, v8, v9);
  CAutoRefPtr<CWLIDItem>::Deinit(&v16);
  return v11;
}

```

## disassembly

```asm
0x18000b700  mov     [rsp-18h+arg_10], rbx
0x18000b705  mov     [rsp-18h+arg_18], rsi
0x18000b70a  push    rbp
0x18000b70b  push    rdi
0x18000b70c  push    r14
0x18000b70e  mov     rbp, rsp
0x18000b711  sub     rsp, 50h
0x18000b715  mov     r14, rcx
0x18000b718  mov     [rbp+arg_0], 0
0x18000b71f  xor     ebx, ebx
0x18000b721  mov     [rbp+arg_8], rbx
0x18000b725  lea     rdx, aCwlidqueueTerm; "CWLIDQueue::Terminate"
0x18000b72c  mov     [rbp+var_20], rdx
0x18000b730  lea     rax, [rbp+arg_0]
0x18000b734  mov     [rbp+var_18], rax
0x18000b738  mov     [rbp+var_10], rbx
0x18000b73c  mov     [rbp+var_8], rbx
0x18000b740  mov     r8d, 192h; char *
0x18000b746  lea     rcx, aWlidqueueCpp; "\\wlidqueue.cpp"
0x18000b74d  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000b752  nop
0x18000b753  mov     rdx, r14
0x18000b756  lea     rcx, [rbp+var_30]
0x18000b75a  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x18000b75f  nop
0x18000b760  cmp     [r14+38h], rbx
0x18000b764  jz      short loc_18000B7B3
0x18000b766  mov     rdi, [r14+28h]
0x18000b76a  jmp     short loc_18000B7AE
0x18000b76c  lea     rsi, [rdi]
0x18000b76f  mov     rdi, [rdi]
0x18000b772  cmp     rbx, [rsi+10h]
0x18000b776  jz      short loc_18000B792
0x18000b778  lea     rcx, [rbp+arg_8]
0x18000b77c  call    ?Deinit@?$CAutoRefPtr@VCWLIDItem@@@@IEAAXXZ; CAutoRefPtr<CWLIDItem>::Deinit(void)
0x18000b781  mov     rbx, [rsi+10h]
0x18000b785  mov     [rbp+arg_8], rbx
0x18000b789  test    rbx, rbx
0x18000b78c  jz      short loc_18000B7AE
0x18000b78e  lock inc dword ptr [rbx+8]
0x18000b792  test    rbx, rbx
0x18000b795  jz      short loc_18000B7AE
0x18000b797  mov     rcx, rbx; this
0x18000b79a  call    ?Cancel@CWLIDItem@@QEAAXXZ; CWLIDItem::Cancel(void)
0x18000b79f  lea     rcx, [rbp+arg_8]
0x18000b7a3  call    ?Deinit@?$CAutoRefPtr@VCWLIDItem@@@@IEAAXXZ; CAutoRefPtr<CWLIDItem>::Deinit(void)
0x18000b7a8  xor     ebx, ebx
0x18000b7aa  mov     [rbp+arg_8], rbx
0x18000b7ae  test    rdi, rdi
0x18000b7b1  jnz     short loc_18000B76C
0x18000b7b3  lea     rcx, [rbp+var_30]
0x18000b7b7  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18000b7bc  xor     r8d, r8d; pcbe
0x18000b7bf  mov     rdx, r14; pv
0x18000b7c2  lea     rcx, ?WLIDTerminateThreadFunc@CWLIDQueue@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18000b7c9  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000b7cf  test    eax, eax
0x18000b7d1  jnz     short loc_18000B7ED
0x18000b7d3  call    cs:__imp_GetLastError
0x18000b7d9  mov     ebx, eax
0x18000b7db  test    eax, eax
0x18000b7dd  jle     short loc_18000B7E8
0x18000b7df  movzx   ebx, ax
0x18000b7e2  or      ebx, 80070000h
0x18000b7e8  mov     [rbp+arg_0], ebx
0x18000b7eb  jmp     short loc_18000B7F0
0x18000b7ed  mov     ebx, [rbp+arg_0]
0x18000b7f0  lea     rcx, [rbp+var_20]
0x18000b7f4  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000b7f9  nop
0x18000b7fa  lea     rcx, [rbp+arg_8]
0x18000b7fe  call    ?Deinit@?$CAutoRefPtr@VCWLIDItem@@@@IEAAXXZ; CAutoRefPtr<CWLIDItem>::Deinit(void)
0x18000b803  mov     eax, ebx
0x18000b805  lea     r11, [rsp+50h+var_s0]
0x18000b80a  mov     rbx, [r11+30h]
0x18000b80e  mov     rsi, [r11+38h]
0x18000b812  mov     rsp, r11
0x18000b815  pop     r14
0x18000b817  pop     rdi
0x18000b818  pop     rbp
0x18000b819  retn
```
