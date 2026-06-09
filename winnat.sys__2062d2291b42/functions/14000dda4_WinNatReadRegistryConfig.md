# WinNatReadRegistryConfig

- ea: `0x14000dda4`
- end: `0x14000e0c9`
- name: `WinNatReadRegistryConfig`
- size: `805`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002f780`

## callees

- `0x14000dda4`
- `0x14002e008`
- `0x14002fa00`
- `0x14002fad4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000e0b0`
- `ntoskrnl!ZwClose` at `0x14000e0b0`

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

  dword_140027B74 = 100;
  Handle = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  dword_140027B78 = 257;
  dword_140027B7C = 300;
  byte_140027B80 = 0;
  result = WinNatRegOpenKey(a1, &Handle, &v6);
  if ( result >= 0 && v6 )
  {
    if ( (int)WinNatRegGetUint32Value(Handle) >= 0 && v6 )
    {
      if ( v7 )
      {
        LOBYTE(dword_140027B78) = 1;
        v2 = 1;
      }
      else
      {
        LOBYTE(dword_140027B78) = 0;
        v2 = 0;
      }
      if ( (xmmword_1400272E0 & 2) != 0 )
        WPP_SF_d(1025, 10, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, v2);
    }
    if ( (int)WinNatRegGetUint32Value(Handle) >= 0 && v6 )
    {
      if ( v8 )
      {
        BYTE1(dword_140027B78) = 1;
        v3 = 1;
      }
      else
      {
        BYTE1(dword_140027B78) = 0;
        v3 = 0;
      }
      if ( (xmmword_1400272E0 & 2) != 0 )
        WPP_SF_d(1025, 11, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, v3);
    }
    if ( (int)WinNatRegGetUint32Value(Handle) >= 0 && v6 )
    {
      if ( v9 )
      {
        BYTE2(dword_140027B78) = 1;
        v4 = 1;
      }
      else
      {
        BYTE2(dword_140027B78) = 0;
        v4 = 0;
      }
      if ( (xmmword_1400272E0 & 2) != 0 )
        WPP_SF_d(1025, 12, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, v4);
    }
    if ( (int)WinNatRegGetUint32Value(Handle) >= 0 )
    {
      if ( v6 )
      {
        HIBYTE(dword_140027B78) = 0;
        if ( (xmmword_1400272E0 & 2) != 0 )
          WPP_SF_d(1025, 13, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, 0);
      }
    }
    if ( (int)WinNatRegGetUint32Value(Handle) >= 0 && v6 )
      byte_140027B80 = 0;
    if ( (xmmword_1400272E0 & 2) != 0 )
      WPP_SF_d(1025, 14, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, (unsigned __int8)byte_140027B80);
    result = WinNatRegGetUint32Value(Handle);
    if ( result >= 0 )
    {
      if ( (xmmword_1400272E0 & 2) != 0 )
        WPP_SF_d(1025, 16, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, (unsigned int)dword_140027B74);
      result = WinNatRegGetUint32Value(Handle);
      if ( result >= 0 && (xmmword_1400272E0 & 2) != 0 )
        result = WPP_SF_d(1025, 18, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids, (unsigned int)dword_140027B7C);
    }
  }
  if ( Handle )
    return ZwClose(Handle);
  return result;
}

```

## disassembly

