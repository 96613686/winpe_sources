# uus::UndockedUpdateCoreTelemetry::UusUpdatedActiveVersion(UusVersion const &,bool,uus::UusInfo const &,bool,UusVersion const &,wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x180009938`
- end: `0x180009c03`
- name: `?UusUpdatedActiveVersion@UndockedUpdateCoreTelemetry@uus@@SAXAEBVUusVersion@@_NAEBUUusInfo@2@10PEB_W33H@Z`
- size: `715`
- prototype: `void __fastcall(const struct UusVersion *, bool, const struct uus::UusInfo *, bool, const struct UusVersion *, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000e888`

## callees

- `0x18000109c`
- `0x1800089f4`
- `0x1800097d8`
- `0x180009938`
- `0x180029644`
- `0x1800427d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall uus::UndockedUpdateCoreTelemetry::UusUpdatedActiveVersion(
        const struct UusVersion *a1,
        char a2,
        const struct uus::UusInfo *a3,
        char a4,
        const struct UusVersion *a5,
        const wchar_t *a6,
        const wchar_t *a7,
        const wchar_t *a8,
        int a9)
{
  const struct _tlgProvider_t *v13; // r13
  __int64 String; // rax
  const wchar_t *v15; // rbx
  const wchar_t *v16; // rsi
  const wchar_t *v17; // rdi
  __int64 v18; // rax
  const wchar_t *v19; // r9
  int v20; // r8d
  __int64 v21; // rcx
  const wchar_t *v22; // rax
  __int64 v23; // rdx
  int v24; // edx
  const wchar_t *v25; // rax
  __int64 v26; // rdx
  int v27; // edx
  const wchar_t *v28; // rax
  __int64 v29; // rdx
  int v30; // edx
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rax
  int v36; // eax
  char v37; // [rsp+30h] [rbp-D0h] BYREF
  char v38; // [rsp+31h] [rbp-CFh] BYREF
  int v39; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v40; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v41[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v42[32]; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v43; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v44; // [rsp+A0h] [rbp-60h]
  __int64 v45; // [rsp+A8h] [rbp-58h]
  const wchar_t *v46; // [rsp+B0h] [rbp-50h]
  int v47; // [rsp+B8h] [rbp-48h]
  int v48; // [rsp+BCh] [rbp-44h]
  char *v49; // [rsp+C0h] [rbp-40h]
  __int64 v50; // [rsp+C8h] [rbp-38h]
  const wchar_t *v51; // [rsp+D0h] [rbp-30h]
  int v52; // [rsp+D8h] [rbp-28h]
  int v53; // [rsp+DCh] [rbp-24h]
  const wchar_t *v54; // [rsp+E0h] [rbp-20h]
  int v55; // [rsp+E8h] [rbp-18h]
  int v56; // [rsp+ECh] [rbp-14h]
  char *v57; // [rsp+F0h] [rbp-10h]
  __int64 v58; // [rsp+F8h] [rbp-8h]
  const wchar_t *v59; // [rsp+100h] [rbp+0h]
  int v60; // [rsp+108h] [rbp+8h]
  int v61; // [rsp+10Ch] [rbp+Ch]
  const wchar_t *v62; // [rsp+110h] [rbp+10h]
  int v63; // [rsp+118h] [rbp+18h]
  int v64; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v65; // [rsp+120h] [rbp+20h]
  int v66; // [rsp+128h] [rbp+28h]
  int v67; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v68; // [rsp+130h] [rbp+30h]
  int v69; // [rsp+138h] [rbp+38h]
  int v70; // [rsp+13Ch] [rbp+3Ch]
  int *v71; // [rsp+140h] [rbp+40h]
  __int64 v72; // [rsp+148h] [rbp+48h]

  v13 = uus::UndockedUpdateCoreTelemetry::Provider();
  if ( *(_DWORD *)v13 > 5u
    && (*((_QWORD *)v13 + 2) & 0x800000000000LL) != 0
    && (*((_QWORD *)v13 + 3) & 0x800000000000LL) == *((_QWORD *)v13 + 3) )
  {
    v39 = a9;
    String = UusVersion::GetString(a5, v42);
    v15 = (const wchar_t *)String;
    if ( *(_QWORD *)(String + 24) > 7u )
      v15 = *(const wchar_t **)String;
    v37 = a4;
    v16 = (const wchar_t *)*((_QWORD *)a3 + 1);
    v17 = *(const wchar_t **)a3;
    v38 = a2;
    v18 = UusVersion::GetString(a1, v41);
    v19 = (const wchar_t *)v18;
    if ( *(_QWORD *)(v18 + 24) > 7u )
      v19 = *(const wchar_t **)v18;
    v40 = 0x1000000;
    v71 = &v39;
    v72 = 4;
    v20 = 2;
    v21 = -1;
    v22 = a8;
    if ( a8 )
    {
      v23 = -1;
      do
        ++v23;
      while ( a8[v23] );
      v24 = 2 * v23 + 2;
    }
    else
    {
      v22 = &qword_180050DC0;
      v24 = 2;
    }
    v68 = v22;
    v69 = v24;
    v70 = 0;
    v25 = a7;
    if ( a7 )
    {
      v26 = -1;
      do
        ++v26;
      while ( a7[v26] );
      v27 = 2 * v26 + 2;
    }
    else
    {
      v25 = &qword_180050DC0;
      v27 = 2;
    }
    v65 = v25;
    v66 = v27;
    v67 = 0;
    v28 = a6;
    if ( a6 )
    {
      v29 = -1;
      do
        ++v29;
      while ( a6[v29] );
      v30 = 2 * v29 + 2;
    }
    else
    {
      v28 = &qword_180050DC0;
      v30 = 2;
    }
    v62 = v28;
    v63 = v30;
    v64 = 0;
    if ( v15 )
    {
      v31 = -1;
      do
        ++v31;
      while ( v15[v31] );
      v32 = 2 * v31 + 2;
    }
    else
    {
      v15 = &qword_180050DC0;
      v32 = 2;
    }
    v59 = v15;
    v60 = v32;
    v61 = 0;
    v57 = &v37;
    v58 = 1;
    if ( v16 )
    {
      v33 = -1;
      do
        ++v33;
      while ( v16[v33] );
      v34 = 2 * v33 + 2;
    }
    else
    {
      v16 = &qword_180050DC0;
      v34 = 2;
    }
    v54 = v16;
    v55 = v34;
    v56 = 0;
    if ( v17 )
    {
      v35 = -1;
      do
        ++v35;
      while ( v17[v35] );
      v36 = 2 * v35 + 2;
    }
    else
    {
      v17 = &qword_180050DC0;
      v36 = 2;
    }
    v51 = v17;
    v52 = v36;
    v53 = 0;
    v49 = &v38;
    v50 = 1;
    if ( v19 )
    {
      do
        ++v21;
      while ( v19[v21] );
      v20 = 2 * v21 + 2;
    }
    else
    {
      v19 = &qword_180050DC0;
    }
    v46 = v19;
    v47 = v20;
    v48 = 0;
    v44 = &v40;
    v45 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)v13, (unsigned __int8 *)&byte_180056989, 0, 0, 0xDu, &v43);
    std::wstring::_Tidy_deallocate((__int64)v41);
    std::wstring::_Tidy_deallocate((__int64)v42);
  }
}

```

