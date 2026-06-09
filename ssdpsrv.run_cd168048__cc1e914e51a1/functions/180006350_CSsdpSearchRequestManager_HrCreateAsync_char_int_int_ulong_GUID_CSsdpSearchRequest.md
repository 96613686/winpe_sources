# CSsdpSearchRequestManager::HrCreateAsync(char *,int,int,ulong,_GUID,CSsdpSearchRequest * *)

- ea: `0x180006350`
- end: `0x180006836`
- name: `?HrCreateAsync@CSsdpSearchRequestManager@@QEAAJPEADHHKU_GUID@@PEAPEAVCSsdpSearchRequest@@@Z`
- size: `1254`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, char *@<rdx>, int@<r8d>, int@<r9d>, unsigned int, struct _GUID *__struct_ptr, struct CSsdpSearchRequest **)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001fe30`

## callees

- `0x180005be0`
- `0x180006350`
- `0x18000683c`
- `0x180006880`
- `0x18000696c`
- `0x180008190`
- `0x180008eb8`
- `0x18000b87c`
- `0x180015168`
- `0x180019fa4`
- `0x18001fbc4`
- `0x1800271fc`
- `0x18002911c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180006493`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180006493`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800065d6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006825`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800065d6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006825`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800063ab`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000672c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800063ab`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000672c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006617`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000669b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006804`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006617`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000669b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006804`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800063d1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800066b2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800063d1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800066b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006440`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000662e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006440`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000662e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006556`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006556`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800064ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180006514`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800064ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180006514`

## pseudocode

