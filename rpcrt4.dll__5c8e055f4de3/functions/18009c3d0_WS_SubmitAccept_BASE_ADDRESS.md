# WS_SubmitAccept(BASE_ADDRESS *)

- ea: `0x18009c3d0`
- end: `0x18009c57e`
- name: `?WS_SubmitAccept@@YAXPEAUBASE_ADDRESS@@@Z`
- size: `430`
- prototype: `void __fastcall(struct BASE_ADDRESS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180080400`

## callees

- `0x180060e18`
- `0x1800610b8`
- `0x18009c3d0`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c50b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c51f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c50b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c51f`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18009c493`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x18009c493`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18009c4b3`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18009c4b3`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18009c52f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18009c52f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009c3fe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009c3fe`
- `WS2_32!WSASocketW` at `0x18009c474`
- `WS2_32!WSASocketW` at `0x18009c474`
- `WS2_32!__imp_closesocket` at `0x18009c440`
- `WS2_32!__imp_closesocket` at `0x18009c53c`
- `WS2_32!__imp_closesocket` at `0x18009c440`
- `WS2_32!__imp_closesocket` at `0x18009c53c`

## pseudocode

```c
void __fastcall WS_SubmitAccept(struct BASE_ADDRESS *a1)
{
  __int64 v1; // rdi
  PTP_TIMER *v3; // rcx
  SOCKET v4; // rcx
  __int64 v5; // rdi
  void *v6; // rax
  PTP_IO *v7; // rcx
  int v8; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((int *)a1 + 3);
  v3 = (PTP_TIMER *)*((_QWORD *)a1 + 13);
  if ( v3 )
  {
    SetThreadpoolTimer(*v3, 0, 0, 0);
    CSpinLock::Lock((struct BASE_ADDRESS *)((char *)a1 + 120));
    if ( !*((_DWORD *)a1 + 48) || !*((_QWORD *)a1 + 25) )
      goto LABEL_13;
    v4 = *((_QWORD *)a1 + 26);
    v5 = 14 * v1;
    if ( v4 )
    {
      closesocket(v4);
      *((_QWORD *)a1 + 26) = 0;
    }
    v6 = (void *)WSASocketW(
                   *(__int16 *)((char *)&WsTransportTable + v5),
                   *(__int16 *)((char *)&WsTransportTable + v5 + 2),
                   *(__int16 *)((char *)&WsTransportTable + v5 + 4),
                   0,
                   0,
                   1u);
    *((_QWORD *)a1 + 26) = v6;
    if ( v6 != (void *)-1LL )
    {
      if ( SetHandleInformation(v6, 1u, 0) )
      {
        v7 = (PTP_IO *)*((_QWORD *)a1 + 83);
        v8 = 0;
        StartThreadpoolIo(*v7);
        _InterlockedAdd((volatile signed __int32 *)a1 + 49, 1u);
        if ( (*((unsigned int (__fastcall **)(_QWORD, _QWORD, char *, _QWORD, int, int, int *, char *))a1 + 80))(
               *((_QWORD *)a1 + 25),
               *((_QWORD *)a1 + 26),
               (char *)a1 + 216,
               0,
               144,
               144,
               &v8,
               (char *)a1 + 136)
          || GetLastError() == 997 )
        {
          goto LABEL_13;
        }
        _InterlockedDecrement((volatile signed __int32 *)a1 + 49);
        GetLastError();
        CancelThreadpoolIo(**((PTP_IO **)a1 + 83));
      }
      closesocket(*((_QWORD *)a1 + 26));
    }
    *((_QWORD *)a1 + 26) = 0;
    COMMON_ResubmitListen(a1);
LABEL_13:
    _InterlockedExchange(
      (volatile __int32 *)a1 + 30,
      ((*((_DWORD *)a1 + 30) - 0x10000000) & 0xF0000000) != 0 ? *((_DWORD *)a1 + 30) - 0x10000000 : 0);
  }
}

```

## disassembly

