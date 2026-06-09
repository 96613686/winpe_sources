# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x18000d4f4`
- end: `0x18000d52f`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000f994`
- `0x18000fa8c`
- `0x18000fefc`

## callees

- `0x18000d4f4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d520`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d520`

## pseudocode

```c
void __fastcall wil::details::EnsureCoalescedTimer_SetTimer(struct _TP_TIMER **a1, _BYTE *a2, __int64 a3)
{
  struct _TP_TIMER *v3; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    pftDueTime = (struct _FILETIME)(-10000 * a3);
    SetThreadpoolTimer(v3, &pftDueTime, 0, (unsigned int)a3 >> 2);
    *a2 = 1;
  }
}

```

## disassembly

```asm
0x18000d4f4  push    rbx
0x18000d4f6  sub     rsp, 20h
0x18000d4fa  mov     rcx, [rcx]; pti
0x18000d4fd  mov     rbx, rdx
0x18000d500  test    rcx, rcx
0x18000d503  jz      short loc_18000D529
0x18000d505  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x18000d50c  shr     r8d, 2
0x18000d510  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000d515  mov     r9d, r8d; msWindowLength
0x18000d518  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18000d51d  xor     r8d, r8d; msPeriod
0x18000d520  call    cs:__imp_SetThreadpoolTimer
0x18000d526  mov     byte ptr [rbx], 1
0x18000d529  add     rsp, 20h
0x18000d52d  pop     rbx
0x18000d52e  retn
```
