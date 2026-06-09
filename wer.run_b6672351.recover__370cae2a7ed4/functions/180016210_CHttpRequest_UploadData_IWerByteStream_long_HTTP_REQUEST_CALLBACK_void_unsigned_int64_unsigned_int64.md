# CHttpRequest::UploadData(IWerByteStream *,long (*)(_HTTP_REQUEST_CALLBACK *),void *,unsigned __int64,unsigned __int64)

- ea: `0x180016210`
- end: `0x180016739`
- name: `?UploadData@CHttpRequest@@IEAAJPEAUIWerByteStream@@P6AJPEAU_HTTP_REQUEST_CALLBACK@@@ZPEAX_K4@Z`
- size: `1321`
- prototype: `__int64 __usercall@<rax>(CHttpRequest *__hidden this@<rcx>, struct IWerByteStream *@<rdx>, int (*)(struct _HTTP_REQUEST_CALLBACK *)@<r8>, void *@<r9>, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18009fa94`

## callees

- `0x180004c64`
- `0x180016210`
- `0x180016838`
- `0x18001c368`
- `0x180020680`
- `0x180026afc`
- `0x18003e1ec`
- `0x18004ea54`
- `0x180053300`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016314`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016314`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016391`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016391`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016266`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016285`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800162e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016266`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016285`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800162e3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180016299`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800162f6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180016299`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800162f6`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180016275`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180016275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001666d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001666d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800163fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800163fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016435`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016435`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016522`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016522`
- `WINHTTP!WinHttpWriteData` at `0x180016415`
- `WINHTTP!WinHttpWriteData` at `0x180016415`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHttpRequest::UploadData(
        CHttpRequest *this,
        struct IWerByteStream *a2,
        __int64 (__fastcall *a3)(__int128 *),
        void *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  struct IWerByteStream *v7; // rbp
  void *v9; // r12
  HANDLE CurrentThread; // rax
  HANDLE v11; // rax
  unsigned __int64 v12; // r14
  int v13; // edi
  wchar_t *v14; // rcx
  HANDLE v15; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int64 v19; // r15
  void *v20; // rcx
  BOOL v21; // edi
  DWORD LastError; // ebp
  bool v23; // r9
  unsigned int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r9
  wchar_t *v30; // rcx
  __int64 v31; // rdx
  DWORD v32; // eax
  DWORD dwNumberOfBytesToWrite; // [rsp+30h] [rbp-A8h] BYREF
  int nPriority; // [rsp+34h] [rbp-A4h]
  struct IWerByteStream *v35; // [rsp+38h] [rbp-A0h]
  void *v36; // [rsp+40h] [rbp-98h]
  void *v37; // [rsp+48h] [rbp-90h]
  __int128 v38; // [rsp+50h] [rbp-88h] BYREF
  __int128 v39; // [rsp+60h] [rbp-78h]
  void *v40[2]; // [rsp+70h] [rbp-68h] BYREF
  __int64 v41; // [rsp+80h] [rbp-58h]

  v37 = a4;
  v7 = a2;
  v35 = a2;
  dwNumberOfBytesToWrite = 0;
  v38 = 0;
  v39 = 0;
  v9 = 0;
  v36 = 0;
  CurrentThread = GetCurrentThread();
  nPriority = GetThreadPriority(CurrentThread);
  v11 = GetCurrentThread();
  SetThreadPriority(v11, -1);
  v12 = a5;
  v13 = (*(__int64 (__fastcall **)(struct IWerByteStream *, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v7 + 16LL))(
          v7,
          a5,
          0,
          0);
  if ( v13 >= 0 )
  {
    v19 = (*(__int64 (__fastcall **)(struct IWerByteStream *))(*(_QWORD *)v7 + 32LL))(v7);
    if ( a6 && a5 + a6 < (*(__int64 (__fastcall **)(struct IWerByteStream *))(*(_QWORD *)v7 + 32LL))(v7) )
      v19 = a5 + a6;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_III(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, a5, v19, a6);
    v9 = HeapAlloc(g_hWerheap, 0, 0x1000u);
    v36 = v9;
    if ( v9 )
    {
      while ( 1 )
      {
        if ( v12 >= v19 )
        {
          v13 = 0;
          goto LABEL_3;
        }
        v20 = (void *)*((_QWORD *)this + 5);
        if ( v20 && !WaitForSingleObject(v20, 0) )
        {
          v13 = -2147467260;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v31 = 98;
            goto LABEL_28;
          }
          goto LABEL_3;
        }
        v13 = (**(__int64 (__fastcall ***)(struct IWerByteStream *, void *, __int64, DWORD *, _QWORD))v7)(
                v7,
                v9,
                4096,
                &dwNumberOfBytesToWrite,
                *((_QWORD *)this + 4));
        if ( v13 < 0 )
          break;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
        v21 = WinHttpWriteData(*((HINTERNET *)this + 2), v9, dwNumberOfBytesToWrite, 0);
        LastError = GetLastError();
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
        if ( !v21 )
        {
          v13 = ERROR_HR_FROM_WIN32(LastError);
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v28 = 100;
            goto LABEL_23;
          }
          goto LABEL_3;
        }
        v40[0] = *((void **)this + 3);
        v40[1] = *((void **)this + 4);
        v41 = *((_QWORD *)this + 5);
        v24 = UtilWaitForMultipleObjects(
                L"CHttpRequest async operation",
                (v41 != 0) + 2,
                v40,
                v23,
                *((_DWORD *)this + 216));
        if ( v24 )
        {
          switch ( v24 )
          {
            case 1u:
              goto LABEL_54;
            case 2u:
              CHttpRequest::AbortRequest(this);
LABEL_54:
              v13 = -2147467260;
LABEL_49:
              v26 = v13;
LABEL_50:
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v28 = 101;
                v29 = (unsigned int)v26;
                goto LABEL_32;
              }
              goto LABEL_3;
            case 0x102u:
              CHttpRequest::AbortRequest(this);
              v13 = -2147023436;
              goto LABEL_49;
          }
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v24);
          v32 = GetLastError();
          v26 = ERROR_HR_FROM_WIN32(v32);
        }
        else
        {
          v26 = *((_DWORD *)this + 14);
        }
        v13 = v26;
        if ( v26 < 0 )
          goto LABEL_50;
        v27 = dwNumberOfBytesToWrite;
        if ( dwNumberOfBytesToWrite != *((_DWORD *)this + 258) )
        {
          MicrosoftTelemetryAssertTriggeredArgs(v25, dwNumberOfBytesToWrite);
          v27 = dwNumberOfBytesToWrite;
        }
        v12 += v27;
        LODWORD(v38) = 1;
        *((_QWORD *)&v38 + 1) = v37;
        *(_QWORD *)&v39 = v12;
        v7 = v35;
        if ( a3 )
        {
          v13 = a3(&v38);
          if ( v13 < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v28 = 102;
              goto LABEL_23;
            }
            goto LABEL_3;
          }
        }
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v28 = 99;
        goto LABEL_23;
      }
    }
    else
    {
      v13 = -2147024882;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v31 = 97;
LABEL_28:
        WPP_SF_(*((_QWORD *)v30 + 2), v31, WPP_158c1c2611d1379e0dd259997317728c_Traceguids);
      }
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v28 = 95;
LABEL_23:
      v29 = (unsigned int)v13;
