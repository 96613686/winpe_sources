# PAL_System_CondWait

- ea: `0x180036efc`
- end: `0x180037201`
- name: `PAL_System_CondWait`
- size: `773`
- prototype: `__int64 __usercall@<rax>(HANDLE *pHandles@<rcx>, DWORD nCount@<edx>, BOOL bWaitAll, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003ea20`

## callees

- `0x180001008`
- `0x1800010b0`
- `0x180036efc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036f33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037046`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036f33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037046`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036f3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036f3c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180036f8d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180036f8d`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180036fee`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180037023`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180036fee`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180037023`
- `USER32!PeekMessageW` at `0x180036fb4`
- `USER32!PeekMessageW` at `0x180036fb4`
- `USER32!DispatchMessageW` at `0x180036fcf`
- `USER32!DispatchMessageW` at `0x180036fcf`

## string_xrefs

- `0x180037079`: `Thread: 0x%x got a WM_QUIT`
- `0x1800370d6`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18003711d`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x180037132`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`

## pseudocode

```c
__int64 __fastcall PAL_System_CondWait(
        HANDLE *pHandles,
        DWORD nCount,
        const char *a3,
        DWORD a4,
        BOOL bWaitAll,
        int a6,
        DWORD *a7)
{
  DWORD *v10; // rdi
  unsigned int v11; // ebx
  DWORD v12; // ecx
  int v13; // r8d
  int v14; // r9d
  unsigned int v15; // r12d
  unsigned int i; // r15d
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  DWORD v20; // eax
  DWORD TickCount; // eax
  DWORD v22; // ecx
  const char *v24; // [rsp+50h] [rbp-31h] BYREF
  const char *v25; // [rsp+58h] [rbp-29h] BYREF
  tagMSG Msg; // [rsp+60h] [rbp-21h] BYREF
  const char *v27; // [rsp+D0h] [rbp+4Fh] BYREF
  const char *v28; // [rsp+E0h] [rbp+5Fh] BYREF
  DWORD dwMilliseconds; // [rsp+E8h] [rbp+67h] BYREF

  dwMilliseconds = a4;
  v28 = a3;
  memset(&Msg, 0, sizeof(Msg));
  LODWORD(v28) = GetTickCount();
  LODWORD(v27) = GetCurrentThreadId();
  if ( pHandles && (v10 = a7) != 0 && nCount )
  {
    if ( bWaitAll )
      *a7 = 0;
    v11 = -2147467259;
    if ( a6 )
    {
      v12 = WaitForMultipleObjects(nCount, pHandles, bWaitAll, a4);
    }
    else
    {
      v15 = a4;
      while ( 1 )
      {
LABEL_9:
        for ( i = 0; i < 0x64; ++i )
        {
          if ( !PeekMessageW(&Msg, 0, 0, 0, 1u) )
            break;
          if ( Msg.message == 18 )
          {
            if ( (unsigned int)dword_18005C008 > 4 )
            {
              dwMilliseconds = (unsigned int)v27;
              v28 = "Thread: 0x%x got a WM_QUIT";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v17,
                (unsigned int)byte_1800549A9,
                v18,
                v19,
                (__int64)&v28,
                (__int64)&dwMilliseconds);
            }
            return (unsigned int)-2092629812;
          }
          DispatchMessageW(&Msg);
        }
        v12 = MsgWaitForMultipleObjectsEx(nCount, pHandles, 0, 0, 6u);
        if ( v12 <= nCount - 1 )
          goto LABEL_26;
        if ( v12 != 192 )
        {
          v20 = MsgWaitForMultipleObjectsEx(nCount, pHandles, dwMilliseconds, 0x1CFFu, 6u);
          v12 = v20;
          if ( v20 != 192 )
          {
            if ( v20 != nCount )
              goto LABEL_26;
            if ( v15 != -1 )
              break;
          }
        }
      }
      TickCount = GetTickCount();
      v22 = TickCount - (_DWORD)v28;
      if ( TickCount - (unsigned int)v28 < v15 )
      {
        v15 -= v22;
        LODWORD(v28) = TickCount;
        goto LABEL_9;
      }
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        dwMilliseconds = 242;
        v25 = "Timeout processing window messages";
        v27 = "PAL_System_CondWait";
        v24 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
        LODWORD(v28) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v22,
          (unsigned int)byte_180054A19,
          v13,
          v14,
          (__int64)&v25,
          (__int64)&v28,
          (__int64)&v24,
          (__int64)&dwMilliseconds,
          (__int64)&v27);
      }
      v12 = 258;
    }
