# ProgidArrayAppendHandler<StateRepository::Cache::Entity::FileTypeAssociation_NoThrow>(void *,__int64,StateRepository::Cache::Entity::FileTypeAssociation_NoThrow &)

- ea: `0x18000def0`
- end: `0x18000e085`
- name: `??$ProgidArrayAppendHandler@VFileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@@@YAJPEAX_JAEAVFileTypeAssociation_NoThrow@Entity@Cache@StateRepository@@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010c30`

## callees

- `0x18000def0`
- `0x18000e08c`
- `0x180010c04`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000dfb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000dfb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000dfc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000dfc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000df6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000df9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e014`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e043`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000df6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000df9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e014`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e043`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e074`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ProgidArrayAppendHandler<StateRepository::Cache::Entity::FileTypeAssociation_NoThrow>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const WCHAR *v5; // rdi
  unsigned __int64 v6; // rbx
  HRESULT v7; // ebx
  UINT32 v9; // edx
  const WCHAR *v10; // rcx
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+40h] [rbp+8h] BYREF
  __int64 v18; // [rsp+50h] [rbp+18h]

  v18 = a1;
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  string = 0;
  v5 = *(const WCHAR **)(a3 + 24);
  if ( v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    if ( v6 > 0xFFFFFFFF )
    {
      v7 = -2147024362;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x682,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v7,
        v15);
      WindowsDeleteString(string);
      string = 0;
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
      return (unsigned int)v7;
    }
    WindowsDeleteString(0);
    v9 = v6;
    v10 = v5;
  }
  else
  {
    WindowsDeleteString(0);
    v9 = 0;
    v10 = &LocaleName;
  }
  string = 0;
  v7 = WindowsCreateString(v10, v9, &string);
  if ( v7 < 0 )
    goto LABEL_8;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( DynamicProgIdHelpers::IsProgIdEnabled(StringRawBuffer, v12)
    && (v13 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)a1 + 104LL))(a1, string), v14 = v13, v13 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x685,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v13,
      v15);
    WindowsDeleteString(string);
    string = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    return v14;
  }
  else
  {
    WindowsDeleteString(string);
    string = 0;
    if ( a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    return 0;
  }
}

```

## disassembly

