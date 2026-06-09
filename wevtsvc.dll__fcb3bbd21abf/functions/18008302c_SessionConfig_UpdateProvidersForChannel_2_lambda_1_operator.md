# _SessionConfig::UpdateProvidersForChannel_::_2_::_lambda_1_::operator()

- ea: `0x18008302c`
- end: `0x180083200`
- name: `_SessionConfig::UpdateProvidersForChannel_::_2_::_lambda_1_::operator()`
- size: `468`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005a814`

## callees

- `0x180016250`
- `0x180057e30`
- `0x180058aec`
- `0x180058b48`
- `0x18005c600`
- `0x18006ea98`
- `0x18008302c`
- `0x1800932b0`
- `0x18009642c`
- `0x18009aee0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180083074`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180083190`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180083074`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180083190`

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
  LPVOID v9; // rax
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
      ChannelConfigReader::ChannelConfigReader(v16, &v13, **(_QWORD **)(a1 + 24));
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
    utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(lpString1);
LABEL_12:
    utl::unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>::~unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>(&v14);
  }
}

```

## disassembly

```asm
0x18008302c  push    rbx
0x18008302e  push    rsi
0x18008302f  push    rdi
0x180083030  push    r14
0x180083032  push    r15
0x180083034  sub     rsp, 150h
0x18008303b  mov     rax, cs:__security_cookie
0x180083042  xor     rax, rsp
0x180083045  mov     [rsp+178h+var_38], rax
0x18008304d  mov     r14d, r9d
0x180083050  mov     rdi, r8
0x180083053  mov     rsi, rdx
0x180083056  mov     rbx, rcx
0x180083059  mov     r15, [r8]
0x18008305c  mov     rcx, [rcx]
0x18008305f  mov     [rsp+178h+bIgnoreCase], 1; bIgnoreCase
0x180083067  mov     r9d, [r8+8]; cchCount2
0x18008306b  mov     r8, r15; lpString2
0x18008306e  mov     edx, [rcx+8]; cchCount1
0x180083071  mov     rcx, [rcx]; lpString1
0x180083074  call    cs:__imp_CompareStringOrdinal
0x18008307a  cmp     eax, 2
0x18008307d  jnz     short loc_1800830B1
0x18008307f  movups  xmm0, xmmword ptr [rsi]
0x180083082  movdqu  xmmword ptr [rsp+178h+var_148.Data1], xmm0
0x180083088  mov     rax, [rbx+18h]
0x18008308c  mov     r9, [rbx+10h]
0x180083090  mov     rax, [rax]
0x180083093  mov     qword ptr [rsp+178h+bIgnoreCase], rax; void *
0x180083098  mov     r9b, [r9]; bool
0x18008309b  mov     r8d, r14d; unsigned int
0x18008309e  mov     rdx, [rbx+8]; struct ChannelConfigSnapshot *
0x1800830a2  lea     rcx, [rsp+178h+var_148]; struct _GUID *
0x1800830a7  call    ?UpdateProvider@SessionConfig@@CAXU_GUID@@AEBVChannelConfigSnapshot@@K_NPEAX@Z; SessionConfig::UpdateProvider(_GUID,ChannelConfigSnapshot const &,ulong,bool,void *)
0x1800830ac  jmp     loc_1800831E1
0x1800830b1  mov     rax, [rbx+20h]
0x1800830b5  cmp     byte ptr [rax], 0
0x1800830b8  jz      loc_1800831E1
0x1800830be  mov     [rsp+178h+var_138], 0
0x1800830c7  mov     qword ptr [rsp+178h+var_148.Data1], r15
0x1800830cc  mov     rax, [rdi+8]
0x1800830d0  mov     qword ptr [rsp+178h+var_148.Data4], rax
0x1800830d5  mov     r8, [rbx+18h]
0x1800830d9  mov     r8, [r8]
0x1800830dc  lea     rdx, [rsp+178h+var_148]
0x1800830e1  lea     rcx, [rsp+178h+var_118]
0x1800830e6  call    ??0ChannelConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z; ChannelConfigReader::ChannelConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x1800830eb  nop
0x1800830ec  mov     ecx, 100h; dwBytes
0x1800830f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800830f6  mov     qword ptr [rsp+178h+var_148.Data1], rax
0x1800830fb  test    rax, rax
0x1800830fe  jz      short loc_180083120
0x180083100  xorps   xmm0, xmm0
0x180083103  movdqa  xmmword ptr [rsp+178h+var_128.Data1], xmm0
0x180083109  lea     r8, [rsp+178h+var_128]
0x18008310e  lea     rdx, [rsp+178h+var_118]
0x180083113  mov     rcx, rax
0x180083116  call    ??0ChannelConfigSnapshot@@QEAA@AEBVChannelConfigReader@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; ChannelConfigSnapshot::ChannelConfigSnapshot(ChannelConfigReader const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18008311b  mov     rdi, rax
0x18008311e  jmp     short loc_180083122
0x180083120  xor     edi, edi
0x180083122  mov     [rsp+178h+var_138], rdi
0x180083127  lea     rcx, [rsp+178h+var_118]; this
0x18008312c  call    ??1ChannelConfigReader@@QEAA@XZ; ChannelConfigReader::~ChannelConfigReader(void)
0x180083131  nop
0x180083132  mov     rax, [rdi+0C8h]
0x180083139  mov     qword ptr [rsp+178h+var_148.Data1], rax
0x18008313e  mov     rcx, [rdi+0D0h]
0x180083145  sub     rcx, rax
0x180083148  sar     rcx, 1
0x18008314b  mov     qword ptr [rsp+178h+var_148.Data4], rcx
0x180083150  movzx   r9d, byte ptr [rdi+0F8h]
0x180083158  movzx   r8d, byte ptr [rdi+0F9h]
0x180083160  lea     rdx, [rsp+178h+var_148]
0x180083165  lea     rcx, [rsp+178h+lpString1]
0x18008316d  call    ??0EtwSessionForChannel@SessionConfig@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4_EVT_CHANNEL_TYPE@@W4_EVT_CHANNEL_ISOLATION_TYPE@@@Z; SessionConfig::EtwSessionForChannel::EtwSessionForChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_EVT_CHANNEL_TYPE,_EVT_CHANNEL_ISOLATION_TYPE)
0x180083172  nop
0x180083173  mov     r8, [rbx+28h]
0x180083177  mov     [rsp+178h+bIgnoreCase], 1; bIgnoreCase
0x18008317f  or      edx, 0FFFFFFFFh; cchCount1
0x180083182  mov     r9d, edx; cchCount2
0x180083185  mov     r8, [r8]; lpString2
0x180083188  mov     rcx, [rsp+178h+lpString1]; lpString1
0x180083190  call    cs:__imp_CompareStringOrdinal
0x180083196  cmp     eax, 2
0x180083199  jnz     short loc_1800831C8
0x18008319b  movups  xmm0, xmmword ptr [rsi]
0x18008319e  movdqu  xmmword ptr [rsp+178h+var_128.Data1], xmm0
0x1800831a4  mov     rax, [rbx+18h]
0x1800831a8  mov     r9, [rbx+10h]
0x1800831ac  mov     rax, [rax]
0x1800831af  mov     qword ptr [rsp+178h+bIgnoreCase], rax; void *
0x1800831b4  mov     r9b, [r9]; bool
0x1800831b7  mov     r8d, r14d; unsigned int
0x1800831ba  mov     rdx, rdi; struct ChannelConfigSnapshot *
0x1800831bd  lea     rcx, [rsp+178h+var_128]; struct _GUID *
0x1800831c2  call    ?UpdateProvider@SessionConfig@@CAXU_GUID@@AEBVChannelConfigSnapshot@@K_NPEAX@Z; SessionConfig::UpdateProvider(_GUID,ChannelConfigSnapshot const &,ulong,bool,void *)
0x1800831c7  nop
0x1800831c8  lea     rcx, [rsp+178h+lpString1]
0x1800831d0  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@utl@@QEAA@XZ; utl::pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>::~pair<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(void)
0x1800831d5  jmp     short $+2
0x1800831d7  lea     rcx, [rsp+178h+var_138]
0x1800831dc  call    ??1?$unique_ptr@VChannelConfigSnapshot@@U?$default_delete@VChannelConfigSnapshot@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>::~unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>(void)
0x1800831e1  mov     rcx, [rsp+178h+var_38]
0x1800831e9  xor     rcx, rsp; StackCookie
0x1800831ec  call    __security_check_cookie
0x1800831f1  add     rsp, 150h
0x1800831f8  pop     r15
0x1800831fa  pop     r14
0x1800831fc  pop     rdi
0x1800831fd  pop     rsi
0x1800831fe  pop     rbx
0x1800831ff  retn
```
