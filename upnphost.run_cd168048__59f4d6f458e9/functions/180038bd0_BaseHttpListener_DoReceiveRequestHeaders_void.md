# BaseHttpListener::DoReceiveRequestHeaders(void)

- ea: `0x180038bd0`
- end: `0x180039241`
- name: `?DoReceiveRequestHeaders@BaseHttpListener@@AEAAKXZ`
- size: `1649`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180054960`

## callees

- `0x18002b138`
- `0x180038bd0`
- `0x180039248`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003d4b0`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180038f18`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180038f63`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003906c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180038f18`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180038f63`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003906c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180038cfe`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180038f27`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180038cfe`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180038f27`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180038cd6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180038cd6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038c45`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180038c45`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180038def`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180038def`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180038cb0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180039187`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180038cb0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180039187`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039100`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039100`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003903e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003903e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180038e13`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180038e13`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180039158`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180039158`

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
          BaseHttpListener::DecrThreadCount((BaseHttpListener *)this);
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
              BaseHttpListener::DecrThreadCount((BaseHttpListener *)this);
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
0x180038bd0  push    rbp
0x180038bd2  push    rbx
0x180038bd3  push    rsi
0x180038bd4  push    rdi
0x180038bd5  push    r12
0x180038bd7  push    r13
0x180038bd9  push    r14
0x180038bdb  push    r15
0x180038bdd  mov     rbp, rsp
0x180038be0  sub     rsp, 78h
0x180038be4  xorps   xmm0, xmm0
0x180038be7  mov     [rbp+NumberOfBytesTransferred], 0
0x180038bee  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x180038bf2  mov     rdi, rcx
0x180038bf5  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180038bf9  movups  xmmword ptr [rbp+hEvent], xmm0
0x180038bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c04  lea     rbx, WPP_GLOBAL_Control
0x180038c0b  cmp     rcx, rbx
0x180038c0e  jz      short loc_180038C2E
0x180038c10  test    dword ptr [rcx+1Ch], 100h
0x180038c17  jz      short loc_180038C2E
0x180038c19  mov     rcx, [rcx+10h]
0x180038c1d  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180038c24  mov     edx, 1Ch
0x180038c29  call    WPP_SF_
0x180038c2e  mov     rax, [rdi+138h]
0x180038c35  xor     r9d, r9d; lpName
0x180038c38  xor     r8d, r8d; bInitialState
0x180038c3b  mov     [rbp+hEvent], rax
0x180038c3f  xor     ecx, ecx; lpEventAttributes
0x180038c41  lea     edx, [r9+1]; bManualReset
0x180038c45  call    cs:__imp_CreateEventW
0x180038c4c  nop     dword ptr [rax+rax+00h]
0x180038c51  mov     [rbp+hEvent+8], rax
0x180038c55  test    rax, rax
0x180038c58  jnz     short loc_180038C8C
0x180038c5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c61  cmp     rcx, rbx
0x180038c64  jz      loc_18003910C
0x180038c6a  test    byte ptr [rcx+1Ch], 1
0x180038c6e  jz      loc_18003910C
0x180038c74  mov     rcx, [rcx+10h]
0x180038c78  lea     edx, [rax+1Dh]
0x180038c7b  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180038c82  call    WPP_SF_
0x180038c87  jmp     loc_18003910C
0x180038c8c  xor     ebx, ebx
0x180038c8e  xor     esi, esi
0x180038c90  xor     r14d, r14d
0x180038c93  xor     r12d, r12d
0x180038c96  xor     r13d, r13d
0x180038c99  xor     r15d, r15d
0x180038c9c  mov     eax, [rdi+6Ch]
0x180038c9f  test    eax, eax
0x180038ca1  jnz     loc_180039053
0x180038ca7  mov     rcx, [rdi+138h]; hHandle
0x180038cae  xor     edx, edx; dwMilliseconds
0x180038cb0  call    cs:__imp_WaitForSingleObject
0x180038cb7  nop     dword ptr [rax+rax+00h]
0x180038cbc  cmp     eax, 102h
0x180038cc1  jnz     loc_180039053
0x180038cc7  mov     rcx, [rbp+hEvent+8]; hEvent
0x180038ccb  xorps   xmm0, xmm0
0x180038cce  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x180038cd2  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180038cd6  call    cs:__imp_ResetEvent
0x180038cdd  nop     dword ptr [rax+rax+00h]
0x180038ce2  test    eax, eax
0x180038ce4  jz      loc_1800391F4
0x180038cea  mov     rax, [rbp+hEvent+8]
0x180038cee  mov     [rbp+Overlapped.hEvent], rax
0x180038cf2  test    rsi, rsi
0x180038cf5  jnz     short loc_180038D1C
0x180038cf7  mov     ebx, 0B60h
0x180038cfc  mov     ecx, ebx; Size
0x180038cfe  call    cs:__imp_malloc
0x180038d05  nop     dword ptr [rax+rax+00h]
0x180038d0a  mov     r14, rax
0x180038d0d  test    rax, rax
0x180038d10  jz      loc_1800390E5
0x180038d16  mov     r12d, ebx
0x180038d19  mov     rsi, rax
0x180038d1c  mov     r8d, r12d; Size
0x180038d1f  xor     edx, edx; Val
0x180038d21  mov     rcx, rsi; void *
0x180038d24  call    memset_0
0x180038d29  mov     rcx, [rdi+78h]
0x180038d2d  lea     rax, [rbp+Overlapped]
0x180038d31  mov     [rsp+78h+var_48], rax
0x180038d36  mov     r9, rsi
0x180038d39  lea     rax, [rbp+NumberOfBytesTransferred]
0x180038d3d  xor     r8d, r8d
0x180038d40  mov     [rsp+78h+var_50], rax
0x180038d45  mov     rdx, r15
0x180038d48  mov     rax, [rdi+60h]
0x180038d4c  mov     [rsp+78h+bAlertable], r12d
0x180038d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d56  mov     ebx, eax
0x180038d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180038d5f  lea     rax, WPP_GLOBAL_Control
0x180038d66  cmp     rcx, rax
0x180038d69  jz      short loc_180038DC8
0x180038d6b  test    dword ptr [rcx+1Ch], 100h
0x180038d72  jz      short loc_180038D9A
0x180038d74  mov     rcx, [rcx+10h]
0x180038d78  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180038d7f  mov     edx, 1Fh
0x180038d84  mov     r9d, ebx
0x180038d87  call    WPP_SF_d
0x180038d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038d93  lea     rax, WPP_GLOBAL_Control
0x180038d9a  cmp     rcx, rax
0x180038d9d  jz      short loc_180038DC8
0x180038d9f  test    dword ptr [rcx+1Ch], 100h
0x180038da6  jz      short loc_180038DC8
0x180038da8  mov     r9d, [rbp+NumberOfBytesTransferred]
0x180038dac  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180038db3  mov     rcx, [rcx+10h]
0x180038db7  mov     edx, 20h ; ' '
0x180038dbc  call    WPP_SF_d
0x180038dc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180038dc8  cmp     ebx, 3E5h
0x180038dce  jz      short loc_180038DD8
0x180038dd0  test    ebx, ebx
0x180038dd2  jnz     loc_180038EFB
0x180038dd8  xor     r8d, r8d; bWaitAll
0x180038ddb  mov     [rsp+78h+bAlertable], 0; bAlertable
0x180038de3  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180038de7  lea     rdx, [rbp+hEvent]; lpHandles
0x180038deb  lea     ecx, [r8+2]; nCount
0x180038def  call    cs:__imp_WaitForMultipleObjectsEx
0x180038df6  nop     dword ptr [rax+rax+00h]
0x180038dfb  cmp     eax, 1
0x180038dfe  jnz     loc_18003911F
0x180038e04  mov     rcx, [rdi+78h]; hFile
0x180038e08  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180038e0c  xor     r9d, r9d; bWait
0x180038e0f  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180038e13  call    cs:__imp_GetOverlappedResult
0x180038e1a  nop     dword ptr [rax+rax+00h]
0x180038e1f  test    eax, eax
0x180038e21  jz      short loc_180038E27
0x180038e23  xor     ebx, ebx
0x180038e25  jmp     short loc_180038E35
0x180038e27  call    cs:__imp_GetLastError
0x180038e2e  nop     dword ptr [rax+rax+00h]
0x180038e33  mov     ebx, eax
0x180038e35  mov     rcx, cs:WPP_GLOBAL_Control
0x180038e3c  lea     rax, WPP_GLOBAL_Control
0x180038e43  cmp     rcx, rax
0x180038e46  jz      short loc_180038EA5
0x180038e48  test    dword ptr [rcx+1Ch], 100h
0x180038e4f  jz      short loc_180038E77
0x180038e51  mov     rcx, [rcx+10h]
0x180038e55  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180038e5c  mov     edx, 21h ; '!'
0x180038e61  mov     r9d, ebx
0x180038e64  call    WPP_SF_d
0x180038e69  mov     rcx, cs:WPP_GLOBAL_Control
0x180038e70  lea     rax, WPP_GLOBAL_Control
0x180038e77  cmp     rcx, rax
0x180038e7a  jz      short loc_180038EA5
0x180038e7c  test    dword ptr [rcx+1Ch], 100h
0x180038e83  jz      short loc_180038EA5
0x180038e85  mov     r9d, [rbp+NumberOfBytesTransferred]
0x180038e89  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180038e90  mov     rcx, [rcx+10h]
0x180038e94  mov     edx, 22h ; '"'
0x180038e99  call    WPP_SF_d
0x180038e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038ea5  test    ebx, ebx
0x180038ea7  jnz     short loc_180038EFB
0x180038ea9  mov     r8, [rdi+78h]; void *
0x180038ead  mov     rdx, rsi; Block
0x180038eb0  mov     rcx, rdi; this
0x180038eb3  mov     [rdi+128h], ebx
0x180038eb9  call    ?HandleHTTPHeader@BaseHttpListener@@IEAAJPEAU_HTTP_REQUEST_V2@@PEAX@Z; BaseHttpListener::HandleHTTPHeader(_HTTP_REQUEST_V2 *,void *)
0x180038ebe  test    eax, eax
0x180038ec0  jns     short loc_180038EF1
0x180038ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180038ec9  lea     rdx, WPP_GLOBAL_Control
0x180038ed0  cmp     rcx, rdx
0x180038ed3  jz      short loc_180038EF1
0x180038ed5  test    byte ptr [rcx+1Ch], 1
0x180038ed9  jz      short loc_180038EF1
0x180038edb  mov     rcx, [rcx+10h]
0x180038edf  lea     edx, [rbx+25h]
0x180038ee2  mov     r9d, eax
0x180038ee5  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180038eec  call    WPP_SF_d
0x180038ef1  xor     r15d, r15d
0x180038ef4  xor     esi, esi
0x180038ef6  jmp     loc_18003904A
0x180038efb  cmp     ebx, 0EAh
0x180038f01  jnz     short loc_180038F47
0x180038f03  mov     r12d, [rbp+NumberOfBytesTransferred]
0x180038f07  mov     rcx, r14; Block
0x180038f0a  mov     dword ptr [rdi+128h], 0
0x180038f14  mov     r15, [rsi+10h]
0x180038f18  call    cs:__imp_free
0x180038f1f  nop     dword ptr [rax+rax+00h]
0x180038f24  mov     ecx, r12d; Size
0x180038f27  call    cs:__imp_malloc
0x180038f2e  nop     dword ptr [rax+rax+00h]
0x180038f33  mov     r14, rax
0x180038f36  test    rax, rax
0x180038f39  jz      loc_180039113
0x180038f3f  mov     rsi, rax
0x180038f42  jmp     loc_18003904A
0x180038f47  cmp     ebx, 4CDh
0x180038f4d  jnz     short loc_180038FB0
0x180038f4f  test    r15, r15
0x180038f52  jz      loc_180038FFC
0x180038f58  xor     r15d, r15d
0x180038f5b  test    r14, r14
0x180038f5e  jz      short loc_180038F76
0x180038f60  mov     rcx, r14; Block
0x180038f63  call    cs:__imp_free
0x180038f6a  nop     dword ptr [rax+rax+00h]
0x180038f6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f76  xor     esi, esi
0x180038f78  lea     rax, WPP_GLOBAL_Control
0x180038f7f  cmp     rcx, rax
0x180038f82  jz      loc_18003904A
0x180038f88  test    byte ptr [rcx+1Ch], 1
0x180038f8c  jz      loc_18003904A
0x180038f92  mov     rcx, [rcx+10h]
0x180038f96  lea     edx, [rsi+26h]
0x180038f99  mov     r9d, 4CDh
0x180038f9f  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180038fa6  call    WPP_SF_d
0x180038fab  jmp     loc_18003904A
0x180038fb0  cmp     ebx, 3E3h
0x180038fb6  jz      loc_180039053
0x180038fbc  cmp     ebx, 6
0x180038fbf  jz      loc_180039053
0x180038fc5  cmp     ebx, 45Ah
0x180038fcb  jnz     short loc_180038FFC
0x180038fcd  lea     rax, WPP_GLOBAL_Control
0x180038fd4  cmp     rcx, rax
0x180038fd7  jz      short loc_180038FF4
0x180038fd9  test    byte ptr [rcx+1Ch], 1
0x180038fdd  jz      short loc_180038FF4
0x180038fdf  mov     rcx, [rcx+10h]
0x180038fe3  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180038fea  mov     edx, 27h ; '''
0x180038fef  call    WPP_SF_
0x180038ff4  mov     r13d, 1
0x180038ffa  jmp     short loc_18003904A
0x180038ffc  lea     rax, WPP_GLOBAL_Control
0x180039003  cmp     rcx, rax
0x180039006  jz      short loc_180039026
0x180039008  test    byte ptr [rcx+1Ch], 1
0x18003900c  jz      short loc_180039026
0x18003900e  mov     rcx, [rcx+10h]
0x180039012  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180039019  mov     edx, 28h ; '('
0x18003901e  mov     r9d, ebx
0x180039021  call    WPP_SF_d
0x180039026  mov     eax, [rdi+128h]
0x18003902c  cmp     eax, 5
0x18003902f  jz      short loc_180039053
0x180039031  inc     eax
0x180039033  mov     ecx, 0Ah; dwMilliseconds
0x180039038  mov     [rdi+128h], eax
0x18003903e  call    cs:__imp_Sleep
0x180039045  nop     dword ptr [rax+rax+00h]
0x18003904a  test    r13d, r13d
0x18003904d  jz      loc_180038C9C
0x180039053  lea     r14, WPP_GLOBAL_Control
0x18003905a  mov     dword ptr [rdi+128h], 0
0x180039064  test    rsi, rsi
0x180039067  jz      short loc_180039078
0x180039069  mov     rcx, rsi; Block
0x18003906c  call    cs:__imp_free
0x180039073  nop     dword ptr [rax+rax+00h]
0x180039078  mov     rcx, [rbp+hEvent+8]; hObject
0x18003907c  test    rcx, rcx
0x18003907f  jz      short loc_180039095
0x180039081  call    cs:__imp_CloseHandle
0x180039088  nop     dword ptr [rax+rax+00h]
0x18003908d  mov     [rbp+hEvent+8], 0
0x180039095  mov     rcx, rdi; this
0x180039098  mov     dword ptr [rdi+80h], 0
0x1800390a2  call    ?DecrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::DecrThreadCount(void)
0x1800390a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800390ae  cmp     rcx, r14
0x1800390b1  jz      short loc_1800390D1
0x1800390b3  test    dword ptr [rcx+1Ch], 100h
0x1800390ba  jz      short loc_1800390D1
0x1800390bc  mov     rcx, [rcx+10h]
0x1800390c0  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800390c7  mov     edx, 29h ; ')'
0x1800390cc  call    WPP_SF_
0x1800390d1  mov     eax, ebx
0x1800390d3  add     rsp, 78h
0x1800390d7  pop     r15
0x1800390d9  pop     r14
0x1800390db  pop     r13
  ... truncated ...
```
