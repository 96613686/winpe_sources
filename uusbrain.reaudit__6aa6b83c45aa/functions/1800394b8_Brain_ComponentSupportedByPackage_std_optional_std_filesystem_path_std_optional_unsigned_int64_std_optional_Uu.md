# Brain::ComponentSupportedByPackage(std::optional<std::filesystem::path>,std::optional<unsigned __int64>,std::optional<UusComponent>)

- ea: `0x1800394b8`
- end: `0x1800396ce`
- name: `?ComponentSupportedByPackage@Brain@@AEAA_NV?$optional@Vpath@filesystem@std@@@std@@V?$optional@_K@3@V?$optional@VUusComponent@@@3@@Z`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180037064`

## callees

- `0x18000f84c`
- `0x180028728`
- `0x180029644`
- `0x180035610`
- `0x1800394b8`
- `0x18003bc5c`
- `0x18003beac`
- `0x1800427d0`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Brain::ComponentSupportedByPackage(__int64 a1, __int64 a2, __int64 *a3, __int64 a4)
{
  unsigned __int8 (*v8)(void); // rax
  int v9; // ecx
  int v10; // eax
  int v11; // r15d
  void **v13; // [rsp+30h] [rbp-49h] BYREF
  __int64 v14; // [rsp+38h] [rbp-41h]
  char v15; // [rsp+40h] [rbp-39h]
  void ***v16; // [rsp+48h] [rbp-31h]
  void ***v17; // [rsp+50h] [rbp-29h]
  _BYTE v18[32]; // [rsp+58h] [rbp-21h] BYREF
  char v19; // [rsp+78h] [rbp-1h]
  __int64 v20; // [rsp+80h] [rbp+7h]
  __int64 v21; // [rsp+88h] [rbp+Fh]

  v20 = a2;
  v21 = a4;
  if ( !*(_BYTE *)(a4 + 72) )
  {
    v16 = &v13;
    v15 = 0;
    if ( *((_BYTE *)a3 + 8) )
    {
      v13 = &UusVersion::`vftable';
      v14 = *a3;
      v15 = 1;
    }
    v17 = (void ***)v18;
    v19 = 0;
    if ( *(_BYTE *)(a2 + 32) )
    {
      std::wstring::wstring(v18, a2);
      v19 = 1;
    }
    uus::UndockedUpdateTelemetry::UusSessionIDNotFoundInPackage(a1 + 256, v18, &v13, a1 + 72);
LABEL_21:
    if ( *(_BYTE *)(a2 + 32) )
      std::wstring::_Tidy_deallocate(a2);
    if ( *(_BYTE *)(a4 + 72) )
    {
      std::vector<enum UusCapability>::~vector<enum UusCapability>(a4 + 32);
      std::wstring::_Tidy_deallocate(a4);
    }
    return 0;
  }
  v8 = *(unsigned __int8 (**)(void))(a4 + 64);
  if ( v8 && !v8() )
  {
    v9 = *(_DWORD *)(a4 + 56);
    v10 = v20;
    if ( v9 )
      v10 = *(_DWORD *)(a4 + 56);
    v11 = v9 != 0 ? v10 : 0;
    v17 = &v13;
    v15 = 0;
    if ( *((_BYTE *)a3 + 8) )
    {
      v13 = &UusVersion::`vftable';
      v14 = *a3;
      v15 = 1;
    }
    v16 = (void ***)v18;
    v19 = 0;
    if ( *(_BYTE *)(a2 + 32) )
    {
      std::wstring::wstring(v18, a2);
      v19 = 1;
    }
    uus::UndockedUpdateTelemetry::UusComponentDisabledByVelocity(
      a1 + 256,
      (unsigned int)v18,
      (unsigned int)&v13,
      a1 + 72,
      v11);
    goto LABEL_21;
  }
  v17 = &v13;
  v15 = 0;
  if ( *((_BYTE *)a3 + 8) )
  {
    v13 = &UusVersion::`vftable';
    v14 = *a3;
    v15 = 1;
  }
  v16 = (void ***)v18;
  v19 = 0;
  if ( *(_BYTE *)(a2 + 32) )
  {
    std::wstring::wstring(v18, a2);
    v19 = 1;
  }
  if ( !(unsigned __int8)UusComponent::CheckCapabilities(
                           a4,
                           (int)a1 + 256,
                           (unsigned int)v18,
                           (unsigned int)&v13,
                           a1 + 72) )
    goto LABEL_21;
  if ( *(_BYTE *)(a2 + 32) )
    std::wstring::_Tidy_deallocate(a2);
  if ( *(_BYTE *)(a4 + 72) )
  {
    std::vector<enum UusCapability>::~vector<enum UusCapability>(a4 + 32);
    std::wstring::_Tidy_deallocate(a4);
  }
  return 1;
}

