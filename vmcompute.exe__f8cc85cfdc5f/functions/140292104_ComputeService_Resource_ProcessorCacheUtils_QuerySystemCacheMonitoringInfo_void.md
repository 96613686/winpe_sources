# ComputeService::Resource::ProcessorCacheUtils::QuerySystemCacheMonitoringInfo(void)

- ea: `0x140292104`
- end: `0x140292315`
- name: `?QuerySystemCacheMonitoringInfo@ProcessorCacheUtils@Resource@ComputeService@@YA?AUCacheMonitoringSystemInfo@ProcessorCache@Resources@Schema@@XZ`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140129708`

## callees

- `0x140080180`
- `0x1400a02f8`
- `0x1401332f0`
- `0x140292104`

## import_xrefs

- `vid!VidGetSystemInformation` at `0x1402921ad`
- `vid!VidGetSystemInformation` at `0x14029228a`
- `vid!VidGetSystemInformation` at `0x1402921ad`
- `vid!VidGetSystemInformation` at `0x14029228a`
- `vid!VidGetPartitionProperty` at `0x14029221d`
- `vid!VidGetPartitionProperty` at `0x14029221d`
- `vid!VidOpenStatisticsHandle` at `0x14029215c`
- `vid!VidOpenStatisticsHandle` at `0x14029215c`

## string_xrefs

- `0x1402921c1`: `onecore\vm\compute\management\resources\processorcache\processorcacheutils.cpp`
- `0x140292231`: `onecore\vm\compute\management\resources\processorcache\processorcacheutils.cpp`
- `0x14029229e`: `onecore\vm\compute\management\resources\processorcache\processorcacheutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall ComputeService::Resource::ProcessorCacheUtils::QuerySystemCacheMonitoringInfo(_OWORD *a1)
{
  __int64 v2; // rbx
  const char *v3; // r9
  const char *v4; // r9
  const char *v5; // r9
  __int128 v7; // [rsp+40h] [rbp-49h]
  unsigned __int128 v8; // [rsp+50h] [rbp-39h]
  __int128 v9; // [rsp+60h] [rbp-29h]
  __int64 v10; // [rsp+70h] [rbp-19h] BYREF
  __int64 v11; // [rsp+78h] [rbp-11h] BYREF
  __int128 v12; // [rsp+80h] [rbp-9h] BYREF
  __int128 v13; // [rsp+90h] [rbp+7h]
  __int128 v14; // [rsp+A0h] [rbp+17h]
  __int128 v15; // [rsp+B0h] [rbp+27h]
  __int128 v16; // [rsp+C0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  *((_QWORD *)&v7 + 1) = 0;
  v8 = 0u;
  v9 = 0u;
  v2 = VidOpenStatisticsHandle(a1);
  v10 = v2;
  v15 = 0;
  v16 = 0;
  v12 = 0;
  v11 = 0;
  if ( !(unsigned int)VidGetSystemInformation(v2, 3, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x122,
      (unsigned int)"onecore\\vm\\compute\\management\\resources\\processorcache\\processorcacheutils.cpp",
      v3);
  LOBYTE(v7) = (v15 & 2) != 0;
  BYTE3(v7) = (v15 & 0x10) != 0;
  BYTE1(v7) = (v15 & 4) != 0;
  BYTE2(v7) = (v15 & 8) != 0;
  DWORD1(v7) = v16;
  if ( (v15 & 2) != 0 )
  {
    if ( !(unsigned int)VidGetPartitionProperty(-1, 327695, &v11) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x12F,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\processorcache\\processorcacheutils.cpp",
        v4);
    DWORD2(v7) = v11;
    DWORD2(v12) = 2;
    HIDWORD(v12) = v11;
    v13 = 0;
    v14 = 0;
    if ( !(unsigned int)VidGetSystemInformation(v2, 5, (char *)&v12 + 8) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x143,
        (unsigned int)"onecore\\vm\\compute\\management\\resources\\processorcache\\processorcacheutils.cpp",
        v5);
    BYTE8(v9) = (_BYTE)v13 != 0;
    v8 = __PAIR128__(v14, *((unsigned __int64 *)&v13 + 1));
    *(_QWORD *)&v9 = *((_QWORD *)&v14 + 1);
  }
  *a1 = v7;
  a1[1] = v8;
  a1[2] = v9;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(&v10);
  return a1;
}

```

## disassembly

```asm
0x140292104  mov     [rsp-8+arg_0], rbx
0x140292109  mov     [rsp-8+arg_8], rdi
0x14029210e  push    rbp
0x14029210f  lea     rbp, [rsp-57h]
0x140292114  sub     rsp, 0E0h
0x14029211b  mov     rax, cs:__security_cookie
0x140292122  xor     rax, rsp
0x140292125  mov     [rbp+57h+var_10], rax
0x140292129  mov     rdi, rcx
0x14029212c  mov     qword ptr [rbp+57h+var_A0+8], 0
0x140292134  mov     qword ptr [rbp+57h+var_90], 0
0x14029213c  mov     qword ptr [rbp+57h+var_90+8], 0
0x140292144  mov     qword ptr [rbp+57h+var_80], 0
0x14029214c  mov     byte ptr [rbp+57h+var_80+8], 0
0x140292150  xor     eax, eax
0x140292152  mov     dword ptr [rbp+57h+var_80+9], eax
0x140292155  mov     word ptr [rbp+57h+var_80+0Dh], ax
0x140292159  mov     byte ptr [rbp+57h+var_80+0Fh], al
0x14029215c  call    cs:__imp_VidOpenStatisticsHandle
0x140292163  nop     dword ptr [rax+rax+00h]
0x140292168  mov     rbx, rax
0x14029216b  mov     [rbp+57h+var_70], rax
0x14029216f  xorps   xmm0, xmm0
0x140292172  movups  [rbp+57h+var_30], xmm0
0x140292176  movups  [rbp+57h+var_20], xmm0
0x14029217a  movups  [rbp+57h+var_60], xmm0
0x14029217e  mov     [rbp+57h+var_68], 0
0x140292186  mov     [rsp+0E0h+var_B0], 0
0x14029218f  mov     [rsp+0E0h+var_B8], 20h ; ' '
0x140292197  lea     rax, [rbp+57h+var_30]
0x14029219b  mov     [rsp+0E0h+var_C0], rax
0x1402921a0  xor     r9d, r9d
0x1402921a3  xor     r8d, r8d
0x1402921a6  lea     edx, [r9+3]
0x1402921aa  mov     rcx, rbx
0x1402921ad  call    cs:__imp_VidGetSystemInformation
0x1402921b4  nop     dword ptr [rax+rax+00h]
0x1402921b9  mov     rcx, [rbp+5Fh]; this
0x1402921bd  test    eax, eax
0x1402921bf  jnz     short loc_1402921D3
0x1402921c1  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\management\\resou"...
0x1402921c8  mov     edx, 122h; void *
0x1402921cd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1402921d3  mov     ecx, dword ptr [rbp+57h+var_30]
0x1402921d6  mov     edx, ecx
0x1402921d8  shr     edx, 1
0x1402921da  mov     r8b, 1
0x1402921dd  and     dl, r8b
0x1402921e0  mov     byte ptr [rbp+57h+var_A0], dl
0x1402921e3  mov     eax, ecx
0x1402921e5  shr     eax, 4
0x1402921e8  and     al, r8b
0x1402921eb  mov     byte ptr [rbp+57h+var_A0+3], al
0x1402921ee  mov     eax, ecx
0x1402921f0  shr     eax, 2
0x1402921f3  and     al, r8b
0x1402921f6  mov     byte ptr [rbp+57h+var_A0+1], al
0x1402921f9  shr     ecx, 3
0x1402921fc  and     cl, r8b
0x1402921ff  mov     byte ptr [rbp+57h+var_A0+2], cl
0x140292202  mov     eax, dword ptr [rbp+57h+var_20]
0x140292205  mov     dword ptr [rbp+57h+var_A0+4], eax
0x140292208  test    dl, dl
0x14029220a  jz      loc_1402922D0
0x140292210  lea     r8, [rbp+57h+var_68]
0x140292214  mov     edx, 5000Fh
0x140292219  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14029221d  call    cs:__imp_VidGetPartitionProperty
0x140292224  nop     dword ptr [rax+rax+00h]
0x140292229  mov     rcx, [rbp+5Fh]; this
0x14029222d  test    eax, eax
0x14029222f  jnz     short loc_140292243
0x140292231  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\management\\resou"...
0x140292238  mov     edx, 12Fh; void *
0x14029223d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140292243  mov     rax, [rbp+57h+var_68]
0x140292247  mov     dword ptr [rbp+57h+var_A0+8], eax
0x14029224a  mov     dword ptr [rbp+57h+var_60+8], 2
0x140292251  mov     dword ptr [rbp+57h+var_60+0Ch], eax
0x140292254  xorps   xmm0, xmm0
0x140292257  movups  [rbp+57h+var_50], xmm0
0x14029225b  movups  [rbp+57h+var_40], xmm0
0x14029225f  mov     [rsp+0E0h+var_B0], 0
0x140292268  mov     [rsp+0E0h+var_B8], 20h ; ' '
0x140292270  lea     rax, [rbp+57h+var_50]
0x140292274  mov     [rsp+0E0h+var_C0], rax
0x140292279  mov     r9d, 8
0x14029227f  lea     r8, [rbp+57h+var_60+8]
0x140292283  lea     edx, [r9-3]
0x140292287  mov     rcx, rbx
0x14029228a  call    cs:__imp_VidGetSystemInformation
0x140292291  nop     dword ptr [rax+rax+00h]
0x140292296  mov     rcx, [rbp+5Fh]; this
0x14029229a  test    eax, eax
0x14029229c  jnz     short loc_1402922B0
0x14029229e  lea     r8, aOnecoreVmCompu_23; "onecore\\vm\\compute\\management\\resou"...
0x1402922a5  mov     edx, 143h; void *
0x1402922aa  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1402922b0  cmp     byte ptr [rbp+57h+var_50], 0
0x1402922b4  setnz   byte ptr [rbp+57h+var_80+8]
0x1402922b8  mov     rax, qword ptr [rbp+57h+var_50+8]
0x1402922bc  mov     qword ptr [rbp+57h+var_90], rax
0x1402922c0  mov     rax, qword ptr [rbp+57h+var_40]
0x1402922c4  mov     qword ptr [rbp+57h+var_90+8], rax
0x1402922c8  mov     rax, qword ptr [rbp+57h+var_40+8]
0x1402922cc  mov     qword ptr [rbp+57h+var_80], rax
0x1402922d0  movups  xmm0, [rbp+57h+var_A0]
0x1402922d4  movups  xmmword ptr [rdi], xmm0
0x1402922d7  movups  xmm1, [rbp+57h+var_90]
0x1402922db  movups  xmmword ptr [rdi+10h], xmm1
0x1402922df  movups  xmm0, [rbp+57h+var_80]
0x1402922e3  movups  xmmword ptr [rdi+20h], xmm0
0x1402922e7  lea     rcx, [rbp+57h+var_70]
0x1402922eb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?VidCloseStatisticsHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>(void)
0x1402922f0  mov     rax, rdi
0x1402922f3  mov     rcx, [rbp+57h+var_10]
0x1402922f7  xor     rcx, rsp; StackCookie
0x1402922fa  call    __security_check_cookie
0x1402922ff  lea     r11, [rsp+0E0h+var_s0]
0x140292307  mov     rbx, [r11+10h]
0x14029230b  mov     rdi, [r11+18h]
0x14029230f  mov     rsp, r11
0x140292312  pop     rbp
0x140292313  retn
```
