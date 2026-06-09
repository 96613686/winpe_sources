# uus::UndockedUpdateTelemetry::UusComponentDisabledByVelocity(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,uint)

- ea: `0x18003bc5c`
- end: `0x18003bea6`
- name: `?UusComponentDisabledByVelocity@UndockedUpdateTelemetry@uus@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@Vpath@filesystem@std@@@4@V?$optional@VUusVersion@@@4@0I@Z`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800394b8`

## callees

- `0x18000109c`
- `0x18000868c`
- `0x1800089f4`
- `0x180029644`
- `0x18003bc5c`
- `0x1800427d0`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall uus::UndockedUpdateTelemetry::UusComponentDisabledByVelocity(
        const wchar_t *a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        int a5)
{
  char v9; // r12
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r13
  const wchar_t *v12; // rdi
  const wchar_t *String; // rax
  int v14; // r8d
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // edx
  __int64 v18; // rdx
  int v19; // edx
  __int64 v20; // rax
  int v21; // eax
  int v23; // [rsp+30h] [rbp-B1h] BYREF
  __int64 v24; // [rsp+38h] [rbp-A9h] BYREF
  _BYTE v25[32]; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v26; // [rsp+60h] [rbp-81h]
  __int64 v27; // [rsp+68h] [rbp-79h]
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+70h] [rbp-71h] BYREF
  __int64 *v29; // [rsp+90h] [rbp-51h]
  __int64 v30; // [rsp+98h] [rbp-49h]
  const wchar_t *v31; // [rsp+A0h] [rbp-41h]
  int v32; // [rsp+A8h] [rbp-39h]
  int v33; // [rsp+ACh] [rbp-35h]
  const wchar_t *v34; // [rsp+B0h] [rbp-31h]
  int v35; // [rsp+B8h] [rbp-29h]
  int v36; // [rsp+BCh] [rbp-25h]
  const wchar_t *v37; // [rsp+C0h] [rbp-21h]
  int v38; // [rsp+C8h] [rbp-19h]
  int v39; // [rsp+CCh] [rbp-15h]
  const wchar_t *v40; // [rsp+D0h] [rbp-11h]
  int v41; // [rsp+D8h] [rbp-9h]
  int v42; // [rsp+DCh] [rbp-5h]
  int *v43; // [rsp+E0h] [rbp-1h]
  __int64 v44; // [rsp+E8h] [rbp+7h]

  v26 = a2;
  v27 = a3;
  v9 = 0;
  v23 = 0;
  v10 = uus::UndockedUpdateTelemetry::Provider();
  v11 = (__int64)v10;
  if ( *(_DWORD *)v10 > 5u )
  {
    LODWORD(v10) = 0;
    if ( (*(_QWORD *)(v11 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v11 + 24) & 0x200000000000LL) == *(_QWORD *)(v11 + 24) )
    {
      v23 = a5;
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const wchar_t **)a4;
      v12 = L"?";
      if ( *(_BYTE *)(a3 + 16) )
      {
        String = (const wchar_t *)UusVersion::GetString(a3, v25);
        v9 = 1;
        if ( *((_QWORD *)String + 3) > 7u )
          String = *(const wchar_t **)String;
      }
      else
      {
        String = L"?";
      }
      if ( *(_BYTE *)(a2 + 32) )
      {
        v12 = (const wchar_t *)a2;
        if ( *(_QWORD *)(a2 + 24) > 7u )
          v12 = *(const wchar_t **)a2;
      }
      if ( *((_QWORD *)a1 + 3) > 7u )
        a1 = *(const wchar_t **)a1;
      v24 = 0x2000000;
      v43 = &v23;
      v44 = 4;
      v14 = 2;
      v15 = -1;
      if ( a4 )
      {
        v16 = -1;
        do
          ++v16;
        while ( a4[v16] );
        v17 = 2 * v16 + 2;
      }
      else
      {
        a4 = &qword_180050DC0;
        v17 = 2;
      }
      v40 = a4;
      v41 = v17;
      v42 = 0;
      if ( String )
      {
        v18 = -1;
        do
          ++v18;
        while ( String[v18] );
        v19 = 2 * v18 + 2;
      }
      else
      {
        String = &qword_180050DC0;
        v19 = 2;
      }
      v37 = String;
      v38 = v19;
      v39 = 0;
      if ( v12 )
      {
        v20 = -1;
        do
          ++v20;
        while ( v12[v20] );
        v21 = 2 * v20 + 2;
      }
      else
      {
        v12 = &qword_180050DC0;
        v21 = 2;
      }
      v34 = v12;
      v35 = v21;
      v36 = 0;
      if ( a1 )
      {
        do
          ++v15;
        while ( a1[v15] );
        v14 = 2 * v15 + 2;
      }
      else
      {
        a1 = &qword_180050DC0;
      }
      v31 = a1;
      v32 = v14;
      v33 = 0;
      v29 = &v24;
      v30 = 8;
      LODWORD(v10) = tlgWriteTransfer_EventWriteTransfer(v11, (unsigned __int8 *)&word_180056F42, 0, 0, 8u, &v28);
      if ( (v9 & 1) != 0 )
        LODWORD(v10) = std::wstring::_Tidy_deallocate(v25);
    }
  }
  if ( *(_BYTE *)(a2 + 32) )
    LODWORD(v10) = std::wstring::_Tidy_deallocate(a2);
  if ( *(_BYTE *)(a3 + 16) )
    LODWORD(v10) = (**(__int64 (__fastcall ***)(__int64, _QWORD))a3)(a3, 0);
  return (int)v10;
}

```

