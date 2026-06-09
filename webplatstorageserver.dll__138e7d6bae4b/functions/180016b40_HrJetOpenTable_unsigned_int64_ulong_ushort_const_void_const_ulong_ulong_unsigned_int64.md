# HrJetOpenTable(unsigned __int64,ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)

- ea: `0x180016b40`
- end: `0x180016d86`
- name: `?HrJetOpenTable@@YAJ_KKPEBGPEBXKKPEA_K@Z`
- size: `582`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, const unsigned __int16 *, const void *, unsigned int, JET_GRBIT, JET_TABLEID *)`
- caller_count: `31`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000a254`
- `0x18000b1c0`
- `0x18000c410`
- `0x18000c4f0`
- `0x18000f9d0`
- `0x1800107e0`
- `0x180011ed0`
- `0x1800163f0`
- `0x1800181e8`
- `0x180018358`
- `0x180020308`
- `0x180020c04`
- `0x1800215dc`
- `0x18002170c`
- `0x180021cc0`
- `0x1800300c0`
- `0x180042000`
- `0x180042d04`
- `0x1800448e4`
- `0x1800498d8`
- `0x18004f368`
- `0x180052cf0`
- `0x180054514`
- `0x180055edc`
- `0x180059654`
- `0x1800599a8`
- `0x180059fe8`
- `0x18006e980`
- `0x1800b818c`
- `0x1800b9b48`
- `0x1800bb384`

## callees

