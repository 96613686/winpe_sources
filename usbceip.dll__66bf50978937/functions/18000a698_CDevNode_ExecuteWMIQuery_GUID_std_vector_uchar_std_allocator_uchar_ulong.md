# CDevNode::ExecuteWMIQuery(_GUID *,std::vector<uchar,std::allocator<uchar>> &,ulong)

- ea: `0x18000a698`
- end: `0x18000a830`
- name: `?ExecuteWMIQuery@CDevNode@@QEAAEPEAU_GUID@@AEAV?$vector@EV?$allocator@E@std@@@std@@K@Z`
- size: `408`
- prototype: `char __fastcall(CDevNode *this, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800089bc`
- `0x1800097ec`

## callees

- `0x180002e6e`
- `0x180003fec`
- `0x180004060`
- `0x1800040cc`
- `0x180008020`
- `0x1800080c8`
- `0x180009fe0`
- `0x18000a698`
- `0x18000b140`

## import_xrefs

- `WMICLNT!WmiQuerySingleInstanceW` at `0x18000a72e`
- `WMICLNT!WmiQuerySingleInstanceW` at `0x18000a7b1`
- `WMICLNT!WmiQuerySingleInstanceW` at `0x18000a72e`
- `WMICLNT!WmiQuerySingleInstanceW` at `0x18000a7b1`
- `WMICLNT!WmiOpenBlock` at `0x18000a6e5`
- `WMICLNT!WmiOpenBlock` at `0x18000a6e5`
- `WMICLNT!WmiCloseBlock` at `0x18000a7e7`
- `WMICLNT!WmiCloseBlock` at `0x18000a7e7`

## pseudocode

```c
char __fastcall CDevNode::ExecuteWMIQuery(CDevNode *this, __int64 a2, __int64 a3, int a4)
{
  __int64 v7; // r10
  unsigned int v8; // eax
  char v9; // r15
  __int64 v10; // rdi
  __int64 *v11; // rbx
  __int64 v12; // rdx
  char *v13; // r14
  char *v14; // rax
  size_t v15; // rsi
  _DWORD *v16; // rsi
  __int64 v17; // rdx
  unsigned int v18; // ecx
  unsigned int v20; // [rsp+20h] [rbp-48h] BYREF
  __int64 v21; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v22[2]; // [rsp+30h] [rbp-38h] BYREF
  void *v23[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v24; // [rsp+50h] [rbp-18h]

  v21 = 0;
  v22[0] = 0;
  std::vector<_bstr_t>::vector<_bstr_t>(v23);
  v20 = 0;
  v8 = WmiOpenBlock(v7, 1, &v21);
  if ( v8 )
    CException::ThrowException(v8, 0, 0);
  v9 = 0;
  v10 = v21;
  v22[1] = v21;
  CDevNode::GetWmiInstanceName(this, (struct _bstr_t *)v22);
  v11 = (__int64 *)v22[0];
  if ( v22[0] )
    v12 = *(_QWORD *)v22[0];
  else
    v12 = 0;
  if ( (unsigned int)WmiQuerySingleInstanceW(v21, v12, &v20, 0) == 122 && v20 )
  {
    v13 = (char *)v23[1];
    if ( (void *)v20 >= (void *)((char *)v23[1] - (char *)v23[0]) )
    {
      if ( (void *)v20 <= (void *)((char *)v23[1] - (char *)v23[0]) )
        goto LABEL_15;
      if ( v20 > v24 - (unsigned __int64)v23[0] )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v23, v20);
        goto LABEL_15;
      }
      v15 = v20 - (unsigned __int64)((char *)v23[1] - (char *)v23[0]);
      memset_0(v23[1], 0, v15);
      v14 = &v13[v15];
    }
    else
    {
      v14 = (char *)v23[0] + v20;
    }
    v23[1] = v14;
LABEL_15:
    v16 = v23[0];
    if ( v11 )
      v17 = *v11;
    else
      v17 = 0;
    if ( !(unsigned int)WmiQuerySingleInstanceW(v21, v17, &v20, v23[0]) && v20 >= 0x40 )
    {
      v18 = v16[14];
      if ( v18 + a4 <= *v16 )
      {
        std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(
          a3,
          (char *)v23[0] + v18,
          (char *)v23[1] - ((char *)v23[0] + v18));
        v9 = 1;
      }
    }
  }
  WmiCloseBlock(v10);
  if ( v23[0] )
  {
    std::_Deallocate<16>(v23[0], v24 - (unsigned __int64)v23[0]);
    *(_OWORD *)v23 = 0;
    v24 = 0;
  }
  _bstr_t::_Free((_bstr_t *)v22);
  return v9;
}

```

## disassembly

