# CHttpRequest::ExecuteISAPI(void)

- ea: `0x180001f50`
- end: `0x180002286`
- name: `?ExecuteISAPI@CHttpRequest@@AEAAHXZ`
- size: `822`
- prototype: `__int64 __fastcall(CHttpRequest *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002600`

## callees

- `0x180001f50`
- `0x180002290`
- `0x180002550`
- `0x180038ce4`
- `0x18003a560`
- `0x18003ae80`
- `0x180046704`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800020c9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800020c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002265`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002265`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002198`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002198`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800021d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800021d1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800021e0`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800021e0`

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
  int v10; // r14d
  void *v11; // rcx
  __int64 v12; // rdi
  DWORD v13; // eax
  void *v14; // rcx
  __int64 v15; // [rsp+38h] [rbp-100h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-F8h] BYREF
  _DWORD v17[2]; // [rsp+50h] [rbp-E8h] BYREF
  CHttpRequest *v18; // [rsp+58h] [rbp-E0h]
  int v19; // [rsp+60h] [rbp-D8h]
  __int64 v20; // [rsp+B8h] [rbp-80h]
  const char near *const *v21; // [rsp+C0h] [rbp-78h]
  const char near *const *v22; // [rsp+C8h] [rbp-70h]
  const char near *const *v23; // [rsp+D0h] [rbp-68h]
  int v24; // [rsp+D8h] [rbp-60h]
  int v25; // [rsp+DCh] [rbp-5Ch]
  __int64 v26; // [rsp+E0h] [rbp-58h]
  const char near *const *v27; // [rsp+E8h] [rbp-50h]
  __int64 (__fastcall *v28)(void *, char *, void *, unsigned int *); // [rsp+F0h] [rbp-48h]
  __int64 (__fastcall *v29)(void *, void *, unsigned int *, unsigned int); // [rsp+F8h] [rbp-40h]
  __int64 (__fastcall *v30)(void *, void *, unsigned int *); // [rsp+100h] [rbp-38h]
  __int64 (__fastcall *v31)(void *, unsigned int, void *, unsigned int *, unsigned int *); // [rsp+108h] [rbp-30h]

  *(_QWORD *)&SystemTime.wYear = this;
  memset_0(v17, 0, 0xC0u);
  v2 = 0;
  v15 = 0;
  result = CISAPICache::Load(*((_QWORD *)g_pVars + 8), *((_QWORD *)this + 16), &v15);
  if ( result )
  {
    memset_0(v17, 0, 0xC0u);
    v17[0] = 192;
    v17[1] = 0x80000;
    v18 = this;
    v19 = 200;
    v20 = *((_QWORD *)this + 7);
    v4 = &cszEmpty;
    v5 = &cszEmpty;
    if ( *((_QWORD *)this + 15) )
      v5 = (const char near *const *)*((_QWORD *)this + 15);
    v21 = v5;
    v6 = &cszEmpty;
    if ( *((_QWORD *)this + 9) )
      v6 = (const char near *const *)*((_QWORD *)this + 9);
    v27 = v6;
    v7 = &cszEmpty;
    if ( *((_QWORD *)this + 18) )
      v7 = (const char near *const *)*((_QWORD *)this + 18);
    v22 = v7;
    if ( *((_QWORD *)this + 19) )
      v4 = (const char near *const *)*((_QWORD *)this + 19);
    v23 = v4;
    v24 = *((_DWORD *)this + 20);
    v25 = *((_DWORD *)this + 9);
    v26 = *((_QWORD *)this + 3);
    v28 = GetServerVariable;
    v29 = WriteClient;
    v30 = ReadClient;
    v31 = ServerSupportFunction;
    *((_QWORD *)this + 22) = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 24) = v17;
    v8 = (struct _FILETIME *)v15;
    v9 = *(__int64 (__fastcall **)(_DWORD *))(v15 + 24);
    if ( v9 )
      v10 = v9(v17);
    else
      v10 = 4;
    *((_DWORD *)this + 27) = v10 == 2;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a551daa9c3c83c532b1715f40d740de9_Traceguids);
    }
    if ( v10 == 3 )
    {
      v13 = 128;
      v14 = (void *)*((_QWORD *)this + 22);
      if ( v14 )
        v13 = WaitForSingleObject(v14, 0x493E0u);
      if ( v13 )
        v10 = 4;
      else
        v10 = *((_DWORD *)this + 46);
    }
    v11 = (void *)*((_QWORD *)this + 22);
    if ( v11 )
    {
      CloseHandle(v11);
      *((_QWORD *)this + 22) = 0;
    }
    CHttpRequest::StartRemoveISAPICacheIfNeeded((CHttpRequest *)v11);
    SystemTime = 0;
    if ( v8 )
    {
      v12 = *((_QWORD *)g_pVars + 8);
      EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
      GetSystemTime(&SystemTime);
      SystemTimeToFileTime(&SystemTime, v8 + 7);
      --v8[6].dwLowDateTime;
      LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
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
0x180001f50  mov     [rsp+arg_8], rbx
0x180001f55  mov     [rsp+arg_10], rsi
0x180001f5a  push    rdi
0x180001f5b  push    r14
0x180001f5d  push    r15
0x180001f5f  sub     rsp, 120h
0x180001f66  mov     rax, cs:__security_cookie
0x180001f6d  xor     rax, rsp
0x180001f70  mov     [rsp+138h+var_28], rax
0x180001f78  mov     rbx, rcx
0x180001f7b  mov     qword ptr [rsp+138h+SystemTime.wYear], rcx
0x180001f80  mov     [rsp+138h+var_108], 4
0x180001f88  xor     edx, edx; Val
0x180001f8a  mov     r8d, 0C0h; Size
0x180001f90  lea     rcx, [rsp+138h+var_E8]; void *
0x180001f95  call    memset_0
0x180001f9a  xor     esi, esi
0x180001f9c  mov     [rsp+138h+var_100], rsi
0x180001fa1  lea     r8, [rsp+138h+var_100]
0x180001fa6  mov     rdx, [rbx+80h]
0x180001fad  mov     rcx, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x180001fb4  mov     rcx, [rcx+40h]
0x180001fb8  call    ?Load@CISAPICache@@QEAAPEAUHINSTANCE__@@PEAGPEAPEAVCISAPI@@W4SCRIPT_TYPE@@@Z; CISAPICache::Load(ushort *,CISAPI * *,SCRIPT_TYPE)
0x180001fbd  test    rax, rax
0x180001fc0  jz      loc_1800020FF
0x180001fc6  xor     edx, edx; Val
0x180001fc8  mov     r8d, 0C0h; Size
0x180001fce  lea     rcx, [rsp+138h+var_E8]; void *
0x180001fd3  call    memset_0
0x180001fd8  mov     [rsp+138h+var_E8], 0C0h
0x180001fe0  mov     [rsp+138h+var_E4], 80000h
0x180001fe8  mov     [rsp+138h+var_E0], rbx
0x180001fed  mov     [rsp+138h+var_D8], 0C8h
0x180001ff5  mov     rax, [rbx+38h]
0x180001ff9  mov     [rsp+138h+var_80], rax
0x180002001  mov     rax, [rbx+78h]
0x180002005  lea     rdx, ?cszEmpty@@3QBDB; char const near * const cszEmpty
0x18000200c  mov     rcx, rdx
0x18000200f  test    rax, rax
0x180002012  cmovnz  rcx, rax
0x180002016  mov     [rsp+138h+var_78], rcx
0x18000201e  mov     rax, [rbx+48h]
0x180002022  mov     rcx, rdx
0x180002025  test    rax, rax
0x180002028  cmovnz  rcx, rax
0x18000202c  mov     [rsp+138h+var_50], rcx
0x180002034  mov     rax, [rbx+90h]
0x18000203b  mov     rcx, rdx
0x18000203e  test    rax, rax
0x180002041  cmovnz  rcx, rax
0x180002045  mov     [rsp+138h+var_70], rcx
0x18000204d  mov     rax, [rbx+98h]
0x180002054  test    rax, rax
0x180002057  cmovnz  rdx, rax
0x18000205b  mov     [rsp+138h+var_68], rdx
0x180002063  mov     eax, [rbx+50h]
0x180002066  mov     [rsp+138h+var_60], eax
0x18000206d  mov     eax, [rbx+24h]
0x180002070  mov     [rsp+138h+var_5C], eax
0x180002077  mov     rax, [rbx+18h]
0x18000207b  mov     [rsp+138h+var_58], rax
0x180002083  lea     rax, ?GetServerVariable@@YAHPEAXPEAD0PEAK@Z; GetServerVariable(void *,char *,void *,ulong *)
0x18000208a  mov     [rsp+138h+var_48], rax
0x180002092  lea     rax, ?WriteClient@@YAHPEAX0PEAKK@Z; WriteClient(void *,void *,ulong *,ulong)
0x180002099  mov     [rsp+138h+var_40], rax
0x1800020a1  lea     rax, ?ReadClient@@YAHPEAX0PEAK@Z; ReadClient(void *,void *,ulong *)
0x1800020a8  mov     [rsp+138h+var_38], rax
0x1800020b0  lea     rax, ?ServerSupportFunction@@YAHPEAXK0PEAK1@Z; ServerSupportFunction(void *,ulong,void *,ulong *,ulong *)
0x1800020b7  mov     [rsp+138h+var_30], rax
0x1800020bf  xor     r9d, r9d; lpName
0x1800020c2  xor     r8d, r8d; bInitialState
0x1800020c5  xor     edx, edx; bManualReset
0x1800020c7  xor     ecx, ecx; lpEventAttributes
0x1800020c9  call    cs:__imp_CreateEventW
0x1800020cf  mov     [rbx+0B0h], rax
0x1800020d6  lea     rax, [rsp+138h+var_E8]
0x1800020db  mov     [rbx+0C0h], rax
0x1800020e2  mov     r15, [rsp+138h+var_100]
0x1800020e7  mov     rax, [r15+18h]
0x1800020eb  test    rax, rax
0x1800020ee  jz      short loc_180002104
0x1800020f0  lea     rcx, [rsp+138h+var_E8]
0x1800020f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020fa  mov     r14d, eax
0x1800020fd  jmp     short loc_18000210A
0x1800020ff  jmp     loc_180002205
0x180002104  mov     r14d, 4
0x18000210a  mov     [rsp+138h+var_108], r14d
0x18000210f  jmp     short loc_180002156
0x180002111  lea     rdx, WPP_GLOBAL_Control
0x180002118  mov     rcx, cs:WPP_GLOBAL_Control
0x18000211f  cmp     rcx, rdx
0x180002122  jz      short loc_180002145
0x180002124  test    dword ptr [rcx+1Ch], 1000h
0x18000212b  jz      short loc_180002145
0x18000212d  mov     r9d, eax
0x180002130  mov     edx, 0Ah
0x180002135  lea     r8, WPP_a551daa9c3c83c532b1715f40d740de9_Traceguids
0x18000213c  mov     rcx, [rcx+10h]
0x180002140  call    WPP_SF_d
0x180002145  xor     esi, esi
0x180002147  mov     r14d, [rsp+138h+var_108]
0x18000214c  mov     r15, [rsp+138h+var_100]
0x180002151  mov     rbx, qword ptr [rsp+138h+SystemTime.wYear]
0x180002156  mov     eax, esi
0x180002158  cmp     r14d, 2
0x18000215c  setz    al
0x18000215f  mov     [rbx+6Ch], eax
0x180002162  lea     rdx, WPP_GLOBAL_Control
0x180002169  mov     rcx, cs:WPP_GLOBAL_Control
0x180002170  cmp     rcx, rdx
0x180002173  jz      short loc_180002182
0x180002175  test    dword ptr [rcx+1Ch], 1000h
0x18000217c  jnz     loc_18000222E
0x180002182  cmp     r14d, 3
0x180002186  jz      loc_18000224F
0x18000218c  mov     rcx, [rbx+0B0h]; hObject
0x180002193  test    rcx, rcx
0x180002196  jz      short loc_1800021A5
0x180002198  call    cs:__imp_CloseHandle
0x18000219e  mov     [rbx+0B0h], rsi
0x1800021a5  call    ?StartRemoveISAPICacheIfNeeded@CHttpRequest@@AEAAXXZ; CHttpRequest::StartRemoveISAPICacheIfNeeded(void)
0x1800021aa  xorps   xmm0, xmm0
0x1800021ad  movups  xmmword ptr [rsp+138h+SystemTime.wYear], xmm0
0x1800021b2  test    r15, r15
0x1800021b5  jz      short loc_1800021F4
0x1800021b7  mov     rax, cs:?g_pVars@@3PEAVCGlobalVariables@@EA; CGlobalVariables * g_pVars
0x1800021be  mov     rdi, [rax+40h]
0x1800021c2  lea     rcx, [rdi+8]; lpCriticalSection
0x1800021c6  call    cs:__imp_EnterCriticalSection
0x1800021cc  lea     rcx, [rsp+138h+SystemTime]; lpSystemTime
0x1800021d1  call    cs:__imp_GetSystemTime
0x1800021d7  lea     rdx, [r15+38h]; lpFileTime
0x1800021db  lea     rcx, [rsp+138h+SystemTime]; lpSystemTime
0x1800021e0  call    cs:__imp_SystemTimeToFileTime
0x1800021e6  dec     dword ptr [r15+30h]
0x1800021ea  lea     rcx, [rdi+8]; lpCriticalSection
0x1800021ee  call    cs:__imp_LeaveCriticalSection
0x1800021f4  mov     [rbx+0C0h], rsi
0x1800021fb  cmp     r14d, 4
0x1800021ff  setnz   sil
0x180002203  mov     eax, esi
0x180002205  mov     rcx, [rsp+138h+var_28]
0x18000220d  xor     rcx, rsp; StackCookie
0x180002210  call    __security_check_cookie
0x180002215  lea     r11, [rsp+138h+var_18]
0x18000221d  mov     rbx, [r11+28h]
0x180002221  mov     rsi, [r11+30h]
0x180002225  mov     rsp, r11
0x180002228  pop     r15
0x18000222a  pop     r14
0x18000222c  pop     rdi
0x18000222d  retn
0x18000222e  mov     edx, 0Bh
0x180002233  mov     [rsp+138h+var_118], eax
0x180002237  mov     r9d, r14d
0x18000223a  lea     r8, WPP_a551daa9c3c83c532b1715f40d740de9_Traceguids
0x180002241  mov     rcx, [rcx+10h]
0x180002245  call    WPP_SF_dd
0x18000224a  jmp     loc_180002182
0x18000224f  mov     eax, 80h
0x180002254  mov     rcx, [rbx+0B0h]; hHandle
0x18000225b  test    rcx, rcx
0x18000225e  jz      short loc_18000226B
0x180002260  mov     edx, 493E0h; dwMilliseconds
0x180002265  call    cs:__imp_WaitForSingleObject
0x18000226b  test    eax, eax
0x18000226d  jnz     short loc_18000227B
0x18000226f  mov     r14d, [rbx+0B8h]
0x180002276  jmp     loc_18000218C
0x18000227b  mov     r14d, 4
0x180002281  jmp     loc_18000218C
```
