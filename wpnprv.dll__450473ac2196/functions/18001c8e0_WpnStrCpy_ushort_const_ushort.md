# WpnStrCpy(ushort const *,ushort * *)

- ea: `0x18001c8e0`
- end: `0x18001ca71`
- name: `?WpnStrCpy@@YAJPEBGPEAPEAG@Z`
- size: `401`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001de60`

## callees

- `0x18000c9e4`
- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x18001c6dc`
- `0x18001c8e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c993`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c993`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ca5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ca5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c97b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ca4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c97b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ca4d`

## string_xrefs

- `0x18001c929`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x18001c9a6`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x18001ca08`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`

## pseudocode

```c
__int64 __fastcall WpnStrCpy(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  HANDLE ProcessHeap; // rax
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
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
  v4 = StringCchLengthW(a1, 0x7FFFFFFFu, &v18);
  v5 = v4;
  if ( v4 >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v10 = v18;
    v11 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * v18 + 2);
    v12 = v11;
    if ( v11 )
    {
      v13 = StringCchCopyW(v11, v10 + 1, a1);
      v5 = v13;
      if ( v13 >= 0 )
      {
        *a2 = v12;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x199,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
          (const char *)(unsigned int)v13,
          v16);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids, v5);
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v12);
      }
    }
    else
    {
      v5 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x196,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
        (const char *)0x8007000ELL,
        v16);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v7 = 28;
        v8 = 2147942414LL;
        goto LABEL_9;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
      (const char *)(unsigned int)v4,
      v16);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v7 = 27;
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
0x18001c8e0  push    rbx
0x18001c8e2  push    rbp
0x18001c8e3  push    rsi
0x18001c8e4  push    rdi
0x18001c8e5  sub     rsp, 28h
0x18001c8e9  mov     [rsp+48h+arg_0], 0
0x18001c8f2  mov     rsi, rdx
0x18001c8f5  mov     rbp, rcx
0x18001c8f8  test    rcx, rcx
0x18001c8fb  jnz     short loc_18001C902
0x18001c8fd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c902  test    rsi, rsi
0x18001c905  jnz     short loc_18001C90C
0x18001c907  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c90c  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x18001c911  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001c916  mov     rcx, rbp; unsigned __int16 *
0x18001c919  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001c91e  mov     ebx, eax
0x18001c920  test    eax, eax
0x18001c922  jns     short loc_18001C97B
0x18001c924  mov     rcx, [rsp+48h]; this
0x18001c929  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001c930  mov     r9d, eax; char *
0x18001c933  mov     edx, 193h; void *
0x18001c938  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c93d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c944  lea     rax, WPP_GLOBAL_Control
0x18001c94b  cmp     rcx, rax
0x18001c94e  jz      loc_18001CA66
0x18001c954  test    byte ptr [rcx+1Ch], 80h
0x18001c958  jz      loc_18001CA66
0x18001c95e  mov     edx, 1Bh
0x18001c963  mov     r9d, ebx
0x18001c966  mov     rcx, [rcx+10h]
0x18001c96a  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x18001c971  call    WPP_SF_d
0x18001c976  jmp     loc_18001CA66
0x18001c97b  call    cs:__imp_GetProcessHeap
0x18001c981  mov     rbx, [rsp+48h+arg_0]
0x18001c986  xor     edx, edx; dwFlags
0x18001c988  mov     rcx, rax; hHeap
0x18001c98b  lea     r8, ds:2[rbx*2]; dwBytes
0x18001c993  call    cs:__imp_HeapAlloc
0x18001c999  mov     rdi, rax
0x18001c99c  test    rax, rax
0x18001c99f  jnz     short loc_18001C9EE
0x18001c9a1  mov     rcx, [rsp+48h]; this
0x18001c9a6  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001c9ad  mov     ebx, 8007000Eh
0x18001c9b2  mov     edx, 196h; void *
0x18001c9b7  mov     r9d, ebx; char *
0x18001c9ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c9bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9c6  lea     rax, WPP_GLOBAL_Control
0x18001c9cd  cmp     rcx, rax
0x18001c9d0  jz      loc_18001CA66
0x18001c9d6  test    byte ptr [rcx+1Ch], 80h
0x18001c9da  jz      loc_18001CA66
0x18001c9e0  lea     edx, [rdi+1Ch]
0x18001c9e3  mov     r9d, 8007000Eh
0x18001c9e9  jmp     loc_18001C966
0x18001c9ee  lea     rdx, [rbx+1]; unsigned __int64
0x18001c9f2  mov     r8, rbp; unsigned __int16 *
0x18001c9f5  mov     rcx, rdi; unsigned __int16 *
0x18001c9f8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c9fd  mov     ebx, eax
0x18001c9ff  test    eax, eax
0x18001ca01  jns     short loc_18001CA63
0x18001ca03  mov     rcx, [rsp+48h]; this
0x18001ca08  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ca0f  mov     r9d, eax; char *
0x18001ca12  mov     edx, 199h; void *
0x18001ca17  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ca1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca23  lea     rax, WPP_GLOBAL_Control
0x18001ca2a  cmp     rcx, rax
0x18001ca2d  jz      short loc_18001CA4D
0x18001ca2f  test    byte ptr [rcx+1Ch], 80h
0x18001ca33  jz      short loc_18001CA4D
0x18001ca35  mov     rcx, [rcx+10h]
0x18001ca39  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x18001ca40  mov     edx, 1Dh
0x18001ca45  mov     r9d, ebx
0x18001ca48  call    WPP_SF_d
0x18001ca4d  call    cs:__imp_GetProcessHeap
0x18001ca53  mov     r8, rdi; lpMem
0x18001ca56  xor     edx, edx; dwFlags
0x18001ca58  mov     rcx, rax; hHeap
0x18001ca5b  call    cs:__imp_HeapFree
0x18001ca61  jmp     short loc_18001CA66
0x18001ca63  mov     [rsi], rdi
0x18001ca66  mov     eax, ebx
0x18001ca68  add     rsp, 28h
0x18001ca6c  pop     rdi
0x18001ca6d  pop     rsi
0x18001ca6e  pop     rbp
0x18001ca6f  pop     rbx
0x18001ca70  retn
```