```c
__int64 __fastcall CSsdpSearchRequestManager::HrCreateAsync(
        LPCRITICAL_SECTION lpCriticalSection,
        char *a2,
        int a3,
        int a4,
        unsigned int a5,
        struct _GUID *a6,
        struct CSsdpSearchRequest **a7)
{
  struct _RTL_CRITICAL_SECTION_DEBUG *v11; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v12; // rbx
  int Win32Error; // esi
  struct _RTL_CRITICAL_SECTION **p_CriticalSection; // r12
  __int128 v15; // xmm6
  struct _RTL_CRITICAL_SECTION *EventA; // rax
  struct _RTL_CRITICAL_SECTION *v17; // rax
  struct _RTL_CRITICAL_SECTION *Semaphore; // rax
  bool v19; // zf
  __int64 v20; // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rax
  int v22; // ecx
  struct _RTL_CRITICAL_SECTION_DEBUG *v23; // rdx
  PRTL_CRITICAL_SECTION_DEBUG *v24; // r8
  struct CSsdpSearchRequest **v25; // rdi
  struct CRundownHelperBase *v27; // rax
  __int64 v28; // rax
  void *Block; // [rsp+30h] [rbp-A8h] BYREF
  char v30[8]; // [rsp+40h] [rbp-98h] BYREF
  __int64 v31; // [rsp+48h] [rbp-90h]
  __int64 v32; // [rsp+90h] [rbp-48h]

  if ( !a7 )
    return 2147500035LL;
  if ( !a2 )
    return 2147942487LL;
  if ( LODWORD(lpCriticalSection[16].SpinCount) )
    return 2147942421LL;
  v11 = (struct _RTL_CRITICAL_SECTION_DEBUG *)malloc(0x148u);
  v12 = v11;
  if ( !v11 )
  {
    v12 = 0;
    Win32Error = -2147024882;
LABEL_6:
    SetEvent(lpCriticalSection[17].DebugInfo);
LABEL_7:
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
        (unsigned int)Win32Error);
    goto LABEL_32;
  }
  p_CriticalSection = &v11->CriticalSection;
  *(_QWORD *)&v11->Type = 0;
  CSsdpSearchRequest::CSsdpSearchRequest((CSsdpSearchRequest *)&v11->CriticalSection);
  *(_QWORD *)&v12->Type = 0;
  v15 = (__int128)*a6;
  EnterCriticalSection((LPCRITICAL_SECTION)(p_CriticalSection + 19));
  if ( lpCriticalSection == (LPCRITICAL_SECTION)-64LL )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(p_CriticalSection + 19));
    Win32Error = -2147024809;
    goto LABEL_6;
  }
  p_CriticalSection[33] = (LPCRITICAL_SECTION)((char *)lpCriticalSection + 64);
  *((_DWORD *)p_CriticalSection + 69) = a5;
  *((_DWORD *)p_CriticalSection + 36) = a3;
  *((_DWORD *)p_CriticalSection + 37) = a4;
  *(_OWORD *)(p_CriticalSection + 35) = v15;
  *((_DWORD *)p_CriticalSection + 74) = _o__stricmp(a2, "ssdp:all") == 0;
  Win32Error = CUString::HrAssign((CUString *)(p_CriticalSection + 1), a2);
  if ( Win32Error < 0 )
    goto LABEL_37;
  SsdpGetTypeVersion(a2, (struct _TypeVersion *)((char *)p_CriticalSection + 300));
  EventA = (struct _RTL_CRITICAL_SECTION *)CreateEventA(0, 1, 0, 0);
  p_CriticalSection[29] = EventA;
  if ( !EventA )
  {
    Win32Error = HrFromLastWin32Error();
    if ( Win32Error < 0 )
      goto LABEL_37;
  }
  v17 = (struct _RTL_CRITICAL_SECTION *)CreateEventA(0, 1, 0, 0);
  p_CriticalSection[30] = v17;
  if ( !v17 )
  {
    Win32Error = HrFromLastWin32Error();
    if ( Win32Error < 0 )
      goto LABEL_37;
  }
  Semaphore = (struct _RTL_CRITICAL_SECTION *)CreateSemaphoreExW(0, 0, 500, 0, 0, 0x1F0003u);
  p_CriticalSection[31] = Semaphore;
  if ( !Semaphore )
    Win32Error = HrFromLastWin32Error();
  v19 = Win32Error == 0;
  if ( Win32Error < 0 )
  {
LABEL_21:
    if ( v19 )
      goto LABEL_22;
    goto LABEL_44;
  }
  memset_0(v30, 0, 0x58u);
  Win32Error = CSsdpSearchRequest::HrInitializeSsdpSearchRequest((struct _SSDP_REQUEST *)v30, a2);
  if ( Win32Error < 0 )
  {
LABEL_37:
    v19 = Win32Error == 0;
    goto LABEL_21;
  }
  Block = 0;
  if ( (unsigned int)ComposeSsdpRequest((const struct _SSDP_REQUEST *)v30, (char **)&Block) )
  {
    Win32Error = CUString::HrAssign((CUString *)(p_CriticalSection + 2), (const char *)Block);
    free(Block);
    v20 = v32;
    v31 = 0;
    *(_QWORD *)(v32 + 32) = 0;
    *(_QWORD *)(v20 + 40) = 0;
    FreeSsdpRequest((struct _SSDP_REQUEST *)v30);
    v19 = Win32Error == 0;
    if ( Win32Error < 0 )
      goto LABEL_21;
    *((_DWORD *)p_CriticalSection + 64) = 0;
    goto LABEL_37;
  }
  v28 = v32;
  Win32Error = -2147024882;
  v31 = 0;
  *(_QWORD *)(v32 + 32) = 0;
  *(_QWORD *)(v28 + 40) = 0;
  FreeSsdpRequest((struct _SSDP_REQUEST *)v30);
LABEL_44:
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids,
      (unsigned int)Win32Error);
LABEL_22:
  LeaveCriticalSection((LPCRITICAL_SECTION)(p_CriticalSection + 19));
  if ( Win32Error < 0 )
    goto LABEL_31;
  EnterCriticalSection(lpCriticalSection);
  DebugInfo = lpCriticalSection[1].DebugInfo;
  v22 = 0;
  if ( DebugInfo )
  {
    do
    {
      DebugInfo = *(PRTL_CRITICAL_SECTION_DEBUG *)&DebugInfo->Type;
      ++v22;
    }
    while ( DebugInfo );
    if ( v22 >= 200 )
    {
      Win32Error = -2147024875;
      goto LABEL_35;
    }
  }
  Win32Error = CSsdpSearchRequest::HrStart((CSsdpSearchRequest *)p_CriticalSection);
  if ( Win32Error < 0 )
  {
LABEL_35:
    v25 = a7;
    goto LABEL_30;
  }
  v23 = v12;
  do
  {
    v24 = (PRTL_CRITICAL_SECTION_DEBUG *)v23;
    v23 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&v23->Type;
  }
  while ( v23 );
  v25 = a7;
  *v24 = lpCriticalSection[1].DebugInfo;
  lpCriticalSection[1].DebugInfo = v12;
  v12 = 0;
  *a7 = (struct CSsdpSearchRequest *)p_CriticalSection;
LABEL_30:
  LeaveCriticalSection(lpCriticalSection);
  if ( Win32Error >= 0 )
  {
    v27 = (struct CRundownHelperBase *)malloc(0x10u);
    if ( v27 )
    {
      *(_QWORD *)v27 = &CRundownHelper<CSsdpSearchRequest>::`vftable';
      *((_QWORD *)v27 + 1) = *v25;
      CSsdpRundownSupport::HrAddItemInternal(&CSsdpRundownSupport::s_instance, v27);
    }
  }
