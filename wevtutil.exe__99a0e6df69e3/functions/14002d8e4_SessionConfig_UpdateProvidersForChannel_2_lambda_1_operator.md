# _SessionConfig::UpdateProvidersForChannel_::_2_::_lambda_1_::operator()

- ea: `0x14002d8e4`
- end: `0x14002dab8`
- name: `_SessionConfig::UpdateProvidersForChannel_::_2_::_lambda_1_::operator()`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002e0cc`

## callees

- `0x140002bd0`
- `0x140006008`
- `0x1400073ec`
- `0x1400098cc`
- `0x14000b6d0`
- `0x14001291c`
- `0x140014960`
- `0x140021b00`
- `0x14002d880`
- `0x14002d8e4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002d92c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002da48`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002d92c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002da48`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SessionConfig::UpdateProvidersForChannel_::_2_::_lambda_1_::operator()(
        __int64 a1,
        struct _GUID *a2,
        __int64 a3,
        unsigned int a4)
{
  LPCWCH v8; // r15
  void *v9; // rax
  __int64 v10; // rdi
  __int64 v11; // r9
  __int64 v12; // r8
  struct _GUID v13; // [rsp+30h] [rbp-148h] BYREF
  __int64 v14; // [rsp+40h] [rbp-138h] BYREF
  struct _GUID v15; // [rsp+50h] [rbp-128h] BYREF
  _BYTE v16[144]; // [rsp+60h] [rbp-118h] BYREF
  LPCWCH lpString1[10]; // [rsp+F0h] [rbp-88h] BYREF

  v8 = *(LPCWCH *)a3;
  if ( CompareStringOrdinal(**(LPCWCH **)a1, *(_DWORD *)(*(_QWORD *)a1 + 8LL), *(LPCWCH *)a3, *(_DWORD *)(a3 + 8), 1) == 2 )
  {
    v13 = *a2;
    SessionConfig::UpdateProvider(
      &v13,
      *(const struct ChannelConfigSnapshot **)(a1 + 8),
      a4,
      **(_BYTE **)(a1 + 16),
      **(void ***)(a1 + 24));
  }
  else if ( **(_BYTE **)(a1 + 32) )
  {
    v14 = 0;
    *(_QWORD *)&v13.Data1 = v8;
    *(_QWORD *)v13.Data4 = *(_QWORD *)(a3 + 8);
    try
    {
      ChannelConfigReader::ChannelConfigReader((__int64)v16, (__int128 *)&v13, **(_QWORD **)(a1 + 24));
      v9 = operator new(0x100u);
      *(_QWORD *)&v13.Data1 = v9;
      if ( v9 )
      {
        v15 = 0;
        v10 = ChannelConfigSnapshot::ChannelConfigSnapshot(v9, v16, &v15);
      }
      else
      {
        v10 = 0;
      }
      v14 = v10;
      ChannelConfigReader::~ChannelConfigReader((ChannelConfigReader *)v16);
      *(_QWORD *)&v13.Data1 = *(_QWORD *)(v10 + 200);
      *(_QWORD *)v13.Data4 = (__int64)(*(_QWORD *)(v10 + 208) - *(_QWORD *)&v13.Data1) >> 1;
      v11 = *(unsigned __int8 *)(v10 + 248);
      v12 = *(unsigned __int8 *)(v10 + 249);
    }
    catch ( EvtException )
    {
      goto LABEL_12;
    }
    SessionConfig::EtwSessionForChannel::EtwSessionForChannel(lpString1, &v13, v12, v11);
    if ( CompareStringOrdinal(lpString1[0], -1, **(LPCWCH **)(a1 + 40), -1, 1) == 2 )
    {
      v15 = *a2;
      SessionConfig::UpdateProvider(
        &v15,
        (const struct ChannelConfigSnapshot *)v10,
        a4,
        **(_BYTE **)(a1 + 16),
        **(void ***)(a1 + 24));
    }
    SessionConfig::EtwSessionForChannel::~EtwSessionForChannel((SessionConfig::EtwSessionForChannel *)lpString1);
LABEL_12:
    utl::unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>::~unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>(&v14);
  }
}