## disassembly

```asm
0x180009938  mov     [rsp-8+arg_8], rbx
0x18000993d  mov     [rsp-8+arg_10], rsi
0x180009942  push    rbp
0x180009943  push    rdi
0x180009944  push    r13
0x180009946  push    r14
0x180009948  push    r15
0x18000994a  lea     rbp, [rsp-60h]
0x18000994f  sub     rsp, 160h
0x180009956  mov     rax, cs:__security_cookie
0x18000995d  xor     rax, rsp
0x180009960  mov     [rbp+80h+var_30], rax
0x180009964  mov     sil, r9b
0x180009967  mov     rdi, r8
0x18000996a  mov     r14b, dl
0x18000996d  mov     r15, rcx
0x180009970  mov     rbx, [rbp+80h+arg_20]
0x180009977  call    ?Provider@UndockedUpdateCoreTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedUpdateCoreTelemetry::Provider(void)
0x18000997c  mov     r13, rax
0x18000997f  cmp     dword ptr [rax], 5
0x180009982  jbe     loc_180009BDB
0x180009988  mov     rax, 800000000000h
0x180009992  test    [r13+10h], rax
0x180009996  jz      loc_180009BDB
0x18000999c  mov     rcx, [r13+18h]
0x1800099a0  and     rcx, rax
0x1800099a3  cmp     rcx, [r13+18h]
0x1800099a7  jnz     loc_180009BDB
0x1800099ad  mov     eax, [rbp+80h+arg_40]
0x1800099b3  mov     [rsp+180h+var_14C], eax
0x1800099b7  lea     rdx, [rsp+180h+var_120]
0x1800099bc  mov     rcx, rbx
0x1800099bf  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x1800099c4  mov     rbx, rax
0x1800099c7  cmp     qword ptr [rax+18h], 7
0x1800099cc  jbe     short loc_1800099D1
0x1800099ce  mov     rbx, [rax]
0x1800099d1  mov     [rsp+180h+var_150], sil
0x1800099d6  mov     rsi, [rdi+8]
0x1800099da  mov     rdi, [rdi]
0x1800099dd  mov     [rsp+180h+var_14F], r14b
0x1800099e2  lea     rdx, [rsp+180h+var_140]
0x1800099e7  mov     rcx, r15
0x1800099ea  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x1800099ef  mov     r9, rax
0x1800099f2  cmp     qword ptr [rax+18h], 7
0x1800099f7  jbe     short loc_1800099FC
0x1800099f9  mov     r9, [rax]
0x1800099fc  mov     [rsp+180h+var_148], 1000000h
0x180009a05  lea     rax, [rsp+180h+var_14C]
0x180009a0a  mov     [rbp+80h+var_40], rax
0x180009a0e  mov     [rbp+80h+var_38], 4
0x180009a16  xor     r10d, r10d
0x180009a19  lea     r11, qword_180050DC0
0x180009a20  lea     r8d, [r10+2]
0x180009a24  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009a28  mov     rax, [rbp+80h+arg_38]
0x180009a2f  test    rax, rax
0x180009a32  jz      short loc_180009A4A
0x180009a34  mov     rdx, rcx
0x180009a37  inc     rdx
0x180009a3a  cmp     [rax+rdx*2], r10w
0x180009a3f  jnz     short loc_180009A37
0x180009a41  lea     edx, ds:2[rdx*2]
0x180009a48  jmp     short loc_180009A50
0x180009a4a  mov     rax, r11
0x180009a4d  mov     edx, r8d
0x180009a50  mov     [rbp+80h+var_50], rax
0x180009a54  mov     [rbp+80h+var_48], edx
0x180009a57  mov     [rbp+80h+var_44], r10d
0x180009a5b  mov     rax, [rbp+80h+arg_30]
0x180009a62  test    rax, rax
0x180009a65  jz      short loc_180009A7D
0x180009a67  mov     rdx, rcx
0x180009a6a  inc     rdx
0x180009a6d  cmp     [rax+rdx*2], r10w
0x180009a72  jnz     short loc_180009A6A
0x180009a74  lea     edx, ds:2[rdx*2]
0x180009a7b  jmp     short loc_180009A83
0x180009a7d  mov     rax, r11
0x180009a80  mov     edx, r8d
0x180009a83  mov     [rbp+80h+var_60], rax
0x180009a87  mov     [rbp+80h+var_58], edx
0x180009a8a  mov     [rbp+80h+var_54], r10d
0x180009a8e  mov     rax, [rbp+80h+arg_28]
0x180009a95  test    rax, rax
0x180009a98  jz      short loc_180009AB0
0x180009a9a  mov     rdx, rcx
0x180009a9d  inc     rdx
0x180009aa0  cmp     [rax+rdx*2], r10w
0x180009aa5  jnz     short loc_180009A9D
0x180009aa7  lea     edx, ds:2[rdx*2]
0x180009aae  jmp     short loc_180009AB6
0x180009ab0  mov     rax, r11
0x180009ab3  mov     edx, r8d
0x180009ab6  mov     [rbp+80h+var_70], rax
0x180009aba  mov     [rbp+80h+var_68], edx
0x180009abd  mov     [rbp+80h+var_64], r10d
0x180009ac1  test    rbx, rbx
0x180009ac4  jz      short loc_180009ADC
0x180009ac6  mov     rax, rcx
0x180009ac9  inc     rax
0x180009acc  cmp     [rbx+rax*2], r10w
0x180009ad1  jnz     short loc_180009AC9
0x180009ad3  lea     eax, ds:2[rax*2]
0x180009ada  jmp     short loc_180009AE2
0x180009adc  mov     rbx, r11
0x180009adf  mov     eax, r8d
0x180009ae2  mov     [rbp+80h+var_80], rbx
0x180009ae6  mov     [rbp+80h+var_78], eax
0x180009ae9  mov     [rbp+80h+var_74], r10d
0x180009aed  lea     rax, [rsp+180h+var_150]
0x180009af2  mov     [rbp+80h+var_90], rax
0x180009af6  mov     [rbp+80h+var_88], 1
0x180009afe  test    rsi, rsi
0x180009b01  jz      short loc_180009B19
0x180009b03  mov     rax, rcx
0x180009b06  inc     rax
0x180009b09  cmp     [rsi+rax*2], r10w
0x180009b0e  jnz     short loc_180009B06
0x180009b10  lea     eax, ds:2[rax*2]
0x180009b17  jmp     short loc_180009B1F
0x180009b19  mov     rsi, r11
0x180009b1c  mov     eax, r8d
0x180009b1f  mov     [rbp+80h+var_A0], rsi
0x180009b23  mov     [rbp+80h+var_98], eax
0x180009b26  mov     [rbp+80h+var_94], r10d
0x180009b2a  test    rdi, rdi
0x180009b2d  jz      short loc_180009B45
0x180009b2f  mov     rax, rcx
0x180009b32  inc     rax
0x180009b35  cmp     [rdi+rax*2], r10w
0x180009b3a  jnz     short loc_180009B32
0x180009b3c  lea     eax, ds:2[rax*2]
0x180009b43  jmp     short loc_180009B4B
0x180009b45  mov     rdi, r11
0x180009b48  mov     eax, r8d
0x180009b4b  mov     [rbp+80h+var_B0], rdi
0x180009b4f  mov     [rbp+80h+var_A8], eax
0x180009b52  mov     [rbp+80h+var_A4], r10d
0x180009b56  lea     rax, [rsp+180h+var_14F]
0x180009b5b  mov     [rbp+80h+var_C0], rax
0x180009b5f  mov     [rbp+80h+var_B8], 1
0x180009b67  test    r9, r9
0x180009b6a  jz      short loc_180009B80
0x180009b6c  inc     rcx
0x180009b6f  cmp     [r9+rcx*2], r10w
0x180009b74  jnz     short loc_180009B6C
0x180009b76  lea     r8d, ds:2[rcx*2]
0x180009b7e  jmp     short loc_180009B83
0x180009b80  mov     r9, r11
0x180009b83  mov     [rbp+80h+var_D0], r9
0x180009b87  mov     [rbp+80h+var_C8], r8d
0x180009b8b  mov     [rbp+80h+var_C4], r10d
0x180009b8f  lea     rax, [rsp+180h+var_148]
0x180009b94  mov     [rbp+80h+var_E0], rax
0x180009b98  mov     [rbp+80h+var_D8], 8
0x180009ba0  lea     rax, [rbp+80h+var_100]
0x180009ba4  mov     [rsp+180h+var_158], rax; PEVENT_DATA_DESCRIPTOR
0x180009ba9  mov     [rsp+180h+var_160], 0Dh; ULONG
0x180009bb1  xor     r9d, r9d; int
0x180009bb4  xor     r8d, r8d; int
0x180009bb7  lea     rdx, byte_180056989; int
0x180009bbe  mov     rcx, r13; int
0x180009bc1  call    _tlgWriteTransfer_EventWriteTransfer
0x180009bc6  lea     rcx, [rsp+180h+var_140]
0x180009bcb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009bd0  nop
0x180009bd1  lea     rcx, [rsp+180h+var_120]
0x180009bd6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009bdb  mov     rcx, [rbp+80h+var_30]
0x180009bdf  xor     rcx, rsp; StackCookie
0x180009be2  call    __security_check_cookie
0x180009be7  lea     r11, [rsp+180h+var_20]
0x180009bef  mov     rbx, [r11+38h]
0x180009bf3  mov     rsi, [r11+40h]
0x180009bf7  mov     rsp, r11
0x180009bfa  pop     r15
0x180009bfc  pop     r14
0x180009bfe  pop     r13
0x180009c00  pop     rdi
0x180009c01  pop     rbp
0x180009c02  retn
```
