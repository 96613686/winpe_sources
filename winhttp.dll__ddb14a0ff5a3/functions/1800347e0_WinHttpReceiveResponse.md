# WinHttpReceiveResponse

- ea: `0x1800347e0`
- end: `0x180034db9`
- name: `WinHttpReceiveResponse`
- size: `1497`
- prototype: `BOOL __stdcall(HINTERNET hRequest, LPVOID lpReserved)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027624`
- `0x1800b3c8c`
- `0x1800bca80`

## callees

- `0x180013680`
- `0x180013f60`
- `0x180033ac0`
- `0x180033b64`
- `0x1800347e0`
- `0x180034dc0`
- `0x18003b0e0`
- `0x18003b230`
- `0x18003bc60`
- `0x1800716a0`
- `0x1800a1d10`
- `0x1800db6b0`
- `0x1800db758`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800348f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034951`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800348f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034951`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003491e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034975`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034d46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003491e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034975`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034d46`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800349d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800349d4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180034abd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180034bcb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180034abd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180034bcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034b2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034d37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034d37`
- `ntdll!EtwEventActivityIdControl` at `0x180034b0e`
- `ntdll!EtwEventActivityIdControl` at `0x180034b0e`

## pseudocode

```c
BOOL __stdcall WinHttpReceiveResponse(HINTERNET hRequest, LPVOID lpReserved)
{
  unsigned int v3; // ebp
  __int64 v4; // r15
  HANDLE_OBJECT *v5; // rdi
  DWORD IsValid; // ebx
  char v7; // al
  HTTP_REQUEST_HANDLE_OBJECT *v8; // rdi
  HTTP_USER_REQUEST *v9; // rsi
  BOOL v10; // r13d
  void (*v11)(void *, unsigned __int64, unsigned int, void *, unsigned int); // r12
  int v12; // ebx
  unsigned __int64 v13; // rbp
  unsigned int v14; // eax
  _QWORD *v15; // rax
  _QWORD *v16; // rcx
  int v17; // r8d
  int v18; // edx
  int v19; // eax
  bool v20; // sf
  void *v22; // r12
  int v23; // edx
  unsigned __int64 v24; // [rsp+20h] [rbp-78h]
  HANDLE hObject; // [rsp+30h] [rbp-68h] BYREF
  HTTP_REQUEST_HANDLE_OBJECT *v26; // [rsp+38h] [rbp-60h] BYREF
  __int128 v27; // [rsp+40h] [rbp-58h] BYREF
  int v28; // [rsp+50h] [rbp-48h]

  v26 = 0;
  v28 = 0;
  v3 = 0;
  v4 = -1;
  v27 = 0;
  v5 = (HANDLE_OBJECT *)hRequest;
  WinHttpEtwSetActivityIdFromHandle((char *)hRequest, 4, (struct _WINHTTP_ETW_INFO *)&v27);
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_qq(1026, 13, (unsigned int)WPP_a25211da527b3d0b325d5ad2246d882e_Traceguids, (_DWORD)v5, (__int64)lpReserved);
  if ( !v5 )
  {
    IsValid = 6;
    goto LABEL_31;
  }
  if ( lpReserved )
  {
    IsValid = 87;
    goto LABEL_31;
  }
  if ( !GlobalDataInitialized )
  {
    IsValid = 12172;
    goto LABEL_31;
  }
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_qqD(1041, 10, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, (_DWORD)v5, (__int64)&v26);
  if ( (unsigned int)HANDLE_OBJECT::IsValid(v5, 1684826455) )
  {
    if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
    {
      v23 = 11;
      goto LABEL_62;
    }
LABEL_53:
    v5 = 0;
    IsValid = 6;
    goto LABEL_12;
  }
  IsValid = HANDLE_OBJECT::Reference(v5);
  v7 = BYTE2(xmmword_180107A50);
  if ( (BYTE2(xmmword_180107A50) & 2) != 0 )
  {
    WPP_SF_d(529, 12, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, IsValid, v24);
    v7 = BYTE2(xmmword_180107A50);
  }
  if ( IsValid != 6 && IsValid )
  {
    if ( (v7 & 2) != 0 )
    {
      v23 = 13;
LABEL_62:
      WPP_SF_qq(529, v23, (unsigned int)WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, (_DWORD)v5, (__int64)v5);
      goto LABEL_53;
    }
    goto LABEL_53;
  }
LABEL_12:
  v26 = v5;
  if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
    WPP_SF_d(1041, 14, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids, IsValid, v24);
  if ( IsValid )
  {
    if ( !v26 )
    {
LABEL_75:
      if ( (xmmword_180107A50 & 4) != 0 )
        WPP_SF_d(514, 14, WPP_a25211da527b3d0b325d5ad2246d882e_Traceguids, IsValid, v24);
      goto LABEL_39;
    }
  }
  else
  {
    v8 = v26;
    IsValid = HANDLE_OBJECT::IsValid(v26, 1902465608);
    if ( IsValid )
      goto LABEL_31;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 328));
    v9 = (HTTP_USER_REQUEST *)*((_QWORD *)v8 + 56);
    if ( v9 )
    {
      (**(void (__fastcall ***)(_QWORD))v9)(*((_QWORD *)v8 + 56));
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 328));
      DereferenceObject(v26);
      v26 = 0;
      if ( *((_DWORD *)v8 + 35) )
      {
        hObject = (HANDLE)-1LL;
        v22 = (void *)*((_QWORD *)GetRootHandle(v8) + 26);
        IsValid = GetCurrentThreadImpersonationToken(&hObject);
        if ( !IsValid )
        {
          if ( SetThreadToken(0, v22) )
          {
            v4 = (__int64)hObject;
            goto LABEL_18;
          }
          IsValid = GetLastError();
        }
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
        if ( IsValid )
          goto LABEL_30;
      }
LABEL_18:
      v10 = 1;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 328));
      v11 = (void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int))*((_QWORD *)v8 + 21);
      v12 = *((_DWORD *)v8 + 45);
      v13 = *((_QWORD *)v8 + 8);
      ++*((_DWORD *)v8 + 110);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 328));
      if ( *((_DWORD *)v8 + 35) && v11 )
        v10 = (v12 & 0x220000) != 2228224;
      v14 = HTTP_USER_REQUEST::RecvResponse(v9, v10, v11, v12 & 0xF681FFFF, v13);
      IsValid = v14;
      if ( v14 != 997 )
      {
        if ( v10 )
        {
          if ( v14 )
          {
            v3 = 0;
            goto LABEL_29;
          }
LABEL_28:
          v3 = 1;
          goto LABEL_29;
        }
        v15 = HeapAlloc(g_hWxProcessHeap, 0, 0x80u);
        if ( !v15 )
        {
          v3 = 0;
          IsValid = 8;
          goto LABEL_29;
        }
        v15[9] = 0;
        v15[11] = 0;
        v15[10] = 0;
        *((_OWORD *)v15 + 6) = 0;
        v15[8] = &HTTP_THREAD_POOL::WORK_ITEM::`vftable';
        v16 = v15 + 5;
        *((_DWORD *)v15 + 9) = 0;
        *(_OWORD *)(v15 + 5) = 0;
        v15[7] = 0;
        *v15 = v11;
        v15[1] = v13;
        *((_DWORD *)v15 + 4) = 1;
        if ( IsValid )
        {
          *v16 = 1;
          v18 = 16;
          *((_DWORD *)v15 + 12) = IsValid;
          v17 = 0x200000;
        }
        else
        {
          v16 = 0;
          v17 = 0x20000;
          v18 = 0;
        }
        *((_DWORD *)v15 + 5) = v17;
        *((_DWORD *)v15 + 8) = v18;
        v15[3] = v16;
        IsValid = HTTP_REQUEST_HANDLE_OBJECT::IndicateCompletionStatusCommon(
                    v8,
                    (struct HTTP_COMPLETION_PACKET *)v15,
                    1);
        v3 = IsValid == 0;
        if ( IsValid != 997 )
        {
LABEL_29:
          if ( v11 && (v10 || !v3) )
            HTTP_REQUEST_HANDLE_OBJECT::SafeReleaseCallbackInfo(v8);
LABEL_30:
          (*(void (__fastcall **)(HTTP_USER_REQUEST *))(*(_QWORD *)v9 + 8LL))(v9);
          goto LABEL_31;
        }
      }
      IsValid = 0;
      goto LABEL_28;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 328));
    IsValid = 6;
  }
