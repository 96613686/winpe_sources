# HrJetMove(unsigned __int64,unsigned __int64,long,ulong)

- ea: `0x18000c250`
- end: `0x18000c3ee`
- name: `?HrJetMove@@YAJ_K0JK@Z`
- size: `414`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, int, unsigned int)`
- caller_count: `30`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000af58`
- `0x18000bd90`
- `0x18000c000`
- `0x18000c0c8`
- `0x18000c12c`
- `0x18000c190`
- `0x18000c4f0`
- `0x18000f9d0`
- `0x1800107e0`
- `0x180011ed0`
- `0x180022b90`
- `0x1800263f0`
- `0x1800447a4`
- `0x1800448e4`
- `0x180054514`
- `0x1800578b8`
- `0x180067280`
- `0x18006e980`
- `0x18006ea94`
- `0x1800b8330`
- `0x1800b8630`
- `0x1800b8a94`
- `0x1800b8e38`
- `0x1800b8fb0`
- `0x1800b94dc`
- `0x1800b9798`
- `0x1800b9c74`
- `0x1800ba108`
- `0x1800bb4c8`
- `0x1800bb61c`

## callees

- `0x18000c250`
- `0x180037e10`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c3c8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c3c8`
- `ESENT!JetMove` at `0x18000c281`
- `ESENT!JetMove` at `0x18000c281`

## pseudocode

```c
__int64 __fastcall HrJetMove(JET_SESID a1, JET_TABLEID a2, int a3, JET_GRBIT a4)
{
  JET_ERR v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  JET_GRBIT v12; // [rsp+30h] [rbp-89h] BYREF
  int v13; // [rsp+34h] [rbp-85h] BYREF
  _DWORD v14[2]; // [rsp+38h] [rbp-81h] BYREF
  JET_TABLEID v15; // [rsp+40h] [rbp-79h] BYREF
  JET_SESID v16; // [rsp+48h] [rbp-71h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-59h] BYREF
  int *v19; // [rsp+70h] [rbp-49h]
  int v20; // [rsp+78h] [rbp-41h]
  int v21; // [rsp+7Ch] [rbp-3Dh]
  _DWORD *v22; // [rsp+80h] [rbp-39h]
  __int64 v23; // [rsp+88h] [rbp-31h]
  JET_SESID *v24; // [rsp+90h] [rbp-29h]
  __int64 v25; // [rsp+98h] [rbp-21h]
  JET_TABLEID *v26; // [rsp+A0h] [rbp-19h]
  __int64 v27; // [rsp+A8h] [rbp-11h]
  int *v28; // [rsp+B0h] [rbp-9h]
  __int64 v29; // [rsp+B8h] [rbp-1h]
  JET_GRBIT *v30; // [rsp+C0h] [rbp+7h]
  __int64 v31; // [rsp+C8h] [rbp+Fh]

  v8 = JetMove(a1, a2, a3, a4);
  if ( !v8 )
    goto LABEL_6;
  if ( v8 >= 0 )
  {
    if ( v8 != 1007 )
    {
      v9 = (unsigned __int16)v8 | 0x8E5E0000;
      goto LABEL_7;
    }
LABEL_6:
    v9 = 0;
    goto LABEL_7;
  }
  v9 = (unsigned __int16)v8 | 0x8E5E0000;
LABEL_7:
  v10 = *((_QWORD *)StorageServerProvider::Instance() + 1);
  if ( *(_DWORD *)v10 > 5u && (*(_QWORD *)(v10 + 16) & 1) != 0 && (*(_QWORD *)(v10 + 24) & 1LL) == *(_QWORD *)(v10 + 24) )
  {
    v12 = a4;
    v30 = &v12;
    v13 = a3;
    v28 = &v13;
    v15 = a2;
    v26 = &v15;
    v16 = a1;
    v24 = &v16;
    v22 = v14;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = *(_QWORD *)(v10 + 8);
    v14[0] = v9;
    v31 = 4;
    v29 = 4;
    v27 = 8;
    v25 = 8;
    v23 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 1;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v19 = &dword_1800FAE7C;
    UserData.Reserved = 2;
    v20 = 60;
    v21 = 1;
    v14[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v10 + 32), &EventDescriptor, 0, 0, 7u, &UserData);
  }
  return v9;
}

