# HUBPDO_ValidateConfigurationDescriptor

- ea: `0x14001b804`
- end: `0x14001ba01`
- name: `HUBPDO_ValidateConfigurationDescriptor`
- size: `509`
- prototype: `__int64 __fastcall(__int64, char *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14001ba08`

## callees

- `0x1400025a4`
- `0x1400067ac`
- `0x14000686c`
- `0x14001b804`
- `0x14003cce8`
- `0x140045570`

## pseudocode

```c
__int64 __fastcall HUBPDO_ValidateConfigurationDescriptor(__int64 a1, char *a2, unsigned int a3)
{
  __int64 v6; // rax
  int v7; // edx
  __int16 v8; // cx
  int v9; // ecx
  bool v10; // zf
  char v11; // r8
  __int64 v12; // rcx
  int v14; // edx
  unsigned int v15; // ebx
  _WORD v17[2]; // [rsp+40h] [rbp-19h] BYREF
  int v18; // [rsp+44h] [rbp-15h]
  __int64 v19; // [rsp+48h] [rbp-11h]
  int v20; // [rsp+50h] [rbp-9h]
  int v21; // [rsp+54h] [rbp-5h]
  void (__fastcall *v22)(__int64, ULONG, __int64, __int64); // [rsp+58h] [rbp-1h]
  void (__fastcall *v23)(__int64, ULONG, __int64, __int64); // [rsp+60h] [rbp+7h]
  __int64 v24; // [rsp+68h] [rbp+Fh]
  _BOOL8 v25; // [rsp+70h] [rbp+17h]

  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  v8 = *(_WORD *)(a1 + 1998);
  v19 = 0;
  v17[0] = v8;
  v18 = *(_DWORD *)(a1 + 172);
  v9 = *(_DWORD *)(v6 + 4);
  v25 = 0;
  *(_WORD *)((char *)&v19 + 5) = (v9 & 0x20) != 0;
  v17[1] = 0;
  HIBYTE(v19) = (v9 & 0x2000) != 0;
  v10 = (*(_DWORD *)(a1 + 1652) & 0x200000) == 0;
  BYTE4(v19) = (v9 & 0x4000) != 0;
  v21 = 0;
  v11 = a2[1];
  v25 = !v10;
  v12 = *(_QWORD *)(a1 + 8);
  v24 = a1;
  v20 = *(_DWORD *)(v12 + 220);
  v22 = HUBMISC_LogDescriptorValidationErrorForDevice;
  v23 = HUBMISC_LogDescriptorValidationWarningForDevice;
  if ( v11 != 2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_c(
        *(_QWORD *)(v12 + 1432),
        v7,
        5,
        24,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        v11);
    }
    return (unsigned int)-1073737984;
  }
  v14 = (unsigned __int8)*a2;
  if ( (unsigned __int8)v14 < 9u )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(v12 + 1432),
        v14,
        5,
        25,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
        *a2,
        9);
    }
    return (unsigned int)-1073737984;
  }
  if ( !*((_WORD *)a2 + 1) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(v12 + 1432), v14, 5, 26, (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
    }
    return (unsigned int)-1073737984;
  }
  v15 = 0;
  if ( !HUBDESC_ValidateConfigurationDescriptorSet(
          (__int64)a2,
          a3,
          (__int64)v17,
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
          0) )
    return (unsigned int)-1073737984;
  return v15;
}

```

## disassembly

