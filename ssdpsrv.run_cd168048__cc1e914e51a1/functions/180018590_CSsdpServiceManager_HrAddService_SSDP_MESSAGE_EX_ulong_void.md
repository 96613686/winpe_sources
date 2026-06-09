# CSsdpServiceManager::HrAddService(_SSDP_MESSAGE_EX *,ulong,void * *)

- ea: `0x180018590`
- end: `0x180018769`
- name: `?HrAddService@CSsdpServiceManager@@QEAAJPEAU_SSDP_MESSAGE_EX@@KPEAPEAX@Z`
- size: `473`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct _SSDP_MESSAGE_EX *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180020320`

## callees

- `0x1800177a0`
- `0x180018590`
- `0x180018804`
- `0x18001ce28`
- `0x18001fbc4`
- `0x180026dd0`
- `0x1800271fc`
- `0x180029df0`
- `0x180031df8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800186da`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800186da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018749`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018749`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800185ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800185ea`

## pseudocode

```c
__int64 __fastcall CSsdpServiceManager::HrAddService(
        LPCRITICAL_SECTION lpCriticalSection,
        char **a2,
        int a3,
        void **a4)
{
  int started; // ebx
  LPCSTR v9; // rcx
  bool v10; // zf
  char *v11; // rsi
  int v12; // eax
  void **v13; // rdi
  void **v14; // rcx
  char *v15; // rax
  struct CRundownHelperBase *v16; // rax
  void *v18; // [rsp+70h] [rbp+8h] BYREF

  started = 0;
  if ( !a2 )
  {
    started = -2147024809;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids);
  }
  EnterCriticalSection(lpCriticalSection);
  if ( a2 && CSsdpServiceManager::FindServiceByUsn(lpCriticalSection, a2[3]) )
  {
    started = -2147024809;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids);
      v9 = WPP_GLOBAL_Control;
LABEL_28:
      if ( v9 != (LPCSTR)&WPP_GLOBAL_Control && (v9[28] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)v9 + 2), 29, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids, (unsigned int)started);
      goto LABEL_31;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
  }
  v10 = started == 0;
  if ( started >= 0 )
  {
    v11 = 0;
    v18 = 0;
    v12 = CUList<CSsdpService>::HrPushFrontDefault(&v18);
    v13 = (void **)v18;
    started = v12;
    if ( v12 >= 0 )
    {
      started = CSsdpService::HrInitialize((CSsdpService *)((char *)v18 + 8), (struct _SSDP_MESSAGE_EX *)a2, a3, a4);
      if ( started >= 0 )
      {
        started = CSsdpService::HrStartTimer(v13 + 1);
        if ( started >= 0 )
        {
          if ( v13 )
          {
            do
            {
              v14 = v13;
              v13 = (void **)*v13;
            }
            while ( v13 );
          }
          else
          {
            v14 = &v18;
          }
          v13 = 0;
          *v14 = lpCriticalSection[1].DebugInfo;
          v15 = (char *)v18;
          lpCriticalSection[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v18;
          v11 = v15 + 8;
        }
      }
    }
    if ( v13 )
      CUList<CSsdpService>::Node::`scalar deleting destructor'(v13);
    if ( v11 )
    {
      v16 = (struct CRundownHelperBase *)malloc(0x10u);
      if ( v16 )
      {
        *((_QWORD *)v16 + 1) = v11;
        *(_QWORD *)v16 = &CRundownHelper<CSsdpService>::`vftable';
        started = CSsdpRundownSupport::HrAddItemInternal(&CSsdpRundownSupport::s_instance, v16);
      }
      else
      {
        started = -2147024882;
      }
    }
    v9 = WPP_GLOBAL_Control;
    v10 = started == 0;
  }
  if ( !v10 )
    goto LABEL_28;
LABEL_31:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180018590  push    rbx
0x180018592  push    rbp
0x180018593  push    rsi
0x180018594  push    rdi
0x180018595  push    r12
0x180018597  push    r13
0x180018599  push    r14
0x18001859b  push    r15
0x18001859d  sub     rsp, 28h
0x1800185a1  xor     ebx, ebx
0x1800185a3  lea     rsi, WPP_GLOBAL_Control
0x1800185aa  mov     r12, r9
0x1800185ad  mov     r13d, r8d
0x1800185b0  mov     rbp, rdx
0x1800185b3  mov     r14, rcx
0x1800185b6  mov     edi, 80070057h
0x1800185bb  test    rdx, rdx
0x1800185be  jnz     short loc_1800185E7
0x1800185c0  mov     ebx, edi
0x1800185c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185c9  cmp     rcx, rsi
0x1800185cc  jz      short loc_1800185E7
0x1800185ce  test    byte ptr [rcx+1Ch], 1
0x1800185d2  jz      short loc_1800185E7
0x1800185d4  mov     rcx, [rcx+10h]
0x1800185d8  lea     edx, [rbp+1Bh]
0x1800185db  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x1800185e2  call    WPP_SF_
0x1800185e7  mov     rcx, r14; lpCriticalSection
0x1800185ea  call    cs:__imp_EnterCriticalSection
0x1800185f1  nop     dword ptr [rax+rax+00h]
0x1800185f6  test    rbp, rbp
0x1800185f9  jz      short loc_180018641
0x1800185fb  mov     rdx, [rbp+18h]; char *
0x1800185ff  mov     rcx, r14; lpCriticalSection
0x180018602  call    ?FindServiceByUsn@CSsdpServiceManager@@QEAAPEAVCSsdpService@@PEAD@Z; CSsdpServiceManager::FindServiceByUsn(char *)
0x180018607  test    rax, rax
0x18001860a  jz      short loc_180018641
0x18001860c  mov     ebx, edi
0x18001860e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018615  cmp     rcx, rsi
0x180018618  jz      short loc_180018648
0x18001861a  test    byte ptr [rcx+1Ch], 1
0x18001861e  jz      short loc_180018648
0x180018620  mov     rcx, [rcx+10h]
0x180018624  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x18001862b  mov     edx, 1Ch
0x180018630  call    WPP_SF_
0x180018635  mov     rcx, cs:WPP_GLOBAL_Control
0x18001863c  jmp     loc_180018723
0x180018641  mov     rcx, cs:WPP_GLOBAL_Control
0x180018648  test    ebx, ebx
0x18001864a  js      loc_180018721
0x180018650  xor     esi, esi
0x180018652  lea     rcx, [rsp+68h+arg_0]
0x180018657  mov     [rsp+68h+arg_0], rsi
0x18001865c  call    ?HrPushFrontDefault@?$CUList@VCSsdpService@@@@QEAAJXZ; CUList<CSsdpService>::HrPushFrontDefault(void)
0x180018661  mov     rdi, [rsp+68h+arg_0]
0x180018666  mov     ebx, eax
0x180018668  test    eax, eax
0x18001866a  js      short loc_1800186C3
0x18001866c  mov     r9, r12; void **
0x18001866f  lea     rcx, [rdi+8]; this
0x180018673  mov     r8d, r13d; unsigned int
0x180018676  mov     rdx, rbp; struct _SSDP_MESSAGE_EX *
0x180018679  call    ?HrInitialize@CSsdpService@@QEAAJPEAU_SSDP_MESSAGE_EX@@KPEAPEAX@Z; CSsdpService::HrInitialize(_SSDP_MESSAGE_EX *,ulong,void * *)
0x18001867e  mov     ebx, eax
0x180018680  test    eax, eax
0x180018682  js      short loc_1800186C3
0x180018684  lea     rcx, [rdi+8]; Parameter
0x180018688  call    ?HrStartTimer@CSsdpService@@QEAAJXZ; CSsdpService::HrStartTimer(void)
0x18001868d  mov     ebx, eax
0x18001868f  test    eax, eax
0x180018691  js      short loc_1800186C3
0x180018693  test    rdi, rdi
0x180018696  jz      short loc_1800186A8
0x180018698  mov     rax, [rdi]
0x18001869b  mov     rcx, rdi
0x18001869e  mov     rdi, rax
0x1800186a1  test    rax, rax
0x1800186a4  jnz     short loc_180018698
0x1800186a6  jmp     short loc_1800186AD
0x1800186a8  lea     rcx, [rsp+68h+arg_0]
0x1800186ad  mov     rax, [r14+28h]
0x1800186b1  xor     edi, edi
0x1800186b3  mov     [rcx], rax
0x1800186b6  mov     rax, [rsp+68h+arg_0]
0x1800186bb  mov     [r14+28h], rax
0x1800186bf  lea     rsi, [rax+8]
0x1800186c3  test    rdi, rdi
0x1800186c6  jz      short loc_1800186D0
0x1800186c8  mov     rcx, rdi; void *
0x1800186cb  call    ??_GNode@?$CUList@VCSsdpService@@@@QEAAPEAXI@Z; CUList<CSsdpService>::Node::`scalar deleting destructor'(uint)
0x1800186d0  test    rsi, rsi
0x1800186d3  jz      short loc_180018711
0x1800186d5  mov     ecx, 10h; Size
0x1800186da  call    cs:__imp_malloc
0x1800186e1  nop     dword ptr [rax+rax+00h]
0x1800186e6  test    rax, rax
0x1800186e9  jz      short loc_18001870C
0x1800186eb  lea     rcx, ??_7?$CRundownHelper@VCSsdpService@@@@6B@; const CRundownHelper<CSsdpService>::`vftable'
0x1800186f2  mov     [rax+8], rsi
0x1800186f6  mov     [rax], rcx
0x1800186f9  mov     rdx, rax; struct CRundownHelperBase *
0x1800186fc  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x180018703  call    ?HrAddItemInternal@CSsdpRundownSupport@@AEAAJPEAVCRundownHelperBase@@@Z; CSsdpRundownSupport::HrAddItemInternal(CRundownHelperBase *)
0x180018708  mov     ebx, eax
0x18001870a  jmp     short loc_180018711
0x18001870c  mov     ebx, 8007000Eh
0x180018711  mov     rcx, cs:WPP_GLOBAL_Control
0x180018718  lea     rsi, WPP_GLOBAL_Control
0x18001871f  test    ebx, ebx
0x180018721  jz      short loc_180018746
0x180018723  cmp     rcx, rsi
0x180018726  jz      short loc_180018746
0x180018728  test    byte ptr [rcx+1Ch], 1
0x18001872c  jz      short loc_180018746
0x18001872e  mov     rcx, [rcx+10h]
0x180018732  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180018739  mov     edx, 1Dh
0x18001873e  mov     r9d, ebx
0x180018741  call    WPP_SF_d
0x180018746  mov     rcx, r14; lpCriticalSection
0x180018749  call    cs:__imp_LeaveCriticalSection
0x180018750  nop     dword ptr [rax+rax+00h]
0x180018755  mov     eax, ebx
0x180018757  add     rsp, 28h
0x18001875b  pop     r15
0x18001875d  pop     r14
0x18001875f  pop     r13
0x180018761  pop     r12
0x180018763  pop     rdi
0x180018764  pop     rsi
0x180018765  pop     rbp
0x180018766  pop     rbx
0x180018767  retn
```