```asm
0x18000def0  mov     [rsp+arg_8], rbx
0x18000def5  push    rbp
0x18000def6  push    rsi
0x18000def7  push    rdi; int
0x18000def8  sub     rsp, 20h
0x18000defc  mov     rdi, r8
0x18000deff  mov     rsi, rcx
0x18000df02  mov     [rsp+38h+arg_10], rcx
0x18000df07  test    rcx, rcx
0x18000df0a  jz      short loc_18000DF19
0x18000df0c  mov     rax, [rcx]
0x18000df0f  mov     rax, [rax+8]
0x18000df13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df18  nop
0x18000df19  xor     ebp, ebp
0x18000df1b  mov     [rsp+38h+string], rbp
0x18000df20  mov     rdi, [rdi+18h]
0x18000df24  test    rdi, rdi
0x18000df27  jz      short loc_18000DF9B
0x18000df29  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000df30  inc     rbx
0x18000df33  cmp     word ptr [rdi+rbx*2], 0
0x18000df38  jnz     short loc_18000DF30
0x18000df3a  mov     eax, 0FFFFFFFFh
0x18000df3f  cmp     rbx, rax
0x18000df42  jbe     loc_18000E072
0x18000df48  mov     ebx, 80070216h
0x18000df4d  mov     rcx, [rsp+38h]; this
0x18000df52  mov     r9d, ebx; char *
0x18000df55  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18000df5c  mov     edx, 682h; void *
0x18000df61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df66  nop
0x18000df67  mov     rcx, [rsp+38h+string]; string
0x18000df6c  call    cs:__imp_WindowsDeleteString
0x18000df72  mov     [rsp+38h+string], rbp
0x18000df77  test    rsi, rsi
0x18000df7a  jz      short loc_18000DF8C
0x18000df7c  mov     rax, [rsi]
0x18000df7f  mov     rcx, rsi
0x18000df82  mov     rax, [rax+10h]
0x18000df86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df8b  nop
0x18000df8c  mov     eax, ebx
0x18000df8e  mov     rbx, [rsp+38h+arg_8]
0x18000df93  add     rsp, 20h
0x18000df97  pop     rdi
0x18000df98  pop     rsi
0x18000df99  pop     rbp
0x18000df9a  retn
0x18000df9b  xor     ecx, ecx; string
0x18000df9d  call    cs:__imp_WindowsDeleteString
0x18000dfa3  xor     edx, edx; length
0x18000dfa5  lea     rcx, LocaleName; sourceString
0x18000dfac  mov     [rsp+38h+string], rbp
0x18000dfb1  lea     r8, [rsp+38h+string]; string
0x18000dfb6  call    cs:__imp_WindowsCreateString
0x18000dfbc  mov     ebx, eax
0x18000dfbe  test    eax, eax
0x18000dfc0  js      short loc_18000DF4D
0x18000dfc2  xor     edx, edx; length
0x18000dfc4  mov     rcx, [rsp+38h+string]; string
0x18000dfc9  call    cs:__imp_WindowsGetStringRawBuffer
0x18000dfcf  mov     rcx, rax; sourceString
0x18000dfd2  call    ?IsProgIdEnabled@DynamicProgIdHelpers@@YA_NPEBG@Z; DynamicProgIdHelpers::IsProgIdEnabled(ushort const *)
0x18000dfd7  test    al, al
0x18000dfd9  jz      short loc_18000E03E
0x18000dfdb  mov     rax, [rsi]
0x18000dfde  mov     rdx, [rsp+38h+string]
0x18000dfe3  mov     rcx, rsi
0x18000dfe6  mov     rax, [rax+68h]
0x18000dfea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfef  mov     ebx, eax
0x18000dff1  test    eax, eax
0x18000dff3  jns     short loc_18000E03E
0x18000dff5  mov     rcx, [rsp+38h]; this
0x18000dffa  mov     r9d, eax; char *
0x18000dffd  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18000e004  mov     edx, 685h; void *
0x18000e009  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e00e  nop
0x18000e00f  mov     rcx, [rsp+38h+string]; string
0x18000e014  call    cs:__imp_WindowsDeleteString
0x18000e01a  mov     [rsp+38h+string], rbp
0x18000e01f  mov     rax, [rsi]
0x18000e022  mov     rcx, rsi
0x18000e025  mov     rax, [rax+10h]
0x18000e029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e02e  nop
0x18000e02f  mov     eax, ebx
0x18000e031  mov     rbx, [rsp+38h+arg_8]
0x18000e036  add     rsp, 20h
0x18000e03a  pop     rdi
0x18000e03b  pop     rsi
0x18000e03c  pop     rbp
0x18000e03d  retn
0x18000e03e  mov     rcx, [rsp+38h+string]; string
0x18000e043  call    cs:__imp_WindowsDeleteString
0x18000e049  mov     [rsp+38h+string], rbp
0x18000e04e  test    rsi, rsi
0x18000e051  jz      short loc_18000E063
0x18000e053  mov     rax, [rsi]
0x18000e056  mov     rcx, rsi
0x18000e059  mov     rax, [rax+10h]
0x18000e05d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e062  nop
0x18000e063  xor     eax, eax
0x18000e065  mov     rbx, [rsp+38h+arg_8]
0x18000e06a  add     rsp, 20h
0x18000e06e  pop     rdi
0x18000e06f  pop     rsi
0x18000e070  pop     rbp
0x18000e071  retn
0x18000e072  xor     ecx, ecx; string
0x18000e074  call    cs:__imp_WindowsDeleteString
0x18000e07a  mov     edx, ebx
0x18000e07c  mov     rcx, rdi
0x18000e07f  jmp     loc_18000DFAC
```
