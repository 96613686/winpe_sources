# wiasFreePropContext

- ea: `0x180040350`
- end: `0x18004040a`
- name: `wiasFreePropContext`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x180040350`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800403d7`
- `ole32!CoTaskMemFree` at `0x1800403e1`
- `ole32!CoTaskMemFree` at `0x1800403d7`
- `ole32!CoTaskMemFree` at `0x1800403e1`

## string_xrefs

- `0x180040383`: `wiasFreePropContext, pContext is a bad (read) pointer`
- `0x1800403a9`: `wiasFreePropContext, pContext is a bad (read) pointer`

## pseudocode

```c
__int64 __fastcall wiasFreePropContext(__int64 a1)
{
  char ***v2; // rax
  char *v3; // rdx
  __int64 v4; // r8
  char *v5; // rbx
  void *v6; // rdx
  void **v7; // rax
  void *v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // ebx
  unsigned int lpMem; // [rsp+20h] [rbp-68h]
  _BYTE v13[88]; // [rsp+30h] [rbp-58h] BYREF

  v2 = (char ***)WiaTrace_Trace("::wiasFreePropContext");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v13, v3, v4, (char **)"wiasFreePropContext", lpMem, v2);
  if ( a1 )
  {
    CoTaskMemFree(*(LPVOID *)(a1 + 8));
    CoTaskMemFree(*(LPVOID *)(a1 + 16));
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    v10 = 0;
  }
  else
  {
    v5 = (char *)WiaTrace_TraceLog("wiasFreePropContext, pContext is a bad (read) pointer");
    WriteDbgTraceErrorWI("wiasFreePropContext", v5);
    WiaTrcLib::Free((WiaTrcLib *)v5, v6);
    v7 = (void **)WiaTrace_Trace("wiasFreePropContext, pContext is a bad (read) pointer");
    WiaTrace_ProcessTrace_Ex(v9, v8, (void *)"wiasFreePropContext", 1, v7);
    v10 = -2147467261;
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v13);
  return v10;
}

```

## disassembly

```asm
0x180040350  push    rbx
0x180040352  sub     rsp, 80h
0x180040359  mov     rbx, rcx
0x18004035c  lea     rcx, aWiasfreepropco_1; "::wiasFreePropContext"
0x180040363  call    WiaTrace_Trace
0x180040368  lea     r9, aWiasfreepropco_2; "wiasFreePropContext"
0x18004036f  mov     [rsp+88h+var_60], rax; struct tagWiaTraceData_Type *
0x180040374  lea     rcx, [rsp+88h+var_58]; this
0x180040379  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18004037e  test    rbx, rbx
0x180040381  jnz     short loc_1800403D3
0x180040383  lea     rcx, aWiasfreepropco_0; "wiasFreePropContext, pContext is a bad "...
0x18004038a  call    WiaTrace_TraceLog
0x18004038f  mov     rdx, rax; char *
0x180040392  lea     rcx, aWiasfreepropco_2; "wiasFreePropContext"
0x180040399  mov     rbx, rax
0x18004039c  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800403a1  mov     rcx, rbx; this
0x1800403a4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800403a9  lea     rcx, aWiasfreepropco_0; "wiasFreePropContext, pContext is a bad "...
0x1800403b0  call    WiaTrace_Trace
0x1800403b5  mov     r9d, 1; int
0x1800403bb  mov     [rsp+88h+lpMem], rax; lpMem
0x1800403c0  lea     r8, aWiasfreepropco_2; "wiasFreePropContext"
0x1800403c7  call    WiaTrace_ProcessTrace_Ex
0x1800403cc  mov     ebx, 80004003h
0x1800403d1  jmp     short loc_1800403F5
0x1800403d3  mov     rcx, [rbx+8]; pv
0x1800403d7  call    cs:__imp_CoTaskMemFree
0x1800403dd  mov     rcx, [rbx+10h]; pv
0x1800403e1  call    cs:__imp_CoTaskMemFree
0x1800403e7  xor     eax, eax
0x1800403e9  xorps   xmm0, xmm0
0x1800403ec  movups  xmmword ptr [rbx], xmm0
0x1800403ef  mov     [rbx+10h], rax
0x1800403f3  xor     ebx, ebx
0x1800403f5  lea     rcx, [rsp+88h+var_58]; this
0x1800403fa  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x1800403ff  mov     eax, ebx
0x180040401  add     rsp, 80h
0x180040408  pop     rbx
0x180040409  retn
```
