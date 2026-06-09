# W3WP_HOST::ProcessPreloadApplications(ulong)

- ea: `0x1800067f4`
- end: `0x1800068b3`
- name: `?ProcessPreloadApplications@W3WP_HOST@@QEAAJK@Z`
- size: `191`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001180`
- `0x180004b20`

## callees

- `0x180001890`
- `0x180003914`
- `0x180006754`
- `0x1800067f4`
- `0x1800068bc`
- `0x1800089f4`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::ProcessPreloadApplications(W3WP_HOST *this, int a2)
{
  W3WP_HOST *v2; // rbx
  int v4; // edi
  __int64 v6; // rcx
  int v7; // [rsp+58h] [rbp+10h] BYREF

  v2 = g_pW3WPHost;
  v4 = W3WP_HOST::CheckConfigFile(g_pW3WPHost);
  if ( v4 >= 0 )
  {
    if ( (a2 & 0xFFFD) == 0 )
    {
      v4 = W3WP_HOST::ProcessWebhostPreloadApplications(v2);
      if ( v4 < 0 )
        goto LABEL_14;
    }
    if ( (unsigned __int16)(a2 - 1) <= 1u )
      v4 = W3WP_HOST::ProcessHttpPreloadApplications((PROTOCOL_MANAGER_LIST ***)v2, (a2 & 0xFFFF0000) == 0x20000);
    if ( v4 >= 0 )
    {
      v6 = *((_QWORD *)v2 + 11);
      v7 = a2;
      WP_IPM::WriteMessage(v6, 24, 4u, (__int64)&v7);
    }
    else
    {
LABEL_14:
      if ( !_InterlockedCompareExchange((volatile signed __int32 *)v2 + 397, 1, 0) )
        WP_IPM::SendFatalFailure(*((_QWORD *)v2 + 11), 8u);
    }
    return (unsigned int)v4;
  }
  else
  {
    WP_IPM::SendFatalFailure(*((_QWORD *)v2 + 11), 9u);
    return 0;
  }
}

```

## disassembly

```asm
0x1800067f4  push    rbx
0x1800067f6  push    rbp
0x1800067f7  push    rsi
0x1800067f8  push    rdi
0x1800067f9  sub     rsp, 28h
0x1800067fd  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180006804  mov     esi, edx
0x180006806  mov     rcx, rbx; this
0x180006809  call    ?CheckConfigFile@W3WP_HOST@@QEAAJXZ; W3WP_HOST::CheckConfigFile(void)
0x18000680e  mov     edi, eax
0x180006810  test    eax, eax
0x180006812  jns     short loc_180006829
0x180006814  mov     rcx, [rbx+58h]
0x180006818  mov     edx, 9
0x18000681d  call    ?SendFatalFailure@WP_IPM@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendFatalFailure(IPM_WP_SHUTDOWN_MSG)
0x180006822  xor     eax, eax
0x180006824  jmp     loc_1800068A9
0x180006829  mov     eax, 0FFFDh
0x18000682e  mov     ebp, 1
0x180006833  test    ax, si
0x180006836  jnz     short loc_180006846
0x180006838  mov     rcx, rbx; this
0x18000683b  call    ?ProcessWebhostPreloadApplications@W3WP_HOST@@QEAAJXZ; W3WP_HOST::ProcessWebhostPreloadApplications(void)
0x180006840  mov     edi, eax
0x180006842  test    eax, eax
0x180006844  js      short loc_18000688D
0x180006846  movzx   eax, si
0x180006849  sub     ax, bp
0x18000684c  cmp     ax, bp
0x18000684f  ja      short loc_18000686C
0x180006851  xor     edx, edx
0x180006853  mov     eax, esi
0x180006855  and     eax, 0FFFF0000h
0x18000685a  mov     rcx, rbx; this
0x18000685d  cmp     eax, 20000h
0x180006862  setz    dl; int
0x180006865  call    ?ProcessHttpPreloadApplications@W3WP_HOST@@QEAAJH@Z; W3WP_HOST::ProcessHttpPreloadApplications(int)
0x18000686a  mov     edi, eax
0x18000686c  test    edi, edi
0x18000686e  js      short loc_18000688D
0x180006870  mov     rcx, [rbx+58h]
0x180006874  lea     r9, [rsp+48h+arg_8]
0x180006879  mov     edx, 18h
0x18000687e  mov     [rsp+48h+arg_8], esi
0x180006882  lea     r8d, [rdx-14h]
0x180006886  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x18000688b  jmp     short loc_1800068A7
0x18000688d  xor     eax, eax
0x18000688f  lock cmpxchg [rbx+634h], ebp
0x180006897  jnz     short loc_1800068A7
0x180006899  mov     rcx, [rbx+58h]
0x18000689d  mov     edx, 8
0x1800068a2  call    ?SendFatalFailure@WP_IPM@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendFatalFailure(IPM_WP_SHUTDOWN_MSG)
0x1800068a7  mov     eax, edi
0x1800068a9  add     rsp, 28h
0x1800068ad  pop     rdi
0x1800068ae  pop     rsi
0x1800068af  pop     rbp
0x1800068b0  pop     rbx
0x1800068b1  retn
```
