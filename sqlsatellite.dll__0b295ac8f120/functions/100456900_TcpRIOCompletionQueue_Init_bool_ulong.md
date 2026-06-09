# TcpRIOCompletionQueue::Init(bool,ulong)

- ea: `0x100456900`
- end: `0x100456c0b`
- name: `?Init@TcpRIOCompletionQueue@@QEAAK_NK@Z`
- size: `779`
- prototype: `unsigned int __fastcall(TcpRIOCompletionQueue *__hidden this, bool, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x100457960`

## callees

- `0x10041da80`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100456900`

## import_xrefs

- `KERNEL32!QueryPerformanceFrequency` at `0x100456982`
- `KERNEL32!QueryPerformanceFrequency` at `0x100456982`
- `KERNEL32!GetLastError` at `0x10045698c`
- `KERNEL32!GetLastError` at `0x10045698c`
- `sqldk!SystemThread_TlsIndex` at `0x100456a5e`
- `sqldk!SystemThread_TlsOffset` at `0x100456a67`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100456a82`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100456a82`
- `WS2_32!__imp_WSAGetLastError` at `0x100456af9`
- `WS2_32!__imp_WSAGetLastError` at `0x100456af9`

## string_xrefs

- `0x1004569de`: `sql\common\dk\sni\src\SNI_IOCompletionQueue.cpp`
- `0x100456931`: `sql\common\dk\sni\src\sni_tcprioprovider.cpp`
- `0x10045693c`: `TcpRIOCompletionQueue::Init`
- `0x10045695c`: `API|SNIpQueue: %p{TcpRIOCompletionQueue*}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TcpRIOCompletionQueue::Init(TcpRIOCompletionQueue *this, char a2, int a3)
{
  unsigned int LastError; // ebx
  const wchar_t *v7; // r9
  __int64 v8; // rbp
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  int Error; // eax
  unsigned int v13; // eax
  __int64 v15; // [rsp+20h] [rbp-88h]
  __int64 v16; // [rsp+28h] [rbp-80h]
  __int64 v17; // [rsp+30h] [rbp-78h]
  _QWORD v18[4]; // [rsp+60h] [rbp-48h] BYREF
  LARGE_INTEGER Frequency; // [rsp+C8h] [rbp+20h] BYREF

  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
      "TcpRIOCompletionQueue::Init",
      299,
      L"API|SNIpQueue: %p{TcpRIOCompletionQueue*}",
      this);
  LastError = 0;
  if ( QueryPerformanceFrequency(&Frequency) )
    *((_QWORD *)this + 2) = ((__int64)((unsigned __int128)(Frequency.QuadPart * (__int128)0x431BDE82D7B634DBLL) >> 64) >> 18)
                          + ((unsigned __int64)((unsigned __int128)(Frequency.QuadPart * (__int128)0x431BDE82D7B634DBLL) >> 64) >> 63)
                          + 1;
  else
    LastError = GetLastError();
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v15) = LastError;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\SNI_IOCompletionQueue.cpp",
      "SNI_PollingIOQueueBase::Init",
      670,
      L"RET|SNI%d{WINERR}\n",
      v15);
  }
  if ( !LastError )
  {
    LastError = CCriticalSectionSOS::Initialize((struct CCriticalSectionSOS **)this + 28);
    if ( !LastError )
    {
      *((_BYTE *)this + 192) = a2;
      *((_DWORD *)this + 52) = a3;
      *((_QWORD *)this + 5) = 0;
      *((_QWORD *)this + 3) = 0;
      *((_QWORD *)this + 4) = 0;
      *((_QWORD *)this + 6) = 0;
      *((_QWORD *)this + 8) = 0;
      *((_QWORD *)this + 9) = 0;
      *((_QWORD *)this + 10) = 0;
      *((_QWORD *)this + 11) = 0;
      *((_DWORD *)this + 40) = 1;
      *((_QWORD *)this + 12) = TcpRIOCompletionQueue::StaticDequeueCompletions;
      *((_QWORD *)this + 13) = this;
      *((_DWORD *)this + 14) = 0;
      v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v9 = *(_QWORD *)(v8 + 256);
      if ( !v9 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v9 = *(_QWORD *)(v8 + 256);
      }
      v10 = *(_QWORD *)(**(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v9 + 992) + 56LL) + 64LL)
                      + 152LL * *((unsigned int *)this + 2)
                      + 8);
      *((_QWORD *)this + 25) = v10;
      v18[0] = 2;
      v18[1] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 48LL))(v10);
      v18[3] = (char *)this + 24;
      v18[2] = this;
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 23) + 48LL))(
              *((unsigned int *)this + 52),
              v18);
      *((_QWORD *)this + 27) = v11;
      if ( !v11 )
      {
        Error = WSAGetLastError();
        LastError = Error;
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v15) = 7;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
            "TcpRIOCompletionQueue::Init",
            333,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v15,
            0,
            Error);
        }
        SNISetLastError(7u, LastError, 0xC3B4u);
      }
      if ( !a2 )
      {
        v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 80LL))(*((_QWORD *)this + 27));
        LastError = v13;
        if ( v13 )
        {
          if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
          {
            LODWORD(v17) = v13;
            LODWORD(v16) = 0;
            LODWORD(v15) = 7;
            SNIXE_SNI_ERROR_ON(
              "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
              "TcpRIOCompletionQueue::Init",
              341,
              L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
              v15,
              v16,
              v17);
          }
          SNISetLastError(7u, LastError, 0xC3B4u);
        }
      }
    }
  }
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v15) = LastError;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
      "TcpRIOCompletionQueue::Init",
      346,
      L"RET|SNI%d{WINERR}\n",
      v15);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON("sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp", "TcpRIOCompletionQueue::Init", 299, v7);
  return LastError;
}

