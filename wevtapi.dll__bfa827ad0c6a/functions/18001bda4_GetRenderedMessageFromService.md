# GetRenderedMessageFromService

- ea: `0x18001bda4`
- end: `0x18001c127`
- name: `GetRenderedMessageFromService`
- size: `899`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int128 *, int, __int64, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, service_task`

## callers

- `0x180007fb8`
- `0x18001b3d4`
- `0x18001bbcc`

## callees

- `0x18000a0dc`
- `0x18000a100`
- `0x18001ab64`
- `0x18001bda4`
- `0x18001c130`
- `0x18001c280`
- `0x18001c43c`
- `0x18001c470`
- `0x18001ca8c`
- `0x180023548`
- `0x180038fa4`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001bedf`
- `RPCRT4!NdrClientCall3` at `0x18001bedf`

## pseudocode

```c
_QWORD *__fastcall GetRenderedMessageFromService(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int128 *a4,
        int a5,
        __int64 a6,
        unsigned int a7,
        __int64 a8)
{
  int v12; // r15d
  __int64 v13; // rdx
  unsigned int Pointer; // ebx
  void *v16; // rax
  __int64 v17; // rax
  int v18; // edx
  unsigned int v19; // ebx
  void *v20; // rax
  unsigned int v21; // [rsp+70h] [rbp-39h] BYREF
  void *v22; // [rsp+78h] [rbp-31h] BYREF
  __int128 v23; // [rsp+80h] [rbp-29h] BYREF
  __int128 pExceptionObject; // [rsp+90h] [rbp-19h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-9h] BYREF
  int v26; // [rsp+A8h] [rbp-1h]
  __int64 v27; // [rsp+ACh] [rbp+3h]
  char v28; // [rsp+B4h] [rbp+Bh]
  int v29; // [rsp+F8h] [rbp+4Fh] BYREF

  v22 = 0;
  if ( !a2 )
  {
    if ( !a3 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, 87);
      }
      pExceptionObject = 0;
      v25 = 0;
      v26 = 87;
      v27 = 0x254FFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    v29 = 0;
    v21 = 0;
    ___replace___BY0A_EU__generic_delete___BY0A_EU__generic_deallocate__MP6AXPEAX_Z1_MIDL_user_free__YAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAEAEAV__unique_ptr___BY0A_EU__generic_delete___BY0A_EU__generic_deallocate__MP6AXPEAX_Z1_MIDL_user_free__YAX0_ZPEAX_tlx___tlx___0__Z(&v22);
    v19 = EvtRpcMessageRenderDefault(*(_QWORD *)(a3 + 72), v18, (_DWORD)a4, a5, a6, a7);
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, v19);
      }
      *(_QWORD *)&pExceptionObject = &word_18004024A;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v25 = 0;
      v26 = v19;
      v27 = -1;
      v28 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( v29 )
    {
      v20 = v22;
      v22 = 0;
      *(_QWORD *)&v23 = v20;
      RpcString<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::RpcString<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(
        a1,
        &v23,
        v21);
      goto LABEL_4;
    }
    goto LABEL_15;
  }
  v23 = *a4;
  v12 = a7;
  PublisherMetadataObject::GetCachedDescString(a2, &pExceptionObject, &v23, a7);
  v13 = *((_QWORD *)&pExceptionObject + 1);
  if ( *((_QWORD *)&pExceptionObject + 1) )
  {
    a1[2] = 0;
    *a1 = pExceptionObject;
    a1[1] = v13;
    pExceptionObject = 0u;
    __4__unique_ptr___BY0A_EU__generic_delete___BY0A_EU__generic_deallocate__MP6AXPEAX_Z1_MIDL_user_free__YAX0_ZPEAX_tlx___tlx___utl__QEAAAEAV01___QEAV01__Z(
      a1 + 2,
      &v25);
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&v25);
LABEL_4:
    utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&v22);
    return a1;
  }
  utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<unsigned long>>>(&v25);
  v29 = 0;
  v21 = 0;
  v22 = 0;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            9u,
                            0,
                            *(_QWORD *)(a2 + 48),
                            16,
                            a4,
                            a5,
                            a6,
                            v12,
                            0x200000,
                            &v29,
                            &v21,
                            &v22,
                            a8).Pointer;
  if ( Pointer )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids, Pointer);
    }
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v25 = 0;
    v26 = Pointer;
    v27 = -1;
    v28 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !v29 )
  {
LABEL_15:
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
    goto LABEL_4;
  }
  v16 = v22;
  v22 = 0;
  *(_QWORD *)&v23 = v16;
  v17 = RpcString<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>::RpcString<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>(
          &pExceptionObject,
          &v23,
          v21);
  v23 = *a4;
  PublisherMetadataObject::SetCachedDescString(a2, (_DWORD)a1, (unsigned int)&v23, v12, v17);
  if ( v22 )
    operator delete(v22);
  return a1;
}

```

