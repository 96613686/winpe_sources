# CUpdate::SerializeBundledUpdateCollection(CSerializationHelper *)

- ea: `0x1800530b4`
- end: `0x180053356`
- name: `?SerializeBundledUpdateCollection@CUpdate@@AEAAJPEAVCSerializationHelper@@@Z`
- size: `674`
- prototype: `int(CUpdate *__hidden this, struct CSerializationHelper *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005101c`

## callees

- `0x180006ac4`
- `0x1800530b4`
- `0x1800843e8`
- `0x180084654`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800531be`
- `OLEAUT32!__imp_SysFreeString` at `0x18005321e`
- `OLEAUT32!__imp_SysFreeString` at `0x180053312`
- `OLEAUT32!__imp_SysFreeString` at `0x1800531be`
- `OLEAUT32!__imp_SysFreeString` at `0x18005321e`
- `OLEAUT32!__imp_SysFreeString` at `0x180053312`

## string_xrefs

- `0x180053108`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18005326f`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x1800532a7`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x1800532df`: `C:\__w\1\s\src\Client\comapi\Update.cpp`
- `0x18005332a`: `C:\__w\1\s\src\Client\comapi\Update.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CUpdate::SerializeBundledUpdateCollection(CUpdate *this, struct CSerializationHelper *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  unsigned int v7; // esi
  int v8; // eax
  int v9; // eax
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, BSTR *, __int64); // rdi
  int v12; // eax
  unsigned int v13; // r8d
  int v14; // eax
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // [rsp+20h] [rbp-30h] BYREF
  unsigned int v18; // [rsp+28h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-20h] BYREF
  __int64 v20; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v18 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)(*((_QWORD *)this + 57) + 24LL) + 80LL))(
         *((_QWORD *)this + 57) + 24LL,
         &v18);
  if ( v4 < 0 )
  {
    v5 = 2508;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)(unsigned int)v4,
      v17);
    return (unsigned int)v4;
  }
  v4 = CSerializationHelper::RawSerializeData(a2, &v18, 4u);
  if ( v4 < 0 )
  {
    v5 = 2510;
    goto LABEL_3;
  }
  v7 = 0;
  if ( v18 )
  {
    while ( 1 )
    {
      v20 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)(*((_QWORD *)this + 57) + 24LL) + 56LL))(
             *((_QWORD *)this + 57) + 24LL,
             v7,
             &v20);
      v4 = v8;
      if ( v8 < 0 )
        break;
      bstrString = 0;
      v17 = 0;
      v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v20)(
             v20,
             &GUID_1d95b653_f6fc_4c51_8c4b_84a679dcdd92,
             &v17);
      v4 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9E0,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
          (const char *)(unsigned int)v9,
          v17);
        if ( v17 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          v17 = 0;
        }
        goto LABEL_26;
      }
      v10 = v17;
      v11 = *(__int64 (__fastcall **)(__int64, BSTR *, __int64))(*(_QWORD *)v17 + 24LL);
      SysFreeString(bstrString);
      bstrString = 0;
      v12 = v11(v10, &bstrString, 5);
      v4 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9E2,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
          (const char *)(unsigned int)v12,
          v17);
        if ( v17 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          v17 = 0;
        }
        goto LABEL_26;
      }
      v14 = CSerializationHelper::RawSerializeBinaryBSTR(a2, bstrString, v13);
      v4 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9E3,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
          (const char *)(unsigned int)v14,
          v17);
        if ( v17 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          v17 = 0;
        }
LABEL_26:
        SysFreeString(bstrString);
        v15 = (unsigned int)v4;
        v16 = 2516;
        goto LABEL_28;
      }
      if ( v17 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        v17 = 0;
      }
      SysFreeString(bstrString);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( ++v7 >= v18 )
        return 0;
    }
    v15 = (unsigned int)v8;
    v16 = 2515;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Update.cpp",
      (const char *)v15,
      v17);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    return (unsigned int)v4;
  }
  return 0;
}

```

## disassembly

