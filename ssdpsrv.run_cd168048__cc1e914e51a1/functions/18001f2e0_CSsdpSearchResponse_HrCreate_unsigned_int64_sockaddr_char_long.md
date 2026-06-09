# CSsdpSearchResponse::HrCreate(unsigned __int64 *,sockaddr *,char *,long)

- ea: `0x18001f2e0`
- end: `0x18001f4a7`
- name: `?HrCreate@CSsdpSearchResponse@@SAJPEA_KPEAUsockaddr@@PEADJ@Z`
- size: `455`
- prototype: `__int64 __fastcall(unsigned __int64 *, struct sockaddr *, char *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800040e0`

## callees

- `0x180014988`
- `0x180016620`
- `0x18001f2e0`
- `0x18001f4b0`
- `0x1800217b4`
- `0x180022980`
- `0x1800259d0`
- `0x1800271fc`
- `0x1800323a0`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f311`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f438`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f45c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f311`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f438`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f45c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f359`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f359`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f421`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f421`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f3af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f3af`

## pseudocode

```c
__int64 __fastcall CSsdpSearchResponse::HrCreate(unsigned __int64 *a1, struct sockaddr *a2, char *a3, int a4)
{
  int v8; // ebx
  LPCSTR v9; // rcx
  CSsdpSearchResponse *v10; // rax
  CSsdpSearchResponse *v11; // rax
  CSsdpSearchResponse *v12; // rdi
  DWORD v13; // esi

  if ( CThrottleByTime::AllowUse((CThrottleByTime *)a1) )
  {
    v10 = (CSsdpSearchResponse *)malloc(0x130u);
    if ( v10 && (v11 = CSsdpSearchResponse::CSsdpSearchResponse(v10), (v12 = v11) != 0) )
    {
      v8 = CSsdpSearchResponse::HrInitialize(v11, a1, a2, a3, a4);
      if ( v8 < 0 )
      {
        free(a3);
      }
      else
      {
        v13 = CSsdpSearchResponse::CalculateDelay(v12);
        EnterCriticalSection((LPCRITICAL_SECTION)v12 + 3);
        v8 = CStaleWorkItemsTracking::HrAddWorkItem(&CSsdpSearchResponse::s_WorkItemTracking, v12);
        if ( v8 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b0629846ed6b35a3ac9171aa0697871c_Traceguids, v13);
          v8 = CTimerBase::HrSetTimer((char *)v12 + 16, v13);
          if ( v8 < 0 )
            CStaleWorkItemsTracking::HrRemoveWorkItem(&CSsdpSearchResponse::s_WorkItemTracking, v12, 0);
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)v12 + 3);
        if ( v8 >= 0 )
        {
          if ( !v8 )
            return (unsigned int)v8;
          goto LABEL_20;
        }
      }
      (**(void (__fastcall ***)(CSsdpSearchResponse *, __int64))v12)(v12, 1);
    }
    else
    {
      free(a3);
      v8 = -2147024882;
    }
LABEL_20:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  v8 = -2147467259;
  free(a3);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
    return (unsigned int)v8;
  if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b0629846ed6b35a3ac9171aa0697871c_Traceguids, 2147500037LL);
    goto LABEL_20;
  }
