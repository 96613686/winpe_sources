# SrvNetQUICListenerOpen

- ea: `0x1400495ac`
- end: `0x1400498ca`
- name: `SrvNetQUICListenerOpen`
- size: `798`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140042864`

## callees

- `0x14001389c`
- `0x140015790`
- `0x14001c700`
- `0x14002a3e0`
- `0x14002a4c0`
- `0x1400495ac`

## import_xrefs

- `ntoskrnl!RtlIpv6StringToAddressW` at `0x1400496ae`
- `ntoskrnl!RtlIpv6StringToAddressW` at `0x1400496ae`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400495fd`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400495fd`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x140049681`
- `ntoskrnl!RtlIpv4StringToAddressW` at `0x140049681`

## pseudocode

```c
__int64 __fastcall SrvNetQUICListenerOpen(__int64 a1, __int64 a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  bool v9; // cf
  __int64 v10; // rcx
  __int16 v11; // ax
  NTSTATUS v12; // eax
  int v14; // [rsp+30h] [rbp-40h] BYREF
  LPCWSTR Terminator; // [rsp+38h] [rbp-38h] BYREF
  _QWORD Addr[4]; // [rsp+40h] [rbp-30h] BYREF

  memset(Addr, 0, 28);
  v14 = 0;
  v4 = RtlRunOnceExecuteOnce(&SrvNetQUICInitOnce, (PRTL_RUN_ONCE_INIT_FN)SrvNetQUICRunOnceInitialize, 0, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v7 = 11;
LABEL_6:
      v8 = (unsigned int)v4;
LABEL_44:
      WPP_SF_d(v6->AttachedDevice, v7, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids, v8);
      goto LABEL_45;
    }
    goto LABEL_45;
  }
  v9 = *(_WORD *)a2 < 0x1Au;
  Terminator = 0;
  if ( v9 )
    goto LABEL_38;
  v10 = *(_QWORD *)(a2 + 8);
  v11 = *(_WORD *)(v10 + 36);
  if ( v11 == 52 )
  {
    LOWORD(Addr[0]) = 2;
    v12 = RtlIpv4StringToAddressW((PCWSTR)(v10 + 50), 1u, &Terminator, (struct in_addr *)Addr + 1);
    goto LABEL_12;
  }
  if ( v11 != 54 )
  {
LABEL_38:
    v5 = -1073741811;
LABEL_39:
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_45;
    }
    v7 = 12;
LABEL_43:
    v8 = v5;
    goto LABEL_44;
  }
  LOWORD(Addr[0]) = 23;
  v12 = RtlIpv6StringToAddressW((PCWSTR)(v10 + 50), &Terminator, (struct in6_addr *)&Addr[1]);
LABEL_12:
  v5 = v12;
  if ( v12 < 0 )
    goto LABEL_39;
  v4 = SrvNetQUICGetInterfaceIndexFromTransportName(a2, &v14);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v7 = 13;
      goto LABEL_6;
    }
LABEL_45:
    if ( *(_QWORD *)(a1 + 32) )
    {
      (*(void (**)(void))(MsQuic + 96))();
      *(_QWORD *)(a1 + 32) = 0;
    }
    return v5;
  }
  WORD1(Addr[0]) = __ROR2__(**(_WORD **)(a1 + 368), 8);
  if ( LOWORD(Addr[0]) != 2 )
    LODWORD(Addr[3]) = v14;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(), __int64, __int64))(MsQuic + 88))(
         SMBQuicRegistration,
         SrvNetQuicServerListenerCallback,
         a1,
         a1 + 32);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v7 = 14;
      goto LABEL_6;
    }
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids);
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, _QWORD *))(MsQuic + 104))(
         *(_QWORD *)(a1 + 32),
         &qword_14002F110,
         1,
         Addr);
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_45;
    }
    v7 = 16;
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x15u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids);
  }
  return v5;
}

```

## disassembly

