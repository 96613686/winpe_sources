# CSsdpServiceManager::HrRemoveServiceInternal(CSsdpService *,int,int,int)

- ea: `0x18002021c`
- end: `0x1800203aa`
- name: `?HrRemoveServiceInternal@CSsdpServiceManager@@AEAAJPEAVCSsdpService@@HHH@Z`
- size: `398`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, void **, int, int, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800201c0`
- `0x18002d870`
- `0x18002fc10`

## callees

- `0x18001587c`
- `0x1800186a0`
- `0x180019bac`
- `0x18002021c`
- `0x180022a80`
- `0x1800255a8`
- `0x18002faf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800202ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800202ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020247`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020247`

## pseudocode

```c
__int64 __fastcall CSsdpServiceManager::HrRemoveServiceInternal(
        LPCRITICAL_SECTION lpCriticalSection,
        void **a2,
        int a3,
        int a4,
        int a5)
{
  unsigned int v5; // edi
  LPCRITICAL_SECTION v10; // r10
  int v11; // r8d
  void **v12; // rdx
  void **v13; // rcx
  int v14; // ebx
  void **v15; // rdx
  CSsdpService *v17; // [rsp+20h] [rbp-10h] BYREF
  void **v18; // [rsp+28h] [rbp-8h] BYREF
  void *v19; // [rsp+60h] [rbp+30h] BYREF

  v5 = 0;
  v19 = 0;
  EnterCriticalSection(lpCriticalSection);
  v10 = lpCriticalSection + 1;
  v11 = 1;
  if ( a5 )
  {
    v12 = (void **)v19;
    if ( v19 )
    {
      do
      {
        v13 = v12;
        v12 = (void **)*v12;
      }
      while ( v12 );
    }
    else
    {
      v13 = &v19;
    }
    *v13 = v10->DebugInfo;
    v10->DebugInfo = 0;
LABEL_18:
    v14 = v11;
  }
  else
  {
    v14 = 0;
    v17 = (CSsdpService *)&lpCriticalSection[1];
    if ( v10->DebugInfo )
    {
      v18 = 0;
      while ( !(unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem((__int64 **)&v17, &v18) )
      {
        if ( v18 == a2 )
        {
          if ( a4 && ((unsigned __int8)v11 & (_BYTE)a2[33]) != 0 )
            break;
          if ( v17 )
          {
            v15 = *(void ***)v17;
            if ( *(_QWORD *)v17 )
            {
              *(_QWORD *)v17 = *v15;
              *v15 = v19;
              v19 = v15;
            }
          }
          goto LABEL_18;
        }
        if ( (unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&v17) )
          break;
      }
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( v14 )
  {
    v18 = &v19;
    if ( v19 )
    {
      v17 = 0;
      do
      {
        if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem((__int64 **)&v18, &v17) )
          break;
        if ( !a4 )
          CSsdpRundownSupport::RemoveRundownItem(&CSsdpRundownSupport::s_instance, v17);
        v5 = CSsdpService::HrCleanup(v17, a3);
      }
      while ( !(unsigned int)CUList<__int64>::Iterator::HrNext((_QWORD ***)&v18) );
      if ( v5 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids, v5);
    }
  }
  if ( v19 )
    CUList<CSsdpService>::Node::`scalar deleting destructor'((_QWORD **)v19);
  return v5;
}

