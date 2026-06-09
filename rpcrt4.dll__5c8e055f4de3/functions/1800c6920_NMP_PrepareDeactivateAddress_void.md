# NMP_PrepareDeactivateAddress(void *)

- ea: `0x1800c6920`
- end: `0x1800c69e7`
- name: `?NMP_PrepareDeactivateAddress@@YAJPEAX@Z`
- size: `199`
- prototype: `__int64 __fastcall(struct BASE_ADDRESS *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180060e18`
- `0x1800610b8`
- `0x1800c6920`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800c697b`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1800c697b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800c69d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x1800c69d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c694e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c694e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c693c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c693c`

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
0x1800c6920  mov     [rsp+arg_0], rbx
0x1800c6925  push    rdi
0x1800c6926  sub     rsp, 20h
0x1800c692a  mov     rbx, rcx
0x1800c692d  xor     r9d, r9d; msWindowLength
0x1800c6930  mov     rcx, [rcx+68h]
0x1800c6934  xor     r8d, r8d; msPeriod
0x1800c6937  xor     edx, edx; pftDueTime
0x1800c6939  mov     rcx, [rcx]; pti
0x1800c693c  call    cs:__imp_SetThreadpoolTimer
0x1800c6942  mov     rcx, [rbx+68h]
0x1800c6946  mov     edx, 1; fCancelPendingCallbacks
0x1800c694b  mov     rcx, [rcx]; pti
0x1800c694e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800c6954  lea     rcx, [rbx+78h]; this
0x1800c6958  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x1800c695d  lock dec dword ptr [rbx+0C0h]
0x1800c6964  mov     rdi, [rbx+0C8h]
0x1800c696b  test    rdi, rdi
0x1800c696e  jz      short loc_1800C6986
0x1800c6970  mov     rcx, [rdi+38h]; hFile
0x1800c6974  lea     rdx, [rbx+88h]; lpOverlapped
0x1800c697b  call    cs:__imp_CancelIoEx
0x1800c6981  mov     r8d, eax
0x1800c6984  jmp     short loc_1800C698B
0x1800c6986  xor     r8d, r8d
0x1800c6989  xor     edi, edi
0x1800c698b  mov     edx, [rbx+78h]
0x1800c698e  add     edx, 0F0000000h
0x1800c6994  mov     eax, edx
0x1800c6996  and     eax, 0F0000000h
0x1800c699b  neg     eax
0x1800c699d  sbb     ecx, ecx
0x1800c699f  and     ecx, edx
0x1800c69a1  xchg    ecx, [rbx+78h]
0x1800c69a4  test    r8d, r8d
0x1800c69a7  jnz     short loc_1800C69C4
0x1800c69a9  test    rdi, rdi
0x1800c69ac  jz      short loc_1800C69D8
0x1800c69ae  mov     edi, 6BBh
0x1800c69b3  lock inc dword ptr [rbx+0C0h]
0x1800c69ba  mov     rcx, rbx; struct BASE_ADDRESS *
0x1800c69bd  call    ?COMMON_ResubmitListen@@YAXPEAUBASE_ADDRESS@@@Z; COMMON_ResubmitListen(BASE_ADDRESS *)
0x1800c69c2  jmp     short loc_1800C69DA
0x1800c69c4  test    rdi, rdi
0x1800c69c7  jz      short loc_1800C69D8
0x1800c69c9  mov     rcx, [rdi+30h]
0x1800c69cd  xor     edx, edx; fCancelPendingCallbacks
0x1800c69cf  mov     rcx, [rcx]; pio
0x1800c69d2  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x1800c69d8  xor     edi, edi
0x1800c69da  mov     rbx, [rsp+28h+arg_0]
0x1800c69df  mov     eax, edi
0x1800c69e1  add     rsp, 20h
0x1800c69e5  pop     rdi
0x1800c69e6  retn
```