```asm
0x1400495ac  mov     [rsp-28h+arg_10], rbx
0x1400495b1  mov     [rsp-28h+arg_18], rsi
0x1400495b6  push    rbp
0x1400495b7  push    rdi
0x1400495b8  push    r13
0x1400495ba  push    r14
0x1400495bc  push    r15
0x1400495be  mov     rbp, rsp
0x1400495c1  sub     rsp, 70h
0x1400495c5  mov     rax, cs:__security_cookie
0x1400495cc  xor     rax, rsp
0x1400495cf  mov     [rbp+var_10], rax
0x1400495d3  xorps   xmm0, xmm0
0x1400495d6  mov     rdi, rdx
0x1400495d9  mov     r14, rcx
0x1400495dc  lea     rdx, SrvNetQUICRunOnceInitialize; InitFn
0x1400495e3  xor     eax, eax
0x1400495e5  lea     rcx, SrvNetQUICInitOnce; RunOnce
0x1400495ec  movups  xmmword ptr [rbp+Addr.S_un], xmm0
0x1400495f0  xor     r9d, r9d; Context
0x1400495f3  mov     [rbp+var_40], eax
0x1400495f6  xor     r8d, r8d; Parameter
0x1400495f9  movups  xmmword ptr [rbp+Addr.S_un+0Ch], xmm0
0x1400495fd  call    cs:__imp_RtlRunOnceExecuteOnce
0x140049604  nop     dword ptr [rax+rax+00h]
0x140049609  mov     ebx, eax
0x14004960b  test    eax, eax
0x14004960d  jns     short loc_140049648
0x14004960f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049616  lea     rsi, WPP_GLOBAL_Control
0x14004961d  cmp     rcx, rsi
0x140049620  jz      loc_140049881
0x140049626  bt      dword ptr [rcx+2Ch], 15h
0x14004962b  jnb     loc_140049881
0x140049631  cmp     byte ptr [rcx+29h], 1
0x140049635  jb      loc_140049881
0x14004963b  mov     edx, 0Bh
0x140049640  mov     r9d, eax
0x140049643  jmp     loc_140049871
0x140049648  cmp     word ptr [rdi], 1Ah
0x14004964c  mov     [rbp+Terminator], 0
0x140049654  jb      loc_140049844
0x14004965a  mov     rcx, [rdi+8]
0x14004965e  mov     r13d, 2
0x140049664  movzx   eax, word ptr [rcx+24h]
0x140049668  cmp     ax, 34h ; '4'
0x14004966c  jnz     short loc_14004968F
0x14004966e  add     rcx, 32h ; '2'; S
0x140049672  mov     word ptr [rbp+Addr.S_un], r13w
0x140049677  lea     r9, [rbp+Addr.S_un+4]; Addr
0x14004967b  mov     dl, 1; Strict
0x14004967d  lea     r8, [rbp+Terminator]; Terminator
0x140049681  call    cs:__imp_RtlIpv4StringToAddressW
0x140049688  nop     dword ptr [rax+rax+00h]
0x14004968d  jmp     short loc_1400496BA
0x14004968f  cmp     ax, 36h ; '6'
0x140049693  jnz     loc_140049844
0x140049699  mov     eax, 17h
0x14004969e  lea     r8, [rbp+Addr.S_un+8]; Addr
0x1400496a2  add     rcx, 32h ; '2'; S
0x1400496a6  mov     word ptr [rbp+Addr.S_un], ax
0x1400496aa  lea     rdx, [rbp+Terminator]; Terminator
0x1400496ae  call    cs:__imp_RtlIpv6StringToAddressW
0x1400496b5  nop     dword ptr [rax+rax+00h]
0x1400496ba  mov     ebx, eax
0x1400496bc  test    eax, eax
0x1400496be  js      loc_140049849
0x1400496c4  lea     rdx, [rbp+var_40]
0x1400496c8  mov     rcx, rdi
0x1400496cb  call    SrvNetQUICGetInterfaceIndexFromTransportName
0x1400496d0  mov     ebx, eax
0x1400496d2  test    eax, eax
0x1400496d4  jns     short loc_14004970C
0x1400496d6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400496dd  lea     rsi, WPP_GLOBAL_Control
0x1400496e4  cmp     rcx, rsi
0x1400496e7  jz      loc_140049881
0x1400496ed  bt      dword ptr [rcx+2Ch], 15h
0x1400496f2  jnb     loc_140049881
0x1400496f8  cmp     byte ptr [rcx+29h], 1
0x1400496fc  jb      loc_140049881
0x140049702  mov     edx, 0Dh
0x140049707  jmp     loc_140049640
0x14004970c  mov     rax, [r14+170h]
0x140049713  movzx   ecx, word ptr [rax]
0x140049716  ror     cx, 8
0x14004971a  mov     word ptr [rbp+Addr.S_un+2], cx
0x14004971e  cmp     word ptr [rbp+Addr.S_un], r13w
0x140049723  jz      short loc_14004972B
0x140049725  mov     eax, [rbp+var_40]
0x140049728  mov     [rbp+var_18], eax
0x14004972b  mov     rax, cs:MsQuic
0x140049732  lea     r9, [r14+20h]
0x140049736  mov     rcx, cs:SMBQuicRegistration
0x14004973d  lea     rdx, SrvNetQuicServerListenerCallback
0x140049744  mov     r8, r14
0x140049747  mov     rax, [rax+58h]
0x14004974b  call    _guard_dispatch_icall
0x140049750  mov     ebx, eax
0x140049752  test    eax, eax
0x140049754  jns     short loc_14004978C
0x140049756  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004975d  lea     rsi, WPP_GLOBAL_Control
0x140049764  cmp     rcx, rsi
0x140049767  jz      loc_140049881
0x14004976d  bt      dword ptr [rcx+2Ch], 15h
0x140049772  jnb     loc_140049881
0x140049778  cmp     byte ptr [rcx+29h], 1
0x14004977c  jb      loc_140049881
0x140049782  mov     edx, 0Eh
0x140049787  jmp     loc_140049640
0x14004978c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049793  lea     rsi, WPP_GLOBAL_Control
0x14004979a  cmp     rcx, rsi
0x14004979d  jz      short loc_1400497C1
0x14004979f  bt      dword ptr [rcx+2Ch], 15h
0x1400497a4  jnb     short loc_1400497C1
0x1400497a6  cmp     [rcx+29h], r13b
0x1400497aa  jb      short loc_1400497C1
0x1400497ac  mov     rcx, [rcx+18h]
0x1400497b0  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x1400497b7  mov     edx, 0Fh
0x1400497bc  call    WPP_SF_
0x1400497c1  mov     rax, cs:MsQuic
0x1400497c8  lea     r9, [rbp+Addr]
0x1400497cc  mov     rcx, [r14+20h]
0x1400497d0  lea     rdx, qword_14002F110
0x1400497d7  mov     r8d, 1
0x1400497dd  mov     rax, [rax+68h]
0x1400497e1  call    _guard_dispatch_icall
0x1400497e6  mov     ebx, eax
0x1400497e8  test    eax, eax
0x1400497ea  jns     short loc_140049810
0x1400497ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400497f3  cmp     rcx, rsi
0x1400497f6  jz      loc_140049881
0x1400497fc  bt      dword ptr [rcx+2Ch], 15h
0x140049801  jnb     short loc_140049881
0x140049803  cmp     byte ptr [rcx+29h], 1
0x140049807  jb      short loc_140049881
0x140049809  mov     edx, 10h
0x14004980e  jmp     short loc_14004986E
0x140049810  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049817  cmp     rcx, rsi
0x14004981a  jz      loc_1400498A2
0x140049820  bt      dword ptr [rcx+2Ch], 15h
0x140049825  jnb     short loc_1400498A2
0x140049827  cmp     [rcx+29h], r13b
0x14004982b  jb      short loc_1400498A2
0x14004982d  mov     rcx, [rcx+18h]
0x140049831  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x140049838  mov     edx, 11h
0x14004983d  call    WPP_SF_
0x140049842  jmp     short loc_1400498A2
0x140049844  mov     ebx, 0C000000Dh
0x140049849  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049850  lea     rsi, WPP_GLOBAL_Control
0x140049857  cmp     rcx, rsi
0x14004985a  jz      short loc_140049881
0x14004985c  bt      dword ptr [rcx+2Ch], 15h
0x140049861  jnb     short loc_140049881
0x140049863  cmp     byte ptr [rcx+29h], 1
0x140049867  jb      short loc_140049881
0x140049869  mov     edx, 0Ch
0x14004986e  mov     r9d, ebx
0x140049871  mov     rcx, [rcx+18h]
0x140049875  lea     r8, WPP_7ac1a65f8ae33ba0b63887aed8f61f96_Traceguids
0x14004987c  call    WPP_SF_d
0x140049881  mov     rcx, [r14+20h]
0x140049885  test    rcx, rcx
0x140049888  jz      short loc_1400498A2
0x14004988a  mov     rax, cs:MsQuic
0x140049891  mov     rax, [rax+60h]
0x140049895  call    _guard_dispatch_icall
0x14004989a  mov     qword ptr [r14+20h], 0
0x1400498a2  mov     eax, ebx
0x1400498a4  mov     rcx, [rbp+var_10]
0x1400498a8  xor     rcx, rsp; StackCookie
0x1400498ab  call    __security_check_cookie
0x1400498b0  lea     r11, [rsp+70h+var_s0]
0x1400498b5  mov     rbx, [r11+40h]
0x1400498b9  mov     rsi, [r11+48h]
0x1400498bd  mov     rsp, r11
0x1400498c0  pop     r15
0x1400498c2  pop     r14
0x1400498c4  pop     r13
0x1400498c6  pop     rdi
0x1400498c7  pop     rbp
0x1400498c8  retn
```
