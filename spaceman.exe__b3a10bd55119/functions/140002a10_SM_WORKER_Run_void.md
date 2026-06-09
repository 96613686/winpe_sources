# SM_WORKER::Run(void)

- ea: `0x140002a10`
- end: `0x140002c15`
- name: `?Run@SM_WORKER@@QEAAXXZ`
- size: `517`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, __int64, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400037dc`

## callees

- `0x140001008`
- `0x1400010b0`
- `0x14000262c`
- `0x140002a10`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140002b7a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x140002b7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002b2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002b50`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002b2e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002b50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002bbb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140002a7d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140002a7d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140002b39`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140002b39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140002b26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140002b8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140002bb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140002b26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140002b8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140002bb5`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140002b03`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140002b03`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140002ad3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140002ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002b61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002b61`

## pseudocode

```c
void __fastcall SM_WORKER::Run(LPCRITICAL_SECTION lpCriticalSection, __int64 a2, int a3, int a4)
{
  BOOL OverlappedResult; // edi
  struct _SU_WORK_OBJECT *v6; // rsi
  DWORD nOutBufferSize; // edi
  SIZE_T i; // rdx
  _DWORD *v9; // rbx
  DWORD LastError; // eax
  int v11; // r8d
  int v12; // r9d
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-20h] BYREF
  DWORD BytesReturned; // [rsp+98h] [rbp+38h] BYREF
  const char *v15; // [rsp+A0h] [rbp+40h] BYREF
  const char *v16; // [rsp+A8h] [rbp+48h] BYREF

  if ( (unsigned int)dword_140014048 > 5 )
  {
    BytesReturned = 193;
    v15 = "SM_WORKER::Run";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)lpCriticalSection,
      (unsigned int)byte_14001083B,
      a3,
      a4,
      (__int64)&v15,
      (__int64)&BytesReturned);
  }
  while ( 2 )
  {
    BytesReturned = 0;
    memset(&Overlapped, 0, sizeof(Overlapped));
    Overlapped.hEvent = CreateEventW(0, 0, 0, 0);
    if ( !Overlapped.hEvent )
    {
      OverlappedResult = 0;
      v6 = 0;
      goto LABEL_14;
    }
    v6 = 0;
    nOutBufferSize = 96;
    for ( i = 148; ; i = nOutBufferSize + 52 )
    {
      v9 = LocalAlloc(0, i);
      if ( !v9 )
      {
        SetLastError(0x5AAu);
LABEL_13:
        OverlappedResult = 0;
        goto LABEL_14;
      }
      OverlappedResult = DeviceIoControl(
                           Spaceport,
                           0xE7180Cu,
                           0,
                           0,
                           v9 + 13,
                           nOutBufferSize,
                           &BytesReturned,
                           &Overlapped);
      if ( OverlappedResult )
        break;
      if ( GetLastError() == 997 )
      {
        OverlappedResult = GetOverlappedResult(Spaceport, &Overlapped, &BytesReturned, 1);
        if ( OverlappedResult )
          break;
      }
      if ( GetLastError() != 234 )
      {
        LocalFree(v9);
        goto LABEL_13;
      }
      nOutBufferSize = v9[14];
      LocalFree(v9);
      SetLastError(0);
    }
    v6 = (struct _SU_WORK_OBJECT *)v9;
    *(_QWORD *)v9 = 0x535041434557524BLL;
    v9[12] = v9[15];
LABEL_14:
    if ( Overlapped.hEvent )
      CloseHandle(Overlapped.hEvent);
    if ( OverlappedResult )
    {
      SM_WORKER::Insert(lpCriticalSection, v6);
      SubmitThreadpoolWork((PTP_WORK)lpCriticalSection[1].OwningThread);
      continue;
    }
    break;
  }
  if ( v6 )
    LocalFree(v6);
  LastError = GetLastError();
  if ( (unsigned int)dword_140014048 > 2 )
  {
    BytesReturned = LastError;
    LODWORD(v15) = 216;
    v16 = "SM_WORKER::Run";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      dword_140014048,
      (unsigned int)byte_1400108CB,
      v11,
      v12,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&BytesReturned);
  }
}

