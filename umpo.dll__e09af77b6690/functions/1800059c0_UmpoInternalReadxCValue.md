# UmpoInternalReadxCValue

- ea: `0x1800059c0`
- end: `0x180005cad`
- name: `UmpoInternalReadxCValue`
- size: `749`
- prototype: `__int64 __fastcall(UUID *Uuid2, UUID *, UUID *Uuid1, _QWORD *, __int64, char, LPDWORD, __int64, LPDWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002e90`
- `0x180004420`
- `0x180004e0c`
- `0x180004e60`
- `0x180005cb4`
- `0x18000681c`
- `0x180008640`

## callees

- `0x1800059c0`
- `0x180005cb4`
- `0x18000681c`
- `0x18000f3dc`

## pseudocode

```c
__int64 __fastcall UmpoInternalReadxCValue(
        UUID *Uuid2,
        UUID *a2,
        UUID *Uuid1,
        _QWORD *a4,
        __int64 a5,
        char a6,
        LPDWORD a7,
        __int64 a8,
        LPDWORD a9)
{
  bool v12; // al
  DWORD *lpType; // rdi
  char v14; // si
  __int64 result; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  char v18; // r15
  int v19; // eax
  int v20; // eax
  int v21[4]; // [rsp+60h] [rbp-38h] BYREF
  DWORD v22; // [rsp+A8h] [rbp+10h] BYREF

  if ( !a2 && !Uuid1 && !a5 && !a4 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return 87;
  }
  v12 = 0;
  v21[0] = 0;
  if ( Uuid2 )
  {
    v16 = *(_QWORD *)&Uuid2->Data1 - *(_QWORD *)&GUID_POWER_MODE_NONE.Data1;
    if ( !v16 )
      v16 = *(_QWORD *)Uuid2->Data4 - *(_QWORD *)GUID_POWER_MODE_NONE.Data4;
    v12 = v16 != 0;
  }
  if ( !a4 )
    goto LABEL_4;
  v17 = *a4 - *(_QWORD *)&GUID_POWER_POLICY_PROFILE_DEFAULT.Data1;
  if ( *a4 == *(_QWORD *)&GUID_POWER_POLICY_PROFILE_DEFAULT.Data1 )
    v17 = a4[1] - *(_QWORD *)GUID_POWER_POLICY_PROFILE_DEFAULT.Data4;
  if ( !v17 )
  {
LABEL_4:
    lpType = a7;
    v14 = a6;
    if ( v12 )
    {
      v22 = 4;
      v20 = UmpoReadFromUserPowerKey(Uuid2, 0, a6 == 0, a7, (__int64)v21, &v22, 0);
      if ( !v20 )
        return UmpoReadFromSystemPowerKey((__int64)a2, Uuid1, 0, 4, (__int64)lpType, v21[0], a8, a9, 0);
      if ( v20 != 2 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v22 = 4;
    result = UmpoReadFromUserPowerKey(a2, 0, v14 == 0, lpType, (__int64)v21, &v22, 0);
    goto LABEL_6;
  }
  lpType = a7;
  v18 = a6;
  if ( !v12 )
  {
LABEL_19:
    v22 = 4;
    result = UmpoReadFromSystemPowerKey(
               (__int64)a2,
               Uuid1,
               0,
               8 - (unsigned int)(v18 != 0),
               (__int64)lpType,
               0,
               (__int64)v21,
               &v22,
               0);
LABEL_6:
    if ( (_DWORD)result )
      return result;
    return UmpoReadFromSystemPowerKey((__int64)a2, Uuid1, 0, 4, (__int64)lpType, v21[0], a8, a9, 0);
  }
  v22 = 4;
  v19 = UmpoReadFromSystemPowerKey(
          (__int64)Uuid2,
          Uuid1,
          1,
          8 - (unsigned int)(a6 != 0),
          (__int64)a7,
          0,
          (__int64)v21,
          &v22,
          0);
  if ( v19 )
  {
    if ( v19 != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_19;
  }
  return UmpoReadFromSystemPowerKey((__int64)a2, Uuid1, 0, 4, (__int64)lpType, v21[0], a8, a9, 0);
}

```

## disassembly