```

## disassembly

```asm
0x100456900  mov     rax, rsp
0x100456903  push    rdi
0x100456904  push    r12
0x100456906  push    r13
0x100456908  push    r14
0x10045690a  push    r15
0x10045690c  sub     rsp, 80h
0x100456913  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x10045691b  mov     [rax+8], rbx
0x10045691f  mov     [rax+10h], rbp
0x100456923  mov     [rax+18h], rsi
0x100456927  mov     edi, r8d
0x10045692a  movzx   r14d, dl
0x10045692e  mov     rsi, rcx
0x100456931  lea     r12, aSqlCommonDkSni_21; "sql\\common\\dk\\sni\\src\\sni_tcpriopr"...
0x100456938  mov     [rax-60h], r12
0x10045693c  lea     r13, aTcpriocompleti_1; "TcpRIOCompletionQueue::Init"
0x100456943  mov     [rax-58h], r13
0x100456947  mov     dword ptr [rax-50h], 12Bh
0x10045694e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100456955  jz      short loc_100456974
0x100456957  mov     [rsp+0A8h+var_88], rcx
0x10045695c  lea     r9, aApiSnipqueuePT; "API|SNIpQueue: %p{TcpRIOCompletionQueue"...
0x100456963  mov     r8d, 12Bh; int
0x100456969  mov     rdx, r13; char *
0x10045696c  mov     rcx, r12; char *
0x10045696f  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x100456974  xor     r15d, r15d
0x100456977  mov     ebx, r15d
0x10045697a  lea     rcx, [rsp+0A8h+Frequency]; lpFrequency
0x100456982  call    cs:__imp_QueryPerformanceFrequency
0x100456988  test    eax, eax
0x10045698a  jnz     short loc_100456996
0x10045698c  call    cs:__imp_GetLastError
0x100456992  mov     ebx, eax
0x100456994  jmp     short loc_1004569BD
0x100456996  mov     rax, 431BDE82D7B634DBh
0x1004569a0  imul    qword ptr [rsp+0A8h+Frequency]
0x1004569a8  sar     rdx, 12h
0x1004569ac  mov     rax, rdx
0x1004569af  shr     rax, 3Fh
0x1004569b3  inc     rax
0x1004569b6  add     rax, rdx
0x1004569b9  mov     [rsi+10h], rax
0x1004569bd  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004569c4  jz      short loc_1004569EA
0x1004569c6  mov     dword ptr [rsp+0A8h+var_88], ebx
0x1004569ca  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x1004569d1  mov     r8d, 29Eh; int
0x1004569d7  lea     rdx, aSniPollingioqu; "SNI_PollingIOQueueBase::Init"
0x1004569de  lea     rcx, aSqlCommonDkSni_8; "sql\\common\\dk\\sni\\src\\SNI_IOComple"...
0x1004569e5  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004569ea  test    ebx, ebx
0x1004569ec  jnz     loc_100456BA8
0x1004569f2  lea     rcx, [rsi+0E0h]; struct CCriticalSectionSOS **
0x1004569f9  call    ?Initialize@CCriticalSectionSOS@@SAKPEAPEAV1@@Z; CCriticalSectionSOS::Initialize(CCriticalSectionSOS * *)
0x1004569fe  mov     ebx, eax
0x100456a00  test    eax, eax
0x100456a02  jnz     loc_100456BA8
0x100456a08  mov     [rsi+0C0h], r14b
0x100456a0f  mov     [rsi+0D0h], edi
0x100456a15  lea     rdi, [rsi+18h]
0x100456a19  mov     [rdi+10h], r15
0x100456a1d  mov     [rdi], r15
0x100456a20  mov     [rdi+8], r15
0x100456a24  mov     [rdi+18h], r15
0x100456a28  mov     [rdi+28h], r15
0x100456a2c  mov     [rdi+30h], r15
0x100456a30  mov     [rdi+38h], r15
0x100456a34  mov     [rdi+40h], r15
0x100456a38  mov     dword ptr [rdi+88h], 1
0x100456a42  lea     rax, ?StaticDequeueCompletions@TcpRIOCompletionQueue@@CAXPEAVSOS_IOCompRequest@@@Z; TcpRIOCompletionQueue::StaticDequeueCompletions(SOS_IOCompRequest *)
0x100456a49  mov     [rdi+48h], rax
0x100456a4d  mov     [rdi+50h], rsi
0x100456a51  mov     [rdi+20h], r15d
0x100456a55  mov     rdx, gs:58h
0x100456a5e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100456a65  mov     ecx, [rax]
0x100456a67  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100456a6e  mov     ebp, [rax]
0x100456a70  add     rbp, [rdx+rcx*8]
0x100456a74  mov     rax, [rbp+100h]
0x100456a7b  test    rax, rax
0x100456a7e  jnz     short loc_100456A8F
0x100456a80  xor     ecx, ecx
0x100456a82  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100456a88  mov     rax, [rbp+100h]
0x100456a8f  mov     rax, [rax+3E0h]
0x100456a96  mov     rcx, [rax+38h]
0x100456a9a  mov     rdx, [rcx+40h]
0x100456a9e  mov     eax, [rsi+8]
0x100456aa1  imul    rcx, rax, 98h
0x100456aa8  add     rcx, [rdx]
0x100456aab  mov     rcx, [rcx+8]
0x100456aaf  mov     [rsi+0C8h], rcx
0x100456ab6  mov     [rsp+0A8h+var_48], 2
0x100456abf  mov     rax, [rcx]
0x100456ac2  call    qword ptr [rax+30h]
0x100456ac5  mov     [rsp+0A8h+var_40], rax
0x100456aca  mov     [rsp+0A8h+var_30], rdi
0x100456acf  mov     [rsp+0A8h+var_38], rsi
0x100456ad4  mov     rax, [rsi+0B8h]
0x100456adb  mov     r8, [rax]
0x100456ade  lea     rdx, [rsp+0A8h+var_48]
0x100456ae3  mov     ecx, [rsi+0D0h]
0x100456ae9  call    qword ptr [r8+30h]
0x100456aed  mov     [rsi+0D8h], rax
0x100456af4  test    rax, rax
0x100456af7  jnz     short loc_100456B45
0x100456af9  call    cs:__imp_WSAGetLastError
0x100456aff  mov     ebx, eax
0x100456b01  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100456b08  jz      short loc_100456B33
0x100456b0a  mov     dword ptr [rsp+0A8h+var_78], eax
0x100456b0e  mov     dword ptr [rsp+0A8h+var_80], r15d
0x100456b13  mov     dword ptr [rsp+0A8h+var_88], 7
0x100456b1b  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100456b22  mov     r8d, 14Dh; int
0x100456b28  mov     rdx, r13; char *
0x100456b2b  mov     rcx, r12; char *
0x100456b2e  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100456b33  mov     r8d, 0C3B4h
0x100456b39  mov     edx, ebx
0x100456b3b  mov     ecx, 7
0x100456b40  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100456b45  test    r14b, r14b
0x100456b48  jnz     short loc_100456BA8
0x100456b4a  mov     rax, [rsi+0B8h]
0x100456b51  mov     rdx, [rax]
0x100456b54  mov     rcx, [rsi+0D8h]
0x100456b5b  call    qword ptr [rdx+50h]
0x100456b5e  mov     ebx, eax
0x100456b60  test    eax, eax
0x100456b62  jz      short loc_100456BA8
0x100456b64  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100456b6b  jz      short loc_100456B96
0x100456b6d  mov     dword ptr [rsp+0A8h+var_78], eax
0x100456b71  mov     dword ptr [rsp+0A8h+var_80], r15d
0x100456b76  mov     dword ptr [rsp+0A8h+var_88], 7
0x100456b7e  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x100456b85  mov     r8d, 155h; int
0x100456b8b  mov     rdx, r13; char *
0x100456b8e  mov     rcx, r12; char *
0x100456b91  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100456b96  mov     r8d, 0C3B4h
0x100456b9c  mov     edx, ebx
0x100456b9e  mov     ecx, 7
0x100456ba3  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100456ba8  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100456baf  jz      short loc_100456BCE
0x100456bb1  mov     dword ptr [rsp+0A8h+var_88], ebx
0x100456bb5  lea     r9, aRetSniDWinerr; "RET|SNI%d{WINERR}\n"
0x100456bbc  mov     r8d, 15Ah; int
0x100456bc2  mov     rdx, r13; char *
0x100456bc5  mov     rcx, r12; char *
0x100456bc8  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100456bcd  nop
0x100456bce  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100456bd5  jz      short loc_100456BE8
0x100456bd7  mov     r8d, 12Bh; int
0x100456bdd  mov     rdx, r13; char *
0x100456be0  mov     rcx, r12; char *
0x100456be3  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x100456be8  mov     eax, ebx
0x100456bea  lea     r11, [rsp+0A8h+var_28]
0x100456bf2  mov     rbx, [r11+30h]
0x100456bf6  mov     rbp, [r11+38h]
0x100456bfa  mov     rsi, [r11+40h]
0x100456bfe  mov     rsp, r11
0x100456c01  pop     r15
0x100456c03  pop     r14
0x100456c05  pop     r13
0x100456c07  pop     r12
0x100456c09  pop     rdi
0x100456c0a  retn
```
