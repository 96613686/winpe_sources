# WpnQoSLoggerImpl::LogConnectResult(_WPN_QOS_ERROR_SOURCE,_WPN_QOS_ATTEMPT_TYPE,_WPN_QOS_INTERFACE_TYPE,_WPN_QOS_PROTOCOL_TYPE,_WPN_QOS_PROXY_TYPE,ushort const *,long,ulong,int)

- ea: `0x18001de60`
- end: `0x18001e10f`
- name: `?LogConnectResult@WpnQoSLoggerImpl@@UEAAJW4_WPN_QOS_ERROR_SOURCE@@W4_WPN_QOS_ATTEMPT_TYPE@@W4_WPN_QOS_INTERFACE_TYPE@@W4_WPN_QOS_PROTOCOL_TYPE@@W4_WPN_QOS_PROXY_TYPE@@PEBGJKH@Z`
- size: `687`
- prototype: `__int64 __fastcall(__int64, int, int, int, int, int, unsigned __int16 *, int, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x18001c8e0`
- `0x18001de60`
- `0x18001e2f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001deec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001deec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e0de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e0fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e0de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e0fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001deda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e0d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e0ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001deda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e0d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e0ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e015`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e007`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e007`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e06a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e06a`

## pseudocode

```c
__int64 __fastcall WpnQoSLoggerImpl::LogConnectResult(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        unsigned __int16 *a7,
        int a8,
        int a9,
        int a10)
{
  unsigned int v14; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  HANDLE ProcessHeap; // rax
  unsigned __int16 **v19; // rax
  unsigned __int16 **v20; // rdi
  int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  struct _TP_WORK *ThreadpoolWork; // rsi
  signed int LastError; // eax
  unsigned __int16 *v27; // rsi
  HANDLE v28; // rax
  HANDLE v29; // rax
  int v31; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a2 == 1 )
  {
    v14 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
      (const char *)0x80070057LL,
      v31);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v16 = 14;
      v17 = 2147942487LL;
LABEL_5:
      WPP_SF_d(v15[2], v16, WPP_b4f52972f4d4384da41e73b76c391f2b_Traceguids, v17);
      return v14;
    }
    return v14;
  }
  ProcessHeap = GetProcessHeap();
  v19 = (unsigned __int16 **)HeapAlloc(ProcessHeap, 8u, 0x30u);
  v20 = v19;
  if ( v19 )
  {
    v21 = WpnStrCpy(a7, v19 + 3);
    v14 = v21;
    if ( v21 >= 0 )
    {
      *(_DWORD *)v20 = *(_DWORD *)(a1 + 8);
      *((_DWORD *)v20 + 4) = a5;
      *((_DWORD *)v20 + 5) = a6;
      *((_DWORD *)v20 + 8) = a8;
      *((_DWORD *)v20 + 1) = a2;
      *((_DWORD *)v20 + 2) = a3;
      *((_DWORD *)v20 + 3) = a4;
      *((_DWORD *)v20 + 10) = *(_DWORD *)(a1 + 12);
      *((_DWORD *)v20 + 9) = a9;
      *((_DWORD *)v20 + 11) = a10;
      v24 = WpnQoSLoggerImpl::ScheduleQoSLoggingTimer((struct WpnQoSLoggerImpl::_QOS_DATA *)v20);
      v14 = v24;
      if ( v24 == 1 )
      {
        ThreadpoolWork = CreateThreadpoolWork(
                           (PTP_WORK_CALLBACK)WpnQoSLoggerImpl::BackgroundResultLogging,
                           v20,
                           &WpnQoSLoggerImpl::s_Environment);
        if ( ThreadpoolWork )
          goto LABEL_22;
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        if ( (v14 & 0x80000000) == 0 )
        {
LABEL_22:
          SubmitThreadpoolWork(ThreadpoolWork);
          return v14;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x131,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
          (const char *)v14,
          v31);
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_28;
        v23 = 17;
      }
      else
      {
        if ( v24 >= 0 )
          return v14;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x13B,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
          (const char *)(unsigned int)v24,
          v31);
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_28;
        v23 = 18;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
        (const char *)(unsigned int)v21,
        v31);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_28;
      v23 = 16;
    }
    WPP_SF_d(v22[2], v23, WPP_b4f52972f4d4384da41e73b76c391f2b_Traceguids, v14);
LABEL_28:
    v27 = v20[3];
    if ( v27 )
    {
      v28 = GetProcessHeap();
      HeapFree(v28, 0, v27);
      v20[3] = 0;
    }
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v20);
    return v14;
  }
  v14 = -2147024882;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x11A,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
    (const char *)0x8007000ELL,
    v31);
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v16 = 15;
    v17 = 2147942414LL;
    goto LABEL_5;
  }
  return v14;
}

