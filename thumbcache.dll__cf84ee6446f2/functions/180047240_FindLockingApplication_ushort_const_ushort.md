# FindLockingApplication(ushort const *,ushort * *)

- ea: `0x180047240`
- end: `0x18004734f`
- name: `?FindLockingApplication@@YAJPEBGPEAPEAG@Z`
- size: `271`
- prototype: `__int64 __fastcall(PCWSTR pszPath, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011094`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x180035830`
- `0x180047240`
- `0x180049010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18004728e`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18004728e`
- `api-ms-win-storage-exports-internal-l1-1-0!GetInfoForFileInUse` at `0x1800472cd`
- `api-ms-win-storage-exports-internal-l1-1-0!GetInfoForFileInUse` at `0x1800472cd`

## string_xrefs

- `0x1800472a1`: `onecoreuap\shell\ext\thumbnailcache\common\util.cpp`
- `0x1800472de`: `onecoreuap\shell\ext\thumbnailcache\common\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FindLockingApplication(PCWSTR pszPath, unsigned __int16 **a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  int InfoForFileInUse; // eax
  __int64 v7; // rdx
  __int64 v9; // [rsp+20h] [rbp-20h] BYREF
  void *ppv; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]

  *a2 = 0;
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v4 = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v9 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    InfoForFileInUse = GetInfoForFileInUse(ppv, &v9);
    v5 = InfoForFileInUse;
    if ( InfoForFileInUse >= 0 )
    {
      InfoForFileInUse = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v9 + 24LL))(v9, a2);
      v5 = InfoForFileInUse;
      if ( InfoForFileInUse >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
        v5 = 0;
        goto LABEL_9;
      }
      v7 = 111;
    }
    else
    {
      v7 = 110;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\util.cpp",
      (const char *)(unsigned int)InfoForFileInUse,
      v9);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\common\\util.cpp",
      (const char *)(unsigned int)v4,
      v9);
  }
LABEL_9:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return v5;
}

```

## disassembly

```asm
0x180047240  mov     [rsp-8+arg_10], rbx
0x180047245  mov     [rsp-8+arg_18], rdi
0x18004724a  push    rbp
0x18004724b  mov     rbp, rsp
0x18004724e  sub     rsp, 40h
0x180047252  mov     rax, cs:__security_cookie
0x180047259  xor     rax, rsp
0x18004725c  mov     [rbp+var_10], rax
0x180047260  mov     rdi, rdx
0x180047263  mov     rbx, rcx
0x180047266  mov     qword ptr [rdx], 0
0x18004726d  mov     [rbp+ppv], 0
0x180047275  lea     rcx, [rbp+ppv]
0x180047279  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004727e  lea     r9, [rbp+ppv]; ppv
0x180047282  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180047289  xor     edx, edx; pbc
0x18004728b  mov     rcx, rbx; pszPath
0x18004728e  call    cs:__imp_SHCreateItemFromParsingName
0x180047294  mov     ebx, eax
0x180047296  test    eax, eax
0x180047298  jns     short loc_1800472B4
0x18004729a  mov     rcx, [rbp+8]; this
0x18004729e  mov     r9d, eax; char *
0x1800472a1  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800472a8  mov     edx, 6Ch ; 'l'; void *
0x1800472ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800472b2  jmp     short loc_180047328
0x1800472b4  mov     [rbp+var_20], 0
0x1800472bc  lea     rcx, [rbp+var_20]
0x1800472c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800472c5  lea     rdx, [rbp+var_20]
0x1800472c9  mov     rcx, [rbp+ppv]
0x1800472cd  call    cs:__imp_GetInfoForFileInUse
0x1800472d3  mov     ebx, eax
0x1800472d5  test    eax, eax
0x1800472d7  jns     short loc_1800472FD
0x1800472d9  mov     edx, 6Eh ; 'n'; void *
0x1800472de  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800472e5  mov     r9d, eax; char *
0x1800472e8  mov     rcx, [rbp+8]; this
0x1800472ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800472f1  nop
0x1800472f2  lea     rcx, [rbp+var_20]
0x1800472f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800472fb  jmp     short loc_180047328
0x1800472fd  mov     rcx, [rbp+var_20]
0x180047301  mov     rax, [rcx]
0x180047304  mov     rdx, rdi
0x180047307  mov     rax, [rax+18h]
0x18004730b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047310  mov     ebx, eax
0x180047312  test    eax, eax
0x180047314  jns     short loc_18004731D
0x180047316  mov     edx, 6Fh ; 'o'
0x18004731b  jmp     short loc_1800472DE
0x18004731d  lea     rcx, [rbp+var_20]
0x180047321  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047326  xor     ebx, ebx
0x180047328  lea     rcx, [rbp+ppv]
0x18004732c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180047331  mov     eax, ebx
0x180047333  mov     rcx, [rbp+var_10]
0x180047337  xor     rcx, rsp; StackCookie
0x18004733a  call    __security_check_cookie
0x18004733f  mov     rbx, [rsp+40h+arg_10]
0x180047344  mov     rdi, [rsp+40h+arg_18]
0x180047349  add     rsp, 40h
0x18004734d  pop     rbp
0x18004734e  retn
```
