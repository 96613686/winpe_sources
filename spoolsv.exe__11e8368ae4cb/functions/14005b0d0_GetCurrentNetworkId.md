# GetCurrentNetworkId

- ea: `0x14005b0d0`
- end: `0x14005b298`
- name: `GetCurrentNetworkId`
- size: `456`
- prototype: `__int64 __fastcall(unsigned __int16 **, enum DefPrnNetworkDescriptor *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140078a70`

## callees

- `0x140017bc0`
- `0x14005a6f8`
- `0x14005b0d0`

## import_xrefs

- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x14005b0f8`
- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x14005b0f8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14005b1f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14005b265`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14005b1f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14005b265`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14005b198`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14005b198`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b1a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b1d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b1a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b1d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005b211`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005b23c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005b23c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x14005b24a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x14005b24a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x14005b25a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x14005b25a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14005b1c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14005b1c9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14005b1e6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x14005b1e6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005b12e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14005b12e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14005b110`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14005b110`

## pseudocode

```c
__int64 __fastcall GetCurrentNetworkId(unsigned __int16 **a1, enum DefPrnNetworkDescriptor *a2)
{
  DWORD LastError; // ebx
  HRESULT v5; // eax
  int CurrentNetworkIdInternal; // eax
  HANDLE EventW; // rsi
  struct _TP_WORK *v8; // rdi
  DWORD v9; // eax
  __int128 pv; // [rsp+20h] [rbp-49h] BYREF
  __int128 v12; // [rsp+30h] [rbp-39h]
  _TP_CALLBACK_ENVIRON_V3 pcbe; // [rsp+40h] [rbp-29h] BYREF

  *a1 = 0;
  *(_DWORD *)a2 = 0;
  if ( RtlIsThreadWithinLoaderCallout() )
    return 1168;
  v5 = CoInitializeEx(0, 0);
  if ( v5 >= 0 )
  {
    CurrentNetworkIdInternal = GetCurrentNetworkIdInternal(a1, a2);
    LastError = WIN32_FROM_HRESULT(CurrentNetworkIdInternal);
    CoUninitialize();
    return LastError;
  }
  if ( v5 != -2147417850 )
    return WIN32_FROM_HRESULT(v5);
  *(_QWORD *)&pcbe.Version = 3;
  *(_QWORD *)&pcbe.Size = 72;
  memset(&pcbe.Pool, 0, 56);
  pv = 0;
  v12 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW || (LastError = GetLastError()) == 0 )
  {
    *(_QWORD *)&pv = EventW;
    v8 = CreateThreadpoolWork(GetCurrentNetworkIdWorker, &pv, &pcbe);
    if ( !v8 )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_16;
    }
    SubmitThreadpoolWork(v8);
    v9 = WaitForSingleObject(EventW, 0x3E8u);
    if ( v9 )
    {
      if ( v9 == 128 )
        goto LABEL_22;
      if ( v9 == 258 )
      {
        WaitForThreadpoolWorkCallbacks(v8, 1);
        if ( WaitForSingleObject(EventW, 0) )
        {
          LastError = 1460;
          goto LABEL_16;
        }
        goto LABEL_15;
      }
      if ( v9 != -1 )
      {
LABEL_22:
        LastError = -2147418113;
        goto LABEL_16;
      }
      LastError = GetLastError();
      if ( LastError )
      {
LABEL_16:
        if ( EventW )
          CloseHandle(EventW);
        if ( v8 )
          CloseThreadpoolWork(v8);
        return LastError;
      }
    }
LABEL_15:
    LastError = WIN32_FROM_HRESULT(SDWORD2(pv));
    *a1 = (unsigned __int16 *)v12;
    *(_DWORD *)a2 = DWORD2(v12);
    goto LABEL_16;
  }
  return LastError;
}

```

## disassembly

