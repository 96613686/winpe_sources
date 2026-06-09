# uus::UndockedUpdateTelemetry::UusActiveVersionMismatch(std::optional<std::filesystem::path>,std::optional<std::filesystem::path>,wchar_t const *,bool,wchar_t const *,char const *,wchar_t const *,uint,uint,bool)

- ea: `0x18003b804`
- end: `0x18003bab3`
- name: `?UusActiveVersionMismatch@UndockedUpdateTelemetry@uus@@SAXV?$optional@Vpath@filesystem@std@@@std@@0PEB_W_N1PEBD1II2@Z`
- size: `687`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18003a00c`

## callees

- `0x18000109c`
- `0x18000868c`
- `0x180029644`
- `0x18003b804`
- `0x1800427d0`

## pseudocode

```c
int __fastcall uus::UndockedUpdateTelemetry::UusActiveVersionMismatch(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        char a4,
        const wchar_t *a5,
        const wchar_t *a6,
        const wchar_t *a7,
        int a8,
        int a9,
        char a10)
{
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r11
  const wchar_t *v16; // r8
  const wchar_t *v17; // r9
  __int64 v18; // rcx
  int v19; // r10d
  const wchar_t *v20; // rax
  __int64 v21; // rdx
  int v22; // edx
  const wchar_t *v23; // rax
  __int64 v24; // rdx
  int v25; // edx
  const wchar_t *v26; // rax
  __int64 v27; // rdx
  int v28; // edx
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  char v34; // [rsp+30h] [rbp-D0h] BYREF
  char v35; // [rsp+31h] [rbp-CFh] BYREF
  int v36; // [rsp+34h] [rbp-CCh] BYREF
  int v37; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v38; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v40; // [rsp+70h] [rbp-90h]
  __int64 v41; // [rsp+78h] [rbp-88h]
  const wchar_t *v42; // [rsp+80h] [rbp-80h]
  int v43; // [rsp+88h] [rbp-78h]
  int v44; // [rsp+8Ch] [rbp-74h]
  const wchar_t *v45; // [rsp+90h] [rbp-70h]
  int v46; // [rsp+98h] [rbp-68h]
  int v47; // [rsp+9Ch] [rbp-64h]
  const wchar_t *v48; // [rsp+A0h] [rbp-60h]
  int v49; // [rsp+A8h] [rbp-58h]
  int v50; // [rsp+ACh] [rbp-54h]
  char *v51; // [rsp+B0h] [rbp-50h]
  __int64 v52; // [rsp+B8h] [rbp-48h]
  const wchar_t *v53; // [rsp+C0h] [rbp-40h]
  int v54; // [rsp+C8h] [rbp-38h]
  int v55; // [rsp+CCh] [rbp-34h]
  const wchar_t *v56; // [rsp+D0h] [rbp-30h]
  int v57; // [rsp+D8h] [rbp-28h]
  int v58; // [rsp+DCh] [rbp-24h]
  const wchar_t *v59; // [rsp+E0h] [rbp-20h]
  int v60; // [rsp+E8h] [rbp-18h]
  int v61; // [rsp+ECh] [rbp-14h]
  int *v62; // [rsp+F0h] [rbp-10h]
  __int64 v63; // [rsp+F8h] [rbp-8h]
  int *v64; // [rsp+100h] [rbp+0h]
  __int64 v65; // [rsp+108h] [rbp+8h]
  char *v66; // [rsp+110h] [rbp+10h]
  __int64 v67; // [rsp+118h] [rbp+18h]

  v14 = uus::UndockedUpdateTelemetry::Provider();
  v15 = (__int64)v14;
  if ( *(_DWORD *)v14 > 5u )
  {
    LODWORD(v14) = 0;
    if ( (*(_QWORD *)(v15 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v15 + 24) & 0x400000000000LL) == *(_QWORD *)(v15 + 24) )
    {
      v16 = L"?";
      v34 = a10;
      v36 = a9;
      v37 = a8;
      v35 = a4;
      if ( *(_BYTE *)(a2 + 32) )
      {
        v17 = (const wchar_t *)a2;
        if ( *(_QWORD *)(a2 + 24) > 7u )
          v17 = *(const wchar_t **)a2;
      }
      else
      {
        v17 = L"?";
      }
      if ( *(_BYTE *)(a1 + 32) )
      {
        v16 = (const wchar_t *)a1;
        if ( *(_QWORD *)(a1 + 24) > 7u )
          v16 = *(const wchar_t **)a1;
      }
      v38 = 0x1000000;
      v66 = &v34;
      v67 = 1;
      v64 = &v36;
      v18 = -1;
      v65 = 4;
      v62 = &v37;
      v19 = 2;
      v20 = a7;
      v63 = 4;
      if ( a7 )
      {
        v21 = -1;
        do
          ++v21;
        while ( a7[v21] );
        v22 = 2 * v21 + 2;
      }
      else
      {
        v20 = &qword_180050DC0;
        v22 = 2;
      }
      v59 = v20;
      v23 = a6;
      v60 = v22;
      v61 = 0;
      if ( a6 )
      {
        v24 = -1;
        do
          ++v24;
        while ( *((_BYTE *)a6 + v24) );
        v25 = v24 + 1;
      }
      else
      {
        v23 = &Src;
        v25 = 1;
      }
      v56 = v23;
      v26 = a5;
      v57 = v25;
      v58 = 0;
      if ( a5 )
      {
        v27 = -1;
        do
          ++v27;
        while ( a5[v27] );
        v28 = 2 * v27 + 2;
      }
      else
      {
        v26 = &qword_180050DC0;
        v28 = 2;
      }
      v53 = v26;
      v51 = &v35;
      v54 = v28;
      v55 = 0;
      v52 = 1;
      if ( a3 )
      {
        v29 = -1;
        do
          ++v29;
        while ( a3[v29] );
        v30 = 2 * v29 + 2;
      }
      else
      {
        a3 = &qword_180050DC0;
        v30 = 2;
      }
      v48 = a3;
      v49 = v30;
      v50 = 0;
      if ( v17 )
      {
        v31 = -1;
        do
          ++v31;
        while ( v17[v31] );
        v32 = 2 * v31 + 2;
      }
      else
      {
        v17 = &qword_180050DC0;
        v32 = 2;
      }
      v45 = v17;
      v46 = v32;
      v47 = 0;
      if ( v16 )
      {
        do
          ++v18;
        while ( v16[v18] );
        v19 = 2 * v18 + 2;
      }
      else
      {
        v16 = &qword_180050DC0;
      }
      v42 = v16;
      v40 = &v38;
      v43 = v19;
      v44 = 0;
      v41 = 8;
      LODWORD(v14) = tlgWriteTransfer_EventWriteTransfer(v15, (unsigned __int8 *)&byte_180056E0B, 0, 0, 0xDu, &v39);
    }
  }
  if ( *(_BYTE *)(a1 + 32) )
    LODWORD(v14) = std::wstring::_Tidy_deallocate(a1);
  if ( *(_BYTE *)(a2 + 32) )
    LODWORD(v14) = std::wstring::_Tidy_deallocate(a2);
  return (int)v14;
}

