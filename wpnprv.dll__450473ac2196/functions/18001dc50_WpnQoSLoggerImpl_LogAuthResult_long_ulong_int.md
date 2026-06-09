# WpnQoSLoggerImpl::LogAuthResult(long,ulong,int)

- ea: `0x18001dc50`
- end: `0x18001de50`
- name: `?LogAuthResult@WpnQoSLoggerImpl@@UEAAJJKH@Z`
- size: `512`
- prototype: `__int64 __fastcall(WpnQoSLoggerImpl *this, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x18001dc50`
- `0x18001e2f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dc81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dc81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001de1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001de39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001de1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001de39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dc6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001de0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001de2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dc6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001de0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001de2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd54`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001dd46`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001dd46`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001dda9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001dda9`

## pseudocode

```c
__int64 __fastcall WpnQoSLoggerImpl::LogAuthResult(WpnQoSLoggerImpl *this, int a2, int a3, int a4)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v8; // rdi
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // eax
  struct _TP_WORK *ThreadpoolWork; // rsi
  signed int LastError; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  void *v16; // rsi
  HANDLE v17; // rax
  HANDLE v18; // rax
  int v20; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *((_DWORD *)this + 3) = a3;
  if ( a2 >= 0 )
    return 0;
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 8u, 0x30u);
  if ( !v8 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
      (const char *)0x8007000ELL,
      v20);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b4f52972f4d4384da41e73b76c391f2b_Traceguids, 2147942414LL);
    return v9;
  }
  v10 = *((_DWORD *)this + 2);
  v8[1] = 1;
  v8[2] = 1;
  v8[3] = 1;
  v8[4] = 1;
  v8[5] = 1;
  *v8 = v10;
  *((_QWORD *)v8 + 3) = 0;
  v8[8] = a2;
  v8[10] = *((_DWORD *)this + 3);
  v8[9] = 0;
  v8[11] = a4;
  v11 = WpnQoSLoggerImpl::ScheduleQoSLoggingTimer((struct WpnQoSLoggerImpl::_QOS_DATA *)v8);
  v9 = v11;
  if ( v11 == 1 )
  {
    ThreadpoolWork = CreateThreadpoolWork(
                       WpnQoSLoggerImpl::BackgroundResultLogging,
                       v8,
                       &WpnQoSLoggerImpl::s_Environment);
    if ( ThreadpoolWork )
      goto LABEL_14;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( (v9 & 0x80000000) == 0 )
    {
LABEL_14:
      SubmitThreadpoolWork(ThreadpoolWork);
      return v9;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
      (const char *)v9,
      v20);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_20;
    v15 = 12;
  }
  else
  {
    if ( v11 >= 0 )
      return v9;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
      (const char *)(unsigned int)v11,
      v20);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_20;
    v15 = 13;
  }
  WPP_SF_d(v14[2], v15, WPP_b4f52972f4d4384da41e73b76c391f2b_Traceguids, v9);
LABEL_20:
  v16 = (void *)*((_QWORD *)v8 + 3);
  if ( v16 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v16);
    *((_QWORD *)v8 + 3) = 0;
  }
  v18 = GetProcessHeap();
  HeapFree(v18, 0, v8);
  return v9;
}

