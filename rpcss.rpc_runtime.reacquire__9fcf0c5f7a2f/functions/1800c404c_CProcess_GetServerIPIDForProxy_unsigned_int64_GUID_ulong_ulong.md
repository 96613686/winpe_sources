# CProcess::GetServerIPIDForProxy(unsigned __int64,_GUID *,ulong *,ulong *)

- ea: `0x1800c404c`
- end: `0x1800c443d`
- name: `?GetServerIPIDForProxy@CProcess@@QEAAJ_KPEAU_GUID@@PEAK2@Z`
- size: `1009`
- prototype: `__int64 __fastcall(CProcess *__hidden this, unsigned __int64, struct _GUID *, unsigned int *, SIZE_T NumberOfBytesRead)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f2430`

## callees

- `0x18000ce5c`
- `0x180013cd4`
- `0x1800210f8`
- `0x180024590`
- `0x180093f20`
- `0x1800b8428`
- `0x1800c404c`
- `0x180112d84`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x1800c40dd`
- `ntdll!NtQueryInformationProcess` at `0x1800c40dd`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800c4199`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800c4199`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800c422b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800c4412`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800c422b`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800c4412`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800c41f3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800c4290`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800c4334`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800c43a0`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800c41f3`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800c4290`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800c4334`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800c43a0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800c408e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800c408e`

## string_xrefs

- `0x1800c40b0`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x1800c40f1`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x1800c4120`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x1800c420c`: `onecore\com\combase\rpcss\objex\process.cxx`

## pseudocode

