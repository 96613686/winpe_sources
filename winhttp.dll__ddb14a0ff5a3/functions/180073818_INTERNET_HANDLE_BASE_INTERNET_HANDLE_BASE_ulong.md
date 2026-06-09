# INTERNET_HANDLE_BASE::INTERNET_HANDLE_BASE(ulong)

- ea: `0x180073818`
- end: `0x180073b30`
- name: `??0INTERNET_HANDLE_BASE@@QEAA@K@Z`
- size: `792`
- prototype: `INTERNET_HANDLE_BASE *__fastcall(INTERNET_HANDLE_BASE *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800600c0`

## callees

- `0x180073818`
- `0x1800cf008`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800dd2e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800738c5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800738d2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800738c5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800738d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180073a42`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180073a42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180073a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180073a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800739f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800739f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800739fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800739fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073a50`

## pseudocode

```c
INTERNET_HANDLE_BASE *__fastcall INTERNET_HANDLE_BASE::INTERNET_HANDLE_BASE(
        INTERNET_HANDLE_BASE *this,
        unsigned int a2)
{
  bool v4; // zf
  int v5; // edi
  signed __int32 v6; // esi
  DWORD CurrentProcessId; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r9
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v13; // rdx
  __int64 v14; // [rsp+20h] [rbp-58h]

  *(_QWORD *)this = &HANDLE_OBJECT::`vftable';
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_q(1032, 10, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
  _InterlockedAdd(&GlobalInternetOpenHandleCount, 1u);
  *((_QWORD *)this + 4) = this;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 10) = 1215194439;
  *(_QWORD *)((char *)this + 44) = 1;
  *((_DWORD *)this + 13) = 0;
  *((_DWORD *)this + 14) = 1094795585;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
  {
    WPP_SF_qq(
      1032,
      11,
      (unsigned int)WPP_989094c1a00a31c88345b82a0793d746_Traceguids,
      *((_QWORD *)this + 4),
      (__int64)this);
    if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
      WPP_SF_(1032, 13, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
  }
  *(_QWORD *)this = &INTERNET_HANDLE_BASE::`vftable';
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 30) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
    WPP_SF_(1032, 27, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
  *((_DWORD *)this + 32) = a2;
  *((_QWORD *)this + 12) = 0;
  v4 = GlobalEnableDefaultHttp2 == 0;
  *((_DWORD *)this + 92) = 1;
  *((_DWORD *)this + 93) = 1;
  *((_QWORD *)this + 26) = 0;
  *(_QWORD *)((char *)this + 132) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 59) = 0;
  *((_DWORD *)this + 37) = -1;
  *((_DWORD *)this + 38) = -1;
  *((_DWORD *)this + 50) = 65001;
  *(_QWORD *)((char *)this + 140) = (a2 >> 28) & 1;
  *(_QWORD *)((char *)this + 156) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *(_QWORD *)((char *)this + 220) = 0;
  *((_DWORD *)this + 57) = 0;
  if ( !v4 )
    *((_DWORD *)this + 57) = 1;
  *((_DWORD *)this + 58) = GlobalDefaultHttpProtocolRequired;
  *((_DWORD *)this + 74) = g_AllowHttp2TransferEncoding;
  *(_QWORD *)((char *)this + 300) = 0;
  *((_DWORD *)this + 77) = 0;
  *((_BYTE *)this + 312) = 0;
  *((_DWORD *)this + 79) = -1;
  *((_QWORD *)this + 40) = 0;
  *((_DWORD *)this + 54) = 0;
  *((_DWORD *)this + 10) = 1952804425;
  if ( this != (INTERNET_HANDLE_BASE *)-184LL )
  {
    v5 = *((_DWORD *)this + 8);
    v6 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    CurrentProcessId = GetCurrentProcessId();
    CurrentThreadId = GetCurrentThreadId();
    *((_DWORD *)this + 46) = v5;
    *((_DWORD *)this + 47) = v6;
    *((_DWORD *)this + 48) = CurrentProcessId ^ (CurrentThreadId << 16);
    *((_DWORD *)this + 49) = (_DWORD)this;
  }
  v9 = *((unsigned int *)this + 18);
  if ( !(_DWORD)v9 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, (PHANDLE)this + 26) )
    {
      *((_QWORD *)this + 26) = 0;
      LastError = GetLastError();
      if ( LastError != 1008 )
        *((_DWORD *)this + 18) = LastError;
    }
    if ( (BYTE1(xmmword_180107A60) & 1) == 0 )
      return this;
    v13 = 30;
LABEL_17:
    WPP_SF_(1032, v13, WPP_989094c1a00a31c88345b82a0793d746_Traceguids);
    return this;
  }
  if ( (BYTE1(xmmword_180107A50) & 1) != 0 )
    WPP_SF_d(520, 28, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v9, v14);
  if ( (BYTE1(xmmword_180107A60) & 1) != 0 )
  {
    v13 = 29;
    goto LABEL_17;
  }
  return this;
}

```

## disassembly

```asm
0x180073818  push    rbx
0x18007381a  push    rbp
0x18007381b  push    rsi
0x18007381c  push    rdi
0x18007381d  push    r12
0x18007381f  push    r13
0x180073821  push    r14
0x180073823  push    r15
0x180073825  sub     rsp, 38h
0x180073829  lea     rax, ??_7HANDLE_OBJECT@@6B@; const HANDLE_OBJECT::`vftable'
0x180073830  mov     ebx, edx
0x180073832  mov     [rcx], rax
0x180073835  mov     r14, rcx
0x180073838  mov     r13d, 1
0x18007383e  lea     rdi, WPP_989094c1a00a31c88345b82a0793d746_Traceguids
0x180073845  test    byte ptr cs:xmmword_180107A60+1, r13b
0x18007384c  mov     esi, 408h
0x180073851  jnz     loc_180073A8F
0x180073857  lock add cs:?GlobalInternetOpenHandleCount@@3JA, r13d; long GlobalInternetOpenHandleCount
0x18007385f  xor     r12d, r12d
0x180073862  mov     [r14+20h], r14
0x180073866  mov     [r14+18h], r12
0x18007386a  mov     [r14+48h], r12d
0x18007386e  mov     dword ptr [r14+28h], 486E6547h
0x180073876  mov     [r14+2Ch], r13d
0x18007387a  mov     [r14+30h], r12d
0x18007387e  mov     [r14+34h], r12d
0x180073882  mov     dword ptr [r14+38h], 41414141h
0x18007388a  mov     [r14+40h], r12
0x18007388e  mov     [r14+50h], r12
0x180073892  mov     [r14+58h], r12
0x180073896  mov     al, byte ptr cs:xmmword_180107A60+1
0x18007389c  test    r13b, al
0x18007389f  jnz     loc_180073AA6
0x1800738a5  lea     rax, ??_7INTERNET_HANDLE_BASE@@6B@; const INTERNET_HANDLE_BASE::`vftable'
0x1800738ac  mov     [r14], rax
0x1800738af  lea     rcx, [r14+0F8h]; lpCriticalSection
0x1800738b6  mov     [r14+70h], r12
0x1800738ba  mov     [r14+78h], r12
0x1800738be  mov     [r14+0F0h], r12
0x1800738c5  call    cs:__imp_InitializeCriticalSection
0x1800738cb  lea     rcx, [r14+148h]; lpCriticalSection
0x1800738d2  call    cs:__imp_InitializeCriticalSection
0x1800738d8  test    byte ptr cs:xmmword_180107A60+1, r13b
0x1800738df  jnz     loc_180073AE1
0x1800738e5  or      ecx, 0FFFFFFFFh
0x1800738e8  mov     [r14+80h], ebx
0x1800738ef  shr     ebx, 1Ch
0x1800738f2  lea     rbp, [r14+0D0h]
0x1800738f9  and     ebx, r13d
0x1800738fc  mov     [r14+60h], r12
0x180073900  cmp     cs:?GlobalEnableDefaultHttp2@@3HA, r12d; int GlobalEnableDefaultHttp2
0x180073907  mov     [r14+170h], r13d
0x18007390e  mov     [r14+174h], r13d
0x180073915  mov     [rbp+0], r12
0x180073919  mov     [r14+84h], r12
0x180073920  mov     [r14+120h], r12
0x180073927  mov     [r14+68h], r12d
0x18007392b  mov     [r14+40h], r12
0x18007392f  mov     [r14+0ECh], r12d
0x180073936  mov     [r14+94h], ecx
0x18007393d  mov     [r14+98h], ecx
0x180073944  mov     dword ptr [r14+0C8h], 0FDE9h
0x18007394f  mov     [r14+8Ch], ebx
0x180073956  mov     [r14+90h], r12d
0x18007395d  mov     [r14+9Ch], r12
0x180073964  mov     [r14+0A8h], r12
0x18007396b  mov     [r14+0B0h], r12
0x180073972  mov     [r14+0DCh], r12
0x180073979  mov     [r14+0E4h], r12d
0x180073980  jz      short loc_180073989
0x180073982  mov     [r14+0E4h], r13d
0x180073989  mov     eax, cs:?GlobalDefaultHttpProtocolRequired@@3HA; int GlobalDefaultHttpProtocolRequired
0x18007398f  lea     r15, [r14+0B8h]
0x180073996  mov     [r14+0E8h], eax
0x18007399d  mov     eax, cs:?g_AllowHttp2TransferEncoding@@3HA; int g_AllowHttp2TransferEncoding
0x1800739a3  mov     [r14+128h], eax
0x1800739aa  mov     [r14+12Ch], r12
0x1800739b1  mov     [r14+134h], r12d
0x1800739b8  mov     [r14+138h], r12b
0x1800739bf  mov     [r14+13Ch], ecx
0x1800739c6  mov     [r14+140h], r12
0x1800739cd  mov     [r14+0D8h], r12d
0x1800739d4  mov     dword ptr [r14+28h], 74656E49h
0x1800739dc  test    r15, r15
0x1800739df  jz      short loc_180073A21
0x1800739e1  mov     edi, [r14+20h]
0x1800739e5  mov     esi, r13d
0x1800739e8  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x1800739f0  add     esi, r13d
0x1800739f3  call    cs:__imp_GetCurrentProcessId
0x1800739f9  mov     ebx, eax
0x1800739fb  call    cs:__imp_GetCurrentThreadId
0x180073a01  mov     [r15], edi
0x180073a04  lea     rdi, WPP_989094c1a00a31c88345b82a0793d746_Traceguids
0x180073a0b  shl     eax, 10h
0x180073a0e  xor     eax, ebx
0x180073a10  mov     [r15+4], esi
0x180073a14  mov     [r15+8], eax
0x180073a18  mov     esi, 408h
0x180073a1d  mov     [r15+0Ch], r14d
0x180073a21  mov     r9d, [r14+48h]
0x180073a25  test    r9d, r9d
0x180073a28  jnz     loc_180073AF5
0x180073a2e  call    cs:__imp_GetCurrentThread
0x180073a34  mov     r9, rbp; TokenHandle
0x180073a37  mov     r8d, r13d; OpenAsSelf
0x180073a3a  mov     rcx, rax; ThreadHandle
0x180073a3d  mov     edx, 2000Ch; DesiredAccess
0x180073a42  call    cs:__imp_OpenThreadToken
0x180073a48  test    eax, eax
0x180073a4a  jnz     short loc_180073A61
0x180073a4c  mov     [rbp+0], r12
0x180073a50  call    cs:__imp_GetLastError
0x180073a56  cmp     eax, 3F0h
0x180073a5b  jnz     loc_180073B27
0x180073a61  test    byte ptr cs:xmmword_180107A60+1, r13b
0x180073a68  jnz     short loc_180073A7E
0x180073a6a  mov     rax, r14
0x180073a6d  add     rsp, 38h
0x180073a71  pop     r15
0x180073a73  pop     r14
0x180073a75  pop     r13
0x180073a77  pop     r12
0x180073a79  pop     rdi
0x180073a7a  pop     rsi
0x180073a7b  pop     rbp
0x180073a7c  pop     rbx
0x180073a7d  retn
0x180073a7e  mov     edx, 1Eh
0x180073a83  mov     r8, rdi
0x180073a86  mov     ecx, esi
0x180073a88  call    WPP_SF_
0x180073a8d  jmp     short loc_180073A6A
0x180073a8f  mov     edx, 0Ah
0x180073a94  mov     ecx, esi
0x180073a96  mov     r9, r14
0x180073a99  mov     r8, rdi
0x180073a9c  call    WPP_SF_q
0x180073aa1  jmp     loc_180073857
0x180073aa6  mov     r9, [r14+20h]
0x180073aaa  mov     edx, 0Bh
0x180073aaf  mov     ecx, esi
0x180073ab1  mov     [rsp+78h+var_58], r14
0x180073ab6  mov     r8, rdi
0x180073ab9  call    WPP_SF_qq
0x180073abe  mov     al, byte ptr cs:xmmword_180107A60+1
0x180073ac4  test    r13b, al
0x180073ac7  jz      loc_1800738A5
0x180073acd  mov     edx, 0Dh
0x180073ad2  mov     ecx, esi
0x180073ad4  mov     r8, rdi
0x180073ad7  call    WPP_SF_
0x180073adc  jmp     loc_1800738A5
0x180073ae1  mov     edx, 1Bh
0x180073ae6  mov     ecx, esi
0x180073ae8  mov     r8, rdi
0x180073aeb  call    WPP_SF_
0x180073af0  jmp     loc_1800738E5
0x180073af5  test    byte ptr cs:xmmword_180107A50+1, r13b
0x180073afc  jz      short loc_180073B10
0x180073afe  mov     edx, 1Ch
0x180073b03  mov     ecx, 208h
0x180073b08  mov     r8, rdi
0x180073b0b  call    WPP_SF_d
0x180073b10  test    byte ptr cs:xmmword_180107A60+1, r13b
0x180073b17  jz      loc_180073A6A
0x180073b1d  mov     edx, 1Dh
0x180073b22  jmp     loc_180073A83
0x180073b27  mov     [r14+48h], eax
0x180073b2b  jmp     loc_180073A61
```
