# CWcnEventManager::DeleteEventSink(CWcnEventSink *)

- ea: `0x18003a0c8`
- end: `0x18003a24a`
- name: `?DeleteEventSink@CWcnEventManager@@QEAAXPEAVCWcnEventSink@@@Z`
- size: `386`
- prototype: `void __fastcall(CWcnEventManager *this, struct CWcnEventSink *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180037d20`
- `0x1800380d0`

## callees

- `0x180004fb8`
- `0x18000fe00`
- `0x18003a0c8`
- `0x18003be88`
- `0x18003c5c8`
- `0x18003c684`
- `0x180053004`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003a1c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a204`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a1c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a204`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a126`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a126`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a1d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a1d9`

## pseudocode

```c
void __fastcall CWcnEventManager::DeleteEventSink(CWcnEventManager *this, struct CWcnEventSink *a2)
{
  __int64 v2; // r14
  const char *Indent; // rax
  __int64 v5; // r10
  struct _RTL_CRITICAL_SECTION *v6; // rbp
  __int64 *v7; // rbx
  __int64 *v8; // r8
  __int64 *v9; // rdx
  __int64 *i; // rax
  __int64 *v11; // rcx
  __int64 v12; // r14
  _QWORD *v13; // rsi
  _QWORD *v14; // rbx
  _QWORD *v15; // rdx
  void *v16; // rcx
  const char *v17; // rax
  __int64 v18; // r10
  CWcnEventManager *v19; // [rsp+60h] [rbp+8h] BYREF

  v19 = this;
  v2 = qword_180075810;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 23, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids, Indent);
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)(v2 + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 48));
  v7 = **(__int64 ***)(v2 + 16);
  while ( v7 != *(__int64 **)(v2 + 16) )
  {
    v8 = v7;
    v9 = v7;
    if ( !*((_BYTE *)v7 + 25) )
    {
      i = (__int64 *)v7[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v7 = i;
LABEL_15:
        v7 = i;
        goto LABEL_16;
      }
      v11 = (__int64 *)*i;
      if ( *(_BYTE *)(*i + 25) )
        goto LABEL_15;
      do
      {
        v7 = v11;
        v11 = (__int64 *)*v11;
      }
      while ( !*((_BYTE *)v11 + 25) );
    }
LABEL_16:
    if ( (struct CWcnEventSink *)v9[5] == a2 )
      std::_Tree<std::_Tmap_traits<_GUID,CWcnWfdGoPeer const *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnWfdGoPeer const *>>,0>>::erase(
        v2 + 16,
        &v19,
        v8);
  }
  v12 = *(_QWORD *)(v2 + 32);
  v13 = *(_QWORD **)v12;
  v14 = **(_QWORD ***)v12;
  while ( v14 != v13 )
  {
    if ( (struct CWcnEventSink *)v14[2] == a2 )
    {
      v15 = (_QWORD *)v14[1];
      v16 = v14;
      v14 = (_QWORD *)*v14;
      *v15 = v14;
      v14[1] = v15;
      operator delete(v16);
      --*(_QWORD *)(v12 + 8);
    }
    else
    {
      v14 = (_QWORD *)*v14;
    }
  }
  LeaveCriticalSection(v6);
  CWcnEventSink::CompleteActiveCallWithStatus(a2, -2147023673);
  CWcnEventSink::ClearActiveCall(a2);
  if ( a2 )
  {
    CWcnEventSink::~CWcnEventSink(a2);
    operator delete(a2);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v17 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v18 + 16), 24, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids, v17);
  }
}

