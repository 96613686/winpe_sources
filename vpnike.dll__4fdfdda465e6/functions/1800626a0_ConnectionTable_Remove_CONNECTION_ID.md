# ConnectionTable::Remove(_CONNECTION_ID_)

- ea: `0x1800626a0`
- end: `0x180062a2e`
- name: `?Remove@ConnectionTable@@QEAAPEAVBaseConnection@@T_CONNECTION_ID_@@@Z`
- size: `910`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18005ef30`

## callees

- `0x180001564`
- `0x180007794`
- `0x1800077bc`
- `0x18000a3a0`
- `0x1800626a0`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062787`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062787`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062940`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062940`

## string_xrefs

- `0x180062767`: `ConnectionTable::Remove`
- `0x18006299c`: `Removed connection with Id %d at index %d`

## pseudocode

```c
__int64 __fastcall ConnectionTable::Remove(__int64 a1, unsigned int a2)
{
  __int64 v4; // rax
  __int64 v5; // r12
  _QWORD *v6; // rdi
  _QWORD *v7; // r14
  unsigned int v8; // ecx
  _QWORD *v9; // rax
  __int64 v10; // r8
  _QWORD *v11; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rsi
  PVOID *v15; // rcx
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+30h] [rbp-D0h]
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v19; // [rsp+40h] [rbp-C0h]
  __int128 v20; // [rsp+50h] [rbp-B0h]
  __int64 v21; // [rsp+60h] [rbp-A0h]
  int v22; // [rsp+68h] [rbp-98h]
  int v23; // [rsp+6Ch] [rbp-94h]
  int v24; // [rsp+70h] [rbp-90h] BYREF
  char v25[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4996f7b031003d065c89e27055bb3d0d_Traceguids);
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v19 = 0;
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v22 = -1;
  v23 = 0;
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v18,
      L"ConnectionTable::Remove",
      0,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))BaseTraceFunction);
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(a1 + 24592);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24592));
  v4 = a2 & 0x1FF;
  v5 = 3 * v4;
  v6 = *(_QWORD **)(a1 + 24 * v4 + 16);
  v7 = 0;
  while ( v6 )
  {
    if ( a2 == (unsigned __int64)*(unsigned int *)(v6[2] + 8LL) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_4996f7b031003d065c89e27055bb3d0d_Traceguids,
          a2,
          a2 & 0x1FF);
      }
      if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
      {
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v24, L"Found the connection object %d at index %d", a2, a2 & 0x1FF);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
          gBaseEtwContext,
          *((_QWORD *)&xmmword_1800AABC0 + 1),
          &v24);
      }
      v8 = *(_DWORD *)(v6[2] + 24LL) & 0x1FF;
      v9 = (_QWORD *)*v6;
      if ( v7 )
        *v7 = v9;
      else
        *(_QWORD *)(a1 + 8 * v5 + 16) = v9;
      v10 = 3 * (v8 + 513LL);
      v11 = *(_QWORD **)(a1 + 24 * (v8 + 513LL));
      v12 = 0;
      while ( v11 && v11 != v6 )
      {
        v12 = v11;
        v11 = (_QWORD *)v11[1];
      }
      v13 = v11[1];
      if ( v12 )
        v12[1] = v13;
      else
        *(_QWORD *)(a1 + 8 * v10) = v13;
      --*(_DWORD *)(a1 + 8);
      v14 = v6[2];
      operator delete(v6);
      goto LABEL_34;
    }
    v7 = v6;
    v6 = (_QWORD *)*v6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_4996f7b031003d065c89e27055bb3d0d_Traceguids, a2);
  }
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"Connection object with %d could NOT be found", a2);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
      gBaseEtwContext,
      *((_QWORD *)&xmmword_1800AABC0 + 1),
      &v24);
  }
  v14 = 0;
LABEL_34:
  LeaveCriticalSection(lpCriticalSection);
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_4996f7b031003d065c89e27055bb3d0d_Traceguids, a2, a2 & 0x1FF);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"Removed connection with Id %d at index %d", a2, a2 & 0x1FF);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
      gBaseEtwContext,
      *((_QWORD *)&xmmword_1800AABC0 + 1),
      &v24);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x10000) != 0 )
    WPP_SF_(v15[2], 24, WPP_4996f7b031003d065c89e27055bb3d0d_Traceguids);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v18);
  return v14;
}