LABEL_26:
    if ( v12 > nCount - 1 )
    {
      if ( v12 < 0x80 || v12 > nCount + 127 )
      {
        if ( v12 == 258 )
        {
          *v10 = 0;
          return (unsigned int)-2092629813;
        }
        else if ( (unsigned int)dword_18005C008 > 2 )
        {
          v27 = "PAL_System_CondWait";
          v24 = "Wait Failed with unknown error";
          dwMilliseconds = 295;
          v25 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
          LODWORD(v28) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)byte_180054AA3,
            v13,
            v14,
            (__int64)&v24,
            (__int64)&v28,
            (__int64)&v25,
            (__int64)&dwMilliseconds,
            (__int64)&v27);
        }
      }
      else
      {
        if ( !bWaitAll )
          *v10 = v12 - 128;
        return (unsigned int)-2092629814;
      }
    }
    else
    {
      if ( !bWaitAll )
        *v10 = v12;
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v11;
}

```

## disassembly

```asm
0x180036efc  mov     [rsp-8+dwMilliseconds], r9d
0x180036f01  mov     [rsp-8+arg_10], r8
0x180036f06  push    rbp
0x180036f07  push    rbx
0x180036f08  push    rsi
0x180036f09  push    rdi
0x180036f0a  push    r12
0x180036f0c  push    r13
0x180036f0e  push    r15
0x180036f10  lea     rbp, [rsp-0Fh]
0x180036f15  sub     rsp, 90h
0x180036f1c  xorps   xmm0, xmm0
0x180036f1f  mov     r15d, r9d
0x180036f22  movups  xmmword ptr [rbp+3Fh+Msg.hwnd], xmm0
0x180036f26  mov     esi, edx
0x180036f28  mov     r13, rcx
0x180036f2b  movups  xmmword ptr [rbp+3Fh+Msg.wParam], xmm0
0x180036f2f  movups  xmmword ptr [rbp+3Fh+Msg.time], xmm0
0x180036f33  call    cs:__imp_GetTickCount
0x180036f39  mov     dword ptr [rbp+3Fh+arg_10], eax
0x180036f3c  call    cs:__imp_GetCurrentThreadId
0x180036f42  mov     dword ptr [rbp+3Fh+arg_0], eax
0x180036f45  test    r13, r13
0x180036f48  jz      loc_1800371E8
0x180036f4e  mov     rdi, [rbp+3Fh+arg_30]
0x180036f52  test    rdi, rdi
0x180036f55  jz      loc_1800371E8
0x180036f5b  test    esi, esi
0x180036f5d  jz      loc_1800371E8
0x180036f63  cmp     [rbp+3Fh+bWaitAll], 0
0x180036f67  jz      short loc_180036F6F
0x180036f69  mov     dword ptr [rdi], 0
0x180036f6f  cmp     [rbp+3Fh+arg_28], 0
0x180036f73  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x180036f7a  mov     ebx, 80004005h
0x180036f7f  jz      short loc_180036F9A
0x180036f81  mov     r8d, [rbp+3Fh+bWaitAll]; bWaitAll
0x180036f85  mov     r9d, r15d; dwMilliseconds
0x180036f88  mov     rdx, r13; lpHandles
0x180036f8b  mov     ecx, esi; nCount
0x180036f8d  call    cs:__imp_WaitForMultipleObjects
0x180036f93  mov     ecx, eax
0x180036f95  jmp     loc_180037132
0x180036f9a  mov     r12d, r15d
0x180036f9d  xor     r15d, r15d
0x180036fa0  xor     r9d, r9d; wMsgFilterMax
0x180036fa3  mov     [rsp+0C0h+wRemoveMsg], 1; wRemoveMsg
0x180036fab  xor     r8d, r8d; wMsgFilterMin
0x180036fae  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x180036fb2  xor     edx, edx; hWnd
0x180036fb4  call    cs:__imp_PeekMessageW
0x180036fba  test    eax, eax
0x180036fbc  jz      short loc_180036FDB
0x180036fbe  cmp     [rbp+3Fh+Msg.message], 12h
0x180036fc2  jz      loc_180037061
0x180036fc8  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x180036fcc  inc     r15d
0x180036fcf  call    cs:__imp_DispatchMessageW
0x180036fd5  cmp     r15d, 64h ; 'd'
0x180036fd9  jb      short loc_180036FA0
0x180036fdb  xor     r9d, r9d; dwWakeMask
0x180036fde  mov     [rsp+0C0h+wRemoveMsg], 6; dwFlags
0x180036fe6  xor     r8d, r8d; dwMilliseconds
0x180036fe9  mov     rdx, r13; pHandles
0x180036fec  mov     ecx, esi; nCount
0x180036fee  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x180036ff4  mov     ecx, eax
0x180036ff6  lea     eax, [rsi-1]
0x180036ff9  cmp     ecx, eax
0x180036ffb  jbe     loc_18003712B
0x180037001  mov     r15d, 0C0h
0x180037007  cmp     ecx, r15d
0x18003700a  jz      short loc_180036F9D
0x18003700c  mov     r8d, [rbp+3Fh+dwMilliseconds]; dwMilliseconds
0x180037010  mov     r9d, 1CFFh; dwWakeMask
0x180037016  mov     rdx, r13; pHandles
0x180037019  mov     [rsp+0C0h+wRemoveMsg], 6; dwFlags
0x180037021  mov     ecx, esi; nCount
0x180037023  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x180037029  mov     ecx, eax
0x18003702b  cmp     eax, r15d
0x18003702e  jz      loc_180036F9D
0x180037034  cmp     eax, esi
0x180037036  jnz     loc_18003712B
0x18003703c  cmp     r12d, 0FFFFFFFFh
0x180037040  jz      loc_180036F9D
0x180037046  call    cs:__imp_GetTickCount
0x18003704c  mov     ecx, eax
0x18003704e  sub     ecx, dword ptr [rbp+3Fh+arg_10]
0x180037051  cmp     ecx, r12d
0x180037054  jnb     short loc_1800370A5
0x180037056  sub     r12d, ecx
0x180037059  mov     dword ptr [rbp+3Fh+arg_10], eax
0x18003705c  jmp     loc_180036F9D
0x180037061  mov     eax, cs:dword_18005C008
0x180037067  cmp     eax, 4
0x18003706a  jbe     short loc_18003709B
0x18003706c  mov     eax, dword ptr [rbp+3Fh+arg_0]
0x18003706f  lea     rdx, byte_1800549A9
0x180037076  mov     [rbp+3Fh+dwMilliseconds], eax
0x180037079  lea     rax, aThread0xXGotAW; "Thread: 0x%x got a WM_QUIT"
0x180037080  mov     [rbp+3Fh+arg_10], rax
0x180037084  lea     rax, [rbp+3Fh+dwMilliseconds]
0x180037088  mov     [rsp+0C0h+var_98], rax
0x18003708d  lea     rax, [rbp+3Fh+arg_10]
0x180037091  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x180037096  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003709b  mov     ebx, 834500CCh
0x1800370a0  jmp     loc_1800371ED
0x1800370a5  mov     eax, cs:dword_18005C008
0x1800370ab  cmp     eax, 2
0x1800370ae  jbe     short loc_180037116
0x1800370b0  lea     rax, aTimeoutProcess; "Timeout processing window messages"
0x1800370b7  mov     [rbp+3Fh+dwMilliseconds], 0F2h
0x1800370be  mov     [rbp+3Fh+var_68], rax
0x1800370c2  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x1800370c9  lea     rax, [rbp+3Fh+arg_0]
0x1800370cd  mov     [rbp+3Fh+arg_0], r12
0x1800370d1  mov     [rsp+0C0h+var_80], rax
0x1800370d6  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800370dd  lea     rax, [rbp+3Fh+dwMilliseconds]
0x1800370e1  mov     [rbp+3Fh+var_70], r15
0x1800370e5  mov     [rsp+0C0h+var_88], rax
0x1800370ea  lea     rdx, byte_180054A19
0x1800370f1  lea     rax, [rbp+3Fh+var_70]
0x1800370f5  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x1800370f8  mov     [rsp+0C0h+var_90], rax
0x1800370fd  lea     rax, [rbp+3Fh+arg_10]
0x180037101  mov     [rsp+0C0h+var_98], rax
0x180037106  lea     rax, [rbp+3Fh+var_68]
0x18003710a  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x18003710f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180037114  jmp     short loc_180037124
0x180037116  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x18003711d  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180037124  mov     ecx, 102h
0x180037129  jmp     short loc_180037139
0x18003712b  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x180037132  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180037139  lea     eax, [rsi-1]
0x18003713c  cmp     ecx, eax
0x18003713e  ja      short loc_18003714F
0x180037140  cmp     [rbp+3Fh+bWaitAll], 0
0x180037144  jnz     short loc_180037148
0x180037146  mov     [rdi], ecx
0x180037148  xor     ebx, ebx
0x18003714a  jmp     loc_1800371ED
0x18003714f  cmp     ecx, 80h
0x180037155  jb      short loc_180037170
0x180037157  lea     eax, [rsi+7Fh]
0x18003715a  cmp     ecx, eax
0x18003715c  ja      short loc_180037170
0x18003715e  cmp     [rbp+3Fh+bWaitAll], 0
0x180037162  jnz     short loc_180037169
0x180037164  lea     eax, [rcx-80h]
0x180037167  mov     [rdi], eax
0x180037169  mov     ebx, 834500CAh
0x18003716e  jmp     short loc_1800371ED
0x180037170  cmp     ecx, 102h
0x180037176  jnz     short loc_180037185
0x180037178  mov     dword ptr [rdi], 0
0x18003717e  mov     ebx, 834500CBh
0x180037183  jmp     short loc_1800371ED
0x180037185  mov     eax, cs:dword_18005C008
0x18003718b  cmp     eax, 2
0x18003718e  jbe     short loc_1800371ED
0x180037190  lea     rax, aWaitFailedWith; "Wait Failed with unknown error"
0x180037197  mov     [rbp+3Fh+arg_0], r12
0x18003719b  mov     [rbp+3Fh+var_70], rax
0x18003719f  lea     rdx, byte_180054AA3
0x1800371a6  lea     rax, [rbp+3Fh+arg_0]
0x1800371aa  mov     [rbp+3Fh+dwMilliseconds], 127h
0x1800371b1  mov     [rsp+0C0h+var_80], rax
0x1800371b6  lea     rax, [rbp+3Fh+dwMilliseconds]
0x1800371ba  mov     [rsp+0C0h+var_88], rax
0x1800371bf  lea     rax, [rbp+3Fh+var_68]
0x1800371c3  mov     [rsp+0C0h+var_90], rax
0x1800371c8  lea     rax, [rbp+3Fh+arg_10]
0x1800371cc  mov     [rsp+0C0h+var_98], rax
0x1800371d1  lea     rax, [rbp+3Fh+var_70]
0x1800371d5  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x1800371da  mov     [rbp+3Fh+var_68], r15
0x1800371de  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x1800371e1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800371e6  jmp     short loc_1800371ED
0x1800371e8  mov     ebx, 80070057h
0x1800371ed  mov     eax, ebx
0x1800371ef  add     rsp, 90h
0x1800371f6  pop     r15
0x1800371f8  pop     r13
0x1800371fa  pop     r12
0x1800371fc  pop     rdi
0x1800371fd  pop     rsi
0x1800371fe  pop     rbx
0x1800371ff  pop     rbp
0x180037200  retn
```
