# uus::UndockedUpdateTelemetry::UusDuplicateVersionsFound(UusVersion const &,wchar_t const *,wchar_t const *)

- ea: `0x180009180`
- end: `0x1800092f9`
- name: `?UusDuplicateVersionsFound@UndockedUpdateTelemetry@uus@@SAXAEBVUusVersion@@PEB_W1@Z`
- size: `377`
- prototype: `void __fastcall(const struct UusVersion *, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000a8dc`
- `0x18003b5f0`

## callees

- `0x18000109c`
- `0x18000868c`
- `0x1800089f4`
- `0x180009180`
- `0x180029644`
- `0x1800427d0`

## pseudocode

```c
void __fastcall uus::UndockedUpdateTelemetry::UusDuplicateVersionsFound(
        const struct UusVersion *a1,
        const wchar_t *a2,
        const wchar_t *a3)
{
  const struct _tlgProvider_t *v6; // r14
  const wchar_t *String; // rax
  __int64 v8; // rcx
  int v9; // r8d
  __int64 v10; // rdx
  int v11; // edx
  __int64 v12; // rdx
  int v13; // edx
  __int64 v14; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v15[40]; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+60h] [rbp-29h] BYREF
  __int64 *v17; // [rsp+80h] [rbp-9h]
  __int64 v18; // [rsp+88h] [rbp-1h]
  const wchar_t *v19; // [rsp+90h] [rbp+7h]
  int v20; // [rsp+98h] [rbp+Fh]
  int v21; // [rsp+9Ch] [rbp+13h]
  const wchar_t *v22; // [rsp+A0h] [rbp+17h]
  int v23; // [rsp+A8h] [rbp+1Fh]
  int v24; // [rsp+ACh] [rbp+23h]
  const wchar_t *v25; // [rsp+B0h] [rbp+27h]
  int v26; // [rsp+B8h] [rbp+2Fh]
  int v27; // [rsp+BCh] [rbp+33h]

  v6 = uus::UndockedUpdateTelemetry::Provider();
  if ( *(_DWORD *)v6 > 5u
    && (*((_QWORD *)v6 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v6 + 3) & 0x400000000000LL) == *((_QWORD *)v6 + 3) )
  {
    String = (const wchar_t *)UusVersion::GetString(a1, v15);
    if ( *((_QWORD *)String + 3) > 7u )
      String = *(const wchar_t **)String;
    v8 = -1;
    v14 = 0x1000000;
    v9 = 2;
    if ( a3 )
    {
      v10 = -1;
      do
        ++v10;
      while ( a3[v10] );
      v11 = 2 * v10 + 2;
    }
    else
    {
      a3 = &qword_180050DC0;
      v11 = 2;
    }
    v25 = a3;
    v26 = v11;
    v27 = 0;
    if ( a2 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      v13 = 2 * v12 + 2;
    }
    else
    {
      a2 = &qword_180050DC0;
      v13 = 2;
    }
    v22 = a2;
    v23 = v13;
    v24 = 0;
    if ( String )
    {
      do
        ++v8;
      while ( String[v8] );
      v9 = 2 * v8 + 2;
    }
    else
    {
      String = &qword_180050DC0;
    }
    v19 = String;
    v20 = v9;
    v17 = &v14;
    v21 = 0;
    v18 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)v6, (unsigned __int8 *)&dword_180056B84, 0, 0, 6u, &v16);
    std::wstring::_Tidy_deallocate(v15);
  }
}

```

## disassembly

