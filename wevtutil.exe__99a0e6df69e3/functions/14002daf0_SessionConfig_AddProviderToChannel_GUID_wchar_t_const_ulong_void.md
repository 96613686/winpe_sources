# SessionConfig::AddProviderToChannel(_GUID,wchar_t const *,ulong,void *)

- ea: `0x14002daf0`
- end: `0x14002dbf8`
- name: `?AddProviderToChannel@SessionConfig@@SAXU_GUID@@PEB_WKPEAX@Z`
- size: `264`
- prototype: `static void(struct _GUID *__struct_ptr, const wchar_t *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140017fbc`

## callees

- `0x140002bd0`
- `0x140006008`
- `0x1400073ec`
- `0x1400098cc`
- `0x14001291c`
- `0x14001b5b4`
- `0x14002d880`
- `0x14002daf0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SessionConfig::AddProviderToChannel(struct _GUID *a1, const wchar_t *a2, unsigned int a3, __int64 a4)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  void *v10; // rax
  __int64 v11; // rbx
  unsigned int v12; // r8d
  const struct ChannelConfigSnapshot *v13; // rdx
  void *v14; // [rsp+20h] [rbp-108h]
  __int128 v15; // [rsp+30h] [rbp-F8h] BYREF
  struct _GUID v16; // [rsp+40h] [rbp-E8h] BYREF
  EvtException *v17; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v18[200]; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+138h] [rbp+10h] BYREF

  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  *(_QWORD *)&v15 = a2;
  *((_QWORD *)&v15 + 1) = v9;
  if ( !IsSecurityChannel(&v15) )
  {
    v19 = 0;
    do
      ++v8;
    while ( a2[v8] );
    *(_QWORD *)&v15 = a2;
    *((_QWORD *)&v15 + 1) = v8;
    try
    {
      ChannelConfigReader::ChannelConfigReader((__int64)v18, &v15, a4);
      v10 = operator new(0x100u);
      *(_QWORD *)&v15 = v10;
      if ( v10 )
      {
        v16 = 0;
        v11 = ChannelConfigSnapshot::ChannelConfigSnapshot((__int64)v10, (__int64)v18, (__int64)&v16);
      }
      else
      {
        v11 = 0;
      }
      v19 = v11;
      ChannelConfigReader::~ChannelConfigReader((ChannelConfigReader *)v18);
      v16 = *a1;
      v14 = (void *)a4;
      v12 = a3;
      v13 = (const struct ChannelConfigSnapshot *)v11;
    }
    catch ( EvtException *v17 )
    {
      if ( *((_DWORD *)v17 + 6) != 2 && *((_DWORD *)v17 + 6) != 15007 )
        throw;
      goto LABEL_12;
    }
    SessionConfig::UpdateProvider(&v16, v13, v12, 1, v14);
LABEL_12:
    utl::unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>::~unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>(&v19);
  }
}

```

## disassembly

```asm
0x14002daf0  push    rbx
0x14002daf2  push    rsi
0x14002daf3  push    rdi
0x14002daf4  push    r12
0x14002daf6  push    r14
0x14002daf8  push    r15
0x14002dafa  sub     rsp, 0F8h
0x14002db01  mov     rsi, r9
0x14002db04  mov     r14d, r8d
0x14002db07  mov     rdi, rdx
0x14002db0a  mov     r15, rcx
0x14002db0d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002db11  mov     rax, rbx
0x14002db14  xor     r12d, r12d
0x14002db17  inc     rax
0x14002db1a  cmp     [rdx+rax*2], r12w
0x14002db1f  jnz     short loc_14002DB17
0x14002db21  mov     [rsp+128h+var_F8], rdi
0x14002db26  mov     [rsp+128h+var_F0], rax
0x14002db2b  lea     rcx, [rsp+128h+var_F8]
0x14002db30  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002db35  test    al, al
0x14002db37  jnz     loc_14002DBE7
0x14002db3d  mov     [rsp+128h+arg_8], r12
0x14002db45  inc     rbx
0x14002db48  cmp     [rdi+rbx*2], r12w
0x14002db4d  jnz     short loc_14002DB45
0x14002db4f  mov     [rsp+128h+var_F8], rdi
0x14002db54  mov     [rsp+128h+var_F0], rbx
0x14002db59  mov     r8, rsi
0x14002db5c  lea     rdx, [rsp+128h+var_F8]
0x14002db61  lea     rcx, [rsp+128h+var_C8]
0x14002db66  call    ??0ChannelConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z; ChannelConfigReader::ChannelConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x14002db6b  nop
0x14002db6c  mov     ecx, 100h; dwBytes
0x14002db71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002db76  mov     [rsp+128h+var_F8], rax
0x14002db7b  test    rax, rax
0x14002db7e  jz      short loc_14002DBA0
0x14002db80  xorps   xmm0, xmm0
0x14002db83  movdqa  xmmword ptr [rsp+128h+var_E8.Data1], xmm0
0x14002db89  lea     r8, [rsp+128h+var_E8]
0x14002db8e  lea     rdx, [rsp+128h+var_C8]
0x14002db93  mov     rcx, rax
0x14002db96  call    ??0ChannelConfigSnapshot@@QEAA@AEBVChannelConfigReader@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; ChannelConfigSnapshot::ChannelConfigSnapshot(ChannelConfigReader const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002db9b  mov     rbx, rax
0x14002db9e  jmp     short loc_14002DBA3
0x14002dba0  mov     rbx, r12
0x14002dba3  mov     [rsp+128h+arg_8], rbx
0x14002dbab  lea     rcx, [rsp+128h+var_C8]; this
0x14002dbb0  call    ??1ChannelConfigReader@@QEAA@XZ; ChannelConfigReader::~ChannelConfigReader(void)
0x14002dbb5  nop
0x14002dbb6  movaps  xmm0, xmmword ptr [r15]
0x14002dbba  movdqa  xmmword ptr [rsp+128h+var_E8.Data1], xmm0
0x14002dbc0  mov     [rsp+128h+var_108], rsi; void *
0x14002dbc5  mov     r9b, 1; bool
0x14002dbc8  mov     r8d, r14d; unsigned int
0x14002dbcb  mov     rdx, rbx; struct ChannelConfigSnapshot *
0x14002dbce  lea     rcx, [rsp+128h+var_E8]; struct _GUID *
0x14002dbd3  call    ?UpdateProvider@SessionConfig@@CAXU_GUID@@AEBVChannelConfigSnapshot@@K_NPEAX@Z; SessionConfig::UpdateProvider(_GUID,ChannelConfigSnapshot const &,ulong,bool,void *)
0x14002dbd8  jmp     short $+2
0x14002dbda  lea     rcx, [rsp+128h+arg_8]
0x14002dbe2  call    ??1?$unique_ptr@VChannelConfigSnapshot@@U?$default_delete@VChannelConfigSnapshot@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>::~unique_ptr<ChannelConfigSnapshot,utl::default_delete<ChannelConfigSnapshot>>(void)
0x14002dbe7  add     rsp, 0F8h
0x14002dbee  pop     r15
0x14002dbf0  pop     r14
0x14002dbf2  pop     r12
0x14002dbf4  pop     rdi
0x14002dbf5  pop     rsi
0x14002dbf6  pop     rbx
0x14002dbf7  retn
```
