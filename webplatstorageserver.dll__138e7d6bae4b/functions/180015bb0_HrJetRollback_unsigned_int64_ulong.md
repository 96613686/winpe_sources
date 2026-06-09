# HrJetRollback(unsigned __int64,ulong)

- ea: `0x180015bb0`
- end: `0x180015d0a`
- name: `?HrJetRollback@@YAJ_KK@Z`
- size: `346`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int)`
- caller_count: `14`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800107e0`
- `0x180014bb0`
- `0x1800163f0`
- `0x180017618`
- `0x180018358`
- `0x18002170c`
- `0x180021cc0`
- `0x180022784`
- `0x18002ff40`
- `0x1800300c0`
- `0x180031b60`
- `0x1800448e4`
- `0x1800b2dbc`
- `0x1800bab60`

## callees

- `0x180015bb0`
- `0x180037e10`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015cea`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180015cea`
- `ESENT!JetRollback` at `0x180015bd4`
- `ESENT!JetRollback` at `0x180015bd4`

## pseudocode

```c
__int64 __fastcall HrJetRollback(JET_SESID a1)
{
  JET_ERR v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v6; // [rsp+30h] [rbp-59h] BYREF
  _DWORD v7[3]; // [rsp+34h] [rbp-55h] BYREF
  JET_SESID v8; // [rsp+40h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-29h] BYREF
  char *v11; // [rsp+70h] [rbp-19h]
  int v12; // [rsp+78h] [rbp-11h]
  int v13; // [rsp+7Ch] [rbp-Dh]
  _DWORD *v14; // [rsp+80h] [rbp-9h]
  __int64 v15; // [rsp+88h] [rbp-1h]
  JET_SESID *v16; // [rsp+90h] [rbp+7h]
  __int64 v17; // [rsp+98h] [rbp+Fh]
  int *v18; // [rsp+A0h] [rbp+17h]
  __int64 v19; // [rsp+A8h] [rbp+1Fh]

  v2 = JetRollback(a1, 0);
  if ( !v2 )
    goto LABEL_6;
  if ( v2 >= 0 )
  {
    if ( v2 != 1007 )
    {
      v3 = (unsigned __int16)v2 | 0x8E5E0000;
      goto LABEL_7;
    }
LABEL_6:
    v3 = 0;
    goto LABEL_7;
  }
  v3 = (unsigned __int16)v2 | 0x8E5E0000;
LABEL_7:
  v4 = *((_QWORD *)StorageServerProvider::Instance() + 1);
  if ( *(_DWORD *)v4 > 5u && (*(_QWORD *)(v4 + 16) & 1) != 0 && (*(_QWORD *)(v4 + 24) & 1LL) == *(_QWORD *)(v4 + 24) )
  {
    v6 = 0;
    v18 = &v6;
    v8 = a1;
    v16 = &v8;
    v7[0] = v3;
    v14 = v7;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = *(_QWORD *)(v4 + 8);
    v19 = 4;
    v17 = 8;
    v15 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 1;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v11 = byte_1800FABBD;
    UserData.Reserved = 2;
    v12 = 47;
    v13 = 1;
    v7[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v4 + 32), &EventDescriptor, 0, 0, 5u, &UserData);
  }
  return v3;
}

```

## disassembly