```

## disassembly

```asm
0x18001dc50  push    rbx
0x18001dc52  push    rbp
0x18001dc53  push    rsi
0x18001dc54  push    rdi
0x18001dc55  push    r14; int
0x18001dc57  sub     rsp, 20h
0x18001dc5b  mov     [rcx+0Ch], r8d
0x18001dc5f  mov     ebp, r9d
0x18001dc62  mov     esi, edx
0x18001dc64  mov     rbx, rcx
0x18001dc67  test    edx, edx
0x18001dc69  jns     loc_18001DE41
0x18001dc6f  call    cs:__imp_GetProcessHeap
0x18001dc75  mov     edx, 8; dwFlags
0x18001dc7a  mov     rcx, rax; hHeap
0x18001dc7d  lea     r8d, [rdx+28h]; dwBytes
0x18001dc81  call    cs:__imp_HeapAlloc
0x18001dc87  mov     rdi, rax
0x18001dc8a  test    rax, rax
0x18001dc8d  jnz     short loc_18001DCEC
0x18001dc8f  mov     rcx, [rsp+48h]; this
0x18001dc94  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001dc9b  mov     ebx, 8007000Eh
0x18001dca0  mov     edx, 0BDh; void *
0x18001dca5  mov     r9d, ebx; char *
0x18001dca8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001dcad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dcb4  lea     rax, WPP_GLOBAL_Control
0x18001dcbb  cmp     rcx, rax
0x18001dcbe  jz      loc_18001DE43
0x18001dcc4  test    byte ptr [rcx+1Ch], 80h
0x18001dcc8  jz      loc_18001DE43
0x18001dcce  mov     rcx, [rcx+10h]
0x18001dcd2  lea     edx, [rdi+0Bh]
0x18001dcd5  mov     r9d, 8007000Eh
0x18001dcdb  lea     r8, WPP_b4f52972f4d4384da41e73b76c391f2b_Traceguids
0x18001dce2  call    WPP_SF_d
0x18001dce7  jmp     loc_18001DE43
0x18001dcec  mov     eax, [rbx+8]
0x18001dcef  mov     r14d, 1
0x18001dcf5  mov     [rdi+4], r14d
0x18001dcf9  mov     rcx, rdi; struct WpnQoSLoggerImpl::_QOS_DATA *
0x18001dcfc  mov     [rdi+8], r14d
0x18001dd00  mov     [rdi+0Ch], r14d
0x18001dd04  mov     [rdi+10h], r14d
0x18001dd08  mov     [rdi+14h], r14d
0x18001dd0c  mov     [rdi], eax
0x18001dd0e  mov     qword ptr [rdi+18h], 0
0x18001dd16  mov     [rdi+20h], esi
0x18001dd19  mov     eax, [rbx+0Ch]
0x18001dd1c  mov     [rdi+28h], eax
0x18001dd1f  mov     dword ptr [rdi+24h], 0
0x18001dd26  mov     [rdi+2Ch], ebp
0x18001dd29  call    ?ScheduleQoSLoggingTimer@WpnQoSLoggerImpl@@CAJPEAU_QOS_DATA@1@@Z; WpnQoSLoggerImpl::ScheduleQoSLoggingTimer(WpnQoSLoggerImpl::_QOS_DATA *)
0x18001dd2e  mov     ebx, eax
0x18001dd30  cmp     eax, r14d
0x18001dd33  jnz     short loc_18001DDB4
0x18001dd35  lea     r8, ?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18001dd3c  mov     rdx, rdi; pv
0x18001dd3f  lea     rcx, ?BackgroundResultLogging@WpnQoSLoggerImpl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001dd46  call    cs:__imp_CreateThreadpoolWork
0x18001dd4c  mov     rsi, rax
0x18001dd4f  test    rax, rax
0x18001dd52  jnz     short loc_18001DDA6
0x18001dd54  call    cs:__imp_GetLastError
0x18001dd5a  mov     ebx, eax
0x18001dd5c  test    eax, eax
0x18001dd5e  jle     short loc_18001DD69
0x18001dd60  movzx   ebx, ax
0x18001dd63  or      ebx, 80070000h
0x18001dd69  test    ebx, ebx
0x18001dd6b  jns     short loc_18001DDA6
0x18001dd6d  mov     rcx, [rsp+48h]; this
0x18001dd72  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001dd79  mov     r9d, ebx; char *
0x18001dd7c  mov     edx, 0D2h; void *
0x18001dd81  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001dd86  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd8d  lea     rax, WPP_GLOBAL_Control
0x18001dd94  cmp     rcx, rax
0x18001dd97  jz      short loc_18001DE06
0x18001dd99  test    byte ptr [rcx+1Ch], 80h
0x18001dd9d  jz      short loc_18001DE06
0x18001dd9f  mov     edx, 0Ch
0x18001dda4  jmp     short loc_18001DDF3
0x18001dda6  mov     rcx, rsi; pwk
0x18001dda9  call    cs:__imp_SubmitThreadpoolWork
0x18001ddaf  jmp     loc_18001DE43
0x18001ddb4  test    ebx, ebx
0x18001ddb6  jns     loc_18001DE43
0x18001ddbc  mov     rcx, [rsp+48h]; this
0x18001ddc1  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ddc8  mov     r9d, ebx; char *
0x18001ddcb  mov     edx, 0DCh; void *
0x18001ddd0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ddd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dddc  lea     rax, WPP_GLOBAL_Control
0x18001dde3  cmp     rcx, rax
0x18001dde6  jz      short loc_18001DE06
0x18001dde8  test    byte ptr [rcx+1Ch], 80h
0x18001ddec  jz      short loc_18001DE06
0x18001ddee  mov     edx, 0Dh
0x18001ddf3  mov     rcx, [rcx+10h]
0x18001ddf7  lea     r8, WPP_b4f52972f4d4384da41e73b76c391f2b_Traceguids
0x18001ddfe  mov     r9d, ebx
0x18001de01  call    WPP_SF_d
0x18001de06  mov     rsi, [rdi+18h]
0x18001de0a  test    rsi, rsi
0x18001de0d  jz      short loc_18001DE2B
0x18001de0f  call    cs:__imp_GetProcessHeap
0x18001de15  mov     r8, rsi; lpMem
0x18001de18  xor     edx, edx; dwFlags
0x18001de1a  mov     rcx, rax; hHeap
0x18001de1d  call    cs:__imp_HeapFree
0x18001de23  mov     qword ptr [rdi+18h], 0
0x18001de2b  call    cs:__imp_GetProcessHeap
0x18001de31  mov     r8, rdi; lpMem
0x18001de34  xor     edx, edx; dwFlags
0x18001de36  mov     rcx, rax; hHeap
0x18001de39  call    cs:__imp_HeapFree
0x18001de3f  jmp     short loc_18001DE43
0x18001de41  xor     ebx, ebx
0x18001de43  mov     eax, ebx
0x18001de45  add     rsp, 20h
0x18001de49  pop     r14
0x18001de4b  pop     rdi
0x18001de4c  pop     rsi
0x18001de4d  pop     rbp
0x18001de4e  pop     rbx
0x18001de4f  retn
```
