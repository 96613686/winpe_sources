# CUser::StopUserPresencePollingUnderLock(void)

- ea: `0x140048b10`
- end: `0x140048dd2`
- name: `?StopUserPresencePollingUnderLock@CUser@@AEAAXXZ`
- size: `706`
- prototype: `void __fastcall(CUser *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400339b4`
- `0x140041ef8`

## callees

- `0x1400057f4`
- `0x140041c34`
- `0x140048b10`
- `0x1400533e4`
- `0x140053720`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x140048b81`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x140048b9a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x140048b81`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x140048b9a`
- `ntdll!EtwEventWriteTransfer` at `0x140048cdd`
- `ntdll!EtwEventWriteTransfer` at `0x140048d7f`
- `ntdll!EtwEventWriteTransfer` at `0x140048cdd`
- `ntdll!EtwEventWriteTransfer` at `0x140048d7f`
- `NaturalAuthClient!NaDynamicLockStop` at `0x140048bbe`
- `NaturalAuthClient!NaDynamicLockStop` at `0x140048bbe`

## pseudocode

```c
void __fastcall CUser::StopUserPresencePollingUnderLock(CUser *this, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // edi
  int v6; // eax
  char *v7; // r8
  _DWORD *v8; // rdi
  __int64 v9; // [rsp+30h] [rbp-59h] BYREF
  __int64 v10; // [rsp+38h] [rbp-51h] BYREF
  __int64 v11; // [rsp+40h] [rbp-49h] BYREF
  __int64 v12; // [rsp+48h] [rbp-41h]
  _DWORD v13[2]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v14; // [rsp+58h] [rbp-31h]
  char *v15; // [rsp+60h] [rbp-29h] BYREF
  int v16; // [rsp+68h] [rbp-21h]
  int v17; // [rsp+6Ch] [rbp-1Dh]
  __int16 *v18; // [rsp+70h] [rbp-19h]
  __int64 v19; // [rsp+78h] [rbp-11h]
  char *v20; // [rsp+80h] [rbp-9h] BYREF
  int v21; // [rsp+88h] [rbp-1h]
  int v22; // [rsp+8Ch] [rbp+3h]
  __int16 *v23; // [rsp+90h] [rbp+7h]
  __int64 v24; // [rsp+98h] [rbp+Fh]
  __int64 *v25; // [rsp+A0h] [rbp+17h]
  __int64 v26; // [rsp+A8h] [rbp+1Fh]
  char *v27; // [rsp+B0h] [rbp+27h]
  __int64 v28; // [rsp+B8h] [rbp+2Fh]

  v5 = 0;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids, a4);
  }
  if ( *((_QWORD *)this + 72) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 72) = 0;
  }
  if ( *((_QWORD *)this + 75) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 75) = 0;
  }
  *((_DWORD *)this + 142) = 0;
  *((_QWORD *)this + 70) = 0;
  if ( *((_DWORD *)this + 136) )
  {
    v6 = NaDynamicLockStop();
    v5 = v6;
    if ( v6 < 0
      && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        194,
        WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids,
        (unsigned int)v6);
    }
    *((_DWORD *)this + 136) = 0;
  }
  v7 = (char *)qword_1400D2DA8;
  if ( qword_1400D2DA8 )
  {
    *(_DWORD *)qword_1400D2DA8 = 2;
    if ( (unsigned int)dword_1400CF778 > 4 )
    {
      HIDWORD(v9) = v5;
      v27 = (char *)&v9 + 4;
      v10 = 0x1000000;
      v25 = &v10;
      v20 = (char *)off_1400CF780;
      v28 = 4;
      v26 = 8;
      v11 = 0x2040B000000LL;
      v12 = 0;
      v21 = *(unsigned __int16 *)off_1400CF780;
      v23 = word_1400BD232;
      v22 = 2;
      v24 = 0x100000043LL;
      LODWORD(v9) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      ((void (__fastcall *)(__int64, __int64 *, char *, _QWORD, int, char **, __int64, __int64))EtwEventWriteTransfer)(
        qword_1400CF798,
        &v11,
        v7 + 8,
        0,
        4,
        &v20,
        v9,
        0x1000000);
    }
    v8 = qword_1400D2DA8;
    if ( qword_1400D2DA8 )
    {
      if ( *(_DWORD *)qword_1400D2DA8 == 1 )
      {
        *(_DWORD *)qword_1400D2DA8 = 2;
        if ( (unsigned int)dword_1400CF778 > 4 )
        {
          v13[1] = 516;
          v15 = (char *)off_1400CF780;
          v13[0] = 184549376;
          v14 = 0;
          v16 = *(unsigned __int16 *)off_1400CF780;
          v18 = word_1400BD01A;
          v17 = 2;
          v19 = 0x100000020LL;
          LODWORD(v9) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_1400CF798, v13, v8 + 2, 0, 2, &v15, v9, v10, v11, v12);
        }
      }
      *v8 = 3;
      operator delete(v8, 0x28u);
    }
    qword_1400D2DA8 = 0;
  }
  *((_DWORD *)this + 137) = 0;
}

