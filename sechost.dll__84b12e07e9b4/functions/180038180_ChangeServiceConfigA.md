# ChangeServiceConfigA

- ea: `0x180038180`
- end: `0x1800383ff`
- name: `ChangeServiceConfigA`
- size: `639`
- prototype: `BOOL __stdcall(SC_HANDLE hService, DWORD dwServiceType, DWORD dwStartType, DWORD dwErrorControl, LPCSTR lpBinaryPathName, LPCSTR lpLoadOrderGroup, LPDWORD lpdwTagId, LPCSTR lpDependencies, LPCSTR lpServiceStartName, LPCSTR lpPassword, LPCSTR lpDisplayName)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x1800198d8`
- `0x180038180`
- `0x18004a88c`
- `0x18004a8c0`
- `0x18004aa18`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800381dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038227`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800383de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800381dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038227`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800383de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038261`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038261`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003821b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800382d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800383c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800383d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003821b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800382d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800383c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800383d2`
- `RPCRT4!NdrClientCall2` at `0x180038385`
- `RPCRT4!NdrClientCall2` at `0x180038385`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800504df`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800504df`

## pseudocode

```c
BOOL __stdcall ChangeServiceConfigA(
        SC_HANDLE hService,
        DWORD dwServiceType,
        DWORD dwStartType,
        DWORD dwErrorControl,
        LPCSTR lpBinaryPathName,
        LPCSTR lpLoadOrderGroup,
        LPDWORD lpdwTagId,
        LPCSTR lpDependencies,
        LPCSTR lpServiceStartName,
        LPCSTR lpPassword,
        LPCSTR lpDisplayName)
{
  HLOCAL v14; // rsi
  unsigned int v15; // r14d
  DWORD Pointer; // ebx
  const char *v18; // rbx
  __int64 v19; // rax
  CLIENT_CALL_RETURN v20; // rax
  _DWORD v21[3]; // [rsp+84h] [rbp-64h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp-58h] BYREF
  HLOCAL v23; // [rsp+98h] [rbp-50h] BYREF
  HLOCAL v24; // [rsp+A0h] [rbp-48h]
  CLIENT_CALL_RETURN v25; // [rsp+A8h] [rbp-40h]

  hMem = 0;
  v23 = 0;
  v21[0] = 0;
  v14 = 0;
  v24 = 0;
  v15 = 0;
  if ( lpPassword )
  {
    if ( !ScConvertToUnicode((unsigned __int16 **)&hMem, lpPassword) )
    {
      SetLastError(8u);
      return 0;
    }
    Pointer = ScEncryptPassword(hService, hMem, &v23, v21);
    LocalFree(hMem);
    if ( Pointer )
      goto LABEL_5;
  }
  v18 = lpDependencies;
  if ( lpDependencies )
  {
    v15 = 2 * ScAStrArraySize(lpDependencies);
    v21[1] = v15;
    v14 = LocalAlloc(0x40u, v15);
    v24 = v14;
    if ( !v14 )
    {
      Pointer = 8;
      goto LABEL_17;
    }
    if ( v15 > 2 )
    {
      while ( *v18 )
      {
        hMem = 0;
        if ( !ScConvertToUnicode((unsigned __int16 **)&hMem, v18) )
        {
          Pointer = 8;
          goto LABEL_17;
        }
        ScAddWStrToWStrArray(v14, hMem);
        LocalFree(hMem);
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        v18 += v19 + 1;
      }
    }
  }
  v25.Simple = 0;
  v20.Pointer = NdrClientCall2(
                  &pStubDescriptor,
                  &byte_180060576,
                  hService,
                  dwServiceType,
                  dwStartType,
                  dwErrorControl,
                  lpBinaryPathName,
                  lpLoadOrderGroup,
                  lpdwTagId,
                  v14,
                  v15,
                  lpServiceStartName,
                  v23,
                  v21[0],
                  lpDisplayName).Pointer;
  Pointer = (DWORD)v20.Pointer;
  v25.Pointer = v20.Pointer;
LABEL_17:
  if ( v23 )
    LocalFree(v23);
  if ( v14 )
    LocalFree(v14);
  if ( Pointer )
  {
LABEL_5:
    SetLastError(Pointer);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180038180  mov     rax, rsp
0x180038183  mov     [rax+10h], edx
0x180038186  push    rbx
0x180038187  push    rsi
0x180038188  push    r12
0x18003818a  push    r13
0x18003818c  push    r14
0x18003818e  push    r15
0x180038190  sub     rsp, 0B8h
0x180038197  mov     r12d, r9d
0x18003819a  mov     r13d, r8d
0x18003819d  mov     r15, rcx
0x1800381a0  mov     qword ptr [rax-58h], 0
0x1800381a8  mov     qword ptr [rax-50h], 0
0x1800381b0  mov     dword ptr [rax-64h], 0
0x1800381b7  xor     esi, esi
0x1800381b9  mov     [rax-48h], rsi
0x1800381bd  xor     r14d, r14d
0x1800381c0  mov     rdx, [rsp+0E8h+lpPassword]; char *
0x1800381c8  test    rdx, rdx
0x1800381cb  jz      short loc_180038234
0x1800381cd  lea     rcx, [rax-58h]; unsigned __int16 **
0x1800381d1  call    ?ScConvertToUnicode@@YAHPEAPEAGPEBD@Z; ScConvertToUnicode(ushort * *,char const *)
0x1800381d6  test    eax, eax
0x1800381d8  jnz     short loc_1800381EA
0x1800381da  lea     ecx, [rsi+8]; dwErrCode
0x1800381dd  call    cs:__imp_SetLastError
0x1800381e3  xor     eax, eax
0x1800381e5  jmp     loc_1800383ED
0x1800381ea  lea     r9, [rsp+0E8h+var_64]
0x1800381f2  lea     r8, [rsp+0E8h+var_50]
0x1800381fa  mov     rdx, [rsp+0E8h+hMem]
0x180038202  mov     rcx, r15
0x180038205  call    ScEncryptPassword
0x18003820a  mov     ebx, eax
0x18003820c  mov     [rsp+0E8h+var_68], eax
0x180038213  mov     rcx, [rsp+0E8h+hMem]; hMem
0x18003821b  call    cs:__imp_LocalFree
0x180038221  test    ebx, ebx
0x180038223  jz      short loc_180038234
0x180038225  mov     ecx, ebx; dwErrCode
0x180038227  call    cs:__imp_SetLastError
0x18003822d  xor     eax, eax
0x18003822f  jmp     loc_1800383ED
0x180038234  mov     rbx, [rsp+0E8h+lpDependencies]
0x18003823c  test    rbx, rbx
0x18003823f  jz      loc_1800382F3
0x180038245  mov     rcx, rbx
0x180038248  call    ScAStrArraySize
0x18003824d  add     eax, eax
0x18003824f  mov     r14d, eax
0x180038252  mov     [rsp+0E8h+var_60], r14d
0x18003825a  mov     edx, eax; uBytes
0x18003825c  mov     ecx, 40h ; '@'; uFlags
0x180038261  call    cs:__imp_LocalAlloc
0x180038267  mov     rsi, rax
0x18003826a  mov     [rsp+0E8h+var_48], rax
0x180038272  test    rax, rax
0x180038275  jnz     short loc_180038286
0x180038277  lea     ebx, [rax+8]
0x18003827a  mov     [rsp+0E8h+var_68], ebx
0x180038281  jmp     loc_1800383B7
0x180038286  cmp     r14d, 2
0x18003828a  jbe     short loc_1800382F3
0x18003828c  cmp     byte ptr [rbx], 0
0x18003828f  jz      short loc_1800382F3
0x180038291  mov     [rsp+0E8h+hMem], 0
0x18003829d  mov     rdx, rbx; char *
0x1800382a0  lea     rcx, [rsp+0E8h+hMem]; unsigned __int16 **
0x1800382a8  call    ?ScConvertToUnicode@@YAHPEAPEAGPEBD@Z; ScConvertToUnicode(ushort * *,char const *)
0x1800382ad  test    eax, eax
0x1800382af  jnz     short loc_1800382C0
0x1800382b1  lea     ebx, [rax+8]
0x1800382b4  mov     [rsp+0E8h+var_68], ebx
0x1800382bb  jmp     loc_1800383B7
0x1800382c0  mov     rdx, [rsp+0E8h+hMem]
0x1800382c8  mov     rcx, rsi
0x1800382cb  call    ScAddWStrToWStrArray
0x1800382d0  mov     rcx, [rsp+0E8h+hMem]; hMem
0x1800382d8  call    cs:__imp_LocalFree
0x1800382de  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800382e2  inc     rax
0x1800382e5  cmp     byte ptr [rbx+rax], 0
0x1800382e9  jnz     short loc_1800382E2
0x1800382eb  inc     rbx
0x1800382ee  add     rbx, rax
0x1800382f1  jmp     short loc_18003828C
0x1800382f3  mov     [rsp+0E8h+var_40], 0
0x1800382ff  mov     rax, [rsp+0E8h+lpDisplayName]
0x180038307  mov     [rsp+0E8h+var_78], rax
0x18003830c  mov     eax, [rsp+0E8h+var_64]
0x180038313  mov     [rsp+0E8h+var_80], eax
0x180038317  mov     rax, [rsp+0E8h+var_50]
0x18003831f  mov     [rsp+0E8h+var_88], rax
0x180038324  mov     rax, [rsp+0E8h+lpServiceStartName]
0x18003832c  mov     [rsp+0E8h+var_90], rax
0x180038331  mov     [rsp+0E8h+var_98], r14d
0x180038336  mov     [rsp+0E8h+var_A0], rsi
0x18003833b  mov     rax, [rsp+0E8h+lpdwTagId]
0x180038343  mov     [rsp+0E8h+var_A8], rax
0x180038348  mov     rax, [rsp+0E8h+lpLoadOrderGroup]
0x180038350  mov     [rsp+0E8h+var_B0], rax
0x180038355  mov     rax, [rsp+0E8h+lpBinaryPathName]
0x18003835d  mov     [rsp+0E8h+var_B8], rax
0x180038362  mov     [rsp+0E8h+var_C0], r12d
0x180038367  mov     [rsp+0E8h+var_C8], r13d
0x18003836c  mov     r9d, [rsp+0E8h+arg_8]
0x180038374  mov     r8, r15
0x180038377  lea     rdx, byte_180060576; pFormat
0x18003837e  lea     rcx, pStubDescriptor; pStubDescriptor
0x180038385  call    cs:__imp_NdrClientCall2
0x18003838b  mov     rbx, rax
0x18003838e  mov     [rsp+0E8h+var_40], rax
0x180038396  mov     [rsp+0E8h+var_68], eax
0x18003839d  jmp     short loc_1800383B7
0x18003839f  mov     ecx, eax; unsigned int
0x1800383a1  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x1800383a6  mov     ebx, eax
0x1800383a8  mov     [rsp+0E8h+var_68], eax
0x1800383af  mov     rsi, [rsp+0E8h+var_48]
0x1800383b7  mov     rcx, [rsp+0E8h+var_50]; hMem
0x1800383bf  test    rcx, rcx
0x1800383c2  jz      short loc_1800383CA
0x1800383c4  call    cs:__imp_LocalFree
0x1800383ca  test    rsi, rsi
0x1800383cd  jz      short loc_1800383D8
0x1800383cf  mov     rcx, rsi; hMem
0x1800383d2  call    cs:__imp_LocalFree
0x1800383d8  test    ebx, ebx
0x1800383da  jz      short loc_1800383E8
0x1800383dc  mov     ecx, ebx; dwErrCode
0x1800383de  call    cs:__imp_SetLastError
0x1800383e4  xor     eax, eax
0x1800383e6  jmp     short loc_1800383ED
0x1800383e8  mov     eax, 1
0x1800383ed  add     rsp, 0B8h
0x1800383f4  pop     r15
0x1800383f6  pop     r14
0x1800383f8  pop     r13
0x1800383fa  pop     r12
0x1800383fc  pop     rsi
0x1800383fd  pop     rbx
0x1800383fe  retn
0x1800504ce  push    rbp
0x1800504d0  sub     rsp, 80h
0x1800504d7  mov     rbp, rdx
0x1800504da  mov     rcx, [rcx]
0x1800504dd  mov     ecx, [rcx]; ExceptionCode
0x1800504df  call    cs:__imp_I_RpcExceptionFilter
0x1800504e5  nop
0x1800504e6  add     rsp, 80h
0x1800504ed  pop     rbp
0x1800504ee  retn
```
