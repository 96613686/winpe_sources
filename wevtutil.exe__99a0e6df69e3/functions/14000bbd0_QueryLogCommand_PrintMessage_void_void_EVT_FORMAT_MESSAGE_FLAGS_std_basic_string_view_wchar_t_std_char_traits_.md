# QueryLogCommand::PrintMessage(void *,void *,_EVT_FORMAT_MESSAGE_FLAGS,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x14000bbd0`
- end: `0x14000be0e`
- name: `?PrintMessage@QueryLogCommand@@AEAAXPEAX0W4_EVT_FORMAT_MESSAGE_FLAGS@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14000be14`

## callees

- `0x14000bbd0`
- `0x14000cabc`
- `0x14000d144`
- `0x14000d868`
- `0x140021b00`
- `0x140027744`
- `0x140027780`
- `0x140027930`
- `0x1400293bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall QueryLogCommand::PrintMessage(__int64 a1, void *a2, void *a3, DWORD a4, __int64 a5)
{
  unsigned __int64 v9; // rdx
  _QWORD *v10; // rcx
  unsigned __int64 v11; // rdx
  _QWORD *v12; // rcx
  const wchar_t *v13; // rax
  _BYTE *v14; // rdx
  _BYTE *v15; // rdx
  _BYTE *v16; // rdx
  _BYTE *v17; // rdx
  bool v18; // zf
  int v20; // [rsp+20h] [rbp-51h]
  _BYTE v21[16]; // [rsp+40h] [rbp-31h] BYREF
  __int128 v22; // [rsp+50h] [rbp-21h] BYREF
  char v23[16]; // [rsp+60h] [rbp-11h] BYREF
  _QWORD Src[2]; // [rsp+70h] [rbp-1h] BYREF
  unsigned __int64 v25; // [rsp+80h] [rbp+Fh]
  unsigned __int64 v26; // [rsp+88h] [rbp+17h]

  std::wstring::wstring(Src, a5);
  v9 = v25;
  v10 = Src;
  if ( v25 >= v26 )
  {
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(Src);
  }
  else
  {
    ++v25;
    if ( v26 > 7 )
      v10 = (_QWORD *)Src[0];
    *(_DWORD *)((char *)v10 + 2 * v9) = 58;
  }
  v11 = v25;
  v12 = Src;
  if ( v25 >= v26 )
  {
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(Src);
  }
  else
  {
    ++v25;
    if ( v26 > 7 )
      v12 = (_QWORD *)Src[0];
    *(_DWORD *)((char *)v12 + 2 * v11) = 32;
  }
  v22 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v23);
  FilePuts(*(HANDLE *)(a1 + 16), &v22);
  if ( a4 == 1 )
  {
    *(_QWORD *)&v22 = L"\r\n";
    *((_QWORD *)&v22 + 1) = 2;
    FilePuts(*(HANDLE *)(a1 + 16), &v22);
  }
  if ( (unsigned int)RenderMessage(a2, a3, 0xFFFFFFFF, v20, a4, a1 + 200) )
  {
    v13 = L"N/A\r\n";
    *((_QWORD *)&v22 + 1) = 5;
  }
  else
  {
    v14 = *(_BYTE **)(a1 + 208);
    if ( (unsigned __int64)&v14[-*(_QWORD *)(a1 + 200)] >= 2 )
    {
      if ( *(v14 - 2) || *(v14 - 1) )
      {
        v21[0] = 13;
        if ( v14 == *(_BYTE **)(a1 + 216) )
        {
          std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(a1 + 200, v14, v21);
        }
        else
        {
          *v14 = 13;
          ++*(_QWORD *)(a1 + 208);
        }
        v21[0] = 0;
        v15 = *(_BYTE **)(a1 + 208);
        if ( v15 == *(_BYTE **)(a1 + 216) )
        {
          std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(a1 + 200, v15, v21);
        }
        else
        {
          *v15 = 0;
          ++*(_QWORD *)(a1 + 208);
        }
      }
      else
      {
        *(v14 - 2) = 13;
        *(_BYTE *)(*(_QWORD *)(a1 + 208) - 1LL) = 0;
      }
      v21[0] = 10;
      v16 = *(_BYTE **)(a1 + 208);
      if ( v16 == *(_BYTE **)(a1 + 216) )
      {
        std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(a1 + 200, v16, v21);
      }
      else
      {
        *v16 = 10;
        ++*(_QWORD *)(a1 + 208);
      }
      v17 = *(_BYTE **)(a1 + 208);
      v18 = v17 == *(_BYTE **)(a1 + 216);
      v21[0] = 0;
      if ( v18 )
      {
        std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(a1 + 200, v17, v21);
      }
      else
      {
        *v17 = 0;
        ++*(_QWORD *)(a1 + 208);
      }
      v13 = *(const wchar_t **)(a1 + 200);
      *((_QWORD *)&v22 + 1) = (*(_QWORD *)(a1 + 208) - (_QWORD)v13) >> 1;
    }
    else
    {
      v13 = L"\r\n";
      *((_QWORD *)&v22 + 1) = 2;
    }
  }
  *(_QWORD *)&v22 = v13;
  FilePuts(*(HANDLE *)(a1 + 16), &v22);
  return std::wstring::_Tidy_deallocate(Src);
}

```

