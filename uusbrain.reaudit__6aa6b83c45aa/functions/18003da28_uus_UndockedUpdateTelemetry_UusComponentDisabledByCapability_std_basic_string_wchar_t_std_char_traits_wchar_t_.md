# uus::UndockedUpdateTelemetry::UusComponentDisabledByCapability(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,char const *,bool,long)

- ea: `0x18003da28`
- end: `0x18003dcc6`
- name: `?UusComponentDisabledByCapability@UndockedUpdateTelemetry@uus@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@Vpath@filesystem@std@@@4@V?$optional@VUusVersion@@@4@0PEBD_NJ@Z`
- size: `670`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180034914`
- `0x18004acd9`

## callees

- `0x18000109c`
- `0x18000868c`
- `0x1800089f4`
- `0x180029644`
- `0x18003da28`
- `0x1800427d0`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall uus::UndockedUpdateTelemetry::UusComponentDisabledByCapability(
        const wchar_t *a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        const wchar_t *a5,
        char a6,
        int a7)
{
  char v11; // r12
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r13
  const wchar_t *v14; // rdi
  __int64 String; // rax
  const wchar_t *v16; // rcx
  __int64 v17; // r8
  const wchar_t *v18; // rax
  __int64 v19; // rdx
  int v20; // edx
  int v21; // edx
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  char v29; // [rsp+30h] [rbp-D0h] BYREF
  int v30; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v32[32]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h]
  __int64 v34; // [rsp+68h] [rbp-98h]
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  const wchar_t *v38; // [rsp+A0h] [rbp-60h]
  int v39; // [rsp+A8h] [rbp-58h]
  int v40; // [rsp+ACh] [rbp-54h]
  const wchar_t *v41; // [rsp+B0h] [rbp-50h]
  int v42; // [rsp+B8h] [rbp-48h]
  int v43; // [rsp+BCh] [rbp-44h]
  const wchar_t *v44; // [rsp+C0h] [rbp-40h]
  int v45; // [rsp+C8h] [rbp-38h]
  int v46; // [rsp+CCh] [rbp-34h]
  const wchar_t *v47; // [rsp+D0h] [rbp-30h]
  int v48; // [rsp+D8h] [rbp-28h]
  int v49; // [rsp+DCh] [rbp-24h]
  const wchar_t *v50; // [rsp+E0h] [rbp-20h]
  int v51; // [rsp+E8h] [rbp-18h]
  int v52; // [rsp+ECh] [rbp-14h]
  char *v53; // [rsp+F0h] [rbp-10h]
  __int64 v54; // [rsp+F8h] [rbp-8h]
  int *v55; // [rsp+100h] [rbp+0h]
  __int64 v56; // [rsp+108h] [rbp+8h]

  v33 = a2;
  v34 = a3;
  v11 = 0;
  v30 = 0;
  v12 = uus::UndockedUpdateTelemetry::Provider();
  v13 = (__int64)v12;
  if ( *(_DWORD *)v12 > 5u )
  {
    LODWORD(v12) = 0;
    if ( (*(_QWORD *)(v13 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v13 + 24) & 0x200000000000LL) == *(_QWORD *)(v13 + 24) )
    {
      v30 = a7;
      v29 = a6;
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const wchar_t **)a4;
      v14 = L"?";
      if ( *(_BYTE *)(a3 + 16) )
      {
        String = UusVersion::GetString(a3, v32);
        v16 = (const wchar_t *)String;
        v11 = 1;
        if ( *(_QWORD *)(String + 24) > 7u )
          v16 = *(const wchar_t **)String;
      }
      else
      {
        v16 = L"?";
      }
      if ( *(_BYTE *)(a2 + 32) )
      {
        v14 = (const wchar_t *)a2;
        if ( *(_QWORD *)(a2 + 24) > 7u )
          v14 = *(const wchar_t **)a2;
      }
      if ( *((_QWORD *)a1 + 3) > 7u )
        a1 = *(const wchar_t **)a1;
      v31 = 0x2000000;
      v55 = &v30;
      v56 = 4;
      v53 = &v29;
      v54 = 1;
      v17 = -1;
      v18 = a5;
      if ( a5 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *((_BYTE *)a5 + v19) );
        v20 = v19 + 1;
      }
      else
      {
        v18 = &Src;
        v20 = 1;
      }
      v50 = v18;
      v51 = v20;
      v52 = 0;
      v21 = 2;
      if ( a4 )
      {
        v22 = -1;
        do
          ++v22;
        while ( a4[v22] );
        v23 = 2 * v22 + 2;
      }
      else
      {
        a4 = &qword_180050DC0;
        v23 = 2;
      }
      v47 = a4;
      v48 = v23;
      v49 = 0;
      if ( v16 )
      {
        v24 = -1;
        do
          ++v24;
        while ( v16[v24] );
        v25 = 2 * v24 + 2;
      }
      else
      {
        v16 = &qword_180050DC0;
        v25 = 2;
      }
      v44 = v16;
      v45 = v25;
      v46 = 0;
      if ( v14 )
      {
        v26 = -1;
        do
          ++v26;
        while ( v14[v26] );
        v27 = 2 * v26 + 2;
      }
      else
      {
        v14 = &qword_180050DC0;
        v27 = 2;
      }
      v41 = v14;
      v42 = v27;
      v43 = 0;
      if ( a1 )
      {
        do
          ++v17;
        while ( a1[v17] );
        v21 = 2 * v17 + 2;
      }
      else
      {
        a1 = &qword_180050DC0;
      }
      v38 = a1;
      v39 = v21;
      v40 = 0;
      v36 = &v31;
      v37 = 8;
      LODWORD(v12) = tlgWriteTransfer_EventWriteTransfer(v13, (unsigned __int8 *)&byte_1800574F7, 0, 0, 0xAu, &v35);
      if ( (v11 & 1) != 0 )
        LODWORD(v12) = std::wstring::_Tidy_deallocate(v32);
    }
  }
  if ( *(_BYTE *)(a2 + 32) )
    LODWORD(v12) = std::wstring::_Tidy_deallocate(a2);
  if ( *(_BYTE *)(a3 + 16) )
    LODWORD(v12) = (**(__int64 (__fastcall ***)(__int64, _QWORD))a3)(a3, 0);
  return (int)v12;
}

```

