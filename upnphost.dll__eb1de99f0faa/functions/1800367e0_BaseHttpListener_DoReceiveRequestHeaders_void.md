# BaseHttpListener::DoReceiveRequestHeaders(void)

- ea: `0x1800367e0`
- end: `0x180036dde`
- name: `?DoReceiveRequestHeaders@BaseHttpListener@@AEAAKXZ`
- size: `1534`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180051200`

## callees

- `0x180029d90`
- `0x1800367e0`
- `0x180036de4`
- `0x180038ce4`
- `0x180039a84`
- `0x18003ae80`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036afe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036b3d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036c3a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036afe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036b3d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180036c3a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800368fc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180036b07`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800368fc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180036b07`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800368da`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800368da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036855`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036855`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800369e7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800369e7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800368ba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180036d36`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800368ba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180036d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036c49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036cc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036c49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036cc1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180036c12`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180036c12`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180036a05`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180036a05`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180036d13`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180036d13`

## pseudocode

```c
__int64 __fastcall BaseHttpListener::DoReceiveRequestHeaders(HANDLE *this)
{
  DWORD v2; // ebx
  struct _HTTP_REQUEST_V2 *v3; // rsi
  struct _HTTP_REQUEST_V2 *v4; // r14
  DWORD v5; // r12d
  int v6; // r13d
  HTTP_REQUEST_ID RequestId; // r15
  struct _HTTP_REQUEST_V2 *v8; // rax
  STRSAFE_PCNZWCH v9; // rcx
  HANDLE v10; // r8
  int v11; // eax
  struct _HTTP_REQUEST_V2 *v12; // rax
  int v13; // eax
  HANDLE v15; // rcx
  signed int v16; // eax
  STRSAFE_PCNZWCH v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  signed int LastError; // eax
  HANDLE hEvent[2]; // [rsp+40h] [rbp-38h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-28h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+C0h] [rbp+48h] BYREF

  NumberOfBytesTransferred = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  *(_OWORD *)hEvent = 0;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
  hEvent[0] = this[39];
  hEvent[1] = CreateEventW(0, 1, 0, 0);
  if ( hEvent[1] )
  {
    v2 = 0;
    v3 = 0;
    v4 = 0;
    v5 = 0;
    v6 = 0;
    RequestId = 0;
    while ( 1 )
    {
      if ( *((_DWORD *)this + 27) || WaitForSingleObject(this[39], 0) != 258 )
        goto LABEL_62;
      memset(&Overlapped, 0, sizeof(Overlapped));
      if ( !ResetEvent(hEvent[1]) )
      {
        LastError = GetLastError();
        v2 = LastError;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        {
          goto LABEL_62;
        }
        if ( LastError > 0 )
          v19 = (unsigned __int16)LastError | 0x80070000;
        else
          v19 = (unsigned int)LastError;
        v18 = 30;
        goto LABEL_85;
      }
      Overlapped.hEvent = hEvent[1];
      if ( !v3 )
      {
        v8 = (struct _HTTP_REQUEST_V2 *)malloc(0xB60u);
        v4 = v8;
        if ( !v8 )
        {
          BaseHttpListener::DecrThreadCount(this);
          v15 = hEvent[1];
          *((_DWORD *)this + 32) = 0;
          if ( v15 )
            CloseHandle(v15);
          return 8;
        }
        v5 = 2912;
        v3 = v8;
      }
      memset_0(v3, 0, v5);
      v2 = ((__int64 (__fastcall *)(HANDLE, HTTP_REQUEST_ID, _QWORD, struct _HTTP_REQUEST_V2 *, DWORD, DWORD *, struct _OVERLAPPED *))this[12])(
             this[15],
             RequestId,
             0,
             v3,
             v5,
             &NumberOfBytesTransferred,
             &Overlapped);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v2);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v9 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x100) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v9 + 2), 32, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, NumberOfBytesTransferred);
          v9 = WPP_GLOBAL_Control;
        }
      }
      if ( v2 != 997 && v2 )
        goto LABEL_39;
      if ( WaitForMultipleObjectsEx(2u, hEvent, 0, 0xFFFFFFFF, 0) != 1 )
      {
        if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
        }
        if ( !CancelIoEx(this[15], &Overlapped) && GetLastError() == 1168
          || !WaitForSingleObject(hEvent[1], 0xFFFFFFFF)
          || WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
        {
          goto LABEL_62;
        }
        v16 = GetLastError();
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        v17 = WPP_GLOBAL_Control;
        v18 = 36;
        v19 = (unsigned int)v16;
LABEL_85:
        WPP_SF_d(*((_QWORD *)v17 + 2), v18, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v19);
        goto LABEL_62;
      }
      if ( GetOverlappedResult(this[15], &Overlapped, &NumberOfBytesTransferred, 0) )
        v2 = 0;
      else
        v2 = GetLastError();
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v2);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v9 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x100) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v9 + 2), 34, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, NumberOfBytesTransferred);
          v9 = WPP_GLOBAL_Control;
        }
      }
      if ( v2 )
      {
LABEL_39:
        switch ( v2 )
        {
          case 0xEAu:
            v5 = NumberOfBytesTransferred;
            *((_DWORD *)this + 74) = 0;
            RequestId = v3->RequestId;
            free(v4);
            v12 = (struct _HTTP_REQUEST_V2 *)malloc(v5);
            v4 = v12;
            if ( !v12 )
            {
              v2 = 8;
              v3 = 0;
LABEL_62:
              *((_DWORD *)this + 74) = 0;
              if ( v3 )
                free(v3);
              if ( hEvent[1] )
              {
                CloseHandle(hEvent[1]);
                hEvent[1] = 0;
              }
              *((_DWORD *)this + 32) = 0;
              BaseHttpListener::DecrThreadCount(this);
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
              }
              return v2;
            }
            v3 = v12;
            break;
          case 0x4CDu:
            if ( RequestId )
            {
              RequestId = 0;
              if ( v4 )
              {
                free(v4);
                v9 = WPP_GLOBAL_Control;
              }
              v3 = 0;
              if ( v9 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v9[14] & 1) != 0 )
                WPP_SF_d(*((_QWORD *)v9 + 2), 38, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, 1229);
              break;
            }
            break;
          case 0x3E3u:
          case 6u:
            goto LABEL_62;
          case 0x45Au:
            if ( v9 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v9[14] & 1) != 0 )
              WPP_SF_(*((_QWORD *)v9 + 2), 39, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
            v6 = 1;
            break;
          default:
            if ( v9 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v9[14] & 1) != 0 )
              WPP_SF_d(*((_QWORD *)v9 + 2), 40, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v2);
            v13 = *((_DWORD *)this + 74);
            if ( v13 == 5 )
              goto LABEL_62;
            *((_DWORD *)this + 74) = v13 + 1;
            Sleep(0xAu);
            break;
        }
      }
      else
      {
        v10 = this[15];
        *((_DWORD *)this + 74) = 0;
        v11 = BaseHttpListener::HandleHTTPHeader((BaseHttpListener *)this, v3, v10);
        if ( v11 < 0 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
            (unsigned int)v11);
        RequestId = 0;
        v3 = 0;
      }
      if ( v6 )
        goto LABEL_62;
    }
  }
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
  return 8;
}

