# wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)

- ea: `0x180019388`
- end: `0x1800193c3`
- name: `?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180023f64`
- `0x180024134`

## callees

- `0x180019388`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800193b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800193b4`

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
0x180019388  push    rbx
0x18001938a  sub     rsp, 20h
0x18001938e  mov     rcx, [rcx]; pti
0x180019391  mov     rbx, rdx
0x180019394  test    rcx, rcx
0x180019397  jz      short loc_1800193BD
0x180019399  imul    rax, r8, 0FFFFFFFFFFFFD8F0h
0x1800193a0  shr     r8d, 2
0x1800193a4  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800193a9  mov     r9d, r8d; msWindowLength
0x1800193ac  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x1800193b1  xor     r8d, r8d; msPeriod
0x1800193b4  call    cs:__imp_SetThreadpoolTimer
0x1800193ba  mov     byte ptr [rbx], 1
0x1800193bd  add     rsp, 20h
0x1800193c1  pop     rbx
0x1800193c2  retn
```
