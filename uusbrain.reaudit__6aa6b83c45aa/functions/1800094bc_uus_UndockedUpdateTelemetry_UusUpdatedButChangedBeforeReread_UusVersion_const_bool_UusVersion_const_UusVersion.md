# uus::UndockedUpdateTelemetry::UusUpdatedButChangedBeforeReread(UusVersion const &,bool,UusVersion const &,UusVersion const &,wchar_t const *)

- ea: `0x1800094bc`
- end: `0x1800096cc`
- name: `?UusUpdatedButChangedBeforeReread@UndockedUpdateTelemetry@uus@@SAXAEBVUusVersion@@_N00PEB_W@Z`
- size: `528`
- prototype: `void __fastcall(const struct UusVersion *, bool, const struct UusVersion *, const struct UusVersion *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000e888`

## callees

- `0x18000109c`
- `0x18000868c`
- `0x1800089f4`
- `0x1800094bc`
- `0x180029644`
- `0x1800427d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall uus::UndockedUpdateTelemetry::UusUpdatedButChangedBeforeReread(
        const struct UusVersion *a1,
        char a2,
        const struct UusVersion *a3,
        const struct UusVersion *a4,
        const wchar_t *a5)
{
  const struct _tlgProvider_t *v9; // r15
  __int64 String; // rax
  const wchar_t *v11; // rbx
  __int64 v12; // rax
  const wchar_t *v13; // rdi
  const wchar_t *v14; // rax
  int v15; // r8d
  __int64 v16; // rcx
  const wchar_t *v17; // rdx
  __int64 v18; // r9
  int v19; // r9d
  __int64 v20; // rdx
  int v21; // edx
  __int64 v22; // rdx
  int v23; // edx
  char v24; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v26[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v27[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[32]; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v30; // [rsp+C0h] [rbp-40h]
  __int64 v31; // [rsp+C8h] [rbp-38h]
  const wchar_t *v32; // [rsp+D0h] [rbp-30h]
  int v33; // [rsp+D8h] [rbp-28h]
  int v34; // [rsp+DCh] [rbp-24h]
  char *v35; // [rsp+E0h] [rbp-20h]
  __int64 v36; // [rsp+E8h] [rbp-18h]
  const wchar_t *v37; // [rsp+F0h] [rbp-10h]
  int v38; // [rsp+F8h] [rbp-8h]
  int v39; // [rsp+FCh] [rbp-4h]
  const wchar_t *v40; // [rsp+100h] [rbp+0h]
  int v41; // [rsp+108h] [rbp+8h]
  int v42; // [rsp+10Ch] [rbp+Ch]
  const wchar_t *v43; // [rsp+110h] [rbp+10h]
  int v44; // [rsp+118h] [rbp+18h]
  int v45; // [rsp+11Ch] [rbp+1Ch]

  v9 = uus::UndockedUpdateTelemetry::Provider();
  if ( *(_DWORD *)v9 > 5u
    && (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v9 + 3) & 0x400000000000LL) == *((_QWORD *)v9 + 3) )
  {
    String = UusVersion::GetString(a4, v28);
    v11 = (const wchar_t *)String;
    if ( *(_QWORD *)(String + 24) > 7u )
      v11 = *(const wchar_t **)String;
    v12 = UusVersion::GetString(a3, v27);
    v13 = (const wchar_t *)v12;
    if ( *(_QWORD *)(v12 + 24) > 7u )
      v13 = *(const wchar_t **)v12;
    v24 = a2;
    v14 = (const wchar_t *)UusVersion::GetString(a1, v26);
    if ( *((_QWORD *)v14 + 3) > 7u )
      v14 = *(const wchar_t **)v14;
    v25 = 0x2000000;
    v15 = 2;
    v16 = -1;
    v17 = a5;
    if ( a5 )
    {
      v18 = -1;
      do
        ++v18;
      while ( a5[v18] );
      v19 = 2 * v18 + 2;
    }
    else
    {
      v17 = &qword_180050DC0;
      v19 = 2;
    }
    v43 = v17;
    v44 = v19;
    v45 = 0;
    if ( v11 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v11[v20] );
      v21 = 2 * v20 + 2;
    }
    else
    {
      v11 = &qword_180050DC0;
      v21 = 2;
    }
    v40 = v11;
    v41 = v21;
    v42 = 0;
    if ( v13 )
    {
      v22 = -1;
      do
        ++v22;
      while ( v13[v22] );
      v23 = 2 * v22 + 2;
    }
    else
    {
      v13 = &qword_180050DC0;
      v23 = 2;
    }
    v37 = v13;
    v38 = v23;
    v39 = 0;
    v35 = &v24;
    v36 = 1;
    if ( v14 )
    {
      do
        ++v16;
      while ( v14[v16] );
      v15 = 2 * v16 + 2;
    }
    else
    {
      v14 = &qword_180050DC0;
    }
    v32 = v14;
    v33 = v15;
    v34 = 0;
    v30 = &v25;
    v31 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)v9, (unsigned __int8 *)&word_180056A8E, 0, 0, 8u, &v29);
    std::wstring::_Tidy_deallocate(v26);
    std::wstring::_Tidy_deallocate(v27);
    std::wstring::_Tidy_deallocate(v28);
  }
}

```

