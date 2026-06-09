# CreateServiceW

- ea: `0x180038f80`
- end: `0x180039317`
- name: `CreateServiceW`
- size: `919`
- prototype: `SC_HANDLE __stdcall(SC_HANDLE hSCManager, LPCWSTR lpServiceName, LPCWSTR lpDisplayName, DWORD dwDesiredAccess, DWORD dwServiceType, DWORD dwStartType, DWORD dwErrorControl, LPCWSTR lpBinaryPathName, LPCWSTR lpLoadOrderGroup, LPDWORD lpdwTagId, LPCWSTR lpDependencies, LPCWSTR lpServiceStartName, LPCWSTR lpPassword)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180038f80`
- `0x18003c4c0`
- `0x18003c588`
- `0x18003c650`
- `0x18004a934`
- `0x18004aa18`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038feb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800392f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038feb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800392f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039024`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039024`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800392e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800392e6`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180039038`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x180039038`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050507`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050529`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005054b`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050507`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050529`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005054b`

## pseudocode

```c
SC_HANDLE __stdcall CreateServiceW(
        SC_HANDLE hSCManager,
        LPCWSTR lpServiceName,
        LPCWSTR lpDisplayName,
        DWORD dwDesiredAccess,
        DWORD dwServiceType,
        DWORD dwStartType,
        DWORD dwErrorControl,
        LPCWSTR lpBinaryPathName,
        LPCWSTR lpLoadOrderGroup,
        LPDWORD lpdwTagId,
        LPCWSTR lpDependencies,
        LPCWSTR lpServiceStartName,
        LPCWSTR lpPassword)
{
  int v14; // edi
  int v15; // r15d
  int v16; // esi
  DWORD v17; // eax
  HANDLE CurrentProcess; // rax
  DWORD v20; // edi
  __int16 v21[2]; // [rsp+90h] [rbp-58h] BYREF
  DWORD v22; // [rsp+94h] [rbp-54h]
  int v23; // [rsp+98h] [rbp-50h] BYREF
  int v24; // [rsp+9Ch] [rbp-4Ch]
  HLOCAL hMem; // [rsp+A0h] [rbp-48h] BYREF
  _QWORD v26[8]; // [rsp+A8h] [rbp-40h] BYREF
  int v27; // [rsp+F8h] [rbp+10h]
  int v28; // [rsp+100h] [rbp+18h]

  v28 = (int)lpDisplayName;
  v27 = (int)lpServiceName;
  v14 = (int)lpDisplayName;
  v15 = (int)hSCManager;
  v26[0] = 0;
  hMem = 0;
  v23 = 0;
  v16 = 0;
  v24 = 0;
  v21[0] = 0;
  if ( lpPassword )
  {
    v17 = ScEncryptPassword(hSCManager, lpPassword, &hMem, &v23);
    v22 = v17;
    if ( v17 )
    {
      SetLastError(v17);
      return 0;
    }
  }
  if ( lpDependencies )
  {
    v16 = ScWStrArraySize(lpDependencies);
    v24 = v16;
  }
  if ( (dwServiceType & 0x30) != 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !(unsigned int)IsWow64Process2(CurrentProcess, v21, 0) )
      return 0;
  }
  if ( v21[0] )
  {
    v20 = RCreateWowService(
            v15,
            v27,
            v14,
            dwDesiredAccess,
            dwServiceType,
            dwStartType,
            dwErrorControl,
            (__int64)lpBinaryPathName,
            (__int64)lpLoadOrderGroup,
            (__int64)lpdwTagId,
            (__int64)lpDependencies,
            v16,
            (__int64)lpServiceStartName,
            (__int64)hMem,
            v23,
            v21[0],
            (__int64)v26);
    v22 = v20;
    if ( v20 != 120 )
      goto LABEL_14;
    v20 = RCreateServiceWOW64W(
            v15,
            v27,
            v28,
            dwDesiredAccess,
            dwServiceType,
            dwStartType,
            dwErrorControl,
            (__int64)lpBinaryPathName,
            (__int64)lpLoadOrderGroup,
            (__int64)lpdwTagId,
            (__int64)lpDependencies,
            v16,
            (__int64)lpServiceStartName,
            (__int64)hMem,
            v23,
            (__int64)v26);
    v22 = v20;
    if ( v20 != 120 )
      goto LABEL_14;
    v14 = v28;
  }
  v20 = RCreateServiceW(
          v15,
          v27,
          v14,
          dwDesiredAccess,
          dwServiceType,
          dwStartType,
          dwErrorControl,
          (__int64)lpBinaryPathName,
          (__int64)lpLoadOrderGroup,
          (__int64)lpdwTagId,
          (__int64)lpDependencies,
          v16,
          (__int64)lpServiceStartName,
          (__int64)hMem,
          v23,
          (__int64)v26);
  v22 = v20;
