# GetApplicationExtensionFromLauncherInfo(Windows::Internal::StateRepository::IFileTypeAssociationLauncherInfo *,Windows::Internal::StateRepository::IApplicationExtension * *,HSTRING__ * *)

- ea: `0x180039320`
- end: `0x1800394f9`
- name: `?GetApplicationExtensionFromLauncherInfo@@YAJPEAUIFileTypeAssociationLauncherInfo@StateRepository@Internal@Windows@@PEAPEAUIApplicationExtension@234@PEAPEAUHSTRING__@@@Z`
- size: `473`
- prototype: `int(struct Windows::Internal::StateRepository::IFileTypeAssociationLauncherInfo *, struct Windows::Internal::StateRepository::IApplicationExtension **, HSTRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021ae4`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x180039320`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800393a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800393de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003949e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800394e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800393a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800393de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003949e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800394e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800393ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800393ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetApplicationExtensionFromLauncherInfo(
        struct Windows::Internal::StateRepository::IFileTypeAssociationLauncherInfo *a1,
        struct Windows::Internal::StateRepository::IApplicationExtension **a2,
        HSTRING *a3)
{
  __int64 (__fastcall *v6)(struct Windows::Internal::StateRepository::IFileTypeAssociationLauncherInfo *, __int64 *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  HRESULT v13; // eax
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  __int64 v21; // [rsp+50h] [rbp+30h] BYREF
  HSTRING string; // [rsp+58h] [rbp+38h] BYREF

  *a2 = 0;
  *a3 = 0;
  v21 = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IFileTypeAssociationLauncherInfo *, __int64 *))(*(_QWORD *)a1 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v7 = v6(a1, &v21);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18E,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v7,
      savedregs);
    v17 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v8;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IApplicationExtension **))(*(_QWORD *)v21 + 96LL))(
         v21,
         a2);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18F,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v9,
      savedregs);
    v16 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v8;
  }
  string = 0;
  v10 = v21;
  v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v21 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v12 = v11(v10, &string);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x192,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v12,
      savedregs);
    WindowsDeleteString(string);
    string = 0;
    v18 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return v8;
  }
  v13 = WindowsDuplicateString(string, a3);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.private.launcherqueryinfo.cpp",
      (const char *)(unsigned int)v13,
      savedregs);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    return v8;
  }
  WindowsDeleteString(string);
  string = 0;
  v14 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return 0;
}

```

## disassembly