```

## disassembly

```asm
0x18001de60  push    rbx
0x18001de62  push    rbp
0x18001de63  push    rsi
0x18001de64  push    rdi
0x18001de65  push    r14
0x18001de67  push    r15
0x18001de69  sub     rsp, 28h
0x18001de6d  mov     r14d, r9d
0x18001de70  mov     r15d, r8d
0x18001de73  mov     esi, edx
0x18001de75  mov     rbp, rcx
0x18001de78  cmp     edx, 1
0x18001de7b  jnz     short loc_18001DEDA
0x18001de7d  mov     rcx, [rsp+58h]; this
0x18001de82  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001de89  mov     ebx, 80070057h
0x18001de8e  mov     edx, 115h; void *
0x18001de93  mov     r9d, ebx; char *
0x18001de96  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001de9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dea2  lea     rax, WPP_GLOBAL_Control
0x18001dea9  cmp     rcx, rax
0x18001deac  jz      loc_18001E100
0x18001deb2  test    byte ptr [rcx+1Ch], 80h
0x18001deb6  jz      loc_18001E100
0x18001debc  lea     edx, [rsi+0Dh]
0x18001debf  mov     r9d, 80070057h
0x18001dec5  mov     rcx, [rcx+10h]
0x18001dec9  lea     r8, WPP_b4f52972f4d4384da41e73b76c391f2b_Traceguids
0x18001ded0  call    WPP_SF_d
0x18001ded5  jmp     loc_18001E100
0x18001deda  call    cs:__imp_GetProcessHeap
0x18001dee0  mov     edx, 8; dwFlags
0x18001dee5  mov     rcx, rax; hHeap
0x18001dee8  lea     r8d, [rdx+28h]; dwBytes
0x18001deec  call    cs:__imp_HeapAlloc
0x18001def2  mov     rdi, rax
0x18001def5  test    rax, rax
0x18001def8  jnz     short loc_18001DF44
0x18001defa  mov     rcx, [rsp+58h]; this
0x18001deff  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001df06  mov     ebx, 8007000Eh
0x18001df0b  mov     edx, 11Ah; void *
0x18001df10  mov     r9d, ebx; char *
0x18001df13  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001df18  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df1f  lea     rax, WPP_GLOBAL_Control
0x18001df26  cmp     rcx, rax
0x18001df29  jz      loc_18001E100
0x18001df2f  test    byte ptr [rcx+1Ch], 80h
0x18001df33  jz      loc_18001E100
0x18001df39  lea     edx, [rdi+0Fh]
0x18001df3c  mov     r9d, 8007000Eh
0x18001df42  jmp     short loc_18001DEC5
0x18001df44  mov     rcx, [rsp+58h+arg_30]; unsigned __int16 *
0x18001df4c  lea     rdx, [rax+18h]; unsigned __int16 **
0x18001df50  call    ?WpnStrCpy@@YAJPEBGPEAPEAG@Z; WpnStrCpy(ushort const *,ushort * *)
0x18001df55  mov     ebx, eax
0x18001df57  test    eax, eax
0x18001df59  jns     short loc_18001DF9F
0x18001df5b  mov     rcx, [rsp+58h]; this
0x18001df60  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001df67  mov     r9d, eax; char *
0x18001df6a  mov     edx, 11Dh; void *
0x18001df6f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001df74  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df7b  lea     rax, WPP_GLOBAL_Control
0x18001df82  cmp     rcx, rax
0x18001df85  jz      loc_18001E0C7
0x18001df8b  test    byte ptr [rcx+1Ch], 80h
0x18001df8f  jz      loc_18001E0C7
0x18001df95  mov     edx, 10h
0x18001df9a  jmp     loc_18001E0B4
0x18001df9f  mov     eax, [rbp+8]
0x18001dfa2  mov     rcx, rdi; struct WpnQoSLoggerImpl::_QOS_DATA *
0x18001dfa5  mov     [rdi], eax
0x18001dfa7  mov     eax, [rsp+58h+arg_20]
0x18001dfae  mov     [rdi+10h], eax
0x18001dfb1  mov     eax, [rsp+58h+arg_28]
0x18001dfb8  mov     [rdi+14h], eax
0x18001dfbb  mov     eax, [rsp+58h+arg_38]
0x18001dfc2  mov     [rdi+20h], eax
0x18001dfc5  mov     [rdi+4], esi
0x18001dfc8  mov     [rdi+8], r15d
0x18001dfcc  mov     [rdi+0Ch], r14d
0x18001dfd0  mov     eax, [rbp+0Ch]
0x18001dfd3  mov     [rdi+28h], eax
0x18001dfd6  mov     eax, [rsp+58h+arg_40]
0x18001dfdd  mov     [rdi+24h], eax
0x18001dfe0  mov     eax, [rsp+58h+arg_48]
0x18001dfe7  mov     [rdi+2Ch], eax
0x18001dfea  call    ?ScheduleQoSLoggingTimer@WpnQoSLoggerImpl@@CAJPEAU_QOS_DATA@1@@Z; WpnQoSLoggerImpl::ScheduleQoSLoggingTimer(WpnQoSLoggerImpl::_QOS_DATA *)
0x18001dfef  mov     ebx, eax
0x18001dff1  cmp     eax, 1
0x18001dff4  jnz     short loc_18001E075
0x18001dff6  lea     r8, ?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18001dffd  mov     rdx, rdi; pv
0x18001e000  lea     rcx, ?BackgroundResultLogging@WpnQoSLoggerImpl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001e007  call    cs:__imp_CreateThreadpoolWork
0x18001e00d  mov     rsi, rax
0x18001e010  test    rax, rax
0x18001e013  jnz     short loc_18001E067
0x18001e015  call    cs:__imp_GetLastError
0x18001e01b  mov     ebx, eax
0x18001e01d  test    eax, eax
0x18001e01f  jle     short loc_18001E02A
0x18001e021  movzx   ebx, ax
0x18001e024  or      ebx, 80070000h
0x18001e02a  test    ebx, ebx
0x18001e02c  jns     short loc_18001E067
0x18001e02e  mov     rcx, [rsp+58h]; this
0x18001e033  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e03a  mov     r9d, ebx; char *
0x18001e03d  mov     edx, 131h; void *
0x18001e042  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e047  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e04e  lea     rax, WPP_GLOBAL_Control
0x18001e055  cmp     rcx, rax
0x18001e058  jz      short loc_18001E0C7
0x18001e05a  test    byte ptr [rcx+1Ch], 80h
0x18001e05e  jz      short loc_18001E0C7
0x18001e060  mov     edx, 11h
0x18001e065  jmp     short loc_18001E0B4
0x18001e067  mov     rcx, rsi; pwk
0x18001e06a  call    cs:__imp_SubmitThreadpoolWork
0x18001e070  jmp     loc_18001E100
0x18001e075  test    ebx, ebx
0x18001e077  jns     loc_18001E100
0x18001e07d  mov     rcx, [rsp+58h]; this
0x18001e082  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001e089  mov     r9d, ebx; char *
0x18001e08c  mov     edx, 13Bh; void *
0x18001e091  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e096  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e09d  lea     rax, WPP_GLOBAL_Control
0x18001e0a4  cmp     rcx, rax
0x18001e0a7  jz      short loc_18001E0C7
0x18001e0a9  test    byte ptr [rcx+1Ch], 80h
0x18001e0ad  jz      short loc_18001E0C7
0x18001e0af  mov     edx, 12h
0x18001e0b4  mov     rcx, [rcx+10h]
0x18001e0b8  lea     r8, WPP_b4f52972f4d4384da41e73b76c391f2b_Traceguids
0x18001e0bf  mov     r9d, ebx
0x18001e0c2  call    WPP_SF_d
0x18001e0c7  mov     rsi, [rdi+18h]
0x18001e0cb  test    rsi, rsi
0x18001e0ce  jz      short loc_18001E0EC
0x18001e0d0  call    cs:__imp_GetProcessHeap
0x18001e0d6  mov     r8, rsi; lpMem
0x18001e0d9  xor     edx, edx; dwFlags
0x18001e0db  mov     rcx, rax; hHeap
0x18001e0de  call    cs:__imp_HeapFree
0x18001e0e4  mov     qword ptr [rdi+18h], 0
0x18001e0ec  call    cs:__imp_GetProcessHeap
0x18001e0f2  mov     r8, rdi; lpMem
0x18001e0f5  xor     edx, edx; dwFlags
0x18001e0f7  mov     rcx, rax; hHeap
0x18001e0fa  call    cs:__imp_HeapFree
0x18001e100  mov     eax, ebx
0x18001e102  add     rsp, 28h
0x18001e106  pop     r15
0x18001e108  pop     r14
0x18001e10a  pop     rdi
0x18001e10b  pop     rsi
0x18001e10c  pop     rbp
0x18001e10d  pop     rbx
0x18001e10e  retn
```
