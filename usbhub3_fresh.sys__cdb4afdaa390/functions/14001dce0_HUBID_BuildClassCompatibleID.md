# HUBID_BuildClassCompatibleID

- ea: `0x14001dce0`
- end: `0x14001e11c`
- name: `HUBID_BuildClassCompatibleID`
- size: `1084`
- prototype: `NTSTATUS __fastcall(__int64, __int64, _OWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001e124`

## callees

- `0x14000f648`
- `0x14001dc30`
- `0x14001dce0`
- `0x14002f788`
- `0x140045530`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001df7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001df7d`
- `ntoskrnl!ExAllocatePool2` at `0x14001dedf`
- `ntoskrnl!ExAllocatePool2` at `0x14001dedf`

## string_xrefs

- `0x14001dd8e`: `USB\MS_COMP_%.8S&MS_SUBCOMP_%.8S`
- `0x14001ddef`: `USB\MS_COMP_%.8S&MS_SUBCOMP_%.8S`
- `0x14001de35`: `USB\MS_COMP_%.8S`
- `0x14001df8d`: `USB\COMPAT_VID_%04X&Class_%02X&SubClass_%02X&Prot_%02X`
- `0x14001dfef`: `USB\COMPAT_VID_%04X&Class_%02X&SubClass_%02X`
- `0x14001e026`: `USB\COMPAT_VID_%04X&Class_%02X`

## pseudocode

```c
NTSTATUS __fastcall HUBID_BuildClassCompatibleID(__int64 a1, __int64 a2, _OWORD *a3)
{
  unsigned __int8 *v6; // rax
  unsigned __int16 v7; // r15
  unsigned __int16 v8; // r13
  unsigned __int16 v9; // r14
  __int64 v10; // rax
  NTSTATUS result; // eax
  _BYTE *v12; // r8
  unsigned int v13; // edi
  unsigned int v14; // r15d
  __int64 v15; // [rsp+20h] [rbp-E0h]
  __int64 v16; // [rsp+20h] [rbp-E0h]
  _QWORD *v17; // [rsp+28h] [rbp-D8h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v19; // [rsp+80h] [rbp-80h]
  _QWORD v20[2]; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING v21; // [rsp+98h] [rbp-68h] BYREF
  char v22; // [rsp+A8h] [rbp-58h] BYREF
  char v23; // [rsp+C0h] [rbp-40h] BYREF

  *(_QWORD *)&DestinationString.Length = 0x1000000;
  DestinationString.Buffer = (wchar_t *)&v23;
  if ( a3 )
    *a3 = 0;
  v6 = *(unsigned __int8 **)(a1 + 2016);
  if ( v6 )
  {
    v7 = v6[5];
    v8 = v6[6];
    v9 = v6[7];
  }
  else
  {
    v9 = 0;
    v8 = 0;
    v7 = 0;
  }
  v19 = *(_WORD *)(a1 + 2004);
  if ( (*(_DWORD *)(a1 + 2472) & 0x20) != 0 )
  {
    v10 = *(_QWORD *)(a1 + 2504);
    if ( *(_BYTE *)(v10 + 12) )
    {
      if ( *(_BYTE *)(v10 + 4) )
      {
        result = RtlUnicodeStringPrintf(&DestinationString, L"USB\\MS_COMP_%.8S&MS_SUBCOMP_%.8S");
        if ( result < 0 )
          return result;
        result = HUBID_AssignIDString((const void **)&DestinationString, 2, a2, (__int64)a3);
        if ( result < 0 )
          return result;
      }
    }
    v12 = (_BYTE *)(*(_QWORD *)(a1 + 2504) + 4LL);
  }
  else
  {
    v12 = *(_BYTE **)(a1 + 2112);
    if ( !v12 )
      goto LABEL_20;
    if ( v12[26] )
    {
      result = RtlUnicodeStringPrintf(&DestinationString, L"USB\\MS_COMP_%.8S&MS_SUBCOMP_%.8S", v12 + 18, v12 + 26);
      if ( result < 0 )
        return result;
      result = HUBID_AssignIDString((const void **)&DestinationString, 2, a2, (__int64)a3);
      if ( result < 0 )
        return result;
    }
    v12 = (_BYTE *)(*(_QWORD *)(a1 + 2112) + 18LL);
  }
  if ( *v12 )
  {
    result = RtlUnicodeStringPrintf(&DestinationString, L"USB\\MS_COMP_%.8S");
    if ( result < 0 )
      return result;
    result = HUBID_AssignIDString((const void **)&DestinationString, 2, a2, (__int64)a3);
    if ( result < 0 )
      return result;
  }
LABEL_20:
  if ( v7 == 1 && (v9 & 0xFFDF) == 0 && (*(_DWORD *)(a1 + 1652) & 0x1000000) != 0 )
  {
    v20[0] = 0x100000;
    v20[1] = &v22;
    v21 = 0;
    HUBMISC_GenerateControllerSuffix((_QWORD *)a1, (__int64)v20, (int)v12);
    if ( !LOWORD(v20[0]) )
    {
LABEL_27:
      if ( v21.Buffer )
        ExFreePoolWithTag(v21.Buffer, 0x64334855u);
      goto LABEL_29;
    }
    v21.Buffer = (wchar_t *)ExAllocatePool2(64, 192, 1681082453);
    if ( v21.Buffer )
    {
      v17 = v20;
      v21.MaximumLength = 192;
      if ( RtlUnicodeStringPrintf(
             &v21,
             L"USB\\Class_%02X&Subclass_%02X&Prot_%02X&%wZ%cUSB\\Class_%02X&Subclass_%02X&%wZ%cUSB\\Class_%02X&%wZ") >= 0 )
        HUBID_AssignIDString((const void **)&v21, 2, a2, (__int64)a3);
      goto LABEL_27;
    }
  }
LABEL_29:
  v13 = v7;
  v14 = v19;
  LODWORD(v17) = v9;
  result = RtlUnicodeStringPrintf(
             &DestinationString,
             L"USB\\COMPAT_VID_%04X&Class_%02X&SubClass_%02X&Prot_%02X",
             v19,
             v13,
             v8,
             v17);
  if ( result >= 0 )
  {
    result = HUBID_AssignIDString((const void **)&DestinationString, 2, a2, (__int64)a3);
    if ( result >= 0 )
    {
      LODWORD(v15) = v8;
      result = RtlUnicodeStringPrintf(
                 &DestinationString,
                 L"USB\\COMPAT_VID_%04X&Class_%02X&SubClass_%02X",
                 v14,
                 v13,
                 v15);
      if ( result >= 0 )
      {
        result = HUBID_AssignIDString((const void **)&DestinationString, 2, a2, (__int64)a3);
        if ( result >= 0 )
        {
          result = RtlUnicodeStringPrintf(&DestinationString, L"USB\\COMPAT_VID_%04X&Class_%02X", v14, v13);
          if ( result >= 0 )
          {
            result = HUBID_AssignIDString((const void **)&DestinationString, 2, a2, (__int64)a3);
            if ( result >= 0 )
            {
              LODWORD(v16) = v9;
              result = RtlUnicodeStringPrintf(
                         &DestinationString,
                         L"USB\\Class_%02X&SubClass_%02X&Prot_%02X",
                         v13,
                         v8,
                         v16);
              if ( result >= 0 )
              {
                result = HUBID_AssignIDString((const void **)&DestinationString, 2, a2, (__int64)a3);
                if ( result >= 0 )
                {
                  result = RtlUnicodeStringPrintf(&DestinationString, L"USB\\Class_%02X&SubClass_%02X", v13, v8);
                  if ( result >= 0 )
                  {
                    result = HUBID_AssignIDString((const void **)&DestinationString, 2, a2, (__int64)a3);
                    if ( result >= 0 )
                    {
                      result = RtlUnicodeStringPrintf(&DestinationString, L"USB\\Class_%02X", v13);
                      if ( result >= 0 )
                        return HUBID_AssignIDString((const void **)&DestinationString, 2, a2, (__int64)a3);
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
0x14001dce0  mov     [rsp-8+arg_18], rbx
0x14001dce5  push    rbp
0x14001dce6  push    rsi
0x14001dce7  push    rdi
0x14001dce8  push    r12
0x14001dcea  push    r13
0x14001dcec  push    r14
0x14001dcee  push    r15
0x14001dcf0  lea     rbp, [rsp-0D0h]
0x14001dcf8  sub     rsp, 1D0h
0x14001dcff  mov     rax, cs:__security_cookie
0x14001dd06  xor     rax, rsp
0x14001dd09  mov     [rbp+100h+var_40], rax
0x14001dd10  xor     r12d, r12d
0x14001dd13  mov     qword ptr [rsp+200h+DestinationString.Length], 1000000h
0x14001dd1c  lea     rax, [rbp+100h+var_140]
0x14001dd20  mov     rbx, r8
0x14001dd23  mov     [rsp+200h+DestinationString.Buffer], rax
0x14001dd28  mov     rsi, rdx
0x14001dd2b  mov     rdi, rcx
0x14001dd2e  test    r8, r8
0x14001dd31  jz      short loc_14001DD3A
0x14001dd33  xorps   xmm0, xmm0
0x14001dd36  movups  xmmword ptr [r8], xmm0
0x14001dd3a  mov     rax, [rcx+7E0h]
0x14001dd41  test    rax, rax
0x14001dd44  jz      short loc_14001DD57
0x14001dd46  movzx   r15d, byte ptr [rax+5]
0x14001dd4b  movzx   r13d, byte ptr [rax+6]
0x14001dd50  movzx   r14d, byte ptr [rax+7]
0x14001dd55  jmp     short loc_14001DD60
0x14001dd57  mov     r14d, r12d
0x14001dd5a  mov     r13d, r12d
0x14001dd5d  mov     r15d, r12d
0x14001dd60  movzx   eax, word ptr [rcx+7D4h]
0x14001dd67  mov     [rbp+100h+var_180], ax
0x14001dd6b  mov     eax, [rcx+9A8h]
0x14001dd71  test    al, 20h
0x14001dd73  jz      short loc_14001DDD1
0x14001dd75  mov     rax, [rcx+9C8h]
0x14001dd7c  lea     r9, [rax+0Ch]
0x14001dd80  cmp     [r9], r12b
0x14001dd83  jz      short loc_14001DDC4
0x14001dd85  lea     r8, [rax+4]
0x14001dd89  cmp     [r8], r12b
0x14001dd8c  jz      short loc_14001DDC4
0x14001dd8e  lea     rdx, aUsbMsComp8sMsS; "USB\\MS_COMP_%.8S&MS_SUBCOMP_%.8S"
0x14001dd95  lea     rcx, [rsp+200h+DestinationString]; DestinationString
0x14001dd9a  call    RtlUnicodeStringPrintf
0x14001dd9f  test    eax, eax
0x14001dda1  js      loc_14001E0F1
0x14001dda7  mov     r9, rbx
0x14001ddaa  lea     rcx, [rsp+200h+DestinationString]
0x14001ddaf  mov     r8, rsi
0x14001ddb2  mov     edx, 2
0x14001ddb7  call    HUBID_AssignIDString
0x14001ddbc  test    eax, eax
0x14001ddbe  js      loc_14001E0F1
0x14001ddc4  mov     r8, [rdi+9C8h]
0x14001ddcb  add     r8, 4
0x14001ddcf  jmp     short loc_14001DE30
0x14001ddd1  mov     r8, [rcx+840h]
0x14001ddd8  test    r8, r8
0x14001dddb  jz      loc_14001DE6B
0x14001dde1  cmp     [r8+1Ah], r12b
0x14001dde5  jz      short loc_14001DE25
0x14001dde7  lea     r9, [r8+1Ah]
0x14001ddeb  add     r8, 12h
0x14001ddef  lea     rdx, aUsbMsComp8sMsS; "USB\\MS_COMP_%.8S&MS_SUBCOMP_%.8S"
0x14001ddf6  lea     rcx, [rsp+200h+DestinationString]; DestinationString
0x14001ddfb  call    RtlUnicodeStringPrintf
0x14001de00  test    eax, eax
0x14001de02  js      loc_14001E0F1
0x14001de08  mov     r9, rbx
0x14001de0b  lea     rcx, [rsp+200h+DestinationString]
0x14001de10  mov     r8, rsi
0x14001de13  mov     edx, 2
0x14001de18  call    HUBID_AssignIDString
0x14001de1d  test    eax, eax
0x14001de1f  js      loc_14001E0F1
0x14001de25  mov     r8, [rdi+840h]
0x14001de2c  add     r8, 12h
0x14001de30  cmp     [r8], r12b
0x14001de33  jz      short loc_14001DE6B
0x14001de35  lea     rdx, aUsbMsComp8s; "USB\\MS_COMP_%.8S"
0x14001de3c  lea     rcx, [rsp+200h+DestinationString]; DestinationString
0x14001de41  call    RtlUnicodeStringPrintf
0x14001de46  test    eax, eax
0x14001de48  js      loc_14001E0F1
0x14001de4e  mov     r9, rbx
0x14001de51  lea     rcx, [rsp+200h+DestinationString]
0x14001de56  mov     r8, rsi
0x14001de59  mov     edx, 2
0x14001de5e  call    HUBID_AssignIDString
0x14001de63  test    eax, eax
0x14001de65  js      loc_14001E0F1
0x14001de6b  mov     eax, 1
0x14001de70  cmp     r15w, ax
0x14001de74  jnz     loc_14001DF89
0x14001de7a  mov     eax, 0FFDFh
0x14001de7f  test    ax, r14w
0x14001de83  jnz     loc_14001DF89
0x14001de89  test    dword ptr [rdi+674h], 1000000h
0x14001de93  jz      loc_14001DF89
0x14001de99  lea     rax, [rbp+100h+var_158]
0x14001de9d  xorps   xmm0, xmm0
0x14001dea0  movups  [rbp+100h+var_178], xmm0
0x14001dea4  mov     qword ptr [rbp+100h+var_178+8], rax
0x14001dea8  lea     rdx, [rbp+100h+var_178]
0x14001deac  mov     eax, 10h
0x14001deb1  xorps   xmm1, xmm1
0x14001deb4  mov     rcx, rdi
0x14001deb7  mov     word ptr [rbp+100h+var_178+2], ax
0x14001debb  movups  xmmword ptr [rbp+100h+var_168.Length], xmm1
0x14001debf  call    HUBMISC_GenerateControllerSuffix
0x14001dec4  mov     edi, 64334855h
0x14001dec9  cmp     word ptr [rbp+100h+var_178], r12w
0x14001dece  jz      loc_14001DF6F
0x14001ded4  mov     edx, 0C0h
0x14001ded9  mov     r8d, edi
0x14001dedc  lea     ecx, [rdx-80h]
0x14001dedf  call    cs:__imp_ExAllocatePool2
0x14001dee6  nop     dword ptr [rax+rax+00h]
0x14001deeb  mov     [rbp+100h+var_168.Buffer], rax
0x14001deef  test    rax, rax
0x14001def2  jz      loc_14001DF89
0x14001def8  mov     r8d, 1
0x14001defe  movzx   r9d, r13w
0x14001df02  mov     eax, 0C0h
0x14001df07  lea     rcx, [rbp+100h+var_178]
0x14001df0b  mov     [rsp+200h+var_1A0], rcx
0x14001df10  lea     rdx, aUsbClass02xSub; "USB\\Class_%02X&Subclass_%02X&Prot_%02X"...
0x14001df17  mov     [rsp+200h+var_1A8], r8d
0x14001df1c  lea     rcx, [rbp+100h+var_178]
0x14001df20  mov     [rsp+200h+var_1B0], r12
0x14001df25  mov     [rsp+200h+var_1B8], rcx
0x14001df2a  lea     rcx, [rbp+100h+var_178]
0x14001df2e  mov     [rsp+200h+var_1C0], r9d
0x14001df33  mov     [rsp+200h+var_1C8], r8d
0x14001df38  mov     [rsp+200h+var_1D0], r12
0x14001df3d  mov     [rsp+200h+var_1D8], rcx
0x14001df42  lea     rcx, [rbp+100h+var_168]; DestinationString
0x14001df46  mov     [rbp+100h+var_168.MaximumLength], ax
0x14001df4a  movzx   eax, r14w
0x14001df4e  mov     dword ptr [rsp+200h+var_1E0], eax
0x14001df52  call    RtlUnicodeStringPrintf
0x14001df57  test    eax, eax
0x14001df59  js      short loc_14001DF6F
0x14001df5b  mov     r9, rbx
0x14001df5e  lea     rcx, [rbp+100h+var_168]
0x14001df62  mov     r8, rsi
0x14001df65  mov     edx, 2
0x14001df6a  call    HUBID_AssignIDString
0x14001df6f  mov     rax, [rbp+100h+var_168.Buffer]
0x14001df73  test    rax, rax
0x14001df76  jz      short loc_14001DF89
0x14001df78  mov     edx, edi; Tag
0x14001df7a  mov     rcx, rax; P
0x14001df7d  call    cs:__imp_ExFreePoolWithTag
0x14001df84  nop     dword ptr [rax+rax+00h]
0x14001df89  movzx   edi, r15w
0x14001df8d  lea     rdx, aUsbCompatVid04_0; "USB\\COMPAT_VID_%04X&Class_%02X&SubClas"...
0x14001df94  movzx   r15d, [rbp+100h+var_180]
0x14001df99  lea     rcx, [rsp+200h+DestinationString]; DestinationString
0x14001df9e  movzx   r12d, r14w
0x14001dfa2  mov     r8d, r15d
0x14001dfa5  movzx   r14d, r13w
0x14001dfa9  mov     r9d, edi
0x14001dfac  mov     dword ptr [rsp+200h+var_1D8], r12d
0x14001dfb1  mov     dword ptr [rsp+200h+var_1E0], r14d
0x14001dfb6  call    RtlUnicodeStringPrintf
0x14001dfbb  test    eax, eax
0x14001dfbd  js      loc_14001E0F1
0x14001dfc3  mov     r13d, 2
0x14001dfc9  lea     rcx, [rsp+200h+DestinationString]
0x14001dfce  mov     edx, r13d
0x14001dfd1  mov     r9, rbx
0x14001dfd4  mov     r8, rsi
0x14001dfd7  call    HUBID_AssignIDString
0x14001dfdc  test    eax, eax
0x14001dfde  js      loc_14001E0F1
0x14001dfe4  mov     r9d, edi
0x14001dfe7  mov     dword ptr [rsp+200h+var_1E0], r14d
0x14001dfec  mov     r8d, r15d
0x14001dfef  lea     rdx, aUsbCompatVid04_2; "USB\\COMPAT_VID_%04X&Class_%02X&SubClas"...
0x14001dff6  lea     rcx, [rsp+200h+DestinationString]; DestinationString
0x14001dffb  call    RtlUnicodeStringPrintf
0x14001e000  test    eax, eax
0x14001e002  js      loc_14001E0F1
0x14001e008  mov     r9, rbx
0x14001e00b  lea     rcx, [rsp+200h+DestinationString]
0x14001e010  mov     r8, rsi
0x14001e013  mov     edx, r13d
0x14001e016  call    HUBID_AssignIDString
0x14001e01b  test    eax, eax
0x14001e01d  js      loc_14001E0F1
0x14001e023  mov     r9d, edi
0x14001e026  lea     rdx, aUsbCompatVid04_3; "USB\\COMPAT_VID_%04X&Class_%02X"
0x14001e02d  mov     r8d, r15d
0x14001e030  lea     rcx, [rsp+200h+DestinationString]; DestinationString
0x14001e035  call    RtlUnicodeStringPrintf
0x14001e03a  test    eax, eax
0x14001e03c  js      loc_14001E0F1
0x14001e042  mov     r9, rbx
0x14001e045  lea     rcx, [rsp+200h+DestinationString]
0x14001e04a  mov     r8, rsi
0x14001e04d  mov     edx, r13d
0x14001e050  call    HUBID_AssignIDString
0x14001e055  test    eax, eax
0x14001e057  js      loc_14001E0F1
0x14001e05d  mov     r9d, r14d
0x14001e060  mov     dword ptr [rsp+200h+var_1E0], r12d
0x14001e065  mov     r8d, edi
0x14001e068  lea     rdx, aUsbClass02xSub_0; "USB\\Class_%02X&SubClass_%02X&Prot_%02X"
0x14001e06f  lea     rcx, [rsp+200h+DestinationString]; DestinationString
0x14001e074  call    RtlUnicodeStringPrintf
0x14001e079  test    eax, eax
0x14001e07b  js      short loc_14001E0F1
0x14001e07d  mov     r9, rbx
0x14001e080  lea     rcx, [rsp+200h+DestinationString]
0x14001e085  mov     r8, rsi
0x14001e088  mov     edx, r13d
0x14001e08b  call    HUBID_AssignIDString
0x14001e090  test    eax, eax
0x14001e092  js      short loc_14001E0F1
0x14001e094  mov     r9d, r14d
0x14001e097  lea     rdx, aUsbClass02xSub_1; "USB\\Class_%02X&SubClass_%02X"
0x14001e09e  mov     r8d, edi
0x14001e0a1  lea     rcx, [rsp+200h+DestinationString]; DestinationString
0x14001e0a6  call    RtlUnicodeStringPrintf
0x14001e0ab  test    eax, eax
0x14001e0ad  js      short loc_14001E0F1
0x14001e0af  mov     r9, rbx
0x14001e0b2  lea     rcx, [rsp+200h+DestinationString]
0x14001e0b7  mov     r8, rsi
0x14001e0ba  mov     edx, r13d
0x14001e0bd  call    HUBID_AssignIDString
0x14001e0c2  test    eax, eax
0x14001e0c4  js      short loc_14001E0F1
0x14001e0c6  mov     r8d, edi
0x14001e0c9  lea     rdx, aUsbClass02x; "USB\\Class_%02X"
0x14001e0d0  lea     rcx, [rsp+200h+DestinationString]; DestinationString
0x14001e0d5  call    RtlUnicodeStringPrintf
0x14001e0da  test    eax, eax
0x14001e0dc  js      short loc_14001E0F1
0x14001e0de  mov     r9, rbx
0x14001e0e1  lea     rcx, [rsp+200h+DestinationString]
0x14001e0e6  mov     r8, rsi
0x14001e0e9  mov     edx, r13d
0x14001e0ec  call    HUBID_AssignIDString
0x14001e0f1  mov     rcx, [rbp+100h+var_40]
0x14001e0f8  xor     rcx, rsp; StackCookie
0x14001e0fb  call    __security_check_cookie
0x14001e100  mov     rbx, [rsp+200h+arg_18]
0x14001e108  add     rsp, 1D0h
0x14001e10f  pop     r15
0x14001e111  pop     r14
0x14001e113  pop     r13
0x14001e115  pop     r12
0x14001e117  pop     rdi
0x14001e118  pop     rsi
0x14001e119  pop     rbp
0x14001e11a  retn
```