```

## disassembly

```asm
0x1800367e0  push    rbp
0x1800367e2  push    rbx
0x1800367e3  push    rsi
0x1800367e4  push    rdi
0x1800367e5  push    r12
0x1800367e7  push    r13
0x1800367e9  push    r14
0x1800367eb  push    r15
0x1800367ed  mov     rbp, rsp
0x1800367f0  sub     rsp, 78h
0x1800367f4  xorps   xmm0, xmm0
0x1800367f7  mov     [rbp+NumberOfBytesTransferred], 0
0x1800367fe  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x180036802  mov     rdi, rcx
0x180036805  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180036809  movups  xmmword ptr [rbp+hEvent], xmm0
0x18003680d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036814  lea     rbx, WPP_GLOBAL_Control
0x18003681b  cmp     rcx, rbx
0x18003681e  jz      short loc_18003683E
0x180036820  test    dword ptr [rcx+1Ch], 100h
0x180036827  jz      short loc_18003683E
0x180036829  mov     rcx, [rcx+10h]
0x18003682d  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180036834  mov     edx, 1Ch
0x180036839  call    WPP_SF_
0x18003683e  mov     rax, [rdi+138h]
0x180036845  xor     r9d, r9d; lpName
0x180036848  xor     r8d, r8d; bInitialState
0x18003684b  mov     [rbp+hEvent], rax
0x18003684f  xor     ecx, ecx; lpEventAttributes
0x180036851  lea     edx, [r9+1]; bManualReset
0x180036855  call    cs:__imp_CreateEventW
0x18003685b  mov     [rbp+hEvent+8], rax
0x18003685f  test    rax, rax
0x180036862  jnz     short loc_180036896
0x180036864  mov     rcx, cs:WPP_GLOBAL_Control
0x18003686b  cmp     rcx, rbx
0x18003686e  jz      loc_180036CC7
0x180036874  test    byte ptr [rcx+1Ch], 1
0x180036878  jz      loc_180036CC7
0x18003687e  mov     rcx, [rcx+10h]
0x180036882  lea     edx, [rax+1Dh]
0x180036885  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18003688c  call    WPP_SF_
0x180036891  jmp     loc_180036CC7
0x180036896  xor     ebx, ebx
0x180036898  xor     esi, esi
0x18003689a  xor     r14d, r14d
0x18003689d  xor     r12d, r12d
0x1800368a0  xor     r13d, r13d
0x1800368a3  xor     r15d, r15d
0x1800368a6  mov     eax, [rdi+6Ch]
0x1800368a9  test    eax, eax
0x1800368ab  jnz     loc_180036C21
0x1800368b1  mov     rcx, [rdi+138h]; hHandle
0x1800368b8  xor     edx, edx; dwMilliseconds
0x1800368ba  call    cs:__imp_WaitForSingleObject
0x1800368c0  cmp     eax, 102h
0x1800368c5  jnz     loc_180036C21
0x1800368cb  mov     rcx, [rbp+hEvent+8]; hEvent
0x1800368cf  xorps   xmm0, xmm0
0x1800368d2  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x1800368d6  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x1800368da  call    cs:__imp_ResetEvent
0x1800368e0  test    eax, eax
0x1800368e2  jz      loc_180036D97
0x1800368e8  mov     rax, [rbp+hEvent+8]
0x1800368ec  mov     [rbp+Overlapped.hEvent], rax
0x1800368f0  test    rsi, rsi
0x1800368f3  jnz     short loc_180036914
0x1800368f5  mov     ebx, 0B60h
0x1800368fa  mov     ecx, ebx; Size
0x1800368fc  call    cs:__imp_malloc
0x180036902  mov     r14, rax
0x180036905  test    rax, rax
0x180036908  jz      loc_180036CA6
0x18003690e  mov     r12d, ebx
0x180036911  mov     rsi, rax
0x180036914  mov     r8d, r12d; Size
0x180036917  xor     edx, edx; Val
0x180036919  mov     rcx, rsi; void *
0x18003691c  call    memset_0
0x180036921  mov     rcx, [rdi+78h]
0x180036925  lea     rax, [rbp+Overlapped]
0x180036929  mov     [rsp+78h+var_48], rax
0x18003692e  mov     r9, rsi
0x180036931  lea     rax, [rbp+NumberOfBytesTransferred]
0x180036935  xor     r8d, r8d
0x180036938  mov     [rsp+78h+var_50], rax
0x18003693d  mov     rdx, r15
0x180036940  mov     rax, [rdi+60h]
0x180036944  mov     [rsp+78h+bAlertable], r12d
0x180036949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003694e  mov     ebx, eax
0x180036950  mov     rcx, cs:WPP_GLOBAL_Control
0x180036957  lea     rax, WPP_GLOBAL_Control
0x18003695e  cmp     rcx, rax
0x180036961  jz      short loc_1800369C0
0x180036963  test    dword ptr [rcx+1Ch], 100h
0x18003696a  jz      short loc_180036992
0x18003696c  mov     rcx, [rcx+10h]
0x180036970  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180036977  mov     edx, 1Fh
0x18003697c  mov     r9d, ebx
0x18003697f  call    WPP_SF_d
0x180036984  mov     rcx, cs:WPP_GLOBAL_Control
0x18003698b  lea     rax, WPP_GLOBAL_Control
0x180036992  cmp     rcx, rax
0x180036995  jz      short loc_1800369C0
0x180036997  test    dword ptr [rcx+1Ch], 100h
0x18003699e  jz      short loc_1800369C0
0x1800369a0  mov     r9d, [rbp+NumberOfBytesTransferred]
0x1800369a4  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800369ab  mov     rcx, [rcx+10h]
0x1800369af  mov     edx, 20h ; ' '
0x1800369b4  call    WPP_SF_d
0x1800369b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369c0  cmp     ebx, 3E5h
0x1800369c6  jz      short loc_1800369D0
0x1800369c8  test    ebx, ebx
0x1800369ca  jnz     loc_180036AE1
0x1800369d0  xor     r8d, r8d; bWaitAll
0x1800369d3  mov     [rsp+78h+bAlertable], 0; bAlertable
0x1800369db  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800369df  lea     rdx, [rbp+hEvent]; lpHandles
0x1800369e3  lea     ecx, [r8+2]; nCount
0x1800369e7  call    cs:__imp_WaitForMultipleObjectsEx
0x1800369ed  cmp     eax, 1
0x1800369f0  jnz     loc_180036CDA
0x1800369f6  mov     rcx, [rdi+78h]; hFile
0x1800369fa  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800369fe  xor     r9d, r9d; bWait
0x180036a01  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180036a05  call    cs:__imp_GetOverlappedResult
0x180036a0b  test    eax, eax
0x180036a0d  jz      short loc_180036A13
0x180036a0f  xor     ebx, ebx
0x180036a11  jmp     short loc_180036A1B
0x180036a13  call    cs:__imp_GetLastError
0x180036a19  mov     ebx, eax
0x180036a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a22  lea     rax, WPP_GLOBAL_Control
0x180036a29  cmp     rcx, rax
0x180036a2c  jz      short loc_180036A8B
0x180036a2e  test    dword ptr [rcx+1Ch], 100h
0x180036a35  jz      short loc_180036A5D
0x180036a37  mov     rcx, [rcx+10h]
0x180036a3b  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180036a42  mov     edx, 21h ; '!'
0x180036a47  mov     r9d, ebx
0x180036a4a  call    WPP_SF_d
0x180036a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a56  lea     rax, WPP_GLOBAL_Control
0x180036a5d  cmp     rcx, rax
0x180036a60  jz      short loc_180036A8B
0x180036a62  test    dword ptr [rcx+1Ch], 100h
0x180036a69  jz      short loc_180036A8B
0x180036a6b  mov     r9d, [rbp+NumberOfBytesTransferred]
0x180036a6f  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180036a76  mov     rcx, [rcx+10h]
0x180036a7a  mov     edx, 22h ; '"'
0x180036a7f  call    WPP_SF_d
0x180036a84  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a8b  test    ebx, ebx
0x180036a8d  jnz     short loc_180036AE1
0x180036a8f  mov     r8, [rdi+78h]; void *
0x180036a93  mov     rdx, rsi; Block
0x180036a96  mov     rcx, rdi; this
0x180036a99  mov     [rdi+128h], ebx
0x180036a9f  call    ?HandleHTTPHeader@BaseHttpListener@@IEAAJPEAU_HTTP_REQUEST_V2@@PEAX@Z; BaseHttpListener::HandleHTTPHeader(_HTTP_REQUEST_V2 *,void *)
0x180036aa4  test    eax, eax
0x180036aa6  jns     short loc_180036AD7
0x180036aa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180036aaf  lea     rdx, WPP_GLOBAL_Control
0x180036ab6  cmp     rcx, rdx
0x180036ab9  jz      short loc_180036AD7
0x180036abb  test    byte ptr [rcx+1Ch], 1
0x180036abf  jz      short loc_180036AD7
0x180036ac1  mov     rcx, [rcx+10h]
0x180036ac5  lea     edx, [rbx+25h]
0x180036ac8  mov     r9d, eax
0x180036acb  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180036ad2  call    WPP_SF_d
0x180036ad7  xor     r15d, r15d
0x180036ada  xor     esi, esi
0x180036adc  jmp     loc_180036C18
0x180036ae1  cmp     ebx, 0EAh
0x180036ae7  jnz     short loc_180036B21
0x180036ae9  mov     r12d, [rbp+NumberOfBytesTransferred]
0x180036aed  mov     rcx, r14; Block
0x180036af0  mov     dword ptr [rdi+128h], 0
0x180036afa  mov     r15, [rsi+10h]
0x180036afe  call    cs:__imp_free
0x180036b04  mov     ecx, r12d; Size
0x180036b07  call    cs:__imp_malloc
0x180036b0d  mov     r14, rax
0x180036b10  test    rax, rax
0x180036b13  jz      loc_180036CCE
0x180036b19  mov     rsi, rax
0x180036b1c  jmp     loc_180036C18
0x180036b21  cmp     ebx, 4CDh
0x180036b27  jnz     short loc_180036B84
0x180036b29  test    r15, r15
0x180036b2c  jz      loc_180036BD0
0x180036b32  xor     r15d, r15d
0x180036b35  test    r14, r14
0x180036b38  jz      short loc_180036B4A
0x180036b3a  mov     rcx, r14; Block
0x180036b3d  call    cs:__imp_free
0x180036b43  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b4a  xor     esi, esi
0x180036b4c  lea     rax, WPP_GLOBAL_Control
0x180036b53  cmp     rcx, rax
0x180036b56  jz      loc_180036C18
0x180036b5c  test    byte ptr [rcx+1Ch], 1
0x180036b60  jz      loc_180036C18
0x180036b66  mov     rcx, [rcx+10h]
0x180036b6a  lea     edx, [rsi+26h]
0x180036b6d  mov     r9d, 4CDh
0x180036b73  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180036b7a  call    WPP_SF_d
0x180036b7f  jmp     loc_180036C18
0x180036b84  cmp     ebx, 3E3h
0x180036b8a  jz      loc_180036C21
0x180036b90  cmp     ebx, 6
0x180036b93  jz      loc_180036C21
0x180036b99  cmp     ebx, 45Ah
0x180036b9f  jnz     short loc_180036BD0
0x180036ba1  lea     rax, WPP_GLOBAL_Control
0x180036ba8  cmp     rcx, rax
0x180036bab  jz      short loc_180036BC8
0x180036bad  test    byte ptr [rcx+1Ch], 1
0x180036bb1  jz      short loc_180036BC8
0x180036bb3  mov     rcx, [rcx+10h]
0x180036bb7  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180036bbe  mov     edx, 27h ; '''
0x180036bc3  call    WPP_SF_
0x180036bc8  mov     r13d, 1
0x180036bce  jmp     short loc_180036C18
0x180036bd0  lea     rax, WPP_GLOBAL_Control
0x180036bd7  cmp     rcx, rax
0x180036bda  jz      short loc_180036BFA
0x180036bdc  test    byte ptr [rcx+1Ch], 1
0x180036be0  jz      short loc_180036BFA
0x180036be2  mov     rcx, [rcx+10h]
0x180036be6  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180036bed  mov     edx, 28h ; '('
0x180036bf2  mov     r9d, ebx
0x180036bf5  call    WPP_SF_d
0x180036bfa  mov     eax, [rdi+128h]
0x180036c00  cmp     eax, 5
0x180036c03  jz      short loc_180036C21
0x180036c05  inc     eax
0x180036c07  mov     ecx, 0Ah; dwMilliseconds
0x180036c0c  mov     [rdi+128h], eax
0x180036c12  call    cs:__imp_Sleep
0x180036c18  test    r13d, r13d
0x180036c1b  jz      loc_1800368A6
0x180036c21  lea     r14, WPP_GLOBAL_Control
0x180036c28  mov     dword ptr [rdi+128h], 0
0x180036c32  test    rsi, rsi
0x180036c35  jz      short loc_180036C40
0x180036c37  mov     rcx, rsi; Block
0x180036c3a  call    cs:__imp_free
0x180036c40  mov     rcx, [rbp+hEvent+8]; hObject
0x180036c44  test    rcx, rcx
0x180036c47  jz      short loc_180036C57
0x180036c49  call    cs:__imp_CloseHandle
0x180036c4f  mov     [rbp+hEvent+8], 0
0x180036c57  mov     rcx, rdi; this
0x180036c5a  mov     dword ptr [rdi+80h], 0
0x180036c64  call    ?DecrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::DecrThreadCount(void)
0x180036c69  mov     rcx, cs:WPP_GLOBAL_Control
0x180036c70  cmp     rcx, r14
0x180036c73  jz      short loc_180036C93
0x180036c75  test    dword ptr [rcx+1Ch], 100h
0x180036c7c  jz      short loc_180036C93
0x180036c7e  mov     rcx, [rcx+10h]
0x180036c82  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180036c89  mov     edx, 29h ; ')'
0x180036c8e  call    WPP_SF_
0x180036c93  mov     eax, ebx
0x180036c95  add     rsp, 78h
0x180036c99  pop     r15
0x180036c9b  pop     r14
0x180036c9d  pop     r13
0x180036c9f  pop     r12
0x180036ca1  pop     rdi
0x180036ca2  pop     rsi
0x180036ca3  pop     rbx
0x180036ca4  pop     rbp
0x180036ca5  retn
0x180036ca6  mov     rcx, rdi; this
0x180036ca9  call    ?DecrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::DecrThreadCount(void)
0x180036cae  mov     rcx, [rbp+hEvent+8]; hObject
0x180036cb2  mov     dword ptr [rdi+80h], 0
0x180036cbc  test    rcx, rcx
0x180036cbf  jz      short loc_180036CC7
0x180036cc1  call    cs:__imp_CloseHandle
  ... truncated ...
```
