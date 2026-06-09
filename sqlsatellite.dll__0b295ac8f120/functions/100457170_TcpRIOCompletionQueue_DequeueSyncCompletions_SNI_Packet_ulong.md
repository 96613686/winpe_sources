# TcpRIOCompletionQueue::DequeueSyncCompletions(SNI_Packet *,ulong)

- ea: `0x100457170`
- end: `0x1004575ce`
- name: `?DequeueSyncCompletions@TcpRIOCompletionQueue@@QEAAKPEAVSNI_Packet@@K@Z`
- size: `1118`
- prototype: `unsigned int __fastcall(TcpRIOCompletionQueue *__hidden this, struct SNI_Packet *, unsigned int)`
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x100456810`
- `0x100458510`
- `0x100458b90`
- `0x1004591d0`

## callees

- `0x10041d520`
- `0x10041d950`
- `0x10042b7f0`
- `0x10042b9b0`
- `0x10042c270`
- `0x10042c430`
- `0x1004349f0`
- `0x100456db0`
- `0x100457170`
- `0x100486af0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1004572c7`
- `KERNEL32!QueryPerformanceCounter` at `0x1004572c7`
- `KERNEL32!GetLastError` at `0x100457395`
- `KERNEL32!GetLastError` at `0x100457395`
- `sqldk!SystemThread_TlsIndex` at `0x1004571fe`
- `sqldk!SystemThread_TlsOffset` at `0x100457207`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457225`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100457225`
- `WS2_32!__imp_WSAGetLastError` at `0x1004573b6`
- `WS2_32!__imp_WSAGetLastError` at `0x1004573b6`

## string_xrefs

- `0x1004571af`: `sql\common\dk\sni\src\sni_tcprioprovider.cpp`
- `0x10045737d`: `sql\common\dk\sni\src\sni_tcprioprovider.cpp`
- `0x1004573f0`: `sql\common\dk\sni\src\sni_tcprioprovider.cpp`
- `0x100457479`: `sql\common\dk\sni\src\sni_tcprioprovider.cpp`
- `0x1004574d4`: `sql\common\dk\sni\src\sni_tcprioprovider.cpp`
- `0x100457517`: `sql\common\dk\sni\src\sni_tcprioprovider.cpp`
- `0x100457571`: `sql\common\dk\sni\src\sni_tcprioprovider.cpp`
- `0x100457594`: `sql\common\dk\sni\src\sni_tcprioprovider.cpp`
- `0x1004571dd`: `API|SNIpQueue: %p{TcpRIOCompletionQueue*}`
- `0x100457369`: `API|SNISyncComp %d{WINERR},%p{packet},%d{type}\n`
- `0x1004574c0`: `API|SNIAlready queued\n`
- `0x1004571bb`: `TcpRIOCompletionQueue::DequeueSyncCompletions`
- `0x100457376`: `TcpRIOCompletionQueue::DequeueSyncCompletions`
- `0x1004573e9`: `TcpRIOCompletionQueue::DequeueSyncCompletions`
- `0x100457472`: `TcpRIOCompletionQueue::DequeueSyncCompletions`
- `0x1004574cd`: `TcpRIOCompletionQueue::DequeueSyncCompletions`
- `0x100457510`: `TcpRIOCompletionQueue::DequeueSyncCompletions`
- `0x10045756a`: `TcpRIOCompletionQueue::DequeueSyncCompletions`
- `0x10045758d`: `TcpRIOCompletionQueue::DequeueSyncCompletions`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TcpRIOCompletionQueue::DequeueSyncCompletions(
        TcpRIOCompletionQueue *this,
        struct SNI_Packet *a2,
        unsigned int a3,
        const wchar_t *a4)
{
  __int64 v4; // rbp
  __int64 v7; // rbx
  __int64 v8; // rcx
  bool v9; // r13
  unsigned int v10; // r15d
  unsigned int Status; // r14d
  int v12; // r12d
  LONGLONG v13; // rbx
  int v14; // eax
  LARGE_INTEGER v15; // rax
  __int64 v16; // rbp
  struct _RIORESULT *v17; // rbx
  __int64 v18; // r8
  struct SNI_Packet *v19; // rdx
  int Error; // eax
  signed __int32 v21; // ebx
  unsigned int v22; // eax
  __int64 v24; // [rsp+20h] [rbp-228h]
  __int64 v25; // [rsp+28h] [rbp-220h]
  __int64 v26; // [rsp+30h] [rbp-218h]
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-208h] BYREF
  __int64 v28; // [rsp+48h] [rbp-200h]
  LONGLONG v29; // [rsp+50h] [rbp-1F8h]
  __int64 v30; // [rsp+58h] [rbp-1F0h]
  const char *v31; // [rsp+60h] [rbp-1E8h]
  const char *v32; // [rsp+68h] [rbp-1E0h]
  int v33; // [rsp+70h] [rbp-1D8h]
  struct _RIORESULT v34; // [rsp+80h] [rbp-1C8h] BYREF

  v30 = -2;
  v4 = a3;
  v31 = "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp";
  v32 = "TcpRIOCompletionQueue::DequeueSyncCompletions";
  v33 = 573;
  if ( (g_XeSniPkg_enabledBitmap & 0x40) != 0 )
    SNIXE_SNI_ENTER_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
      "TcpRIOCompletionQueue::DequeueSyncCompletions",
      573,
      L"API|SNIpQueue: %p{TcpRIOCompletionQueue*}",
      this);
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v8 = *(_QWORD *)(v7 + 256);
  v28 = v8;
  if ( !v8 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v8 = *(_QWORD *)(v7 + 256);
    v28 = v8;
  }
  v9 = (*(_DWORD *)(v8 + 800) & 0x200000) == 0;
  if ( (*(_DWORD *)(v8 + 800) & 0x200000) == 0 )
    *(_DWORD *)(v8 + 800) |= 0x200000u;
  v10 = 0;
  Status = 997;
  v12 = 0;
  PerformanceCount.QuadPart = 0;
  v13 = 0;
  v29 = 0;
  if ( v9 )
  {
    CCriticalSectionSOS::Enter(*((CCriticalSectionSOS **)this + 28));
    while ( 1 )
    {
      v14 = (*(__int64 (__fastcall **)(_QWORD, struct _RIORESULT *, __int64))(**((_QWORD **)this + 23) + 64LL))(
              *((_QWORD *)this + 27),
              &v34,
              16);
      v12 = v14;
      if ( v14 )
        break;
      if ( !(_DWORD)v4 )
        goto LABEL_14;
      if ( !QueryPerformanceCounter(&PerformanceCount) )
      {
        GetLastError();
        goto LABEL_28;
      }
      if ( v13 )
      {
LABEL_14:
        v15 = PerformanceCount;
      }
      else
      {
        v15 = PerformanceCount;
        v13 = PerformanceCount.QuadPart + *((_QWORD *)this + 2) * v4;
        v29 = v13;
      }
      if ( v13 <= v15.QuadPart )
        goto LABEL_16;
    }
    if ( v14 != -1 )
      goto LABEL_16;
LABEL_28:
    SOS_UnfairRecursiveMutexExtendedGuarantee::Release(*(SOS_UnfairRecursiveMutexExtendedGuarantee **)(*((_QWORD *)this + 28) + 8LL));
    Error = WSAGetLastError();
    v10 = Error;
    if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
    {
      LODWORD(v24) = 7;
      SNIXE_SNI_ERROR_ON(
        "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
        "TcpRIOCompletionQueue::DequeueSyncCompletions",
        711,
        L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
        v24,
        0,
        Error);
    }
    SNISetLastError(7, v10, 50100);
    goto LABEL_47;
  }
LABEL_16:
  v16 = v12;
  if ( v12 > 0 )
  {
    v17 = &v34;
    do
    {
      v18 = v17->RequestContext & 3;
      v19 = (struct SNI_Packet *)(v17->RequestContext & 0xFFFFFFFFFFFFFFFCuLL);
      if ( v19 != a2 || (_DWORD)v18 == 1 )
      {
        TcpRIOCompletionQueue::HandleCompletion(v17, v19, v18);
        ++*((_QWORD *)this + 31);
      }
      else
      {
        Status = v17->Status;
        if ( !v17->Status && !*((_DWORD *)a2 + 61) )
          *((_DWORD *)a2 + 44) += v17->BytesTransferred;
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
        {
          LODWORD(v26) = *((_DWORD *)a2 + 61);
          LODWORD(v24) = Status;
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
            "TcpRIOCompletionQueue::DequeueSyncCompletions",
            670,
            L"API|SNISyncComp %d{WINERR},%p{packet},%d{type}\n",
            v24,
            a2,
            v26);
        }
        ++*((_QWORD *)this + 29);
      }
      ++v17;
      --v16;
    }
    while ( v16 );
  }
  if ( v9 )
    SOS_UnfairRecursiveMutexExtendedGuarantee::Release(*(SOS_UnfairRecursiveMutexExtendedGuarantee **)(*((_QWORD *)this + 28) + 8LL));
  v21 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 64, -v12);
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v24) = v21 - v12;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
      "TcpRIOCompletionQueue::DequeueSyncCompletions",
      687,
      L"API|SNI%d{cOldPending - cDequeued}\n",
      v24);
  }
  if ( v21 > v12 )
  {
    _mm_lfence();
    v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 80LL))(*((_QWORD *)this + 27));
    v10 = v22;
    if ( v22 )
    {
      if ( v22 == 10037 )
      {
        if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
          SNIXE_SNI_TRACE_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
            "TcpRIOCompletionQueue::DequeueSyncCompletions",
            696,
            L"API|SNIAlready queued\n");
        v10 = 0;
      }
      else
      {
        if ( (g_XeSniPkg_enabledBitmap & 2) != 0 )
        {
          LODWORD(v26) = v22;
          LODWORD(v25) = 0;
          LODWORD(v24) = 7;
          SNIXE_SNI_ERROR_ON(
            "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
            "TcpRIOCompletionQueue::DequeueSyncCompletions",
            701,
            L"ERR|SNIProviderNum: %d{ProviderNum}, SNIError: %d{SNIError}, NativeError: %d{WINERR}\n",
            v24,
            v25,
            v26);
        }
        SNISetLastError(7, v10, 50100);
      }
    }
  }
  if ( v9 )
LABEL_47:
    *(_DWORD *)(v28 + 800) &= ~0x200000u;
  if ( (g_XeSniPkg_enabledBitmap & 1) != 0 )
  {
    LODWORD(v25) = v10;
    LODWORD(v24) = Status;
    SNIXE_SNI_TRACE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
      "TcpRIOCompletionQueue::DequeueSyncCompletions",
      721,
      L"RET|SNI%d{WINERR},%d{DQWINERR}\n",
      v24,
      v25);
  }
  if ( (g_XeSniPkg_enabledBitmap & 0x80u) != 0 )
    SNIXE_SNI_LEAVE_ON(
      "sql\\common\\dk\\sni\\src\\sni_tcprioprovider.cpp",
      "TcpRIOCompletionQueue::DequeueSyncCompletions",
      573,
      a4);
  return Status;
}

```

