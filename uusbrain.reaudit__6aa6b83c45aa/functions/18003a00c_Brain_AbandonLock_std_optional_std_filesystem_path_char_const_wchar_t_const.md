# Brain::AbandonLock(std::optional<std::filesystem::path>,char const *,wchar_t const *)

- ea: `0x18003a00c`
- end: `0x18003a1fc`
- name: `?AbandonLock@Brain@@AEAAXV?$optional@Vpath@filesystem@std@@@std@@PEBDPEB_W@Z`
- size: `496`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, installer_update`

## callers

- `0x180037064`
- `0x18003a204`

## callees

- `0x1800089f4`
- `0x180028728`
- `0x180029644`
- `0x180034774`
- `0x18003a00c`
- `0x18003b804`
- `0x1800427d0`
- `0x180047a30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003a088`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003a088`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18003a099`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x18003a099`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Brain::AbandonLock(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v6; // r15
  HANDLE CurrentProcess; // rax
  int v8; // r13d
  __int64 *String; // rax
  int v10; // r9d
  __int64 v11; // rsi
  char v12; // r12
  _QWORD *v13; // rdi
  __int64 result; // rax
  int v15; // [rsp+50h] [rbp-B0h]
  _QWORD v18[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v19[32]; // [rsp+78h] [rbp-88h] BYREF
  char v20; // [rsp+98h] [rbp-68h]
  _BYTE *v21; // [rsp+A0h] [rbp-60h]
  _BYTE *v22; // [rsp+A8h] [rbp-58h]
  _BYTE v23[32]; // [rsp+B0h] [rbp-50h] BYREF
  char v24; // [rsp+D0h] [rbp-30h]
  _BYTE v25[32]; // [rsp+D8h] [rbp-28h] BYREF
  char v26; // [rsp+F8h] [rbp-8h]
  __int64 v27; // [rsp+100h] [rbp+0h]
  _WORD v28[2]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 v29; // [rsp+10Ch] [rbp+Ch] BYREF
  _BYTE v30[32]; // [rsp+110h] [rbp+10h] BYREF
  char v31; // [rsp+130h] [rbp+30h]

  v27 = a2;
  v20 = 0;
  if ( *(_BYTE *)(a2 + 32) )
  {
    std::wstring::wstring(v19, a2);
    v20 = 1;
  }
  BrainUtils::GetFinalPathFromPath((__int64)v30, (__int64)v19);
  v28[0] = 0;
  v29 = 0;
  v6 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (unsigned int)IsWow64Process2(CurrentProcess, v28, &v29) )
    v6 = v28[0] != 0;
  v8 = v28[0];
  v15 = v29;
  v18[0] = &UusVersion::`vftable';
  v18[1] = *(_QWORD *)(a1 + 384);
  String = (__int64 *)UusVersion::GetString(v18, v19);
  v11 = (__int64)String;
  if ( (unsigned __int64)String[3] > 7 )
    v11 = *String;
  v12 = *(_BYTE *)(a1 + 216);
  v13 = (_QWORD *)(a1 + 256);
  if ( *(_QWORD *)(a1 + 280) > 7u )
    v13 = (_QWORD *)*v13;
  v21 = v23;
  v24 = 0;
  if ( v31 )
  {
    std::wstring::wstring(v23, v30);
    v24 = 1;
  }
  v22 = v25;
  v26 = 0;
  if ( *(_BYTE *)(a2 + 32) )
  {
    std::wstring::wstring(v25, a2);
    v26 = 1;
  }
  LOBYTE(v10) = v12;
  uus::UndockedUpdateTelemetry::UusActiveVersionMismatch(
    (unsigned int)v25,
    (unsigned int)v23,
    (_DWORD)v13,
    v10,
    v11,
    a3,
    a4,
    v15,
    v8,
    v6);
  result = std::wstring::_Tidy_deallocate(v19);
  if ( *(_BYTE *)(a1 + 392) )
  {
    result = (**(__int64 (__fastcall ***)(__int64, _QWORD))(a1 + 304))(a1 + 304, 0);
    *(_BYTE *)(a1 + 392) = 0;
  }
  if ( v31 )
    result = std::wstring::_Tidy_deallocate(v30);
  if ( *(_BYTE *)(a2 + 32) )
    return std::wstring::_Tidy_deallocate(a2);
  return result;
}

```

## disassembly

```asm
0x18003a00c  mov     [rsp-8+arg_18], rbx
0x18003a011  push    rbp
0x18003a012  push    rsi
0x18003a013  push    rdi
0x18003a014  push    r12
0x18003a016  push    r13
0x18003a018  push    r14
0x18003a01a  push    r15
0x18003a01c  lea     rbp, [rsp-40h]
0x18003a021  sub     rsp, 140h
0x18003a028  mov     rax, cs:__security_cookie
0x18003a02f  xor     rax, rsp
0x18003a032  mov     [rbp+70h+var_38], rax
0x18003a036  mov     [rsp+170h+var_118], r9
0x18003a03b  mov     [rsp+170h+var_110], r8
0x18003a040  mov     rbx, rdx
0x18003a043  mov     r14, rcx
0x18003a046  mov     [rbp+70h+var_70], rdx
0x18003a04a  lea     rax, [rsp+170h+var_F8]
0x18003a04f  mov     [rsp+170h+var_120], rax
0x18003a054  xor     edi, edi
0x18003a056  mov     [rbp+70h+var_D8], dil
0x18003a05a  cmp     [rdx+20h], dil
0x18003a05e  jz      short loc_18003A06E
0x18003a060  lea     rcx, [rsp+170h+var_F8]
0x18003a065  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003a06a  mov     [rbp+70h+var_D8], 1
0x18003a06e  lea     rdx, [rsp+170h+var_F8]
0x18003a073  lea     rcx, [rbp+70h+var_60]
0x18003a077  call    ?GetFinalPathFromPath@BrainUtils@@SA?AV?$optional@Vpath@filesystem@std@@@std@@V23@@Z; BrainUtils::GetFinalPathFromPath(std::optional<std::filesystem::path>)
0x18003a07c  nop
0x18003a07d  mov     [rbp+70h+var_68], di
0x18003a081  mov     [rbp+70h+var_64], di
0x18003a085  mov     r15b, dil
0x18003a088  call    cs:__imp_GetCurrentProcess
0x18003a08e  mov     rcx, rax
0x18003a091  lea     r8, [rbp+70h+var_64]
0x18003a095  lea     rdx, [rbp+70h+var_68]
0x18003a099  call    cs:__imp_IsWow64Process2
0x18003a09f  movzx   ecx, [rbp+70h+var_68]
0x18003a0a3  test    eax, eax
0x18003a0a5  jz      short loc_18003A0AE
0x18003a0a7  test    cx, cx
0x18003a0aa  setnz   r15b
0x18003a0ae  mov     r13d, ecx
0x18003a0b1  movzx   eax, [rbp+70h+var_64]
0x18003a0b5  mov     dword ptr [rsp+170h+var_120], eax
0x18003a0b9  lea     rcx, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x18003a0c0  mov     [rsp+170h+var_108], rcx
0x18003a0c5  mov     rax, [r14+180h]
0x18003a0cc  mov     [rsp+170h+var_100], rax
0x18003a0d1  lea     rdx, [rsp+170h+var_F8]
0x18003a0d6  lea     rcx, [rsp+170h+var_108]
0x18003a0db  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x18003a0e0  mov     rsi, rax
0x18003a0e3  cmp     qword ptr [rax+18h], 7
0x18003a0e8  jbe     short loc_18003A0ED
0x18003a0ea  mov     rsi, [rax]
0x18003a0ed  mov     r12b, [r14+0D8h]
0x18003a0f4  lea     rdi, [r14+100h]
0x18003a0fb  cmp     qword ptr [rdi+18h], 7
0x18003a100  jbe     short loc_18003A105
0x18003a102  mov     rdi, [rdi]
0x18003a105  lea     rax, [rbp+70h+var_C0]
0x18003a109  mov     [rbp+70h+var_D0], rax
0x18003a10d  mov     [rbp+70h+var_A0], 0
0x18003a111  cmp     [rbp+70h+var_40], 0
0x18003a115  jz      short loc_18003A128
0x18003a117  lea     rdx, [rbp+70h+var_60]
0x18003a11b  lea     rcx, [rbp+70h+var_C0]
0x18003a11f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003a124  mov     [rbp+70h+var_A0], 1
0x18003a128  lea     rax, [rbp+70h+var_98]
0x18003a12c  mov     [rbp+70h+var_C8], rax
0x18003a130  mov     [rbp+70h+var_78], 0
0x18003a134  cmp     byte ptr [rbx+20h], 0
0x18003a138  jz      short loc_18003A14A
0x18003a13a  mov     rdx, rbx
0x18003a13d  lea     rcx, [rbp+70h+var_98]
0x18003a141  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003a146  mov     [rbp+70h+var_78], 1
0x18003a14a  mov     [rsp+170h+var_128], r15b
0x18003a14f  mov     [rsp+170h+var_130], r13d
0x18003a154  mov     eax, dword ptr [rsp+170h+var_120]
0x18003a158  mov     [rsp+170h+var_138], eax
0x18003a15c  mov     rax, [rsp+170h+var_118]
0x18003a161  mov     [rsp+170h+var_140], rax
0x18003a166  mov     rax, [rsp+170h+var_110]
0x18003a16b  mov     [rsp+170h+var_148], rax
0x18003a170  mov     [rsp+170h+var_150], rsi
0x18003a175  mov     r9b, r12b
0x18003a178  mov     r8, rdi
0x18003a17b  lea     rdx, [rbp+70h+var_C0]
0x18003a17f  lea     rcx, [rbp+70h+var_98]
0x18003a183  call    ?UusActiveVersionMismatch@UndockedUpdateTelemetry@uus@@SAXV?$optional@Vpath@filesystem@std@@@std@@0PEB_W_N1PEBD1II2@Z; uus::UndockedUpdateTelemetry::UusActiveVersionMismatch(std::optional<std::filesystem::path>,std::optional<std::filesystem::path>,wchar_t const *,bool,wchar_t const *,char const *,wchar_t const *,uint,uint,bool)
0x18003a188  nop
0x18003a189  lea     rcx, [rsp+170h+var_F8]
0x18003a18e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a193  nop
0x18003a194  lea     rdi, [r14+130h]
0x18003a19b  xor     esi, esi
0x18003a19d  cmp     [rdi+58h], sil
0x18003a1a1  jz      short loc_18003A1B7
0x18003a1a3  mov     rax, [rdi]
0x18003a1a6  xor     edx, edx
0x18003a1a8  mov     rcx, rdi
0x18003a1ab  mov     rax, [rax]
0x18003a1ae  call    _guard_dispatch_icall
0x18003a1b3  mov     [rdi+58h], sil
0x18003a1b7  cmp     [rbp+70h+var_40], sil
0x18003a1bb  jz      short loc_18003A1C7
0x18003a1bd  lea     rcx, [rbp+70h+var_60]
0x18003a1c1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a1c6  nop
0x18003a1c7  cmp     [rbx+20h], sil
0x18003a1cb  jz      short loc_18003A1D5
0x18003a1cd  mov     rcx, rbx
0x18003a1d0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a1d5  mov     rcx, [rbp+70h+var_38]
0x18003a1d9  xor     rcx, rsp; StackCookie
0x18003a1dc  call    __security_check_cookie
0x18003a1e1  mov     rbx, [rsp+170h+arg_18]
0x18003a1e9  add     rsp, 140h
0x18003a1f0  pop     r15
0x18003a1f2  pop     r14
0x18003a1f4  pop     r13
0x18003a1f6  pop     r12
0x18003a1f8  pop     rdi
0x18003a1f9  pop     rsi
0x18003a1fa  pop     rbp
0x18003a1fb  retn
```