## disassembly

```asm
0x14000bbd0  mov     [rsp-8+arg_18], rbx
0x14000bbd5  push    rbp
0x14000bbd6  push    rsi
0x14000bbd7  push    rdi
0x14000bbd8  push    r14
0x14000bbda  push    r15
0x14000bbdc  lea     rbp, [rsp-2Fh]
0x14000bbe1  sub     rsp, 0A0h
0x14000bbe8  mov     rax, cs:__security_cookie
0x14000bbef  xor     rax, rsp
0x14000bbf2  mov     [rbp+4Fh+var_30], rax
0x14000bbf6  mov     esi, r9d
0x14000bbf9  mov     r15, r8
0x14000bbfc  mov     r14, rdx
0x14000bbff  mov     rdi, rcx
0x14000bc02  mov     rdx, [rbp+4Fh+arg_20]
0x14000bc06  lea     rcx, [rbp+4Fh+Src]
0x14000bc0a  call    ??$?0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring_view const &,std::allocator<wchar_t> const &)
0x14000bc0f  nop
0x14000bc10  mov     rdx, [rbp+4Fh+var_40]
0x14000bc14  lea     rcx, [rbp+4Fh+Src]; Src
0x14000bc18  cmp     rdx, [rbp+4Fh+var_38]
0x14000bc1c  jnb     short loc_14000BC39
0x14000bc1e  lea     rax, [rdx+1]
0x14000bc22  mov     [rbp+4Fh+var_40], rax
0x14000bc26  cmp     [rbp+4Fh+var_38], 7
0x14000bc2b  cmova   rcx, [rbp+4Fh+Src]
0x14000bc30  mov     dword ptr [rcx+rdx*2], 3Ah ; ':'
0x14000bc37  jmp     short loc_14000BC44
0x14000bc39  mov     r9d, 3Ah ; ':'
0x14000bc3f  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x14000bc44  mov     rdx, [rbp+4Fh+var_40]
0x14000bc48  lea     rcx, [rbp+4Fh+Src]; Src
0x14000bc4c  cmp     rdx, [rbp+4Fh+var_38]
0x14000bc50  jnb     short loc_14000BC6D
0x14000bc52  lea     rax, [rdx+1]
0x14000bc56  mov     [rbp+4Fh+var_40], rax
0x14000bc5a  cmp     [rbp+4Fh+var_38], 7
0x14000bc5f  cmova   rcx, [rbp+4Fh+Src]
0x14000bc64  mov     dword ptr [rcx+rdx*2], 20h ; ' '
0x14000bc6b  jmp     short loc_14000BC78
0x14000bc6d  mov     r9d, 20h ; ' '
0x14000bc73  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x14000bc78  lea     rdx, [rbp+4Fh+var_60]
0x14000bc7c  lea     rcx, [rbp+4Fh+Src]
0x14000bc80  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000bc85  movups  xmm0, xmmword ptr [rax]
0x14000bc88  movdqu  [rbp+4Fh+var_70], xmm0
0x14000bc8d  lea     rdx, [rbp+4Fh+var_70]
0x14000bc91  mov     rcx, [rdi+10h]; hFile
0x14000bc95  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x14000bc9a  lea     rax, asc_140038FDC; "\r\n"
0x14000bca1  cmp     esi, 1
0x14000bca4  jnz     short loc_14000BCBF
0x14000bca6  mov     qword ptr [rbp+4Fh+var_70], rax
0x14000bcaa  mov     qword ptr [rbp+4Fh+var_70+8], 2
0x14000bcb2  lea     rdx, [rbp+4Fh+var_70]
0x14000bcb6  mov     rcx, [rdi+10h]; hFile
0x14000bcba  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x14000bcbf  lea     rbx, [rdi+0C8h]
0x14000bcc6  mov     [rsp+0C0h+var_90], rbx; __int64
0x14000bccb  mov     [rsp+0C0h+var_98], esi; DWORD
0x14000bccf  or      r8d, 0FFFFFFFFh; MessageId
0x14000bcd3  mov     rdx, r15; Event
0x14000bcd6  mov     rcx, r14; PublisherMetadata
0x14000bcd9  call    ?RenderMessage@@YAKPEAX0KKPEAU_EVT_VARIANT@@KAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; RenderMessage(void *,void *,ulong,ulong,_EVT_VARIANT *,ulong,std::vector<uchar> &)
0x14000bcde  test    eax, eax
0x14000bce0  jz      short loc_14000BCF6
0x14000bce2  lea     rax, aNA_0; "N/A\r\n"
0x14000bce9  mov     qword ptr [rbp+4Fh+var_70+8], 5
0x14000bcf1  jmp     loc_14000BDD0
0x14000bcf6  mov     rdx, [rbx+8]
0x14000bcfa  mov     rax, rdx
0x14000bcfd  sub     rax, [rbx]
0x14000bd00  cmp     rax, 2
0x14000bd04  jnb     short loc_14000BD1A
0x14000bd06  lea     rax, asc_140038FDC; "\r\n"
0x14000bd0d  mov     qword ptr [rbp+4Fh+var_70+8], 2
0x14000bd15  jmp     loc_14000BDD0
0x14000bd1a  cmp     byte ptr [rdx-2], 0
0x14000bd1e  jnz     short loc_14000BD37
0x14000bd20  cmp     byte ptr [rdx-1], 0
0x14000bd24  jnz     short loc_14000BD37
0x14000bd26  mov     byte ptr [rdx-2], 0Dh
0x14000bd2a  mov     rax, [rdi+0D0h]
0x14000bd31  mov     byte ptr [rax-1], 0
0x14000bd35  jmp     short loc_14000BD79
0x14000bd37  mov     [rbp+4Fh+var_80], 0Dh
0x14000bd3b  cmp     rdx, [rbx+10h]
0x14000bd3f  jz      short loc_14000BD4A
0x14000bd41  mov     byte ptr [rdx], 0Dh
0x14000bd44  inc     qword ptr [rbx+8]
0x14000bd48  jmp     short loc_14000BD56
0x14000bd4a  lea     r8, [rbp+4Fh+var_80]
0x14000bd4e  mov     rcx, rbx
0x14000bd51  call    ??$_Emplace_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAE$$QEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar>(uchar * const,uchar &&)
0x14000bd56  mov     [rbp+4Fh+var_80], 0
0x14000bd5a  mov     rdx, [rbx+8]
0x14000bd5e  cmp     rdx, [rbx+10h]
0x14000bd62  jz      short loc_14000BD6D
0x14000bd64  mov     byte ptr [rdx], 0
0x14000bd67  inc     qword ptr [rbx+8]
0x14000bd6b  jmp     short loc_14000BD79
0x14000bd6d  lea     r8, [rbp+4Fh+var_80]
0x14000bd71  mov     rcx, rbx
0x14000bd74  call    ??$_Emplace_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAE$$QEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar>(uchar * const,uchar &&)
0x14000bd79  mov     [rbp+4Fh+var_80], 0Ah
0x14000bd7d  mov     rdx, [rbx+8]
0x14000bd81  cmp     rdx, [rbx+10h]
0x14000bd85  jz      short loc_14000BD90
0x14000bd87  mov     byte ptr [rdx], 0Ah
0x14000bd8a  inc     qword ptr [rbx+8]
0x14000bd8e  jmp     short loc_14000BD9C
0x14000bd90  lea     r8, [rbp+4Fh+var_80]
0x14000bd94  mov     rcx, rbx
0x14000bd97  call    ??$_Emplace_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAE$$QEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar>(uchar * const,uchar &&)
0x14000bd9c  mov     rdx, [rbx+8]
0x14000bda0  cmp     rdx, [rbx+10h]
0x14000bda4  mov     [rbp+4Fh+var_80], 0
0x14000bda8  jz      short loc_14000BDB3
0x14000bdaa  mov     byte ptr [rdx], 0
0x14000bdad  inc     qword ptr [rbx+8]
0x14000bdb1  jmp     short loc_14000BDBF
0x14000bdb3  lea     r8, [rbp+4Fh+var_80]
0x14000bdb7  mov     rcx, rbx
0x14000bdba  call    ??$_Emplace_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAE$$QEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar>(uchar * const,uchar &&)
0x14000bdbf  mov     rax, [rbx]
0x14000bdc2  mov     rcx, [rbx+8]
0x14000bdc6  sub     rcx, rax
0x14000bdc9  shr     rcx, 1
0x14000bdcc  mov     qword ptr [rbp+4Fh+var_70+8], rcx
0x14000bdd0  mov     qword ptr [rbp+4Fh+var_70], rax
0x14000bdd4  lea     rdx, [rbp+4Fh+var_70]
0x14000bdd8  mov     rcx, [rdi+10h]; hFile
0x14000bddc  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x14000bde1  nop
0x14000bde2  lea     rcx, [rbp+4Fh+Src]
0x14000bde6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000bdeb  mov     rcx, [rbp+4Fh+var_30]
0x14000bdef  xor     rcx, rsp; StackCookie
0x14000bdf2  call    __security_check_cookie
0x14000bdf7  mov     rbx, [rsp+0C0h+arg_18]
0x14000bdff  add     rsp, 0A0h
0x14000be06  pop     r15
0x14000be08  pop     r14
0x14000be0a  pop     rdi
0x14000be0b  pop     rsi
0x14000be0c  pop     rbp
0x14000be0d  retn
```
