# CProtocolHandler::Terminate(void)

- ea: `0x1800340ec`
- end: `0x18003436e`
- name: `?Terminate@CProtocolHandler@@QEAAKXZ`
- size: `642`
- prototype: `unsigned int __fastcall(CProtocolHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000da34`

## callees

- `0x18001de04`
- `0x180024550`
- `0x180033cd0`
- `0x1800340ec`
- `0x1800343f8`
- `0x1800351fc`
- `0x1800357f0`

## import_xrefs

- `ntdll!NtClose` at `0x180034344`
- `ntdll!NtClose` at `0x180034344`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800342c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800341d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800341d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800341ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800342b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800341ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800342b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034110`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034110`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003431d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034304`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003431d`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180034258`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180034258`

## pseudocode

```c
__int64 __fastcall CProtocolHandler::Terminate(CProtocolHandler *this)
{
  CProtocolHandler *v1; // rbx
  DWORD v2; // edi
  _QWORD *v3; // r14
  CClusterConnection **v4; // rax
  CClusterConnection *v5; // rsi
  _QWORD *v6; // rsi
  CClusterConnection **v7; // rax
  CClusterConnection *v8; // rbp
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  DWORD LastError; // eax
  void *v11; // rcx
  DWORD v12; // eax
  void *v13; // rcx
  DWORD v14; // eax
  void *v15; // rcx
  CThreadPool *v16; // rcx
  void *v17; // rcx
  CProtocolHandler *v19; // [rsp+40h] [rbp+8h] BYREF

  v19 = this;
  v1 = WitnessProtocolHandler;
  v2 = 0;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)WitnessProtocolHandler + 10));
  v3 = (_QWORD *)((char *)v1 + 24);
  v4 = (CClusterConnection **)**((_QWORD **)v1 + 3);
  v19 = (CProtocolHandler *)v4;
  while ( v4 != (CClusterConnection **)*v3 )
  {
    v5 = v4[8];
    if ( !CClusterConnection::ReleaseRegisterReference(v5) )
      CClusterConnection::Terminate(v5);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>::operator++(&v19);
    v4 = (CClusterConnection **)v19;
  }
  v6 = (_QWORD *)((char *)v1 + 40);
  v7 = (CClusterConnection **)**((_QWORD **)v1 + 5);
  v19 = (CProtocolHandler *)v7;
  while ( v7 != (CClusterConnection **)*v6 )
  {
    v8 = v7[8];
    if ( !CClusterConnection::ReleaseRegisterReference(v8) )
      CClusterConnection::Terminate(v8);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>::operator++(&v19);
    v7 = (CClusterConnection **)v19;
  }
  std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(
    (char *)v1 + 8,
    **((_QWORD **)v1 + 1),
    *((_QWORD *)v1 + 1));
  std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(
    (char *)v1 + 24,
    *(_QWORD *)*v3,
    *v3);
  std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(
    (char *)v1 + 40,
    *(_QWORD *)*v6,
    *v6);
  v9 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v1 + 10);
  *((_DWORD *)v1 + 32) = 0;
  LeaveCriticalSection(v9);
  if ( WaitForSingleObject(*((HANDLE *)v1 + 17), 0xFFFFFFFF) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
        25,
        &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids,
        LastError);
    }
  }
  v11 = (void *)*((_QWORD *)v1 + 8);
  if ( v11 != (void *)-1LL && !PostQueuedCompletionStatus(v11, 0, 4u, 0) )
  {
    v12 = GetLastError();
    v2 = v12;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 26, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v12);
    }
  }
  v13 = (void *)*((_QWORD *)v1 + 9);
  if ( v13 != (void *)-1LL )
  {
    if ( WaitForSingleObject(v13, 0x2710u) )
    {
      v14 = GetLastError();
      v2 = v14;
      if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 27, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v14);
      }
    }
    CloseHandle(*((HANDLE *)v1 + 9));
    *((_QWORD *)v1 + 9) = -1;
  }
  v15 = (void *)*((_QWORD *)v1 + 8);
  if ( v15 != (void *)-1LL )
  {
    CloseHandle(v15);
    *((_QWORD *)v1 + 8) = -1;
  }
  v16 = (CThreadPool *)*((_QWORD *)v1 + 7);
  if ( v16 )
    CThreadPool::Close(v16);
  v17 = (void *)*((_QWORD *)v1 + 11);
  if ( v17 )
  {
    NtClose(v17);
    *((_QWORD *)v1 + 11) = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1800340ec  mov     [rsp+arg_8], rbx
0x1800340f1  mov     [rsp+arg_10], rbp
0x1800340f6  mov     [rsp+arg_0], rcx
0x1800340fb  push    rsi
0x1800340fc  push    rdi
0x1800340fd  push    r14
0x1800340ff  sub     rsp, 20h
0x180034103  mov     rbx, cs:?WitnessProtocolHandler@@3PEAVCProtocolHandler@@EA; CProtocolHandler * WitnessProtocolHandler
0x18003410a  xor     edi, edi
0x18003410c  mov     rcx, [rbx+50h]; lpCriticalSection
0x180034110  call    cs:__imp_EnterCriticalSection
0x180034117  nop     dword ptr [rax+rax+00h]
0x18003411c  lea     r14, [rbx+18h]
0x180034120  mov     rax, [r14]
0x180034123  mov     rax, [rax]
0x180034126  mov     [rsp+38h+arg_0], rax
0x18003412b  cmp     rax, [r14]
0x18003412e  jz      short loc_180034159
0x180034130  mov     rsi, [rax+40h]
0x180034134  mov     rcx, rsi; this
0x180034137  call    ?ReleaseRegisterReference@CClusterConnection@@QEAAKXZ; CClusterConnection::ReleaseRegisterReference(void)
0x18003413c  test    eax, eax
0x18003413e  jnz     short loc_180034148
0x180034140  mov     rcx, rsi; this
0x180034143  call    ?Terminate@CClusterConnection@@QEAAXXZ; CClusterConnection::Terminate(void)
0x180034148  lea     rcx, [rsp+38h+arg_0]
0x18003414d  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>::operator++(void)
0x180034152  mov     rax, [rsp+38h+arg_0]
0x180034157  jmp     short loc_18003412B
0x180034159  lea     rsi, [rbx+28h]
0x18003415d  mov     rax, [rsi]
0x180034160  mov     rax, [rax]
0x180034163  mov     [rsp+38h+arg_0], rax
0x180034168  cmp     rax, [rsi]
0x18003416b  jz      short loc_180034196
0x18003416d  mov     rbp, [rax+40h]
0x180034171  mov     rcx, rbp; this
0x180034174  call    ?ReleaseRegisterReference@CClusterConnection@@QEAAKXZ; CClusterConnection::ReleaseRegisterReference(void)
0x180034179  test    eax, eax
0x18003417b  jnz     short loc_180034185
0x18003417d  mov     rcx, rbp; this
0x180034180  call    ?Terminate@CClusterConnection@@QEAAXXZ; CClusterConnection::Terminate(void)
0x180034185  lea     rcx, [rsp+38h+arg_0]
0x18003418a  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>::operator++(void)
0x18003418f  mov     rax, [rsp+38h+arg_0]
0x180034194  jmp     short loc_180034168
0x180034196  lea     rcx, [rbx+8]
0x18003419a  mov     rdx, [rcx]
0x18003419d  mov     r8, rdx
0x1800341a0  mov     rdx, [rdx]
0x1800341a3  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>)
0x1800341a8  mov     rdx, [r14]
0x1800341ab  mov     rcx, r14
0x1800341ae  mov     r8, rdx
0x1800341b1  mov     rdx, [rdx]
0x1800341b4  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>)
0x1800341b9  mov     rdx, [rsi]
0x1800341bc  mov     rcx, rsi
0x1800341bf  mov     r8, rdx
0x1800341c2  mov     rdx, [rdx]
0x1800341c5  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>)
0x1800341ca  mov     rcx, [rbx+50h]; lpCriticalSection
0x1800341ce  mov     [rbx+80h], edi
0x1800341d4  call    cs:__imp_LeaveCriticalSection
0x1800341db  nop     dword ptr [rax+rax+00h]
0x1800341e0  mov     rcx, [rbx+88h]; hHandle
0x1800341e7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800341ea  call    cs:__imp_WaitForSingleObject
0x1800341f1  nop     dword ptr [rax+rax+00h]
0x1800341f6  mov     sil, 1
0x1800341f9  lea     r14, WPP_witness_GLOBAL_Control
0x180034200  test    eax, eax
0x180034202  jz      short loc_180034242
0x180034204  call    cs:__imp_GetLastError
0x18003420b  nop     dword ptr [rax+rax+00h]
0x180034210  mov     edi, eax
0x180034212  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180034219  cmp     rcx, r14
0x18003421c  jz      short loc_180034242
0x18003421e  test    [rcx+1Ch], sil
0x180034222  jz      short loc_180034242
0x180034224  cmp     [rcx+19h], sil
0x180034228  jb      short loc_180034242
0x18003422a  mov     rcx, [rcx+10h]
0x18003422e  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x180034235  mov     edx, 19h
0x18003423a  mov     r9d, eax
0x18003423d  call    WPP_SF_d
0x180034242  mov     rcx, [rbx+40h]; CompletionPort
0x180034246  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18003424a  cmp     rcx, rbp
0x18003424d  jz      short loc_1800342A4
0x18003424f  xor     r9d, r9d; lpOverlapped
0x180034252  lea     r8d, [rbp+5]; dwCompletionKey
0x180034256  xor     edx, edx; dwNumberOfBytesTransferred
0x180034258  call    cs:__imp_PostQueuedCompletionStatus
0x18003425f  nop     dword ptr [rax+rax+00h]
0x180034264  test    eax, eax
0x180034266  jnz     short loc_1800342A4
0x180034268  call    cs:__imp_GetLastError
0x18003426f  nop     dword ptr [rax+rax+00h]
0x180034274  mov     edi, eax
0x180034276  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18003427d  cmp     rcx, r14
0x180034280  jz      short loc_1800342A4
0x180034282  test    [rcx+1Ch], sil
0x180034286  jz      short loc_1800342A4
0x180034288  cmp     [rcx+19h], sil
0x18003428c  jb      short loc_1800342A4
0x18003428e  mov     rcx, [rcx+10h]
0x180034292  lea     edx, [rbp+1Bh]
0x180034295  mov     r9d, eax
0x180034298  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18003429f  call    WPP_SF_d
0x1800342a4  mov     rcx, [rbx+48h]; hHandle
0x1800342a8  cmp     rcx, rbp
0x1800342ab  jz      short loc_180034314
0x1800342ad  mov     edx, 2710h; dwMilliseconds
0x1800342b2  call    cs:__imp_WaitForSingleObject
0x1800342b9  nop     dword ptr [rax+rax+00h]
0x1800342be  test    eax, eax
0x1800342c0  jz      short loc_180034300
0x1800342c2  call    cs:__imp_GetLastError
0x1800342c9  nop     dword ptr [rax+rax+00h]
0x1800342ce  mov     edi, eax
0x1800342d0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800342d7  cmp     rcx, r14
0x1800342da  jz      short loc_180034300
0x1800342dc  test    [rcx+1Ch], sil
0x1800342e0  jz      short loc_180034300
0x1800342e2  cmp     [rcx+19h], sil
0x1800342e6  jb      short loc_180034300
0x1800342e8  mov     rcx, [rcx+10h]
0x1800342ec  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x1800342f3  mov     edx, 1Bh
0x1800342f8  mov     r9d, eax
0x1800342fb  call    WPP_SF_d
0x180034300  mov     rcx, [rbx+48h]; hObject
0x180034304  call    cs:__imp_CloseHandle
0x18003430b  nop     dword ptr [rax+rax+00h]
0x180034310  mov     [rbx+48h], rbp
0x180034314  mov     rcx, [rbx+40h]; hObject
0x180034318  cmp     rcx, rbp
0x18003431b  jz      short loc_18003432D
0x18003431d  call    cs:__imp_CloseHandle
0x180034324  nop     dword ptr [rax+rax+00h]
0x180034329  mov     [rbx+40h], rbp
0x18003432d  mov     rcx, [rbx+38h]; this
0x180034331  test    rcx, rcx
0x180034334  jz      short loc_18003433B
0x180034336  call    ?Close@CThreadPool@@QEAAXXZ; CThreadPool::Close(void)
0x18003433b  mov     rcx, [rbx+58h]; Handle
0x18003433f  test    rcx, rcx
0x180034342  jz      short loc_180034358
0x180034344  call    cs:__imp_NtClose
0x18003434b  nop     dword ptr [rax+rax+00h]
0x180034350  mov     qword ptr [rbx+58h], 0
0x180034358  mov     rbx, [rsp+38h+arg_8]
0x18003435d  mov     eax, edi
0x18003435f  mov     rbp, [rsp+38h+arg_10]
0x180034364  add     rsp, 20h
0x180034368  pop     r14
0x18003436a  pop     rdi
0x18003436b  pop     rsi
0x18003436c  retn
```
