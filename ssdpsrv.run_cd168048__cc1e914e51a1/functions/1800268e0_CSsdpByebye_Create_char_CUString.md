# CSsdpByebye::Create(char *,CUString &)

- ea: `0x1800268e0`
- end: `0x1800269e8`
- name: `?Create@CSsdpByebye@@SAJPEADAEAVCUString@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(char *, struct CUString *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180017ec0`
- `0x180032068`

## callees

- `0x1800148c4`
- `0x180018ec4`
- `0x180022980`
- `0x1800268e0`
- `0x1800271fc`
- `0x180027bc4`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026998`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026998`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800268fa`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800268fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026967`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026967`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026937`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026937`

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
0x1800268e0  mov     [rsp+arg_0], rbx
0x1800268e5  mov     [rsp+arg_8], rsi
0x1800268ea  push    rdi
0x1800268eb  sub     rsp, 20h
0x1800268ef  mov     rsi, rcx
0x1800268f2  mov     rbx, rdx
0x1800268f5  mov     ecx, 0B0h; Size
0x1800268fa  call    cs:__imp_malloc
0x180026901  nop     dword ptr [rax+rax+00h]
0x180026906  test    rax, rax
0x180026909  jz      loc_180026990
0x18002690f  mov     rdx, rsi; char *
0x180026912  mov     rcx, rax; this
0x180026915  call    ??0CSsdpByebye@@QEAA@PEAD@Z; CSsdpByebye::CSsdpByebye(char *)
0x18002691a  mov     rdi, rax
0x18002691d  test    rax, rax
0x180026920  jz      short loc_180026990
0x180026922  mov     rdx, rbx; struct CUString *
0x180026925  mov     rcx, rax; this
0x180026928  call    ?AssignUSN@CSsdpByebye@@QEAAXAEAVCUString@@@Z; CSsdpByebye::AssignUSN(CUString &)
0x18002692d  lea     rsi, [rdi+80h]
0x180026934  mov     rcx, rsi; lpCriticalSection
0x180026937  call    cs:__imp_EnterCriticalSection
0x18002693e  nop     dword ptr [rax+rax+00h]
0x180026943  mov     rdx, rdi; struct CWorkItem *
0x180026946  lea     rcx, ?s_WorkItemTracking@CSsdpByebye@@2VCStaleWorkItemsTracking@@A; lpCriticalSection
0x18002694d  call    ?HrAddWorkItem@CStaleWorkItemsTracking@@QEAAJPEAVCWorkItem@@@Z; CStaleWorkItemsTracking::HrAddWorkItem(CWorkItem *)
0x180026952  mov     ebx, eax
0x180026954  test    eax, eax
0x180026956  js      short loc_180026964
0x180026958  xor     edx, edx; int
0x18002695a  mov     rcx, rdi; this
0x18002695d  call    ?SendByeBye@CSsdpByebye@@AEAAJH@Z; CSsdpByebye::SendByeBye(int)
0x180026962  mov     ebx, eax
0x180026964  mov     rcx, rsi; lpCriticalSection
0x180026967  call    cs:__imp_LeaveCriticalSection
0x18002696e  nop     dword ptr [rax+rax+00h]
0x180026973  test    ebx, ebx
0x180026975  jns     short loc_18002698C
0x180026977  mov     rax, [rdi]
0x18002697a  mov     edx, 1
0x18002697f  mov     rcx, rdi
0x180026982  mov     rax, [rax]
0x180026985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002698a  jmp     short loc_1800269A4
0x18002698c  jnz     short loc_1800269A4
0x18002698e  jmp     short loc_1800269D5
0x180026990  mov     rcx, rsi; Block
0x180026993  mov     ebx, 8007000Eh
0x180026998  call    cs:__imp_free
0x18002699f  nop     dword ptr [rax+rax+00h]
0x1800269a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269ab  lea     rax, WPP_GLOBAL_Control
0x1800269b2  cmp     rcx, rax
0x1800269b5  jz      short loc_1800269D5
0x1800269b7  test    byte ptr [rcx+1Ch], 1
0x1800269bb  jz      short loc_1800269D5
0x1800269bd  mov     rcx, [rcx+10h]
0x1800269c1  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x1800269c8  mov     edx, 16h
0x1800269cd  mov     r9d, ebx
0x1800269d0  call    WPP_SF_d
0x1800269d5  mov     rsi, [rsp+28h+arg_8]
0x1800269da  mov     eax, ebx
0x1800269dc  mov     rbx, [rsp+28h+arg_0]
0x1800269e1  add     rsp, 20h
0x1800269e5  pop     rdi
0x1800269e6  retn
```
