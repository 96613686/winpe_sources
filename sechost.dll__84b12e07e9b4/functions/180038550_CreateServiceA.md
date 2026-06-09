# CreateServiceA

- ea: `0x180038550`
- end: `0x180038bb3`
- name: `CreateServiceA`
- size: `1635`
- prototype: `SC_HANDLE __stdcall(SC_HANDLE hSCManager, LPCSTR lpServiceName, LPCSTR lpDisplayName, DWORD dwDesiredAccess, DWORD dwServiceType, DWORD dwStartType, DWORD dwErrorControl, LPCSTR lpBinaryPathName, LPCSTR lpLoadOrderGroup, LPDWORD lpdwTagId, LPCSTR lpDependencies, LPCSTR lpServiceStartName, LPCSTR lpPassword)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1800198d8`
- `0x180038550`
- `0x18003c650`
- `0x18004a88c`
- `0x18004a8c0`
- `0x18004aa18`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800385e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003862f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038b8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800385e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003862f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038b8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180038705`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180038705`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038669`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038669`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038623`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800386dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038623`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800386dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b82`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180038719`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180038719`
- `RPCRT4!NdrClientCall2` at `0x1800389c5`
- `RPCRT4!NdrClientCall2` at `0x180038ad7`
- `RPCRT4!NdrClientCall2` at `0x1800389c5`
- `RPCRT4!NdrClientCall2` at `0x180038ad7`

## pseudocode

```c
SC_HANDLE __stdcall CreateServiceA(
        SC_HANDLE hSCManager,
        LPCSTR lpServiceName,
        LPCSTR lpDisplayName,
        DWORD dwDesiredAccess,
        DWORD dwServiceType,
        DWORD dwStartType,
        DWORD dwErrorControl,
        LPCSTR lpBinaryPathName,
        LPCSTR lpLoadOrderGroup,
        LPDWORD lpdwTagId,
        LPCSTR lpDependencies,
        LPCSTR lpServiceStartName,
        LPCSTR lpPassword)
{
  HLOCAL v16; // rsi
  unsigned int v17; // r14d
  DWORD v19; // ebx
  const char *v20; // rbx
  CLIENT_CALL_RETURN v21; // rbx
  __int64 v22; // rax
  HANDLE CurrentProcess; // rax
  __int64 v24; // [rsp+28h] [rbp-110h]
  __int64 v25; // [rsp+28h] [rbp-110h]
  __int64 v26; // [rsp+30h] [rbp-108h]
  __int64 v27; // [rsp+30h] [rbp-108h]
  __int64 v28; // [rsp+38h] [rbp-100h]
  __int64 v29; // [rsp+38h] [rbp-100h]
  __int64 v30; // [rsp+40h] [rbp-F8h]
  __int64 v31; // [rsp+40h] [rbp-F8h]
  __int64 v32; // [rsp+68h] [rbp-D0h]
  __int64 v33; // [rsp+68h] [rbp-D0h]
  __int64 v34; // [rsp+80h] [rbp-B8h]
  __int64 v35; // [rsp+80h] [rbp-B8h]
  __int64 v36; // [rsp+90h] [rbp-A8h] BYREF
  int v37; // [rsp+98h] [rbp-A0h] BYREF
  unsigned int v38; // [rsp+9Ch] [rbp-9Ch]
  HLOCAL hMem; // [rsp+A0h] [rbp-98h] BYREF
  HLOCAL v40; // [rsp+A8h] [rbp-90h] BYREF
  HLOCAL v41; // [rsp+B0h] [rbp-88h]
  SC_HANDLE v42; // [rsp+B8h] [rbp-80h] BYREF
  HLOCAL v43; // [rsp+C0h] [rbp-78h] BYREF
  HLOCAL v44; // [rsp+C8h] [rbp-70h] BYREF
  HLOCAL v45; // [rsp+D0h] [rbp-68h] BYREF
  HLOCAL v46; // [rsp+D8h] [rbp-60h] BYREF
  HLOCAL v47; // [rsp+E0h] [rbp-58h] BYREF
  CLIENT_CALL_RETURN v48; // [rsp+E8h] [rbp-50h]
  CLIENT_CALL_RETURN v49; // [rsp+F0h] [rbp-48h]

  v42 = 0;
  hMem = 0;
  v40 = 0;
  v37 = 0;
  v16 = 0;
  v41 = 0;
  v17 = 0;
  v38 = 0;
  WORD2(v36) = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  if ( lpPassword )
  {
    if ( !ScConvertToUnicode((unsigned __int16 **)&hMem, lpPassword) )
    {
      SetLastError(8u);
      return 0;
    }
    v19 = ScEncryptPassword(hSCManager, hMem, &v40, &v37);
    LODWORD(v36) = v19;
    LocalFree(hMem);
    if ( v19 )
    {
      SetLastError(v19);
      return 0;
    }
  }
  v20 = lpDependencies;
  if ( !lpDependencies )
  {
LABEL_16:
    if ( (dwServiceType & 0x30) != 0 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( !(unsigned int)IsWow64Process2(CurrentProcess, (char *)&v36 + 4, 0) )
        return 0;
    }
    if ( WORD2(v36) )
    {
      if ( lpServiceName && !ScConvertToUnicode((unsigned __int16 **)&v43, lpServiceName) )
      {
        LODWORD(v21.Pointer) = 8;
        goto LABEL_38;
      }
      if ( lpDisplayName && !ScConvertToUnicode((unsigned __int16 **)&v44, lpDisplayName) )
      {
        LODWORD(v21.Pointer) = 8;
        goto LABEL_38;
      }
      if ( lpBinaryPathName && !ScConvertToUnicode((unsigned __int16 **)&v45, lpBinaryPathName) )
      {
        LODWORD(v21.Pointer) = 8;
        goto LABEL_38;
      }
      if ( lpLoadOrderGroup && !ScConvertToUnicode((unsigned __int16 **)&v46, lpLoadOrderGroup) )
      {
        LODWORD(v21.Pointer) = 8;
        goto LABEL_38;
      }
      if ( lpServiceStartName && !ScConvertToUnicode((unsigned __int16 **)&v47, lpServiceStartName) )
      {
        LODWORD(v21.Pointer) = 8;
        goto LABEL_38;
      }
      LODWORD(v21.Pointer) = RCreateWowService(
                               (_DWORD)hSCManager,
                               (_DWORD)v43,
                               (_DWORD)v44,
                               dwDesiredAccess,
                               dwServiceType,
                               dwStartType,
                               dwErrorControl,
                               (__int64)v45,
                               (__int64)v46,
                               (__int64)lpdwTagId,
                               (__int64)v16,
                               v17,
                               (__int64)v47,
                               (__int64)v40,
                               v37,
                               SWORD2(v36),
                               (__int64)&v42);
      LODWORD(v36) = v21.Pointer;
      if ( LODWORD(v21.Pointer) != 120 )
        goto LABEL_38;
      v48.Simple = 0;
      LODWORD(v35) = v37;
      LODWORD(v33) = v17;
      LODWORD(v31) = dwErrorControl;
      LODWORD(v29) = dwStartType;
      LODWORD(v27) = dwServiceType;
      LODWORD(v25) = dwDesiredAccess;
      v21.Pointer = NdrClientCall2(
                      &pStubDescriptor,
                      &byte_180060B88,
                      hSCManager,
                      lpServiceName,
                      lpDisplayName,
                      v25,
                      v27,
                      v29,
                      v31,
                      lpBinaryPathName,
                      lpLoadOrderGroup,
                      lpdwTagId,
                      v16,
                      v33,
                      lpServiceStartName,
                      v40,
                      v35,
                      &v42,
                      v36).Pointer;
      v48.Pointer = v21.Pointer;
      LODWORD(v36) = v21.Pointer;
      if ( LODWORD(v21.Pointer) != 120 )
        goto LABEL_38;
    }
    v49.Simple = 0;
    LODWORD(v34) = v37;
    LODWORD(v32) = v17;
    LODWORD(v30) = dwErrorControl;
    LODWORD(v28) = dwStartType;
    LODWORD(v26) = dwServiceType;
    LODWORD(v24) = dwDesiredAccess;
    v49.Pointer = NdrClientCall2(
                    &pStubDescriptor,
                    &byte_1800605EA,
                    hSCManager,
                    lpServiceName,
                    lpDisplayName,
                    v24,
                    v26,
                    v28,
                    v30,
                    lpBinaryPathName,
                    lpLoadOrderGroup,
                    lpdwTagId,
                    v16,
                    v32,
                    lpServiceStartName,
                    v40,
                    v34,
                    &v42,
                    v36).Pointer;
    LODWORD(v21.Pointer) = v49.Pointer;
    goto LABEL_38;
  }
  v17 = 2 * ScAStrArraySize(lpDependencies);
  v38 = v17;
  v16 = LocalAlloc(0x40u, v17);
  v41 = v16;
  if ( v16 )
  {
    if ( v17 > 2 )
    {
      while ( *v20 )
      {
        hMem = 0;
        if ( !ScConvertToUnicode((unsigned __int16 **)&hMem, v20) )
        {
          LODWORD(v21.Pointer) = 8;
          goto LABEL_38;
        }
        ScAddWStrToWStrArray(v16, hMem);
        LocalFree(hMem);
        v22 = -1;
        do
          ++v22;
        while ( v20[v22] );
        v20 += v22 + 1;
      }
    }
    goto LABEL_16;
  }
  LODWORD(v21.Pointer) = 8;
LABEL_38:
  if ( v16 )
    LocalFree(v16);
  if ( v40 )
    LocalFree(v40);
  if ( v43 )
    LocalFree(v43);
  if ( v44 )
    LocalFree(v44);
  if ( v45 )
    LocalFree(v45);
  if ( v46 )
    LocalFree(v46);
  if ( v47 )
    LocalFree(v47);
  if ( !LODWORD(v21.Pointer) )
    return v42;
  SetLastError((DWORD)v21.Pointer);
  return 0;
}

