# ComputeService::ContainerUtilities::Details::ForEachProcessInfo(void *,std::function<void (_SYSTEM_PROCESS_INFORMATION *)>)

- ea: `0x1400d74c8`
- end: `0x1400d7814`
- name: `?ForEachProcessInfo@Details@ContainerUtilities@ComputeService@@YAXPEAXV?$function@$$A6AXPEAU_SYSTEM_PROCESS_INFORMATION@@@Z@std@@@Z`
- size: `844`
- prototype: `__int64 __fastcall(HANDLE hJob)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400d7d18`

## callees

- `0x140005360`
- `0x1400056c4`
- `0x1400056fc`
- `0x140006098`
- `0x1400068e0`
- `0x14000ddac`
- `0x14000ea60`
- `0x140082150`
- `0x1400d7398`
- `0x1400d74c8`
- `0x1400fe010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1400d77e6`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1400d77e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d75d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d75d5`
- `ntdll!NtQuerySystemInformation` at `0x1400d7549`
- `ntdll!NtQuerySystemInformation` at `0x1400d7549`
- `ntdll!NtQueryInformationProcess` at `0x1400d76e3`
- `ntdll!NtQueryInformationProcess` at `0x1400d76e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d7726`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d7726`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400d76ac`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400d76ac`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x1400d75c7`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x1400d75c7`

## string_xrefs