LABEL_31:
  if ( v26 )
  {
    DereferenceObject(v26);
    v26 = 0;
  }
  if ( v4 != -1 )
  {
    if ( !SetThreadToken(0, (HANDLE)v4) )
      GetLastError();
    if ( v4 )
      CloseHandle((HANDLE)v4);
  }
  if ( IsValid )
    goto LABEL_75;
LABEL_39:
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_d(1026, 15, WPP_a25211da527b3d0b325d5ad2246d882e_Traceguids, v3, v24);
  if ( v28 )
  {
    HIDWORD(hObject) = 0;
    v19 = EtwEventActivityIdControl(2, &v27);
    v20 = v19 < 0;
    if ( v19 > 0 )
      v20 = 1;
    if ( v20 )
      HIDWORD(hObject) = 144;
  }
  SetLastError(IsValid);
  return v3;
}

```

## disassembly

```asm
0x1800347e0  push    rbx
0x1800347e2  push    rbp
0x1800347e3  push    r12
0x1800347e5  sub     rsp, 80h
0x1800347ec  mov     rax, cs:__security_cookie
0x1800347f3  xor     rax, rsp
0x1800347f6  mov     [rsp+98h+var_40], rax
0x1800347fb  xor     r12d, r12d
0x1800347fe  mov     [rsp+98h+var_20], rdi
0x180034803  mov     rbx, rdx
0x180034806  mov     [rsp+98h+var_38], r15
0x18003480b  xorps   xmm0, xmm0
0x18003480e  mov     [rsp+98h+var_60], r12
0x180034813  xor     eax, eax
0x180034815  lea     r8, [rsp+98h+var_58]; struct _WINHTTP_ETW_INFO *
0x18003481a  mov     edx, 4; unsigned int
0x18003481f  mov     [rsp+98h+var_48], eax
0x180034823  mov     ebp, r12d
0x180034826  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18003482d  movups  [rsp+98h+var_58], xmm0
0x180034832  mov     rdi, rcx
0x180034835  call    ?WinHttpEtwSetActivityIdFromHandle@@YAXPEAXKPEAU_WINHTTP_ETW_INFO@@@Z; WinHttpEtwSetActivityIdFromHandle(void *,ulong,_WINHTTP_ETW_INFO *)
0x18003483a  test    byte ptr cs:xmmword_180107A60, 4
0x180034841  jnz     loc_180034CE2
0x180034847  test    rdi, rdi
0x18003484a  jz      loc_180034BF6
0x180034850  test    rbx, rbx
0x180034853  jnz     loc_180034D05
0x180034859  cmp     cs:?GlobalDataInitialized@@3HA, ebp; int GlobalDataInitialized
0x18003485f  jz      loc_180034D0F
0x180034865  test    byte ptr cs:xmmword_180107A60+2, 2
0x18003486c  jnz     loc_180034C23
0x180034872  mov     edx, 646C6957h
0x180034877  mov     rcx, rdi
0x18003487a  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x18003487f  test    eax, eax
0x180034881  jnz     loc_180034B88
0x180034887  mov     rcx, rdi; this
0x18003488a  call    ?Reference@HANDLE_OBJECT@@QEAAKXZ; HANDLE_OBJECT::Reference(void)
0x18003488f  mov     ebx, eax
0x180034891  movzx   eax, byte ptr cs:xmmword_180107A50+2
0x180034898  test    al, 2
0x18003489a  jnz     loc_180034C7A
0x1800348a0  cmp     ebx, 6
0x1800348a3  jnz     loc_180034BE3
0x1800348a9  mov     [rsp+98h+var_60], rdi
0x1800348ae  test    byte ptr cs:xmmword_180107A60+2, 2
0x1800348b5  jnz     loc_180034C5C
0x1800348bb  test    ebx, ebx
0x1800348bd  jnz     loc_180034D19
0x1800348c3  mov     rdi, [rsp+98h+var_60]
0x1800348c8  mov     edx, 71655248h
0x1800348cd  mov     rcx, rdi
0x1800348d0  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x1800348d5  mov     ebx, eax
0x1800348d7  test    eax, eax
0x1800348d9  jnz     loc_180034AA4
0x1800348df  mov     [rsp+98h+arg_10], rsi
0x1800348e7  lea     rcx, [rdi+148h]; lpCriticalSection
0x1800348ee  mov     [rsp+98h+var_30], r14
0x1800348f3  call    cs:__imp_EnterCriticalSection
0x1800348f9  mov     rsi, [rdi+1C0h]
0x180034900  test    rsi, rsi
0x180034903  jz      loc_180034D3F
0x180034909  mov     rax, [rsi]
0x18003490c  mov     rcx, rsi
0x18003490f  mov     rax, [rax]
0x180034912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034917  lea     rcx, [rdi+148h]; lpCriticalSection
0x18003491e  call    cs:__imp_LeaveCriticalSection
0x180034924  mov     rcx, [rsp+98h+var_60]; void *
0x180034929  call    ?DereferenceObject@@YAKPEAX@Z; DereferenceObject(void *)
0x18003492e  mov     [rsp+98h+var_60], r12
0x180034933  cmp     [rdi+8Ch], ebp
0x180034939  jnz     loc_180034B9E
0x18003493f  mov     [rsp+98h+var_28], r13
0x180034944  lea     rcx, [rdi+148h]; lpCriticalSection
0x18003494b  mov     r13d, 1
0x180034951  call    cs:__imp_EnterCriticalSection
0x180034957  mov     r12, [rdi+0A8h]
0x18003495e  lea     rcx, [rdi+148h]; lpCriticalSection
0x180034965  mov     ebx, [rdi+0B4h]
0x18003496b  mov     rbp, [rdi+40h]
0x18003496f  inc     dword ptr [rdi+1B8h]
0x180034975  call    cs:__imp_LeaveCriticalSection
0x18003497b  cmp     dword ptr [rdi+8Ch], 0
0x180034982  jnz     loc_180034B4B
0x180034988  and     ebx, 0F681FFFFh
0x18003498e  mov     [rsp+98h+var_78], rbp; unsigned __int64
0x180034993  mov     r9d, ebx; unsigned int
0x180034996  mov     r8, r12; void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int)
0x180034999  mov     edx, r13d; int
0x18003499c  mov     rcx, rsi; this
0x18003499f  call    ?RecvResponse@HTTP_USER_REQUEST@@QEAAKHP6AXPEAX_KK0K@ZK1@Z; HTTP_USER_REQUEST::RecvResponse(int,void (*)(void *,unsigned __int64,ulong,void *,ulong),ulong,unsigned __int64)
0x1800349a4  mov     ebx, eax
0x1800349a6  cmp     eax, 3E5h
0x1800349ab  jz      loc_180034A70
0x1800349b1  test    r13d, r13d
0x1800349b4  jz      short loc_1800349C5
0x1800349b6  test    eax, eax
0x1800349b8  jz      loc_180034A72
0x1800349be  xor     ebp, ebp
0x1800349c0  jmp     loc_180034A77
0x1800349c5  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800349cc  xor     edx, edx; dwFlags
0x1800349ce  mov     r8d, 80h; dwBytes
0x1800349d4  call    cs:__imp_HeapAlloc
0x1800349da  test    rax, rax
0x1800349dd  jz      loc_180034C50
0x1800349e3  mov     qword ptr [rax+48h], 0
0x1800349eb  xorps   xmm0, xmm0
0x1800349ee  mov     qword ptr [rax+58h], 0
0x1800349f6  lea     rcx, ??_7WORK_ITEM@HTTP_THREAD_POOL@@6B@; const HTTP_THREAD_POOL::WORK_ITEM::`vftable'
0x1800349fd  mov     qword ptr [rax+50h], 0
0x180034a05  movups  xmmword ptr [rax+60h], xmm0
0x180034a09  mov     [rax+40h], rcx
0x180034a0d  lea     rcx, [rax+28h]
0x180034a11  mov     dword ptr [rax+24h], 0
0x180034a18  movups  xmmword ptr [rcx], xmm0
0x180034a1b  mov     qword ptr [rax+38h], 0
0x180034a23  mov     [rax], r12
0x180034a26  mov     [rax+8], rbp
0x180034a2a  mov     dword ptr [rax+10h], 1
0x180034a31  test    ebx, ebx
0x180034a33  jnz     loc_180034C9F
0x180034a39  xor     ecx, ecx
0x180034a3b  mov     r8d, 20000h
0x180034a41  xor     edx, edx
0x180034a43  mov     [rax+14h], r8d
0x180034a47  mov     r8d, 1; int
0x180034a4d  mov     [rax+20h], edx
0x180034a50  mov     rdx, rax; struct HTTP_COMPLETION_PACKET *
0x180034a53  mov     [rax+18h], rcx
0x180034a57  mov     rcx, rdi; this
0x180034a5a  call    ?IndicateCompletionStatusCommon@HTTP_REQUEST_HANDLE_OBJECT@@AEAAKPEAUHTTP_COMPLETION_PACKET@@H@Z; HTTP_REQUEST_HANDLE_OBJECT::IndicateCompletionStatusCommon(HTTP_COMPLETION_PACKET *,int)
0x180034a5f  xor     ebp, ebp
0x180034a61  mov     ebx, eax
0x180034a63  test    eax, eax
0x180034a65  setz    bpl
0x180034a69  cmp     eax, 3E5h
0x180034a6e  jnz     short loc_180034A77
0x180034a70  xor     ebx, ebx
0x180034a72  mov     ebp, 1
0x180034a77  test    r12, r12
0x180034a7a  jnz     loc_180034B6E
0x180034a80  mov     r13, [rsp+98h+var_28]
0x180034a85  mov     rax, [rsi]
0x180034a88  mov     rcx, rsi
0x180034a8b  mov     rax, [rax+8]
0x180034a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a94  xor     r12d, r12d
0x180034a97  mov     rsi, [rsp+98h+arg_10]
0x180034a9f  mov     r14, [rsp+98h+var_30]
0x180034aa4  mov     rcx, [rsp+98h+var_60]; void *
0x180034aa9  test    rcx, rcx
0x180034aac  jnz     loc_180034D56
0x180034ab2  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180034ab6  jz      short loc_180034AD9
0x180034ab8  mov     rdx, r15; Token
0x180034abb  xor     ecx, ecx; Thread
0x180034abd  call    cs:__imp_SetThreadToken
0x180034ac3  test    eax, eax
0x180034ac5  jz      loc_180034D65
0x180034acb  test    r15, r15
0x180034ace  jz      short loc_180034AD9
0x180034ad0  mov     rcx, r15; hObject
0x180034ad3  call    cs:__imp_CloseHandle
0x180034ad9  test    ebx, ebx
0x180034adb  jnz     loc_180034D70
0x180034ae1  test    byte ptr cs:xmmword_180107A60, 4
0x180034ae8  mov     r15, [rsp+98h+var_38]
0x180034aed  mov     rdi, [rsp+98h+var_20]
0x180034af2  jnz     loc_180034D9B
0x180034af8  cmp     [rsp+98h+var_48], 0
0x180034afd  jz      short loc_180034B28
0x180034aff  lea     rdx, [rsp+98h+var_58]
0x180034b04  mov     dword ptr [rsp+98h+hObject+4], r12d
0x180034b09  mov     ecx, 2
0x180034b0e  call    cs:__imp_EtwEventActivityIdControl
0x180034b14  test    eax, eax
0x180034b16  jle     short loc_180034B22
0x180034b18  movzx   eax, ax
0x180034b1b  or      eax, 80070000h
0x180034b20  test    eax, eax
0x180034b22  js      loc_180034CB9
0x180034b28  mov     ecx, ebx; dwErrCode
0x180034b2a  call    cs:__imp_SetLastError
0x180034b30  mov     eax, ebp
0x180034b32  mov     rcx, [rsp+98h+var_40]
0x180034b37  xor     rcx, rsp; StackCookie
0x180034b3a  call    __security_check_cookie
0x180034b3f  add     rsp, 80h
0x180034b46  pop     r12
0x180034b48  pop     rbp
0x180034b49  pop     rbx
0x180034b4a  retn
0x180034b4b  test    r12, r12
0x180034b4e  jz      loc_180034988
0x180034b54  mov     eax, ebx
0x180034b56  and     eax, 220000h
0x180034b5b  cmp     eax, 220000h
0x180034b60  jnz     loc_180034988
0x180034b66  xor     r13d, r13d
0x180034b69  jmp     loc_180034988
0x180034b6e  test    r13d, r13d
0x180034b71  jnz     short loc_180034B7B
0x180034b73  test    ebp, ebp
0x180034b75  jnz     loc_180034A80
0x180034b7b  mov     rcx, rdi; this
0x180034b7e  call    ?SafeReleaseCallbackInfo@HTTP_REQUEST_HANDLE_OBJECT@@QEAAXXZ; HTTP_REQUEST_HANDLE_OBJECT::SafeReleaseCallbackInfo(void)
0x180034b83  jmp     loc_180034A80
0x180034b88  test    byte ptr cs:xmmword_180107A50+2, 2
0x180034b8f  jnz     short loc_180034C00
0x180034b91  mov     rdi, r12
0x180034b94  mov     ebx, 6
0x180034b99  jmp     loc_1800348A9
0x180034b9e  mov     rcx, rdi; struct HANDLE_OBJECT *
0x180034ba1  call    ?GetRootHandle@@YAPEAVINTERNET_SESSION_HANDLE_OBJECT@@PEAVHANDLE_OBJECT@@@Z; GetRootHandle(HANDLE_OBJECT *)
0x180034ba6  lea     rcx, [rsp+98h+hObject]
0x180034bab  mov     [rsp+98h+hObject], r15
0x180034bb0  mov     r12, [rax+0D0h]
0x180034bb7  call    GetCurrentThreadImpersonationToken
0x180034bbc  mov     ebx, eax
0x180034bbe  test    eax, eax
0x180034bc0  jnz     loc_180034CC6
0x180034bc6  mov     rdx, r12; Token
0x180034bc9  xor     ecx, ecx; Thread
0x180034bcb  call    cs:__imp_SetThreadToken
0x180034bd1  test    eax, eax
0x180034bd3  jz      loc_180034D2D
0x180034bd9  mov     r15, [rsp+98h+hObject]
0x180034bde  jmp     loc_18003493F
0x180034be3  test    ebx, ebx
0x180034be5  jz      loc_1800348A9
0x180034beb  test    al, 2
0x180034bed  jz      short loc_180034B91
0x180034bef  mov     edx, 0Dh
0x180034bf4  jmp     short loc_180034C05
0x180034bf6  mov     ebx, 6
0x180034bfb  jmp     loc_180034AA4
0x180034c00  mov     edx, 0Bh
0x180034c05  mov     r9, rdi
0x180034c08  mov     [rsp+98h+var_78], rdi
0x180034c0d  lea     r8, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids
0x180034c14  mov     ecx, 211h
0x180034c19  call    WPP_SF_qq
0x180034c1e  jmp     loc_180034B91
0x180034c23  lea     rax, [rsp+98h+var_60]
0x180034c28  mov     [rsp+98h+var_70], r12d
0x180034c2d  mov     edx, 0Ah
0x180034c32  mov     [rsp+98h+var_78], rax
0x180034c37  mov     ecx, 411h
0x180034c3c  lea     r8, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids
0x180034c43  mov     r9, rdi
0x180034c46  call    WPP_SF_qqD
0x180034c4b  jmp     loc_180034872
0x180034c50  xor     ebp, ebp
0x180034c52  mov     ebx, 8
0x180034c57  jmp     loc_180034A77
0x180034c5c  mov     edx, 0Eh
0x180034c61  lea     r8, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids
0x180034c68  mov     ecx, 411h
0x180034c6d  mov     r9d, ebx
0x180034c70  call    WPP_SF_d
0x180034c75  jmp     loc_1800348BB
0x180034c7a  mov     edx, 0Ch
0x180034c7f  lea     r8, WPP_55aa5532adbc3902e0ca54617a4c0df4_Traceguids
0x180034c86  mov     ecx, 211h
0x180034c8b  mov     r9d, ebx
0x180034c8e  call    WPP_SF_d
0x180034c93  movzx   eax, byte ptr cs:xmmword_180107A50+2
0x180034c9a  jmp     loc_1800348A0
0x180034c9f  mov     qword ptr [rcx], 1
0x180034ca6  mov     edx, 10h
0x180034cab  mov     [rax+30h], ebx
0x180034cae  mov     r8d, 200000h
0x180034cb4  jmp     loc_180034A43
0x180034cb9  mov     dword ptr [rsp+98h+hObject+4], 90h
0x180034cc1  jmp     loc_180034B28
0x180034cc6  mov     rcx, [rsp+98h+hObject]; hObject
0x180034ccb  lea     rax, [rcx-1]
0x180034ccf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034cd3  jbe     short loc_180034D37
0x180034cd5  test    ebx, ebx
0x180034cd7  jnz     loc_180034A85
0x180034cdd  jmp     loc_18003493F
0x180034ce2  mov     edx, 0Dh
0x180034ce7  mov     [rsp+98h+var_78], rbx
0x180034cec  mov     ecx, 402h
0x180034cf1  lea     r8, WPP_a25211da527b3d0b325d5ad2246d882e_Traceguids
0x180034cf8  mov     r9, rdi
0x180034cfb  call    WPP_SF_qq
0x180034d00  jmp     loc_180034847
0x180034d05  mov     ebx, 57h ; 'W'
0x180034d0a  jmp     loc_180034AA4
0x180034d0f  mov     ebx, 2F8Ch
0x180034d14  jmp     loc_180034AA4
0x180034d19  cmp     [rsp+98h+var_60], rbp
0x180034d1e  jz      short loc_180034D70
0x180034d20  test    ebx, ebx
  ... truncated ...
```