```

## disassembly

```asm
0x180038550  mov     rax, rsp
0x180038553  mov     [rax+20h], r9d
0x180038557  mov     [rax+18h], r8
0x18003855b  mov     [rax+10h], rdx
0x18003855f  mov     [rax+8], rcx
0x180038563  push    rbx
0x180038564  push    rsi
0x180038565  push    rdi
0x180038566  push    r12
0x180038568  push    r13
0x18003856a  push    r14
0x18003856c  push    r15
0x18003856e  sub     rsp, 100h
0x180038575  mov     r15, r8
0x180038578  mov     r12, rdx
0x18003857b  mov     rbx, rcx
0x18003857e  xor     edi, edi
0x180038580  mov     [rax-80h], rdi
0x180038584  mov     [rax-98h], rdi
0x18003858b  mov     [rax-90h], rdi
0x180038592  mov     [rax-0A0h], edi
0x180038598  mov     esi, edi
0x18003859a  mov     [rax-88h], rdi
0x1800385a1  mov     r14d, edi
0x1800385a4  mov     [rax-9Ch], edi
0x1800385aa  mov     [rax-0A4h], di
0x1800385b1  mov     [rax-78h], rdi
0x1800385b5  mov     [rax-70h], rdi
0x1800385b9  mov     [rax-68h], rdi
0x1800385bd  mov     [rax-60h], rdi
0x1800385c1  mov     [rax-58h], rdi
0x1800385c5  mov     rdx, [rsp+138h+lpPassword]; char *
0x1800385cd  test    rdx, rdx
0x1800385d0  jz      short loc_18003863C
0x1800385d2  lea     rcx, [rax-98h]; unsigned __int16 **
0x1800385d9  call    ?ScConvertToUnicode@@YAHPEAPEAGPEBD@Z; ScConvertToUnicode(ushort * *,char const *)
0x1800385de  test    eax, eax
0x1800385e0  jnz     short loc_1800385F2
0x1800385e2  lea     ecx, [rdi+8]; dwErrCode
0x1800385e5  call    cs:__imp_SetLastError
0x1800385eb  xor     eax, eax
0x1800385ed  jmp     loc_180038BA0
0x1800385f2  lea     r9, [rsp+138h+var_A0]
0x1800385fa  lea     r8, [rsp+138h+var_90]
0x180038602  mov     rdx, [rsp+138h+hMem]
0x18003860a  mov     rcx, rbx
0x18003860d  call    ScEncryptPassword
0x180038612  mov     ebx, eax
0x180038614  mov     [rsp+138h+var_A8], eax
0x18003861b  mov     rcx, [rsp+138h+hMem]; hMem
0x180038623  call    cs:__imp_LocalFree
0x180038629  test    ebx, ebx
0x18003862b  jz      short loc_18003863C
0x18003862d  mov     ecx, ebx; dwErrCode
0x18003862f  call    cs:__imp_SetLastError
0x180038635  xor     eax, eax
0x180038637  jmp     loc_180038BA0
0x18003863c  mov     rbx, [rsp+138h+lpDependencies]
0x180038644  test    rbx, rbx
0x180038647  jz      loc_1800386F7
0x18003864d  mov     rcx, rbx
0x180038650  call    ScAStrArraySize
0x180038655  add     eax, eax
0x180038657  mov     r14d, eax
0x18003865a  mov     [rsp+138h+var_9C], r14d
0x180038662  mov     edx, eax; uBytes
0x180038664  mov     ecx, 40h ; '@'; uFlags
0x180038669  call    cs:__imp_LocalAlloc
0x18003866f  mov     rsi, rax
0x180038672  mov     [rsp+138h+var_88], rax
0x18003867a  test    rax, rax
0x18003867d  jnz     short loc_18003868E
0x18003867f  lea     ebx, [rax+8]
0x180038682  mov     [rsp+138h+var_A8], ebx
0x180038689  jmp     loc_180038B08
0x18003868e  cmp     r14d, 2
0x180038692  jbe     short loc_1800386F7
0x180038694  cmp     [rbx], dil
0x180038697  jz      short loc_1800386F7
0x180038699  mov     [rsp+138h+hMem], rdi
0x1800386a1  mov     rdx, rbx; char *
0x1800386a4  lea     rcx, [rsp+138h+hMem]; unsigned __int16 **
0x1800386ac  call    ?ScConvertToUnicode@@YAHPEAPEAGPEBD@Z; ScConvertToUnicode(ushort * *,char const *)
0x1800386b1  test    eax, eax
0x1800386b3  jnz     short loc_1800386C4
0x1800386b5  lea     ebx, [rax+8]
0x1800386b8  mov     [rsp+138h+var_A8], ebx
0x1800386bf  jmp     loc_180038B08
0x1800386c4  mov     rdx, [rsp+138h+hMem]
0x1800386cc  mov     rcx, rsi
0x1800386cf  call    ScAddWStrToWStrArray
0x1800386d4  mov     rcx, [rsp+138h+hMem]; hMem
0x1800386dc  call    cs:__imp_LocalFree
0x1800386e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800386e6  inc     rax
0x1800386e9  cmp     [rbx+rax], dil
0x1800386ed  jnz     short loc_1800386E6
0x1800386ef  inc     rbx
0x1800386f2  add     rbx, rax
0x1800386f5  jmp     short loc_180038694
0x1800386f7  mov     r13d, [rsp+138h+dwServiceType]
0x1800386ff  test    r13b, 30h
0x180038703  jz      short loc_18003872A
0x180038705  call    cs:__imp_GetCurrentProcess
0x18003870b  mov     rcx, rax
0x18003870e  xor     r8d, r8d
0x180038711  lea     rdx, [rsp+138h+var_A4]
0x180038719  call    cs:__imp_IsWow64Process2
0x18003871f  test    eax, eax
0x180038721  jnz     short loc_18003872A
0x180038723  xor     eax, eax
0x180038725  jmp     loc_180038BA0
0x18003872a  cmp     [rsp+138h+var_A4], di
0x180038732  jz      loc_180038A22
0x180038738  test    r12, r12
0x18003873b  jz      short loc_180038760
0x18003873d  mov     rdx, r12; char *
0x180038740  lea     rcx, [rsp+138h+var_78]; unsigned __int16 **
0x180038748  call    ?ScConvertToUnicode@@YAHPEAPEAGPEBD@Z; ScConvertToUnicode(ushort * *,char const *)
0x18003874d  test    eax, eax
0x18003874f  jnz     short loc_180038760
0x180038751  lea     ebx, [rax+8]
0x180038754  mov     [rsp+138h+var_A8], ebx
0x18003875b  jmp     loc_180038B08
0x180038760  test    r15, r15
0x180038763  jz      short loc_180038788
0x180038765  mov     rdx, r15; char *
0x180038768  lea     rcx, [rsp+138h+var_70]; unsigned __int16 **
0x180038770  call    ?ScConvertToUnicode@@YAHPEAPEAGPEBD@Z; ScConvertToUnicode(ushort * *,char const *)
0x180038775  test    eax, eax
0x180038777  jnz     short loc_180038788
0x180038779  lea     ebx, [rax+8]
0x18003877c  mov     [rsp+138h+var_A8], ebx
0x180038783  jmp     loc_180038B08
0x180038788  mov     rdx, [rsp+138h+lpBinaryPathName]; char *
0x180038790  test    rdx, rdx
0x180038793  jz      short loc_1800387B5
0x180038795  lea     rcx, [rsp+138h+var_68]; unsigned __int16 **
0x18003879d  call    ?ScConvertToUnicode@@YAHPEAPEAGPEBD@Z; ScConvertToUnicode(ushort * *,char const *)
0x1800387a2  test    eax, eax
0x1800387a4  jnz     short loc_1800387B5
0x1800387a6  lea     ebx, [rax+8]
0x1800387a9  mov     [rsp+138h+var_A8], ebx
0x1800387b0  jmp     loc_180038B08
0x1800387b5  mov     rdx, [rsp+138h+lpLoadOrderGroup]; char *
0x1800387bd  test    rdx, rdx
0x1800387c0  jz      short loc_1800387E2
0x1800387c2  lea     rcx, [rsp+138h+var_60]; unsigned __int16 **
0x1800387ca  call    ?ScConvertToUnicode@@YAHPEAPEAGPEBD@Z; ScConvertToUnicode(ushort * *,char const *)
0x1800387cf  test    eax, eax
0x1800387d1  jnz     short loc_1800387E2
0x1800387d3  lea     ebx, [rax+8]
0x1800387d6  mov     [rsp+138h+var_A8], ebx
0x1800387dd  jmp     loc_180038B08
0x1800387e2  mov     rdx, [rsp+138h+lpServiceStartName]; char *
0x1800387ea  test    rdx, rdx
0x1800387ed  jz      short loc_18003880F
0x1800387ef  lea     rcx, [rsp+138h+var_58]; unsigned __int16 **
0x1800387f7  call    ?ScConvertToUnicode@@YAHPEAPEAGPEBD@Z; ScConvertToUnicode(ushort * *,char const *)
0x1800387fc  test    eax, eax
0x1800387fe  jnz     short loc_18003880F
0x180038800  lea     ebx, [rax+8]
0x180038803  mov     [rsp+138h+var_A8], ebx
0x18003880a  jmp     loc_180038B08
0x18003880f  lea     rax, [rsp+138h+var_80]
0x180038817  mov     [rsp+138h+var_B8], rax
0x18003881f  movzx   eax, [rsp+138h+var_A4]
0x180038827  mov     word ptr [rsp+138h+var_C0], ax
0x18003882c  mov     eax, [rsp+138h+var_A0]
0x180038833  mov     dword ptr [rsp+138h+var_C8], eax
0x180038837  mov     rax, [rsp+138h+var_90]
0x18003883f  mov     [rsp+138h+var_D0], rax
0x180038844  mov     rax, [rsp+138h+var_58]
0x18003884c  mov     [rsp+138h+var_D8], rax
0x180038851  mov     dword ptr [rsp+138h+var_E0], r14d
0x180038856  mov     [rsp+138h+var_E8], rsi
0x18003885b  mov     rax, [rsp+138h+lpdwTagId]
0x180038863  mov     [rsp+138h+var_F0], rax
0x180038868  mov     rax, [rsp+138h+var_60]
0x180038870  mov     [rsp+138h+var_F8], rax
0x180038875  mov     rax, [rsp+138h+var_68]
0x18003887d  mov     [rsp+138h+var_100], rax
0x180038882  mov     eax, [rsp+138h+dwErrorControl]
0x180038889  mov     dword ptr [rsp+138h+var_108], eax
0x18003888d  mov     eax, [rsp+138h+dwStartType]
0x180038894  mov     dword ptr [rsp+138h+var_110], eax
0x180038898  mov     dword ptr [rsp+138h+var_118], r13d
0x18003889d  mov     r9d, [rsp+138h+arg_18]
0x1800388a5  mov     r8, [rsp+138h+var_70]
0x1800388ad  mov     rdx, [rsp+138h+var_78]
0x1800388b5  mov     rcx, [rsp+138h+arg_0]
0x1800388bd  call    RCreateWowService
0x1800388c2  mov     ebx, eax
0x1800388c4  mov     [rsp+138h+var_A8], eax
0x1800388cb  jmp     short loc_180038907
0x1800388cd  mov     ecx, eax; unsigned int
0x1800388cf  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x1800388d4  mov     ebx, eax
0x1800388d6  mov     [rsp+138h+var_A8], eax
0x1800388dd  xor     edi, edi
0x1800388df  mov     r13d, [rsp+138h+dwServiceType]
0x1800388e7  mov     r15, [rsp+138h+arg_10]
0x1800388ef  mov     r12, [rsp+138h+arg_8]
0x1800388f7  mov     rsi, [rsp+138h+var_88]
0x1800388ff  mov     r14d, [rsp+138h+var_9C]
0x180038907  cmp     ebx, 78h ; 'x'
0x18003890a  jnz     loc_180038B08
0x180038910  mov     [rsp+138h+var_50], rdi
0x180038918  lea     rax, [rsp+138h+var_80]
0x180038920  mov     [rsp+138h+var_B0], rax
0x180038928  mov     eax, [rsp+138h+var_A0]
0x18003892f  mov     dword ptr [rsp+138h+var_B8], eax
0x180038936  mov     rax, [rsp+138h+var_90]
0x18003893e  mov     [rsp+138h+var_C0], rax
0x180038943  mov     rax, [rsp+138h+lpServiceStartName]
0x18003894b  mov     [rsp+138h+var_C8], rax
0x180038950  mov     dword ptr [rsp+138h+var_D0], r14d
0x180038955  mov     [rsp+138h+var_D8], rsi
0x18003895a  mov     rax, [rsp+138h+lpdwTagId]
0x180038962  mov     [rsp+138h+var_E0], rax
0x180038967  mov     rax, [rsp+138h+lpLoadOrderGroup]
0x18003896f  mov     [rsp+138h+var_E8], rax
0x180038974  mov     rax, [rsp+138h+lpBinaryPathName]
0x18003897c  mov     [rsp+138h+var_F0], rax
0x180038981  mov     eax, [rsp+138h+dwErrorControl]
0x180038988  mov     dword ptr [rsp+138h+var_F8], eax
0x18003898c  mov     eax, [rsp+138h+dwStartType]
0x180038993  mov     dword ptr [rsp+138h+var_100], eax
0x180038997  mov     dword ptr [rsp+138h+var_108], r13d
0x18003899c  mov     eax, [rsp+138h+arg_18]
0x1800389a3  mov     dword ptr [rsp+138h+var_110], eax
0x1800389a7  mov     [rsp+138h+var_118], r15
0x1800389ac  mov     r9, r12
0x1800389af  mov     r8, [rsp+138h+arg_0]
0x1800389b7  lea     rdx, byte_180060B88; pFormat
0x1800389be  lea     rcx, pStubDescriptor; pStubDescriptor
0x1800389c5  call    cs:__imp_NdrClientCall2
0x1800389cb  mov     rbx, rax
0x1800389ce  mov     [rsp+138h+var_50], rax
0x1800389d6  mov     [rsp+138h+var_A8], eax
0x1800389dd  jmp     short loc_180038A19
0x1800389df  mov     ecx, eax; unsigned int
0x1800389e1  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x1800389e6  mov     ebx, eax
0x1800389e8  mov     [rsp+138h+var_A8], eax
0x1800389ef  xor     edi, edi
0x1800389f1  mov     r13d, [rsp+138h+dwServiceType]
0x1800389f9  mov     r15, [rsp+138h+arg_10]
0x180038a01  mov     r12, [rsp+138h+arg_8]
0x180038a09  mov     rsi, [rsp+138h+var_88]
0x180038a11  mov     r14d, [rsp+138h+var_9C]
0x180038a19  cmp     ebx, 78h ; 'x'
0x180038a1c  jnz     loc_180038B08
0x180038a22  mov     [rsp+138h+var_48], rdi
0x180038a2a  lea     rax, [rsp+138h+var_80]
0x180038a32  mov     [rsp+138h+var_B0], rax
0x180038a3a  mov     eax, [rsp+138h+var_A0]
0x180038a41  mov     dword ptr [rsp+138h+var_B8], eax
0x180038a48  mov     rax, [rsp+138h+var_90]
0x180038a50  mov     [rsp+138h+var_C0], rax
0x180038a55  mov     rax, [rsp+138h+lpServiceStartName]
0x180038a5d  mov     [rsp+138h+var_C8], rax
0x180038a62  mov     dword ptr [rsp+138h+var_D0], r14d
0x180038a67  mov     [rsp+138h+var_D8], rsi
0x180038a6c  mov     rax, [rsp+138h+lpdwTagId]
0x180038a74  mov     [rsp+138h+var_E0], rax
0x180038a79  mov     rax, [rsp+138h+lpLoadOrderGroup]
0x180038a81  mov     [rsp+138h+var_E8], rax
0x180038a86  mov     rax, [rsp+138h+lpBinaryPathName]
0x180038a8e  mov     [rsp+138h+var_F0], rax
0x180038a93  mov     eax, [rsp+138h+dwErrorControl]
0x180038a9a  mov     dword ptr [rsp+138h+var_F8], eax
0x180038a9e  mov     eax, [rsp+138h+dwStartType]
0x180038aa5  mov     dword ptr [rsp+138h+var_100], eax
0x180038aa9  mov     dword ptr [rsp+138h+var_108], r13d
0x180038aae  mov     eax, [rsp+138h+arg_18]
0x180038ab5  mov     dword ptr [rsp+138h+var_110], eax
0x180038ab9  mov     [rsp+138h+var_118], r15
0x180038abe  mov     r9, r12
0x180038ac1  mov     r8, [rsp+138h+arg_0]
0x180038ac9  lea     rdx, byte_1800605EA; pFormat
0x180038ad0  lea     rcx, pStubDescriptor; pStubDescriptor
0x180038ad7  call    cs:__imp_NdrClientCall2
0x180038add  mov     [rsp+138h+var_48], rax
0x180038ae5  mov     ebx, eax
0x180038ae7  mov     [rsp+138h+var_A8], eax
0x180038aee  jmp     short loc_180038B08
0x180038af0  mov     ecx, eax; unsigned int
0x180038af2  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x180038af7  mov     ebx, eax
0x180038af9  mov     [rsp+138h+var_A8], eax
0x180038b00  mov     rsi, [rsp+138h+var_88]
0x180038b08  test    rsi, rsi
0x180038b0b  jz      short loc_180038B16
0x180038b0d  mov     rcx, rsi; hMem
0x180038b10  call    cs:__imp_LocalFree
0x180038b16  mov     rcx, [rsp+138h+var_90]; hMem
0x180038b1e  test    rcx, rcx
0x180038b21  jz      short loc_180038B29
0x180038b23  call    cs:__imp_LocalFree
  ... truncated ...
```