```

## disassembly

```asm
0x18003b804  mov     [rsp-8+arg_10], rbx
0x18003b809  push    rbp
0x18003b80a  push    rsi
0x18003b80b  push    rdi
0x18003b80c  push    r14
0x18003b80e  push    r15
0x18003b810  lea     rbp, [rsp-30h]
0x18003b815  sub     rsp, 130h
0x18003b81c  mov     rax, cs:__security_cookie
0x18003b823  xor     rax, rsp
0x18003b826  mov     [rbp+50h+var_30], rax
0x18003b82a  mov     bl, r9b
0x18003b82d  mov     r14, r8
0x18003b830  mov     rsi, rdx
0x18003b833  mov     rdi, rcx
0x18003b836  call    ?Provider@UndockedUpdateTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedUpdateTelemetry::Provider(void)
0x18003b83b  xor     r15d, r15d
0x18003b83e  mov     r11, rax
0x18003b841  cmp     dword ptr [rax], 5
0x18003b844  jbe     loc_18003BA74
0x18003b84a  mov     rax, 400000000000h
0x18003b854  test    [r11+10h], rax
0x18003b858  jz      loc_18003BA74
0x18003b85e  mov     rcx, [r11+18h]
0x18003b862  and     rcx, rax
0x18003b865  cmp     rcx, [r11+18h]
0x18003b869  jnz     loc_18003BA74
0x18003b86f  lea     r8, asc_180052F84; "?"
0x18003b876  mov     al, [rbp+50h+arg_48]
0x18003b87c  mov     [rsp+150h+var_120], al
0x18003b880  mov     eax, [rbp+50h+arg_40]
0x18003b886  mov     [rsp+150h+var_11C], eax
0x18003b88a  mov     eax, [rbp+50h+arg_38]
0x18003b890  mov     [rsp+150h+var_118], eax
0x18003b894  mov     [rsp+150h+var_11F], bl
0x18003b898  cmp     [rsi+20h], r15b
0x18003b89c  jz      short loc_18003B8AD
0x18003b89e  cmp     qword ptr [rsi+18h], 7
0x18003b8a3  mov     r9, rsi
0x18003b8a6  jbe     short loc_18003B8B0
0x18003b8a8  mov     r9, [rsi]
0x18003b8ab  jmp     short loc_18003B8B0
0x18003b8ad  mov     r9, r8
0x18003b8b0  cmp     [rdi+20h], r15b
0x18003b8b4  jz      short loc_18003B8C3
0x18003b8b6  cmp     qword ptr [rdi+18h], 7
0x18003b8bb  mov     r8, rdi
0x18003b8be  jbe     short loc_18003B8C3
0x18003b8c0  mov     r8, [rdi]
0x18003b8c3  lea     rax, [rsp+150h+var_120]
0x18003b8c8  mov     [rsp+150h+var_110], 1000000h
0x18003b8d1  mov     [rbp+50h+var_40], rax
0x18003b8d5  lea     rbx, qword_180050DC0
0x18003b8dc  lea     rax, [rsp+150h+var_11C]
0x18003b8e1  mov     [rbp+50h+var_38], 1
0x18003b8e9  mov     [rbp+50h+var_50], rax
0x18003b8ed  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003b8f1  lea     rax, [rsp+150h+var_118]
0x18003b8f6  mov     [rbp+50h+var_48], 4
0x18003b8fe  mov     [rbp+50h+var_60], rax
0x18003b902  mov     r10d, 2
0x18003b908  mov     rax, [rbp+50h+arg_30]
0x18003b90f  mov     [rbp+50h+var_58], 4
0x18003b917  test    rax, rax
0x18003b91a  jz      short loc_18003B932
0x18003b91c  mov     rdx, rcx
0x18003b91f  inc     rdx
0x18003b922  cmp     [rax+rdx*2], r15w
0x18003b927  jnz     short loc_18003B91F
0x18003b929  lea     edx, ds:2[rdx*2]
0x18003b930  jmp     short loc_18003B938
0x18003b932  mov     rax, rbx
0x18003b935  mov     edx, r10d
0x18003b938  mov     [rbp+50h+var_70], rax
0x18003b93c  mov     rax, [rbp+50h+arg_28]
0x18003b943  mov     [rbp+50h+var_68], edx
0x18003b946  mov     [rbp+50h+var_64], r15d
0x18003b94a  test    rax, rax
0x18003b94d  jz      short loc_18003B95F
0x18003b94f  mov     rdx, rcx
0x18003b952  inc     rdx
0x18003b955  cmp     [rax+rdx], r15b
0x18003b959  jnz     short loc_18003B952
0x18003b95b  inc     edx
0x18003b95d  jmp     short loc_18003B96B
0x18003b95f  lea     rax, Src
0x18003b966  mov     edx, 1
0x18003b96b  mov     [rbp+50h+var_80], rax
0x18003b96f  mov     rax, [rbp+50h+arg_20]
0x18003b976  mov     [rbp+50h+var_78], edx
0x18003b979  mov     [rbp+50h+var_74], r15d
0x18003b97d  test    rax, rax
0x18003b980  jz      short loc_18003B998
0x18003b982  mov     rdx, rcx
0x18003b985  inc     rdx
0x18003b988  cmp     [rax+rdx*2], r15w
0x18003b98d  jnz     short loc_18003B985
0x18003b98f  lea     edx, ds:2[rdx*2]
0x18003b996  jmp     short loc_18003B99E
0x18003b998  mov     rax, rbx
0x18003b99b  mov     edx, r10d
0x18003b99e  mov     [rbp+50h+var_90], rax
0x18003b9a2  lea     rax, [rsp+150h+var_11F]
0x18003b9a7  mov     [rbp+50h+var_A0], rax
0x18003b9ab  mov     [rbp+50h+var_88], edx
0x18003b9ae  mov     [rbp+50h+var_84], r15d
0x18003b9b2  mov     [rbp+50h+var_98], 1
0x18003b9ba  test    r14, r14
0x18003b9bd  jz      short loc_18003B9D5
0x18003b9bf  mov     rax, rcx
0x18003b9c2  inc     rax
0x18003b9c5  cmp     [r14+rax*2], r15w
0x18003b9ca  jnz     short loc_18003B9C2
0x18003b9cc  lea     eax, ds:2[rax*2]
0x18003b9d3  jmp     short loc_18003B9DB
0x18003b9d5  mov     r14, rbx
0x18003b9d8  mov     eax, r10d
0x18003b9db  mov     [rbp+50h+var_B0], r14
0x18003b9df  mov     [rbp+50h+var_A8], eax
0x18003b9e2  mov     [rbp+50h+var_A4], r15d
0x18003b9e6  test    r9, r9
0x18003b9e9  jz      short loc_18003BA01
0x18003b9eb  mov     rax, rcx
0x18003b9ee  inc     rax
0x18003b9f1  cmp     [r9+rax*2], r15w
0x18003b9f6  jnz     short loc_18003B9EE
0x18003b9f8  lea     eax, ds:2[rax*2]
0x18003b9ff  jmp     short loc_18003BA07
0x18003ba01  mov     r9, rbx
0x18003ba04  mov     eax, r10d
0x18003ba07  mov     [rbp+50h+var_C0], r9
0x18003ba0b  mov     [rbp+50h+var_B8], eax
0x18003ba0e  mov     [rbp+50h+var_B4], r15d
0x18003ba12  test    r8, r8
0x18003ba15  jz      short loc_18003BA2B
0x18003ba17  inc     rcx
0x18003ba1a  cmp     [r8+rcx*2], r15w
0x18003ba1f  jnz     short loc_18003BA17
0x18003ba21  lea     r10d, ds:2[rcx*2]
0x18003ba29  jmp     short loc_18003BA2E
0x18003ba2b  mov     r8, rbx
0x18003ba2e  lea     rax, [rsp+150h+var_110]
0x18003ba33  mov     [rbp+50h+var_D0], r8
0x18003ba37  mov     [rsp+150h+var_E0], rax
0x18003ba3c  lea     rdx, byte_180056E0B; int
0x18003ba43  lea     rax, [rsp+150h+var_100]
0x18003ba48  mov     [rbp+50h+var_C8], r10d
0x18003ba4c  mov     [rsp+150h+var_128], rax; PEVENT_DATA_DESCRIPTOR
0x18003ba51  xor     r9d, r9d; int
0x18003ba54  xor     r8d, r8d; int
0x18003ba57  mov     [rsp+150h+var_130], 0Dh; ULONG
0x18003ba5f  mov     rcx, r11; int
0x18003ba62  mov     [rbp+50h+var_C4], r15d
0x18003ba66  mov     [rsp+150h+var_D8], 8
0x18003ba6f  call    _tlgWriteTransfer_EventWriteTransfer
0x18003ba74  cmp     [rdi+20h], r15b
0x18003ba78  jz      short loc_18003BA82
0x18003ba7a  mov     rcx, rdi
0x18003ba7d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ba82  cmp     [rsi+20h], r15b
0x18003ba86  jz      short loc_18003BA90
0x18003ba88  mov     rcx, rsi
0x18003ba8b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ba90  mov     rcx, [rbp+50h+var_30]
0x18003ba94  xor     rcx, rsp; StackCookie
0x18003ba97  call    __security_check_cookie
0x18003ba9c  mov     rbx, [rsp+150h+arg_10]
0x18003baa4  add     rsp, 130h
0x18003baab  pop     r15
0x18003baad  pop     r14
0x18003baaf  pop     rdi
0x18003bab0  pop     rsi
0x18003bab1  pop     rbp
0x18003bab2  retn
```
