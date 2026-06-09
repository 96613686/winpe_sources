# CProcess::GetServerIPIDForProxy(unsigned __int64,_GUID *,ulong *,ulong *)

- ea: `0x1800be64c`
- end: `0x1800bea06`
- name: `?GetServerIPIDForProxy@CProcess@@QEAAJ_KPEAU_GUID@@PEAK2@Z`
- size: `954`
- prototype: `__int64 __fastcall(CProcess *__hidden this, unsigned __int64, struct _GUID *, unsigned int *, SIZE_T NumberOfBytesRead)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800eaa90`

## callees

- `0x18000fe24`
- `0x18001ec28`
- `0x18002ba28`
- `0x18002ed28`
- `0x18008cd90`
- `0x1800b3128`
- `0x1800be64c`
- `0x18010a084`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x1800be6d7`
- `ntdll!NtQueryInformationProcess` at `0x1800be6d7`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800be78d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800be78d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800be813`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800be9e2`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800be813`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800be9e2`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800be7e1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800be872`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800be910`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800be976`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800be7e1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800be872`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800be910`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800be976`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800be68e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800be68e`

## string_xrefs

- `0x1800be6aa`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x1800be6e5`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x1800be714`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x1800be7f4`: `onecore\com\combase\rpcss\objex\process.cxx`

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
0x1800be64c  mov     [rsp-40h+arg_10], r8
0x1800be651  mov     [rsp-40h+arg_8], rdx
0x1800be656  push    rbp
0x1800be657  push    rbx
0x1800be658  push    rsi
0x1800be659  push    rdi
0x1800be65a  push    r12
0x1800be65c  push    r13
0x1800be65e  push    r14
0x1800be660  push    r15
0x1800be662  mov     rbp, rsp
0x1800be665  sub     rsp, 48h
0x1800be669  mov     r12, [rbp+NumberOfBytesRead]
0x1800be66d  xorps   xmm0, xmm0
0x1800be670  movups  xmmword ptr [r8], xmm0
0x1800be674  mov     r8d, [rcx+58h]; dwProcessId
0x1800be678  mov     r14, rcx
0x1800be67b  xor     edi, edi
0x1800be67d  mov     ecx, 410h; dwDesiredAccess
0x1800be682  xor     edx, edx; bInheritHandle
0x1800be684  mov     [r12], edi
0x1800be688  mov     r13, r9
0x1800be68b  mov     [r9], edi
0x1800be68e  call    cs:__imp_OpenProcess
0x1800be694  mov     rbx, rax
0x1800be697  mov     [rbp+var_10], rax
0x1800be69b  inc     rax
0x1800be69e  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800be6a4  jnz     short loc_1800BE6BD
0x1800be6a6  mov     rcx, [rbp+40h]; this
0x1800be6aa  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x1800be6b1  mov     edx, 0D0Dh; void *
0x1800be6b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800be6bb  jmp     short loc_1800BE6F9
0x1800be6bd  mov     r9d, 8; ProcessInformationLength
0x1800be6c3  mov     [rbp+ProcessInformation], rdi
0x1800be6c7  lea     r8, [rbp+ProcessInformation]; ProcessInformation
0x1800be6cb  mov     qword ptr [rsp+48h+ReturnLength], rdi; int
0x1800be6d0  mov     rcx, rbx; ProcessHandle
0x1800be6d3  lea     edx, [r9-1]; ProcessInformationClass
0x1800be6d7  call    cs:__imp_NtQueryInformationProcess
0x1800be6dd  test    eax, eax
0x1800be6df  jns     short loc_1800BE700
0x1800be6e1  mov     rcx, [rbp+40h]; this
0x1800be6e5  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x1800be6ec  mov     r9d, eax; char *
0x1800be6ef  mov     edx, 0D12h; void *
0x1800be6f4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800be6f9  mov     ebx, eax
0x1800be6fb  jmp     loc_1800BE9EA
0x1800be700  cmp     [rbp+ProcessInformation], rdi
0x1800be704  jnz     short loc_1800BE728
0x1800be706  mov     ebx, 80070005h
0x1800be70b  mov     edx, 0D13h; void *
0x1800be710  mov     rcx, [rbp+40h]; this
0x1800be714  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x1800be71b  mov     r9d, ebx; char *
0x1800be71e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be723  jmp     loc_1800BE9EA
0x1800be728  movzx   ecx, word ptr [r14+1ACh]; unsigned __int16
0x1800be730  call    ?GetArchitecturePointerSizeInBytes@@YAKG@Z; GetArchitecturePointerSizeInBytes(ushort)
0x1800be735  mov     rcx, [r14+198h]
0x1800be73c  mov     esi, eax
0x1800be73e  mov     r8d, [rcx+30h]
0x1800be742  mov     r9d, [rcx+10h]
0x1800be746  mov     r10d, r9d
0x1800be749  mov     edx, [rcx+3Ch]
0x1800be74c  cmp     r9d, r8d
0x1800be74f  cmovbe  r10d, r8d
0x1800be753  cmp     edx, r10d
0x1800be756  jbe     short loc_1800BE75C
0x1800be758  mov     ecx, edx
0x1800be75a  jmp     short loc_1800BE766
0x1800be75c  cmp     r9d, r8d
0x1800be75f  mov     ecx, r8d
0x1800be762  cmova   ecx, r9d
0x1800be766  cmp     esi, ecx
0x1800be768  jbe     short loc_1800BE76F
0x1800be76a  mov     rdx, rsi
0x1800be76d  jmp     short loc_1800BE77E
0x1800be76f  cmp     edx, r10d
0x1800be772  ja      short loc_1800BE77E
0x1800be774  cmp     r9d, r8d
0x1800be777  mov     edx, r8d
0x1800be77a  cmova   edx, r9d; dwSize
0x1800be77e  xor     ecx, ecx; lpAddress
0x1800be780  mov     r15d, edx
0x1800be783  mov     r8d, 3000h; flAllocationType
0x1800be789  lea     r9d, [rcx+4]; flProtect
0x1800be78d  call    cs:__imp_VirtualAlloc
0x1800be793  mov     rdi, rax
0x1800be796  test    rax, rax
0x1800be799  jnz     short loc_1800BE7AA
0x1800be79b  mov     ebx, 8007000Eh
0x1800be7a0  mov     edx, 0D1Ch
0x1800be7a5  jmp     loc_1800BE710
0x1800be7aa  mov     r8, r15; Size
0x1800be7ad  mov     [rbp+NumberOfBytesRead], 0
0x1800be7b5  xor     edx, edx; Val
0x1800be7b7  mov     rcx, rdi; void *
0x1800be7ba  call    memset_0
0x1800be7bf  mov     rax, [r14+198h]
0x1800be7c6  mov     r9, rsi; nSize
0x1800be7c9  mov     r8, rdi; lpBuffer
0x1800be7cc  mov     rcx, rbx; hProcess
0x1800be7cf  mov     r15, rsi
0x1800be7d2  mov     edx, [rax]
0x1800be7d4  lea     rax, [rbp+NumberOfBytesRead]
0x1800be7d8  add     rdx, [rbp+arg_8]; lpBaseAddress
0x1800be7dc  mov     qword ptr [rsp+48h+ReturnLength], rax; int
0x1800be7e1  call    cs:__imp_ReadProcessMemory
0x1800be7e7  test    eax, eax
0x1800be7e9  jnz     short loc_1800BE81E
0x1800be7eb  mov     edx, 0D24h; void *
0x1800be7f0  mov     rcx, [rbp+40h]; this
0x1800be7f4  lea     r8, aOnecoreComComb_49; "onecore\\com\\combase\\rpcss\\objex\\pr"...
0x1800be7fb  mov     ebx, 80010113h
0x1800be800  mov     r9d, ebx; char *
0x1800be803  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be808  xor     edx, edx; dwSize
0x1800be80a  mov     r8d, 8000h; dwFreeType
0x1800be810  mov     rcx, rdi; lpAddress
0x1800be813  call    cs:__imp_VirtualFree
0x1800be819  jmp     loc_1800BE9EA
0x1800be81e  cmp     r15, [rbp+NumberOfBytesRead]
0x1800be822  jz      short loc_1800BE82B
0x1800be824  mov     edx, 0D25h
0x1800be829  jmp     short loc_1800BE7F0
0x1800be82b  mov     r8, r15; Size
0x1800be82e  mov     [rbp+lpBaseAddress], 0
0x1800be836  mov     rdx, rdi; Src
0x1800be839  lea     rcx, [rbp+lpBaseAddress]; void *
0x1800be83d  call    memcpy_0
0x1800be842  mov     rax, [r14+198h]
0x1800be849  mov     rdx, [rbp+lpBaseAddress]
0x1800be84d  mov     ecx, [rax+40h]
0x1800be850  cmp     rdx, rcx
0x1800be853  jnb     short loc_1800BE85C
0x1800be855  mov     edx, 0D2Dh
0x1800be85a  jmp     short loc_1800BE7F0
0x1800be85c  mov     r9d, [rax+3Ch]; nSize
0x1800be860  sub     rdx, rcx; lpBaseAddress
0x1800be863  lea     rax, [rbp+NumberOfBytesRead]
0x1800be867  mov     r8, rdi; lpBuffer
0x1800be86a  mov     rcx, rbx; hProcess
0x1800be86d  mov     qword ptr [rsp+48h+ReturnLength], rax; lpNumberOfBytesRead
0x1800be872  call    cs:__imp_ReadProcessMemory
0x1800be878  test    eax, eax
0x1800be87a  jnz     short loc_1800BE886
0x1800be87c  mov     edx, 0D31h
0x1800be881  jmp     loc_1800BE7F0
0x1800be886  mov     rsi, [r14+198h]
0x1800be88d  mov     eax, [rsi+3Ch]
0x1800be890  cmp     rax, [rbp+NumberOfBytesRead]
0x1800be894  jz      short loc_1800BE8A0
0x1800be896  mov     edx, 0D33h
0x1800be89b  jmp     loc_1800BE7F0
0x1800be8a0  mov     edx, [rsi+48h]
0x1800be8a3  lea     rcx, [rbp+lpBaseAddress]; void *
0x1800be8a7  add     rdx, rdi; Src
0x1800be8aa  mov     [rbp+lpBaseAddress], 0
0x1800be8b2  mov     r8, r15; Size
0x1800be8b5  call    memcpy_0
0x1800be8ba  mov     edx, [rsi+44h]
0x1800be8bd  lea     rcx, [rbp+var_18]; void *
0x1800be8c1  add     rdx, rdi; Src
0x1800be8c4  mov     [rbp+var_18], 0
0x1800be8cc  mov     r8, r15; Size
0x1800be8cf  call    memcpy_0
0x1800be8d4  mov     ecx, [rsi+4Ch]
0x1800be8d7  mov     rax, [rcx+rdi]
0x1800be8db  sub     rax, [rsi+50h]
0x1800be8df  jnz     short loc_1800BE8EA
0x1800be8e1  mov     rax, [rcx+rdi+8]
0x1800be8e6  sub     rax, [rsi+58h]
0x1800be8ea  test    rax, rax
0x1800be8ed  jz      short loc_1800BE8F9
0x1800be8ef  mov     edx, 0D3Dh
0x1800be8f4  jmp     loc_1800BE7F0
0x1800be8f9  mov     r9d, [rsi+30h]; nSize
0x1800be8fd  lea     rax, [rbp+NumberOfBytesRead]
0x1800be901  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x1800be905  mov     r8, rdi; lpBuffer
0x1800be908  mov     rcx, rbx; hProcess
0x1800be90b  mov     qword ptr [rsp+48h+ReturnLength], rax; lpNumberOfBytesRead
0x1800be910  call    cs:__imp_ReadProcessMemory
0x1800be916  test    eax, eax
0x1800be918  jnz     short loc_1800BE924
0x1800be91a  mov     edx, 0D41h
0x1800be91f  jmp     loc_1800BE7F0
0x1800be924  mov     rdx, [r14+198h]
0x1800be92b  mov     eax, [rdx+30h]
0x1800be92e  cmp     rax, [rbp+NumberOfBytesRead]
0x1800be932  jz      short loc_1800BE93E
0x1800be934  mov     edx, 0D42h
0x1800be939  jmp     loc_1800BE7F0
0x1800be93e  mov     eax, [rdx+34h]
0x1800be941  mov     ecx, [rax+rdi]
0x1800be944  mov     eax, [rdx+38h]
0x1800be947  mov     [r13+0], ecx
0x1800be94b  mov     ecx, [rax+rdi]
0x1800be94e  mov     [r12], ecx
0x1800be952  cmp     ecx, 0FFFFFFFFh
0x1800be955  jnz     short loc_1800BE95F
0x1800be957  mov     dword ptr [r12], 0FFFFh
0x1800be95f  mov     r9d, [rdx+10h]; nSize
0x1800be963  lea     rax, [rbp+NumberOfBytesRead]
0x1800be967  mov     rdx, [rbp+var_18]; lpBaseAddress
0x1800be96b  mov     r8, rdi; lpBuffer
0x1800be96e  mov     rcx, rbx; hProcess
0x1800be971  mov     qword ptr [rsp+48h+ReturnLength], rax; lpNumberOfBytesRead
0x1800be976  call    cs:__imp_ReadProcessMemory
0x1800be97c  test    eax, eax
0x1800be97e  jnz     short loc_1800BE98A
0x1800be980  mov     edx, 0D4Eh
0x1800be985  jmp     loc_1800BE7F0
0x1800be98a  mov     rcx, [r14+198h]
0x1800be991  mov     eax, [rcx+10h]
0x1800be994  cmp     rax, [rbp+NumberOfBytesRead]
0x1800be998  jz      short loc_1800BE9A4
0x1800be99a  mov     edx, 0D4Fh
0x1800be99f  jmp     loc_1800BE7F0
0x1800be9a4  mov     eax, [rcx+18h]
0x1800be9a7  mov     edx, [rax+rdi]
0x1800be9aa  test    [rcx+2Ch], edx
0x1800be9ad  jz      short loc_1800BE9B9
0x1800be9af  mov     edx, 0D53h
0x1800be9b4  jmp     loc_1800BE7F0
0x1800be9b9  test    [rcx+28h], edx
0x1800be9bc  jz      short loc_1800BE9C8
0x1800be9be  mov     edx, 0D54h
0x1800be9c3  jmp     loc_1800BE7F0
0x1800be9c8  mov     eax, [rcx+1Ch]
0x1800be9cb  xor     edx, edx; dwSize
0x1800be9cd  mov     r8d, 8000h; dwFreeType
0x1800be9d3  mov     rcx, rdi; lpAddress
0x1800be9d6  movups  xmm0, xmmword ptr [rax+rdi]
0x1800be9da  mov     rax, [rbp+arg_10]
0x1800be9de  movdqu  xmmword ptr [rax], xmm0
0x1800be9e2  call    cs:__imp_VirtualFree
0x1800be9e8  xor     ebx, ebx
0x1800be9ea  lea     rcx, [rbp+var_10]
0x1800be9ee  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800be9f3  mov     eax, ebx
0x1800be9f5  add     rsp, 48h
0x1800be9f9  pop     r15
0x1800be9fb  pop     r14
0x1800be9fd  pop     r13
0x1800be9ff  pop     r12
0x1800bea01  pop     rdi
0x1800bea02  pop     rsi
0x1800bea03  pop     rbx
0x1800bea04  pop     rbp
0x1800bea05  retn
```
