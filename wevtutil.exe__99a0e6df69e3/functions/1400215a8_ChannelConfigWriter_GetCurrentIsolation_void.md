# ChannelConfigWriter::GetCurrentIsolation(void)

- ea: `0x1400215a8`
- end: `0x140021645`
- name: `?GetCurrentIsolation@ChannelConfigWriter@@AEBA?AW4_EVT_CHANNEL_ISOLATION_TYPE@@XZ`
- size: `157`
- prototype: `enum _EVT_CHANNEL_ISOLATION_TYPE __fastcall(ChannelConfigWriter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400203a8`

## callees

- `0x140008870`
- `0x14001b580`
- `0x14001b5b4`
- `0x1400215a8`

## pseudocode

```c
__int64 __fastcall ChannelConfigWriter::GetCurrentIsolation(ChannelConfigWriter *this)
{
  __int64 v1; // rdi
  __int64 v3; // rbx
  __int64 v4; // rbx
  const wchar_t *v6; // rdx
  HKEY v7; // rcx
  LSTATUS v8; // eax
  unsigned int v9; // ecx
  __int64 v10; // [rsp+20h] [rbp-18h] BYREF
  __int64 v11; // [rsp+28h] [rbp-10h]
  unsigned int v12; // [rsp+40h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 35);
  v3 = *((_QWORD *)this + 36);
  v10 = v1;
  v4 = (v3 - v1) >> 1;
  v11 = v4;
  if ( (unsigned __int8)IsSystemChannel(&v10) )
    return 1;
  v10 = v1;
  v11 = v4;
  if ( IsSecurityChannel(&v10) )
    return 2;
  v7 = (HKEY)*((_QWORD *)this + 32);
  v12 = 0;
  v8 = RegReadDWORDValueNoThrow(v7, v6, L"Isolation", &v12);
  v9 = 0;
  if ( !v8 )
    return v12;
  return v9;
}

```

## disassembly

```asm
0x1400215a8  mov     rax, rsp
0x1400215ab  mov     [rax+10h], rbx
0x1400215af  mov     [rax+18h], rsi
0x1400215b3  push    rdi
0x1400215b4  sub     rsp, 30h
0x1400215b8  mov     rdi, [rcx+118h]
0x1400215bf  mov     rsi, rcx
0x1400215c2  mov     rbx, [rcx+120h]
0x1400215c9  lea     rcx, [rax-18h]
0x1400215cd  sub     rbx, rdi
0x1400215d0  mov     [rax-18h], rdi
0x1400215d4  sar     rbx, 1
0x1400215d7  mov     [rax-10h], rbx
0x1400215db  call    ?IsSystemChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSystemChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1400215e0  test    al, al
0x1400215e2  jz      short loc_1400215EB
0x1400215e4  mov     eax, 1
0x1400215e9  jmp     short loc_140021635
0x1400215eb  lea     rcx, [rsp+38h+var_18]
0x1400215f0  mov     [rsp+38h+var_18], rdi
0x1400215f5  mov     [rsp+38h+var_10], rbx
0x1400215fa  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x1400215ff  test    al, al
0x140021601  jz      short loc_14002160A
0x140021603  mov     eax, 2
0x140021608  jmp     short loc_140021635
0x14002160a  mov     rcx, [rsi+100h]; HKEY
0x140021611  lea     r9, [rsp+38h+arg_0]; unsigned int *
0x140021616  lea     r8, aIsolation; "Isolation"
0x14002161d  mov     [rsp+38h+arg_0], 0
0x140021625  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x14002162a  xor     ecx, ecx
0x14002162c  test    eax, eax
0x14002162e  cmovz   ecx, [rsp+38h+arg_0]
0x140021633  mov     eax, ecx
0x140021635  mov     rbx, [rsp+38h+arg_8]
0x14002163a  mov     rsi, [rsp+38h+arg_10]
0x14002163f  add     rsp, 30h
0x140021643  pop     rdi
0x140021644  retn
```
