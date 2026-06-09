# CWcnPeerCache::~CWcnPeerCache(void)

- ea: `0x18000da4c`
- end: `0x18000db08`
- name: `??1CWcnPeerCache@@QEAA@XZ`
- size: `188`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002e04`
- `0x18005730a`

## callees

- `0x18000d998`
- `0x18000da4c`
- `0x18000fd10`
- `0x18001daa4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000daf1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000daf1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da5e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da68`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da5e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da68`

## pseudocode

```c
void __fastcall CWcnPeerCache::~CWcnPeerCache(struct _RTL_CRITICAL_SECTION *this)
{
  void **p_DebugInfo; // rdi
  __int64 *v3; // rbx
  __int64 *i; // rax
  __int64 *v5; // rcx
  char v6; // [rsp+30h] [rbp+8h] BYREF

  DeleteCriticalSection(this);
  DeleteCriticalSection(this + 1);
  p_DebugInfo = (void **)&this[2].DebugInfo;
  v3 = *(__int64 **)this[2].DebugInfo;
  while ( v3 != *p_DebugInfo )
  {
    CWcnPeer::CacheUnref((CWcnPeer *)v3[6]);
    if ( !*((_BYTE *)v3 + 25) )
    {
      i = (__int64 *)v3[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v3[1]; !*((_BYTE *)i + 25) && v3 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v3 = i;
LABEL_12:
        v3 = i;
      }
      else
      {
        v5 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 25) )
          goto LABEL_12;
        do
        {
          v3 = v5;
          v5 = (__int64 *)*v5;
        }
        while ( !*((_BYTE *)v5 + 25) );
      }
    }
  }
  std::_Tree<std::_Tmap_traits<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<enum tagWCN_DATATYPE>,std::allocator<std::pair<enum tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>::~_Tree<std::_Tmap_traits<enum tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<enum tagWCN_DATATYPE>,std::allocator<std::pair<enum tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>(&this[2].OwningThread);
  std::_Tree<std::_Tmap_traits<unsigned __int64,CWcnEventSink *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,CWcnEventSink *>>,1>>::erase(
    &this[2],
    &v6,
    *(_QWORD *)*p_DebugInfo,
    *p_DebugInfo);
  operator delete(*p_DebugInfo);
}

```

## disassembly

```asm
0x18000da4c  mov     [rsp+arg_8], rbx
0x18000da51  mov     [rsp+arg_10], rsi
0x18000da56  push    rdi
0x18000da57  sub     rsp, 20h
0x18000da5b  mov     rsi, rcx
0x18000da5e  call    cs:__imp_DeleteCriticalSection
0x18000da64  lea     rcx, [rsi+28h]; lpCriticalSection
0x18000da68  call    cs:__imp_DeleteCriticalSection
0x18000da6e  lea     rdi, [rsi+50h]
0x18000da72  mov     rbx, [rdi]
0x18000da75  mov     rbx, [rbx]
0x18000da78  cmp     rbx, [rdi]
0x18000da7b  jz      short loc_18000DACE
0x18000da7d  mov     rcx, [rbx+30h]; this
0x18000da81  call    ?CacheUnref@CWcnPeer@@QEAAXXZ; CWcnPeer::CacheUnref(void)
0x18000da86  cmp     byte ptr [rbx+19h], 0
0x18000da8a  jnz     short loc_18000DA78
0x18000da8c  mov     rax, [rbx+10h]
0x18000da90  cmp     byte ptr [rax+19h], 0
0x18000da94  jnz     short loc_18000DAB0
0x18000da96  mov     rcx, [rax]
0x18000da99  cmp     byte ptr [rcx+19h], 0
0x18000da9d  jnz     short loc_18000DAC9
0x18000da9f  mov     rbx, rcx
0x18000daa2  mov     rax, [rcx]
0x18000daa5  mov     rcx, rax
0x18000daa8  cmp     byte ptr [rax+19h], 0
0x18000daac  jz      short loc_18000DA9F
0x18000daae  jmp     short loc_18000DA78
0x18000dab0  mov     rax, [rbx+8]
0x18000dab4  jmp     short loc_18000DAC3
0x18000dab6  cmp     rbx, [rax+10h]
0x18000daba  jnz     short loc_18000DAC9
0x18000dabc  mov     rbx, rax
0x18000dabf  mov     rax, [rax+8]
0x18000dac3  cmp     byte ptr [rax+19h], 0
0x18000dac7  jz      short loc_18000DAB6
0x18000dac9  mov     rbx, rax
0x18000dacc  jmp     short loc_18000DA78
0x18000dace  lea     rcx, [rsi+60h]
0x18000dad2  call    ??1?$_Tree@V?$_Tmap_traits@W4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@U?$less@W4tagWCN_DATATYPE@@@std@@V?$allocator@U?$pair@$$CBW4tagWCN_DATATYPE@@PEBUtagWCN_DATATYPE_RULE@CWcnAttributeRules@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<tagWCN_DATATYPE>,std::allocator<std::pair<tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>::~_Tree<std::_Tmap_traits<tagWCN_DATATYPE,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *,std::less<tagWCN_DATATYPE>,std::allocator<std::pair<tagWCN_DATATYPE const,CWcnAttributeRules::tagWCN_DATATYPE_RULE const *>>,0>>(void)
0x18000dad7  nop
0x18000dad8  mov     r8, [rdi]
0x18000dadb  mov     r9, r8
0x18000dade  mov     r8, [r8]
0x18000dae1  lea     rdx, [rsp+28h+arg_0]
0x18000dae6  mov     rcx, rdi
0x18000dae9  call    ?erase@?$_Tree@V?$_Tmap_traits@_KPEAVCWcnEventSink@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@@3@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAVCWcnEventSink@@@std@@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,CWcnEventSink *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,CWcnEventSink *>>,1>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,CWcnEventSink *>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,CWcnEventSink *>>>>)
0x18000daee  mov     rcx, [rdi]
0x18000daf1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000daf7  nop
0x18000daf8  mov     rbx, [rsp+28h+arg_8]
0x18000dafd  mov     rsi, [rsp+28h+arg_10]
0x18000db02  add     rsp, 20h
0x18000db06  pop     rdi
0x18000db07  retn
```
