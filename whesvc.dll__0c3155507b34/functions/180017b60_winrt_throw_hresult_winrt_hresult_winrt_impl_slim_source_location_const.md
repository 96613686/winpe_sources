# winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x180017b60`
- end: `0x180017d84`
- name: `?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z`
- size: `548`
- prototype: `void __fastcall __noreturn(_QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010094`
- `0x1800120a0`
- `0x18001399c`
- `0x18001a69c`
- `0x18001a868`
- `0x18001bfec`
- `0x18001c0e4`
- `0x1800202a8`
- `0x180020310`
- `0x180020634`
- `0x180020a8c`
- `0x180020b44`
- `0x1800214d8`
- `0x18002275c`
- `0x1800227bc`
- `0x180022fcc`
- `0x180023378`
- `0x1800233d8`
- `0x180023ae8`
- `0x180023efc`
- `0x1800255e0`
- `0x1800256ac`

## callees

- `0x180003db0`
- `0x1800050f0`
- `0x180010f38`
- `0x180010f60`
- `0x180010f88`
- `0x180010fb0`
- `0x180010fd8`
- `0x180011000`
- `0x1800112a8`
- `0x1800112d0`
- `0x1800112f8`
- `0x180011320`
- `0x180011348`
- `0x180011370`
- `0x180011398`
- `0x1800113c0`
- `0x180017b60`
- `0x180029010`

## pseudocode

