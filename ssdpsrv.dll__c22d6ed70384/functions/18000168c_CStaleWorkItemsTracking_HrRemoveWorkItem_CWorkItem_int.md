# CStaleWorkItemsTracking::HrRemoveWorkItem(CWorkItem *,int)

- ea: `0x18000168c`
- end: `0x180001792`
- name: `?HrRemoveWorkItem@CStaleWorkItemsTracking@@QEAAJPEAVCWorkItem@@H@Z`
- size: `262`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, PVOID pv, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180001530`
- `0x1800015cc`
- `0x18001de28`

## callees

- `0x18000168c`
- `0x180001798`
- `0x18001cc20`
- `0x18002c8cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000170f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000170f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800016cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800016cf`

## pseudocode

```c
__int64 __fastcall CStaleWorkItemsTracking::HrRemoveWorkItem(LPCRITICAL_SECTION lpCriticalSection, PVOID pv, int a3)
{
  int v6; // ebx
  int v7; // edx
  LPCRITICAL_SECTION v8; // rax
  bool v9; // zf
  LPCRITICAL_SECTION v10; // rcx
  LPCRITICAL_SECTION v12; // [rsp+40h] [rbp+8h] BYREF

  v6 = -2147467259;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids, pv);
  EnterCriticalSection(lpCriticalSection);
  v8 = lpCriticalSection + 1;
  v9 = lpCriticalSection[1].DebugInfo == 0;
  v12 = lpCriticalSection + 1;
  if ( !v9 )
  {
    v10 = lpCriticalSection + 1;
    do
    {
      if ( !v10 )
        break;
      v8 = (LPCRITICAL_SECTION)v8->DebugInfo;
      if ( !v8 )
        break;
      if ( *(PVOID *)&v8->LockCount == pv )
      {
        if ( a3 )
        {
          v6 = CWorkItem::HrStart(pv, v7);
          if ( v6 < 0 )
            break;
        }
        else
        {
          v6 = 0;
        }
        CUList<CWorkItem *>::Iterator::HrErase(&v12);
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids, pv);
        break;
      }
      v9 = v8->DebugInfo == 0;
      v10 = v8;
      v12 = v8;
    }
    while ( !v9 );
  }
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000168c  mov     [rsp+arg_8], rbx
0x180001691  mov     [rsp+arg_10], rbp
0x180001696  push    rsi
0x180001697  push    rdi
0x180001698  push    r15
0x18000169a  sub     rsp, 20h
0x18000169e  mov     ebp, r8d
0x1800016a1  mov     rdi, rdx
0x1800016a4  mov     rsi, rcx
0x1800016a7  mov     ebx, 80004005h
0x1800016ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016b3  lea     r15, WPP_GLOBAL_Control
0x1800016ba  cmp     rcx, r15
0x1800016bd  jz      short loc_1800016CC
0x1800016bf  test    dword ptr [rcx+1Ch], 100h
0x1800016c6  jnz     loc_180001775
0x1800016cc  mov     rcx, rsi; lpCriticalSection
0x1800016cf  call    cs:__imp_EnterCriticalSection
0x1800016d5  lea     rax, [rsi+28h]
0x1800016d9  cmp     qword ptr [rax], 0
0x1800016dd  mov     [rsp+38h+arg_0], rax
0x1800016e2  jz      short loc_18000170C
0x1800016e4  mov     rcx, rax
0x1800016e7  test    rcx, rcx
0x1800016ea  jz      short loc_18000170C
0x1800016ec  mov     rax, [rax]
0x1800016ef  test    rax, rax
0x1800016f2  jz      short loc_18000170C
0x1800016f4  cmp     [rax+8], rdi
0x1800016f8  jnz     short loc_18000172A
0x1800016fa  test    ebp, ebp
0x1800016fc  jz      short loc_18000173A
0x1800016fe  mov     rcx, rdi; pv
0x180001701  call    ?HrStart@CWorkItem@@QEAAJH@Z; CWorkItem::HrStart(int)
0x180001706  mov     ebx, eax
0x180001708  test    eax, eax
0x18000170a  jns     short loc_18000173C
0x18000170c  mov     rcx, rsi; lpCriticalSection
0x18000170f  call    cs:__imp_LeaveCriticalSection
0x180001715  mov     rbp, [rsp+38h+arg_10]
0x18000171a  mov     eax, ebx
0x18000171c  mov     rbx, [rsp+38h+arg_8]
0x180001721  add     rsp, 20h
0x180001725  pop     r15
0x180001727  pop     rdi
0x180001728  pop     rsi
0x180001729  retn
0x18000172a  cmp     qword ptr [rax], 0
0x18000172e  mov     rcx, rax
0x180001731  mov     [rsp+38h+arg_0], rax
0x180001736  jnz     short loc_1800016E7
0x180001738  jmp     short loc_18000170C
0x18000173a  xor     ebx, ebx
0x18000173c  lea     rcx, [rsp+38h+arg_0]
0x180001741  call    ?HrErase@Iterator@?$CUList@PEAVCWorkItem@@@@QEAAJXZ; CUList<CWorkItem *>::Iterator::HrErase(void)
0x180001746  mov     rcx, cs:WPP_GLOBAL_Control
0x18000174d  cmp     rcx, r15
0x180001750  jz      short loc_18000170C
0x180001752  test    dword ptr [rcx+1Ch], 100h
0x180001759  jz      short loc_18000170C
0x18000175b  mov     rcx, [rcx+10h]
0x18000175f  lea     r8, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids
0x180001766  mov     edx, 17h
0x18000176b  mov     r9, rdi
0x18000176e  call    WPP_SF_q
0x180001773  jmp     short loc_18000170C
0x180001775  mov     rcx, [rcx+10h]
0x180001779  lea     r8, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids
0x180001780  mov     edx, 16h
0x180001785  mov     r9, rdi
0x180001788  call    WPP_SF_q
0x18000178d  jmp     loc_1800016CC
```
