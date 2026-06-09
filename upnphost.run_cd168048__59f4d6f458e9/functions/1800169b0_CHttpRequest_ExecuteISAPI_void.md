# CHttpRequest::ExecuteISAPI(void)

- ea: `0x1800169b0`
- end: `0x180016d11`
- name: `?ExecuteISAPI@CHttpRequest@@AEAAHXZ`
- size: `865`
- prototype: `__int64 __fastcall(CHttpRequest *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180017060`

## callees

- `0x1800169b0`
- `0x180016d20`
- `0x180016fa0`
- `0x18003b1cc`
- `0x18003cb60`
- `0x18003d4b0`
- `0x180049430`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016b29`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016b29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016c32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016c32`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016cea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016cea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016c6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016c6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016bfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016bfe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180016c43`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180016c43`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016c58`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180016c58`

## pseudocode

```c
__int64 __fastcall CHttpRequest::ExecuteISAPI(CHttpRequest *this)
{
  unsigned int v2; // esi
  __int64 result; // rax
  const char near *const *v4; // rdx
  const char near *const *v5; // rcx
  const char near *const *v6; // rcx
  const char near *const *v7; // rcx
  struct _FILETIME *v8; // r15
  __int64 (__fastcall *v9)(_DWORD *); // rax
  unsigned int v10; // r14d
  BOOL v11; // eax
  void *v12; // rcx
  __int64 v13; // rdi
  DWORD v14; // eax
  void *v15; // rcx
  struct _FILETIME *v16; // [rsp+38h] [rbp-100h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-F8h] BYREF
  _DWORD v18[2]; // [rsp+50h] [rbp-E8h] BYREF
  CHttpRequest *v19; // [rsp+58h] [rbp-E0h]
  int v20; // [rsp+60h] [rbp-D8h]
  __int64 v21; // [rsp+B8h] [rbp-80h]
  const char near *const *v22; // [rsp+C0h] [rbp-78h]
  const char near *const *v23; // [rsp+C8h] [rbp-70h]
  const char near *const *v24; // [rsp+D0h] [rbp-68h]
  int v25; // [rsp+D8h] [rbp-60h]
  int v26; // [rsp+DCh] [rbp-5Ch]
  __int64 v27; // [rsp+E0h] [rbp-58h]
  const char near *const *v28; // [rsp+E8h] [rbp-50h]
  __int64 (__fastcall *v29)(void *, char *, void *, unsigned int *); // [rsp+F0h] [rbp-48h]
  __int64 (__fastcall *v30)(void *, void *, unsigned int *, unsigned int); // [rsp+F8h] [rbp-40h]
  __int64 (__fastcall *v31)(void *, void *, unsigned int *); // [rsp+100h] [rbp-38h]
  __int64 (__fastcall *v32)(void *, unsigned int, void *, unsigned int *, unsigned int *); // [rsp+108h] [rbp-30h]

  *(_QWORD *)&SystemTime.wYear = this;
  memset_0(v18, 0, 0xC0u);
  v2 = 0;
  v16 = 0;
  result = CISAPICache::Load(*((_QWORD *)g_pVars + 8), *((_QWORD *)this + 16), (CISAPI **)&v16);
  if ( result )
  {
    memset_0(v18, 0, 0xC0u);
    v18[0] = 192;
    v18[1] = 0x80000;
    v19 = this;
    v20 = 200;
    v21 = *((_QWORD *)this + 7);
    v4 = &cszEmpty;
    v5 = &cszEmpty;
    if ( *((_QWORD *)this + 15) )
      v5 = (const char near *const *)*((_QWORD *)this + 15);
    v22 = v5;
    v6 = &cszEmpty;
    if ( *((_QWORD *)this + 9) )
      v6 = (const char near *const *)*((_QWORD *)this + 9);
    v28 = v6;
    v7 = &cszEmpty;
    if ( *((_QWORD *)this + 18) )
      v7 = (const char near *const *)*((_QWORD *)this + 18);
    v23 = v7;
    if ( *((_QWORD *)this + 19) )
      v4 = (const char near *const *)*((_QWORD *)this + 19);
    v24 = v4;
    v25 = *((_DWORD *)this + 20);
    v26 = *((_DWORD *)this + 9);
    v27 = *((_QWORD *)this + 3);
    v29 = GetServerVariable;
    v30 = WriteClient;
    v31 = ReadClient;
    v32 = ServerSupportFunction;
    *((_QWORD *)this + 22) = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 24) = v18;
    v8 = v16;
    v9 = (__int64 (__fastcall *)(_DWORD *))v16[3];
    if ( v9 )
      v10 = v9(v18);
    else
      v10 = 4;
    v11 = v10 == 2;
    *((_DWORD *)this + 27) = v11;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a551daa9c3c83c532b1715f40d740de9_Traceguids, v10, v11);
    }
    if ( v10 == 3 )
    {
      v14 = 128;
      v15 = (void *)*((_QWORD *)this + 22);
      if ( v15 )
        v14 = WaitForSingleObject(v15, 0x493E0u);
      if ( v14 )
        v10 = 4;
      else
        v10 = *((_DWORD *)this + 46);
    }
    v12 = (void *)*((_QWORD *)this + 22);
    if ( v12 )
    {
      CloseHandle(v12);
      *((_QWORD *)this + 22) = 0;
    }
    CHttpRequest::StartRemoveISAPICacheIfNeeded((CHttpRequest *)v12);
    SystemTime = 0;
    if ( v8 )
    {
      v13 = *((_QWORD *)g_pVars + 8);
      EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
      GetSystemTime(&SystemTime);
      SystemTimeToFileTime(&SystemTime, v8 + 7);
      --v8[6].dwLowDateTime;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
    }
    *((_QWORD *)this + 24) = 0;
    LOBYTE(v2) = v10 != 4;
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x1800169b0  mov     [rsp+arg_8], rbx
0x1800169b5  mov     [rsp+arg_10], rsi
0x1800169ba  push    rdi
0x1800169bb  push    r14
0x1800169bd  push    r15
0x1800169bf  sub     rsp, 120h
0x1800169c6  mov     rax, cs:__security_cookie
0x1800169cd  xor     rax, rsp
0x1800169d0  mov     [rsp+138h+var_28], rax
0x1800169d8  mov     rbx, rcx
0x1800169db  mov     qword ptr [rsp+138h+SystemTime.wYear], rcx
0x1800169e0  mov     [rsp+138h+var_108], 4
0x1800169e8  xor     edx, edx; Val
0x1800169ea  mov     r8d, 0C0h; Size
0x1800169f0  lea     rcx, [rsp+138h+var_E8]; void *
0x1800169f5  call    memset_0
0x1800169fa  xor     esi, esi
0x1800169fc  mov     [rsp+138h+var_100], rsi
0x180016a01  lea     r8, [rsp+138h+var_100]
0x180016a06  mov     rdx, [rbx+80h]
0x180016a0d  mov     rcx, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x180016a14  mov     rcx, [rcx+40h]
0x180016a18  call    ?Load@CISAPICache@@QEAAPEAUHINSTANCE__@@PEAGPEAPEAVCISAPI@@W4SCRIPT_TYPE@@@Z; CISAPICache::Load(ushort *,CISAPI * *,SCRIPT_TYPE)
0x180016a1d  test    rax, rax
0x180016a20  jz      loc_180016B65
0x180016a26  xor     edx, edx; Val
0x180016a28  mov     r8d, 0C0h; Size
0x180016a2e  lea     rcx, [rsp+138h+var_E8]; void *
0x180016a33  call    memset_0
0x180016a38  mov     [rsp+138h+var_E8], 0C0h
0x180016a40  mov     [rsp+138h+var_E4], 80000h
0x180016a48  mov     [rsp+138h+var_E0], rbx
0x180016a4d  mov     [rsp+138h+var_D8], 0C8h
0x180016a55  mov     rax, [rbx+38h]
0x180016a59  mov     [rsp+138h+var_80], rax
0x180016a61  mov     rax, [rbx+78h]
0x180016a65  lea     rdx, ?cszEmpty@@3QBDB; char const near * const cszEmpty
0x180016a6c  mov     rcx, rdx
0x180016a6f  test    rax, rax
0x180016a72  cmovnz  rcx, rax
0x180016a76  mov     [rsp+138h+var_78], rcx
0x180016a7e  mov     rax, [rbx+48h]
0x180016a82  mov     rcx, rdx
0x180016a85  test    rax, rax
0x180016a88  cmovnz  rcx, rax
0x180016a8c  mov     [rsp+138h+var_50], rcx
0x180016a94  mov     rax, [rbx+90h]
0x180016a9b  mov     rcx, rdx
0x180016a9e  test    rax, rax
0x180016aa1  cmovnz  rcx, rax
0x180016aa5  mov     [rsp+138h+var_70], rcx
0x180016aad  mov     rax, [rbx+98h]
0x180016ab4  test    rax, rax
0x180016ab7  cmovnz  rdx, rax
0x180016abb  mov     [rsp+138h+var_68], rdx
0x180016ac3  mov     eax, [rbx+50h]
0x180016ac6  mov     [rsp+138h+var_60], eax
0x180016acd  mov     eax, [rbx+24h]
0x180016ad0  mov     [rsp+138h+var_5C], eax
0x180016ad7  mov     rax, [rbx+18h]
0x180016adb  mov     [rsp+138h+var_58], rax
0x180016ae3  lea     rax, ?GetServerVariable@@YAHPEAXPEAD0PEAK@Z; GetServerVariable(void *,char *,void *,ulong *)
0x180016aea  mov     [rsp+138h+var_48], rax
0x180016af2  lea     rax, ?WriteClient@@YAHPEAX0PEAKK@Z; WriteClient(void *,void *,ulong *,ulong)
0x180016af9  mov     [rsp+138h+var_40], rax
0x180016b01  lea     rax, ?ReadClient@@YAHPEAX0PEAK@Z; ReadClient(void *,void *,ulong *)
0x180016b08  mov     [rsp+138h+var_38], rax
0x180016b10  lea     rax, ?ServerSupportFunction@@YAHPEAXK0PEAK1@Z; ServerSupportFunction(void *,ulong,void *,ulong *,ulong *)
0x180016b17  mov     [rsp+138h+var_30], rax
0x180016b1f  xor     r9d, r9d; lpName
0x180016b22  xor     r8d, r8d; bInitialState
0x180016b25  xor     edx, edx; bManualReset
0x180016b27  xor     ecx, ecx; lpEventAttributes
0x180016b29  call    cs:__imp_CreateEventW
0x180016b30  nop     dword ptr [rax+rax+00h]
0x180016b35  mov     [rbx+0B0h], rax
0x180016b3c  lea     rax, [rsp+138h+var_E8]
0x180016b41  mov     [rbx+0C0h], rax
0x180016b48  mov     r15, [rsp+138h+var_100]
0x180016b4d  mov     rax, [r15+18h]
0x180016b51  test    rax, rax
0x180016b54  jz      short loc_180016B6A
0x180016b56  lea     rcx, [rsp+138h+var_E8]
0x180016b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b60  mov     r14d, eax
0x180016b63  jmp     short loc_180016B70
0x180016b65  jmp     loc_180016C89
0x180016b6a  mov     r14d, 4
0x180016b70  mov     [rsp+138h+var_108], r14d
0x180016b75  jmp     short loc_180016BBC
0x180016b77  lea     rdx, WPP_GLOBAL_Control
0x180016b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b85  cmp     rcx, rdx
0x180016b88  jz      short loc_180016BAB
0x180016b8a  test    dword ptr [rcx+1Ch], 1000h
0x180016b91  jz      short loc_180016BAB
0x180016b93  mov     r9d, eax
0x180016b96  mov     edx, 0Ah
0x180016b9b  lea     r8, WPP_a551daa9c3c83c532b1715f40d740de9_Traceguids
0x180016ba2  mov     rcx, [rcx+10h]
0x180016ba6  call    WPP_SF_d
0x180016bab  xor     esi, esi
0x180016bad  mov     r14d, [rsp+138h+var_108]
0x180016bb2  mov     r15, [rsp+138h+var_100]
0x180016bb7  mov     rbx, qword ptr [rsp+138h+SystemTime.wYear]
0x180016bbc  mov     eax, esi
0x180016bbe  cmp     r14d, 2
0x180016bc2  setz    al
0x180016bc5  mov     [rbx+6Ch], eax
0x180016bc8  lea     rdx, WPP_GLOBAL_Control
0x180016bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bd6  cmp     rcx, rdx
0x180016bd9  jz      short loc_180016BE8
0x180016bdb  test    dword ptr [rcx+1Ch], 1000h
0x180016be2  jnz     loc_180016CB3
0x180016be8  cmp     r14d, 3
0x180016bec  jz      loc_180016CD4
0x180016bf2  mov     rcx, [rbx+0B0h]; hObject
0x180016bf9  test    rcx, rcx
0x180016bfc  jz      short loc_180016C11
0x180016bfe  call    cs:__imp_CloseHandle
0x180016c05  nop     dword ptr [rax+rax+00h]
0x180016c0a  mov     [rbx+0B0h], rsi
0x180016c11  call    ?StartRemoveISAPICacheIfNeeded@CHttpRequest@@AEAAXXZ; CHttpRequest::StartRemoveISAPICacheIfNeeded(void)
0x180016c16  xorps   xmm0, xmm0
0x180016c19  movups  xmmword ptr [rsp+138h+SystemTime.wYear], xmm0
0x180016c1e  test    r15, r15
0x180016c21  jz      short loc_180016C78
0x180016c23  mov     rax, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x180016c2a  mov     rdi, [rax+40h]
0x180016c2e  lea     rcx, [rdi+8]; lpCriticalSection
0x180016c32  call    cs:__imp_EnterCriticalSection
0x180016c39  nop     dword ptr [rax+rax+00h]
0x180016c3e  lea     rcx, [rsp+138h+SystemTime]; lpSystemTime
0x180016c43  call    cs:__imp_GetSystemTime
0x180016c4a  nop     dword ptr [rax+rax+00h]
0x180016c4f  lea     rdx, [r15+38h]; lpFileTime
0x180016c53  lea     rcx, [rsp+138h+SystemTime]; lpSystemTime
0x180016c58  call    cs:__imp_SystemTimeToFileTime
0x180016c5f  nop     dword ptr [rax+rax+00h]
0x180016c64  dec     dword ptr [r15+30h]
0x180016c68  lea     rcx, [rdi+8]; lpCriticalSection
0x180016c6c  call    cs:__imp_LeaveCriticalSection
0x180016c73  nop     dword ptr [rax+rax+00h]
0x180016c78  mov     [rbx+0C0h], rsi
0x180016c7f  cmp     r14d, 4
0x180016c83  setnz   sil
0x180016c87  mov     eax, esi
0x180016c89  mov     rcx, [rsp+138h+var_28]
0x180016c91  xor     rcx, rsp; StackCookie
0x180016c94  call    __security_check_cookie
0x180016c99  lea     r11, [rsp+138h+var_18]
0x180016ca1  mov     rbx, [r11+28h]
0x180016ca5  mov     rsi, [r11+30h]
0x180016ca9  mov     rsp, r11
0x180016cac  pop     r15
0x180016cae  pop     r14
0x180016cb0  pop     rdi
0x180016cb1  retn
0x180016cb3  mov     edx, 0Bh
0x180016cb8  mov     [rsp+138h+var_118], eax
0x180016cbc  mov     r9d, r14d
0x180016cbf  lea     r8, WPP_a551daa9c3c83c532b1715f40d740de9_Traceguids
0x180016cc6  mov     rcx, [rcx+10h]
0x180016cca  call    WPP_SF_dd
0x180016ccf  jmp     loc_180016BE8
0x180016cd4  mov     eax, 80h
0x180016cd9  mov     rcx, [rbx+0B0h]; hHandle
0x180016ce0  test    rcx, rcx
0x180016ce3  jz      short loc_180016CF6
0x180016ce5  mov     edx, 493E0h; dwMilliseconds
0x180016cea  call    cs:__imp_WaitForSingleObject
0x180016cf1  nop     dword ptr [rax+rax+00h]
0x180016cf6  test    eax, eax
0x180016cf8  jnz     short loc_180016D06
0x180016cfa  mov     r14d, [rbx+0B8h]
0x180016d01  jmp     loc_180016BF2
0x180016d06  mov     r14d, 4
0x180016d0c  jmp     loc_180016BF2
```
