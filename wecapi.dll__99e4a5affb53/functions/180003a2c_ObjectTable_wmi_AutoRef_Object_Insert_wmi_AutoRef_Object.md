# ObjectTable<wmi::AutoRef<Object>>::Insert(wmi::AutoRef<Object>)

- ea: `0x180003a2c`
- end: `0x180003c05`
- name: `?Insert@?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@QEAAKV?$AutoRef@VObject@@@wmi@@@Z`
- size: `473`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180005220`
- `0x1800054c0`
- `0x1800066c4`

## callees

- `0x180002b28`
- `0x180002de4`
- `0x180003604`
- `0x180003a2c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003a52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003a52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003bc1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003bc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ObjectTable<wmi::AutoRef<Object>>::Insert(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rcx
  unsigned int v7; // ebp
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  __int64 v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v16; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17; // [rsp+38h] [rbp-30h]
  __int64 v18; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v19; // [rsp+78h] [rbp+10h]
  struct _RTL_CRITICAL_SECTION *v20; // [rsp+80h] [rbp+18h]
  __int64 v21; // [rsp+88h] [rbp+20h]

  v19 = a2;
  v18 = a1;
  v20 = &g_objectTable;
  EnterCriticalSection(&g_objectTable);
  v4 = *((_QWORD *)&xmmword_180014A60 + 1);
  if ( !*((_QWORD *)&xmmword_180014A60 + 1) )
  {
    ObjectTable<wmi::AutoRef<Object>>::AddToFreeList(v3, (unsigned int)qword_180014A40, (unsigned int)dword_180014A70);
    v4 = *((_QWORD *)&xmmword_180014A60 + 1);
  }
  v5 = xmmword_180014A60;
  if ( qword_180014A48 )
    v6 = *(_QWORD *)qword_180014A48;
  else
    v6 = 0;
  v7 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 8)
                             + 8 * (((unsigned __int64)xmmword_180014A60 >> 2) & (*(_QWORD *)(v6 + 16) - 1LL)))
                 + 4 * (xmmword_180014A60 & 3));
  if ( v4 )
  {
    *((_QWORD *)&xmmword_180014A60 + 1) = v4 - 1;
    if ( v4 == 1 )
      *(_QWORD *)&xmmword_180014A60 = 0;
    else
      *(_QWORD *)&xmmword_180014A60 = xmmword_180014A60 + 1;
  }
  v8 = *(_QWORD *)(qword_180014A38 + 8);
  v9 = qword_180014A38;
  while ( !*(_BYTE *)(v8 + 25) )
  {
    if ( *(_DWORD *)(v8 + 32) >= v7 )
    {
      v9 = v8;
      v8 = *(_QWORD *)v8;
    }
    else
    {
      v8 = *(_QWORD *)(v8 + 16);
    }
  }
  if ( v9 == qword_180014A38 || v7 < *(_DWORD *)(v9 + 32) )
  {
    v16 = v7;
    v17 = 0;
    v21 = 0;
    v10 = std::_Tree_buy<std::pair<unsigned long const,wmi::AutoRef<Object>>>::_Buynode<std::pair<unsigned long,wmi::AutoRef<Object>>>(
            &qword_180014A38,
            &v16,
            v4,
            v5);
    std::_Tree<std::_Tmap_traits<unsigned long,wmi::AutoRef<Object>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,wmi::AutoRef<Object>>>,0>>::_Insert_hint<std::pair<unsigned long const,wmi::AutoRef<Object>> &,std::_Tree_node<std::pair<unsigned long const,wmi::AutoRef<Object>>,void *> *>(
      &qword_180014A38,
      &v18,
      v9,
      v10 + 32,
      v10);
    v9 = v18;
    v11 = (void (__fastcall ***)(_QWORD, __int64))v17;
    if ( v17 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 + 8), 0xFFFFFFFF) == 1 )
        (**v11)(v11, 1);
    }
  }
  v12 = *a2;
  if ( *a2 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  v13 = *(_QWORD *)(v9 + 40);
  if ( v13 && _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64, __int64, __int64))v13)(v13, 1, v4, v5);
  *(_QWORD *)(v9 + 40) = v12;
  LeaveCriticalSection(&g_objectTable);
  v14 = *a2;
  if ( *a2 && _InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v14)(v14, 1);
  *a2 = 0;
  return v7 + 1;
}