## disassembly

```asm
0x18001bda4  mov     [rsp-8+arg_0], rbx
0x18001bda9  mov     [rsp-8+arg_10], rsi
0x18001bdae  push    rbp
0x18001bdaf  push    rdi
0x18001bdb0  push    r12
0x18001bdb2  push    r14
0x18001bdb4  push    r15
0x18001bdb6  lea     rbp, [rsp-17h]
0x18001bdbb  sub     rsp, 0C0h
0x18001bdc2  mov     r14, r9
0x18001bdc5  mov     rbx, r8
0x18001bdc8  mov     rsi, rdx
0x18001bdcb  mov     rdi, rcx
0x18001bdce  xor     r12d, r12d
0x18001bdd1  mov     [rbp+37h+var_68], r12
0x18001bdd5  test    rdx, rdx
0x18001bdd8  jz      loc_18001BFC4
0x18001bdde  movups  xmm0, xmmword ptr [r9]
0x18001bde2  movdqu  [rbp+37h+var_60], xmm0
0x18001bde7  mov     r15d, [rbp+37h+arg_30]
0x18001bdeb  mov     r9d, r15d
0x18001bdee  lea     r8, [rbp+37h+var_60]
0x18001bdf2  lea     rdx, [rbp+37h+pExceptionObject]
0x18001bdf6  mov     rcx, rsi
0x18001bdf9  call    ?GetCachedDescString@PublisherMetadataObject@@QEAA?AV?$RpcString@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@@U_EVENT_DESCRIPTOR@@W4_EVT_FORMAT_MESSAGE_FLAGS@@@Z; PublisherMetadataObject::GetCachedDescString(_EVENT_DESCRIPTOR,_EVT_FORMAT_MESSAGE_FLAGS)
0x18001bdfe  mov     rdx, qword ptr [rbp+37h+pExceptionObject+8]
0x18001be02  test    rdx, rdx
0x18001be05  jz      short loc_18001BE5C
0x18001be07  lea     rcx, [rdi+10h]
0x18001be0b  mov     [rcx], r12
0x18001be0e  mov     rax, qword ptr [rbp+37h+pExceptionObject]
0x18001be12  mov     [rdi], rax
0x18001be15  mov     [rdi+8], rdx
0x18001be19  mov     qword ptr [rbp+37h+pExceptionObject], r12
0x18001be1d  mov     qword ptr [rbp+37h+pExceptionObject+8], r12
0x18001be21  lea     rdx, [rbp+37h+var_40]
0x18001be25  call    ??4?$unique_ptr@$$BY0A@EU?$generic_delete@$$BY0A@EU?$generic_deallocate@$MP6AXPEAX@Z1?MIDL_user_free@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z
0x18001be2a  lea     rcx, [rbp+37h+var_40]
0x18001be2e  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x18001be33  nop
0x18001be34  lea     rcx, [rbp+37h+var_68]
0x18001be38  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x18001be3d  mov     rax, rdi
0x18001be40  lea     r11, [rsp+0E0h+var_20]
0x18001be48  mov     rbx, [r11+30h]
0x18001be4c  mov     rsi, [r11+40h]
0x18001be50  mov     rsp, r11
0x18001be53  pop     r15
0x18001be55  pop     r14
0x18001be57  pop     r12
0x18001be59  pop     rdi
0x18001be5a  pop     rbp
0x18001be5b  retn
0x18001be5c  lea     rcx, [rbp+37h+var_40]
0x18001be60  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_TreeNode@K@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>::~_UninitializedAllocation<utl::allocator<utl::_TreeNode<ulong>>>(void)
0x18001be65  mov     [rbp+37h+arg_8], r12d
0x18001be69  mov     [rbp+37h+var_70], r12d
0x18001be6d  mov     rcx, [rbp+37h+var_68]; void *
0x18001be71  mov     [rbp+37h+var_68], r12
0x18001be75  test    rcx, rcx
0x18001be78  jz      short loc_18001BE7F
0x18001be7a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001be7f  mov     rax, [rbp+37h+arg_38]
0x18001be83  mov     [rsp+0E0h+var_78], rax
0x18001be88  lea     rax, [rbp+37h+var_68]
0x18001be8c  mov     [rsp+0E0h+var_80], rax
0x18001be91  lea     rax, [rbp+37h+var_70]
0x18001be95  mov     [rsp+0E0h+var_88], rax
0x18001be9a  lea     rax, [rbp+37h+arg_8]
0x18001be9e  mov     [rsp+0E0h+var_90], rax
0x18001bea3  mov     dword ptr [rsp+0E0h+var_98], 200000h
0x18001beab  mov     dword ptr [rsp+0E0h+var_A0], r15d
0x18001beb0  mov     rax, [rbp+37h+arg_28]
0x18001beb4  mov     [rsp+0E0h+var_A8], rax
0x18001beb9  mov     eax, [rbp+37h+arg_20]
0x18001bebc  mov     [rsp+0E0h+var_B0], eax
0x18001bec0  mov     [rsp+0E0h+var_B8], r14
0x18001bec5  mov     dword ptr [rsp+0E0h+var_C0], 10h
0x18001becd  mov     r9, [rsi+30h]
0x18001bed1  xor     r8d, r8d; pReturnValue
0x18001bed4  lea     edx, [r8+9]; nProcNum
0x18001bed8  lea     rcx, pProxyInfo; pProxyInfo
0x18001bedf  call    cs:__imp_NdrClientCall3
0x18001bee5  mov     rbx, rax
0x18001bee8  test    eax, eax
0x18001beea  jz      short loc_18001BF59
0x18001beec  lea     rax, WPP_GLOBAL_Control
0x18001bef3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001befa  cmp     rcx, rax
0x18001befd  jz      short loc_18001BF26
0x18001beff  test    dword ptr [rcx+1Ch], 40000h
0x18001bf06  jz      short loc_18001BF26
0x18001bf08  cmp     byte ptr [rcx+19h], 2
0x18001bf0c  jb      short loc_18001BF26
0x18001bf0e  mov     edx, 15h
0x18001bf13  mov     r9d, ebx
0x18001bf16  lea     r8, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids
0x18001bf1d  mov     rcx, [rcx+10h]
0x18001bf21  call    WPP_SF_D
0x18001bf26  lea     rax, word_18004024A
0x18001bf2d  mov     qword ptr [rbp+37h+pExceptionObject], rax
0x18001bf31  mov     qword ptr [rbp+37h+pExceptionObject+8], r12
0x18001bf35  mov     [rbp+37h+var_40], r12
0x18001bf39  mov     [rbp+37h+var_38], ebx
0x18001bf3c  mov     [rbp+37h+var_34], 0FFFFFFFFFFFFFFFFh
0x18001bf44  mov     [rbp+37h+var_2C], r12b
0x18001bf48  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001bf4f  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x18001bf53  call    _CxxThrowException_0
0x18001bf59  cmp     [rbp+37h+arg_8], r12d
0x18001bf5d  jz      short loc_18001BFB4
0x18001bf5f  mov     rax, [rbp+37h+var_68]
0x18001bf63  mov     [rbp+37h+var_68], r12
0x18001bf67  mov     qword ptr [rbp+37h+var_60], rax
0x18001bf6b  mov     r8d, [rbp+37h+var_70]
0x18001bf6f  lea     rdx, [rbp+37h+var_60]
0x18001bf73  lea     rcx, [rbp+37h+pExceptionObject]
0x18001bf77  call    ??0?$RpcString@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@@QEAA@V?$unique_ptr@$$BY0A@EU?$generic_delete@$$BY0A@EU?$generic_deallocate@$MP6AXPEAX@Z1?MIDL_user_free@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@_K@Z
0x18001bf7c  movups  xmm0, xmmword ptr [r14]
0x18001bf80  movdqu  [rbp+37h+var_60], xmm0
0x18001bf85  mov     [rsp+0E0h+var_C0], rax
0x18001bf8a  mov     r9d, r15d
0x18001bf8d  lea     r8, [rbp+37h+var_60]
0x18001bf91  mov     rdx, rdi
0x18001bf94  mov     rcx, rsi
0x18001bf97  call    ?SetCachedDescString@PublisherMetadataObject@@QEAA?AV?$RpcString@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@@U_EVENT_DESCRIPTOR@@W4_EVT_FORMAT_MESSAGE_FLAGS@@V2@@Z; PublisherMetadataObject::SetCachedDescString(_EVENT_DESCRIPTOR,_EVT_FORMAT_MESSAGE_FLAGS,RpcString<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>>)
0x18001bf9c  nop
0x18001bf9d  mov     rcx, [rbp+37h+var_68]; void *
0x18001bfa1  test    rcx, rcx
0x18001bfa4  jz      loc_18001BE3D
0x18001bfaa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bfaf  jmp     loc_18001BE3D
0x18001bfb4  mov     [rdi], r12
0x18001bfb7  mov     [rdi+8], r12
0x18001bfbb  mov     [rdi+10h], r12
0x18001bfbf  jmp     loc_18001BE34
0x18001bfc4  test    rbx, rbx
0x18001bfc7  jz      loc_18001C0BC
0x18001bfcd  mov     [rbp+37h+arg_8], r12d
0x18001bfd1  mov     [rbp+37h+var_70], r12d
0x18001bfd5  lea     rcx, [rbp+37h+var_68]
0x18001bfd9  call    ??$replace@$$BY0A@EU?$generic_delete@$$BY0A@EU?$generic_deallocate@$MP6AXPEAX@Z1?MIDL_user_free@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAEAEAV?$unique_ptr@$$BY0A@EU?$generic_delete@$$BY0A@EU?$generic_deallocate@$MP6AXPEAX@Z1?MIDL_user_free@@YAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x18001bfde  mov     rcx, [rbp+37h+arg_38]
0x18001bfe2  mov     [rsp+0E0h+var_90], rcx
0x18001bfe7  mov     [rsp+0E0h+var_98], rax
0x18001bfec  lea     rax, [rbp+37h+var_70]
0x18001bff0  mov     [rsp+0E0h+var_A0], rax
0x18001bff5  lea     rax, [rbp+37h+arg_8]
0x18001bff9  mov     [rsp+0E0h+var_A8], rax
0x18001bffe  mov     eax, [rbp+37h+arg_30]
0x18001c001  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18001c005  mov     rax, [rbp+37h+arg_28]
0x18001c009  mov     [rsp+0E0h+var_C0], rax
0x18001c00e  mov     r9d, [rbp+37h+arg_20]
0x18001c012  mov     r8, r14
0x18001c015  mov     rcx, [rbx+48h]
0x18001c019  call    EvtRpcMessageRenderDefault
0x18001c01e  mov     ebx, eax
0x18001c020  test    eax, eax
0x18001c022  jz      short loc_18001C091
0x18001c024  lea     rax, WPP_GLOBAL_Control
0x18001c02b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c032  cmp     rcx, rax
0x18001c035  jz      short loc_18001C05E
0x18001c037  test    dword ptr [rcx+1Ch], 40000h
0x18001c03e  jz      short loc_18001C05E
0x18001c040  cmp     byte ptr [rcx+19h], 2
0x18001c044  jb      short loc_18001C05E
0x18001c046  mov     edx, 16h
0x18001c04b  mov     r9d, ebx
0x18001c04e  lea     r8, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids
0x18001c055  mov     rcx, [rcx+10h]
0x18001c059  call    WPP_SF_D
0x18001c05e  lea     rax, word_18004024A
0x18001c065  mov     qword ptr [rbp+37h+pExceptionObject], rax
0x18001c069  mov     qword ptr [rbp+37h+pExceptionObject+8], r12
0x18001c06d  mov     [rbp+37h+var_40], r12
0x18001c071  mov     [rbp+37h+var_38], ebx
0x18001c074  mov     [rbp+37h+var_34], 0FFFFFFFFFFFFFFFFh
0x18001c07c  mov     [rbp+37h+var_2C], r12b
0x18001c080  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001c087  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x18001c08b  call    _CxxThrowException_0
0x18001c091  cmp     [rbp+37h+arg_8], r12d
0x18001c095  jz      loc_18001BFB4
0x18001c09b  mov     rax, [rbp+37h+var_68]
0x18001c09f  mov     [rbp+37h+var_68], r12
0x18001c0a3  mov     qword ptr [rbp+37h+var_60], rax
0x18001c0a7  mov     r8d, [rbp+37h+var_70]
0x18001c0ab  lea     rdx, [rbp+37h+var_60]
0x18001c0af  mov     rcx, rdi
0x18001c0b2  call    ??0?$RpcString@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@@QEAA@V?$unique_ptr@$$BY0A@EU?$generic_delete@$$BY0A@EU?$generic_deallocate@$MP6AXPEAX@Z1?MIDL_user_free@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@_K@Z
0x18001c0b7  jmp     loc_18001BE34
0x18001c0bc  lea     rax, WPP_GLOBAL_Control
0x18001c0c3  mov     ebx, 57h ; 'W'
0x18001c0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0cf  cmp     rcx, rax
0x18001c0d2  jz      short loc_18001C0F9
0x18001c0d4  test    dword ptr [rcx+1Ch], 40000h
0x18001c0db  jz      short loc_18001C0F9
0x18001c0dd  cmp     byte ptr [rcx+19h], 2
0x18001c0e1  jb      short loc_18001C0F9
0x18001c0e3  lea     edx, [rbx-40h]
0x18001c0e6  mov     r9d, ebx
0x18001c0e9  lea     r8, WPP_3bc86abd75cd3b17614f116c1f3b6354_Traceguids
0x18001c0f0  mov     rcx, [rcx+10h]
0x18001c0f4  call    WPP_SF_D
0x18001c0f9  xorps   xmm0, xmm0
0x18001c0fc  movdqu  [rbp+37h+pExceptionObject], xmm0
0x18001c101  mov     [rbp+37h+var_40], r12
0x18001c105  mov     [rbp+37h+var_38], ebx
0x18001c108  mov     dword ptr [rbp+37h+var_34], 0FFFFFFFFh
0x18001c10f  mov     dword ptr [rbp+37h+var_34+4], 254h
0x18001c116  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001c11d  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x18001c121  call    _CxxThrowException_0
```
