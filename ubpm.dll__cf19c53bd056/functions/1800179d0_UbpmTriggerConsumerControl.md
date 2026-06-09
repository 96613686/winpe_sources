# UbpmTriggerConsumerControl

- ea: `0x1800179d0`
- end: `0x180017d67`
- name: `UbpmTriggerConsumerControl`
- size: `919`
- prototype: `__int64 __fastcall(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *, _QWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003684`
- `0x18000a500`
- `0x1800179d0`
- `0x180018254`
- `0x180030be8`
- `0x180032cb0`
- `0x180032d38`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180017cc9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180017cc9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180017ae0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180017ae0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180017af4`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180017af4`

## pseudocode

```c
__int64 __fastcall UbpmTriggerConsumerControl(
        struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1,
        struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *a2,
        _QWORD *a3)
{
  _QWORD *v6; // r8
  unsigned int v7; // esi
  int v8; // ecx
  __int64 v9; // rax
  unsigned int v10; // eax
  DWORD v11; // ebx
  int v13; // edx
  int v14; // r9d
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  int v17; // [rsp+20h] [rbp-F8h]
  _BYTE v18[144]; // [rsp+60h] [rbp-B8h] BYREF

  memset_0(v18, 0, 0x88u);
  UbpmUtilsStartLockTracking((struct _CEM_LOCK_TRACKER *)v18);
  v7 = 87;
  if ( !a2 )
    goto LABEL_15;
  if ( a3 )
    *a3 = 0;
  v8 = *((_DWORD *)a2 + 1);
  if ( v8 && (v8 & 0x1F) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_LSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)&WPP_854cad5030553c91fcf88b43a20977bf_Traceguids,
        v8,
        *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL));
    goto LABEL_15;
  }
  if ( *(_DWORD *)a2 != 1 )
  {
    if ( *(_DWORD *)a2 != 2 )
      goto LABEL_15;
    if ( v8 || *((_DWORD *)a2 + 2) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_LdS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
          (_DWORD)WPP_GLOBAL_Control,
          v8,
          *((_DWORD *)a2 + 2),
          *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL));
      goto LABEL_15;
    }
    v10 = UbpmpStopAllConsumerActions(a1, *((_QWORD *)a2 + 4), *((_QWORD *)a2 + 3));
LABEL_14:
    v7 = v10;
    goto LABEL_15;
  }
  if ( (v8 & 2) != 0 )
  {
    if ( *((_DWORD *)a2 + 2) == -1 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_15;
      v13 = 11;
      goto LABEL_23;
    }
    if ( (v8 & 8) != 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_15;
      v13 = 12;
      goto LABEL_23;
    }
  }
  else if ( *((_DWORD *)a2 + 2) != -1 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v13 = 13;
    goto LABEL_23;
  }
  v9 = *((_QWORD *)a2 + 3);
  if ( (v8 & 4) == 0 )
  {
    if ( !v9 )
    {
      if ( (v8 & 8) == 0 )
        goto LABEL_12;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_15;
      v13 = 16;
LABEL_41:
      v14 = *((_DWORD *)a2 + 1);
LABEL_42:
      v15 = v16[2];
      goto LABEL_43;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v13 = 15;
LABEL_23:
    v14 = *((_DWORD *)a2 + 1);
    v15 = v6[2];
LABEL_43:
    WPP_SF_LS(v15, v13, (_DWORD)v6, v14, *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL));
    goto LABEL_15;
  }
  if ( !v9 || !IsValidSid(*((PSID *)a2 + 3)) )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_15;
    v13 = 14;
    goto LABEL_41;
  }
LABEL_12:
  LODWORD(v6) = *((_DWORD *)a2 + 1);
  if ( ((unsigned __int8)v6 & 0x10) == 0 || ((unsigned __int8)v6 & 6) != 0 )
  {
    *((_DWORD *)a2 + 1) = (unsigned int)v6 | 0x10000;
    v10 = UbpmRunConsumerActions(a1, v17, 0, 0xFFFFu, 0, 0, a2, (__int64)a3);
    goto LABEL_14;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v13 = 17;
    v14 = *((_DWORD *)a2 + 1);
    goto LABEL_42;
  }
LABEL_15:
  v11 = UbpmpLockTrackerId;
  if ( UbpmpLockTrackerId != -1 )
  {
    if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
      __int2c();
    TlsSetValue(v11, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x1800179d0  mov     [rsp+arg_18], rbx
0x1800179d5  push    rsi
0x1800179d6  push    rdi
0x1800179d7  push    r14
0x1800179d9  sub     rsp, 100h
0x1800179e0  mov     rax, cs:__security_cookie
0x1800179e7  xor     rax, rsp
0x1800179ea  mov     [rsp+118h+var_28], rax
0x1800179f2  mov     r14, r8
0x1800179f5  mov     rbx, rdx
0x1800179f8  mov     rdi, rcx
0x1800179fb  xor     edx, edx; Val
0x1800179fd  mov     r8d, 88h; Size
0x180017a03  lea     rcx, [rsp+118h+var_B8]; void *
0x180017a08  call    memset_0
0x180017a0d  lea     rcx, [rsp+118h+var_B8]; lpTlsValue
0x180017a12  call    ?UbpmUtilsStartLockTracking@@YAXPEAU_CEM_LOCK_TRACKER@@@Z; UbpmUtilsStartLockTracking(_CEM_LOCK_TRACKER *)
0x180017a17  mov     esi, 57h ; 'W'
0x180017a1c  test    rbx, rbx
0x180017a1f  jz      loc_180017AD3
0x180017a25  test    r14, r14
0x180017a28  jz      short loc_180017A31
0x180017a2a  mov     qword ptr [r14], 0
0x180017a31  mov     ecx, [rbx+4]
0x180017a34  test    ecx, ecx
0x180017a36  jz      short loc_180017A41
0x180017a38  test    cl, 1Fh
0x180017a3b  jz      loc_180017BD5
0x180017a41  mov     edx, [rbx]
0x180017a43  sub     edx, 1
0x180017a46  jnz     loc_180017B4B
0x180017a4c  test    cl, 2
0x180017a4f  jnz     loc_180017B76
0x180017a55  cmp     dword ptr [rbx+8], 0FFFFFFFFh
0x180017a59  jnz     loc_180017BA9
0x180017a5f  mov     rax, [rbx+18h]
0x180017a63  test    cl, 4
0x180017a66  jnz     loc_180017CC1
0x180017a6c  test    rax, rax
0x180017a6f  jnz     loc_180017B20
0x180017a75  test    cl, 8
0x180017a78  jnz     loc_180017CFD
0x180017a7e  mov     r8d, [rbx+4]
0x180017a82  test    r8b, 10h
0x180017a86  jnz     loc_180017D28
0x180017a8c  mov     [rsp+118h+var_C8], r14; __int64
0x180017a91  bts     r8d, 10h
0x180017a96  mov     [rsp+118h+var_D0], rbx; struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *
0x180017a9b  xor     r9d, r9d
0x180017a9e  mov     [rsp+118h+var_D8], 0; __int64
0x180017aa7  xor     edx, edx
0x180017aa9  mov     [rsp+118h+var_E0], 0; unsigned int
0x180017ab1  mov     rcx, rdi; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x180017ab4  mov     [rbx+4], r8d
0x180017ab8  xor     r8d, r8d
0x180017abb  mov     [rsp+118h+var_E8], 0FFFFh; unsigned int
0x180017ac3  mov     [rsp+118h+var_F0], 0; unsigned __int64
0x180017acc  call    UbpmRunConsumerActions
0x180017ad1  mov     esi, eax
0x180017ad3  mov     ebx, cs:UbpmpLockTrackerId
0x180017ad9  cmp     ebx, 0FFFFFFFFh
0x180017adc  jz      short loc_180017AFA
0x180017ade  mov     ecx, ebx; dwTlsIndex
0x180017ae0  call    cs:__imp_TlsGetValue
0x180017ae6  cmp     qword ptr [rax], 0
0x180017aea  jnz     loc_180017D60
0x180017af0  xor     edx, edx; lpTlsValue
0x180017af2  mov     ecx, ebx; dwTlsIndex
0x180017af4  call    cs:__imp_TlsSetValue
0x180017afa  mov     eax, esi
0x180017afc  mov     rcx, [rsp+118h+var_28]
0x180017b04  xor     rcx, rsp; StackCookie
0x180017b07  call    __security_check_cookie
0x180017b0c  mov     rbx, [rsp+118h+arg_18]
0x180017b14  add     rsp, 100h
0x180017b1b  pop     r14
0x180017b1d  pop     rdi
0x180017b1e  pop     rsi
0x180017b1f  retn
0x180017b20  mov     r8, cs:WPP_GLOBAL_Control
0x180017b27  lea     rax, WPP_GLOBAL_Control
0x180017b2e  cmp     r8, rax
0x180017b31  jz      short loc_180017AD3
0x180017b33  test    byte ptr [r8+1Ch], 1
0x180017b38  jz      short loc_180017AD3
0x180017b3a  mov     edx, 0Fh
0x180017b3f  mov     r9d, ecx
0x180017b42  mov     rcx, [r8+10h]
0x180017b46  jmp     loc_180017C75
0x180017b4b  cmp     edx, 1
0x180017b4e  jnz     short loc_180017AD3
0x180017b50  test    ecx, ecx
0x180017b52  jnz     loc_180017C21
0x180017b58  cmp     [rbx+8], ecx
0x180017b5b  jnz     loc_180017C21
0x180017b61  mov     r8, [rbx+18h]
0x180017b65  mov     rcx, rdi
0x180017b68  mov     rdx, [rbx+20h]
0x180017b6c  call    UbpmpStopAllConsumerActions
0x180017b71  jmp     loc_180017AD1
0x180017b76  cmp     dword ptr [rbx+8], 0FFFFFFFFh
0x180017b7a  jnz     loc_180017C8C
0x180017b80  mov     r8, cs:WPP_GLOBAL_Control
0x180017b87  lea     rax, WPP_GLOBAL_Control
0x180017b8e  cmp     r8, rax
0x180017b91  jz      loc_180017AD3
0x180017b97  test    byte ptr [r8+1Ch], 1
0x180017b9c  jz      loc_180017AD3
0x180017ba2  mov     edx, 0Bh
0x180017ba7  jmp     short loc_180017B3F
0x180017ba9  mov     r8, cs:WPP_GLOBAL_Control
0x180017bb0  lea     rax, WPP_GLOBAL_Control
0x180017bb7  cmp     r8, rax
0x180017bba  jz      loc_180017AD3
0x180017bc0  test    byte ptr [r8+1Ch], 1
0x180017bc5  jz      loc_180017AD3
0x180017bcb  mov     edx, 0Dh
0x180017bd0  jmp     loc_180017B3F
0x180017bd5  mov     r10, cs:WPP_GLOBAL_Control
0x180017bdc  lea     rax, WPP_GLOBAL_Control
0x180017be3  cmp     r10, rax
0x180017be6  jz      loc_180017AD3
0x180017bec  test    byte ptr [r10+1Ch], 1
0x180017bf1  jz      loc_180017AD3
0x180017bf7  mov     rax, [rdi+18h]
0x180017bfb  lea     r8, WPP_854cad5030553c91fcf88b43a20977bf_Traceguids
0x180017c02  mov     r9d, ecx
0x180017c05  mov     edx, 0Ah
0x180017c0a  mov     rcx, [r10+10h]
0x180017c0e  mov     rax, [rax+8]
0x180017c12  mov     [rsp+118h+var_F8], rax
0x180017c17  call    WPP_SF_LSd
0x180017c1c  jmp     loc_180017AD3
0x180017c21  mov     r8, cs:WPP_GLOBAL_Control
0x180017c28  lea     rax, WPP_GLOBAL_Control
0x180017c2f  cmp     r8, rax
0x180017c32  jz      loc_180017AD3
0x180017c38  test    byte ptr [r8+1Ch], 1
0x180017c3d  jz      loc_180017AD3
0x180017c43  mov     rax, [rdi+18h]
0x180017c47  mov     r9d, ecx
0x180017c4a  mov     rcx, [r8+10h]
0x180017c4e  mov     rdx, [rax+8]
0x180017c52  mov     eax, [rbx+8]
0x180017c55  mov     [rsp+118h+var_F0], rdx
0x180017c5a  mov     dword ptr [rsp+118h+var_F8], eax
0x180017c5e  call    WPP_SF_LdS
0x180017c63  jmp     loc_180017AD3
0x180017c68  mov     edx, 0Eh
0x180017c6d  mov     r9d, [rbx+4]
0x180017c71  mov     rcx, [rcx+10h]
0x180017c75  mov     rax, [rdi+18h]
0x180017c79  mov     rax, [rax+8]
0x180017c7d  mov     [rsp+118h+var_F8], rax
0x180017c82  call    WPP_SF_LS
0x180017c87  jmp     loc_180017AD3
0x180017c8c  test    cl, 8
0x180017c8f  jz      loc_180017A5F
0x180017c95  mov     r8, cs:WPP_GLOBAL_Control
0x180017c9c  lea     rax, WPP_GLOBAL_Control
0x180017ca3  cmp     r8, rax
0x180017ca6  jz      loc_180017AD3
0x180017cac  test    byte ptr [r8+1Ch], 1
0x180017cb1  jz      loc_180017AD3
0x180017cb7  mov     edx, 0Ch
0x180017cbc  jmp     loc_180017B3F
0x180017cc1  test    rax, rax
0x180017cc4  jz      short loc_180017CD7
0x180017cc6  mov     rcx, rax; pSid
0x180017cc9  call    cs:__imp_IsValidSid
0x180017ccf  test    eax, eax
0x180017cd1  jnz     loc_180017A7E
0x180017cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cde  lea     rax, WPP_GLOBAL_Control
0x180017ce5  cmp     rcx, rax
0x180017ce8  jz      loc_180017AD3
0x180017cee  test    byte ptr [rcx+1Ch], 1
0x180017cf2  jz      loc_180017AD3
0x180017cf8  jmp     loc_180017C68
0x180017cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d04  lea     rax, WPP_GLOBAL_Control
0x180017d0b  cmp     rcx, rax
0x180017d0e  jz      loc_180017AD3
0x180017d14  test    byte ptr [rcx+1Ch], 1
0x180017d18  jz      loc_180017AD3
0x180017d1e  mov     edx, 10h
0x180017d23  jmp     loc_180017C6D
0x180017d28  test    r8b, 6
0x180017d2c  jnz     loc_180017A8C
0x180017d32  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d39  lea     rax, WPP_GLOBAL_Control
0x180017d40  cmp     rcx, rax
0x180017d43  jz      loc_180017AD3
0x180017d49  test    byte ptr [rcx+1Ch], 1
0x180017d4d  jz      loc_180017AD3
0x180017d53  mov     edx, 11h
0x180017d58  mov     r9d, r8d
0x180017d5b  jmp     loc_180017C71
0x180017d60  int     2Ch; Windows NT - assertion failure
0x180017d62  jmp     loc_180017AF0
```
