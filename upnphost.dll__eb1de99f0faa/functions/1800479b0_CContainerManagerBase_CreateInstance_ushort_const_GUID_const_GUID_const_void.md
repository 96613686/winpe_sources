# CContainerManagerBase::CreateInstance(ushort const *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800479b0`
- end: `0x180047aeb`
- name: `?CreateInstance@CContainerManagerBase@@QEAAJPEBGAEBU_GUID@@1PEAPEAX@Z`
- size: `315`
- prototype: `__int64 __fastcall(CContainerManagerBase *this, const unsigned __int16 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180047950`
- `0x180047b60`

## callees

- `0x180013180`
- `0x18001ab90`
- `0x180038ce4`
- `0x1800479b0`
- `0x180047d90`
- `0x1800507d0`
- `0x180055010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180047a93`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180047a93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180047a79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180047a79`

## pseudocode

```c
__int64 __fastcall CContainerManagerBase::CreateInstance(
        CContainerManagerBase *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        void **a5)
{
  int IsAllowedCOMCallLocality; // ebx
  __int64 *v10; // rdi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD); // rbx
  DWORD CurrentProcessId; // eax
  __int64 *v15; // [rsp+30h] [rbp-28h] BYREF
  void *Block; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 || !a5 )
    return 2147500035LL;
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality >= 0 )
  {
    IsAllowedCOMCallLocality = ValidateCallerAccess();
    if ( IsAllowedCOMCallLocality >= 0 )
    {
      Block = 0;
      IsAllowedCOMCallLocality = CUString::HrAssign((CUString *)&Block, a2);
      if ( IsAllowedCOMCallLocality >= 0 )
      {
        v15 = 0;
        IsAllowedCOMCallLocality = CTable<CUString,ContainerInfo>::HrLookup(this, &Block, &v15);
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          v10 = v15;
          IsAllowedCOMCallLocality = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)*v15 + 24LL))(
                                       *v15,
                                       a3,
                                       a4,
                                       a5);
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            v11 = *v10;
            v12 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 40LL);
            CurrentProcessId = GetCurrentProcessId();
            IsAllowedCOMCallLocality = v12(v11, CurrentProcessId);
          }
        }
      }
      free(Block);
    }
  }
  if ( IsAllowedCOMCallLocality
    && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_689efb96ff203bf804ee80d0c70e112e_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  }
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x1800479b0  mov     [rsp+arg_0], rbx
0x1800479b5  mov     [rsp+arg_10], rbp
0x1800479ba  push    rdi
0x1800479bb  push    r14
0x1800479bd  push    r15
0x1800479bf  sub     rsp, 40h
0x1800479c3  mov     r14, r9
0x1800479c6  mov     r15, r8
0x1800479c9  mov     rdi, rdx
0x1800479cc  mov     rbp, rcx
0x1800479cf  test    rdx, rdx
0x1800479d2  jz      loc_180047AD2
0x1800479d8  cmp     [rsp+58h+arg_20], 0
0x1800479e1  jz      loc_180047AD2
0x1800479e7  mov     ecx, 1
0x1800479ec  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x1800479f1  mov     ebx, eax
0x1800479f3  test    eax, eax
0x1800479f5  js      loc_180047A99
0x1800479fb  call    ?ValidateCallerAccess@@YAJXZ; ValidateCallerAccess(void)
0x180047a00  mov     ebx, eax
0x180047a02  test    eax, eax
0x180047a04  js      loc_180047A99
0x180047a0a  mov     rdx, rdi; unsigned __int16 *
0x180047a0d  mov     [rsp+58h+Block], 0
0x180047a16  lea     rcx, [rsp+58h+Block]; this
0x180047a1b  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180047a20  mov     ebx, eax
0x180047a22  test    eax, eax
0x180047a24  js      short loc_180047A8E
0x180047a26  lea     r8, [rsp+58h+var_28]
0x180047a2b  mov     [rsp+58h+var_28], 0
0x180047a34  lea     rdx, [rsp+58h+Block]
0x180047a39  mov     rcx, rbp
0x180047a3c  call    ?HrLookup@?$CTable@VCUString@@UContainerInfo@@@@QEAAJAEBVCUString@@PEAPEAUContainerInfo@@@Z; CTable<CUString,ContainerInfo>::HrLookup(CUString const &,ContainerInfo * *)
0x180047a41  mov     ebx, eax
0x180047a43  test    eax, eax
0x180047a45  js      short loc_180047A8E
0x180047a47  mov     rdi, [rsp+58h+var_28]
0x180047a4c  mov     r8, r14
0x180047a4f  mov     r9, [rsp+58h+arg_20]
0x180047a57  mov     rdx, r15
0x180047a5a  mov     rcx, [rdi]
0x180047a5d  mov     rax, [rcx]
0x180047a60  mov     rax, [rax+18h]
0x180047a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a69  mov     ebx, eax
0x180047a6b  test    eax, eax
0x180047a6d  js      short loc_180047A8E
0x180047a6f  mov     rdi, [rdi]
0x180047a72  mov     rax, [rdi]
0x180047a75  mov     rbx, [rax+28h]
0x180047a79  call    cs:__imp_GetCurrentProcessId
0x180047a7f  mov     edx, eax
0x180047a81  mov     rcx, rdi
0x180047a84  mov     rax, rbx
0x180047a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a8c  mov     ebx, eax
0x180047a8e  mov     rcx, [rsp+58h+Block]; Block
0x180047a93  call    cs:__imp_free
0x180047a99  test    ebx, ebx
0x180047a9b  jz      short loc_180047ACE
0x180047a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180047aa4  lea     rax, WPP_GLOBAL_Control
0x180047aab  cmp     rcx, rax
0x180047aae  jz      short loc_180047ACE
0x180047ab0  test    byte ptr [rcx+1Ch], 1
0x180047ab4  jz      short loc_180047ACE
0x180047ab6  mov     rcx, [rcx+10h]
0x180047aba  lea     r8, WPP_689efb96ff203bf804ee80d0c70e112e_Traceguids
0x180047ac1  mov     edx, 0Ch
0x180047ac6  mov     r9d, ebx
0x180047ac9  call    WPP_SF_d
0x180047ace  mov     eax, ebx
0x180047ad0  jmp     short loc_180047AD7
0x180047ad2  mov     eax, 80004003h
0x180047ad7  mov     rbx, [rsp+58h+arg_0]
0x180047adc  mov     rbp, [rsp+58h+arg_10]
0x180047ae1  add     rsp, 40h
0x180047ae5  pop     r15
0x180047ae7  pop     r14
0x180047ae9  pop     rdi
0x180047aea  retn
```
