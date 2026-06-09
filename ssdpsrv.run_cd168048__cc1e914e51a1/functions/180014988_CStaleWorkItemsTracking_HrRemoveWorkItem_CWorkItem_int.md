# CStaleWorkItemsTracking::HrRemoveWorkItem(CWorkItem *,int)

- ea: `0x180014988`
- end: `0x180014a9b`
- name: `?HrRemoveWorkItem@CStaleWorkItemsTracking@@QEAAJPEAVCWorkItem@@H@Z`
- size: `275`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, PVOID pv, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800025f0`
- `0x1800148c4`
- `0x18001f2e0`

## callees

- `0x180014988`
- `0x180014aa4`
- `0x18001e0c4`
- `0x18002e8ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149cb`

## pseudocode

```c
__int64 __fastcall CStaleWorkItemsTracking::HrRemoveWorkItem(LPCRITICAL_SECTION lpCriticalSection, _DWORD *pv, int a3)
{
  int v6; // ebx
  LPCRITICAL_SECTION v7; // rax
  bool v8; // zf
  LPCRITICAL_SECTION v9; // rcx
  LPCRITICAL_SECTION v11; // [rsp+40h] [rbp+8h] BYREF

  v6 = -2147467259;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids);
  EnterCriticalSection(lpCriticalSection);
  v7 = lpCriticalSection + 1;
  v8 = lpCriticalSection[1].DebugInfo == 0;
  v11 = lpCriticalSection + 1;
  if ( !v8 )
  {
    v9 = lpCriticalSection + 1;
    do
    {
      if ( !v9 )
        break;
      v7 = (LPCRITICAL_SECTION)v7->DebugInfo;
      if ( !v7 )
        break;
      if ( *(_DWORD **)&v7->LockCount == pv )
      {
        if ( a3 )
        {
          v6 = CWorkItem::HrStart(pv);
          if ( v6 < 0 )
            break;
        }
        else
        {
          v6 = 0;
        }
        CUList<CWorkItem *>::Iterator::HrErase(&v11);
        if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids);
        break;
      }
      v8 = v7->DebugInfo == 0;
      v9 = v7;
      v11 = v7;
    }
    while ( !v8 );
  }
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180014988  mov     [rsp+arg_8], rbx
0x18001498d  mov     [rsp+arg_10], rbp
0x180014992  push    rsi
0x180014993  push    rdi
0x180014994  push    r15
0x180014996  sub     rsp, 20h
0x18001499a  mov     ebp, r8d
0x18001499d  mov     rdi, rdx
0x1800149a0  mov     rsi, rcx
0x1800149a3  mov     ebx, 80004005h
0x1800149a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149af  lea     r15, WPP_GLOBAL_Control
0x1800149b6  cmp     rcx, r15
0x1800149b9  jz      short loc_1800149C8
0x1800149bb  test    dword ptr [rcx+1Ch], 100h
0x1800149c2  jnz     loc_180014A7E
0x1800149c8  mov     rcx, rsi; lpCriticalSection
0x1800149cb  call    cs:__imp_EnterCriticalSection
0x1800149d2  nop     dword ptr [rax+rax+00h]
0x1800149d7  lea     rax, [rsi+28h]
0x1800149db  cmp     qword ptr [rax], 0
0x1800149df  mov     [rsp+38h+arg_0], rax
0x1800149e4  jz      short loc_180014A0E
0x1800149e6  mov     rcx, rax
0x1800149e9  test    rcx, rcx
0x1800149ec  jz      short loc_180014A0E
0x1800149ee  mov     rax, [rax]
0x1800149f1  test    rax, rax
0x1800149f4  jz      short loc_180014A0E
0x1800149f6  cmp     [rax+8], rdi
0x1800149fa  jnz     short loc_180014A33
0x1800149fc  test    ebp, ebp
0x1800149fe  jz      short loc_180014A43
0x180014a00  mov     rcx, rdi; pv
0x180014a03  call    ?HrStart@CWorkItem@@QEAAJH@Z; CWorkItem::HrStart(int)
0x180014a08  mov     ebx, eax
0x180014a0a  test    eax, eax
0x180014a0c  jns     short loc_180014A45
0x180014a0e  mov     rcx, rsi; lpCriticalSection
0x180014a11  call    cs:__imp_LeaveCriticalSection
0x180014a18  nop     dword ptr [rax+rax+00h]
0x180014a1d  mov     rbp, [rsp+38h+arg_10]
0x180014a22  mov     eax, ebx
0x180014a24  mov     rbx, [rsp+38h+arg_8]
0x180014a29  add     rsp, 20h
0x180014a2d  pop     r15
0x180014a2f  pop     rdi
0x180014a30  pop     rsi
0x180014a31  retn
0x180014a33  cmp     qword ptr [rax], 0
0x180014a37  mov     rcx, rax
0x180014a3a  mov     [rsp+38h+arg_0], rax
0x180014a3f  jnz     short loc_1800149E9
0x180014a41  jmp     short loc_180014A0E
0x180014a43  xor     ebx, ebx
0x180014a45  lea     rcx, [rsp+38h+arg_0]
0x180014a4a  call    ?HrErase@Iterator@?$CUList@PEAVCWorkItem@@@@QEAAJXZ; CUList<CWorkItem *>::Iterator::HrErase(void)
0x180014a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a56  cmp     rcx, r15
0x180014a59  jz      short loc_180014A0E
0x180014a5b  test    dword ptr [rcx+1Ch], 100h
0x180014a62  jz      short loc_180014A0E
0x180014a64  mov     rcx, [rcx+10h]
0x180014a68  lea     r8, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids
0x180014a6f  mov     edx, 17h
0x180014a74  mov     r9, rdi
0x180014a77  call    WPP_SF_q
0x180014a7c  jmp     short loc_180014A0E
0x180014a7e  mov     rcx, [rcx+10h]
0x180014a82  lea     r8, WPP_d99cd052381a3366086b95fac24ae15e_Traceguids
0x180014a89  mov     edx, 16h
0x180014a8e  mov     r9, rdi
0x180014a91  call    WPP_SF_q
0x180014a96  jmp     loc_1800149C8
```
