# SkhalpPciSetupAccessAndRestoreRules

- ea: `0x140091d18`
- end: `0x14009203f`
- name: `SkhalpPciSetupAccessAndRestoreRules`
- size: `807`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14008b580`

## callees

- `0x140090d8c`
- `0x140090e1c`
- `0x140091d18`

## pseudocode

```c
__int64 __fastcall SkhalpPciSetupAccessAndRestoreRules(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax
  int v5; // r8d
  char v6; // al
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  int v11; // r9d
  int v12; // r9d
  int v13; // r9d
  int v14; // r9d
  int v15; // r9d
  int v16; // r9d
  int v17; // r9d
  int v18; // r9d
  int v19; // eax
  unsigned int v20; // ecx

  *(_QWORD *)(a1 + 392) = a1 + 384;
  *(_QWORD *)(a1 + 384) = a1 + 384;
  *(_DWORD *)(a1 + 400) = 0;
  *(_QWORD *)(a1 + 416) = a1 + 408;
  *(_QWORD *)(a1 + 408) = a1 + 408;
  result = SkhalpPciAddRule(a1, (unsigned int)SkhalpPciAccessCommandRegister, a3, 4, 2);
  if ( (int)result >= 0 )
  {
    v6 = *(_BYTE *)(a1 + 57);
    if ( v6 )
    {
      if ( v6 == 1 )
      {
        result = SkhalpPciAddRule(a1, (unsigned int)SkhalpPciAccessBarRegisters, v5, 16, 8);
        if ( (int)result < 0 )
          return result;
        result = SkhalpPciAddRule(a1, (unsigned int)SkhalpPciAccessPrimaryBusNumberRegister, v7, 24, 1);
        if ( (int)result < 0 )
          return result;
        result = SkhalpPciAddRule(a1, (unsigned int)SkhalpPciAccessSecondaryBusNumberRegister, v8, 25, 1);
        if ( (int)result < 0 )
          return result;
        result = SkhalpPciAddRule(a1, (unsigned int)SkhalpPciAccessSubordinateBusNumberRegisters, v9, 26, 1);
        if ( (int)result < 0 )
          return result;
        SkhalpPciAddRule(a1, (unsigned int)&SkhalpPciAccessBridgeWindows, v10, 32, 16);
      }
    }
    else
    {
      result = SkhalpPciAddRule(a1, (unsigned int)SkhalpPciAccessBarRegisters, v5, 16, 24);
      if ( (int)result < 0 )
        return result;
    }
    if ( !*(_BYTE *)(a1 + 353)
      || (result = SkhalpPciAddRule(
                     a1,
                     (unsigned int)SkhalpPciAccessPowerCapability,
                     v5,
                     *(unsigned __int8 *)(a1 + 353),
                     8),
          (int)result >= 0) )
    {
      v11 = *(unsigned __int16 *)(a1 + 360);
      if ( !(_WORD)v11
        || (result = SkhalpPciAddRule(a1, (unsigned int)SkhalpPciAccessGenericNoWrite, v5, v11, 8), (int)result >= 0) )
      {
        v12 = *(unsigned __int16 *)(a1 + 362);
        if ( !(_WORD)v12
          || (result = SkhalpPciAddRule(
                         a1,
                         (unsigned int)&SkhalpPciAccessAcsCapability,
                         v5,
                         v12,
                         (2 * *(_WORD *)(a1 + 424)) & 2 | 0xCu),
              (int)result >= 0)
          && (result = SkhalpPciAddConfigSpaceNeedRestore(a1, &SkhalpPciSaveRestoreAcs, 2), (int)result >= 0) )
        {
          v13 = *(unsigned __int16 *)(a1 + 364);
          if ( !(_WORD)v13
            || (result = SkhalpPciAddRule(a1, (unsigned int)SkpnppSwdValidateTrustlet, v5, v13, 8), (int)result >= 0) )
          {
            v14 = *(unsigned __int16 *)(a1 + 366);
            if ( !(_WORD)v14
              || (result = SkhalpPciAddRule(a1, (unsigned int)SkhalpPciAccessGenericNoWrite, v5, v14, 8),
                  (int)result >= 0)
              && (result = SkhalpPciAddConfigSpaceNeedRestore(a1, &SkhalpPciSaveRestorePasid, 2), (int)result >= 0) )
            {
              v15 = *(unsigned __int16 *)(a1 + 368);
              if ( !(_WORD)v15
                || (result = SkhalpPciAddRule(a1, (unsigned int)SkhalpPciAccessGenericNoWrite, v5, v15, 16),
                    (int)result >= 0)
                && (result = SkhalpPciAddConfigSpaceNeedRestore(a1, &SkhalpPciSaveRestorePri, 2), (int)result >= 0) )
              {
                v16 = *(unsigned __int16 *)(a1 + 370);
                if ( !(_WORD)v16
                  || (result = SkhalpPciAddRule(a1, (unsigned int)SkhalpPciAccessGenericNoWrite, v5, v16, 64),
                      (int)result >= 0) )
                {
                  v17 = *(unsigned __int16 *)(a1 + 372);
                  if ( !(_WORD)v17
                    || (result = SkhalpPciAddRule(a1, (unsigned int)SkhalpPciAccessGenericNoWrite, v5, v17, 52),
                        (int)result >= 0) )
                  {
                    v18 = *(unsigned __int16 *)(a1 + 374);
                    if ( (_WORD)v18 )
                    {
                      result = SkhalpPciAddRule(a1, (unsigned int)SkhalpPciAccessGenericNoWrite, v5, v18, 112);
                      if ( (int)result >= 0 )
                      {
                        v19 = SkhalpPciAddConfigSpaceNeedRestore(
                                a1,
                                &SkhalpPciSaveRestoreVc,
                                *(unsigned __int16 *)(a1 + 376));
                        v20 = 0;
                        if ( v19 < 0 )
                          return (unsigned int)v19;
                        return v20;
                      }
                    }
                    else
                    {
                      return 0;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140091d18  push    rbx
0x140091d1a  push    rbp
0x140091d1b  push    rsi
0x140091d1c  push    rdi
0x140091d1d  push    r14
0x140091d1f  push    r15
0x140091d21  sub     rsp, 38h
0x140091d25  lea     rax, [rcx+180h]
0x140091d2c  xor     edi, edi
0x140091d2e  mov     [rax+8], rax
0x140091d32  lea     rdx, SkhalpPciAccessCommandRegister
0x140091d39  mov     [rax], rax
0x140091d3c  mov     rbx, rcx
0x140091d3f  lea     rax, [rcx+198h]
0x140091d46  mov     [rcx+190h], edi
0x140091d4c  lea     r14d, [rdi+2]
0x140091d50  mov     [rax+8], rax
0x140091d54  lea     r9d, [rdi+4]
0x140091d58  mov     [rsp+68h+var_48], r14w
0x140091d5e  mov     [rax], rax
0x140091d61  call    SkhalpPciAddRule
0x140091d66  test    eax, eax
0x140091d68  js      loc_140092031
0x140091d6e  mov     al, [rbx+39h]
0x140091d71  lea     ebp, [rdi+8]
0x140091d74  lea     r15d, [rdi+10h]
0x140091d78  test    al, al
0x140091d7a  jnz     short loc_140091DA2
0x140091d7c  mov     r9d, r15d
0x140091d7f  mov     [rsp+68h+var_48], 18h
0x140091d86  lea     rdx, SkhalpPciAccessBarRegisters
0x140091d8d  mov     rcx, rbx
0x140091d90  call    SkhalpPciAddRule
0x140091d95  test    eax, eax
0x140091d97  jns     loc_140091E48
0x140091d9d  jmp     loc_140092031
0x140091da2  mov     esi, 1
0x140091da7  cmp     al, sil
0x140091daa  jnz     loc_140091E48
0x140091db0  mov     r9d, r15d
0x140091db3  mov     [rsp+68h+var_48], bp
0x140091db8  lea     rdx, SkhalpPciAccessBarRegisters
0x140091dbf  mov     rcx, rbx
0x140091dc2  call    SkhalpPciAddRule
0x140091dc7  test    eax, eax
0x140091dc9  js      loc_140092031
0x140091dcf  lea     r9d, [rsi+17h]
0x140091dd3  mov     [rsp+68h+var_48], si
0x140091dd8  lea     rdx, SkhalpPciAccessPrimaryBusNumberRegister
0x140091ddf  mov     rcx, rbx
0x140091de2  call    SkhalpPciAddRule
0x140091de7  test    eax, eax
0x140091de9  js      loc_140092031
0x140091def  lea     r9d, [rsi+18h]
0x140091df3  mov     [rsp+68h+var_48], si
0x140091df8  lea     rdx, SkhalpPciAccessSecondaryBusNumberRegister
0x140091dff  mov     rcx, rbx
0x140091e02  call    SkhalpPciAddRule
0x140091e07  test    eax, eax
0x140091e09  js      loc_140092031
0x140091e0f  lea     r9d, [rsi+19h]
0x140091e13  mov     [rsp+68h+var_48], si
0x140091e18  lea     rdx, SkhalpPciAccessSubordinateBusNumberRegisters
0x140091e1f  mov     rcx, rbx
0x140091e22  call    SkhalpPciAddRule
0x140091e27  test    eax, eax
0x140091e29  js      loc_140092031
0x140091e2f  lea     r9d, [rsi+1Fh]
0x140091e33  mov     [rsp+68h+var_48], r15w
0x140091e39  lea     rdx, SkhalpPciAccessBridgeWindows
0x140091e40  mov     rcx, rbx
0x140091e43  call    SkhalpPciAddRule
0x140091e48  movzx   eax, byte ptr [rbx+161h]
0x140091e4f  test    al, al
0x140091e51  jz      short loc_140091E73
0x140091e53  movzx   r9d, ax
0x140091e57  mov     [rsp+68h+var_48], bp
0x140091e5c  lea     rdx, SkhalpPciAccessPowerCapability
0x140091e63  mov     rcx, rbx
0x140091e66  call    SkhalpPciAddRule
0x140091e6b  test    eax, eax
0x140091e6d  js      loc_140092031
0x140091e73  movzx   r9d, word ptr [rbx+168h]
0x140091e7b  lea     rsi, SkhalpPciAccessGenericNoWrite
0x140091e82  test    r9w, r9w
0x140091e86  jz      short loc_140091EA0
0x140091e88  mov     rdx, rsi
0x140091e8b  mov     [rsp+68h+var_48], bp
0x140091e90  mov     rcx, rbx
0x140091e93  call    SkhalpPciAddRule
0x140091e98  test    eax, eax
0x140091e9a  js      loc_140092031
0x140091ea0  movzx   r9d, word ptr [rbx+16Ah]
0x140091ea8  test    r9w, r9w
0x140091eac  jz      short loc_140091EF6
0x140091eae  mov     rax, [rbx+1A8h]
0x140091eb5  lea     rdx, SkhalpPciAccessAcsCapability
0x140091ebc  add     rax, rax
0x140091ebf  mov     rcx, rbx
0x140091ec2  and     ax, r14w
0x140091ec6  or      ax, 0Ch
0x140091eca  mov     [rsp+68h+var_48], ax
0x140091ecf  call    SkhalpPciAddRule
0x140091ed4  test    eax, eax
0x140091ed6  js      loc_140092031
0x140091edc  mov     r8d, r14d
0x140091edf  lea     rdx, SkhalpPciSaveRestoreAcs
0x140091ee6  mov     rcx, rbx
0x140091ee9  call    SkhalpPciAddConfigSpaceNeedRestore
0x140091eee  test    eax, eax
0x140091ef0  js      loc_140092031
0x140091ef6  movzx   r9d, word ptr [rbx+16Ch]
0x140091efe  test    r9w, r9w
0x140091f02  jz      short loc_140091F20
0x140091f04  lea     rdx, SkpnppSwdValidateTrustlet
0x140091f0b  mov     [rsp+68h+var_48], bp
0x140091f10  mov     rcx, rbx
0x140091f13  call    SkhalpPciAddRule
0x140091f18  test    eax, eax
0x140091f1a  js      loc_140092031
0x140091f20  movzx   r9d, word ptr [rbx+16Eh]
0x140091f28  test    r9w, r9w
0x140091f2c  jz      short loc_140091F60
0x140091f2e  mov     rdx, rsi
0x140091f31  mov     [rsp+68h+var_48], bp
0x140091f36  mov     rcx, rbx
0x140091f39  call    SkhalpPciAddRule
0x140091f3e  test    eax, eax
0x140091f40  js      loc_140092031
0x140091f46  mov     r8d, r14d
0x140091f49  lea     rdx, SkhalpPciSaveRestorePasid
0x140091f50  mov     rcx, rbx
0x140091f53  call    SkhalpPciAddConfigSpaceNeedRestore
0x140091f58  test    eax, eax
0x140091f5a  js      loc_140092031
0x140091f60  movzx   r9d, word ptr [rbx+170h]
0x140091f68  test    r9w, r9w
0x140091f6c  jz      short loc_140091FA1
0x140091f6e  mov     rdx, rsi
0x140091f71  mov     [rsp+68h+var_48], r15w
0x140091f77  mov     rcx, rbx
0x140091f7a  call    SkhalpPciAddRule
0x140091f7f  test    eax, eax
0x140091f81  js      loc_140092031
0x140091f87  mov     r8d, r14d
0x140091f8a  lea     rdx, SkhalpPciSaveRestorePri
0x140091f91  mov     rcx, rbx
0x140091f94  call    SkhalpPciAddConfigSpaceNeedRestore
0x140091f99  test    eax, eax
0x140091f9b  js      loc_140092031
0x140091fa1  movzx   r9d, word ptr [rbx+172h]
0x140091fa9  test    r9w, r9w
0x140091fad  jz      short loc_140091FC5
0x140091faf  mov     rdx, rsi
0x140091fb2  mov     [rsp+68h+var_48], 40h ; '@'
0x140091fb9  mov     rcx, rbx
0x140091fbc  call    SkhalpPciAddRule
0x140091fc1  test    eax, eax
0x140091fc3  js      short loc_140092031
0x140091fc5  movzx   r9d, word ptr [rbx+174h]
0x140091fcd  test    r9w, r9w
0x140091fd1  jz      short loc_140091FE9
0x140091fd3  mov     rdx, rsi
0x140091fd6  mov     [rsp+68h+var_48], 34h ; '4'
0x140091fdd  mov     rcx, rbx
0x140091fe0  call    SkhalpPciAddRule
0x140091fe5  test    eax, eax
0x140091fe7  js      short loc_140092031
0x140091fe9  movzx   r9d, word ptr [rbx+176h]
0x140091ff1  test    r9w, r9w
0x140091ff5  jz      short loc_14009202F
0x140091ff7  mov     rdx, rsi
0x140091ffa  mov     [rsp+68h+var_48], 70h ; 'p'
0x140092001  mov     rcx, rbx
0x140092004  call    SkhalpPciAddRule
0x140092009  test    eax, eax
0x14009200b  js      short loc_140092031
0x14009200d  movzx   r8d, word ptr [rbx+178h]
0x140092015  lea     rdx, SkhalpPciSaveRestoreVc
0x14009201c  mov     rcx, rbx
0x14009201f  call    SkhalpPciAddConfigSpaceNeedRestore
0x140092024  test    eax, eax
0x140092026  mov     ecx, edi
0x140092028  cmovs   ecx, eax
0x14009202b  mov     eax, ecx
0x14009202d  jmp     short loc_140092031
0x14009202f  xor     eax, eax
0x140092031  add     rsp, 38h
0x140092035  pop     r15
0x140092037  pop     r14
0x140092039  pop     rdi
0x14009203a  pop     rsi
0x14009203b  pop     rbp
0x14009203c  pop     rbx
0x14009203d  retn
```