```

## disassembly

```asm
0x18000c250  push    rbp
0x18000c252  push    rbx
0x18000c253  push    rsi
0x18000c254  push    rdi
0x18000c255  push    r12
0x18000c257  push    r14
0x18000c259  push    r15
0x18000c25b  lea     rbp, [rsp-27h]
0x18000c260  sub     rsp, 0E0h
0x18000c267  mov     rax, cs:__security_cookie
0x18000c26e  xor     rax, rsp
0x18000c271  mov     [rbp+57h+var_40], rax
0x18000c275  mov     r15d, r9d
0x18000c278  mov     r14d, r8d
0x18000c27b  mov     rsi, rdx
0x18000c27e  mov     rdi, rcx
0x18000c281  call    cs:__imp_JetMove
0x18000c287  xor     r12d, r12d
0x18000c28a  test    eax, eax
0x18000c28c  jz      short loc_18000C2AD
0x18000c28e  jns     short loc_18000C29B
0x18000c290  movzx   ebx, ax
0x18000c293  or      ebx, 8E5E0000h
0x18000c299  jmp     short loc_18000C2B0
0x18000c29b  cmp     eax, 3EFh
0x18000c2a0  jz      short loc_18000C2AD
0x18000c2a2  movzx   ebx, ax
0x18000c2a5  or      ebx, 8E5E0000h
0x18000c2ab  jmp     short loc_18000C2B0
0x18000c2ad  mov     ebx, r12d
0x18000c2b0  call    ?Instance@StorageServerProvider@@KAPEAV1@XZ; StorageServerProvider::Instance(void)
0x18000c2b5  mov     rcx, [rax+8]
0x18000c2b9  mov     eax, [rcx]
0x18000c2bb  cmp     eax, 5
0x18000c2be  jbe     loc_18000C3CE
0x18000c2c4  mov     rdx, [rcx+18h]
0x18000c2c8  mov     rax, [rcx+10h]
0x18000c2cc  test    al, 1
0x18000c2ce  jz      loc_18000C3CE
0x18000c2d4  mov     rax, rdx
0x18000c2d7  and     eax, 1
0x18000c2da  cmp     rax, rdx
0x18000c2dd  jnz     loc_18000C3CE
0x18000c2e3  mov     [rsp+110h+var_E0], r15d
0x18000c2e8  lea     rax, [rsp+110h+var_E0]
0x18000c2ed  mov     [rbp+57h+var_50], rax
0x18000c2f1  lea     rdx, _TraceLoggingMetadataEnd
0x18000c2f8  mov     [rsp+110h+var_DC], r14d
0x18000c2fd  lea     rax, [rsp+110h+var_DC]
0x18000c302  mov     [rbp+57h+var_60], rax
0x18000c306  xor     r9d, r9d; RelatedActivityId
0x18000c309  mov     [rbp+57h+var_D0], rsi
0x18000c30d  lea     rax, [rbp+57h+var_D0]
0x18000c311  mov     [rbp+57h+var_70], rax
0x18000c315  xor     r8d, r8d; ActivityId
0x18000c318  mov     [rbp+57h+var_C8], rdi
0x18000c31c  lea     rax, [rbp+57h+var_C8]
0x18000c320  mov     [rbp+57h+var_80], rax
0x18000c324  lea     rax, [rsp+110h+var_D8]
0x18000c329  mov     [rbp+57h+var_90], rax
0x18000c32d  movzx   eax, cs:word_1800FAE72
0x18000c334  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000c337  mov     rax, [rcx+8]
0x18000c33b  mov     [rbp+57h+var_B0.Ptr], rax
0x18000c33f  mov     [rsp+110h+var_D8], ebx
0x18000c343  mov     [rbp+57h+var_48], 4
0x18000c34b  mov     [rbp+57h+var_58], 4
0x18000c353  mov     [rbp+57h+var_68], 8
0x18000c35b  mov     [rbp+57h+var_78], 8
0x18000c363  mov     [rbp+57h+var_88], 4
0x18000c36b  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000c372  mov     [rbp+57h+EventDescriptor.Keyword], 1
0x18000c37a  movzx   eax, word ptr [rax]
0x18000c37d  mov     [rbp+57h+var_B0.Size], eax
0x18000c380  lea     rax, dword_1800FAE7C
0x18000c387  mov     [rbp+57h+var_A0], rax
0x18000c38b  lea     rax, _TraceLoggingMetadata
0x18000c392  sub     edx, eax
0x18000c394  mov     dword ptr [rbp+57h+var_B0.0Ch], 2
0x18000c39b  mov     [rbp+57h+var_98], 3Ch ; '<'
0x18000c3a2  lea     rax, [rbp+57h+var_B0]
0x18000c3a6  mov     [rbp+57h+var_94], 1
0x18000c3ad  mov     [rbp+57h+var_D4], edx
0x18000c3b0  mov     edx, [rbp+57h+var_D4]
0x18000c3b3  mov     rcx, [rcx+20h]; RegHandle
0x18000c3b7  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000c3bb  mov     [rsp+110h+UserData], rax; UserData
0x18000c3c0  mov     [rsp+110h+UserDataCount], 7; UserDataCount
0x18000c3c8  call    cs:__imp_EventWriteTransfer
0x18000c3ce  mov     eax, ebx
0x18000c3d0  mov     rcx, [rbp+57h+var_40]
0x18000c3d4  xor     rcx, rsp; StackCookie
0x18000c3d7  call    __security_check_cookie
0x18000c3dc  add     rsp, 0E0h
0x18000c3e3  pop     r15
0x18000c3e5  pop     r14
0x18000c3e7  pop     r12
0x18000c3e9  pop     rdi
0x18000c3ea  pop     rsi
0x18000c3eb  pop     rbx
0x18000c3ec  pop     rbp
0x18000c3ed  retn
```
