# ChannelPublishingConfigData::ChannelPublishingConfigData(ChannelConfigReader const &)

- ea: `0x14000750c`
- end: `0x1400076ad`
- name: `??0ChannelPublishingConfigData@@QEAA@AEBVChannelConfigReader@@@Z`
- size: `417`
- prototype: `ChannelPublishingConfigData *(ChannelPublishingConfigData *__hidden this, const struct ChannelConfigReader *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400073ec`

## callees

- `0x14000750c`
- `0x1400076b4`
- `0x1400161fc`
- `0x140016284`
- `0x140019348`
- `0x14001ad34`
- `0x14001b580`
- `0x14001b5b4`

## string_xrefs

- `0x140007660`: `SidType`

## pseudocode

```c
ChannelPublishingConfigData *__fastcall ChannelPublishingConfigData::ChannelPublishingConfigData(
        ChannelPublishingConfigData *this,
        const struct ChannelConfigReader *a2)
{
  char v4; // bp
  unsigned int v5; // r14d
  __int64 v6; // r15
  __int64 v7; // rbx
  __int64 v8; // rbx
  int v9; // ebx
  unsigned int DWORDHelper; // eax
  __int64 v11; // rcx
  unsigned int v12; // eax
  char v13; // cl
  ChannelPublishingConfigData *result; // rax
  __int64 v15; // [rsp+20h] [rbp-48h] BYREF
  __int64 v16; // [rsp+28h] [rbp-40h]

  *(_QWORD *)this = ChannelConfigReader::GetKeywords(a2);
  ChannelConfigReader::GetControlGuid(a2, (struct _GUID *)((char *)this + 8));
  v4 = 1;
  if ( (unsigned int)(*((_DWORD *)a2 + 34) - 2) > 1 )
  {
    v6 = *((_QWORD *)a2 + 4);
    v7 = *((_QWORD *)a2 + 5) - v6;
    v15 = v6;
    v8 = v7 >> 1;
    v16 = v8;
    v5 = 64;
    if ( !(unsigned __int8)IsSystemChannel(&v15) )
    {
      v15 = v6;
      v16 = v8;
      IsSecurityChannel(&v15);
    }
  }
  else
  {
    v5 = 4;
  }
  *((_DWORD *)this + 6) = GetDWORDHelper(*(_QWORD *)a2, v5, L"BufferSize");
  *((_DWORD *)this + 7) = GetDWORDHelper(*(_QWORD *)a2, 0, L"MinBuffers");
  *((_DWORD *)this + 8) = ChannelConfigReader::GetMaxBuffers(a2);
  v9 = 1000;
  DWORDHelper = GetDWORDHelper(*(_QWORD *)a2, (unsigned int)(*((_DWORD *)a2 + 34) - 2) <= 1 ? 5000 : 1000, L"Latency");
  if ( DWORDHelper > 0x3E8 )
    v9 = DWORDHelper;
  *((_DWORD *)this + 9) = v9;
  *((_DWORD *)this + 10) = GetDWORDHelper(*(_QWORD *)a2, 1, L"FileMax");
  *((_DWORD *)this + 11) = GetDWORDHelper(*(_QWORD *)a2, 0, L"FileCounter");
  *((_BYTE *)this + 48) = GetDWORDHelper(*(_QWORD *)a2, 0, L"ClockType");
  v11 = *((_QWORD *)a2 + 5) - *((_QWORD *)a2 + 4);
  v15 = *((_QWORD *)a2 + 4);
  v16 = v11 >> 1;
  if ( !(unsigned __int8)IsCoreChannel(&v15) )
    v4 = GetDWORDHelper(*(_QWORD *)a2, (unsigned int)(*((_DWORD *)a2 + 34) - 2) > 1, L"SidType");
  *((_BYTE *)this + 49) = v4;
  v12 = GetDWORDHelper(*(_QWORD *)a2, 0, L"Level");
  v13 = -1;
  if ( v12 < 0xFF )
    v13 = v12;
  result = this;
  *((_BYTE *)this + 50) = v13;
  return result;
}

```

## disassembly

