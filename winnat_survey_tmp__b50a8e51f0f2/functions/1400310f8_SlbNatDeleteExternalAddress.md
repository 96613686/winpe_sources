# SlbNatDeleteExternalAddress

- ea: `0x1400310f8`
- end: `0x1400312fa`
- name: `SlbNatDeleteExternalAddress`
- size: `514`
- prototype: `__int64 __fastcall(char *P, __int64)`
- caller_count: `9`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14000975c`
- `0x14000bc6c`
- `0x140014b38`
- `0x1400308ac`
- `0x140031300`
- `0x14003179c`
- `0x140032314`
- `0x1400324b8`
- `0x140032be4`

## callees

- `0x140008560`
- `0x14000d678`
- `0x140013ef0`
- `0x140014cd4`
- `0x140018e40`
- `0x14001ede0`
- `0x14001f140`
- `0x1400310f8`
- `0x1400315a0`
- `0x140033514`
- `0x140034310`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400312a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400312a5`
- `fwpkclnt!FwpmEngineClose0` at `0x1400311bf`
- `fwpkclnt!FwpmEngineClose0` at `0x1400311bf`

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
  __int16 v13; // cx
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
    (_DWORD)qword_1400263D8,
    (unsigned int)v19,
    v10,
    *((unsigned __int16 *)P + 36),
    *((_WORD *)P + 37));
  v12 = (void *)*((_QWORD *)P + 5);
  if ( v12 )
    FwpmEngineClose0(v12);
  if ( (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
  {
    v13 = *((_WORD *)P + 26);
    memset(v19, 0, 28);
    INETADDR_SETSOCKADDR(v13, (__int64)v19, (IN6_ADDR *)(P + 56), 0, 0);
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
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
    --dword_140026368;
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
0x1400310f8  mov     [rsp+arg_10], rbx
0x1400310fd  push    rbp
0x1400310fe  push    rsi
0x1400310ff  push    rdi
0x140031100  push    r13
0x140031102  push    r14
0x140031104  sub     rsp, 70h
0x140031108  mov     rax, cs:__security_cookie
0x14003110f  xor     rax, rsp
0x140031112  mov     [rsp+98h+var_30], rax
0x140031117  xorps   xmm0, xmm0
0x14003111a  mov     [rsp+98h+var_58], 0
0x140031122  movups  [rsp+98h+var_50], xmm0
0x140031127  mov     rbp, rdx
0x14003112a  lea     rbx, [rcx+10h]
0x14003112e  mov     rsi, rcx
0x140031131  mov     rcx, [rbx]; P
0x140031134  cmp     rcx, rbx
0x140031137  jz      short loc_140031163
0x140031139  cmp     [rcx+8], rbx
0x14003113d  jnz     short loc_14003115C
0x14003113f  mov     rax, [rcx]
0x140031142  cmp     [rax+8], rcx
0x140031146  jnz     short loc_14003115C
0x140031148  mov     [rbx], rax
0x14003114b  mov     rdx, rbp
0x14003114e  mov     [rax+8], rbx
0x140031152  dec     dword ptr [rsi+20h]
0x140031155  call    SlbNatDeleteStaticMapping
0x14003115a  jmp     short loc_140031131
0x14003115c  mov     ecx, 3
0x140031161  int     29h; Win8: RtlFailFast(ecx)
0x140031163  movzx   ebx, word ptr [rsi+34h]
0x140031167  lea     r14, [rsi+38h]
0x14003116b  mov     edi, 4
0x140031170  lea     rcx, [rsp+98h+var_50]; void *
0x140031175  cmp     bx, 2
0x140031179  mov     r8d, edi
0x14003117c  mov     rdx, r14; Src
0x14003117f  lea     r13d, [rdi+0Ch]
0x140031183  cmovnz  r8d, r13d; Size
0x140031187  call    memmove
0x14003118c  movzx   eax, word ptr [rsi+4Ah]
0x140031190  lea     rdx, [rsp+98h+var_50]
0x140031195  movzx   r9d, word ptr [rsi+48h]
0x14003119a  cmp     bx, 2
0x14003119e  mov     rcx, cs:qword_1400263D8
0x1400311a5  cmovnz  edi, r13d
0x1400311a9  mov     word ptr [rsp+98h+var_78], ax
0x1400311ae  mov     r8b, dil
0x1400311b1  call    WinNatLibDeleteAddress
0x1400311b6  mov     rcx, [rsi+28h]; engineHandle
0x1400311ba  test    rcx, rcx
0x1400311bd  jz      short loc_1400311CB
0x1400311bf  call    cs:__imp_FwpmEngineClose0
0x1400311c6  nop     dword ptr [rax+rax+00h]
0x1400311cb  test    cs:Microsoft_Windows_WinNatEnableBits, r13b
0x1400311d2  jz      loc_140031258
0x1400311d8  movzx   ecx, word ptr [rsi+34h]
0x1400311dc  lea     rdx, [rsp+98h+var_50]
0x1400311e1  xorps   xmm0, xmm0
0x1400311e4  xor     eax, eax
0x1400311e6  movups  [rsp+98h+var_50], xmm0
0x1400311eb  xor     r9d, r9d
0x1400311ee  mov     word ptr [rsp+98h+var_78], ax
0x1400311f3  mov     r8, r14
0x1400311f6  movups  [rsp+98h+var_50+0Ch], xmm0
0x1400311fb  call    INETADDR_SETSOCKADDR
0x140031200  cmp     cs:dword_140026104, 1
0x140031207  jnz     short loc_140031258
0x140031209  test    cs:Microsoft_Windows_WinNatEnableBits, r13b
0x140031210  jz      short loc_140031258
0x140031212  movzx   eax, word ptr [rsi+4Ah]
0x140031216  lea     r9, [rbp+50h]
0x14003121a  cmp     word ptr [rsp+98h+var_50], 2
0x140031220  lea     rdx, WINNATM_EXTERNAL_ADDRESS_REMOVAL
0x140031227  mov     [rsp+98h+var_60], ax
0x14003122c  mov     ecx, 1Ch
0x140031231  movzx   eax, word ptr [rsi+48h]
0x140031235  cmovz   ecx, r13d
0x140031239  mov     [rsp+98h+var_68], ax
0x14003123e  lea     rax, [rsp+98h+var_50]
0x140031243  mov     [rsp+98h+var_70], rax
0x140031248  mov     [rsp+98h+var_78], ecx
0x14003124c  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140031253  call    McTemplateK0zqbr1hh_EtwWriteTransfer
0x140031258  cmp     qword ptr [rsi+50h], 0
0x14003125d  jz      short loc_14003128F
0x14003125f  cmp     byte ptr [rbp+0E6h], 0
0x140031266  jbe     short loc_14003126D
0x140031268  xor     r8d, r8d
0x14003126b  jmp     short loc_140031271
0x14003126d  mov     r8, [rbp+10h]
0x140031271  mov     ecx, [rsi+58h]
0x140031274  call    SlbNatIpsRemoveInterfaceMapping
0x140031279  mov     rcx, [rsi+50h]
0x14003127d  lea     rdx, SlbNatAsyncFreePort
0x140031284  mov     r8, rcx
0x140031287  mov     rcx, [rcx]
0x14003128a  call    SlbNatQueueWorkItem
0x14003128f  cmp     dword ptr [r14], 0
0x140031293  jnz     short loc_14003129D
0x140031295  dec     cs:dword_140026368
0x14003129b  jmp     short loc_1400312A0
0x14003129d  dec     dword ptr [rbp+28h]
0x1400312a0  xor     edx, edx; Tag
0x1400312a2  mov     rcx, rsi; P
0x1400312a5  call    cs:__imp_ExFreePoolWithTag
0x1400312ac  nop     dword ptr [rax+rax+00h]
0x1400312b1  lea     rdx, [rsp+98h+var_58]
0x1400312b6  mov     rcx, rbp
0x1400312b9  call    SlbNatFindExternalAddressForLoopback
0x1400312be  test    eax, eax
0x1400312c0  js      short loc_1400312D8
0x1400312c2  mov     ecx, 1
0x1400312c7  call    SlbNatIpsFindInterfaceContext
0x1400312cc  test    rax, rax
0x1400312cf  jz      short loc_1400312D8
0x1400312d1  mov     ecx, [rsp+98h+var_58]
0x1400312d5  mov     [rax+24h], ecx
0x1400312d8  mov     rcx, [rsp+98h+var_30]
0x1400312dd  xor     rcx, rsp; StackCookie
0x1400312e0  call    __security_check_cookie
0x1400312e5  mov     rbx, [rsp+98h+arg_10]
0x1400312ed  add     rsp, 70h
0x1400312f1  pop     r14
0x1400312f3  pop     r13
0x1400312f5  pop     rdi
0x1400312f6  pop     rsi
0x1400312f7  pop     rbp
0x1400312f8  retn
```
