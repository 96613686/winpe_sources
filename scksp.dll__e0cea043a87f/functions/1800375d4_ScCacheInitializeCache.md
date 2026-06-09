# ScCacheInitializeCache

- ea: `0x1800375d4`
- end: `0x180037728`
- name: `ScCacheInitializeCache`
- size: `340`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180024e98`
- `0x1800307d0`

## callees

- `0x18000a408`
- `0x18000a590`
- `0x180013734`
- `0x18002b140`
- `0x180036dcc`
- `0x180036e68`
- `0x1800375d4`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800376a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800376a3`

## pseudocode

```c
__int64 __fastcall ScCacheInitializeCache(struct _RTL_CRITICAL_SECTION **a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  unsigned int v7; // ebx
  PVOID v8; // rcx
  struct _RTL_CRITICAL_SECTION_DEBUG *v9; // rax

  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v4 = (*(__int64 (__fastcall **)(__int64))(a2 + 16))(104);
  v6 = (struct _RTL_CRITICAL_SECTION *)v4;
  if ( v4 )
  {
    *(_DWORD *)(v4 + 88) = *(_DWORD *)a2;
    *(_DWORD *)(v4 + 92) = *(_DWORD *)(a2 + 4);
    *(_DWORD *)(v4 + 96) = *(_DWORD *)(a2 + 8);
    *(_QWORD *)(v4 + 48) = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(v4 + 56) = *(_QWORD *)(a2 + 24);
    InitializeCriticalSection((LPCRITICAL_SECTION)v4);
    v9 = (struct _RTL_CRITICAL_SECTION_DEBUG *)MIDL_user_allocate(0x88u);
    if ( v9 )
    {
      v7 = 0;
      v6[1].DebugInfo = v9;
      I_ScInitializeCacheReadData(v6, 0, 0);
      *a1 = v6;
    }
    else
    {
      I_ServerCacheCleanup(v6);
      v7 = 8;
    }
  }
  else
  {
    WppTraceIndent(v5, 2u);
    v7 = 8;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
    }
  }
  WppTraceIndent((__int64)v8, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x1800375d4  push    rbx
0x1800375d6  push    rsi
0x1800375d7  push    rdi
0x1800375d8  push    r15
0x1800375da  sub     rsp, 38h
0x1800375de  mov     rbx, rdx
0x1800375e1  mov     rsi, rcx
0x1800375e4  xor     edx, edx
0x1800375e6  call    WppTraceIndent
0x1800375eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800375f2  lea     r15, WPP_GLOBAL_Control
0x1800375f9  cmp     rcx, r15
0x1800375fc  jz      short loc_180037626
0x1800375fe  test    byte ptr [rcx+1Ch], 2
0x180037602  jz      short loc_180037626
0x180037604  cmp     byte ptr [rcx+19h], 5
0x180037608  jb      short loc_180037626
0x18003760a  mov     r9, cs:WPP_pszIndent
0x180037611  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180037618  mov     rcx, [rcx+10h]
0x18003761c  mov     edx, 14h
0x180037621  call    WPP_SF_s
0x180037626  mov     rax, [rbx+10h]
0x18003762a  mov     ecx, 68h ; 'h'
0x18003762f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037634  mov     rdi, rax
0x180037637  test    rax, rax
0x18003763a  jnz     short loc_18003767F
0x18003763c  lea     edx, [rax+2]
0x18003763f  call    WppTraceIndent
0x180037644  lea     ebx, [rdi+8]
0x180037647  mov     rcx, cs:WPP_GLOBAL_Control
0x18003764e  cmp     rcx, r15
0x180037651  jz      loc_1800376DA
0x180037657  test    byte ptr [rcx+1Ch], 1
0x18003765b  jz      short loc_1800376DA
0x18003765d  cmp     byte ptr [rcx+19h], 2
0x180037661  jb      short loc_1800376DA
0x180037663  mov     r9, cs:WPP_pszIndent
0x18003766a  lea     edx, [rdi+15h]
0x18003766d  mov     rcx, [rcx+10h]
0x180037671  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180037678  call    WPP_SF_s
0x18003767d  jmp     short loc_1800376DA
0x18003767f  mov     eax, [rbx]
0x180037681  mov     rcx, rdi; lpCriticalSection
0x180037684  mov     [rdi+58h], eax
0x180037687  mov     eax, [rbx+4]
0x18003768a  mov     [rdi+5Ch], eax
0x18003768d  mov     eax, [rbx+8]
0x180037690  mov     [rdi+60h], eax
0x180037693  mov     rax, [rbx+10h]
0x180037697  mov     [rdi+30h], rax
0x18003769b  mov     rax, [rbx+18h]
0x18003769f  mov     [rdi+38h], rax
0x1800376a3  call    cs:__imp_InitializeCriticalSection
0x1800376a9  mov     ecx, 88h; size
0x1800376ae  call    MIDL_user_allocate
0x1800376b3  mov     rcx, rdi
0x1800376b6  test    rax, rax
0x1800376b9  jz      short loc_1800376D0
0x1800376bb  xor     ebx, ebx
0x1800376bd  mov     [rdi+28h], rax
0x1800376c1  xor     r8d, r8d
0x1800376c4  xor     edx, edx
0x1800376c6  call    I_ScInitializeCacheReadData
0x1800376cb  mov     [rsi], rdi
0x1800376ce  jmp     short loc_1800376DA
0x1800376d0  call    I_ServerCacheCleanup
0x1800376d5  mov     ebx, 8
0x1800376da  mov     edx, 1
0x1800376df  call    WppTraceIndent
0x1800376e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376eb  cmp     rcx, r15
0x1800376ee  jz      short loc_18003771C
0x1800376f0  test    byte ptr [rcx+1Ch], 2
0x1800376f4  jz      short loc_18003771C
0x1800376f6  cmp     byte ptr [rcx+19h], 5
0x1800376fa  jb      short loc_18003771C
0x1800376fc  mov     r9, cs:WPP_pszIndent
0x180037703  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x18003770a  mov     rcx, [rcx+10h]
0x18003770e  mov     edx, 16h
0x180037713  mov     [rsp+58h+var_38], ebx
0x180037717  call    WPP_SF_sd
0x18003771c  mov     eax, ebx
0x18003771e  add     rsp, 38h
0x180037722  pop     r15
0x180037724  pop     rdi
0x180037725  pop     rsi
0x180037726  pop     rbx
0x180037727  retn
```