LABEL_31:
  SetEvent(lpCriticalSection[17].DebugInfo);
  if ( Win32Error )
    goto LABEL_7;
LABEL_32:
  if ( v12 )
  {
    CUList<CSsdpSearchRequest>::Node::~Node(v12);
    free(v12);
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x180006350  mov     r11, rsp
0x180006353  push    rbp
0x180006354  push    rsi
0x180006355  push    rdi
0x180006356  push    r13
0x180006358  sub     rsp, 0B8h
0x18000635f  cmp     [rsp+0D8h+arg_30], 0
0x180006368  mov     esi, r9d
0x18000636b  mov     ebp, r8d
0x18000636e  mov     rdi, rdx
0x180006371  mov     r13, rcx
0x180006374  jz      loc_180006766
0x18000637a  test    rdx, rdx
0x18000637d  jz      loc_18000676D
0x180006383  mov     eax, [rcx+2A0h]
0x180006389  test    eax, eax
0x18000638b  jnz     loc_180006774
0x180006391  mov     [r11+8], rbx
0x180006395  mov     ecx, 148h; Size
0x18000639a  mov     [r11+10h], r12
0x18000639e  mov     [r11+18h], r14
0x1800063a2  mov     [r11-28h], r15
0x1800063a6  movaps  xmmword ptr [r11-38h], xmm6
0x1800063ab  call    cs:__imp_malloc
0x1800063b2  nop     dword ptr [rax+rax+00h]
0x1800063b7  xor     r15d, r15d
0x1800063ba  mov     rbx, rax
0x1800063bd  test    rax, rax
0x1800063c0  jnz     short loc_18000641B
0x1800063c2  mov     ebx, r15d
0x1800063c5  mov     esi, 8007000Eh
0x1800063ca  mov     rcx, [r13+2A8h]; hEvent
0x1800063d1  call    cs:__imp_SetEvent
0x1800063d8  nop     dword ptr [rax+rax+00h]
0x1800063dd  lea     rbp, WPP_GLOBAL_Control
0x1800063e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063eb  cmp     rcx, rbp
0x1800063ee  jz      loc_1800066C6
0x1800063f4  test    byte ptr [rcx+1Ch], 1
0x1800063f8  jz      loc_1800066C6
0x1800063fe  mov     rcx, [rcx+10h]
0x180006402  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x180006409  mov     edx, 28h ; '('
0x18000640e  mov     r9d, esi
0x180006411  call    WPP_SF_d
0x180006416  jmp     loc_1800066C6
0x18000641b  lea     r12, [rax+8]
0x18000641f  mov     [rax], r15
0x180006422  mov     rcx, r12; this
0x180006425  call    ??0CSsdpSearchRequest@@QEAA@XZ; CSsdpSearchRequest::CSsdpSearchRequest(void)
0x18000642a  mov     rax, [rsp+0D8h+arg_28]
0x180006432  lea     rcx, [r12+98h]; lpCriticalSection
0x18000643a  mov     [rbx], r15
0x18000643d  movaps  xmm6, xmmword ptr [rax]
0x180006440  call    cs:__imp_EnterCriticalSection
0x180006447  nop     dword ptr [rax+rax+00h]
0x18000644c  lea     rax, [r13+40h]
0x180006450  test    rax, rax
0x180006453  jz      loc_1800067FC
0x180006459  mov     [r12+108h], rax
0x180006461  lea     rdx, aSsdpAll; "ssdp:all"
0x180006468  mov     eax, [rsp+0D8h+arg_20]
0x18000646f  mov     rcx, rdi
0x180006472  mov     [r12+114h], eax
0x18000647a  mov     [r12+90h], ebp
0x180006482  mov     [r12+94h], esi
0x18000648a  movups  xmmword ptr [r12+118h], xmm6
0x180006493  call    cs:__imp__o__stricmp
0x18000649a  nop     dword ptr [rax+rax+00h]
0x18000649f  mov     ecx, r15d
0x1800064a2  mov     rdx, rdi; char *
0x1800064a5  test    eax, eax
0x1800064a7  setz    cl
0x1800064aa  mov     [r12+128h], ecx
0x1800064b2  lea     rcx, [r12+8]; this
0x1800064b7  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x1800064bc  lea     rbp, WPP_GLOBAL_Control
0x1800064c3  mov     esi, eax
0x1800064c5  test    eax, eax
0x1800064c7  js      loc_180006720
0x1800064cd  lea     rdx, [r12+12Ch]; struct _TypeVersion *
0x1800064d5  mov     rcx, rdi; char *
0x1800064d8  call    ?SsdpGetTypeVersion@@YAXPEBDPEAU_TypeVersion@@@Z; SsdpGetTypeVersion(char const *,_TypeVersion *)
0x1800064dd  xor     r9d, r9d; lpName
0x1800064e0  xor     r8d, r8d; bInitialState
0x1800064e3  mov     edx, 1; bManualReset
0x1800064e8  xor     ecx, ecx; lpEventAttributes
0x1800064ea  call    cs:__imp_CreateEventA
0x1800064f1  nop     dword ptr [rax+rax+00h]
0x1800064f6  mov     [r12+0E8h], rax
0x1800064fe  test    rax, rax
0x180006501  jz      loc_180006711
0x180006507  xor     r9d, r9d; lpName
0x18000650a  xor     r8d, r8d; bInitialState
0x18000650d  mov     edx, 1; bManualReset
0x180006512  xor     ecx, ecx; lpEventAttributes
0x180006514  call    cs:__imp_CreateEventA
0x18000651b  nop     dword ptr [rax+rax+00h]
0x180006520  mov     [r12+0F0h], rax
0x180006528  test    rax, rax
0x18000652b  jnz     short loc_18000653C
0x18000652d  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180006532  mov     esi, eax
0x180006534  test    eax, eax
0x180006536  js      loc_180006720
0x18000653c  mov     [rsp+0D8h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180006544  xor     r9d, r9d; lpName
0x180006547  xor     edx, edx; lInitialCount
0x180006549  mov     [rsp+0D8h+dwFlags], r15d; dwFlags
0x18000654e  xor     ecx, ecx; lpSemaphoreAttributes
0x180006550  mov     r8d, 1F4h; lMaximumCount
0x180006556  call    cs:__imp_CreateSemaphoreExW
0x18000655d  nop     dword ptr [rax+rax+00h]
0x180006562  mov     [r12+0F8h], rax
0x18000656a  test    rax, rax
0x18000656d  jz      loc_18000677E
0x180006573  test    esi, esi
0x180006575  js      loc_180006609
0x18000657b  xor     edx, edx; Val
0x18000657d  lea     rcx, [rsp+0D8h+var_98]; void *
0x180006582  mov     r8d, 58h ; 'X'; Size
0x180006588  call    memset_0
0x18000658d  mov     rdx, rdi; char *
0x180006590  lea     rcx, [rsp+0D8h+var_98]; struct _SSDP_REQUEST *
0x180006595  call    ?HrInitializeSsdpSearchRequest@CSsdpSearchRequest@@SAJPEAU_SSDP_REQUEST@@PEAD@Z; CSsdpSearchRequest::HrInitializeSsdpSearchRequest(_SSDP_REQUEST *,char *)
0x18000659a  mov     esi, eax
0x18000659c  test    eax, eax
0x18000659e  js      loc_180006720
0x1800065a4  lea     rdx, [rsp+0D8h+Block]; char **
0x1800065a9  mov     [rsp+0D8h+Block], r15
0x1800065ae  lea     rcx, [rsp+0D8h+var_98]; struct _SSDP_REQUEST *
0x1800065b3  call    ?ComposeSsdpRequest@@YAHPEBU_SSDP_REQUEST@@PEAPEAD@Z; ComposeSsdpRequest(_SSDP_REQUEST const *,char * *)
0x1800065b8  test    eax, eax
0x1800065ba  jz      loc_18000678A
0x1800065c0  mov     rdx, [rsp+0D8h+Block]; char *
0x1800065c5  lea     rcx, [r12+10h]; this
0x1800065ca  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x1800065cf  mov     rcx, [rsp+0D8h+Block]; Block
0x1800065d4  mov     esi, eax
0x1800065d6  call    cs:__imp_free
0x1800065dd  nop     dword ptr [rax+rax+00h]
0x1800065e2  mov     rax, [rsp+0D8h+var_48]
0x1800065ea  lea     rcx, [rsp+0D8h+var_98]; struct _SSDP_REQUEST *
0x1800065ef  mov     [rsp+0D8h+var_90], r15
0x1800065f4  mov     [rax+20h], r15
0x1800065f8  mov     [rax+28h], r15
0x1800065fc  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180006601  test    esi, esi
0x180006603  jns     loc_1800067E5
0x180006609  jnz     loc_1800067AE
0x18000660f  lea     rcx, [r12+98h]; lpCriticalSection
0x180006617  call    cs:__imp_LeaveCriticalSection
0x18000661e  nop     dword ptr [rax+rax+00h]
0x180006623  test    esi, esi
0x180006625  js      loc_1800066AB
0x18000662b  mov     rcx, r13; lpCriticalSection
0x18000662e  call    cs:__imp_EnterCriticalSection
0x180006635  nop     dword ptr [rax+rax+00h]
0x18000663a  mov     rax, [r13+28h]
0x18000663e  mov     ecx, r15d
0x180006641  test    rax, rax
0x180006644  jz      short loc_18000665C
0x180006646  mov     rax, [rax]
0x180006649  inc     ecx
0x18000664b  test    rax, rax
0x18000664e  jnz     short loc_180006646
0x180006650  cmp     ecx, 0C8h
0x180006656  jge     loc_1800067F2
0x18000665c  mov     rcx, r12; this
0x18000665f  call    ?HrStart@CSsdpSearchRequest@@QEAAJXZ; CSsdpSearchRequest::HrStart(void)
0x180006664  mov     esi, eax
0x180006666  test    eax, eax
0x180006668  js      loc_180006707
0x18000666e  mov     rdx, rbx
0x180006671  mov     rcx, [rdx]
0x180006674  lea     r8, [rdx]
0x180006677  mov     rdx, rcx
0x18000667a  test    rcx, rcx
0x18000667d  jnz     short loc_180006671
0x18000667f  mov     rax, [r13+28h]
0x180006683  mov     rdi, [rsp+0D8h+arg_30]
0x18000668b  mov     [r8], rax
0x18000668e  mov     [r13+28h], rbx
0x180006692  mov     rbx, r15
0x180006695  mov     [rdi], r12
0x180006698  mov     rcx, r13; lpCriticalSection
0x18000669b  call    cs:__imp_LeaveCriticalSection
0x1800066a2  nop     dword ptr [rax+rax+00h]
0x1800066a7  test    esi, esi
0x1800066a9  jns     short loc_180006727
0x1800066ab  mov     rcx, [r13+2A8h]; hEvent
0x1800066b2  call    cs:__imp_SetEvent
0x1800066b9  nop     dword ptr [rax+rax+00h]
0x1800066be  test    esi, esi
0x1800066c0  jnz     loc_1800063E4
0x1800066c6  movaps  xmm6, [rsp+0D8h+var_38]
0x1800066ce  mov     r15, [rsp+0D8h+var_28]
0x1800066d6  mov     r14, [rsp+0D8h+arg_10]
0x1800066de  mov     r12, [rsp+0D8h+arg_8]
0x1800066e6  test    rbx, rbx
0x1800066e9  jnz     loc_18000681A
0x1800066ef  mov     rbx, [rsp+0D8h+arg_0]
0x1800066f7  mov     eax, esi
0x1800066f9  add     rsp, 0B8h
0x180006700  pop     r13
0x180006702  pop     rdi
0x180006703  pop     rsi
0x180006704  pop     rbp
0x180006705  retn
0x180006707  mov     rdi, [rsp+0D8h+arg_30]
0x18000670f  jmp     short loc_180006698
0x180006711  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180006716  mov     esi, eax
0x180006718  test    eax, eax
0x18000671a  jns     loc_180006507
0x180006720  test    esi, esi
0x180006722  jmp     loc_180006609
0x180006727  mov     ecx, 10h; Size
0x18000672c  call    cs:__imp_malloc
0x180006733  nop     dword ptr [rax+rax+00h]
0x180006738  test    rax, rax
0x18000673b  jz      loc_1800066AB
0x180006741  lea     rcx, ??_7?$CRundownHelper@VCSsdpSearchRequest@@@@6B@; const CRundownHelper<CSsdpSearchRequest>::`vftable'
0x180006748  mov     rdx, rax; struct CRundownHelperBase *
0x18000674b  mov     [rax], rcx
0x18000674e  mov     rcx, [rdi]
0x180006751  mov     [rax+8], rcx
0x180006755  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x18000675c  call    ?HrAddItemInternal@CSsdpRundownSupport@@AEAAJPEAVCRundownHelperBase@@@Z; CSsdpRundownSupport::HrAddItemInternal(CRundownHelperBase *)
0x180006761  jmp     loc_1800066AB
0x180006766  mov     eax, 80004003h
0x18000676b  jmp     short loc_1800066F9
0x18000676d  mov     eax, 80070057h
0x180006772  jmp     short loc_1800066F9
0x180006774  mov     eax, 80070015h
0x180006779  jmp     loc_1800066F9
0x18000677e  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180006783  mov     esi, eax
0x180006785  jmp     loc_180006573
0x18000678a  mov     rax, [rsp+0D8h+var_48]
0x180006792  lea     rcx, [rsp+0D8h+var_98]; struct _SSDP_REQUEST *
0x180006797  mov     esi, 8007000Eh
0x18000679c  mov     [rsp+0D8h+var_90], r15
0x1800067a1  mov     [rax+20h], r15
0x1800067a5  mov     [rax+28h], r15
0x1800067a9  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x1800067ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067b5  cmp     rcx, rbp
0x1800067b8  jz      loc_18000660F
0x1800067be  test    byte ptr [rcx+1Ch], 1
0x1800067c2  jz      loc_18000660F
0x1800067c8  mov     rcx, [rcx+10h]
0x1800067cc  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x1800067d3  mov     edx, 0Ah
0x1800067d8  mov     r9d, esi
0x1800067db  call    WPP_SF_d
0x1800067e0  jmp     loc_18000660F
0x1800067e5  mov     [r12+100h], r15d
0x1800067ed  jmp     loc_180006720
0x1800067f2  mov     esi, 80070015h
0x1800067f7  jmp     loc_180006707
0x1800067fc  lea     rcx, [r12+98h]; lpCriticalSection
0x180006804  call    cs:__imp_LeaveCriticalSection
0x18000680b  nop     dword ptr [rax+rax+00h]
0x180006810  mov     esi, 80070057h
0x180006815  jmp     loc_1800063CA
0x18000681a  mov     rcx, rbx
0x18000681d  call    ??1Node@?$CUList@VCSsdpSearchRequest@@@@QEAA@XZ; CUList<CSsdpSearchRequest>::Node::~Node(void)
0x180006822  mov     rcx, rbx; Block
0x180006825  call    cs:__imp_free
0x18000682c  nop     dword ptr [rax+rax+00h]
0x180006831  jmp     loc_1800066EF
```