```c
void __fastcall __noreturn winrt::throw_hresult(unsigned int a1, unsigned int *a2, __int64 a3)
{
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-20h] BYREF
  void *retaddr; // [rsp+58h] [rbp+8h]

  if ( winrt_throw_hresult_handler )
    winrt_throw_hresult_handler(*a2, *((_QWORD *)a2 + 1), *((_QWORD *)a2 + 2), retaddr, a1);
  switch ( a1 )
  {
    case 0x8007000E:
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    case 0x80070005:
      winrt::hresult_access_denied::hresult_access_denied((__int64)pExceptionObject, (__int64)a2, (__int64)a2);
      throw (winrt::hresult_access_denied *)pExceptionObject;
    case 0x8001010E:
      winrt::hresult_wrong_thread::hresult_wrong_thread((__int64)pExceptionObject, (__int64)a2, a2);
      throw (winrt::hresult_wrong_thread *)pExceptionObject;
    case 0x80004001:
      winrt::hresult_not_implemented::hresult_not_implemented(pExceptionObject, a2, a2);
      throw (winrt::hresult_not_implemented *)pExceptionObject;
    case 0x80070057:
      winrt::hresult_invalid_argument::hresult_invalid_argument(pExceptionObject, a2, a2);
      throw (winrt::hresult_invalid_argument *)pExceptionObject;
    case 0x8000000B:
      winrt::hresult_out_of_bounds::hresult_out_of_bounds(pExceptionObject, a2, a2);
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    case 0x80004002:
      winrt::hresult_no_interface::hresult_no_interface(pExceptionObject, a2, a2);
      throw (winrt::hresult_no_interface *)pExceptionObject;
    case 0x80040111:
      winrt::hresult_class_not_available::hresult_class_not_available(pExceptionObject, a2, a2);
      throw (winrt::hresult_class_not_available *)pExceptionObject;
    case 0x80040154:
      winrt::hresult_class_not_registered::hresult_class_not_registered(pExceptionObject, a2, a2);
      throw (winrt::hresult_class_not_registered *)pExceptionObject;
    case 0x8000000C:
      winrt::hresult_changed_state::hresult_changed_state(pExceptionObject, a2, a2);
      throw (winrt::hresult_changed_state *)pExceptionObject;
    case 0x8000000E:
      winrt::hresult_illegal_method_call::hresult_illegal_method_call(pExceptionObject, a2, a2);
      throw (winrt::hresult_illegal_method_call *)pExceptionObject;
    case 0x8000000D:
      winrt::hresult_illegal_state_change::hresult_illegal_state_change(pExceptionObject, a2, a2);
      throw (winrt::hresult_illegal_state_change *)pExceptionObject;
    case 0x80000018:
      winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(pExceptionObject, a2, a2);
      throw (winrt::hresult_illegal_delegate_assignment *)pExceptionObject;
    case 0x800704C7:
      winrt::hresult_canceled::hresult_canceled(pExceptionObject, a2, a2);
      throw (winrt::hresult_canceled *)pExceptionObject;
  }
  winrt::hresult_error::hresult_error((__int64)pExceptionObject, a1, a3, a2);
  throw (winrt::hresult_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180017b60  mov     [rsp-8+arg_0], rbx
0x180017b65  mov     [rsp-8+arg_8], rdi
0x180017b6a  push    rbp
0x180017b6b  mov     rbp, rsp
0x180017b6e  sub     rsp, 50h
0x180017b72  mov     rax, cs:?winrt_throw_hresult_handler@@3P6AXIPEBD0PEAXUhresult@winrt@@@_EEA
0x180017b79  mov     rdi, rdx
0x180017b7c  mov     ebx, ecx
0x180017b7e  test    rax, rax
0x180017b81  jz      short loc_180017B9A
0x180017b83  mov     r8, [rdx+10h]
0x180017b87  mov     rdx, [rdx+8]
0x180017b8b  mov     r9, [rbp+8]
0x180017b8f  mov     [rsp+50h+var_30], ecx
0x180017b93  mov     ecx, [rdi]
0x180017b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b9a  lea     rcx, [rbp+pExceptionObject]; this
0x180017b9e  cmp     ebx, 8007000Eh
0x180017ba4  jnz     short loc_180017BBC
0x180017ba6  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180017bab  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180017bb2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017bb6  call    _CxxThrowException_0
0x180017bbc  cmp     ebx, 80070005h
0x180017bc2  jnz     short loc_180017BDD
0x180017bc4  mov     r8, rdi
0x180017bc7  call    ??0hresult_access_denied@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_access_denied::hresult_access_denied(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017bcc  lea     rdx, _TI2?AUhresult_access_denied@winrt@@; pThrowInfo
0x180017bd3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017bd7  call    _CxxThrowException_0
0x180017bdd  cmp     ebx, 8001010Eh
0x180017be3  jnz     short loc_180017BFE
0x180017be5  mov     r8, rdi
0x180017be8  call    ??0hresult_wrong_thread@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_wrong_thread::hresult_wrong_thread(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017bed  lea     rdx, _TI2?AUhresult_wrong_thread@winrt@@; pThrowInfo
0x180017bf4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017bf8  call    _CxxThrowException_0
0x180017bfe  cmp     ebx, 80004001h
0x180017c04  jnz     short loc_180017C1F
0x180017c06  mov     r8, rdi
0x180017c09  call    ??0hresult_not_implemented@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_not_implemented::hresult_not_implemented(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017c0e  lea     rdx, _TI2?AUhresult_not_implemented@winrt@@; pThrowInfo
0x180017c15  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017c19  call    _CxxThrowException_0
0x180017c1f  cmp     ebx, 80070057h
0x180017c25  jnz     short loc_180017C40
0x180017c27  mov     r8, rdi
0x180017c2a  call    ??0hresult_invalid_argument@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017c2f  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180017c36  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017c3a  call    _CxxThrowException_0
0x180017c40  cmp     ebx, 8000000Bh
0x180017c46  jnz     short loc_180017C61
0x180017c48  mov     r8, rdi
0x180017c4b  call    ??0hresult_out_of_bounds@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_out_of_bounds::hresult_out_of_bounds(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017c50  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180017c57  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017c5b  call    _CxxThrowException_0
0x180017c61  cmp     ebx, 80004002h
0x180017c67  jnz     short loc_180017C82
0x180017c69  mov     r8, rdi
0x180017c6c  call    ??0hresult_no_interface@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_no_interface::hresult_no_interface(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017c71  lea     rdx, _TI2?AUhresult_no_interface@winrt@@; pThrowInfo
0x180017c78  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017c7c  call    _CxxThrowException_0
0x180017c82  cmp     ebx, 80040111h
0x180017c88  jnz     short loc_180017CA3
0x180017c8a  mov     r8, rdi
0x180017c8d  call    ??0hresult_class_not_available@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_available::hresult_class_not_available(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017c92  lea     rdx, _TI2?AUhresult_class_not_available@winrt@@; pThrowInfo
0x180017c99  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017c9d  call    _CxxThrowException_0
0x180017ca3  cmp     ebx, 80040154h
0x180017ca9  jnz     short loc_180017CC4
0x180017cab  mov     r8, rdi
0x180017cae  call    ??0hresult_class_not_registered@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_class_not_registered::hresult_class_not_registered(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017cb3  lea     rdx, _TI2?AUhresult_class_not_registered@winrt@@; pThrowInfo
0x180017cba  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017cbe  call    _CxxThrowException_0
0x180017cc4  cmp     ebx, 8000000Ch
0x180017cca  jnz     short loc_180017CE5
0x180017ccc  mov     r8, rdi
0x180017ccf  call    ??0hresult_changed_state@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_changed_state::hresult_changed_state(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017cd4  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180017cdb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017cdf  call    _CxxThrowException_0
0x180017ce5  cmp     ebx, 8000000Eh
0x180017ceb  jnz     short loc_180017D06
0x180017ced  mov     r8, rdi
0x180017cf0  call    ??0hresult_illegal_method_call@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017cf5  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x180017cfc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017d00  call    _CxxThrowException_0
0x180017d06  cmp     ebx, 8000000Dh
0x180017d0c  jnz     short loc_180017D27
0x180017d0e  mov     r8, rdi
0x180017d11  call    ??0hresult_illegal_state_change@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_state_change::hresult_illegal_state_change(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017d16  lea     rdx, _TI2?AUhresult_illegal_state_change@winrt@@; pThrowInfo
0x180017d1d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017d21  call    _CxxThrowException_0
0x180017d27  cmp     ebx, 80000018h
0x180017d2d  jnz     short loc_180017D48
0x180017d2f  mov     r8, rdi
0x180017d32  call    ??0hresult_illegal_delegate_assignment@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_delegate_assignment::hresult_illegal_delegate_assignment(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017d37  lea     rdx, _TI2?AUhresult_illegal_delegate_assignment@winrt@@; pThrowInfo
0x180017d3e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017d42  call    _CxxThrowException_0
0x180017d48  cmp     ebx, 800704C7h
0x180017d4e  jnz     short loc_180017D69
0x180017d50  mov     r8, rdi
0x180017d53  call    ??0hresult_canceled@winrt@@QEAA@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017d58  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180017d5f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017d63  call    _CxxThrowException_0
0x180017d69  mov     r9, rdi
0x180017d6c  mov     edx, ebx
0x180017d6e  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@Utake_ownership_from_abi_t@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::take_ownership_from_abi_t,winrt::impl::slim_source_location const &)
0x180017d73  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180017d7a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180017d7e  call    _CxxThrowException_0
```
