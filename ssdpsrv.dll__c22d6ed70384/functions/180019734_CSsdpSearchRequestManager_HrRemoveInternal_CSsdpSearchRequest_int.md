# CSsdpSearchRequestManager::HrRemoveInternal(CSsdpSearchRequest *,int)

- ea: `0x180019734`
- end: `0x18001986d`
- name: `?HrRemoveInternal@CSsdpSearchRequestManager@@AEAAJPEAVCSsdpSearchRequest@@H@Z`
- size: `313`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct CSsdpSearchRequest *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180019490`
- `0x18002f470`

## callees

- `0x18001959c`
- `0x180019734`
- `0x180019bac`
- `0x1800255a8`
- `0x18002f1d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001976d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001976d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001975b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001975b`

## pseudocode

```c
__int64 __fastcall CSsdpSearchRequestManager::HrRemoveInternal(
        LPCRITICAL_SECTION lpCriticalSection,
        struct CSsdpSearchRequest *a2,
        int a3)
{
  void *v3; // rdi
  unsigned int v7; // esi
  LPCRITICAL_SECTION v8; // rax
  _QWORD *v9; // rbx
  _QWORD *v11; // rax
  CSsdpSearchRequest *v12; // rsi
  unsigned int v13; // eax
  _QWORD *p_Type; // rdx
  _QWORD *v15; // [rsp+40h] [rbp+8h] BYREF

  v3 = 0;
  v15 = 0;
  v7 = 1;
  EnterCriticalSection(lpCriticalSection);
  v8 = lpCriticalSection + 1;
  if ( lpCriticalSection[1].DebugInfo )
  {
    while ( v8 )
    {
      p_Type = &v8->DebugInfo->Type;
      if ( !v8->DebugInfo )
        break;
      if ( a2 == (struct CSsdpSearchRequest *)(p_Type + 1) )
      {
        v8->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)*p_Type;
        *p_Type = 0;
        v3 = p_Type;
        v15 = p_Type;
        break;
      }
      if ( !*p_Type )
        break;
      v8 = (LPCRITICAL_SECTION)v8->DebugInfo;
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( !v3 )
    goto LABEL_22;
  v9 = &v15;
  do
  {
    if ( !v9 )
      break;
    v11 = (_QWORD *)*v9;
    if ( !*v9 )
      break;
    v12 = (CSsdpSearchRequest *)(v11 + 1);
    if ( !a3 )
      CSsdpRundownSupport::RemoveRundownItem(&CSsdpRundownSupport::s_instance, v11 + 1);
    v13 = CSsdpSearchRequest::HrShutdown(v12);
    v9 = (_QWORD *)*v9;
    v7 = v13;
    if ( !v9 )
      break;
  }
  while ( *v9 );
  if ( v7 )
  {
LABEL_22:
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids, v7);
  }
  if ( v3 )
    CUList<CSsdpSearchRequest>::Node::`scalar deleting destructor'(v3);
  return v7;
}

```

## disassembly

```asm
0x180019734  mov     [rsp+arg_8], rbx
0x180019739  mov     [rsp+arg_10], rbp
0x18001973e  push    rsi
0x18001973f  push    rdi
0x180019740  push    r14
0x180019742  sub     rsp, 20h
0x180019746  xor     edi, edi
0x180019748  mov     r14d, r8d
0x18001974b  mov     [rsp+38h+arg_0], rdi
0x180019750  mov     rbp, rdx
0x180019753  mov     rbx, rcx
0x180019756  mov     esi, 1
0x18001975b  call    cs:__imp_EnterCriticalSection
0x180019761  lea     rax, [rbx+28h]
0x180019765  cmp     [rax], rdi
0x180019768  jnz     short loc_1800197D7
0x18001976a  mov     rcx, rbx; lpCriticalSection
0x18001976d  call    cs:__imp_LeaveCriticalSection
0x180019773  test    rdi, rdi
0x180019776  jz      loc_180019822
0x18001977c  lea     rbx, [rsp+38h+arg_0]
0x180019781  test    rbx, rbx
0x180019784  jnz     short loc_1800197AC
0x180019786  test    esi, esi
0x180019788  jnz     loc_180019822
0x18001978e  test    rdi, rdi
0x180019791  jnz     loc_180019860
0x180019797  mov     rbx, [rsp+38h+arg_8]
0x18001979c  mov     eax, esi
0x18001979e  mov     rbp, [rsp+38h+arg_10]
0x1800197a3  add     rsp, 20h
0x1800197a7  pop     r14
0x1800197a9  pop     rdi
0x1800197aa  pop     rsi
0x1800197ab  retn
0x1800197ac  mov     rax, [rbx]
0x1800197af  test    rax, rax
0x1800197b2  jz      short loc_180019786
0x1800197b4  lea     rsi, [rax+8]
0x1800197b8  test    r14d, r14d
0x1800197bb  jz      short loc_180019811
0x1800197bd  mov     rcx, rsi; this
0x1800197c0  call    ?HrShutdown@CSsdpSearchRequest@@QEAAJXZ; CSsdpSearchRequest::HrShutdown(void)
0x1800197c5  mov     rbx, [rbx]
0x1800197c8  mov     esi, eax
0x1800197ca  test    rbx, rbx
0x1800197cd  jz      short loc_180019786
0x1800197cf  cmp     qword ptr [rbx], 0
0x1800197d3  jz      short loc_180019786
0x1800197d5  jmp     short loc_180019781
0x1800197d7  test    rax, rax
0x1800197da  jz      short loc_18001976A
0x1800197dc  mov     rdx, [rax]
0x1800197df  test    rdx, rdx
0x1800197e2  jz      short loc_18001976A
0x1800197e4  lea     rcx, [rdx+8]
0x1800197e8  cmp     rbp, rcx
0x1800197eb  jz      short loc_1800197FB
0x1800197ed  cmp     [rdx], rdi
0x1800197f0  jz      loc_18001976A
0x1800197f6  mov     rax, rdx
0x1800197f9  jmp     short loc_1800197D7
0x1800197fb  mov     rcx, [rdx]
0x1800197fe  mov     [rax], rcx
0x180019801  mov     [rdx], rdi
0x180019804  mov     rdi, rdx
0x180019807  mov     [rsp+38h+arg_0], rdx
0x18001980c  jmp     loc_18001976A
0x180019811  mov     rdx, rsi; void *
0x180019814  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x18001981b  call    ?RemoveRundownItem@CSsdpRundownSupport@@QEAAXPEAX@Z; CSsdpRundownSupport::RemoveRundownItem(void *)
0x180019820  jmp     short loc_1800197BD
0x180019822  mov     rcx, cs:WPP_GLOBAL_Control
0x180019829  lea     rax, WPP_GLOBAL_Control
0x180019830  cmp     rcx, rax
0x180019833  jz      loc_18001978E
0x180019839  test    byte ptr [rcx+1Ch], 1
0x18001983d  jz      loc_18001978E
0x180019843  mov     rcx, [rcx+10h]
0x180019847  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x18001984e  mov     edx, 29h ; ')'
0x180019853  mov     r9d, esi
0x180019856  call    WPP_SF_d
0x18001985b  jmp     loc_18001978E
0x180019860  mov     rcx, rdi; void *
0x180019863  call    ??_GNode@?$CUList@VCSsdpSearchRequest@@@@QEAAPEAXI@Z; CUList<CSsdpSearchRequest>::Node::`scalar deleting destructor'(uint)
0x180019868  jmp     loc_180019797
```