```asm
0x14000750c  push    rbx
0x14000750e  push    rbp
0x14000750f  push    rsi
0x140007510  push    rdi
0x140007511  push    r14
0x140007513  push    r15
0x140007515  sub     rsp, 38h
0x140007519  mov     rsi, rcx
0x14000751c  mov     rdi, rdx
0x14000751f  mov     rcx, rdx; this
0x140007522  call    ?GetKeywords@ChannelConfigReader@@QEBA_KXZ; ChannelConfigReader::GetKeywords(void)
0x140007527  lea     rdx, [rsi+8]; retstr
0x14000752b  mov     [rsi], rax
0x14000752e  mov     rcx, rdi; this
0x140007531  call    ?GetControlGuid@ChannelConfigReader@@QEBA?AU_GUID@@XZ; ChannelConfigReader::GetControlGuid(void)
0x140007536  mov     eax, [rdi+88h]
0x14000753c  mov     ebp, 1
0x140007541  sub     eax, 2
0x140007544  cmp     eax, ebp
0x140007546  ja      short loc_14000754E
0x140007548  lea     r14d, [rbp+3]
0x14000754c  jmp     short loc_14000758E
0x14000754e  mov     r15, [rdi+20h]
0x140007552  lea     rcx, [rsp+68h+var_48]
0x140007557  mov     rbx, [rdi+28h]
0x14000755b  sub     rbx, r15
0x14000755e  mov     [rsp+68h+var_48], r15
0x140007563  sar     rbx, 1
0x140007566  mov     [rsp+68h+var_40], rbx
0x14000756b  call    ?IsSystemChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSystemChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140007570  mov     r14d, 40h ; '@'
0x140007576  test    al, al
0x140007578  jnz     short loc_14000758E
0x14000757a  lea     rcx, [rsp+68h+var_48]
0x14000757f  mov     [rsp+68h+var_48], r15
0x140007584  mov     [rsp+68h+var_40], rbx
0x140007589  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x14000758e  mov     rcx, [rdi]
0x140007591  lea     r8, aBuffersize_0; "BufferSize"
0x140007598  mov     edx, r14d
0x14000759b  call    GetDWORDHelper
0x1400075a0  mov     [rsi+18h], eax
0x1400075a3  lea     r8, aMinbuffers; "MinBuffers"
0x1400075aa  mov     rcx, [rdi]
0x1400075ad  xor     edx, edx
0x1400075af  call    GetDWORDHelper
0x1400075b4  mov     rcx, rdi; this
0x1400075b7  mov     [rsi+1Ch], eax
0x1400075ba  call    ?GetMaxBuffers@ChannelConfigReader@@QEBAKXZ; ChannelConfigReader::GetMaxBuffers(void)
0x1400075bf  mov     [rsi+20h], eax
0x1400075c2  lea     r8, aLatency; "Latency"
0x1400075c9  mov     eax, [rdi+88h]
0x1400075cf  mov     ebx, 3E8h
0x1400075d4  mov     rcx, [rdi]
0x1400075d7  sub     eax, 2
0x1400075da  cmp     eax, ebp
0x1400075dc  setbe   al
0x1400075df  neg     al
0x1400075e1  sbb     edx, edx
0x1400075e3  and     edx, 0FA0h
0x1400075e9  add     edx, ebx
0x1400075eb  call    GetDWORDHelper
0x1400075f0  cmp     eax, ebx
0x1400075f2  lea     r8, aFilemax; "FileMax"
0x1400075f9  mov     edx, ebp
0x1400075fb  cmova   ebx, eax
0x1400075fe  mov     [rsi+24h], ebx
0x140007601  mov     rcx, [rdi]
0x140007604  call    GetDWORDHelper
0x140007609  mov     [rsi+28h], eax
0x14000760c  lea     r8, aFilecounter; "FileCounter"
0x140007613  mov     rcx, [rdi]
0x140007616  xor     edx, edx
0x140007618  call    GetDWORDHelper
0x14000761d  mov     [rsi+2Ch], eax
0x140007620  lea     r8, aClocktype; "ClockType"
0x140007627  mov     rcx, [rdi]
0x14000762a  xor     edx, edx
0x14000762c  call    GetDWORDHelper
0x140007631  mov     [rsi+30h], al
0x140007634  mov     rax, [rdi+20h]
0x140007638  mov     rcx, [rdi+28h]
0x14000763c  sub     rcx, rax
0x14000763f  mov     [rsp+68h+var_48], rax
0x140007644  sar     rcx, 1
0x140007647  mov     [rsp+68h+var_40], rcx
0x14000764c  lea     rcx, [rsp+68h+var_48]
0x140007651  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140007656  test    al, al
0x140007658  jnz     short loc_14000767B
0x14000765a  mov     eax, [rdi+88h]
0x140007660  lea     r8, aSidtype; "SidType"
0x140007667  mov     rcx, [rdi]
0x14000766a  xor     edx, edx
0x14000766c  sub     eax, 2
0x14000766f  cmp     eax, ebp
0x140007671  setnbe  dl
0x140007674  call    GetDWORDHelper
0x140007679  mov     ebp, eax
0x14000767b  mov     [rsi+31h], bpl
0x14000767f  lea     r8, aLevel_0; "Level"
0x140007686  mov     rcx, [rdi]
0x140007689  xor     edx, edx
0x14000768b  call    GetDWORDHelper
0x140007690  mov     ecx, 0FFh
0x140007695  cmp     eax, ecx
0x140007697  cmovb   ecx, eax
0x14000769a  mov     rax, rsi
0x14000769d  mov     [rsi+32h], cl
0x1400076a0  add     rsp, 38h
0x1400076a4  pop     r15
0x1400076a6  pop     r14
0x1400076a8  pop     rdi
0x1400076a9  pop     rsi
0x1400076aa  pop     rbp
0x1400076ab  pop     rbx
0x1400076ac  retn
```
