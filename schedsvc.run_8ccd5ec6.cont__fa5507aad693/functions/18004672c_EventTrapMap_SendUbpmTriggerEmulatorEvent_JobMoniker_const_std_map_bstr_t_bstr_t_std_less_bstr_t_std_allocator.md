# EventTrapMap::SendUbpmTriggerEmulatorEvent(JobMoniker const &,std::map<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>> const &)

- ea: `0x18004672c`
- end: `0x180046a42`
- name: `?SendUbpmTriggerEmulatorEvent@EventTrapMap@@AEAAJAEBVJobMoniker@@AEBV?$map@V_bstr_t@@V1@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@V1@@std@@@3@@std@@@Z`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002dd30`

## callees

- `0x180027910`
- `0x180045d1c`
- `0x18004672c`
- `0x180051258`
- `0x18005a2d6`
- `0x180082a40`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x18004678f`
- `ntdll!EtwEventRegister` at `0x18004678f`
- `ntdll!EtwEventWrite` at `0x180046a20`
- `ntdll!EtwEventWrite` at `0x180046a20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800467c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800467c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EventTrapMap::SendUbpmTriggerEmulatorEvent(__int64 a1, __int64 a2, __int64 **a3)
{
  _WORD *v4; // r10
  void *v5; // r15
  _QWORD *v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  SIZE_T v10; // r12
  __int64 *v11; // r9
  __int64 v12; // rax
  __int64 v13; // r14
  _QWORD *v14; // rcx
  _WORD *v15; // rdx
  __int64 v16; // r8
  _QWORD *v17; // rcx
  _WORD *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 i; // rcx
  void *v22; // rax
  char *v23; // rsi
  __int64 v24; // rbx
  _QWORD *v25; // rax
  _WORD *v26; // rdx
  __int64 v27; // rcx
  _WORD *v28; // rdx
  __int64 *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rax
  char *v32; // rsi
  _QWORD *v33; // rcx
  _WORD *v34; // rdx
  __int64 v35; // rax
  _WORD *v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 j; // rax
  _QWORD *v44; // rax
  _WORD *v45; // rcx
  _WORD *v46; // rcx
  void *v47; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v48; // [rsp+28h] [rbp-40h]
  __int64 v49; // [rsp+30h] [rbp-38h]
  _WORD *v50; // [rsp+38h] [rbp-30h] BYREF
  __int128 v51; // [rsp+40h] [rbp-28h]
  unsigned __int64 v52; // [rsp+50h] [rbp-18h]

  v49 = a2;
  v4 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v5 = 0;
  v47 = 0;
  v6 = (_QWORD *)(a1 + 2088);
  v48 = (_QWORD *)(a1 + 2088);
  if ( !*(_QWORD *)(a1 + 2088) )
  {
    v7 = EtwEventRegister(TRIGGER_EMULATOR_PROVIDER_GUID, 0, 0, a1 + 2088);
    v8 = v7;
    v4 = 0;
    if ( v7 )
    {
      if ( v7 <= 0 )
        goto LABEL_5;
      goto LABEL_4;
    }
  }
  v8 = 0;
  v10 = 0;
  v11 = *a3;
  v12 = **a3;
  v13 = -1;
  while ( (__int64 *)v12 != v11 )
  {
    v14 = *(_QWORD **)(v12 + 32);
    if ( v14 )
      v15 = (_WORD *)*v14;
    else
      v15 = v4;
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] != (_WORD)v4 );
    v17 = *(_QWORD **)(v12 + 40);
    if ( v17 )
      v18 = (_WORD *)*v17;
    else
      v18 = v4;
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] != (_WORD)v4 );
    v10 += 2 * (v16 + v19) + 4;
    if ( *(_BYTE *)(v12 + 25) == (_BYTE)v4 )
    {
      v20 = *(_QWORD *)(v12 + 16);
      if ( *(_BYTE *)(v20 + 25) == (_BYTE)v4 )
      {
        v12 = std::_Tree_val<std::_Tree_simple_types<std::pair<_bstr_t const,std::list<_FILETIME> *>>>::_Min(
                v20,
                v18,
                v16);
      }
      else
      {
        for ( i = *(_QWORD *)(v12 + 8);
              *(_BYTE *)(i + 25) == (_BYTE)v4 && v12 == *(_QWORD *)(i + 16);
              i = *(_QWORD *)(i + 8) )
        {
          v12 = i;
        }
        v12 = i;
      }
    }
  }
  if ( v10 )
  {
    v22 = operator new(v10);
    wmi::AutoVectorPtr<unsigned char>::operator=(&v47, v22);
    v5 = v47;
    v23 = (char *)v47;
    v24 = **a3;
    v4 = 0;
    while ( (__int64 *)v24 != *a3 )
    {
      v25 = *(_QWORD **)(v24 + 32);
      if ( v25 )
        v26 = (_WORD *)*v25;
      else
        v26 = v4;
      v27 = -1;
      do
        ++v27;
      while ( v26[v27] != (_WORD)v4 );
      if ( v25 )
        v28 = (_WORD *)*v25;
      else
        v28 = v4;
      memcpy_0(v23, v28, 2 * v27 + 2);
      v29 = *(__int64 **)(v24 + 32);
      if ( v29 )
        v30 = *v29;
      else
        v30 = 0;
      v31 = -1;
      do
        ++v31;
      while ( *(_WORD *)(v30 + 2 * v31) );
      v32 = &v23[2 * v31 + 2];
      v33 = *(_QWORD **)(v24 + 40);
      if ( v33 )
        v34 = (_WORD *)*v33;
      else
        v34 = 0;
      v35 = -1;
      do
        ++v35;
      while ( v34[v35] );
      if ( v33 )
        v36 = (_WORD *)*v33;
      else
        v36 = 0;
      memcpy_0(v32, v36, 2 * v35 + 2);
      v39 = *(__int64 **)(v24 + 40);
      v4 = 0;
      if ( v39 )
        v40 = *v39;
      else
        v40 = 0;
      v41 = -1;
      do
        ++v41;
      while ( *(_WORD *)(v40 + 2 * v41) );
      v23 = &v32[2 * v41 + 2];
      if ( !*(_BYTE *)(v24 + 25) )
      {
        v42 = *(_QWORD *)(v24 + 16);
        if ( *(_BYTE *)(v42 + 25) )
        {
          for ( j = *(_QWORD *)(v24 + 8); !*(_BYTE *)(j + 25) && v24 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
            v24 = j;
        }
        else
        {
          j = std::_Tree_val<std::_Tree_simple_types<std::pair<_bstr_t const,std::list<_FILETIME> *>>>::_Min(
                v42,
                v37,
                v38);
        }
        v24 = j;
      }
    }
    v6 = v48;
  }
  v44 = *(_QWORD **)(v49 + 16);
  if ( v44 )
    v45 = (_WORD *)*v44;
  else
    v45 = v4;
  do
    ++v13;
  while ( v45[v13] != (_WORD)v4 );
  if ( v44 )
    v46 = (_WORD *)*v44;
  else
    v46 = v4;
  v50 = v46;
  LODWORD(v51) = 2 * v13 + 2;
  DWORD1(v51) = (_DWORD)v4;
  *((_QWORD *)&v51 + 1) = v5;
  v52 = __PAIR64__((unsigned int)v4, v10);
  v7 = EtwEventWrite(*v6, UBPM_TRIGGER_EMULATOR_EVENT, 2, &v50);
  if ( v7 )
  {
    if ( v7 > 0 )
    {
LABEL_4:
      v8 = (unsigned __int16)v7 | 0x80070000;
      goto LABEL_5;
    }
    v8 = v7;
  }
LABEL_5:
  if ( v5 )
    HeapFree(g_PrivateHeap, 0, v5);
  return v8;
}

```

