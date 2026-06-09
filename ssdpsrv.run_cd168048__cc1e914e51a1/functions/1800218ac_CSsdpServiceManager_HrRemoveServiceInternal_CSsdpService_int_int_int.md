# CSsdpServiceManager::HrRemoveServiceInternal(CSsdpService *,int,int,int)

- ea: `0x1800218ac`
- end: `0x180021a47`
- name: `?HrRemoveServiceInternal@CSsdpServiceManager@@AEAAJPEAVCSsdpService@@HHH@Z`
- size: `411`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, struct CSsdpService *@<rdx>, int@<r8d>, int@<r9d>, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180021850`
- `0x18002f900`
- `0x180031f10`

## callees

- `0x180017ec0`
- `0x180019920`
- `0x18001aeb4`
- `0x1800218ac`
- `0x180024490`
- `0x1800271fc`
- `0x180031df8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021983`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021983`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800218d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800218d7`

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
      while ( !(unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&v17, &v18) )
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
        if ( (unsigned int)CUList<__int64>::Iterator::HrNext(&v17) )
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
        if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&v18, &v17) )
          break;
        if ( !a4 )
          CSsdpRundownSupport::RemoveRundownItem(&CSsdpRundownSupport::s_instance, v17);
        v5 = CSsdpService::HrCleanup(v17, a3);
      }
      while ( !(unsigned int)CUList<__int64>::Iterator::HrNext(&v18) );
      if ( v5 && WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids, v5);
    }
  }
  if ( v19 )
    CUList<CSsdpService>::Node::`scalar deleting destructor'(v19);
  return v5;
}

