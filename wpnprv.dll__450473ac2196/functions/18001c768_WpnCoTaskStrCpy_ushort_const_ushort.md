# WpnCoTaskStrCpy(ushort const *,ushort * *)

- ea: `0x18001c768`
- end: `0x18001c8d8`
- name: `?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z`
- size: `368`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180084ac8`

## callees

- `0x18000c9e4`
- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x18001c6dc`
- `0x18001c768`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c8c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c8c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c810`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c810`

## string_xrefs

- `0x18001c7b1`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x18001c823`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`
- `0x18001c87a`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnstr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WpnCoTaskStrCpy(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  int v12; // eax
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  v16 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  v4 = StringCchLengthW(a1, 0x7FFFFFFFu, &v16);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v9 = v16;
    v10 = (unsigned __int16 *)CoTaskMemAlloc(2 * v16 + 2);
    v11 = v10;
    if ( v10 )
    {
      v12 = StringCchCopyW(v10, v9 + 1, a1);
      v5 = v12;
      if ( v12 >= 0 )
      {
        *a2 = v11;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1CB,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
          (const char *)(unsigned int)v12,
          v14);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids, v5);
        CoTaskMemFree(v11);
      }
    }
    else
    {
      v5 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
        (const char *)0x8007000ELL,
        v14);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v7 = 31;
        v8 = 2147942414LL;
        goto LABEL_9;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1C5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnstr.cpp",
      (const char *)(unsigned int)v4,
      v14);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v7 = 30;
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
0x18001c768  push    rbx
0x18001c76a  push    rbp
0x18001c76b  push    rsi
0x18001c76c  push    rdi
0x18001c76d  sub     rsp, 28h
0x18001c771  mov     [rsp+48h+arg_0], 0
0x18001c77a  mov     rsi, rdx
0x18001c77d  mov     rbp, rcx
0x18001c780  test    rcx, rcx
0x18001c783  jnz     short loc_18001C78A
0x18001c785  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c78a  test    rsi, rsi
0x18001c78d  jnz     short loc_18001C794
0x18001c78f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c794  lea     r8, [rsp+48h+arg_0]; unsigned __int64 *
0x18001c799  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001c79e  mov     rcx, rbp; unsigned __int16 *
0x18001c7a1  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001c7a6  mov     ebx, eax
0x18001c7a8  test    eax, eax
0x18001c7aa  jns     short loc_18001C803
0x18001c7ac  mov     rcx, [rsp+48h]; this
0x18001c7b1  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001c7b8  mov     r9d, eax; char *
0x18001c7bb  mov     edx, 1C5h; void *
0x18001c7c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c7c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7cc  lea     rax, WPP_GLOBAL_Control
0x18001c7d3  cmp     rcx, rax
0x18001c7d6  jz      loc_18001C8CD
0x18001c7dc  test    byte ptr [rcx+1Ch], 80h
0x18001c7e0  jz      loc_18001C8CD
0x18001c7e6  mov     edx, 1Eh
0x18001c7eb  mov     r9d, ebx
0x18001c7ee  mov     rcx, [rcx+10h]
0x18001c7f2  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x18001c7f9  call    WPP_SF_d
0x18001c7fe  jmp     loc_18001C8CD
0x18001c803  mov     rbx, [rsp+48h+arg_0]
0x18001c808  lea     rcx, ds:2[rbx*2]; cb
0x18001c810  call    cs:__imp_CoTaskMemAlloc
0x18001c816  mov     rdi, rax
0x18001c819  test    rax, rax
0x18001c81c  jnz     short loc_18001C860
0x18001c81e  mov     rcx, [rsp+48h]; this
0x18001c823  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001c82a  mov     ebx, 8007000Eh
0x18001c82f  mov     edx, 1C8h; void *
0x18001c834  mov     r9d, ebx; char *
0x18001c837  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c83c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c843  lea     rax, WPP_GLOBAL_Control
0x18001c84a  cmp     rcx, rax
0x18001c84d  jz      short loc_18001C8CD
0x18001c84f  test    byte ptr [rcx+1Ch], 80h
0x18001c853  jz      short loc_18001C8CD
0x18001c855  lea     edx, [rdi+1Fh]
0x18001c858  mov     r9d, 8007000Eh
0x18001c85e  jmp     short loc_18001C7EE
0x18001c860  lea     rdx, [rbx+1]; unsigned __int64
0x18001c864  mov     r8, rbp; unsigned __int16 *
0x18001c867  mov     rcx, rdi; unsigned __int16 *
0x18001c86a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c86f  mov     ebx, eax
0x18001c871  test    eax, eax
0x18001c873  jns     short loc_18001C8CA
0x18001c875  mov     rcx, [rsp+48h]; this
0x18001c87a  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001c881  mov     r9d, eax; char *
0x18001c884  mov     edx, 1CBh; void *
0x18001c889  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c88e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c895  lea     rax, WPP_GLOBAL_Control
0x18001c89c  cmp     rcx, rax
0x18001c89f  jz      short loc_18001C8BF
0x18001c8a1  test    byte ptr [rcx+1Ch], 80h
0x18001c8a5  jz      short loc_18001C8BF
0x18001c8a7  mov     rcx, [rcx+10h]
0x18001c8ab  lea     r8, WPP_d989c3166eed3020292a0d8941f8b143_Traceguids
0x18001c8b2  mov     edx, 20h ; ' '
0x18001c8b7  mov     r9d, ebx
0x18001c8ba  call    WPP_SF_d
0x18001c8bf  mov     rcx, rdi; pv
0x18001c8c2  call    cs:__imp_CoTaskMemFree
0x18001c8c8  jmp     short loc_18001C8CD
0x18001c8ca  mov     [rsi], rdi
0x18001c8cd  mov     eax, ebx
0x18001c8cf  add     rsp, 28h
0x18001c8d3  pop     rdi
0x18001c8d4  pop     rsi
0x18001c8d5  pop     rbp
0x18001c8d6  pop     rbx
0x18001c8d7  retn
```