```asm
0x180009180  mov     [rsp-8+arg_8], rbx
0x180009185  mov     [rsp-8+arg_10], rsi
0x18000918a  push    rbp
0x18000918b  push    rdi
0x18000918c  push    r14
0x18000918e  lea     rbp, [rsp-47h]
0x180009193  sub     rsp, 0D0h
0x18000919a  mov     rax, cs:__security_cookie
0x1800091a1  xor     rax, rsp
0x1800091a4  mov     [rbp+57h+var_20], rax
0x1800091a8  mov     rbx, r8
0x1800091ab  mov     rdi, rdx
0x1800091ae  mov     rsi, rcx
0x1800091b1  call    ?Provider@UndockedUpdateTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedUpdateTelemetry::Provider(void)
0x1800091b6  mov     r14, rax
0x1800091b9  cmp     dword ptr [rax], 5
0x1800091bc  jbe     loc_1800092D5
0x1800091c2  mov     rax, 400000000000h
0x1800091cc  test    [r14+10h], rax
0x1800091d0  jz      loc_1800092D5
0x1800091d6  mov     rdx, [r14+18h]
0x1800091da  and     rdx, rax
0x1800091dd  cmp     rdx, [r14+18h]
0x1800091e1  jnz     loc_1800092D5
0x1800091e7  lea     rdx, [rbp+57h+var_A8]
0x1800091eb  mov     rcx, rsi
0x1800091ee  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x1800091f3  cmp     qword ptr [rax+18h], 7
0x1800091f8  jbe     short loc_1800091FD
0x1800091fa  mov     rax, [rax]
0x1800091fd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009201  mov     [rbp+57h+var_B0], 1000000h
0x180009209  xor     r9d, r9d; int
0x18000920c  lea     r10, qword_180050DC0
0x180009213  mov     r8d, 2
0x180009219  test    rbx, rbx
0x18000921c  jz      short loc_180009234
0x18000921e  mov     rdx, rcx
0x180009221  inc     rdx
0x180009224  cmp     [rbx+rdx*2], r9w
0x180009229  jnz     short loc_180009221
0x18000922b  lea     edx, ds:2[rdx*2]
0x180009232  jmp     short loc_18000923A
0x180009234  mov     rbx, r10
0x180009237  mov     edx, r8d
0x18000923a  mov     [rbp+57h+var_30], rbx
0x18000923e  mov     [rbp+57h+var_28], edx
0x180009241  mov     [rbp+57h+var_24], r9d
0x180009245  test    rdi, rdi
0x180009248  jz      short loc_180009260
0x18000924a  mov     rdx, rcx
0x18000924d  inc     rdx
0x180009250  cmp     [rdi+rdx*2], r9w
0x180009255  jnz     short loc_18000924D
0x180009257  lea     edx, ds:2[rdx*2]
0x18000925e  jmp     short loc_180009266
0x180009260  mov     rdi, r10
0x180009263  mov     edx, r8d
0x180009266  mov     [rbp+57h+var_40], rdi
0x18000926a  mov     [rbp+57h+var_38], edx
0x18000926d  mov     [rbp+57h+var_34], r9d
0x180009271  test    rax, rax
0x180009274  jz      short loc_18000928A
0x180009276  inc     rcx
0x180009279  cmp     [rax+rcx*2], r9w
0x18000927e  jnz     short loc_180009276
0x180009280  lea     r8d, ds:2[rcx*2]
0x180009288  jmp     short loc_18000928D
0x18000928a  mov     rax, r10
0x18000928d  mov     [rbp+57h+var_50], rax
0x180009291  lea     rdx, dword_180056B84; int
0x180009298  lea     rax, [rbp+57h+var_B0]
0x18000929c  mov     [rbp+57h+var_48], r8d
0x1800092a0  mov     [rbp+57h+var_60], rax
0x1800092a4  xor     r8d, r8d; int
0x1800092a7  lea     rax, [rbp+57h+var_80]
0x1800092ab  mov     [rbp+57h+var_44], r9d
0x1800092af  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x1800092b4  mov     rcx, r14; int
0x1800092b7  mov     [rsp+0E0h+var_C0], 6; ULONG
0x1800092bf  mov     [rbp+57h+var_58], 8
0x1800092c7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800092cc  lea     rcx, [rbp+57h+var_A8]
0x1800092d0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800092d5  mov     rcx, [rbp+57h+var_20]
0x1800092d9  xor     rcx, rsp; StackCookie
0x1800092dc  call    __security_check_cookie
0x1800092e1  lea     r11, [rsp+0E0h+var_10]
0x1800092e9  mov     rbx, [r11+28h]
0x1800092ed  mov     rsi, [r11+30h]
0x1800092f1  mov     rsp, r11
0x1800092f4  pop     r14
0x1800092f6  pop     rdi
0x1800092f7  pop     rbp
0x1800092f8  retn
```
