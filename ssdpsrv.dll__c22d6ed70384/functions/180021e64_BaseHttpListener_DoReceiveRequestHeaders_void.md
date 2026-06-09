# BaseHttpListener::DoReceiveRequestHeaders(void)

- ea: `0x180021e64`
- end: `0x180022461`
- name: `?DoReceiveRequestHeaders@BaseHttpListener@@AEAAKXZ`
- size: `1533`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800251e0`

## callees

- `0x180021e64`
- `0x1800242a4`
- `0x1800255a8`
- `0x18002735c`
- `0x180028000`
- `0x180030bac`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002218b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800221ca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800223ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002218b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800221ca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800223ee`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180021f89`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180022194`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180021f89`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180022194`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021f47`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002230f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021f47`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002230f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021ed9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021ed9`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022074`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180022074`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180021f67`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180021f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022332`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022332`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800223c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800223fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800223c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800223fd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800222a8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800222a8`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800222ec`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800222ec`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180022092`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180022092`

## pseudocode

```c
__int64 __fastcall BaseHttpListener::DoReceiveRequestHeaders(HANDLE *this)
{
  DWORD LastError; // ebx
  struct _HTTP_REQUEST_V2 *v3; // rsi
  struct _HTTP_REQUEST_V2 *v4; // r15
  DWORD v5; // r13d
  int v6; // r14d
  HTTP_REQUEST_ID RequestId; // r12
  struct _HTTP_REQUEST_V2 *v8; // rax
  LPCSTR v9; // rcx
  HANDLE v10; // r8
  int v11; // eax
  struct _HTTP_REQUEST_V2 *v12; // rax
  int v13; // eax
  signed int v14; // eax
  LPCSTR v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  HANDLE v18; // rcx
  HANDLE hEvent[2]; // [rsp+40h] [rbp-38h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-28h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+C0h] [rbp+48h] BYREF

  NumberOfBytesTransferred = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  *(_OWORD *)hEvent = 0;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
  hEvent[0] = this[39];
  hEvent[1] = CreateEventW(0, 1, 0, 0);
  if ( hEvent[1] )
  {
    LastError = 0;
    v3 = 0;
    v4 = 0;
    v5 = 0;
    v6 = 0;
    RequestId = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v6 || *((_DWORD *)this + 27) || WaitForSingleObject(this[39], 0) != 258 )
          goto LABEL_84;
        memset(&Overlapped, 0, sizeof(Overlapped));
        if ( ResetEvent(hEvent[1]) )
          break;
        LastError = GetLastError();
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          if ( (int)LastError > 0 )
            v17 = (unsigned __int16)LastError | 0x80070000;
          else
            v17 = LastError;
          v16 = 30;
LABEL_78:
          WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v17);
        }
