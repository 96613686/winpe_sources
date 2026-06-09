# CAANapEnforcementClientCallback::GetConnections(tagConnections * *)

- ea: `0x180003370`
- end: `0x1800034d8`
- name: `?GetConnections@CAANapEnforcementClientCallback@@UEAAJPEAPEAUtagConnections@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(CAANapEnforcementClientCallback *__hidden this, struct tagConnections **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180003370`
- `0x1800054b8`
- `0x18000c010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180003412`
- `ole32!CoTaskMemAlloc` at `0x180003425`
- `ole32!CoTaskMemAlloc` at `0x180003412`
- `ole32!CoTaskMemAlloc` at `0x180003425`
- `KERNEL32!LeaveCriticalSection` at `0x1800034b7`
- `KERNEL32!LeaveCriticalSection` at `0x1800034b7`
- `KERNEL32!EnterCriticalSection` at `0x1800033ab`
- `KERNEL32!EnterCriticalSection` at `0x1800033ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAANapEnforcementClientCallback::GetConnections(
        CAANapEnforcementClientCallback *this,
        struct tagConnections **a2)
{
  char *v4; // rdi
  unsigned int v5; // r14d
  int v6; // ebx
  struct tagConnections *v7; // r15
  __int64 v8; // r12
  __int64 *v9; // rbx
  __int64 *i; // rax
  __int64 *v11; // rcx

  v4 = (char *)this + 24;
  if ( *((_DWORD *)this + 8) && *(_QWORD *)v4 )
    EnterCriticalSection(*(LPCRITICAL_SECTION *)v4);
  if ( a2 )
  {
    v6 = *((_DWORD *)this + 12);
    v5 = 0;
    if ( !v6 )
    {
      *a2 = 0;
      goto LABEL_25;
    }
    v7 = (struct tagConnections *)CoTaskMemAlloc(0x10u);
    *(_WORD *)v7 = v6;
    *((_QWORD *)v7 + 1) = CoTaskMemAlloc(8LL * (unsigned __int16)v6);
    v8 = 0;
    v9 = (__int64 *)**((_QWORD **)this + 5);
    while ( 1 )
    {
      while ( 1 )
      {
        do
        {
          if ( v9 == *((__int64 **)this + 5) )
          {
            *a2 = v7;
            goto LABEL_25;
          }
          *(_QWORD *)(*((_QWORD *)v7 + 1) + 8 * v8) = v9[5];
          v8 = (unsigned int)(v8 + 1);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9[5] + 8LL))(v9[5]);
        }
        while ( *((_BYTE *)v9 + 25) );
        i = (__int64 *)v9[2];
        if ( !*((_BYTE *)i + 25) )
          break;
        for ( i = (__int64 *)v9[1]; !*((_BYTE *)i + 25) && v9 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v9 = i;
LABEL_23:
        v9 = i;
      }
      v11 = (__int64 *)*i;
      if ( *(_BYTE *)(*i + 25) )
        goto LABEL_23;
      do
      {
        v9 = v11;
        v11 = (__int64 *)*v11;
      }
      while ( !*((_BYTE *)v11 + 25) );
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids, L"pConnections");
  }
  v5 = -2147024809;
LABEL_25:
  if ( *((_DWORD *)v4 + 2) && *(_QWORD *)v4 )
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)v4);
  return v5;
}

```

## disassembly