```c
__int64 __fastcall CProcess::GetServerIPIDForProxy(
        CProcess *this,
        __int64 a2,
        struct _GUID *a3,
        unsigned int *a4,
        _DWORD *NumberOfBytesRead)
{
  _DWORD *v5; // r12
  DWORD v6; // r8d
  HANDLE v9; // rbx
  const char *v10; // r9
  int LastError; // eax
  NTSTATUS v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  unsigned int ArchitecturePointerSizeInBytes; // eax
  _DWORD *v16; // rcx
  size_t v17; // rsi
  unsigned int v18; // r8d
  unsigned int v19; // r9d
  unsigned int v20; // r10d
  SIZE_T v21; // rdx
  unsigned int v22; // ecx
  size_t v23; // r15
  char *v24; // rax
  char *v25; // rdi
  size_t v26; // r15
  __int64 v27; // rdx
  __int64 v28; // rax
  unsigned __int64 v29; // rcx
  __int64 v30; // rsi
  char *v31; // rdx
  char *v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rax
  unsigned int *v35; // rdx
  __int64 v36; // rax
  int v37; // ecx
  _DWORD *v38; // rcx
  int v39; // edx
  int ReturnLength; // [rsp+20h] [rbp-28h]
  int ReturnLengtha; // [rsp+20h] [rbp-28h]
  LPCVOID v43; // [rsp+30h] [rbp-18h] BYREF
  HANDLE v44[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  __int64 ProcessInformation; // [rsp+90h] [rbp+48h] BYREF
  __int64 v47; // [rsp+98h] [rbp+50h]
  struct _GUID *v48; // [rsp+A0h] [rbp+58h]
  LPCVOID lpBaseAddress; // [rsp+A8h] [rbp+60h] BYREF

  v48 = a3;
  v47 = a2;
  v5 = NumberOfBytesRead;
  *a3 = 0;
  v6 = *((_DWORD *)this + 22);
  *v5 = 0;
  *a4 = 0;
  v9 = OpenProcess(0x410u, 0, v6);
  v44[0] = v9;
  if ( (((unsigned __int64)v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xD0D,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
                  v10);
LABEL_5:
    v13 = LastError;
    goto LABEL_52;
  }
  ProcessInformation = 0;
  v12 = NtQueryInformationProcess(v9, ProcessDebugPort, &ProcessInformation, 8u, 0);
  if ( v12 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0xD12,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
                  (const char *)(unsigned int)v12,
                  ReturnLength);
    goto LABEL_5;
  }
  if ( !ProcessInformation )
  {
    v13 = -2147024891;
    v14 = 3347;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
      (const char *)v13,
      ReturnLength);
    goto LABEL_52;
  }
  ArchitecturePointerSizeInBytes = GetArchitecturePointerSizeInBytes(*((_WORD *)this + 214));
  v16 = (_DWORD *)*((_QWORD *)this + 51);
  v17 = ArchitecturePointerSizeInBytes;
  v18 = v16[12];
  v19 = v16[4];
  v20 = v19;
  v21 = (unsigned int)v16[15];
  if ( v19 <= v18 )
    v20 = v16[12];
  if ( (unsigned int)v21 <= v20 )
  {
    v22 = v16[12];
    if ( v19 > v18 )
      v22 = v19;
  }
  else
  {
    v22 = v16[15];
  }
  if ( ArchitecturePointerSizeInBytes <= v22 )
  {
    if ( (unsigned int)v21 <= v20 )
    {
      v21 = v18;
      if ( v19 > v18 )
        v21 = v19;
    }
  }
  else
  {
    v21 = ArchitecturePointerSizeInBytes;
  }
  v23 = (unsigned int)v21;
  v24 = (char *)VirtualAlloc(0, v21, 0x3000u, 4u);
  v25 = v24;
  if ( !v24 )
  {
    v13 = -2147024882;
    v14 = 3356;
    goto LABEL_8;
  }
  NumberOfBytesRead = 0;
  memset_0(v24, 0, v23);
  v26 = v17;
  if ( ReadProcessMemory(v9, (LPCVOID)(v47 + **((unsigned int **)this + 51)), v25, v17, (SIZE_T *)&NumberOfBytesRead) )
  {
    if ( (_DWORD *)v17 == NumberOfBytesRead )
    {
      lpBaseAddress = 0;
      memcpy_0(&lpBaseAddress, v25, v17);
      v28 = *((_QWORD *)this + 51);
      v29 = *(unsigned int *)(v28 + 64);
      if ( (unsigned __int64)lpBaseAddress >= v29 )
      {
        if ( ReadProcessMemory(
               v9,
               (char *)lpBaseAddress - v29,
               v25,
               *(unsigned int *)(v28 + 60),
               (SIZE_T *)&NumberOfBytesRead) )
        {
          v30 = *((_QWORD *)this + 51);
          if ( (_DWORD *)*(unsigned int *)(v30 + 60) == NumberOfBytesRead )
          {
            v31 = &v25[*(unsigned int *)(v30 + 72)];
            lpBaseAddress = 0;
            memcpy_0(&lpBaseAddress, v31, v26);
            v32 = &v25[*(unsigned int *)(v30 + 68)];
            v43 = 0;
            memcpy_0(&v43, v32, v26);
            v33 = *(unsigned int *)(v30 + 76);
            v34 = *(_QWORD *)&v25[v33] - *(_QWORD *)(v30 + 80);
            if ( !v34 )
              v34 = *(_QWORD *)&v25[v33 + 8] - *(_QWORD *)(v30 + 88);
            if ( v34 )
            {
              v27 = 3389;
            }
            else if ( ReadProcessMemory(
                        v9,
                        lpBaseAddress,
                        v25,
                        *(unsigned int *)(v30 + 48),
                        (SIZE_T *)&NumberOfBytesRead) )
            {
              v35 = (unsigned int *)*((_QWORD *)this + 51);
              if ( (_DWORD *)v35[12] == NumberOfBytesRead )
              {
                v36 = v35[14];
                *a4 = *(_DWORD *)&v25[v35[13]];
                v37 = *(_DWORD *)&v25[v36];
                *v5 = v37;
                if ( v37 == -1 )
                  *v5 = 0xFFFF;
                if ( ReadProcessMemory(v9, v43, v25, v35[4], (SIZE_T *)&NumberOfBytesRead) )
                {
                  v38 = (_DWORD *)*((_QWORD *)this + 51);
                  if ( (_DWORD *)(unsigned int)v38[4] == NumberOfBytesRead )
                  {
                    v39 = *(_DWORD *)&v25[v38[6]];
                    if ( (v39 & v38[11]) != 0 )
                    {
                      v27 = 3411;
                    }
                    else
                    {
                      if ( (v39 & v38[10]) == 0 )
                      {
                        *v48 = *(struct _GUID *)&v25[v38[7]];
                        VirtualFree(v25, 0, 0x8000u);
                        v13 = 0;
                        goto LABEL_52;
                      }
                      v27 = 3412;
                    }
                  }
                  else
                  {
                    v27 = 3407;
                  }
                }
                else
                {
                  v27 = 3406;
                }
              }
              else
              {
                v27 = 3394;
              }
            }
            else
            {
              v27 = 3393;
            }
          }
          else
          {
            v27 = 3379;
          }
        }
        else
        {
          v27 = 3377;
        }
      }
      else
      {
        v27 = 3373;
      }
    }
    else
    {
      v27 = 3365;
    }
  }
  else
  {
    v27 = 3364;
  }
  v13 = -2147417837;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v27,
    (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\process.cxx",
    (const char *)0x80010113LL,
    ReturnLengtha);
  VirtualFree(v25, 0, 0x8000u);
LABEL_52:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v44);
  return v13;
}

```