```asm
0x180015bb0  push    rbp
0x180015bb2  push    rbx
0x180015bb3  push    rsi
0x180015bb4  push    rdi
0x180015bb5  lea     rbp, [rsp-3Fh]
0x180015bba  sub     rsp, 0C8h
0x180015bc1  mov     rax, cs:__security_cookie
0x180015bc8  xor     rax, rsp
0x180015bcb  mov     [rbp+57h+var_30], rax
0x180015bcf  xor     edx, edx; grbit
0x180015bd1  mov     rdi, rcx
0x180015bd4  call    cs:__imp_JetRollback
0x180015bda  xor     esi, esi
0x180015bdc  test    eax, eax
0x180015bde  jz      short loc_180015BFF
0x180015be0  jns     short loc_180015BED
0x180015be2  movzx   ebx, ax
0x180015be5  or      ebx, 8E5E0000h
0x180015beb  jmp     short loc_180015C01
0x180015bed  cmp     eax, 3EFh
0x180015bf2  jz      short loc_180015BFF
0x180015bf4  movzx   ebx, ax
0x180015bf7  or      ebx, 8E5E0000h
0x180015bfd  jmp     short loc_180015C01
0x180015bff  mov     ebx, esi
0x180015c01  call    ?Instance@StorageServerProvider@@KAPEAV1@XZ; StorageServerProvider::Instance(void)
0x180015c06  mov     rcx, [rax+8]
0x180015c0a  mov     eax, [rcx]
0x180015c0c  cmp     eax, 5
0x180015c0f  jbe     loc_180015CF0
0x180015c15  mov     rdx, [rcx+18h]
0x180015c19  mov     rax, [rcx+10h]
0x180015c1d  test    al, 1
0x180015c1f  jz      loc_180015CF0
0x180015c25  mov     rax, rdx
0x180015c28  and     eax, 1
0x180015c2b  cmp     rax, rdx
0x180015c2e  jnz     loc_180015CF0
0x180015c34  mov     [rbp+57h+var_B0], esi
0x180015c37  lea     rax, [rbp+57h+var_B0]
0x180015c3b  mov     [rbp+57h+var_40], rax
0x180015c3f  lea     rdx, _TraceLoggingMetadataEnd
0x180015c46  mov     [rbp+57h+var_A0], rdi
0x180015c4a  lea     rax, [rbp+57h+var_A0]
0x180015c4e  mov     [rbp+57h+var_50], rax
0x180015c52  xor     r9d, r9d; RelatedActivityId
0x180015c55  lea     rax, [rbp+57h+var_AC]
0x180015c59  mov     [rbp+57h+var_AC], ebx
0x180015c5c  mov     [rbp+57h+var_60], rax
0x180015c60  xor     r8d, r8d; ActivityId
0x180015c63  movzx   eax, cs:word_1800FABB3
0x180015c6a  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180015c6d  mov     rax, [rcx+8]
0x180015c71  mov     [rbp+57h+var_80.Ptr], rax
0x180015c75  mov     [rbp+57h+var_38], 4
0x180015c7d  mov     [rbp+57h+var_48], 8
0x180015c85  mov     [rbp+57h+var_58], 4
0x180015c8d  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180015c94  mov     [rbp+57h+EventDescriptor.Keyword], 1
0x180015c9c  movzx   eax, word ptr [rax]
0x180015c9f  mov     [rbp+57h+var_80.Size], eax
0x180015ca2  lea     rax, byte_1800FABBD
0x180015ca9  mov     [rbp+57h+var_70], rax
0x180015cad  lea     rax, _TraceLoggingMetadata
0x180015cb4  sub     edx, eax
0x180015cb6  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180015cbd  mov     [rbp+57h+var_68], 2Fh ; '/'
0x180015cc4  lea     rax, [rbp+57h+var_80]
0x180015cc8  mov     [rbp+57h+var_64], 1
0x180015ccf  mov     [rbp+57h+var_A8], edx
0x180015cd2  mov     edx, [rbp+57h+var_A8]
0x180015cd5  mov     rcx, [rcx+20h]; RegHandle
0x180015cd9  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180015cdd  mov     [rsp+0E0h+UserData], rax; UserData
0x180015ce2  mov     [rsp+0E0h+UserDataCount], 5; UserDataCount
0x180015cea  call    cs:__imp_EventWriteTransfer
0x180015cf0  mov     eax, ebx
0x180015cf2  mov     rcx, [rbp+57h+var_30]
0x180015cf6  xor     rcx, rsp; StackCookie
0x180015cf9  call    __security_check_cookie
0x180015cfe  add     rsp, 0C8h
0x180015d05  pop     rdi
0x180015d06  pop     rsi
0x180015d07  pop     rbx
0x180015d08  pop     rbp
0x180015d09  retn
```
