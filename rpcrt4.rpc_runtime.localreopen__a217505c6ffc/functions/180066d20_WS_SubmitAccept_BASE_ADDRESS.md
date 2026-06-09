# WS_SubmitAccept(BASE_ADDRESS *)

- ea: `0x180066d20`
- end: `0x180066f05`
- name: `?WS_SubmitAccept@@YAXPEAUBASE_ADDRESS@@@Z`
- size: `485`
- prototype: `void __fastcall(struct BASE_ADDRESS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180081d30`

## callees

- `0x180064e3c`
- `0x180066420`
- `0x180066d20`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e93`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180066df5`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180066df5`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180066e1b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180066e1b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180066ea9`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180066ea9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180066d4e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180066d4e`
- `WS2_32!WSASocketW` at `0x180066dd0`
- `WS2_32!WSASocketW` at `0x180066dd0`
- `WS2_32!__imp_closesocket` at `0x180066d96`
- `WS2_32!__imp_closesocket` at `0x180066ebc`
- `WS2_32!__imp_closesocket` at `0x180066d96`
- `WS2_32!__imp_closesocket` at `0x180066ebc`

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
0x180066d20  mov     [rsp+arg_8], rbx
0x180066d25  mov     [rsp+arg_10], rbp
0x180066d2a  push    rdi
0x180066d2b  sub     rsp, 50h
0x180066d2f  movsxd  rdi, dword ptr [rcx+0Ch]
0x180066d33  mov     rbx, rcx
0x180066d36  mov     rcx, [rcx+68h]
0x180066d3a  test    rcx, rcx
0x180066d3d  jz      loc_180066EF4
0x180066d43  mov     rcx, [rcx]; pti
0x180066d46  xor     r9d, r9d; msWindowLength
0x180066d49  xor     r8d, r8d; msPeriod
0x180066d4c  xor     edx, edx; pftDueTime
0x180066d4e  call    cs:__imp_SetThreadpoolTimer
0x180066d55  nop     dword ptr [rax+rax+00h]
0x180066d5a  lea     rcx, [rbx+78h]; this
0x180066d5e  call    ?Lock@CSpinLock@@QEAAXXZ; CSpinLock::Lock(void)
0x180066d63  mov     eax, [rbx+0C0h]
0x180066d69  test    eax, eax
0x180066d6b  jz      loc_180066EDB
0x180066d71  cmp     qword ptr [rbx+0C8h], 0
0x180066d79  jz      loc_180066EDB
0x180066d7f  mov     rcx, [rbx+0D0h]; s
0x180066d86  lea     rbp, ?WsTransportTable@@3QBUWS_TRANS_INFO@@B; WS_TRANS_INFO const near * const WsTransportTable
0x180066d8d  imul    rdi, 0Eh
0x180066d91  test    rcx, rcx
0x180066d94  jz      short loc_180066DAD
0x180066d96  call    cs:__imp_closesocket
0x180066d9d  nop     dword ptr [rax+rax+00h]
0x180066da2  mov     qword ptr [rbx+0D0h], 0
0x180066dad  movsx   r8d, word ptr [rdi+rbp+4]; protocol
0x180066db3  xor     r9d, r9d; lpProtocolInfo
0x180066db6  movsx   edx, word ptr [rdi+rbp+2]; type
0x180066dbb  movsx   ecx, word ptr [rdi+rbp]; af
0x180066dbf  mov     edi, 1
0x180066dc4  mov     [rsp+58h+dwFlags], edi; dwFlags
0x180066dc8  mov     [rsp+58h+g], 0; g
0x180066dd0  call    cs:__imp_WSASocketW
0x180066dd7  nop     dword ptr [rax+rax+00h]
0x180066ddc  mov     [rbx+0D0h], rax
0x180066de3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180066de7  jz      loc_180066EC8
0x180066ded  xor     r8d, r8d; dwFlags
0x180066df0  mov     edx, edi; dwMask
0x180066df2  mov     rcx, rax; hObject
0x180066df5  call    cs:__imp_SetHandleInformation
0x180066dfc  nop     dword ptr [rax+rax+00h]
0x180066e01  test    eax, eax
0x180066e03  jz      loc_180066EB5
0x180066e09  mov     rcx, [rbx+298h]
0x180066e10  mov     [rsp+58h+arg_0], 0
0x180066e18  mov     rcx, [rcx]; pio
0x180066e1b  call    cs:__imp_StartThreadpoolIo
0x180066e22  nop     dword ptr [rax+rax+00h]
0x180066e27  lock add [rbx+0C4h], edi
0x180066e2e  mov     rdx, [rbx+0D0h]
0x180066e35  lea     rax, [rsp+58h+arg_0]
0x180066e3a  lea     rcx, [rbx+88h]
0x180066e41  xor     r9d, r9d
0x180066e44  mov     [rsp+58h+var_20], rcx
0x180066e49  lea     r8, [rbx+0D8h]
0x180066e50  mov     rcx, [rbx+0C8h]
0x180066e57  mov     [rsp+58h+var_28], rax
0x180066e5c  mov     eax, 90h
0x180066e61  mov     [rsp+58h+dwFlags], eax
0x180066e65  mov     [rsp+58h+g], eax
0x180066e69  mov     rax, [rbx+280h]
0x180066e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e75  test    eax, eax
0x180066e77  jnz     short loc_180066EDB
0x180066e79  call    cs:__imp_GetLastError
0x180066e80  nop     dword ptr [rax+rax+00h]
0x180066e85  cmp     eax, 3E5h
0x180066e8a  jz      short loc_180066EDB
0x180066e8c  lock dec dword ptr [rbx+0C4h]
0x180066e93  call    cs:__imp_GetLastError
0x180066e9a  nop     dword ptr [rax+rax+00h]
0x180066e9f  mov     rcx, [rbx+298h]
0x180066ea6  mov     rcx, [rcx]; pio
0x180066ea9  call    cs:__imp_CancelThreadpoolIo
0x180066eb0  nop     dword ptr [rax+rax+00h]
0x180066eb5  mov     rcx, [rbx+0D0h]; s
0x180066ebc  call    cs:__imp_closesocket
0x180066ec3  nop     dword ptr [rax+rax+00h]
0x180066ec8  mov     rcx, rbx; struct BASE_ADDRESS *
0x180066ecb  mov     qword ptr [rbx+0D0h], 0
0x180066ed6  call    ?COMMON_ResubmitListen@@YAXPEAUBASE_ADDRESS@@@Z; COMMON_ResubmitListen(BASE_ADDRESS *)
0x180066edb  mov     edx, [rbx+78h]
0x180066ede  add     edx, 0F0000000h
0x180066ee4  mov     eax, edx
0x180066ee6  and     eax, 0F0000000h
0x180066eeb  neg     eax
0x180066eed  sbb     ecx, ecx
0x180066eef  and     ecx, edx
0x180066ef1  xchg    ecx, [rbx+78h]
0x180066ef4  mov     rbx, [rsp+58h+arg_8]
0x180066ef9  mov     rbp, [rsp+58h+arg_10]
0x180066efe  add     rsp, 50h
0x180066f02  pop     rdi
0x180066f03  retn
```