## disassembly

```asm
0x1800c404c  mov     [rsp-40h+arg_10], r8
0x1800c4051  mov     [rsp-40h+arg_8], rdx
0x1800c4056  push    rbp
0x1800c4057  push    rbx
0x1800c4058  push    rsi
0x1800c4059  push    rdi
0x1800c405a  push    r12
0x1800c405c  push    r13
0x1800c405e  push    r14
0x1800c4060  push    r15
0x1800c4062  mov     rbp, rsp
0x1800c4065  sub     rsp, 48h
0x1800c4069  mov     r12, [rbp+NumberOfBytesRead]
0x1800c406d  xorps   xmm0, xmm0
0x1800c4070  movups  xmmword ptr [r8], xmm0
0x1800c4074  mov     r8d, [rcx+58h]; dwProcessId
0x1800c4078  mov     r14, rcx
0x1800c407b  xor     edi, edi
0x1800c407d  mov     ecx, 410h; dwDesiredAccess
0x1800c4082  xor     edx, edx; bInheritHandle
0x1800c4084  mov     [r12], edi
0x1800c4088  mov     r13, r9
0x1800c408b  mov     [r9], edi
0x1800c408e  call    cs:__imp_OpenProcess
0x1800c4095  nop     dword ptr [rax+rax+00h]
0x1800c409a  mov     rbx, rax
0x1800c409d  mov     [rbp+var_10], rax
0x1800c40a1  inc     rax
0x1800c40a4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800c40aa  jnz     short loc_1800C40C3
0x1800c40ac  mov     rcx, [rbp+40h]; this
0x1800c40b0  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x1800c40b7  mov     edx, 0D0Dh; void *
0x1800c40bc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c40c1  jmp     short loc_1800C4105
0x1800c40c3  mov     r9d, 8; ProcessInformationLength
0x1800c40c9  mov     [rbp+ProcessInformation], rdi
0x1800c40cd  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x1800c40d1  mov     qword ptr [rsp+48h+ReturnLength], rdi; int
0x1800c40d6  mov     rcx, rbx; ProcessHandle
0x1800c40d9  lea     edx, [r9-1]; ProcessInformationClass
0x1800c40dd  call    cs:__imp_NtQueryInformationProcess
0x1800c40e4  nop     dword ptr [rax+rax+00h]
0x1800c40e9  test    eax, eax
0x1800c40eb  jns     short loc_1800C410C
0x1800c40ed  mov     rcx, [rbp+40h]; this
0x1800c40f1  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x1800c40f8  mov     r9d, eax; char *
0x1800c40fb  mov     edx, 0D12h; void *
0x1800c4100  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800c4105  mov     ebx, eax
0x1800c4107  jmp     loc_1800C4420
0x1800c410c  cmp     [rbp+ProcessInformation], rdi
0x1800c4110  jnz     short loc_1800C4134
0x1800c4112  mov     ebx, 80070005h
0x1800c4117  mov     edx, 0D13h; void *
0x1800c411c  mov     rcx, [rbp+40h]; this
0x1800c4120  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x1800c4127  mov     r9d, ebx; char *
0x1800c412a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c412f  jmp     loc_1800C4420
0x1800c4134  movzx   ecx, word ptr [r14+1ACh]; unsigned __int16
0x1800c413c  call    ?GetArchitecturePointerSizeInBytes@@YAKG@Z; GetArchitecturePointerSizeInBytes(ushort)
0x1800c4141  mov     rcx, [r14+198h]
0x1800c4148  mov     esi, eax
0x1800c414a  mov     r8d, [rcx+30h]
0x1800c414e  mov     r9d, [rcx+10h]
0x1800c4152  mov     r10d, r9d
0x1800c4155  mov     edx, [rcx+3Ch]
0x1800c4158  cmp     r9d, r8d
0x1800c415b  cmovbe  r10d, r8d
0x1800c415f  cmp     edx, r10d
0x1800c4162  jbe     short loc_1800C4168
0x1800c4164  mov     ecx, edx
0x1800c4166  jmp     short loc_1800C4172
0x1800c4168  cmp     r9d, r8d
0x1800c416b  mov     ecx, r8d
0x1800c416e  cmova   ecx, r9d
0x1800c4172  cmp     esi, ecx
0x1800c4174  jbe     short loc_1800C417B
0x1800c4176  mov     rdx, rsi
0x1800c4179  jmp     short loc_1800C418A
0x1800c417b  cmp     edx, r10d
0x1800c417e  ja      short loc_1800C418A
0x1800c4180  cmp     r9d, r8d
0x1800c4183  mov     edx, r8d
0x1800c4186  cmova   edx, r9d; dwSize
0x1800c418a  xor     ecx, ecx; lpAddress
0x1800c418c  mov     r15d, edx
0x1800c418f  mov     r8d, 3000h; flAllocationType
0x1800c4195  lea     r9d, [rcx+4]; flProtect
0x1800c4199  call    cs:__imp_VirtualAlloc
0x1800c41a0  nop     dword ptr [rax+rax+00h]
0x1800c41a5  mov     rdi, rax
0x1800c41a8  test    rax, rax
0x1800c41ab  jnz     short loc_1800C41BC
0x1800c41ad  mov     ebx, 8007000Eh
0x1800c41b2  mov     edx, 0D1Ch
0x1800c41b7  jmp     loc_1800C411C
0x1800c41bc  mov     r8, r15; Size
0x1800c41bf  mov     [rbp+NumberOfBytesRead], 0
0x1800c41c7  xor     edx, edx; Val
0x1800c41c9  mov     rcx, rdi; void *
0x1800c41cc  call    memset_0
0x1800c41d1  mov     rax, [r14+198h]
0x1800c41d8  mov     r9, rsi; nSize
0x1800c41db  mov     r8, rdi; lpBuffer
0x1800c41de  mov     rcx, rbx; hProcess
0x1800c41e1  mov     r15, rsi
0x1800c41e4  mov     edx, [rax]
0x1800c41e6  lea     rax, [rbp+NumberOfBytesRead]
0x1800c41ea  add     rdx, [rbp+arg_8]; lpBaseAddress
0x1800c41ee  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x1800c41f3  call    cs:__imp_ReadProcessMemory
0x1800c41fa  nop     dword ptr [rax+rax+00h]
0x1800c41ff  test    eax, eax
0x1800c4201  jnz     short loc_1800C423C
0x1800c4203  mov     edx, 0D24h; void *
0x1800c4208  mov     rcx, [rbp+40h]; this
0x1800c420c  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x1800c4213  mov     ebx, 80010113h
0x1800c4218  mov     r9d, ebx; char *
0x1800c421b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4220  xor     edx, edx; dwSize
0x1800c4222  mov     r8d, 8000h; dwFreeType
0x1800c4228  mov     rcx, rdi; lpAddress
0x1800c422b  call    cs:__imp_VirtualFree
0x1800c4232  nop     dword ptr [rax+rax+00h]
0x1800c4237  jmp     loc_1800C4420
0x1800c423c  cmp     r15, [rbp+NumberOfBytesRead]
0x1800c4240  jz      short loc_1800C4249
0x1800c4242  mov     edx, 0D25h
0x1800c4247  jmp     short loc_1800C4208
0x1800c4249  mov     r8, r15; Size
0x1800c424c  mov     [rbp+lpBaseAddress], 0
0x1800c4254  mov     rdx, rdi; Src
0x1800c4257  lea     rcx, [rbp+lpBaseAddress]; void *
0x1800c425b  call    memcpy_0
0x1800c4260  mov     rax, [r14+198h]
0x1800c4267  mov     rdx, [rbp+lpBaseAddress]
0x1800c426b  mov     ecx, [rax+40h]
0x1800c426e  cmp     rdx, rcx
0x1800c4271  jnb     short loc_1800C427A
0x1800c4273  mov     edx, 0D2Dh
0x1800c4278  jmp     short loc_1800C4208
0x1800c427a  mov     r9d, [rax+3Ch]; nSize
0x1800c427e  sub     rdx, rcx; lpBaseAddress
0x1800c4281  lea     rax, [rbp+NumberOfBytesRead]
0x1800c4285  mov     r8, rdi; lpBuffer
0x1800c4288  mov     rcx, rbx; hProcess
0x1800c428b  mov     qword ptr [rsp+48h+ReturnLength], rax; lpNumberOfBytesRead
0x1800c4290  call    cs:__imp_ReadProcessMemory
0x1800c4297  nop     dword ptr [rax+rax+00h]
0x1800c429c  test    eax, eax
0x1800c429e  jnz     short loc_1800C42AA
0x1800c42a0  mov     edx, 0D31h
0x1800c42a5  jmp     loc_1800C4208
0x1800c42aa  mov     rsi, [r14+198h]
0x1800c42b1  mov     eax, [rsi+3Ch]
0x1800c42b4  cmp     rax, [rbp+NumberOfBytesRead]
0x1800c42b8  jz      short loc_1800C42C4
0x1800c42ba  mov     edx, 0D33h
0x1800c42bf  jmp     loc_1800C4208
0x1800c42c4  mov     edx, [rsi+48h]
0x1800c42c7  lea     rcx, [rbp+lpBaseAddress]; void *
0x1800c42cb  add     rdx, rdi; Src
0x1800c42ce  mov     [rbp+lpBaseAddress], 0
0x1800c42d6  mov     r8, r15; Size
0x1800c42d9  call    memcpy_0
0x1800c42de  mov     edx, [rsi+44h]
0x1800c42e1  lea     rcx, [rbp+var_18]; void *
0x1800c42e5  add     rdx, rdi; Src
0x1800c42e8  mov     [rbp+var_18], 0
0x1800c42f0  mov     r8, r15; Size
0x1800c42f3  call    memcpy_0
0x1800c42f8  mov     ecx, [rsi+4Ch]
0x1800c42fb  mov     rax, [rcx+rdi]
0x1800c42ff  sub     rax, [rsi+50h]
0x1800c4303  jnz     short loc_1800C430E
0x1800c4305  mov     rax, [rcx+rdi+8]
0x1800c430a  sub     rax, [rsi+58h]
0x1800c430e  test    rax, rax
0x1800c4311  jz      short loc_1800C431D
0x1800c4313  mov     edx, 0D3Dh
0x1800c4318  jmp     loc_1800C4208
0x1800c431d  mov     r9d, [rsi+30h]; nSize
0x1800c4321  lea     rax, [rbp+NumberOfBytesRead]
0x1800c4325  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x1800c4329  mov     r8, rdi; lpBuffer
0x1800c432c  mov     rcx, rbx; hProcess
0x1800c432f  mov     qword ptr [rsp+48h+ReturnLength], rax; lpNumberOfBytesRead
0x1800c4334  call    cs:__imp_ReadProcessMemory
0x1800c433b  nop     dword ptr [rax+rax+00h]
0x1800c4340  test    eax, eax
0x1800c4342  jnz     short loc_1800C434E
0x1800c4344  mov     edx, 0D41h
0x1800c4349  jmp     loc_1800C4208
0x1800c434e  mov     rdx, [r14+198h]
0x1800c4355  mov     eax, [rdx+30h]
0x1800c4358  cmp     rax, [rbp+NumberOfBytesRead]
0x1800c435c  jz      short loc_1800C4368
0x1800c435e  mov     edx, 0D42h
0x1800c4363  jmp     loc_1800C4208
0x1800c4368  mov     eax, [rdx+34h]
0x1800c436b  mov     ecx, [rax+rdi]
0x1800c436e  mov     eax, [rdx+38h]
0x1800c4371  mov     [r13+0], ecx
0x1800c4375  mov     ecx, [rax+rdi]
0x1800c4378  mov     [r12], ecx
0x1800c437c  cmp     ecx, 0FFFFFFFFh
0x1800c437f  jnz     short loc_1800C4389
0x1800c4381  mov     dword ptr [r12], 0FFFFh
0x1800c4389  mov     r9d, [rdx+10h]; nSize
0x1800c438d  lea     rax, [rbp+NumberOfBytesRead]
0x1800c4391  mov     rdx, [rbp+var_18]; lpBaseAddress
0x1800c4395  mov     r8, rdi; lpBuffer
0x1800c4398  mov     rcx, rbx; hProcess
0x1800c439b  mov     qword ptr [rsp+48h+ReturnLength], rax; lpNumberOfBytesRead
0x1800c43a0  call    cs:__imp_ReadProcessMemory
0x1800c43a7  nop     dword ptr [rax+rax+00h]
0x1800c43ac  test    eax, eax
0x1800c43ae  jnz     short loc_1800C43BA
0x1800c43b0  mov     edx, 0D4Eh
0x1800c43b5  jmp     loc_1800C4208
0x1800c43ba  mov     rcx, [r14+198h]
0x1800c43c1  mov     eax, [rcx+10h]
0x1800c43c4  cmp     rax, [rbp+NumberOfBytesRead]
0x1800c43c8  jz      short loc_1800C43D4
0x1800c43ca  mov     edx, 0D4Fh
0x1800c43cf  jmp     loc_1800C4208
0x1800c43d4  mov     eax, [rcx+18h]
0x1800c43d7  mov     edx, [rax+rdi]
0x1800c43da  test    [rcx+2Ch], edx
0x1800c43dd  jz      short loc_1800C43E9
0x1800c43df  mov     edx, 0D53h
0x1800c43e4  jmp     loc_1800C4208
0x1800c43e9  test    [rcx+28h], edx
0x1800c43ec  jz      short loc_1800C43F8
0x1800c43ee  mov     edx, 0D54h
0x1800c43f3  jmp     loc_1800C4208
0x1800c43f8  mov     eax, [rcx+1Ch]
0x1800c43fb  xor     edx, edx; dwSize
0x1800c43fd  mov     r8d, 8000h; dwFreeType
0x1800c4403  mov     rcx, rdi; lpAddress
0x1800c4406  movups  xmm0, xmmword ptr [rax+rdi]
0x1800c440a  mov     rax, [rbp+arg_10]
0x1800c440e  movdqu  xmmword ptr [rax], xmm0
0x1800c4412  call    cs:__imp_VirtualFree
0x1800c4419  nop     dword ptr [rax+rax+00h]
0x1800c441e  xor     ebx, ebx
0x1800c4420  lea     rcx, [rbp+var_10]
0x1800c4424  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c4429  mov     eax, ebx
0x1800c442b  add     rsp, 48h
0x1800c442f  pop     r15
0x1800c4431  pop     r14
0x1800c4433  pop     r13
0x1800c4435  pop     r12
0x1800c4437  pop     rdi
0x1800c4438  pop     rsi
0x1800c4439  pop     rbx
0x1800c443a  pop     rbp
0x1800c443b  retn
```
