# Accommodation::FindProcess(ushort const *,void * *,int)

- ea: `0x18038138c`
- end: `0x180381530`
- name: `?FindProcess@Accommodation@@SAKPEBGPEAPEAXH@Z`
- size: `420`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180381538`

## callees

- `0x18013d330`
- `0x18038138c`
- `0x180394a10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1803814d7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1803814d7`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180381424`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18038144d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180381424`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18038144d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18038140c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18038140c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803814e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803814e4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18038147a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18038147a`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x1803814a4`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x1803814a4`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x1803813e6`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x1803813e6`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1803814c3`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1803814c3`

## pseudocode

```c
__int64 __fastcall Accommodation::FindProcess(const unsigned __int16 *a1, void **a2)
{
  DWORD CurrentProcessId; // eax
  DWORD v5; // r15d
  DWORD v6; // esi
  __int64 v7; // rbx
  DWORD v8; // ecx
  DWORD v9; // r8d
  HANDLE v10; // rax
  void *v11; // rdi
  DWORD cbNeeded; // [rsp+20h] [rbp-E0h] BYREF
  DWORD pSessionId; // [rsp+24h] [rbp-DCh] BYREF
  DWORD v15; // [rsp+28h] [rbp-D8h] BYREF
  DWORD v16; // [rsp+2Ch] [rbp-D4h] BYREF
  HMODULE hModule; // [rsp+30h] [rbp-D0h] BYREF
  DWORD idProcess[2048]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR BaseName[264]; // [rsp+2040h] [rbp+1F40h] BYREF

  *a2 = 0;
  cbNeeded = 0;
  if ( !K32EnumProcesses(idProcess, 0x2000u, &cbNeeded) )
    return 0;
  cbNeeded >>= 2;
  if ( cbNeeded > 0x800 )
    cbNeeded = 2048;
  CurrentProcessId = GetCurrentProcessId();
  pSessionId = 0;
  v5 = CurrentProcessId;
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    return 0;
  v6 = 0;
  v7 = 0;
  if ( !cbNeeded )
    return v6;
  while ( 1 )
  {
    v8 = idProcess[v7];
    v15 = 0;
    if ( !ProcessIdToSessionId(v8, &v15) )
      goto LABEL_14;
    if ( v15 != pSessionId )
      goto LABEL_14;
    v9 = idProcess[v7];
    if ( v5 == v9 )
      goto LABEL_14;
    v10 = OpenProcess(0x410u, 0, v9);
    v11 = v10;
    if ( !v10 )
      goto LABEL_14;
    hModule = 0;
    v16 = 0;
    if ( K32EnumProcessModules(v10, &hModule, 8u, &v16) )
    {
      if ( K32GetModuleBaseNameW(v11, hModule, BaseName, 0x104u) && !(unsigned int)_o__wcsicmp(BaseName, a1) )
        break;
    }
    CloseHandle(v11);
LABEL_14:
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= cbNeeded )
      return v6;
  }
  v6 = idProcess[v7];
  *a2 = v11;
  return v6;
}

```

## disassembly

