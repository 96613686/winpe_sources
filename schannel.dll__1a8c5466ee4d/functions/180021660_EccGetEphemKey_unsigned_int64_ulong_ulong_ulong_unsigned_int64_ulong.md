# EccGetEphemKey(unsigned __int64,ulong,ulong,ulong,unsigned __int64 *,ulong *)

- ea: `0x180021660`
- end: `0x180021734`
- name: `?EccGetEphemKey@@YAK_KKKKPEA_KPEAK@Z`
- size: `212`
- prototype: `unsigned int(unsigned __int64, unsigned int, unsigned int, unsigned int, unsigned __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180078588`

## callees

- `0x180021660`
- `0x180021da8`
- `0x180041960`
- `0x1800525bc`
- `0x180052620`
- `0x18007be38`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18008c35b`
- `ntdll!RtlReleaseResource` at `0x18008c35b`
- `ntdll!RtlAcquireResourceShared` at `0x18008c336`
- `ntdll!RtlAcquireResourceShared` at `0x18008c336`
- `ncrypt!SslCreateEphemeralKey` at `0x1800216df`
- `ncrypt!SslCreateEphemeralKey` at `0x1800216df`

## pseudocode

```c
__int64 __fastcall EccGetEphemKey(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int64 *a5,
        unsigned int *a6)
{
  unsigned int PublicKeyLength; // ebx
  CCipherMill *v12; // rcx
  KeyExchangeGroup *KeyExchangeGroup; // rcx
  unsigned int KeyExchangeSize; // eax
  MasterKeyExchangeInfo **v15; // rcx
  MasterKeyExchangeInfo *v16; // rcx
  unsigned int v17; // esi
  unsigned int v18; // [rsp+98h] [rbp+20h] BYREF

  if ( a4 && qword_1800AE5C8 )
  {
    v18 = 0;
    RtlAcquireResourceShared(&Resource, 1u);
    PublicKeyLength = CMasterEccCurveInfo::GetPublicKeyLength(qword_1800AE5C8, a4, &v18);
    RtlReleaseResource(&Resource);
    if ( PublicKeyLength == 1168 && (KeyExchangeGroup = CCipherMill::GetKeyExchangeGroup(v12, a4)) != 0 )
    {
      KeyExchangeSize = KeyExchangeGroup::GetKeyExchangeSize(KeyExchangeGroup, 0);
      v16 = *v15;
      PublicKeyLength = 0;
      v17 = KeyExchangeSize;
      if ( !KeyExchangeSize )
        PublicKeyLength = 1168;
      MasterKeyExchangeInfo::Dereference(v16);
    }
    else
    {
      v17 = v18;
    }
    if ( !PublicKeyLength )
    {
      PublicKeyLength = SslCreateEphemeralKey(a1, a5, a3, a2, a4, v17, 0, 0, 0);
      if ( PublicKeyLength
        && WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_3e0ca11e9b65363ec3903422d835754d_Traceguids,
          PublicKeyLength);
      }
      if ( a6 )
        *a6 = v17;
    }
  }
  else
  {
    return 87;
  }
  return PublicKeyLength;
}