LABEL_79:
        v6 = 1;
      }
      Overlapped.hEvent = hEvent[1];
      if ( !v3 )
      {
        v8 = (struct _HTTP_REQUEST_V2 *)malloc(0xB60u);
        v4 = v8;
        if ( !v8 )
        {
          BaseHttpListener::DecrThreadCount((BaseHttpListener *)this);
          v18 = hEvent[1];
          *((_DWORD *)this + 32) = 0;
          if ( v18 )
            CloseHandle(v18);
          return 8;
        }
        v5 = 2912;
        v3 = v8;
      }
      memset_0(v3, 0, v5);
      LastError = ((__int64 (__fastcall *)(HANDLE, HTTP_REQUEST_ID, _QWORD, struct _HTTP_REQUEST_V2 *, DWORD, DWORD *, struct _OVERLAPPED *))this[12])(
                    this[15],
                    RequestId,
                    0,
                    v3,
                    v5,
                    &NumberOfBytesTransferred,
                    &Overlapped);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, LastError);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v9 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x100) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v9 + 2), 32, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, NumberOfBytesTransferred);
          v9 = WPP_GLOBAL_Control;
        }
      }
      if ( LastError != 997 && LastError )
        goto LABEL_40;
      if ( WaitForMultipleObjectsEx(2u, hEvent, 0, 0xFFFFFFFF, 0) != 1 )
      {
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
        if ( (CancelIoEx(this[15], &Overlapped) || GetLastError() != 1168)
          && WaitForSingleObject(hEvent[1], 0xFFFFFFFF)
          && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          v14 = GetLastError();
          if ( v14 > 0 )
            v14 = (unsigned __int16)v14 | 0x80070000;
          v15 = WPP_GLOBAL_Control;
          v16 = 36;
          v17 = (unsigned int)v14;
          goto LABEL_78;
        }
        goto LABEL_79;
      }
      if ( GetOverlappedResult(this[15], &Overlapped, &NumberOfBytesTransferred, 0) )
        LastError = 0;
      else
        LastError = GetLastError();
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, LastError);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v9 != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x100) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v9 + 2), 34, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, NumberOfBytesTransferred);
          v9 = WPP_GLOBAL_Control;
        }
      }
      if ( LastError )
      {
LABEL_40:
        switch ( LastError )
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
              LastError = 8;
              v3 = 0;
LABEL_84:
              *((_DWORD *)this + 74) = 0;
              if ( v3 )
                free(v3);
              if ( hEvent[1] )
              {
                CloseHandle(hEvent[1]);
                hEvent[1] = 0;
              }
              *((_DWORD *)this + 32) = 0;
              BaseHttpListener::DecrThreadCount((BaseHttpListener *)this);
              if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
              }
              return LastError;
            }
            v3 = v12;
            break;
          case 0x4CDu:
            if ( !RequestId )
              goto LABEL_56;
            RequestId = 0;
            if ( v4 )
            {
              free(v4);
              v9 = WPP_GLOBAL_Control;
            }
            v3 = 0;
            if ( v9 != (LPCSTR)&WPP_GLOBAL_Control && (v9[28] & 1) != 0 )
              WPP_SF_d(*((_QWORD *)v9 + 2), 38, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, 1229);
            break;
          case 0x3E3u:
          case 6u:
            goto LABEL_79;
          case 0x45Au:
            if ( v9 != (LPCSTR)&WPP_GLOBAL_Control && (v9[28] & 1) != 0 )
              WPP_SF_(*((_QWORD *)v9 + 2), 39, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
            goto LABEL_79;
          default:
LABEL_56:
            if ( v9 != (LPCSTR)&WPP_GLOBAL_Control && (v9[28] & 1) != 0 )
              WPP_SF_d(*((_QWORD *)v9 + 2), 40, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, LastError);
            v13 = *((_DWORD *)this + 74);
            if ( v13 == 5 )
              goto LABEL_79;
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
        if ( v11 < 0 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
            (unsigned int)v11);
        RequestId = 0;
        v3 = 0;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
  return 8;
}

