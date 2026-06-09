# HrJetCommitTransaction(unsigned __int64,ulong)

- ea: `0x180017c20`
- end: `0x180017d82`
- name: `?HrJetCommitTransaction@@YAJ_KK@Z`
- size: `354`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int)`
- caller_count: `26`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007678`
- `0x1800107e0`
- `0x1800163f0`
- `0x180017b70`
- `0x180017eb0`
- `0x180018358`
- `0x18002170c`
- `0x180021cc0`
- `0x1800300c0`
- `0x180030c04`
- `0x180031b60`
- `0x1800448e4`
- `0x180059768`
- `0x1800599a8`
- `0x180066c90`
- `0x18006ea94`
- `0x18007b368`
- `0x18007e0f4`
- `0x1800b809c`
- `0x1800ba108`
- `0x1800ba1d8`
- `0x1800ba34c`
- `0x1800ba8e4`
- `0x1800bab60`
- `0x1800bad5c`
- `0x1800bb060`

## callees

- `0x180017c20`
- `0x180037e10`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017d5b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017d5b`
- `ESENT!JetCommitTransaction` at `0x180017c47`
- `ESENT!JetCommitTransaction` at `0x180017c47`

## pseudocode

```c
__int64 __fastcall HrJetCommitTransaction(JET_SESID a1, JET_GRBIT a2)
{
  JET_ERR v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  JET_GRBIT v8; // [rsp+30h] [rbp-49h] BYREF
  _DWORD v9[3]; // [rsp+34h] [rbp-45h] BYREF
  JET_SESID v10; // [rsp+40h] [rbp-39h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-19h] BYREF
  char *v13; // [rsp+70h] [rbp-9h]
  int v14; // [rsp+78h] [rbp-1h]
  int v15; // [rsp+7Ch] [rbp+3h]
  _DWORD *v16; // [rsp+80h] [rbp+7h]
  __int64 v17; // [rsp+88h] [rbp+Fh]
  JET_SESID *v18; // [rsp+90h] [rbp+17h]
  __int64 v19; // [rsp+98h] [rbp+1Fh]
  JET_GRBIT *v20; // [rsp+A0h] [rbp+27h]
  __int64 v21; // [rsp+A8h] [rbp+2Fh]

  v4 = JetCommitTransaction(a1, a2);
  if ( !v4 )
    goto LABEL_6;
  if ( v4 >= 0 )
  {
    if ( v4 != 1007 )
    {
      v5 = (unsigned __int16)v4 | 0x8E5E0000;
      goto LABEL_7;
    }
LABEL_6:
    v5 = 0;
    goto LABEL_7;
  }
  v5 = (unsigned __int16)v4 | 0x8E5E0000;
LABEL_7:
  v6 = *((_QWORD *)StorageServerProvider::Instance() + 1);
  if ( *(_DWORD *)v6 > 5u && (*(_QWORD *)(v6 + 16) & 1) != 0 && (*(_QWORD *)(v6 + 24) & 1LL) == *(_QWORD *)(v6 + 24) )
  {
    v8 = a2;
    v20 = &v8;
    v10 = a1;
    v18 = &v10;
    v9[0] = v5;
    v16 = v9;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = *(_QWORD *)(v6 + 8);
    v21 = 4;
    v19 = 8;
    v17 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 1;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v13 = &byte_1800FB3CF;
    UserData.Reserved = 2;
    v14 = 56;
    v15 = 1;
    v9[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v6 + 32), &EventDescriptor, 0, 0, 5u, &UserData);
  }
  return v5;
}

