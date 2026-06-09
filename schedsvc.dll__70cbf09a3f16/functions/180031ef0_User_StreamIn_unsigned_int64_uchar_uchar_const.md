# User::StreamIn(unsigned __int64,uchar * &,uchar const *)

- ea: `0x180031ef0`
- end: `0x180032295`
- name: `?StreamIn@User@@QEAAJ_KAEAPEAEPEBE@Z`
- size: `933`
- prototype: `__int64 __fastcall(User *__hidden this, unsigned __int64, unsigned __int8 **, const unsigned __int8 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180031120`
- `0x180032650`
- `0x180071010`

## callees

- `0x18000b4e0`
- `0x1800290f0`
- `0x18002ab90`
- `0x18002ac60`
- `0x180031ef0`
- `0x1800421e8`
- `0x18004b5b4`
- `0x18004cfb0`
- `0x18007a0b0`
- `0x18007e6d0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180032092`
- `OLEAUT32!__imp_SysFreeString` at `0x18003224e`
- `OLEAUT32!__imp_SysFreeString` at `0x180032092`
- `OLEAUT32!__imp_SysFreeString` at `0x18003224e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800321cd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800321cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800320ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800320c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032269`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003227f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800320ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800320c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032269`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003227f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180031fa4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180031fb1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180031fa4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180031fb1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall User::StreamIn(User *this, __int64 a2, unsigned __int8 **a3, unsigned __int8 *a4)
{
  unsigned __int8 *v7; // rdx
  char v8; // al
  unsigned int v9; // ebx
  unsigned __int8 *v10; // rax
  unsigned __int8 v11; // r13
  __int64 v12; // r8
  unsigned __int8 *v13; // rcx
  unsigned __int8 *v14; // rbx
  __int64 v15; // rdx
  unsigned __int8 *v16; // rcx
  unsigned __int8 *v18; // r14
  int v19; // ecx
  unsigned __int8 *v20; // rdx
  User::UserEntry **v21; // rax
  LPVOID v22; // rdi
  void *v23; // r8
  _QWORD *v24; // rax
  int v25; // eax
  int v26; // eax
  User::UserEntry **v27; // rax
  BSTR *v28; // rbx
  BSTR v29; // r8
  LPVOID lpMem; // [rsp+30h] [rbp-69h] BYREF
  LPVOID v31; // [rsp+38h] [rbp-61h] BYREF
  enum _SID_NAME_USE v32; // [rsp+40h] [rbp-59h]
  User::UserEntry *v33; // [rsp+48h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-39h] BYREF
  int *v36; // [rsp+70h] [rbp-29h]
  int v37; // [rsp+78h] [rbp-21h]
  int v38; // [rsp+7Ch] [rbp-1Dh]
  User::UserEntry **v39; // [rsp+80h] [rbp-19h]
  __int64 v40; // [rsp+88h] [rbp-11h]
  unsigned __int8 *v41; // [rsp+90h] [rbp-9h]
  int v42; // [rsp+98h] [rbp-1h]
  int v43; // [rsp+9Ch] [rbp+3h]

  v7 = *a3 + 8;
  if ( v7 > a4 )
    return (unsigned int)-2147418113;
  v8 = **a3;
  *a3 = v7;
  if ( v8 )
  {
    wmi::AutoRef<User::UserEntry>::operator=(this, 0);
    return 0;
  }
  v10 = v7 + 8;
  if ( v7 + 8 > a4 )
    return (unsigned int)-2147418113;
  v11 = *v7;
  *a3 = v10;
  v12 = 4294967288LL;
  if ( v11 )
  {
    v14 = 0;
    v32 = SidTypeUnknown;
  }
  else
  {
    v13 = v7 + 16;
    if ( v7 + 16 > a4 )
      return (unsigned int)-2147418113;
    v32 = *(_DWORD *)v10;
    *a3 = v13;
    v14 = v7 + 24;
    if ( v7 + 24 > a4 )
      return (unsigned int)-2147418113;
    v15 = *(unsigned int *)v13;
    *a3 = v14;
    v16 = &v14[((_DWORD)v15 + 7) & 0xFFFFFFF8];
    if ( v16 > a4 )
      return (unsigned int)-2147418113;
    if ( !(_DWORD)v15 )
      goto LABEL_14;
    *a3 = v16;
    if ( !v14 )
      goto LABEL_14;
    if ( !IsValidSid(v14) )
    {
      if ( !IsValidSid(v14) )
LABEL_14:
        MicrosoftTelemetryAssertTriggeredNoArgs(v16, v15, v12);
      return (unsigned int)-2147418113;
    }
  }
  v18 = *a3 + 8;
  if ( v18 > a4 )
    return (unsigned int)-2147418113;
  v19 = *(_DWORD *)*a3;
  *a3 = v18;
  v20 = &v18[(v19 + 7) & 0xFFFFFFF8];
  if ( v20 > a4 )
    return (unsigned int)-2147418113;
  if ( v19 )
    *a3 = v20;
  else
    v18 = 0;
  if ( v11 )
  {
    v9 = 0;
    _bstr_t::_bstr_t((_bstr_t *)&lpMem, (const unsigned __int16 *)v18);
    v21 = User::CreateAlias(&v33, (const struct _bstr_t *)&lpMem);
    wmi::AutoRef<User::UserEntry>::operator=(this, *v21);
    wmi::AutoRef<User::UserEntry>::Release(&v33);
    v22 = lpMem;
    if ( !lpMem )
      return v9;
LABEL_26:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v22 + 4, 0xFFFFFFFF) == 1 && v22 )
    {
      if ( *(_QWORD *)v22 )
      {
        SysFreeString(*(BSTR *)v22);
        *(_QWORD *)v22 = 0;
      }
      v23 = (void *)*((_QWORD *)v22 + 1);
      if ( v23 )
      {
        HeapFree(g_PrivateHeap, 0, v23);
        *((_QWORD *)v22 + 1) = 0;
      }
      HeapFree(g_PrivateHeap, 0, v22);
    }
    return v9;
  }
  v24 = (_QWORD *)User::LookupUser(&lpMem, v14);
  wmi::AutoRef<User::UserEntry>::operator=(this, *v24);
  wmi::AutoRef<User::UserEntry>::Release(&lpMem);
  if ( *(_QWORD *)this )
    return 0;
  v22 = 0;
  lpMem = 0;
  if ( !v18 )
  {
    v25 = User::FromSidToDomainAccount((struct _bstr_t *)&lpMem, v14);
    if ( v25 >= 0 )
    {
      v22 = lpMem;
      if ( lpMem )
        v18 = *(unsigned __int8 **)lpMem;
      else
        v18 = 0;
    }
    else
    {
      if ( (unsigned int)dword_1800BC358 > 4 )
      {
        LODWORD(v33) = v25;
        v26 = 4 * v14[1] + 8;
        v41 = v14;
        v42 = v26;
        v43 = 0;
        v39 = &v33;
        v40 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 4;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_1800BC360;
        UserData.Size = *(unsigned __int16 *)off_1800BC360;
        UserData.Reserved = 2;
        v36 = &dword_1800AD62C;
        v37 = 61;
        v38 = 1;
        LODWORD(v31) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
      }
      v22 = lpMem;
    }
  }
  _bstr_t::_bstr_t((_bstr_t *)&v31, (const unsigned __int16 *)v18);
  v27 = User::CreateUser(&v33, (const wchar_t ***)&v31, v32, v14, 1);
  wmi::AutoRef<User::UserEntry>::operator=(this, *v27);
  wmi::AutoRef<User::UserEntry>::Release(&v33);
  v28 = (BSTR *)v31;
  if ( v31 && _InterlockedExchangeAdd((volatile signed __int32 *)v31 + 4, 0xFFFFFFFF) == 1 && v28 )
  {
    if ( *v28 )
    {
      SysFreeString(*v28);
      *v28 = 0;
    }
    v29 = v28[1];
    if ( v29 )
    {
      HeapFree(g_PrivateHeap, 0, v29);
      v28[1] = 0;
    }
    HeapFree(g_PrivateHeap, 0, v28);
  }
  v9 = 0;
  if ( v22 )
    goto LABEL_26;
  return v9;
}

```