## disassembly

```asm
0x18003bc5c  mov     [rsp-8+arg_0], rbx
0x18003bc61  push    rbp
0x18003bc62  push    rsi
0x18003bc63  push    rdi
0x18003bc64  push    r12
0x18003bc66  push    r13
0x18003bc68  push    r14
0x18003bc6a  push    r15
0x18003bc6c  lea     rbp, [rsp-1Fh]
0x18003bc71  sub     rsp, 100h
0x18003bc78  mov     rax, cs:__security_cookie
0x18003bc7f  xor     rax, rsp
0x18003bc82  mov     [rbp+4Fh+var_40], rax
0x18003bc86  mov     rbx, r9
0x18003bc89  mov     r14, r8
0x18003bc8c  mov     rsi, rdx
0x18003bc8f  mov     r15, rcx
0x18003bc92  mov     [rsp+130h+var_D0], rdx
0x18003bc97  mov     [rbp+4Fh+var_C8], r8
0x18003bc9b  xor     edi, edi
0x18003bc9d  mov     r12d, edi
0x18003bca0  mov     [rsp+130h+var_100], edi
0x18003bca4  call    ?Provider@UndockedUpdateTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedUpdateTelemetry::Provider(void)
0x18003bca9  mov     r13, rax
0x18003bcac  cmp     dword ptr [rax], 5
0x18003bcaf  jbe     loc_18003BE5A
0x18003bcb5  mov     rax, 200000000000h
0x18003bcbf  test    [r13+10h], rax
0x18003bcc3  jz      loc_18003BE5A
0x18003bcc9  mov     rcx, [r13+18h]
0x18003bccd  and     rcx, rax
0x18003bcd0  cmp     rcx, [r13+18h]
0x18003bcd4  jnz     loc_18003BE5A
0x18003bcda  mov     eax, [rbp+4Fh+arg_20]
0x18003bcdd  mov     [rsp+130h+var_100], eax
0x18003bce1  cmp     qword ptr [rbx+18h], 7
0x18003bce6  jbe     short loc_18003BCEB
0x18003bce8  mov     rbx, [rbx]
0x18003bceb  lea     rdi, asc_180052F84; "?"
0x18003bcf2  xor     r9d, r9d
0x18003bcf5  cmp     [r14+10h], r9b
0x18003bcf9  jz      short loc_18003BD1D
0x18003bcfb  lea     rdx, [rsp+130h+var_F0]
0x18003bd00  mov     rcx, r14
0x18003bd03  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x18003bd08  mov     r12d, 1
0x18003bd0e  cmp     qword ptr [rax+18h], 7
0x18003bd13  jbe     short loc_18003BD18
0x18003bd15  mov     rax, [rax]
0x18003bd18  xor     r9d, r9d
0x18003bd1b  jmp     short loc_18003BD20
0x18003bd1d  mov     rax, rdi
0x18003bd20  cmp     [rsi+20h], r9b
0x18003bd24  jz      short loc_18003BD33
0x18003bd26  mov     rdi, rsi
0x18003bd29  cmp     qword ptr [rsi+18h], 7
0x18003bd2e  jbe     short loc_18003BD33
0x18003bd30  mov     rdi, [rsi]
0x18003bd33  cmp     qword ptr [r15+18h], 7
0x18003bd38  jbe     short loc_18003BD3D
0x18003bd3a  mov     r15, [r15]
0x18003bd3d  mov     [rsp+130h+var_F8], 2000000h
0x18003bd46  lea     rcx, [rsp+130h+var_100]
0x18003bd4b  mov     [rbp+4Fh+var_50], rcx
0x18003bd4f  mov     [rbp+4Fh+var_48], 4
0x18003bd57  lea     r10, qword_180050DC0
0x18003bd5e  mov     r8d, 2
0x18003bd64  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003bd68  test    rbx, rbx
0x18003bd6b  jz      short loc_18003BD83
0x18003bd6d  mov     rdx, rcx
0x18003bd70  inc     rdx
0x18003bd73  cmp     [rbx+rdx*2], r9w
0x18003bd78  jnz     short loc_18003BD70
0x18003bd7a  lea     edx, ds:2[rdx*2]
0x18003bd81  jmp     short loc_18003BD89
0x18003bd83  mov     rbx, r10
0x18003bd86  mov     edx, r8d
0x18003bd89  mov     [rbp+4Fh+var_60], rbx
0x18003bd8d  mov     [rbp+4Fh+var_58], edx
0x18003bd90  mov     [rbp+4Fh+var_54], r9d
0x18003bd94  test    rax, rax
0x18003bd97  jz      short loc_18003BDAF
0x18003bd99  mov     rdx, rcx
0x18003bd9c  inc     rdx
0x18003bd9f  cmp     [rax+rdx*2], r9w
0x18003bda4  jnz     short loc_18003BD9C
0x18003bda6  lea     edx, ds:2[rdx*2]
0x18003bdad  jmp     short loc_18003BDB5
0x18003bdaf  mov     rax, r10
0x18003bdb2  mov     edx, r8d
0x18003bdb5  mov     [rbp+4Fh+var_70], rax
0x18003bdb9  mov     [rbp+4Fh+var_68], edx
0x18003bdbc  mov     [rbp+4Fh+var_64], r9d
0x18003bdc0  test    rdi, rdi
0x18003bdc3  jz      short loc_18003BDDB
0x18003bdc5  mov     rax, rcx
0x18003bdc8  inc     rax
0x18003bdcb  cmp     [rdi+rax*2], r9w
0x18003bdd0  jnz     short loc_18003BDC8
0x18003bdd2  lea     eax, ds:2[rax*2]
0x18003bdd9  jmp     short loc_18003BDE1
0x18003bddb  mov     rdi, r10
0x18003bdde  mov     eax, r8d
0x18003bde1  mov     [rbp+4Fh+var_80], rdi
0x18003bde5  mov     [rbp+4Fh+var_78], eax
0x18003bde8  mov     [rbp+4Fh+var_74], r9d
0x18003bdec  test    r15, r15
0x18003bdef  jz      short loc_18003BE05
0x18003bdf1  inc     rcx
0x18003bdf4  cmp     [r15+rcx*2], r9w
0x18003bdf9  jnz     short loc_18003BDF1
0x18003bdfb  lea     r8d, ds:2[rcx*2]
0x18003be03  jmp     short loc_18003BE08
0x18003be05  mov     r15, r10
0x18003be08  mov     [rbp+4Fh+var_90], r15
0x18003be0c  mov     [rbp+4Fh+var_88], r8d
0x18003be10  mov     [rbp+4Fh+var_84], r9d
0x18003be14  lea     rax, [rsp+130h+var_F8]
0x18003be19  mov     [rbp+4Fh+var_A0], rax
0x18003be1d  mov     ecx, 8
0x18003be22  mov     [rbp+4Fh+var_98], rcx
0x18003be26  lea     rax, [rbp+4Fh+var_C0]
0x18003be2a  mov     [rsp+130h+var_108], rax; PEVENT_DATA_DESCRIPTOR
0x18003be2f  mov     [rsp+130h+var_110], ecx; ULONG
0x18003be33  xor     r9d, r9d; int
0x18003be36  xor     r8d, r8d; int
0x18003be39  lea     rdx, word_180056F42; int
0x18003be40  mov     rcx, r13; int
0x18003be43  call    _tlgWriteTransfer_EventWriteTransfer
0x18003be48  test    r12b, 1
0x18003be4c  jz      short loc_18003BE58
0x18003be4e  lea     rcx, [rsp+130h+var_F0]
0x18003be53  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003be58  xor     edi, edi
0x18003be5a  cmp     [rsi+20h], dil
0x18003be5e  jz      short loc_18003BE69
0x18003be60  mov     rcx, rsi
0x18003be63  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003be68  nop
0x18003be69  cmp     [r14+10h], dil
0x18003be6d  jz      short loc_18003BE7F
0x18003be6f  mov     rax, [r14]
0x18003be72  xor     edx, edx
0x18003be74  mov     rcx, r14
0x18003be77  mov     rax, [rax]
0x18003be7a  call    _guard_dispatch_icall
0x18003be7f  mov     rcx, [rbp+4Fh+var_40]
0x18003be83  xor     rcx, rsp; StackCookie
0x18003be86  call    __security_check_cookie
0x18003be8b  mov     rbx, [rsp+130h+arg_0]
0x18003be93  add     rsp, 100h
0x18003be9a  pop     r15
0x18003be9c  pop     r14
0x18003be9e  pop     r13
0x18003bea0  pop     r12
0x18003bea2  pop     rdi
0x18003bea3  pop     rsi
0x18003bea4  pop     rbp
0x18003bea5  retn
```
