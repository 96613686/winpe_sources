# wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::~svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>(void)

- ea: `0x180007684`
- end: `0x1800076e6`
- name: `??1?$svchost_service_t@Uservice_traits_whesvc@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800282f0`

## callees

- `0x180007684`
- `0x180009d5c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076b7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800076ca`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800076ca`

## pseudocode

```c
void __fastcall wil::svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>::~svchost_service_t<service_traits_whesvc,wil::err_returncode_policy>(
        _QWORD *a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  void *v3; // rcx
  unsigned int v4; // r8d
  const char *v5; // r9
  void *v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void (__fastcall ***)(_QWORD, __int64))a1[3];
  a1[3] = 0;
  if ( v2 )
    (**v2)(v2, 1);
  v3 = (void *)a1[2];
  if ( v3 && !CloseHandle(v3) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v4, v5);
  v6 = (void *)a1[1];
  if ( v6 )
    UnregisterWait(v6);
}

```

## disassembly

```asm
0x180007684  push    rbx
0x180007686  sub     rsp, 20h
0x18000768a  mov     rbx, rcx
0x18000768d  mov     rcx, [rcx+18h]
0x180007691  mov     qword ptr [rbx+18h], 0
0x180007699  test    rcx, rcx
0x18000769c  jz      short loc_1800076AE
0x18000769e  mov     rax, [rcx]
0x1800076a1  mov     edx, 1
0x1800076a6  mov     rax, [rax]
0x1800076a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ae  mov     rcx, [rbx+10h]; hObject
0x1800076b2  test    rcx, rcx
0x1800076b5  jz      short loc_1800076C1
0x1800076b7  call    cs:__imp_CloseHandle
0x1800076bd  test    eax, eax
0x1800076bf  jz      short loc_1800076D6
0x1800076c1  mov     rcx, [rbx+8]; WaitHandle
0x1800076c5  test    rcx, rcx
0x1800076c8  jz      short loc_1800076D0
0x1800076ca  call    cs:__imp_UnregisterWait
0x1800076d0  add     rsp, 20h
0x1800076d4  pop     rbx
0x1800076d5  retn
0x1800076d6  mov     rcx, [rsp+28h]; this
0x1800076db  mov     edx, 0A0Bh; void *
0x1800076e0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
