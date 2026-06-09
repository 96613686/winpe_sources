# SlbNatDeleteExternalAddress

- ea: `0x140032228`
- end: `0x14003242a`
- name: `SlbNatDeleteExternalAddress`
- size: `514`
- prototype: `__int64 __fastcall(char *P, __int64)`
- caller_count: `9`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14000975c`
- `0x14000bc6c`
- `0x140015478`
- `0x1400319dc`
- `0x140032430`
- `0x1400328cc`
- `0x140033444`
- `0x1400335e8`
- `0x140033d14`

## callees

- `0x140008560`
- `0x14000d648`
- `0x140014830`
- `0x140015614`
- `0x140019320`
- `0x14001f320`
- `0x14001f680`
- `0x140032228`
- `0x1400326d0`
- `0x140034644`
- `0x140035620`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400323d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400323d5`
- `fwpkclnt!FwpmEngineClose0` at `0x1400322ef`
- `fwpkclnt!FwpmEngineClose0` at `0x1400322ef`

## pseudocode

```c
__int64 __fastcall SlbNatDeleteExternalAddress(char *P, __int64 a2)
{
  _QWORD **v3; // rbx
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  __int16 v7; // bx
  char v8; // di
  size_t v9; // r8
  int v10; // r8d
  __int64 v11; // rdx
  void *v12; // rcx
  int v13; // ecx
  int v14; // r8d
  int v15; // ecx
  __int64 v16; // r8
  __int64 result; // rax
  int v18; // [rsp+40h] [rbp-58h] BYREF
  _OWORD v19[2]; // [rsp+48h] [rbp-50h] BYREF

  v18 = 0;
  v19[0] = 0;
  v3 = (_QWORD **)(P + 16);
  while ( 1 )
  {
    v5 = *v3;
    if ( *v3 == v3 )
      break;
    if ( (_QWORD **)v5[1] != v3 || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5) )
      __fastfail(3u);
    *v3 = v6;
    v6[1] = v3;
    --*((_DWORD *)P + 8);
    SlbNatDeleteStaticMapping(v5);
  }
  v7 = *((_WORD *)P + 26);
  v8 = 4;
  v9 = 4;
  if ( v7 != 2 )
    v9 = 16;
  memmove(v19, P + 56, v9);
  if ( v7 != 2 )
    v8 = 16;
  LOBYTE(v10) = v8;
  WinNatLibDeleteAddress(
    (_DWORD)qword_1400273D8,
    (unsigned int)v19,
    v10,
    *((unsigned __int16 *)P + 36),
    *((_WORD *)P + 37));
  v12 = (void *)*((_QWORD *)P + 5);
  if ( v12 )
    FwpmEngineClose0(v12);
  if ( (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
  {
    v13 = *((unsigned __int16 *)P + 26);
    memset(v19, 0, 28);
    INETADDR_SETSOCKADDR(v13, (unsigned int)v19, (_DWORD)P + 56, 0, 0);
    if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
    {
      v15 = 28;
      if ( LOWORD(v19[0]) == 2 )
        v15 = 16;
      McTemplateK0zqbr1hh_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        (unsigned int)WINNATM_EXTERNAL_ADDRESS_REMOVAL,
        v14,
        a2 + 80,
        v15,
        (__int64)v19,
        *((_WORD *)P + 36),
        *((_WORD *)P + 37));
    }
  }
  if ( *((_QWORD *)P + 10) )
  {
    if ( *(_BYTE *)(a2 + 230) )
      v16 = 0;
    else
      v16 = *(_QWORD *)(a2 + 16);
    SlbNatIpsRemoveInterfaceMapping(*((unsigned int *)P + 22), v11, v16);
    SlbNatQueueWorkItem(**((_QWORD **)P + 10), &SlbNatAsyncFreePort, *((_QWORD *)P + 10));
  }
  if ( *((_DWORD *)P + 14) )
    --*(_DWORD *)(a2 + 40);
  else
    --dword_140027368;
  ExFreePoolWithTag(P, 0);
  result = SlbNatFindExternalAddressForLoopback(a2, &v18);
  if ( (int)result >= 0 )
  {
    result = SlbNatIpsFindInterfaceContext(1);
    if ( result )
      *(_DWORD *)(result + 36) = v18;
  }
  return result;
}

```

## disassembly