```asm
0x18000a698  push    rbp
0x18000a69a  push    rbx
0x18000a69b  push    rsi
0x18000a69c  push    rdi
0x18000a69d  push    r12
0x18000a69f  push    r13
0x18000a6a1  push    r14
0x18000a6a3  push    r15
0x18000a6a5  mov     rbp, rsp
0x18000a6a8  sub     rsp, 68h
0x18000a6ac  mov     r12d, r9d
0x18000a6af  mov     r13, r8
0x18000a6b2  mov     r10, rdx
0x18000a6b5  mov     rbx, rcx
0x18000a6b8  mov     [rbp+var_40], 0
0x18000a6c0  mov     [rbp+var_38], 0
0x18000a6c8  lea     rcx, [rbp+var_28]
0x18000a6cc  call    ??0?$vector@V_bstr_t@@V?$allocator@V_bstr_t@@@std@@@std@@QEAA@XZ; std::vector<_bstr_t>::vector<_bstr_t>(void)
0x18000a6d1  nop
0x18000a6d2  mov     [rbp+var_48], 0
0x18000a6d9  lea     r8, [rbp+var_40]
0x18000a6dd  mov     edx, 1
0x18000a6e2  mov     rcx, r10
0x18000a6e5  call    cs:__imp_WmiOpenBlock
0x18000a6eb  test    eax, eax
0x18000a6ed  jz      short loc_18000A6FC
0x18000a6ef  xor     r8d, r8d
0x18000a6f2  xor     edx, edx
0x18000a6f4  mov     ecx, eax
0x18000a6f6  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000a6fc  xor     r15b, r15b
0x18000a6ff  mov     rdi, [rbp+var_40]
0x18000a703  mov     [rbp+var_30], rdi
0x18000a707  lea     rdx, [rbp+var_38]; struct _bstr_t *
0x18000a70b  mov     rcx, rbx; this
0x18000a70e  call    ?GetWmiInstanceName@CDevNode@@QEAAXAEAV_bstr_t@@@Z; CDevNode::GetWmiInstanceName(_bstr_t &)
0x18000a713  mov     rbx, [rbp+var_38]
0x18000a717  test    rbx, rbx
0x18000a71a  jz      short loc_18000A721
0x18000a71c  mov     rdx, [rbx]
0x18000a71f  jmp     short loc_18000A723
0x18000a721  xor     edx, edx
0x18000a723  xor     r9d, r9d
0x18000a726  lea     r8, [rbp+var_48]
0x18000a72a  mov     rcx, [rbp+var_40]
0x18000a72e  call    cs:__imp_WmiQuerySingleInstanceW
0x18000a734  cmp     eax, 7Ah ; 'z'
0x18000a737  jnz     loc_18000A7E4
0x18000a73d  mov     eax, [rbp+var_48]
0x18000a740  test    eax, eax
0x18000a742  jz      loc_18000A7E4
0x18000a748  mov     esi, eax
0x18000a74a  mov     rdx, [rbp+var_28]
0x18000a74e  mov     r14, [rbp+var_28+8]
0x18000a752  mov     rcx, r14
0x18000a755  sub     rcx, rdx
0x18000a758  cmp     rax, rcx
0x18000a75b  jnb     short loc_18000A762
0x18000a75d  add     rax, rdx
0x18000a760  jmp     short loc_18000A792
0x18000a762  jbe     short loc_18000A796
0x18000a764  mov     rax, [rbp+var_18]
0x18000a768  sub     rax, rdx
0x18000a76b  cmp     rsi, rax
0x18000a76e  jbe     short loc_18000A77E
0x18000a770  mov     rdx, rsi
0x18000a773  lea     rcx, [rbp+var_28]
0x18000a777  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000a77c  jmp     short loc_18000A796
0x18000a77e  sub     rsi, rcx
0x18000a781  mov     r8, rsi; Size
0x18000a784  xor     edx, edx; Val
0x18000a786  mov     rcx, r14; void *
0x18000a789  call    memset_0
0x18000a78e  lea     rax, [rsi+r14]
0x18000a792  mov     [rbp+var_28+8], rax
0x18000a796  mov     rsi, [rbp+var_28]
0x18000a79a  test    rbx, rbx
0x18000a79d  jz      short loc_18000A7A4
0x18000a79f  mov     rdx, [rbx]
0x18000a7a2  jmp     short loc_18000A7A6
0x18000a7a4  xor     edx, edx
0x18000a7a6  mov     r9, rsi
0x18000a7a9  lea     r8, [rbp+var_48]
0x18000a7ad  mov     rcx, [rbp+var_40]
0x18000a7b1  call    cs:__imp_WmiQuerySingleInstanceW
0x18000a7b7  test    eax, eax
0x18000a7b9  jnz     short loc_18000A7E4
0x18000a7bb  cmp     [rbp+var_48], 40h ; '@'
0x18000a7bf  jb      short loc_18000A7E4
0x18000a7c1  mov     ecx, [rsi+38h]
0x18000a7c4  lea     eax, [rcx+r12]
0x18000a7c8  cmp     eax, [rsi]
0x18000a7ca  ja      short loc_18000A7E4
0x18000a7cc  mov     edx, ecx
0x18000a7ce  add     rdx, [rbp+var_28]
0x18000a7d2  mov     r8, [rbp+var_28+8]
0x18000a7d6  sub     r8, rdx
0x18000a7d9  mov     rcx, r13
0x18000a7dc  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x18000a7e1  mov     r15b, 1
0x18000a7e4  mov     rcx, rdi
0x18000a7e7  call    cs:__imp_WmiCloseBlock
0x18000a7ed  nop
0x18000a7ee  mov     rcx, [rbp+var_28]
0x18000a7f2  test    rcx, rcx
0x18000a7f5  jz      short loc_18000A813
0x18000a7f7  mov     rdx, [rbp+var_18]
0x18000a7fb  sub     rdx, rcx
0x18000a7fe  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a803  xorps   xmm0, xmm0
0x18000a806  movdqu  xmmword ptr [rbp+var_28], xmm0
0x18000a80b  mov     [rbp+var_18], 0
0x18000a813  lea     rcx, [rbp+var_38]; this
0x18000a817  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000a81c  mov     al, r15b
0x18000a81f  add     rsp, 68h
0x18000a823  pop     r15
0x18000a825  pop     r14
0x18000a827  pop     r13
0x18000a829  pop     r12
0x18000a82b  pop     rdi
0x18000a82c  pop     rsi
0x18000a82d  pop     rbx
0x18000a82e  pop     rbp
0x18000a82f  retn
```
