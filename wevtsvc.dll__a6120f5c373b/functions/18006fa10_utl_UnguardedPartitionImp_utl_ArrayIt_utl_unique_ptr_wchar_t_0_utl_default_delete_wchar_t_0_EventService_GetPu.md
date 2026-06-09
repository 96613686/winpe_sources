# utl::_UnguardedPartitionImp_utl::_ArrayIt_utl::unique_ptr_wchar_t_[0]_utl::default_delete_wchar_t_[0]_______EventService::GetPublisherList_::_2_::_lambda_2___

- ea: `0x18006fa10`
- end: `0x18006fc31`
- name: `utl::_UnguardedPartitionImp_utl::_ArrayIt_utl::unique_ptr_wchar_t_[0]_utl::default_delete_wchar_t_[0]_______EventService::GetPublisherList_::_2_::_lambda_2___`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180088e9c`

## callees

- `0x18006fa10`
- `0x18006fc38`
- `0x180071b10`
- `0x1800895b4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006fa87`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006faaa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006fad8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006fafc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006fa87`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006faaa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006fad8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006fafc`

## pseudocode

```c
LPCWCH **__fastcall utl::_UnguardedPartitionImp_utl::_ArrayIt_utl::unique_ptr_wchar_t__0__utl::default_delete_wchar_t__0________EventService::GetPublisherList_::_2_::_lambda_2___(
        LPCWCH **a1,
        unsigned __int64 a2,
        LPCWCH *a3)
{
  LPCWCH *v6; // rbx
  __int64 v7; // rcx
  LPCWCH *v8; // rdi
  LPCWCH *v9; // rsi
  LPCWCH *v10; // rbp
  LPCWCH *v11; // r12
  bool v12; // zf
  LPCWCH *v13; // r9
  LPCWCH *v14; // rcx
  LPCWCH **result; // rax
  __int64 v16; // rcx

  v6 = (LPCWCH *)(a2 + 8 * (((__int64)((__int64)a3 - a2) >> 3) / 2));
  utl::_MedianImp_utl::_ArrayIt_utl::unique_ptr_wchar_t__0__utl::default_delete_wchar_t__0________EventService::GetPublisherList_::_2_::_lambda_2___(
    a2,
    v6,
    a3 - 1);
  v8 = v6 + 1;
  while ( a2 < (unsigned __int64)v6
       && !(unsigned __int8)EventService::GetPublisherList_::_2_::_lambda_2_::operator()(v7, v6 - 1, v6)
       && !(unsigned __int8)EventService::GetPublisherList_::_2_::_lambda_2_::operator()(v7, v6, v6 - 1) )
    --v6;
  while ( v8 < a3
       && !(unsigned __int8)EventService::GetPublisherList_::_2_::_lambda_2_::operator()(v7, v8, v6)
       && !(unsigned __int8)EventService::GetPublisherList_::_2_::_lambda_2_::operator()(v16, v6, v8) )
    ++v8;
  v9 = v8;
  v10 = v6;
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v9 >= a3 )
        goto LABEL_8;
      if ( CompareStringOrdinal(*v6, -1, *v9, -1, 1) != 1 )
        break;
LABEL_21:
      ++v9;
    }
    if ( CompareStringOrdinal(*v9, -1, *v6, -1, 1) != 1 )
    {
      v14 = v8++;
      utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(v14, v9);
      goto LABEL_21;
    }
LABEL_8:
    while ( 1 )
    {
      v11 = v10 - 1;
      v12 = v10 == (LPCWCH *)a2;
      if ( (unsigned __int64)v10 <= a2 )
        break;
      if ( CompareStringOrdinal(*v11, -1, *v6, -1, 1) != 1 )
      {
        if ( CompareStringOrdinal(*v6, -1, *v11, -1, 1) == 1 )
        {
          v12 = v10 == (LPCWCH *)a2;
          break;
        }
        utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(--v6, v10 - 1);
      }
      --v10;
    }
    if ( v12 && v9 == a3 )
      break;
    if ( v10 == (LPCWCH *)a2 )
    {
      if ( v8 != v9 )
        utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(v6, v8);
      v11 = v9;
      ++v8;
      ++v9;
      v13 = v6++;
    }
    else
    {
      --v10;
      if ( v9 == a3 )
      {
        v13 = --v6;
        if ( v11 != v6 )
          utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(v11, v6);
        v11 = --v8;
      }
      else
      {
        v13 = v9++;
      }
    }
    utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(v13, v11);
  }
  *a1 = v6;
  result = a1;
  a1[1] = v8;
  return result;
}

