# CSsdpServiceManager::HrAddService(_SSDP_MESSAGE_EX *,ulong,void * *)

- ea: `0x1800161b4`
- end: `0x18001637c`
- name: `?HrAddService@CSsdpServiceManager@@QEAAJPEAU_SSDP_MESSAGE_EX@@KPEAPEAX@Z`
- size: `456`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct _SSDP_MESSAGE_EX *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18001ed50`

## callees

- `0x1800151ec`
- `0x1800161b4`
- `0x180016410`
- `0x18001b274`
- `0x18001e63c`
- `0x1800255a8`
- `0x180028000`
- `0x18002f95c`
- `0x18002faf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001626b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800162eb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001626b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800162eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001634d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001634d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001620c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001620c`

## pseudocode

```c
__int64 __fastcall CSsdpServiceManager::HrAddService(
        LPCRITICAL_SECTION lpCriticalSection,
        struct _SSDP_MESSAGE_EX *a2,
        unsigned int a3,
        void **a4)
{
  int started; // edi
  LPCSTR v9; // rcx
  bool v10; // zf
  _QWORD *v11; // rax
  _QWORD **v12; // rbx
  _QWORD *v13; // rcx
  PRTL_CRITICAL_SECTION_DEBUG *v14; // rdx
  struct CRundownHelperBase *v15; // rax

  started = 0;
  if ( !a2 )
  {
    started = -2147024809;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids);
  }
  EnterCriticalSection(lpCriticalSection);
  if ( !a2 || !CSsdpServiceManager::FindServiceByUsn(lpCriticalSection, *((char **)a2 + 3)) )
  {
    v10 = started == 0;
    if ( started >= 0 )
    {
      v11 = malloc(0x138u);
      v12 = (_QWORD **)v11;
      if ( !v11 )
      {
        started = -2147024882;
        goto LABEL_21;
      }
      *v11 = 0;
      CSsdpService::CSsdpService((CSsdpService *)(v11 + 1));
      *v12 = 0;
      started = CSsdpService::HrInitialize((CSsdpService *)(v12 + 1), a2, a3, a4);
      if ( started < 0 || (started = CSsdpService::HrStartTimer(v12 + 1), started < 0) )
      {
        CUList<CSsdpService>::Node::`scalar deleting destructor'(v12);
        goto LABEL_21;
      }
      v13 = v12;
      do
      {
        v14 = (PRTL_CRITICAL_SECTION_DEBUG *)v13;
        v13 = (_QWORD *)*v13;
      }
      while ( v13 );
      *v14 = lpCriticalSection[1].DebugInfo;
      lpCriticalSection[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v12;
      if ( v12 != (_QWORD **)-8LL )
      {
        v15 = (struct CRundownHelperBase *)malloc(0x10u);
        if ( v15 )
        {
          *((_QWORD *)v15 + 1) = v12 + 1;
          *(_QWORD *)v15 = &CRundownHelper<CSsdpService>::`vftable';
          started = CSsdpRundownSupport::HrAddItemInternal(&CSsdpRundownSupport::s_instance, v15);
        }
        else
        {
          started = -2147024882;
        }
      }
      v10 = started == 0;
    }
    if ( v10 )
      goto LABEL_25;
    goto LABEL_21;
  }
  started = -2147024809;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids);
