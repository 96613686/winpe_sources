# MergeSdbp_GetManifestedStub(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)

- ea: `0x1400230fc`
- end: `0x14002332d`
- name: `?MergeSdbp_GetManifestedStub@@YA_NAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `561`
- prototype: `bool __fastcall(void **, char *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140024958`

## callees

- `0x14001008c`
- `0x140020f9c`
- `0x140022014`
- `0x1400230fc`
- `0x1400245b8`
- `0x1400293cc`
- `0x14002ac4c`
- `0x14002c10c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400231c1`
- `ADVAPI32!RegCloseKey` at `0x1400232f6`
- `ADVAPI32!RegCloseKey` at `0x1400231c1`
- `ADVAPI32!RegCloseKey` at `0x1400232f6`
- `KERNEL32!GetLastError` at `0x140023284`
- `KERNEL32!GetLastError` at `0x140023284`
- `KERNEL32!GetProcessHeap` at `0x1400231d0`
- `KERNEL32!GetProcessHeap` at `0x14002328c`
- `KERNEL32!GetProcessHeap` at `0x1400232c0`
- `KERNEL32!GetProcessHeap` at `0x140023305`
- `KERNEL32!GetProcessHeap` at `0x1400231d0`
- `KERNEL32!GetProcessHeap` at `0x14002328c`
- `KERNEL32!GetProcessHeap` at `0x1400232c0`
- `KERNEL32!GetProcessHeap` at `0x140023305`
- `KERNEL32!SetLastError` at `0x1400232a2`
- `KERNEL32!SetLastError` at `0x1400232a2`
- `KERNEL32!HeapFree` at `0x1400231de`
- `KERNEL32!HeapFree` at `0x14002329a`
- `KERNEL32!HeapFree` at `0x1400232ce`
- `KERNEL32!HeapFree` at `0x140023313`
- `KERNEL32!HeapFree` at `0x1400231de`
- `KERNEL32!HeapFree` at `0x14002329a`
- `KERNEL32!HeapFree` at `0x1400232ce`
- `KERNEL32!HeapFree` at `0x140023313`

## string_xrefs

- `0x14002312a`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x140023149`: `Failed to open ManifestedMergeStubSdbs key (%d)`
- `0x14002318f`: `Failed to get the values for manifested stubs key (%d)`
- `0x140023156`: `MergeSdbp_GetManifestedStub`
- `0x14002319c`: `MergeSdbp_GetManifestedStub`

## pseudocode

```c
bool __fastcall MergeSdbp_GetManifestedStub(void **a1, char *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rcx
  int AllValues; // eax
  HKEY v7; // rbx
  HANDLE ProcessHeap; // rax
  __int64 *v10; // rsi
  __int64 *i; // rdi
  Pca::MergeSdb::Utils::RegValue *v12; // rcx
  _WORD *v13; // r11
  __int64 v14; // r11
  unsigned __int16 *v15; // rax
  int v16; // r9d
  int v17; // r8d
  void *v18; // r12
  void *v19; // r14
  DWORD LastError; // ebx
  HANDLE v21; // rax
  void *v22; // rbx
  HANDLE v23; // rax
  bool v24; // di
  HKEY v25; // rbx
  HANDLE v26; // rax
  void *v27; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v28[2]; // [rsp+38h] [rbp-30h] BYREF
  HKEY hKey[2]; // [rsp+48h] [rbp-20h] BYREF
  __int16 v30; // [rsp+58h] [rbp-10h]
  unsigned __int16 *v31; // [rsp+C0h] [rbp+58h] BYREF

  hKey[0] = 0;
  hKey[1] = 0;
  v30 = 0;
  v4 = Pca::MergeSdb::Utils::RegKey::AssignFromKeyAndSubPath(
         (Pca::MergeSdb::Utils::RegKey *)hKey,
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\ManifestedMergeStubSdbs");
  if ( v4 )
  {
    AslLogCallPrintf(1, "MergeSdbp_GetManifestedStub", 1236, "Failed to open ManifestedMergeStubSdbs key (%d)", v4);
LABEL_5:
    if ( hKey[1] )
      RegCloseKey(hKey[1]);
    v7 = hKey[0];
    if ( hKey[0] )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
    }
    return 0;
  }
  v28[1] = 0;
  v28[0] = std::_List_alloc<0,std::_List_base_types<Pca::MergeSdb::Utils::RegValue>>::_Buynode0(v5, 0, 0);
  AllValues = Pca::MergeSdb::Utils::RegKey::GetAllValues((Pca::MergeSdb::Utils::RegKey *)hKey);
  if ( AllValues )
  {
    AslLogCallPrintf(
      1,
      "MergeSdbp_GetManifestedStub",
      1242,
      "Failed to get the values for manifested stubs key (%d)",
      AllValues);
    std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v28);
    goto LABEL_5;
  }
  v10 = (__int64 *)v28[0];
  for ( i = *(__int64 **)v28[0]; i != v10; i = (__int64 *)*i )
  {
    v31 = 0;
    v12 = (Pca::MergeSdb::Utils::RegValue *)(i + 2);
    if ( *((_DWORD *)i + 6) <= 3u || (v13 = (_WORD *)(*(_QWORD *)v12 + 12LL), !*(_QWORD *)v12) )
      v13 = 0;
    if ( *v13 && (!Pca::MergeSdb::Utils::RegValue::GetValueValue(v12, (const unsigned __int16 **)&v31) || *v31) )
    {
      v15 = (unsigned __int16 *)a2;
      do
      {
        v16 = *(unsigned __int16 *)((char *)v15 + (char *)v31 - a2);
        v17 = *v15 - v16;
        if ( v17 )
          break;
        ++v15;
      }
      while ( v16 );
      if ( !v17 )
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v27,
          v14,
          -1);
        if ( a1 == &v27 )
        {
          v22 = v27;
        }
        else
        {
          v18 = v27;
          v19 = *a1;
          if ( *a1 )
          {
            LastError = GetLastError();
            v21 = GetProcessHeap();
            HeapFree(v21, 0, v19);
            SetLastError(LastError);
          }
          *a1 = v18;
          v22 = 0;
          v27 = 0;
        }
        if ( v22 )
        {
          v23 = GetProcessHeap();
          HeapFree(v23, 0, v22);
        }
      }
    }
  }
  v24 = *a1 != 0;
  std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v28);
  if ( hKey[1] )
    RegCloseKey(hKey[1]);
  v25 = hKey[0];
  if ( hKey[0] )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v25);
  }
  return v24;
}

```

## disassembly

```asm
0x1400230fc  push    rbp
0x1400230fe  push    rbx
0x1400230ff  push    rsi
0x140023100  push    rdi
0x140023101  push    r12
0x140023103  push    r13
0x140023105  push    r14
0x140023107  push    r15
0x140023109  mov     rbp, rsp
0x14002310c  sub     rsp, 68h
0x140023110  mov     r13, rdx
0x140023113  mov     r15, rcx
0x140023116  xorps   xmm0, xmm0
0x140023119  movdqu  xmmword ptr [rbp+hKey], xmm0
0x14002311e  xor     r14d, r14d
0x140023121  mov     [rbp+hKey+8], r14
0x140023125  mov     [rbp+var_10], r14w
0x14002312a  lea     r8, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x140023131  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x140023138  lea     rcx, [rbp+hKey]; this
0x14002313c  call    ?AssignFromKeyAndSubPath@RegKey@Utils@MergeSdb@Pca@@QEAAKPEAUHKEY__@@PEBG@Z; Pca::MergeSdb::Utils::RegKey::AssignFromKeyAndSubPath(HKEY__ *,ushort const *)
0x140023141  test    eax, eax
0x140023143  jz      short loc_140023168
0x140023145  mov     [rsp+68h+var_48], eax
0x140023149  lea     r9, aFailedToOpenMa; "Failed to open ManifestedMergeStubSdbs "...
0x140023150  mov     r8d, 4D4h
0x140023156  lea     rdx, aMergesdbpGetma; "MergeSdbp_GetManifestedStub"
0x14002315d  lea     ecx, [r14+1]
0x140023161  call    AslLogCallPrintf
0x140023166  jmp     short loc_1400231B8
0x140023168  mov     [rbp+var_28], r14
0x14002316c  xor     r8d, r8d
0x14002316f  xor     edx, edx
0x140023171  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@@std@@QEAAPEAU?$_List_node@VRegValue@Utils@MergeSdb@Pca@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Pca::MergeSdb::Utils::RegValue>>::_Buynode0(std::_List_node<Pca::MergeSdb::Utils::RegValue,void *> *,std::_List_node<Pca::MergeSdb::Utils::RegValue,void *> *)
0x140023176  mov     [rbp+var_30], rax
0x14002317a  lea     rdx, [rbp+var_30]
0x14002317e  lea     rcx, [rbp+hKey]; this
0x140023182  call    ?GetAllValues@RegKey@Utils@MergeSdb@Pca@@QEAAKAEAV?$list@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@@Z; Pca::MergeSdb::Utils::RegKey::GetAllValues(std::list<Pca::MergeSdb::Utils::RegValue> &)
0x140023187  test    eax, eax
0x140023189  jz      short loc_1400231EB
0x14002318b  mov     [rsp+68h+var_48], eax
0x14002318f  lea     r9, aFailedToGetThe_0; "Failed to get the values for manifested"...
0x140023196  mov     r8d, 4DAh
0x14002319c  lea     rdx, aMergesdbpGetma; "MergeSdbp_GetManifestedStub"
0x1400231a3  mov     ecx, 1
0x1400231a8  call    AslLogCallPrintf
0x1400231ad  nop
0x1400231ae  lea     rcx, [rbp+var_30]
0x1400231b2  call    ??1?$list@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@QEAA@XZ; std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(void)
0x1400231b7  nop
0x1400231b8  mov     rcx, [rbp+hKey+8]; hKey
0x1400231bc  test    rcx, rcx
0x1400231bf  jz      short loc_1400231C7
0x1400231c1  call    cs:__imp_RegCloseKey
0x1400231c7  mov     rbx, [rbp+hKey]
0x1400231cb  test    rbx, rbx
0x1400231ce  jz      short loc_1400231E4
0x1400231d0  call    cs:__imp_GetProcessHeap
0x1400231d6  mov     r8, rbx; lpMem
0x1400231d9  xor     edx, edx; dwFlags
0x1400231db  mov     rcx, rax; hHeap
0x1400231de  call    cs:__imp_HeapFree
0x1400231e4  xor     al, al
0x1400231e6  jmp     loc_14002331C
0x1400231eb  mov     rsi, [rbp+var_30]
0x1400231ef  mov     rdi, [rsi]
0x1400231f2  cmp     rdi, rsi
0x1400231f5  jz      loc_1400232DC
0x1400231fb  mov     [rbp+arg_10], r14
0x1400231ff  lea     rcx, [rdi+10h]; this
0x140023203  cmp     dword ptr [rdi+18h], 3
0x140023207  jbe     short loc_140023215
0x140023209  mov     rax, [rcx]
0x14002320c  test    rax, rax
0x14002320f  lea     r11, [rax+0Ch]
0x140023213  jnz     short loc_140023218
0x140023215  mov     r11, r14
0x140023218  cmp     [r11], r14w
0x14002321c  jz      loc_1400232D4
0x140023222  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x140023226  call    ?GetValueValue@RegValue@Utils@MergeSdb@Pca@@QEBA_NAEAPEBG@Z; Pca::MergeSdb::Utils::RegValue::GetValueValue(ushort const * &)
0x14002322b  mov     rcx, [rbp+arg_10]
0x14002322f  test    al, al
0x140023231  jz      short loc_14002323D
0x140023233  cmp     [rcx], r14w
0x140023237  jz      loc_1400232D4
0x14002323d  mov     rax, r13
0x140023240  sub     rcx, r13
0x140023243  movzx   r8d, word ptr [rax]
0x140023247  movzx   r9d, word ptr [rax+rcx]
0x14002324c  sub     r8d, r9d
0x14002324f  jnz     short loc_14002325A
0x140023251  add     rax, 2
0x140023255  test    r9d, r9d
0x140023258  jnz     short loc_140023243
0x14002325a  test    r8d, r8d
0x14002325d  jnz     short loc_1400232D4
0x14002325f  or      r8, 0FFFFFFFFFFFFFFFFh
0x140023263  mov     rdx, r11
0x140023266  lea     rcx, [rbp+var_38]
0x14002326a  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14002326f  lea     rax, [rbp+var_38]
0x140023273  cmp     r15, rax
0x140023276  jz      short loc_1400232B7
0x140023278  mov     r12, [rbp+var_38]
0x14002327c  mov     r14, [r15]
0x14002327f  test    r14, r14
0x140023282  jz      short loc_1400232A8
0x140023284  call    cs:__imp_GetLastError
0x14002328a  mov     ebx, eax
0x14002328c  call    cs:__imp_GetProcessHeap
0x140023292  mov     rcx, rax; hHeap
0x140023295  mov     r8, r14; lpMem
0x140023298  xor     edx, edx; dwFlags
0x14002329a  call    cs:__imp_HeapFree
0x1400232a0  mov     ecx, ebx; dwErrCode
0x1400232a2  call    cs:__imp_SetLastError
0x1400232a8  mov     [r15], r12
0x1400232ab  xor     r14d, r14d
0x1400232ae  mov     ebx, r14d
0x1400232b1  mov     [rbp+var_38], rbx
0x1400232b5  jmp     short loc_1400232BB
0x1400232b7  mov     rbx, [rbp+var_38]
0x1400232bb  test    rbx, rbx
0x1400232be  jz      short loc_1400232D4
0x1400232c0  call    cs:__imp_GetProcessHeap
0x1400232c6  mov     rcx, rax; hHeap
0x1400232c9  mov     r8, rbx; lpMem
0x1400232cc  xor     edx, edx; dwFlags
0x1400232ce  call    cs:__imp_HeapFree
0x1400232d4  mov     rdi, [rdi]
0x1400232d7  jmp     loc_1400231F2
0x1400232dc  cmp     [r15], r14
0x1400232df  setnz   dil
0x1400232e3  lea     rcx, [rbp+var_30]
0x1400232e7  call    ??1?$list@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@QEAA@XZ; std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(void)
0x1400232ec  nop
0x1400232ed  mov     rcx, [rbp+hKey+8]; hKey
0x1400232f1  test    rcx, rcx
0x1400232f4  jz      short loc_1400232FC
0x1400232f6  call    cs:__imp_RegCloseKey
0x1400232fc  mov     rbx, [rbp+hKey]
0x140023300  test    rbx, rbx
0x140023303  jz      short loc_140023319
0x140023305  call    cs:__imp_GetProcessHeap
0x14002330b  mov     rcx, rax; hHeap
0x14002330e  mov     r8, rbx; lpMem
0x140023311  xor     edx, edx; dwFlags
0x140023313  call    cs:__imp_HeapFree
0x140023319  mov     al, dil
0x14002331c  add     rsp, 68h
0x140023320  pop     r15
0x140023322  pop     r14
0x140023324  pop     r13
0x140023326  pop     r12
0x140023328  pop     rdi
0x140023329  pop     rsi
0x14002332a  pop     rbx
0x14002332b  pop     rbp
0x14002332c  retn
```
