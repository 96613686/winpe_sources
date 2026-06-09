# HUBID_BuildDeviceCompatibleID

- ea: `0x14001e6d0`
- end: `0x14001e919`
- name: `HUBID_BuildDeviceCompatibleID`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001e124`

## callees

- `0x14000f648`
- `0x14001dc30`
- `0x14001e6d0`
- `0x140045530`

## string_xrefs

- `0x14001e7dc`: `USB\COMPOSITE`
- `0x14001e800`: `USB\COMPAT_VID_%04X&DevClass_00&SubClass_00&Prot00`
- `0x14001e840`: `USB\COMPAT_VID_%04X&DevClass_00&SubClass_00`
- `0x14001e877`: `USB\COMPAT_VID_%04X&DevClass_00`

## pseudocode

```c
NTSTATUS __fastcall HUBID_BuildDeviceCompatibleID(__int64 a1, __int64 a2, _OWORD *a3)
{
  unsigned int v5; // esi
  NTSTATUS result; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v8[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v10[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v11[2]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v12[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v13[2]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v14[3]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v15; // [rsp+E0h] [rbp-20h]
  _OWORD v16[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v17; // [rsp+130h] [rbp+30h]
  char v18; // [rsp+140h] [rbp+40h] BYREF

  v16[0] = *(_OWORD *)L"USB\\DevClass_00&SubClass_00&Prot_00";
  v16[2] = *(_OWORD *)L"SubClass_00&Prot_00";
  v16[1] = *(_OWORD *)L"lass_00&SubClass_00&Prot_00";
  v17 = *(_QWORD *)L"_00";
  v16[3] = *(_OWORD *)L"_00&Prot_00";
  v8[1] = v16;
  v9[1] = v14;
  v10[1] = v13;
  v11[1] = v12;
  v8[0] = 4718662;
  v9[0] = 3670070;
  v10[0] = 2097182;
  v11[0] = 1835034;
  *(_QWORD *)&DestinationString.Length = 0x1000000;
  DestinationString.Buffer = (wchar_t *)&v18;
  v14[0] = *(_OWORD *)L"USB\\DevClass_00&SubClass_00";
  v14[1] = *(_OWORD *)L"lass_00&SubClass_00";
  v15 = *(_QWORD *)L"_00";
  v14[2] = *(_OWORD *)L"SubClass_00";
  v13[1] = *(_OWORD *)L"lass_00";
  v13[0] = *(_OWORD *)L"USB\\DevClass_00";
  v12[0] = *(_OWORD *)L"USB\\COMPOSITE";
  *(_OWORD *)((char *)v12 + 12) = *(_OWORD *)L"MPOSITE";
  if ( a3 )
    *a3 = 0;
  v5 = *(unsigned __int16 *)(a1 + 2004);
  result = RtlUnicodeStringPrintf(
             &DestinationString,
             L"USB\\COMPAT_VID_%04X&DevClass_00&SubClass_00&Prot00",
             *(unsigned __int16 *)(a1 + 2004));
  if ( result >= 0 )
  {
    result = HUBID_AssignIDString(&DestinationString, 2, a2, a3);
    if ( result >= 0 )
    {
      result = RtlUnicodeStringPrintf(&DestinationString, L"USB\\COMPAT_VID_%04X&DevClass_00&SubClass_00", v5);
      if ( result >= 0 )
      {
        result = HUBID_AssignIDString(&DestinationString, 2, a2, a3);
        if ( result >= 0 )
        {
          result = RtlUnicodeStringPrintf(&DestinationString, L"USB\\COMPAT_VID_%04X&DevClass_00", v5);
          if ( result >= 0 )
          {
            result = HUBID_AssignIDString(&DestinationString, 2, a2, a3);
            if ( result >= 0 )
            {
              result = HUBID_AssignIDString(v8, 2, a2, a3);
              if ( result >= 0 )
              {
                result = HUBID_AssignIDString(v9, 2, a2, a3);
                if ( result >= 0 )
                {
                  result = HUBID_AssignIDString(v10, 2, a2, a3);
                  if ( result >= 0 )
                    return HUBID_AssignIDString(v11, 2, a2, a3);
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
0x14001e6d0  push    rbp
0x14001e6d2  push    rbx
0x14001e6d3  push    rsi
0x14001e6d4  push    rdi
0x14001e6d5  push    r14
0x14001e6d7  lea     rbp, [rsp-150h]
0x14001e6df  sub     rsp, 250h
0x14001e6e6  mov     rax, cs:__security_cookie
0x14001e6ed  xor     rax, rsp
0x14001e6f0  mov     [rbp+170h+var_30], rax
0x14001e6f7  movaps  xmm0, xmmword ptr cs:aUsbDevclass00S_0; "USB\\DevClass_00&SubClass_00&Prot_00"
0x14001e6fe  lea     rax, [rbp+170h+var_180]
0x14001e702  movaps  xmm1, xmmword ptr cs:aUsbDevclass00S_0+10h; "lass_00&SubClass_00&Prot_00"
0x14001e709  mov     rbx, r8
0x14001e70c  movaps  [rbp+170h+var_180], xmm0
0x14001e710  mov     rdi, rdx
0x14001e713  movaps  xmm0, xmmword ptr cs:aUsbDevclass00S_0+20h; "SubClass_00&Prot_00"
0x14001e71a  movaps  [rbp+170h+var_160], xmm0
0x14001e71e  movsd   xmm0, qword ptr cs:aUsbDevclass00S_0+40h; "_00"
0x14001e726  movaps  [rbp+170h+var_170], xmm1
0x14001e72a  movaps  xmm1, xmmword ptr cs:aUsbDevclass00S_0+30h; "_00&Prot_00"
0x14001e731  movsd   [rbp+170h+var_140], xmm0
0x14001e736  movaps  [rbp+170h+var_150], xmm1
0x14001e73a  mov     [rsp+270h+var_238], rax
0x14001e73f  lea     rax, [rbp+170h+var_1C0]
0x14001e743  mov     [rsp+270h+var_228], rax
0x14001e748  lea     rax, [rbp+170h+var_1E0]
0x14001e74c  mov     [rsp+270h+var_218], rax
0x14001e751  lea     rax, [rsp+270h+var_200]
0x14001e756  mov     [rsp+270h+var_208], rax
0x14001e75b  lea     rax, [rbp+170h+var_130]
0x14001e75f  mov     [rsp+270h+var_240], 480046h
0x14001e768  mov     [rsp+270h+var_230], 380036h
0x14001e771  mov     [rsp+270h+var_220], 20001Eh
0x14001e77a  mov     [rsp+270h+var_210], 1C001Ah
0x14001e783  mov     qword ptr [rsp+270h+DestinationString.Length], 1000000h
0x14001e78c  mov     [rsp+270h+DestinationString.Buffer], rax
0x14001e791  movups  xmm0, xmmword ptr cs:aUsbDevclass00S; "USB\\DevClass_00&SubClass_00"
0x14001e798  movups  xmm1, xmmword ptr cs:aUsbDevclass00S+10h; "lass_00&SubClass_00"
0x14001e79f  movups  [rbp+170h+var_1C0], xmm0
0x14001e7a3  movups  xmm0, xmmword ptr cs:aUsbDevclass00S+20h; "SubClass_00"
0x14001e7aa  movups  [rbp+170h+var_1B0], xmm1
0x14001e7ae  movsd   xmm1, qword ptr cs:aUsbDevclass00S+30h; "_00"
0x14001e7b6  movsd   [rbp+170h+var_190], xmm1
0x14001e7bb  movups  xmm1, xmmword ptr cs:aUsbDevclass00+10h; "lass_00"
0x14001e7c2  movups  [rbp+170h+var_1A0], xmm0
0x14001e7c6  movups  xmm0, xmmword ptr cs:aUsbDevclass00; "USB\\DevClass_00"
0x14001e7cd  movups  [rbp+170h+var_1D0], xmm1
0x14001e7d1  movups  xmm1, xmmword ptr cs:aUsbComposite+0Ch; "MPOSITE"
0x14001e7d8  movups  [rbp+170h+var_1E0], xmm0
0x14001e7dc  movups  xmm0, xmmword ptr cs:aUsbComposite; "USB\\COMPOSITE"
0x14001e7e3  movups  xmmword ptr [rsp+270h+var_200], xmm0
0x14001e7e8  movups  xmmword ptr [rsp+270h+var_200+0Ch], xmm1
0x14001e7ed  test    r8, r8
0x14001e7f0  jz      short loc_14001E7F9
0x14001e7f2  xorps   xmm0, xmm0
0x14001e7f5  movups  xmmword ptr [r8], xmm0
0x14001e7f9  movzx   esi, word ptr [rcx+7D4h]
0x14001e800  lea     rdx, aUsbCompatVid04_4; "USB\\COMPAT_VID_%04X&DevClass_00&SubCla"...
0x14001e807  mov     r8d, esi
0x14001e80a  lea     rcx, [rsp+270h+DestinationString]; DestinationString
0x14001e80f  call    RtlUnicodeStringPrintf
0x14001e814  test    eax, eax
0x14001e816  js      loc_14001E8FB
0x14001e81c  mov     r14d, 2
0x14001e822  lea     rcx, [rsp+270h+DestinationString]
0x14001e827  mov     edx, r14d
0x14001e82a  mov     r9, rbx
0x14001e82d  mov     r8, rdi
0x14001e830  call    HUBID_AssignIDString
0x14001e835  test    eax, eax
0x14001e837  js      loc_14001E8FB
0x14001e83d  mov     r8d, esi
0x14001e840  lea     rdx, aUsbCompatVid04; "USB\\COMPAT_VID_%04X&DevClass_00&SubCla"...
0x14001e847  lea     rcx, [rsp+270h+DestinationString]; DestinationString
0x14001e84c  call    RtlUnicodeStringPrintf
0x14001e851  test    eax, eax
0x14001e853  js      loc_14001E8FB
0x14001e859  mov     r9, rbx
0x14001e85c  lea     rcx, [rsp+270h+DestinationString]
0x14001e861  mov     r8, rdi
0x14001e864  mov     edx, r14d
0x14001e867  call    HUBID_AssignIDString
0x14001e86c  test    eax, eax
0x14001e86e  js      loc_14001E8FB
0x14001e874  mov     r8d, esi
0x14001e877  lea     rdx, aUsbCompatVid04_1; "USB\\COMPAT_VID_%04X&DevClass_00"
0x14001e87e  lea     rcx, [rsp+270h+DestinationString]; DestinationString
0x14001e883  call    RtlUnicodeStringPrintf
0x14001e888  test    eax, eax
0x14001e88a  js      short loc_14001E8FB
0x14001e88c  mov     r9, rbx
0x14001e88f  lea     rcx, [rsp+270h+DestinationString]
0x14001e894  mov     r8, rdi
0x14001e897  mov     edx, r14d
0x14001e89a  call    HUBID_AssignIDString
0x14001e89f  test    eax, eax
0x14001e8a1  js      short loc_14001E8FB
0x14001e8a3  mov     r9, rbx
0x14001e8a6  lea     rcx, [rsp+270h+var_240]
0x14001e8ab  mov     r8, rdi
0x14001e8ae  mov     edx, r14d
0x14001e8b1  call    HUBID_AssignIDString
0x14001e8b6  test    eax, eax
0x14001e8b8  js      short loc_14001E8FB
0x14001e8ba  mov     r9, rbx
0x14001e8bd  lea     rcx, [rsp+270h+var_230]
0x14001e8c2  mov     r8, rdi
0x14001e8c5  mov     edx, r14d
0x14001e8c8  call    HUBID_AssignIDString
0x14001e8cd  test    eax, eax
0x14001e8cf  js      short loc_14001E8FB
0x14001e8d1  mov     r9, rbx
0x14001e8d4  lea     rcx, [rsp+270h+var_220]
0x14001e8d9  mov     r8, rdi
0x14001e8dc  mov     edx, r14d
0x14001e8df  call    HUBID_AssignIDString
0x14001e8e4  test    eax, eax
0x14001e8e6  js      short loc_14001E8FB
0x14001e8e8  mov     r9, rbx
0x14001e8eb  lea     rcx, [rsp+270h+var_210]
0x14001e8f0  mov     r8, rdi
0x14001e8f3  mov     edx, r14d
0x14001e8f6  call    HUBID_AssignIDString
0x14001e8fb  mov     rcx, [rbp+170h+var_30]
0x14001e902  xor     rcx, rsp; StackCookie
0x14001e905  call    __security_check_cookie
0x14001e90a  add     rsp, 250h
0x14001e911  pop     r14
0x14001e913  pop     rdi
0x14001e914  pop     rsi
0x14001e915  pop     rbx
0x14001e916  pop     rbp
0x14001e917  retn
```