```

## disassembly

```asm
0x14002d8e4  push    rbx
0x14002d8e6  push    rsi
0x14002d8e7  push    rdi
0x14002d8e8  push    r14
0x14002d8ea  push    r15
0x14002d8ec  sub     rsp, 150h
0x14002d8f3  mov     rax, cs:__security_cookie
0x14002d8fa  xor     rax, rsp
0x14002d8fd  mov     [rsp+178h+var_38], rax
0x14002d905  mov     r14d, r9d
0x14002d908  mov     rdi, r8
0x14002d90b  mov     rsi, rdx
0x14002d90e  mov     rbx, rcx
0x14002d911  mov     r15, [r8]
0x14002d914  mov     rcx, [rcx]
0x14002d917  mov     [rsp+178h+bIgnoreCase], 1; bIgnoreCase
0x14002d91f  mov     r9d, [r8+8]; cchCount2
0x14002d923  mov     r8, r15; lpString2
0x14002d926  mov     edx, [rcx+8]; cchCount1
0x14002d929  mov     rcx, [rcx]; lpString1
0x14002d92c  call    cs:__imp_CompareStringOrdinal
0x14002d932  cmp     eax, 2
0x14002d935  jnz     short loc_14002D969
0x14002d937  movups  xmm0, xmmword ptr [rsi]
0x14002d93a  movdqu  xmmword ptr [rsp+178h+var_148.Data1], xmm0
0x14002d940  mov     rax, [rbx+18h]
0x14002d944  mov     r9, [rbx+10h]
0x14002d948  mov     rax, [rax]
0x14002d94b  mov     qword ptr [rsp+178h+bIgnoreCase], rax; void *
0x14002d950  mov     r9b, [r9]; bool
0x14002d953  mov     r8d, r14d; unsigned int
0x14002d956  mov     rdx, [rbx+8]; struct ChannelConfigSnapshot *
0x14002d95a  lea     rcx, [rsp+178h+var_148]; struct _GUID *
0x14002d95f  call    ?UpdateProvider@SessionConfig@@CAXU_GUID@@AEBVChannelConfigSnapshot@@K_NPEAX@Z; SessionConfig::UpdateProvider(_GUID,ChannelConfigSnapshot const &,ulong,bool,void *)
0x14002d964  jmp     loc_14002DA99
0x14002d969  mov     rax, [rbx+20h]
0x14002d96d  cmp     byte ptr [rax], 0
0x14002d970  jz      loc_14002DA99
0x14002d976  mov     [rsp+178h+var_138], 0
0x14002d97f  mov     qword ptr [rsp+178h+var_148.Data1], r15
0x14002d984  mov     rax, [rdi+8]
0x14002d988  mov     qword ptr [rsp+178h+var_148.Data4], rax
0x14002d98d  mov     r8, [rbx+18h]
0x14002d991  mov     r8, [r8]
0x14002d994  lea     rdx, [rsp+178h+var_148]
0x14002d999  lea     rcx, [rsp+178h+var_118]
0x14002d99e  call    ??0ChannelConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z; ChannelConfigReader::ChannelConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x14002d9a3  nop
0x14002d9a4  mov     ecx, 100h; dwBytes
0x14002d9a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002d9ae  mov     qword ptr [rsp+178h+var_148.Data1], rax
0x14002d9b3  test    rax, rax
0x14002d9b6  jz      short loc_14002D9D8
0x14002d9b8  xorps   xmm0, xmm0
0x14002d9bb  movdqa  xmmword ptr [rsp+178h+var_128.Data1], xmm0
0x14002d9c1  lea     r8, [rsp+178h+var_128]
0x14002d9c6  lea     rdx, [rsp+178h+var_118]
0x14002d9cb  mov     rcx, rax
0x14002d9ce  call    ??0ChannelConfigSnapshot@@QEAA@AEBVChannelConfigReader@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; ChannelConfigSnapshot::ChannelConfigSnapshot(ChannelConfigReader const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002d9d3  mov     rdi, rax
0x14002d9d6  jmp     short loc_14002D9DA
0x14002d9d8  xor     edi, edi
0x14002d9da  mov     [rsp+178h+var_138], rdi
0x14002d9df  lea     rcx, [rsp+178h+var_118]; this
0x14002d9e4  call    ??1ChannelConfigReader@@QEAA@XZ; ChannelConfigReader::~ChannelConfigReader(void)
0x14002d9e9  nop
0x14002d9ea  mov     rax, [rdi+0C8h]
0x14002d9f1  mov     qword ptr [rsp+178h+var_148.Data1], rax
0x14002d9f6  mov     rcx, [rdi+0D0h]
0x14002d9fd  sub     rcx, rax
0x14002da00  sar     rcx, 1
0x14002da03  mov     qword ptr [rsp+178h+var_148.Data4], rcx
0x14002da08  movzx   r9d, byte ptr [rdi+0F8h]
0x14002da10  movzx   r8d, byte ptr [rdi+0F9h]
0x14002da18  lea     rdx, [rsp+178h+var_148]
0x14002da1d  lea     rcx, [rsp+178h+lpString1]
0x14002da25  call    ??0EtwSessionForChannel@SessionConfig@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4_EVT_CHANNEL_TYPE@@W4_EVT_CHANNEL_ISOLATION_TYPE@@@Z; SessionConfig::EtwSessionForChannel::EtwSessionForChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,_EVT_CHANNEL_ISOLATION_TYPE)
0x14002da2a  nop
0x14002da2b  mov     r8, [rbx+28h]
0x14002da2f  mov     [rsp+178h+bIgnoreCase], 1; bIgnoreCase
0x14002da37  or      edx, 0FFFFFFFFh; cchCount1
0x14002da3a  mov     r9d, edx; cchCount2
0x14002da3d  mov     r8, [r8]; lpString2
0x14002da40  mov     rcx, [rsp+178h+lpString1]; lpString1
0x14002da48  call    cs:__imp_CompareStringOrdinal
0x14002da4e  cmp     eax, 2
0x14002da51  jnz     short loc_14002DA80
0x14002da53  movups  xmm0, xmmword ptr [rsi]
0x14002da56  movdqu  xmmword ptr [rsp+178h+var_128.Data1], xmm0
0x14002da5c  mov     rax, [rbx+18h]
0x14002da60  mov     r9, [rbx+10h]
0x14002da64  mov     rax, [rax]
0x14002da67  mov     qword ptr [rsp+178h+bIgnoreCase], rax; void *
0x14002da6c  mov     r9b, [r9]; bool
0x14002da6f  mov     r8d, r14d; unsigned int
0x14002da72  mov     rdx, rdi; struct ChannelConfigSnapshot *
0x14002da75  lea     rcx, [rsp+178h+var_128]; struct _GUID *
0x14002da7a  call    ?UpdateProvider@SessionConfig@@CAXU_GUID@@AEBVChannelConfigSnapshot@@K_NPEAX@Z; SessionConfig::UpdateProvider(_GUID,ChannelConfigSnapshot const &,ulong,bool,void *)
0x14002da7f  nop
0x14002da80  lea     rcx, [rsp+178h+lpString1]; this
0x14002da88  call    ??1EtwSessionForChannel@SessionConfig@@QEAA@XZ; SessionConfig::EtwSessionForChannel::~EtwSessionForChannel(void)
0x14002da8d  jmp     short $+2
0x14002da8f  lea     rcx, [rsp+178h+var_138]
0x14002da94  call    ??1?$unique_ptr@VChannelConfigSnapshot@@U?$default_delete@VChannelConfigSnapshot@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>::~unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>(void)
0x14002da99  mov     rcx, [rsp+178h+var_38]
0x14002daa1  xor     rcx, rsp; StackCookie
0x14002daa4  call    __security_check_cookie
0x14002daa9  add     rsp, 150h
0x14002dab0  pop     r15
0x14002dab2  pop     r14
0x14002dab4  pop     rdi
0x14002dab5  pop     rsi
0x14002dab6  pop     rbx
0x14002dab7  retn
```