```asm
0x14005b0d0  push    rbp
0x14005b0d2  push    rbx
0x14005b0d3  push    rsi
0x14005b0d4  push    rdi
0x14005b0d5  push    r14
0x14005b0d7  push    r15
0x14005b0d9  lea     rbp, [rsp-2Fh]
0x14005b0de  sub     rsp, 98h
0x14005b0e5  mov     r14, rdx
0x14005b0e8  mov     qword ptr [rcx], 0
0x14005b0ef  mov     r15, rcx
0x14005b0f2  mov     dword ptr [rdx], 0
0x14005b0f8  call    cs:__imp_RtlIsThreadWithinLoaderCallout
0x14005b0fe  test    al, al
0x14005b100  jz      short loc_14005B10C
0x14005b102  mov     ebx, 490h
0x14005b107  jmp     loc_14005B286
0x14005b10c  xor     edx, edx; dwCoInit
0x14005b10e  xor     ecx, ecx; pvReserved
0x14005b110  call    cs:__imp_CoInitializeEx
0x14005b116  test    eax, eax
0x14005b118  js      short loc_14005B139
0x14005b11a  mov     rdx, r14; enum DefPrnNetworkDescriptor *
0x14005b11d  mov     rcx, r15; unsigned __int16 **
0x14005b120  call    ?GetCurrentNetworkIdInternal@@YAJPEAPEAGPEAW4DefPrnNetworkDescriptor@@@Z; GetCurrentNetworkIdInternal(ushort * *,DefPrnNetworkDescriptor *)
0x14005b125  mov     ecx, eax; int
0x14005b127  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x14005b12c  mov     ebx, eax
0x14005b12e  call    cs:__imp_CoUninitialize
0x14005b134  jmp     loc_14005B286
0x14005b139  cmp     eax, 80010106h
0x14005b13e  jnz     loc_14005B27D
0x14005b144  xorps   xmm0, xmm0
0x14005b147  mov     qword ptr [rbp+57h+pcbe.Version], 3
0x14005b14f  xor     r9d, r9d; lpName
0x14005b152  mov     qword ptr [rbp+57h+pcbe.Size], 48h ; 'H'
0x14005b15a  xor     r8d, r8d; bInitialState
0x14005b15d  mov     [rbp+57h+pcbe.Pool], 0
0x14005b165  xor     ecx, ecx; lpEventAttributes
0x14005b167  mov     [rbp+57h+pcbe.CleanupGroup], 0
0x14005b16f  movups  [rbp+57h+pv], xmm0
0x14005b173  lea     edx, [r9+1]; bManualReset
0x14005b177  mov     [rbp+57h+pcbe.CleanupGroupCancelCallback], 0
0x14005b17f  movups  [rbp+57h+var_90], xmm0
0x14005b183  mov     [rbp+57h+pcbe.FinalizationCallback], 0
0x14005b18b  movdqa  xmmword ptr [rbp+57h+pcbe.RaceDll], xmm0
0x14005b190  mov     qword ptr [rbp+57h+pcbe.u], 0
0x14005b198  call    cs:__imp_CreateEventW
0x14005b19e  mov     rsi, rax
0x14005b1a1  test    rax, rax
0x14005b1a4  jnz     short loc_14005B1B6
0x14005b1a6  call    cs:__imp_GetLastError
0x14005b1ac  mov     ebx, eax
0x14005b1ae  test    eax, eax
0x14005b1b0  jnz     loc_14005B286
0x14005b1b6  lea     r8, [rbp+57h+pcbe]; pcbe
0x14005b1ba  mov     qword ptr [rbp+57h+pv], rsi
0x14005b1be  lea     rdx, [rbp+57h+pv]; pv
0x14005b1c2  lea     rcx, ?GetCurrentNetworkIdWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x14005b1c9  call    cs:__imp_CreateThreadpoolWork
0x14005b1cf  mov     rdi, rax
0x14005b1d2  test    rax, rax
0x14005b1d5  jnz     short loc_14005B1E3
0x14005b1d7  call    cs:__imp_GetLastError
0x14005b1dd  mov     ebx, eax
0x14005b1df  test    eax, eax
0x14005b1e1  jnz     short loc_14005B234
0x14005b1e3  mov     rcx, rdi; pwk
0x14005b1e6  call    cs:__imp_SubmitThreadpoolWork
0x14005b1ec  mov     edx, 3E8h; dwMilliseconds
0x14005b1f1  mov     rcx, rsi; hHandle
0x14005b1f4  call    cs:__imp_WaitForSingleObject
0x14005b1fa  test    eax, eax
0x14005b1fc  jz      short loc_14005B21D
0x14005b1fe  cmp     eax, 80h
0x14005b203  jz      short loc_14005B276
0x14005b205  cmp     eax, 102h
0x14005b20a  jz      short loc_14005B252
0x14005b20c  cmp     eax, 0FFFFFFFFh
0x14005b20f  jnz     short loc_14005B276
0x14005b211  call    cs:__imp_GetLastError
0x14005b217  mov     ebx, eax
0x14005b219  test    eax, eax
0x14005b21b  jnz     short loc_14005B234
0x14005b21d  mov     ecx, dword ptr [rbp+57h+pv+8]; int
0x14005b220  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x14005b225  mov     ebx, eax
0x14005b227  mov     rax, qword ptr [rbp+57h+var_90]
0x14005b22b  mov     [r15], rax
0x14005b22e  mov     eax, dword ptr [rbp+57h+var_90+8]
0x14005b231  mov     [r14], eax
0x14005b234  test    rsi, rsi
0x14005b237  jz      short loc_14005B242
0x14005b239  mov     rcx, rsi; hObject
0x14005b23c  call    cs:__imp_CloseHandle
0x14005b242  test    rdi, rdi
0x14005b245  jz      short loc_14005B286
0x14005b247  mov     rcx, rdi; pwk
0x14005b24a  call    cs:__imp_CloseThreadpoolWork
0x14005b250  jmp     short loc_14005B286
0x14005b252  mov     edx, 1; fCancelPendingCallbacks
0x14005b257  mov     rcx, rdi; pwk
0x14005b25a  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x14005b260  xor     edx, edx; dwMilliseconds
0x14005b262  mov     rcx, rsi; hHandle
0x14005b265  call    cs:__imp_WaitForSingleObject
0x14005b26b  test    eax, eax
0x14005b26d  jz      short loc_14005B21D
0x14005b26f  mov     ebx, 5B4h
0x14005b274  jmp     short loc_14005B234
0x14005b276  mov     ebx, 8000FFFFh
0x14005b27b  jmp     short loc_14005B234
0x14005b27d  mov     ecx, eax; int
0x14005b27f  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x14005b284  mov     ebx, eax
0x14005b286  mov     eax, ebx
0x14005b288  add     rsp, 98h
0x14005b28f  pop     r15
0x14005b291  pop     r14
0x14005b293  pop     rdi
0x14005b294  pop     rsi
0x14005b295  pop     rbx
0x14005b296  pop     rbp
0x14005b297  retn
```
