# WriteServiceConfig

- ea: `0x180034154`
- end: `0x1800342cb`
- name: `WriteServiceConfig`
- size: `375`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180032ad0`

## callees

- `0x18001c740`
- `0x18001c854`
- `0x18002c8d4`
- `0x180034154`
- `0x18003dc84`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800342a9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800342b2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800342a9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800342b2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003417f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003417f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800341a1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800341a1`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18003426e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18003426e`
- `KERNEL32!HeapAlloc` at `0x1800341eb`
- `KERNEL32!HeapAlloc` at `0x1800341eb`
- `KERNEL32!GetLastError` at `0x18003427d`
- `KERNEL32!GetLastError` at `0x18003427d`

## string_xrefs

- `0x180034283`: `WriteServiceConfig: ChangeServiceConfig failed, err=%ld`

## pseudocode

```c
__int64 __fastcall WriteServiceConfig(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR a2, const WCHAR *a3, int a4)
{
  unsigned int v7; // ebx
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rsi
  SC_HANDLE v10; // rbp
  __int64 v11; // rax
  __int64 v12; // rcx
  SIZE_T v13; // r14
  wchar_t *v14; // rax
  wchar_t *lpServiceStartName; // rdi
  DWORD LastError; // eax

  v7 = -2147483576;
  v8 = OpenSCManagerW(0, 0, 4u);
  v9 = v8;
  if ( v8 )
  {
    v10 = OpenServiceW(v8, L"TAPISRV", 2u);
    if ( v10 )
    {
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      do
        ++v11;
      while ( pszSrc[v11] );
      v13 = (unsigned int)(2 * (v12 + v11) + 4);
      v14 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, v13);
      lpServiceStartName = v14;
      if ( v14 )
      {
        StringCbCopyW(v14, (unsigned int)v13, pszSrc);
        StringCbCatW(lpServiceStartName, (unsigned int)v13, L"\\");
        StringCbCatW(lpServiceStartName, (unsigned int)v13, a2);
        if ( ChangeServiceConfigW(v10, 0x10u, 3 - (a4 != 0), 0xFFFFFFFF, 0, 0, 0, 0, lpServiceStartName, a3, 0) )
        {
          v7 = 0;
        }
        else
        {
          LastError = GetLastError();
          TRACELogPrint(65538, "WriteServiceConfig: ChangeServiceConfig failed, err=%ld", LastError);
        }
        ServerFree(lpServiceStartName);
      }
      else
      {
        v7 = -2147483580;
      }
      CloseServiceHandle(v10);
    }
    CloseServiceHandle(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x180034154  mov     [rsp+arg_10], r8
0x180034159  push    rbx
0x18003415a  push    rbp
0x18003415b  push    rsi
0x18003415c  push    rdi
0x18003415d  push    r12
0x18003415f  push    r13
0x180034161  push    r14
0x180034163  push    r15
0x180034165  sub     rsp, 68h
0x180034169  mov     r15, rdx
0x18003416c  mov     r12, rcx
0x18003416f  xor     edx, edx; lpDatabaseName
0x180034171  xor     ecx, ecx; lpMachineName
0x180034173  mov     r13d, r9d
0x180034176  mov     ebx, 80000048h
0x18003417b  lea     r8d, [rdx+4]; dwDesiredAccess
0x18003417f  call    cs:__imp_OpenSCManagerW
0x180034185  xor     edi, edi
0x180034187  mov     rsi, rax
0x18003418a  test    rax, rax
0x18003418d  jz      loc_1800342B8
0x180034193  lea     r8d, [rdi+2]; dwDesiredAccess
0x180034197  mov     rcx, rax; hSCManager
0x18003419a  lea     rdx, aTapisrv; "TAPISRV"
0x1800341a1  call    cs:__imp_OpenServiceW
0x1800341a7  mov     rbp, rax
0x1800341aa  test    rax, rax
0x1800341ad  jz      loc_1800342AF
0x1800341b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800341b7  mov     rcx, rax
0x1800341ba  inc     rcx
0x1800341bd  cmp     [r15+rcx*2], di
0x1800341c2  jnz     short loc_1800341BA
0x1800341c4  inc     rax
0x1800341c7  cmp     [r12+rax*2], di
0x1800341cc  jnz     short loc_1800341C4
0x1800341ce  add     rax, rcx
0x1800341d1  mov     edx, 8; dwFlags
0x1800341d6  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800341dd  lea     rax, ds:4[rax*2]
0x1800341e5  mov     r8d, eax; dwBytes
0x1800341e8  mov     r14d, eax
0x1800341eb  call    cs:__imp_HeapAlloc
0x1800341f1  mov     rdi, rax
0x1800341f4  test    rax, rax
0x1800341f7  jz      loc_1800342A1
0x1800341fd  mov     r8, r12; pszSrc
0x180034200  mov     edx, r14d; cbDest
0x180034203  mov     rcx, rax; pszDest
0x180034206  call    StringCbCopyW
0x18003420b  lea     r8, pszSrc; "\\"
0x180034212  mov     edx, r14d; cbDest
0x180034215  mov     rcx, rdi; pszDest
0x180034218  call    StringCbCatW
0x18003421d  mov     r8, r15; pszSrc
0x180034220  mov     edx, r14d; cbDest
0x180034223  mov     rcx, rdi; pszDest
0x180034226  call    StringCbCatW
0x18003422b  mov     rax, [rsp+0A8h+arg_10]
0x180034233  neg     r13d
0x180034236  mov     rcx, rbp; hService
0x180034239  sbb     r8d, r8d
0x18003423c  xor     r14d, r14d
0x18003423f  mov     [rsp+0A8h+lpDisplayName], r14; lpDisplayName
0x180034244  add     r8d, 3; dwStartType
0x180034248  mov     [rsp+0A8h+lpPassword], rax; lpPassword
0x18003424d  or      r9d, 0FFFFFFFFh; dwErrorControl
0x180034251  mov     [rsp+0A8h+lpServiceStartName], rdi; lpServiceStartName
0x180034256  mov     [rsp+0A8h+lpDependencies], r14; lpDependencies
0x18003425b  lea     edx, [r14+10h]; dwServiceType
0x18003425f  mov     [rsp+0A8h+lpdwTagId], r14; lpdwTagId
0x180034264  mov     [rsp+0A8h+lpLoadOrderGroup], r14; lpLoadOrderGroup
0x180034269  mov     [rsp+0A8h+lpBinaryPathName], r14; lpBinaryPathName
0x18003426e  call    cs:__imp_ChangeServiceConfigW
0x180034274  test    eax, eax
0x180034276  jz      short loc_18003427D
0x180034278  mov     ebx, r14d
0x18003427b  jmp     short loc_180034297
0x18003427d  call    cs:__imp_GetLastError
0x180034283  lea     rdx, aWriteserviceco; "WriteServiceConfig: ChangeServiceConfig"...
0x18003428a  mov     ecx, 10002h
0x18003428f  mov     r8d, eax
0x180034292  call    TRACELogPrint
0x180034297  mov     rcx, rdi; lpMem
0x18003429a  call    ServerFree
0x18003429f  jmp     short loc_1800342A6
0x1800342a1  mov     ebx, 80000044h
0x1800342a6  mov     rcx, rbp; hSCObject
0x1800342a9  call    cs:__imp_CloseServiceHandle
0x1800342af  mov     rcx, rsi; hSCObject
0x1800342b2  call    cs:__imp_CloseServiceHandle
0x1800342b8  mov     eax, ebx
0x1800342ba  add     rsp, 68h
0x1800342be  pop     r15
0x1800342c0  pop     r14
0x1800342c2  pop     r13
0x1800342c4  pop     r12
0x1800342c6  pop     rdi
0x1800342c7  pop     rsi
0x1800342c8  pop     rbp
0x1800342c9  pop     rbx
0x1800342ca  retn
```