```asm
0x1800059c0  push    rbx
0x1800059c2  push    rbp
0x1800059c3  push    rsi
0x1800059c4  push    r14
0x1800059c6  sub     rsp, 78h
0x1800059ca  mov     r14, [rsp+98h+arg_20]
0x1800059d2  mov     rsi, r9
0x1800059d5  mov     rbp, r8
0x1800059d8  mov     rbx, rdx
0x1800059db  mov     r10, rcx
0x1800059de  test    rdx, rdx
0x1800059e1  jz      loc_180005C0A
0x1800059e7  mov     [rsp+98h+arg_10], r12
0x1800059ef  xor     al, al
0x1800059f1  xor     r12d, r12d
0x1800059f4  mov     [rsp+98h+var_38], r12d
0x1800059f9  test    r10, r10
0x1800059fc  jnz     loc_180005AEC
0x180005a02  mov     [rsp+98h+arg_0], rdi
0x180005a0a  mov     [rsp+98h+var_28], r15
0x180005a0f  test    rsi, rsi
0x180005a12  jnz     loc_180005B16
0x180005a18  mov     rdi, [rsp+98h+arg_30]
0x180005a20  movzx   esi, [rsp+98h+arg_28]
0x180005a28  test    al, al
0x180005a2a  jnz     loc_180005C39
0x180005a30  mov     [rsp+98h+var_50], r12; __int64
0x180005a35  lea     rcx, [rsp+98h+arg_8]
0x180005a3d  mov     [rsp+98h+var_58], rcx; LPDWORD
0x180005a42  mov     eax, r12d
0x180005a45  test    sil, sil
0x180005a48  mov     [rsp+98h+arg_8], 4
0x180005a53  lea     rcx, [rsp+98h+var_38]
0x180005a58  mov     r8, r14
0x180005a5b  mov     [rsp+98h+var_60], rcx; __int64
0x180005a60  setz    al
0x180005a63  mov     [rsp+98h+lpType], rdi; lpType
0x180005a68  xor     r9d, r9d
0x180005a6b  mov     [rsp+98h+var_70], eax; int
0x180005a6f  mov     rdx, rbp
0x180005a72  mov     rcx, rbx; Uuid2
0x180005a75  mov     [rsp+98h+var_78], r12b; char
0x180005a7a  call    UmpoReadFromUserPowerKey
0x180005a7f  test    eax, eax
0x180005a81  jnz     short loc_180005ACD
0x180005a83  mov     rax, [rsp+98h+arg_40]
0x180005a8b  mov     r9, r14
0x180005a8e  mov     [rsp+98h+var_48], r12; __int64
0x180005a93  xor     r8d, r8d
0x180005a96  mov     [rsp+98h+var_50], rax; LPDWORD
0x180005a9b  mov     rdx, rbp; Uuid1
0x180005a9e  mov     rax, [rsp+98h+arg_38]
0x180005aa6  mov     rcx, rbx; __int64
0x180005aa9  mov     [rsp+98h+var_58], rax; __int64
0x180005aae  mov     eax, [rsp+98h+var_38]
0x180005ab2  mov     dword ptr [rsp+98h+var_60], eax; int
0x180005ab6  mov     [rsp+98h+lpType], rdi; __int64
0x180005abb  mov     [rsp+98h+var_70], 4; int
0x180005ac3  mov     [rsp+98h+var_78], r12b; char
0x180005ac8  call    UmpoReadFromSystemPowerKey
0x180005acd  mov     r15, [rsp+98h+var_28]
0x180005ad2  mov     r12, [rsp+98h+arg_10]
0x180005ada  mov     rdi, [rsp+98h+arg_0]
0x180005ae2  add     rsp, 78h
0x180005ae6  pop     r14
0x180005ae8  pop     rsi
0x180005ae9  pop     rbp
0x180005aea  pop     rbx
0x180005aeb  retn
0x180005aec  mov     rcx, [rcx]
0x180005aef  sub     rcx, qword ptr cs:GUID_POWER_MODE_NONE.Data1
0x180005af6  jnz     short loc_180005B03
0x180005af8  mov     rcx, [r10+8]
0x180005afc  sub     rcx, qword ptr cs:GUID_POWER_MODE_NONE.Data4
0x180005b03  test    rcx, rcx
0x180005b06  movzx   eax, al
0x180005b09  mov     edx, 1
0x180005b0e  cmovnz  eax, edx
0x180005b11  jmp     loc_180005A02
0x180005b16  mov     rcx, [r9]
0x180005b19  sub     rcx, qword ptr cs:GUID_POWER_POLICY_PROFILE_DEFAULT.Data1
0x180005b20  jnz     short loc_180005B2D
0x180005b22  mov     rcx, [r9+8]
0x180005b26  sub     rcx, qword ptr cs:GUID_POWER_POLICY_PROFILE_DEFAULT.Data4
0x180005b2d  test    rcx, rcx
0x180005b30  jz      loc_180005A18
0x180005b36  mov     rdi, [rsp+98h+arg_30]
0x180005b3e  movzx   r15d, [rsp+98h+arg_28]
0x180005b47  test    al, al
0x180005b49  jz      short loc_180005BB2
0x180005b4b  mov     [rsp+98h+var_48], r12; __int64
0x180005b50  movzx   eax, r15b
0x180005b54  neg     al
0x180005b56  mov     [rsp+98h+arg_8], 4
0x180005b61  lea     rax, [rsp+98h+arg_8]
0x180005b69  mov     r9, r14
0x180005b6c  mov     [rsp+98h+var_50], rax; LPDWORD
0x180005b71  sbb     ecx, ecx
0x180005b73  add     ecx, 8
0x180005b76  lea     rax, [rsp+98h+var_38]
0x180005b7b  mov     [rsp+98h+var_58], rax; __int64
0x180005b80  mov     r8, rsi
0x180005b83  mov     dword ptr [rsp+98h+var_60], r12d; int
0x180005b88  mov     rdx, rbp; Uuid1
0x180005b8b  mov     [rsp+98h+lpType], rdi; __int64
0x180005b90  mov     [rsp+98h+var_70], ecx; int
0x180005b94  mov     rcx, r10; __int64
0x180005b97  mov     [rsp+98h+var_78], 1; char
0x180005b9c  call    UmpoReadFromSystemPowerKey
0x180005ba1  test    eax, eax
0x180005ba3  jz      loc_180005A83
0x180005ba9  cmp     eax, 2
0x180005bac  jnz     loc_180005CA3
0x180005bb2  mov     [rsp+98h+var_48], r12; __int64
0x180005bb7  lea     rcx, [rsp+98h+arg_8]
0x180005bbf  mov     [rsp+98h+var_50], rcx; LPDWORD
0x180005bc4  neg     r15b
0x180005bc7  lea     rcx, [rsp+98h+var_38]
0x180005bcc  mov     [rsp+98h+arg_8], 4
0x180005bd7  mov     [rsp+98h+var_58], rcx; __int64
0x180005bdc  sbb     eax, eax
0x180005bde  mov     dword ptr [rsp+98h+var_60], r12d; int
0x180005be3  add     eax, 8
0x180005be6  mov     [rsp+98h+lpType], rdi; __int64
0x180005beb  mov     r9, r14
0x180005bee  mov     [rsp+98h+var_70], eax; int
0x180005bf2  mov     r8, rsi
0x180005bf5  mov     rdx, rbp; Uuid1
0x180005bf8  mov     [rsp+98h+var_78], r12b; char
0x180005bfd  mov     rcx, rbx; __int64
0x180005c00  call    UmpoReadFromSystemPowerKey
0x180005c05  jmp     loc_180005A7F
0x180005c0a  test    rbp, rbp
0x180005c0d  jnz     loc_1800059E7
0x180005c13  test    r14, r14
0x180005c16  jnz     loc_1800059E7
0x180005c1c  test    rsi, rsi
0x180005c1f  jnz     loc_1800059E7
0x180005c25  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180005c2a  mov     eax, 57h ; 'W'
0x180005c2f  add     rsp, 78h
0x180005c33  pop     r14
0x180005c35  pop     rsi
0x180005c36  pop     rbp
0x180005c37  pop     rbx
0x180005c38  retn
0x180005c39  mov     [rsp+98h+var_50], r12; __int64
0x180005c3e  lea     rcx, [rsp+98h+arg_8]
0x180005c46  mov     [rsp+98h+var_58], rcx; LPDWORD
0x180005c4b  mov     eax, r12d
0x180005c4e  lea     rcx, [rsp+98h+var_38]
0x180005c53  mov     [rsp+98h+arg_8], 4
0x180005c5e  mov     [rsp+98h+var_60], rcx; __int64
0x180005c63  test    sil, sil
0x180005c66  mov     [rsp+98h+lpType], rdi; lpType
0x180005c6b  mov     r9b, 1
0x180005c6e  setz    al
0x180005c71  mov     r8, r14
0x180005c74  mov     [rsp+98h+var_70], eax; int
0x180005c78  mov     rdx, rbp
0x180005c7b  mov     rcx, r10; Uuid2
0x180005c7e  mov     [rsp+98h+var_78], r12b; char
0x180005c83  call    UmpoReadFromUserPowerKey
0x180005c88  test    eax, eax
0x180005c8a  jz      loc_180005A83
0x180005c90  cmp     eax, 2
0x180005c93  jz      loc_180005A30
0x180005c99  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180005c9e  jmp     loc_180005A30
0x180005ca3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180005ca8  jmp     loc_180005BB2
```
