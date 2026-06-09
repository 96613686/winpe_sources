# wiasCreatePropContext

- ea: `0x18003fd80`
- end: `0x18003ffe0`
- name: `wiasCreatePropContext`
- size: `608`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000da10`
- `0x18000dd00`
- `0x18002de18`
- `0x18002def8`
- `0x180034658`
- `0x18003fd80`
- `0x180077608`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18003fea3`
- `ole32!CoTaskMemAlloc` at `0x18003feaf`
- `ole32!CoTaskMemAlloc` at `0x18003fea3`
- `ole32!CoTaskMemAlloc` at `0x18003feaf`

## string_xrefs

- `0x18003fd9e`: `::wiasCreatePropContext`
- `0x18003fdb0`: `wiasCreatePropContext`
- `0x18003ff83`: `wiasCreatePropContext`
- `0x18003ffb1`: `wiasCreatePropContext`
- `0x18003fdd3`: `wiasCreatePropContext, pPropSpec is a bad (read) pointer`
- `0x18003fdf5`: `wiasCreatePropContext, pPropSpec is a bad (read) pointer`
- `0x18003fe31`: `wiasCreatePropContext, pProps is a bad (read) pointer`
- `0x18003fe53`: `wiasCreatePropContext, pProps is a bad (read) pointer`
- `0x18003fe69`: `wiasCreatePropContext, pContext is a bad (write) pointer`
- `0x18003fe8b`: `wiasCreatePropContext, pContext is a bad (write) pointer`
- `0x18003ff74`: `wiasCreatePropContext, pContext is a bad (write) pointer`
- `0x18003ff9a`: `wiasCreatePropContext, pContext is a bad (write) pointer`

## pseudocode