```

## disassembly

```asm
0x1800394b8  push    rbp
0x1800394ba  push    rbx
0x1800394bb  push    rsi
0x1800394bc  push    rdi
0x1800394bd  push    r12
0x1800394bf  push    r14
0x1800394c1  push    r15
0x1800394c3  lea     rbp, [rsp-27h]
0x1800394c8  sub     rsp, 0A0h
0x1800394cf  mov     rax, cs:__security_cookie
0x1800394d6  xor     rax, rsp
0x1800394d9  mov     [rbp+57h+var_40], rax
0x1800394dd  mov     rbx, r9
0x1800394e0  mov     rsi, r8
0x1800394e3  mov     rdi, rdx
0x1800394e6  mov     r14, rcx
0x1800394e9  mov     [rbp+57h+var_50], rdx
0x1800394ed  mov     [rbp+57h+var_48], rbx
0x1800394f1  xor     r12d, r12d
0x1800394f4  cmp     [r9+48h], r12b
0x1800394f8  jnz     short loc_18003955E
0x1800394fa  lea     rax, [rbp+57h+var_A0]
0x1800394fe  mov     [rbp+57h+var_88], rax
0x180039502  mov     [rbp+57h+var_90], r12b
0x180039506  cmp     [r8+8], r12b
0x18003950a  jz      short loc_180039522
0x18003950c  lea     rax, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x180039513  mov     [rbp+57h+var_A0], rax
0x180039517  mov     rax, [r8]
0x18003951a  mov     [rbp+57h+var_98], rax
0x18003951e  mov     [rbp+57h+var_90], 1
0x180039522  lea     rax, [rbp+57h+var_78]
0x180039526  mov     [rbp+57h+var_80], rax
0x18003952a  mov     [rbp+57h+var_58], r12b
0x18003952e  cmp     [rdx+20h], r12b
0x180039532  jz      short loc_180039541
0x180039534  lea     rcx, [rbp+57h+var_78]
0x180039538  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003953d  mov     [rbp+57h+var_58], 1
0x180039541  lea     r9, [r14+48h]
0x180039545  lea     rcx, [r14+100h]
0x18003954c  lea     r8, [rbp+57h+var_A0]
0x180039550  lea     rdx, [rbp+57h+var_78]
0x180039554  call    ?UusSessionIDNotFoundInPackage@UndockedUpdateTelemetry@uus@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@Vpath@filesystem@std@@@4@V?$optional@VUusVersion@@@4@0@Z; uus::UndockedUpdateTelemetry::UusSessionIDNotFoundInPackage(std::wstring const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::wstring const &)
0x180039559  jmp     loc_18003965E
0x18003955e  mov     rax, [r9+40h]
0x180039562  test    rax, rax
0x180039565  jz      loc_1800395F0
0x18003956b  call    _guard_dispatch_icall
0x180039570  test    al, al
0x180039572  jnz     short loc_1800395F0
0x180039574  mov     ecx, [rbx+38h]
0x180039577  mov     eax, dword ptr [rbp+57h+var_50]
0x18003957a  test    ecx, ecx
0x18003957c  cmovnz  eax, ecx
0x18003957f  neg     ecx
0x180039581  sbb     r15d, r15d
0x180039584  and     r15d, eax
0x180039587  lea     rax, [rbp+57h+var_A0]
0x18003958b  mov     [rbp+57h+var_80], rax
0x18003958f  mov     [rbp+57h+var_90], r12b
0x180039593  cmp     [rsi+8], r12b
0x180039597  jz      short loc_1800395AF
0x180039599  lea     rax, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x1800395a0  mov     [rbp+57h+var_A0], rax
0x1800395a4  mov     rax, [rsi]
0x1800395a7  mov     [rbp+57h+var_98], rax
0x1800395ab  mov     [rbp+57h+var_90], 1
0x1800395af  lea     rax, [rbp+57h+var_78]
0x1800395b3  mov     [rbp+57h+var_88], rax
0x1800395b7  mov     [rbp+57h+var_58], r12b
0x1800395bb  cmp     [rdi+20h], r12b
0x1800395bf  jz      short loc_1800395D1
0x1800395c1  mov     rdx, rdi
0x1800395c4  lea     rcx, [rbp+57h+var_78]
0x1800395c8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800395cd  mov     [rbp+57h+var_58], 1
0x1800395d1  lea     r9, [r14+48h]
0x1800395d5  lea     rcx, [r14+100h]
0x1800395dc  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x1800395e1  lea     r8, [rbp+57h+var_A0]
0x1800395e5  lea     rdx, [rbp+57h+var_78]
0x1800395e9  call    ?UusComponentDisabledByVelocity@UndockedUpdateTelemetry@uus@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@Vpath@filesystem@std@@@4@V?$optional@VUusVersion@@@4@0I@Z; uus::UndockedUpdateTelemetry::UusComponentDisabledByVelocity(std::wstring const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::wstring const &,uint)
0x1800395ee  jmp     short loc_18003965E
0x1800395f0  lea     rax, [rbp+57h+var_A0]
0x1800395f4  mov     [rbp+57h+var_80], rax
0x1800395f8  mov     [rbp+57h+var_90], r12b
0x1800395fc  cmp     [rsi+8], r12b
0x180039600  jz      short loc_180039618
0x180039602  lea     rax, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x180039609  mov     [rbp+57h+var_A0], rax
0x18003960d  mov     rax, [rsi]
0x180039610  mov     [rbp+57h+var_98], rax
0x180039614  mov     [rbp+57h+var_90], 1
0x180039618  lea     rax, [rbp+57h+var_78]
0x18003961c  mov     [rbp+57h+var_88], rax
0x180039620  mov     [rbp+57h+var_58], r12b
0x180039624  cmp     [rdi+20h], r12b
0x180039628  jz      short loc_18003963A
0x18003962a  mov     rdx, rdi
0x18003962d  lea     rcx, [rbp+57h+var_78]
0x180039631  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180039636  mov     [rbp+57h+var_58], 1
0x18003963a  lea     rax, [r14+48h]
0x18003963e  lea     rdx, [r14+100h]
0x180039645  mov     [rsp+0D0h+var_B0], rax
0x18003964a  lea     r9, [rbp+57h+var_A0]
0x18003964e  lea     r8, [rbp+57h+var_78]
0x180039652  mov     rcx, rbx
0x180039655  call    ?CheckCapabilities@UusComponent@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$optional@Vpath@filesystem@std@@@3@V?$optional@VUusVersion@@@3@0@Z; UusComponent::CheckCapabilities(std::wstring const &,std::optional<std::filesystem::path>,std::optional<UusVersion>,std::wstring const &)
0x18003965a  test    al, al
0x18003965c  jnz     short loc_180039688
0x18003965e  cmp     [rdi+20h], r12b
0x180039662  jz      short loc_18003966D
0x180039664  mov     rcx, rdi
0x180039667  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003966c  nop
0x18003966d  cmp     [rbx+48h], r12b
0x180039671  jz      short loc_180039684
0x180039673  lea     rcx, [rbx+20h]
0x180039677  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x18003967c  mov     rcx, rbx
0x18003967f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039684  xor     al, al
0x180039686  jmp     short loc_1800396B0
0x180039688  cmp     [rdi+20h], r12b
0x18003968c  jz      short loc_180039697
0x18003968e  mov     rcx, rdi
0x180039691  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039696  nop
0x180039697  cmp     [rbx+48h], r12b
0x18003969b  jz      short loc_1800396AE
0x18003969d  lea     rcx, [rbx+20h]
0x1800396a1  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x1800396a6  mov     rcx, rbx
0x1800396a9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800396ae  mov     al, 1
0x1800396b0  mov     rcx, [rbp+57h+var_40]
0x1800396b4  xor     rcx, rsp; StackCookie
0x1800396b7  call    __security_check_cookie
0x1800396bc  add     rsp, 0A0h
0x1800396c3  pop     r15
0x1800396c5  pop     r14
0x1800396c7  pop     r12
0x1800396c9  pop     rdi
0x1800396ca  pop     rsi
0x1800396cb  pop     rbx
0x1800396cc  pop     rbp
0x1800396cd  retn
```