```

## disassembly

```asm
0x18003a0c8  mov     [rsp+arg_0], rcx
0x18003a0cd  push    rbx
0x18003a0ce  push    rbp
0x18003a0cf  push    rsi
0x18003a0d0  push    rdi
0x18003a0d1  push    r12
0x18003a0d3  push    r14
0x18003a0d5  sub     rsp, 28h
0x18003a0d9  mov     r14, cs:qword_180075810
0x18003a0e0  mov     rdi, rdx
0x18003a0e3  mov     r10, cs:WPP_GLOBAL_Control
0x18003a0ea  lea     r12, WPP_GLOBAL_Control
0x18003a0f1  cmp     r10, r12
0x18003a0f4  jz      short loc_18003A11F
0x18003a0f6  cmp     byte ptr [r10+19h], 6
0x18003a0fb  jb      short loc_18003A11F
0x18003a0fd  mov     ecx, 1; int
0x18003a102  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003a107  mov     rcx, [r10+10h]
0x18003a10b  lea     r8, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids
0x18003a112  mov     edx, 17h
0x18003a117  mov     r9, rax
0x18003a11a  call    WPP_SF_s
0x18003a11f  lea     rbp, [r14+30h]
0x18003a123  mov     rcx, rbp; lpCriticalSection
0x18003a126  call    cs:__imp_EnterCriticalSection
0x18003a12c  lea     rsi, [r14+10h]
0x18003a130  mov     rbx, [rsi]
0x18003a133  mov     rbx, [rbx]
0x18003a136  cmp     rbx, [rsi]
0x18003a139  jz      short loc_18003A19C
0x18003a13b  cmp     byte ptr [rbx+19h], 0
0x18003a13f  mov     r8, rbx
0x18003a142  mov     rdx, rbx
0x18003a145  jnz     short loc_18003A187
0x18003a147  mov     rax, [rbx+10h]
0x18003a14b  cmp     byte ptr [rax+19h], 0
0x18003a14f  jnz     short loc_18003A16B
0x18003a151  mov     rcx, [rax]
0x18003a154  cmp     byte ptr [rcx+19h], 0
0x18003a158  jnz     short loc_18003A184
0x18003a15a  mov     rax, [rcx]
0x18003a15d  mov     rbx, rcx
0x18003a160  mov     rcx, rax
0x18003a163  cmp     byte ptr [rax+19h], 0
0x18003a167  jz      short loc_18003A15A
0x18003a169  jmp     short loc_18003A187
0x18003a16b  mov     rax, [rbx+8]
0x18003a16f  jmp     short loc_18003A17E
0x18003a171  cmp     rbx, [rax+10h]
0x18003a175  jnz     short loc_18003A184
0x18003a177  mov     rbx, rax
0x18003a17a  mov     rax, [rax+8]
0x18003a17e  cmp     byte ptr [rax+19h], 0
0x18003a182  jz      short loc_18003A171
0x18003a184  mov     rbx, rax
0x18003a187  cmp     [rdx+28h], rdi
0x18003a18b  jnz     short loc_18003A136
0x18003a18d  lea     rdx, [rsp+58h+arg_0]
0x18003a192  mov     rcx, rsi
0x18003a195  call    ?erase@?$_Tree@V?$_Tmap_traits@U_GUID@@PEBVCWcnWfdGoPeer@@UGuidCompare@@V?$allocator@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEBVCWcnWfdGoPeer@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<_GUID,CWcnWfdGoPeer const *,GuidCompare,std::allocator<std::pair<_GUID const,CWcnWfdGoPeer const *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CWcnWfdGoPeer const *>>>>)
0x18003a19a  jmp     short loc_18003A136
0x18003a19c  mov     r14, [r14+20h]
0x18003a1a0  mov     rsi, [r14]
0x18003a1a3  mov     rbx, [rsi]
0x18003a1a6  jmp     short loc_18003A1D1
0x18003a1a8  cmp     [rbx+10h], rdi
0x18003a1ac  jnz     short loc_18003A1CE
0x18003a1ae  mov     rdx, [rbx+8]
0x18003a1b2  mov     rcx, rbx
0x18003a1b5  mov     rax, [rbx]
0x18003a1b8  mov     rbx, rax
0x18003a1bb  mov     [rdx], rax
0x18003a1be  mov     [rax+8], rdx
0x18003a1c2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a1c8  dec     qword ptr [r14+8]
0x18003a1cc  jmp     short loc_18003A1D1
0x18003a1ce  mov     rbx, [rbx]
0x18003a1d1  cmp     rbx, rsi
0x18003a1d4  jnz     short loc_18003A1A8
0x18003a1d6  mov     rcx, rbp; lpCriticalSection
0x18003a1d9  call    cs:__imp_LeaveCriticalSection
0x18003a1df  mov     edx, 800704C7h; int
0x18003a1e4  mov     rcx, rdi; this
0x18003a1e7  call    ?CompleteActiveCallWithStatus@CWcnEventSink@@QEAAXJ@Z; CWcnEventSink::CompleteActiveCallWithStatus(long)
0x18003a1ec  mov     rcx, rdi; this
0x18003a1ef  call    ?ClearActiveCall@CWcnEventSink@@QEAAXXZ; CWcnEventSink::ClearActiveCall(void)
0x18003a1f4  test    rdi, rdi
0x18003a1f7  jz      short loc_18003A20A
0x18003a1f9  mov     rcx, rdi; this
0x18003a1fc  call    ??1CWcnEventSink@@QEAA@XZ; CWcnEventSink::~CWcnEventSink(void)
0x18003a201  mov     rcx, rdi
0x18003a204  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a20a  mov     r10, cs:WPP_GLOBAL_Control
0x18003a211  cmp     r10, r12
0x18003a214  jz      short loc_18003A23D
0x18003a216  cmp     byte ptr [r10+19h], 6
0x18003a21b  jb      short loc_18003A23D
0x18003a21d  or      ecx, 0FFFFFFFFh; int
0x18003a220  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003a225  mov     rcx, [r10+10h]
0x18003a229  lea     r8, WPP_e0de45765f7234980260fe5ced58e1dd_Traceguids
0x18003a230  mov     edx, 18h
0x18003a235  mov     r9, rax
0x18003a238  call    WPP_SF_s
0x18003a23d  add     rsp, 28h
0x18003a241  pop     r14
0x18003a243  pop     r12
0x18003a245  pop     rdi
0x18003a246  pop     rsi
0x18003a247  pop     rbp
0x18003a248  pop     rbx
0x18003a249  retn
```
