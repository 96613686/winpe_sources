# OncRpcConnMgrpFindOrCreateRemoteAddress

- ea: `0x1400064cc`
- end: `0x1400065fe`
- name: `OncRpcConnMgrpFindOrCreateRemoteAddress`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d300`

## callees

- `0x1400020c0`
- `0x1400064cc`
- `0x140006720`
- `0x14000675c`
- `0x140015640`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140006526`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140006526`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpFindOrCreateRemoteAddress(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // r9
  char *inserted; // rax
  char *v7; // rdx
  __int64 result; // rax
  _QWORD *v9; // rax
  unsigned __int8 NewElement[8]; // [rsp+20h] [rbp-48h] BYREF
  _OWORD Buffer[3]; // [rsp+28h] [rbp-40h] BYREF

  NewElement[0] = 0;
  memset(Buffer, 0, sizeof(Buffer));
  OncRpcCopyAddress(Buffer, a2);
  inserted = (char *)RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(v5 + 288), Buffer, 0x30u, NewElement);
  v7 = inserted;
  if ( !inserted )
    return 3221225626LL;
  if ( NewElement[0] )
  {
    v9 = inserted + 32;
    v9[1] = v9;
    *v9 = v9;
    *((_DWORD *)v7 + 7) = 0;
  }
  if ( *((_DWORD *)v7 + 7) <= (unsigned int)dword_14001A3E8 )
  {
    result = 0;
    *a3 = v7;
  }
  else
  {
    if ( *(_WORD *)a2 == 2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_e6da9dcbba6831c1b4289775a52989f5_Traceguids,
          *(unsigned int *)(a2 + 4));
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    {
      WPP_SF__IPV6_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_e6da9dcbba6831c1b4289775a52989f5_Traceguids, a2 + 8);
    }
    return 3221226054LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400064cc  mov     [rsp+arg_18], rbx
0x1400064d1  push    rdi
0x1400064d2  sub     rsp, 60h
0x1400064d6  mov     rax, cs:__security_cookie
0x1400064dd  xor     rax, rsp
0x1400064e0  mov     [rsp+68h+var_10], rax
0x1400064e5  xorps   xmm0, xmm0
0x1400064e8  mov     [rsp+68h+NewElement], 0
0x1400064ed  mov     r9, rcx
0x1400064f0  mov     rdi, r8
0x1400064f3  lea     rcx, [rsp+68h+Buffer]
0x1400064f8  mov     rbx, rdx
0x1400064fb  movups  [rsp+68h+Buffer], xmm0
0x140006500  movups  [rsp+68h+var_30], xmm0
0x140006505  movups  [rsp+68h+var_20], xmm0
0x14000650a  call    OncRpcCopyAddress
0x14000650f  lea     rcx, [r9+120h]; Table
0x140006516  mov     r8d, 30h ; '0'; BufferSize
0x14000651c  lea     r9, [rsp+68h+NewElement]; NewElement
0x140006521  lea     rdx, [rsp+68h+Buffer]; Buffer
0x140006526  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14000652d  nop     dword ptr [rax+rax+00h]
0x140006532  mov     rdx, rax
0x140006535  test    rax, rax
0x140006538  jnz     short loc_140006544
0x14000653a  mov     eax, 0C000009Ah
0x14000653f  jmp     loc_1400065E2
0x140006544  cmp     [rsp+68h+NewElement], 0
0x140006549  jz      short loc_14000655D
0x14000654b  add     rax, 20h ; ' '
0x14000654f  mov     [rax+8], rax
0x140006553  mov     [rax], rax
0x140006556  mov     dword ptr [rdx+1Ch], 0
0x14000655d  mov     eax, cs:dword_14001A3E8
0x140006563  cmp     [rdx+1Ch], eax
0x140006566  jbe     short loc_1400065DD
0x140006568  cmp     word ptr [rbx], 2
0x14000656c  jnz     short loc_1400065A3
0x14000656e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006575  lea     rax, WPP_GLOBAL_Control
0x14000657c  cmp     rcx, rax
0x14000657f  jz      short loc_1400065D6
0x140006581  mov     eax, [rcx+2Ch]
0x140006584  test    al, 8
0x140006586  jz      short loc_1400065D6
0x140006588  mov     r9d, [rbx+4]
0x14000658c  lea     r8, WPP_e6da9dcbba6831c1b4289775a52989f5_Traceguids
0x140006593  mov     rcx, [rcx+18h]
0x140006597  mov     edx, 0Fh
0x14000659c  call    WPP_SF_d
0x1400065a1  jmp     short loc_1400065D6
0x1400065a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400065aa  lea     rax, WPP_GLOBAL_Control
0x1400065b1  cmp     rcx, rax
0x1400065b4  jz      short loc_1400065D6
0x1400065b6  mov     eax, [rcx+2Ch]
0x1400065b9  test    al, 8
0x1400065bb  jz      short loc_1400065D6
0x1400065bd  mov     rcx, [rcx+18h]
0x1400065c1  lea     r9, [rbx+8]
0x1400065c5  mov     edx, 10h
0x1400065ca  lea     r8, WPP_e6da9dcbba6831c1b4289775a52989f5_Traceguids
0x1400065d1  call    WPP_SF__IPV6_
0x1400065d6  mov     eax, 0C0000246h
0x1400065db  jmp     short loc_1400065E2
0x1400065dd  xor     eax, eax
0x1400065df  mov     [rdi], rdx
0x1400065e2  mov     rcx, [rsp+68h+var_10]
0x1400065e7  xor     rcx, rsp; StackCookie
0x1400065ea  call    __security_check_cookie
0x1400065ef  mov     rbx, [rsp+68h+arg_18]
0x1400065f7  add     rsp, 60h
0x1400065fb  pop     rdi
0x1400065fc  retn
```