```

## disassembly

```asm
0x180021660  mov     [rsp+arg_8], rbx
0x180021665  mov     [rsp+arg_10], rbp
0x18002166a  push    rsi
0x18002166b  push    rdi
0x18002166c  push    r12
0x18002166e  push    r14
0x180021670  push    r15
0x180021672  sub     rsp, 50h
0x180021676  mov     edi, r9d
0x180021679  mov     ebp, r8d
0x18002167c  mov     r14d, edx
0x18002167f  mov     r15, rcx
0x180021682  test    r9d, r9d
0x180021685  jnz     loc_18008C30C
0x18002168b  mov     ebx, 57h ; 'W'
0x180021690  lea     r11, [rsp+78h+var_28]
0x180021695  mov     eax, ebx
0x180021697  mov     rbx, [r11+38h]
0x18002169b  mov     rbp, [r11+40h]
0x18002169f  mov     rsp, r11
0x1800216a2  pop     r15
0x1800216a4  pop     r14
0x1800216a6  pop     r12
0x1800216a8  pop     rdi
0x1800216a9  pop     rsi
0x1800216aa  retn
0x1800216ab  mov     r13, [rsp+78h+arg_0]
0x1800216b3  test    ebx, ebx
0x1800216b5  jnz     short loc_180021690
0x1800216b7  mov     rdx, [rsp+78h+arg_20]
0x1800216bf  mov     r9d, r14d
0x1800216c2  mov     [rsp+78h+var_38], r12d
0x1800216c7  mov     r8d, ebp
0x1800216ca  mov     [rsp+78h+var_40], r12d
0x1800216cf  mov     rcx, r15
0x1800216d2  mov     [rsp+78h+var_48], r12
0x1800216d7  mov     [rsp+78h+var_50], esi
0x1800216db  mov     [rsp+78h+var_58], edi
0x1800216df  call    cs:__imp_SslCreateEphemeralKey
0x1800216e5  mov     ebx, eax
0x1800216e7  test    eax, eax
0x1800216e9  jz      short loc_18002171C
0x1800216eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216f2  lea     rax, WPP_GLOBAL_Control
0x1800216f9  cmp     rcx, rax
0x1800216fc  jz      short loc_18002171C
0x1800216fe  test    byte ptr [rcx+1Ch], 1
0x180021702  jz      short loc_18002171C
0x180021704  mov     rcx, [rcx+10h]
0x180021708  lea     r8, WPP_3e0ca11e9b65363ec3903422d835754d_Traceguids
0x18002170f  mov     edx, 0Bh
0x180021714  mov     r9d, ebx
0x180021717  call    WPP_SF_d
0x18002171c  mov     rax, [rsp+78h+arg_28]
0x180021724  test    rax, rax
0x180021727  jz      loc_180021690
0x18002172d  mov     [rax], esi
0x18002172f  jmp     loc_180021690
0x18008c30c  cmp     cs:qword_1800AE5C8, 0
0x18008c314  jz      loc_18002168B
0x18008c31a  xor     r12d, r12d
0x18008c31d  mov     [rsp+78h+arg_0], r13
0x18008c325  mov     dl, 1; Wait
0x18008c327  mov     [rsp+78h+arg_18], r12d
0x18008c32f  lea     rcx, Resource; Resource
0x18008c336  call    cs:__imp_RtlAcquireResourceShared
0x18008c33c  mov     rcx, cs:qword_1800AE5C8; this
0x18008c343  lea     r8, [rsp+78h+arg_18]; unsigned int *
0x18008c34b  mov     edx, edi; unsigned int
0x18008c34d  call    ?GetPublicKeyLength@CMasterEccCurveInfo@@QEAAKKPEAK@Z; CMasterEccCurveInfo::GetPublicKeyLength(ulong,ulong *)
0x18008c352  lea     rcx, Resource; Resource
0x18008c359  mov     ebx, eax
0x18008c35b  call    cs:__imp_RtlReleaseResource
0x18008c361  mov     r13d, 490h
0x18008c367  cmp     ebx, r13d
0x18008c36a  jnz     short loc_18008C39C
0x18008c36c  movzx   edx, di; unsigned __int16
0x18008c36f  call    ?GetKeyExchangeGroup@CCipherMill@@QEBAPEAVKeyExchangeGroup@@G@Z; CCipherMill::GetKeyExchangeGroup(ushort)
0x18008c374  mov     rcx, rax; this
0x18008c377  test    rax, rax
0x18008c37a  jz      short loc_18008C39C
0x18008c37c  xor     edx, edx; unsigned __int8
0x18008c37e  call    ?GetKeyExchangeSize@KeyExchangeGroup@@QEBAKE@Z; KeyExchangeGroup::GetKeyExchangeSize(uchar)
0x18008c383  mov     rcx, [rcx]; this
0x18008c386  test    eax, eax
0x18008c388  mov     ebx, r12d
0x18008c38b  mov     esi, eax
0x18008c38d  cmovz   ebx, r13d
0x18008c391  call    ?Dereference@MasterKeyExchangeInfo@@QEAAXXZ; MasterKeyExchangeInfo::Dereference(void)
0x18008c396  nop
0x18008c397  jmp     loc_1800216AB
0x18008c39c  mov     esi, [rsp+78h+arg_18]
0x18008c3a3  jmp     loc_1800216AB
```
