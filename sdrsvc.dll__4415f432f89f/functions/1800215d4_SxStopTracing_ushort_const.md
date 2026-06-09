# SxStopTracing(ushort const *)

- ea: `0x1800215d4`
- end: `0x1800216dc`
- name: `?SxStopTracing@@YAJPEBG@Z`
- size: `264`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016520`
- `0x18001698c`

## callees

- `0x18000ea0c`
- `0x18001586c`
- `0x180015974`
- `0x18002050c`
- `0x1800215d4`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180021680`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180021698`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180021680`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180021698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800216bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800216bd`

## pseudocode

```c
__int64 __fastcall SxStopTracing(struct _EVENT_TRACE_PROPERTIES *a1)
{
  int v1; // eax
  struct _EVENT_TRACE_PROPERTIES *v2; // rbx
  bool v3; // sf
  __int16 v4; // ax
  signed int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-40h] BYREF
  __int16 v9; // [rsp+24h] [rbp-3Ch]
  __int16 v10; // [rsp+26h] [rbp-3Ah]
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+70h] [rbp+10h] BYREF

  Properties = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "SxStopTracing", 685, 1);
  Properties = 0;
  v9 = 689;
  v8 = 0;
  v1 = SxAllocateEventTraceProp(&Properties);
  v2 = Properties;
  v3 = v1 < 0;
  v8 = v1;
  v4 = 691;
  if ( v3 )
    goto LABEL_5;
  v9 = 691;
  ControlTraceW(0, L"BuiltInWindowsBackupTracing", Properties, 3u);
  v5 = ControlTraceW(0, L"BuiltInWindowsBackupTracing", v2, 1u);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  v8 = v5;
  v3 = v5 < 0;
  v4 = 695;
  if ( v3 )
LABEL_5:
    v10 = v4;
  else
    v9 = 695;
  CoTaskMemFree(v2);
  v6 = v8;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return v6;
}

```

## disassembly

```asm
0x1800215d4  mov     [rsp-8+arg_8], rbx
0x1800215d9  mov     [rsp-8+Properties], rcx
0x1800215de  push    rbp
0x1800215df  mov     rbp, rsp
0x1800215e2  sub     rsp, 60h
0x1800215e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215ed  lea     rax, WPP_GLOBAL_Control
0x1800215f4  cmp     rcx, rax
0x1800215f7  jz      short loc_180021617
0x1800215f9  test    dword ptr [rcx+1Ch], 20000000h
0x180021600  jz      short loc_180021617
0x180021602  mov     rcx, [rcx+10h]
0x180021606  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x18002160d  mov     edx, 19h
0x180021612  call    WPP_SF_
0x180021617  mov     r9d, 1; unsigned __int16
0x18002161d  lea     rdx, aSxstoptracing; "SxStopTracing"
0x180021624  mov     r8d, 2ADh; unsigned __int16
0x18002162a  lea     rcx, [rbp+var_40]; this
0x18002162e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180021633  mov     eax, 2B1h
0x180021638  mov     [rbp+Properties], 0
0x180021640  lea     rcx, [rbp+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x180021644  mov     [rbp+var_3C], ax
0x180021648  mov     [rbp+var_40], 0
0x18002164f  call    ?SxAllocateEventTraceProp@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; SxAllocateEventTraceProp(_EVENT_TRACE_PROPERTIES * *)
0x180021654  mov     rbx, [rbp+Properties]
0x180021658  test    eax, eax
0x18002165a  mov     [rbp+var_40], eax
0x18002165d  mov     eax, 2B3h
0x180021662  jns     short loc_18002166A
0x180021664  mov     [rbp+var_3A], ax
0x180021668  jmp     short loc_1800216BA
0x18002166a  mov     r9d, 3; ControlCode
0x180021670  mov     [rbp+var_3C], ax
0x180021674  mov     r8, rbx; Properties
0x180021677  lea     rdx, aBuiltinwindows; "BuiltInWindowsBackupTracing"
0x18002167e  xor     ecx, ecx; TraceHandle
0x180021680  call    cs:__imp_ControlTraceW
0x180021686  mov     r9d, 1; ControlCode
0x18002168c  lea     rdx, aBuiltinwindows; "BuiltInWindowsBackupTracing"
0x180021693  mov     r8, rbx; Properties
0x180021696  xor     ecx, ecx; TraceHandle
0x180021698  call    cs:__imp_ControlTraceW
0x18002169e  test    eax, eax
0x1800216a0  jle     short loc_1800216AA
0x1800216a2  movzx   eax, ax
0x1800216a5  or      eax, 80070000h
0x1800216aa  mov     [rbp+var_40], eax
0x1800216ad  test    eax, eax
0x1800216af  mov     eax, 2B7h
0x1800216b4  js      short loc_180021664
0x1800216b6  mov     [rbp+var_3C], ax
0x1800216ba  mov     rcx, rbx; pv
0x1800216bd  call    cs:__imp_CoTaskMemFree
0x1800216c3  mov     ebx, [rbp+var_40]
0x1800216c6  lea     rcx, [rbp+var_40]; this
0x1800216ca  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800216cf  mov     eax, ebx
0x1800216d1  mov     rbx, [rsp+60h+arg_8]
0x1800216d6  add     rsp, 60h
0x1800216da  pop     rbp
0x1800216db  retn
```
