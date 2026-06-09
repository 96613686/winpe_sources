# BaseHttpListener::DoReceiveRequestHeaders(void)

- ea: `0x180023738`
- end: `0x180023daf`
- name: `?DoReceiveRequestHeaders@BaseHttpListener@@AEAAKXZ`
- size: `1655`
- prototype: `unsigned int __fastcall(BaseHttpListener *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180026e90`

## callees

- `0x180023738`
- `0x180025d44`
- `0x1800271fc`
- `0x18002911c`
- `0x180029df0`
- `0x1800332c8`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180023a89`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180023ad4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180023d2f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180023a89`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180023ad4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180023d2f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002386f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180023a98`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002386f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180023a98`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023821`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023c31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023821`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180023c31`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800237ad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800237ad`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180023960`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180023960`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180023847`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180023847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023d44`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023bb8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180023bb8`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180023c02`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180023c02`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180023984`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180023984`

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
0x180023738  push    rbp
0x18002373a  push    rbx
0x18002373b  push    rsi
0x18002373c  push    rdi
0x18002373d  push    r12
0x18002373f  push    r13
0x180023741  push    r14
0x180023743  push    r15
0x180023745  mov     rbp, rsp
0x180023748  sub     rsp, 78h
0x18002374c  xorps   xmm0, xmm0
0x18002374f  mov     [rbp+NumberOfBytesTransferred], 0
0x180023756  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18002375a  mov     rdi, rcx
0x18002375d  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180023761  movups  xmmword ptr [rbp+hEvent], xmm0
0x180023765  mov     rcx, cs:WPP_GLOBAL_Control
0x18002376c  lea     rbx, WPP_GLOBAL_Control
0x180023773  cmp     rcx, rbx
0x180023776  jz      short loc_180023796
0x180023778  test    dword ptr [rcx+1Ch], 100h
0x18002377f  jz      short loc_180023796
0x180023781  mov     rcx, [rcx+10h]
0x180023785  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002378c  mov     edx, 1Ch
0x180023791  call    WPP_SF_
0x180023796  mov     rax, [rdi+138h]
0x18002379d  xor     r9d, r9d; lpName
0x1800237a0  xor     r8d, r8d; bInitialState
0x1800237a3  mov     [rbp+hEvent], rax
0x1800237a7  xor     ecx, ecx; lpEventAttributes
0x1800237a9  lea     edx, [r9+1]; bManualReset
0x1800237ad  call    cs:__imp_CreateEventW
0x1800237b4  nop     dword ptr [rax+rax+00h]
0x1800237b9  mov     [rbp+hEvent+8], rax
0x1800237bd  test    rax, rax
0x1800237c0  jnz     short loc_1800237F4
0x1800237c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800237c9  cmp     rcx, rbx
0x1800237cc  jz      loc_180023D0C
0x1800237d2  test    byte ptr [rcx+1Ch], 1
0x1800237d6  jz      loc_180023D0C
0x1800237dc  mov     rcx, [rcx+10h]
0x1800237e0  lea     edx, [rax+1Dh]
0x1800237e3  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800237ea  call    WPP_SF_
0x1800237ef  jmp     loc_180023D0C
0x1800237f4  xor     ebx, ebx
0x1800237f6  xor     esi, esi
0x1800237f8  xor     r15d, r15d
0x1800237fb  xor     r13d, r13d
0x1800237fe  xor     r14d, r14d
0x180023801  xor     r12d, r12d
0x180023804  test    r14d, r14d
0x180023807  jnz     loc_180023D1D
0x18002380d  mov     eax, [rdi+6Ch]
0x180023810  test    eax, eax
0x180023812  jnz     loc_180023D1D
0x180023818  mov     rcx, [rdi+138h]; hHandle
0x18002381f  xor     edx, edx; dwMilliseconds
0x180023821  call    cs:__imp_WaitForSingleObject
0x180023828  nop     dword ptr [rax+rax+00h]
0x18002382d  cmp     eax, 102h
0x180023832  jnz     loc_180023D1D
0x180023838  mov     rcx, [rbp+hEvent+8]; hEvent
0x18002383c  xorps   xmm0, xmm0
0x18002383f  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x180023843  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180023847  call    cs:__imp_ResetEvent
0x18002384e  nop     dword ptr [rax+rax+00h]
0x180023853  test    eax, eax
0x180023855  jz      loc_180023C87
0x18002385b  mov     rax, [rbp+hEvent+8]
0x18002385f  mov     [rbp+Overlapped.hEvent], rax
0x180023863  test    rsi, rsi
0x180023866  jnz     short loc_18002388D
0x180023868  mov     ebx, 0B60h
0x18002386d  mov     ecx, ebx; Size
0x18002386f  call    cs:__imp_malloc
0x180023876  nop     dword ptr [rax+rax+00h]
0x18002387b  mov     r15, rax
0x18002387e  test    rax, rax
0x180023881  jz      loc_180023CE5
0x180023887  mov     r13d, ebx
0x18002388a  mov     rsi, rax
0x18002388d  mov     r8d, r13d; Size
0x180023890  xor     edx, edx; Val
0x180023892  mov     rcx, rsi; void *
0x180023895  call    memset_0
0x18002389a  mov     rcx, [rdi+78h]
0x18002389e  lea     rax, [rbp+Overlapped]
0x1800238a2  mov     [rsp+78h+var_48], rax
0x1800238a7  mov     r9, rsi
0x1800238aa  lea     rax, [rbp+NumberOfBytesTransferred]
0x1800238ae  xor     r8d, r8d
0x1800238b1  mov     [rsp+78h+var_50], rax
0x1800238b6  mov     rdx, r12
0x1800238b9  mov     rax, [rdi+60h]
0x1800238bd  mov     [rsp+78h+bAlertable], r13d
0x1800238c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238c7  mov     ebx, eax
0x1800238c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238d0  lea     rax, WPP_GLOBAL_Control
0x1800238d7  cmp     rcx, rax
0x1800238da  jz      short loc_180023939
0x1800238dc  test    dword ptr [rcx+1Ch], 100h
0x1800238e3  jz      short loc_18002390B
0x1800238e5  mov     rcx, [rcx+10h]
0x1800238e9  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800238f0  mov     edx, 1Fh
0x1800238f5  mov     r9d, ebx
0x1800238f8  call    WPP_SF_d
0x1800238fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180023904  lea     rax, WPP_GLOBAL_Control
0x18002390b  cmp     rcx, rax
0x18002390e  jz      short loc_180023939
0x180023910  test    dword ptr [rcx+1Ch], 100h
0x180023917  jz      short loc_180023939
0x180023919  mov     r9d, [rbp+NumberOfBytesTransferred]
0x18002391d  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180023924  mov     rcx, [rcx+10h]
0x180023928  mov     edx, 20h ; ' '
0x18002392d  call    WPP_SF_d
0x180023932  mov     rcx, cs:WPP_GLOBAL_Control
0x180023939  cmp     ebx, 3E5h
0x18002393f  jz      short loc_180023949
0x180023941  test    ebx, ebx
0x180023943  jnz     loc_180023A6C
0x180023949  xor     r8d, r8d; bWaitAll
0x18002394c  mov     [rsp+78h+bAlertable], 0; bAlertable
0x180023954  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180023958  lea     rdx, [rbp+hEvent]; lpHandles
0x18002395c  lea     ecx, [r8+2]; nCount
0x180023960  call    cs:__imp_WaitForMultipleObjectsEx
0x180023967  nop     dword ptr [rax+rax+00h]
0x18002396c  cmp     eax, 1
0x18002396f  jnz     loc_180023BC9
0x180023975  mov     rcx, [rdi+78h]; hFile
0x180023979  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002397d  xor     r9d, r9d; bWait
0x180023980  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180023984  call    cs:__imp_GetOverlappedResult
0x18002398b  nop     dword ptr [rax+rax+00h]
0x180023990  test    eax, eax
0x180023992  jz      short loc_180023998
0x180023994  xor     ebx, ebx
0x180023996  jmp     short loc_1800239A6
0x180023998  call    cs:__imp_GetLastError
0x18002399f  nop     dword ptr [rax+rax+00h]
0x1800239a4  mov     ebx, eax
0x1800239a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239ad  lea     rax, WPP_GLOBAL_Control
0x1800239b4  cmp     rcx, rax
0x1800239b7  jz      short loc_180023A16
0x1800239b9  test    dword ptr [rcx+1Ch], 100h
0x1800239c0  jz      short loc_1800239E8
0x1800239c2  mov     rcx, [rcx+10h]
0x1800239c6  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800239cd  mov     edx, 21h ; '!'
0x1800239d2  mov     r9d, ebx
0x1800239d5  call    WPP_SF_d
0x1800239da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239e1  lea     rax, WPP_GLOBAL_Control
0x1800239e8  cmp     rcx, rax
0x1800239eb  jz      short loc_180023A16
0x1800239ed  test    dword ptr [rcx+1Ch], 100h
0x1800239f4  jz      short loc_180023A16
0x1800239f6  mov     r9d, [rbp+NumberOfBytesTransferred]
0x1800239fa  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180023a01  mov     rcx, [rcx+10h]
0x180023a05  mov     edx, 22h ; '"'
0x180023a0a  call    WPP_SF_d
0x180023a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a16  test    ebx, ebx
0x180023a18  jnz     short loc_180023A6C
0x180023a1a  mov     r8, [rdi+78h]; void *
0x180023a1e  mov     rdx, rsi; struct _HTTP_REQUEST_V2 *
0x180023a21  mov     rcx, rdi; this
0x180023a24  mov     [rdi+128h], ebx
0x180023a2a  call    ?HandleHTTPHeader@BaseHttpListener@@IEAAJPEAU_HTTP_REQUEST_V2@@PEAX@Z; BaseHttpListener::HandleHTTPHeader(_HTTP_REQUEST_V2 *,void *)
0x180023a2f  test    eax, eax
0x180023a31  jns     short loc_180023A62
0x180023a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a3a  lea     rdx, WPP_GLOBAL_Control
0x180023a41  cmp     rcx, rdx
0x180023a44  jz      short loc_180023A62
0x180023a46  test    byte ptr [rcx+1Ch], 1
0x180023a4a  jz      short loc_180023A62
0x180023a4c  mov     rcx, [rcx+10h]
0x180023a50  lea     edx, [rbx+25h]
0x180023a53  mov     r9d, eax
0x180023a56  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180023a5d  call    WPP_SF_d
0x180023a62  xor     r12d, r12d
0x180023a65  xor     esi, esi
0x180023a67  jmp     loc_180023804
0x180023a6c  cmp     ebx, 0EAh
0x180023a72  jnz     short loc_180023AB8
0x180023a74  mov     r13d, [rbp+NumberOfBytesTransferred]
0x180023a78  mov     rcx, r15; Block
0x180023a7b  mov     dword ptr [rdi+128h], 0
0x180023a85  mov     r12, [rsi+10h]
0x180023a89  call    cs:__imp_free
0x180023a90  nop     dword ptr [rax+rax+00h]
0x180023a95  mov     ecx, r13d; Size
0x180023a98  call    cs:__imp_malloc
0x180023a9f  nop     dword ptr [rax+rax+00h]
0x180023aa4  mov     r15, rax
0x180023aa7  test    rax, rax
0x180023aaa  jz      loc_180023D16
0x180023ab0  mov     rsi, rax
0x180023ab3  jmp     loc_180023804
0x180023ab8  cmp     ebx, 4CDh
0x180023abe  jnz     short loc_180023B21
0x180023ac0  test    r12, r12
0x180023ac3  jz      loc_180023B72
0x180023ac9  xor     r12d, r12d
0x180023acc  test    r15, r15
0x180023acf  jz      short loc_180023AE7
0x180023ad1  mov     rcx, r15; Block
0x180023ad4  call    cs:__imp_free
0x180023adb  nop     dword ptr [rax+rax+00h]
0x180023ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ae7  xor     esi, esi
0x180023ae9  lea     rax, WPP_GLOBAL_Control
0x180023af0  cmp     rcx, rax
0x180023af3  jz      loc_180023804
0x180023af9  test    byte ptr [rcx+1Ch], 1
0x180023afd  jz      loc_180023804
0x180023b03  mov     rcx, [rcx+10h]
0x180023b07  lea     edx, [rsi+26h]
0x180023b0a  mov     r9d, 4CDh
0x180023b10  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180023b17  call    WPP_SF_d
0x180023b1c  jmp     loc_180023804
0x180023b21  cmp     ebx, 3E3h
0x180023b27  jz      loc_180023CDA
0x180023b2d  cmp     ebx, 6
0x180023b30  jz      loc_180023CDA
0x180023b36  cmp     ebx, 45Ah
0x180023b3c  jnz     short loc_180023B72
0x180023b3e  lea     rax, WPP_GLOBAL_Control
0x180023b45  cmp     rcx, rax
0x180023b48  jz      loc_180023CDA
0x180023b4e  test    byte ptr [rcx+1Ch], 1
0x180023b52  jz      loc_180023CDA
0x180023b58  mov     rcx, [rcx+10h]
0x180023b5c  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180023b63  mov     edx, 27h ; '''
0x180023b68  call    WPP_SF_
0x180023b6d  jmp     loc_180023CDA
0x180023b72  lea     rax, WPP_GLOBAL_Control
0x180023b79  cmp     rcx, rax
0x180023b7c  jz      short loc_180023B9C
0x180023b7e  test    byte ptr [rcx+1Ch], 1
0x180023b82  jz      short loc_180023B9C
0x180023b84  mov     rcx, [rcx+10h]
0x180023b88  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180023b8f  mov     edx, 28h ; '('
0x180023b94  mov     r9d, ebx
0x180023b97  call    WPP_SF_d
0x180023b9c  mov     eax, [rdi+128h]
0x180023ba2  cmp     eax, 5
0x180023ba5  jz      loc_180023CDA
0x180023bab  inc     eax
0x180023bad  mov     ecx, 0Ah; dwMilliseconds
0x180023bb2  mov     [rdi+128h], eax
0x180023bb8  call    cs:__imp_Sleep
0x180023bbf  nop     dword ptr [rax+rax+00h]
0x180023bc4  jmp     loc_180023804
0x180023bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180023bd0  lea     r14, WPP_GLOBAL_Control
0x180023bd7  cmp     rcx, r14
0x180023bda  jz      short loc_180023BFA
0x180023bdc  test    dword ptr [rcx+1Ch], 100h
0x180023be3  jz      short loc_180023BFA
0x180023be5  mov     rcx, [rcx+10h]
0x180023be9  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180023bf0  mov     edx, 23h ; '#'
0x180023bf5  call    WPP_SF_
0x180023bfa  mov     rcx, [rdi+78h]; hFile
0x180023bfe  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180023c02  call    cs:__imp_CancelIoEx
0x180023c09  nop     dword ptr [rax+rax+00h]
0x180023c0e  cmp     eax, 1
0x180023c11  jz      short loc_180023C2A
0x180023c13  call    cs:__imp_GetLastError
0x180023c1a  nop     dword ptr [rax+rax+00h]
0x180023c1f  cmp     eax, 490h
0x180023c24  jz      loc_180023CDA
0x180023c2a  mov     rcx, [rbp+hEvent+8]; hHandle
0x180023c2e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180023c31  call    cs:__imp_WaitForSingleObject
0x180023c38  nop     dword ptr [rax+rax+00h]
0x180023c3d  test    eax, eax
0x180023c3f  jz      loc_180023CDA
0x180023c45  mov     rax, cs:WPP_GLOBAL_Control
0x180023c4c  cmp     rax, r14
0x180023c4f  jz      loc_180023CDA
0x180023c55  test    dword ptr [rax+1Ch], 100h
  ... truncated ...
```