## disassembly

```asm
0x1800094bc  mov     [rsp-8+arg_8], rbx
0x1800094c1  push    rbp
0x1800094c2  push    rsi
0x1800094c3  push    rdi
0x1800094c4  push    r14
0x1800094c6  push    r15
0x1800094c8  lea     rbp, [rsp-30h]
0x1800094cd  sub     rsp, 130h
0x1800094d4  mov     rax, cs:__security_cookie
0x1800094db  xor     rax, rsp
0x1800094de  mov     [rbp+50h+var_30], rax
0x1800094e2  mov     rbx, r9
0x1800094e5  mov     rdi, r8
0x1800094e8  mov     sil, dl
0x1800094eb  mov     r14, rcx
0x1800094ee  call    ?Provider@UndockedUpdateTelemetry@uus@@SAPEBU_tlgProvider_t@@XZ; uus::UndockedUpdateTelemetry::Provider(void)
0x1800094f3  mov     r15, rax
0x1800094f6  cmp     dword ptr [rax], 5
0x1800094f9  jbe     loc_1800096A9
0x1800094ff  mov     rax, 400000000000h
0x180009509  test    [r15+10h], rax
0x18000950d  jz      loc_1800096A9
0x180009513  mov     rcx, [r15+18h]
0x180009517  and     rcx, rax
0x18000951a  cmp     rcx, [r15+18h]
0x18000951e  jnz     loc_1800096A9
0x180009524  lea     rdx, [rbp+50h+var_D0]
0x180009528  mov     rcx, rbx
0x18000952b  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x180009530  mov     rbx, rax
0x180009533  cmp     qword ptr [rax+18h], 7
0x180009538  jbe     short loc_18000953D
0x18000953a  mov     rbx, [rax]
0x18000953d  lea     rdx, [rsp+150h+var_F0]
0x180009542  mov     rcx, rdi
0x180009545  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x18000954a  mov     rdi, rax
0x18000954d  cmp     qword ptr [rax+18h], 7
0x180009552  jbe     short loc_180009557
0x180009554  mov     rdi, [rax]
0x180009557  mov     [rsp+150h+var_120], sil
0x18000955c  lea     rdx, [rsp+150h+var_110]
0x180009561  mov     rcx, r14
0x180009564  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x180009569  cmp     qword ptr [rax+18h], 7
0x18000956e  jbe     short loc_180009573
0x180009570  mov     rax, [rax]
0x180009573  mov     [rsp+150h+var_118], 2000000h
0x18000957c  lea     r11, qword_180050DC0
0x180009583  mov     r8d, 2
0x180009589  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000958d  mov     rdx, [rbp+50h+arg_20]
0x180009594  xor     r10d, r10d
0x180009597  test    rdx, rdx
0x18000959a  jz      short loc_1800095B3
0x18000959c  mov     r9, rcx
0x18000959f  inc     r9
0x1800095a2  cmp     [rdx+r9*2], r10w
0x1800095a7  jnz     short loc_18000959F
0x1800095a9  lea     r9d, ds:2[r9*2]
0x1800095b1  jmp     short loc_1800095B9
0x1800095b3  mov     rdx, r11
0x1800095b6  mov     r9d, r8d
0x1800095b9  mov     [rbp+50h+var_40], rdx
0x1800095bd  mov     [rbp+50h+var_38], r9d
0x1800095c1  mov     [rbp+50h+var_34], r10d
0x1800095c5  test    rbx, rbx
0x1800095c8  jz      short loc_1800095E0
0x1800095ca  mov     rdx, rcx
0x1800095cd  inc     rdx
0x1800095d0  cmp     [rbx+rdx*2], r10w
0x1800095d5  jnz     short loc_1800095CD
0x1800095d7  lea     edx, ds:2[rdx*2]
0x1800095de  jmp     short loc_1800095E6
0x1800095e0  mov     rbx, r11
0x1800095e3  mov     edx, r8d
0x1800095e6  mov     [rbp+50h+var_50], rbx
0x1800095ea  mov     [rbp+50h+var_48], edx
0x1800095ed  mov     [rbp+50h+var_44], r10d
0x1800095f1  test    rdi, rdi
0x1800095f4  jz      short loc_18000960C
0x1800095f6  mov     rdx, rcx
0x1800095f9  inc     rdx
0x1800095fc  cmp     [rdi+rdx*2], r10w
0x180009601  jnz     short loc_1800095F9
0x180009603  lea     edx, ds:2[rdx*2]
0x18000960a  jmp     short loc_180009612
0x18000960c  mov     rdi, r11
0x18000960f  mov     edx, r8d
0x180009612  mov     [rbp+50h+var_60], rdi
0x180009616  mov     [rbp+50h+var_58], edx
0x180009619  mov     [rbp+50h+var_54], r10d
0x18000961d  lea     rdx, [rsp+150h+var_120]
0x180009622  mov     [rbp+50h+var_70], rdx
0x180009626  mov     [rbp+50h+var_68], 1
0x18000962e  test    rax, rax
0x180009631  jz      short loc_180009647
0x180009633  inc     rcx
0x180009636  cmp     [rax+rcx*2], r10w
0x18000963b  jnz     short loc_180009633
0x18000963d  lea     r8d, ds:2[rcx*2]
0x180009645  jmp     short loc_18000964A
0x180009647  mov     rax, r11
0x18000964a  mov     [rbp+50h+var_80], rax
0x18000964e  mov     [rbp+50h+var_78], r8d
0x180009652  mov     [rbp+50h+var_74], r10d
0x180009656  lea     rax, [rsp+150h+var_118]
0x18000965b  mov     [rbp+50h+var_90], rax
0x18000965f  mov     ecx, 8
0x180009664  mov     [rbp+50h+var_88], rcx
0x180009668  lea     rax, [rbp+50h+var_B0]
0x18000966c  mov     [rsp+150h+var_128], rax; PEVENT_DATA_DESCRIPTOR
0x180009671  mov     [rsp+150h+var_130], ecx; ULONG
0x180009675  xor     r9d, r9d; int
0x180009678  xor     r8d, r8d; int
0x18000967b  lea     rdx, word_180056A8E; int
0x180009682  mov     rcx, r15; int
0x180009685  call    _tlgWriteTransfer_EventWriteTransfer
0x18000968a  lea     rcx, [rsp+150h+var_110]
0x18000968f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009694  nop
0x180009695  lea     rcx, [rsp+150h+var_F0]
0x18000969a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000969f  nop
0x1800096a0  lea     rcx, [rbp+50h+var_D0]
0x1800096a4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800096a9  mov     rcx, [rbp+50h+var_30]
0x1800096ad  xor     rcx, rsp; StackCookie
0x1800096b0  call    __security_check_cookie
0x1800096b5  mov     rbx, [rsp+150h+arg_8]
0x1800096bd  add     rsp, 130h
0x1800096c4  pop     r15
0x1800096c6  pop     r14
0x1800096c8  pop     rdi
0x1800096c9  pop     rsi
0x1800096ca  pop     rbp
0x1800096cb  retn
```
