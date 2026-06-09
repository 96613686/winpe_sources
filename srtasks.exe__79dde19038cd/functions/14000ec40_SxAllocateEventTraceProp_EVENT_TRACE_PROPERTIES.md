# SxAllocateEventTraceProp(_EVENT_TRACE_PROPERTIES * *)

- ea: `0x14000ec40`
- end: `0x14000ed46`
- name: `?SxAllocateEventTraceProp@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct _EVENT_TRACE_PROPERTIES **)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14000ed4c`
- `0x14000fa1c`
- `0x14000fd0c`

## callees

- `0x140002e1c`
- `0x14000e324`
- `0x14000e41c`
- `0x14000ec40`
- `0x14001094e`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x14000ecbc`
- `ole32!CoTaskMemAlloc` at `0x14000ecbc`
- `ole32!CoTaskMemFree` at `0x14000ed25`
- `ole32!CoTaskMemFree` at `0x14000ed25`

## pseudocode

```c
__int64 __fastcall SxAllocateEventTraceProp(struct _EVENT_TRACE_PROPERTIES **a1)
{
  __int16 v2; // ax
  struct _EVENT_TRACE_PROPERTIES *v3; // rbx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  int v8; // [rsp+20h] [rbp-48h] BYREF
  __int16 v9; // [rsp+24h] [rbp-44h]
  __int16 v10; // [rsp+26h] [rbp-42h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "SxAllocateEventTraceProp", 34, 1);
  v2 = 41;
  if ( !a1 )
  {
    v8 = -2147024809;
    goto LABEL_9;
  }
  *a1 = 0;
  v8 = 0;
  v9 = 41;
  v3 = (struct _EVENT_TRACE_PROPERTIES *)CoTaskMemAlloc(0x488u);
  v2 = 45;
  if ( !v3 )
  {
    v8 = -2147024882;
LABEL_9:
    v10 = v2;
    goto LABEL_10;
  }
  v8 = 0;
  v9 = 45;
  memset_0(v3, 0, 0x488u);
  v3->Wnode.BufferSize = 1160;
  v3->Wnode.Flags = 0x20000;
  v3->LoggerNameOffset = 120;
  v3->LogFileNameOffset = 640;
  *a1 = v3;
LABEL_10:
  CoTaskMemFree(0);
  v4 = v8;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8, v5, v6);
  return v4;
}

```

## disassembly

```asm
0x14000ec40  mov     [rsp+arg_0], rbx
0x14000ec45  push    rdi
0x14000ec46  sub     rsp, 60h
0x14000ec4a  mov     rdi, rcx
0x14000ec4d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec54  lea     rax, WPP_GLOBAL_Control
0x14000ec5b  cmp     rcx, rax
0x14000ec5e  jz      short loc_14000EC7E
0x14000ec60  test    dword ptr [rcx+1Ch], 20000000h
0x14000ec67  jz      short loc_14000EC7E
0x14000ec69  mov     rcx, [rcx+10h]
0x14000ec6d  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x14000ec74  mov     edx, 0Ah
0x14000ec79  call    WPP_SF_
0x14000ec7e  mov     r9d, 1; unsigned __int16
0x14000ec84  lea     rdx, aSxallocateeven; "SxAllocateEventTraceProp"
0x14000ec8b  lea     rcx, [rsp+68h+var_48]; this
0x14000ec90  lea     r8d, [r9+21h]; unsigned __int16
0x14000ec94  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000ec99  mov     eax, 29h ; ')'
0x14000ec9e  test    rdi, rdi
0x14000eca1  jz      short loc_14000ED16
0x14000eca3  mov     ecx, 488h; cb
0x14000eca8  mov     qword ptr [rdi], 0
0x14000ecaf  mov     [rsp+68h+var_48], 0
0x14000ecb7  mov     [rsp+68h+var_44], ax
0x14000ecbc  call    cs:__imp_CoTaskMemAlloc
0x14000ecc2  mov     rbx, rax
0x14000ecc5  test    rax, rax
0x14000ecc8  mov     eax, 2Dh ; '-'
0x14000eccd  jnz     short loc_14000ECD9
0x14000eccf  mov     [rsp+68h+var_48], 8007000Eh
0x14000ecd7  jmp     short loc_14000ED1E
0x14000ecd9  xor     edx, edx; Val
0x14000ecdb  mov     [rsp+68h+var_48], 0
0x14000ece3  mov     r8d, 488h; Size
0x14000ece9  mov     [rsp+68h+var_44], ax
0x14000ecee  mov     rcx, rbx; void *
0x14000ecf1  call    memset_0
0x14000ecf6  mov     dword ptr [rbx], 488h
0x14000ecfc  mov     dword ptr [rbx+2Ch], 20000h
0x14000ed03  mov     dword ptr [rbx+74h], 78h ; 'x'
0x14000ed0a  mov     dword ptr [rbx+70h], 280h
0x14000ed11  mov     [rdi], rbx
0x14000ed14  jmp     short loc_14000ED23
0x14000ed16  mov     [rsp+68h+var_48], 80070057h
0x14000ed1e  mov     [rsp+68h+var_42], ax
0x14000ed23  xor     ecx, ecx; pv
0x14000ed25  call    cs:__imp_CoTaskMemFree
0x14000ed2b  mov     ebx, [rsp+68h+var_48]
0x14000ed2f  lea     rcx, [rsp+68h+var_48]; this
0x14000ed34  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000ed39  mov     eax, ebx
0x14000ed3b  mov     rbx, [rsp+68h+arg_0]
0x14000ed40  add     rsp, 60h
0x14000ed44  pop     rdi
0x14000ed45  retn
```
