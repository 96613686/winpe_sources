# SessionConfig::OfflineUpdateAutologgerForChannel(wchar_t const *,void *)

- ea: `0x14002e018`
- end: `0x14002e0c4`
- name: `?OfflineUpdateAutologgerForChannel@SessionConfig@@SAXPEB_WPEAX@Z`
- size: `172`
- prototype: `static void(const wchar_t *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x140017fbc`

## callees

- `0x140006008`
- `0x1400073ec`
- `0x1400098cc`
- `0x140013658`
- `0x140021b00`
- `0x14002d89c`
- `0x14002e018`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SessionConfig::OfflineUpdateAutologgerForChannel(const wchar_t *a1, void *a2)
{
  __int64 v3; // rax
  __int128 v4; // [rsp+20h] [rbp-1B8h] BYREF
  _BYTE v5[144]; // [rsp+30h] [rbp-1A8h] BYREF
  _BYTE v6[256]; // [rsp+C0h] [rbp-118h] BYREF

  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  *(_QWORD *)&v4 = a1;
  *((_QWORD *)&v4 + 1) = v3;
  ChannelConfigReader::ChannelConfigReader((__int64)v5, &v4, (__int64)a2);
  v4 = 0;
  ChannelConfigSnapshot::ChannelConfigSnapshot((__int64)v6, (__int64)v5, (__int64)&v4);
  SessionConfig::UpdateAutologgerForChannel((const struct ChannelConfigSnapshot *)v6, a2);
  ChannelConfigSnapshot::~ChannelConfigSnapshot((ChannelConfigSnapshot *)v6);
  ChannelConfigReader::~ChannelConfigReader((ChannelConfigReader *)v5);
}

```

## disassembly

```asm
0x14002e018  push    rbx
0x14002e01a  sub     rsp, 1D0h
0x14002e021  mov     rax, cs:__security_cookie
0x14002e028  xor     rax, rsp
0x14002e02b  mov     [rsp+1D8h+var_18], rax
0x14002e033  mov     rbx, rdx
0x14002e036  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002e03a  inc     rax
0x14002e03d  cmp     word ptr [rcx+rax*2], 0
0x14002e042  jnz     short loc_14002E03A
0x14002e044  mov     qword ptr [rsp+1D8h+var_1B8], rcx
0x14002e049  mov     qword ptr [rsp+1D8h+var_1B8+8], rax
0x14002e04e  mov     r8, rbx
0x14002e051  lea     rdx, [rsp+1D8h+var_1B8]
0x14002e056  lea     rcx, [rsp+1D8h+var_1A8]
0x14002e05b  call    ??0ChannelConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z; ChannelConfigReader::ChannelConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)
0x14002e060  nop
0x14002e061  xorps   xmm0, xmm0
0x14002e064  movdqa  [rsp+1D8h+var_1B8], xmm0
0x14002e06a  lea     r8, [rsp+1D8h+var_1B8]
0x14002e06f  lea     rdx, [rsp+1D8h+var_1A8]
0x14002e074  lea     rcx, [rsp+1D8h+var_118]
0x14002e07c  call    ??0ChannelConfigSnapshot@@QEAA@AEBVChannelConfigReader@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; ChannelConfigSnapshot::ChannelConfigSnapshot(ChannelConfigReader const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14002e081  nop
0x14002e082  mov     rdx, rbx; void *
0x14002e085  lea     rcx, [rsp+1D8h+var_118]; struct ChannelConfigSnapshot *
0x14002e08d  call    ?UpdateAutologgerForChannel@SessionConfig@@SAXAEBVChannelConfigSnapshot@@PEAX@Z; SessionConfig::UpdateAutologgerForChannel(ChannelConfigSnapshot const &,void *)
0x14002e092  nop
0x14002e093  lea     rcx, [rsp+1D8h+var_118]; this
0x14002e09b  call    ??1ChannelConfigSnapshot@@QEAA@XZ; ChannelConfigSnapshot::~ChannelConfigSnapshot(void)
0x14002e0a0  nop
0x14002e0a1  lea     rcx, [rsp+1D8h+var_1A8]; this
0x14002e0a6  call    ??1ChannelConfigReader@@QEAA@XZ; ChannelConfigReader::~ChannelConfigReader(void)
0x14002e0ab  mov     rcx, [rsp+1D8h+var_18]
0x14002e0b3  xor     rcx, rsp; StackCookie
0x14002e0b6  call    __security_check_cookie
0x14002e0bb  add     rsp, 1D0h
0x14002e0c2  pop     rbx
0x14002e0c3  retn
```
