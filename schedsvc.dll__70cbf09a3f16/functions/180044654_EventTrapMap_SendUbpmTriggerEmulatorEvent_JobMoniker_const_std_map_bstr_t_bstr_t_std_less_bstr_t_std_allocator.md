# EventTrapMap::SendUbpmTriggerEmulatorEvent(JobMoniker const &,std::map<_bstr_t,_bstr_t,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,_bstr_t>>> const &)

- ea: `0x180044654`
- end: `0x180044957`
- name: `?SendUbpmTriggerEmulatorEvent@EventTrapMap@@AEAAJAEBVJobMoniker@@AEBV?$map@V_bstr_t@@V1@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@V1@@std@@@3@@std@@@Z`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800329cc`

## callees

- `0x180030f80`
- `0x180043d78`
- `0x180044654`
- `0x18004eee4`
- `0x180057926`
- `0x18007e6d0`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x1800446b7`
- `ntdll!EtwEventRegister` at `0x1800446b7`
- `ntdll!EtwEventWrite` at `0x18004493b`
- `ntdll!EtwEventWrite` at `0x18004493b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800446e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800446e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EventTrapMap::SendUbpmTriggerEmulatorEvent(__int64 a1, __int64 a2, _QWORD **a3)
{
  _WORD *v4; // r10
  void *v5; // r15
  _QWORD *v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  SIZE_T v10; // r12
  _QWORD **v11; // r9
  _QWORD *v12; // rax
  __int64 v13; // r14
  _QWORD *v14; // rcx
  _WORD *v15; // rdx
  __int64 v16; // r8
  _QWORD *v17; // rcx
  _WORD *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 i; // rcx
  LPVOID v22; // rax
  char *v23; // rsi
  _QWORD *v24; // rbx
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
  __int64 *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  _QWORD *j; // rax
  _QWORD *v42; // rax
  _WORD *v43; // rcx
  _WORD *v44; // rcx
  void *v45; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v46; // [rsp+28h] [rbp-40h]
  __int64 v47; // [rsp+30h] [rbp-38h]
  _WORD *v48; // [rsp+38h] [rbp-30h] BYREF
  __int128 v49; // [rsp+40h] [rbp-28h]
  unsigned __int64 v50; // [rsp+50h] [rbp-18h]

  v47 = a2;
  v4 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v5 = 0;
  v45 = 0;
  v6 = (_QWORD *)(a1 + 2088);
  v46 = (_QWORD *)(a1 + 2088);
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
  v11 = (_QWORD **)*a3;
  v12 = (_QWORD *)**a3;
  v13 = -1;
  while ( v12 != v11 )
  {
    v14 = (_QWORD *)v12[4];
    if ( v14 )
      v15 = (_WORD *)*v14;
    else
      v15 = v4;
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] != (_WORD)v4 );
    v17 = (_QWORD *)v12[5];
    if ( v17 )
      v18 = (_WORD *)*v17;
    else
      v18 = v4;
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] != (_WORD)v4 );
    v10 += 2 * (v16 + v19) + 4;
    if ( *((_BYTE *)v12 + 25) == (_BYTE)v4 )
    {
      v20 = v12[2];
      if ( *(_BYTE *)(v20 + 25) == (_BYTE)v4 )
      {
        v12 = std::_Tree_val<std::_Tree_simple_types<std::pair<_bstr_t const,std::list<_FILETIME> *>>>::_Min((_QWORD *)v20);
      }
      else
      {
        for ( i = v12[1]; *(_BYTE *)(i + 25) == (_BYTE)v4 && v12 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
          v12 = (_QWORD *)i;
        v12 = (_QWORD *)i;
      }
    }
  }
  if ( v10 )
  {
    v22 = operator new(v10);
    wmi::AutoVectorPtr<unsigned char>::operator=(&v45, v22);
    v5 = v45;
    v23 = (char *)v45;
    v24 = (_QWORD *)**a3;
    v4 = 0;
    while ( v24 != *a3 )
    {
      v25 = (_QWORD *)v24[4];
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
      v29 = (__int64 *)v24[4];
      if ( v29 )
        v30 = *v29;
      else
        v30 = 0;
      v31 = -1;
      do
        ++v31;
      while ( *(_WORD *)(v30 + 2 * v31) );
      v32 = &v23[2 * v31 + 2];
      v33 = (_QWORD *)v24[5];
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
      v37 = (__int64 *)v24[5];
      v4 = 0;
      if ( v37 )
        v38 = *v37;
      else
        v38 = 0;
      v39 = -1;
      do
        ++v39;
      while ( *(_WORD *)(v38 + 2 * v39) );
      v23 = &v32[2 * v39 + 2];
      if ( !*((_BYTE *)v24 + 25) )
      {
        v40 = v24[2];
        if ( *(_BYTE *)(v40 + 25) )
        {
          for ( j = (_QWORD *)v24[1]; !*((_BYTE *)j + 25) && v24 == (_QWORD *)j[2]; j = (_QWORD *)j[1] )
            v24 = j;
        }
        else
        {
          j = std::_Tree_val<std::_Tree_simple_types<std::pair<_bstr_t const,std::list<_FILETIME> *>>>::_Min((_QWORD *)v40);
        }
        v24 = j;
      }
    }
    v6 = v46;
  }
  v42 = *(_QWORD **)(v47 + 16);
  if ( v42 )
    v43 = (_WORD *)*v42;
  else
    v43 = v4;
  do
    ++v13;
  while ( v43[v13] != (_WORD)v4 );
  if ( v42 )
    v44 = (_WORD *)*v42;
  else
    v44 = v4;
  v48 = v44;
  LODWORD(v49) = 2 * v13 + 2;
  DWORD1(v49) = (_DWORD)v4;
  *((_QWORD *)&v49 + 1) = v5;
  v50 = __PAIR64__((unsigned int)v4, v10);
  v7 = EtwEventWrite(*v6, UBPM_TRIGGER_EMULATOR_EVENT, 2, &v48);
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
0x180044654  push    rbp
0x180044656  push    rbx
0x180044657  push    rsi
0x180044658  push    rdi
0x180044659  push    r12
0x18004465b  push    r13
0x18004465d  push    r14
0x18004465f  push    r15
0x180044661  mov     rbp, rsp
0x180044664  sub     rsp, 68h
0x180044668  mov     rax, cs:__security_cookie
0x18004466f  xor     rax, rsp
0x180044672  mov     [rbp+var_10], rax
0x180044676  mov     r13, r8
0x180044679  mov     [rbp+var_38], rdx
0x18004467d  xor     r10d, r10d
0x180044680  mov     [rbp+var_30], r10
0x180044684  xorps   xmm0, xmm0
0x180044687  xor     eax, eax
0x180044689  movups  [rbp+var_28], xmm0
0x18004468d  mov     [rbp+var_18], rax
0x180044691  mov     r15d, r10d
0x180044694  mov     [rbp+var_48], r10
0x180044698  lea     rbx, [rcx+828h]
0x18004469f  mov     [rbp+var_40], rbx
0x1800446a3  cmp     [rbx], r10
0x1800446a6  jnz     short loc_180044707
0x1800446a8  mov     r9, rbx
0x1800446ab  xor     r8d, r8d
0x1800446ae  xor     edx, edx
0x1800446b0  lea     rcx, TRIGGER_EMULATOR_PROVIDER_GUID
0x1800446b7  call    cs:__imp_EtwEventRegister
0x1800446bd  mov     edi, eax
0x1800446bf  xor     r10d, r10d
0x1800446c2  test    eax, eax
0x1800446c4  jz      short loc_180044707
0x1800446c6  jle     short loc_1800446D1
0x1800446c8  movzx   edi, ax
0x1800446cb  or      edi, 80070000h
0x1800446d1  test    r15, r15
0x1800446d4  jz      short loc_1800446E8
0x1800446d6  mov     r8, r15; lpMem
0x1800446d9  xor     edx, edx; dwFlags
0x1800446db  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800446e2  call    cs:__imp_HeapFree
0x1800446e8  mov     eax, edi
0x1800446ea  mov     rcx, [rbp+var_10]
0x1800446ee  xor     rcx, rsp; StackCookie
0x1800446f1  call    __security_check_cookie
0x1800446f6  add     rsp, 68h
0x1800446fa  pop     r15
0x1800446fc  pop     r14
0x1800446fe  pop     r13
0x180044700  pop     r12
0x180044702  pop     rdi
0x180044703  pop     rsi
0x180044704  pop     rbx
0x180044705  pop     rbp
0x180044706  retn
0x180044707  mov     edi, r10d
0x18004470a  mov     r12, r10
0x18004470d  mov     r9, [r13+0]
0x180044711  mov     rax, [r9]
0x180044714  or      r14, 0FFFFFFFFFFFFFFFFh
0x180044718  cmp     rax, r9
0x18004471b  jz      short loc_18004479C
0x18004471d  mov     rcx, [rax+20h]
0x180044721  test    rcx, rcx
0x180044724  jz      short loc_18004472B
0x180044726  mov     rdx, [rcx]
0x180044729  jmp     short loc_18004472E
0x18004472b  mov     rdx, r10
0x18004472e  mov     r8, r14
0x180044731  inc     r8
0x180044734  cmp     [rdx+r8*2], r10w
0x180044739  jnz     short loc_180044731
0x18004473b  mov     rcx, [rax+28h]
0x18004473f  test    rcx, rcx
0x180044742  jz      short loc_180044749
0x180044744  mov     rdx, [rcx]
0x180044747  jmp     short loc_18004474C
0x180044749  mov     rdx, r10
0x18004474c  mov     rcx, r14
0x18004474f  inc     rcx
0x180044752  cmp     [rdx+rcx*2], r10w
0x180044757  jnz     short loc_18004474F
0x180044759  add     rcx, r8
0x18004475c  lea     r12, [r12+rcx*2]
0x180044760  add     r12, 4
0x180044764  cmp     [rax+19h], r10b
0x180044768  jnz     short loc_180044718
0x18004476a  mov     rcx, [rax+10h]
0x18004476e  cmp     [rcx+19h], r10b
0x180044772  jnz     short loc_18004477B
0x180044774  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV_bstr_t@@PEAV?$list@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAV?$list@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_bstr_t const,std::list<_FILETIME> *>>>::_Min(std::_Tree_node<std::pair<_bstr_t const,std::list<_FILETIME> *>,void *> *)
0x180044779  jmp     short loc_180044718
0x18004477b  mov     rcx, [rax+8]
0x18004477f  jmp     short loc_18004478E
0x180044781  cmp     rax, [rcx+10h]
0x180044785  jnz     short loc_180044794
0x180044787  mov     rax, rcx
0x18004478a  mov     rcx, [rcx+8]
0x18004478e  cmp     [rcx+19h], r10b
0x180044792  jz      short loc_180044781
0x180044794  mov     rax, rcx
0x180044797  jmp     loc_180044718
0x18004479c  test    r12, r12
0x18004479f  jz      loc_1800448DC
0x1800447a5  mov     rcx, r12; dwBytes
0x1800447a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800447ad  mov     rdx, rax
0x1800447b0  lea     rcx, [rbp+var_48]
0x1800447b4  call    ??4?$AutoVectorPtr@E@wmi@@QEAAAEAV01@PEAE@Z; wmi::AutoVectorPtr<uchar>::operator=(uchar *)
0x1800447b9  mov     r15, [rbp+var_48]
0x1800447bd  mov     rsi, r15
0x1800447c0  mov     rbx, [r13+0]
0x1800447c4  mov     rbx, [rbx]
0x1800447c7  xor     r10d, r10d
0x1800447ca  cmp     rbx, [r13+0]
0x1800447ce  jz      loc_1800448D8
0x1800447d4  mov     rax, [rbx+20h]
0x1800447d8  test    rax, rax
0x1800447db  jz      short loc_1800447E2
0x1800447dd  mov     rdx, [rax]
0x1800447e0  jmp     short loc_1800447E5
0x1800447e2  mov     rdx, r10
0x1800447e5  mov     rcx, r14
0x1800447e8  inc     rcx
0x1800447eb  cmp     [rdx+rcx*2], r10w
0x1800447f0  jnz     short loc_1800447E8
0x1800447f2  lea     r8, ds:2[rcx*2]; Size
0x1800447fa  test    rax, rax
0x1800447fd  jz      short loc_180044804
0x1800447ff  mov     rdx, [rax]
0x180044802  jmp     short loc_180044807
0x180044804  mov     rdx, r10; Src
0x180044807  mov     rcx, rsi; void *
0x18004480a  call    memcpy_0
0x18004480f  mov     rcx, [rbx+20h]
0x180044813  xor     r9d, r9d
0x180044816  test    rcx, rcx
0x180044819  jz      short loc_180044820
0x18004481b  mov     rcx, [rcx]
0x18004481e  jmp     short loc_180044823
0x180044820  mov     rcx, r9
0x180044823  mov     rax, r14
0x180044826  inc     rax
0x180044829  cmp     [rcx+rax*2], r9w
0x18004482e  jnz     short loc_180044826
0x180044830  lea     rsi, [rsi+rax*2]
0x180044834  add     rsi, 2
0x180044838  mov     rcx, [rbx+28h]
0x18004483c  test    rcx, rcx
0x18004483f  jz      short loc_180044846
0x180044841  mov     rdx, [rcx]
0x180044844  jmp     short loc_180044849
0x180044846  mov     rdx, r9
0x180044849  mov     rax, r14
0x18004484c  inc     rax
0x18004484f  cmp     [rdx+rax*2], r9w
0x180044854  jnz     short loc_18004484C
0x180044856  lea     r8, ds:2[rax*2]; Size
0x18004485e  test    rcx, rcx
0x180044861  jz      short loc_180044868
0x180044863  mov     rdx, [rcx]
0x180044866  jmp     short loc_18004486B
0x180044868  mov     rdx, r9; Src
0x18004486b  mov     rcx, rsi; void *
0x18004486e  call    memcpy_0
0x180044873  mov     rcx, [rbx+28h]
0x180044877  xor     r10d, r10d
0x18004487a  test    rcx, rcx
0x18004487d  jz      short loc_180044884
0x18004487f  mov     rcx, [rcx]
0x180044882  jmp     short loc_180044887
0x180044884  mov     rcx, r10
0x180044887  mov     rax, r14
0x18004488a  inc     rax
0x18004488d  cmp     [rcx+rax*2], r10w
0x180044892  jnz     short loc_18004488A
0x180044894  lea     rsi, [rsi+rax*2]
0x180044898  add     rsi, 2
0x18004489c  cmp     [rbx+19h], r10b
0x1800448a0  jnz     loc_1800447CA
0x1800448a6  mov     rcx, [rbx+10h]
0x1800448aa  cmp     [rcx+19h], r10b
0x1800448ae  jnz     short loc_1800448B7
0x1800448b0  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV_bstr_t@@PEAV?$list@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAV?$list@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_bstr_t const,std::list<_FILETIME> *>>>::_Min(std::_Tree_node<std::pair<_bstr_t const,std::list<_FILETIME> *>,void *> *)
0x1800448b5  jmp     short loc_1800448D0
0x1800448b7  mov     rax, [rbx+8]
0x1800448bb  jmp     short loc_1800448CA
0x1800448bd  cmp     rbx, [rax+10h]
0x1800448c1  jnz     short loc_1800448D0
0x1800448c3  mov     rbx, rax
0x1800448c6  mov     rax, [rax+8]
0x1800448ca  cmp     [rax+19h], r10b
0x1800448ce  jz      short loc_1800448BD
0x1800448d0  mov     rbx, rax
0x1800448d3  jmp     loc_1800447CA
0x1800448d8  mov     rbx, [rbp+var_40]
0x1800448dc  mov     rax, [rbp+var_38]
0x1800448e0  mov     rax, [rax+10h]
0x1800448e4  test    rax, rax
0x1800448e7  jz      short loc_1800448EE
0x1800448e9  mov     rcx, [rax]
0x1800448ec  jmp     short loc_1800448F1
0x1800448ee  mov     rcx, r10
0x1800448f1  inc     r14
0x1800448f4  cmp     [rcx+r14*2], r10w
0x1800448f9  jnz     short loc_1800448F1
0x1800448fb  lea     edx, ds:2[r14*2]
0x180044903  test    rax, rax
0x180044906  jz      short loc_18004490D
0x180044908  mov     rcx, [rax]
0x18004490b  jmp     short loc_180044910
0x18004490d  mov     rcx, r10
0x180044910  mov     [rbp+var_30], rcx
0x180044914  mov     dword ptr [rbp+var_28], edx
0x180044917  mov     dword ptr [rbp+var_28+4], r10d
0x18004491b  mov     qword ptr [rbp+var_28+8], r15
0x18004491f  mov     dword ptr [rbp+var_18], r12d
0x180044923  mov     dword ptr [rbp+var_18+4], r10d
0x180044927  lea     r9, [rbp+var_30]
0x18004492b  mov     r8d, 2
0x180044931  lea     rdx, UBPM_TRIGGER_EMULATOR_EVENT
0x180044938  mov     rcx, [rbx]
0x18004493b  call    cs:__imp_EtwEventWrite
0x180044941  test    eax, eax
0x180044943  jz      loc_1800446D1
0x180044949  jg      loc_1800446C8
0x18004494f  mov     edi, eax
0x180044951  jmp     loc_1800446D1
```
