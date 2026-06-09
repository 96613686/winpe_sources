# ComputeService::ContainerUtilities::QueryJobPrivateWorkingSet(void *)

- ea: `0x1400d7b60`
- end: `0x1400d7d12`
- name: `?QueryJobPrivateWorkingSet@ContainerUtilities@ComputeService@@YA_KPEAX@Z`
- size: `434`
- prototype: `unsigned __int64 __fastcall(HANDLE JobHandle, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x14008c3a4`

## callees

- `0x140005360`
- `0x1400056c4`
- `0x140006098`
- `0x14000ddac`
- `0x140082150`
- `0x1400d7a08`
- `0x1400d7b60`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x1400d7c25`
- `ntdll!NtQueryInformationProcess` at `0x1400d7c25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d7c40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400d7c40`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400d7bbd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400d7bbd`
- `api-ms-win-core-job-l1-1-0!IsProcessInJob` at `0x1400d7be4`
- `api-ms-win-core-job-l1-1-0!IsProcessInJob` at `0x1400d7be4`

## string_xrefs

- `0x1400d7d00`: `onecore\vm\compute\management\shared\container\containerjobinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ComputeService::ContainerUtilities::QueryJobPrivateWorkingSet(HANDLE JobHandle, void *a2)
{
  __int64 v3; // rsi
  __int64 *v4; // rbx
  char *v5; // rdi
  const char *v6; // r9
  __int64 **v7; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  void *v10; // rcx
  _QWORD *v11; // rbx
  void *v12; // rcx
  WINBOOL Result; // [rsp+38h] [rbp-51h] BYREF
  void *v15[2]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE ProcessInformation[96]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v17; // [rsp+B0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v3 = 0;
  *(_OWORD *)v15 = 0;
  ComputeService::ContainerUtilities::QueryJobPids(v15, JobHandle);
  v4 = *(__int64 **)v15[0];
  while ( !*((_BYTE *)v4 + 25) )
  {
    v5 = (char *)OpenProcess(0x1000u, 0, *((_DWORD *)v4 + 7));
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      Result = 0;
      if ( !IsProcessInJob(v5, JobHandle, &Result) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xDB,
          (unsigned int)"onecore\\vm\\compute\\management\\shared\\container\\containerjobinfo.cpp",
          v6);
      if ( Result )
      {
        memset_0(ProcessInformation, 0, 0x70u);
        if ( NtQueryInformationProcess(v5, ProcessVmCounters, ProcessInformation, 0x70u, 0) >= 0 )
          v3 += v17;
      }
    }
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v5);
    v7 = (__int64 **)v4[2];
    if ( *((_BYTE *)v7 + 25) )
    {
      for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 25) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v4 = i;
      v4 = i;
    }
    else
    {
      v4 = (__int64 *)v4[2];
      for ( j = *v7; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v4 = j;
    }
  }
  v10 = v15[0];
  v11 = (_QWORD *)*((_QWORD *)v15[0] + 1);
  if ( !*((_BYTE *)v11 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<unsigned long>>::_Erase_tree<std::allocator<std::_Tree_node<unsigned long,void *>>>(
        v15,
        v15,
        v11[2]);
      v12 = v11;
      v11 = (_QWORD *)*v11;
      operator delete(v12, 0x20u);
    }
    while ( !*((_BYTE *)v11 + 25) );
    v10 = v15[0];
  }
  operator delete(v10, 0x20u);
  return v3;
}

```

## disassembly

