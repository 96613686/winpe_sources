# CWlanProfileStore::MoveProfile(CProfile const &,int)

- ea: `0x18002b320`
- end: `0x18002b429`
- name: `?MoveProfile@CWlanProfileStore@@UEAAXAEBVCProfile@@H@Z`
- size: `265`
- prototype: `void __fastcall(CWlanProfileStore *__hidden this, const struct CProfile *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800027d0`
- `0x180003014`
- `0x18000d4c8`
- `0x180010500`
- `0x18001215c`
- `0x180029f38`
- `0x18002b320`
- `0x18002bfc0`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CWlanProfileStore::MoveProfile(CWlanProfileStore *this, const struct CProfile *a2, int a3)
{
  int v6; // esi
  char *v7; // rbx
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 *v12; // rcx
  __int64 Index; // rax
  _BYTE v14[56]; // [rsp+20h] [rbp-38h] BYREF

  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    v14,
    (char *)this + 96);
  if ( !*((_BYTE *)a2 + 81) )
  {
    v6 = (*(__int64 (__fastcall **)(CWlanProfileStore *, const struct CProfile *))(*(_QWORD *)this + 64LL))(this, a2);
    if ( v6 != -1 && a3 != v6 )
    {
      v7 = (char *)this + 184;
      if ( !a3 )
      {
LABEL_5:
        ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::AddHead(v7, a2);
LABEL_14:
        Index = ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::FindIndex(v7);
        ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAt(v7, Index);
        goto LABEL_15;
      }
      v8 = *((_DWORD *)v7 + 4) - 1;
      if ( a3 < v8 )
      {
        v9 = ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::FindIndex(v7);
        v10 = v9;
        if ( v9 )
        {
          v11 = ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::NewNode(v7, a2, *(_QWORD *)(v9 + 8), v9);
          v12 = *(__int64 **)(v10 + 8);
          if ( v12 )
            *v12 = v11;
          else
            *(_QWORD *)v7 = v11;
          *(_QWORD *)(v10 + 8) = v11;
          goto LABEL_14;
        }
        goto LABEL_5;
      }
      if ( a3 == v8 )
      {
        ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::AddTail(v7, a2);
        goto LABEL_14;
      }
    }
  }
LABEL_15:
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v14);
}

```

## disassembly

```asm
0x18002b320  push    rbx
0x18002b322  push    rbp
0x18002b323  push    rsi
0x18002b324  push    rdi
0x18002b325  push    r14
0x18002b327  sub     rsp, 30h
0x18002b32b  mov     edi, r8d
0x18002b32e  mov     rbp, rdx
0x18002b331  mov     rbx, rcx
0x18002b334  lea     rdx, [rcx+60h]
0x18002b338  lea     rcx, [rsp+58h+var_38]
0x18002b33d  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18002b342  nop
0x18002b343  cmp     byte ptr [rbp+51h], 0
0x18002b347  jnz     loc_18002B414
0x18002b34d  mov     rax, [rbx]
0x18002b350  mov     rdx, rbp
0x18002b353  mov     rcx, rbx
0x18002b356  mov     rax, [rax+40h]
0x18002b35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b35f  movsxd  rsi, eax
0x18002b362  cmp     esi, 0FFFFFFFFh
0x18002b365  jz      loc_18002B414
0x18002b36b  cmp     edi, esi
0x18002b36d  jz      loc_18002B414
0x18002b373  add     rbx, 0B8h
0x18002b37a  test    edi, edi
0x18002b37c  jnz     short loc_18002B391
0x18002b37e  mov     rdx, rbp
0x18002b381  mov     rcx, rbx
0x18002b384  call    ?AddHead@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBVCProfile@@@Z; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::AddHead(CProfile const &)
0x18002b389  lea     eax, [rsi+1]
0x18002b38c  movsxd  rdx, eax
0x18002b38f  jmp     short loc_18002B400
0x18002b391  mov     eax, [rbx+10h]
0x18002b394  dec     eax
0x18002b396  cmp     edi, eax
0x18002b398  jge     short loc_18002B3F0
0x18002b39a  lea     r14d, [rdi+1]
0x18002b39e  cmp     edi, esi
0x18002b3a0  cmovle  r14d, edi
0x18002b3a4  movsxd  rdx, r14d
0x18002b3a7  mov     rcx, rbx
0x18002b3aa  call    ?FindIndex@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEBAPEAU__POSITION@@_K@Z; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::FindIndex(unsigned __int64)
0x18002b3af  mov     rdi, rax
0x18002b3b2  mov     rdx, rbp
0x18002b3b5  mov     rcx, rbx
0x18002b3b8  test    rax, rax
0x18002b3bb  jnz     short loc_18002B3C4
0x18002b3bd  call    ?AddHead@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBVCProfile@@@Z; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::AddHead(CProfile const &)
0x18002b3c2  jmp     short loc_18002B3E5
0x18002b3c4  mov     r9, rdi
0x18002b3c7  mov     r8, [rax+8]
0x18002b3cb  call    ?NewNode@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@AEAAPEAVCNode@12@AEBVCProfile@@PEAV312@1@Z; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::NewNode(CProfile const &,ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::CNode *,ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::CNode *)
0x18002b3d0  mov     rcx, [rdi+8]
0x18002b3d4  test    rcx, rcx
0x18002b3d7  jz      short loc_18002B3DE
0x18002b3d9  mov     [rcx], rax
0x18002b3dc  jmp     short loc_18002B3E1
0x18002b3de  mov     [rbx], rax
0x18002b3e1  mov     [rdi+8], rax
0x18002b3e5  lea     eax, [rsi+1]
0x18002b3e8  cmp     r14d, esi
0x18002b3eb  cmovge  eax, esi
0x18002b3ee  jmp     short loc_18002B38C
0x18002b3f0  jnz     short loc_18002B414
0x18002b3f2  mov     rdx, rbp
0x18002b3f5  mov     rcx, rbx
0x18002b3f8  call    ?AddTail@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBVCProfile@@@Z; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::AddTail(CProfile const &)
0x18002b3fd  mov     rdx, rsi
0x18002b400  mov     rcx, rbx
0x18002b403  call    ?FindIndex@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEBAPEAU__POSITION@@_K@Z; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::FindIndex(unsigned __int64)
0x18002b408  mov     rdx, rax
0x18002b40b  mov     rcx, rbx
0x18002b40e  call    ?RemoveAt@?$CAtlList@VCProfile@@V?$CElementTraits@VCProfile@@@ATL@@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<CProfile,ATL::CElementTraits<CProfile>>::RemoveAt(__POSITION *)
0x18002b413  nop
0x18002b414  lea     rcx, [rsp+58h+var_38]
0x18002b419  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18002b41e  add     rsp, 30h
0x18002b422  pop     r14
0x18002b424  pop     rdi
0x18002b425  pop     rsi
0x18002b426  pop     rbp
0x18002b427  pop     rbx
0x18002b428  retn
```