```

## disassembly

```asm
0x180003a2c  mov     rax, rsp
0x180003a2f  mov     [rax+10h], rdx
0x180003a33  mov     [rax+8], rcx
0x180003a37  push    rbx
0x180003a38  push    rbp
0x180003a39  push    rsi
0x180003a3a  push    rdi
0x180003a3b  push    r13
0x180003a3d  sub     rsp, 40h
0x180003a41  mov     rsi, rdx
0x180003a44  lea     r13, ?g_objectTable@@3V?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@A; ObjectTable<wmi::AutoRef<Object>> g_objectTable
0x180003a4b  mov     [rax+18h], r13
0x180003a4f  mov     rcx, r13; lpCriticalSection
0x180003a52  call    cs:__imp_EnterCriticalSection
0x180003a58  nop
0x180003a59  mov     r8, qword ptr cs:xmmword_180014A60+8
0x180003a60  test    r8, r8
0x180003a63  jnz     short loc_180003A7E
0x180003a65  mov     r8d, cs:dword_180014A70
0x180003a6c  mov     edx, dword ptr cs:qword_180014A40
0x180003a72  call    ?AddToFreeList@?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@AEAAXKK@Z; ObjectTable<wmi::AutoRef<Object>>::AddToFreeList(ulong,ulong)
0x180003a77  mov     r8, qword ptr cs:xmmword_180014A60+8
0x180003a7e  mov     r9, qword ptr cs:xmmword_180014A60
0x180003a85  mov     rax, cs:qword_180014A48
0x180003a8c  test    rax, rax
0x180003a8f  jnz     short loc_180003A95
0x180003a91  xor     ecx, ecx
0x180003a93  jmp     short loc_180003A98
0x180003a95  mov     rcx, [rax]
0x180003a98  mov     rdx, [rcx+10h]
0x180003a9c  dec     rdx
0x180003a9f  mov     rax, r9
0x180003aa2  shr     rax, 2
0x180003aa6  and     rdx, rax
0x180003aa9  mov     rax, [rcx+8]
0x180003aad  mov     rcx, r9
0x180003ab0  and     ecx, 3
0x180003ab3  mov     rax, [rax+rdx*8]
0x180003ab7  mov     ebp, [rax+rcx*4]
0x180003aba  test    r8, r8
0x180003abd  jz      short loc_180003AE3
0x180003abf  lea     rax, [r8-1]
0x180003ac3  mov     qword ptr cs:xmmword_180014A60+8, rax
0x180003aca  test    rax, rax
0x180003acd  jnz     short loc_180003AD8
0x180003acf  mov     qword ptr cs:xmmword_180014A60, rax
0x180003ad6  jmp     short loc_180003AE3
0x180003ad8  lea     rax, [r9+1]
0x180003adc  mov     qword ptr cs:xmmword_180014A60, rax
0x180003ae3  mov     rcx, cs:qword_180014A38
0x180003aea  mov     rax, [rcx+8]
0x180003aee  mov     rbx, rcx
0x180003af1  jmp     short loc_180003B04
0x180003af3  cmp     [rax+20h], ebp
0x180003af6  jnb     short loc_180003AFE
0x180003af8  mov     rax, [rax+10h]
0x180003afc  jmp     short loc_180003B04
0x180003afe  mov     rbx, rax
0x180003b01  mov     rax, [rax]
0x180003b04  cmp     byte ptr [rax+19h], 0
0x180003b08  jz      short loc_180003AF3
0x180003b0a  cmp     rbx, rcx
0x180003b0d  jz      short loc_180003B14
0x180003b0f  cmp     ebp, [rbx+20h]
0x180003b12  jnb     short loc_180003B88
0x180003b14  mov     [rsp+68h+var_38], ebp
0x180003b18  mov     [rsp+68h+var_30], 0
0x180003b21  mov     [rsp+68h+arg_18], 0
0x180003b2d  lea     rdx, [rsp+68h+var_38]
0x180003b32  lea     rcx, qword_180014A38
0x180003b39  call    ??$_Buynode@U?$pair@KV?$AutoRef@VObject@@@wmi@@@std@@@?$_Tree_buy@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@V?$allocator@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@PEAX@1@$$QEAU?$pair@KV?$AutoRef@VObject@@@wmi@@@1@@Z; std::_Tree_buy<std::pair<ulong const,wmi::AutoRef<Object>>>::_Buynode<std::pair<ulong,wmi::AutoRef<Object>>>(std::pair<ulong,wmi::AutoRef<Object>> &&)
0x180003b3e  lea     r9, [rax+20h]
0x180003b42  mov     [rsp+68h+var_48], rax
0x180003b47  mov     r8, rbx
0x180003b4a  lea     rdx, [rsp+68h+arg_0]
0x180003b4f  lea     rcx, qword_180014A38
0x180003b56  call    ??$_Insert_hint@AEAU?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@PEAU?$_Tree_node@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@KV?$AutoRef@VObject@@@wmi@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@@4@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@@std@@@std@@@1@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@@std@@@std@@@1@AEAU?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$AutoRef@VObject@@@wmi@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ulong,wmi::AutoRef<Object>,std::less<ulong>,std::allocator<std::pair<ulong const,wmi::AutoRef<Object>>>,0>>::_Insert_hint<std::pair<ulong const,wmi::AutoRef<Object>> &,std::_Tree_node<std::pair<ulong const,wmi::AutoRef<Object>>,void *> *>(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,wmi::AutoRef<Object>>>>>,std::pair<ulong const,wmi::AutoRef<Object>> &,std::_Tree_node<std::pair<ulong const,wmi::AutoRef<Object>>,void *> *)
0x180003b5b  mov     rbx, [rsp+68h+arg_0]
0x180003b60  mov     rcx, [rsp+68h+var_30]
0x180003b65  test    rcx, rcx
0x180003b68  jz      short loc_180003B88
0x180003b6a  or      eax, 0FFFFFFFFh
0x180003b6d  lock xadd [rcx+8], eax
0x180003b72  cmp     eax, 1
0x180003b75  jnz     short loc_180003B88
0x180003b77  mov     rax, [rcx]
0x180003b7a  mov     edx, 1
0x180003b7f  mov     rax, [rax]
0x180003b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b87  nop
0x180003b88  mov     rdi, [rsi]
0x180003b8b  test    rdi, rdi
0x180003b8e  jz      short loc_180003B94
0x180003b90  lock inc dword ptr [rdi+8]
0x180003b94  mov     rcx, [rbx+28h]
0x180003b98  test    rcx, rcx
0x180003b9b  jz      short loc_180003BBA
0x180003b9d  or      eax, 0FFFFFFFFh
0x180003ba0  lock xadd [rcx+8], eax
0x180003ba5  cmp     eax, 1
0x180003ba8  jnz     short loc_180003BBA
0x180003baa  mov     rax, [rcx]
0x180003bad  mov     edx, 1
0x180003bb2  mov     rax, [rax]
0x180003bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bba  mov     [rbx+28h], rdi
0x180003bbe  mov     rcx, r13; lpCriticalSection
0x180003bc1  call    cs:__imp_LeaveCriticalSection
0x180003bc7  nop
0x180003bc8  mov     rcx, [rsi]
0x180003bcb  test    rcx, rcx
0x180003bce  jz      short loc_180003BF0
0x180003bd0  or      r8d, 0FFFFFFFFh
0x180003bd4  lock xadd [rcx+8], r8d
0x180003bda  cmp     r8d, 1
0x180003bde  jnz     short loc_180003BF0
0x180003be0  mov     r8, [rcx]
0x180003be3  mov     edx, 1
0x180003be8  mov     rax, [r8]
0x180003beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bf0  mov     qword ptr [rsi], 0
0x180003bf7  lea     eax, [rbp+1]
0x180003bfa  add     rsp, 40h
0x180003bfe  pop     r13
0x180003c00  pop     rdi
0x180003c01  pop     rsi
0x180003c02  pop     rbp
0x180003c03  pop     rbx
0x180003c04  retn
```
