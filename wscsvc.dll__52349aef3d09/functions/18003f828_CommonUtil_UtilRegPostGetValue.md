# CommonUtil::UtilRegPostGetValue

- ea: `0x18003f828`
- end: `0x18003f8fb`
- name: `CommonUtil::UtilRegPostGetValue`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003f254`

## callees

- `0x180029158`
- `0x18003ef7c`
- `0x18003f164`
- `0x18003f828`
- `0x18003f9a4`

## string_xrefs

- `0x18003f8cf`: `InstallLocation`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegPostGetValue(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned __int64 a5)
{
  __int64 result; // rax
  int v8; // ecx
  int v9; // eax

  if ( !a5 )
    return 0;
  if ( a3 - 1 <= 1 )
  {
    LODWORD(result) = MpUtilsExports::RegAdjustStringValue(a2 >> 1, a5, a4);
  }
  else
  {
    if ( a3 != 7 )
    {
LABEL_12:
      if ( CommonUtil::UtilRegIsValidValue((CommonUtil *)a3, *a4, a5, a4) )
        return 0;
      goto LABEL_13;
    }
    LODWORD(result) = MpUtilsExports::RegAdjustMultiStringValue(a2 >> 1, a5, a4);
  }
  v8 = result;
  if ( !(_DWORD)result || (_DWORD)result == -2147024662 )
    return (unsigned int)result;
  v9 = 0;
  if ( v8 == -2147019873 )
    v9 = -2147019873;
  if ( v9 != -2147019873 )
    goto LABEL_12;
LABEL_13:
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_206b02167db13a360b8041c753392543_Traceguids,
      L"InstallLocation");
  return 2147947423LL;
}

```

## disassembly

```asm
0x18003f828  mov     [rsp+arg_0], rbx
0x18003f82d  push    rsi
0x18003f82e  sub     rsp, 20h
0x18003f832  cmp     [rsp+28h+arg_20], 0
0x18003f838  mov     rsi, r9
0x18003f83b  mov     ebx, r8d
0x18003f83e  mov     r10, rdx
0x18003f841  jnz     short loc_18003F84A
0x18003f843  xor     eax, eax
0x18003f845  jmp     loc_18003F8F0
0x18003f84a  lea     eax, [r8-1]
0x18003f84e  cmp     eax, 1
0x18003f851  jbe     short loc_18003F86D
0x18003f853  cmp     ebx, 7
0x18003f856  jnz     short loc_18003F89F
0x18003f858  mov     rdx, [rsp+28h+arg_20]
0x18003f85d  mov     r8, rsi
0x18003f860  shr     r10, 1
0x18003f863  mov     rcx, r10
0x18003f866  call    MpUtilsExports__RegAdjustMultiStringValue
0x18003f86b  jmp     short loc_18003F880
0x18003f86d  mov     rdx, [rsp+28h+arg_20]
0x18003f872  mov     r8, rsi
0x18003f875  shr     r10, 1
0x18003f878  mov     rcx, r10
0x18003f87b  call    MpUtilsExports__RegAdjustStringValue
0x18003f880  mov     ecx, eax
0x18003f882  test    eax, eax
0x18003f884  jz      short loc_18003F8EE
0x18003f886  cmp     eax, 800700EAh
0x18003f88b  jz      short loc_18003F8EE
0x18003f88d  xor     eax, eax
0x18003f88f  cmp     ecx, 8007139Fh
0x18003f895  cmovz   eax, ecx
0x18003f898  cmp     eax, 8007139Fh
0x18003f89d  jz      short loc_18003F8B2
0x18003f89f  mov     r8, [rsp+28h+arg_20]; unsigned __int64
0x18003f8a4  mov     ecx, ebx; this
0x18003f8a6  mov     rdx, [rsi]; unsigned int
0x18003f8a9  call    ?UtilRegIsValidValue@CommonUtil@@YA_NK_KPEBX@Z; CommonUtil::UtilRegIsValidValue(ulong,unsigned __int64,void const *)
0x18003f8ae  test    al, al
0x18003f8b0  jnz     short loc_18003F843
0x18003f8b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f8b9  lea     rdx, WPP_GLOBAL_Control
0x18003f8c0  cmp     rcx, rdx
0x18003f8c3  jz      short loc_18003F8E7
0x18003f8c5  test    byte ptr [rcx+1Ch], 1
0x18003f8c9  jz      short loc_18003F8E7
0x18003f8cb  mov     rcx, [rcx+10h]
0x18003f8cf  lea     r9, aInstalllocatio; "InstallLocation"
0x18003f8d6  mov     edx, 16h
0x18003f8db  lea     r8, WPP_206b02167db13a360b8041c753392543_Traceguids
0x18003f8e2  call    WPP_SF_S
0x18003f8e7  mov     eax, 8007139Fh
0x18003f8ec  jmp     short loc_18003F8F0
0x18003f8ee  mov     eax, ecx
0x18003f8f0  mov     rbx, [rsp+28h+arg_0]
0x18003f8f5  add     rsp, 20h
0x18003f8f9  pop     rsi
0x18003f8fa  retn
```