LABEL_21:
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (LPCSTR)&WPP_GLOBAL_Control && (v9[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v9 + 2), 29, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids, (unsigned int)started);
LABEL_25:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800161b4  push    rbx
0x1800161b6  push    rbp
0x1800161b7  push    rsi
0x1800161b8  push    rdi
0x1800161b9  push    r12
0x1800161bb  push    r14
0x1800161bd  push    r15
0x1800161bf  sub     rsp, 20h
0x1800161c3  xor     edi, edi
0x1800161c5  lea     rsi, WPP_GLOBAL_Control
0x1800161cc  mov     r15, r9
0x1800161cf  mov     r12d, r8d
0x1800161d2  mov     rbp, rdx
0x1800161d5  mov     r14, rcx
0x1800161d8  mov     ebx, 80070057h
0x1800161dd  test    rdx, rdx
0x1800161e0  jnz     short loc_180016209
0x1800161e2  mov     edi, ebx
0x1800161e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161eb  cmp     rcx, rsi
0x1800161ee  jz      short loc_180016209
0x1800161f0  test    byte ptr [rcx+1Ch], 1
0x1800161f4  jz      short loc_180016209
0x1800161f6  mov     rcx, [rcx+10h]
0x1800161fa  lea     edx, [rbp+1Bh]
0x1800161fd  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x180016204  call    WPP_SF_
0x180016209  mov     rcx, r14; lpCriticalSection
0x18001620c  call    cs:__imp_EnterCriticalSection
0x180016212  test    rbp, rbp
0x180016215  jz      short loc_18001625E
0x180016217  mov     rdx, [rbp+18h]; char *
0x18001621b  mov     rcx, r14; lpCriticalSection
0x18001621e  call    ?FindServiceByUsn@CSsdpServiceManager@@QEAAPEAVCSsdpService@@PEAD@Z; CSsdpServiceManager::FindServiceByUsn(char *)
0x180016223  test    rax, rax
0x180016226  jz      short loc_18001625E
0x180016228  mov     edi, ebx
0x18001622a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016231  cmp     rcx, rsi
0x180016234  jz      loc_180016320
0x18001623a  test    byte ptr [rcx+1Ch], 1
0x18001623e  jz      loc_180016320
0x180016244  mov     rcx, [rcx+10h]
0x180016248  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x18001624f  mov     edx, 1Ch
0x180016254  call    WPP_SF_
0x180016259  jmp     loc_180016319
0x18001625e  test    edi, edi
0x180016260  js      loc_180016317
0x180016266  mov     ecx, 138h; Size
0x18001626b  call    cs:__imp_malloc
0x180016271  mov     rbx, rax
0x180016274  test    rax, rax
0x180016277  jz      loc_180016375
0x18001627d  lea     rcx, [rax+8]; this
0x180016281  mov     qword ptr [rax], 0
0x180016288  call    ??0CSsdpService@@QEAA@XZ; CSsdpService::CSsdpService(void)
0x18001628d  lea     rsi, [rbx+8]
0x180016291  mov     qword ptr [rbx], 0
0x180016298  mov     rcx, rsi; this
0x18001629b  mov     r9, r15; void **
0x18001629e  mov     r8d, r12d; unsigned int
0x1800162a1  mov     rdx, rbp; struct _SSDP_MESSAGE_EX *
0x1800162a4  call    ?HrInitialize@CSsdpService@@QEAAJPEAU_SSDP_MESSAGE_EX@@KPEAPEAX@Z; CSsdpService::HrInitialize(_SSDP_MESSAGE_EX *,ulong,void * *)
0x1800162a9  mov     edi, eax
0x1800162ab  test    eax, eax
0x1800162ad  js      loc_18001636B
0x1800162b3  mov     rcx, rsi; Parameter
0x1800162b6  call    ?HrStartTimer@CSsdpService@@QEAAJXZ; CSsdpService::HrStartTimer(void)
0x1800162bb  mov     edi, eax
0x1800162bd  test    eax, eax
0x1800162bf  js      loc_18001636B
0x1800162c5  mov     rcx, rbx
0x1800162c8  mov     rax, [rcx]
0x1800162cb  lea     rdx, [rcx]
0x1800162ce  mov     rcx, rax
0x1800162d1  test    rax, rax
0x1800162d4  jnz     short loc_1800162C8
0x1800162d6  mov     rax, [r14+28h]
0x1800162da  mov     [rdx], rax
0x1800162dd  mov     [r14+28h], rbx
0x1800162e1  test    rsi, rsi
0x1800162e4  jz      short loc_180016315
0x1800162e6  mov     ecx, 10h; Size
0x1800162eb  call    cs:__imp_malloc
0x1800162f1  test    rax, rax
0x1800162f4  jz      short loc_180016364
0x1800162f6  lea     rcx, ??_7?$CRundownHelper@VCSsdpService@@@@6B@; const CRundownHelper<CSsdpService>::`vftable'
0x1800162fd  mov     [rax+8], rsi
0x180016301  mov     [rax], rcx
0x180016304  mov     rdx, rax; struct CRundownHelperBase *
0x180016307  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x18001630e  call    ?HrAddItemInternal@CSsdpRundownSupport@@AEAAJPEAVCRundownHelperBase@@@Z; CSsdpRundownSupport::HrAddItemInternal(CRundownHelperBase *)
0x180016313  mov     edi, eax
0x180016315  test    edi, edi
0x180016317  jz      short loc_18001634A
0x180016319  mov     rcx, cs:WPP_GLOBAL_Control
0x180016320  lea     rax, WPP_GLOBAL_Control
0x180016327  cmp     rcx, rax
0x18001632a  jz      short loc_18001634A
0x18001632c  test    byte ptr [rcx+1Ch], 1
0x180016330  jz      short loc_18001634A
0x180016332  mov     rcx, [rcx+10h]
0x180016336  lea     r8, WPP_71fcbfaa684a35e38cde20de91eb05b5_Traceguids
0x18001633d  mov     edx, 1Dh
0x180016342  mov     r9d, edi
0x180016345  call    WPP_SF_d
0x18001634a  mov     rcx, r14; lpCriticalSection
0x18001634d  call    cs:__imp_LeaveCriticalSection
0x180016353  mov     eax, edi
0x180016355  add     rsp, 20h
0x180016359  pop     r15
0x18001635b  pop     r14
0x18001635d  pop     r12
0x18001635f  pop     rdi
0x180016360  pop     rsi
0x180016361  pop     rbp
0x180016362  pop     rbx
0x180016363  retn
0x180016364  mov     edi, 8007000Eh
0x180016369  jmp     short loc_180016315
0x18001636b  mov     rcx, rbx; void *
0x18001636e  call    ??_GNode@?$CUList@VCSsdpService@@@@QEAAPEAXI@Z; CUList<CSsdpService>::Node::`scalar deleting destructor'(uint)
0x180016373  jmp     short loc_180016319
0x180016375  mov     edi, 8007000Eh
0x18001637a  jmp     short loc_180016319
```
