# NMP_PrepareDeactivateAddress(void *)

- ea: `0x1800cb390`
- end: `0x1800cb470`
- name: `?NMP_PrepareDeactivateAddress@@YAJPEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(struct BASE_ADDRESS *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180064e3c`
- `0x180066420`
- `0x1800cb390`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800cb3f7`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800cb3f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800cb454`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800cb454`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800cb3c4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800cb3c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800cb3ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800cb3ac`

## pseudocode

```c
__int64 __fastcall NMP_PrepareDeactivateAddress(struct BASE_ADDRESS *a1)
{
  __int64 v2; // rdi
  BOOL v3; // r8d
  unsigned int v4; // edi

  SetThreadpoolTimer(**((PTP_TIMER **)a1 + 13), 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(**((PTP_TIMER **)a1 + 13), 1);
  CSpinLock::Lock((struct BASE_ADDRESS *)((char *)a1 + 120));
  _InterlockedDecrement((volatile signed __int32 *)a1 + 48);
  v2 = *((_QWORD *)a1 + 25);
  if ( v2 )
  {
    v3 = CancelIoEx(*(HANDLE *)(v2 + 56), (LPOVERLAPPED)((char *)a1 + 136));
  }
  else
  {
    v3 = 0;
    v2 = 0;
  }
  _InterlockedExchange(
    (volatile __int32 *)a1 + 30,
    ((*((_DWORD *)a1 + 30) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)a1 + 30) - 0x10000000 : 0);
  if ( v3 )
  {
    if ( v2 )
      WaitForThreadpoolIoCallbacks(**(PTP_IO **)(v2 + 48), 0);
    return 0;
  }
  if ( !v2 )
    return 0;
  v4 = 1723;
  _InterlockedIncrement((volatile signed __int32 *)a1 + 48);
  COMMON_ResubmitListen(a1);
  return v4;
}

```

## disassembly

```asm
0x1800cb390  mov     [rsp+arg_0], rbx
0x1800cb395  push    rdi
0x1800cb396  sub     rsp, 20h
0x1800cb39a  mov     rbx, rcx
0x1800cb39d  xor     r9d, r9d; msWindowLength
0x1800cb3a0  mov     rcx, [rcx+68h]
0x1800cb3a4  xor     r8d, r8d; msPeriod
0x1800cb3a7  xor     edx, edx; pftDueTime
0x1800cb3a9  mov     rcx, [rcx]; pti
0x1800cb3ac  call    cs:__imp_SetThreadpoolTimer
0x1800cb3b3  nop     dword ptr [rax+rax+00h]
0x1800cb3b8  mov     rcx, [rbx+68h]
0x1800cb3bc  mov     edx, 1; fCancelPendingCallbacks
0x1800cb3c1  mov     rcx, [rcx]; pti
0x1800cb3c4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800cb3cb  nop     dword ptr [rax+rax+00h]
0x1800cb3d0  lea     rcx, [rbx+78h]; this
0x1800cb3d4  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x1800cb3d9  lock dec dword ptr [rbx+0C0h]
0x1800cb3e0  mov     rdi, [rbx+0C8h]
0x1800cb3e7  test    rdi, rdi
0x1800cb3ea  jz      short loc_1800CB408
0x1800cb3ec  mov     rcx, [rdi+38h]; hFile
0x1800cb3f0  lea     rdx, [rbx+88h]; lpOverlapped
0x1800cb3f7  call    cs:__imp_CancelIoEx
0x1800cb3fe  nop     dword ptr [rax+rax+00h]
0x1800cb403  mov     r8d, eax
0x1800cb406  jmp     short loc_1800CB40D
0x1800cb408  xor     r8d, r8d
0x1800cb40b  xor     edi, edi
0x1800cb40d  mov     edx, [rbx+78h]
0x1800cb410  add     edx, 0F0000000h
0x1800cb416  mov     eax, edx
0x1800cb418  and     eax, 0F0000000h
0x1800cb41d  neg     eax
0x1800cb41f  sbb     ecx, ecx
0x1800cb421  and     ecx, edx
0x1800cb423  xchg    ecx, [rbx+78h]
0x1800cb426  test    r8d, r8d
0x1800cb429  jnz     short loc_1800CB446
0x1800cb42b  test    rdi, rdi
0x1800cb42e  jz      short loc_1800CB460
0x1800cb430  mov     edi, 6BBh
0x1800cb435  lock inc dword ptr [rbx+0C0h]
0x1800cb43c  mov     rcx, rbx; struct BASE_ADDRESS *
0x1800cb43f  call    ?COMMON_ResubmitListen@@YAXPEAUBASE_ADDRESS@@@Z; COMMON_ResubmitListen(BASE_ADDRESS *)
0x1800cb444  jmp     short loc_1800CB462
0x1800cb446  test    rdi, rdi
0x1800cb449  jz      short loc_1800CB460
0x1800cb44b  mov     rcx, [rdi+30h]
0x1800cb44f  xor     edx, edx; fCancelPendingCallbacks
0x1800cb451  mov     rcx, [rcx]; pio
0x1800cb454  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800cb45b  nop     dword ptr [rax+rax+00h]
0x1800cb460  xor     edi, edi
0x1800cb462  mov     rbx, [rsp+28h+arg_0]
0x1800cb467  mov     eax, edi
0x1800cb469  add     rsp, 20h
0x1800cb46d  pop     rdi
0x1800cb46e  retn
```
