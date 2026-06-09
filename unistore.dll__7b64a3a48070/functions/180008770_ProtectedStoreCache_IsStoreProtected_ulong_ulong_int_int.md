# ProtectedStoreCache::IsStoreProtected(ulong,ulong,int *,int *)

- ea: `0x180008770`
- end: `0x180008ae1`
- name: `?IsStoreProtected@ProtectedStoreCache@@YAJKKPEAH0@Z`
- size: `881`
- prototype: `__int64 __fastcall(ProtectedStoreCache *__hidden this, unsigned int, unsigned int, int *, int *)`
- caller_count: `4`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006b20`
- `0x180006ce0`
- `0x180008af0`
- `0x180015e00`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180008770`
- `0x18002c9f0`
- `0x18007d2ec`
- `0x18007d2fc`
- `0x18007d8d4`
- `0x18007d99c`
- `0x18007da48`
- `0x18008131c`
- `0x1800c50b6`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800087e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008924`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800087e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008924`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008833`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008886`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008962`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008833`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008886`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008962`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008a18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800089b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800089d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800089b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800089d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a27`

## string_xrefs

- `0x1800089bf`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800089fe`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180008a6a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180008a91`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall ProtectedStoreCache::IsStoreProtected(ProtectedStoreCache *this, int a2, int *a3, int *a4)
{
  int v4; // r12d
  unsigned int v7; // ebx
  __int64 *v8; // rcx
  __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _DWORD *v12; // rax
  _QWORD *v14; // rax
  int v15; // r15d
  int v16; // r13d
  int Instance; // eax
  unsigned int v18; // edi
  struct IDBManager *v19; // rdi
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  HLOCAL v24; // rbx
  char *v25; // rcx
  _QWORD *v26; // rax
  const wchar_t *v27; // rcx
  __int64 v28; // [rsp+30h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-38h] BYREF
  __int128 v30; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v31[16]; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v32; // [rsp+A0h] [rbp+30h] BYREF
  int v33; // [rsp+B0h] [rbp+40h] BYREF
  struct IDBManager *v34; // [rsp+B8h] [rbp+48h] BYREF

  v32 = (unsigned int)this;
  v4 = 0;
  *a3 = 0;
  v7 = (unsigned int)this;
  if ( a4 )
    *a4 = 0;
  if ( (_DWORD)this == -1 || (_DWORD)this == 2147483640 || a2 == -1 || (dword_18010A17C[24 * a2] & 0x100000) == 0 )
    return 0;
  EnterCriticalSection(&stru_18010C338);
  utl::_HashTable<unsigned long,utl::pair<unsigned long const,_ProtectedCacheProps>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,_ProtectedCacheProps>>,0>::find<void>(
    v8,
    (__int64)&v34,
    &v32);
  v10 = (_QWORD *)utl::_HashTable<unsigned long,utl::pair<unsigned long const,_ProtectedCacheProps>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,_ProtectedCacheProps>>,0>::end(
                    v9,
                    &v30);
  if ( utl::operator!=<utl::_HashNode<utl::pair<unsigned long const,_ProtectedCacheProps>>,utl::pair<unsigned long const,_ProtectedCacheProps>>(
         &v34,
         v10) )
  {
    v12 = (_DWORD *)utl::_DlistIt<utl::_HashNode<utl::pair<unsigned long const,_ProtectedCacheProps>>,utl::pair<unsigned long const,_ProtectedCacheProps>>::operator->(&v34);
    if ( !v12[4] )
    {
      *a3 = v12[1];
      if ( a4 )
        *a4 = v12[2];
      LeaveCriticalSection(&stru_18010C338);
      return 0;
    }
  }
  v14 = (_QWORD *)utl::_HashTable<unsigned long,utl::pair<unsigned long const,_ProtectedCacheProps>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,_ProtectedCacheProps>>,0>::end(
                    v11,
                    &v30);
  v15 = 1;
  if ( !utl::operator!=<utl::_HashNode<utl::pair<unsigned long const,_ProtectedCacheProps>>,utl::pair<unsigned long const,_ProtectedCacheProps>>(
          &v34,
          v14)
    || (v16 = 1,
        !*(_DWORD *)(utl::_DlistIt<utl::_HashNode<utl::pair<unsigned long const,_ProtectedCacheProps>>,utl::pair<unsigned long const,_ProtectedCacheProps>>::operator->(&v34)
                   + 16)) )
  {
    v16 = 0;
  }
  LeaveCriticalSection(&stru_18010C338);
  v34 = 0;
  Instance = DBManager::GetInstance(&v34);
  v18 = Instance;
  if ( Instance < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)Instance,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      613);
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v34);
    return v18;
  }
  else
  {
    v19 = v34;
    v28 = 0;
    v20 = (*(__int64 (__fastcall **)(struct IDBManager *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v34 + 56LL))(
            v34,
            0,
            v7,
            &v28);
    v21 = v20;
    if ( v20 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v20,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        616);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v28);
      ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v34);
      return v21;
    }
    else
    {
      hMem = 0;
      v33 = 874577951;
      v22 = (*(__int64 (__fastcall **)(__int64, __int64, int *, HLOCAL *, _QWORD))(*(_QWORD *)v28 + 40LL))(
              v28,
              1,
              &v33,
              &hMem,
              0);
      v23 = v22;
      if ( v22 < 0 )
      {
        Log_UnistoreHREvent_0(
          (unsigned int)v22,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          620);
        if ( hMem )
          LocalFree(hMem);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v28);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v34);
        return v23;
      }
      else
      {
        v24 = hMem;
        if ( (*((_WORD *)hMem + 3) & 0x300) != 0 || (v27 = (const wchar_t *)*((_QWORD *)hMem + 1)) == 0 )
        {
          v15 = 0;
        }
        else if ( !wcscmp_0(v27, L"{E2CAA6FC-5124-48F5-806B-8E64ABCDEBA1}") )
        {
          v4 = 1;
        }
        if ( v16 )
          goto LABEL_23;
        EnterCriticalSection(&stru_18010C338);
        v30 = __PAIR64__(v4, v15);
        v26 = (_QWORD *)utl::_HashTable<unsigned long,utl::pair<unsigned long const,_ProtectedCacheProps>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,_ProtectedCacheProps>>,0>::emplace<unsigned long &,_ProtectedCacheProps &,0>(
                          v25,
                          (__int64)v31,
                          &v32,
                          &v30);
        if ( utl::operator!=<utl::_HashNode<utl::pair<unsigned long const,_ProtectedCacheProps>>,utl::pair<unsigned long const,_ProtectedCacheProps>>(v26) )
        {
          LeaveCriticalSection(&stru_18010C338);
          v24 = hMem;
LABEL_23:
          *a3 = v15;
          if ( a4 )
            *a4 = v4;
          if ( v24 )
            LocalFree(v24);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( v19 )
            (*(void (__fastcall **)(struct IDBManager *))(*(_QWORD *)v19 + 16LL))(v19);
          return 0;
        }
        Log_UnistoreHREvent_0(
          2147942414LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          631);
        LeaveCriticalSection(&stru_18010C338);
        if ( hMem )
          LocalFree(hMem);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v28);
        ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(&v34);
        return 2147942414LL;
      }
    }
  }
}

```

