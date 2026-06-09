# GetCurrentNetworkId

- ea: `0x140060a04`
- end: `0x140060c29`
- name: `GetCurrentNetworkId`
- size: `549`
- prototype: `__int64 __fastcall(unsigned __int16 **, enum DefPrnNetworkDescriptor *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14007ff1c`

## callees

- `0x1400190a4`
- `0x14005ff8c`
- `0x140060a04`

## import_xrefs

- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x140060a2c`
- `ntdll!RtlIsThreadWithinLoaderCallout` at `0x140060a2c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140060b58`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140060bef`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140060b58`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140060bef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140060ade`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140060ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060af2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060b83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060af2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060b2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140060b83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140060bb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140060bb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140060bc8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140060bc8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x140060bde`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x140060bde`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140060b1b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x140060b1b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140060b44`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140060b44`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140060a6e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140060a6e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140060a4a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140060a4a`

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
0x140060a04  push    rbp
0x140060a06  push    rbx
0x140060a07  push    rsi
0x140060a08  push    rdi
0x140060a09  push    r14
0x140060a0b  push    r15
0x140060a0d  lea     rbp, [rsp-2Fh]
0x140060a12  sub     rsp, 98h
0x140060a19  mov     r14, rdx
0x140060a1c  mov     qword ptr [rcx], 0
0x140060a23  mov     r15, rcx
0x140060a26  mov     dword ptr [rdx], 0
0x140060a2c  call    cs:__imp_RtlIsThreadWithinLoaderCallout
0x140060a33  nop     dword ptr [rax+rax+00h]
0x140060a38  test    al, al
0x140060a3a  jz      short loc_140060A46
0x140060a3c  mov     ebx, 490h
0x140060a41  jmp     loc_140060C16
0x140060a46  xor     edx, edx; dwCoInit
0x140060a48  xor     ecx, ecx; pvReserved
0x140060a4a  call    cs:__imp_CoInitializeEx
0x140060a51  nop     dword ptr [rax+rax+00h]
0x140060a56  test    eax, eax
0x140060a58  js      short loc_140060A7F
0x140060a5a  mov     rdx, r14; enum DefPrnNetworkDescriptor *
0x140060a5d  mov     rcx, r15; unsigned __int16 **
0x140060a60  call    ?GetCurrentNetworkIdInternal@@YAJPEAPEAGPEAW4DefPrnNetworkDescriptor@@@Z; GetCurrentNetworkIdInternal(ushort * *,DefPrnNetworkDescriptor *)
0x140060a65  mov     ecx, eax; int
0x140060a67  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x140060a6c  mov     ebx, eax
0x140060a6e  call    cs:__imp_CoUninitialize
0x140060a75  nop     dword ptr [rax+rax+00h]
0x140060a7a  jmp     loc_140060C16
0x140060a7f  cmp     eax, 80010106h
0x140060a84  jnz     loc_140060C0D
0x140060a8a  xorps   xmm0, xmm0
0x140060a8d  mov     qword ptr [rbp+57h+pcbe.Version], 3
0x140060a95  xor     r9d, r9d; lpName
0x140060a98  mov     qword ptr [rbp+57h+pcbe.Size], 48h ; 'H'
0x140060aa0  xor     r8d, r8d; bInitialState
0x140060aa3  mov     [rbp+57h+pcbe.Pool], 0
0x140060aab  xor     ecx, ecx; lpEventAttributes
0x140060aad  mov     [rbp+57h+pcbe.CleanupGroup], 0
0x140060ab5  movups  [rbp+57h+pv], xmm0
0x140060ab9  lea     edx, [r9+1]; bManualReset
0x140060abd  mov     [rbp+57h+pcbe.CleanupGroupCancelCallback], 0
0x140060ac5  movups  [rbp+57h+var_90], xmm0
0x140060ac9  mov     [rbp+57h+pcbe.FinalizationCallback], 0
0x140060ad1  movdqa  xmmword ptr [rbp+57h+pcbe.RaceDll], xmm0
0x140060ad6  mov     qword ptr [rbp+57h+pcbe.u], 0
0x140060ade  call    cs:__imp_CreateEventW
0x140060ae5  nop     dword ptr [rax+rax+00h]
0x140060aea  mov     rsi, rax
0x140060aed  test    rax, rax
0x140060af0  jnz     short loc_140060B08
0x140060af2  call    cs:__imp_GetLastError
0x140060af9  nop     dword ptr [rax+rax+00h]
0x140060afe  mov     ebx, eax
0x140060b00  test    eax, eax
0x140060b02  jnz     loc_140060C16
0x140060b08  lea     r8, [rbp+57h+pcbe]; pcbe
0x140060b0c  mov     qword ptr [rbp+57h+pv], rsi
0x140060b10  lea     rdx, [rbp+57h+pv]; pv
0x140060b14  lea     rcx, ?GetCurrentNetworkIdWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x140060b1b  call    cs:__imp_CreateThreadpoolWork
0x140060b22  nop     dword ptr [rax+rax+00h]
0x140060b27  mov     rdi, rax
0x140060b2a  test    rax, rax
0x140060b2d  jnz     short loc_140060B41
0x140060b2f  call    cs:__imp_GetLastError
0x140060b36  nop     dword ptr [rax+rax+00h]
0x140060b3b  mov     ebx, eax
0x140060b3d  test    eax, eax
0x140060b3f  jnz     short loc_140060BAC
0x140060b41  mov     rcx, rdi; pwk
0x140060b44  call    cs:__imp_SubmitThreadpoolWork
0x140060b4b  nop     dword ptr [rax+rax+00h]
0x140060b50  mov     edx, 3E8h; dwMilliseconds
0x140060b55  mov     rcx, rsi; hHandle
0x140060b58  call    cs:__imp_WaitForSingleObject
0x140060b5f  nop     dword ptr [rax+rax+00h]
0x140060b64  test    eax, eax
0x140060b66  jz      short loc_140060B95
0x140060b68  cmp     eax, 80h
0x140060b6d  jz      loc_140060C06
0x140060b73  cmp     eax, 102h
0x140060b78  jz      short loc_140060BD6
0x140060b7a  cmp     eax, 0FFFFFFFFh
0x140060b7d  jnz     loc_140060C06
0x140060b83  call    cs:__imp_GetLastError
0x140060b8a  nop     dword ptr [rax+rax+00h]
0x140060b8f  mov     ebx, eax
0x140060b91  test    eax, eax
0x140060b93  jnz     short loc_140060BAC
0x140060b95  mov     ecx, dword ptr [rbp+57h+pv+8]; int
0x140060b98  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x140060b9d  mov     ebx, eax
0x140060b9f  mov     rax, qword ptr [rbp+57h+var_90]
0x140060ba3  mov     [r15], rax
0x140060ba6  mov     eax, dword ptr [rbp+57h+var_90+8]
0x140060ba9  mov     [r14], eax
0x140060bac  test    rsi, rsi
0x140060baf  jz      short loc_140060BC0
0x140060bb1  mov     rcx, rsi; hObject
0x140060bb4  call    cs:__imp_CloseHandle
0x140060bbb  nop     dword ptr [rax+rax+00h]
0x140060bc0  test    rdi, rdi
0x140060bc3  jz      short loc_140060C16
0x140060bc5  mov     rcx, rdi; pwk
0x140060bc8  call    cs:__imp_CloseThreadpoolWork
0x140060bcf  nop     dword ptr [rax+rax+00h]
0x140060bd4  jmp     short loc_140060C16
0x140060bd6  mov     edx, 1; fCancelPendingCallbacks
0x140060bdb  mov     rcx, rdi; pwk
0x140060bde  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x140060be5  nop     dword ptr [rax+rax+00h]
0x140060bea  xor     edx, edx; dwMilliseconds
0x140060bec  mov     rcx, rsi; hHandle
0x140060bef  call    cs:__imp_WaitForSingleObject
0x140060bf6  nop     dword ptr [rax+rax+00h]
0x140060bfb  test    eax, eax
0x140060bfd  jz      short loc_140060B95
0x140060bff  mov     ebx, 5B4h
0x140060c04  jmp     short loc_140060BAC
0x140060c06  mov     ebx, 8000FFFFh
0x140060c0b  jmp     short loc_140060BAC
0x140060c0d  mov     ecx, eax; int
0x140060c0f  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x140060c14  mov     ebx, eax
0x140060c16  mov     eax, ebx
0x140060c18  add     rsp, 98h
0x140060c1f  pop     r15
0x140060c21  pop     r14
0x140060c23  pop     rdi
0x140060c24  pop     rsi
0x140060c25  pop     rbx
0x140060c26  pop     rbp
0x140060c27  retn
```
