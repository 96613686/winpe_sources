# NotifyRoutine

- ea: `0x140003be0`
- end: `0x140003f95`
- name: `NotifyRoutine`
- size: `949`
- prototype: `void __stdcall(PEPROCESS Process, HANDLE ProcessId, PPS_CREATE_NOTIFY_INFO CreateInfo)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003524`
- `0x140003be0`
- `0x140003fcc`
- `0x140006b60`
- `0x140007db0`
- `0x140015958`
- `0x140017250`
- `0x140017294`
- `0x140017c04`
- `0x140018ac0`
- `0x140019160`
- `0x140019360`

## import_xrefs

- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140003cf4`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140003cf4`
- `ntoskrnl!EtwWriteTransfer` at `0x140003ddc`
- `ntoskrnl!EtwWriteTransfer` at `0x140003f5a`
- `ntoskrnl!EtwWriteTransfer` at `0x140003ddc`
- `ntoskrnl!EtwWriteTransfer` at `0x140003f5a`

## pseudocode

```c
void __fastcall NotifyRoutine(PEPROCESS Process, HANDLE ProcessId, PPS_CREATE_NOTIFY_INFO CreateInfo)
{
  __int64 v6; // rdi
  int v7; // r8d
  int v8; // r9d
  int v9; // edi
  unsigned __int64 v10; // r14
  int v11; // eax
  PCUNICODE_STRING ImageFileName; // rcx
  PWSTR Buffer; // rdx
  bool v14; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v15; // [rsp+34h] [rbp-A5h] BYREF
  __int64 v16; // [rsp+38h] [rbp-A1h] BYREF
  HANDLE v17; // [rsp+40h] [rbp-99h] BYREF
  __int128 v18; // [rsp+48h] [rbp-91h] BYREF
  HANDLE ParentProcessId; // [rsp+58h] [rbp-81h] BYREF
  __int128 v20; // [rsp+60h] [rbp-79h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-59h] BYREF
  __int16 *v23; // [rsp+90h] [rbp-49h]
  int v24; // [rsp+98h] [rbp-41h]
  int v25; // [rsp+9Ch] [rbp-3Dh]
  HANDLE *v26; // [rsp+A0h] [rbp-39h]
  __int64 v27; // [rsp+A8h] [rbp-31h]
  bool *p_ParentProcessId; // [rsp+B0h] [rbp-29h]
  __int64 v29; // [rsp+B8h] [rbp-21h]
  char *v30; // [rsp+C0h] [rbp-19h]
  __int64 v31; // [rsp+C8h] [rbp-11h]
  PWSTR v32; // [rsp+D0h] [rbp-9h]
  int v33; // [rsp+D8h] [rbp-1h]
  int v34; // [rsp+DCh] [rbp+3h]
  unsigned int *v35; // [rsp+E0h] [rbp+7h]
  __int64 v36; // [rsp+E8h] [rbp+Fh]

  v18 = 0;
  v20 = 0;
  if ( !byte_14000F3D0 )
    sub_140006B60();
  sub_140017250(Process, &v20);
  if ( (_DWORD)v20 != (_DWORD)ProcessId )
    sub_140006B60();
  if ( !CreateInfo )
  {
    sub_140003FCC(&v20);
    v6 = sub_140017C04(1, 0);
    if ( v6 )
    {
      if ( (unsigned int)dword_14000F030 > 4 )
      {
        v16 = *((_QWORD *)&v20 + 1);
        v15 = v20;
        sub_140003524(
          (unsigned int)&dword_14000F030,
          (unsigned int)byte_14000B4D1,
          v7,
          v8,
          (__int64)&v15,
          (__int64)&v16);
      }
      sub_140017294(v6, &v20);
    }
    v9 = sub_140015958(Process);
    if ( v9 == -1073741275 )
    {
      v10 = qword_14000F280;
      if ( qword_14000F280 )
      {
        if ( PsGetProcessCreateTimeQuadPart(Process) <= v10 )
          return;
        sub_140006B60();
      }
      goto LABEL_14;
    }
LABEL_26:
    if ( v9 >= 0 )
      return;
    goto LABEL_14;
  }
  if ( !CreateInfo->ImageFileName )
    sub_140006B60();
  v11 = sub_140019360(Process, CreateInfo->ImageFileName);
  if ( (int)(v11 + 0x80000000) >= 0 && v11 != -1073741670 )
    sub_140006B60();
  v9 = sub_140019160(CreateInfo->ParentProcessId, &v18);
  if ( v9 >= 0 )
  {
    v9 = sub_140018AC0((unsigned int)&v20, (unsigned int)&v18, CreateInfo->ImageFileName, CreateInfo->CommandLine, 0);
    goto LABEL_26;
  }
  if ( (unsigned int)dword_14000F030 > 2 )
  {
    ImageFileName = CreateInfo->ImageFileName;
    v15 = v9;
    v36 = 4;
    v31 = 2;
    Buffer = ImageFileName->Buffer;
    LODWORD(ImageFileName) = ImageFileName->Length & 0xFFFE;
    ParentProcessId = CreateInfo->ParentProcessId;
    v35 = &v15;
    v30 = (char *)&v18 + 8;
    p_ParentProcessId = (bool *)&ParentProcessId;
    v26 = &v17;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_14000F038;
    *(_QWORD *)&v18 = Buffer;
    WORD4(v18) = (_WORD)ImageFileName;
    v32 = Buffer;
    v33 = (int)ImageFileName;
    v17 = ProcessId;
    v34 = 0;
    v29 = 8;
    v27 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_14000F038;
    v23 = word_14000AF6A;
    UserData.Reserved = 2;
    v24 = 70;
    v25 = 1;
    LODWORD(v16) = (unsigned int)&word_14000D2C2 - (unsigned int)qword_14000AF00;
    EtwWriteTransfer(qword_14000F050, &EventDescriptor, 0, 0, 7u, &UserData);
  }
LABEL_14:
  if ( (unsigned int)dword_14000F030 > 2 )
  {
    LODWORD(v16) = v9;
    v30 = (char *)&v16;
    v17 = ProcessId;
    p_ParentProcessId = &v14;
    v31 = 4;
    v26 = &v17;
    v14 = CreateInfo != 0;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_14000F038;
    v29 = 1;
    v27 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_14000F038;
    v23 = (__int16 *)&byte_14000B0A7;
    UserData.Reserved = 2;
    v24 = 45;
    v25 = 1;
    v15 = (unsigned int)&word_14000D2C2 - (unsigned int)qword_14000AF00;
    EtwWriteTransfer(qword_14000F050, &EventDescriptor, 0, 0, 5u, &UserData);
  }
}

```

