# HUBACPI_EvaluateDSD

- ea: `0x14008be5c`
- end: `0x14008c1dc`
- name: `HUBACPI_EvaluateDSD`
- size: `896`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int16, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14008c9fc`

## callees

- `0x1400025a4`
- `0x1400067ac`
- `0x14000f648`
- `0x140045506`
- `0x140045570`
- `0x14008ba0c`
- `0x14008be5c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14008c1b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c1b9`
- `ntoskrnl!RtlCompareMemory` at `0x14008bfa9`
- `ntoskrnl!RtlCompareMemory` at `0x14008bfa9`
- `ntoskrnl!ExAllocatePool2` at `0x14008c0f9`
- `ntoskrnl!ExAllocatePool2` at `0x14008c0f9`

## pseudocode

```c
__int64 __fastcall HUBACPI_EvaluateDSD(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int16 a6,
        __int64 a7)
{
  int v8; // eax
  int v9; // edx
  NTSTATUS v10; // esi
  __int64 v11; // rax
  int v12; // edx
  __int64 v13; // r14
  int v14; // r9d
  int v15; // r8d
  unsigned int v16; // edi
  __int64 v17; // rbx
  __int64 v18; // rcx
  unsigned __int64 v19; // r15
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rdi
  __int64 v23; // rax
  unsigned __int16 v24; // di
  unsigned __int64 v25; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-51h] BYREF
  __int128 v28; // [rsp+50h] [rbp-41h] BYREF
  __int128 v29; // [rsp+60h] [rbp-31h]
  __int128 v30; // [rsp+70h] [rbp-21h]
  __int64 v31; // [rsp+80h] [rbp-11h]

  *(_QWORD *)&DestinationString.Length = 0;
  LODWORD(v31) = 0;
  v28 = 0;
  DestinationString.Buffer = 0;
  v29 = 0;
  v30 = 0;
  v8 = HUBACPI_EvalAcpiMethodEx(a1, a2, 1146307679, a5);
  v10 = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -1073741772 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_dD(
        *(_QWORD *)(a1 + 2536),
        v9,
        3,
        29,
        (__int64)WPP_87abda6c49cb3f06b0a228f67f220255_Traceguids,
        a6,
        v8);
    }
    goto LABEL_43;
  }
  v10 = -1073741823;
  v11 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 1552))(
          WdfDriverGlobals,
          a5,
          0);
  v13 = v11;
  if ( !*(_DWORD *)(v11 + 8) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = 30;
      goto LABEL_8;
    }
    goto LABEL_43;
  }
  v16 = 0;
  v17 = v11 + 12;
  while ( 1 )
  {
    if ( (v16 & 1) == 0
      && *(_DWORD *)v17 == 1048578
      && RtlCompareMemory((const void *)(v17 + 4), ACPI_DEVICE_PROPERTIES_DSD_GUID, 0x10u) == 16 )
    {
      v18 = 4;
      if ( *(_WORD *)(v17 + 2) >= 4u )
        v18 = *(unsigned __int16 *)(v17 + 2);
      v19 = v17 + v18 + *(unsigned __int16 *)(v18 + v17 + 6) + 4LL;
      if ( *(_WORD *)(v18 + v17 + 4) == 3 )
        break;
    }
    v20 = *(unsigned __int16 *)(v17 + 2);
    if ( (unsigned __int16)v20 < 4u )
      v20 = 4;
    ++v16;
    v17 += v20 + 4;
    if ( v16 >= *(_DWORD *)(v13 + 8) )
      goto LABEL_43;
  }
  v21 = v18 + v17 + 8;
  if ( v21 + 8 >= v19 )
    goto LABEL_43;
  while ( 1 )
  {
    v22 = *(unsigned __int16 *)(v21 + 2);
    if ( *(_WORD *)v21 == 3 && (unsigned __int16)v22 >= 0x10u )
      break;
    if ( (unsigned __int16)v22 >= 4u )
      goto LABEL_29;
    v23 = 4;
LABEL_30:
    v21 += v23 + 4;
    if ( v21 + 8 >= v19 )
      goto LABEL_43;
  }
  if ( *(_WORD *)(v21 + 4) != 1
    || *(_WORD *)(v21 + 6) != 20
    || strncmp_0((const char *)(v21 + 8), "usb4-host-interface", 0x13u) )
  {
LABEL_29:
    v23 = v22;
    goto LABEL_30;
  }
  if ( v21 + 36 <= v19 )
  {
    if ( *(_WORD *)(v21 + 28) == 1 )
    {
      v24 = 2 * *(_WORD *)(v21 + 30);
      DestinationString.Buffer = (wchar_t *)ExAllocatePool2(256, v24, 1882409045);
      if ( DestinationString.Buffer )
      {
        DestinationString.MaximumLength = v24;
        DestinationString.Length = 0;
        v10 = RtlUnicodeStringPrintf(&DestinationString, L"%S", v21 + 32);
        if ( v10 >= 0 )
        {
          v31 = 0;
          v25 = *(_QWORD *)(a1 + 16);
          *(_QWORD *)&v29 = 0;
          *((_QWORD *)&v29 + 1) = 0x100000001LL;
          v30 = v25;
          v28 = 0;
          LODWORD(v28) = 56;
          v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct _UNICODE_STRING *, __int128 *, __int64))(WdfFunctions_01015 + 2464))(
                  WdfDriverGlobals,
                  &DestinationString,
                  &v28,
                  a7);
        }
        goto LABEL_43;
      }
      v10 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_43;
      v14 = 33;
      v15 = 3;
    }
    else
    {
      v10 = -1072431096;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_43;
      v14 = 32;
LABEL_8:
      v15 = 6;
    }
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(a1 + 2536), v12, v15, v14, (__int64)WPP_87abda6c49cb3f06b0a228f67f220255_Traceguids);
    goto LABEL_43;
  }
  v10 = -1072431099;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = 31;
    goto LABEL_8;
  }