LABEL_14:
  if ( hMem )
    LocalFree(hMem);
  if ( !v20 )
    return (SC_HANDLE)v26[0];
  SetLastError(v20);
  return 0;
}

```

## disassembly

```asm
0x180038f80  mov     rax, rsp
0x180038f83  mov     [rax+20h], r9d
0x180038f87  mov     [rax+18h], r8
0x180038f8b  mov     [rax+10h], rdx
0x180038f8f  mov     [rax+8], rcx
0x180038f93  push    rbx
0x180038f94  push    rsi
0x180038f95  push    rdi
0x180038f96  push    r12
0x180038f98  push    r13
0x180038f9a  push    r14
0x180038f9c  push    r15
0x180038f9e  sub     rsp, 0B0h
0x180038fa5  mov     r13d, r9d
0x180038fa8  mov     rdi, r8
0x180038fab  mov     r15, rcx
0x180038fae  xor     ebx, ebx
0x180038fb0  mov     [rax-40h], rbx
0x180038fb4  mov     [rax-48h], rbx
0x180038fb8  mov     [rax-50h], ebx
0x180038fbb  mov     esi, ebx
0x180038fbd  mov     [rax-4Ch], ebx
0x180038fc0  mov     [rax-58h], bx
0x180038fc4  mov     rdx, [rsp+0E8h+lpPassword]
0x180038fcc  test    rdx, rdx
0x180038fcf  jz      short loc_180038FF8
0x180038fd1  lea     r9, [rax-50h]
0x180038fd5  lea     r8, [rax-48h]
0x180038fd9  call    ScEncryptPassword
0x180038fde  mov     [rsp+0E8h+var_54], eax
0x180038fe5  test    eax, eax
0x180038fe7  jz      short loc_180038FF8
0x180038fe9  mov     ecx, eax; dwErrCode
0x180038feb  call    cs:__imp_SetLastError
0x180038ff1  xor     eax, eax
0x180038ff3  jmp     loc_180039304
0x180038ff8  mov     r14, [rsp+0E8h+lpDependencies]
0x180039000  test    r14, r14
0x180039003  jz      short loc_180039016
0x180039005  mov     rcx, r14
0x180039008  call    ScWStrArraySize
0x18003900d  mov     esi, eax
0x18003900f  mov     [rsp+0E8h+var_4C], eax
0x180039016  mov     r12d, [rsp+0E8h+dwServiceType]
0x18003901e  test    r12b, 30h
0x180039022  jz      short loc_180039049
0x180039024  call    cs:__imp_GetCurrentProcess
0x18003902a  mov     rcx, rax
0x18003902d  xor     r8d, r8d
0x180039030  lea     rdx, [rsp+0E8h+var_58]
0x180039038  call    cs:__imp_IsWow64Process2
0x18003903e  test    eax, eax
0x180039040  jnz     short loc_180039049
0x180039042  xor     eax, eax
0x180039044  jmp     loc_180039304
0x180039049  movzx   eax, [rsp+0E8h+var_58]
0x180039051  test    ax, ax
0x180039054  jz      loc_18003922B
0x18003905a  lea     rcx, [rsp+0E8h+var_40]
0x180039062  mov     [rsp+0E8h+var_68], rcx
0x18003906a  mov     word ptr [rsp+0E8h+var_70], ax
0x18003906f  mov     eax, [rsp+0E8h+var_50]
0x180039076  mov     [rsp+0E8h+var_78], eax
0x18003907a  mov     rax, [rsp+0E8h+hMem]
0x180039082  mov     [rsp+0E8h+var_80], rax
0x180039087  mov     rax, [rsp+0E8h+lpServiceStartName]
0x18003908f  mov     [rsp+0E8h+var_88], rax
0x180039094  mov     [rsp+0E8h+var_90], esi
0x180039098  mov     [rsp+0E8h+var_98], r14
0x18003909d  mov     rax, [rsp+0E8h+lpdwTagId]
0x1800390a5  mov     [rsp+0E8h+var_A0], rax
0x1800390aa  mov     rax, [rsp+0E8h+lpLoadOrderGroup]
0x1800390b2  mov     [rsp+0E8h+var_A8], rax
0x1800390b7  mov     rax, [rsp+0E8h+lpBinaryPathName]
0x1800390bf  mov     [rsp+0E8h+var_B0], rax
0x1800390c4  mov     eax, [rsp+0E8h+dwErrorControl]
0x1800390cb  mov     [rsp+0E8h+var_B8], eax
0x1800390cf  mov     eax, [rsp+0E8h+dwStartType]
0x1800390d6  mov     [rsp+0E8h+var_C0], eax
0x1800390da  mov     [rsp+0E8h+var_C8], r12d
0x1800390df  mov     r9d, r13d
0x1800390e2  mov     r8, rdi
0x1800390e5  mov     rdx, [rsp+0E8h+arg_8]
0x1800390ed  mov     rcx, r15
0x1800390f0  call    RCreateWowService
0x1800390f5  mov     edi, eax
0x1800390f7  mov     [rsp+0E8h+var_54], eax
0x1800390fe  jmp     short loc_180039137
0x180039100  mov     ecx, eax; unsigned int
0x180039102  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x180039107  mov     edi, eax
0x180039109  mov     [rsp+0E8h+var_54], eax
0x180039110  mov     r14, [rsp+0E8h+lpDependencies]
0x180039118  mov     r12d, [rsp+0E8h+dwServiceType]
0x180039120  mov     r13d, [rsp+0E8h+arg_18]
0x180039128  mov     r15, [rsp+0E8h+arg_0]
0x180039130  mov     esi, [rsp+0E8h+var_4C]
0x180039137  cmp     edi, 78h ; 'x'
0x18003913a  jnz     loc_1800392D9
0x180039140  lea     rax, [rsp+0E8h+var_40]
0x180039148  mov     [rsp+0E8h+var_70], rax
0x18003914d  mov     eax, [rsp+0E8h+var_50]
0x180039154  mov     [rsp+0E8h+var_78], eax
0x180039158  mov     rax, [rsp+0E8h+hMem]
0x180039160  mov     [rsp+0E8h+var_80], rax
0x180039165  mov     rax, [rsp+0E8h+lpServiceStartName]
0x18003916d  mov     [rsp+0E8h+var_88], rax
0x180039172  mov     [rsp+0E8h+var_90], esi
0x180039176  mov     [rsp+0E8h+var_98], r14
0x18003917b  mov     rax, [rsp+0E8h+lpdwTagId]
0x180039183  mov     [rsp+0E8h+var_A0], rax
0x180039188  mov     rax, [rsp+0E8h+lpLoadOrderGroup]
0x180039190  mov     [rsp+0E8h+var_A8], rax
0x180039195  mov     rax, [rsp+0E8h+lpBinaryPathName]
0x18003919d  mov     [rsp+0E8h+var_B0], rax
0x1800391a2  mov     eax, [rsp+0E8h+dwErrorControl]
0x1800391a9  mov     [rsp+0E8h+var_B8], eax
0x1800391ad  mov     eax, [rsp+0E8h+dwStartType]
0x1800391b4  mov     [rsp+0E8h+var_C0], eax
0x1800391b8  mov     [rsp+0E8h+var_C8], r12d
0x1800391bd  mov     r9d, r13d
0x1800391c0  mov     r8, [rsp+0E8h+arg_10]
0x1800391c8  mov     rdx, [rsp+0E8h+arg_8]
0x1800391d0  mov     rcx, r15
0x1800391d3  call    RCreateServiceWOW64W
0x1800391d8  mov     edi, eax
0x1800391da  mov     [rsp+0E8h+var_54], eax
0x1800391e1  jmp     short loc_18003921A
0x1800391e3  mov     ecx, eax; unsigned int
0x1800391e5  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x1800391ea  mov     edi, eax
0x1800391ec  mov     [rsp+0E8h+var_54], eax
0x1800391f3  mov     r14, [rsp+0E8h+lpDependencies]
0x1800391fb  mov     r12d, [rsp+0E8h+dwServiceType]
0x180039203  mov     r13d, [rsp+0E8h+arg_18]
0x18003920b  mov     r15, [rsp+0E8h+arg_0]
0x180039213  mov     esi, [rsp+0E8h+var_4C]
0x18003921a  cmp     edi, 78h ; 'x'
0x18003921d  jnz     loc_1800392D9
0x180039223  mov     rdi, [rsp+0E8h+arg_10]
0x18003922b  lea     rax, [rsp+0E8h+var_40]
0x180039233  mov     [rsp+0E8h+var_70], rax
0x180039238  mov     eax, [rsp+0E8h+var_50]
0x18003923f  mov     [rsp+0E8h+var_78], eax
0x180039243  mov     rax, [rsp+0E8h+hMem]
0x18003924b  mov     [rsp+0E8h+var_80], rax
0x180039250  mov     rax, [rsp+0E8h+lpServiceStartName]
0x180039258  mov     [rsp+0E8h+var_88], rax
0x18003925d  mov     [rsp+0E8h+var_90], esi
0x180039261  mov     [rsp+0E8h+var_98], r14
0x180039266  mov     rax, [rsp+0E8h+lpdwTagId]
0x18003926e  mov     [rsp+0E8h+var_A0], rax
0x180039273  mov     rax, [rsp+0E8h+lpLoadOrderGroup]
0x18003927b  mov     [rsp+0E8h+var_A8], rax
0x180039280  mov     rax, [rsp+0E8h+lpBinaryPathName]
0x180039288  mov     [rsp+0E8h+var_B0], rax
0x18003928d  mov     eax, [rsp+0E8h+dwErrorControl]
0x180039294  mov     [rsp+0E8h+var_B8], eax
0x180039298  mov     eax, [rsp+0E8h+dwStartType]
0x18003929f  mov     [rsp+0E8h+var_C0], eax
0x1800392a3  mov     [rsp+0E8h+var_C8], r12d
0x1800392a8  mov     r9d, r13d
0x1800392ab  mov     r8, rdi
0x1800392ae  mov     rdx, [rsp+0E8h+arg_8]
0x1800392b6  mov     rcx, r15
0x1800392b9  call    RCreateServiceW
0x1800392be  mov     edi, eax
0x1800392c0  mov     [rsp+0E8h+var_54], eax
0x1800392c7  jmp     short loc_1800392D9
0x1800392c9  mov     ecx, eax; unsigned int
0x1800392cb  call    ?ScMapRpcError@@YAKKK@Z; ScMapRpcError(ulong,ulong)
0x1800392d0  mov     edi, eax
0x1800392d2  mov     [rsp+0E8h+var_54], eax
0x1800392d9  mov     rcx, [rsp+0E8h+hMem]; hMem
0x1800392e1  test    rcx, rcx
0x1800392e4  jz      short loc_1800392EC
0x1800392e6  call    cs:__imp_LocalFree
0x1800392ec  test    edi, edi
0x1800392ee  jz      short loc_1800392FC
0x1800392f0  mov     ecx, edi; dwErrCode
0x1800392f2  call    cs:__imp_SetLastError
0x1800392f8  xor     eax, eax
0x1800392fa  jmp     short loc_180039304
0x1800392fc  mov     rax, [rsp+0E8h+var_40]
0x180039304  add     rsp, 0B0h
0x18003930b  pop     r15
0x18003930d  pop     r14
0x18003930f  pop     r13
0x180039311  pop     r12
0x180039313  pop     rdi
0x180039314  pop     rsi
0x180039315  pop     rbx
0x180039316  retn
0x1800504f6  push    rbp
0x1800504f8  sub     rsp, 90h
0x1800504ff  mov     rbp, rdx
0x180050502  mov     rcx, [rcx]
0x180050505  mov     ecx, [rcx]; ExceptionCode
0x180050507  call    cs:__imp_I_RpcExceptionFilter
0x18005050d  nop
0x18005050e  add     rsp, 90h
0x180050515  pop     rbp
0x180050516  retn
0x180050518  push    rbp
0x18005051a  sub     rsp, 90h
0x180050521  mov     rbp, rdx
0x180050524  mov     rcx, [rcx]
0x180050527  mov     ecx, [rcx]; ExceptionCode
0x180050529  call    cs:__imp_I_RpcExceptionFilter
0x18005052f  nop
0x180050530  add     rsp, 90h
0x180050537  pop     rbp
0x180050538  retn
0x18005053a  push    rbp
0x18005053c  sub     rsp, 90h
0x180050543  mov     rbp, rdx
0x180050546  mov     rcx, [rcx]
0x180050549  mov     ecx, [rcx]; ExceptionCode
0x18005054b  call    cs:__imp_I_RpcExceptionFilter
0x180050551  nop
0x180050552  add     rsp, 90h
0x180050559  pop     rbp
0x18005055a  retn
```
