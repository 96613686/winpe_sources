# SxCheckWBDiagSession(void)

- ea: `0x180020618`
- end: `0x180020802`
- name: `?SxCheckWBDiagSession@@YAJXZ`
- size: `490`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016520`

## callees

- `0x18000ea0c`
- `0x180014f70`
- `0x18001507c`
- `0x18001586c`
- `0x180015974`
- `0x18002050c`
- `0x180020618`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x1800206fd`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x1800206fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020723`

## pseudocode

```c
__int64 SxCheckWBDiagSession(void)
{
  __int16 v0; // ax
  signed int v1; // eax
  bool v2; // sf
  int v3; // ebx
  unsigned int v4; // ebx
  int v6; // [rsp+30h] [rbp-39h] BYREF
  __int16 v7; // [rsp+34h] [rbp-35h]
  __int16 v8; // [rsp+36h] [rbp-33h]
  int v9; // [rsp+68h] [rbp-1h] BYREF
  __int16 v10; // [rsp+6Ch] [rbp+3h]
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+D0h] [rbp+67h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "SxCheckWBDiagSession", 293, 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v6, "SxQueryTraceSession", 93, 1);
  Properties = 0;
  v7 = 97;
  v6 = 0;
  v6 = SxAllocateEventTraceProp(&Properties);
  v0 = 99;
  if ( v6 < 0 )
    goto LABEL_8;
  v7 = 99;
  v1 = ControlTraceW(0, L"blblog", Properties, 0);
  if ( v1 > 0 )
    v1 = (unsigned __int16)v1 | 0x80070000;
  v6 = v1;
  v2 = v1 < 0;
  v0 = 101;
  if ( v2 )
LABEL_8:
    v8 = v0;
  else
    v7 = 101;
  CoTaskMemFree(Properties);
  v3 = v6;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v6);
  if ( v3 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids, L"blblog");
    v9 = 1;
    v10 = 313;
  }
  else if ( v3 == -2147020695 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids, L"blblog");
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids,
      (unsigned int)L"blblog",
      v3);
  }
  v4 = v9;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return v4;
}

