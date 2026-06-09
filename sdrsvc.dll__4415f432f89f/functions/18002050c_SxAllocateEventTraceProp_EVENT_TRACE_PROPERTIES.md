# SxAllocateEventTraceProp(_EVENT_TRACE_PROPERTIES * *)

- ea: `0x18002050c`
- end: `0x180020612`
- name: `?SxAllocateEventTraceProp@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct _EVENT_TRACE_PROPERTIES **)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020618`
- `0x1800212e4`
- `0x1800215d4`

## callees

- `0x18000ea0c`
- `0x18001586c`
- `0x180015974`
- `0x18002050c`
- `0x18002170a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020588`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800205f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800205f1`

## pseudocode

```c
__int64 __fastcall SxAllocateEventTraceProp(struct _EVENT_TRACE_PROPERTIES **a1)
{
  __int16 v2; // ax
  struct _EVENT_TRACE_PROPERTIES *v3; // rbx
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-48h] BYREF
  __int16 v7; // [rsp+24h] [rbp-44h]
  __int16 v8; // [rsp+26h] [rbp-42h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v6, "SxAllocateEventTraceProp", 34, 1);
  v2 = 41;
  if ( !a1 )
  {
    v6 = -2147024809;
    goto LABEL_9;
  }
  *a1 = 0;
  v6 = 0;
  v7 = 41;
  v3 = (struct _EVENT_TRACE_PROPERTIES *)CoTaskMemAlloc(0x488u);
  v2 = 45;
  if ( !v3 )
  {
    v6 = -2147024882;
LABEL_9:
    v8 = v2;
    goto LABEL_10;
  }
  v6 = 0;
  v7 = 45;
  memset_0(v3, 0, 0x488u);
  v3->Wnode.BufferSize = 1160;
  v3->Wnode.Flags = 0x20000;
  v3->LoggerNameOffset = 120;
  v3->LogFileNameOffset = 640;
  *a1 = v3;
LABEL_10:
  CoTaskMemFree(0);
  v4 = v6;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v6);
  return v4;
}

```

## disassembly

```asm
0x18002050c  mov     [rsp+arg_0], rbx
0x180020511  push    rdi
0x180020512  sub     rsp, 60h
0x180020516  mov     rdi, rcx
0x180020519  mov     rcx, cs:WPP_GLOBAL_Control
0x180020520  lea     rax, WPP_GLOBAL_Control
0x180020527  cmp     rcx, rax
0x18002052a  jz      short loc_18002054A
0x18002052c  test    dword ptr [rcx+1Ch], 20000000h
0x180020533  jz      short loc_18002054A
0x180020535  mov     rcx, [rcx+10h]
0x180020539  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x180020540  mov     edx, 0Ah
0x180020545  call    WPP_SF_
0x18002054a  mov     r9d, 1; unsigned __int16
0x180020550  lea     rdx, aSxallocateeven; "SxAllocateEventTraceProp"
0x180020557  lea     rcx, [rsp+68h+var_48]; this
0x18002055c  lea     r8d, [r9+21h]; unsigned __int16
0x180020560  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180020565  mov     eax, 29h ; ')'
0x18002056a  test    rdi, rdi
0x18002056d  jz      short loc_1800205E2
0x18002056f  mov     ecx, 488h; cb
0x180020574  mov     qword ptr [rdi], 0
0x18002057b  mov     [rsp+68h+var_48], 0
0x180020583  mov     [rsp+68h+var_44], ax
0x180020588  call    cs:__imp_CoTaskMemAlloc
0x18002058e  mov     rbx, rax
0x180020591  test    rax, rax
0x180020594  mov     eax, 2Dh ; '-'
0x180020599  jnz     short loc_1800205A5
0x18002059b  mov     [rsp+68h+var_48], 8007000Eh
0x1800205a3  jmp     short loc_1800205EA
0x1800205a5  xor     edx, edx; Val
0x1800205a7  mov     [rsp+68h+var_48], 0
0x1800205af  mov     r8d, 488h; Size
0x1800205b5  mov     [rsp+68h+var_44], ax
0x1800205ba  mov     rcx, rbx; void *
0x1800205bd  call    memset_0
0x1800205c2  mov     dword ptr [rbx], 488h
0x1800205c8  mov     dword ptr [rbx+2Ch], 20000h
0x1800205cf  mov     dword ptr [rbx+74h], 78h ; 'x'
0x1800205d6  mov     dword ptr [rbx+70h], 280h
0x1800205dd  mov     [rdi], rbx
0x1800205e0  jmp     short loc_1800205EF
0x1800205e2  mov     [rsp+68h+var_48], 80070057h
0x1800205ea  mov     [rsp+68h+var_42], ax
0x1800205ef  xor     ecx, ecx; pv
0x1800205f1  call    cs:__imp_CoTaskMemFree
0x1800205f7  mov     ebx, [rsp+68h+var_48]
0x1800205fb  lea     rcx, [rsp+68h+var_48]; this
0x180020600  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180020605  mov     eax, ebx
0x180020607  mov     rbx, [rsp+68h+arg_0]
0x18002060c  add     rsp, 60h
0x180020610  pop     rdi
0x180020611  retn
```