```asm
0x1800530b4  mov     [rsp-28h+arg_10], rbx
0x1800530b9  push    rbp
0x1800530ba  push    rsi
0x1800530bb  push    rdi
0x1800530bc  push    r14
0x1800530be  push    r15
0x1800530c0  mov     rbp, rsp
0x1800530c3  sub     rsp, 50h
0x1800530c7  mov     rax, cs:__security_cookie
0x1800530ce  xor     rax, rsp
0x1800530d1  mov     [rbp+var_10], rax
0x1800530d5  mov     r14, rdx
0x1800530d8  mov     r15, rcx
0x1800530db  mov     [rbp+var_28], 0
0x1800530e2  mov     rcx, [rcx+1C8h]
0x1800530e9  add     rcx, 18h
0x1800530ed  mov     rax, [rcx]
0x1800530f0  lea     rdx, [rbp+var_28]
0x1800530f4  mov     rax, [rax+50h]
0x1800530f8  call    _guard_dispatch_icall
0x1800530fd  mov     ebx, eax
0x1800530ff  test    eax, eax
0x180053101  jns     short loc_180053122
0x180053103  mov     edx, 9CCh; void *
0x180053108  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x18005310f  mov     r9d, ebx; char *
0x180053112  mov     rcx, [rbp+28h]; this
0x180053116  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005311b  mov     eax, ebx
0x18005311d  jmp     loc_180053248
0x180053122  mov     r8d, 4; unsigned int
0x180053128  lea     rdx, [rbp+var_28]; void *
0x18005312c  mov     rcx, r14; this
0x18005312f  call    ?RawSerializeData@CSerializationHelper@@QEAAJPEBXK@Z; CSerializationHelper::RawSerializeData(void const *,ulong)
0x180053134  mov     ebx, eax
0x180053136  test    eax, eax
0x180053138  jns     short loc_180053141
0x18005313a  mov     edx, 9CEh
0x18005313f  jmp     short loc_180053108
0x180053141  xor     esi, esi
0x180053143  cmp     [rbp+var_28], esi
0x180053146  jbe     loc_180053246
0x18005314c  mov     [rbp+var_18], 0
0x180053154  mov     rcx, [r15+1C8h]
0x18005315b  add     rcx, 18h
0x18005315f  mov     rax, [rcx]
0x180053162  lea     r8, [rbp+var_18]
0x180053166  mov     edx, esi
0x180053168  mov     rax, [rax+38h]
0x18005316c  call    _guard_dispatch_icall
0x180053171  mov     ebx, eax
0x180053173  test    eax, eax
0x180053175  js      loc_180053322
0x18005317b  mov     rcx, [rbp+var_18]
0x18005317f  mov     [rbp+bstrString], 0
0x180053187  mov     [rbp+var_30], 0
0x18005318f  mov     rax, [rcx]
0x180053192  lea     r8, [rbp+var_30]
0x180053196  lea     rdx, _GUID_1d95b653_f6fc_4c51_8c4b_84a679dcdd92
0x18005319d  mov     rax, [rax]
0x1800531a0  call    _guard_dispatch_icall
0x1800531a5  mov     ebx, eax
0x1800531a7  test    eax, eax
0x1800531a9  js      loc_1800532D8
0x1800531af  mov     rbx, [rbp+var_30]
0x1800531b3  mov     rax, [rbx]
0x1800531b6  mov     rdi, [rax+18h]
0x1800531ba  mov     rcx, [rbp+bstrString]; bstrString
0x1800531be  call    cs:__imp_SysFreeString
0x1800531c4  mov     [rbp+bstrString], 0
0x1800531cc  mov     r8d, 5
0x1800531d2  lea     rdx, [rbp+bstrString]
0x1800531d6  mov     rcx, rbx
0x1800531d9  mov     rax, rdi
0x1800531dc  call    _guard_dispatch_icall
0x1800531e1  mov     ebx, eax
0x1800531e3  test    eax, eax
0x1800531e5  js      loc_1800532A0
0x1800531eb  mov     rdx, [rbp+bstrString]; wchar_t *
0x1800531ef  mov     rcx, r14; this
0x1800531f2  call    ?RawSerializeBinaryBSTR@CSerializationHelper@@QEAAJPEA_WK@Z; CSerializationHelper::RawSerializeBinaryBSTR(wchar_t *,ulong)
0x1800531f7  mov     ebx, eax
0x1800531f9  test    eax, eax
0x1800531fb  js      short loc_180053268
0x1800531fd  mov     rcx, [rbp+var_30]
0x180053201  test    rcx, rcx
0x180053204  jz      short loc_18005321A
0x180053206  mov     rax, [rcx]
0x180053209  mov     rax, [rax+10h]
0x18005320d  call    _guard_dispatch_icall
0x180053212  mov     [rbp+var_30], 0
0x18005321a  mov     rcx, [rbp+bstrString]; bstrString
0x18005321e  call    cs:__imp_SysFreeString
0x180053224  nop
0x180053225  mov     rcx, [rbp+var_18]
0x180053229  test    rcx, rcx
0x18005322c  jz      short loc_18005323B
0x18005322e  mov     rax, [rcx]
0x180053231  mov     rax, [rax+10h]
0x180053235  call    _guard_dispatch_icall
0x18005323a  nop
0x18005323b  inc     esi
0x18005323d  cmp     esi, [rbp+var_28]
0x180053240  jb      loc_18005314C
0x180053246  xor     eax, eax
0x180053248  mov     rcx, [rbp+var_10]
0x18005324c  xor     rcx, rsp; StackCookie
0x18005324f  call    __security_check_cookie
0x180053254  mov     rbx, [rsp+50h+arg_10]
0x18005325c  add     rsp, 50h
0x180053260  pop     r15
0x180053262  pop     r14
0x180053264  pop     rdi
0x180053265  pop     rsi
0x180053266  pop     rbp
0x180053267  retn
0x180053268  mov     rcx, [rbp+28h]; this
0x18005326c  mov     r9d, eax; char *
0x18005326f  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180053276  mov     edx, 9E3h; void *
0x18005327b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053280  nop
0x180053281  mov     rcx, [rbp+var_30]
0x180053285  test    rcx, rcx
0x180053288  jz      short loc_18005329E
0x18005328a  mov     rax, [rcx]
0x18005328d  mov     rax, [rax+10h]
0x180053291  call    _guard_dispatch_icall
0x180053296  mov     [rbp+var_30], 0
0x18005329e  jmp     short loc_18005330E
0x1800532a0  mov     rcx, [rbp+28h]; this
0x1800532a4  mov     r9d, eax; char *
0x1800532a7  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x1800532ae  mov     edx, 9E2h; void *
0x1800532b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800532b8  nop
0x1800532b9  mov     rcx, [rbp+var_30]
0x1800532bd  test    rcx, rcx
0x1800532c0  jz      short loc_1800532D6
0x1800532c2  mov     rax, [rcx]
0x1800532c5  mov     rax, [rax+10h]
0x1800532c9  call    _guard_dispatch_icall
0x1800532ce  mov     [rbp+var_30], 0
0x1800532d6  jmp     short loc_18005330E
0x1800532d8  mov     rcx, [rbp+28h]; this
0x1800532dc  mov     r9d, eax; char *
0x1800532df  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x1800532e6  mov     edx, 9E0h; void *
0x1800532eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800532f0  nop
0x1800532f1  mov     rcx, [rbp+var_30]
0x1800532f5  test    rcx, rcx
0x1800532f8  jz      short loc_18005330E
0x1800532fa  mov     rax, [rcx]
0x1800532fd  mov     rax, [rax+10h]
0x180053301  call    _guard_dispatch_icall
0x180053306  mov     [rbp+var_30], 0
0x18005330e  mov     rcx, [rbp+bstrString]; bstrString
0x180053312  call    cs:__imp_SysFreeString
0x180053318  mov     r9d, ebx
0x18005331b  mov     edx, 9D4h
0x180053320  jmp     short loc_18005332A
0x180053322  mov     r9d, eax; char *
0x180053325  mov     edx, 9D3h; void *
0x18005332a  lea     r8, aCW1SSrcClientC_32; "C:\\__w\\1\\s\\src\\Client\\comapi\\Upd"...
0x180053331  mov     rcx, [rbp+28h]; this
0x180053335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005333a  nop
0x18005333b  mov     rcx, [rbp+var_18]
0x18005333f  test    rcx, rcx
0x180053342  jz      short loc_180053351
0x180053344  mov     rdx, [rcx]
0x180053347  mov     rax, [rdx+10h]
0x18005334b  call    _guard_dispatch_icall
0x180053350  nop
0x180053351  jmp     loc_18005311B
```
