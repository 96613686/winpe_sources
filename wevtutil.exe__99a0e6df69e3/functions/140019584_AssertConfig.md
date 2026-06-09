# AssertConfig

- ea: `0x140019584`
- end: `0x14001968e`
- name: `AssertConfig`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400088e0`

## callees

- `0x14000cc80`
- `0x140019584`
- `0x140022cec`
- `0x140023c6c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x140019631`
- `RPCRT4!NdrClientCall3` at `0x140019631`

## pseudocode

```c
__int64 __fastcall AssertConfig(__int64 a1, __int64 a2, int a3)
{
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int Pointer; // eax
  int v11; // [rsp+28h] [rbp-30h]

  if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    v6 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v6;
    }
    v8 = 94;
LABEL_6:
    WPP_SF_d(v7[2], v8, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, v6);
    return v6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids);
  }
  v11 = a3;
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xFu, 0, a1, a2, v11).Pointer;
  v6 = Pointer;
  if ( Pointer != 1722 && Pointer != 120 && Pointer )
  {
    eventlog::ai::WarningMessage((eventlog::ai *)0x60, Pointer);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v6;
    }
    v8 = 96;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x140019584  push    rbx
0x140019586  push    rbp
0x140019587  push    rsi
0x140019588  push    rdi
0x140019589  sub     rsp, 38h
0x14001958d  mov     ebx, r8d
0x140019590  mov     rsi, rdx
0x140019593  mov     rbp, rcx
0x140019596  test    r8d, 0FFFFFFFEh
0x14001959d  jz      short loc_1400195E0
0x14001959f  lea     rdi, WPP_GLOBAL_Control
0x1400195a6  mov     ebx, 57h ; 'W'
0x1400195ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400195b2  cmp     rcx, rdi
0x1400195b5  jz      short loc_1400195D9
0x1400195b7  test    byte ptr [rcx+1Ch], 4
0x1400195bb  jz      short loc_1400195D9
0x1400195bd  cmp     byte ptr [rcx+19h], 2
0x1400195c1  jb      short loc_1400195D9
0x1400195c3  lea     edx, [rbx+7]
0x1400195c6  mov     r9d, ebx
0x1400195c9  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x1400195d0  mov     rcx, [rcx+10h]
0x1400195d4  call    WPP_SF_d
0x1400195d9  mov     eax, ebx
0x1400195db  jmp     loc_140019685
0x1400195e0  lea     rdi, WPP_GLOBAL_Control
0x1400195e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400195ee  cmp     rcx, rdi
0x1400195f1  jz      short loc_140019617
0x1400195f3  test    byte ptr [rcx+1Ch], 4
0x1400195f7  jz      short loc_140019617
0x1400195f9  cmp     byte ptr [rcx+19h], 5
0x1400195fd  jb      short loc_140019617
0x1400195ff  mov     edx, 5Fh ; '_'
0x140019604  mov     r9, rsi
0x140019607  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001960e  mov     rcx, [rcx+10h]
0x140019612  call    WPP_SF_S
0x140019617  mov     [rsp+58h+var_30], ebx
0x14001961b  mov     [rsp+58h+var_38], rsi
0x140019620  mov     r9, rbp
0x140019623  xor     r8d, r8d; pReturnValue
0x140019626  lea     edx, [r8+0Fh]; nProcNum
0x14001962a  lea     rcx, pProxyInfo; pProxyInfo
0x140019631  call    cs:__imp_NdrClientCall3
0x140019637  mov     rbx, rax
0x14001963a  cmp     eax, 6BAh
0x14001963f  jz      short loc_140019683
0x140019641  cmp     ebx, 78h ; 'x'
0x140019644  jz      short loc_140019683
0x140019646  test    ebx, ebx
0x140019648  jz      short loc_140019683
0x14001964a  mov     edx, ebx; unsigned int
0x14001964c  mov     esi, 60h ; '`'
0x140019651  mov     ecx, esi; this
0x140019653  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x140019658  mov     rcx, cs:WPP_GLOBAL_Control
0x14001965f  cmp     rcx, rdi
0x140019662  jz      loc_1400195D9
0x140019668  test    byte ptr [rcx+1Ch], 4
0x14001966c  jz      loc_1400195D9
0x140019672  cmp     byte ptr [rcx+19h], 2
0x140019676  jb      loc_1400195D9
0x14001967c  mov     edx, esi
0x14001967e  jmp     loc_1400195C6
0x140019683  xor     eax, eax
0x140019685  add     rsp, 38h
0x140019689  pop     rdi
0x14001968a  pop     rsi
0x14001968b  pop     rbp
0x14001968c  pop     rbx
0x14001968d  retn
```