LABEL_32:
      WPP_SF_d(*((_QWORD *)v14 + 2), v28, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v29);
    }
  }
LABEL_3:
  v15 = GetCurrentThread();
  SetThreadPriority(v15, nPriority);
  if ( v9 )
    HeapFree(g_hWerheap, 0, v9);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180016210  push    rbx
0x180016212  push    rbp
0x180016213  push    rsi
0x180016214  push    rdi
0x180016215  push    r12
0x180016217  push    r13
0x180016219  push    r14
0x18001621b  push    r15
0x18001621d  sub     rsp, 98h
0x180016224  mov     rax, cs:__security_cookie
0x18001622b  xor     rax, rsp
0x18001622e  mov     [rsp+0D8h+var_50], rax
0x180016236  mov     [rsp+0D8h+var_90], r9
0x18001623b  mov     r13, r8
0x18001623e  mov     rbp, rdx
0x180016241  mov     [rsp+0D8h+var_A0], rdx
0x180016246  mov     rbx, rcx
0x180016249  mov     [rsp+0D8h+dwNumberOfBytesToWrite], 0
0x180016251  xorps   xmm0, xmm0
0x180016254  movups  [rsp+0D8h+var_88], xmm0
0x180016259  movups  [rsp+0D8h+var_78], xmm0
0x18001625e  xor     r12d, r12d
0x180016261  mov     [rsp+0D8h+var_98], r12
0x180016266  call    cs:__imp_GetCurrentThread
0x18001626d  nop     dword ptr [rax+rax+00h]
0x180016272  mov     rcx, rax; hThread
0x180016275  call    cs:__imp_GetThreadPriority
0x18001627c  nop     dword ptr [rax+rax+00h]
0x180016281  mov     [rsp+0D8h+nPriority], eax
0x180016285  call    cs:__imp_GetCurrentThread
0x18001628c  nop     dword ptr [rax+rax+00h]
0x180016291  mov     rcx, rax; hThread
0x180016294  mov     edx, 0FFFFFFFFh; nPriority
0x180016299  call    cs:__imp_SetThreadPriority
0x1800162a0  nop     dword ptr [rax+rax+00h]
0x1800162a5  mov     rcx, [rbp+0]
0x1800162a9  mov     rax, [rcx+10h]
0x1800162ad  xor     r9d, r9d
0x1800162b0  xor     r8d, r8d
0x1800162b3  mov     r14, [rsp+0D8h+arg_20]
0x1800162bb  mov     rdx, r14
0x1800162be  mov     rcx, rbp
0x1800162c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800162c6  mov     edi, eax
0x1800162c8  test    eax, eax
0x1800162ca  jns     short loc_180016347
0x1800162cc  lea     rax, WPP_GLOBAL_Control
0x1800162d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162da  cmp     rcx, rax
0x1800162dd  jnz     loc_18001657D
0x1800162e3  call    cs:__imp_GetCurrentThread
0x1800162ea  nop     dword ptr [rax+rax+00h]
0x1800162ef  mov     rcx, rax; hThread
0x1800162f2  mov     edx, [rsp+0D8h+nPriority]; nPriority
0x1800162f6  call    cs:__imp_SetThreadPriority
0x1800162fd  nop     dword ptr [rax+rax+00h]
0x180016302  nop
0x180016303  test    r12, r12
0x180016306  jz      short loc_180016320
0x180016308  mov     r8, r12; lpMem
0x18001630b  xor     edx, edx; dwFlags
0x18001630d  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180016314  call    cs:__imp_HeapFree
0x18001631b  nop     dword ptr [rax+rax+00h]
0x180016320  mov     eax, edi
0x180016322  mov     rcx, [rsp+0D8h+var_50]
0x18001632a  xor     rcx, rsp; StackCookie
0x18001632d  call    __security_check_cookie
0x180016332  add     rsp, 98h
0x180016339  pop     r15
0x18001633b  pop     r14
0x18001633d  pop     r13
0x18001633f  pop     r12
0x180016341  pop     rdi
0x180016342  pop     rsi
0x180016343  pop     rbp
0x180016344  pop     rbx
0x180016345  retn
0x180016347  mov     rax, [rbp+0]
0x18001634b  mov     rcx, rbp
0x18001634e  mov     rax, [rax+20h]
0x180016352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016357  mov     r15, rax
0x18001635a  mov     rsi, [rsp+0D8h+arg_28]
0x180016362  test    rsi, rsi
0x180016365  jnz     loc_1800165AB
0x18001636b  lea     rax, WPP_GLOBAL_Control
0x180016372  mov     rcx, cs:WPP_GLOBAL_Control
0x180016379  cmp     rcx, rax
0x18001637c  jnz     loc_1800165CB
0x180016382  xor     edx, edx; dwFlags
0x180016384  mov     r8d, 1000h; dwBytes
0x18001638a  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x180016391  call    cs:__imp_HeapAlloc
0x180016398  nop     dword ptr [rax+rax+00h]
0x18001639d  mov     r12, rax
0x1800163a0  mov     [rsp+0D8h+var_98], rax
0x1800163a5  test    rax, rax
0x1800163a8  jz      loc_1800165F0
0x1800163ae  xchg    ax, ax
0x1800163b0  cmp     r14, r15
0x1800163b3  jnb     loc_180016576
0x1800163b9  mov     rcx, [rbx+28h]; hHandle
0x1800163bd  test    rcx, rcx
0x1800163c0  jnz     loc_180016520
0x1800163c6  mov     rax, [rbp+0]
0x1800163ca  mov     rcx, [rbx+20h]
0x1800163ce  mov     qword ptr [rsp+0D8h+var_B8], rcx
0x1800163d3  lea     r9, [rsp+0D8h+dwNumberOfBytesToWrite]
0x1800163d8  mov     r8d, 1000h
0x1800163de  mov     rdx, r12
0x1800163e1  mov     rcx, rbp
0x1800163e4  mov     rax, [rax]
0x1800163e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163ec  mov     edi, eax
0x1800163ee  test    eax, eax
0x1800163f0  js      loc_18001670D
0x1800163f6  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800163fa  call    cs:__imp_EnterCriticalSection
0x180016401  nop     dword ptr [rax+rax+00h]
0x180016406  xor     r9d, r9d; lpdwNumberOfBytesWritten
0x180016409  mov     r8d, [rsp+0D8h+dwNumberOfBytesToWrite]; dwNumberOfBytesToWrite
0x18001640e  mov     rdx, r12; lpBuffer
0x180016411  mov     rcx, [rbx+10h]; hRequest
0x180016415  call    cs:__imp_WinHttpWriteData
0x18001641c  nop     dword ptr [rax+rax+00h]
0x180016421  mov     edi, eax
0x180016423  call    cs:__imp_GetLastError
0x18001642a  nop     dword ptr [rax+rax+00h]
0x18001642f  mov     ebp, eax
0x180016431  lea     rcx, [rbx+48h]; lpCriticalSection
0x180016435  call    cs:__imp_LeaveCriticalSection
0x18001643c  nop     dword ptr [rax+rax+00h]
0x180016441  test    edi, edi
0x180016443  jz      loc_1800166D9
0x180016449  mov     rax, [rbx+18h]
0x18001644d  mov     [rsp+0D8h+var_68], rax
0x180016452  mov     rax, [rbx+20h]
0x180016456  mov     [rsp+0D8h+var_60], rax
0x18001645b  mov     rax, [rbx+28h]
0x18001645f  mov     [rsp+0D8h+var_58], rax
0x180016467  xor     edx, edx
0x180016469  test    rax, rax
0x18001646c  setnz   dl
0x18001646f  add     edx, 2; unsigned int
0x180016472  mov     eax, [rbx+360h]
0x180016478  mov     [rsp+0D8h+var_B8], eax; unsigned int
0x18001647c  lea     r8, [rsp+0D8h+var_68]; void **
0x180016481  lea     rcx, aChttprequestAs; "CHttpRequest async operation"
0x180016488  call    ?UtilWaitForMultipleObjects@@YAKPEB_WKQEAPEAX_NK@Z; UtilWaitForMultipleObjects(wchar_t const *,ulong,void * * const,bool,ulong)
0x18001648d  test    eax, eax
0x18001648f  jnz     loc_180016620
0x180016495  mov     eax, [rbx+38h]
0x180016498  mov     edi, eax
0x18001649a  test    eax, eax
0x18001649c  js      loc_1800166A4
0x1800164a2  mov     r8d, [rbx+408h]
0x1800164a9  mov     eax, [rsp+0D8h+dwNumberOfBytesToWrite]
0x1800164ad  cmp     eax, r8d
0x1800164b0  jnz     loc_180016685
0x1800164b6  add     r14, rax
0x1800164b9  mov     dword ptr [rsp+0D8h+var_88], 1
0x1800164c1  mov     rax, [rsp+0D8h+var_90]
0x1800164c6  mov     qword ptr [rsp+0D8h+var_88+8], rax
0x1800164cb  mov     qword ptr [rsp+0D8h+var_78], r14
0x1800164d0  test    r13, r13
0x1800164d3  mov     rbp, [rsp+0D8h+var_A0]
0x1800164d8  jz      loc_1800163B0
0x1800164de  lea     rcx, [rsp+0D8h+var_88]
0x1800164e3  mov     rax, r13
0x1800164e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164eb  mov     edi, eax
0x1800164ed  test    eax, eax
0x1800164ef  jns     loc_1800163B0
0x1800164f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800164fc  lea     rax, WPP_GLOBAL_Control
0x180016503  cmp     rcx, rax
0x180016506  jz      loc_1800162E3
0x18001650c  test    byte ptr [rcx+1Ch], 1
0x180016510  jz      loc_1800162E3
0x180016516  mov     edx, 66h ; 'f'
0x18001651b  mov     r9d, edi
0x18001651e  jmp     short loc_180016596
0x180016520  xor     edx, edx; dwMilliseconds
0x180016522  call    cs:__imp_WaitForSingleObject
0x180016529  nop     dword ptr [rax+rax+00h]
0x18001652e  test    eax, eax
0x180016530  jnz     loc_1800163C6
0x180016536  mov     edi, 80004004h
0x18001653b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016542  lea     rax, WPP_GLOBAL_Control
0x180016549  cmp     rcx, rax
0x18001654c  jz      loc_1800162E3
0x180016552  test    byte ptr [rcx+1Ch], 1
0x180016556  jz      loc_1800162E3
0x18001655c  mov     edx, 62h ; 'b'
0x180016561  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x180016568  mov     rcx, [rcx+10h]
0x18001656c  call    WPP_SF_
0x180016571  jmp     loc_1800162E3
0x180016576  xor     edi, edi
0x180016578  jmp     loc_1800162E3
0x18001657d  test    byte ptr [rcx+1Ch], 1
0x180016581  jz      loc_1800162E3
0x180016587  mov     edx, 5Fh ; '_'
0x18001658c  jmp     short loc_18001651B
0x18001658e  mov     edx, 65h ; 'e'
0x180016593  mov     r9d, eax
0x180016596  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18001659d  mov     rcx, [rcx+10h]
0x1800165a1  call    WPP_SF_d
0x1800165a6  jmp     loc_1800162E3
0x1800165ab  lea     rdi, [r14+rsi]
0x1800165af  mov     rcx, [rbp+0]
0x1800165b3  mov     rax, [rcx+20h]
0x1800165b7  mov     rcx, rbp
0x1800165ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165bf  cmp     rdi, rax
0x1800165c2  cmovb   r15, rdi
0x1800165c6  jmp     loc_18001636B
0x1800165cb  test    byte ptr [rcx+1Ch], 1
0x1800165cf  jz      loc_180016382
0x1800165d5  mov     [rsp+0D8h+var_B0], rsi
0x1800165da  mov     qword ptr [rsp+0D8h+var_B8], r15
0x1800165df  mov     r9, r14
0x1800165e2  mov     rcx, [rcx+10h]
0x1800165e6  call    WPP_SF_III
0x1800165eb  jmp     loc_180016382
0x1800165f0  mov     edi, 8007000Eh
0x1800165f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165fc  lea     rax, WPP_GLOBAL_Control
0x180016603  cmp     rcx, rax
0x180016606  jz      loc_1800162E3
0x18001660c  test    byte ptr [rcx+1Ch], 1
0x180016610  jz      loc_1800162E3
0x180016616  mov     edx, 61h ; 'a'
0x18001661b  jmp     loc_180016561
0x180016620  mov     ecx, eax
0x180016622  sub     ecx, 1
0x180016625  jz      loc_1800166D2
0x18001662b  sub     ecx, 1
0x18001662e  jz      loc_1800166CA
0x180016634  cmp     ecx, 100h
0x18001663a  jz      short loc_180016695
0x18001663c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016643  lea     rdx, WPP_GLOBAL_Control
0x18001664a  cmp     rcx, rdx
0x18001664d  jz      short loc_18001666D
0x18001664f  test    byte ptr [rcx+1Ch], 1
0x180016653  jz      short loc_18001666D
0x180016655  mov     edx, 10h
0x18001665a  mov     r9d, eax
0x18001665d  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x180016664  mov     rcx, [rcx+10h]
0x180016668  call    WPP_SF_d
0x18001666d  call    cs:__imp_GetLastError
0x180016674  nop     dword ptr [rax+rax+00h]
0x180016679  mov     ecx, eax; unsigned int
0x18001667b  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180016680  jmp     loc_180016498
0x180016685  mov     edx, eax
0x180016687  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001668c  mov     eax, [rsp+0D8h+dwNumberOfBytesToWrite]
0x180016690  jmp     loc_1800164B6
0x180016695  mov     rcx, rbx; this
0x180016698  call    ?AbortRequest@CHttpRequest@@QEAAXXZ; CHttpRequest::AbortRequest(void)
0x18001669d  mov     edi, 800705B4h
0x1800166a2  mov     eax, edi
0x1800166a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166ab  lea     rdx, WPP_GLOBAL_Control
0x1800166b2  cmp     rcx, rdx
0x1800166b5  jz      loc_1800162E3
0x1800166bb  test    byte ptr [rcx+1Ch], 1
0x1800166bf  jz      loc_1800162E3
0x1800166c5  jmp     loc_18001658E
0x1800166ca  mov     rcx, rbx; this
0x1800166cd  call    ?AbortRequest@CHttpRequest@@QEAAXXZ; CHttpRequest::AbortRequest(void)
0x1800166d2  mov     edi, 80004004h
0x1800166d7  jmp     short loc_1800166A2
0x1800166d9  mov     ecx, ebp; unsigned int
0x1800166db  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800166e0  mov     edi, eax
0x1800166e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166e9  lea     rax, WPP_GLOBAL_Control
0x1800166f0  cmp     rcx, rax
0x1800166f3  jz      loc_1800162E3
0x1800166f9  test    byte ptr [rcx+1Ch], 1
0x1800166fd  jz      loc_1800162E3
0x180016703  mov     edx, 64h ; 'd'
0x180016708  jmp     loc_18001651B
0x18001670d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016714  lea     rax, WPP_GLOBAL_Control
0x18001671b  cmp     rcx, rax
0x18001671e  jz      loc_1800162E3
0x180016724  test    byte ptr [rcx+1Ch], 1
0x180016728  jz      loc_1800162E3
0x18001672e  mov     edx, 63h ; 'c'
0x180016733  jmp     loc_18001651B
```
