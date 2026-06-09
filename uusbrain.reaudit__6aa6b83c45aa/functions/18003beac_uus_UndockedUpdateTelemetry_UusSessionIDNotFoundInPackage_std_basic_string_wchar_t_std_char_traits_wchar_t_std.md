# uus::UndockedUpdateTelemetry::UusSessionIDNotFoundInPackage(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x18003beac`
- end: `0x18003c0e0`
- name: `?UusSessionIDNotFoundInPackage@UndockedUpdateTelemetry@uus@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@Vpath@filesystem@std@@@4@V?$optional@VUusVersion@@@4@0@Z`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800394b8`

## callees

- `0x18000109c`
- `0x18000868c`
- `0x1800089f4`
- `0x180029644`
- `0x18003beac`
- `0x1800427d0`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall uus::UndockedUpdateTelemetry::UusSessionIDNotFoundInPackage(
        const wchar_t *a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4)
{
  char v8; // r12
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r13
  const wchar_t *v11; // rsi
  const wchar_t *String; // rax
  int v13; // r8d
  __int64 v14; // rcx
  __int64 v15; // rdx
  int v16; // edx
  __int64 v17; // rdx
  int v18; // edx
  __int64 v19; // rax
  int v20; // eax
  __int64 v22; // [rsp+30h] [rbp-99h] BYREF
  _BYTE v23[32]; // [rsp+38h] [rbp-91h] BYREF
  __int64 v24; // [rsp+58h] [rbp-71h]
  __int64 v25; // [rsp+60h] [rbp-69h]
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+70h] [rbp-59h] BYREF
  __int64 *v27; // [rsp+90h] [rbp-39h]
  __int64 v28; // [rsp+98h] [rbp-31h]
  const wchar_t *v29; // [rsp+A0h] [rbp-29h]
  int v30; // [rsp+A8h] [rbp-21h]
  int v31; // [rsp+ACh] [rbp-1Dh]
  const wchar_t *v32; // [rsp+B0h] [rbp-19h]
  int v33; // [rsp+B8h] [rbp-11h]
  int v34; // [rsp+BCh] [rbp-Dh]
  const wchar_t *v35; // [rsp+C0h] [rbp-9h]
  int v36; // [rsp+C8h] [rbp-1h]
  int v37; // [rsp+CCh] [rbp+3h]
  const wchar_t *v38; // [rsp+D0h] [rbp+7h]
  int v39; // [rsp+D8h] [rbp+Fh]
  int v40; // [rsp+DCh] [rbp+13h]

  v24 = a2;
  v25 = a3;
  v8 = 0;
  LODWORD(v22) = 0;
  v9 = uus::UndockedUpdateTelemetry::Provider();
  v10 = (__int64)v9;
  if ( *(_DWORD *)v9 > 5u )
  {
    LODWORD(v9) = 0;
    if ( (*(_QWORD *)(v10 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v10 + 24) & 0x400000000000LL) == *(_QWORD *)(v10 + 24) )
    {
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const wchar_t **)a4;
      v11 = L"?";
      if ( *(_BYTE *)(a3 + 16) )
      {
        String = (const wchar_t *)UusVersion::GetString(a3, v23);
        v8 = 1;
        if ( *((_QWORD *)String + 3) > 7u )
          String = *(const wchar_t **)String;
      }
      else
      {
        String = L"?";
      }
      if ( *(_BYTE *)(a2 + 32) )
      {
        v11 = (const wchar_t *)a2;
        if ( *(_QWORD *)(a2 + 24) > 7u )
          v11 = *(const wchar_t **)a2;
      }
      if ( *((_QWORD *)a1 + 3) > 7u )
        a1 = *(const wchar_t **)a1;
      v22 = 0x2000000;
      v13 = 2;
      v14 = -1;
      if ( a4 )
      {
        v15 = -1;
        do
          ++v15;
        while ( a4[v15] );
        v16 = 2 * v15 + 2;
      }
      else
      {
        a4 = &qword_180050DC0;
        v16 = 2;
      }
      v38 = a4;
      v39 = v16;
      v40 = 0;
      if ( String )
      {
        v17 = -1;
        do
          ++v17;
        while ( String[v17] );
        v18 = 2 * v17 + 2;
      }
      else
      {
        String = &qword_180050DC0;
        v18 = 2;
      }
      v35 = String;
      v36 = v18;
      v37 = 0;
      if ( v11 )
      {
        v19 = -1;
        do
          ++v19;
        while ( v11[v19] );
        v20 = 2 * v19 + 2;
      }
      else
      {
        v11 = &qword_180050DC0;
        v20 = 2;
      }
      v32 = v11;
      v33 = v20;
      v34 = 0;
      if ( a1 )
      {
        do
          ++v14;
        while ( a1[v14] );
        v13 = 2 * v14 + 2;
      }
      else
      {
        a1 = &qword_180050DC0;
      }
      v29 = a1;
      v30 = v13;
      v31 = 0;
      v27 = &v22;
      v28 = 8;
      LODWORD(v9) = tlgWriteTransfer_EventWriteTransfer(v10, (unsigned __int8 *)&word_180056FB6, 0, 0, 7u, &v26);
      if ( (v8 & 1) != 0 )
        LODWORD(v9) = std::wstring::_Tidy_deallocate(v23);
    }
  }
  if ( *(_BYTE *)(a2 + 32) )
    LODWORD(v9) = std::wstring::_Tidy_deallocate(a2);
  if ( *(_BYTE *)(a3 + 16) )
    LODWORD(v9) = (**(__int64 (__fastcall ***)(__int64, _QWORD))a3)(a3, 0);
  return (int)v9;
}

```

