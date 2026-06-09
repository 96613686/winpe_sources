# User::StreamIn(unsigned __int64,uchar * &,uchar const *)

- ea: `0x18001d1e0`
- end: `0x18001d5bf`
- name: `?StreamIn@User@@QEAAJ_KAEAPEAEPEBE@Z`
- size: `991`
- prototype: `__int64 __fastcall(User *__hidden this, unsigned __int64, unsigned __int8 **, const unsigned __int8 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180015a60`
- `0x18001d5d0`
- `0x180074960`

## callees

- `0x18000fe50`
- `0x180017740`
- `0x180017820`
- `0x18001d1e0`
- `0x18003bd70`
- `0x180044548`
- `0x18004da18`
- `0x18004f2b0`
- `0x18007e258`
- `0x180082a40`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001d392`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d566`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d392`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d566`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d4df`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d4df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d3b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d3cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d587`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d5a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d3b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d3cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d587`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d5a3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001d297`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001d2aa`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001d297`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001d2aa`

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
  _QWORD *v21; // rax
  LPVOID v22; // rdi
  void *v23; // r8
  _QWORD *v24; // rax
  int v25; // eax
  int v26; // eax
  const wchar_t **v27; // rax
  BSTR *v28; // rbx
  BSTR v29; // r8
  LPVOID lpMem; // [rsp+30h] [rbp-69h] BYREF
  LPVOID v31; // [rsp+38h] [rbp-61h] BYREF
  enum _SID_NAME_USE v32; // [rsp+40h] [rbp-59h]
  const wchar_t *v33; // [rsp+48h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-39h] BYREF
  int *v36; // [rsp+70h] [rbp-29h]
  int v37; // [rsp+78h] [rbp-21h]
  int v38; // [rsp+7Ch] [rbp-1Dh]
  const wchar_t **v39; // [rsp+80h] [rbp-19h]
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
    v21 = (_QWORD *)User::CreateAlias(&v33, &lpMem);
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
      if ( (unsigned int)dword_1800C0358 > 4 )
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
        UserData.Ptr = (ULONGLONG)off_1800C0360;
        UserData.Size = *(unsigned __int16 *)off_1800C0360;
        UserData.Reserved = 2;
        v36 = &dword_1800B1674;
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
0x18001d1e0  push    rbp
0x18001d1e2  push    rbx
0x18001d1e3  push    rsi
0x18001d1e4  push    rdi
0x18001d1e5  push    r12
0x18001d1e7  push    r13
0x18001d1e9  push    r14
0x18001d1eb  push    r15
0x18001d1ed  lea     rbp, [rsp-1Fh]
0x18001d1f2  sub     rsp, 0B8h
0x18001d1f9  mov     rax, cs:__security_cookie
0x18001d200  xor     rax, rsp
0x18001d203  mov     [rbp+57h+var_50], rax
0x18001d207  mov     r15, r9
0x18001d20a  mov     rdi, r8
0x18001d20d  mov     r12, rcx
0x18001d210  mov     rax, [r8]
0x18001d213  lea     rdx, [rax+8]
0x18001d217  cmp     rdx, r9
0x18001d21a  ja      loc_18001D2BF
0x18001d220  movzx   eax, byte ptr [rax]
0x18001d223  mov     [r8], rdx
0x18001d226  test    al, al
0x18001d228  jz      short loc_18001D23A
0x18001d22a  xor     edx, edx
0x18001d22c  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18001d231  xor     esi, esi
0x18001d233  mov     ebx, esi
0x18001d235  jmp     loc_18001D2C4
0x18001d23a  lea     rax, [rdx+8]
0x18001d23e  cmp     rax, r15
0x18001d241  ja      short loc_18001D2BF
0x18001d243  movzx   r13d, byte ptr [rdx]
0x18001d247  mov     [r8], rax
0x18001d24a  xor     esi, esi
0x18001d24c  mov     r8d, 0FFFFFFF8h
0x18001d252  test    r13b, r13b
0x18001d255  jnz     loc_18001D2EF
0x18001d25b  lea     rcx, [rax+8]
0x18001d25f  cmp     rcx, r15
0x18001d262  ja      short loc_18001D2BF
0x18001d264  mov     eax, [rax]
0x18001d266  mov     [rbp+57h+var_B0], eax
0x18001d269  mov     [rdi], rcx
0x18001d26c  lea     rbx, [rcx+8]
0x18001d270  cmp     rbx, r15
0x18001d273  ja      short loc_18001D2BF
0x18001d275  mov     edx, [rcx]
0x18001d277  mov     [rdi], rbx
0x18001d27a  lea     ecx, [rdx+7]
0x18001d27d  and     rcx, r8
0x18001d280  add     rcx, rbx
0x18001d283  cmp     rcx, r15
0x18001d286  ja      short loc_18001D2BF
0x18001d288  test    edx, edx
0x18001d28a  jz      short loc_18001D2BA
0x18001d28c  mov     [rdi], rcx
0x18001d28f  test    rbx, rbx
0x18001d292  jz      short loc_18001D2BA
0x18001d294  mov     rcx, rbx; pSid
0x18001d297  call    cs:__imp_IsValidSid
0x18001d29e  nop     dword ptr [rax+rax+00h]
0x18001d2a3  test    eax, eax
0x18001d2a5  jnz     short loc_18001D2E7
0x18001d2a7  mov     rcx, rbx; pSid
0x18001d2aa  call    cs:__imp_IsValidSid
0x18001d2b1  nop     dword ptr [rax+rax+00h]
0x18001d2b6  test    eax, eax
0x18001d2b8  jnz     short loc_18001D2BF
0x18001d2ba  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001d2bf  mov     ebx, 8000FFFFh
0x18001d2c4  mov     eax, ebx
0x18001d2c6  mov     rcx, [rbp+57h+var_50]
0x18001d2ca  xor     rcx, rsp; StackCookie
0x18001d2cd  call    __security_check_cookie
0x18001d2d2  add     rsp, 0B8h
0x18001d2d9  pop     r15
0x18001d2db  pop     r14
0x18001d2dd  pop     r13
0x18001d2df  pop     r12
0x18001d2e1  pop     rdi
0x18001d2e2  pop     rsi
0x18001d2e3  pop     rbx
0x18001d2e4  pop     rbp
0x18001d2e5  retn
0x18001d2e7  mov     r8d, 0FFFFFFF8h
0x18001d2ed  jmp     short loc_18001D2F9
0x18001d2ef  mov     rbx, rsi
0x18001d2f2  mov     [rbp+57h+var_B0], 8
0x18001d2f9  mov     rax, [rdi]
0x18001d2fc  lea     r14, [rax+8]
0x18001d300  cmp     r14, r15
0x18001d303  ja      short loc_18001D2BF
0x18001d305  mov     ecx, [rax]
0x18001d307  mov     [rdi], r14
0x18001d30a  lea     edx, [rcx+7]
0x18001d30d  and     rdx, r8
0x18001d310  add     rdx, r14
0x18001d313  cmp     rdx, r15
0x18001d316  ja      short loc_18001D2BF
0x18001d318  test    ecx, ecx
0x18001d31a  jz      short loc_18001D321
0x18001d31c  mov     [rdi], rdx
0x18001d31f  jmp     short loc_18001D324
0x18001d321  mov     r14, rsi
0x18001d324  lea     rcx, [rbp+57h+lpMem]; this
0x18001d328  test    r13b, r13b
0x18001d32b  jz      loc_18001D3E0
0x18001d331  mov     ebx, esi
0x18001d333  mov     rdx, r14; unsigned __int16 *
0x18001d336  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001d33b  nop
0x18001d33c  lea     rdx, [rbp+57h+lpMem]
0x18001d340  lea     rcx, [rbp+57h+var_A8]
0x18001d344  call    ?CreateAlias@User@@SA?AV1@AEBV_bstr_t@@@Z; User::CreateAlias(_bstr_t const &)
0x18001d349  mov     rdx, [rax]
0x18001d34c  mov     rcx, r12
0x18001d34f  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18001d354  lea     rcx, [rbp+57h+var_A8]
0x18001d358  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001d35d  nop
0x18001d35e  mov     rdi, [rbp+57h+lpMem]
0x18001d362  test    rdi, rdi
0x18001d365  jz      loc_18001D2C4
0x18001d36b  mov     r14d, 0FFFFFFFFh
0x18001d371  lock xadd [rdi+10h], r14d
0x18001d377  cmp     r14d, 1
0x18001d37b  jnz     loc_18001D2C4
0x18001d381  test    rdi, rdi
0x18001d384  jz      loc_18001D2C4
0x18001d38a  mov     rcx, [rdi]; bstrString
0x18001d38d  test    rcx, rcx
0x18001d390  jz      short loc_18001D3A1
0x18001d392  call    cs:__imp_SysFreeString
0x18001d399  nop     dword ptr [rax+rax+00h]
0x18001d39e  mov     [rdi], rsi
0x18001d3a1  mov     r8, [rdi+8]; lpMem
0x18001d3a5  test    r8, r8
0x18001d3a8  jz      short loc_18001D3C3
0x18001d3aa  xor     edx, edx; dwFlags
0x18001d3ac  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001d3b3  call    cs:__imp_HeapFree
0x18001d3ba  nop     dword ptr [rax+rax+00h]
0x18001d3bf  mov     [rdi+8], rsi
0x18001d3c3  mov     r8, rdi; lpMem
0x18001d3c6  xor     edx, edx; dwFlags
0x18001d3c8  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001d3cf  call    cs:__imp_HeapFree
0x18001d3d6  nop     dword ptr [rax+rax+00h]
0x18001d3db  jmp     loc_18001D2C4
0x18001d3e0  mov     rdx, rbx
0x18001d3e3  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x18001d3e8  mov     rdx, [rax]
0x18001d3eb  mov     rcx, r12
0x18001d3ee  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18001d3f3  lea     rcx, [rbp+57h+lpMem]
0x18001d3f7  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001d3fc  cmp     [r12], rsi
0x18001d400  jnz     loc_18001D233
0x18001d406  mov     rdi, rsi
0x18001d409  mov     [rbp+57h+lpMem], rsi
0x18001d40d  test    r14, r14
0x18001d410  jnz     loc_18001D502
0x18001d416  mov     rdx, rbx; Sid
0x18001d419  lea     rcx, [rbp+57h+lpMem]; this
0x18001d41d  call    ?FromSidToDomainAccount@User@@CAJAEAV_bstr_t@@PEAX@Z; User::FromSidToDomainAccount(_bstr_t &,void *)
0x18001d422  test    eax, eax
0x18001d424  jns     loc_18001D4F1
0x18001d42a  mov     ecx, cs:dword_1800C0358
0x18001d430  cmp     ecx, 4
0x18001d433  jbe     loc_18001D4EB
0x18001d439  mov     dword ptr [rbp+57h+var_A8], eax
0x18001d43c  movzx   eax, byte ptr [rbx+1]
0x18001d440  lea     eax, ds:8[rax*4]
0x18001d447  mov     [rbp+57h+var_60], rbx
0x18001d44b  mov     [rbp+57h+var_58], eax
0x18001d44e  mov     [rbp+57h+var_54], esi
0x18001d451  lea     rax, [rbp+57h+var_A8]
0x18001d455  mov     [rbp+57h+var_70], rax
0x18001d459  mov     [rbp+57h+var_68], 4
0x18001d461  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18001d468  movzx   eax, cs:word_1800B166A
0x18001d46f  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18001d472  mov     [rbp+57h+EventDescriptor.Keyword], rsi
0x18001d476  mov     rax, cs:off_1800C0360
0x18001d47d  mov     [rbp+57h+var_90.Ptr], rax
0x18001d481  movzx   eax, word ptr [rax]
0x18001d484  mov     [rbp+57h+var_90.Size], eax
0x18001d487  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x18001d48e  lea     rax, dword_1800B1674
0x18001d495  mov     [rbp+57h+var_80], rax
0x18001d499  mov     [rbp+57h+var_78], 3Dh ; '='
0x18001d4a0  mov     [rbp+57h+var_74], 1
0x18001d4a7  lea     rax, _TraceLoggingMetadataEnd
0x18001d4ae  lea     rcx, _TraceLoggingMetadata
0x18001d4b5  sub     eax, ecx
0x18001d4b7  mov     dword ptr [rbp+57h+var_B8], eax
0x18001d4ba  mov     eax, dword ptr [rbp+57h+var_B8]
0x18001d4bd  lea     rax, [rbp+57h+var_90]
0x18001d4c1  mov     [rsp+0F0h+UserData], rax; UserData
0x18001d4c6  mov     [rsp+0F0h+UserDataCount], 4; UserDataCount
0x18001d4ce  xor     r9d, r9d; RelatedActivityId
0x18001d4d1  xor     r8d, r8d; ActivityId
0x18001d4d4  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18001d4d8  mov     rcx, cs:RegHandle; RegHandle
0x18001d4df  call    cs:__imp_EventWriteTransfer
0x18001d4e6  nop     dword ptr [rax+rax+00h]
0x18001d4eb  mov     rdi, [rbp+57h+lpMem]
0x18001d4ef  jmp     short loc_18001D502
0x18001d4f1  mov     rdi, [rbp+57h+lpMem]
0x18001d4f5  test    rdi, rdi
0x18001d4f8  jz      short loc_18001D4FF
0x18001d4fa  mov     r14, [rdi]
0x18001d4fd  jmp     short loc_18001D502
0x18001d4ff  mov     r14, rsi
0x18001d502  mov     rdx, r14; unsigned __int16 *
0x18001d505  lea     rcx, [rbp+57h+var_B8]; this
0x18001d509  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18001d50e  nop
0x18001d50f  mov     byte ptr [rsp+0F0h+UserDataCount], 1
0x18001d514  mov     r9, rbx
0x18001d517  mov     r8d, [rbp+57h+var_B0]
0x18001d51b  lea     rdx, [rbp+57h+var_B8]
0x18001d51f  lea     rcx, [rbp+57h+var_A8]
0x18001d523  call    ?CreateUser@User@@SA?AV1@AEBV_bstr_t@@W4_SID_NAME_USE@@PEAX_N@Z; User::CreateUser(_bstr_t const &,_SID_NAME_USE,void *,bool)
0x18001d528  mov     rdx, [rax]
0x18001d52b  mov     rcx, r12
0x18001d52e  call    ??4?$AutoRef@UUserEntry@User@@@wmi@@QEAAAEAV01@PEAUUserEntry@User@@@Z; wmi::AutoRef<User::UserEntry>::operator=(User::UserEntry *)
0x18001d533  lea     rcx, [rbp+57h+var_A8]
0x18001d537  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18001d53c  nop
0x18001d53d  mov     r14d, 0FFFFFFFFh
0x18001d543  mov     rbx, [rbp+57h+var_B8]
0x18001d547  test    rbx, rbx
0x18001d54a  jz      short loc_18001D5AF
0x18001d54c  mov     eax, r14d
0x18001d54f  lock xadd [rbx+10h], eax
0x18001d554  cmp     eax, 1
0x18001d557  jnz     short loc_18001D5AF
0x18001d559  test    rbx, rbx
0x18001d55c  jz      short loc_18001D5AF
0x18001d55e  mov     rcx, [rbx]; bstrString
0x18001d561  test    rcx, rcx
0x18001d564  jz      short loc_18001D575
0x18001d566  call    cs:__imp_SysFreeString
0x18001d56d  nop     dword ptr [rax+rax+00h]
0x18001d572  mov     [rbx], rsi
0x18001d575  mov     r8, [rbx+8]; lpMem
0x18001d579  test    r8, r8
0x18001d57c  jz      short loc_18001D597
0x18001d57e  xor     edx, edx; dwFlags
0x18001d580  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001d587  call    cs:__imp_HeapFree
0x18001d58e  nop     dword ptr [rax+rax+00h]
0x18001d593  mov     [rbx+8], rsi
0x18001d597  mov     r8, rbx; lpMem
0x18001d59a  xor     edx, edx; dwFlags
0x18001d59c  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18001d5a3  call    cs:__imp_HeapFree
0x18001d5aa  nop     dword ptr [rax+rax+00h]
0x18001d5af  mov     ebx, esi
0x18001d5b1  test    rdi, rdi
0x18001d5b4  jz      loc_18001D2C4
0x18001d5ba  jmp     loc_18001D371
```