LABEL_43:
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x70334855u);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14008be5c  push    rbp
0x14008be5e  push    rbx
0x14008be5f  push    rsi
0x14008be60  push    rdi
0x14008be61  push    r12
0x14008be63  push    r13
0x14008be65  push    r14
0x14008be67  push    r15
0x14008be69  lea     rbp, [rsp-7]
0x14008be6e  sub     rsp, 98h
0x14008be75  mov     r9, [rbp+3Fh+arg_20]
0x14008be79  xorps   xmm0, xmm0
0x14008be7c  xor     eax, eax
0x14008be7e  mov     qword ptr [rbp+3Fh+DestinationString.Length], 0
0x14008be86  mov     r8d, 4453445Fh
0x14008be8c  mov     dword ptr [rbp+3Fh+var_50], eax
0x14008be8f  movups  [rbp+3Fh+var_80], xmm0
0x14008be93  mov     [rbp+3Fh+DestinationString.Buffer], rax
0x14008be97  mov     r13, rcx
0x14008be9a  movups  [rbp+3Fh+var_70], xmm0
0x14008be9e  movups  [rbp+3Fh+var_60], xmm0
0x14008bea2  call    HUBACPI_EvalAcpiMethodEx
0x14008bea7  mov     esi, eax
0x14008bea9  test    eax, eax
0x14008beab  jns     short loc_14008BF01
0x14008bead  cmp     eax, 0C0000034h
0x14008beb2  jz      loc_14008C1AB
0x14008beb8  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008bebf  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008bec6  jz      loc_14008C1AB
0x14008becc  movzx   ecx, [rbp+3Fh+arg_28]
0x14008bed0  mov     r9d, 1Dh
0x14008bed6  mov     [rsp+0D0h+var_A0], eax
0x14008beda  mov     dl, 2
0x14008bedc  mov     [rsp+0D0h+var_A8], ecx
0x14008bee0  lea     rax, WPP_87abda6c49cb3f06b0a228f67f220255_Traceguids
0x14008bee7  mov     rcx, [r13+9E8h]
0x14008beee  lea     r8d, [r9-1Ah]
0x14008bef2  mov     [rsp+0D0h+var_B0], rax
0x14008bef7  call    WPP_RECORDER_SF_dD
0x14008befc  jmp     loc_14008C1AB
0x14008bf01  mov     rax, cs:WdfFunctions_01015
0x14008bf08  xor     r8d, r8d
0x14008bf0b  mov     rdx, [rbp+3Fh+arg_20]
0x14008bf0f  mov     esi, 0C0000001h
0x14008bf14  mov     rcx, cs:WdfDriverGlobals
0x14008bf1b  mov     rax, [rax+610h]
0x14008bf22  call    _guard_dispatch_icall
0x14008bf27  mov     r14, rax
0x14008bf2a  mov     ecx, [rax+8]
0x14008bf2d  test    ecx, ecx
0x14008bf2f  jnz     short loc_14008BF70
0x14008bf31  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008bf38  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008bf3f  jz      loc_14008C1AB
0x14008bf45  mov     r9d, 1Eh
0x14008bf4b  mov     r8d, 6
0x14008bf51  mov     rcx, [r13+9E8h]
0x14008bf58  lea     rax, WPP_87abda6c49cb3f06b0a228f67f220255_Traceguids
0x14008bf5f  mov     dl, 2
0x14008bf61  mov     [rsp+0D0h+var_B0], rax
0x14008bf66  call    WPP_RECORDER_SF_
0x14008bf6b  jmp     loc_14008C1AB
0x14008bf70  xor     edi, edi
0x14008bf72  lea     rbx, [rax+0Ch]
0x14008bf76  test    ecx, ecx
0x14008bf78  jz      loc_14008C1AB
0x14008bf7e  lea     ecx, [rdi+1]
0x14008bf81  lea     edx, [rdi+4]
0x14008bf84  lea     r12d, [rdi+3]
0x14008bf88  lea     r8d, [rdi+10h]; Length
0x14008bf8c  test    cl, dil
0x14008bf8f  jnz     short loc_14008BFED
0x14008bf91  cmp     word ptr [rbx], 2
0x14008bf95  jnz     short loc_14008BFED
0x14008bf97  cmp     [rbx+2], r8w
0x14008bf9c  jnz     short loc_14008BFED
0x14008bf9e  lea     rcx, [rbx+4]; Source1
0x14008bfa2  lea     rdx, ACPI_DEVICE_PROPERTIES_DSD_GUID; Source2
0x14008bfa9  call    cs:__imp_RtlCompareMemory
0x14008bfb0  nop     dword ptr [rax+rax+00h]
0x14008bfb5  mov     r8d, 10h
0x14008bfbb  lea     edx, [r8-0Ch]
0x14008bfbf  cmp     rax, r8
0x14008bfc2  jnz     short loc_14008BFE8
0x14008bfc4  movzx   eax, word ptr [rbx+2]
0x14008bfc8  mov     ecx, edx
0x14008bfca  cmp     dx, ax
0x14008bfcd  ja      short loc_14008BFD1
0x14008bfcf  mov     ecx, eax
0x14008bfd1  movzx   r15d, word ptr [rcx+rbx+6]
0x14008bfd7  add     r15, rdx
0x14008bfda  add     r15, rcx
0x14008bfdd  add     r15, rbx
0x14008bfe0  cmp     [rcx+rbx+4], r12w
0x14008bfe6  jz      short loc_14008C00D
0x14008bfe8  mov     ecx, 1
0x14008bfed  movzx   eax, word ptr [rbx+2]
0x14008bff1  cmp     dx, ax
0x14008bff4  jbe     short loc_14008BFF9
0x14008bff6  mov     rax, rdx
0x14008bff9  add     rbx, 4
0x14008bffd  add     edi, ecx
0x14008bfff  add     rbx, rax
0x14008c002  cmp     edi, [r14+8]
0x14008c006  jb      short loc_14008BF8C
0x14008c008  jmp     loc_14008C1AB
0x14008c00d  add     rbx, 8
0x14008c011  add     rbx, rcx
0x14008c014  lea     rax, [rbx+8]
0x14008c018  cmp     rax, r15
0x14008c01b  jnb     loc_14008C1AB
0x14008c021  mov     r14d, 1
0x14008c027  movzx   edi, word ptr [rbx+2]
0x14008c02b  cmp     [rbx], r12w
0x14008c02f  jz      short loc_14008C03B
0x14008c031  cmp     dx, di
0x14008c034  jbe     short loc_14008C072
0x14008c036  mov     rax, rdx
0x14008c039  jmp     short loc_14008C075
0x14008c03b  cmp     di, r8w
0x14008c03f  jb      short loc_14008C031
0x14008c041  cmp     [rbx+4], r14w
0x14008c046  jnz     short loc_14008C072
0x14008c048  cmp     word ptr [rbx+6], 14h
0x14008c04d  jnz     short loc_14008C072
0x14008c04f  lea     rcx, [rbx+8]; Str1
0x14008c053  mov     r8d, 13h; MaxCount
0x14008c059  lea     rdx, aUsb4HostInterf_0; "usb4-host-interface"
0x14008c060  call    strncmp_0
0x14008c065  test    eax, eax
0x14008c067  jz      short loc_14008C08A
0x14008c069  mov     edx, 4
0x14008c06e  lea     r8d, [rdx+0Ch]
0x14008c072  mov     rax, rdi
0x14008c075  add     rax, 4
0x14008c079  add     rbx, rax
0x14008c07c  lea     rax, [rbx+8]
0x14008c080  cmp     rax, r15
0x14008c083  jb      short loc_14008C027
0x14008c085  jmp     loc_14008C1AB
0x14008c08a  lea     rax, [rbx+24h]
0x14008c08e  cmp     rax, r15
0x14008c091  jbe     short loc_14008C0B7
0x14008c093  mov     esi, 0C0140005h
0x14008c098  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008c09f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008c0a6  jz      loc_14008C1AB
0x14008c0ac  mov     r9d, 1Fh
0x14008c0b2  jmp     loc_14008BF4B
0x14008c0b7  cmp     [rbx+1Ch], r14w
0x14008c0bc  jz      short loc_14008C0E2
0x14008c0be  mov     esi, 0C0140008h
0x14008c0c3  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008c0ca  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008c0d1  jz      loc_14008C1AB
0x14008c0d7  mov     r9d, 20h ; ' '
0x14008c0dd  jmp     loc_14008BF4B
0x14008c0e2  movzx   eax, word ptr [rbx+1Eh]
0x14008c0e6  mov     ecx, 100h
0x14008c0eb  add     ax, ax
0x14008c0ee  mov     r8d, 70334855h
0x14008c0f4  movzx   edi, ax
0x14008c0f7  mov     edx, edi
0x14008c0f9  call    cs:__imp_ExAllocatePool2
0x14008c100  nop     dword ptr [rax+rax+00h]
0x14008c105  mov     [rbp+3Fh+DestinationString.Buffer], rax
0x14008c109  test    rax, rax
0x14008c10c  jnz     short loc_14008C133
0x14008c10e  mov     esi, 0C000009Ah
0x14008c113  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008c11a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008c121  jz      loc_14008C1AB
0x14008c127  lea     r9d, [rax+21h]
0x14008c12b  mov     r8d, r12d
0x14008c12e  jmp     loc_14008BF51
0x14008c133  xor     eax, eax
0x14008c135  mov     [rbp+3Fh+DestinationString.MaximumLength], di
0x14008c139  lea     r8, [rbx+20h]
0x14008c13d  mov     [rbp+3Fh+DestinationString.Length], ax
0x14008c141  lea     rdx, aS; "%S"
0x14008c148  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x14008c14c  call    RtlUnicodeStringPrintf
0x14008c151  mov     esi, eax
0x14008c153  test    eax, eax
0x14008c155  js      short loc_14008C1AB
0x14008c157  mov     r9, [rbp+3Fh+arg_30]
0x14008c15b  lea     r8, [rbp+3Fh+var_80]
0x14008c15f  mov     rcx, cs:WdfDriverGlobals
0x14008c166  lea     rdx, [rbp+3Fh+DestinationString]
0x14008c16a  xor     eax, eax
0x14008c16c  xorps   xmm0, xmm0
0x14008c16f  mov     [rbp+3Fh+var_50], rax
0x14008c173  mov     rax, [r13+10h]
0x14008c177  movups  [rbp+3Fh+var_70], xmm0
0x14008c17b  mov     dword ptr [rbp+3Fh+var_70+8], r14d
0x14008c17f  movups  [rbp+3Fh+var_60], xmm0
0x14008c183  mov     qword ptr [rbp+3Fh+var_60], rax
0x14008c187  mov     rax, cs:WdfFunctions_01015
0x14008c18e  movups  [rbp+3Fh+var_80], xmm0
0x14008c192  mov     dword ptr [rbp+3Fh+var_80], 38h ; '8'
0x14008c199  mov     dword ptr [rbp+3Fh+var_70+0Ch], r14d
0x14008c19d  mov     rax, [rax+9A0h]
0x14008c1a4  call    _guard_dispatch_icall
0x14008c1a9  mov     esi, eax
0x14008c1ab  mov     rcx, [rbp+3Fh+DestinationString.Buffer]; P
0x14008c1af  test    rcx, rcx
0x14008c1b2  jz      short loc_14008C1C5
0x14008c1b4  mov     edx, 70334855h; Tag
0x14008c1b9  call    cs:__imp_ExFreePoolWithTag
0x14008c1c0  nop     dword ptr [rax+rax+00h]
0x14008c1c5  mov     eax, esi
0x14008c1c7  add     rsp, 98h
0x14008c1ce  pop     r15
0x14008c1d0  pop     r14
0x14008c1d2  pop     r13
0x14008c1d4  pop     r12
0x14008c1d6  pop     rdi
0x14008c1d7  pop     rsi
0x14008c1d8  pop     rbx
0x14008c1d9  pop     rbp
0x14008c1da  retn
```