- `0x180016b40`
- `0x180037e10`
- `0x180080fb0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016d33`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180016d33`
- `ESENT!JetOpenTableW` at `0x180016b90`
- `ESENT!JetOpenTableW` at `0x180016b90`

## pseudocode

```c
__int64 __fastcall HrJetOpenTable(
        JET_SESID a1,
        JET_DBID a2,
        const unsigned __int16 *a3,
        const void *a4,
        unsigned int a5,
        JET_GRBIT grbit,
        JET_TABLEID *ptableid)
{
  const WCHAR *v7; // rdi
  JET_ERR v10; // ebx
  __int64 v11; // r10
  __int64 v12; // rax
  JET_TABLEID v13; // rcx
  unsigned int v14; // ecx
  int v16; // eax
  JET_ERR v17; // eax
  JET_GRBIT v19; // [rsp+40h] [rbp-B1h] BYREF
  JET_DBID v20; // [rsp+44h] [rbp-ADh] BYREF
  _DWORD v21[2]; // [rsp+48h] [rbp-A9h] BYREF
  JET_TABLEID v22; // [rsp+50h] [rbp-A1h] BYREF
  JET_SESID v23; // [rsp+58h] [rbp-99h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-91h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-81h] BYREF
  __int16 *v26; // [rsp+80h] [rbp-71h]
  int v27; // [rsp+88h] [rbp-69h]
  int v28; // [rsp+8Ch] [rbp-65h]
  _DWORD *v29; // [rsp+90h] [rbp-61h]
  __int64 v30; // [rsp+98h] [rbp-59h]
  JET_SESID *v31; // [rsp+A0h] [rbp-51h]
  __int64 v32; // [rsp+A8h] [rbp-49h]
  JET_DBID *v33; // [rsp+B0h] [rbp-41h]
  __int64 v34; // [rsp+B8h] [rbp-39h]
  const WCHAR *v35; // [rsp+C0h] [rbp-31h]
  int v36; // [rsp+C8h] [rbp-29h]
  int v37; // [rsp+CCh] [rbp-25h]
  JET_GRBIT *v38; // [rsp+D0h] [rbp-21h]
  __int64 v39; // [rsp+D8h] [rbp-19h]
  JET_TABLEID *v40; // [rsp+E0h] [rbp-11h]
  __int64 v41; // [rsp+E8h] [rbp-9h]

  v7 = a3;
  v10 = JetOpenTableW(a1, a2, a3, 0, 0, grbit, ptableid);
  v11 = *((_QWORD *)StorageServerProvider::Instance() + 1);
  if ( *(_DWORD *)v11 <= 5u
    || (*(_QWORD *)(v11 + 16) & 1) == 0
    || (*(_QWORD *)(v11 + 24) & 1LL) != *(_QWORD *)(v11 + 24) )
  {
    goto LABEL_18;
  }
  v12 = -1;
  if ( ptableid )
    v13 = *ptableid;
  else
    v13 = -1;
  v22 = v13;
  v19 = grbit;
  v20 = a2;
  v23 = a1;
  if ( !v10 )
    goto LABEL_12;
  if ( v10 >= 0 )
  {
    if ( v10 != 1007 )
    {
      v14 = (unsigned __int16)v10 | 0x8E5E0000;
      goto LABEL_13;
    }
LABEL_12:
    v14 = 0;
    goto LABEL_13;
  }
  v14 = (unsigned __int16)v10 | 0x8E5E0000;
LABEL_13:
  v21[0] = v14;
  v40 = &v22;
  v38 = &v19;
  v41 = 8;
  v39 = 4;
  if ( v7 )
  {
    while ( v7[++v12] != 0 )
      ;
    v16 = 2 * v12 + 2;
  }
  else
  {
    v7 = &word_1800D6108;
    v16 = 2;
  }
  v36 = v16;
  v35 = v7;
  v33 = &v20;
  v37 = 0;
  v31 = &v23;
  v34 = 4;
  v29 = v21;
  *(_DWORD *)&EventDescriptor.Level = 5;
  UserData.Ptr = *(_QWORD *)(v11 + 8);
  v32 = 8;
  v30 = 4;
  *(_DWORD *)&EventDescriptor.Id = 184549376;
  EventDescriptor.Keyword = 1;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v26 = word_1800FAD82;
  UserData.Reserved = 2;
  v27 = 80;
  v28 = 1;
  v21[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
  EventWriteTransfer(*(_QWORD *)(v11 + 32), &EventDescriptor, 0, 0, 8u, &UserData);
LABEL_18:
  v17 = 0;
  if ( v10 != 1327 )
    v17 = v10;
  if ( !v17 || v17 == 1007 )
    return 0;
  else
    return (unsigned __int16)v17 | 0x8E5E0000;
}

```

## disassembly

```asm
0x180016b40  mov     [rsp-8+arg_18], rbx
0x180016b45  push    rbp
0x180016b46  push    rsi
0x180016b47  push    rdi
0x180016b48  push    r12
0x180016b4a  push    r13
0x180016b4c  push    r14
0x180016b4e  push    r15
0x180016b50  lea     rbp, [rsp-0Fh]
0x180016b55  sub     rsp, 100h
0x180016b5c  mov     rax, cs:__security_cookie
0x180016b63  xor     rax, rsp
0x180016b66  mov     [rbp+3Fh+var_40], rax
0x180016b6a  mov     rsi, [rbp+3Fh+arg_30]
0x180016b6e  xor     r13d, r13d
0x180016b71  mov     r12d, [rbp+3Fh+arg_28]
0x180016b75  xor     r9d, r9d; pvParameters
0x180016b78  mov     [rsp+130h+ptableid], rsi; ptableid
0x180016b7d  mov     rdi, r8
0x180016b80  mov     [rsp+130h+grbit], r12d; grbit
0x180016b85  mov     r15d, edx
0x180016b88  mov     [rsp+130h+cbParameters], r13d; cbParameters
0x180016b8d  mov     r14, rcx
0x180016b90  call    cs:__imp_JetOpenTableW
0x180016b96  mov     ebx, eax
0x180016b98  call    ?Instance@StorageServerProvider@@KAPEAV1@XZ; StorageServerProvider::Instance(void)
0x180016b9d  mov     r10, [rax+8]
0x180016ba1  mov     eax, [r10]
0x180016ba4  cmp     eax, 5
0x180016ba7  jbe     loc_180016D39
0x180016bad  mov     rcx, [r10+18h]
0x180016bb1  mov     rax, [r10+10h]
0x180016bb5  test    al, 1
0x180016bb7  jz      loc_180016D39
0x180016bbd  mov     rax, rcx
0x180016bc0  and     eax, 1
0x180016bc3  cmp     rax, rcx
0x180016bc6  jnz     loc_180016D39
0x180016bcc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180016bd3  test    rsi, rsi
0x180016bd6  jz      short loc_180016BDD
0x180016bd8  mov     rcx, [rsi]
0x180016bdb  jmp     short loc_180016BE0
0x180016bdd  mov     rcx, rax
0x180016be0  mov     [rsp+130h+var_E0], rcx
0x180016be5  mov     [rsp+130h+var_F0], r12d
0x180016bea  mov     [rsp+130h+var_EC], r15d
0x180016bef  mov     [rsp+130h+var_D8], r14
0x180016bf4  test    ebx, ebx
0x180016bf6  jz      short loc_180016C18
0x180016bf8  jns     short loc_180016C05
0x180016bfa  movzx   ecx, bx
0x180016bfd  or      ecx, 8E5E0000h
0x180016c03  jmp     short loc_180016C1B
0x180016c05  cmp     ebx, 3EFh
0x180016c0b  jz      short loc_180016C18
0x180016c0d  movzx   ecx, bx
0x180016c10  or      ecx, 8E5E0000h
0x180016c16  jmp     short loc_180016C1B
0x180016c18  mov     ecx, r13d
0x180016c1b  mov     [rsp+130h+var_E8], ecx
0x180016c1f  lea     rcx, [rsp+130h+var_E0]
0x180016c24  mov     [rbp+3Fh+var_50], rcx
0x180016c28  lea     rcx, [rsp+130h+var_F0]
0x180016c2d  mov     [rbp+3Fh+var_60], rcx
0x180016c31  mov     [rbp+3Fh+var_48], 8
0x180016c39  mov     [rbp+3Fh+var_58], 4
0x180016c41  test    rdi, rdi
0x180016c44  jz      short loc_180016C65
0x180016c46  nop     word ptr [rax+rax+00000000h]
0x180016c50  cmp     [rdi+rax*2+2], r13w
0x180016c56  lea     rax, [rax+1]
0x180016c5a  jnz     short loc_180016C50
0x180016c5c  lea     eax, ds:2[rax*2]
0x180016c63  jmp     short loc_180016C71
0x180016c65  lea     rdi, word_1800D6108
0x180016c6c  mov     eax, 2
0x180016c71  mov     [rbp+3Fh+var_68], eax
0x180016c74  lea     rcx, _TraceLoggingMetadata
0x180016c7b  mov     [rbp+3Fh+var_70], rdi
0x180016c7f  lea     rax, [rsp+130h+var_EC]
0x180016c84  mov     [rbp+3Fh+var_80], rax
0x180016c88  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x180016c8d  mov     [rbp+3Fh+var_64], r13d
0x180016c91  lea     rax, [rsp+130h+var_D8]
0x180016c96  mov     [rbp+3Fh+var_90], rax
0x180016c9a  xor     r9d, r9d; RelatedActivityId
0x180016c9d  lea     rax, [rsp+130h+var_E8]
0x180016ca2  mov     [rbp+3Fh+var_78], 4
0x180016caa  mov     [rbp+3Fh+var_A0], rax
0x180016cae  xor     r8d, r8d; ActivityId
0x180016cb1  movzx   eax, cs:word_1800FAD78
0x180016cb8  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x180016cbc  mov     rax, [r10+8]
0x180016cc0  mov     [rsp+130h+UserData.Ptr], rax
0x180016cc5  mov     [rbp+3Fh+var_88], 8
0x180016ccd  mov     [rbp+3Fh+var_98], 4
0x180016cd5  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x180016cdd  mov     [rsp+130h+EventDescriptor.Keyword], 1
0x180016ce6  movzx   eax, word ptr [rax]
0x180016ce9  mov     [rbp+3Fh+UserData.Size], eax
0x180016cec  lea     rax, word_1800FAD82
0x180016cf3  mov     [rbp+3Fh+var_B0], rax
0x180016cf7  lea     rax, _TraceLoggingMetadataEnd
0x180016cfe  sub     eax, ecx
0x180016d00  mov     dword ptr [rbp+3Fh+UserData.0Ch], 2
0x180016d07  mov     [rbp+3Fh+var_A8], 50h ; 'P'
0x180016d0e  mov     [rbp+3Fh+var_A4], 1
0x180016d15  mov     [rsp+130h+var_E4], eax
0x180016d19  mov     eax, [rsp+130h+var_E4]
0x180016d1d  mov     rcx, [r10+20h]; RegHandle
0x180016d21  lea     rax, [rsp+130h+UserData]
0x180016d26  mov     qword ptr [rsp+130h+grbit], rax; UserData
0x180016d2b  mov     [rsp+130h+cbParameters], 8; UserDataCount
0x180016d33  call    cs:__imp_EventWriteTransfer
0x180016d39  cmp     ebx, 52Fh
0x180016d3f  mov     eax, r13d
0x180016d42  cmovnz  eax, ebx
0x180016d45  test    eax, eax
0x180016d47  jz      short loc_180016D5C
0x180016d49  jns     short loc_180016D55
0x180016d4b  movzx   eax, ax
0x180016d4e  or      eax, 8E5E0000h
0x180016d53  jmp     short loc_180016D5F
0x180016d55  cmp     eax, 3EFh
0x180016d5a  jnz     short loc_180016D4B
0x180016d5c  mov     eax, r13d
0x180016d5f  mov     rcx, [rbp+3Fh+var_40]
0x180016d63  xor     rcx, rsp; StackCookie
0x180016d66  call    __security_check_cookie
0x180016d6b  mov     rbx, [rsp+130h+arg_18]
0x180016d73  add     rsp, 100h
0x180016d7a  pop     r15
0x180016d7c  pop     r14
0x180016d7e  pop     r13
0x180016d80  pop     r12
0x180016d82  pop     rdi
0x180016d83  pop     rsi
0x180016d84  pop     rbp
0x180016d85  retn
```