## disassembly

```asm
0x180031ef0  push    rbp
0x180031ef2  push    rbx
0x180031ef3  push    rsi
0x180031ef4  push    rdi
0x180031ef5  push    r12
0x180031ef7  push    r13
0x180031ef9  push    r14
0x180031efb  push    r15
0x180031efd  lea     rbp, [rsp-1Fh]
0x180031f02  sub     rsp, 0B8h
0x180031f09  mov     rax, cs:__security_cookie
0x180031f10  xor     rax, rsp
0x180031f13  mov     [rbp+57h+var_50], rax
0x180031f17  mov     r15, r9
0x180031f1a  mov     rdi, r8
0x180031f1d  mov     r12, rcx
0x180031f20  mov     rax, [r8]
0x180031f23  lea     rdx, [rax+8]
0x180031f27  cmp     rdx, r9
0x180031f2a  ja      loc_180031FC0
0x180031f30  movzx   eax, byte ptr [rax]
0x180031f33  mov     [r8], rdx
0x180031f36  test    al, al
0x180031f38  jz      short loc_180031F47
0x180031f3a  xor     edx, edx
0x180031f3c  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180031f41  xor     esi, esi
0x180031f43  mov     ebx, esi
0x180031f45  jmp     short loc_180031FC5
0x180031f47  lea     rax, [rdx+8]
0x180031f4b  cmp     rax, r15
0x180031f4e  ja      short loc_180031FC0
0x180031f50  movzx   r13d, byte ptr [rdx]
0x180031f54  mov     [r8], rax
0x180031f57  xor     esi, esi
0x180031f59  mov     r8d, 0FFFFFFF8h
0x180031f5f  test    r13b, r13b
0x180031f62  jnz     loc_180031FEF
0x180031f68  lea     rcx, [rax+8]
0x180031f6c  cmp     rcx, r15
0x180031f6f  ja      short loc_180031FC0
0x180031f71  mov     eax, [rax]
0x180031f73  mov     [rbp+57h+var_B0], eax
0x180031f76  mov     [rdi], rcx
0x180031f79  lea     rbx, [rcx+8]
0x180031f7d  cmp     rbx, r15
0x180031f80  ja      short loc_180031FC0
0x180031f82  mov     edx, [rcx]
0x180031f84  mov     [rdi], rbx
0x180031f87  lea     ecx, [rdx+7]
0x180031f8a  and     rcx, r8
0x180031f8d  add     rcx, rbx
0x180031f90  cmp     rcx, r15
0x180031f93  ja      short loc_180031FC0
0x180031f95  test    edx, edx
0x180031f97  jz      short loc_180031FBB
0x180031f99  mov     [rdi], rcx
0x180031f9c  test    rbx, rbx
0x180031f9f  jz      short loc_180031FBB
0x180031fa1  mov     rcx, rbx; pSid
0x180031fa4  call    cs:__imp_IsValidSid
0x180031faa  test    eax, eax
0x180031fac  jnz     short loc_180031FE7
0x180031fae  mov     rcx, rbx; pSid
0x180031fb1  call    cs:__imp_IsValidSid
0x180031fb7  test    eax, eax
0x180031fb9  jnz     short loc_180031FC0
0x180031fbb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031fc0  mov     ebx, 8000FFFFh
0x180031fc5  mov     eax, ebx
0x180031fc7  mov     rcx, [rbp+57h+var_50]
0x180031fcb  xor     rcx, rsp; StackCookie
0x180031fce  call    __security_check_cookie
0x180031fd3  add     rsp, 0B8h
0x180031fda  pop     r15
0x180031fdc  pop     r14
0x180031fde  pop     r13
0x180031fe0  pop     r12
0x180031fe2  pop     rdi
0x180031fe3  pop     rsi
0x180031fe4  pop     rbx
0x180031fe5  pop     rbp
0x180031fe6  retn
0x180031fe7  mov     r8d, 0FFFFFFF8h
0x180031fed  jmp     short loc_180031FF9
0x180031fef  mov     rbx, rsi
0x180031ff2  mov     [rbp+57h+var_B0], 8
0x180031ff9  mov     rax, [rdi]
0x180031ffc  lea     r14, [rax+8]
0x180032000  cmp     r14, r15
0x180032003  ja      short loc_180031FC0
0x180032005  mov     ecx, [rax]
0x180032007  mov     [rdi], r14
0x18003200a  lea     edx, [rcx+7]
0x18003200d  and     rdx, r8
0x180032010  add     rdx, r14
0x180032013  cmp     rdx, r15
0x180032016  ja      short loc_180031FC0
0x180032018  test    ecx, ecx
0x18003201a  jz      short loc_180032021
0x18003201c  mov     [rdi], rdx
0x18003201f  jmp     short loc_180032024
0x180032021  mov     r14, rsi
0x180032024  lea     rcx, [rbp+57h+lpMem]; this
0x180032028  test    r13b, r13b
0x18003202b  jz      loc_1800320CE
0x180032031  mov     ebx, esi
0x180032033  mov     rdx, r14; unsigned __int16 *
0x180032036  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003203b  nop
0x18003203c  lea     rdx, [rbp+57h+lpMem]
0x180032040  lea     rcx, [rbp+57h+var_A8]
0x180032044  call    ?CreateAlias@User@@SA?AV1@AEBV_bstr_t@@@Z; User::CreateAlias(_bstr_t const &)
0x180032049  mov     rdx, [rax]
0x18003204c  mov     rcx, r12
0x18003204f  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x180032054  lea     rcx, [rbp+57h+var_A8]
0x180032058  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18003205d  nop
0x18003205e  mov     rdi, [rbp+57h+lpMem]
0x180032062  test    rdi, rdi
0x180032065  jz      loc_180031FC5
0x18003206b  mov     r14d, 0FFFFFFFFh
0x180032071  lock xadd [rdi+10h], r14d
0x180032077  cmp     r14d, 1
0x18003207b  jnz     loc_180031FC5
0x180032081  test    rdi, rdi
0x180032084  jz      loc_180031FC5
0x18003208a  mov     rcx, [rdi]; bstrString
0x18003208d  test    rcx, rcx
0x180032090  jz      short loc_18003209B
0x180032092  call    cs:__imp_SysFreeString
0x180032098  mov     [rdi], rsi
0x18003209b  mov     r8, [rdi+8]; lpMem
0x18003209f  test    r8, r8
0x1800320a2  jz      short loc_1800320B7
0x1800320a4  xor     edx, edx; dwFlags
0x1800320a6  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800320ad  call    cs:__imp_HeapFree
0x1800320b3  mov     [rdi+8], rsi
0x1800320b7  mov     r8, rdi; lpMem
0x1800320ba  xor     edx, edx; dwFlags
0x1800320bc  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x1800320c3  call    cs:__imp_HeapFree
0x1800320c9  jmp     loc_180031FC5
0x1800320ce  mov     rdx, rbx
0x1800320d1  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x1800320d6  mov     rdx, [rax]
0x1800320d9  mov     rcx, r12
0x1800320dc  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x1800320e1  lea     rcx, [rbp+57h+lpMem]
0x1800320e5  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800320ea  cmp     [r12], rsi
0x1800320ee  jnz     loc_180031F43
0x1800320f4  mov     rdi, rsi
0x1800320f7  mov     [rbp+57h+lpMem], rsi
0x1800320fb  test    r14, r14
0x1800320fe  jnz     loc_1800321EA
0x180032104  mov     rdx, rbx; Sid
0x180032107  lea     rcx, [rbp+57h+lpMem]; this
0x18003210b  call    ?FromSidToDomainAccount@User@@CAJAEAV_bstr_t@@PEAX@Z; User::FromSidToDomainAccount(_bstr_t &,void *)
0x180032110  test    eax, eax
0x180032112  jns     loc_1800321D9
0x180032118  mov     ecx, cs:dword_1800BC358
0x18003211e  cmp     ecx, 4
0x180032121  jbe     loc_1800321D3
0x180032127  mov     dword ptr [rbp+57h+var_A8], eax
0x18003212a  movzx   eax, byte ptr [rbx+1]
0x18003212e  lea     eax, ds:8[rax*4]
0x180032135  mov     [rbp+57h+var_60], rbx
0x180032139  mov     [rbp+57h+var_58], eax
0x18003213c  mov     [rbp+57h+var_54], esi
0x18003213f  lea     rax, [rbp+57h+var_A8]
0x180032143  mov     [rbp+57h+var_70], rax
0x180032147  mov     [rbp+57h+var_68], 4
0x18003214f  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180032156  movzx   eax, cs:word_1800AD622
0x18003215d  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180032160  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x180032164  mov     rax, cs:off_1800BC360
0x18003216b  mov     [rbp+57h+var_90.Ptr], rax
0x18003216f  movzx   eax, word ptr [rax]
0x180032172  mov     [rbp+57h+var_90.Size], eax
0x180032175  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x18003217c  lea     rax, dword_1800AD62C
0x180032183  mov     [rbp+57h+var_80], rax
0x180032187  mov     [rbp+57h+var_78], 3Dh ; '='
0x18003218e  mov     [rbp+57h+var_74], 1
0x180032195  lea     rax, _TraceLoggingMetadataEnd
0x18003219c  lea     rcx, _TraceLoggingMetadata
0x1800321a3  sub     eax, ecx
0x1800321a5  mov     dword ptr [rbp+57h+var_B8], eax
0x1800321a8  mov     eax, dword ptr [rbp+57h+var_B8]
0x1800321ab  lea     rax, [rbp+57h+var_90]
0x1800321af  mov     [rsp+0F0h+UserData], rax; UserData
0x1800321b4  mov     [rsp+0F0h+UserDataCount], 4; UserDataCount
0x1800321bc  xor     r9d, r9d; RelatedActivityId
0x1800321bf  xor     r8d, r8d; ActivityId
0x1800321c2  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1800321c6  mov     rcx, cs:RegHandle; RegHandle
0x1800321cd  call    cs:__imp_EventWriteTransfer
0x1800321d3  mov     rdi, [rbp+57h+lpMem]
0x1800321d7  jmp     short loc_1800321EA
0x1800321d9  mov     rdi, [rbp+57h+lpMem]
0x1800321dd  test    rdi, rdi
0x1800321e0  jz      short loc_1800321E7
0x1800321e2  mov     r14, [rdi]
0x1800321e5  jmp     short loc_1800321EA
0x1800321e7  mov     r14, rsi
0x1800321ea  mov     rdx, r14; unsigned __int16 *
0x1800321ed  lea     rcx, [rbp+57h+var_B8]; this
0x1800321f1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800321f6  nop
0x1800321f7  mov     byte ptr [rsp+0F0h+UserDataCount], 1
0x1800321fc  mov     r9, rbx
0x1800321ff  mov     r8d, [rbp+57h+var_B0]
0x180032203  lea     rdx, [rbp+57h+var_B8]
0x180032207  lea     rcx, [rbp+57h+var_A8]
0x18003220b  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@W4_SID_NAME_USE@@PEAX_N@Z; User::CreateUser(_bstr_t const &,_SID_NAME_USE,void *,bool)
0x180032210  mov     rdx, [rax]
0x180032213  mov     rcx, r12
0x180032216  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18003221b  lea     rcx, [rbp+57h+var_A8]
0x18003221f  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180032224  nop
0x180032225  mov     r14d, 0FFFFFFFFh
0x18003222b  mov     rbx, [rbp+57h+var_B8]
0x18003222f  test    rbx, rbx
0x180032232  jz      short loc_180032285
0x180032234  mov     eax, r14d
0x180032237  lock xadd [rbx+10h], eax
0x18003223c  cmp     eax, 1
0x18003223f  jnz     short loc_180032285
0x180032241  test    rbx, rbx
0x180032244  jz      short loc_180032285
0x180032246  mov     rcx, [rbx]; bstrString
0x180032249  test    rcx, rcx
0x18003224c  jz      short loc_180032257
0x18003224e  call    cs:__imp_SysFreeString
0x180032254  mov     [rbx], rsi
0x180032257  mov     r8, [rbx+8]; lpMem
0x18003225b  test    r8, r8
0x18003225e  jz      short loc_180032273
0x180032260  xor     edx, edx; dwFlags
0x180032262  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180032269  call    cs:__imp_HeapFree
0x18003226f  mov     [rbx+8], rsi
0x180032273  mov     r8, rbx; lpMem
0x180032276  xor     edx, edx; dwFlags
0x180032278  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18003227f  call    cs:__imp_HeapFree
0x180032285  mov     ebx, esi
0x180032287  test    rdi, rdi
0x18003228a  jz      loc_180031FC5
0x180032290  jmp     loc_180032071
```