- `0x1400d77ed`: `onecore\vm\compute\management\shared\container\containerjobinfo.cpp`
- `0x1400d7802`: `onecore\vm\compute\management\shared\container\containerjobinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ComputeService::ContainerUtilities::Details::ForEachProcessInfo(HANDLE hJob, __int64 a2)
{
  _DWORD *v4; // r14
  ULONG v5; // esi
  void *v6; // rbx
  char *v7; // r13
  unsigned __int64 v8; // rdx
  void *v9; // rcx
  NTSTATUS v10; // eax
  const char *v11; // r9
  DWORD i; // esi
  void *v13; // rdi
  unsigned __int64 v14; // rdx
  wil::details::in1diag3 *v15; // rbx
  const char *v16; // r9
  _QWORD *v17; // r8
  unsigned int v18; // ebx
  unsigned int v19; // esi
  char *v20; // rdi
  DWORD v21; // edx
  _QWORD *v22; // rax
  _BYTE *v23; // rcx
  __int64 v24; // rcx
  _QWORD *v25; // rbx
  void *v26; // rcx
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rcx
  int lpReturnLength; // [rsp+20h] [rbp-69h]
  wil::details::in1diag3 *v32; // [rsp+48h] [rbp-41h] BYREF
  int v33; // [rsp+54h] [rbp-35h]
  char *v34; // [rsp+60h] [rbp-29h] BYREF
  ULONG ReturnLength; // [rsp+68h] [rbp-21h] BYREF
  __int128 v36; // [rsp+70h] [rbp-19h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+80h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v4 = 0;
  v5 = 0x80000;
  v6 = 0;
  while ( 1 )
  {
    v7 = (char *)operator new[](v5);
    memset_0(v7, 0, v5);
    v9 = v6;
    v6 = v7;
    if ( v9 )
      operator delete(v9, v8);
    ReturnLength = 0;
    v10 = NtQuerySystemInformation(SystemProcessInformation, v7, v5, &ReturnLength);
    if ( v10 >= 0 )
      break;
    v11 = (const char *)(unsigned int)v10;
    if ( v10 != -1073741820 )
    {
      LODWORD(v11) = v10 | 0x10000000;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerjobinfo.cpp",
        v11,
        lpReturnLength);
    }
    if ( ReturnLength <= v5 )
      v5 += 4096;
    else
      v5 = ReturnLength;
  }
  for ( i = 1024; ; i = 8 * *v4 + 8 )
  {
    v13 = v4;
    v4 = operator new[](i);
    memset_0(v4, 0, i);
    if ( v13 )
      operator delete(v13, v14);
    if ( QueryInformationJobObject(hJob, JobObjectBasicProcessIdList, v4, i, 0) )
      break;
    v15 = retaddr;
    if ( GetLastError() != 234 )
      goto LABEL_44;
  }
  v36 = 0u;
  v17 = operator new(0x20u);
  *v17 = v17;
  v17[1] = v17;
  v17[2] = v17;
  *((_WORD *)v17 + 12) = 257;
  *(_QWORD *)&v36 = v17;
  v18 = 0;
  if ( v4[1] )
  {
    do
    {
      LODWORD(v34) = v4[2 * v18 + 2];
      std::_Tree<std::_Tset_traits<unsigned long,std::less<unsigned long>,std::allocator<unsigned long>,0>>::insert<0,0>(
        &v36,
        &v32,
        &v34);
      ++v18;
    }
    while ( v18 < v4[1] );
    v17 = (_QWORD *)v36;
  }
  v19 = 0;
  do
  {
    v20 = &v7[v19];
    v21 = *((_DWORD *)v20 + 20);
    v22 = (_QWORD *)v17[1];
    v33 = 0;
    v23 = v17;
    while ( !*((_BYTE *)v22 + 25) )
    {
      if ( *((_DWORD *)v22 + 7) >= v21 )
      {
        v23 = v22;
        v22 = (_QWORD *)*v22;
      }
      else
      {
        v22 = (_QWORD *)v22[2];
      }
    }
    if ( !v23[25] && v21 >= *((_DWORD *)v23 + 7) && v23 != (_BYTE *)v17 )
    {
      v15 = (wil::details::in1diag3 *)OpenProcess(0x1000u, 0, v21);
      v32 = v15;
      if ( (unsigned __int64)v15 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        memset(ProcessInformation, 0, sizeof(ProcessInformation));
        if ( NtQueryInformationProcess(v15, ProcessTimes, ProcessInformation, 0x20u, 0) >= 0
          && *(_QWORD *)&ProcessInformation[0] == *((_QWORD *)v20 + 4) )
        {
          v34 = &v7[v19];
          v24 = *(_QWORD *)(a2 + 56);
          if ( !v24 )
          {
            std::_Xbad_function_call();
LABEL_44:
            wil::details::in1diag3::Throw_GetLastError(
              v15,
              (void *)0x57,
              (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerjobinfo.cpp",
              v16);
          }
          (*(void (__fastcall **)(__int64, char **))(*(_QWORD *)v24 + 16LL))(v24, &v34);
        }
      }
      if ( (unsigned __int64)v15 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v15);
      v17 = (_QWORD *)v36;
    }
    if ( !*(_DWORD *)v20 )
      break;
    v19 += *(_DWORD *)v20;
  }
  while ( (unsigned __int64)v19 + 256 <= ReturnLength );
  v25 = (_QWORD *)v17[1];
  if ( !*((_BYTE *)v25 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned long,void *>>>(
        &v36,
        &v36,
        v25[2]);
      v26 = v25;
      v25 = (_QWORD *)*v25;
      operator delete(v26, 0x20u);
    }
    while ( !*((_BYTE *)v25 + 25) );
    v17 = (_QWORD *)v36;
  }
  operator delete(v17, 0x20u);
  operator delete(v4, v27);
  operator delete(v7, v28);
  v30 = *(_QWORD *)(a2 + 56);
  if ( v30 )
  {
    LOBYTE(v29) = v30 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 32LL))(v30, v29);
    *(_QWORD *)(a2 + 56) = 0;
  }
}

```

## disassembly

