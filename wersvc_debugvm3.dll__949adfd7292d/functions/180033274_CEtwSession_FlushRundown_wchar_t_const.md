# CEtwSession::FlushRundown(wchar_t const *)

- ea: `0x180033274`
- end: `0x1800335ea`
- name: `?FlushRundown@CEtwSession@@AEAAJPEB_W@Z`
- size: `886`
- prototype: `int(CEtwSession *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180031d14`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x1800035e8`
- `0x180004a44`
- `0x180006134`
- `0x1800101dc`
- `0x180033274`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033314`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033314`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800335a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800335a0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800333df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800333df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033591`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1800334de`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180033517`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18003354c`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1800334de`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180033517`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18003354c`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003357c`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18003357c`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180033427`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180033427`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTraceEx` at `0x18003349e`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTraceEx` at `0x18003349e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CEtwSession::FlushRundown(CEtwSession *this, wchar_t *a2)
{
  char v4; // r14
  int v5; // ebx
  HANDLE FileW; // rax
  signed int started; // eax
  bool v8; // cc
  ULONG64 TraceHandle; // [rsp+50h] [rbp-49h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-41h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-39h] BYREF
  _WORD v13[8]; // [rsp+70h] [rbp-29h] BYREF
  RTL_SRWLOCK *v14; // [rsp+80h] [rbp-19h]
  char v15; // [rsp+88h] [rbp-11h]
  struct _EVENT_FILTER_DESCRIPTOR EnableFilterDesc; // [rsp+90h] [rbp-9h] BYREF
  __int128 v17; // [rsp+A0h] [rbp+7h] BYREF
  __int128 v18; // [rsp+B0h] [rbp+17h]

  lpFileName[0] = v13;
  lpFileName[1] = v13;
  v13[0] = 0;
  TraceHandle = 0;
  v17 = 0;
  v18 = 0;
  EnableFilterDesc = 0;
  v14 = &stru_180048768;
  v4 = 0;
  v15 = 0;
  hObject = 0;
  v5 = UtilVerifyAndLockDirectory(a2, &hObject);
  if ( v5 >= 0 )
  {
    if ( !*((_DWORD *)this + 1) || *((_DWORD *)this + 1) == 3 )
    {
      v5 = -2147024809;
    }
    else
    {
      AcquireSRWLockExclusive(&stru_180048768);
      v4 = 1;
      memset_0((char *)this + 8, 0, 0x1080u);
      *((_DWORD *)this + 2) = 4224;
      *((_DWORD *)this + 31) = 120;
      *((_DWORD *)this + 30) = 2170;
      *((_DWORD *)this + 13) = 0x20000;
      *((_DWORD *)this + 14) = 64;
      *((_DWORD *)this + 18) = 33554433;
      if ( *((_DWORD *)this + 1) == 2 )
      {
        *((_DWORD *)this + 14) = 512;
        *((_DWORD *)this + 15) = 16;
        *((_DWORD *)this + 16) = 64;
      }
      if ( (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  lpFileName,
                  L"%s\\%s.etl",
                  a2,
                  *((_QWORD *)this + 529)) >= 0 )
      {
        StringCchPrintfW((wchar_t *)this + 1089, 0x401u, lpFileName[0]);
        FileW = CreateFileW(lpFileName[0], 0xC0000000, 0, 0, 1u, 0x80u, 0);
        if ( (unsigned __int64)FileW + 1 > 1 )
        {
          CloseHandle(FileW);
          started = StartTraceW(&TraceHandle, *((LPCWSTR *)this + 529), (PEVENT_TRACE_PROPERTIES)((char *)this + 8));
          v5 = started;
          v8 = started <= 0;
          if ( !started )
          {
            v17 = 0;
            v18 = 0;
            EnableFilterDesc.Type = -2147483647;
            EnableFilterDesc.Ptr = (ULONGLONG)&v17;
            EnableFilterDesc.Size = 32;
            if ( *((_DWORD *)this + 1) == 2 )
              *(_QWORD *)&v17 = 0x200080010000C004LL;
            else
              LODWORD(v17) = 33554951;
            started = EnableTraceEx(&ProviderId, 0, TraceHandle, 2u, 0, 2u, 0, 0, &EnableFilterDesc);
            v5 = started;
            v8 = started <= 0;
            if ( !started )
            {
              if ( *((_DWORD *)this + 1) != 2 )
                goto LABEL_25;
              started = EnableTraceEx2(TraceHandle, &ProviderId, 1u, 0, 0, 0, 0, 0);
              v5 = started;
              v8 = started <= 0;
              if ( !started )
              {
                started = EnableTraceEx2(TraceHandle, &DxgkControlGuid, 1u, 5u, 0x41u, 0, 0, 0);
                v5 = started;
                v8 = started <= 0;
                if ( !started )
                {
                  started = EnableTraceEx2(TraceHandle, &DxgkControlGuid, 2u, 5u, 0x41u, 0, 0, 0);
                  v5 = started;
                  v8 = started <= 0;
                  if ( !started )
                  {
LABEL_25:
                    v5 = 0;
                    goto LABEL_27;
                  }
                }
              }
            }
          }
        }
        else
        {
          started = GetLastError();
          v5 = started;
          v8 = started <= 0;
        }
        if ( !v8 )
          v5 = (unsigned __int16)started | 0x80070000;
        if ( v5 >= 0 )
          v5 = -2147467259;
      }
      else
      {
        v5 = -2147024690;
      }
    }
  }
LABEL_27:
  if ( TraceHandle )
    ControlTraceW(TraceHandle, 0, (PEVENT_TRACE_PROPERTIES)((char *)this + 8), 1u);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( v4 )
    ReleaseSRWLockExclusive(&stru_180048768);
  if ( lpFileName[0] != v13 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180033274  mov     [rsp-8+arg_10], rbx
0x180033279  mov     [rsp-8+arg_18], rsi
0x18003327e  push    rbp
0x18003327f  push    rdi
0x180033280  push    r12
0x180033282  push    r14
0x180033284  push    r15
0x180033286  lea     rbp, [rsp-37h]
0x18003328b  sub     rsp, 0D0h
0x180033292  mov     rax, cs:__security_cookie
0x180033299  xor     rax, rsp
0x18003329c  mov     [rbp+57h+var_30], rax
0x1800332a0  mov     rsi, rdx
0x1800332a3  mov     rdi, rcx
0x1800332a6  lea     rax, [rbp+57h+var_80]
0x1800332aa  mov     [rbp+57h+lpFileName], rax
0x1800332ae  lea     rax, [rbp+57h+var_80]
0x1800332b2  mov     [rbp+57h+var_88], rax
0x1800332b6  xor     r12d, r12d
0x1800332b9  mov     [rbp+57h+var_80], r12w
0x1800332be  mov     [rbp+57h+TraceHandle], r12
0x1800332c2  xorps   xmm0, xmm0
0x1800332c5  movups  [rbp+57h+var_50], xmm0
0x1800332c9  movups  [rbp+57h+var_40], xmm0
0x1800332cd  movups  xmmword ptr [rbp+57h+var_60.Ptr], xmm0
0x1800332d1  lea     r15, stru_180048768
0x1800332d8  mov     [rbp+57h+var_70], r15
0x1800332dc  mov     r14b, r12b
0x1800332df  mov     [rbp+57h+var_68], r12b
0x1800332e3  mov     [rbp+57h+hObject], r12
0x1800332e7  lea     rdx, [rbp+57h+hObject]
0x1800332eb  mov     rcx, rsi; wchar_t *
0x1800332ee  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x1800332f3  mov     ebx, eax
0x1800332f5  test    eax, eax
0x1800332f7  js      loc_180033569
0x1800332fd  cmp     [rdi+4], r12d
0x180033301  jz      loc_180033564
0x180033307  cmp     dword ptr [rdi+4], 3
0x18003330b  jz      loc_180033564
0x180033311  mov     rcx, r15; SRWLock
0x180033314  call    cs:__imp_AcquireSRWLockExclusive
0x18003331a  mov     r14b, 1
0x18003331d  lea     rbx, [rdi+8]
0x180033321  mov     r15d, 1080h
0x180033327  mov     r8d, r15d; Size
0x18003332a  xor     edx, edx; Val
0x18003332c  mov     rcx, rbx; void *
0x18003332f  call    memset_0
0x180033334  mov     [rbx], r15d
0x180033337  mov     dword ptr [rdi+7Ch], 78h ; 'x'
0x18003333e  mov     dword ptr [rdi+78h], 87Ah
0x180033345  mov     dword ptr [rdi+34h], 20000h
0x18003334c  lea     eax, [r12+40h]
0x180033351  mov     [rdi+38h], eax
0x180033354  mov     dword ptr [rdi+48h], 2000001h
0x18003335b  lea     r15d, [r12+2]
0x180033360  cmp     [rdi+4], r15d
0x180033364  jnz     short loc_180033377
0x180033366  mov     dword ptr [rdi+38h], 200h
0x18003336d  mov     dword ptr [rdi+3Ch], 10h
0x180033374  mov     [rdi+40h], eax
0x180033377  mov     r9, [rdi+1088h]
0x18003337e  mov     r8, rsi
0x180033381  lea     rdx, aSSEtl_0; "%s\\%s.etl"
0x180033388  lea     rcx, [rbp+57h+lpFileName]
0x18003338c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180033391  test    eax, eax
0x180033393  jns     short loc_1800333A6
0x180033395  mov     ebx, 800700CEh
0x18003339a  lea     r15, stru_180048768
0x1800333a1  jmp     loc_180033569
0x1800333a6  lea     rcx, [rdi+882h]; wchar_t *
0x1800333ad  mov     r8, [rbp+57h+lpFileName]; wchar_t *
0x1800333b1  mov     edx, 401h; unsigned __int64
0x1800333b6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800333bb  mov     [rsp+0F0h+hTemplateFile], r12; hTemplateFile
0x1800333c0  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800333c8  mov     [rsp+0F0h+dwCreationDisposition], 1; dwCreationDisposition
0x1800333d0  xor     r9d, r9d; lpSecurityAttributes
0x1800333d3  xor     r8d, r8d; dwShareMode
0x1800333d6  mov     edx, 0C0000000h; dwDesiredAccess
0x1800333db  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x1800333df  call    cs:__imp_CreateFileW
0x1800333e5  lea     rcx, [rax+1]
0x1800333e9  cmp     rcx, 1
0x1800333ed  ja      short loc_180033410
0x1800333ef  call    cs:__imp_GetLastError
0x1800333f5  mov     ebx, eax
0x1800333f7  test    eax, eax
0x1800333f9  jle     short loc_180033404
0x1800333fb  movzx   ebx, ax
0x1800333fe  or      ebx, 80070000h
0x180033404  mov     eax, 80004005h
0x180033409  test    ebx, ebx
0x18003340b  cmovns  ebx, eax
0x18003340e  jmp     short loc_18003339A
0x180033410  mov     rcx, rax; hObject
0x180033413  call    cs:__imp_CloseHandle
0x180033419  mov     r8, rbx; Properties
0x18003341c  mov     rdx, [rdi+1088h]; InstanceName
0x180033423  lea     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x180033427  call    cs:__imp_StartTraceW
0x18003342d  mov     ebx, eax
0x18003342f  test    eax, eax
0x180033431  jnz     short loc_1800333F9
0x180033433  xorps   xmm0, xmm0
0x180033436  movups  [rbp+57h+var_50], xmm0
0x18003343a  movups  [rbp+57h+var_40], xmm0
0x18003343e  mov     [rbp+57h+var_60.Type], 80000001h
0x180033445  lea     rax, [rbp+57h+var_50]
0x180033449  mov     [rbp+57h+var_60.Ptr], rax
0x18003344d  mov     [rbp+57h+var_60.Size], 20h ; ' '
0x180033454  cmp     [rdi+4], r15d
0x180033458  jnz     short loc_18003346A
0x18003345a  mov     dword ptr [rbp+57h+var_50], 0C004h
0x180033461  mov     dword ptr [rbp+57h+var_50+4], 20008001h
0x180033468  jmp     short loc_180033471
0x18003346a  mov     dword ptr [rbp+57h+var_50], 2000207h
0x180033471  lea     rax, [rbp+57h+var_60]
0x180033475  mov     [rsp+0F0h+EnableFilterDesc], rax; EnableFilterDesc
0x18003347a  mov     [rsp+0F0h+EnableProperty], r12d; EnableProperty
0x18003347f  mov     [rsp+0F0h+hTemplateFile], r12; MatchAllKeyword
0x180033484  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], r15; MatchAnyKeyword
0x180033489  mov     byte ptr [rsp+0F0h+dwCreationDisposition], r12b; Level
0x18003348e  mov     r9d, r15d; IsEnabled
0x180033491  mov     r8, [rbp+57h+TraceHandle]; TraceHandle
0x180033495  xor     edx, edx; SourceId
0x180033497  lea     rcx, ProviderId; ProviderId
0x18003349e  call    cs:__imp_EnableTraceEx
0x1800334a4  mov     ebx, eax
0x1800334a6  test    eax, eax
0x1800334a8  jnz     loc_1800333F9
0x1800334ae  cmp     [rdi+4], r15d
0x1800334b2  jnz     loc_18003355C
0x1800334b8  mov     qword ptr [rsp+0F0h+EnableProperty], r12; EnableParameters
0x1800334bd  mov     dword ptr [rsp+0F0h+hTemplateFile], r12d; Timeout
0x1800334c2  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], r12; MatchAllKeyword
0x1800334c7  mov     qword ptr [rsp+0F0h+dwCreationDisposition], r12; MatchAnyKeyword
0x1800334cc  xor     r9d, r9d; Level
0x1800334cf  lea     r8d, [rax+1]; ControlCode
0x1800334d3  lea     rdx, ProviderId; ProviderId
0x1800334da  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x1800334de  call    cs:__imp_EnableTraceEx2
0x1800334e4  mov     ebx, eax
0x1800334e6  test    eax, eax
0x1800334e8  jnz     loc_1800333F9
0x1800334ee  mov     qword ptr [rsp+0F0h+EnableProperty], r12; EnableParameters
0x1800334f3  mov     dword ptr [rsp+0F0h+hTemplateFile], r12d; Timeout
0x1800334f8  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], r12; MatchAllKeyword
0x1800334fd  lea     esi, [rax+41h]
0x180033500  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; MatchAnyKeyword
0x180033505  mov     r9b, 5; Level
0x180033508  lea     r8d, [rax+1]; ControlCode
0x18003350c  lea     rdx, DxgkControlGuid; ProviderId
0x180033513  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x180033517  call    cs:__imp_EnableTraceEx2
0x18003351d  mov     ebx, eax
0x18003351f  test    eax, eax
0x180033521  jnz     loc_1800333F9
0x180033527  mov     qword ptr [rsp+0F0h+EnableProperty], r12; EnableParameters
0x18003352c  mov     dword ptr [rsp+0F0h+hTemplateFile], r12d; Timeout
0x180033531  mov     qword ptr [rsp+0F0h+dwFlagsAndAttributes], r12; MatchAllKeyword
0x180033536  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rsi; MatchAnyKeyword
0x18003353b  mov     r9b, 5; Level
0x18003353e  mov     r8d, r15d; ControlCode
0x180033541  lea     rdx, DxgkControlGuid; ProviderId
0x180033548  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x18003354c  call    cs:__imp_EnableTraceEx2
0x180033552  mov     ebx, eax
0x180033554  test    eax, eax
0x180033556  jnz     loc_1800333F9
0x18003355c  mov     ebx, r12d
0x18003355f  jmp     loc_18003339A
0x180033564  mov     ebx, 80070057h
0x180033569  mov     rcx, [rbp+57h+TraceHandle]; TraceHandle
0x18003356d  test    rcx, rcx
0x180033570  jz      short loc_180033583
0x180033572  lea     r8, [rdi+8]; Properties
0x180033576  xor     edx, edx; InstanceName
0x180033578  lea     r9d, [rdx+1]; ControlCode
0x18003357c  call    cs:__imp_ControlTraceW
0x180033582  nop
0x180033583  mov     rcx, [rbp+57h+hObject]; hObject
0x180033587  lea     rax, [rcx+1]
0x18003358b  cmp     rax, 1
0x18003358f  jbe     short loc_180033598
0x180033591  call    cs:__imp_CloseHandle
0x180033597  nop
0x180033598  test    r14b, r14b
0x18003359b  jz      short loc_1800335A7
0x18003359d  mov     rcx, r15; SRWLock
0x1800335a0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800335a6  nop
0x1800335a7  lea     rax, [rbp+57h+var_80]
0x1800335ab  mov     rcx, [rbp+57h+lpFileName]; void *
0x1800335af  cmp     rcx, rax
0x1800335b2  jz      short loc_1800335C0
0x1800335b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800335bb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800335c0  mov     eax, ebx
0x1800335c2  mov     rcx, [rbp+57h+var_30]
0x1800335c6  xor     rcx, rsp; StackCookie
0x1800335c9  call    __security_check_cookie
0x1800335ce  lea     r11, [rsp+0F0h+var_20]
0x1800335d6  mov     rbx, [r11+40h]
0x1800335da  mov     rsi, [r11+48h]
0x1800335de  mov     rsp, r11
0x1800335e1  pop     r15
0x1800335e3  pop     r14
0x1800335e5  pop     r12
0x1800335e7  pop     rdi
0x1800335e8  pop     rbp
0x1800335e9  retn
```