```

## disassembly

```asm
0x18002021c  mov     [rsp-28h+arg_8], rbx
0x180020221  mov     [rsp-28h+arg_10], rsi
0x180020226  push    rbp
0x180020227  push    rdi
0x180020228  push    r12
0x18002022a  push    r14
0x18002022c  push    r15
0x18002022e  mov     rbp, rsp
0x180020231  sub     rsp, 30h
0x180020235  xor     edi, edi
0x180020237  mov     r15d, r9d
0x18002023a  mov     [rbp+arg_0], rdi
0x18002023e  mov     r12d, r8d
0x180020241  mov     rsi, rdx
0x180020244  mov     r14, rcx
0x180020247  call    cs:__imp_EnterCriticalSection
0x18002024d  lea     r10, [r14+28h]
0x180020251  lea     r8d, [rdi+1]
0x180020255  cmp     [rbp+arg_20], edi
0x180020258  jz      short loc_180020282
0x18002025a  mov     rdx, [rbp+arg_0]
0x18002025e  test    rdx, rdx
0x180020261  jz      short loc_180020273
0x180020263  mov     rax, [rdx]
0x180020266  mov     rcx, rdx
0x180020269  mov     rdx, rax
0x18002026c  test    rax, rax
0x18002026f  jnz     short loc_180020263
0x180020271  jmp     short loc_180020277
0x180020273  lea     rcx, [rbp+arg_0]
0x180020277  mov     rax, [r10]
0x18002027a  mov     [rcx], rax
0x18002027d  mov     [r10], rdi
0x180020280  jmp     short loc_1800202E7
0x180020282  xor     ebx, ebx
0x180020284  mov     [rbp+var_10], r10
0x180020288  cmp     [r10], rbx
0x18002028b  jz      short loc_1800202EA
0x18002028d  mov     [rbp+var_8], rbx
0x180020291  lea     rdx, [rbp+var_8]
0x180020295  lea     rcx, [rbp+var_10]
0x180020299  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x18002029e  test    eax, eax
0x1800202a0  jnz     short loc_1800202EA
0x1800202a2  cmp     [rbp+var_8], rsi
0x1800202a6  jz      short loc_1800202B7
0x1800202a8  lea     rcx, [rbp+var_10]
0x1800202ac  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x1800202b1  test    eax, eax
0x1800202b3  jz      short loc_180020291
0x1800202b5  jmp     short loc_1800202EA
0x1800202b7  test    r15d, r15d
0x1800202ba  jz      short loc_1800202C5
0x1800202bc  test    [rsi+108h], r8b
0x1800202c3  jnz     short loc_1800202EA
0x1800202c5  mov     rax, [rbp+var_10]
0x1800202c9  test    rax, rax
0x1800202cc  jz      short loc_1800202E7
0x1800202ce  mov     rdx, [rax]
0x1800202d1  test    rdx, rdx
0x1800202d4  jz      short loc_1800202E7
0x1800202d6  mov     rcx, [rdx]
0x1800202d9  mov     [rax], rcx
0x1800202dc  mov     rax, [rbp+arg_0]
0x1800202e0  mov     [rdx], rax
0x1800202e3  mov     [rbp+arg_0], rdx
0x1800202e7  mov     ebx, r8d
0x1800202ea  mov     rcx, r14; lpCriticalSection
0x1800202ed  call    cs:__imp_LeaveCriticalSection
0x1800202f3  test    ebx, ebx
0x1800202f5  jz      loc_180020383
0x1800202fb  lea     rax, [rbp+arg_0]
0x1800202ff  mov     [rbp+var_8], rax
0x180020303  cmp     [rbp+arg_0], rdi
0x180020307  jz      short loc_180020383
0x180020309  mov     [rbp+var_10], rdi
0x18002030d  lea     rdx, [rbp+var_10]
0x180020311  lea     rcx, [rbp+var_8]
0x180020315  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x18002031a  test    eax, eax
0x18002031c  jnz     short loc_18002034E
0x18002031e  test    r15d, r15d
0x180020321  jnz     short loc_180020333
0x180020323  mov     rdx, [rbp+var_10]; void *
0x180020327  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x18002032e  call    ?RemoveRundownItem@CSsdpRundownSupport@@QEAAXPEAX@Z; CSsdpRundownSupport::RemoveRundownItem(void *)
0x180020333  mov     rcx, [rbp+var_10]; this
0x180020337  mov     edx, r12d; int
0x18002033a  call    ?HrCleanup@CSsdpService@@QEAAJH@Z; CSsdpService::HrCleanup(int)
0x18002033f  lea     rcx, [rbp+var_8]
0x180020343  mov     edi, eax
0x180020345  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x18002034a  test    eax, eax
0x18002034c  jz      short loc_18002030D
0x18002034e  test    edi, edi
0x180020350  jz      short loc_180020383
0x180020352  mov     rcx, cs:WPP_GLOBAL_Control
0x180020359  lea     rax, WPP_GLOBAL_Control
0x180020360  cmp     rcx, rax
0x180020363  jz      short loc_180020383
0x180020365  test    byte ptr [rcx+1Ch], 1
0x180020369  jz      short loc_180020383
0x18002036b  mov     rcx, [rcx+10h]
0x18002036f  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180020376  mov     edx, 23h ; '#'
0x18002037b  mov     r9d, edi
0x18002037e  call    WPP_SF_d
0x180020383  mov     rcx, [rbp+arg_0]; void *
0x180020387  test    rcx, rcx
0x18002038a  jz      short loc_180020391
0x18002038c  call    ??_GNode@?$CUList@VCSsdpService@@@@QEAAPEAXI@Z; CUList<CSsdpService>::Node::`scalar deleting destructor'(uint)
0x180020391  mov     rbx, [rsp+30h+arg_8]
0x180020396  mov     eax, edi
0x180020398  mov     rsi, [rsp+30h+arg_10]
0x18002039d  add     rsp, 30h
0x1800203a1  pop     r15
0x1800203a3  pop     r14
0x1800203a5  pop     r12
0x1800203a7  pop     rdi
0x1800203a8  pop     rbp
0x1800203a9  retn
```