```asm
0x180003370  mov     rax, rsp
0x180003373  push    rsi
0x180003374  push    rdi
0x180003375  push    r12
0x180003377  push    r14
0x180003379  push    r15
0x18000337b  sub     rsp, 30h
0x18000337f  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180003387  mov     [rax+10h], rbx
0x18000338b  mov     [rax+18h], rbp
0x18000338f  mov     rsi, rdx
0x180003392  mov     rbp, rcx
0x180003395  lea     rdi, [rcx+18h]
0x180003399  mov     [rax+8], rdi
0x18000339d  cmp     dword ptr [rdi+8], 0
0x1800033a1  jz      short loc_1800033B2
0x1800033a3  mov     rcx, [rdi]; lpCriticalSection
0x1800033a6  test    rcx, rcx
0x1800033a9  jz      short loc_1800033B2
0x1800033ab  call    cs:__imp_EnterCriticalSection
0x1800033b1  nop
0x1800033b2  test    rsi, rsi
0x1800033b5  jnz     short loc_1800033FB
0x1800033b7  lea     rax, WPP_GLOBAL_Control
0x1800033be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033c5  cmp     rcx, rax
0x1800033c8  jz      short loc_1800033F0
0x1800033ca  test    byte ptr [rcx+1Ch], 8
0x1800033ce  jz      short loc_1800033F0
0x1800033d0  cmp     byte ptr [rcx+19h], 2
0x1800033d4  jb      short loc_1800033F0
0x1800033d6  lea     edx, [rsi+1Dh]
0x1800033d9  lea     r9, aPconnections; "pConnections"
0x1800033e0  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x1800033e7  mov     rcx, [rcx+10h]
0x1800033eb  call    WPP_SF_S
0x1800033f0  mov     r14d, 80070057h
0x1800033f6  jmp     loc_1800034A9
0x1800033fb  mov     ebx, [rbp+30h]
0x1800033fe  xor     r14d, r14d
0x180003401  test    ebx, ebx
0x180003403  jnz     short loc_18000340D
0x180003405  mov     [rsi], r14
0x180003408  jmp     loc_1800034A9
0x18000340d  mov     ecx, 10h; cb
0x180003412  call    cs:__imp_CoTaskMemAlloc
0x180003418  mov     r15, rax
0x18000341b  movzx   ecx, bx
0x18000341e  mov     [rax], cx
0x180003421  shl     rcx, 3; cb
0x180003425  call    cs:__imp_CoTaskMemAlloc
0x18000342b  mov     [r15+8], rax
0x18000342f  xor     r12d, r12d
0x180003432  mov     rbx, [rbp+28h]
0x180003436  mov     rbx, [rbx]
0x180003439  cmp     rbx, [rbp+28h]
0x18000343d  jz      short loc_1800034A6
0x18000343f  mov     rcx, [r15+8]
0x180003443  mov     rax, [rbx+28h]
0x180003447  mov     [rcx+r12*8], rax
0x18000344b  inc     r12d
0x18000344e  mov     rcx, [rbx+28h]
0x180003452  mov     rax, [rcx]
0x180003455  mov     rax, [rax+8]
0x180003459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000345e  cmp     [rbx+19h], r14b
0x180003462  jnz     short loc_180003439
0x180003464  mov     rax, [rbx+10h]
0x180003468  cmp     [rax+19h], r14b
0x18000346c  jnz     short loc_180003488
0x18000346e  mov     rcx, [rax]
0x180003471  cmp     [rcx+19h], r14b
0x180003475  jnz     short loc_1800034A1
0x180003477  mov     rbx, rcx
0x18000347a  mov     rax, [rcx]
0x18000347d  mov     rcx, rax
0x180003480  cmp     [rax+19h], r14b
0x180003484  jz      short loc_180003477
0x180003486  jmp     short loc_180003439
0x180003488  mov     rax, [rbx+8]
0x18000348c  jmp     short loc_18000349B
0x18000348e  cmp     rbx, [rax+10h]
0x180003492  jnz     short loc_1800034A1
0x180003494  mov     rbx, rax
0x180003497  mov     rax, [rax+8]
0x18000349b  cmp     [rax+19h], r14b
0x18000349f  jz      short loc_18000348E
0x1800034a1  mov     rbx, rax
0x1800034a4  jmp     short loc_180003439
0x1800034a6  mov     [rsi], r15
0x1800034a9  cmp     dword ptr [rdi+8], 0
0x1800034ad  jz      short loc_1800034BE
0x1800034af  mov     rcx, [rdi]; lpCriticalSection
0x1800034b2  test    rcx, rcx
0x1800034b5  jz      short loc_1800034BE
0x1800034b7  call    cs:__imp_LeaveCriticalSection
0x1800034bd  nop
0x1800034be  mov     eax, r14d
0x1800034c1  mov     rbx, [rsp+58h+arg_8]
0x1800034c6  mov     rbp, [rsp+58h+arg_10]
0x1800034cb  add     rsp, 30h
0x1800034cf  pop     r15
0x1800034d1  pop     r14
0x1800034d3  pop     r12
0x1800034d5  pop     rdi
0x1800034d6  pop     rsi
0x1800034d7  retn
```
