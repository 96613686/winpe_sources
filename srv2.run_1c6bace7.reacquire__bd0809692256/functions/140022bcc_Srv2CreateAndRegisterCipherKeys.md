# Srv2CreateAndRegisterCipherKeys

- ea: `0x140022bcc`
- end: `0x140022d7b`
- name: `Srv2CreateAndRegisterCipherKeys`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140092240`

## callees

- `0x14001f7a4`
- `0x140022bcc`
- `0x140022e3c`
- `0x140022ea4`

## import_xrefs

- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140022be2`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x140022be2`
- `srvnet!SmbCryptoKeyDereference` at `0x140022d23`
- `srvnet!SmbCryptoKeyDereference` at `0x140022d39`
- `srvnet!SmbCryptoKeyDereference` at `0x140022d23`
- `srvnet!SmbCryptoKeyDereference` at `0x140022d39`
- `srvnet!SmbCryptoKeyTableInsert` at `0x140022c73`
- `srvnet!SmbCryptoKeyTableInsert` at `0x140022c73`
- `srvnet!SmbCryptoCreateServerCipherKeys` at `0x140022c38`
- `srvnet!SmbCryptoCreateServerCipherKeys` at `0x140022c38`

## pseudocode

```c
__int64 __fastcall Srv2CreateAndRegisterCipherKeys(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        _QWORD *a8,
        _QWORD *a9)
{
  __int64 v10; // rbp
  USHORT HighestNodeNumber; // r14
  __int64 v14; // rdx
  int v15; // edi
  __int64 v16; // r8
  unsigned __int16 v17; // r14
  unsigned __int16 i; // bx
  __int64 v20; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v21[6]; // [rsp+48h] [rbp-30h] BYREF

  v10 = a1;
  HighestNodeNumber = KeQueryHighestNodeNumber();
  v20 = 0;
  v21[0] = 0;
  v15 = SmbCryptoCreateServerCipherKeys(a3, a4, a5, a6, a7, &v20, v21);
  if ( v15 < 0 )
  {
LABEL_11:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && SHIDWORD(WPP_GLOBAL_Control->Timer) < 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_DiD(WPP_GLOBAL_Control->AttachedDevice, v14, v16, (unsigned int)v10, a2, v15);
    }
    if ( v20 )
      SmbCryptoKeyDereference();
    if ( v21[0] )
      SmbCryptoKeyDereference();
    *a8 = 0;
    *a9 = 0;
    Srv2DeregisterDecryptionKey((unsigned int)v10, a2);
  }
  else
  {
    v17 = HighestNodeNumber + 1;
    for ( i = 0; i < v17; ++i )
    {
      v15 = SmbCryptoKeyTableInsert(*((_QWORD *)Srv2DecryptionKeyTable + i), v10, a2, v21[0]);
      if ( v15 < 0 )
        goto LABEL_11;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && SHIDWORD(WPP_GLOBAL_Control->Timer) < 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDi(WPP_GLOBAL_Control->AttachedDevice, v14, v16, v20, v10, a2);
    }
    *a8 = v20;
    *a9 = v21[0];
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140022bcc  push    rbx
0x140022bce  push    rbp
0x140022bcf  push    rsi
0x140022bd0  push    rdi
0x140022bd1  push    r14
0x140022bd3  sub     rsp, 50h
0x140022bd7  mov     rbx, r9
0x140022bda  mov     ebp, ecx
0x140022bdc  mov     edi, r8d
0x140022bdf  mov     rsi, rdx
0x140022be2  call    cs:__imp_KeQueryHighestNodeNumber
0x140022be9  nop     dword ptr [rax+rax+00h]
0x140022bee  mov     r9, [rsp+78h+arg_28]
0x140022bf6  mov     rdx, rbx
0x140022bf9  mov     r8d, [rsp+78h+arg_20]
0x140022c01  movzx   r14d, ax
0x140022c05  lea     rax, [rsp+78h+var_30]
0x140022c0a  mov     [rsp+78h+var_38], 0
0x140022c13  mov     [rsp+78h+var_48], rax
0x140022c18  mov     ecx, edi
0x140022c1a  lea     rax, [rsp+78h+var_38]
0x140022c1f  mov     [rsp+78h+var_30], 0
0x140022c28  mov     [rsp+78h+var_50], rax
0x140022c2d  mov     eax, [rsp+78h+arg_30]
0x140022c34  mov     dword ptr [rsp+78h+var_58], eax
0x140022c38  call    cs:__imp_SmbCryptoCreateServerCipherKeys
0x140022c3f  nop     dword ptr [rax+rax+00h]
0x140022c44  mov     edi, eax
0x140022c46  test    eax, eax
0x140022c48  js      loc_140022CE5
0x140022c4e  inc     r14w
0x140022c52  xor     ebx, ebx
0x140022c54  cmp     bx, r14w
0x140022c58  jnb     short loc_140022C8A
0x140022c5a  mov     rcx, cs:Srv2DecryptionKeyTable
0x140022c61  mov     rdx, rbp
0x140022c64  mov     r9, [rsp+78h+var_30]
0x140022c69  mov     r8, rsi
0x140022c6c  movzx   eax, bx
0x140022c6f  mov     rcx, [rcx+rax*8]
0x140022c73  call    cs:__imp_SmbCryptoKeyTableInsert
0x140022c7a  nop     dword ptr [rax+rax+00h]
0x140022c7f  mov     edi, eax
0x140022c81  test    eax, eax
0x140022c83  js      short loc_140022CE5
0x140022c85  inc     bx
0x140022c88  jmp     short loc_140022C54
0x140022c8a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140022c91  lea     rax, WPP_GLOBAL_Control
0x140022c98  cmp     rcx, rax
0x140022c9b  jz      short loc_140022CC0
0x140022c9d  cmp     dword ptr [rcx+2Ch], 0
0x140022ca1  jge     short loc_140022CC0
0x140022ca3  cmp     byte ptr [rcx+29h], 2
0x140022ca7  jb      short loc_140022CC0
0x140022ca9  mov     r9, [rsp+78h+var_38]
0x140022cae  mov     rcx, [rcx+18h]
0x140022cb2  mov     [rsp+78h+var_50], rsi
0x140022cb7  mov     dword ptr [rsp+78h+var_58], ebp
0x140022cbb  call    WPP_SF_qDi
0x140022cc0  mov     rcx, [rsp+78h+arg_38]
0x140022cc8  mov     rax, [rsp+78h+var_38]
0x140022ccd  mov     [rcx], rax
0x140022cd0  mov     rcx, [rsp+78h+arg_40]
0x140022cd8  mov     rax, [rsp+78h+var_30]
0x140022cdd  mov     [rcx], rax
0x140022ce0  jmp     loc_140022D6D
0x140022ce5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140022cec  lea     rax, WPP_GLOBAL_Control
0x140022cf3  cmp     rcx, rax
0x140022cf6  jz      short loc_140022D19
0x140022cf8  cmp     dword ptr [rcx+2Ch], 0
0x140022cfc  jge     short loc_140022D19
0x140022cfe  cmp     byte ptr [rcx+29h], 1
0x140022d02  jb      short loc_140022D19
0x140022d04  mov     rcx, [rcx+18h]
0x140022d08  mov     r9d, ebp
0x140022d0b  mov     dword ptr [rsp+78h+var_50], edi
0x140022d0f  mov     [rsp+78h+var_58], rsi
0x140022d14  call    WPP_SF_DiD
0x140022d19  mov     rcx, [rsp+78h+var_38]
0x140022d1e  test    rcx, rcx
0x140022d21  jz      short loc_140022D2F
0x140022d23  call    cs:__imp_SmbCryptoKeyDereference
0x140022d2a  nop     dword ptr [rax+rax+00h]
0x140022d2f  mov     rcx, [rsp+78h+var_30]
0x140022d34  test    rcx, rcx
0x140022d37  jz      short loc_140022D45
0x140022d39  call    cs:__imp_SmbCryptoKeyDereference
0x140022d40  nop     dword ptr [rax+rax+00h]
0x140022d45  mov     rax, [rsp+78h+arg_38]
0x140022d4d  mov     rdx, rsi
0x140022d50  mov     ecx, ebp
0x140022d52  mov     qword ptr [rax], 0
0x140022d59  mov     rax, [rsp+78h+arg_40]
0x140022d61  mov     qword ptr [rax], 0
0x140022d68  call    Srv2DeregisterDecryptionKey
0x140022d6d  mov     eax, edi
0x140022d6f  add     rsp, 50h
0x140022d73  pop     r14
0x140022d75  pop     rdi
0x140022d76  pop     rsi
0x140022d77  pop     rbp
0x140022d78  pop     rbx
0x140022d79  retn
```