```

## disassembly

```asm
0x180020618  push    rbp
0x18002061a  push    rbx
0x18002061b  push    rsi
0x18002061c  push    rdi
0x18002061d  lea     rbp, [rsp-3Fh]
0x180020622  sub     rsp, 0A8h
0x180020629  mov     rcx, cs:WPP_GLOBAL_Control
0x180020630  lea     rdi, WPP_GLOBAL_Control
0x180020637  lea     rsi, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x18002063e  mov     ebx, 20000000h
0x180020643  cmp     rcx, rdi
0x180020646  jz      short loc_18002065E
0x180020648  test    [rcx+1Ch], ebx
0x18002064b  jz      short loc_18002065E
0x18002064d  mov     rcx, [rcx+10h]
0x180020651  mov     edx, 0Fh
0x180020656  mov     r8, rsi
0x180020659  call    WPP_SF_
0x18002065e  mov     r9d, 1; unsigned __int16
0x180020664  lea     rdx, aSxcheckwbdiags; "SxCheckWBDiagSession"
0x18002066b  mov     r8d, 125h; unsigned __int16
0x180020671  lea     rcx, [rbp+57h+var_58]; this
0x180020675  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002067a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020681  cmp     rcx, rdi
0x180020684  jz      short loc_18002069C
0x180020686  test    [rcx+1Ch], ebx
0x180020689  jz      short loc_18002069C
0x18002068b  mov     rcx, [rcx+10h]
0x18002068f  mov     edx, 0Ch
0x180020694  mov     r8, rsi
0x180020697  call    WPP_SF_
0x18002069c  mov     r9d, 1; unsigned __int16
0x1800206a2  lea     rdx, aSxquerytracese; "SxQueryTraceSession"
0x1800206a9  lea     rcx, [rbp+57h+var_90]; this
0x1800206ad  lea     r8d, [r9+5Ch]; unsigned __int16
0x1800206b1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800206b6  mov     eax, 61h ; 'a'
0x1800206bb  mov     [rbp+57h+Properties], 0
0x1800206c3  lea     rcx, [rbp+57h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x1800206c7  mov     [rbp+57h+var_8C], ax
0x1800206cb  mov     [rbp+57h+var_90], 0
0x1800206d2  call    ?SxAllocateEventTraceProp@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; SxAllocateEventTraceProp(_EVENT_TRACE_PROPERTIES * *)
0x1800206d7  mov     [rbp+57h+var_90], eax
0x1800206da  test    eax, eax
0x1800206dc  mov     eax, 63h ; 'c'
0x1800206e1  jns     short loc_1800206E9
0x1800206e3  mov     [rbp+57h+var_8A], ax
0x1800206e7  jmp     short loc_18002071F
0x1800206e9  mov     r8, [rbp+57h+Properties]; Properties
0x1800206ed  lea     rdx, InstanceName; "blblog"
0x1800206f4  xor     r9d, r9d; ControlCode
0x1800206f7  mov     [rbp+57h+var_8C], ax
0x1800206fb  xor     ecx, ecx; TraceHandle
0x1800206fd  call    cs:__imp_ControlTraceW
0x180020703  test    eax, eax
0x180020705  jle     short loc_18002070F
0x180020707  movzx   eax, ax
0x18002070a  or      eax, 80070000h
0x18002070f  mov     [rbp+57h+var_90], eax
0x180020712  test    eax, eax
0x180020714  mov     eax, 65h ; 'e'
0x180020719  js      short loc_1800206E3
0x18002071b  mov     [rbp+57h+var_8C], ax
0x18002071f  mov     rcx, [rbp+57h+Properties]; pv
0x180020723  call    cs:__imp_CoTaskMemFree
0x180020729  mov     ebx, [rbp+57h+var_90]
0x18002072c  lea     rcx, [rbp+57h+var_90]; this
0x180020730  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180020735  test    ebx, ebx
0x180020737  jns     short loc_1800207AB
0x180020739  cmp     ebx, 80071069h
0x18002073f  jnz     short loc_180020778
0x180020741  mov     rcx, cs:WPP_GLOBAL_Control
0x180020748  cmp     rcx, rdi
0x18002074b  jz      loc_1800207E8
0x180020751  test    dword ptr [rcx+1Ch], 8000000h
0x180020758  jz      loc_1800207E8
0x18002075e  mov     rcx, [rcx+10h]
0x180020762  lea     r9, InstanceName; "blblog"
0x180020769  mov     edx, 10h
0x18002076e  mov     r8, rsi
0x180020771  call    WPP_SF_S
0x180020776  jmp     short loc_1800207E8
0x180020778  mov     rcx, cs:WPP_GLOBAL_Control
0x18002077f  cmp     rcx, rdi
0x180020782  jz      short loc_1800207E8
0x180020784  test    dword ptr [rcx+1Ch], 4000000h
0x18002078b  jz      short loc_1800207E8
0x18002078d  mov     rcx, [rcx+10h]
0x180020791  lea     r9, InstanceName; "blblog"
0x180020798  mov     edx, 11h
0x18002079d  mov     [rsp+0C0h+var_A0], ebx
0x1800207a1  mov     r8, rsi
0x1800207a4  call    WPP_SF_Sd
0x1800207a9  jmp     short loc_1800207E8
0x1800207ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207b2  cmp     rcx, rdi
0x1800207b5  jz      short loc_1800207D8
0x1800207b7  test    dword ptr [rcx+1Ch], 8000000h
0x1800207be  jz      short loc_1800207D8
0x1800207c0  mov     rcx, [rcx+10h]
0x1800207c4  lea     r9, InstanceName; "blblog"
0x1800207cb  mov     edx, 12h
0x1800207d0  mov     r8, rsi
0x1800207d3  call    WPP_SF_S
0x1800207d8  mov     eax, 139h
0x1800207dd  mov     [rbp+57h+var_58], 1
0x1800207e4  mov     [rbp+57h+var_54], ax
0x1800207e8  mov     ebx, [rbp+57h+var_58]
0x1800207eb  lea     rcx, [rbp+57h+var_58]; this
0x1800207ef  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800207f4  mov     eax, ebx
0x1800207f6  add     rsp, 0A8h
0x1800207fd  pop     rdi
0x1800207fe  pop     rsi
0x1800207ff  pop     rbx
0x180020800  pop     rbp
0x180020801  retn
```