```asm
0x14000dda4  push    rbp
0x14000dda6  push    rbx
0x14000dda7  push    rdi
0x14000dda8  push    r14
0x14000ddaa  push    r15
0x14000ddac  mov     rbp, rsp
0x14000ddaf  sub     rsp, 40h
0x14000ddb3  xor     edi, edi
0x14000ddb5  mov     cs:dword_140027B74, 64h ; 'd'
0x14000ddbf  lea     r8, [rbp+arg_0]
0x14000ddc3  mov     [rbp+Handle], rdi
0x14000ddc7  lea     rdx, [rbp+Handle]
0x14000ddcb  mov     [rbp+arg_0], dil
0x14000ddcf  mov     [rbp+var_18], edi
0x14000ddd2  lea     ebx, [rdi+1]
0x14000ddd5  mov     [rbp+arg_8], edi
0x14000ddd8  mov     [rbp+arg_10], edi
0x14000dddb  mov     [rbp+arg_18], edi
0x14000ddde  mov     [rbp+var_14], edi
0x14000dde1  mov     [rbp+var_20], edi
0x14000dde4  mov     [rbp+var_1C], edi
0x14000dde7  mov     cs:dword_140027B78, 101h
0x14000ddf1  mov     cs:dword_140027B7C, 12Ch
0x14000ddfb  mov     cs:byte_140027B80, dil
0x14000de02  call    WinNatRegOpenKey
0x14000de07  test    eax, eax
0x14000de09  js      loc_14000E0A7
0x14000de0f  cmp     [rbp+arg_0], dil
0x14000de13  jz      loc_14000E0A7
0x14000de19  mov     rcx, [rbp+Handle]; KeyHandle
0x14000de1d  lea     r9, [rbp+arg_0]
0x14000de21  lea     r8, [rbp+arg_8]
0x14000de25  lea     rdx, aRscaware; "RSCAware"
0x14000de2c  call    WinNatRegGetUint32Value
0x14000de31  lea     r15, WPP_3bfaaace2ff9302deb5712e69b1506cc_Traceguids
0x14000de38  mov     r14d, 401h
0x14000de3e  test    eax, eax
0x14000de40  js      short loc_14000DE7B
0x14000de42  cmp     [rbp+arg_0], dil
0x14000de46  jz      short loc_14000DE7B
0x14000de48  cmp     [rbp+arg_8], edi
0x14000de4b  jz      short loc_14000DE58
0x14000de4d  mov     byte ptr cs:dword_140027B78, bl
0x14000de53  mov     r9d, ebx
0x14000de56  jmp     short loc_14000DE62
0x14000de58  mov     byte ptr cs:dword_140027B78, dil
0x14000de5f  mov     r9d, edi
0x14000de62  test    byte ptr cs:xmmword_1400272E0, 2
0x14000de69  jz      short loc_14000DE7B
0x14000de6b  mov     edx, 0Ah
0x14000de70  mov     ecx, r14d
0x14000de73  mov     r8, r15
0x14000de76  call    WPP_SF_d
0x14000de7b  mov     rcx, [rbp+Handle]; KeyHandle
0x14000de7f  lea     r9, [rbp+arg_0]
0x14000de83  lea     r8, [rbp+arg_10]
0x14000de87  lea     rdx, aUroaware; "UROAware"
0x14000de8e  call    WinNatRegGetUint32Value
0x14000de93  test    eax, eax
0x14000de95  js      short loc_14000DED0
0x14000de97  cmp     [rbp+arg_0], dil
0x14000de9b  jz      short loc_14000DED0
0x14000de9d  cmp     [rbp+arg_10], edi
0x14000dea0  jz      short loc_14000DEAD
0x14000dea2  mov     byte ptr cs:dword_140027B78+1, bl
0x14000dea8  mov     r9d, ebx
0x14000deab  jmp     short loc_14000DEB7
0x14000dead  mov     byte ptr cs:dword_140027B78+1, dil
0x14000deb4  mov     r9d, edi
0x14000deb7  test    byte ptr cs:xmmword_1400272E0, 2
0x14000debe  jz      short loc_14000DED0
0x14000dec0  mov     edx, 0Bh
0x14000dec5  mov     ecx, r14d
0x14000dec8  mov     r8, r15
0x14000decb  call    WPP_SF_d
0x14000ded0  mov     rcx, [rbp+Handle]; KeyHandle
0x14000ded4  lea     r9, [rbp+arg_0]
0x14000ded8  lea     r8, [rbp+arg_18]
0x14000dedc  lea     rdx, aFragmentaware; "FragmentAware"
0x14000dee3  call    WinNatRegGetUint32Value
0x14000dee8  test    eax, eax
0x14000deea  js      short loc_14000DF25
0x14000deec  cmp     [rbp+arg_0], dil
0x14000def0  jz      short loc_14000DF25
0x14000def2  cmp     [rbp+arg_18], edi
0x14000def5  jz      short loc_14000DF02
0x14000def7  mov     byte ptr cs:dword_140027B78+2, bl
0x14000defd  mov     r9d, ebx
0x14000df00  jmp     short loc_14000DF0C
0x14000df02  mov     byte ptr cs:dword_140027B78+2, dil
0x14000df09  mov     r9d, edi
0x14000df0c  test    byte ptr cs:xmmword_1400272E0, 2
0x14000df13  jz      short loc_14000DF25
0x14000df15  mov     edx, 0Ch
0x14000df1a  mov     ecx, r14d
0x14000df1d  mov     r8, r15
0x14000df20  call    WPP_SF_d
0x14000df25  mov     rcx, [rbp+Handle]; KeyHandle
0x14000df29  lea     r9, [rbp+arg_0]
0x14000df2d  lea     r8, [rbp+var_20]
0x14000df31  lea     rdx, aForceinternalr; "ForceInternalRoute"
0x14000df38  call    WinNatRegGetUint32Value
0x14000df3d  test    eax, eax
0x14000df3f  js      short loc_14000DF79
0x14000df41  cmp     [rbp+arg_0], dil
0x14000df45  jz      short loc_14000DF79
0x14000df47  cmp     [rbp+var_20], edi
0x14000df4a  jz      short loc_14000DF54
0x14000df4c  mov     byte ptr cs:dword_140027B78+3, bl
0x14000df52  jmp     short loc_14000DF5D
0x14000df54  mov     byte ptr cs:dword_140027B78+3, dil
0x14000df5b  mov     ebx, edi
0x14000df5d  test    byte ptr cs:xmmword_1400272E0, 2
0x14000df64  jz      short loc_14000DF79
0x14000df66  mov     edx, 0Dh
0x14000df6b  mov     ecx, r14d
0x14000df6e  mov     r9d, ebx
0x14000df71  mov     r8, r15
0x14000df74  call    WPP_SF_d
0x14000df79  mov     rcx, [rbp+Handle]; KeyHandle
0x14000df7d  lea     r9, [rbp+arg_0]
0x14000df81  lea     r8, [rbp+var_1C]
0x14000df85  lea     rdx, aClampmssenable; "ClampMssEnabled"
0x14000df8c  call    WinNatRegGetUint32Value
0x14000df91  test    eax, eax
0x14000df93  js      short loc_14000DFA5
0x14000df95  cmp     [rbp+arg_0], dil
0x14000df99  jz      short loc_14000DFA5
0x14000df9b  cmp     [rbp+var_1C], edi
0x14000df9e  setnz   cs:byte_140027B80
0x14000dfa5  test    byte ptr cs:xmmword_1400272E0, 2
0x14000dfac  jz      short loc_14000DFC6
0x14000dfae  movzx   r9d, cs:byte_140027B80
0x14000dfb6  mov     edx, 0Eh
0x14000dfbb  mov     ecx, r14d
0x14000dfbe  mov     r8, r15
0x14000dfc1  call    WPP_SF_d
0x14000dfc6  mov     rcx, [rbp+Handle]; KeyHandle
0x14000dfca  lea     r9, [rbp+arg_0]
0x14000dfce  lea     r8, [rbp+var_18]
0x14000dfd2  lea     rdx, aPortchunksize; "PortChunkSize"
0x14000dfd9  call    WinNatRegGetUint32Value
0x14000dfde  test    eax, eax
0x14000dfe0  js      loc_14000E0A7
0x14000dfe6  cmp     [rbp+arg_0], dil
0x14000dfea  jz      short loc_14000E01B
0x14000dfec  mov     ebx, [rbp+var_18]
0x14000dfef  lea     eax, [rbx-1]
0x14000dff2  cmp     eax, 0FFFEh
0x14000dff7  ja      short loc_14000E01B
0x14000dff9  test    byte ptr cs:xmmword_1400272E0, 2
0x14000e000  jz      short loc_14000E015
0x14000e002  mov     edx, 0Fh
0x14000e007  mov     ecx, r14d
0x14000e00a  mov     r9d, ebx
0x14000e00d  mov     r8, r15
0x14000e010  call    WPP_SF_d
0x14000e015  mov     cs:dword_140027B74, ebx
0x14000e01b  test    byte ptr cs:xmmword_1400272E0, 2
0x14000e022  jz      short loc_14000E03B
0x14000e024  mov     r9d, cs:dword_140027B74
0x14000e02b  mov     edx, 10h
0x14000e030  mov     ecx, r14d
0x14000e033  mov     r8, r15
0x14000e036  call    WPP_SF_d
0x14000e03b  mov     rcx, [rbp+Handle]; KeyHandle
0x14000e03f  lea     r9, [rbp+arg_0]
0x14000e043  lea     r8, [rbp+var_14]
0x14000e047  lea     rdx, aUdpsessiontime; "UdpSessionTimeout"
0x14000e04e  call    WinNatRegGetUint32Value
0x14000e053  test    eax, eax
0x14000e055  js      short loc_14000E0A7
0x14000e057  cmp     [rbp+arg_0], dil
0x14000e05b  jz      short loc_14000E087
0x14000e05d  mov     r9d, [rbp+var_14]
0x14000e061  cmp     r9d, 1Eh
0x14000e065  jb      short loc_14000E087
0x14000e067  mov     cs:dword_140027B7C, r9d
0x14000e06e  test    byte ptr cs:xmmword_1400272E0, 2
0x14000e075  jz      short loc_14000E0A7
0x14000e077  mov     edx, 11h
0x14000e07c  mov     ecx, r14d
0x14000e07f  mov     r8, r15
0x14000e082  call    WPP_SF_d
0x14000e087  test    byte ptr cs:xmmword_1400272E0, 2
0x14000e08e  jz      short loc_14000E0A7
0x14000e090  mov     r9d, cs:dword_140027B7C
0x14000e097  mov     edx, 12h
0x14000e09c  mov     ecx, r14d
0x14000e09f  mov     r8, r15
0x14000e0a2  call    WPP_SF_d
0x14000e0a7  mov     rcx, [rbp+Handle]; Handle
0x14000e0ab  test    rcx, rcx
0x14000e0ae  jz      short loc_14000E0BC
0x14000e0b0  call    cs:__imp_ZwClose
0x14000e0b7  nop     dword ptr [rax+rax+00h]
0x14000e0bc  add     rsp, 40h
0x14000e0c0  pop     r15
0x14000e0c2  pop     r14
0x14000e0c4  pop     rdi
0x14000e0c5  pop     rbx
0x14000e0c6  pop     rbp
0x14000e0c7  retn
```
