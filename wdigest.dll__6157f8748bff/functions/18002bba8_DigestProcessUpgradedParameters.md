# DigestProcessUpgradedParameters

- ea: `0x18002bba8`
- end: `0x18002bd2c`
- name: `DigestProcessUpgradedParameters`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e4b0`

## callees

- `0x18000c770`
- `0x180012880`
- `0x18002ba20`
- `0x18002bba8`
- `0x18003327c`
- `0x180034434`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002bc0a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002bc5c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002bc0a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18002bc5c`

## string_xrefs

- `0x18002bc7b`: `service-name`

## pseudocode

```c
__int64 __fastcall DigestProcessUpgradedParameters(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v10; // [rsp+40h] [rbp-78h] BYREF
  void *Source1; // [rsp+48h] [rbp-70h]
  char v12; // [rsp+50h] [rbp-68h] BYREF

  if ( *(_WORD *)(a6 + 72) >= 0x2Cu && RtlCompareMemory("+Upgraded+", *(const void **)(a6 + 80), 0xAu) == 10 )
  {
    v10 = 2162688;
    Source1 = &v12;
    if ( (int)HashHashedDirs(a1, a6, &v10) < 0
      || *(_WORD *)(a6 + 72) < 0x2Cu
      || RtlCompareMemory(Source1, (const void *)(*(_QWORD *)(a6 + 80) + 12LL), 0x20u) != 32
      || *(_WORD *)(a6 + 376) && (int)CheckItemInList("service-name") < 0 )
    {
      return 2148074248LL;
    }
    *(_WORD *)(a6 + 4) |= 0x200u;
    if ( !*(_WORD *)(a6 + 392) || (int)CheckItemInList("channel-binding") < 0 || *(_WORD *)(a6 + 392) != 32 )
      return 2148074248LL;
    HexToBin(*(_QWORD *)(a6 + 400), 32, &v10);
  }
  return SspVerifyAscChannelBindings(a1, a4, a5, a2);
}

```

## disassembly

```asm
0x18002bba8  mov     [rsp+arg_10], rbx
0x18002bbad  push    rbp
0x18002bbae  push    rsi
0x18002bbaf  push    rdi
0x18002bbb0  push    r12
0x18002bbb2  push    r13
0x18002bbb4  push    r14
0x18002bbb6  push    r15
0x18002bbb8  sub     rsp, 80h
0x18002bbbf  mov     rax, cs:__security_cookie
0x18002bbc6  xor     rax, rsp
0x18002bbc9  mov     [rsp+0B8h+var_40], rax
0x18002bbce  mov     rdi, [rsp+0B8h+arg_28]
0x18002bbd6  xor     r13d, r13d
0x18002bbd9  mov     r12, [rsp+0B8h+arg_20]
0x18002bbe1  mov     rbx, r9
0x18002bbe4  mov     r15d, edx
0x18002bbe7  mov     r14, rcx
0x18002bbea  mov     esi, r13d
0x18002bbed  mov     bpl, r13b
0x18002bbf0  cmp     word ptr [rdi+48h], 2Ch ; ','
0x18002bbf5  jb      loc_18002BCE3
0x18002bbfb  mov     rdx, [rdi+50h]; Source2
0x18002bbff  lea     r8d, [r13+0Ah]; Length
0x18002bc03  lea     rcx, aUpgraded; "+Upgraded+"
0x18002bc0a  call    cs:__imp_RtlCompareMemory
0x18002bc10  cmp     rax, 0Ah
0x18002bc14  jnz     loc_18002BCE3
0x18002bc1a  lea     rax, [rsp+0B8h+var_68]
0x18002bc1f  mov     [rsp+0B8h+var_78], 210000h
0x18002bc28  lea     r8, [rsp+0B8h+var_78]
0x18002bc2d  mov     [rsp+0B8h+Source1], rax
0x18002bc32  mov     rdx, rdi
0x18002bc35  mov     rcx, r14
0x18002bc38  call    HashHashedDirs
0x18002bc3d  test    eax, eax
0x18002bc3f  js      short loc_18002BC8B
0x18002bc41  cmp     word ptr [rdi+48h], 2Ch ; ','
0x18002bc46  jb      short loc_18002BC8B
0x18002bc48  mov     rdx, [rdi+50h]
0x18002bc4c  lea     esi, [r13+20h]
0x18002bc50  mov     rcx, [rsp+0B8h+Source1]; Source1
0x18002bc55  add     rdx, 0Ch; Source2
0x18002bc59  mov     r8d, esi; Length
0x18002bc5c  call    cs:__imp_RtlCompareMemory
0x18002bc62  cmp     rax, rsi
0x18002bc65  jnz     short loc_18002BC8B
0x18002bc67  cmp     [rdi+178h], r13w
0x18002bc6f  jz      short loc_18002BC92
0x18002bc71  lea     rdx, [rdi+168h]
0x18002bc78  xor     r8d, r8d
0x18002bc7b  lea     rcx, aServiceName; "service-name"
0x18002bc82  call    CheckItemInList
0x18002bc87  test    eax, eax
0x18002bc89  jns     short loc_18002BC92
0x18002bc8b  mov     eax, 80090308h
0x18002bc90  jmp     short loc_18002BD04
0x18002bc92  mov     eax, 200h
0x18002bc97  or      [rdi+4], ax
0x18002bc9b  cmp     [rdi+188h], r13w
0x18002bca3  jz      short loc_18002BC8B
0x18002bca5  lea     rdx, [rdi+168h]
0x18002bcac  xor     r8d, r8d
0x18002bcaf  lea     rcx, aChannelBinding; "channel-binding"
0x18002bcb6  call    CheckItemInList
0x18002bcbb  test    eax, eax
0x18002bcbd  js      short loc_18002BC8B
0x18002bcbf  cmp     [rdi+188h], si
0x18002bcc6  jnz     short loc_18002BC8B
0x18002bcc8  mov     rcx, [rdi+190h]
0x18002bccf  lea     r8, [rsp+0B8h+var_78]
0x18002bcd4  mov     edx, esi
0x18002bcd6  mov     bpl, 1
0x18002bcd9  call    HexToBin
0x18002bcde  mov     esi, 10h
0x18002bce3  lea     rax, [rsp+0B8h+var_78]
0x18002bce8  mov     [rsp+0B8h+var_80], esi
0x18002bcec  mov     [rsp+0B8h+var_88], rax
0x18002bcf1  mov     r9d, r15d
0x18002bcf4  mov     r8, r12
0x18002bcf7  mov     [rsp+0B8h+var_90], bpl
0x18002bcfc  mov     rdx, rbx
0x18002bcff  call    SspVerifyAscChannelBindings
0x18002bd04  mov     rcx, [rsp+0B8h+var_40]
0x18002bd09  xor     rcx, rsp; StackCookie
0x18002bd0c  call    __security_check_cookie
0x18002bd11  mov     rbx, [rsp+0B8h+arg_10]
0x18002bd19  add     rsp, 80h
0x18002bd20  pop     r15
0x18002bd22  pop     r14
0x18002bd24  pop     r13
0x18002bd26  pop     r12
0x18002bd28  pop     rdi
0x18002bd29  pop     rsi
0x18002bd2a  pop     rbp
0x18002bd2b  retn
```