```c
__int64 __fastcall wiasCreatePropContext(unsigned int a1, __int64 a2, unsigned int a3, const void *a4, int *a5)
{
  __int64 v6; // rbp
  struct tagWiaTraceData_Type *v9; // rax
  char *v10; // rdx
  unsigned int v11; // r8d
  char *v12; // rbx
  void *v13; // rdx
  void **v14; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  char *v18; // rbx
  void *v19; // rdx
  char *v20; // rbx
  void *v21; // rdx
  int v22; // ebx
  SIZE_T v23; // rsi
  _OWORD *v24; // r14
  LPVOID v25; // rax
  void *v26; // r15
  unsigned int v27; // r8d
  __int64 v28; // rdx
  char *v29; // rbx
  void *v30; // rdx
  void **v31; // rax
  void *v32; // rdx
  __int64 v33; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-A8h]
  _BYTE v35[152]; // [rsp+30h] [rbp-98h] BYREF

  v6 = a3;
  v9 = (struct tagWiaTraceData_Type *)WiaTrace_Trace("::wiasCreatePropContext");
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v35, v10, v11, "wiasCreatePropContext", lpMem, v9);
  if ( a1 && !a2 )
  {
    v12 = (char *)WiaTrace_TraceLog("wiasCreatePropContext, pPropSpec is a bad (read) pointer");
    WriteDbgTraceErrorWI("wiasCreatePropContext", v12);
    WiaTrcLib::Free((WiaTrcLib *)v12, v13);
    v14 = (void **)WiaTrace_Trace("wiasCreatePropContext, pPropSpec is a bad (read) pointer");
LABEL_4:
    WiaTrace_ProcessTrace_Ex(v16, v15, (void *)"wiasCreatePropContext", 1, v14);
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v35);
    return 2147500035LL;
  }
  if ( (_DWORD)v6 && !a4 )
  {
    v18 = (char *)WiaTrace_TraceLog("wiasCreatePropContext, pProps is a bad (read) pointer");
    WriteDbgTraceErrorWI("wiasCreatePropContext", v18);
    WiaTrcLib::Free((WiaTrcLib *)v18, v19);
    v14 = (void **)WiaTrace_Trace("wiasCreatePropContext, pProps is a bad (read) pointer");
    goto LABEL_4;
  }
  if ( !a5 )
  {
    v20 = (char *)WiaTrace_TraceLog("wiasCreatePropContext, pContext is a bad (write) pointer");
    WriteDbgTraceErrorWI("wiasCreatePropContext", v20);
    WiaTrcLib::Free((WiaTrcLib *)v20, v21);
    v14 = (void **)WiaTrace_Trace("wiasCreatePropContext, pContext is a bad (write) pointer");
    goto LABEL_4;
  }
  v22 = v6 + 13;
  v23 = 4LL * (unsigned int)(v6 + 13);
  v24 = CoTaskMemAlloc(v23);
  v25 = CoTaskMemAlloc(v23);
  v26 = v25;
  if ( v24 && v25 )
  {
    *v24 = WIA_StdPropsInContext;
    v24[1] = xmmword_1800B0908;
    v24[2] = xmmword_1800B0918;
    *((_DWORD *)v24 + 12) = dword_1800B0928;
    memcpy_0((char *)v24 + 52, a4, 4 * v6);
    memset_0(v26, 0, v23);
    *a5 = v22;
    *((_QWORD *)a5 + 1) = v24;
    *((_QWORD *)a5 + 2) = v26;
    if ( a1 )
    {
      v27 = 0;
      do
      {
        v28 = 0;
        if ( v22 )
        {
          do
          {
            if ( *(_DWORD *)(*((_QWORD *)a5 + 1) + 4 * v28) == *(_DWORD *)(a2 + 16LL * v27 + 8) )
              *(_DWORD *)(*((_QWORD *)a5 + 2) + 4 * v28) = 1;
            v22 = *a5;
            v28 = (unsigned int)(v28 + 1);
          }
          while ( (unsigned int)v28 < *a5 );
        }
        ++v27;
      }
      while ( v27 < a1 );
    }
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v35);
    return 0;
  }
  else
  {
    v29 = (char *)WiaTrace_TraceLog("wiasCreatePropContext, pContext is a bad (write) pointer");
    WriteDbgTraceErrorWI("wiasCreatePropContext", v29);
    WiaTrcLib::Free((WiaTrcLib *)v29, v30);
    v31 = (void **)WiaTrace_Trace("wiasCreatePropContext, pContext is a bad (write) pointer");
    WiaTrace_ProcessTrace_Ex(v33, v32, (void *)"wiasCreatePropContext", 1, v31);
    CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v35);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18003fd80  mov     [rsp+arg_8], rdx
0x18003fd85  push    rbx
0x18003fd86  push    rbp
0x18003fd87  push    rsi
0x18003fd88  push    rdi
0x18003fd89  push    r12
0x18003fd8b  push    r13
0x18003fd8d  push    r14
0x18003fd8f  push    r15
0x18003fd91  sub     rsp, 88h
0x18003fd98  mov     r13d, ecx
0x18003fd9b  mov     ebp, r8d
0x18003fd9e  lea     rcx, aWiascreateprop_2; "::wiasCreatePropContext"
0x18003fda5  mov     r12, r9
0x18003fda8  mov     rbx, rdx
0x18003fdab  call    WiaTrace_Trace
0x18003fdb0  lea     rsi, aWiascreateprop_3; "wiasCreatePropContext"
0x18003fdb7  mov     [rsp+0C8h+var_A0], rax; struct tagWiaTraceData_Type *
0x18003fdbc  mov     r9, rsi; char *
0x18003fdbf  lea     rcx, [rsp+0C8h+var_98]; this
0x18003fdc4  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18003fdc9  test    r13d, r13d
0x18003fdcc  jz      short loc_18003FE28
0x18003fdce  test    rbx, rbx
0x18003fdd1  jnz     short loc_18003FE28
0x18003fdd3  lea     rcx, aWiascreateprop_4; "wiasCreatePropContext, pPropSpec is a b"...
0x18003fdda  call    WiaTrace_TraceLog
0x18003fddf  mov     rdx, rax; char *
0x18003fde2  mov     rcx, rsi; char *
0x18003fde5  mov     rbx, rax
0x18003fde8  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003fded  mov     rcx, rbx; this
0x18003fdf0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003fdf5  lea     rcx, aWiascreateprop_4; "wiasCreatePropContext, pPropSpec is a b"...
0x18003fdfc  call    WiaTrace_Trace
0x18003fe01  mov     r9d, 1; int
0x18003fe07  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18003fe0c  mov     r8, rsi; int
0x18003fe0f  call    WiaTrace_ProcessTrace_Ex
0x18003fe14  lea     rcx, [rsp+0C8h+var_98]; this
0x18003fe19  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18003fe1e  mov     eax, 80004003h
0x18003fe23  jmp     loc_18003FFCC
0x18003fe28  test    ebp, ebp
0x18003fe2a  jz      short loc_18003FE5C
0x18003fe2c  test    r12, r12
0x18003fe2f  jnz     short loc_18003FE5C
0x18003fe31  lea     rcx, aWiascreateprop_1; "wiasCreatePropContext, pProps is a bad "...
0x18003fe38  call    WiaTrace_TraceLog
0x18003fe3d  mov     rdx, rax; char *
0x18003fe40  mov     rcx, rsi; char *
0x18003fe43  mov     rbx, rax
0x18003fe46  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003fe4b  mov     rcx, rbx; this
0x18003fe4e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003fe53  lea     rcx, aWiascreateprop_1; "wiasCreatePropContext, pProps is a bad "...
0x18003fe5a  jmp     short loc_18003FDFC
0x18003fe5c  mov     rdi, [rsp+0C8h+arg_20]
0x18003fe64  test    rdi, rdi
0x18003fe67  jnz     short loc_18003FE97
0x18003fe69  lea     rcx, aWiascreateprop_0; "wiasCreatePropContext, pContext is a ba"...
0x18003fe70  call    WiaTrace_TraceLog
0x18003fe75  mov     rdx, rax; char *
0x18003fe78  mov     rcx, rsi; char *
0x18003fe7b  mov     rbx, rax
0x18003fe7e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003fe83  mov     rcx, rbx; this
0x18003fe86  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003fe8b  lea     rcx, aWiascreateprop_0; "wiasCreatePropContext, pContext is a ba"...
0x18003fe92  jmp     loc_18003FDFC
0x18003fe97  lea     ebx, [rbp+0Dh]
0x18003fe9a  mov     esi, ebx
0x18003fe9c  shl     rsi, 2
0x18003fea0  mov     rcx, rsi; cb
0x18003fea3  call    cs:__imp_CoTaskMemAlloc
0x18003fea9  mov     rcx, rsi; cb
0x18003feac  mov     r14, rax
0x18003feaf  call    cs:__imp_CoTaskMemAlloc
0x18003feb5  mov     r15, rax
0x18003feb8  test    r14, r14
0x18003febb  jz      loc_18003FF74
0x18003fec1  test    rax, rax
0x18003fec4  jz      loc_18003FF74
0x18003feca  movups  xmm0, cs:WIA_StdPropsInContext
0x18003fed1  mov     r8, rbp
0x18003fed4  lea     rcx, [r14+34h]; void *
0x18003fed8  shl     r8, 2; Size
0x18003fedc  mov     rdx, r12; Src
0x18003fedf  movups  xmmword ptr [r14], xmm0
0x18003fee3  movups  xmm1, cs:xmmword_1800B0908
0x18003feea  movups  xmmword ptr [r14+10h], xmm1
0x18003feef  movups  xmm0, cs:xmmword_1800B0918
0x18003fef6  movups  xmmword ptr [r14+20h], xmm0
0x18003fefb  mov     eax, cs:dword_1800B0928
0x18003ff01  mov     [r14+30h], eax
0x18003ff05  call    memcpy_0
0x18003ff0a  mov     r8, rsi; Size
0x18003ff0d  xor     edx, edx; Val
0x18003ff0f  mov     rcx, r15; void *
0x18003ff12  call    memset_0
0x18003ff17  mov     [rdi], ebx
0x18003ff19  mov     [rdi+8], r14
0x18003ff1d  mov     [rdi+10h], r15
0x18003ff21  test    r13d, r13d
0x18003ff24  jz      short loc_18003FF66
0x18003ff26  mov     r11, [rsp+0C8h+arg_8]
0x18003ff2e  xor     r8d, r8d
0x18003ff31  xor     edx, edx
0x18003ff33  test    ebx, ebx
0x18003ff35  jz      short loc_18003FF5E
0x18003ff37  mov     r9d, r8d
0x18003ff3a  add     r9, r9
0x18003ff3d  mov     rcx, [rdi+8]
0x18003ff41  mov     eax, [r11+r9*8+8]
0x18003ff46  cmp     [rcx+rdx*4], eax
0x18003ff49  jnz     short loc_18003FF56
0x18003ff4b  mov     rax, [rdi+10h]
0x18003ff4f  mov     dword ptr [rax+rdx*4], 1
0x18003ff56  mov     ebx, [rdi]
0x18003ff58  inc     edx
0x18003ff5a  cmp     edx, ebx
0x18003ff5c  jb      short loc_18003FF3D
0x18003ff5e  inc     r8d
0x18003ff61  cmp     r8d, r13d
0x18003ff64  jb      short loc_18003FF31
0x18003ff66  lea     rcx, [rsp+0C8h+var_98]; this
0x18003ff6b  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18003ff70  xor     eax, eax
0x18003ff72  jmp     short loc_18003FFCC
0x18003ff74  lea     rcx, aWiascreateprop_0; "wiasCreatePropContext, pContext is a ba"...
0x18003ff7b  call    WiaTrace_TraceLog
0x18003ff80  mov     rdx, rax; char *
0x18003ff83  lea     rcx, aWiascreateprop_3; "wiasCreatePropContext"
0x18003ff8a  mov     rbx, rax
0x18003ff8d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18003ff92  mov     rcx, rbx; this
0x18003ff95  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18003ff9a  lea     rcx, aWiascreateprop_0; "wiasCreatePropContext, pContext is a ba"...
0x18003ffa1  call    WiaTrace_Trace
0x18003ffa6  mov     r9d, 1; int
0x18003ffac  mov     [rsp+0C8h+lpMem], rax; lpMem
0x18003ffb1  lea     r8, aWiascreateprop_3; "wiasCreatePropContext"
0x18003ffb8  call    WiaTrace_ProcessTrace_Ex
0x18003ffbd  lea     rcx, [rsp+0C8h+var_98]; this
0x18003ffc2  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18003ffc7  mov     eax, 8007000Eh
0x18003ffcc  add     rsp, 88h
0x18003ffd3  pop     r15
0x18003ffd5  pop     r14
0x18003ffd7  pop     r13
0x18003ffd9  pop     r12
0x18003ffdb  pop     rdi
0x18003ffdc  pop     rsi
0x18003ffdd  pop     rbp
0x18003ffde  pop     rbx
0x18003ffdf  retn
```
