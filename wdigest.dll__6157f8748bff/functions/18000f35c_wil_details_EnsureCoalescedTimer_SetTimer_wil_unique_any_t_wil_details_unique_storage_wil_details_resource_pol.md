# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x18000f35c`
- end: `0x18000f399`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000f294`
- `0x180010920`
- `0x180010e40`

## callees

- `0x18000f35c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f38e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f38e`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(struct _TP_TIMER **a1, _BYTE *a2, __int64 a3)
{
  struct _TP_TIMER *v3; // rcx
  _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    pftDueTime = (_FILETIME)(-10000 * a3);
    SetThreadpoolTimer(v3, &pftDueTime, 0, (unsigned int)a3 >> 2);
    *a2 = 1;
  }
}

```

## disassembly

```asm
0x18000f35c  push    rbx
0x18000f35e  sub     rsp, 20h
0x18000f362  mov     rcx, [rcx]; pti
0x18000f365  mov     rbx, rdx
0x18000f368  test    rcx, rcx
0x18000f36b  jnz     short loc_18000F373
0x18000f36d  add     rsp, 20h
0x18000f371  pop     rbx
0x18000f372  retn
0x18000f373  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x18000f37a  shr     r8d, 2
0x18000f37e  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000f383  mov     r9d, r8d; msWindowLength
0x18000f386  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000f38b  xor     r8d, r8d; msPeriod
0x18000f38e  call    cs:__imp_SetThreadpoolTimer
0x18000f394  mov     byte ptr [rbx], 1
0x18000f397  jmp     short loc_18000F36D
```
