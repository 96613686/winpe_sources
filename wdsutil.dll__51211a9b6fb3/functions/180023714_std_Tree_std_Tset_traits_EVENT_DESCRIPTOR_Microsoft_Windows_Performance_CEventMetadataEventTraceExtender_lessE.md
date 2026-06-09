# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Insert_nohint<_EVENT_DESCRIPTOR const &,std::_Nil>(bool,_EVENT_DESCRIPTOR const &,std::_Nil)

- ea: `0x180023714`
- end: `0x180023888`
- name: `??$_Insert_nohint@AEBU_EVENT_DESCRIPTOR@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_EVENT_DESCRIPTOR@@@std@@@std@@@std@@_N@1@_NAEBU_EVENT_DESCRIPTOR@@U_Nil@1@@Z`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026640`

## callees

- `0x1800229e4`
- `0x180023714`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Insert_nohint<_EVENT_DESCRIPTOR const &,std::_Nil>(
        __int64 ***a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5)
{
  int v7; // edi
  __int64 **v8; // r11
  __int64 *v9; // rdx
  unsigned __int16 v10; // r9
  __int64 *v11; // rax
  unsigned __int8 v12; // cl
  char v13; // r8
  __int64 *v14; // r9
  __int64 result; // rax
  __int64 j; // rcx
  __int64 *i; // rcx
  unsigned __int16 v18; // cx
  unsigned __int8 v19; // cl
  unsigned __int64 v20; // rcx
  char v21; // [rsp+50h] [rbp+8h] BYREF

  try
  {
    v7 = (int)a1;
    v8 = *a1;
    v9 = (*a1)[1];
    if ( *((_BYTE *)v9 + 25) )
    {
      v13 = 1;
      v14 = (__int64 *)*a1;
      v11 = (__int64 *)*a1;
    }
    else
    {
      v10 = *(_WORD *)a4;
      do
      {
        v11 = v9;
        if ( v10 >= *((_WORD *)v9 + 16)
          && (v10 > *((_WORD *)v9 + 16)
           || (v12 = *(_BYTE *)(a4 + 2), v12 >= *((_BYTE *)v9 + 34))
           && (v12 > *((_BYTE *)v9 + 34)
            || *(_QWORD *)a4 >= (unsigned __int64)v9[4]
            && (*(_QWORD *)a4 > (unsigned __int64)v9[4] || *(_QWORD *)(a4 + 8) >= (unsigned __int64)v9[5]))) )
        {
          v13 = 0;
          v9 = (__int64 *)v9[2];
        }
        else
        {
          v13 = 1;
          v9 = (__int64 *)*v9;
        }
      }
      while ( !*((_BYTE *)v9 + 25) );
      v14 = v11;
      if ( !v13 )
        goto LABEL_32;
    }
    if ( v14 == *v8 )
    {
      *(_QWORD *)a2 = *(_QWORD *)std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::_Insert_at<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::_Nil>(
                                   v7,
                                   (unsigned int)&v21,
                                   1,
                                   (_DWORD)v14,
                                   a4);
      *(_BYTE *)(a2 + 8) = 1;
      return a2;
    }
    if ( *((_BYTE *)v14 + 25) )
    {
      v11 = (__int64 *)v14[2];
    }
    else if ( *(_BYTE *)(*v14 + 25) )
    {
      for ( i = (__int64 *)v14[1]; !*((_BYTE *)i + 25) && v11 == (__int64 *)*i; i = (__int64 *)i[1] )
        v11 = i;
      if ( !*((_BYTE *)v11 + 25) )
        v11 = i;
    }
    else
    {
      v11 = (__int64 *)*v14;
      for ( j = *(_QWORD *)(*v14 + 16); !*(_BYTE *)(j + 25); j = v11[2] )
        v11 = (__int64 *)v11[2];
    }
LABEL_32:
    v18 = *((_WORD *)v11 + 16);
    if ( v18 < *(_WORD *)a4
      || v18 <= *(_WORD *)a4
      && ((v19 = *((_BYTE *)v11 + 34), v19 < *(_BYTE *)(a4 + 2))
       || v19 <= *(_BYTE *)(a4 + 2)
       && ((v20 = v11[4], v20 < *(_QWORD *)a4) || v20 <= *(_QWORD *)a4 && (unsigned __int64)v11[5] < *(_QWORD *)(a4 + 8))) )
    {
      *(_QWORD *)a2 = *(_QWORD *)std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::_Insert_at<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::_Nil>(
                                   v7,
                                   (unsigned int)&v21,
                                   v13,
                                   (_DWORD)v14,
                                   a4);
      *(_BYTE *)(a2 + 8) = 1;
      result = a2;
    }
    else
    {
      *(_QWORD *)a2 = v11;
      *(_BYTE *)(a2 + 8) = 0;
      result = a2;
    }
  }
  catch ( ... )
  {
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180023714  push    rdi
0x180023716  sub     rsp, 40h
0x18002371a  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x180023723  mov     [rsp+48h+arg_8], rbx
0x180023728  mov     r10, r9
0x18002372b  mov     rbx, rdx
0x18002372e  mov     rdi, rcx
0x180023731  mov     r11, [rcx]
0x180023734  mov     rdx, [r11+8]
0x180023738  cmp     byte ptr [rdx+19h], 0
0x18002373c  jnz     short loc_180023791
0x18002373e  movzx   r9d, word ptr [r9]
0x180023742  mov     rax, rdx
0x180023745  cmp     r9w, [rdx+20h]
0x18002374a  jb      short loc_18002376E
0x18002374c  ja      short loc_180023776
0x18002374e  mov     cl, [r10+2]
0x180023752  cmp     cl, [rdx+22h]
0x180023755  jb      short loc_18002376E
0x180023757  ja      short loc_180023776
0x180023759  mov     rcx, [r10]
0x18002375c  cmp     rcx, [rdx+20h]
0x180023760  jb      short loc_18002376E
0x180023762  ja      short loc_180023776
0x180023764  mov     rcx, [rdx+28h]
0x180023768  cmp     [r10+8], rcx
0x18002376c  jnb     short loc_180023776
0x18002376e  mov     r8b, 1
0x180023771  mov     rdx, [rdx]
0x180023774  jmp     short loc_18002377D
0x180023776  xor     r8b, r8b
0x180023779  mov     rdx, [rdx+10h]
0x18002377d  cmp     byte ptr [rdx+19h], 0
0x180023781  jz      short loc_180023742
0x180023783  mov     r9, rax
0x180023786  test    r8b, r8b
0x180023789  jz      loc_18002381D
0x18002378f  jmp     short loc_18002379A
0x180023791  mov     r8b, 1
0x180023794  mov     r9, r11
0x180023797  mov     rax, r11
0x18002379a  cmp     r9, [r11]
0x18002379d  jnz     short loc_1800237CE
0x18002379f  mov     al, [rsp+48h+arg_20]
0x1800237a3  mov     [rsp+48h+var_20], al
0x1800237a7  mov     [rsp+48h+var_28], r10
0x1800237ac  mov     r8b, 1
0x1800237af  lea     rdx, [rsp+48h+arg_0]
0x1800237b4  mov     rcx, rdi
0x1800237b7  call    ??$_Insert_at@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@1@$$QEAU?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::_Insert_at<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::_Nil>(bool,std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *> *,Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator> &&,std::_Nil)
0x1800237bc  mov     rax, [rax]
0x1800237bf  mov     [rbx], rax
0x1800237c2  mov     byte ptr [rbx+8], 1
0x1800237c6  mov     rax, rbx
0x1800237c9  jmp     loc_18002387C
0x1800237ce  cmp     byte ptr [r9+19h], 0
0x1800237d3  jz      short loc_1800237DB
0x1800237d5  mov     rax, [r9+10h]
0x1800237d9  jmp     short loc_18002381D
0x1800237db  mov     rcx, [r9]
0x1800237de  cmp     byte ptr [rcx+19h], 0
0x1800237e2  jnz     short loc_1800237FD
0x1800237e4  mov     rax, rcx
0x1800237e7  mov     rcx, [rcx+10h]
0x1800237eb  jmp     short loc_1800237F5
0x1800237ed  mov     rax, [rax+10h]
0x1800237f1  mov     rcx, [rax+10h]
0x1800237f5  cmp     byte ptr [rcx+19h], 0
0x1800237f9  jz      short loc_1800237ED
0x1800237fb  jmp     short loc_18002381D
0x1800237fd  mov     rcx, [r9+8]
0x180023801  jmp     short loc_18002380F
0x180023803  cmp     rax, [rcx]
0x180023806  jnz     short loc_180023815
0x180023808  mov     rax, rcx
0x18002380b  mov     rcx, [rcx+8]
0x18002380f  cmp     byte ptr [rcx+19h], 0
0x180023813  jz      short loc_180023803
0x180023815  cmp     byte ptr [rax+19h], 0
0x180023819  cmovz   rax, rcx
0x18002381d  movzx   ecx, word ptr [rax+20h]
0x180023821  cmp     cx, [r10]
0x180023825  jb      short loc_180023855
0x180023827  ja      short loc_180023849
0x180023829  mov     cl, [rax+22h]
0x18002382c  cmp     cl, [r10+2]
0x180023830  jb      short loc_180023855
0x180023832  ja      short loc_180023849
0x180023834  mov     rcx, [rax+20h]
0x180023838  cmp     rcx, [r10]
0x18002383b  jb      short loc_180023855
0x18002383d  ja      short loc_180023849
0x18002383f  mov     rcx, [r10+8]
0x180023843  cmp     [rax+28h], rcx
0x180023847  jb      short loc_180023855
0x180023849  mov     [rbx], rax
0x18002384c  mov     byte ptr [rbx+8], 0
0x180023850  mov     rax, rbx
0x180023853  jmp     short loc_18002387C
0x180023855  mov     al, [rsp+48h+arg_20]
0x180023859  mov     [rsp+48h+var_20], al
0x18002385d  mov     [rsp+48h+var_28], r10
0x180023862  lea     rdx, [rsp+48h+arg_0]
0x180023867  mov     rcx, rdi
0x18002386a  call    ??$_Insert_at@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@PEAX@1@$$QEAU?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::_Insert_at<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::_Nil>(bool,std::_Tree_node<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,void *> *,Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator> &&,std::_Nil)
0x18002386f  mov     rax, [rax]
0x180023872  mov     [rbx], rax
0x180023875  mov     byte ptr [rbx+8], 1
0x180023879  mov     rax, rbx
0x18002387c  mov     rbx, [rsp+48h+arg_8]
0x180023881  add     rsp, 40h
0x180023885  pop     rdi
0x180023886  retn
```
