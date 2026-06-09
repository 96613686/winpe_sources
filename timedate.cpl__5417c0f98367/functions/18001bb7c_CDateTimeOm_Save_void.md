# CDateTimeOm::Save(void)

- ea: `0x18001bb7c`
- end: `0x18001be4c`
- name: `?Save@CDateTimeOm@@QEAAJXZ`
- size: `720`
- prototype: `__int64 __fastcall(CDateTimeOm *__hidden this)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x1800057f0`
- `0x18000a670`
- `0x18001e290`

## callees

- `0x18000893c`
- `0x1800089c8`
- `0x1800092c4`
- `0x18000ed64`
- `0x18000ed94`
- `0x18000edbc`
- `0x18000eec0`
- `0x18000ef8c`
- `0x18001bb7c`
- `0x18001c450`
- `0x18001c560`
- `0x18001ca60`
- `0x18001cab0`
- `0x180028f2e`
- `0x180028f60`
- `0x18002a010`

## import_xrefs

- `SHLWAPI!__imp_SHRegSetValue` at `0x18001bdeb`
- `SHLWAPI!__imp_SHRegSetValue` at `0x18001bdeb`

## pseudocode

```c
__int64 __fastcall CDateTimeOm::Save(CDateTimeOm *this)
{
  int v2; // esi
  int v3; // edi
  int v4; // eax
  unsigned __int64 v5; // r11
  int v6; // eax
  int v7; // r14d
  int v8; // eax
  int v10; // [rsp+20h] [rbp-E0h]
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v12[128]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v2 = 0;
  if ( !*((_DWORD *)this + 110) && !*((_DWORD *)this + 111) )
  {
    if ( *((_DWORD *)this + 112) )
      goto LABEL_7;
    if ( !*((_DWORD *)this + 113) )
    {
      v3 = 0;
      goto LABEL_14;
    }
  }
  if ( !*((_DWORD *)this + 112) )
  {
LABEL_13:
    v3 = 1;
    goto LABEL_14;
  }
LABEL_7:
  if ( !(unsigned int)CDateTimeOm::get_CanModifyTimeZone(this) )
    goto LABEL_13;
  memset_0(v12, 0, sizeof(v12));
  v4 = StringCchCopyW(v12, 0x80u, (const unsigned __int16 *)this + 86);
  v2 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"shell\\cpls\\utc\\om.cpp",
      (const char *)(unsigned int)v4,
      v10);
LABEL_12:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"shell\\cpls\\utc\\om.cpp",
      (const char *)(unsigned int)v2,
      v10);
    goto LABEL_13;
  }
  if ( !*((_DWORD *)this + 107) )
  {
    v2 = StringCchCatW(v12, v5, L"_dstoff");
    if ( v2 < 0 )
      goto LABEL_12;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 14) + 64LL))(
         *((_QWORD *)this + 14),
         v12);
  v2 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"shell\\cpls\\utc\\om.cpp",
      (const char *)(unsigned int)v8,
      v10);
    LogSetTimeZoneError(v12, v2);
    goto LABEL_13;
  }
  *((_DWORD *)this + 112) = 0;
  v11.Ptr = (ULONGLONG)v12;
  v3 = 1;
  v11.Size = GetEtwStringByteSize(v12);
  v11.Reserved = 0;
  DateTimeEventWrite(&DATETIME_ETW_EVENT_SET_TIMEZONE_SUCCESS, 1u, &v11);
LABEL_14:
  if ( (*((_DWORD *)this + 110) || *((_DWORD *)this + 111)) && (unsigned int)CDateTimeOm::get_CanModifyDateTime(this) )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 14) + 48LL))(
           *((_QWORD *)this + 14),
           (char *)this + 156);
    v7 = v6;
    if ( v6 >= 0 )
    {
      *((_QWORD *)this + 55) = 0;
      LogSetLocalTimeSuccess((const struct _SYSTEMTIME *)((char *)this + 156));
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1D5,
        (unsigned int)"shell\\cpls\\utc\\om.cpp",
        (const char *)(unsigned int)v6,
        v10);
      v2 = v7;
      LogSetLocalTimeError((const struct _SYSTEMTIME *)((char *)this + 156), v7);
    }
  }
  if ( *((_DWORD *)this + 113) )
  {
    SHRegSetValue((LPCWSTR)0xFFFFFFFF80000001LL, L"Control Panel\\TimeDate");
    *((_DWORD *)this + 113) = 0;
  }
  if ( v3 )
  {
    CDateTimeOm::_PollTime(this);
    CDateTimeOm::_OnChange(this, 3);
    CDateTimeOm::_OnChange(this, 10);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001bb7c  mov     [rsp-8+arg_8], rbx
0x18001bb81  mov     [rsp-8+arg_10], rsi
0x18001bb86  push    rbp
0x18001bb87  push    rdi
0x18001bb88  push    r12
0x18001bb8a  push    r14
0x18001bb8c  push    r15
0x18001bb8e  lea     rbp, [rsp-70h]
0x18001bb93  sub     rsp, 170h
0x18001bb9a  mov     rax, cs:__security_cookie
0x18001bba1  xor     rax, rsp
0x18001bba4  mov     [rbp+90h+var_30], rax
0x18001bba8  xor     r12d, r12d
0x18001bbab  mov     rbx, rcx
0x18001bbae  mov     esi, r12d
0x18001bbb1  cmp     [rcx+1B8h], r12d
0x18001bbb8  jnz     short loc_18001BBDD
0x18001bbba  cmp     [rcx+1BCh], r12d
0x18001bbc1  jnz     short loc_18001BBDD
0x18001bbc3  cmp     [rcx+1C0h], r12d
0x18001bbca  jnz     short loc_18001BBEA
0x18001bbcc  cmp     [rcx+1C4h], r12d
0x18001bbd3  jnz     short loc_18001BBDD
0x18001bbd5  mov     edi, r12d
0x18001bbd8  jmp     loc_18001BC91
0x18001bbdd  cmp     [rcx+1C0h], r12d
0x18001bbe4  jz      loc_18001BC8C
0x18001bbea  call    ?get_CanModifyTimeZone@CDateTimeOm@@QEAAHXZ; CDateTimeOm::get_CanModifyTimeZone(void)
0x18001bbef  test    eax, eax
0x18001bbf1  jz      loc_18001BC8C
0x18001bbf7  xor     edx, edx; Val
0x18001bbf9  lea     rcx, [rsp+190h+var_130]; void *
0x18001bbfe  mov     r8d, 100h; Size
0x18001bc04  call    memset_0
0x18001bc09  mov     r11d, 80h
0x18001bc0f  lea     r8, [rbx+0ACh]; unsigned __int16 *
0x18001bc16  mov     edx, r11d; unsigned __int64
0x18001bc19  lea     rcx, [rsp+190h+var_130]; unsigned __int16 *
0x18001bc1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001bc23  mov     esi, eax
0x18001bc25  test    eax, eax
0x18001bc27  jns     short loc_18001BC46
0x18001bc29  mov     rcx, [rbp+98h]; this
0x18001bc30  lea     r8, aShellCplsUtcOm; "shell\\cpls\\utc\\om.cpp"
0x18001bc37  mov     r9d, eax; char *
0x18001bc3a  mov     edx, 1B9h; void *
0x18001bc3f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001bc44  jmp     short loc_18001BC71
0x18001bc46  cmp     [rbx+1ACh], r12d
0x18001bc4d  jnz     loc_18001BD0A
0x18001bc53  lea     r8, pszSrc; "_dstoff"
0x18001bc5a  mov     rdx, r11; unsigned __int64
0x18001bc5d  lea     rcx, [rsp+190h+var_130]; unsigned __int16 *
0x18001bc62  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bc67  mov     esi, eax
0x18001bc69  test    eax, eax
0x18001bc6b  jns     loc_18001BD0A
0x18001bc71  mov     rcx, [rbp+98h]; this
0x18001bc78  lea     r8, aShellCplsUtcOm; "shell\\cpls\\utc\\om.cpp"
0x18001bc7f  mov     r9d, esi; char *
0x18001bc82  mov     edx, 1BEh; void *
0x18001bc87  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001bc8c  mov     edi, 1
0x18001bc91  cmp     [rbx+1B8h], r12d
0x18001bc98  jnz     short loc_18001BCA7
0x18001bc9a  cmp     [rbx+1BCh], r12d
0x18001bca1  jz      loc_18001BDA1
0x18001bca7  mov     rcx, rbx; this
0x18001bcaa  call    ?get_CanModifyDateTime@CDateTimeOm@@QEAAHXZ; CDateTimeOm::get_CanModifyDateTime(void)
0x18001bcaf  test    eax, eax
0x18001bcb1  jz      loc_18001BDA1
0x18001bcb7  mov     rcx, [rbx+70h]
0x18001bcbb  lea     r15, [rbx+9Ch]
0x18001bcc2  mov     rdx, r15
0x18001bcc5  mov     rax, [rcx]
0x18001bcc8  mov     rax, [rax+30h]
0x18001bccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcd1  mov     r14d, eax
0x18001bcd4  test    eax, eax
0x18001bcd6  jns     loc_18001BD92
0x18001bcdc  mov     rcx, [rbp+98h]; this
0x18001bce3  lea     r8, aShellCplsUtcOm; "shell\\cpls\\utc\\om.cpp"
0x18001bcea  mov     r9d, eax; char *
0x18001bced  mov     edx, 1D5h; void *
0x18001bcf2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001bcf7  mov     edx, r14d; int
0x18001bcfa  mov     rcx, r15; struct _SYSTEMTIME *
0x18001bcfd  mov     esi, r14d
0x18001bd00  call    ?LogSetLocalTimeError@@YAJPEBU_SYSTEMTIME@@J@Z; LogSetLocalTimeError(_SYSTEMTIME const *,long)
0x18001bd05  jmp     loc_18001BDA1
0x18001bd0a  mov     rcx, [rbx+70h]
0x18001bd0e  lea     rdx, [rsp+190h+var_130]
0x18001bd13  mov     rax, [rcx]
0x18001bd16  mov     rax, [rax+40h]
0x18001bd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd1f  mov     esi, eax
0x18001bd21  test    eax, eax
0x18001bd23  jns     short loc_18001BD51
0x18001bd25  mov     rcx, [rbp+98h]; this
0x18001bd2c  lea     r8, aShellCplsUtcOm; "shell\\cpls\\utc\\om.cpp"
0x18001bd33  mov     r9d, eax; char *
0x18001bd36  mov     edx, 1C2h; void *
0x18001bd3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001bd40  mov     edx, esi; int
0x18001bd42  lea     rcx, [rsp+190h+var_130]; unsigned __int16 *
0x18001bd47  call    ?LogSetTimeZoneError@@YAJPEBGJ@Z; LogSetTimeZoneError(ushort const *,long)
0x18001bd4c  jmp     loc_18001BC8C
0x18001bd51  lea     rax, [rsp+190h+var_130]
0x18001bd56  mov     [rbx+1C0h], r12d
0x18001bd5d  lea     rcx, [rsp+190h+var_130]; unsigned __int16 *
0x18001bd62  mov     [rsp+190h+var_148.Ptr], rax
0x18001bd67  call    ?GetEtwStringByteSize@@YAKPEBG@Z; GetEtwStringByteSize(ushort const *)
0x18001bd6c  mov     edi, 1
0x18001bd71  mov     [rsp+190h+var_148.Size], eax
0x18001bd75  mov     edx, edi; unsigned int
0x18001bd77  mov     dword ptr [rsp+190h+var_148.0Ch], r12d
0x18001bd7c  lea     r8, [rsp+190h+var_148]; struct _EVENT_DATA_DESCRIPTOR *
0x18001bd81  lea     rcx, DATETIME_ETW_EVENT_SET_TIMEZONE_SUCCESS; struct _EVENT_DESCRIPTOR *
0x18001bd88  call    ?DateTimeEventWrite@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; DateTimeEventWrite(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18001bd8d  jmp     loc_18001BC91
0x18001bd92  mov     rcx, r15; struct _SYSTEMTIME *
0x18001bd95  mov     [rbx+1B8h], r12
0x18001bd9c  call    ?LogSetLocalTimeSuccess@@YAJPEBU_SYSTEMTIME@@@Z; LogSetLocalTimeSuccess(_SYSTEMTIME const *)
0x18001bda1  cmp     [rbx+1C4h], r12d
0x18001bda8  jz      short loc_18001BDF8
0x18001bdaa  cmp     [rbx+1B0h], r12d
0x18001bdb1  lea     r8, Value; "DstNotification"
0x18001bdb8  mov     ecx, 4
0x18001bdbd  lea     rdx, SubKey; "Control Panel\\TimeDate"
0x18001bdc4  mov     [rsp+190h+var_160], ecx
0x18001bdc8  mov     eax, r12d
0x18001bdcb  setnz   al
0x18001bdce  mov     [rsp+190h+var_150], eax
0x18001bdd2  lea     rax, [rsp+190h+var_150]
0x18001bdd7  mov     [rsp+190h+var_168], rax
0x18001bddc  lea     r9d, [rcx+0Ch]
0x18001bde0  mov     [rsp+190h+var_170], ecx
0x18001bde4  mov     rcx, 0FFFFFFFF80000001h; pszPrefix
0x18001bdeb  call    cs:__imp_SHRegSetValue
0x18001bdf1  mov     [rbx+1C4h], r12d
0x18001bdf8  test    edi, edi
0x18001bdfa  jz      short loc_18001BE22
0x18001bdfc  mov     rcx, rbx; this
0x18001bdff  call    ?_PollTime@CDateTimeOm@@AEAAXXZ; CDateTimeOm::_PollTime(void)
0x18001be04  xor     r8d, r8d
0x18001be07  mov     rcx, rbx
0x18001be0a  lea     edx, [r8+3]
0x18001be0e  call    ?_OnChange@CDateTimeOm@@AEAAXW4ADVISE_WPARAM@@_J@Z; CDateTimeOm::_OnChange(ADVISE_WPARAM,__int64)
0x18001be13  xor     r8d, r8d
0x18001be16  mov     rcx, rbx
0x18001be19  lea     edx, [r8+0Ah]
0x18001be1d  call    ?_OnChange@CDateTimeOm@@AEAAXW4ADVISE_WPARAM@@_J@Z; CDateTimeOm::_OnChange(ADVISE_WPARAM,__int64)
0x18001be22  mov     eax, esi
0x18001be24  mov     rcx, [rbp+90h+var_30]
0x18001be28  xor     rcx, rsp; StackCookie
0x18001be2b  call    __security_check_cookie
0x18001be30  lea     r11, [rsp+190h+var_20]
0x18001be38  mov     rbx, [r11+38h]
0x18001be3c  mov     rsi, [r11+40h]
0x18001be40  mov     rsp, r11
0x18001be43  pop     r15
0x18001be45  pop     r14
0x18001be47  pop     r12
0x18001be49  pop     rdi
0x18001be4a  pop     rbp
0x18001be4b  retn
```
