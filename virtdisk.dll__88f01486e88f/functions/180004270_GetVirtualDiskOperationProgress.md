# GetVirtualDiskOperationProgress

- ea: `0x180004270`
- end: `0x18000454c`
- name: `GetVirtualDiskOperationProgress`
- size: `732`
- prototype: `DWORD __stdcall(HANDLE VirtualDiskHandle, LPOVERLAPPED Overlapped, PVIRTUAL_DISK_PROGRESS Progress)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004270`
- `0x180005730`
- `0x1800063a8`
- `0x180006fac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000445c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000445c`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180004330`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000444c`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180004330`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000444c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004414`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004414`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004472`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004472`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000439d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000439d`

## pseudocode

```c
DWORD __stdcall GetVirtualDiskOperationProgress(
        HANDLE VirtualDiskHandle,
        LPOVERLAPPED Overlapped,
        PVIRTUAL_DISK_PROGRESS Progress)
{
  _QWORD *v6; // rcx
  DWORD v7; // ebx
  DWORD LastError; // eax
  unsigned __int64 EventW; // rax
  void *v10; // rbp
  DWORD v11; // esi
  DWORD NumberOfBytesTransferred; // [rsp+40h] [rbp-78h] BYREF
  LPOVERLAPPED InBuffer; // [rsp+48h] [rbp-70h] BYREF
  struct _OVERLAPPED Overlappeda; // [rsp+50h] [rbp-68h] BYREF
  __int128 OutBuffer; // [rsp+70h] [rbp-48h] BYREF

  InBuffer = 0;
  NumberOfBytesTransferred = 0;
  OutBuffer = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fd0a3c00299b3fdb8e4ab3ba33ee6bc8_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (char *)VirtualDiskHandle - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v7 = 6;
    goto LABEL_27;
  }
  if ( !Overlapped || !Progress )
  {
    v7 = 87;
    goto LABEL_27;
  }
  Progress->OperationStatus = 997;
  Progress->CurrentValue = 0;
  Progress->CompletionValue = 0;
  if ( GetOverlappedResult(VirtualDiskHandle, Overlapped, &NumberOfBytesTransferred, 0) )
  {
    Progress->OperationStatus = 0;
    v7 = 0;
    v6 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  LastError = GetLastError();
  if ( LastError != 996 )
  {
    Progress->OperationStatus = LastError;
    v7 = 0;
    v6 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  InBuffer = Overlapped;
  memset(&Overlappeda, 0, sizeof(Overlappeda));
  EventW = (unsigned __int64)CreateEventW(0, 1, 0, 0);
  v10 = (void *)EventW;
  if ( !EventW )
  {
    v11 = GetLastError();
    goto LABEL_20;
  }
  memset(&Overlappeda, 0, 24);
  Overlappeda.hEvent = (HANDLE)(EventW | 1);
  if ( DeviceIoControl(
         VirtualDiskHandle,
         0x2D1930u,
         &InBuffer,
         8u,
         &OutBuffer,
         0x10u,
         &NumberOfBytesTransferred,
         &Overlappeda) )
  {
    goto LABEL_18;
  }
  v11 = GetLastError();
  if ( v11 == 997 )
  {
    if ( !GetOverlappedResult(VirtualDiskHandle, &Overlappeda, &NumberOfBytesTransferred, 1) )
    {
      v11 = GetLastError();
      goto LABEL_19;
    }
LABEL_18:
    v11 = 0;
  }
LABEL_19:
  CloseHandle(v10);
LABEL_20:
  if ( v11 )
  {
    v7 = 0;
    Progress->CurrentValue = 0x68DB8BAC710CBLL;
    Progress->CompletionValue = 0x68DB8BAC710CBLL;
    v6 = WPP_GLOBAL_Control;
  }
  else if ( NumberOfBytesTransferred == 16 )
  {
    v7 = 0;
    *(_OWORD *)&Progress->CurrentValue = OutBuffer;
    v6 = WPP_GLOBAL_Control;
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    v7 = 13;
  }
LABEL_27:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_d(v6[2], 11, WPP_fd0a3c00299b3fdb8e4ab3ba33ee6bc8_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180004270  mov     r11, rsp
0x180004273  push    rbx
0x180004274  sub     rsp, 0B0h
0x18000427b  mov     rax, cs:__security_cookie
0x180004282  xor     rax, rsp
0x180004285  mov     [rsp+0B8h+var_38], rax
0x18000428d  mov     [r11-10h], rsi
0x180004291  xorps   xmm0, xmm0
0x180004294  mov     [r11-18h], rdi
0x180004298  mov     rsi, rdx
0x18000429b  mov     [r11-20h], r14
0x18000429f  mov     rdi, r8
0x1800042a2  mov     [r11-28h], r15
0x1800042a6  mov     rbx, rcx
0x1800042a9  xor     r15d, r15d
0x1800042ac  mov     [r11-70h], r15
0x1800042b0  mov     [r11-78h], r15d
0x1800042b4  movups  [rsp+0B8h+OutBuffer], xmm0
0x1800042b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042c0  lea     r14, WPP_GLOBAL_Control
0x1800042c7  cmp     rcx, r14
0x1800042ca  jz      short loc_1800042F4
0x1800042cc  test    byte ptr [rcx+1Ch], 20h
0x1800042d0  jz      short loc_1800042F4
0x1800042d2  cmp     byte ptr [rcx+19h], 4
0x1800042d6  jb      short loc_1800042F4
0x1800042d8  mov     rcx, [rcx+10h]
0x1800042dc  lea     r8, WPP_fd0a3c00299b3fdb8e4ab3ba33ee6bc8_Traceguids
0x1800042e3  mov     edx, 0Ah
0x1800042e8  call    WPP_SF_
0x1800042ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042f4  lea     rax, [rbx-1]
0x1800042f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800042fc  ja      loc_1800044E2
0x180004302  test    rsi, rsi
0x180004305  jz      loc_1800044DB
0x18000430b  test    rdi, rdi
0x18000430e  jz      loc_1800044DB
0x180004314  xor     r9d, r9d; bWait
0x180004317  mov     dword ptr [rdi], 3E5h
0x18000431d  lea     r8, [rsp+0B8h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180004322  mov     [rdi+8], r15
0x180004326  mov     rdx, rsi; lpOverlapped
0x180004329  mov     [rdi+10h], r15
0x18000432d  mov     rcx, rbx; hFile
0x180004330  call    cs:__imp_GetOverlappedResult
0x180004337  nop     dword ptr [rax+rax+00h]
0x18000433c  test    eax, eax
0x18000433e  jz      short loc_180004352
0x180004340  mov     [rdi], r15d
0x180004343  mov     ebx, r15d
0x180004346  mov     rcx, cs:WPP_GLOBAL_Control
0x18000434d  jmp     loc_1800044E7
0x180004352  call    cs:__imp_GetLastError
0x180004359  nop     dword ptr [rax+rax+00h]
0x18000435e  cmp     eax, 3E4h
0x180004363  jz      short loc_180004376
0x180004365  mov     [rdi], eax
0x180004367  mov     ebx, r15d
0x18000436a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004371  jmp     loc_1800044E7
0x180004376  xorps   xmm0, xmm0
0x180004379  mov     [rsp+0B8h+arg_18], rbp
0x180004381  xor     r9d, r9d; lpName
0x180004384  mov     [rsp+0B8h+InBuffer], rsi
0x180004389  xor     r8d, r8d; bInitialState
0x18000438c  mov     edx, 1; bManualReset
0x180004391  xor     ecx, ecx; lpEventAttributes
0x180004393  movups  xmmword ptr [rsp+0B8h+Overlapped.Internal], xmm0
0x180004398  movups  xmmword ptr [rsp+0B8h+Overlapped.10h], xmm0
0x18000439d  call    cs:__imp_CreateEventW
0x1800043a4  nop     dword ptr [rax+rax+00h]
0x1800043a9  mov     rbp, rax
0x1800043ac  test    rax, rax
0x1800043af  jnz     short loc_1800043C4
0x1800043b1  call    cs:__imp_GetLastError
0x1800043b8  nop     dword ptr [rax+rax+00h]
0x1800043bd  mov     esi, eax
0x1800043bf  jmp     loc_18000447E
0x1800043c4  or      rax, 1
0x1800043c8  mov     [rsp+0B8h+Overlapped.Internal], r15
0x1800043cd  mov     [rsp+0B8h+Overlapped.hEvent], rax
0x1800043d2  lea     r8, [rsp+0B8h+InBuffer]; lpInBuffer
0x1800043d7  lea     rax, [rsp+0B8h+Overlapped]
0x1800043dc  xorps   xmm0, xmm0
0x1800043df  mov     [rsp+0B8h+lpOverlapped], rax; lpOverlapped
0x1800043e4  mov     r9d, 8; nInBufferSize
0x1800043ea  lea     rax, [rsp+0B8h+NumberOfBytesTransferred]
0x1800043ef  mov     edx, 2D1930h; dwIoControlCode
0x1800043f4  mov     [rsp+0B8h+lpBytesReturned], rax; lpBytesReturned
0x1800043f9  mov     rcx, rbx; hDevice
0x1800043fc  lea     rax, [rsp+0B8h+OutBuffer]
0x180004401  mov     [rsp+0B8h+nOutBufferSize], 10h; nOutBufferSize
0x180004409  mov     [rsp+0B8h+lpOutBuffer], rax; lpOutBuffer
0x18000440e  movdqu  xmmword ptr [rsp+0B8h+Overlapped.InternalHigh], xmm0
0x180004414  call    cs:__imp_DeviceIoControl
0x18000441b  nop     dword ptr [rax+rax+00h]
0x180004420  test    eax, eax
0x180004422  jnz     short loc_18000446C
0x180004424  call    cs:__imp_GetLastError
0x18000442b  nop     dword ptr [rax+rax+00h]
0x180004430  mov     esi, eax
0x180004432  cmp     eax, 3E5h
0x180004437  jnz     short loc_18000446F
0x180004439  mov     r9d, 1; bWait
0x18000443f  lea     r8, [rsp+0B8h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180004444  lea     rdx, [rsp+0B8h+Overlapped]; lpOverlapped
0x180004449  mov     rcx, rbx; hFile
0x18000444c  call    cs:__imp_GetOverlappedResult
0x180004453  nop     dword ptr [rax+rax+00h]
0x180004458  test    eax, eax
0x18000445a  jnz     short loc_18000446C
0x18000445c  call    cs:__imp_GetLastError
0x180004463  nop     dword ptr [rax+rax+00h]
0x180004468  mov     esi, eax
0x18000446a  jmp     short loc_18000446F
0x18000446c  mov     esi, r15d
0x18000446f  mov     rcx, rbp; hObject
0x180004472  call    cs:__imp_CloseHandle
0x180004479  nop     dword ptr [rax+rax+00h]
0x18000447e  mov     rbp, [rsp+0B8h+arg_18]
0x180004486  test    esi, esi
0x180004488  jz      short loc_1800044A8
0x18000448a  mov     rax, 68DB8BAC710CBh
0x180004494  mov     ebx, r15d
0x180004497  mov     [rdi+8], rax
0x18000449b  mov     [rdi+10h], rax
0x18000449f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044a6  jmp     short loc_1800044E7
0x1800044a8  cmp     [rsp+0B8h+NumberOfBytesTransferred], 10h
0x1800044ad  jz      short loc_1800044BD
0x1800044af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044b6  mov     ebx, 0Dh
0x1800044bb  jmp     short loc_1800044E7
0x1800044bd  mov     rax, qword ptr [rsp+0B8h+OutBuffer+8]
0x1800044c2  mov     ebx, r15d
0x1800044c5  mov     [rdi+10h], rax
0x1800044c9  mov     rax, qword ptr [rsp+0B8h+OutBuffer]
0x1800044ce  mov     [rdi+8], rax
0x1800044d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044d9  jmp     short loc_1800044E7
0x1800044db  mov     ebx, 57h ; 'W'
0x1800044e0  jmp     short loc_1800044E7
0x1800044e2  mov     ebx, 6
0x1800044e7  mov     r15, [rsp+0B8h+var_28]
0x1800044ef  mov     rdi, [rsp+0B8h+var_18]
0x1800044f7  mov     rsi, [rsp+0B8h+var_10]
0x1800044ff  cmp     rcx, r14
0x180004502  mov     r14, [rsp+0B8h+var_20]
0x18000450a  jz      short loc_180004530
0x18000450c  test    byte ptr [rcx+1Ch], 20h
0x180004510  jz      short loc_180004530
0x180004512  cmp     byte ptr [rcx+19h], 4
0x180004516  jb      short loc_180004530
0x180004518  mov     rcx, [rcx+10h]
0x18000451c  lea     r8, WPP_fd0a3c00299b3fdb8e4ab3ba33ee6bc8_Traceguids
0x180004523  mov     edx, 0Bh
0x180004528  mov     r9d, ebx
0x18000452b  call    WPP_SF_d
0x180004530  mov     eax, ebx
0x180004532  mov     rcx, [rsp+0B8h+var_38]
0x18000453a  xor     rcx, rsp; StackCookie
0x18000453d  call    __security_check_cookie
0x180004542  add     rsp, 0B0h
0x180004549  pop     rbx
0x18000454a  retn
```
