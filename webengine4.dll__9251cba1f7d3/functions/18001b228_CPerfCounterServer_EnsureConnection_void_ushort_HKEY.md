# CPerfCounterServer::EnsureConnection(void *,ushort *,HKEY__ *)

- ea: `0x18001b228`
- end: `0x18001b37f`
- name: `?EnsureConnection@CPerfCounterServer@@AEAAJPEAXPEAGPEAUHKEY__@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(CPerfCounterServer *__hidden this, HANDLE hNamedPipe, LPCWSTR lpValueName, HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001be18`

## callees

- `0x18001aa0c`
- `0x18001aa34`
- `0x18001afdc`
- `0x18001b228`
- `0x180049810`
- `0x18004d6c8`
- `0x18004d754`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001b2ad`
- `KERNEL32!GetLastError` at `0x18001b2ad`
- `KERNEL32!GetCurrentProcessId` at `0x18001b2e0`
- `KERNEL32!GetCurrentProcessId` at `0x18001b2e0`
- `KERNEL32!ConnectNamedPipe` at `0x18001b2a3`
- `KERNEL32!ConnectNamedPipe` at `0x18001b2a3`
- `KERNEL32!DisconnectNamedPipe` at `0x18001b316`
- `KERNEL32!DisconnectNamedPipe` at `0x18001b316`
- `ADVAPI32!RegSetValueExW` at `0x18001b306`
- `ADVAPI32!RegSetValueExW` at `0x18001b306`

## pseudocode

```c
__int64 __fastcall CPerfCounterServer::EnsureConnection(
        CPerfCounterServer *this,
        HANDLE hNamedPipe,
        LPCWSTR lpValueName,
        HKEY hKey)
{
  int v4; // esi
  unsigned int v9; // ebx
  CPerfPipeOverlapped *v10; // rax
  CPerfPipeOverlapped *v11; // rax
  CPerfPipeOverlapped *v12; // rdi
  signed int LastError; // eax
  LSTATUS v14; // r15d
  DWORD Data; // [rsp+68h] [rbp+10h] BYREF

  v4 = 0;
  if ( hNamedPipe == (HANDLE)-1LL )
  {
    return (unsigned int)-2147024890;
  }
  else
  {
    v10 = (CPerfPipeOverlapped *)MemAllocClear(0x90u);
    if ( !v10 )
      return (unsigned int)-2147024882;
    v11 = CPerfPipeOverlapped::CPerfPipeOverlapped(v10);
    v12 = v11;
    if ( !v11 )
      return (unsigned int)-2147024882;
    *((_QWORD *)v11 + 4) = this;
    *((_QWORD *)v11 + 9) = hNamedPipe;
    v9 = AttachHandleToThreadPool(hNamedPipe);
    if ( v9 )
      goto LABEL_19;
    if ( ConnectNamedPipe(hNamedPipe, (LPOVERLAPPED)v12)
      || (LastError = GetLastError(), LastError == 997)
      || LastError == 536 )
    {
      v4 = 1;
      if ( !hKey
        || !lpValueName
        || (Data = GetCurrentProcessId(), (v14 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u)) == 0) )
      {
        *((_DWORD *)v12 + 11) = _InterlockedIncrement((volatile signed __int32 *)this + 13);
        return v9;
      }
      DisconnectNamedPipe(hNamedPipe);
      v9 = (unsigned __int16)v14 | 0x80070000;
      if ( v14 <= 0 )
        v9 = v14;
    }
    else
    {
      v9 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v9 = LastError;
    }
    if ( v9 && !v4 )
    {
LABEL_19:
      CPerfCounterServer::ClosePipe(this, v12);
      CPerfPipeOverlapped::~CPerfPipeOverlapped(v12);
      MemFree(v12);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18001b228  mov     [rsp+arg_0], rbx
0x18001b22d  mov     [rsp+arg_10], rbp
0x18001b232  push    rsi
0x18001b233  push    rdi
0x18001b234  push    r12
0x18001b236  push    r14
0x18001b238  push    r15
0x18001b23a  sub     rsp, 30h
0x18001b23e  xor     esi, esi
0x18001b240  mov     r15, r9
0x18001b243  mov     r12, r8
0x18001b246  mov     rbp, rdx
0x18001b249  mov     r14, rcx
0x18001b24c  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001b250  jnz     short loc_18001B25C
0x18001b252  mov     ebx, 80070006h
0x18001b257  jmp     loc_18001B366
0x18001b25c  mov     ecx, 90h; unsigned __int64
0x18001b261  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x18001b266  test    rax, rax
0x18001b269  jz      loc_18001B361
0x18001b26f  mov     rcx, rax; this
0x18001b272  call    ??0CPerfPipeOverlapped@@QEAA@XZ; CPerfPipeOverlapped::CPerfPipeOverlapped(void)
0x18001b277  mov     rdi, rax
0x18001b27a  test    rax, rax
0x18001b27d  jz      loc_18001B361
0x18001b283  mov     rcx, rbp
0x18001b286  mov     [rax+20h], r14
0x18001b28a  mov     [rax+48h], rbp
0x18001b28e  call    AttachHandleToThreadPool
0x18001b293  mov     ebx, eax
0x18001b295  test    eax, eax
0x18001b297  jnz     loc_18001B335
0x18001b29d  mov     rdx, rdi; lpOverlapped
0x18001b2a0  mov     rcx, rbp; hNamedPipe
0x18001b2a3  call    cs:__imp_ConnectNamedPipe
0x18001b2a9  test    eax, eax
0x18001b2ab  jnz     short loc_18001B2D1
0x18001b2ad  call    cs:__imp_GetLastError
0x18001b2b3  cmp     eax, 3E5h
0x18001b2b8  jz      short loc_18001B2D1
0x18001b2ba  cmp     eax, 218h
0x18001b2bf  jz      short loc_18001B2D1
0x18001b2c1  movzx   ebx, ax
0x18001b2c4  or      ebx, 80070000h
0x18001b2ca  test    eax, eax
0x18001b2cc  cmovle  ebx, eax
0x18001b2cf  jmp     short loc_18001B32D
0x18001b2d1  mov     esi, 1
0x18001b2d6  test    r15, r15
0x18001b2d9  jz      short loc_18001B352
0x18001b2db  test    r12, r12
0x18001b2de  jz      short loc_18001B352
0x18001b2e0  call    cs:__imp_GetCurrentProcessId
0x18001b2e6  mov     [rsp+58h+Data], eax
0x18001b2ea  lea     r9d, [rsi+3]; dwType
0x18001b2ee  mov     [rsp+58h+cbData], r9d; cbData
0x18001b2f3  xor     r8d, r8d; Reserved
0x18001b2f6  lea     rax, [rsp+58h+Data]
0x18001b2fb  mov     rdx, r12; lpValueName
0x18001b2fe  mov     rcx, r15; hKey
0x18001b301  mov     [rsp+58h+lpData], rax; lpData
0x18001b306  call    cs:__imp_RegSetValueExW
0x18001b30c  mov     r15d, eax
0x18001b30f  test    eax, eax
0x18001b311  jz      short loc_18001B352
0x18001b313  mov     rcx, rbp; hNamedPipe
0x18001b316  call    cs:__imp_DisconnectNamedPipe
0x18001b31c  movzx   ebx, r15w
0x18001b320  or      ebx, 80070000h
0x18001b326  test    r15d, r15d
0x18001b329  cmovle  ebx, r15d
0x18001b32d  test    ebx, ebx
0x18001b32f  jz      short loc_18001B366
0x18001b331  test    esi, esi
0x18001b333  jnz     short loc_18001B366
0x18001b335  mov     rdx, rdi; struct CPerfPipeOverlapped *
0x18001b338  mov     rcx, r14; this
0x18001b33b  call    ?ClosePipe@CPerfCounterServer@@AEAAXPEAVCPerfPipeOverlapped@@@Z; CPerfCounterServer::ClosePipe(CPerfPipeOverlapped *)
0x18001b340  mov     rcx, rdi; this
0x18001b343  call    ??1CPerfPipeOverlapped@@QEAA@XZ; CPerfPipeOverlapped::~CPerfPipeOverlapped(void)
0x18001b348  mov     rcx, rdi; lpMem
0x18001b34b  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001b350  jmp     short loc_18001B366
0x18001b352  mov     eax, esi
0x18001b354  lock xadd [r14+34h], eax
0x18001b35a  add     eax, esi
0x18001b35c  mov     [rdi+2Ch], eax
0x18001b35f  jmp     short loc_18001B366
0x18001b361  mov     ebx, 8007000Eh
0x18001b366  mov     rbp, [rsp+58h+arg_10]
0x18001b36b  mov     eax, ebx
0x18001b36d  mov     rbx, [rsp+58h+arg_0]
0x18001b372  add     rsp, 30h
0x18001b376  pop     r15
0x18001b378  pop     r14
0x18001b37a  pop     r12
0x18001b37c  pop     rdi
0x18001b37d  pop     rsi
0x18001b37e  retn
```