```asm
0x1400d74c8  mov     [rsp-8+arg_10], rbx
0x1400d74cd  push    rbp
0x1400d74ce  push    rsi
0x1400d74cf  push    rdi
0x1400d74d0  push    r12
0x1400d74d2  push    r13
0x1400d74d4  push    r14
0x1400d74d6  push    r15
0x1400d74d8  lea     rbp, [rsp-27h]
0x1400d74dd  sub     rsp, 0B0h
0x1400d74e4  mov     rax, cs:__security_cookie
0x1400d74eb  xor     rax, rsp
0x1400d74ee  mov     [rbp+57h+var_40], rax
0x1400d74f2  mov     r15, rdx
0x1400d74f5  mov     r12, rcx
0x1400d74f8  mov     [rbp+57h+var_A0], rdx
0x1400d74fc  xor     r14d, r14d
0x1400d74ff  mov     esi, 80000h
0x1400d7504  mov     ebx, r14d
0x1400d7507  mov     [rbp+57h+var_B0], rbx
0x1400d750b  mov     ecx, esi; unsigned __int64
0x1400d750d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400d7512  mov     r13, rax
0x1400d7515  mov     r8d, esi; Size
0x1400d7518  xor     edx, edx; Val
0x1400d751a  mov     rcx, rax; void *
0x1400d751d  call    memset_0
0x1400d7522  mov     rcx, rbx; void *
0x1400d7525  mov     rbx, r13
0x1400d7528  mov     [rbp+57h+var_B0], rbx
0x1400d752c  test    rcx, rcx
0x1400d752f  jz      short loc_1400D7536
0x1400d7531  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400d7536  mov     [rbp+57h+ReturnLength], r14d
0x1400d753a  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x1400d753e  mov     r8d, esi; SystemInformationLength
0x1400d7541  mov     rdx, r13; SystemInformation
0x1400d7544  mov     ecx, 5; SystemInformationClass
0x1400d7549  call    cs:__imp_NtQuerySystemInformation
0x1400d754f  test    eax, eax
0x1400d7551  jns     short loc_1400D757C
0x1400d7553  mov     r9d, eax
0x1400d7556  bts     r9d, 1Ch; char *
0x1400d755b  mov     rcx, [rbp+5Fh]; this
0x1400d755f  cmp     eax, 0C0000004h
0x1400d7564  jnz     loc_1400D7802
0x1400d756a  cmp     [rbp+57h+ReturnLength], esi
0x1400d756d  jbe     short loc_1400D7574
0x1400d756f  mov     esi, [rbp+57h+ReturnLength]
0x1400d7572  jmp     short loc_1400D750B
0x1400d7574  add     esi, 1000h
0x1400d757a  jmp     short loc_1400D750B
0x1400d757c  mov     esi, 400h
0x1400d7581  mov     [rbp+57h+var_A8], r14
0x1400d7585  mov     rdi, r14
0x1400d7588  mov     ecx, esi; unsigned __int64
0x1400d758a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400d758f  mov     r14, rax
0x1400d7592  mov     r8d, esi; Size
0x1400d7595  xor     edx, edx; Val
0x1400d7597  mov     rcx, rax; void *
0x1400d759a  call    memset_0
0x1400d759f  mov     [rbp+57h+var_A8], r14
0x1400d75a3  test    rdi, rdi
0x1400d75a6  jz      short loc_1400D75B0
0x1400d75a8  mov     rcx, rdi; void *
0x1400d75ab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400d75b0  mov     qword ptr [rsp+0E0h+lpReturnLength], 0; lpReturnLength
0x1400d75b9  mov     r9d, esi; cbJobObjectInformationLength
0x1400d75bc  mov     r8, r14; lpJobObjectInformation
0x1400d75bf  mov     edx, 3; JobObjectInformationClass
0x1400d75c4  mov     rcx, r12; hJob
0x1400d75c7  call    cs:__imp_QueryInformationJobObject
0x1400d75cd  test    eax, eax
0x1400d75cf  jnz     short loc_1400D75F2
0x1400d75d1  mov     rbx, [rbp+5Fh]
0x1400d75d5  call    cs:__imp_GetLastError
0x1400d75db  cmp     eax, 0EAh
0x1400d75e0  jnz     loc_1400D77ED
0x1400d75e6  mov     eax, [r14]
0x1400d75e9  lea     esi, ds:8[rax*8]
0x1400d75f0  jmp     short loc_1400D7585
0x1400d75f2  xorps   xmm0, xmm0
0x1400d75f5  movups  [rbp+57h+var_70], xmm0
0x1400d75f9  xor     r12d, r12d
0x1400d75fc  mov     qword ptr [rbp+57h+var_70], r12
0x1400d7600  mov     qword ptr [rbp+57h+var_70+8], r12
0x1400d7604  lea     ecx, [r12+20h]; Size
0x1400d7609  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400d760e  mov     r8, rax
0x1400d7611  mov     [rax], rax
0x1400d7614  mov     [rax+8], rax
0x1400d7618  mov     [rax+10h], rax
0x1400d761c  mov     word ptr [rax+18h], 101h
0x1400d7622  mov     qword ptr [rbp+57h+var_70], rax
0x1400d7626  mov     ebx, r12d
0x1400d7629  cmp     [r14+4], r12d
0x1400d762d  jbe     short loc_1400D7656
0x1400d762f  mov     eax, ebx
0x1400d7631  mov     ecx, [r14+rax*8+8]
0x1400d7636  mov     dword ptr [rbp+57h+var_80], ecx
0x1400d7639  lea     r8, [rbp+57h+var_80]
0x1400d763d  lea     rdx, [rbp+57h+var_98]
0x1400d7641  lea     rcx, [rbp+57h+var_70]
0x1400d7645  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@KU?$less@K@std@@V?$allocator@K@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@@std@@_N@1@$$QEAK@Z; std::_Tree<std::_Tset_traits<ulong,std::less<ulong>,std::allocator<ulong>,0>>::insert<0,0>(ulong &&)
0x1400d764a  inc     ebx
0x1400d764c  cmp     ebx, [r14+4]
0x1400d7650  jb      short loc_1400D762F
0x1400d7652  mov     r8, qword ptr [rbp+57h+var_70]
0x1400d7656  mov     esi, r12d
0x1400d7659  mov     edi, esi
0x1400d765b  add     rdi, r13
0x1400d765e  mov     edx, [rdi+50h]
0x1400d7661  mov     rax, [r8+8]
0x1400d7665  xor     ecx, ecx
0x1400d7667  mov     [rbp+57h+var_8C], ecx
0x1400d766a  mov     rcx, r8
0x1400d766d  jmp     short loc_1400D7680
0x1400d766f  cmp     [rax+1Ch], edx
0x1400d7672  jnb     short loc_1400D767A
0x1400d7674  mov     rax, [rax+10h]
0x1400d7678  jmp     short loc_1400D7680
0x1400d767a  mov     rcx, rax
0x1400d767d  mov     rax, [rax]
0x1400d7680  cmp     [rax+19h], r12b
0x1400d7684  jz      short loc_1400D766F
0x1400d7686  cmp     [rcx+19h], r12b
0x1400d768a  jnz     loc_1400D7730
0x1400d7690  cmp     edx, [rcx+1Ch]
0x1400d7693  jb      loc_1400D7730
0x1400d7699  cmp     rcx, r8
0x1400d769c  jz      loc_1400D7730
0x1400d76a2  mov     r8d, edx; dwProcessId
0x1400d76a5  xor     edx, edx; bInheritHandle
0x1400d76a7  mov     ecx, 1000h; dwDesiredAccess
0x1400d76ac  call    cs:__imp_OpenProcess
0x1400d76b2  mov     rbx, rax
0x1400d76b5  mov     [rbp+57h+var_98], rax
0x1400d76b9  dec     rax
0x1400d76bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d76c0  ja      short loc_1400D7719
0x1400d76c2  xorps   xmm0, xmm0
0x1400d76c5  movups  [rbp+57h+ProcessInformation], xmm0
0x1400d76c9  movups  [rbp+57h+var_50], xmm0
0x1400d76cd  mov     qword ptr [rsp+0E0h+lpReturnLength], r12; ReturnLength
0x1400d76d2  mov     r9d, 20h ; ' '; ProcessInformationLength
0x1400d76d8  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x1400d76dc  lea     edx, [r9-1Ch]; ProcessInformationClass
0x1400d76e0  mov     rcx, rbx; ProcessHandle
0x1400d76e3  call    cs:__imp_NtQueryInformationProcess
0x1400d76e9  test    eax, eax
0x1400d76eb  js      short loc_1400D7719
0x1400d76ed  mov     rax, [rdi+20h]
0x1400d76f1  cmp     qword ptr [rbp+57h+ProcessInformation], rax
0x1400d76f5  jnz     short loc_1400D7719
0x1400d76f7  mov     [rbp+57h+var_80], rdi
0x1400d76fb  mov     rcx, [r15+38h]
0x1400d76ff  test    rcx, rcx
0x1400d7702  jz      loc_1400D77E6
0x1400d7708  mov     rax, [rcx]
0x1400d770b  lea     rdx, [rbp+57h+var_80]
0x1400d770f  mov     rax, [rax+10h]
0x1400d7713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400d7718  nop
0x1400d7719  lea     rax, [rbx-1]
0x1400d771d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d7721  ja      short loc_1400D772C
0x1400d7723  mov     rcx, rbx; hObject
0x1400d7726  call    cs:__imp_CloseHandle
0x1400d772c  mov     r8, qword ptr [rbp+57h+var_70]
0x1400d7730  cmp     [rdi], r12d
0x1400d7733  jz      short loc_1400D774B
0x1400d7735  add     esi, [rdi]
0x1400d7737  mov     ecx, [rbp+57h+ReturnLength]
0x1400d773a  mov     eax, esi
0x1400d773c  add     rax, 100h
0x1400d7742  cmp     rax, rcx
0x1400d7745  jbe     loc_1400D7659
0x1400d774b  mov     rbx, [r8+8]
0x1400d774f  cmp     [rbx+19h], r12b
0x1400d7753  jnz     short loc_1400D7780
0x1400d7755  mov     r8, [rbx+10h]
0x1400d7759  lea     rdx, [rbp+57h+var_70]
0x1400d775d  lea     rcx, [rbp+57h+var_70]
0x1400d7761  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@KPEAX@std@@@1@PEAU?$_Tree_node@KPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree<std::allocator<std::_Tree_node<ulong,void *>>>(std::allocator<std::_Tree_node<ulong,void *>> &,std::_Tree_node<ulong,void *> *)
0x1400d7766  mov     rcx, rbx; void *
0x1400d7769  mov     rbx, [rbx]
0x1400d776c  mov     edx, 20h ; ' '; unsigned __int64
0x1400d7771  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400d7776  cmp     [rbx+19h], r12b
0x1400d777a  jz      short loc_1400D7755
0x1400d777c  mov     r8, qword ptr [rbp+57h+var_70]
0x1400d7780  mov     edx, 20h ; ' '; unsigned __int64
0x1400d7785  mov     rcx, r8; void *
0x1400d7788  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400d778d  nop
0x1400d778e  mov     rcx, r14; void *
0x1400d7791  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400d7796  nop
0x1400d7797  mov     rcx, r13; void *
0x1400d779a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400d779f  nop
0x1400d77a0  mov     rcx, [r15+38h]
0x1400d77a4  test    rcx, rcx
0x1400d77a7  jz      short loc_1400D77BF
0x1400d77a9  mov     rax, [rcx]
0x1400d77ac  cmp     rcx, r15
0x1400d77af  setnz   dl
0x1400d77b2  mov     rax, [rax+20h]
0x1400d77b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400d77bb  mov     [r15+38h], r12
0x1400d77bf  mov     rcx, [rbp+57h+var_40]
0x1400d77c3  xor     rcx, rsp; StackCookie
0x1400d77c6  call    __security_check_cookie
0x1400d77cb  mov     rbx, [rsp+0E0h+arg_10]
0x1400d77d3  add     rsp, 0B0h
0x1400d77da  pop     r15
0x1400d77dc  pop     r14
0x1400d77de  pop     r13
0x1400d77e0  pop     r12
0x1400d77e2  pop     rdi
0x1400d77e3  pop     rsi
0x1400d77e4  pop     rbp
0x1400d77e5  retn
0x1400d77e6  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1400d77ec  nop
0x1400d77ed  lea     r8, aOnecoreVmCompu_33; "onecore\\vm\\compute\\management\\share"...
0x1400d77f4  mov     edx, 57h ; 'W'; void *
0x1400d77f9  mov     rcx, rbx; this
0x1400d77fc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400d7802  lea     r8, aOnecoreVmCompu_33; "onecore\\vm\\compute\\management\\share"...
0x1400d7809  mov     edx, 43h ; 'C'; void *
0x1400d780e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