## disassembly

```asm
0x100457170  push    rbp
0x100457172  push    rsi
0x100457173  push    rdi
0x100457174  push    r12
0x100457176  push    r13
0x100457178  push    r14
0x10045717a  push    r15
0x10045717c  sub     rsp, 210h
0x100457183  mov     [rsp+248h+var_1F0], 0FFFFFFFFFFFFFFFEh
0x10045718c  mov     [rsp+248h+arg_10], rbx
0x100457194  mov     rax, cs:__security_cookie
0x10045719b  xor     rax, rsp
0x10045719e  mov     [rsp+248h+var_48], rax
0x1004571a6  mov     ebp, r8d
0x1004571a9  mov     rsi, rdx
0x1004571ac  mov     rdi, rcx
0x1004571af  lea     rax, aSqlCommonDkSni_21; "sql\\common\\dk\\sni\\src\\sni_tcpriopr"...
0x1004571b6  mov     [rsp+248h+var_1E8], rax
0x1004571bb  lea     rcx, aTcpriocompleti; "TcpRIOCompletionQueue::DequeueSyncCompl"...
0x1004571c2  mov     [rsp+248h+var_1E0], rcx
0x1004571c7  mov     [rsp+248h+var_1D8], 23Dh
0x1004571cf  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 40h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004571d6  jz      short loc_1004571F5
0x1004571d8  mov     [rsp+248h+var_228], rdi
0x1004571dd  lea     r9, aApiSnipqueuePT; "API|SNIpQueue: %p{TcpRIOCompletionQueue"...
0x1004571e4  mov     r8d, 23Dh; int
0x1004571ea  mov     rdx, rcx; char *
0x1004571ed  mov     rcx, rax; char *
0x1004571f0  call    ?SNIXE_SNI_ENTER_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ENTER_ON(char const *,char const *,int,wchar_t const *,...)
0x1004571f5  mov     rdx, gs:58h
0x1004571fe  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100457205  mov     ecx, [rax]
0x100457207  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10045720e  mov     ebx, [rax]
0x100457210  add     rbx, [rdx+rcx*8]
0x100457214  mov     rcx, [rbx+100h]
0x10045721b  mov     [rsp+248h+var_200], rcx
0x100457220  test    rcx, rcx
0x100457223  jnz     short loc_100457237
0x100457225  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10045722b  mov     rcx, [rbx+100h]
0x100457232  mov     [rsp+248h+var_200], rcx
0x100457237  mov     eax, [rcx+320h]
0x10045723d  mov     r13d, eax
0x100457240  shr     r13d, 15h
0x100457244  not     r13b
0x100457247  and     r13b, 1
0x10045724b  jz      short loc_100457257
0x10045724d  bts     eax, 15h
0x100457251  mov     [rcx+320h], eax
0x100457257  xor     r15d, r15d
0x10045725a  mov     r14d, 3E5h
0x100457260  xor     r12d, r12d
0x100457263  xor     eax, eax
0x100457265  mov     qword ptr [rsp+248h+PerformanceCount], rax
0x10045726a  xor     ebx, ebx
0x10045726c  mov     [rsp+248h+var_1F8], rbx
0x100457271  test    r13b, r13b
0x100457274  jz      loc_1004572FB
0x10045727a  mov     rcx, [rdi+0E0h]; this
0x100457281  call    ?Enter@CCriticalSectionSOS@@QEAAXXZ; CCriticalSectionSOS::Enter(void)
0x100457286  nop     word ptr [rax+rax+00000000h]
0x100457290  mov     rax, [rdi+0B8h]
0x100457297  mov     r9, [rax]
0x10045729a  mov     r8d, 10h
0x1004572a0  lea     rdx, [rsp+248h+var_1C8]
0x1004572a8  mov     rcx, [rdi+0D8h]
0x1004572af  call    qword ptr [r9+40h]
0x1004572b3  mov     r12d, eax
0x1004572b6  test    eax, eax
0x1004572b8  jnz     loc_10045739D
0x1004572be  test    ebp, ebp
0x1004572c0  jz      short loc_1004572F1
0x1004572c2  lea     rcx, [rsp+248h+PerformanceCount]; lpPerformanceCount
0x1004572c7  call    cs:__imp_QueryPerformanceCounter
0x1004572cd  test    eax, eax
0x1004572cf  jz      loc_100457395
0x1004572d5  test    rbx, rbx
0x1004572d8  jnz     short loc_1004572F1
0x1004572da  mov     rbx, rbp
0x1004572dd  imul    rbx, [rdi+10h]
0x1004572e2  mov     rax, qword ptr [rsp+248h+PerformanceCount]
0x1004572e7  add     rbx, rax
0x1004572ea  mov     [rsp+248h+var_1F8], rbx
0x1004572ef  jmp     short loc_1004572F6
0x1004572f1  mov     rax, qword ptr [rsp+248h+PerformanceCount]
0x1004572f6  cmp     rbx, rax
0x1004572f9  jg      short loc_100457290
0x1004572fb  movsxd  rbp, r12d
0x1004572fe  test    r12d, r12d
0x100457301  jle     loc_100457431
0x100457307  lea     rbx, [rsp+248h+var_1C8]
0x10045730f  nop
0x100457310  mov     rdx, [rbx+10h]
0x100457314  mov     r8d, edx
0x100457317  and     r8d, 3; unsigned int
0x10045731b  and     rdx, 0FFFFFFFFFFFFFFFCh; struct SNI_Packet *
0x10045731f  cmp     rdx, rsi
0x100457322  jnz     loc_100457414
0x100457328  cmp     r8d, 1
0x10045732c  jz      loc_100457414
0x100457332  mov     r14d, [rbx]
0x100457335  test    r14d, r14d
0x100457338  jnz     short loc_10045734C
0x10045733a  cmp     [rsi+0F4h], r15d
0x100457341  jnz     short loc_10045734C
0x100457343  mov     eax, [rbx+4]
0x100457346  add     [rsi+0B0h], eax
0x10045734c  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100457353  jz      short loc_100457389
0x100457355  mov     eax, [rsi+0F4h]
0x10045735b  mov     [rsp+248h+var_218], eax
0x10045735f  mov     [rsp+248h+var_220], rsi
0x100457364  mov     dword ptr [rsp+248h+var_228], r14d
0x100457369  lea     r9, aApiSnisynccomp; "API|SNISyncComp %d{WINERR},%p{packet},%"...
0x100457370  mov     r8d, 29Eh; int
0x100457376  lea     rdx, aTcpriocompleti; "TcpRIOCompletionQueue::DequeueSyncCompl"...
0x10045737d  lea     rcx, aSqlCommonDkSni_21; "sql\\common\\dk\\sni\\src\\sni_tcpriopr"...
0x100457384  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100457389  inc     qword ptr [rdi+0E8h]
0x100457390  jmp     loc_100457423
0x100457395  call    cs:__imp_GetLastError
0x10045739b  jmp     short loc_1004573A6
0x10045739d  cmp     eax, 0FFFFFFFFh
0x1004573a0  jnz     loc_1004572FB
0x1004573a6  mov     rcx, [rdi+0E0h]
0x1004573ad  mov     rcx, [rcx+8]; this
0x1004573b1  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x1004573b6  call    cs:__imp_WSAGetLastError
0x1004573bc  mov     r15d, eax
0x1004573bf  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004573c6  jz      short loc_1004573FC
0x1004573c8  mov     [rsp+248h+var_218], eax
0x1004573cc  mov     dword ptr [rsp+248h+var_220], 0
0x1004573d4  mov     dword ptr [rsp+248h+var_228], 7
0x1004573dc  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x1004573e3  mov     r8d, 2C7h; int
0x1004573e9  lea     rdx, aTcpriocompleti; "TcpRIOCompletionQueue::DequeueSyncCompl"...
0x1004573f0  lea     rcx, aSqlCommonDkSni_21; "sql\\common\\dk\\sni\\src\\sni_tcpriopr"...
0x1004573f7  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x1004573fc  mov     r8d, 0C3B4h
0x100457402  mov     edx, r15d
0x100457405  mov     ecx, 7
0x10045740a  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10045740f  jmp     loc_10045753B
0x100457414  mov     rcx, rbx; struct _RIORESULT *
0x100457417  call    ?HandleCompletion@TcpRIOCompletionQueue@@CAXPEAU_RIORESULT@@PEAVSNI_Packet@@K@Z; TcpRIOCompletionQueue::HandleCompletion(_RIORESULT *,SNI_Packet *,ulong)
0x10045741c  inc     qword ptr [rdi+0F8h]
0x100457423  add     rbx, 18h
0x100457427  sub     rbp, 1
0x10045742b  jnz     loc_100457310
0x100457431  test    r13b, r13b
0x100457434  jz      short loc_100457446
0x100457436  mov     rcx, [rdi+0E0h]
0x10045743d  mov     rcx, [rcx+8]; this
0x100457441  call    ?Release@SOS_UnfairRecursiveMutexExtendedGuarantee@@QEAAXXZ; SOS_UnfairRecursiveMutexExtendedGuarantee::Release(void)
0x100457446  mov     ebx, r12d
0x100457449  neg     ebx
0x10045744b  lock xadd [rdi+100h], ebx
0x100457453  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x10045745a  jz      short loc_100457485
0x10045745c  mov     eax, ebx
0x10045745e  sub     eax, r12d
0x100457461  mov     dword ptr [rsp+248h+var_228], eax
0x100457465  lea     r9, aApiSniDColdpen; "API|SNI%d{cOldPending - cDequeued}\n"
0x10045746c  mov     r8d, 2AFh; int
0x100457472  lea     rdx, aTcpriocompleti; "TcpRIOCompletionQueue::DequeueSyncCompl"...
0x100457479  lea     rcx, aSqlCommonDkSni_21; "sql\\common\\dk\\sni\\src\\sni_tcpriopr"...
0x100457480  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x100457485  cmp     ebx, r12d
0x100457488  jle     loc_100457536
0x10045748e  lfence
0x100457491  mov     rax, [rdi+0B8h]
0x100457498  mov     rdx, [rax]
0x10045749b  mov     rcx, [rdi+0D8h]
0x1004574a2  call    qword ptr [rdx+50h]
0x1004574a5  mov     r15d, eax
0x1004574a8  test    eax, eax
0x1004574aa  jz      loc_100457536
0x1004574b0  cmp     eax, 2735h
0x1004574b5  jnz     short loc_1004574E5
0x1004574b7  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004574be  jz      short loc_1004574E0
0x1004574c0  lea     r9, aApiSnialreadyQ; "API|SNIAlready queued\n"
0x1004574c7  mov     r8d, 2B8h; int
0x1004574cd  lea     rdx, aTcpriocompleti; "TcpRIOCompletionQueue::DequeueSyncCompl"...
0x1004574d4  lea     rcx, aSqlCommonDkSni_21; "sql\\common\\dk\\sni\\src\\sni_tcpriopr"...
0x1004574db  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x1004574e0  xor     r15d, r15d
0x1004574e3  jmp     short loc_100457536
0x1004574e5  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 2; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x1004574ec  jz      short loc_100457523
0x1004574ee  mov     [rsp+248h+var_218], r15d
0x1004574f3  mov     dword ptr [rsp+248h+var_220], 0
0x1004574fb  mov     dword ptr [rsp+248h+var_228], 7
0x100457503  lea     r9, aErrSniprovider; "ERR|SNIProviderNum: %d{ProviderNum}, SN"...
0x10045750a  mov     r8d, 2BDh; int
0x100457510  lea     rdx, aTcpriocompleti; "TcpRIOCompletionQueue::DequeueSyncCompl"...
0x100457517  lea     rcx, aSqlCommonDkSni_21; "sql\\common\\dk\\sni\\src\\sni_tcpriopr"...
0x10045751e  call    ?SNIXE_SNI_ERROR_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_ERROR_ON(char const *,char const *,int,wchar_t const *,...)
0x100457523  mov     r8d, 0C3B4h
0x100457529  mov     edx, r15d
0x10045752c  mov     ecx, 7
0x100457531  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100457536  test    r13b, r13b
0x100457539  jz      short loc_10045754A
0x10045753b  mov     rax, [rsp+248h+var_200]
0x100457540  and     dword ptr [rax+320h], 0FFDFFFFFh
0x10045754a  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 1; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100457551  jz      short loc_10045757E
0x100457553  mov     dword ptr [rsp+248h+var_220], r15d
0x100457558  mov     dword ptr [rsp+248h+var_228], r14d
0x10045755d  lea     r9, aRetSniDWinerrD_0; "RET|SNI%d{WINERR},%d{DQWINERR}\n"
0x100457564  mov     r8d, 2D1h; int
0x10045756a  lea     rdx, aTcpriocompleti; "TcpRIOCompletionQueue::DequeueSyncCompl"...
0x100457571  lea     rcx, aSqlCommonDkSni_21; "sql\\common\\dk\\sni\\src\\sni_tcpriopr"...
0x100457578  call    ?SNIXE_SNI_TRACE_ON@@YAXPEBD0HPEB_WZZ; SNIXE_SNI_TRACE_ON(char const *,char const *,int,wchar_t const *,...)
0x10045757d  nop
0x10045757e  test    byte ptr cs:?g_XeSniPkg_enabledBitmap@@3U?$XBitmap@U?$StaticStorage@$08@@@@A, 80h; XBitmap<StaticStorage<9>> g_XeSniPkg_enabledBitmap
0x100457585  jz      short loc_1004575A0
0x100457587  mov     r8d, 23Dh; int
0x10045758d  lea     rdx, aTcpriocompleti; "TcpRIOCompletionQueue::DequeueSyncCompl"...
0x100457594  lea     rcx, aSqlCommonDkSni_21; "sql\\common\\dk\\sni\\src\\sni_tcpriopr"...
0x10045759b  call    ?SNIXE_SNI_LEAVE_ON@@YAXPEBD0HPEB_W@Z; SNIXE_SNI_LEAVE_ON(char const *,char const *,int,wchar_t const *)
0x1004575a0  mov     eax, r14d
0x1004575a3  mov     rcx, [rsp+248h+var_48]
0x1004575ab  xor     rcx, rsp; StackCookie
0x1004575ae  call    __security_check_cookie
0x1004575b3  mov     rbx, [rsp+248h+arg_10]
0x1004575bb  add     rsp, 210h
0x1004575c2  pop     r15
0x1004575c4  pop     r14
0x1004575c6  pop     r13
0x1004575c8  pop     r12
0x1004575ca  pop     rdi
0x1004575cb  pop     rsi
0x1004575cc  pop     rbp
0x1004575cd  retn
```