```

## disassembly

```asm
0x180021e64  push    rbp
0x180021e66  push    rbx
0x180021e67  push    rsi
0x180021e68  push    rdi
0x180021e69  push    r12
0x180021e6b  push    r13
0x180021e6d  push    r14
0x180021e6f  push    r15
0x180021e71  mov     rbp, rsp
0x180021e74  sub     rsp, 78h
0x180021e78  xorps   xmm0, xmm0
0x180021e7b  mov     [rbp+NumberOfBytesTransferred], 0
0x180021e82  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x180021e86  mov     rdi, rcx
0x180021e89  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180021e8d  movups  xmmword ptr [rbp+hEvent], xmm0
0x180021e91  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e98  lea     rbx, WPP_GLOBAL_Control
0x180021e9f  cmp     rcx, rbx
0x180021ea2  jz      short loc_180021EC2
0x180021ea4  test    dword ptr [rcx+1Ch], 100h
0x180021eab  jz      short loc_180021EC2
0x180021ead  mov     rcx, [rcx+10h]
0x180021eb1  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180021eb8  mov     edx, 1Ch
0x180021ebd  call    WPP_SF_
0x180021ec2  mov     rax, [rdi+138h]
0x180021ec9  xor     r9d, r9d; lpName
0x180021ecc  xor     r8d, r8d; bInitialState
0x180021ecf  mov     [rbp+hEvent], rax
0x180021ed3  xor     ecx, ecx; lpEventAttributes
0x180021ed5  lea     edx, [r9+1]; bManualReset
0x180021ed9  call    cs:__imp_CreateEventW
0x180021edf  mov     [rbp+hEvent+8], rax
0x180021ee3  test    rax, rax
0x180021ee6  jnz     short loc_180021F1A
0x180021ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x180021eef  cmp     rcx, rbx
0x180021ef2  jz      loc_1800223CE
0x180021ef8  test    byte ptr [rcx+1Ch], 1
0x180021efc  jz      loc_1800223CE
0x180021f02  mov     rcx, [rcx+10h]
0x180021f06  lea     edx, [rax+1Dh]
0x180021f09  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180021f10  call    WPP_SF_
0x180021f15  jmp     loc_1800223CE
0x180021f1a  xor     ebx, ebx
0x180021f1c  xor     esi, esi
0x180021f1e  xor     r15d, r15d
0x180021f21  xor     r13d, r13d
0x180021f24  xor     r14d, r14d
0x180021f27  xor     r12d, r12d
0x180021f2a  test    r14d, r14d
0x180021f2d  jnz     loc_1800223DC
0x180021f33  mov     eax, [rdi+6Ch]
0x180021f36  test    eax, eax
0x180021f38  jnz     loc_1800223DC
0x180021f3e  mov     rcx, [rdi+138h]; hHandle
0x180021f45  xor     edx, edx; dwMilliseconds
0x180021f47  call    cs:__imp_WaitForSingleObject
0x180021f4d  cmp     eax, 102h
0x180021f52  jnz     loc_1800223DC
0x180021f58  mov     rcx, [rbp+hEvent+8]; hEvent
0x180021f5c  xorps   xmm0, xmm0
0x180021f5f  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x180021f63  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180021f67  call    cs:__imp_ResetEvent
0x180021f6d  test    eax, eax
0x180021f6f  jz      loc_180022355
0x180021f75  mov     rax, [rbp+hEvent+8]
0x180021f79  mov     [rbp+Overlapped.hEvent], rax
0x180021f7d  test    rsi, rsi
0x180021f80  jnz     short loc_180021FA1
0x180021f82  mov     ebx, 0B60h
0x180021f87  mov     ecx, ebx; Size
0x180021f89  call    cs:__imp_malloc
0x180021f8f  mov     r15, rax
0x180021f92  test    rax, rax
0x180021f95  jz      loc_1800223AD
0x180021f9b  mov     r13d, ebx
0x180021f9e  mov     rsi, rax
0x180021fa1  mov     r8d, r13d; Size
0x180021fa4  xor     edx, edx; Val
0x180021fa6  mov     rcx, rsi; void *
0x180021fa9  call    memset_0
0x180021fae  mov     rcx, [rdi+78h]
0x180021fb2  lea     rax, [rbp+Overlapped]
0x180021fb6  mov     [rsp+78h+var_48], rax
0x180021fbb  mov     r9, rsi
0x180021fbe  lea     rax, [rbp+NumberOfBytesTransferred]
0x180021fc2  xor     r8d, r8d
0x180021fc5  mov     [rsp+78h+var_50], rax
0x180021fca  mov     rdx, r12
0x180021fcd  mov     rax, [rdi+60h]
0x180021fd1  mov     [rsp+78h+bAlertable], r13d
0x180021fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fdb  mov     ebx, eax
0x180021fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180021fe4  lea     rax, WPP_GLOBAL_Control
0x180021feb  cmp     rcx, rax
0x180021fee  jz      short loc_18002204D
0x180021ff0  test    dword ptr [rcx+1Ch], 100h
0x180021ff7  jz      short loc_18002201F
0x180021ff9  mov     rcx, [rcx+10h]
0x180021ffd  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180022004  mov     edx, 1Fh
0x180022009  mov     r9d, ebx
0x18002200c  call    WPP_SF_d
0x180022011  mov     rcx, cs:WPP_GLOBAL_Control
0x180022018  lea     rax, WPP_GLOBAL_Control
0x18002201f  cmp     rcx, rax
0x180022022  jz      short loc_18002204D
0x180022024  test    dword ptr [rcx+1Ch], 100h
0x18002202b  jz      short loc_18002204D
0x18002202d  mov     r9d, [rbp+NumberOfBytesTransferred]
0x180022031  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180022038  mov     rcx, [rcx+10h]
0x18002203c  mov     edx, 20h ; ' '
0x180022041  call    WPP_SF_d
0x180022046  mov     rcx, cs:WPP_GLOBAL_Control
0x18002204d  cmp     ebx, 3E5h
0x180022053  jz      short loc_18002205D
0x180022055  test    ebx, ebx
0x180022057  jnz     loc_18002216E
0x18002205d  xor     r8d, r8d; bWaitAll
0x180022060  mov     [rsp+78h+bAlertable], 0; bAlertable
0x180022068  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18002206c  lea     rdx, [rbp+hEvent]; lpHandles
0x180022070  lea     ecx, [r8+2]; nCount
0x180022074  call    cs:__imp_WaitForMultipleObjectsEx
0x18002207a  cmp     eax, 1
0x18002207d  jnz     loc_1800222B3
0x180022083  mov     rcx, [rdi+78h]; hFile
0x180022087  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002208b  xor     r9d, r9d; bWait
0x18002208e  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180022092  call    cs:__imp_GetOverlappedResult
0x180022098  test    eax, eax
0x18002209a  jz      short loc_1800220A0
0x18002209c  xor     ebx, ebx
0x18002209e  jmp     short loc_1800220A8
0x1800220a0  call    cs:__imp_GetLastError
0x1800220a6  mov     ebx, eax
0x1800220a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220af  lea     rax, WPP_GLOBAL_Control
0x1800220b6  cmp     rcx, rax
0x1800220b9  jz      short loc_180022118
0x1800220bb  test    dword ptr [rcx+1Ch], 100h
0x1800220c2  jz      short loc_1800220EA
0x1800220c4  mov     rcx, [rcx+10h]
0x1800220c8  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800220cf  mov     edx, 21h ; '!'
0x1800220d4  mov     r9d, ebx
0x1800220d7  call    WPP_SF_d
0x1800220dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220e3  lea     rax, WPP_GLOBAL_Control
0x1800220ea  cmp     rcx, rax
0x1800220ed  jz      short loc_180022118
0x1800220ef  test    dword ptr [rcx+1Ch], 100h
0x1800220f6  jz      short loc_180022118
0x1800220f8  mov     r9d, [rbp+NumberOfBytesTransferred]
0x1800220fc  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180022103  mov     rcx, [rcx+10h]
0x180022107  mov     edx, 22h ; '"'
0x18002210c  call    WPP_SF_d
0x180022111  mov     rcx, cs:WPP_GLOBAL_Control
0x180022118  test    ebx, ebx
0x18002211a  jnz     short loc_18002216E
0x18002211c  mov     r8, [rdi+78h]; void *
0x180022120  mov     rdx, rsi; struct _HTTP_REQUEST_V2 *
0x180022123  mov     rcx, rdi; this
0x180022126  mov     [rdi+128h], ebx
0x18002212c  call    ?HandleHTTPHeader@BaseHttpListener@@IEAAJPEAU_HTTP_REQUEST_V2@@PEAX@Z; BaseHttpListener::HandleHTTPHeader(_HTTP_REQUEST_V2 *,void *)
0x180022131  test    eax, eax
0x180022133  jns     short loc_180022164
0x180022135  mov     rcx, cs:WPP_GLOBAL_Control
0x18002213c  lea     rdx, WPP_GLOBAL_Control
0x180022143  cmp     rcx, rdx
0x180022146  jz      short loc_180022164
0x180022148  test    byte ptr [rcx+1Ch], 1
0x18002214c  jz      short loc_180022164
0x18002214e  mov     rcx, [rcx+10h]
0x180022152  lea     edx, [rbx+25h]
0x180022155  mov     r9d, eax
0x180022158  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002215f  call    WPP_SF_d
0x180022164  xor     r12d, r12d
0x180022167  xor     esi, esi
0x180022169  jmp     loc_180021F2A
0x18002216e  cmp     ebx, 0EAh
0x180022174  jnz     short loc_1800221AE
0x180022176  mov     r13d, [rbp+NumberOfBytesTransferred]
0x18002217a  mov     rcx, r15; Block
0x18002217d  mov     dword ptr [rdi+128h], 0
0x180022187  mov     r12, [rsi+10h]
0x18002218b  call    cs:__imp_free
0x180022191  mov     ecx, r13d; Size
0x180022194  call    cs:__imp_malloc
0x18002219a  mov     r15, rax
0x18002219d  test    rax, rax
0x1800221a0  jz      loc_1800223D5
0x1800221a6  mov     rsi, rax
0x1800221a9  jmp     loc_180021F2A
0x1800221ae  cmp     ebx, 4CDh
0x1800221b4  jnz     short loc_180022211
0x1800221b6  test    r12, r12
0x1800221b9  jz      loc_180022262
0x1800221bf  xor     r12d, r12d
0x1800221c2  test    r15, r15
0x1800221c5  jz      short loc_1800221D7
0x1800221c7  mov     rcx, r15; Block
0x1800221ca  call    cs:__imp_free
0x1800221d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221d7  xor     esi, esi
0x1800221d9  lea     rax, WPP_GLOBAL_Control
0x1800221e0  cmp     rcx, rax
0x1800221e3  jz      loc_180021F2A
0x1800221e9  test    byte ptr [rcx+1Ch], 1
0x1800221ed  jz      loc_180021F2A
0x1800221f3  mov     rcx, [rcx+10h]
0x1800221f7  lea     edx, [rsi+26h]
0x1800221fa  mov     r9d, 4CDh
0x180022200  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180022207  call    WPP_SF_d
0x18002220c  jmp     loc_180021F2A
0x180022211  cmp     ebx, 3E3h
0x180022217  jz      loc_1800223A2
0x18002221d  cmp     ebx, 6
0x180022220  jz      loc_1800223A2
0x180022226  cmp     ebx, 45Ah
0x18002222c  jnz     short loc_180022262
0x18002222e  lea     rax, WPP_GLOBAL_Control
0x180022235  cmp     rcx, rax
0x180022238  jz      loc_1800223A2
0x18002223e  test    byte ptr [rcx+1Ch], 1
0x180022242  jz      loc_1800223A2
0x180022248  mov     rcx, [rcx+10h]
0x18002224c  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180022253  mov     edx, 27h ; '''
0x180022258  call    WPP_SF_
0x18002225d  jmp     loc_1800223A2
0x180022262  lea     rax, WPP_GLOBAL_Control
0x180022269  cmp     rcx, rax
0x18002226c  jz      short loc_18002228C
0x18002226e  test    byte ptr [rcx+1Ch], 1
0x180022272  jz      short loc_18002228C
0x180022274  mov     rcx, [rcx+10h]
0x180022278  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002227f  mov     edx, 28h ; '('
0x180022284  mov     r9d, ebx
0x180022287  call    WPP_SF_d
0x18002228c  mov     eax, [rdi+128h]
0x180022292  cmp     eax, 5
0x180022295  jz      loc_1800223A2
0x18002229b  inc     eax
0x18002229d  mov     ecx, 0Ah; dwMilliseconds
0x1800222a2  mov     [rdi+128h], eax
0x1800222a8  call    cs:__imp_Sleep
0x1800222ae  jmp     loc_180021F2A
0x1800222b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222ba  lea     r14, WPP_GLOBAL_Control
0x1800222c1  cmp     rcx, r14
0x1800222c4  jz      short loc_1800222E4
0x1800222c6  test    dword ptr [rcx+1Ch], 100h
0x1800222cd  jz      short loc_1800222E4
0x1800222cf  mov     rcx, [rcx+10h]
0x1800222d3  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800222da  mov     edx, 23h ; '#'
0x1800222df  call    WPP_SF_
0x1800222e4  mov     rcx, [rdi+78h]; hFile
0x1800222e8  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1800222ec  call    cs:__imp_CancelIoEx
0x1800222f2  cmp     eax, 1
0x1800222f5  jz      short loc_180022308
0x1800222f7  call    cs:__imp_GetLastError
0x1800222fd  cmp     eax, 490h
0x180022302  jz      loc_1800223A2
0x180022308  mov     rcx, [rbp+hEvent+8]; hHandle
0x18002230c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002230f  call    cs:__imp_WaitForSingleObject
0x180022315  test    eax, eax
0x180022317  jz      loc_1800223A2
0x18002231d  mov     rax, cs:WPP_GLOBAL_Control
0x180022324  cmp     rax, r14
0x180022327  jz      short loc_1800223A2
0x180022329  test    dword ptr [rax+1Ch], 100h
0x180022330  jz      short loc_1800223A2
0x180022332  call    cs:__imp_GetLastError
0x180022338  test    eax, eax
0x18002233a  jle     short loc_180022344
0x18002233c  movzx   eax, ax
0x18002233f  or      eax, 80070000h
0x180022344  mov     rcx, cs:WPP_GLOBAL_Control
0x18002234b  mov     edx, 24h ; '$'
0x180022350  mov     r9d, eax
0x180022353  jmp     short loc_180022392
0x180022355  call    cs:__imp_GetLastError
0x18002235b  mov     ebx, eax
0x18002235d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022364  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