```asm
0x18038138c  mov     [rsp-8+arg_10], rbx
0x180381391  push    rbp
0x180381392  push    rsi
0x180381393  push    rdi
0x180381394  push    r12
0x180381396  push    r13
0x180381398  push    r14
0x18038139a  push    r15
0x18038139c  lea     rbp, [rsp-2160h]
0x1803813a4  mov     eax, 2260h
0x1803813a9  call    _alloca_probe
0x1803813ae  sub     rsp, rax
0x1803813b1  mov     rax, cs:__security_cookie
0x1803813b8  xor     rax, rsp
0x1803813bb  mov     [rbp+2190h+var_40], rax
0x1803813c2  mov     r12, rdx
0x1803813c5  mov     qword ptr [rdx], 0
0x1803813cc  mov     r13, rcx
0x1803813cf  mov     [rsp+2290h+cbNeeded], 0
0x1803813d7  mov     edx, 2000h; cb
0x1803813dc  lea     rcx, [rsp+2290h+idProcess]; lpidProcess
0x1803813e1  lea     r8, [rsp+2290h+cbNeeded]; lpcbNeeded
0x1803813e6  call    cs:__imp_K32EnumProcesses
0x1803813ec  test    eax, eax
0x1803813ee  jz      loc_180381504
0x1803813f4  mov     eax, [rsp+2290h+cbNeeded]
0x1803813f8  mov     ecx, 800h
0x1803813fd  shr     eax, 2
0x180381400  mov     [rsp+2290h+cbNeeded], eax
0x180381404  cmp     eax, ecx
0x180381406  jbe     short loc_18038140C
0x180381408  mov     [rsp+2290h+cbNeeded], ecx
0x18038140c  call    cs:__imp_GetCurrentProcessId
0x180381412  lea     rdx, [rsp+2290h+pSessionId]; pSessionId
0x180381417  mov     [rsp+2290h+pSessionId], 0
0x18038141f  mov     ecx, eax; dwProcessId
0x180381421  mov     r15d, eax
0x180381424  call    cs:__imp_ProcessIdToSessionId
0x18038142a  test    eax, eax
0x18038142c  jz      loc_180381504
0x180381432  xor     esi, esi
0x180381434  xor     ebx, ebx
0x180381436  cmp     [rsp+2290h+cbNeeded], ebx
0x18038143a  jbe     loc_180381500
0x180381440  mov     ecx, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x180381444  lea     rdx, [rsp+2290h+var_2268]; pSessionId
0x180381449  mov     [rsp+2290h+var_2268], esi
0x18038144d  call    cs:__imp_ProcessIdToSessionId
0x180381453  test    eax, eax
0x180381455  jz      loc_1803814EA
0x18038145b  mov     eax, [rsp+2290h+pSessionId]
0x18038145f  cmp     [rsp+2290h+var_2268], eax
0x180381463  jnz     loc_1803814EA
0x180381469  mov     r8d, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x18038146e  cmp     r15d, r8d
0x180381471  jz      short loc_1803814EA
0x180381473  xor     edx, edx; bInheritHandle
0x180381475  mov     ecx, 410h; dwDesiredAccess
0x18038147a  call    cs:__imp_OpenProcess
0x180381480  mov     rdi, rax
0x180381483  test    rax, rax
0x180381486  jz      short loc_1803814EA
0x180381488  lea     r9, [rsp+2290h+var_2264]; lpcbNeeded
0x18038148d  mov     [rsp+2290h+hModule], rsi
0x180381492  mov     r8d, 8; cb
0x180381498  mov     [rsp+2290h+var_2264], esi
0x18038149c  lea     rdx, [rsp+2290h+hModule]; lphModule
0x1803814a1  mov     rcx, rax; hProcess
0x1803814a4  call    cs:__imp_K32EnumProcessModules
0x1803814aa  test    eax, eax
0x1803814ac  jz      short loc_1803814E1
0x1803814ae  mov     rdx, [rsp+2290h+hModule]; hModule
0x1803814b3  lea     r8, [rbp+2190h+BaseName]; lpBaseName
0x1803814ba  mov     r9d, 104h; nSize
0x1803814c0  mov     rcx, rdi; hProcess
0x1803814c3  call    cs:__imp_K32GetModuleBaseNameW
0x1803814c9  test    eax, eax
0x1803814cb  jz      short loc_1803814E1
0x1803814cd  mov     rdx, r13
0x1803814d0  lea     rcx, [rbp+2190h+BaseName]
0x1803814d7  call    cs:__imp__o__wcsicmp
0x1803814dd  test    eax, eax
0x1803814df  jz      short loc_1803814F8
0x1803814e1  mov     rcx, rdi; hObject
0x1803814e4  call    cs:__imp_CloseHandle
0x1803814ea  inc     ebx
0x1803814ec  cmp     ebx, [rsp+2290h+cbNeeded]
0x1803814f0  jb      loc_180381440
0x1803814f6  jmp     short loc_180381500
0x1803814f8  mov     esi, [rsp+rbx*4+2290h+idProcess]
0x1803814fc  mov     [r12], rdi
0x180381500  mov     eax, esi
0x180381502  jmp     short loc_180381506
0x180381504  xor     eax, eax
0x180381506  mov     rcx, [rbp+2190h+var_40]
0x18038150d  xor     rcx, rsp; StackCookie
0x180381510  call    __security_check_cookie
0x180381515  mov     rbx, [rsp+2290h+arg_10]
0x18038151d  add     rsp, 2260h
0x180381524  pop     r15
0x180381526  pop     r14
0x180381528  pop     r13
0x18038152a  pop     r12
0x18038152c  pop     rdi
0x18038152d  pop     rsi
0x18038152e  pop     rbp
0x18038152f  retn
```