```asm
0x140032228  mov     [rsp+arg_10], rbx
0x14003222d  push    rbp
0x14003222e  push    rsi
0x14003222f  push    rdi
0x140032230  push    r13
0x140032232  push    r14
0x140032234  sub     rsp, 70h
0x140032238  mov     rax, cs:__security_cookie
0x14003223f  xor     rax, rsp
0x140032242  mov     [rsp+98h+var_30], rax
0x140032247  xorps   xmm0, xmm0
0x14003224a  mov     [rsp+98h+var_58], 0
0x140032252  movups  [rsp+98h+var_50], xmm0
0x140032257  mov     rbp, rdx
0x14003225a  lea     rbx, [rcx+10h]
0x14003225e  mov     rsi, rcx
0x140032261  mov     rcx, [rbx]; P
0x140032264  cmp     rcx, rbx
0x140032267  jz      short loc_140032293
0x140032269  cmp     [rcx+8], rbx
0x14003226d  jnz     short loc_14003228C
0x14003226f  mov     rax, [rcx]
0x140032272  cmp     [rax+8], rcx
0x140032276  jnz     short loc_14003228C
0x140032278  mov     [rbx], rax
0x14003227b  mov     rdx, rbp
0x14003227e  mov     [rax+8], rbx
0x140032282  dec     dword ptr [rsi+20h]
0x140032285  call    SlbNatDeleteStaticMapping
0x14003228a  jmp     short loc_140032261
0x14003228c  mov     ecx, 3
0x140032291  int     29h; Win8: RtlFailFast(ecx)
0x140032293  movzx   ebx, word ptr [rsi+34h]
0x140032297  lea     r14, [rsi+38h]
0x14003229b  mov     edi, 4
0x1400322a0  lea     rcx, [rsp+98h+var_50]; void *
0x1400322a5  cmp     bx, 2
0x1400322a9  mov     r8d, edi
0x1400322ac  mov     rdx, r14; Src
0x1400322af  lea     r13d, [rdi+0Ch]
0x1400322b3  cmovnz  r8d, r13d; Size
0x1400322b7  call    memmove
0x1400322bc  movzx   eax, word ptr [rsi+4Ah]
0x1400322c0  lea     rdx, [rsp+98h+var_50]
0x1400322c5  movzx   r9d, word ptr [rsi+48h]
0x1400322ca  cmp     bx, 2
0x1400322ce  mov     rcx, cs:qword_1400273D8
0x1400322d5  cmovnz  edi, r13d
0x1400322d9  mov     word ptr [rsp+98h+var_78], ax
0x1400322de  mov     r8b, dil
0x1400322e1  call    WinNatLibDeleteAddress
0x1400322e6  mov     rcx, [rsi+28h]; engineHandle
0x1400322ea  test    rcx, rcx
0x1400322ed  jz      short loc_1400322FB
0x1400322ef  call    cs:__imp_FwpmEngineClose0
0x1400322f6  nop     dword ptr [rax+rax+00h]
0x1400322fb  test    cs:Microsoft_Windows_WinNatEnableBits, r13b
0x140032302  jz      loc_140032388
0x140032308  movzx   ecx, word ptr [rsi+34h]
0x14003230c  lea     rdx, [rsp+98h+var_50]
0x140032311  xorps   xmm0, xmm0
0x140032314  xor     eax, eax
0x140032316  movups  [rsp+98h+var_50], xmm0
0x14003231b  xor     r9d, r9d
0x14003231e  mov     word ptr [rsp+98h+var_78], ax
0x140032323  mov     r8, r14
0x140032326  movups  [rsp+98h+var_50+0Ch], xmm0
0x14003232b  call    INETADDR_SETSOCKADDR
0x140032330  cmp     cs:dword_140027104, 1
0x140032337  jnz     short loc_140032388
0x140032339  test    cs:Microsoft_Windows_WinNatEnableBits, r13b
0x140032340  jz      short loc_140032388
0x140032342  movzx   eax, word ptr [rsi+4Ah]
0x140032346  lea     r9, [rbp+50h]
0x14003234a  cmp     word ptr [rsp+98h+var_50], 2
0x140032350  lea     rdx, WINNATM_EXTERNAL_ADDRESS_REMOVAL
0x140032357  mov     [rsp+98h+var_60], ax
0x14003235c  mov     ecx, 1Ch
0x140032361  movzx   eax, word ptr [rsi+48h]
0x140032365  cmovz   ecx, r13d
0x140032369  mov     [rsp+98h+var_68], ax
0x14003236e  lea     rax, [rsp+98h+var_50]
0x140032373  mov     [rsp+98h+var_70], rax
0x140032378  mov     [rsp+98h+var_78], ecx
0x14003237c  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140032383  call    McTemplateK0zqbr1hh_EtwWriteTransfer
0x140032388  cmp     qword ptr [rsi+50h], 0
0x14003238d  jz      short loc_1400323BF
0x14003238f  cmp     byte ptr [rbp+0E6h], 0
0x140032396  jbe     short loc_14003239D
0x140032398  xor     r8d, r8d
0x14003239b  jmp     short loc_1400323A1
0x14003239d  mov     r8, [rbp+10h]
0x1400323a1  mov     ecx, [rsi+58h]
0x1400323a4  call    SlbNatIpsRemoveInterfaceMapping
0x1400323a9  mov     rcx, [rsi+50h]
0x1400323ad  lea     rdx, SlbNatAsyncFreePort
0x1400323b4  mov     r8, rcx
0x1400323b7  mov     rcx, [rcx]
0x1400323ba  call    SlbNatQueueWorkItem
0x1400323bf  cmp     dword ptr [r14], 0
0x1400323c3  jnz     short loc_1400323CD
0x1400323c5  dec     cs:dword_140027368
0x1400323cb  jmp     short loc_1400323D0
0x1400323cd  dec     dword ptr [rbp+28h]
0x1400323d0  xor     edx, edx; Tag
0x1400323d2  mov     rcx, rsi; P
0x1400323d5  call    cs:__imp_ExFreePoolWithTag
0x1400323dc  nop     dword ptr [rax+rax+00h]
0x1400323e1  lea     rdx, [rsp+98h+var_58]
0x1400323e6  mov     rcx, rbp
0x1400323e9  call    SlbNatFindExternalAddressForLoopback
0x1400323ee  test    eax, eax
0x1400323f0  js      short loc_140032408
0x1400323f2  mov     ecx, 1
0x1400323f7  call    SlbNatIpsFindInterfaceContext
0x1400323fc  test    rax, rax
0x1400323ff  jz      short loc_140032408
0x140032401  mov     ecx, [rsp+98h+var_58]
0x140032405  mov     [rax+24h], ecx
0x140032408  mov     rcx, [rsp+98h+var_30]
0x14003240d  xor     rcx, rsp; StackCookie
0x140032410  call    __security_check_cookie
0x140032415  mov     rbx, [rsp+98h+arg_10]
0x14003241d  add     rsp, 70h
0x140032421  pop     r14
0x140032423  pop     r13
0x140032425  pop     rdi
0x140032426  pop     rsi
0x140032427  pop     rbp
0x140032428  retn
```
