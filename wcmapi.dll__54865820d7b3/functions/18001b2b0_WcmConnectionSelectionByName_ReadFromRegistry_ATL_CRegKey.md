# WcmConnectionSelectionByName::ReadFromRegistry(ATL::CRegKey &)

- ea: `0x18001b2b0`
- end: `0x18001b3bf`
- name: `?ReadFromRegistry@WcmConnectionSelectionByName@@UEAAJAEAVCRegKey@ATL@@@Z`
- size: `271`
- prototype: `int(WcmConnectionSelectionByName *__hidden this, struct ATL::CRegKey *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x180018f18`
- `0x18001ae30`
- `0x18001b2b0`

## string_xrefs

- `0x18001b2e4`: `WcmConnectionSelectionByName::ReadFromRegistry`
- `0x18001b39b`: `WcmConnectionSelectionByName::ReadFromRegistry`

## pseudocode

```c
__int64 __fastcall WcmConnectionSelectionByName::ReadFromRegistry(
        WcmConnectionSelectionByName *this,
        struct ATL::CRegKey *a2)
{
  unsigned int v3; // ebx
  int StringValue; // edi
  WcmPolicyManager *v5; // rcx

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_a9846ea38e1b3fe5df91ade435e7f482_Traceguids,
      "WcmConnectionSelectionByName::ReadFromRegistry");
  }
  try
  {
    v3 = 0;
    StringValue = QueryStringValue(a2, L"ConnectionName");
    if ( StringValue )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"ConnectionName");
        v5 = WPP_GLOBAL_Control;
      }
      if ( StringValue > 0 )
        v3 = (unsigned __int16)StringValue | 0x80070000;
      else
        v3 = StringValue;
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
    }
  }
  catch ( std::bad_alloc )
  {
    v3 = -2147024882;
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v5 + 25) >= 5u && (*((_BYTE *)v5 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v5 + 2),
      16,
      (unsigned int)WPP_a9846ea38e1b3fe5df91ade435e7f482_Traceguids,
      (unsigned int)"WcmConnectionSelectionByName::ReadFromRegistry",
      v3);
  return v3;
}

```

## disassembly

```asm
0x18001b2b0  push    rbx
0x18001b2b2  push    rsi
0x18001b2b3  push    rdi
0x18001b2b4  push    r14
0x18001b2b6  sub     rsp, 38h
0x18001b2ba  mov     rdi, rdx
0x18001b2bd  mov     r14, rcx
0x18001b2c0  lea     rsi, WPP_GLOBAL_Control
0x18001b2c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2ce  cmp     rcx, rsi
0x18001b2d1  jz      short loc_18001B2FB
0x18001b2d3  cmp     byte ptr [rcx+19h], 5
0x18001b2d7  jb      short loc_18001B2FB
0x18001b2d9  test    byte ptr [rcx+1Ch], 1
0x18001b2dd  jz      short loc_18001B2FB
0x18001b2df  mov     edx, 0Eh
0x18001b2e4  lea     r9, aWcmconnections_2; "WcmConnectionSelectionByName::ReadFromR"...
0x18001b2eb  lea     r8, WPP_a9846ea38e1b3fe5df91ade435e7f482_Traceguids
0x18001b2f2  mov     rcx, [rcx+10h]
0x18001b2f6  call    WPP_SF_s
0x18001b2fb  xor     ebx, ebx
0x18001b2fd  lea     r8, [r14+10h]
0x18001b301  lea     r14, ?c_szConnectionSelection_ConnectionNameRegKey@@3QBGB; "ConnectionName"
0x18001b308  mov     rdx, r14; unsigned __int16 *
0x18001b30b  mov     rcx, rdi; this
0x18001b30e  call    ?QueryStringValue@@YAKAEAVCRegKey@ATL@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; QueryStringValue(ATL::CRegKey &,ushort const *,std::wstring &)
0x18001b313  mov     edi, eax
0x18001b315  test    eax, eax
0x18001b317  jz      short loc_18001B366
0x18001b319  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b320  cmp     rcx, rsi
0x18001b323  jz      short loc_18001B353
0x18001b325  cmp     byte ptr [rcx+19h], 1
0x18001b329  jb      short loc_18001B353
0x18001b32b  test    byte ptr [rcx+1Ch], 1
0x18001b32f  jz      short loc_18001B353
0x18001b331  lea     edx, [rbx+0Fh]
0x18001b334  mov     [rsp+58h+var_38], r14; __int64
0x18001b339  mov     r9d, eax
0x18001b33c  lea     r8, WPP_a9846ea38e1b3fe5df91ade435e7f482_Traceguids
0x18001b343  mov     rcx, [rcx+10h]; LoggerHandle
0x18001b347  call    WPP_SF_DS
0x18001b34c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b353  test    edi, edi
0x18001b355  jg      short loc_18001B35B
0x18001b357  mov     ebx, edi
0x18001b359  jmp     short loc_18001B36D
0x18001b35b  movzx   ebx, di
0x18001b35e  or      ebx, 80070000h
0x18001b364  jmp     short loc_18001B36D
0x18001b366  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b36d  jmp     short loc_18001B381
0x18001b36f  lea     rsi, WPP_GLOBAL_Control
0x18001b376  mov     ebx, [rsp+58h+arg_0]
0x18001b37a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b381  cmp     rcx, rsi
0x18001b384  jz      short loc_18001B3B2
0x18001b386  cmp     byte ptr [rcx+19h], 5
0x18001b38a  jb      short loc_18001B3B2
0x18001b38c  test    byte ptr [rcx+1Ch], 1
0x18001b390  jz      short loc_18001B3B2
0x18001b392  mov     edx, 10h
0x18001b397  mov     dword ptr [rsp+58h+var_38], ebx
0x18001b39b  lea     r9, aWcmconnections_2; "WcmConnectionSelectionByName::ReadFromR"...
0x18001b3a2  lea     r8, WPP_a9846ea38e1b3fe5df91ade435e7f482_Traceguids
0x18001b3a9  mov     rcx, [rcx+10h]
0x18001b3ad  call    WPP_SF_sL
0x18001b3b2  mov     eax, ebx
0x18001b3b4  add     rsp, 38h
0x18001b3b8  pop     r14
0x18001b3ba  pop     rdi
0x18001b3bb  pop     rsi
0x18001b3bc  pop     rbx
0x18001b3bd  retn
```