## disassembly

```asm
0x18003beac  mov     [rsp-8+arg_0], rbx
0x18003beb1  push    rbp
0x18003beb2  push    rsi
0x18003beb3  push    rdi
0x18003beb4  push    r12
0x18003beb6  push    r13
0x18003beb8  push    r14
0x18003beba  push    r15
0x18003bebc  lea     rbp, [rsp-27h]
0x18003bec1  sub     rsp, 0F0h
0x18003bec8  mov     rax, cs:__security_cookie
0x18003becf  xor     rax, rsp
0x18003bed2  mov     [rbp+57h+var_40], rax
0x18003bed6  mov     rbx, r9
0x18003bed9  mov     r14, r8
0x18003bedc  mov     rdi, rdx
0x18003bedf  mov     r15, rcx
0x18003bee2  mov     [rbp+57h+var_C8], rdx
0x18003bee6  mov     [rbp+57h+var_C0], r8
0x18003beea  xor     esi, esi
0x18003beec  mov     r12d, esi
0x18003beef  mov     dword ptr [rsp+120h+var_F0], esi
0x18003bef3  call    ?Provider@UndockedUpdateTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedUpdateTelemetry::Provider(void)
0x18003bef8  mov     r13, rax
0x18003befb  cmp     dword ptr [rax], 5
0x18003befe  jbe     loc_18003C094
0x18003bf04  mov     rax, 400000000000h
0x18003bf0e  test    [r13+10h], rax
0x18003bf12  jz      loc_18003C094
0x18003bf18  mov     rcx, [r13+18h]
0x18003bf1c  and     rcx, rax
0x18003bf1f  cmp     rcx, [r13+18h]
0x18003bf23  jnz     loc_18003C094
0x18003bf29  cmp     qword ptr [rbx+18h], 7
0x18003bf2e  jbe     short loc_18003BF33
0x18003bf30  mov     rbx, [rbx]
0x18003bf33  lea     rsi, asc_180052F84; "?"
0x18003bf3a  xor     r9d, r9d
0x18003bf3d  cmp     [r14+10h], r9b
0x18003bf41  jz      short loc_18003BF65
0x18003bf43  lea     rdx, [rsp+120h+var_E8]
0x18003bf48  mov     rcx, r14
0x18003bf4b  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x18003bf50  mov     r12d, 1
0x18003bf56  cmp     qword ptr [rax+18h], 7
0x18003bf5b  jbe     short loc_18003BF60
0x18003bf5d  mov     rax, [rax]
0x18003bf60  xor     r9d, r9d
0x18003bf63  jmp     short loc_18003BF68
0x18003bf65  mov     rax, rsi
0x18003bf68  cmp     [rdi+20h], r9b
0x18003bf6c  jz      short loc_18003BF7B
0x18003bf6e  mov     rsi, rdi
0x18003bf71  cmp     qword ptr [rdi+18h], 7
0x18003bf76  jbe     short loc_18003BF7B
0x18003bf78  mov     rsi, [rdi]
0x18003bf7b  cmp     qword ptr [r15+18h], 7
0x18003bf80  jbe     short loc_18003BF85
0x18003bf82  mov     r15, [r15]
0x18003bf85  mov     [rsp+120h+var_F0], 2000000h
0x18003bf8e  lea     r10, qword_180050DC0
0x18003bf95  mov     r8d, 2
0x18003bf9b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003bf9f  test    rbx, rbx
0x18003bfa2  jz      short loc_18003BFBA
0x18003bfa4  mov     rdx, rcx
0x18003bfa7  inc     rdx
0x18003bfaa  cmp     [rbx+rdx*2], r9w
0x18003bfaf  jnz     short loc_18003BFA7
0x18003bfb1  lea     edx, ds:2[rdx*2]
0x18003bfb8  jmp     short loc_18003BFC0
0x18003bfba  mov     rbx, r10
0x18003bfbd  mov     edx, r8d
0x18003bfc0  mov     [rbp+57h+var_50], rbx
0x18003bfc4  mov     [rbp+57h+var_48], edx
0x18003bfc7  mov     [rbp+57h+var_44], r9d
0x18003bfcb  test    rax, rax
0x18003bfce  jz      short loc_18003BFE6
0x18003bfd0  mov     rdx, rcx
0x18003bfd3  inc     rdx
0x18003bfd6  cmp     [rax+rdx*2], r9w
0x18003bfdb  jnz     short loc_18003BFD3
0x18003bfdd  lea     edx, ds:2[rdx*2]
0x18003bfe4  jmp     short loc_18003BFEC
0x18003bfe6  mov     rax, r10
0x18003bfe9  mov     edx, r8d
0x18003bfec  mov     [rbp+57h+var_60], rax
0x18003bff0  mov     [rbp+57h+var_58], edx
0x18003bff3  mov     [rbp+57h+var_54], r9d
0x18003bff7  test    rsi, rsi
0x18003bffa  jz      short loc_18003C012
0x18003bffc  mov     rax, rcx
0x18003bfff  inc     rax
0x18003c002  cmp     [rsi+rax*2], r9w
0x18003c007  jnz     short loc_18003BFFF
0x18003c009  lea     eax, ds:2[rax*2]
0x18003c010  jmp     short loc_18003C018
0x18003c012  mov     rsi, r10
0x18003c015  mov     eax, r8d
0x18003c018  mov     [rbp+57h+var_70], rsi
0x18003c01c  mov     [rbp+57h+var_68], eax
0x18003c01f  mov     [rbp+57h+var_64], r9d
0x18003c023  test    r15, r15
0x18003c026  jz      short loc_18003C03C
0x18003c028  inc     rcx
0x18003c02b  cmp     [r15+rcx*2], r9w
0x18003c030  jnz     short loc_18003C028
0x18003c032  lea     r8d, ds:2[rcx*2]
0x18003c03a  jmp     short loc_18003C03F
0x18003c03c  mov     r15, r10
0x18003c03f  mov     [rbp+57h+var_80], r15
0x18003c043  mov     [rbp+57h+var_78], r8d
0x18003c047  mov     [rbp+57h+var_74], r9d
0x18003c04b  lea     rax, [rsp+120h+var_F0]
0x18003c050  mov     [rbp+57h+var_90], rax
0x18003c054  mov     [rbp+57h+var_88], 8
0x18003c05c  lea     rax, [rbp+57h+var_B0]
0x18003c060  mov     [rsp+120h+var_F8], rax; PEVENT_DATA_DESCRIPTOR
0x18003c065  mov     [rsp+120h+var_100], 7; ULONG
0x18003c06d  xor     r9d, r9d; int
0x18003c070  xor     r8d, r8d; int
0x18003c073  lea     rdx, word_180056FB6; int
0x18003c07a  mov     rcx, r13; int
0x18003c07d  call    _tlgWriteTransfer_EventWriteTransfer
0x18003c082  test    r12b, 1
0x18003c086  jz      short loc_18003C092
0x18003c088  lea     rcx, [rsp+120h+var_E8]
0x18003c08d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c092  xor     esi, esi
0x18003c094  cmp     [rdi+20h], sil
0x18003c098  jz      short loc_18003C0A3
0x18003c09a  mov     rcx, rdi
0x18003c09d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c0a2  nop
0x18003c0a3  cmp     [r14+10h], sil
0x18003c0a7  jz      short loc_18003C0B9
0x18003c0a9  mov     rax, [r14]
0x18003c0ac  xor     edx, edx
0x18003c0ae  mov     rcx, r14
0x18003c0b1  mov     rax, [rax]
0x18003c0b4  call    _guard_dispatch_icall
0x18003c0b9  mov     rcx, [rbp+57h+var_40]
0x18003c0bd  xor     rcx, rsp; StackCookie
0x18003c0c0  call    __security_check_cookie
0x18003c0c5  mov     rbx, [rsp+120h+arg_0]
0x18003c0cd  add     rsp, 0F0h
0x18003c0d4  pop     r15
0x18003c0d6  pop     r14
0x18003c0d8  pop     r13
0x18003c0da  pop     r12
0x18003c0dc  pop     rdi
0x18003c0dd  pop     rsi
0x18003c0de  pop     rbp
0x18003c0df  retn
```