## disassembly

```asm
0x18004672c  push    rbp
0x18004672e  push    rbx
0x18004672f  push    rsi
0x180046730  push    rdi
0x180046731  push    r12
0x180046733  push    r13
0x180046735  push    r14
0x180046737  push    r15
0x180046739  mov     rbp, rsp
0x18004673c  sub     rsp, 68h
0x180046740  mov     rax, cs:__security_cookie
0x180046747  xor     rax, rsp
0x18004674a  mov     [rbp+var_10], rax
0x18004674e  mov     r13, r8
0x180046751  mov     [rbp+var_38], rdx
0x180046755  xor     r10d, r10d
0x180046758  mov     [rbp+var_30], r10
0x18004675c  xorps   xmm0, xmm0
0x18004675f  xor     eax, eax
0x180046761  movups  [rbp+var_28], xmm0
0x180046765  mov     [rbp+var_18], rax
0x180046769  mov     r15d, r10d
0x18004676c  mov     [rbp+var_48], r10
0x180046770  lea     rbx, [rcx+828h]
0x180046777  mov     [rbp+var_40], rbx
0x18004677b  cmp     [rbx], r10
0x18004677e  jnz     short loc_1800467EC
0x180046780  mov     r9, rbx
0x180046783  xor     r8d, r8d
0x180046786  xor     edx, edx
0x180046788  lea     rcx, TRIGGER_EMULATOR_PROVIDER_GUID
0x18004678f  call    cs:__imp_EtwEventRegister
0x180046796  nop     dword ptr [rax+rax+00h]
0x18004679b  mov     edi, eax
0x18004679d  xor     r10d, r10d
0x1800467a0  test    eax, eax
0x1800467a2  jz      short loc_1800467EC
0x1800467a4  jle     short loc_1800467AF
0x1800467a6  movzx   edi, ax
0x1800467a9  or      edi, 80070000h
0x1800467af  test    r15, r15
0x1800467b2  jz      short loc_1800467CC
0x1800467b4  mov     r8, r15; lpMem
0x1800467b7  xor     edx, edx; dwFlags
0x1800467b9  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800467c0  call    cs:__imp_HeapFree
0x1800467c7  nop     dword ptr [rax+rax+00h]
0x1800467cc  mov     eax, edi
0x1800467ce  mov     rcx, [rbp+var_10]
0x1800467d2  xor     rcx, rsp; StackCookie
0x1800467d5  call    __security_check_cookie
0x1800467da  add     rsp, 68h
0x1800467de  pop     r15
0x1800467e0  pop     r14
0x1800467e2  pop     r13
0x1800467e4  pop     r12
0x1800467e6  pop     rdi
0x1800467e7  pop     rsi
0x1800467e8  pop     rbx
0x1800467e9  pop     rbp
0x1800467ea  retn
0x1800467ec  mov     edi, r10d
0x1800467ef  mov     r12, r10
0x1800467f2  mov     r9, [r13+0]
0x1800467f6  mov     rax, [r9]
0x1800467f9  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800467fd  cmp     rax, r9
0x180046800  jz      short loc_180046881
0x180046802  mov     rcx, [rax+20h]
0x180046806  test    rcx, rcx
0x180046809  jz      short loc_180046810
0x18004680b  mov     rdx, [rcx]
0x18004680e  jmp     short loc_180046813
0x180046810  mov     rdx, r10
0x180046813  mov     r8, r14
0x180046816  inc     r8
0x180046819  cmp     [rdx+r8*2], r10w
0x18004681e  jnz     short loc_180046816
0x180046820  mov     rcx, [rax+28h]
0x180046824  test    rcx, rcx
0x180046827  jz      short loc_18004682E
0x180046829  mov     rdx, [rcx]
0x18004682c  jmp     short loc_180046831
0x18004682e  mov     rdx, r10
0x180046831  mov     rcx, r14
0x180046834  inc     rcx
0x180046837  cmp     [rdx+rcx*2], r10w
0x18004683c  jnz     short loc_180046834
0x18004683e  add     rcx, r8
0x180046841  lea     r12, [r12+rcx*2]
0x180046845  add     r12, 4
0x180046849  cmp     [rax+19h], r10b
0x18004684d  jnz     short loc_1800467FD
0x18004684f  mov     rcx, [rax+10h]
0x180046853  cmp     [rcx+19h], r10b
0x180046857  jnz     short loc_180046860
0x180046859  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV_bstr_t@@PEAV?$list@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAV?$list@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_bstr_t const,std::list<_FILETIME> *>>>::_Min(std::_Tree_node<std::pair<_bstr_t const,std::list<_FILETIME> *>,void *> *)
0x18004685e  jmp     short loc_1800467FD
0x180046860  mov     rcx, [rax+8]
0x180046864  jmp     short loc_180046873
0x180046866  cmp     rax, [rcx+10h]
0x18004686a  jnz     short loc_180046879
0x18004686c  mov     rax, rcx
0x18004686f  mov     rcx, [rcx+8]
0x180046873  cmp     [rcx+19h], r10b
0x180046877  jz      short loc_180046866
0x180046879  mov     rax, rcx
0x18004687c  jmp     loc_1800467FD
0x180046881  test    r12, r12
0x180046884  jz      loc_1800469C1
0x18004688a  mov     rcx, r12; dwBytes
0x18004688d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180046892  mov     rdx, rax
0x180046895  lea     rcx, [rbp+var_48]
0x180046899  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x18004689e  mov     r15, [rbp+var_48]
0x1800468a2  mov     rsi, r15
0x1800468a5  mov     rbx, [r13+0]
0x1800468a9  mov     rbx, [rbx]
0x1800468ac  xor     r10d, r10d
0x1800468af  cmp     rbx, [r13+0]
0x1800468b3  jz      loc_1800469BD
0x1800468b9  mov     rax, [rbx+20h]
0x1800468bd  test    rax, rax
0x1800468c0  jz      short loc_1800468C7
0x1800468c2  mov     rdx, [rax]
0x1800468c5  jmp     short loc_1800468CA
0x1800468c7  mov     rdx, r10
0x1800468ca  mov     rcx, r14
0x1800468cd  inc     rcx
0x1800468d0  cmp     [rdx+rcx*2], r10w
0x1800468d5  jnz     short loc_1800468CD
0x1800468d7  lea     r8, ds:2[rcx*2]; Size
0x1800468df  test    rax, rax
0x1800468e2  jz      short loc_1800468E9
0x1800468e4  mov     rdx, [rax]
0x1800468e7  jmp     short loc_1800468EC
0x1800468e9  mov     rdx, r10; Src
0x1800468ec  mov     rcx, rsi; void *
0x1800468ef  call    memcpy_0
0x1800468f4  mov     rcx, [rbx+20h]
0x1800468f8  xor     r9d, r9d
0x1800468fb  test    rcx, rcx
0x1800468fe  jz      short loc_180046905
0x180046900  mov     rcx, [rcx]
0x180046903  jmp     short loc_180046908
0x180046905  mov     rcx, r9
0x180046908  mov     rax, r14
0x18004690b  inc     rax
0x18004690e  cmp     [rcx+rax*2], r9w
0x180046913  jnz     short loc_18004690B
0x180046915  lea     rsi, [rsi+rax*2]
0x180046919  add     rsi, 2
0x18004691d  mov     rcx, [rbx+28h]
0x180046921  test    rcx, rcx
0x180046924  jz      short loc_18004692B
0x180046926  mov     rdx, [rcx]
0x180046929  jmp     short loc_18004692E
0x18004692b  mov     rdx, r9
0x18004692e  mov     rax, r14
0x180046931  inc     rax
0x180046934  cmp     [rdx+rax*2], r9w
0x180046939  jnz     short loc_180046931
0x18004693b  lea     r8, ds:2[rax*2]; Size
0x180046943  test    rcx, rcx
0x180046946  jz      short loc_18004694D
0x180046948  mov     rdx, [rcx]
0x18004694b  jmp     short loc_180046950
0x18004694d  mov     rdx, r9; Src
0x180046950  mov     rcx, rsi; void *
0x180046953  call    memcpy_0
0x180046958  mov     rcx, [rbx+28h]
0x18004695c  xor     r10d, r10d
0x18004695f  test    rcx, rcx
0x180046962  jz      short loc_180046969
0x180046964  mov     rcx, [rcx]
0x180046967  jmp     short loc_18004696C
0x180046969  mov     rcx, r10
0x18004696c  mov     rax, r14
0x18004696f  inc     rax
0x180046972  cmp     [rcx+rax*2], r10w
0x180046977  jnz     short loc_18004696F
0x180046979  lea     rsi, [rsi+rax*2]
0x18004697d  add     rsi, 2
0x180046981  cmp     [rbx+19h], r10b
0x180046985  jnz     loc_1800468AF
0x18004698b  mov     rcx, [rbx+10h]
0x18004698f  cmp     [rcx+19h], r10b
0x180046993  jnz     short loc_18004699C
0x180046995  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV_bstr_t@@PEAV?$list@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAV?$list@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_bstr_t const,std::list<_FILETIME> *>>>::_Min(std::_Tree_node<std::pair<_bstr_t const,std::list<_FILETIME> *>,void *> *)
0x18004699a  jmp     short loc_1800469B5
0x18004699c  mov     rax, [rbx+8]
0x1800469a0  jmp     short loc_1800469AF
0x1800469a2  cmp     rbx, [rax+10h]
0x1800469a6  jnz     short loc_1800469B5
0x1800469a8  mov     rbx, rax
0x1800469ab  mov     rax, [rax+8]
0x1800469af  cmp     [rax+19h], r10b
0x1800469b3  jz      short loc_1800469A2
0x1800469b5  mov     rbx, rax
0x1800469b8  jmp     loc_1800468AF
0x1800469bd  mov     rbx, [rbp+var_40]
0x1800469c1  mov     rax, [rbp+var_38]
0x1800469c5  mov     rax, [rax+10h]
0x1800469c9  test    rax, rax
0x1800469cc  jz      short loc_1800469D3
0x1800469ce  mov     rcx, [rax]
0x1800469d1  jmp     short loc_1800469D6
0x1800469d3  mov     rcx, r10
0x1800469d6  inc     r14
0x1800469d9  cmp     [rcx+r14*2], r10w
0x1800469de  jnz     short loc_1800469D6
0x1800469e0  lea     edx, ds:2[r14*2]
0x1800469e8  test    rax, rax
0x1800469eb  jz      short loc_1800469F2
0x1800469ed  mov     rcx, [rax]
0x1800469f0  jmp     short loc_1800469F5
0x1800469f2  mov     rcx, r10
0x1800469f5  mov     [rbp+var_30], rcx
0x1800469f9  mov     dword ptr [rbp+var_28], edx
0x1800469fc  mov     dword ptr [rbp+var_28+4], r10d
0x180046a00  mov     qword ptr [rbp+var_28+8], r15
0x180046a04  mov     dword ptr [rbp+var_18], r12d
0x180046a08  mov     dword ptr [rbp+var_18+4], r10d
0x180046a0c  lea     r9, [rbp+var_30]
0x180046a10  mov     r8d, 2
0x180046a16  lea     rdx, UBPM_TRIGGER_EMULATOR_EVENT
0x180046a1d  mov     rcx, [rbx]
0x180046a20  call    cs:__imp_EtwEventWrite
0x180046a27  nop     dword ptr [rax+rax+00h]
0x180046a2c  test    eax, eax
0x180046a2e  jz      loc_1800467AF
0x180046a34  jg      loc_1800467A6
0x180046a3a  mov     edi, eax
0x180046a3c  jmp     loc_1800467AF
```