```asm
0x180039320  mov     [rsp-28h+arg_10], rbx
0x180039325  push    rbp
0x180039326  push    rsi
0x180039327  push    rdi
0x180039328  push    r14
0x18003932a  push    r15; int
0x18003932c  mov     rbp, rsp
0x18003932f  sub     rsp, 20h
0x180039333  mov     rsi, r8
0x180039336  mov     r14, rdx
0x180039339  mov     rdi, rcx
0x18003933c  xor     r15d, r15d
0x18003933f  mov     [rdx], r15
0x180039342  mov     [r8], r15
0x180039345  mov     [rbp+arg_0], r15
0x180039349  mov     rax, [rcx]
0x18003934c  mov     rbx, [rax+38h]
0x180039350  lea     rcx, [rbp+arg_0]
0x180039354  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180039359  lea     rdx, [rbp+arg_0]
0x18003935d  mov     rcx, rdi
0x180039360  mov     rax, rbx
0x180039363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039368  mov     ebx, eax
0x18003936a  test    eax, eax
0x18003936c  js      loc_18003944C
0x180039372  mov     rcx, [rbp+arg_0]
0x180039376  mov     rax, [rcx]
0x180039379  mov     rdx, r14
0x18003937c  mov     rax, [rax+60h]
0x180039380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039385  mov     ebx, eax
0x180039387  test    eax, eax
0x180039389  js      loc_180039415
0x18003938f  mov     [rbp+string], r15
0x180039393  mov     rdi, [rbp+arg_0]
0x180039397  mov     rax, [rdi]
0x18003939a  mov     rbx, [rax+40h]
0x18003939e  xor     ecx, ecx; string
0x1800393a0  call    cs:__imp_WindowsDeleteString
0x1800393a6  mov     [rbp+string], r15
0x1800393aa  lea     rdx, [rbp+string]
0x1800393ae  mov     rcx, rdi
0x1800393b1  mov     rax, rbx
0x1800393b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393b9  mov     ebx, eax
0x1800393bb  test    eax, eax
0x1800393bd  js      loc_180039481
0x1800393c3  mov     rdx, rsi; newString
0x1800393c6  mov     rcx, [rbp+string]; string
0x1800393ca  call    cs:__imp_WindowsDuplicateString
0x1800393d0  mov     ebx, eax
0x1800393d2  test    eax, eax
0x1800393d4  js      loc_1800394C4
0x1800393da  mov     rcx, [rbp+string]; string
0x1800393de  call    cs:__imp_WindowsDeleteString
0x1800393e4  mov     [rbp+string], r15
0x1800393e8  mov     rcx, [rbp+arg_0]
0x1800393ec  test    rcx, rcx
0x1800393ef  jz      short loc_180039402
0x1800393f1  mov     [rbp+arg_0], r15
0x1800393f5  mov     rax, [rcx]
0x1800393f8  mov     rax, [rax+10h]
0x1800393fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039401  nop
0x180039402  xor     eax, eax
0x180039404  mov     rbx, [rsp+20h+arg_10]
0x180039409  add     rsp, 20h
0x18003940d  pop     r15
0x18003940f  pop     r14
0x180039411  pop     rdi
0x180039412  pop     rsi
0x180039413  pop     rbp
0x180039414  retn
0x180039415  mov     rcx, [rbp+28h]; this
0x180039419  mov     r9d, ebx; char *
0x18003941c  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x180039423  mov     edx, 18Fh; void *
0x180039428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003942d  nop
0x18003942e  mov     rcx, [rbp+arg_0]
0x180039432  test    rcx, rcx
0x180039435  jz      short loc_180039448
0x180039437  mov     [rbp+arg_0], r15
0x18003943b  mov     rax, [rcx]
0x18003943e  mov     rax, [rax+10h]
0x180039442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039447  nop
0x180039448  mov     eax, ebx
0x18003944a  jmp     short loc_180039404
0x18003944c  mov     rcx, [rbp+28h]; this
0x180039450  mov     r9d, ebx; char *
0x180039453  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18003945a  mov     edx, 18Eh; void *
0x18003945f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039464  nop
0x180039465  mov     rcx, [rbp+arg_0]
0x180039469  test    rcx, rcx
0x18003946c  jz      short loc_18003947F
0x18003946e  mov     [rbp+arg_0], r15
0x180039472  mov     rax, [rcx]
0x180039475  mov     rax, [rax+10h]
0x180039479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003947e  nop
0x18003947f  jmp     short loc_180039448
0x180039481  mov     rcx, [rbp+28h]; this
0x180039485  mov     r9d, ebx; char *
0x180039488  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x18003948f  mov     edx, 192h; void *
0x180039494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039499  nop
0x18003949a  mov     rcx, [rbp+string]; string
0x18003949e  call    cs:__imp_WindowsDeleteString
0x1800394a4  mov     [rbp+string], r15
0x1800394a8  mov     rcx, [rbp+arg_0]
0x1800394ac  test    rcx, rcx
0x1800394af  jz      short loc_1800394C2
0x1800394b1  mov     [rbp+arg_0], r15
0x1800394b5  mov     rax, [rcx]
0x1800394b8  mov     rax, [rax+10h]
0x1800394bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394c1  nop
0x1800394c2  jmp     short loc_180039448
0x1800394c4  mov     rcx, [rbp+28h]; this
0x1800394c8  mov     r9d, ebx; char *
0x1800394cb  lea     r8, aOnecoreuapShel_31; "onecoreuap\\shell\\windows.system.launc"...
0x1800394d2  mov     edx, 193h; void *
0x1800394d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800394dc  nop
0x1800394dd  mov     rcx, [rbp+string]; string
0x1800394e1  call    cs:__imp_WindowsDeleteString
0x1800394e7  mov     [rbp+string], r15
0x1800394eb  lea     rcx, [rbp+arg_0]
0x1800394ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800394f4  jmp     loc_180039448
```