## disassembly

```asm
0x18003da28  mov     [rsp-8+arg_0], rbx
0x18003da2d  push    rbp
0x18003da2e  push    rsi
0x18003da2f  push    rdi
0x18003da30  push    r12
0x18003da32  push    r13
0x18003da34  push    r14
0x18003da36  push    r15
0x18003da38  lea     rbp, [rsp-20h]
0x18003da3d  sub     rsp, 120h
0x18003da44  mov     rax, cs:__security_cookie
0x18003da4b  xor     rax, rsp
0x18003da4e  mov     [rbp+50h+var_40], rax
0x18003da52  mov     rbx, r9
0x18003da55  mov     r14, r8
0x18003da58  mov     rsi, rdx
0x18003da5b  mov     r15, rcx
0x18003da5e  mov     [rsp+150h+var_F0], rdx
0x18003da63  mov     [rsp+150h+var_E8], r8
0x18003da68  xor     edi, edi
0x18003da6a  mov     r12d, edi
0x18003da6d  mov     [rsp+150h+var_11C], edi
0x18003da71  call    ?Provider@UndockedUpdateTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedUpdateTelemetry::Provider(void)
0x18003da76  mov     r13, rax
0x18003da79  cmp     dword ptr [rax], 5
0x18003da7c  jbe     loc_18003DC7A
0x18003da82  mov     rax, 200000000000h
0x18003da8c  test    [r13+10h], rax
0x18003da90  jz      loc_18003DC7A
0x18003da96  mov     rcx, [r13+18h]
0x18003da9a  and     rcx, rax
0x18003da9d  cmp     rcx, [r13+18h]
0x18003daa1  jnz     loc_18003DC7A
0x18003daa7  mov     eax, [rbp+50h+arg_30]
0x18003daad  mov     [rsp+150h+var_11C], eax
0x18003dab1  mov     al, [rbp+50h+arg_28]
0x18003dab7  mov     [rsp+150h+var_120], al
0x18003dabb  cmp     qword ptr [rbx+18h], 7
0x18003dac0  jbe     short loc_18003DAC5
0x18003dac2  mov     rbx, [rbx]
0x18003dac5  lea     rdi, asc_180052F84; "?"
0x18003dacc  xor     r9d, r9d
0x18003dacf  cmp     [r14+10h], r9b
0x18003dad3  jz      short loc_18003DAFA
0x18003dad5  lea     rdx, [rsp+150h+var_110]
0x18003dada  mov     rcx, r14
0x18003dadd  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x18003dae2  mov     rcx, rax
0x18003dae5  mov     r12d, 1
0x18003daeb  cmp     qword ptr [rax+18h], 7
0x18003daf0  jbe     short loc_18003DAF5
0x18003daf2  mov     rcx, [rax]
0x18003daf5  xor     r9d, r9d
0x18003daf8  jmp     short loc_18003DAFD
0x18003dafa  mov     rcx, rdi
0x18003dafd  cmp     [rsi+20h], r9b
0x18003db01  jz      short loc_18003DB10
0x18003db03  mov     rdi, rsi
0x18003db06  cmp     qword ptr [rsi+18h], 7
0x18003db0b  jbe     short loc_18003DB10
0x18003db0d  mov     rdi, [rsi]
0x18003db10  cmp     qword ptr [r15+18h], 7
0x18003db15  jbe     short loc_18003DB1A
0x18003db17  mov     r15, [r15]
0x18003db1a  mov     [rsp+150h+var_118], 2000000h
0x18003db23  lea     rax, [rsp+150h+var_11C]
0x18003db28  mov     [rbp+50h+var_50], rax
0x18003db2c  mov     [rbp+50h+var_48], 4
0x18003db34  lea     rax, [rsp+150h+var_120]
0x18003db39  mov     [rbp+50h+var_60], rax
0x18003db3d  mov     [rbp+50h+var_58], 1
0x18003db45  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003db49  mov     rax, [rbp+50h+arg_20]
0x18003db50  test    rax, rax
0x18003db53  jz      short loc_18003DB65
0x18003db55  mov     rdx, r8
0x18003db58  inc     rdx
0x18003db5b  cmp     [rax+rdx], r9b
0x18003db5f  jnz     short loc_18003DB58
0x18003db61  inc     edx
0x18003db63  jmp     short loc_18003DB71
0x18003db65  lea     rax, Src
0x18003db6c  mov     edx, 1
0x18003db71  mov     [rbp+50h+var_70], rax
0x18003db75  mov     [rbp+50h+var_68], edx
0x18003db78  mov     [rbp+50h+var_64], r9d
0x18003db7c  lea     r10, qword_180050DC0
0x18003db83  mov     edx, 2
0x18003db88  test    rbx, rbx
0x18003db8b  jz      short loc_18003DBA3
0x18003db8d  mov     rax, r8
0x18003db90  inc     rax
0x18003db93  cmp     [rbx+rax*2], r9w
0x18003db98  jnz     short loc_18003DB90
0x18003db9a  lea     eax, ds:2[rax*2]
0x18003dba1  jmp     short loc_18003DBA8
0x18003dba3  mov     rbx, r10
0x18003dba6  mov     eax, edx
0x18003dba8  mov     [rbp+50h+var_80], rbx
0x18003dbac  mov     [rbp+50h+var_78], eax
0x18003dbaf  mov     [rbp+50h+var_74], r9d
0x18003dbb3  test    rcx, rcx
0x18003dbb6  jz      short loc_18003DBCE
0x18003dbb8  mov     rax, r8
0x18003dbbb  inc     rax
0x18003dbbe  cmp     [rcx+rax*2], r9w
0x18003dbc3  jnz     short loc_18003DBBB
0x18003dbc5  lea     eax, ds:2[rax*2]
0x18003dbcc  jmp     short loc_18003DBD3
0x18003dbce  mov     rcx, r10
0x18003dbd1  mov     eax, edx
0x18003dbd3  mov     [rbp+50h+var_90], rcx
0x18003dbd7  mov     [rbp+50h+var_88], eax
0x18003dbda  mov     [rbp+50h+var_84], r9d
0x18003dbde  test    rdi, rdi
0x18003dbe1  jz      short loc_18003DBF9
0x18003dbe3  mov     rax, r8
0x18003dbe6  inc     rax
0x18003dbe9  cmp     [rdi+rax*2], r9w
0x18003dbee  jnz     short loc_18003DBE6
0x18003dbf0  lea     eax, ds:2[rax*2]
0x18003dbf7  jmp     short loc_18003DBFE
0x18003dbf9  mov     rdi, r10
0x18003dbfc  mov     eax, edx
0x18003dbfe  mov     [rbp+50h+var_A0], rdi
0x18003dc02  mov     [rbp+50h+var_98], eax
0x18003dc05  mov     [rbp+50h+var_94], r9d
0x18003dc09  test    r15, r15
0x18003dc0c  jz      short loc_18003DC22
0x18003dc0e  inc     r8
0x18003dc11  cmp     [r15+r8*2], r9w
0x18003dc16  jnz     short loc_18003DC0E
0x18003dc18  lea     edx, ds:2[r8*2]
0x18003dc20  jmp     short loc_18003DC25
0x18003dc22  mov     r15, r10
0x18003dc25  mov     [rbp+50h+var_B0], r15
0x18003dc29  mov     [rbp+50h+var_A8], edx
0x18003dc2c  mov     [rbp+50h+var_A4], r9d
0x18003dc30  lea     rax, [rsp+150h+var_118]
0x18003dc35  mov     [rbp+50h+var_C0], rax
0x18003dc39  mov     [rbp+50h+var_B8], 8
0x18003dc41  lea     rax, [rsp+150h+var_E0]
0x18003dc46  mov     [rsp+150h+var_128], rax; PEVENT_DATA_DESCRIPTOR
0x18003dc4b  mov     [rsp+150h+var_130], 0Ah; ULONG
0x18003dc53  xor     r9d, r9d; int
0x18003dc56  xor     r8d, r8d; int
0x18003dc59  lea     rdx, byte_1800574F7; int
0x18003dc60  mov     rcx, r13; int
0x18003dc63  call    _tlgWriteTransfer_EventWriteTransfer
0x18003dc68  test    r12b, 1
0x18003dc6c  jz      short loc_18003DC78
0x18003dc6e  lea     rcx, [rsp+150h+var_110]
0x18003dc73  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003dc78  xor     edi, edi
0x18003dc7a  cmp     [rsi+20h], dil
0x18003dc7e  jz      short loc_18003DC89
0x18003dc80  mov     rcx, rsi
0x18003dc83  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003dc88  nop
0x18003dc89  cmp     [r14+10h], dil
0x18003dc8d  jz      short loc_18003DC9F
0x18003dc8f  mov     rax, [r14]
0x18003dc92  xor     edx, edx
0x18003dc94  mov     rcx, r14
0x18003dc97  mov     rax, [rax]
0x18003dc9a  call    _guard_dispatch_icall
0x18003dc9f  mov     rcx, [rbp+50h+var_40]
0x18003dca3  xor     rcx, rsp; StackCookie
0x18003dca6  call    __security_check_cookie
0x18003dcab  mov     rbx, [rsp+150h+arg_0]
0x18003dcb3  add     rsp, 120h
0x18003dcba  pop     r15
0x18003dcbc  pop     r14
0x18003dcbe  pop     r13
0x18003dcc0  pop     r12
0x18003dcc2  pop     rdi
0x18003dcc3  pop     rsi
0x18003dcc4  pop     rbp
0x18003dcc5  retn
```