```

## disassembly

```asm
0x1800218ac  mov     [rsp-28h+arg_8], rbx
0x1800218b1  mov     [rsp-28h+arg_10], rsi
0x1800218b6  push    rbp
0x1800218b7  push    rdi
0x1800218b8  push    r12
0x1800218ba  push    r14
0x1800218bc  push    r15
0x1800218be  mov     rbp, rsp
0x1800218c1  sub     rsp, 30h
0x1800218c5  xor     edi, edi
0x1800218c7  mov     r15d, r9d
0x1800218ca  mov     [rbp+arg_0], rdi
0x1800218ce  mov     r12d, r8d
0x1800218d1  mov     rsi, rdx
0x1800218d4  mov     r14, rcx
0x1800218d7  call    cs:__imp_EnterCriticalSection
0x1800218de  nop     dword ptr [rax+rax+00h]
0x1800218e3  lea     r10, [r14+28h]
0x1800218e7  lea     r8d, [rdi+1]
0x1800218eb  cmp     [rbp+arg_20], edi
0x1800218ee  jz      short loc_180021918
0x1800218f0  mov     rdx, [rbp+arg_0]
0x1800218f4  test    rdx, rdx
0x1800218f7  jz      short loc_180021909
0x1800218f9  mov     rax, [rdx]
0x1800218fc  mov     rcx, rdx
0x1800218ff  mov     rdx, rax
0x180021902  test    rax, rax
0x180021905  jnz     short loc_1800218F9
0x180021907  jmp     short loc_18002190D
0x180021909  lea     rcx, [rbp+arg_0]
0x18002190d  mov     rax, [r10]
0x180021910  mov     [rcx], rax
0x180021913  mov     [r10], rdi
0x180021916  jmp     short loc_18002197D
0x180021918  xor     ebx, ebx
0x18002191a  mov     [rbp+var_10], r10
0x18002191e  cmp     [r10], rbx
0x180021921  jz      short loc_180021980
0x180021923  mov     [rbp+var_8], rbx
0x180021927  lea     rdx, [rbp+var_8]
0x18002192b  lea     rcx, [rbp+var_10]
0x18002192f  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x180021934  test    eax, eax
0x180021936  jnz     short loc_180021980
0x180021938  cmp     [rbp+var_8], rsi
0x18002193c  jz      short loc_18002194D
0x18002193e  lea     rcx, [rbp+var_10]
0x180021942  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x180021947  test    eax, eax
0x180021949  jz      short loc_180021927
0x18002194b  jmp     short loc_180021980
0x18002194d  test    r15d, r15d
0x180021950  jz      short loc_18002195B
0x180021952  test    [rsi+108h], r8b
0x180021959  jnz     short loc_180021980
0x18002195b  mov     rax, [rbp+var_10]
0x18002195f  test    rax, rax
0x180021962  jz      short loc_18002197D
0x180021964  mov     rdx, [rax]
0x180021967  test    rdx, rdx
0x18002196a  jz      short loc_18002197D
0x18002196c  mov     rcx, [rdx]
0x18002196f  mov     [rax], rcx
0x180021972  mov     rax, [rbp+arg_0]
0x180021976  mov     [rdx], rax
0x180021979  mov     [rbp+arg_0], rdx
0x18002197d  mov     ebx, r8d
0x180021980  mov     rcx, r14; lpCriticalSection
0x180021983  call    cs:__imp_LeaveCriticalSection
0x18002198a  nop     dword ptr [rax+rax+00h]
0x18002198f  test    ebx, ebx
0x180021991  jz      loc_180021A1F
0x180021997  lea     rax, [rbp+arg_0]
0x18002199b  mov     [rbp+var_8], rax
0x18002199f  cmp     [rbp+arg_0], rdi
0x1800219a3  jz      short loc_180021A1F
0x1800219a5  mov     [rbp+var_10], rdi
0x1800219a9  lea     rdx, [rbp+var_10]
0x1800219ad  lea     rcx, [rbp+var_8]
0x1800219b1  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x1800219b6  test    eax, eax
0x1800219b8  jnz     short loc_1800219EA
0x1800219ba  test    r15d, r15d
0x1800219bd  jnz     short loc_1800219CF
0x1800219bf  mov     rdx, [rbp+var_10]; void *
0x1800219c3  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x1800219ca  call    ?RemoveRundownItem@CSsdpRundownSupport@@QEAAXPEAX@Z; CSsdpRundownSupport::RemoveRundownItem(void *)
0x1800219cf  mov     rcx, [rbp+var_10]; this
0x1800219d3  mov     edx, r12d; int
0x1800219d6  call    ?HrCleanup@CSsdpService@@QEAAJH@Z; CSsdpService::HrCleanup(int)
0x1800219db  lea     rcx, [rbp+var_8]
0x1800219df  mov     edi, eax
0x1800219e1  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x1800219e6  test    eax, eax
0x1800219e8  jz      short loc_1800219A9
0x1800219ea  test    edi, edi
0x1800219ec  jz      short loc_180021A1F
0x1800219ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219f5  lea     rax, WPP_GLOBAL_Control
0x1800219fc  cmp     rcx, rax
0x1800219ff  jz      short loc_180021A1F
0x180021a01  test    byte ptr [rcx+1Ch], 1
0x180021a05  jz      short loc_180021A1F
0x180021a07  mov     rcx, [rcx+10h]
0x180021a0b  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180021a12  mov     edx, 23h ; '#'
0x180021a17  mov     r9d, edi
0x180021a1a  call    WPP_SF_d
0x180021a1f  mov     rcx, [rbp+arg_0]; void *
0x180021a23  test    rcx, rcx
0x180021a26  jz      short loc_180021A2D
0x180021a28  call    ??_GNode@?$CUList@VCSsdpService@@@@QEAAPEAXI@Z; CUList<CSsdpService>::Node::`scalar deleting destructor'(uint)
0x180021a2d  mov     rbx, [rsp+30h+arg_8]
0x180021a32  mov     eax, edi
0x180021a34  mov     rsi, [rsp+30h+arg_10]
0x180021a39  add     rsp, 30h
0x180021a3d  pop     r15
0x180021a3f  pop     r14
0x180021a41  pop     r12
0x180021a43  pop     rdi
0x180021a44  pop     rbp
0x180021a45  retn
```