```asm
0x14001b804  push    rbp
0x14001b806  push    rbx
0x14001b807  push    rsi
0x14001b808  push    rdi
0x14001b809  push    r14
0x14001b80b  push    r15
0x14001b80d  lea     rbp, [rsp-2Fh]
0x14001b812  sub     rsp, 88h
0x14001b819  mov     rax, cs:WdfFunctions_01015
0x14001b820  mov     rsi, rcx
0x14001b823  mov     rcx, cs:WdfDriverGlobals
0x14001b82a  mov     r14d, r8d
0x14001b82d  mov     r8, cs:off_14006B2C0
0x14001b834  mov     rdi, rdx
0x14001b837  mov     rax, [rax+650h]
0x14001b83e  mov     rdx, [rcx]
0x14001b841  call    _guard_dispatch_icall
0x14001b846  movzx   ecx, word ptr [rsi+7CEh]
0x14001b84d  xor     r15d, r15d
0x14001b850  mov     [rbp+57h+var_68], r15
0x14001b854  mov     [rbp+57h+var_70], cx
0x14001b858  mov     ecx, [rsi+0ACh]
0x14001b85e  lea     r8d, [r15+1]
0x14001b862  mov     [rbp+57h+var_6C], ecx
0x14001b865  mov     ecx, [rax+4]
0x14001b868  test    cl, 20h
0x14001b86b  movzx   eax, byte ptr [rbp+57h+var_68+5]
0x14001b86f  cmovnz  eax, r8d
0x14001b873  mov     [rbp+57h+var_40], r15
0x14001b877  mov     byte ptr [rbp+57h+var_68+5], al
0x14001b87a  bt      ecx, 0Dh
0x14001b87e  movzx   eax, byte ptr [rbp+57h+var_68+7]
0x14001b882  cmovb   eax, r8d
0x14001b886  mov     [rbp+57h+var_6E], r15w
0x14001b88b  bt      ecx, 0Eh
0x14001b88f  mov     byte ptr [rbp+57h+var_68+7], al
0x14001b892  movzx   eax, byte ptr [rbp+57h+var_68+4]
0x14001b896  cmovb   eax, r8d
0x14001b89a  movzx   ecx, r15b
0x14001b89e  test    dword ptr [rsi+674h], 200000h
0x14001b8a8  mov     byte ptr [rbp+57h+var_68+4], al
0x14001b8ab  cmovnz  ecx, r8d
0x14001b8af  mov     [rbp+57h+var_5C], r15d
0x14001b8b3  mov     r8b, [rdi+1]
0x14001b8b7  mov     byte ptr [rbp+57h+var_40], cl
0x14001b8ba  mov     rcx, [rsi+8]
0x14001b8be  mov     [rbp+57h+var_48], rsi
0x14001b8c2  mov     eax, [rcx+0DCh]
0x14001b8c8  mov     [rbp+57h+var_60], eax
0x14001b8cb  lea     rax, HUBMISC_LogDescriptorValidationErrorForDevice
0x14001b8d2  mov     [rbp+57h+var_58], rax
0x14001b8d6  lea     rax, HUBMISC_LogDescriptorValidationWarningForDevice
0x14001b8dd  mov     [rbp+57h+var_50], rax
0x14001b8e1  cmp     r8b, 2
0x14001b8e5  jz      short loc_14001B928
0x14001b8e7  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b8ee  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b8f5  jz      short loc_14001B91E
0x14001b8f7  mov     rcx, [rcx+598h]
0x14001b8fe  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001b905  mov     byte ptr [rsp+0B0h+var_88], r8b
0x14001b90a  lea     r9d, [r15+18h]
0x14001b90e  lea     r8d, [r15+5]
0x14001b912  mov     [rsp+0B0h+var_90], rax
0x14001b917  mov     dl, 2
0x14001b919  call    WPP_RECORDER_SF_c
0x14001b91e  mov     ecx, 0C0000F00h
0x14001b923  jmp     loc_14001B9EE
0x14001b928  movzx   edx, byte ptr [rdi]
0x14001b92b  cmp     dl, 9
0x14001b92e  jnb     short loc_14001B972
0x14001b930  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b937  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b93e  jz      short loc_14001B91E
0x14001b940  mov     rcx, [rcx+598h]
0x14001b947  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001b94e  mov     r9d, 19h
0x14001b954  mov     [rsp+0B0h+var_80], 9
0x14001b95c  mov     [rsp+0B0h+var_88], edx
0x14001b960  mov     dl, 2
0x14001b962  mov     [rsp+0B0h+var_90], rax
0x14001b967  lea     r8d, [r9-14h]
0x14001b96b  call    WPP_RECORDER_SF_dD
0x14001b970  jmp     short loc_14001B91E
0x14001b972  cmp     [rdi+2], r15w
0x14001b977  jnz     short loc_14001B9B2
0x14001b979  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14001b980  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b987  jz      short loc_14001B91E
0x14001b989  mov     rcx, [rcx+598h]
0x14001b990  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001b997  mov     r9d, 1Ah
0x14001b99d  mov     [rsp+0B0h+var_90], rax
0x14001b9a2  mov     dl, 2
0x14001b9a4  lea     r8d, [r9-15h]
0x14001b9a8  call    WPP_RECORDER_SF_
0x14001b9ad  jmp     loc_14001B91E
0x14001b9b2  movzx   eax, word ptr [rdi+2]
0x14001b9b6  lea     r8, [rbp+57h+var_70]
0x14001b9ba  mov     r9, [rsi+8]
0x14001b9be  mov     ebx, r15d
0x14001b9c1  mov     [rbp+57h+arg_18], dl
0x14001b9c4  mov     edx, r14d
0x14001b9c7  mov     [rsp+0B0h+var_90], r15
0x14001b9cc  mov     cl, [rax+rdi-1]
0x14001b9d0  mov     r9, [r9+598h]
0x14001b9d7  mov     [rbp+57h+arg_18], cl
0x14001b9da  mov     rcx, rdi
0x14001b9dd  call    HUBDESC_ValidateConfigurationDescriptorSet
0x14001b9e2  mov     ecx, 0C0000F00h
0x14001b9e7  test    al, al
0x14001b9e9  cmovz   ebx, ecx
0x14001b9ec  mov     ecx, ebx
0x14001b9ee  mov     eax, ecx
0x14001b9f0  add     rsp, 88h
0x14001b9f7  pop     r15
0x14001b9f9  pop     r14
0x14001b9fb  pop     rdi
0x14001b9fc  pop     rsi
0x14001b9fd  pop     rbx
0x14001b9fe  pop     rbp
0x14001b9ff  retn
```