```

## disassembly

```asm
0x140048b10  mov     [rsp-8+arg_10], rbx
0x140048b15  mov     [rsp-8+arg_18], rsi
0x140048b1a  push    rbp
0x140048b1b  push    rdi
0x140048b1c  push    r14
0x140048b1e  lea     rbp, [rsp-47h]
0x140048b23  sub     rsp, 0D0h
0x140048b2a  mov     rax, cs:__security_cookie
0x140048b31  xor     rax, rsp
0x140048b34  mov     [rbp+57h+var_20], rax
0x140048b38  xor     r14d, r14d
0x140048b3b  mov     rbx, rcx
0x140048b3e  mov     edi, r14d
0x140048b41  mov     rcx, cs:WPP_GLOBAL_Control
0x140048b48  lea     rsi, WPP_GLOBAL_Control
0x140048b4f  cmp     rcx, rsi
0x140048b52  jz      short loc_140048B75
0x140048b54  test    byte ptr [rcx+1Ch], 20h
0x140048b58  jz      short loc_140048B75
0x140048b5a  cmp     byte ptr [rcx+19h], 5
0x140048b5e  jb      short loc_140048B75
0x140048b60  mov     rcx, [rcx+10h]
0x140048b64  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140048b6b  mov     edx, 0C1h
0x140048b70  call    WPP_SF_
0x140048b75  mov     rcx, [rbx+240h]
0x140048b7c  test    rcx, rcx
0x140048b7f  jz      short loc_140048B8E
0x140048b81  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x140048b87  mov     [rbx+240h], r14
0x140048b8e  mov     rcx, [rbx+258h]
0x140048b95  test    rcx, rcx
0x140048b98  jz      short loc_140048BA7
0x140048b9a  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x140048ba0  mov     [rbx+258h], r14
0x140048ba7  mov     [rbx+238h], r14d
0x140048bae  mov     [rbx+230h], r14
0x140048bb5  cmp     [rbx+220h], r14d
0x140048bbc  jz      short loc_140048C01
0x140048bbe  call    cs:__imp_NaDynamicLockStop
0x140048bc4  mov     edi, eax
0x140048bc6  test    eax, eax
0x140048bc8  jns     short loc_140048BFA
0x140048bca  mov     rcx, cs:WPP_GLOBAL_Control
0x140048bd1  cmp     rcx, rsi
0x140048bd4  jz      short loc_140048BFA
0x140048bd6  test    byte ptr [rcx+1Ch], 20h
0x140048bda  jz      short loc_140048BFA
0x140048bdc  cmp     byte ptr [rcx+19h], 2
0x140048be0  jb      short loc_140048BFA
0x140048be2  mov     rcx, [rcx+10h]
0x140048be6  lea     r8, WPP_586e3f58e70b3bd7f4fb97bd2f93cbf8_Traceguids
0x140048bed  mov     edx, 0C2h
0x140048bf2  mov     r9d, eax
0x140048bf5  call    WPP_SF_d
0x140048bfa  mov     [rbx+220h], r14d
0x140048c01  mov     r8, cs:qword_1400D2DA8
0x140048c08  test    r8, r8
0x140048c0b  jz      loc_140048DA7
0x140048c11  mov     dword ptr [r8], 2
0x140048c18  lea     rsi, _TraceLoggingMetadataEnd
0x140048c1f  mov     eax, cs:dword_1400CF778
0x140048c25  mov     [rsp+0E0h+arg_8], r15
0x140048c2d  lea     r15, _TraceLoggingMetadata
0x140048c34  cmp     eax, 4
0x140048c37  jbe     loc_140048CE3
0x140048c3d  mov     [rbp+57h+var_AC], edi
0x140048c40  lea     rax, [rbp+57h+var_AC]
0x140048c44  mov     [rbp+57h+var_30], rax
0x140048c48  lea     rdx, [rbp+57h+var_A0]
0x140048c4c  lea     rax, [rbp+57h+var_A8]
0x140048c50  mov     [rbp+57h+var_A8], 1000000h
0x140048c58  mov     [rbp+57h+var_40], rax
0x140048c5c  add     r8, 8
0x140048c60  movzx   eax, cs:word_1400BD228
0x140048c67  xor     r9d, r9d
0x140048c6a  mov     [rbp+57h+var_9C], eax
0x140048c6d  mov     rax, cs:off_1400CF780
0x140048c74  mov     [rbp+57h+var_60], rax
0x140048c78  mov     [rbp+57h+var_28], 4
0x140048c80  mov     [rbp+57h+var_38], 8
0x140048c88  mov     [rbp+57h+var_A0], 0B000000h
0x140048c8f  mov     [rbp+57h+var_98], r14
0x140048c93  movzx   eax, word ptr [rax]
0x140048c96  mov     [rbp+57h+var_58], eax
0x140048c99  lea     rax, word_1400BD232
0x140048ca0  mov     [rbp+57h+var_50], rax
0x140048ca4  mov     rax, rsi
0x140048ca7  sub     eax, r15d
0x140048caa  mov     [rbp+57h+var_54], 2
0x140048cb1  mov     dword ptr [rbp+57h+var_48], 43h ; 'C'
0x140048cb8  mov     dword ptr [rbp+57h+var_48+4], 1
0x140048cbf  mov     [rbp+57h+var_B0], eax
0x140048cc2  mov     eax, [rbp+57h+var_B0]
0x140048cc5  mov     rcx, cs:qword_1400CF798
0x140048ccc  lea     rax, [rbp+57h+var_60]
0x140048cd0  mov     [rsp+0E0h+var_B8], rax
0x140048cd5  mov     [rsp+0E0h+var_C0], 4
0x140048cdd  call    cs:__imp_EtwEventWriteTransfer
0x140048ce3  mov     rdi, cs:qword_1400D2DA8
0x140048cea  test    rdi, rdi
0x140048ced  jz      loc_140048D98
0x140048cf3  cmp     dword ptr [rdi], 1
0x140048cf6  jnz     loc_140048D85
0x140048cfc  mov     dword ptr [rdi], 2
0x140048d02  mov     eax, cs:dword_1400CF778
0x140048d08  cmp     eax, 4
0x140048d0b  jbe     short loc_140048D85
0x140048d0d  movzx   eax, cs:word_1400BD010
0x140048d14  lea     r8, [rdi+8]
0x140048d18  mov     [rbp+57h+var_8C], eax
0x140048d1b  lea     rdx, [rbp+57h+var_90]
0x140048d1f  mov     rax, cs:off_1400CF780
0x140048d26  sub     esi, r15d
0x140048d29  mov     [rbp+57h+var_80], rax
0x140048d2d  xor     r9d, r9d
0x140048d30  mov     [rbp+57h+var_90], 0B000000h
0x140048d37  mov     [rbp+57h+var_88], r14
0x140048d3b  movzx   eax, word ptr [rax]
0x140048d3e  mov     [rbp+57h+var_78], eax
0x140048d41  lea     rax, word_1400BD01A
0x140048d48  mov     [rbp+57h+var_70], rax
0x140048d4c  mov     [rbp+57h+var_74], 2
0x140048d53  mov     dword ptr [rbp+57h+var_68], 20h ; ' '
0x140048d5a  mov     dword ptr [rbp+57h+var_68+4], 1
0x140048d61  mov     [rbp+57h+var_B0], esi
0x140048d64  mov     eax, [rbp+57h+var_B0]
0x140048d67  mov     rcx, cs:qword_1400CF798
0x140048d6e  lea     rax, [rbp+57h+var_80]
0x140048d72  mov     [rsp+0E0h+var_B8], rax
0x140048d77  mov     [rsp+0E0h+var_C0], 2
0x140048d7f  call    cs:__imp_EtwEventWriteTransfer
0x140048d85  mov     edx, 28h ; '('; unsigned __int64
0x140048d8a  mov     dword ptr [rdi], 3
0x140048d90  mov     rcx, rdi; void *
0x140048d93  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140048d98  mov     r15, [rsp+0E0h+arg_8]
0x140048da0  mov     cs:qword_1400D2DA8, r14
0x140048da7  mov     [rbx+224h], r14d
0x140048dae  mov     rcx, [rbp+57h+var_20]
0x140048db2  xor     rcx, rsp; StackCookie
0x140048db5  call    __security_check_cookie
0x140048dba  lea     r11, [rsp+0E0h+var_10]
0x140048dc2  mov     rbx, [r11+30h]
0x140048dc6  mov     rsi, [r11+38h]
0x140048dca  mov     rsp, r11
0x140048dcd  pop     r14
0x140048dcf  pop     rdi
0x140048dd0  pop     rbp
0x140048dd1  retn
```
