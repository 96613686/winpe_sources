# CSsdpSearchResponse::HrCreate(unsigned __int64 *,sockaddr *,char *,long)

- ea: `0x18001de28`
- end: `0x18001dfca`
- name: `?HrCreate@CSsdpSearchResponse@@SAJPEA_KPEAUsockaddr@@PEADJ@Z`
- size: `418`
- prototype: `__int64 __fastcall(unsigned __int64 *, struct sockaddr *, char *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800029b0`

## callees

- `0x18000168c`
- `0x1800140e0`
- `0x18001de28`
- `0x18001dfd0`
- `0x180020124`
- `0x1800211d8`
- `0x180023f68`
- `0x1800255a8`
- `0x180030050`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001de59`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001df68`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001df86`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001de59`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001df68`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001df86`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001de9b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001de9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001df57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001df57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001deeb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001deeb`

## pseudocode

```c
__int64 __fastcall CSsdpSearchResponse::HrCreate(unsigned __int64 *a1, struct sockaddr *a2, char *a3, int a4)
{
  int v8; // ebx
  LPCSTR v9; // rcx
  CSsdpSearchResponse *v10; // rax
  CSsdpSearchResponse *v11; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  DWORD v13; // esi

  if ( CThrottleByTime::AllowUse((CThrottleByTime *)a1) )
  {
    v10 = (CSsdpSearchResponse *)malloc(0x130u);
    if ( v10 && (v11 = CSsdpSearchResponse::CSsdpSearchResponse(v10), (v12 = (struct _RTL_CRITICAL_SECTION *)v11) != 0) )
    {
      v8 = CSsdpSearchResponse::HrInitialize(v11, a1, a2, a3, a4);
      if ( v8 < 0 )
      {
        free(a3);
      }
      else
      {
        v13 = CSsdpSearchResponse::CalculateDelay((CSsdpSearchResponse *)v12);
        EnterCriticalSection(v12 + 3);
        v8 = CStaleWorkItemsTracking::HrAddWorkItem(&CSsdpSearchResponse::s_WorkItemTracking, (struct CWorkItem *)v12);
        if ( v8 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b0629846ed6b35a3ac9171aa0697871c_Traceguids, v13);
          v8 = CTimerBase::HrSetTimer(&v12->OwningThread, v13);
          if ( v8 < 0 )
            CStaleWorkItemsTracking::HrRemoveWorkItem(&CSsdpSearchResponse::s_WorkItemTracking, v12, 0);
        }
        LeaveCriticalSection(v12 + 3);
        if ( v8 >= 0 )
        {
          if ( !v8 )
            return (unsigned int)v8;
          goto LABEL_20;
        }
      }
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v12->DebugInfo->Type)(v12, 1);
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
0x18001de28  push    rbx
0x18001de2a  push    rbp
0x18001de2b  push    rsi
0x18001de2c  push    rdi
0x18001de2d  push    r14
0x18001de2f  push    r15
0x18001de31  sub     rsp, 38h
0x18001de35  mov     ebx, r9d
0x18001de38  mov     rsi, r8
0x18001de3b  mov     rbp, rdx
0x18001de3e  mov     r14, rcx
0x18001de41  call    ?AllowUse@CThrottleByTime@@QEAA_NXZ; CThrottleByTime::AllowUse(void)
0x18001de46  lea     r15, WPP_GLOBAL_Control
0x18001de4d  test    al, al
0x18001de4f  jnz     short loc_18001DE96
0x18001de51  mov     rcx, rsi; Block
0x18001de54  mov     ebx, 80004005h
0x18001de59  call    cs:__imp_free
0x18001de5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de66  cmp     rcx, r15
0x18001de69  jz      loc_18001DFBB
0x18001de6f  test    byte ptr [rcx+1Ch], 1
0x18001de73  jz      loc_18001DF98
0x18001de79  mov     rcx, [rcx+10h]
0x18001de7d  lea     r8, WPP_b0629846ed6b35a3ac9171aa0697871c_Traceguids
0x18001de84  mov     edx, 0Ah
0x18001de89  mov     r9d, ebx
0x18001de8c  call    WPP_SF_d
0x18001de91  jmp     loc_18001DF91
0x18001de96  mov     ecx, 130h; Size
0x18001de9b  call    cs:__imp_malloc
0x18001dea1  test    rax, rax
0x18001dea4  jz      loc_18001DF83
0x18001deaa  mov     rcx, rax; this
0x18001dead  call    ??0CSsdpSearchResponse@@AEAA@XZ; CSsdpSearchResponse::CSsdpSearchResponse(void)
0x18001deb2  mov     rdi, rax
0x18001deb5  test    rax, rax
0x18001deb8  jz      loc_18001DF83
0x18001debe  mov     r9, rsi; char *
0x18001dec1  mov     [rsp+68h+var_48], ebx; int
0x18001dec5  mov     r8, rbp; struct sockaddr *
0x18001dec8  mov     rdx, r14; unsigned __int64 *
0x18001decb  mov     rcx, rax; this
0x18001dece  call    ?HrInitialize@CSsdpSearchResponse@@AEAAJPEA_KPEAUsockaddr@@PEADJ@Z; CSsdpSearchResponse::HrInitialize(unsigned __int64 *,sockaddr *,char *,long)
0x18001ded3  mov     ebx, eax
0x18001ded5  test    eax, eax
0x18001ded7  js      loc_18001DF65
0x18001dedd  mov     rcx, rdi; this
0x18001dee0  call    ?CalculateDelay@CSsdpSearchResponse@@AEAAJXZ; CSsdpSearchResponse::CalculateDelay(void)
0x18001dee5  lea     rcx, [rdi+78h]; lpCriticalSection
0x18001dee9  mov     esi, eax
0x18001deeb  call    cs:__imp_EnterCriticalSection
0x18001def1  mov     rdx, rdi; struct CWorkItem *
0x18001def4  lea     rcx, ?s_WorkItemTracking@CSsdpSearchResponse@@2VCStaleWorkItemsTracking@@A; lpCriticalSection
0x18001defb  call    ?HrAddWorkItem@CStaleWorkItemsTracking@@QEAAJPEAVCWorkItem@@@Z; CStaleWorkItemsTracking::HrAddWorkItem(CWorkItem *)
0x18001df00  mov     ebx, eax
0x18001df02  test    eax, eax
0x18001df04  js      short loc_18001DF53
0x18001df06  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df0d  cmp     rcx, r15
0x18001df10  jz      short loc_18001DF30
0x18001df12  test    byte ptr [rcx+1Ch], 8
0x18001df16  jz      short loc_18001DF30
0x18001df18  mov     rcx, [rcx+10h]
0x18001df1c  lea     r8, WPP_b0629846ed6b35a3ac9171aa0697871c_Traceguids
0x18001df23  mov     edx, 0Bh
0x18001df28  mov     r9d, esi
0x18001df2b  call    WPP_SF_d
0x18001df30  lea     rcx, [rdi+10h]; Parameter
0x18001df34  mov     edx, esi; DueTime
0x18001df36  call    ?HrSetTimer@CTimerBase@@QEAAJK@Z; CTimerBase::HrSetTimer(ulong)
0x18001df3b  mov     ebx, eax
0x18001df3d  test    eax, eax
0x18001df3f  jns     short loc_18001DF53
0x18001df41  xor     r8d, r8d; int
0x18001df44  lea     rcx, ?s_WorkItemTracking@CSsdpSearchResponse@@2VCStaleWorkItemsTracking@@A; lpCriticalSection
0x18001df4b  mov     rdx, rdi; pv
0x18001df4e  call    ?HrRemoveWorkItem@CStaleWorkItemsTracking@@QEAAJPEAVCWorkItem@@H@Z; CStaleWorkItemsTracking::HrRemoveWorkItem(CWorkItem *,int)
0x18001df53  lea     rcx, [rdi+78h]; lpCriticalSection
0x18001df57  call    cs:__imp_LeaveCriticalSection
0x18001df5d  test    ebx, ebx
0x18001df5f  js      short loc_18001DF6E
0x18001df61  jnz     short loc_18001DF91
0x18001df63  jmp     short loc_18001DFBB
0x18001df65  mov     rcx, rsi; Block
0x18001df68  call    cs:__imp_free
0x18001df6e  mov     rax, [rdi]
0x18001df71  mov     edx, 1
0x18001df76  mov     rcx, rdi
0x18001df79  mov     rax, [rax]
0x18001df7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df81  jmp     short loc_18001DF91
0x18001df83  mov     rcx, rsi; Block
0x18001df86  call    cs:__imp_free
0x18001df8c  mov     ebx, 8007000Eh
0x18001df91  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df98  cmp     rcx, r15
0x18001df9b  jz      short loc_18001DFBB
0x18001df9d  test    byte ptr [rcx+1Ch], 1
0x18001dfa1  jz      short loc_18001DFBB
0x18001dfa3  mov     rcx, [rcx+10h]
0x18001dfa7  lea     r8, WPP_b0629846ed6b35a3ac9171aa0697871c_Traceguids
0x18001dfae  mov     edx, 0Ch
0x18001dfb3  mov     r9d, ebx
0x18001dfb6  call    WPP_SF_d
0x18001dfbb  mov     eax, ebx
0x18001dfbd  add     rsp, 38h
0x18001dfc1  pop     r15
0x18001dfc3  pop     r14
0x18001dfc5  pop     rdi
0x18001dfc6  pop     rsi
0x18001dfc7  pop     rbp
0x18001dfc8  pop     rbx
0x18001dfc9  retn
```
