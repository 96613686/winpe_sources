# CSsdpSearchRequestManager::HrCreateAsync(char *,int,int,ulong,_GUID,CSsdpSearchRequest * *)

- ea: `0x1800050b0`
- end: `0x180005543`
- name: `?HrCreateAsync@CSsdpSearchRequestManager@@QEAAJPEADHHKU_GUID@@PEAPEAVCSsdpSearchRequest@@@Z`
- size: `1171`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, char *, int, int, unsigned int, struct _GUID *, struct CSsdpSearchRequest **)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001e8e0`

## callees

- `0x180004340`
- `0x1800050b0`
- `0x18000554c`
- `0x180005588`
- `0x180005654`
- `0x180006d70`
- `0x1800079ac`
- `0x1800097f0`
- `0x18000a1d0`
- `0x180013924`
- `0x18001e63c`
- `0x1800255a8`
- `0x18002735c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800051e1`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800051e1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000530c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005538`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000530c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005538`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000510b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000544e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000510b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000544e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005347`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000551d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005347`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000551d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000512b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800053db`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000512b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800053db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005194`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005358`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005194`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005358`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005292`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180005292`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005232`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005256`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005232`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005256`

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
0x1800050b0  mov     r11, rsp
0x1800050b3  push    rbp
0x1800050b4  push    rsi
0x1800050b5  push    rdi
0x1800050b6  push    r13
0x1800050b8  sub     rsp, 0B8h
0x1800050bf  cmp     [rsp+0D8h+arg_30], 0
0x1800050c8  mov     esi, r9d
0x1800050cb  mov     ebp, r8d
0x1800050ce  mov     rdi, rdx
0x1800050d1  mov     r13, rcx
0x1800050d4  jz      loc_180005482
0x1800050da  test    rdx, rdx
0x1800050dd  jz      loc_180005489
0x1800050e3  mov     eax, [rcx+2A0h]
0x1800050e9  test    eax, eax
0x1800050eb  jnz     loc_180005490
0x1800050f1  mov     [r11+8], rbx
0x1800050f5  mov     ecx, 148h; Size
0x1800050fa  mov     [r11+10h], r12
0x1800050fe  mov     [r11+18h], r14
0x180005102  mov     [r11-28h], r15
0x180005106  movaps  xmmword ptr [r11-38h], xmm6
0x18000510b  call    cs:__imp_malloc
0x180005111  xor     r15d, r15d
0x180005114  mov     rbx, rax
0x180005117  test    rax, rax
0x18000511a  jnz     short loc_18000516F
0x18000511c  mov     ebx, r15d
0x18000511f  mov     esi, 8007000Eh
0x180005124  mov     rcx, [r13+2A8h]; hEvent
0x18000512b  call    cs:__imp_SetEvent
0x180005131  lea     rbp, WPP_GLOBAL_Control
0x180005138  mov     rcx, cs:WPP_GLOBAL_Control
0x18000513f  cmp     rcx, rbp
0x180005142  jz      loc_1800053E9
0x180005148  test    byte ptr [rcx+1Ch], 1
0x18000514c  jz      loc_1800053E9
0x180005152  mov     rcx, [rcx+10h]
0x180005156  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x18000515d  mov     edx, 28h ; '('
0x180005162  mov     r9d, esi
0x180005165  call    WPP_SF_d
0x18000516a  jmp     loc_1800053E9
0x18000516f  lea     r12, [rax+8]
0x180005173  mov     [rax], r15
0x180005176  mov     rcx, r12; this
0x180005179  call    ??0CSsdpSearchRequest@@QEAA@XZ; CSsdpSearchRequest::CSsdpSearchRequest(void)
0x18000517e  mov     rax, [rsp+0D8h+arg_28]
0x180005186  lea     rcx, [r12+98h]; lpCriticalSection
0x18000518e  mov     [rbx], r15
0x180005191  movaps  xmm6, xmmword ptr [rax]
0x180005194  call    cs:__imp_EnterCriticalSection
0x18000519a  lea     rax, [r13+40h]
0x18000519e  test    rax, rax
0x1800051a1  jz      loc_180005515
0x1800051a7  mov     [r12+108h], rax
0x1800051af  lea     rdx, Str2; "ssdp:all"
0x1800051b6  mov     eax, [rsp+0D8h+arg_20]
0x1800051bd  mov     rcx, rdi
0x1800051c0  mov     [r12+114h], eax
0x1800051c8  mov     [r12+90h], ebp
0x1800051d0  mov     [r12+94h], esi
0x1800051d8  movups  xmmword ptr [r12+118h], xmm6
0x1800051e1  call    cs:__imp__o__stricmp
0x1800051e7  mov     ecx, r15d
0x1800051ea  mov     rdx, rdi; char *
0x1800051ed  test    eax, eax
0x1800051ef  setz    cl
0x1800051f2  mov     [r12+128h], ecx
0x1800051fa  lea     rcx, [r12+8]; this
0x1800051ff  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x180005204  lea     rbp, WPP_GLOBAL_Control
0x18000520b  mov     esi, eax
0x18000520d  test    eax, eax
0x18000520f  js      loc_180005442
0x180005215  lea     rdx, [r12+12Ch]; struct _TypeVersion *
0x18000521d  mov     rcx, rdi; char *
0x180005220  call    ?SsdpGetTypeVersion@@YAXPEBDPEAU_TypeVersion@@@Z; SsdpGetTypeVersion(char const *,_TypeVersion *)
0x180005225  xor     r9d, r9d; lpName
0x180005228  xor     r8d, r8d; bInitialState
0x18000522b  mov     edx, 1; bManualReset
0x180005230  xor     ecx, ecx; lpEventAttributes
0x180005232  call    cs:__imp_CreateEventA
0x180005238  mov     [r12+0E8h], rax
0x180005240  test    rax, rax
0x180005243  jz      loc_180005433
0x180005249  xor     r9d, r9d; lpName
0x18000524c  xor     r8d, r8d; bInitialState
0x18000524f  mov     edx, 1; bManualReset
0x180005254  xor     ecx, ecx; lpEventAttributes
0x180005256  call    cs:__imp_CreateEventA
0x18000525c  mov     [r12+0F0h], rax
0x180005264  test    rax, rax
0x180005267  jnz     short loc_180005278
0x180005269  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000526e  mov     esi, eax
0x180005270  test    eax, eax
0x180005272  js      loc_180005442
0x180005278  mov     [rsp+0D8h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180005280  xor     r9d, r9d; lpName
0x180005283  xor     edx, edx; lInitialCount
0x180005285  mov     [rsp+0D8h+dwFlags], r15d; dwFlags
0x18000528a  xor     ecx, ecx; lpSemaphoreAttributes
0x18000528c  mov     r8d, 1F4h; lMaximumCount
0x180005292  call    cs:__imp_CreateSemaphoreExW
0x180005298  mov     [r12+0F8h], rax
0x1800052a0  test    rax, rax
0x1800052a3  jz      loc_180005497
0x1800052a9  test    esi, esi
0x1800052ab  js      loc_180005339
0x1800052b1  xor     edx, edx; Val
0x1800052b3  lea     rcx, [rsp+0D8h+var_98]; void *
0x1800052b8  mov     r8d, 58h ; 'X'; Size
0x1800052be  call    memset_0
0x1800052c3  mov     rdx, rdi; char *
0x1800052c6  lea     rcx, [rsp+0D8h+var_98]; struct _SSDP_REQUEST *
0x1800052cb  call    ?HrInitializeSsdpSearchRequest@CSsdpSearchRequest@@SAJPEAU_SSDP_REQUEST@@PEAD@Z; CSsdpSearchRequest::HrInitializeSsdpSearchRequest(_SSDP_REQUEST *,char *)
0x1800052d0  mov     esi, eax
0x1800052d2  test    eax, eax
0x1800052d4  js      loc_180005442
0x1800052da  lea     rdx, [rsp+0D8h+Block]; char **
0x1800052df  mov     [rsp+0D8h+Block], r15
0x1800052e4  lea     rcx, [rsp+0D8h+var_98]; struct _SSDP_REQUEST *
0x1800052e9  call    ?ComposeSsdpRequest@@YAHPEBU_SSDP_REQUEST@@PEAPEAD@Z; ComposeSsdpRequest(_SSDP_REQUEST const *,char * *)
0x1800052ee  test    eax, eax
0x1800052f0  jz      loc_1800054A3
0x1800052f6  mov     rdx, [rsp+0D8h+Block]; char *
0x1800052fb  lea     rcx, [r12+10h]; this
0x180005300  call    ?HrAssign@CUString@@QEAAJPEBD@Z; CUString::HrAssign(char const *)
0x180005305  mov     rcx, [rsp+0D8h+Block]; Block
0x18000530a  mov     esi, eax
0x18000530c  call    cs:__imp_free
0x180005312  mov     rax, [rsp+0D8h+var_48]
0x18000531a  lea     rcx, [rsp+0D8h+var_98]; struct _SSDP_REQUEST *
0x18000531f  mov     [rsp+0D8h+var_90], r15
0x180005324  mov     [rax+20h], r15
0x180005328  mov     [rax+28h], r15
0x18000532c  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x180005331  test    esi, esi
0x180005333  jns     loc_1800054FE
0x180005339  jnz     loc_1800054C7
0x18000533f  lea     rcx, [r12+98h]; lpCriticalSection
0x180005347  call    cs:__imp_LeaveCriticalSection
0x18000534d  test    esi, esi
0x18000534f  js      loc_1800053D4
0x180005355  mov     rcx, r13; lpCriticalSection
0x180005358  call    cs:__imp_EnterCriticalSection
0x18000535e  mov     rax, [r13+28h]
0x180005362  mov     ecx, r15d
0x180005365  test    rax, rax
0x180005368  jz      short loc_180005386
0x18000536a  nop     word ptr [rax+rax+00h]
0x180005370  mov     rax, [rax]
0x180005373  inc     ecx
0x180005375  test    rax, rax
0x180005378  jnz     short loc_180005370
0x18000537a  cmp     ecx, 0C8h
0x180005380  jge     loc_18000550B
0x180005386  mov     rcx, r12; this
0x180005389  call    ?HrStart@CSsdpSearchRequest@@QEAAJXZ; CSsdpSearchRequest::HrStart(void)
0x18000538e  mov     esi, eax
0x180005390  test    eax, eax
0x180005392  js      loc_180005429
0x180005398  mov     rdx, rbx
0x18000539b  nop     dword ptr [rax+rax+00h]
0x1800053a0  mov     rcx, [rdx]
0x1800053a3  lea     r8, [rdx]
0x1800053a6  mov     rdx, rcx
0x1800053a9  test    rcx, rcx
0x1800053ac  jnz     short loc_1800053A0
0x1800053ae  mov     rax, [r13+28h]
0x1800053b2  mov     rdi, [rsp+0D8h+arg_30]
0x1800053ba  mov     [r8], rax
0x1800053bd  mov     [r13+28h], rbx
0x1800053c1  mov     rbx, r15
0x1800053c4  mov     [rdi], r12
0x1800053c7  mov     rcx, r13; lpCriticalSection
0x1800053ca  call    cs:__imp_LeaveCriticalSection
0x1800053d0  test    esi, esi
0x1800053d2  jns     short loc_180005449
0x1800053d4  mov     rcx, [r13+2A8h]; hEvent
0x1800053db  call    cs:__imp_SetEvent
0x1800053e1  test    esi, esi
0x1800053e3  jnz     loc_180005138
0x1800053e9  movaps  xmm6, [rsp+0D8h+var_38]
0x1800053f1  mov     r15, [rsp+0D8h+var_28]
0x1800053f9  mov     r14, [rsp+0D8h+arg_10]
0x180005401  mov     r12, [rsp+0D8h+arg_8]
0x180005409  test    rbx, rbx
0x18000540c  jnz     loc_18000552D
0x180005412  mov     rbx, [rsp+0D8h+arg_0]
0x18000541a  mov     eax, esi
0x18000541c  add     rsp, 0B8h
0x180005423  pop     r13
0x180005425  pop     rdi
0x180005426  pop     rsi
0x180005427  pop     rbp
0x180005428  retn
0x180005429  mov     rdi, [rsp+0D8h+arg_30]
0x180005431  jmp     short loc_1800053C7
0x180005433  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180005438  mov     esi, eax
0x18000543a  test    eax, eax
0x18000543c  jns     loc_180005249
0x180005442  test    esi, esi
0x180005444  jmp     loc_180005339
0x180005449  mov     ecx, 10h; Size
0x18000544e  call    cs:__imp_malloc
0x180005454  test    rax, rax
0x180005457  jz      loc_1800053D4
0x18000545d  lea     rcx, ??_7?$CRundownHelper@VCSsdpSearchRequest@@@@6B@; const CRundownHelper<CSsdpSearchRequest>::`vftable'
0x180005464  mov     rdx, rax; struct CRundownHelperBase *
0x180005467  mov     [rax], rcx
0x18000546a  mov     rcx, [rdi]
0x18000546d  mov     [rax+8], rcx
0x180005471  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x180005478  call    ?HrAddItemInternal@CSsdpRundownSupport@@AEAAJPEAVCRundownHelperBase@@@Z; CSsdpRundownSupport::HrAddItemInternal(CRundownHelperBase *)
0x18000547d  jmp     loc_1800053D4
0x180005482  mov     eax, 80004003h
0x180005487  jmp     short loc_18000541C
0x180005489  mov     eax, 80070057h
0x18000548e  jmp     short loc_18000541C
0x180005490  mov     eax, 80070015h
0x180005495  jmp     short loc_18000541C
0x180005497  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18000549c  mov     esi, eax
0x18000549e  jmp     loc_1800052A9
0x1800054a3  mov     rax, [rsp+0D8h+var_48]
0x1800054ab  lea     rcx, [rsp+0D8h+var_98]; struct _SSDP_REQUEST *
0x1800054b0  mov     esi, 8007000Eh
0x1800054b5  mov     [rsp+0D8h+var_90], r15
0x1800054ba  mov     [rax+20h], r15
0x1800054be  mov     [rax+28h], r15
0x1800054c2  call    ?FreeSsdpRequest@@YAXPEAU_SSDP_REQUEST@@@Z; FreeSsdpRequest(_SSDP_REQUEST *)
0x1800054c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800054ce  cmp     rcx, rbp
0x1800054d1  jz      loc_18000533F
0x1800054d7  test    byte ptr [rcx+1Ch], 1
0x1800054db  jz      loc_18000533F
0x1800054e1  mov     rcx, [rcx+10h]
0x1800054e5  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x1800054ec  mov     edx, 0Ah
0x1800054f1  mov     r9d, esi
0x1800054f4  call    WPP_SF_d
0x1800054f9  jmp     loc_18000533F
0x1800054fe  mov     [r12+100h], r15d
0x180005506  jmp     loc_180005442
0x18000550b  mov     esi, 80070015h
0x180005510  jmp     loc_180005429
0x180005515  lea     rcx, [r12+98h]; lpCriticalSection
0x18000551d  call    cs:__imp_LeaveCriticalSection
0x180005523  mov     esi, 80070057h
0x180005528  jmp     loc_180005124
0x18000552d  mov     rcx, rbx
0x180005530  call    ??1Node@?$CUList@VCSsdpSearchRequest@@@@QEAA@XZ; CUList<CSsdpSearchRequest>::Node::~Node(void)
0x180005535  mov     rcx, rbx; Block
0x180005538  call    cs:__imp_free
0x18000553e  jmp     loc_180005412
```
