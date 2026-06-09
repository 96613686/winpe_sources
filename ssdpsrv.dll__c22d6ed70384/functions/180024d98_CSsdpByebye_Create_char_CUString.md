# CSsdpByebye::Create(char *,CUString &)

- ea: `0x180024d98`
- end: `0x180024e83`
- name: `?Create@CSsdpByebye@@SAJPEADAEAVCUString@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(char *, struct CUString *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18001587c`
- `0x18002fd54`

## callees

- `0x1800015cc`
- `0x180016a90`
- `0x1800211d8`
- `0x180024d98`
- `0x1800255a8`
- `0x180025e50`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024e3a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024e3a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180024db2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180024db2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024e0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024e0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024de5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024de5`

## pseudocode

```c
__int64 __fastcall CSsdpByebye::Create(char *a1, struct CUString *a2)
{
  CSsdpByebye *v4; // rax
  CSsdpByebye *v5; // rax
  CSsdpByebye *v6; // rdi
  int v7; // ebx

  v4 = (CSsdpByebye *)malloc(0xB0u);
  if ( v4 && (v5 = CSsdpByebye::CSsdpByebye(v4, a1), (v6 = v5) != 0) )
  {
    CSsdpByebye::AssignUSN(v5, a2);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 128));
    v7 = CStaleWorkItemsTracking::HrAddWorkItem(&CSsdpByebye::s_WorkItemTracking, v6);
    if ( v7 >= 0 )
      v7 = CSsdpByebye::SendByeBye(v6, 0);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 128));
    if ( v7 >= 0 )
    {
      if ( !v7 )
        return (unsigned int)v7;
    }
    else
    {
      (**(void (__fastcall ***)(CSsdpByebye *, __int64))v6)(v6, 1);
    }
  }
  else
  {
    v7 = -2147024882;
    free(a1);
  }
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180024d98  mov     [rsp+arg_0], rbx
0x180024d9d  mov     [rsp+arg_8], rsi
0x180024da2  push    rdi
0x180024da3  sub     rsp, 20h
0x180024da7  mov     rsi, rcx
0x180024daa  mov     rbx, rdx
0x180024dad  mov     ecx, 0B0h; Size
0x180024db2  call    cs:__imp_malloc
0x180024db8  test    rax, rax
0x180024dbb  jz      short loc_180024E32
0x180024dbd  mov     rdx, rsi; char *
0x180024dc0  mov     rcx, rax; this
0x180024dc3  call    ??0CSsdpByebye@@QEAA@PEAD@Z; CSsdpByebye::CSsdpByebye(char *)
0x180024dc8  mov     rdi, rax
0x180024dcb  test    rax, rax
0x180024dce  jz      short loc_180024E32
0x180024dd0  mov     rdx, rbx; struct CUString *
0x180024dd3  mov     rcx, rax; this
0x180024dd6  call    ?AssignUSN@CSsdpByebye@@QEAAXAEAVCUString@@@Z; CSsdpByebye::AssignUSN(CUString &)
0x180024ddb  lea     rsi, [rdi+80h]
0x180024de2  mov     rcx, rsi; lpCriticalSection
0x180024de5  call    cs:__imp_EnterCriticalSection
0x180024deb  mov     rdx, rdi; struct CWorkItem *
0x180024dee  lea     rcx, ?s_WorkItemTracking@CSsdpByebye@@2VCStaleWorkItemsTracking@@A; lpCriticalSection
0x180024df5  call    ?HrAddWorkItem@CStaleWorkItemsTracking@@QEAAJPEAVCWorkItem@@@Z; CStaleWorkItemsTracking::HrAddWorkItem(CWorkItem *)
0x180024dfa  mov     ebx, eax
0x180024dfc  test    eax, eax
0x180024dfe  js      short loc_180024E0C
0x180024e00  xor     edx, edx; int
0x180024e02  mov     rcx, rdi; this
0x180024e05  call    ?SendByeBye@CSsdpByebye@@AEAAJH@Z; CSsdpByebye::SendByeBye(int)
0x180024e0a  mov     ebx, eax
0x180024e0c  mov     rcx, rsi; lpCriticalSection
0x180024e0f  call    cs:__imp_LeaveCriticalSection
0x180024e15  test    ebx, ebx
0x180024e17  jns     short loc_180024E2E
0x180024e19  mov     rax, [rdi]
0x180024e1c  mov     edx, 1
0x180024e21  mov     rcx, rdi
0x180024e24  mov     rax, [rax]
0x180024e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e2c  jmp     short loc_180024E40
0x180024e2e  jnz     short loc_180024E40
0x180024e30  jmp     short loc_180024E71
0x180024e32  mov     rcx, rsi; Block
0x180024e35  mov     ebx, 8007000Eh
0x180024e3a  call    cs:__imp_free
0x180024e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e47  lea     rax, WPP_GLOBAL_Control
0x180024e4e  cmp     rcx, rax
0x180024e51  jz      short loc_180024E71
0x180024e53  test    byte ptr [rcx+1Ch], 1
0x180024e57  jz      short loc_180024E71
0x180024e59  mov     rcx, [rcx+10h]
0x180024e5d  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180024e64  mov     edx, 16h
0x180024e69  mov     r9d, ebx
0x180024e6c  call    WPP_SF_d
0x180024e71  mov     rsi, [rsp+28h+arg_8]
0x180024e76  mov     eax, ebx
0x180024e78  mov     rbx, [rsp+28h+arg_0]
0x180024e7d  add     rsp, 20h
0x180024e81  pop     rdi
0x180024e82  retn
```
