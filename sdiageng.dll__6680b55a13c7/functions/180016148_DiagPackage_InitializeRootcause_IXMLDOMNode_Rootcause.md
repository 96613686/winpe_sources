# DiagPackage::InitializeRootcause(IXMLDOMNode *,Rootcause *)

- ea: `0x180016148`
- end: `0x180016222`
- name: `?InitializeRootcause@DiagPackage@@AEAAJPEAUIXMLDOMNode@@PEAVRootcause@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(DiagPackage *this, struct IXMLDOMNode *, struct Rootcause *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016228`

## callees

- `0x180016148`
- `0x18001a530`
- `0x180026fa0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800161af`
- `KERNEL32!HeapAlloc` at `0x1800161af`
- `KERNEL32!GetProcessHeap` at `0x1800161a0`
- `KERNEL32!GetProcessHeap` at `0x1800161a0`

## pseudocode

```c
__int64 __fastcall DiagPackage::InitializeRootcause(DiagPackage *this, struct IXMLDOMNode *a2, struct Rootcause *a3)
{
  int v5; // r9d
  int v6; // r8d
  int v7; // ebx
  __int64 v8; // rax
  HANDLE ProcessHeap; // rax
  _QWORD *v10; // rax
  int v11; // r8d

  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 1543;
    v7 = -2147024809;
LABEL_13:
    SdpDebugTrace(1u, L"DiagPackage::InitializeRootcause", v6, v5);
    return (unsigned int)v7;
  }
  if ( !a3 )
  {
    v5 = -2147024809;
    v6 = 1544;
    v7 = -2147024809;
    goto LABEL_13;
  }
  v8 = *((_QWORD *)this + 1);
  if ( !v8 )
  {
    v7 = -2147467261;
    v6 = 1546;
LABEL_12:
    v5 = v7;
    goto LABEL_13;
  }
  *(_QWORD *)a3 = v8;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 0, 0x10u);
  *((_QWORD *)a3 + 15) = v10;
  if ( !v10 )
  {
    v7 = -2147024882;
    v11 = 97;
LABEL_11:
    SdpDebugTrace(1u, L"Rootcause::Initialize", v11, v7);
    v6 = 1549;
    goto LABEL_12;
  }
  v10[1] = v10;
  *v10 = v10;
  v7 = Rootcause::ParseRootcauseXml(a3, a2);
  if ( v7 < 0 )
  {
    v11 = 102;
    goto LABEL_11;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180016148  mov     [rsp+arg_0], rbx
0x18001614d  push    rdi
0x18001614e  sub     rsp, 20h
0x180016152  mov     rbx, r8
0x180016155  mov     rdi, rdx
0x180016158  test    rdx, rdx
0x18001615b  jnz     short loc_180016171
0x18001615d  mov     r9d, 80070057h
0x180016163  mov     r8d, 607h
0x180016169  mov     ebx, r9d
0x18001616c  jmp     loc_180016204
0x180016171  test    rbx, rbx
0x180016174  jnz     short loc_180016187
0x180016176  mov     r9d, 80070057h
0x18001617c  mov     r8d, 608h
0x180016182  mov     ebx, r9d
0x180016185  jmp     short loc_180016204
0x180016187  mov     rax, [rcx+8]
0x18001618b  test    rax, rax
0x18001618e  jnz     short loc_18001619D
0x180016190  mov     ebx, 80004003h
0x180016195  mov     r8d, 60Ah
0x18001619b  jmp     short loc_180016201
0x18001619d  mov     [r8], rax
0x1800161a0  call    cs:__imp_GetProcessHeap
0x1800161a6  xor     edx, edx; dwFlags
0x1800161a8  mov     rcx, rax; hHeap
0x1800161ab  lea     r8d, [rdx+10h]; dwBytes
0x1800161af  call    cs:__imp_HeapAlloc
0x1800161b5  mov     [rbx+78h], rax
0x1800161b9  test    rax, rax
0x1800161bc  jnz     short loc_1800161C9
0x1800161be  mov     ebx, 8007000Eh
0x1800161c3  lea     r8d, [rax+61h]
0x1800161c7  jmp     short loc_1800161E7
0x1800161c9  mov     rdx, rdi; struct IXMLDOMNode *
0x1800161cc  mov     [rax+8], rax
0x1800161d0  mov     rcx, rbx; this
0x1800161d3  mov     [rax], rax
0x1800161d6  call    ?ParseRootcauseXml@Rootcause@@AEAAJPEAUIXMLDOMNode@@@Z; Rootcause::ParseRootcauseXml(IXMLDOMNode *)
0x1800161db  mov     ebx, eax
0x1800161dd  test    eax, eax
0x1800161df  jns     short loc_180016215
0x1800161e1  mov     r8d, 66h ; 'f'; int
0x1800161e7  mov     r9d, ebx; int
0x1800161ea  lea     rdx, aRootcauseIniti_2; "Rootcause::Initialize"
0x1800161f1  mov     ecx, 1; Level
0x1800161f6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800161fb  mov     r8d, 60Dh; int
0x180016201  mov     r9d, ebx; int
0x180016204  lea     rdx, aDiagpackageIni_0; "DiagPackage::InitializeRootcause"
0x18001620b  mov     ecx, 1; Level
0x180016210  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180016215  mov     eax, ebx
0x180016217  mov     rbx, [rsp+28h+arg_0]
0x18001621c  add     rsp, 20h
0x180016220  pop     rdi
0x180016221  retn
```