## disassembly

```asm
0x180008770  mov     [rsp-28h+arg_0], ecx
0x180008774  push    rbp
0x180008775  push    rbx
0x180008776  push    rsi
0x180008777  push    r12
0x180008779  push    r14
0x18000877b  mov     rbp, rsp
0x18000877e  sub     rsp, 70h
0x180008782  xor     r12d, r12d
0x180008785  mov     rsi, r9
0x180008788  mov     [r8], r12d
0x18000878b  mov     r14, r8
0x18000878e  mov     ebx, ecx
0x180008790  test    r9, r9
0x180008793  jz      short loc_180008798
0x180008795  mov     [r9], r12d
0x180008798  mov     [rsp+70h+arg_8], rdi
0x1800087a0  mov     [rsp+70h+var_8], r13
0x1800087a5  mov     [rsp+70h+var_10], r15
0x1800087aa  cmp     ebx, 0FFFFFFFFh
0x1800087ad  jz      loc_180008839
0x1800087b3  cmp     ebx, 7FFFFFF8h
0x1800087b9  jz      short loc_180008839
0x1800087bb  cmp     edx, 0FFFFFFFFh
0x1800087be  jz      short loc_180008839
0x1800087c0  mov     eax, edx
0x1800087c2  lea     rcx, [rax+rax*2]
0x1800087c6  shl     rcx, 5
0x1800087ca  lea     rax, dword_18010A17C
0x1800087d1  test    dword ptr [rcx+rax], 100000h
0x1800087d8  jz      short loc_180008839
0x1800087da  lea     rcx, stru_18010C338; lpCriticalSection
0x1800087e1  call    cs:__imp_EnterCriticalSection
0x1800087e7  lea     r8, [rbp+arg_0]
0x1800087eb  lea     rdx, [rbp+arg_18]
0x1800087ef  call    ??$find@X@?$_HashTable@KU?$pair@$$CBKU_ProtectedCacheProps@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@2@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@utl@@U?$pair@$$CBKU_ProtectedCacheProps@@@2@@1@AEBK@Z; utl::_HashTable<ulong,utl::pair<ulong const,_ProtectedCacheProps>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,_ProtectedCacheProps>>,0>::find<void>(ulong const &)
0x1800087f4  lea     rdx, [rbp+var_30]
0x1800087f8  call    ?end@?$_HashTable@KU?$pair@$$CBKU_ProtectedCacheProps@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@2@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@utl@@U?$pair@$$CBKU_ProtectedCacheProps@@@2@@2@XZ; utl::_HashTable<ulong,utl::pair<ulong const,_ProtectedCacheProps>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,_ProtectedCacheProps>>,0>::end(void)
0x1800087fd  mov     rdx, rax
0x180008800  lea     rcx, [rbp+arg_18]
0x180008804  call    ??$?9U?$_HashNode@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@utl@@U?$pair@$$CBKU_ProtectedCacheProps@@@1@@utl@@YA_NAEBV?$_DlistConstIt@U?$_HashNode@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@utl@@U?$pair@$$CBKU_ProtectedCacheProps@@@2@@0@0@Z; utl::operator!=<utl::_HashNode<utl::pair<ulong const,_ProtectedCacheProps>>,utl::pair<ulong const,_ProtectedCacheProps>>(utl::_DlistConstIt<utl::_HashNode<utl::pair<ulong const,_ProtectedCacheProps>>,utl::pair<ulong const,_ProtectedCacheProps>> const &,utl::_DlistConstIt<utl::_HashNode<utl::pair<ulong const,_ProtectedCacheProps>>,utl::pair<ulong const,_ProtectedCacheProps>> const &)
0x180008809  test    al, al
0x18000880b  jz      short loc_180008859
0x18000880d  lea     rcx, [rbp+arg_18]
0x180008811  call    ??C?$_DlistIt@U?$_HashNode@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@utl@@U?$pair@$$CBKU_ProtectedCacheProps@@@2@@utl@@QEBAPEAU?$pair@$$CBKU_ProtectedCacheProps@@@1@XZ; utl::_DlistIt<utl::_HashNode<utl::pair<ulong const,_ProtectedCacheProps>>,utl::pair<ulong const,_ProtectedCacheProps>>::operator->(void)
0x180008816  cmp     [rax+10h], r12d
0x18000881a  jnz     short loc_180008859
0x18000881c  mov     edx, [rax+4]
0x18000881f  mov     [r14], edx
0x180008822  test    rsi, rsi
0x180008825  jz      short loc_18000882C
0x180008827  mov     eax, [rax+8]
0x18000882a  mov     [rsi], eax
0x18000882c  lea     rcx, stru_18010C338; lpCriticalSection
0x180008833  call    cs:__imp_LeaveCriticalSection
0x180008839  xor     eax, eax
0x18000883b  mov     r15, [rsp+70h+var_10]
0x180008840  mov     r13, [rsp+70h+var_8]
0x180008845  mov     rdi, [rsp+70h+arg_8]
0x18000884d  add     rsp, 70h
0x180008851  pop     r14
0x180008853  pop     r12
0x180008855  pop     rsi
0x180008856  pop     rbx
0x180008857  pop     rbp
0x180008858  retn
0x180008859  lea     rdx, [rbp+var_30]
0x18000885d  call    ?end@?$_HashTable@KU?$pair@$$CBKU_ProtectedCacheProps@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@2@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@utl@@U?$pair@$$CBKU_ProtectedCacheProps@@@2@@2@XZ; utl::_HashTable<ulong,utl::pair<ulong const,_ProtectedCacheProps>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,_ProtectedCacheProps>>,0>::end(void)
0x180008862  mov     rdx, rax
0x180008865  lea     rcx, [rbp+arg_18]
0x180008869  call    ??$?9U?$_HashNode@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@utl@@U?$pair@$$CBKU_ProtectedCacheProps@@@1@@utl@@YA_NAEBV?$_DlistConstIt@U?$_HashNode@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@utl@@U?$pair@$$CBKU_ProtectedCacheProps@@@2@@0@0@Z; utl::operator!=<utl::_HashNode<utl::pair<ulong const,_ProtectedCacheProps>>,utl::pair<ulong const,_ProtectedCacheProps>>(utl::_DlistConstIt<utl::_HashNode<utl::pair<ulong const,_ProtectedCacheProps>>,utl::pair<ulong const,_ProtectedCacheProps>> const &,utl::_DlistConstIt<utl::_HashNode<utl::pair<ulong const,_ProtectedCacheProps>>,utl::pair<ulong const,_ProtectedCacheProps>> const &)
0x18000886e  mov     r15d, 1
0x180008874  test    al, al
0x180008876  jnz     loc_180008A49
0x18000887c  mov     r13d, r12d
0x18000887f  lea     rcx, stru_18010C338; lpCriticalSection
0x180008886  call    cs:__imp_LeaveCriticalSection
0x18000888c  lea     rcx, [rbp+arg_18]; struct IDBManager **
0x180008890  mov     [rbp+arg_18], r12
0x180008894  call    ?GetInstance@DBManager@@SAJPEAPEAVIDBManager@@@Z; DBManager::GetInstance(IDBManager * *)
0x180008899  mov     edi, eax
0x18000889b  test    eax, eax
0x18000889d  js      loc_180008A64
0x1800088a3  mov     rdi, [rbp+arg_18]
0x1800088a7  lea     r9, [rbp+var_40]
0x1800088ab  mov     [rbp+var_40], r12
0x1800088af  mov     r8d, ebx
0x1800088b2  xor     edx, edx
0x1800088b4  mov     rcx, rdi
0x1800088b7  mov     rax, [rdi]
0x1800088ba  mov     rax, [rax+38h]
0x1800088be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088c3  mov     ebx, eax
0x1800088c5  mov     edx, r15d
0x1800088c8  test    eax, eax
0x1800088ca  js      loc_180008A8B
0x1800088d0  mov     rcx, [rbp+var_40]
0x1800088d4  lea     r9, [rbp+hMem]
0x1800088d8  mov     [rbp+hMem], r12
0x1800088dc  lea     r8, [rbp+arg_10]
0x1800088e0  mov     [rbp+arg_10], 3421001Fh
0x1800088e7  mov     [rsp+70h+var_50], r12
0x1800088ec  mov     rax, [rcx]
0x1800088ef  mov     rax, [rax+28h]
0x1800088f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088f8  mov     ebx, eax
0x1800088fa  test    eax, eax
0x1800088fc  js      loc_1800089B9
0x180008902  mov     rbx, [rbp+hMem]
0x180008906  mov     eax, 300h
0x18000890b  test    [rbx+6], ax
0x18000890f  jz      loc_180008AB8
0x180008915  mov     r15d, r12d
0x180008918  test    r13d, r13d
0x18000891b  jnz     short loc_18000896C
0x18000891d  lea     rcx, stru_18010C338; lpCriticalSection
0x180008924  call    cs:__imp_EnterCriticalSection
0x18000892a  lea     r9, [rbp+var_30]
0x18000892e  mov     [rbp+var_28], 0
0x180008936  lea     r8, [rbp+arg_0]
0x18000893a  mov     [rbp+var_30], r15d
0x18000893e  lea     rdx, [rbp+var_20]
0x180008942  mov     [rbp+var_2C], r12d
0x180008946  call    ??$emplace@AEAKAEAU_ProtectedCacheProps@@$0A@@?$_HashTable@KU?$pair@$$CBKU_ProtectedCacheProps@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@utl@@U?$pair@$$CBKU_ProtectedCacheProps@@@2@@utl@@_N@1@AEAKAEAU_ProtectedCacheProps@@@Z; utl::_HashTable<ulong,utl::pair<ulong const,_ProtectedCacheProps>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,_ProtectedCacheProps>>,0>::emplace<ulong &,_ProtectedCacheProps &,0>(ulong &,_ProtectedCacheProps &)
0x18000894b  mov     rcx, rax
0x18000894e  call    ??$?9U?$_HashNode@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@utl@@U?$pair@$$CBKU_ProtectedCacheProps@@@1@@utl@@YA_NAEBV?$_DlistConstIt@U?$_HashNode@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@utl@@U?$pair@$$CBKU_ProtectedCacheProps@@@2@@0@$$T@Z; utl::operator!=<utl::_HashNode<utl::pair<ulong const,_ProtectedCacheProps>>,utl::pair<ulong const,_ProtectedCacheProps>>(utl::_DlistConstIt<utl::_HashNode<utl::pair<ulong const,_ProtectedCacheProps>>,utl::pair<ulong const,_ProtectedCacheProps>> const &,std::nullptr_t)
0x180008953  test    al, al
0x180008955  jz      loc_1800089F8
0x18000895b  lea     rcx, stru_18010C338; lpCriticalSection
0x180008962  call    cs:__imp_LeaveCriticalSection
0x180008968  mov     rbx, [rbp+hMem]
0x18000896c  mov     [r14], r15d
0x18000896f  test    rsi, rsi
0x180008972  jz      short loc_180008977
0x180008974  mov     [rsi], r12d
0x180008977  test    rbx, rbx
0x18000897a  jnz     short loc_1800089AE
0x18000897c  mov     rcx, [rbp+var_40]
0x180008980  test    rcx, rcx
0x180008983  jz      short loc_180008991
0x180008985  mov     rax, [rcx]
0x180008988  mov     rax, [rax+10h]
0x18000898c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008991  test    rdi, rdi
0x180008994  jz      loc_180008839
0x18000899a  mov     rax, [rdi]
0x18000899d  mov     rcx, rdi
0x1800089a0  mov     rax, [rax+10h]
0x1800089a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089a9  jmp     loc_180008839
0x1800089ae  mov     rcx, rbx; hMem
0x1800089b1  call    cs:__imp_LocalFree
0x1800089b7  jmp     short loc_18000897C
0x1800089b9  mov     r9d, 26Ch
0x1800089bf  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800089c6  mov     edx, r15d
0x1800089c9  mov     ecx, ebx
0x1800089cb  call    Log_UnistoreHREvent_0
0x1800089d0  mov     rcx, [rbp+hMem]; hMem
0x1800089d4  test    rcx, rcx
0x1800089d7  jz      short loc_1800089DF
0x1800089d9  call    cs:__imp_LocalFree
0x1800089df  lea     rcx, [rbp+var_40]; void *
0x1800089e3  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800089e8  lea     rcx, [rbp+arg_18]; void *
0x1800089ec  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800089f1  mov     eax, ebx
0x1800089f3  jmp     loc_18000883B
0x1800089f8  mov     r9d, 277h
0x1800089fe  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008a05  xor     edx, edx
0x180008a07  mov     ecx, 8007000Eh
0x180008a0c  call    Log_UnistoreHREvent_0
0x180008a11  lea     rcx, stru_18010C338; lpCriticalSection
0x180008a18  call    cs:__imp_LeaveCriticalSection
0x180008a1e  mov     rcx, [rbp+hMem]; hMem
0x180008a22  test    rcx, rcx
0x180008a25  jz      short loc_180008A2D
0x180008a27  call    cs:__imp_LocalFree
0x180008a2d  lea     rcx, [rbp+var_40]; void *
0x180008a31  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180008a36  lea     rcx, [rbp+arg_18]; void *
0x180008a3a  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180008a3f  mov     eax, 8007000Eh
0x180008a44  jmp     loc_18000883B
0x180008a49  lea     rcx, [rbp+arg_18]
0x180008a4d  call    ??C?$_DlistIt@U?$_HashNode@U?$pair@$$CBKU_ProtectedCacheProps@@@utl@@@utl@@U?$pair@$$CBKU_ProtectedCacheProps@@@2@@utl@@QEBAPEAU?$pair@$$CBKU_ProtectedCacheProps@@@1@XZ; utl::_DlistIt<utl::_HashNode<utl::pair<ulong const,_ProtectedCacheProps>>,utl::pair<ulong const,_ProtectedCacheProps>>::operator->(void)
0x180008a52  mov     r13d, r15d
0x180008a55  cmp     [rax+10h], r12d
0x180008a59  jnz     loc_18000887F
0x180008a5f  jmp     loc_18000887C
0x180008a64  mov     r9d, 265h
0x180008a6a  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008a71  mov     edx, r15d
0x180008a74  mov     ecx, edi
0x180008a76  call    Log_UnistoreHREvent_0
0x180008a7b  lea     rcx, [rbp+arg_18]; void *
0x180008a7f  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180008a84  mov     eax, edi
0x180008a86  jmp     loc_18000883B
0x180008a8b  mov     r9d, 268h
0x180008a91  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008a98  mov     ecx, ebx
0x180008a9a  call    Log_UnistoreHREvent_0
0x180008a9f  lea     rcx, [rbp+var_40]; void *
0x180008aa3  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180008aa8  lea     rcx, [rbp+arg_18]; void *
0x180008aac  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x180008ab1  mov     eax, ebx
0x180008ab3  jmp     loc_18000883B
0x180008ab8  mov     rcx, [rbx+8]; String1
0x180008abc  test    rcx, rcx
0x180008abf  jz      loc_180008915
0x180008ac5  lea     rdx, aE2caa6fc512448; "{E2CAA6FC-5124-48F5-806B-8E64ABCDEBA1}"
0x180008acc  call    wcscmp_0
0x180008ad1  test    eax, eax
0x180008ad3  jnz     loc_180008918
0x180008ad9  mov     r12d, r15d
0x180008adc  jmp     loc_180008918
```
