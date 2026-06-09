# BackgroundActivation::AddPersistedItem(WpnBackgroundTriggerType,void *,_GUID const *,IAppInfo *)

- ea: `0x180022fc4`
- end: `0x1800232fe`
- name: `?AddPersistedItem@BackgroundActivation@@AEAAJW4WpnBackgroundTriggerType@@PEAXPEBU_GUID@@PEAVIAppInfo@@@Z`
- size: `826`
- prototype: `int __high(enum WpnBackgroundTriggerType, void *, const struct _GUID *, struct IAppInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180022ccc`

## callees

- `0x180022fc4`
- `0x180023304`
- `0x18002ee38`
- `0x1800af0a4`
- `0x1800bc541`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023066`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180023066`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023058`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800230f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023058`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800230f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800230fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800230fe`
- `ntdll!RtlNtStatusToDosError` at `0x180023119`
- `ntdll!RtlNtStatusToDosError` at `0x180023119`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180023035`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180023035`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180023021`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180023021`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryBrokeredEvent` at `0x180022ffd`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtQueryBrokeredEvent` at `0x180022ffd`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1800230dd`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtFreeMemory` at `0x1800230dd`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x180023262`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x180023262`

## pseudocode

```c
__int64 __fastcall BackgroundActivation::AddPersistedItem(
        __int64 a1,
        unsigned int a2,
        void *a3,
        __int64 a4,
        __int64 (__fastcall ***a5)(_QWORD, void *, char *))
{
  unsigned int v5; // ebx
  void *v9; // rdi
  NTSTATUS v11; // eax
  char *v12; // r14
  HANDLE ProcessHeap; // rax
  int v14; // eax
  int v15; // eax
  HANDLE v16; // rax
  signed int v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  size_t Size; // [rsp+20h] [rbp-18h] BYREF
  unsigned int *v23; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+40h]

  v5 = 0;
  v23 = 0;
  Size = 0;
  v9 = 0;
  v11 = BiPtQueryBrokeredEvent(a4, &Size, &v23);
  if ( v11 < 0 )
  {
    v18 = RtlNtStatusToDosError(v11);
    v5 = v18;
    if ( v18 > 0 )
      v5 = (unsigned __int16)v18 | 0x80070000;
  }
  if ( (v5 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3CB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
      (const char *)v5,
      Size);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_10;
    v20 = 17;
LABEL_37:
    v21 = v5;
    goto LABEL_38;
  }
  v12 = (char *)v23 + v23[10];
  if ( !IsValidSid(v12) )
  {
    v5 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3D1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
      (const char *)0x80070057LL,
      Size);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_10;
    v20 = 18;
    goto LABEL_23;
  }
  if ( !EqualSid(a3, v12) )
    goto LABEL_10;
  if ( v23[12] != 260 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3DB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
      (const char *)0x80070057LL,
      Size);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_10;
    v20 = 19;
LABEL_23:
    v21 = 2147942487LL;
    goto LABEL_38;
  }
  LODWORD(Size) = 260;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, 0x104u);
  if ( !v9 )
  {
    v5 = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3E0,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
      (const char *)0x8007000ELL,
      Size);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_10;
    v20 = 20;
    v21 = 2147942414LL;
LABEL_38:
    WPP_SF_d(v19[2], v20, WPP_ebc66346838a30418ba30573d23d0a14_Traceguids, v21);
    goto LABEL_10;
  }
  memcpy_0(v9, (char *)v23 + v23[11], (unsigned int)Size);
  v14 = (**a5)(a5, v9, (char *)&Size + 4);
  v5 = v14;
  if ( v14 == -2147023728 )
  {
    BiPtDeleteEvent(a4);
LABEL_31:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3F0,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
      (const char *)v5,
      Size);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_10;
    v20 = 21;
    goto LABEL_37;
  }
  if ( v14 < 0 )
    goto LABEL_31;
  v15 = BackgroundActivation::AddToList(a1, a2, v9, a4);
  v5 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3F6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
      (const char *)(unsigned int)v15,
      Size);
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v20 = 22;
      goto LABEL_37;
    }
  }
LABEL_10:
  if ( v23 )
  {
    BiPtFreeMemory();
    v23 = 0;
  }
  if ( v9 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v9);
  }
  return v5;
}

