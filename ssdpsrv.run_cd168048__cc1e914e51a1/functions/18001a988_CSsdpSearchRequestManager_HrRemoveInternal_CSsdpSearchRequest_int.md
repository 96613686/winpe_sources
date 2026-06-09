# CSsdpSearchRequestManager::HrRemoveInternal(CSsdpSearchRequest *,int)

- ea: `0x18001a988`
- end: `0x18001aad2`
- name: `?HrRemoveInternal@CSsdpSearchRequestManager@@AEAAJPEAVCSsdpSearchRequest@@H@Z`
- size: `330`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct CSsdpSearchRequest *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001a690`
- `0x180031730`

## callees

- `0x18001a7c8`
- `0x18001a988`
- `0x18001aeb4`
- `0x1800271fc`
- `0x180031440`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a9c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a9c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a9af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a9af`

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
0x18001a988  mov     [rsp+arg_8], rbx
0x18001a98d  mov     [rsp+arg_10], rbp
0x18001a992  push    rsi
0x18001a993  push    rdi
0x18001a994  push    r14
0x18001a996  sub     rsp, 20h
0x18001a99a  xor     edi, edi
0x18001a99c  mov     r14d, r8d
0x18001a99f  mov     [rsp+38h+arg_0], rdi
0x18001a9a4  mov     rbp, rdx
0x18001a9a7  mov     rbx, rcx
0x18001a9aa  mov     esi, 1
0x18001a9af  call    cs:__imp_EnterCriticalSection
0x18001a9b6  nop     dword ptr [rax+rax+00h]
0x18001a9bb  lea     rax, [rbx+28h]
0x18001a9bf  cmp     [rax], rdi
0x18001a9c2  jnz     short loc_18001AA38
0x18001a9c4  mov     rcx, rbx; lpCriticalSection
0x18001a9c7  call    cs:__imp_LeaveCriticalSection
0x18001a9ce  nop     dword ptr [rax+rax+00h]
0x18001a9d3  test    rdi, rdi
0x18001a9d6  jz      loc_18001AA87
0x18001a9dc  lea     rbx, [rsp+38h+arg_0]
0x18001a9e1  test    rbx, rbx
0x18001a9e4  jnz     short loc_18001AA0D
0x18001a9e6  test    esi, esi
0x18001a9e8  jnz     loc_18001AA87
0x18001a9ee  test    rdi, rdi
0x18001a9f1  jnz     loc_18001AAC5
0x18001a9f7  mov     rbx, [rsp+38h+arg_8]
0x18001a9fc  mov     eax, esi
0x18001a9fe  mov     rbp, [rsp+38h+arg_10]
0x18001aa03  add     rsp, 20h
0x18001aa07  pop     r14
0x18001aa09  pop     rdi
0x18001aa0a  pop     rsi
0x18001aa0b  retn
0x18001aa0d  mov     rax, [rbx]
0x18001aa10  test    rax, rax
0x18001aa13  jz      short loc_18001A9E6
0x18001aa15  lea     rsi, [rax+8]
0x18001aa19  test    r14d, r14d
0x18001aa1c  jz      short loc_18001AA76
0x18001aa1e  mov     rcx, rsi; this
0x18001aa21  call    ?HrShutdown@CSsdpSearchRequest@@QEAAJXZ; CSsdpSearchRequest::HrShutdown(void)
0x18001aa26  mov     rbx, [rbx]
0x18001aa29  mov     esi, eax
0x18001aa2b  test    rbx, rbx
0x18001aa2e  jz      short loc_18001A9E6
0x18001aa30  cmp     qword ptr [rbx], 0
0x18001aa34  jz      short loc_18001A9E6
0x18001aa36  jmp     short loc_18001A9E1
0x18001aa38  test    rax, rax
0x18001aa3b  jz      short loc_18001A9C4
0x18001aa3d  mov     rdx, [rax]
0x18001aa40  test    rdx, rdx
0x18001aa43  jz      loc_18001A9C4
0x18001aa49  lea     rcx, [rdx+8]
0x18001aa4d  cmp     rbp, rcx
0x18001aa50  jz      short loc_18001AA60
0x18001aa52  cmp     [rdx], rdi
0x18001aa55  jz      loc_18001A9C4
0x18001aa5b  mov     rax, rdx
0x18001aa5e  jmp     short loc_18001AA38
0x18001aa60  mov     rcx, [rdx]
0x18001aa63  mov     [rax], rcx
0x18001aa66  mov     [rdx], rdi
0x18001aa69  mov     rdi, rdx
0x18001aa6c  mov     [rsp+38h+arg_0], rdx
0x18001aa71  jmp     loc_18001A9C4
0x18001aa76  mov     rdx, rsi; void *
0x18001aa79  lea     rcx, ?s_instance@CSsdpRundownSupport@@0V1@A; lpCriticalSection
0x18001aa80  call    ?RemoveRundownItem@CSsdpRundownSupport@@QEAAXPEAX@Z; CSsdpRundownSupport::RemoveRundownItem(void *)
0x18001aa85  jmp     short loc_18001AA1E
0x18001aa87  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa8e  lea     rax, WPP_GLOBAL_Control
0x18001aa95  cmp     rcx, rax
0x18001aa98  jz      loc_18001A9EE
0x18001aa9e  test    byte ptr [rcx+1Ch], 1
0x18001aaa2  jz      loc_18001A9EE
0x18001aaa8  mov     rcx, [rcx+10h]
0x18001aaac  lea     r8, WPP_a39c2586c9f736b52f5e075cbea19de6_Traceguids
0x18001aab3  mov     edx, 29h ; ')'
0x18001aab8  mov     r9d, esi
0x18001aabb  call    WPP_SF_d
0x18001aac0  jmp     loc_18001A9EE
0x18001aac5  mov     rcx, rdi; void *
0x18001aac8  call    ??_GNode@?$CUList@VCSsdpSearchRequest@@@@QEAAPEAXI@Z; CUList<CSsdpSearchRequest>::Node::`scalar deleting destructor'(uint)
0x18001aacd  jmp     loc_18001A9F7
```
