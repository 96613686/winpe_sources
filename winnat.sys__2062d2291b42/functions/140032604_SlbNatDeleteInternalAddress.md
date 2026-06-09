# SlbNatDeleteInternalAddress

- ea: `0x140032604`
- end: `0x1400326c7`
- name: `SlbNatDeleteInternalAddress`
- size: `195`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002f380`
- `0x140032430`

## callees

- `0x14000d648`
- `0x1400148fc`
- `0x14001f320`
- `0x140032604`
- `0x140034644`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003269f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003269f`

## pseudocode

```c
void __fastcall SlbNatDeleteInternalAddress(_DWORD *P, __int64 a2)
{
  int v4; // r8d
  int v5; // [rsp+20h] [rbp-58h]
  _OWORD v6[2]; // [rsp+40h] [rbp-38h] BYREF

  if ( (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
  {
    memset(v6, 0, 28);
    INETADDR_SETSOCKADDR(2, (unsigned int)v6, (_DWORD)P + 16, 0, 0);
    if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
      McTemplateK0zqbr1q_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        (unsigned int)WINNATM_INTERNAL_ADDRESS_REMOVAL,
        v4,
        a2 + 80,
        v5,
        (__int64)v6,
        P[8]);
  }
  SlbNatIpsRemoveInterfaceMapping(P[8], a2, *(_QWORD *)(a2 + 16));
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140032604  mov     [rsp+arg_10], rbx
0x140032609  push    rdi
0x14003260a  sub     rsp, 70h
0x14003260e  mov     rax, cs:__security_cookie
0x140032615  xor     rax, rsp
0x140032618  mov     [rsp+78h+var_18], rax
0x14003261d  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x140032624  mov     rdi, rdx
0x140032627  mov     rbx, rcx
0x14003262a  jz      short loc_14003268E
0x14003262c  xor     eax, eax
0x14003262e  lea     r8, [rcx+10h]
0x140032632  xorps   xmm0, xmm0
0x140032635  mov     [rsp+78h+var_58], ax
0x14003263a  movups  [rsp+78h+var_38], xmm0
0x14003263f  xor     r9d, r9d
0x140032642  lea     rdx, [rsp+78h+var_38]
0x140032647  lea     ecx, [rax+2]
0x14003264a  movups  [rsp+78h+var_38+0Ch], xmm0
0x14003264f  call    INETADDR_SETSOCKADDR
0x140032654  cmp     cs:dword_140027104, 1
0x14003265b  jnz     short loc_14003268E
0x14003265d  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x140032664  jz      short loc_14003268E
0x140032666  mov     eax, [rbx+20h]
0x140032669  lea     r9, [rdi+50h]
0x14003266d  mov     [rsp+78h+var_48], eax
0x140032671  lea     rdx, WINNATM_INTERNAL_ADDRESS_REMOVAL
0x140032678  lea     rax, [rsp+78h+var_38]
0x14003267d  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140032684  mov     [rsp+78h+var_50], rax
0x140032689  call    McTemplateK0zqbr1q_EtwWriteTransfer
0x14003268e  mov     r8, [rdi+10h]
0x140032692  mov     ecx, [rbx+20h]
0x140032695  call    SlbNatIpsRemoveInterfaceMapping
0x14003269a  xor     edx, edx; Tag
0x14003269c  mov     rcx, rbx; P
0x14003269f  call    cs:__imp_ExFreePoolWithTag
0x1400326a6  nop     dword ptr [rax+rax+00h]
0x1400326ab  mov     rcx, [rsp+78h+var_18]
0x1400326b0  xor     rcx, rsp; StackCookie
0x1400326b3  call    __security_check_cookie
0x1400326b8  mov     rbx, [rsp+78h+arg_10]
0x1400326c0  add     rsp, 70h
0x1400326c4  pop     rdi
0x1400326c5  retn
```
