# CContainerManagerBase::CreateInstance(ushort const *,_GUID const &,_GUID const &,void * *)

- ea: `0x18004a768`
- end: `0x18004a8b0`
- name: `?CreateInstance@CContainerManagerBase@@QEAAJPEBGAEBU_GUID@@1PEAPEAX@Z`
- size: `328`
- prototype: `__int64 __fastcall(CContainerManagerBase *this, const unsigned __int16 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004a700`
- `0x18004a928`

## callees

- `0x1800071c0`
- `0x18000f8a0`
- `0x18003b1cc`
- `0x18004a768`
- `0x18004ab60`
- `0x180053e68`
- `0x180059010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a851`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a851`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004a831`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004a831`

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
0x18004a768  mov     [rsp+arg_0], rbx
0x18004a76d  mov     [rsp+arg_10], rbp
0x18004a772  push    rdi
0x18004a773  push    r14
0x18004a775  push    r15
0x18004a777  sub     rsp, 40h
0x18004a77b  mov     r14, r9
0x18004a77e  mov     r15, r8
0x18004a781  mov     rdi, rdx
0x18004a784  mov     rbp, rcx
0x18004a787  test    rdx, rdx
0x18004a78a  jz      loc_18004A896
0x18004a790  cmp     [rsp+58h+arg_20], 0
0x18004a799  jz      loc_18004A896
0x18004a79f  mov     ecx, 1
0x18004a7a4  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18004a7a9  mov     ebx, eax
0x18004a7ab  test    eax, eax
0x18004a7ad  js      loc_18004A85D
0x18004a7b3  call    ?ValidateCallerAccess@@YAJXZ; ValidateCallerAccess(void)
0x18004a7b8  mov     ebx, eax
0x18004a7ba  test    eax, eax
0x18004a7bc  js      loc_18004A85D
0x18004a7c2  mov     rdx, rdi; unsigned __int16 *
0x18004a7c5  mov     [rsp+58h+Block], 0
0x18004a7ce  lea     rcx, [rsp+58h+Block]; this
0x18004a7d3  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x18004a7d8  mov     ebx, eax
0x18004a7da  test    eax, eax
0x18004a7dc  js      short loc_18004A84C
0x18004a7de  lea     r8, [rsp+58h+var_28]
0x18004a7e3  mov     [rsp+58h+var_28], 0
0x18004a7ec  lea     rdx, [rsp+58h+Block]
0x18004a7f1  mov     rcx, rbp
0x18004a7f4  call    ?HrLookup@?$CTable@VCUString@@UContainerInfo@@@@QEAAJAEBVCUString@@PEAPEAUContainerInfo@@@Z; CTable<CUString,ContainerInfo>::HrLookup(CUString const &,ContainerInfo * *)
0x18004a7f9  mov     ebx, eax
0x18004a7fb  test    eax, eax
0x18004a7fd  js      short loc_18004A84C
0x18004a7ff  mov     rdi, [rsp+58h+var_28]
0x18004a804  mov     r8, r14
0x18004a807  mov     r9, [rsp+58h+arg_20]
0x18004a80f  mov     rdx, r15
0x18004a812  mov     rcx, [rdi]
0x18004a815  mov     rax, [rcx]
0x18004a818  mov     rax, [rax+18h]
0x18004a81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a821  mov     ebx, eax
0x18004a823  test    eax, eax
0x18004a825  js      short loc_18004A84C
0x18004a827  mov     rdi, [rdi]
0x18004a82a  mov     rax, [rdi]
0x18004a82d  mov     rbx, [rax+28h]
0x18004a831  call    cs:__imp_GetCurrentProcessId
0x18004a838  nop     dword ptr [rax+rax+00h]
0x18004a83d  mov     edx, eax
0x18004a83f  mov     rcx, rdi
0x18004a842  mov     rax, rbx
0x18004a845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a84a  mov     ebx, eax
0x18004a84c  mov     rcx, [rsp+58h+Block]; Block
0x18004a851  call    cs:__imp_free
0x18004a858  nop     dword ptr [rax+rax+00h]
0x18004a85d  test    ebx, ebx
0x18004a85f  jz      short loc_18004A892
0x18004a861  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a868  lea     rax, WPP_GLOBAL_Control
0x18004a86f  cmp     rcx, rax
0x18004a872  jz      short loc_18004A892
0x18004a874  test    byte ptr [rcx+1Ch], 1
0x18004a878  jz      short loc_18004A892
0x18004a87a  mov     rcx, [rcx+10h]
0x18004a87e  lea     r8, WPP_689efb96ff203bf804ee80d0c70e112e_Traceguids
0x18004a885  mov     edx, 0Ch
0x18004a88a  mov     r9d, ebx
0x18004a88d  call    WPP_SF_d
0x18004a892  mov     eax, ebx
0x18004a894  jmp     short loc_18004A89B
0x18004a896  mov     eax, 80004003h
0x18004a89b  mov     rbx, [rsp+58h+arg_0]
0x18004a8a0  mov     rbp, [rsp+58h+arg_10]
0x18004a8a5  add     rsp, 40h
0x18004a8a9  pop     r15
0x18004a8ab  pop     r14
0x18004a8ad  pop     rdi
0x18004a8ae  retn
```
