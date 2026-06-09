# wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Management::Deployment::IPackageManager2>(void)

- ea: `0x180013d80`
- end: `0x180013dcf`
- name: `??$query@UIPackageManager2@Deployment@Management@Windows@@@?$com_ptr_t@UIInspectable@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIPackageManager2@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@1@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012b74`

## callees

- `0x180013d80`
- `0x18001a610`
- `0x180029010`

## string_xrefs

- `0x180013db1`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
_QWORD *__fastcall wil::com_ptr_t<IInspectable,wil::err_exception_policy>::query<Windows::Management::Deployment::IPackageManager2>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, _QWORD *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, _QWORD *); // rcx
  int v4; // eax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *a1;
  *a2 = 0;
  v4 = (**v2)(v2, &GUID_f7aad08d_0840_46f2_b5d8_cad47693a095, a2);
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
0x180013d80  push    rbx
0x180013d82  sub     rsp, 30h
0x180013d86  mov     rcx, [rcx]
0x180013d89  mov     rbx, rdx
0x180013d8c  mov     qword ptr [rdx], 0
0x180013d93  mov     r8, rdx
0x180013d96  lea     rdx, _GUID_f7aad08d_0840_46f2_b5d8_cad47693a095
0x180013d9d  mov     rax, [rcx]
0x180013da0  mov     rax, [rax]
0x180013da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013da8  test    eax, eax
0x180013daa  jns     short loc_180013DC6
0x180013dac  mov     rcx, [rsp+38h]; this
0x180013db1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013db8  mov     r9d, eax; char *
0x180013dbb  mov     edx, 1CBEh; void *
0x180013dc0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180013dc6  mov     rax, rbx
0x180013dc9  add     rsp, 30h
0x180013dcd  pop     rbx
0x180013dce  retn
```