```asm
0x18009c3d0  mov     [rsp+arg_8], rbx
0x18009c3d5  mov     [rsp+arg_10], rbp
0x18009c3da  push    rdi
0x18009c3db  sub     rsp, 50h
0x18009c3df  movsxd  rdi, dword ptr [rcx+0Ch]
0x18009c3e3  mov     rbx, rcx
0x18009c3e6  mov     rcx, [rcx+68h]
0x18009c3ea  test    rcx, rcx
0x18009c3ed  jz      loc_18009C56E
0x18009c3f3  mov     rcx, [rcx]; pti
0x18009c3f6  xor     r9d, r9d; msWindowLength
0x18009c3f9  xor     r8d, r8d; msPeriod
0x18009c3fc  xor     edx, edx; pftDueTime
0x18009c3fe  call    cs:__imp_SetThreadpoolTimer
0x18009c404  lea     rcx, [rbx+78h]; this
0x18009c408  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x18009c40d  mov     eax, [rbx+0C0h]
0x18009c413  test    eax, eax
0x18009c415  jz      loc_18009C555
0x18009c41b  cmp     qword ptr [rbx+0C8h], 0
0x18009c423  jz      loc_18009C555
0x18009c429  mov     rcx, [rbx+0D0h]; s
0x18009c430  lea     rbp, ?WsTransportTable@@3QBUWS_TRANS_INFO@@B; WS_TRANS_INFO const near * const WsTransportTable
0x18009c437  imul    rdi, 0Eh
0x18009c43b  test    rcx, rcx
0x18009c43e  jz      short loc_18009C451
0x18009c440  call    cs:__imp_closesocket
0x18009c446  mov     qword ptr [rbx+0D0h], 0
0x18009c451  movsx   r8d, word ptr [rdi+rbp+4]; protocol
0x18009c457  xor     r9d, r9d; lpProtocolInfo
0x18009c45a  movsx   edx, word ptr [rdi+rbp+2]; type
0x18009c45f  movsx   ecx, word ptr [rdi+rbp]; af
0x18009c463  mov     edi, 1
0x18009c468  mov     [rsp+58h+dwFlags], edi; dwFlags
0x18009c46c  mov     [rsp+58h+g], 0; g
0x18009c474  call    cs:__imp_WSASocketW
0x18009c47a  mov     [rbx+0D0h], rax
0x18009c481  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009c485  jz      loc_18009C542
0x18009c48b  xor     r8d, r8d; dwFlags
0x18009c48e  mov     edx, edi; dwMask
0x18009c490  mov     rcx, rax; hObject
0x18009c493  call    cs:__imp_SetHandleInformation
0x18009c499  test    eax, eax
0x18009c49b  jz      loc_18009C535
0x18009c4a1  mov     rcx, [rbx+298h]
0x18009c4a8  mov     [rsp+58h+arg_0], 0
0x18009c4b0  mov     rcx, [rcx]; pio
0x18009c4b3  call    cs:__imp_StartThreadpoolIo
0x18009c4b9  lock add [rbx+0C4h], edi
0x18009c4c0  mov     rdx, [rbx+0D0h]
0x18009c4c7  lea     rax, [rsp+58h+arg_0]
0x18009c4cc  lea     rcx, [rbx+88h]
0x18009c4d3  xor     r9d, r9d
0x18009c4d6  mov     [rsp+58h+var_20], rcx
0x18009c4db  lea     r8, [rbx+0D8h]
0x18009c4e2  mov     rcx, [rbx+0C8h]
0x18009c4e9  mov     [rsp+58h+var_28], rax
0x18009c4ee  mov     eax, 90h
0x18009c4f3  mov     [rsp+58h+dwFlags], eax
0x18009c4f7  mov     [rsp+58h+g], eax
0x18009c4fb  mov     rax, [rbx+280h]
0x18009c502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c507  test    eax, eax
0x18009c509  jnz     short loc_18009C555
0x18009c50b  call    cs:__imp_GetLastError
0x18009c511  cmp     eax, 3E5h
0x18009c516  jz      short loc_18009C555
0x18009c518  lock dec dword ptr [rbx+0C4h]
0x18009c51f  call    cs:__imp_GetLastError
0x18009c525  mov     rcx, [rbx+298h]
0x18009c52c  mov     rcx, [rcx]; pio
0x18009c52f  call    cs:__imp_CancelThreadpoolIo
0x18009c535  mov     rcx, [rbx+0D0h]; s
0x18009c53c  call    cs:__imp_closesocket
0x18009c542  mov     rcx, rbx; struct BASE_ADDRESS *
0x18009c545  mov     qword ptr [rbx+0D0h], 0
0x18009c550  call    ?COMMON_ResubmitListen@@YAXPEAUBASE_ADDRESS@@@Z; COMMON_ResubmitListen(BASE_ADDRESS *)
0x18009c555  mov     edx, [rbx+78h]
0x18009c558  add     edx, 0F0000000h
0x18009c55e  mov     eax, edx
0x18009c560  and     eax, 0F0000000h
0x18009c565  neg     eax
0x18009c567  sbb     ecx, ecx
0x18009c569  and     ecx, edx
0x18009c56b  xchg    ecx, [rbx+78h]
0x18009c56e  mov     rbx, [rsp+58h+arg_8]
0x18009c573  mov     rbp, [rsp+58h+arg_10]
0x18009c578  add     rsp, 50h
0x18009c57c  pop     rdi
0x18009c57d  retn
```