```asm
0x1400d7b60  mov     [rsp-8+arg_8], rbx
0x1400d7b65  mov     [rsp-8+arg_10], rsi
0x1400d7b6a  push    rbp
0x1400d7b6b  push    rdi
0x1400d7b6c  push    r14
0x1400d7b6e  lea     rbp, [rsp-47h]
0x1400d7b73  sub     rsp, 0D0h
0x1400d7b7a  mov     rax, cs:__security_cookie
0x1400d7b81  xor     rax, rsp
0x1400d7b84  mov     [rbp+57h+var_20], rax
0x1400d7b88  mov     r14, rcx
0x1400d7b8b  xor     esi, esi
0x1400d7b8d  xorps   xmm0, xmm0
0x1400d7b90  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x1400d7b94  mov     rdx, rcx
0x1400d7b97  lea     rcx, [rbp+57h+var_A0]
0x1400d7b9b  call    ?QueryJobPids@ContainerUtilities@ComputeService@@YA?AV?$set@KU?$less@K@std@@V?$allocator@K@2@@std@@PEAX@Z; ComputeService::ContainerUtilities::QueryJobPids(void *)
0x1400d7ba0  nop
0x1400d7ba1  mov     rbx, [rbp+57h+var_A0]
0x1400d7ba5  mov     rbx, [rbx]
0x1400d7ba8  cmp     byte ptr [rbx+19h], 0
0x1400d7bac  jnz     loc_1400D7C95
0x1400d7bb2  mov     r8d, [rbx+1Ch]; dwProcessId
0x1400d7bb6  xor     edx, edx; bInheritHandle
0x1400d7bb8  mov     ecx, 1000h; dwDesiredAccess
0x1400d7bbd  call    cs:__imp_OpenProcess
0x1400d7bc3  mov     rdi, rax
0x1400d7bc6  mov     [rbp+57h+var_B0], rax
0x1400d7bca  dec     rax
0x1400d7bcd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d7bd1  ja      short loc_1400D7C33
0x1400d7bd3  mov     [rbp+57h+Result], 0
0x1400d7bda  lea     r8, [rbp+57h+Result]; Result
0x1400d7bde  mov     rdx, r14; JobHandle
0x1400d7be1  mov     rcx, rdi; ProcessHandle
0x1400d7be4  call    cs:__imp_IsProcessInJob
0x1400d7bea  mov     rcx, [rbp+5Fh]; this
0x1400d7bee  test    eax, eax
0x1400d7bf0  jz      loc_1400D7D00
0x1400d7bf6  cmp     [rbp+57h+Result], 0
0x1400d7bfa  jz      short loc_1400D7C33
0x1400d7bfc  xor     edx, edx; Val
0x1400d7bfe  lea     r8d, [rdx+70h]; Size
0x1400d7c02  lea     rcx, [rbp+57h+ProcessInformation]; void *
0x1400d7c06  call    memset_0
0x1400d7c0b  mov     [rsp+0E0h+ReturnLength], 0; ReturnLength
0x1400d7c14  mov     r9d, 70h ; 'p'; ProcessInformationLength
0x1400d7c1a  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x1400d7c1e  lea     edx, [r9-6Dh]; ProcessInformationClass
0x1400d7c22  mov     rcx, rdi; ProcessHandle
0x1400d7c25  call    cs:__imp_NtQueryInformationProcess
0x1400d7c2b  test    eax, eax
0x1400d7c2d  js      short loc_1400D7C33
0x1400d7c2f  add     rsi, [rbp+57h+var_30]
0x1400d7c33  lea     rax, [rdi-1]
0x1400d7c37  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d7c3b  ja      short loc_1400D7C46
0x1400d7c3d  mov     rcx, rdi; hObject
0x1400d7c40  call    cs:__imp_CloseHandle
0x1400d7c46  mov     rcx, [rbx+10h]
0x1400d7c4a  cmp     byte ptr [rcx+19h], 0
0x1400d7c4e  jz      short loc_1400D7C71
0x1400d7c50  mov     rax, [rbx+8]
0x1400d7c54  jmp     short loc_1400D7C63
0x1400d7c56  cmp     rbx, [rax+10h]
0x1400d7c5a  jnz     short loc_1400D7C69
0x1400d7c5c  mov     rbx, rax
0x1400d7c5f  mov     rax, [rax+8]
0x1400d7c63  cmp     byte ptr [rax+19h], 0
0x1400d7c67  jz      short loc_1400D7C56
0x1400d7c69  mov     rbx, rax
0x1400d7c6c  jmp     loc_1400D7BA8
0x1400d7c71  mov     rbx, rcx
0x1400d7c74  mov     rcx, [rcx]
0x1400d7c77  cmp     byte ptr [rcx+19h], 0
0x1400d7c7b  jnz     loc_1400D7BA8
0x1400d7c81  mov     rbx, rcx
0x1400d7c84  mov     rax, [rcx]
0x1400d7c87  mov     rcx, rax
0x1400d7c8a  cmp     byte ptr [rax+19h], 0
0x1400d7c8e  jz      short loc_1400D7C81
0x1400d7c90  jmp     loc_1400D7BA8
0x1400d7c95  mov     rcx, [rbp+57h+var_A0]
0x1400d7c99  mov     rbx, [rcx+8]
0x1400d7c9d  mov     edi, 20h ; ' '
0x1400d7ca2  cmp     byte ptr [rbx+19h], 0
0x1400d7ca6  jnz     short loc_1400D7CD1
0x1400d7ca8  mov     r8, [rbx+10h]
0x1400d7cac  lea     rdx, [rbp+57h+var_A0]
0x1400d7cb0  lea     rcx, [rbp+57h+var_A0]
0x1400d7cb4  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@KPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@K@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@KPEAX@std@@@1@PEAU?$_Tree_node@KPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<ulong>>::_Erase_tree<std::allocator<std::_Tree_node<ulong,void *>>>(std::allocator<std::_Tree_node<ulong,void *>> &,std::_Tree_node<ulong,void *> *)
0x1400d7cb9  mov     rcx, rbx; void *
0x1400d7cbc  mov     rbx, [rbx]
0x1400d7cbf  mov     rdx, rdi; unsigned __int64
0x1400d7cc2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400d7cc7  cmp     byte ptr [rbx+19h], 0
0x1400d7ccb  jz      short loc_1400D7CA8
0x1400d7ccd  mov     rcx, [rbp+57h+var_A0]; void *
0x1400d7cd1  mov     rdx, rdi; unsigned __int64
0x1400d7cd4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400d7cd9  mov     rax, rsi
0x1400d7cdc  mov     rcx, [rbp+57h+var_20]
0x1400d7ce0  xor     rcx, rsp; StackCookie
0x1400d7ce3  call    __security_check_cookie
0x1400d7ce8  lea     r11, [rsp+0E0h+var_10]
0x1400d7cf0  mov     rbx, [r11+28h]
0x1400d7cf4  mov     rsi, [r11+30h]
0x1400d7cf8  mov     rsp, r11
0x1400d7cfb  pop     r14
0x1400d7cfd  pop     rdi
0x1400d7cfe  pop     rbp
0x1400d7cff  retn
0x1400d7d00  lea     r8, aOnecoreVmCompu_33; "onecore\\vm\\compute\\management\\share"...
0x1400d7d07  mov     edx, 0DBh; void *
0x1400d7d0c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