```

## disassembly

```asm
0x1800626a0  mov     [rsp-8+arg_10], rbx
0x1800626a5  push    rbp
0x1800626a6  push    rsi
0x1800626a7  push    rdi
0x1800626a8  push    r12
0x1800626aa  push    r13
0x1800626ac  push    r14
0x1800626ae  push    r15
0x1800626b0  lea     rbp, [rsp-780h]
0x1800626b8  sub     rsp, 880h
0x1800626bf  mov     rax, cs:__security_cookie
0x1800626c6  xor     rax, rsp
0x1800626c9  mov     [rbp+7B0h+var_40], rax
0x1800626d0  mov     rbx, rdx
0x1800626d3  mov     rsi, rcx
0x1800626d6  lea     r13, WPP_GLOBAL_Control
0x1800626dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800626e4  cmp     rcx, r13
0x1800626e7  jz      short loc_180062707
0x1800626e9  test    dword ptr [rcx+1Ch], 10000h
0x1800626f0  jz      short loc_180062707
0x1800626f2  mov     edx, 14h
0x1800626f7  lea     r8, WPP_4996f7b031003d065c89e27055bb3d0d_Traceguids
0x1800626fe  mov     rcx, [rcx+10h]
0x180062702  call    WPP_SF_
0x180062707  xor     eax, eax
0x180062709  mov     [rsp+8B0h+var_840], eax
0x18006270d  xor     edx, edx; Val
0x18006270f  mov     r8d, 7FCh; Size
0x180062715  lea     rcx, [rsp+8B0h+var_83C]; void *
0x18006271a  call    memset_0
0x18006271f  xorps   xmm0, xmm0
0x180062722  movdqu  [rsp+8B0h+var_870], xmm0
0x180062728  mov     [rsp+8B0h+var_878], 0
0x180062731  xorps   xmm1, xmm1
0x180062734  movdqu  [rsp+8B0h+var_860], xmm1
0x18006273a  mov     [rsp+8B0h+var_850], 0
0x180062743  mov     [rsp+8B0h+var_848], 0FFFFFFFFh
0x18006274b  mov     [rsp+8B0h+var_844], 0
0x180062753  cmp     qword ptr cs:xmmword_1800AABC0+8, 0
0x18006275b  jz      short loc_180062778
0x18006275d  lea     r9, ?BaseTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x180062764  xor     r8d, r8d; unsigned int *
0x180062767  lea     rdx, aConnectiontabl; "ConnectionTable::Remove"
0x18006276e  lea     rcx, [rsp+8B0h+var_878]; this
0x180062773  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180062778  lea     rax, [rsi+6010h]
0x18006277f  mov     [rsp+8B0h+lpCriticalSection], rax
0x180062784  mov     rcx, rax; lpCriticalSection
0x180062787  call    cs:__imp_EnterCriticalSection
0x18006278d  mov     eax, ebx
0x18006278f  and     eax, 1FFh
0x180062794  mov     r15d, eax
0x180062797  lea     r12, [rax+rax*2]
0x18006279b  mov     rdi, [rsi+r12*8+10h]
0x1800627a0  xor     r14d, r14d
0x1800627a3  test    rdi, rdi
0x1800627a6  jz      loc_1800628BB
0x1800627ac  mov     r13d, ebx
0x1800627af  mov     rax, [rdi+10h]
0x1800627b3  mov     ecx, [rax+8]
0x1800627b6  cmp     r13, rcx
0x1800627b9  jz      short loc_1800627C3
0x1800627bb  mov     r14, rdi
0x1800627be  mov     rdi, [rdi]
0x1800627c1  jmp     short loc_1800627A3
0x1800627c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800627ca  lea     rax, WPP_GLOBAL_Control
0x1800627d1  cmp     rcx, rax
0x1800627d4  jz      short loc_180062802
0x1800627d6  test    dword ptr [rcx+1Ch], 10000h
0x1800627dd  jz      short loc_180062802
0x1800627df  cmp     byte ptr [rcx+19h], 3
0x1800627e3  jb      short loc_180062802
0x1800627e5  mov     edx, 15h
0x1800627ea  mov     [rsp+8B0h+var_890], r15d
0x1800627ef  mov     r9d, ebx
0x1800627f2  lea     r8, WPP_4996f7b031003d065c89e27055bb3d0d_Traceguids
0x1800627f9  mov     rcx, [rcx+10h]
0x1800627fd  call    WPP_SF_dd
0x180062802  cmp     qword ptr cs:xmmword_1800AABC0+8, 0
0x18006280a  jz      short loc_180062849
0x18006280c  xor     eax, eax
0x18006280e  mov     word ptr [rsp+8B0h+var_840], ax
0x180062813  mov     r9d, r15d
0x180062816  mov     r8, r13
0x180062819  lea     rdx, aFoundTheConnec; "Found the connection object %d at index"...
0x180062820  lea     rcx, [rsp+8B0h+var_840]
0x180062825  call    FormatRRASErrorString
0x18006282a  lea     r8, [rsp+8B0h+var_840]
0x18006282f  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x180062836  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18006283d  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180062844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062849  mov     rax, [rdi+10h]
0x18006284d  mov     ecx, [rax+18h]
0x180062850  and     ecx, 1FFh
0x180062856  mov     rax, [rdi]
0x180062859  test    r14, r14
0x18006285c  jz      short loc_180062863
0x18006285e  mov     [r14], rax
0x180062861  jmp     short loc_180062868
0x180062863  mov     [rsi+r12*8+10h], rax
0x180062868  mov     eax, ecx
0x18006286a  add     rax, 201h
0x180062870  lea     r8, [rax+rax*2]
0x180062874  mov     rax, [rsi+r8*8]
0x180062878  xor     ecx, ecx
0x18006287a  jmp     short loc_180062888
0x18006287c  cmp     rax, rdi
0x18006287f  jz      short loc_18006288D
0x180062881  mov     rcx, rax
0x180062884  mov     rax, [rax+8]
0x180062888  test    rax, rax
0x18006288b  jnz     short loc_18006287C
0x18006288d  mov     rdx, [rax+8]
0x180062891  test    rcx, rcx
0x180062894  jz      short loc_18006289C
0x180062896  mov     [rcx+8], rdx
0x18006289a  jmp     short loc_1800628A0
0x18006289c  mov     [rsi+r8*8], rdx
0x1800628a0  dec     dword ptr [rsi+8]
0x1800628a3  mov     rsi, [rdi+10h]
0x1800628a7  mov     rcx, rdi; Block
0x1800628aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800628af  lea     r13, WPP_GLOBAL_Control
0x1800628b6  jmp     loc_18006293B
0x1800628bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800628c2  lea     r13, WPP_GLOBAL_Control
0x1800628c9  cmp     rcx, r13
0x1800628cc  jz      short loc_1800628F5
0x1800628ce  test    dword ptr [rcx+1Ch], 10000h
0x1800628d5  jz      short loc_1800628F5
0x1800628d7  cmp     byte ptr [rcx+19h], 1
0x1800628db  jb      short loc_1800628F5
0x1800628dd  mov     edx, 16h
0x1800628e2  mov     r9d, ebx
0x1800628e5  lea     r8, WPP_4996f7b031003d065c89e27055bb3d0d_Traceguids
0x1800628ec  mov     rcx, [rcx+10h]
0x1800628f0  call    WPP_SF_d
0x1800628f5  cmp     qword ptr cs:xmmword_1800AABC0+8, 0
0x1800628fd  jz      short loc_180062939
0x1800628ff  xor     eax, eax
0x180062901  mov     word ptr [rsp+8B0h+var_840], ax
0x180062906  mov     r8d, ebx
0x180062909  lea     rdx, aConnectionObje; "Connection object with %d could NOT be "...
0x180062910  lea     rcx, [rsp+8B0h+var_840]
0x180062915  call    FormatRRASErrorString
0x18006291a  lea     r8, [rsp+8B0h+var_840]
0x18006291f  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x180062926  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18006292d  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180062934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062939  xor     esi, esi
0x18006293b  mov     rcx, [rsp+8B0h+lpCriticalSection]; lpCriticalSection
0x180062940  call    cs:__imp_LeaveCriticalSection
0x180062946  mov     rcx, cs:WPP_GLOBAL_Control
0x18006294d  cmp     rcx, r13
0x180062950  jz      short loc_180062985
0x180062952  test    dword ptr [rcx+1Ch], 10000h
0x180062959  jz      short loc_180062985
0x18006295b  cmp     byte ptr [rcx+19h], 3
0x18006295f  jb      short loc_180062985
0x180062961  mov     edx, 17h
0x180062966  mov     [rsp+8B0h+var_890], r15d
0x18006296b  mov     r9d, ebx
0x18006296e  lea     r8, WPP_4996f7b031003d065c89e27055bb3d0d_Traceguids
0x180062975  mov     rcx, [rcx+10h]
0x180062979  call    WPP_SF_dd
0x18006297e  mov     rcx, cs:WPP_GLOBAL_Control
0x180062985  cmp     qword ptr cs:xmmword_1800AABC0+8, 0
0x18006298d  jz      short loc_1800629D3
0x18006298f  xor     eax, eax
0x180062991  mov     word ptr [rsp+8B0h+var_840], ax
0x180062996  mov     r8d, ebx
0x180062999  mov     r9d, r15d
0x18006299c  lea     rdx, aRemovedConnect; "Removed connection with Id %d at index "...
0x1800629a3  lea     rcx, [rsp+8B0h+var_840]
0x1800629a8  call    FormatRRASErrorString
0x1800629ad  lea     r8, [rsp+8B0h+var_840]
0x1800629b2  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x1800629b9  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x1800629c0  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800629c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800629cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800629d3  cmp     rcx, r13
0x1800629d6  jz      short loc_1800629F7
0x1800629d8  test    dword ptr [rcx+1Ch], 10000h
0x1800629df  jz      short loc_1800629F7
0x1800629e1  mov     edx, 18h
0x1800629e6  lea     r8, WPP_4996f7b031003d065c89e27055bb3d0d_Traceguids
0x1800629ed  mov     rcx, [rcx+10h]
0x1800629f1  call    WPP_SF_
0x1800629f6  nop
0x1800629f7  lea     rcx, [rsp+8B0h+var_878]; this
0x1800629fc  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180062a01  mov     rax, rsi
0x180062a04  mov     rcx, [rbp+7B0h+var_40]
0x180062a0b  xor     rcx, rsp; StackCookie
0x180062a0e  call    __security_check_cookie
0x180062a13  mov     rbx, [rsp+8B0h+arg_10]
0x180062a1b  add     rsp, 880h
0x180062a22  pop     r15
0x180062a24  pop     r14
0x180062a26  pop     r13
0x180062a28  pop     r12
0x180062a2a  pop     rdi
0x180062a2b  pop     rsi
0x180062a2c  pop     rbp
0x180062a2d  retn
```
