# FormatContext::~FormatContext(void)

- ea: `0x18003edd8`
- end: `0x18003ee5c`
- name: `??1FormatContext@@QEAA@XZ`
- size: `132`
- prototype: `void __fastcall(FormatContext *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18003f5e4`

## callees

- `0x1800201f8`
- `0x180020828`
- `0x18003eab8`
- `0x18003edd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003ede9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003ede9`

## pseudocode

```c
void __fastcall FormatContext::~FormatContext(FormatContext *this)
{
  _QWORD **v2; // rdi
  _QWORD *v3; // rbx
  _QWORD *v4; // rdx
  __int64 **v5; // r14
  __int64 v6; // rax
  __int64 *v7; // rdx
  __int64 *v8; // rcx
  __int64 v9; // rax

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v2 = (_QWORD **)((char *)this + 32);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    v4 = (_QWORD *)v3[1];
    v5 = (__int64 **)(v3 + 2);
    v6 = *v3;
    *v4 = *v3;
    *(_QWORD *)(v6 + 8) = v4;
    while ( 1 )
    {
      v7 = *v5;
      if ( *v5 == (__int64 *)v5 )
        break;
      v8 = (__int64 *)v7[1];
      v9 = *v7;
      *v8 = *v7;
      *(_QWORD *)(v9 + 8) = v8;
      utl::_ContainerBase<ENUM_INFO,utl::allocator<ENUM_INFO>>::_DeleteNode<utl::_DlistNode<ENUM_INFO>>(v8, v7);
    }
    v3[4] = 0;
    operator delete(v3, (const struct std::nothrow_t *)&std::nothrow);
  }
  *((_QWORD *)this + 6) = 0;
  utl::_Tree<_GUID,utl::pair<_GUID const,MESSAGE_GUID_LIST>,lessGuid,utl::allocator<utl::pair<_GUID const,MESSAGE_GUID_LIST>>,0>::clear(this);
}

```

## disassembly

```asm
0x18003edd8  push    rbx
0x18003edda  push    rsi
0x18003eddb  push    rdi
0x18003eddc  push    r14
0x18003edde  sub     rsp, 28h
0x18003ede2  mov     rsi, rcx
0x18003ede5  add     rcx, 38h ; '8'; lpCriticalSection
0x18003ede9  call    cs:__imp_DeleteCriticalSection
0x18003edef  lea     rdi, [rsi+20h]
0x18003edf3  mov     rbx, [rdi]
0x18003edf6  cmp     rbx, rdi
0x18003edf9  jz      short loc_18003EE43
0x18003edfb  mov     rdx, [rbx+8]
0x18003edff  lea     r14, [rbx+10h]
0x18003ee03  mov     rax, [rbx]
0x18003ee06  mov     [rdx], rax
0x18003ee09  mov     [rax+8], rdx
0x18003ee0d  mov     rdx, [r14]
0x18003ee10  cmp     rdx, r14
0x18003ee13  jz      short loc_18003EE2A
0x18003ee15  mov     rcx, [rdx+8]
0x18003ee19  mov     rax, [rdx]
0x18003ee1c  mov     [rcx], rax
0x18003ee1f  mov     [rax+8], rcx
0x18003ee23  call    ??$_DeleteNode@U?$_DlistNode@UENUM_INFO@@@utl@@@?$_ContainerBase@UENUM_INFO@@V?$allocator@UENUM_INFO@@@utl@@@utl@@IEAAXPEAU?$_DlistNode@UENUM_INFO@@@1@@Z; utl::_ContainerBase<ENUM_INFO,utl::allocator<ENUM_INFO>>::_DeleteNode<utl::_DlistNode<ENUM_INFO>>(utl::_DlistNode<ENUM_INFO> *)
0x18003ee28  jmp     short loc_18003EE0D
0x18003ee2a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003ee31  mov     qword ptr [r14+10h], 0
0x18003ee39  mov     rcx, rbx; void *
0x18003ee3c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ee41  jmp     short loc_18003EDF3
0x18003ee43  mov     rcx, rsi
0x18003ee46  mov     qword ptr [rdi+10h], 0
0x18003ee4e  add     rsp, 28h
0x18003ee52  pop     r14
0x18003ee54  pop     rdi
0x18003ee55  pop     rsi
0x18003ee56  pop     rbx
0x18003ee57  jmp     ?clear@?$_Tree@U_GUID@@U?$pair@$$CBU_GUID@@UMESSAGE_GUID_LIST@@@utl@@UlessGuid@@V?$allocator@U?$pair@$$CBU_GUID@@UMESSAGE_GUID_LIST@@@utl@@@3@$0A@@utl@@QEAAXXZ; utl::_Tree<_GUID,utl::pair<_GUID const,MESSAGE_GUID_LIST>,lessGuid,utl::allocator<utl::pair<_GUID const,MESSAGE_GUID_LIST>>,0>::clear(void)
```
