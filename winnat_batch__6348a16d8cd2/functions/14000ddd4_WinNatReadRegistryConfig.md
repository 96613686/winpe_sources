# WinNatReadRegistryConfig

- ea: `0x14000ddd4`
- end: `0x14000e0f9`
- name: `WinNatReadRegistryConfig`
- size: `805`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002e780`

## callees

- `0x14000ddd4`
- `0x14002d008`
- `0x14002ea00`
- `0x14002ead4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000e0e0`
- `ntoskrnl!ZwClose` at `0x14000e0e0`

## pseudocode

```c
int __fastcall WinNatReadRegistryConfig(__int64 a1)
{
  int result; // eax
  __int64 v2; // r9
  __int64 v3; // r9
  __int64 v4; // r9
  HANDLE Handle; // [rsp+30h] [rbp-10h] BYREF
  char v6; // [rsp+70h] [rbp+30h] BYREF
  int v7; // [rsp+78h] [rbp+38h]
  int v8; // [rsp+80h] [rbp+40h]
  int v9; // [rsp+88h] [rbp+48h]

  dword_140026B74 = 100;
  Handle = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  dword_140026B78 = 257;
  dword_140026B7C = 300;
  byte_140026B80 = 0;
  result = WinNatRegOpenKey(a1, &Handle, &v6);
  if ( result >= 0 && v6 )
  {
    if ( (int)WinNatRegGetUint32Value(Handle) >= 0 && v6 )
    {
      if ( v7 )
      {
        LOBYTE(dword_140026B78) = 1;
        v2 = 1;
      }
      else
      {
        LOBYTE(dword_140026B78) = 0;
        v2 = 0;
      }
      if ( (xmmword_1400262E0 & 2) != 0 )
        WPP_SF_d(1025, 10, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, v2);
    }
    if ( (int)WinNatRegGetUint32Value(Handle) >= 0 && v6 )
    {
      if ( v8 )
      {
        BYTE1(dword_140026B78) = 1;
        v3 = 1;
      }
      else
      {
        BYTE1(dword_140026B78) = 0;
        v3 = 0;
      }
      if ( (xmmword_1400262E0 & 2) != 0 )
        WPP_SF_d(1025, 11, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, v3);
    }
    if ( (int)WinNatRegGetUint32Value(Handle) >= 0 && v6 )
    {
      if ( v9 )
      {
        BYTE2(dword_140026B78) = 1;
        v4 = 1;
      }
      else
      {
        BYTE2(dword_140026B78) = 0;
        v4 = 0;
      }
      if ( (xmmword_1400262E0 & 2) != 0 )
        WPP_SF_d(1025, 12, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, v4);
    }
    if ( (int)WinNatRegGetUint32Value(Handle) >= 0 )
    {
      if ( v6 )
      {
        HIBYTE(dword_140026B78) = 0;
        if ( (xmmword_1400262E0 & 2) != 0 )
          WPP_SF_d(1025, 13, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, 0);
      }
    }
    if ( (int)WinNatRegGetUint32Value(Handle) >= 0 && v6 )
      byte_140026B80 = 0;
    if ( (xmmword_1400262E0 & 2) != 0 )
      WPP_SF_d(1025, 14, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, (unsigned __int8)byte_140026B80);
    result = WinNatRegGetUint32Value(Handle);
    if ( result >= 0 )
    {
      if ( (xmmword_1400262E0 & 2) != 0 )
        WPP_SF_d(1025, 16, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, (unsigned int)dword_140026B74);
      result = WinNatRegGetUint32Value(Handle);
      if ( result >= 0 && (xmmword_1400262E0 & 2) != 0 )
        result = WPP_SF_d(1025, 18, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, (unsigned int)dword_140026B7C);
    }
  }
  if ( Handle )
    return ZwClose(Handle);
  return result;
}

