# W3WP_HOST::ProcessPreloadApplications(ulong)

- ea: `0x1800061dc`
- end: `0x18000629a`
- name: `?ProcessPreloadApplications@W3WP_HOST@@QEAAJK@Z`
- size: `190`
- prototype: `__int64 __fastcall(W3WP_HOST *this, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001170`
- `0x180004750`

## callees

- `0x180001830`
- `0x180003684`
- `0x180006144`
- `0x1800061dc`
- `0x1800062a0`
- `0x18000812c`

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
      v4 = W3WP_HOST::ProcessHttpPreloadApplications(v2, (a2 & 0xFFFF0000) == 0x20000);
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
        WP_IPM::SendFatalFailure(*((_QWORD *)v2 + 11), 8);
    }
    return (unsigned int)v4;
  }
  else
  {
    WP_IPM::SendFatalFailure(*((_QWORD *)v2 + 11), 9);
    return 0;
  }
}

```

## disassembly

```asm
0x1800061dc  push    rbx
0x1800061de  push    rbp
0x1800061df  push    rsi
0x1800061e0  push    rdi
0x1800061e1  sub     rsp, 28h
0x1800061e5  mov     rbx, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800061ec  mov     esi, edx
0x1800061ee  mov     rcx, rbx; this
0x1800061f1  call    ?CheckConfigFile@W3WP_HOST@@QEAAJXZ; W3WP_HOST::CheckConfigFile(void)
0x1800061f6  mov     edi, eax
0x1800061f8  test    eax, eax
0x1800061fa  jns     short loc_180006211
0x1800061fc  mov     rcx, [rbx+58h]
0x180006200  mov     edx, 9
0x180006205  call    ?SendFatalFailure@WP_IPM@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendFatalFailure(IPM_WP_SHUTDOWN_MSG)
0x18000620a  xor     eax, eax
0x18000620c  jmp     loc_180006291
0x180006211  mov     eax, 0FFFDh
0x180006216  mov     ebp, 1
0x18000621b  test    ax, si
0x18000621e  jnz     short loc_18000622E
0x180006220  mov     rcx, rbx; this
0x180006223  call    ?ProcessWebhostPreloadApplications@W3WP_HOST@@QEAAJXZ; W3WP_HOST::ProcessWebhostPreloadApplications(void)
0x180006228  mov     edi, eax
0x18000622a  test    eax, eax
0x18000622c  js      short loc_180006275
0x18000622e  movzx   eax, si
0x180006231  sub     ax, bp
0x180006234  cmp     ax, bp
0x180006237  ja      short loc_180006254
0x180006239  xor     edx, edx
0x18000623b  mov     eax, esi
0x18000623d  and     eax, 0FFFF0000h
0x180006242  mov     rcx, rbx; this
0x180006245  cmp     eax, 20000h
0x18000624a  setz    dl; int
0x18000624d  call    ?ProcessHttpPreloadApplications@W3WP_HOST@@QEAAJH@Z; W3WP_HOST::ProcessHttpPreloadApplications(int)
0x180006252  mov     edi, eax
0x180006254  test    edi, edi
0x180006256  js      short loc_180006275
0x180006258  mov     rcx, [rbx+58h]
0x18000625c  lea     r9, [rsp+48h+arg_8]
0x180006261  mov     edx, 18h
0x180006266  mov     [rsp+48h+arg_8], esi
0x18000626a  lea     r8d, [rdx-14h]
0x18000626e  call    ?WriteMessage@WP_IPM@@AEAAJW4IPM_OPCODE@@KPEAX@Z; WP_IPM::WriteMessage(IPM_OPCODE,ulong,void *)
0x180006273  jmp     short loc_18000628F
0x180006275  xor     eax, eax
0x180006277  lock cmpxchg [rbx+634h], ebp
0x18000627f  jnz     short loc_18000628F
0x180006281  mov     rcx, [rbx+58h]
0x180006285  mov     edx, 8
0x18000628a  call    ?SendFatalFailure@WP_IPM@@QEAAXW4IPM_WP_SHUTDOWN_MSG@@@Z; WP_IPM::SendFatalFailure(IPM_WP_SHUTDOWN_MSG)
0x18000628f  mov     eax, edi
0x180006291  add     rsp, 28h
0x180006295  pop     rdi
0x180006296  pop     rsi
0x180006297  pop     rbp
0x180006298  pop     rbx
0x180006299  retn
```
