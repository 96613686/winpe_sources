# utl::_Med3Imp_utl::_ArrayIt_utl::unique_ptr_wchar_t_[0]_utl::default_delete_wchar_t_[0]_______EventService::GetPublisherList_::_2_::_lambda_2___

- ea: `0x180089660`
- end: `0x1800896f5`
- name: `utl::_Med3Imp_utl::_ArrayIt_utl::unique_ptr_wchar_t_[0]_utl::default_delete_wchar_t_[0]_______EventService::GetPublisherList_::_2_::_lambda_2___`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800895b4`

## callees

- `0x18006fc38`
- `0x180071b10`
- `0x180089660`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008968d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800896b8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008968d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800896b8`

## pseudocode

```c
int __fastcall utl::_Med3Imp_utl::_ArrayIt_utl::unique_ptr_wchar_t__0__utl::default_delete_wchar_t__0________EventService::GetPublisherList_::_2_::_lambda_2___(
        LPCWCH *a1,
        LPCWCH *a2,
        LPCWCH *a3)
{
  int result; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx

  if ( CompareStringOrdinal(*a2, -1, *a1, -1, 1) == 1 )
    utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(a2, a1);
  result = CompareStringOrdinal(*a3, -1, *a2, -1, 1);
  if ( result == 1 )
  {
    utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(a3, a2);
    result = EventService::GetPublisherList_::_2_::_lambda_2_::operator()(v8, v7, a1);
    if ( (_BYTE)result )
      return utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(a2, a1);
  }
  return result;
}

```

## disassembly

```asm
0x180089660  mov     [rsp+arg_0], rbx
0x180089665  mov     [rsp+arg_8], rsi
0x18008966a  push    rdi
0x18008966b  sub     rsp, 30h
0x18008966f  mov     rbx, rdx
0x180089672  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18008967a  mov     rsi, r8
0x18008967d  or      r9d, 0FFFFFFFFh; cchCount2
0x180089681  mov     r8, [rcx]; lpString2
0x180089684  mov     rdi, rcx
0x180089687  or      edx, r9d; cchCount1
0x18008968a  mov     rcx, [rbx]; lpString1
0x18008968d  call    cs:__imp_CompareStringOrdinal
0x180089693  cmp     eax, 1
0x180089696  jnz     short loc_1800896A3
0x180089698  mov     rdx, rdi
0x18008969b  mov     rcx, rbx
0x18008969e  call    ??$swap@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@$0A@@utl@@YAXAEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@0@Z; utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &)
0x1800896a3  mov     r8, [rbx]; lpString2
0x1800896a6  or      r9d, 0FFFFFFFFh; cchCount2
0x1800896aa  mov     rcx, [rsi]; lpString1
0x1800896ad  or      edx, r9d; cchCount1
0x1800896b0  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800896b8  call    cs:__imp_CompareStringOrdinal
0x1800896be  cmp     eax, 1
0x1800896c1  jnz     short loc_1800896E5
0x1800896c3  mov     rdx, rbx
0x1800896c6  mov     rcx, rsi
0x1800896c9  call    ??$swap@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@$0A@@utl@@YAXAEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@0@Z; utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &)
0x1800896ce  mov     r8, rdi
0x1800896d1  call    _EventService__GetPublisherList____2____lambda_2___operator__
0x1800896d6  test    al, al
0x1800896d8  jz      short loc_1800896E5
0x1800896da  mov     rdx, rdi
0x1800896dd  mov     rcx, rbx
0x1800896e0  call    ??$swap@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@$0A@@utl@@YAXAEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@0@Z; utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &)
0x1800896e5  mov     rbx, [rsp+38h+arg_0]
0x1800896ea  mov     rsi, [rsp+38h+arg_8]
0x1800896ef  add     rsp, 30h
0x1800896f3  pop     rdi
0x1800896f4  retn
```