```

## disassembly

```asm
0x14000ddd4  push    rbp
0x14000ddd6  push    rbx
0x14000ddd7  push    rdi
0x14000ddd8  push    r14
0x14000ddda  push    r15
0x14000dddc  mov     rbp, rsp
0x14000dddf  sub     rsp, 40h
0x14000dde3  xor     edi, edi
0x14000dde5  mov     cs:dword_140026B74, 64h ; 'd'
0x14000ddef  lea     r8, [rbp+arg_0]
0x14000ddf3  mov     [rbp+Handle], rdi
0x14000ddf7  lea     rdx, [rbp+Handle]
0x14000ddfb  mov     [rbp+arg_0], dil
0x14000ddff  mov     [rbp+var_18], edi
0x14000de02  lea     ebx, [rdi+1]
0x14000de05  mov     [rbp+arg_8], edi
0x14000de08  mov     [rbp+arg_10], edi
0x14000de0b  mov     [rbp+arg_18], edi
0x14000de0e  mov     [rbp+var_14], edi
0x14000de11  mov     [rbp+var_20], edi
0x14000de14  mov     [rbp+var_1C], edi
0x14000de17  mov     cs:dword_140026B78, 101h
0x14000de21  mov     cs:dword_140026B7C, 12Ch
0x14000de2b  mov     cs:byte_140026B80, dil
0x14000de32  call    WinNatRegOpenKey
0x14000de37  test    eax, eax
0x14000de39  js      loc_14000E0D7
0x14000de3f  cmp     [rbp+arg_0], dil
0x14000de43  jz      loc_14000E0D7
0x14000de49  mov     rcx, [rbp+Handle]; KeyHandle
0x14000de4d  lea     r9, [rbp+arg_0]
0x14000de51  lea     r8, [rbp+arg_8]
0x14000de55  lea     rdx, aRscaware; "RSCAware"
0x14000de5c  call    WinNatRegGetUint32Value
0x14000de61  lea     r15, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids
0x14000de68  mov     r14d, 401h
0x14000de6e  test    eax, eax
0x14000de70  js      short loc_14000DEAB
0x14000de72  cmp     [rbp+arg_0], dil
0x14000de76  jz      short loc_14000DEAB
0x14000de78  cmp     [rbp+arg_8], edi
0x14000de7b  jz      short loc_14000DE88
0x14000de7d  mov     byte ptr cs:dword_140026B78, bl
0x14000de83  mov     r9d, ebx
0x14000de86  jmp     short loc_14000DE92
0x14000de88  mov     byte ptr cs:dword_140026B78, dil
0x14000de8f  mov     r9d, edi
0x14000de92  test    byte ptr cs:xmmword_1400262E0, 2
0x14000de99  jz      short loc_14000DEAB
0x14000de9b  mov     edx, 0Ah
0x14000dea0  mov     ecx, r14d
0x14000dea3  mov     r8, r15
0x14000dea6  call    WPP_SF_d
0x14000deab  mov     rcx, [rbp+Handle]; KeyHandle
0x14000deaf  lea     r9, [rbp+arg_0]
0x14000deb3  lea     r8, [rbp+arg_10]
0x14000deb7  lea     rdx, aUroaware; "UROAware"
0x14000debe  call    WinNatRegGetUint32Value
0x14000dec3  test    eax, eax
0x14000dec5  js      short loc_14000DF00
0x14000dec7  cmp     [rbp+arg_0], dil
0x14000decb  jz      short loc_14000DF00
0x14000decd  cmp     [rbp+arg_10], edi
0x14000ded0  jz      short loc_14000DEDD
0x14000ded2  mov     byte ptr cs:dword_140026B78+1, bl
0x14000ded8  mov     r9d, ebx
0x14000dedb  jmp     short loc_14000DEE7
0x14000dedd  mov     byte ptr cs:dword_140026B78+1, dil
0x14000dee4  mov     r9d, edi
0x14000dee7  test    byte ptr cs:xmmword_1400262E0, 2
0x14000deee  jz      short loc_14000DF00
0x14000def0  mov     edx, 0Bh
0x14000def5  mov     ecx, r14d
0x14000def8  mov     r8, r15
0x14000defb  call    WPP_SF_d
0x14000df00  mov     rcx, [rbp+Handle]; KeyHandle
0x14000df04  lea     r9, [rbp+arg_0]
0x14000df08  lea     r8, [rbp+arg_18]
0x14000df0c  lea     rdx, aFragmentaware; "FragmentAware"
0x14000df13  call    WinNatRegGetUint32Value
0x14000df18  test    eax, eax
0x14000df1a  js      short loc_14000DF55
0x14000df1c  cmp     [rbp+arg_0], dil
0x14000df20  jz      short loc_14000DF55
0x14000df22  cmp     [rbp+arg_18], edi
0x14000df25  jz      short loc_14000DF32
0x14000df27  mov     byte ptr cs:dword_140026B78+2, bl
0x14000df2d  mov     r9d, ebx
0x14000df30  jmp     short loc_14000DF3C
0x14000df32  mov     byte ptr cs:dword_140026B78+2, dil
0x14000df39  mov     r9d, edi
0x14000df3c  test    byte ptr cs:xmmword_1400262E0, 2
0x14000df43  jz      short loc_14000DF55
0x14000df45  mov     edx, 0Ch
0x14000df4a  mov     ecx, r14d
0x14000df4d  mov     r8, r15
0x14000df50  call    WPP_SF_d
0x14000df55  mov     rcx, [rbp+Handle]; KeyHandle
0x14000df59  lea     r9, [rbp+arg_0]
0x14000df5d  lea     r8, [rbp+var_20]
0x14000df61  lea     rdx, aForceinternalr; "ForceInternalRoute"
0x14000df68  call    WinNatRegGetUint32Value
0x14000df6d  test    eax, eax
0x14000df6f  js      short loc_14000DFA9
0x14000df71  cmp     [rbp+arg_0], dil
0x14000df75  jz      short loc_14000DFA9
0x14000df77  cmp     [rbp+var_20], edi
0x14000df7a  jz      short loc_14000DF84
0x14000df7c  mov     byte ptr cs:dword_140026B78+3, bl
0x14000df82  jmp     short loc_14000DF8D
0x14000df84  mov     byte ptr cs:dword_140026B78+3, dil
0x14000df8b  mov     ebx, edi
0x14000df8d  test    byte ptr cs:xmmword_1400262E0, 2
0x14000df94  jz      short loc_14000DFA9
0x14000df96  mov     edx, 0Dh
0x14000df9b  mov     ecx, r14d
0x14000df9e  mov     r9d, ebx
0x14000dfa1  mov     r8, r15
0x14000dfa4  call    WPP_SF_d
0x14000dfa9  mov     rcx, [rbp+Handle]; KeyHandle
0x14000dfad  lea     r9, [rbp+arg_0]
0x14000dfb1  lea     r8, [rbp+var_1C]
0x14000dfb5  lea     rdx, aClampmssenable; "ClampMssEnabled"
0x14000dfbc  call    WinNatRegGetUint32Value
0x14000dfc1  test    eax, eax
0x14000dfc3  js      short loc_14000DFD5
0x14000dfc5  cmp     [rbp+arg_0], dil
0x14000dfc9  jz      short loc_14000DFD5
0x14000dfcb  cmp     [rbp+var_1C], edi
0x14000dfce  setnz   cs:byte_140026B80
0x14000dfd5  test    byte ptr cs:xmmword_1400262E0, 2
0x14000dfdc  jz      short loc_14000DFF6
0x14000dfde  movzx   r9d, cs:byte_140026B80
0x14000dfe6  mov     edx, 0Eh
0x14000dfeb  mov     ecx, r14d
0x14000dfee  mov     r8, r15
0x14000dff1  call    WPP_SF_d
0x14000dff6  mov     rcx, [rbp+Handle]; KeyHandle
0x14000dffa  lea     r9, [rbp+arg_0]
0x14000dffe  lea     r8, [rbp+var_18]
0x14000e002  lea     rdx, aPortchunksize; "PortChunkSize"
0x14000e009  call    WinNatRegGetUint32Value
0x14000e00e  test    eax, eax
0x14000e010  js      loc_14000E0D7
0x14000e016  cmp     [rbp+arg_0], dil
0x14000e01a  jz      short loc_14000E04B
0x14000e01c  mov     ebx, [rbp+var_18]
0x14000e01f  lea     eax, [rbx-1]
0x14000e022  cmp     eax, 0FFFEh
0x14000e027  ja      short loc_14000E04B
0x14000e029  test    byte ptr cs:xmmword_1400262E0, 2
0x14000e030  jz      short loc_14000E045
0x14000e032  mov     edx, 0Fh
0x14000e037  mov     ecx, r14d
0x14000e03a  mov     r9d, ebx
0x14000e03d  mov     r8, r15
0x14000e040  call    WPP_SF_d
0x14000e045  mov     cs:dword_140026B74, ebx
0x14000e04b  test    byte ptr cs:xmmword_1400262E0, 2
0x14000e052  jz      short loc_14000E06B
0x14000e054  mov     r9d, cs:dword_140026B74
0x14000e05b  mov     edx, 10h
0x14000e060  mov     ecx, r14d
0x14000e063  mov     r8, r15
0x14000e066  call    WPP_SF_d
0x14000e06b  mov     rcx, [rbp+Handle]; KeyHandle
0x14000e06f  lea     r9, [rbp+arg_0]
0x14000e073  lea     r8, [rbp+var_14]
0x14000e077  lea     rdx, aUdpsessiontime; "UdpSessionTimeout"
0x14000e07e  call    WinNatRegGetUint32Value
0x14000e083  test    eax, eax
0x14000e085  js      short loc_14000E0D7
0x14000e087  cmp     [rbp+arg_0], dil
0x14000e08b  jz      short loc_14000E0B7
0x14000e08d  mov     r9d, [rbp+var_14]
0x14000e091  cmp     r9d, 1Eh
0x14000e095  jb      short loc_14000E0B7
0x14000e097  mov     cs:dword_140026B7C, r9d
0x14000e09e  test    byte ptr cs:xmmword_1400262E0, 2
0x14000e0a5  jz      short loc_14000E0D7
0x14000e0a7  mov     edx, 11h
0x14000e0ac  mov     ecx, r14d
0x14000e0af  mov     r8, r15
0x14000e0b2  call    WPP_SF_d
0x14000e0b7  test    byte ptr cs:xmmword_1400262E0, 2
0x14000e0be  jz      short loc_14000E0D7
0x14000e0c0  mov     r9d, cs:dword_140026B7C
0x14000e0c7  mov     edx, 12h
0x14000e0cc  mov     ecx, r14d
0x14000e0cf  mov     r8, r15
0x14000e0d2  call    WPP_SF_d
0x14000e0d7  mov     rcx, [rbp+Handle]; Handle
0x14000e0db  test    rcx, rcx
0x14000e0de  jz      short loc_14000E0EC
0x14000e0e0  call    cs:__imp_ZwClose
0x14000e0e7  nop     dword ptr [rax+rax+00h]
0x14000e0ec  add     rsp, 40h
0x14000e0f0  pop     r15
0x14000e0f2  pop     r14
0x14000e0f4  pop     rdi
0x14000e0f5  pop     rbx
0x14000e0f6  pop     rbp
0x14000e0f7  retn
```