```

## disassembly

```asm
0x180022fc4  push    rbp
0x180022fc6  push    rbx
0x180022fc7  push    rsi
0x180022fc8  push    rdi
0x180022fc9  push    r12
0x180022fcb  push    r13
0x180022fcd  push    r14
0x180022fcf  push    r15
0x180022fd1  mov     rbp, rsp
0x180022fd4  sub     rsp, 38h
0x180022fd8  xor     ebx, ebx
0x180022fda  mov     r15, r8
0x180022fdd  mov     r12d, edx
0x180022fe0  mov     [rbp+var_10], rbx
0x180022fe4  mov     r13, rcx
0x180022fe7  mov     dword ptr [rbp+Size], ebx
0x180022fea  lea     r8, [rbp+var_10]
0x180022fee  mov     dword ptr [rbp+Size+4], ebx
0x180022ff1  lea     rdx, [rbp+Size]
0x180022ff5  mov     rcx, r9
0x180022ff8  mov     edi, ebx
0x180022ffa  mov     rsi, r9
0x180022ffd  call    cs:__imp_BiPtQueryBrokeredEvent
0x180023003  test    eax, eax
0x180023005  js      loc_180023117
0x18002300b  test    ebx, ebx
0x18002300d  js      loc_180023137
0x180023013  mov     rcx, [rbp+var_10]
0x180023017  mov     r14d, [rcx+28h]
0x18002301b  add     r14, rcx
0x18002301e  mov     rcx, r14; pSid
0x180023021  call    cs:__imp_IsValidSid
0x180023027  test    eax, eax
0x180023029  jz      loc_18002317A
0x18002302f  mov     rdx, r14; pSid2
0x180023032  mov     rcx, r15; pSid1
0x180023035  call    cs:__imp_EqualSid
0x18002303b  test    eax, eax
0x18002303d  jz      loc_1800230D4
0x180023043  mov     rax, [rbp+var_10]
0x180023047  mov     ebx, 104h
0x18002304c  cmp     [rax+30h], ebx
0x18002304f  jnz     loc_1800231D0
0x180023055  mov     dword ptr [rbp+Size], ebx
0x180023058  call    cs:__imp_GetProcessHeap
0x18002305e  mov     r8d, ebx; dwBytes
0x180023061  xor     edx, edx; dwFlags
0x180023063  mov     rcx, rax; hHeap
0x180023066  call    cs:__imp_HeapAlloc
0x18002306c  mov     rdi, rax
0x18002306f  test    rax, rax
0x180023072  jz      loc_180023211
0x180023078  mov     rax, [rbp+var_10]
0x18002307c  mov     rcx, rdi; void *
0x18002307f  mov     r8d, dword ptr [rbp+Size]; Size
0x180023083  mov     edx, [rax+2Ch]
0x180023086  add     rdx, rax; Src
0x180023089  call    memcpy_0
0x18002308e  mov     rcx, [rbp+arg_20]
0x180023092  lea     r8, [rbp+Size+4]
0x180023096  mov     rdx, rdi
0x180023099  mov     rax, [rcx]
0x18002309c  mov     rax, [rax]
0x18002309f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230a4  mov     ebx, eax
0x1800230a6  cmp     eax, 80070490h
0x1800230ab  jz      loc_18002325F
0x1800230b1  test    eax, eax
0x1800230b3  js      loc_180023268
0x1800230b9  mov     r9, rsi
0x1800230bc  mov     r8, rdi
0x1800230bf  mov     edx, r12d
0x1800230c2  mov     rcx, r13
0x1800230c5  call    ?AddToList@BackgroundActivation@@AEAAJW4WpnBackgroundTriggerType@@PEBGAEBU_GUID@@@Z; BackgroundActivation::AddToList(WpnBackgroundTriggerType,ushort const *,_GUID const &)
0x1800230ca  mov     ebx, eax
0x1800230cc  test    eax, eax
0x1800230ce  js      loc_1800232A8
0x1800230d4  mov     rcx, [rbp+var_10]
0x1800230d8  test    rcx, rcx
0x1800230db  jz      short loc_1800230EB
0x1800230dd  call    cs:__imp_BiPtFreeMemory
0x1800230e3  mov     [rbp+var_10], 0
0x1800230eb  test    rdi, rdi
0x1800230ee  jz      short loc_180023104
0x1800230f0  call    cs:__imp_GetProcessHeap
0x1800230f6  mov     r8, rdi; lpMem
0x1800230f9  xor     edx, edx; dwFlags
0x1800230fb  mov     rcx, rax; hHeap
0x1800230fe  call    cs:__imp_HeapFree
0x180023104  mov     eax, ebx
0x180023106  add     rsp, 38h
0x18002310a  pop     r15
0x18002310c  pop     r14
0x18002310e  pop     r13
0x180023110  pop     r12
0x180023112  pop     rdi
0x180023113  pop     rsi
0x180023114  pop     rbx
0x180023115  pop     rbp
0x180023116  retn
0x180023117  mov     ecx, eax; Status
0x180023119  call    cs:__imp_RtlNtStatusToDosError
0x18002311f  mov     ebx, eax
0x180023121  test    eax, eax
0x180023123  jle     loc_18002300B
0x180023129  movzx   ebx, ax
0x18002312c  or      ebx, 80070000h
0x180023132  jmp     loc_18002300B
0x180023137  mov     rcx, [rbp+40h]; this
0x18002313b  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180023142  mov     r9d, ebx; char *
0x180023145  mov     edx, 3CBh; void *
0x18002314a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002314f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023156  lea     rax, WPP_GLOBAL_Control
0x18002315d  cmp     rcx, rax
0x180023160  jz      loc_1800230D4
0x180023166  test    byte ptr [rcx+1Ch], 80h
0x18002316a  jz      loc_1800230D4
0x180023170  mov     edx, 11h
0x180023175  jmp     loc_1800232E6
0x18002317a  mov     rcx, [rbp+40h]; this
0x18002317e  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180023185  mov     r9d, 80070057h; char *
0x18002318b  mov     edx, 3D1h; void *
0x180023190  mov     ebx, r9d
0x180023193  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023198  mov     rcx, cs:WPP_GLOBAL_Control
0x18002319f  lea     rax, WPP_GLOBAL_Control
0x1800231a6  cmp     rcx, rax
0x1800231a9  jz      loc_1800230D4
0x1800231af  test    byte ptr [rcx+1Ch], 80h
0x1800231b3  jz      loc_1800230D4
0x1800231b9  mov     edx, 12h
0x1800231be  jmp     short loc_1800231C5
0x1800231c0  mov     edx, 13h
0x1800231c5  mov     r9d, 80070057h
0x1800231cb  jmp     loc_1800232E9
0x1800231d0  mov     rcx, [rbp+40h]; this
0x1800231d4  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800231db  mov     r9d, 80070057h; char *
0x1800231e1  mov     edx, 3DBh; void *
0x1800231e6  mov     ebx, r9d
0x1800231e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800231ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231f5  lea     rax, WPP_GLOBAL_Control
0x1800231fc  cmp     rcx, rax
0x1800231ff  jz      loc_1800230D4
0x180023205  test    byte ptr [rcx+1Ch], 80h
0x180023209  jz      loc_1800230D4
0x18002320f  jmp     short loc_1800231C0
0x180023211  mov     rcx, [rbp+40h]; this
0x180023215  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002321c  mov     ebx, 8007000Eh
0x180023221  mov     edx, 3E0h; void *
0x180023226  mov     r9d, ebx; char *
0x180023229  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002322e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023235  lea     rax, WPP_GLOBAL_Control
0x18002323c  cmp     rcx, rax
0x18002323f  jz      loc_1800230D4
0x180023245  test    byte ptr [rcx+1Ch], 80h
0x180023249  jz      loc_1800230D4
0x18002324f  mov     edx, 14h
0x180023254  mov     r9d, 8007000Eh
0x18002325a  jmp     loc_1800232E9
0x18002325f  mov     rcx, rsi
0x180023262  call    cs:__imp_BiPtDeleteEvent
0x180023268  mov     rcx, [rbp+40h]; this
0x18002326c  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180023273  mov     r9d, ebx; char *
0x180023276  mov     edx, 3F0h; void *
0x18002327b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023280  mov     rcx, cs:WPP_GLOBAL_Control
0x180023287  lea     rax, WPP_GLOBAL_Control
0x18002328e  cmp     rcx, rax
0x180023291  jz      loc_1800230D4
0x180023297  test    byte ptr [rcx+1Ch], 80h
0x18002329b  jz      loc_1800230D4
0x1800232a1  mov     edx, 15h
0x1800232a6  jmp     short loc_1800232E6
0x1800232a8  mov     rcx, [rbp+40h]; this
0x1800232ac  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800232b3  mov     r9d, ebx; char *
0x1800232b6  mov     edx, 3F6h; void *
0x1800232bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800232c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800232c7  lea     rax, WPP_GLOBAL_Control
0x1800232ce  cmp     rcx, rax
0x1800232d1  jz      loc_1800230D4
0x1800232d7  test    byte ptr [rcx+1Ch], 80h
0x1800232db  jz      loc_1800230D4
0x1800232e1  mov     edx, 16h
0x1800232e6  mov     r9d, ebx
0x1800232e9  mov     rcx, [rcx+10h]
0x1800232ed  lea     r8, WPP_ebc66346838a30418ba30573d23d0a14_Traceguids
0x1800232f4  call    WPP_SF_d
0x1800232f9  jmp     loc_1800230D4
```
