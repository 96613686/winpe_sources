# ProgidArrayAppendHandler<StateRepository::Cache::Entity::AppUriHandlerLauncherInfo_NoThrow>(void *,__int64,StateRepository::Cache::Entity::AppUriHandlerLauncherInfo_NoThrow &)

- ea: `0x18000dd40`
- end: `0x18000deba`
- name: `??$ProgidArrayAppendHandler@VAppUriHandlerLauncherInfo_NoThrow@Entity@Cache@StateRepository@@@@YAJPEAX_JAEAVAppUriHandlerLauncherInfo_NoThrow@Entity@Cache@StateRepository@@@Z`
- size: `378`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008db8`
- `0x1800d12d8`

## callees

- `0x1800049bc`
- `0x18000dd40`
- `0x18000e08c`
- `0x180010c04`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ddc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000ddc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ddd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ddd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dd9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ddae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000de0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000de5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dd9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ddae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000de0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000de5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000dea5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ProgidArrayAppendHandler<StateRepository::Cache::Entity::AppUriHandlerLauncherInfo_NoThrow>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const WCHAR *v5; // rsi
  unsigned __int64 v6; // rdi
  UINT32 v7; // edx
  const WCHAR *v8; // rcx
  unsigned int v9; // edi
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v11; // rdx
  int v12; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+40h] [rbp+20h] BYREF
  __int64 v17; // [rsp+50h] [rbp+30h] BYREF

  v17 = a1;
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  string = 0;
  v5 = *(const WCHAR **)(a3 + 24);
  if ( !v5 )
  {
    WindowsDeleteString(0);
    v7 = 0;
    v8 = &LocaleName;
    goto LABEL_9;
  }
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  if ( v6 <= 0xFFFFFFFF )
  {
    WindowsDeleteString(0);
    v7 = v6;
    v8 = v5;
LABEL_9:
    string = 0;
    v9 = WindowsCreateString(v8, v7, &string);
    goto LABEL_10;
  }
  v9 = -2147024362;
LABEL_10:
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x682,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)v9,
      savedregs);
    WindowsDeleteString(string);
    string = 0;
    if ( a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    return v9;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( DynamicProgIdHelpers::IsProgIdEnabled(StringRawBuffer, v11) )
  {
    v12 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)a1 + 104LL))(a1, string);
    v9 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x685,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
        (const char *)(unsigned int)v12,
        savedregs);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
      return v9;
    }
  }
  WindowsDeleteString(string);
  string = 0;
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18000dd40  mov     [rsp-18h+arg_8], rbx
0x18000dd45  mov     [rsp-18h+arg_18], rsi
0x18000dd4a  push    rbp
0x18000dd4b  push    rdi
0x18000dd4c  push    r14; int
0x18000dd4e  mov     rbp, rsp
0x18000dd51  sub     rsp, 20h
0x18000dd55  mov     rsi, r8
0x18000dd58  mov     rbx, rcx
0x18000dd5b  mov     [rbp+arg_10], rcx
0x18000dd5f  xor     r14d, r14d
0x18000dd62  test    rcx, rcx
0x18000dd65  jz      short loc_18000DD74
0x18000dd67  mov     rax, [rcx]
0x18000dd6a  mov     rax, [rax+8]
0x18000dd6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd73  nop
0x18000dd74  mov     [rbp+string], r14
0x18000dd78  mov     rsi, [rsi+18h]
0x18000dd7c  test    rsi, rsi
0x18000dd7f  jz      short loc_18000DDAC
0x18000dd81  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000dd85  inc     rdi
0x18000dd88  cmp     [rsi+rdi*2], r14w
0x18000dd8d  jnz     short loc_18000DD85
0x18000dd8f  mov     eax, 0FFFFFFFFh
0x18000dd94  cmp     rdi, rax
0x18000dd97  ja      loc_18000DE7E
0x18000dd9d  xor     ecx, ecx; string
0x18000dd9f  call    cs:__imp_WindowsDeleteString
0x18000dda5  mov     edx, edi
0x18000dda7  mov     rcx, rsi
0x18000ddaa  jmp     short loc_18000DDBD
0x18000ddac  xor     ecx, ecx; string
0x18000ddae  call    cs:__imp_WindowsDeleteString
0x18000ddb4  xor     edx, edx; length
0x18000ddb6  lea     rcx, LocaleName; sourceString
0x18000ddbd  mov     [rbp+string], r14
0x18000ddc1  lea     r8, [rbp+string]; string
0x18000ddc5  call    cs:__imp_WindowsCreateString
0x18000ddcb  mov     edi, eax
0x18000ddcd  test    edi, edi
0x18000ddcf  js      short loc_18000DE3E
0x18000ddd1  xor     edx, edx; length
0x18000ddd3  mov     rcx, [rbp+string]; string
0x18000ddd7  call    cs:__imp_WindowsGetStringRawBuffer
0x18000dddd  mov     rcx, rax; sourceString
0x18000dde0  call    ?IsProgIdEnabled@DynamicProgIdHelpers@@YA_NPEBG@Z; DynamicProgIdHelpers::IsProgIdEnabled(ushort const *)
0x18000dde5  test    al, al
0x18000dde7  jz      short loc_18000DE06
0x18000dde9  mov     rax, [rbx]
0x18000ddec  mov     rdx, [rbp+string]
0x18000ddf0  mov     rcx, rbx
0x18000ddf3  mov     rax, [rax+68h]
0x18000ddf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddfc  mov     edi, eax
0x18000ddfe  test    eax, eax
0x18000de00  js      loc_18000DE88
0x18000de06  mov     rcx, [rbp+string]; string
0x18000de0a  call    cs:__imp_WindowsDeleteString
0x18000de10  mov     [rbp+string], r14
0x18000de14  test    rbx, rbx
0x18000de17  jz      short loc_18000DE29
0x18000de19  mov     rax, [rbx]
0x18000de1c  mov     rcx, rbx
0x18000de1f  mov     rax, [rax+10h]
0x18000de23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de28  nop
0x18000de29  xor     eax, eax
0x18000de2b  mov     rbx, [rsp+20h+arg_8]
0x18000de30  mov     rsi, [rsp+20h+arg_18]
0x18000de35  add     rsp, 20h
0x18000de39  pop     r14
0x18000de3b  pop     rdi
0x18000de3c  pop     rbp
0x18000de3d  retn
0x18000de3e  mov     rcx, [rbp+18h]; this
0x18000de42  mov     r9d, edi; char *
0x18000de45  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18000de4c  mov     edx, 682h; void *
0x18000de51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de56  nop
0x18000de57  mov     rcx, [rbp+string]; string
0x18000de5b  call    cs:__imp_WindowsDeleteString
0x18000de61  mov     [rbp+string], r14
0x18000de65  test    rbx, rbx
0x18000de68  jz      short loc_18000DE7A
0x18000de6a  mov     rax, [rbx]
0x18000de6d  mov     rcx, rbx
0x18000de70  mov     rax, [rax+10h]
0x18000de74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de79  nop
0x18000de7a  mov     eax, edi
0x18000de7c  jmp     short loc_18000DE2B
0x18000de7e  mov     edi, 80070216h
0x18000de83  jmp     loc_18000DDCD
0x18000de88  mov     rcx, [rbp+18h]; this
0x18000de8c  mov     r9d, edi; char *
0x18000de8f  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18000de96  mov     edx, 685h; void *
0x18000de9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dea0  nop
0x18000dea1  mov     rcx, [rbp+string]; string
0x18000dea5  call    cs:__imp_WindowsDeleteString
0x18000deab  mov     [rbp+string], r14
0x18000deaf  lea     rcx, [rbp+arg_10]
0x18000deb3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000deb8  jmp     short loc_18000DE7A
```
