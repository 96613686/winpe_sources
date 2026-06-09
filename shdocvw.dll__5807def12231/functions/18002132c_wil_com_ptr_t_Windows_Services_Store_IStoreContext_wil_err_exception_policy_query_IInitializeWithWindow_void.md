# wil::com_ptr_t<Windows::Services::Store::IStoreContext,wil::err_exception_policy>::query<IInitializeWithWindow>(void)

- ea: `0x18002132c`
- end: `0x18002137b`
- name: `??$query@UIInitializeWithWindow@@@?$com_ptr_t@UIStoreContext@Store@Services@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIInitializeWithWindow@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005b0c`
- `0x1800060a8`

## callees

- `0x18001a610`
- `0x18002132c`
- `0x180029010`

## string_xrefs

- `0x18002135d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<Windows::Services::Store::IStoreContext,wil::err_exception_policy>::query<IInitializeWithWindow>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1, a2);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v4,
      v6);
  return a2;
}

```

## disassembly

```asm
0x18002132c  push    rbx
0x18002132e  sub     rsp, 30h
0x180021332  mov     rcx, [rcx]
0x180021335  mov     rbx, rdx
0x180021338  mov     qword ptr [rdx], 0
0x18002133f  mov     r8, rdx
0x180021342  lea     rdx, _GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1
0x180021349  mov     rax, [rcx]
0x18002134c  mov     rax, [rax]
0x18002134f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021354  test    eax, eax
0x180021356  jns     short loc_180021372
0x180021358  mov     rcx, [rsp+38h]; this
0x18002135d  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021364  mov     r9d, eax; char *
0x180021367  mov     edx, 1CBEh; void *
0x18002136c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180021372  mov     rax, rbx
0x180021375  add     rsp, 30h
0x180021379  pop     rbx
0x18002137a  retn
```