```

## disassembly

```asm
0x180017c20  mov     [rsp-8+arg_10], rbx
0x180017c25  push    rbp
0x180017c26  push    rsi
0x180017c27  push    rdi
0x180017c28  lea     rbp, [rsp-47h]
0x180017c2d  sub     rsp, 0C0h
0x180017c34  mov     rax, cs:__security_cookie
0x180017c3b  xor     rax, rsp
0x180017c3e  mov     [rbp+57h+var_20], rax
0x180017c42  mov     esi, edx
0x180017c44  mov     rdi, rcx
0x180017c47  call    cs:__imp_JetCommitTransaction
0x180017c4d  test    eax, eax
0x180017c4f  jz      short loc_180017C70
0x180017c51  jns     short loc_180017C5E
0x180017c53  movzx   ebx, ax
0x180017c56  or      ebx, 8E5E0000h
0x180017c5c  jmp     short loc_180017C72
0x180017c5e  cmp     eax, 3EFh
0x180017c63  jz      short loc_180017C70
0x180017c65  movzx   ebx, ax
0x180017c68  or      ebx, 8E5E0000h
0x180017c6e  jmp     short loc_180017C72
0x180017c70  xor     ebx, ebx
0x180017c72  call    ?Instance@StorageServerProvider@@KAPEAV1@XZ; StorageServerProvider::Instance(void)
0x180017c77  mov     rcx, [rax+8]
0x180017c7b  mov     eax, [rcx]
0x180017c7d  cmp     eax, 5
0x180017c80  jbe     loc_180017D61
0x180017c86  mov     rdx, [rcx+18h]
0x180017c8a  mov     rax, [rcx+10h]
0x180017c8e  test    al, 1
0x180017c90  jz      loc_180017D61
0x180017c96  mov     rax, rdx
0x180017c99  and     eax, 1
0x180017c9c  cmp     rax, rdx
0x180017c9f  jnz     loc_180017D61
0x180017ca5  mov     [rbp+57h+var_A0], esi
0x180017ca8  lea     rax, [rbp+57h+var_A0]
0x180017cac  mov     [rbp+57h+var_30], rax
0x180017cb0  lea     rdx, _TraceLoggingMetadataEnd
0x180017cb7  mov     [rbp+57h+var_90], rdi
0x180017cbb  lea     rax, [rbp+57h+var_90]
0x180017cbf  mov     [rbp+57h+var_40], rax
0x180017cc3  xor     r9d, r9d; RelatedActivityId
0x180017cc6  lea     rax, [rbp+57h+var_9C]
0x180017cca  mov     [rbp+57h+var_9C], ebx
0x180017ccd  mov     [rbp+57h+var_50], rax
0x180017cd1  xor     r8d, r8d; ActivityId
0x180017cd4  movzx   eax, cs:word_1800FB3C5
0x180017cdb  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180017cde  mov     rax, [rcx+8]
0x180017ce2  mov     [rbp+57h+var_70.Ptr], rax
0x180017ce6  mov     [rbp+57h+var_28], 4
0x180017cee  mov     [rbp+57h+var_38], 8
0x180017cf6  mov     [rbp+57h+var_48], 4
0x180017cfe  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180017d05  mov     [rbp+57h+EventDescriptor.Keyword], 1
0x180017d0d  movzx   eax, word ptr [rax]
0x180017d10  mov     [rbp+57h+var_70.Size], eax
0x180017d13  lea     rax, byte_1800FB3CF
0x180017d1a  mov     [rbp+57h+var_60], rax
0x180017d1e  lea     rax, _TraceLoggingMetadata
0x180017d25  sub     edx, eax
0x180017d27  mov     dword ptr [rbp+57h+var_70.0Ch], 2
0x180017d2e  mov     [rbp+57h+var_58], 38h ; '8'
0x180017d35  lea     rax, [rbp+57h+var_70]
0x180017d39  mov     [rbp+57h+var_54], 1
0x180017d40  mov     [rbp+57h+var_98], edx
0x180017d43  mov     edx, [rbp+57h+var_98]
0x180017d46  mov     rcx, [rcx+20h]; RegHandle
0x180017d4a  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180017d4e  mov     [rsp+0D0h+UserData], rax; UserData
0x180017d53  mov     [rsp+0D0h+UserDataCount], 5; UserDataCount
0x180017d5b  call    cs:__imp_EventWriteTransfer
0x180017d61  mov     eax, ebx
0x180017d63  mov     rcx, [rbp+57h+var_20]
0x180017d67  xor     rcx, rsp; StackCookie
0x180017d6a  call    __security_check_cookie
0x180017d6f  mov     rbx, [rsp+0D0h+arg_10]
0x180017d77  add     rsp, 0C0h
0x180017d7e  pop     rdi
0x180017d7f  pop     rsi
0x180017d80  pop     rbp
0x180017d81  retn
```