LABEL_21:
  if ( v9 != (LPCSTR)&WPP_GLOBAL_Control && (v9[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v9 + 2), 12, WPP_b0629846ed6b35a3ac9171aa0697871c_Traceguids, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001f2e0  push    rbx
0x18001f2e2  push    rbp
0x18001f2e3  push    rsi
0x18001f2e4  push    rdi
0x18001f2e5  push    r14
0x18001f2e7  push    r15
0x18001f2e9  sub     rsp, 38h
0x18001f2ed  mov     ebx, r9d
0x18001f2f0  mov     rsi, r8
0x18001f2f3  mov     rbp, rdx
0x18001f2f6  mov     r14, rcx
0x18001f2f9  call    ?AllowUse@CThrottleByTime@@QEAA_NXZ; CThrottleByTime::AllowUse(void)
0x18001f2fe  lea     r15, WPP_GLOBAL_Control
0x18001f305  test    al, al
0x18001f307  jnz     short loc_18001F354
0x18001f309  mov     rcx, rsi; Block
0x18001f30c  mov     ebx, 80004005h
0x18001f311  call    cs:__imp_free
0x18001f318  nop     dword ptr [rax+rax+00h]
0x18001f31d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f324  cmp     rcx, r15
0x18001f327  jz      loc_18001F497
0x18001f32d  test    byte ptr [rcx+1Ch], 1
0x18001f331  jz      loc_18001F474
0x18001f337  mov     rcx, [rcx+10h]
0x18001f33b  lea     r8, WPP_b0629846ed6b35a3ac9171aa0697871c_Traceguids
0x18001f342  mov     edx, 0Ah
0x18001f347  mov     r9d, ebx
0x18001f34a  call    WPP_SF_d
0x18001f34f  jmp     loc_18001F46D
0x18001f354  mov     ecx, 130h; Size
0x18001f359  call    cs:__imp_malloc
0x18001f360  nop     dword ptr [rax+rax+00h]
0x18001f365  test    rax, rax
0x18001f368  jz      loc_18001F459
0x18001f36e  mov     rcx, rax; this
0x18001f371  call    ??0CSsdpSearchResponse@@AEAA@XZ; CSsdpSearchResponse::CSsdpSearchResponse(void)
0x18001f376  mov     rdi, rax
0x18001f379  test    rax, rax
0x18001f37c  jz      loc_18001F459
0x18001f382  mov     r9, rsi; char *
0x18001f385  mov     [rsp+68h+var_48], ebx; int
0x18001f389  mov     r8, rbp; struct sockaddr *
0x18001f38c  mov     rdx, r14; unsigned __int64 *
0x18001f38f  mov     rcx, rax; this
0x18001f392  call    ?HrInitialize@CSsdpSearchResponse@@AEAAJPEA_KPEAUsockaddr@@PEADJ@Z; CSsdpSearchResponse::HrInitialize(unsigned __int64 *,sockaddr *,char *,long)
0x18001f397  mov     ebx, eax
0x18001f399  test    eax, eax
0x18001f39b  js      loc_18001F435
0x18001f3a1  mov     rcx, rdi; this
0x18001f3a4  call    ?CalculateDelay@CSsdpSearchResponse@@AEAAJXZ; CSsdpSearchResponse::CalculateDelay(void)
0x18001f3a9  lea     rcx, [rdi+78h]; lpCriticalSection
0x18001f3ad  mov     esi, eax
0x18001f3af  call    cs:__imp_EnterCriticalSection
0x18001f3b6  nop     dword ptr [rax+rax+00h]
0x18001f3bb  mov     rdx, rdi; struct CWorkItem *
0x18001f3be  lea     rcx, ?s_WorkItemTracking@CSsdpSearchResponse@@2VCStaleWorkItemsTracking@@A; lpCriticalSection
0x18001f3c5  call    ?HrAddWorkItem@CStaleWorkItemsTracking@@QEAAJPEAVCWorkItem@@@Z; CStaleWorkItemsTracking::HrAddWorkItem(CWorkItem *)
0x18001f3ca  mov     ebx, eax
0x18001f3cc  test    eax, eax
0x18001f3ce  js      short loc_18001F41D
0x18001f3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f3d7  cmp     rcx, r15
0x18001f3da  jz      short loc_18001F3FA
0x18001f3dc  test    byte ptr [rcx+1Ch], 8
0x18001f3e0  jz      short loc_18001F3FA
0x18001f3e2  mov     rcx, [rcx+10h]
0x18001f3e6  lea     r8, WPP_b0629846ed6b35a3ac9171aa0697871c_Traceguids
0x18001f3ed  mov     edx, 0Bh
0x18001f3f2  mov     r9d, esi
0x18001f3f5  call    WPP_SF_d
0x18001f3fa  lea     rcx, [rdi+10h]; Parameter
0x18001f3fe  mov     edx, esi; DueTime
0x18001f400  call    ?HrSetTimer@CTimerBase@@QEAAJK@Z; CTimerBase::HrSetTimer(ulong)
0x18001f405  mov     ebx, eax
0x18001f407  test    eax, eax
0x18001f409  jns     short loc_18001F41D
0x18001f40b  xor     r8d, r8d; int
0x18001f40e  lea     rcx, ?s_WorkItemTracking@CSsdpSearchResponse@@2VCStaleWorkItemsTracking@@A; lpCriticalSection
0x18001f415  mov     rdx, rdi; pv
0x18001f418  call    ?HrRemoveWorkItem@CStaleWorkItemsTracking@@QEAAJPEAVCWorkItem@@H@Z; CStaleWorkItemsTracking::HrRemoveWorkItem(CWorkItem *,int)
0x18001f41d  lea     rcx, [rdi+78h]; lpCriticalSection
0x18001f421  call    cs:__imp_LeaveCriticalSection
0x18001f428  nop     dword ptr [rax+rax+00h]
0x18001f42d  test    ebx, ebx
0x18001f42f  js      short loc_18001F444
0x18001f431  jnz     short loc_18001F46D
0x18001f433  jmp     short loc_18001F497
0x18001f435  mov     rcx, rsi; Block
0x18001f438  call    cs:__imp_free
0x18001f43f  nop     dword ptr [rax+rax+00h]
0x18001f444  mov     rax, [rdi]
0x18001f447  mov     edx, 1
0x18001f44c  mov     rcx, rdi
0x18001f44f  mov     rax, [rax]
0x18001f452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f457  jmp     short loc_18001F46D
0x18001f459  mov     rcx, rsi; Block
0x18001f45c  call    cs:__imp_free
0x18001f463  nop     dword ptr [rax+rax+00h]
0x18001f468  mov     ebx, 8007000Eh
0x18001f46d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f474  cmp     rcx, r15
0x18001f477  jz      short loc_18001F497
0x18001f479  test    byte ptr [rcx+1Ch], 1
0x18001f47d  jz      short loc_18001F497
0x18001f47f  mov     rcx, [rcx+10h]
0x18001f483  lea     r8, WPP_b0629846ed6b35a3ac9171aa0697871c_Traceguids
0x18001f48a  mov     edx, 0Ch
0x18001f48f  mov     r9d, ebx
0x18001f492  call    WPP_SF_d
0x18001f497  mov     eax, ebx
0x18001f499  add     rsp, 38h
0x18001f49d  pop     r15
0x18001f49f  pop     r14
0x18001f4a1  pop     rdi
0x18001f4a2  pop     rsi
0x18001f4a3  pop     rbp
0x18001f4a4  pop     rbx
0x18001f4a5  retn
```