```

## disassembly

```asm
0x18006fa10  push    rbx
0x18006fa12  push    rbp
0x18006fa13  push    rsi
0x18006fa14  push    rdi
0x18006fa15  push    r12
0x18006fa17  push    r13
0x18006fa19  push    r14
0x18006fa1b  push    r15
0x18006fa1d  sub     rsp, 38h
0x18006fa21  mov     r14, rdx
0x18006fa24  mov     rax, r8
0x18006fa27  sub     rax, rdx
0x18006fa2a  mov     r13, rcx
0x18006fa2d  sar     rax, 3
0x18006fa31  mov     ecx, 2
0x18006fa36  cqo
0x18006fa38  mov     r15, r8
0x18006fa3b  idiv    rcx
0x18006fa3e  add     r8, 0FFFFFFFFFFFFFFF8h
0x18006fa42  mov     rcx, r14
0x18006fa45  lea     rbx, [r14+rax*8]
0x18006fa49  mov     rdx, rbx
0x18006fa4c  call    utl___MedianImp_utl___ArrayIt_utl__unique_ptr_wchar_t__0__utl__default_delete_wchar_t__0________EventService__GetPublisherList____2____lambda_2___
0x18006fa51  lea     rdi, [rbx+8]
0x18006fa55  cmp     r14, rbx
0x18006fa58  jb      loc_18006FBC0
0x18006fa5e  cmp     rdi, r15
0x18006fa61  jb      loc_18006FBF2
0x18006fa67  mov     rsi, rdi
0x18006fa6a  mov     rbp, rbx
0x18006fa6d  cmp     rsi, r15
0x18006fa70  jnb     short loc_18006FAB9
0x18006fa72  mov     r8, [rsi]; lpString2
0x18006fa75  or      r9d, 0FFFFFFFFh; cchCount2
0x18006fa79  mov     rcx, [rbx]; lpString1
0x18006fa7c  or      edx, r9d; cchCount1
0x18006fa7f  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18006fa87  call    cs:__imp_CompareStringOrdinal
0x18006fa8d  cmp     eax, 1
0x18006fa90  jz      loc_18006FB63
0x18006fa96  mov     r8, [rbx]; lpString2
0x18006fa99  or      edx, 0FFFFFFFFh; cchCount1
0x18006fa9c  mov     rcx, [rsi]; lpString1
0x18006fa9f  mov     r9d, edx; cchCount2
0x18006faa2  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18006faaa  call    cs:__imp_CompareStringOrdinal
0x18006fab0  cmp     eax, 1
0x18006fab3  jnz     loc_18006FB54
0x18006fab9  lea     r12, [rbp-8]
0x18006fabd  cmp     rbp, r14
0x18006fac0  jbe     short loc_18006FB0A
0x18006fac2  mov     r8, [rbx]; lpString2
0x18006fac5  or      r9d, 0FFFFFFFFh; cchCount2
0x18006fac9  mov     rcx, [r12]; lpString1
0x18006facd  or      edx, r9d; cchCount1
0x18006fad0  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18006fad8  call    cs:__imp_CompareStringOrdinal
0x18006fade  cmp     eax, 1
0x18006fae1  jz      loc_18006FB7B
0x18006fae7  mov     r8, [r12]; lpString2
0x18006faeb  or      edx, 0FFFFFFFFh; cchCount1
0x18006faee  mov     rcx, [rbx]; lpString1
0x18006faf1  mov     r9d, edx; cchCount2
0x18006faf4  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18006fafc  call    cs:__imp_CompareStringOrdinal
0x18006fb02  cmp     eax, 1
0x18006fb05  jnz     short loc_18006FB6C
0x18006fb07  cmp     rbp, r14
0x18006fb0a  jz      short loc_18006FB83
0x18006fb0c  cmp     rbp, r14
0x18006fb0f  jz      loc_18006FBA4
0x18006fb15  mov     rbp, r12
0x18006fb18  cmp     rsi, r15
0x18006fb1b  jz      short loc_18006FB34
0x18006fb1d  mov     r9, rsi
0x18006fb20  add     rsi, 8
0x18006fb24  mov     rdx, r12
0x18006fb27  mov     rcx, r9
0x18006fb2a  call    ??$swap@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@$0A@@utl@@YAXAEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@0@Z; utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &)
0x18006fb2f  jmp     loc_18006FA6D
0x18006fb34  sub     rbx, 8
0x18006fb38  mov     r9, rbx
0x18006fb3b  cmp     r12, rbx
0x18006fb3e  jz      short loc_18006FB4B
0x18006fb40  mov     rdx, rbx
0x18006fb43  mov     rcx, r12
0x18006fb46  call    ??$swap@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@$0A@@utl@@YAXAEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@0@Z; utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &)
0x18006fb4b  sub     rdi, 8
0x18006fb4f  mov     r12, rdi
0x18006fb52  jmp     short loc_18006FB24
0x18006fb54  mov     rcx, rdi
0x18006fb57  mov     rdx, rsi
0x18006fb5a  add     rdi, 8
0x18006fb5e  call    ??$swap@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@$0A@@utl@@YAXAEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@0@Z; utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &)
0x18006fb63  add     rsi, 8
0x18006fb67  jmp     loc_18006FA6D
0x18006fb6c  sub     rbx, 8
0x18006fb70  mov     rdx, r12
0x18006fb73  mov     rcx, rbx
0x18006fb76  call    ??$swap@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@$0A@@utl@@YAXAEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@0@Z; utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &)
0x18006fb7b  mov     rbp, r12
0x18006fb7e  jmp     loc_18006FAB9
0x18006fb83  cmp     rsi, r15
0x18006fb86  jnz     short loc_18006FB0C
0x18006fb88  mov     [r13+0], rbx
0x18006fb8c  mov     rax, r13
0x18006fb8f  mov     [r13+8], rdi
0x18006fb93  add     rsp, 38h
0x18006fb97  pop     r15
0x18006fb99  pop     r14
0x18006fb9b  pop     r13
0x18006fb9d  pop     r12
0x18006fb9f  pop     rdi
0x18006fba0  pop     rsi
0x18006fba1  pop     rbp
0x18006fba2  pop     rbx
0x18006fba3  retn
0x18006fba4  cmp     rdi, rsi
0x18006fba7  jnz     short loc_18006FC21
0x18006fba9  mov     r12, rsi
0x18006fbac  add     rdi, 8
0x18006fbb0  add     rsi, 8
0x18006fbb4  mov     r9, rbx
0x18006fbb7  add     rbx, 8
0x18006fbbb  jmp     loc_18006FB24
0x18006fbc0  lea     rsi, [rbx-8]
0x18006fbc4  mov     r8, rbx
0x18006fbc7  mov     rdx, rsi
0x18006fbca  call    _EventService__GetPublisherList____2____lambda_2___operator__
0x18006fbcf  test    al, al
0x18006fbd1  jnz     loc_18006FA5E
0x18006fbd7  mov     r8, rsi
0x18006fbda  mov     rdx, rbx
0x18006fbdd  call    _EventService__GetPublisherList____2____lambda_2___operator__
0x18006fbe2  test    al, al
0x18006fbe4  jnz     loc_18006FA5E
0x18006fbea  mov     rbx, rsi
0x18006fbed  jmp     loc_18006FA55
0x18006fbf2  mov     r8, rbx
0x18006fbf5  mov     rdx, rdi
0x18006fbf8  call    _EventService__GetPublisherList____2____lambda_2___operator__
0x18006fbfd  test    al, al
0x18006fbff  jnz     loc_18006FA67
0x18006fc05  mov     r8, rdi
0x18006fc08  mov     rdx, rbx
0x18006fc0b  call    _EventService__GetPublisherList____2____lambda_2___operator__
0x18006fc10  test    al, al
0x18006fc12  jnz     loc_18006FA67
0x18006fc18  add     rdi, 8
0x18006fc1c  jmp     loc_18006FA5E
0x18006fc21  mov     rdx, rdi
0x18006fc24  mov     rcx, rbx
0x18006fc27  call    ??$swap@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@$0A@@utl@@YAXAEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@0@Z; utl::swap<wchar_t [0],utl::default_delete<wchar_t [0]>,0>(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> &)
0x18006fc2c  jmp     loc_18006FBA9
```
