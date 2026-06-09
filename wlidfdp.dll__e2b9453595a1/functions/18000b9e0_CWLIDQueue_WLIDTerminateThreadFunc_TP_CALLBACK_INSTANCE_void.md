# CWLIDQueue::WLIDTerminateThreadFunc(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x18000b9e0`
- end: `0x18000baab`
- name: `?WLIDTerminateThreadFunc@CWLIDQueue@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `203`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, CWLIDQueue *Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002814`
- `0x180008edc`
- `0x180008f6c`
- `0x180009f14`
- `0x18000b9e0`
- `0x18000bbf8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b9fa`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b9fa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ba59`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ba91`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ba59`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000ba91`

## string_xrefs

- `0x18000ba20`: `CWLIDQueue::WLIDTerminateThreadFunc`

## pseudocode

```c
void __fastcall CWLIDQueue::WLIDTerminateThreadFunc(PTP_CALLBACK_INSTANCE Instance, CWLIDQueue *Context)
{
  CPassportException *v3; // [rsp+20h] [rbp-28h] BYREF
  ATL::CAtlException *v4; // [rsp+28h] [rbp-20h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h] BYREF
  const wil::ResultException *v6; // [rsp+38h] [rbp-10h] BYREF
  BOOL v7; // [rsp+58h] [rbp+10h]

  v7 = CoInitializeEx(0, 0) >= 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"\\wlidqueue.cpp",
    "CWLIDQueue::WLIDTerminateThreadFunc",
    (const char *)0x200);
  if ( !Context )
  {
    MsaTracingInternal::TraceFunctionExit((MsaTracingInternal *)"CWLIDQueue::WLIDTerminateThreadFunc", 0);
    if ( v7 )
      CoUninitialize();
    return;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    CWLIDQueue::_InternalTerminate(Context);
    CWLIDQueue::~CWLIDQueue((struct _RTL_CRITICAL_SECTION *)Context);
    operator delete(Context);
    MsaTracingInternal::TraceFunctionExit((MsaTracingInternal *)"CWLIDQueue::WLIDTerminateThreadFunc", 0);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &CPassportException `RTTI Type Descriptor', &v3) )
    {
      __eh34_try_continuation(0, &CPassportException `RTTI Type Descriptor', &loc_18000BAA2);
      goto LABEL_5;
    }
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v4) )
    {
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000BAA4);
      goto LABEL_5;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000BAA6);
      goto LABEL_5;
    }
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v5) )
    {
      __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_18000BAA8);
      goto LABEL_5;
    }
    if ( __eh34_catch_type(0, &wil::ResultException `RTTI Type Descriptor', &v6) )
      __eh34_try_continuation(0, &wil::ResultException `RTTI Type Descriptor', &loc_18000BA8A);
  }
LABEL_5:
  if ( v7 )
    CoUninitialize();
}

```

## disassembly

```asm
0x18000b9e0  mov     [rsp+arg_0], rbx
0x18000b9e5  push    rdi
0x18000b9e6  sub     rsp, 40h
0x18000b9ea  mov     rbx, rdx
0x18000b9ed  mov     [rsp+48h+arg_8], 0
0x18000b9f6  xor     edx, edx; dwCoInit
0x18000b9f8  xor     ecx, ecx; pvReserved
0x18000b9fa  call    cs:__imp_CoInitializeEx
0x18000ba00  mov     edx, eax
0x18000ba02  mov     ecx, 1
0x18000ba07  test    eax, eax
0x18000ba09  js      short loc_18000BA11
0x18000ba0b  mov     dword ptr [rsp+48h+arg_8], ecx
0x18000ba0f  jmp     short loc_18000BA20
0x18000ba11  xor     eax, eax
0x18000ba13  cmp     edx, 80010106h
0x18000ba19  cmovz   eax, ecx
0x18000ba1c  mov     dword ptr [rsp+48h+arg_8+4], eax
0x18000ba20  lea     rdi, aCwlidqueueWlid; "CWLIDQueue::WLIDTerminateThreadFunc"
0x18000ba27  mov     [rsp+48h+arg_10], rdi
0x18000ba2c  mov     r8d, 200h; char *
0x18000ba32  mov     rdx, rdi; char *
0x18000ba35  lea     rcx, aWlidqueueCpp; "\\wlidqueue.cpp"
0x18000ba3c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000ba41  nop
0x18000ba42  test    rbx, rbx
0x18000ba45  jnz     short loc_18000BA61
0x18000ba47  xor     edx, edx; char *
0x18000ba49  mov     rcx, rdi; this
0x18000ba4c  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x18000ba51  nop
0x18000ba52  cmp     dword ptr [rsp+48h+arg_8], 0
0x18000ba57  jz      short loc_18000BA5F
0x18000ba59  call    cs:__imp_CoUninitialize
0x18000ba5f  jmp     short loc_18000BA97
0x18000ba61  mov     rcx, rbx; this
0x18000ba64  call    ?_InternalTerminate@CWLIDQueue@@AEAAJXZ; CWLIDQueue::_InternalTerminate(void)
0x18000ba69  mov     rcx, rbx; this
0x18000ba6c  call    ??1CWLIDQueue@@QEAA@XZ; CWLIDQueue::~CWLIDQueue(void)
0x18000ba71  mov     edx, 0D0h
0x18000ba76  mov     rcx, rbx; Block
0x18000ba79  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ba7e  nop
0x18000ba7f  xor     edx, edx; char *
0x18000ba81  mov     rcx, rdi; this
0x18000ba84  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x18000ba89  nop
0x18000ba8a  cmp     dword ptr [rsp+48h+arg_8], 0
0x18000ba8f  jz      short loc_18000BA97
0x18000ba91  call    cs:__imp_CoUninitialize
0x18000ba97  mov     rbx, [rsp+48h+arg_0]
0x18000ba9c  add     rsp, 40h
0x18000baa0  pop     rdi
0x18000baa1  retn
0x18000baa2  jmp     short loc_18000BA8A
0x18000baa4  jmp     short loc_18000BA8A
0x18000baa6  jmp     short loc_18000BA8A
0x18000baa8  jmp     short loc_18000BA8A
```
