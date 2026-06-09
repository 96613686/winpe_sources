# CStreamWriterTimeoutManager::~CStreamWriterTimeoutManager(void)

- ea: `0x180047764`
- end: `0x180047841`
- name: `??1CStreamWriterTimeoutManager@@QEAA@XZ`
- size: `221`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180047750`

## callees

- `0x18000ddd4`
- `0x1800285b8`
- `0x180047764`
- `0x180047848`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800477d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800477b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800477b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047773`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047839`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047839`

## pseudocode

```c
void __fastcall CStreamWriterTimeoutManager::~CStreamWriterTimeoutManager(LPCRITICAL_SECTION lpCriticalSection)
{
  char *v2; // rcx
  int v3; // edx
  unsigned int v4; // edi
  __int64 v5; // rax
  char *OwningThread; // rcx
  unsigned __int64 i; // rdi
  LPVOID pv; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v9; // [rsp+28h] [rbp-20h]
  __int64 v10; // [rsp+30h] [rbp-18h]
  __int64 v11; // [rsp+38h] [rbp-10h]
  LPVOID *p_pv; // [rsp+70h] [rbp+28h] BYREF

  EnterCriticalSection(lpCriticalSection);
  pv = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  p_pv = &pv;
  if ( lpCriticalSection[1].OwningThread )
  {
    v3 = 1;
    v4 = 0;
    do
    {
      if ( v4 >= HIDWORD(lpCriticalSection[1].DebugInfo) )
        break;
      v5 = 16LL * v4;
      OwningThread = (char *)lpCriticalSection[1].OwningThread;
      if ( *(_DWORD *)&OwningThread[v5] == 1 )
        v3 = CSimpleHashTable<unsigned __int64,Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>,CDefaultHashPolicy<unsigned __int64>,CDefaultKeyCompare<unsigned __int64>,CDefaultResizePolicy,CDefaultRehashPolicy>::s_EnumAdaptor<_lambda_a8024b8f1aa6fa5080f5dd5641512aaa_>(
               &p_pv,
               &OwningThread[v5 + 4],
               &OwningThread[v5 + 8]);
      ++v4;
    }
    while ( v3 );
  }
  CSimpleHashTable<unsigned long,Microsoft::WRL::ComPtr<CStreamWriterTimeoutManager::CTimerIdAndWriters>,CDefaultHashPolicy<unsigned long>,CDefaultKeyCompare<unsigned long>,CDefaultResizePolicy,CDefaultRehashPolicy>::RemoveAll(&lpCriticalSection[1]);
  LeaveCriticalSection(lpCriticalSection);
  v2 = (char *)pv;
  if ( pv )
  {
    for ( i = 0; i < v9; v2 = (char *)pv )
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(&v2[8 * i++]);
    CoTaskMemFree(v2);
  }
  CSimpleHashTable<unsigned long,Microsoft::WRL::ComPtr<CStreamWriterTimeoutManager::CTimerIdAndWriters>,CDefaultHashPolicy<unsigned long>,CDefaultKeyCompare<unsigned long>,CDefaultResizePolicy,CDefaultRehashPolicy>::RemoveAll(&lpCriticalSection[1]);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180047764  push    rbp
0x180047766  push    rbx
0x180047767  push    rsi
0x180047768  push    rdi
0x180047769  mov     rbp, rsp
0x18004776c  sub     rsp, 48h
0x180047770  mov     rbx, rcx
0x180047773  call    cs:__imp_EnterCriticalSection
0x180047779  mov     [rbp+pv], 0
0x180047781  mov     [rbp+var_20], 0
0x180047789  mov     [rbp+var_18], 0
0x180047791  mov     [rbp+var_10], 0
0x180047799  lea     rax, [rbp+pv]
0x18004779d  mov     [rbp+arg_0], rax
0x1800477a1  cmp     qword ptr [rbx+38h], 0
0x1800477a6  jnz     short loc_1800477DE
0x1800477a8  lea     rcx, [rbx+28h]
0x1800477ac  call    ?RemoveAll@?$CSimpleHashTable@KV?$ComPtr@VCTimerIdAndWriters@CStreamWriterTimeoutManager@@@WRL@Microsoft@@V?$CDefaultHashPolicy@K@@V?$CDefaultKeyCompare@K@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@QEAAXXZ; CSimpleHashTable<ulong,Microsoft::WRL::ComPtr<CStreamWriterTimeoutManager::CTimerIdAndWriters>,CDefaultHashPolicy<ulong>,CDefaultKeyCompare<ulong>,CDefaultResizePolicy,CDefaultRehashPolicy>::RemoveAll(void)
0x1800477b1  mov     rcx, rbx; lpCriticalSection
0x1800477b4  call    cs:__imp_LeaveCriticalSection
0x1800477ba  mov     rcx, [rbp+pv]
0x1800477be  test    rcx, rcx
0x1800477c1  jnz     short loc_18004781B
0x1800477c3  lea     rcx, [rbx+28h]
0x1800477c7  call    ?RemoveAll@?$CSimpleHashTable@KV?$ComPtr@VCTimerIdAndWriters@CStreamWriterTimeoutManager@@@WRL@Microsoft@@V?$CDefaultHashPolicy@K@@V?$CDefaultKeyCompare@K@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@QEAAXXZ; CSimpleHashTable<ulong,Microsoft::WRL::ComPtr<CStreamWriterTimeoutManager::CTimerIdAndWriters>,CDefaultHashPolicy<ulong>,CDefaultKeyCompare<ulong>,CDefaultResizePolicy,CDefaultRehashPolicy>::RemoveAll(void)
0x1800477cc  mov     rcx, rbx
0x1800477cf  add     rsp, 48h
0x1800477d3  pop     rdi
0x1800477d4  pop     rsi
0x1800477d5  pop     rbx
0x1800477d6  pop     rbp
0x1800477d7  jmp     cs:__imp_DeleteCriticalSection
0x1800477de  mov     edx, 1
0x1800477e3  xor     edi, edi
0x1800477e5  cmp     edi, [rbx+2Ch]
0x1800477e8  jnb     short loc_1800477A8
0x1800477ea  mov     eax, edi
0x1800477ec  shl     rax, 4
0x1800477f0  mov     rcx, [rbx+38h]
0x1800477f4  cmp     dword ptr [rax+rcx], 1
0x1800477f8  jnz     short loc_180047813
0x1800477fa  lea     r8, [rcx+8]
0x1800477fe  add     r8, rax
0x180047801  lea     rdx, [rcx+4]
0x180047805  add     rdx, rax
0x180047808  lea     rcx, [rbp+arg_0]
0x18004780c  call    ??$s_EnumAdaptor@V_lambda_a8024b8f1aa6fa5080f5dd5641512aaa_@@@?$CSimpleHashTable@_KV?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@V?$CDefaultHashPolicy@_K@@V?$CDefaultKeyCompare@_K@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@CAHPEBV_lambda_a8024b8f1aa6fa5080f5dd5641512aaa_@@AEB_KAEAV?$ComPtr@UICurrentWindowChangeListener@@@WRL@Microsoft@@@Z; CSimpleHashTable<unsigned __int64,Microsoft::WRL::ComPtr<ICurrentWindowChangeListener>,CDefaultHashPolicy<unsigned __int64>,CDefaultKeyCompare<unsigned __int64>,CDefaultResizePolicy,CDefaultRehashPolicy>::s_EnumAdaptor<_lambda_a8024b8f1aa6fa5080f5dd5641512aaa_>(_lambda_a8024b8f1aa6fa5080f5dd5641512aaa_ const *,unsigned __int64 const &,Microsoft::WRL::ComPtr<ICurrentWindowChangeListener> &)
0x180047811  mov     edx, eax
0x180047813  inc     edi
0x180047815  test    edx, edx
0x180047817  jnz     short loc_1800477E5
0x180047819  jmp     short loc_1800477A8
0x18004781b  xor     edi, edi
0x18004781d  cmp     [rbp+var_20], rdi
0x180047821  jbe     short loc_180047839
0x180047823  lea     rcx, [rcx+rdi*8]
0x180047827  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18004782c  inc     rdi
0x18004782f  mov     rcx, [rbp+pv]; pv
0x180047833  cmp     rdi, [rbp+var_20]
0x180047837  jb      short loc_180047823
0x180047839  call    cs:__imp_CoTaskMemFree
0x18004783f  jmp     short loc_1800477C3
```