## disassembly

```asm
0x140003be0  push    rbp
0x140003be2  push    rbx
0x140003be3  push    rsi
0x140003be4  push    r12
0x140003be6  push    r13
0x140003be8  push    r14
0x140003bea  push    r15
0x140003bec  lea     rbp, [rsp-27h]
0x140003bf1  sub     rsp, 100h
0x140003bf8  mov     rax, cs:__security_cookie
0x140003bff  xor     rax, rsp
0x140003c02  mov     [rbp+57h+var_40], rax
0x140003c06  cmp     cs:byte_14000F3D0, 0
0x140003c0d  xorps   xmm0, xmm0
0x140003c10  xorps   xmm1, xmm1
0x140003c13  mov     rbx, r8
0x140003c16  movups  [rsp+130h+var_E8], xmm0
0x140003c1b  mov     r15, rdx
0x140003c1e  mov     rsi, rcx
0x140003c21  movups  [rbp+57h+var_D0], xmm1
0x140003c25  jnz     short loc_140003C2C
0x140003c27  call    sub_140006B60
0x140003c2c  lea     rdx, [rbp+57h+var_D0]
0x140003c30  mov     rcx, rsi
0x140003c33  call    sub_140017250
0x140003c38  cmp     dword ptr [rbp+57h+var_D0], r15d
0x140003c3c  jz      short loc_140003C43
0x140003c3e  call    sub_140006B60
0x140003c43  xor     r13d, r13d
0x140003c46  mov     [rsp+130h+arg_8], rdi
0x140003c4e  lea     r12, word_14000D2C2
0x140003c55  lea     r14, qword_14000AF00
0x140003c5c  test    rbx, rbx
0x140003c5f  jnz     loc_140003E10
0x140003c65  lea     rcx, [rbp+57h+var_D0]
0x140003c69  call    sub_140003FCC
0x140003c6e  xor     edx, edx
0x140003c70  mov     ecx, 1
0x140003c75  call    sub_140017C04
0x140003c7a  mov     rdi, rax
0x140003c7d  test    rax, rax
0x140003c80  jz      short loc_140003CD0
0x140003c82  mov     ecx, cs:dword_14000F030
0x140003c88  cmp     ecx, 4
0x140003c8b  jbe     short loc_140003CC4
0x140003c8d  mov     rcx, qword ptr [rbp+57h+var_D0+8]
0x140003c91  lea     rax, [rsp+130h+var_F8]
0x140003c96  mov     [rsp+130h+var_F8], rcx
0x140003c9b  lea     rdx, byte_14000B4D1
0x140003ca2  mov     ecx, dword ptr [rbp+57h+var_D0]
0x140003ca5  mov     [rsp+130h+UserData], rax
0x140003caa  lea     rax, [rsp+130h+var_FC]
0x140003caf  mov     [rsp+130h+var_FC], ecx
0x140003cb3  lea     rcx, dword_14000F030
0x140003cba  mov     qword ptr [rsp+130h+UserDataCount], rax
0x140003cbf  call    sub_140003524
0x140003cc4  lea     rdx, [rbp+57h+var_D0]
0x140003cc8  mov     rcx, rdi
0x140003ccb  call    sub_140017294
0x140003cd0  mov     rcx, rsi
0x140003cd3  call    sub_140015958
0x140003cd8  mov     edi, eax
0x140003cda  cmp     eax, 0C0000225h
0x140003cdf  jnz     loc_140003F88
0x140003ce5  mov     r14, cs:qword_14000F280
0x140003cec  test    r14, r14
0x140003cef  jz      short loc_140003D0E
0x140003cf1  mov     rcx, rsi; Process
0x140003cf4  call    cs:PsGetProcessCreateTimeQuadPart
0x140003cfb  nop     dword ptr [rax+rax+00h]
0x140003d00  cmp     rax, r14
0x140003d03  jbe     loc_140003DE8
0x140003d09  call    sub_140006B60
0x140003d0e  lea     r14, qword_14000AF00
0x140003d15  mov     eax, cs:dword_14000F030
0x140003d1b  cmp     eax, 2
0x140003d1e  jbe     loc_140003DE8
0x140003d24  mov     dword ptr [rsp+130h+var_F8], edi
0x140003d28  lea     rax, [rsp+130h+var_F8]
0x140003d2d  mov     [rbp+57h+var_70], rax
0x140003d31  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140003d35  mov     [rsp+130h+var_F0], r15
0x140003d3a  lea     rax, [rsp+130h+var_100]
0x140003d3f  mov     [rbp+57h+var_80], rax
0x140003d43  test    rbx, rbx
0x140003d46  lea     rax, [rsp+130h+var_F0]
0x140003d4b  mov     [rbp+57h+var_68], 4
0x140003d53  mov     [rbp+57h+var_90], rax
0x140003d57  setnz   [rsp+130h+var_100]
0x140003d5c  movzx   eax, cs:word_14000B09D
0x140003d63  sub     r12d, r14d
0x140003d66  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140003d69  xor     r9d, r9d; RelatedActivityId
0x140003d6c  mov     rax, cs:off_14000F038
0x140003d73  xor     r8d, r8d; ActivityId
0x140003d76  mov     [rbp+57h+var_B0.Ptr], rax
0x140003d7a  mov     [rbp+57h+var_78], 1
0x140003d82  mov     [rbp+57h+var_88], 8
0x140003d8a  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140003d91  mov     [rbp+57h+EventDescriptor.Keyword], r13
0x140003d95  movzx   eax, word ptr [rax]
0x140003d98  mov     [rbp+57h+var_B0.Size], eax
0x140003d9b  lea     rax, byte_14000B0A7
0x140003da2  mov     [rbp+57h+var_A0], rax
0x140003da6  mov     dword ptr [rbp+57h+var_B0.0Ch], 2
0x140003dad  mov     [rbp+57h+var_98], 2Dh ; '-'
0x140003db4  mov     [rbp+57h+var_94], 1
0x140003dbb  mov     [rsp+130h+var_FC], r12d
0x140003dc0  mov     eax, [rsp+130h+var_FC]
0x140003dc4  mov     rcx, cs:qword_14000F050; RegHandle
0x140003dcb  lea     rax, [rbp+57h+var_B0]
0x140003dcf  mov     [rsp+130h+UserData], rax; UserData
0x140003dd4  mov     [rsp+130h+UserDataCount], 5; UserDataCount
0x140003ddc  call    cs:EtwWriteTransfer
0x140003de3  nop     dword ptr [rax+rax+00h]
0x140003de8  mov     rdi, [rsp+130h+arg_8]
0x140003df0  mov     rcx, [rbp+57h+var_40]
0x140003df4  xor     rcx, rsp; StackCookie
0x140003df7  call    __security_check_cookie
0x140003dfc  add     rsp, 100h
0x140003e03  pop     r15
0x140003e05  pop     r14
0x140003e07  pop     r13
0x140003e09  pop     r12
0x140003e0b  pop     rsi
0x140003e0c  pop     rbx
0x140003e0d  pop     rbp
0x140003e0e  retn
0x140003e10  cmp     [rbx+30h], r13
0x140003e14  jnz     short loc_140003E1B
0x140003e16  call    sub_140006B60
0x140003e1b  mov     rdx, [rbx+30h]
0x140003e1f  mov     rcx, rsi
0x140003e22  call    sub_140019360
0x140003e27  mov     edx, 80000000h
0x140003e2c  lea     ecx, [rax+rdx]
0x140003e2f  test    edx, ecx
0x140003e31  jnz     short loc_140003E3F
0x140003e33  cmp     eax, 0C000009Ah
0x140003e38  jz      short loc_140003E3F
0x140003e3a  call    sub_140006B60
0x140003e3f  mov     rcx, [rbx+10h]
0x140003e43  lea     rdx, [rsp+130h+var_E8]
0x140003e48  call    sub_140019160
0x140003e4d  mov     edi, eax
0x140003e4f  test    eax, eax
0x140003e51  jns     loc_140003F6B
0x140003e57  mov     eax, cs:dword_14000F030
0x140003e5d  cmp     eax, 2
0x140003e60  jbe     loc_140003D15
0x140003e66  mov     rcx, [rbx+30h]
0x140003e6a  mov     eax, 0FFFEh
0x140003e6f  mov     [rsp+130h+var_FC], edi
0x140003e73  xor     r9d, r9d; RelatedActivityId
0x140003e76  mov     [rbp+57h+var_48], 4
0x140003e7e  xor     r8d, r8d; ActivityId
0x140003e81  mov     [rbp+57h+var_68], 2
0x140003e89  and     ax, [rcx]
0x140003e8c  mov     rdx, [rcx+8]
0x140003e90  movzx   ecx, ax
0x140003e93  mov     rax, [rbx+10h]
0x140003e97  mov     [rsp+130h+var_D8], rax
0x140003e9c  lea     rax, [rsp+130h+var_FC]
0x140003ea1  mov     [rbp+57h+var_50], rax
0x140003ea5  lea     rax, [rsp+130h+var_E8+8]
0x140003eaa  mov     [rbp+57h+var_70], rax
0x140003eae  lea     rax, [rsp+130h+var_D8]
0x140003eb3  mov     [rbp+57h+var_80], rax
0x140003eb7  lea     rax, [rsp+130h+var_F0]
0x140003ebc  mov     [rbp+57h+var_90], rax
0x140003ec0  movzx   eax, cs:word_14000AF60
0x140003ec7  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x140003eca  mov     rax, cs:off_14000F038
0x140003ed1  mov     [rbp+57h+var_B0.Ptr], rax
0x140003ed5  mov     qword ptr [rsp+130h+var_E8], rdx
0x140003eda  mov     word ptr [rsp+130h+var_E8+8], cx
0x140003edf  mov     [rbp+57h+var_60], rdx
0x140003ee3  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140003ee7  mov     [rbp+57h+var_58], ecx
0x140003eea  mov     [rsp+130h+var_F0], r15
0x140003eef  mov     [rbp+57h+var_54], r13d
0x140003ef3  mov     [rbp+57h+var_78], 8
0x140003efb  mov     [rbp+57h+var_88], 8
0x140003f03  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140003f0a  mov     [rbp+57h+EventDescriptor.Keyword], r13
0x140003f0e  movzx   eax, word ptr [rax]
0x140003f11  mov     [rbp+57h+var_B0.Size], eax
0x140003f14  lea     rax, word_14000AF6A
0x140003f1b  mov     [rbp+57h+var_A0], rax
0x140003f1f  mov     rax, r12
0x140003f22  sub     eax, r14d
0x140003f25  mov     dword ptr [rbp+57h+var_B0.0Ch], 2
0x140003f2c  mov     [rbp+57h+var_98], 46h ; 'F'
0x140003f33  mov     [rbp+57h+var_94], 1
0x140003f3a  mov     dword ptr [rsp+130h+var_F8], eax
0x140003f3e  mov     eax, dword ptr [rsp+130h+var_F8]
0x140003f42  mov     rcx, cs:qword_14000F050; RegHandle
0x140003f49  lea     rax, [rbp+57h+var_B0]
0x140003f4d  mov     [rsp+130h+UserData], rax; UserData
0x140003f52  mov     [rsp+130h+UserDataCount], 7; UserDataCount
0x140003f5a  call    cs:EtwWriteTransfer
0x140003f61  nop     dword ptr [rax+rax+00h]
0x140003f66  jmp     loc_140003D15
0x140003f6b  mov     r9, [rbx+38h]
0x140003f6f  lea     rdx, [rsp+130h+var_E8]
0x140003f74  mov     r8, [rbx+30h]
0x140003f78  lea     rcx, [rbp+57h+var_D0]
0x140003f7c  mov     byte ptr [rsp+130h+UserDataCount], r13b
0x140003f81  call    sub_140018AC0
0x140003f86  mov     edi, eax
0x140003f88  test    edi, edi
0x140003f8a  jns     loc_140003DE8
0x140003f90  jmp     loc_140003D15
```