```

## disassembly

```asm
0x140002a10  mov     [rsp-28h+arg_0], rbx
0x140002a15  push    rbp
0x140002a16  push    rsi
0x140002a17  push    rdi
0x140002a18  push    r14
0x140002a1a  push    r15
0x140002a1c  mov     rbp, rsp
0x140002a1f  sub     rsp, 60h
0x140002a23  mov     eax, cs:dword_140014048
0x140002a29  lea     r15, aSmWorkerRun; "SM_WORKER::Run"
0x140002a30  mov     r14, rcx
0x140002a33  cmp     eax, 5
0x140002a36  jbe     short loc_140002A61
0x140002a38  lea     rax, [rbp+BytesReturned]
0x140002a3c  mov     [rbp+BytesReturned], 0C1h
0x140002a43  mov     qword ptr [rsp+60h+nOutBufferSize], rax
0x140002a48  lea     rdx, byte_14001083B
0x140002a4f  lea     rax, [rbp+arg_10]
0x140002a53  mov     [rbp+arg_10], r15
0x140002a57  mov     [rsp+60h+lpOutBuffer], rax
0x140002a5c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140002a61  xorps   xmm0, xmm0
0x140002a64  mov     [rbp+BytesReturned], 0
0x140002a6b  xor     r9d, r9d; lpName
0x140002a6e  xor     r8d, r8d; bInitialState
0x140002a71  xor     edx, edx; bManualReset
0x140002a73  xor     ecx, ecx; lpEventAttributes
0x140002a75  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x140002a79  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x140002a7d  call    cs:__imp_CreateEventW
0x140002a83  mov     [rbp+Overlapped.hEvent], rax
0x140002a87  test    rax, rax
0x140002a8a  jnz     short loc_140002A95
0x140002a8c  xor     edi, edi
0x140002a8e  xor     esi, esi
0x140002a90  jmp     loc_140002B58
0x140002a95  xor     esi, esi
0x140002a97  lea     edi, [rsi+60h]
0x140002a9a  lea     edx, [rdi+34h]
0x140002a9d  jmp     loc_140002B37
0x140002aa2  lea     rax, [rbp+Overlapped]
0x140002aa6  xor     r9d, r9d; nInBufferSize
0x140002aa9  mov     [rsp+60h+lpOverlapped], rax; lpOverlapped
0x140002aae  lea     rcx, [rbx+34h]
0x140002ab2  lea     rax, [rbp+BytesReturned]
0x140002ab6  xor     r8d, r8d; lpInBuffer
0x140002ab9  mov     [rsp+60h+lpBytesReturned], rax; lpBytesReturned
0x140002abe  mov     edx, 0E7180Ch; dwIoControlCode
0x140002ac3  mov     [rsp+60h+nOutBufferSize], edi; nOutBufferSize
0x140002ac7  mov     [rsp+60h+lpOutBuffer], rcx; lpOutBuffer
0x140002acc  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x140002ad3  call    cs:__imp_DeviceIoControl
0x140002ad9  mov     edi, eax
0x140002adb  test    eax, eax
0x140002add  jnz     loc_140002B95
0x140002ae3  call    cs:__imp_GetLastError
0x140002ae9  cmp     eax, 3E5h
0x140002aee  jnz     short loc_140002B13
0x140002af0  mov     rcx, cs:?Spaceport@@3PEAXEA; hFile
0x140002af7  lea     r9d, [rdi+1]; bWait
0x140002afb  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x140002aff  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x140002b03  call    cs:__imp_GetOverlappedResult
0x140002b09  mov     edi, eax
0x140002b0b  test    eax, eax
0x140002b0d  jnz     loc_140002B95
0x140002b13  call    cs:__imp_GetLastError
0x140002b19  cmp     eax, 0EAh
0x140002b1e  jnz     short loc_140002B85
0x140002b20  mov     edi, [rbx+38h]
0x140002b23  mov     rcx, rbx; hMem
0x140002b26  call    cs:__imp_LocalFree
0x140002b2c  xor     ecx, ecx; dwErrCode
0x140002b2e  call    cs:__imp_SetLastError
0x140002b34  lea     edx, [rdi+34h]; uBytes
0x140002b37  xor     ecx, ecx; uFlags
0x140002b39  call    cs:__imp_LocalAlloc
0x140002b3f  mov     rbx, rax
0x140002b42  test    rax, rax
0x140002b45  jnz     loc_140002AA2
0x140002b4b  mov     ecx, 5AAh; dwErrCode
0x140002b50  call    cs:__imp_SetLastError
0x140002b56  xor     edi, edi
0x140002b58  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x140002b5c  test    rcx, rcx
0x140002b5f  jz      short loc_140002B67
0x140002b61  call    cs:__imp_CloseHandle
0x140002b67  test    edi, edi
0x140002b69  jz      short loc_140002BAD
0x140002b6b  mov     rdx, rsi; struct _SU_WORK_OBJECT *
0x140002b6e  mov     rcx, r14; lpCriticalSection
0x140002b71  call    ?Insert@SM_WORKER@@QEAAXPEAU_SU_WORK_OBJECT@@@Z; SM_WORKER::Insert(_SU_WORK_OBJECT *)
0x140002b76  mov     rcx, [r14+38h]; pwk
0x140002b7a  call    cs:__imp_SubmitThreadpoolWork
0x140002b80  jmp     loc_140002A61
0x140002b85  test    rbx, rbx
0x140002b88  jz      short loc_140002B56
0x140002b8a  mov     rcx, rbx; hMem
0x140002b8d  call    cs:__imp_LocalFree
0x140002b93  jmp     short loc_140002B56
0x140002b95  mov     rax, 535041434557524Bh
0x140002b9f  mov     rsi, rbx
0x140002ba2  mov     [rbx], rax
0x140002ba5  mov     eax, [rbx+3Ch]
0x140002ba8  mov     [rbx+30h], eax
0x140002bab  jmp     short loc_140002B58
0x140002bad  test    rsi, rsi
0x140002bb0  jz      short loc_140002BBB
0x140002bb2  mov     rcx, rsi; hMem
0x140002bb5  call    cs:__imp_LocalFree
0x140002bbb  call    cs:__imp_GetLastError
0x140002bc1  mov     ecx, cs:dword_140014048
0x140002bc7  cmp     ecx, 2
0x140002bca  jbe     short loc_140002C01
0x140002bcc  mov     [rbp+BytesReturned], eax
0x140002bcf  lea     rdx, byte_1400108CB
0x140002bd6  lea     rax, [rbp+BytesReturned]
0x140002bda  mov     dword ptr [rbp+arg_10], 0D8h
0x140002be1  mov     [rsp+60h+lpBytesReturned], rax
0x140002be6  lea     rax, [rbp+arg_10]
0x140002bea  mov     qword ptr [rsp+60h+nOutBufferSize], rax
0x140002bef  lea     rax, [rbp+arg_18]
0x140002bf3  mov     [rsp+60h+lpOutBuffer], rax
0x140002bf8  mov     [rbp+arg_18], r15
0x140002bfc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140002c01  mov     rbx, [rsp+60h+arg_0]
0x140002c09  add     rsp, 60h
0x140002c0d  pop     r15
0x140002c0f  pop     r14
0x140002c11  pop     rdi
0x140002c12  pop     rsi
0x140002c13  pop     rbp
0x140002c14  retn
```
