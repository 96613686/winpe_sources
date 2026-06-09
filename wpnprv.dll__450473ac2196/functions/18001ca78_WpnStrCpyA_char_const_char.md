# WpnStrCpyA(char const *,char * *)

- ea: `0x18001ca78`
- end: `0x18001cc07`
- name: `?WpnStrCpyA@@YAJPEBDPEAPEAD@Z`
- size: `399`
- prototype: `__int64 __fastcall(const char *, char **)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180040ab8`
- `0x180051e60`
- `0x180063cb0`

## callees

- `0x18000c97c`
- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x18001c680`
- `0x18001ca78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cb28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cb28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cbf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001cbf0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cb14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cbe2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cb14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cbe2`

## string_xrefs

- `0x18001cac2`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x18001cb3b`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x18001cb9d`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`

## pseudocode

```c
__int64 __fastcall WpnStrCpyA(const char *a1, char **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  HANDLE ProcessHeap; // rax
  unsigned __int64 v10; // rbx
  char *v11; // rax
  char *v12; // rdi
  int v13; // eax
  HANDLE v14; // rax
  int v16; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int64 v18; // [rsp+50h] [rbp+8h] BYREF

  v18 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  v4 = StringCchLengthA(a1, 0x7FFFFFFFu, &v18);
  v5 = v4;
  if ( v4 >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v10 = v18;
    v11 = (char *)HeapAlloc(ProcessHeap, 0, v18 + 1);
    v12 = v11;
    if ( v11 )
    {
      v13 = StringCchCopyA(v11, v10 + 1, a1);
      v5 = v13;
      if ( v13 >= 0 )
      {
        *a2 = v12;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x280,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
          (const char *)(unsigned int)v13,
          v16);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids, v5);
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v12);
      }
    }
    else
    {
      v5 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x27D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
        (const char *)0x8007000ELL,
        v16);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v7 = 40;
        v8 = 2147942414LL;
        goto LABEL_9;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x27A,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
      (const char *)(unsigned int)v4,
      v16);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v7 = 39;
      v8 = v5;
LABEL_9:
      WPP_SF_d(v6[2], v7, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids, v8);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001ca78  push    rbx
0x18001ca7a  push    rsi
0x18001ca7b  push    rdi
0x18001ca7c  push    r14
0x18001ca7e  sub     rsp, 28h
0x18001ca82  mov     [rsp+48h+arg_0], 0
0x18001ca8b  mov     r14, rdx
0x18001ca8e  mov     rsi, rcx
0x18001ca91  test    rcx, rcx
0x18001ca94  jnz     short loc_18001CA9B
0x18001ca96  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ca9b  test    r14, r14
0x18001ca9e  jnz     short loc_18001CAA5
0x18001caa0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001caa5  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x18001caaa  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001caaf  mov     rcx, rsi; char *
0x18001cab2  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x18001cab7  mov     ebx, eax
0x18001cab9  test    eax, eax
0x18001cabb  jns     short loc_18001CB14
0x18001cabd  mov     rcx, [rsp+48h]; this
0x18001cac2  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001cac9  mov     r9d, eax; char *
0x18001cacc  mov     edx, 27Ah; void *
0x18001cad1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cad6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cadd  lea     rax, WPP_GLOBAL_Control
0x18001cae4  cmp     rcx, rax
0x18001cae7  jz      loc_18001CBFB
0x18001caed  test    byte ptr [rcx+1Ch], 80h
0x18001caf1  jz      loc_18001CBFB
0x18001caf7  mov     edx, 27h ; '''
0x18001cafc  mov     r9d, ebx
0x18001caff  mov     rcx, [rcx+10h]
0x18001cb03  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x18001cb0a  call    WPP_SF_d
0x18001cb0f  jmp     loc_18001CBFB
0x18001cb14  call    cs:__imp_GetProcessHeap
0x18001cb1a  mov     rbx, [rsp+48h+arg_0]
0x18001cb1f  xor     edx, edx; dwFlags
0x18001cb21  mov     rcx, rax; hHeap
0x18001cb24  lea     r8, [rbx+1]; dwBytes
0x18001cb28  call    cs:__imp_HeapAlloc
0x18001cb2e  mov     rdi, rax
0x18001cb31  test    rax, rax
0x18001cb34  jnz     short loc_18001CB83
0x18001cb36  mov     rcx, [rsp+48h]; this
0x18001cb3b  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001cb42  mov     ebx, 8007000Eh
0x18001cb47  mov     edx, 27Dh; void *
0x18001cb4c  mov     r9d, ebx; char *
0x18001cb4f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cb54  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb5b  lea     rax, WPP_GLOBAL_Control
0x18001cb62  cmp     rcx, rax
0x18001cb65  jz      loc_18001CBFB
0x18001cb6b  test    byte ptr [rcx+1Ch], 80h
0x18001cb6f  jz      loc_18001CBFB
0x18001cb75  lea     edx, [rdi+28h]
0x18001cb78  mov     r9d, 8007000Eh
0x18001cb7e  jmp     loc_18001CAFF
0x18001cb83  mov     r8, rsi; char *
0x18001cb86  lea     rdx, [rbx+1]; unsigned __int64
0x18001cb8a  mov     rcx, rdi; char *
0x18001cb8d  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001cb92  mov     ebx, eax
0x18001cb94  test    eax, eax
0x18001cb96  jns     short loc_18001CBF8
0x18001cb98  mov     rcx, [rsp+48h]; this
0x18001cb9d  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001cba4  mov     r9d, eax; char *
0x18001cba7  mov     edx, 280h; void *
0x18001cbac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cbb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbb8  lea     rax, WPP_GLOBAL_Control
0x18001cbbf  cmp     rcx, rax
0x18001cbc2  jz      short loc_18001CBE2
0x18001cbc4  test    byte ptr [rcx+1Ch], 80h
0x18001cbc8  jz      short loc_18001CBE2
0x18001cbca  mov     rcx, [rcx+10h]
0x18001cbce  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x18001cbd5  mov     edx, 29h ; ')'
0x18001cbda  mov     r9d, ebx
0x18001cbdd  call    WPP_SF_d
0x18001cbe2  call    cs:__imp_GetProcessHeap
0x18001cbe8  mov     r8, rdi; lpMem
0x18001cbeb  xor     edx, edx; dwFlags
0x18001cbed  mov     rcx, rax; hHeap
0x18001cbf0  call    cs:__imp_HeapFree
0x18001cbf6  jmp     short loc_18001CBFB
0x18001cbf8  mov     [r14], rdi
0x18001cbfb  mov     eax, ebx
0x18001cbfd  add     rsp, 28h
0x18001cc01  pop     r14
0x18001cc03  pop     rdi
0x18001cc04  pop     rsi
0x18001cc05  pop     rbx
0x18001cc06  retn
```
