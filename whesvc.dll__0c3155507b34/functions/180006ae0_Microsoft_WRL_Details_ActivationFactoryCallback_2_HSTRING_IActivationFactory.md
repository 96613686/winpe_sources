# Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)

- ea: `0x180006ae0`
- end: `0x180006c50`
- name: `??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(HSTRING string, struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800032e0`
- `0x180006ae0`
- `0x180007ff8`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180006b1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180006b1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180006b4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180006b4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180006b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180006b31`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180006c26`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180006c26`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006bc6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006bc6`

## string_xrefs

- `0x180006bef`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::ActivationFactoryCallback<2>(
        HSTRING string,
        struct Microsoft::WRL::Details::CreatorMap *a2)
{
  Microsoft::WRL::Details *v4; // rsi
  PCWSTR StringRawBuffer; // r15
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rbp
  __int64 v8; // rax
  unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  unsigned int *v11; // r8
  int v12; // edx
  unsigned int v13; // ebx
  struct IUnknown **v15; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v17; // [rsp+34h] [rbp-64h] BYREF
  __int128 v18; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v19[22]; // [rsp+48h] [rbp-50h]

  v4 = Microsoft::WRL::Details::ModuleBase::module_;
  *(_QWORD *)a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v18 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v19 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v19[14] = *(_QWORD *)L"sId";
    v13 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v18);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v4 + 40LL))(v4) + 8);
    v7 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v4 + 48LL))(v4);
    if ( (unsigned __int64)v6 >= v7 )
    {
LABEL_11:
      v13 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *v6 )
        {
          v8 = (*(__int64 (**)(void))(*v6)->Data4)();
          v9 = (unsigned __int16 *)StringRawBuffer;
          v10 = v8 - (_QWORD)StringRawBuffer;
          do
          {
            v11 = (unsigned int *)*(unsigned __int16 *)((char *)v9 + v10);
            v12 = *v9 - (_DWORD)v11;
            if ( v12 )
              break;
            ++v9;
          }
          while ( (_DWORD)v11 );
          if ( !v12 )
            break;
        }
        if ( (unsigned __int64)++v6 >= v7 )
          goto LABEL_11;
      }
      v17 = 2;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             v4,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v17,
                             v11,
                             *v6,
                             a2,
                             v15);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180006ae0  mov     [rsp+arg_10], rbx
0x180006ae5  push    rbp
0x180006ae6  push    rsi
0x180006ae7  push    rdi
0x180006ae8  push    r14
0x180006aea  push    r15
0x180006aec  sub     rsp, 70h
0x180006af0  mov     rax, cs:__security_cookie
0x180006af7  xor     rax, rsp
0x180006afa  mov     [rsp+98h+var_38], rax
0x180006aff  mov     r14, rdx
0x180006b02  mov     rdi, rcx
0x180006b05  mov     rsi, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006b0c  mov     qword ptr [rdx], 0
0x180006b13  mov     [rsp+98h+hasEmbedNull], 0
0x180006b1b  call    cs:__imp_WindowsIsStringEmpty
0x180006b21  test    eax, eax
0x180006b23  jnz     loc_180006BEF
0x180006b29  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180006b2e  mov     rcx, rdi; string
0x180006b31  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180006b37  test    eax, eax
0x180006b39  js      loc_180006BEF
0x180006b3f  cmp     [rsp+98h+hasEmbedNull], 1
0x180006b44  jz      loc_180006BEF
0x180006b4a  xor     edx, edx; length
0x180006b4c  mov     rcx, rdi; string
0x180006b4f  call    cs:__imp_WindowsGetStringRawBuffer
0x180006b55  mov     r15, rax
0x180006b58  mov     rcx, [rsi]
0x180006b5b  mov     rax, [rcx+28h]
0x180006b5f  mov     rcx, rsi
0x180006b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b67  lea     rbx, [rax+8]
0x180006b6b  mov     rcx, [rsi]
0x180006b6e  mov     rax, [rcx+30h]
0x180006b72  mov     rcx, rsi
0x180006b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b7a  mov     rbp, rax
0x180006b7d  cmp     rbx, rax
0x180006b80  jnb     short loc_180006BBC
0x180006b82  mov     rax, [rbx]
0x180006b85  test    rax, rax
0x180006b88  jz      short loc_180006BB3
0x180006b8a  mov     rax, [rax+8]
0x180006b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b93  mov     rcx, r15
0x180006b96  sub     rax, r15
0x180006b99  movzx   edx, word ptr [rcx]
0x180006b9c  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180006ba1  sub     edx, r8d
0x180006ba4  jnz     short loc_180006BAF
0x180006ba6  add     rcx, 2
0x180006baa  test    r8d, r8d
0x180006bad  jnz     short loc_180006B99
0x180006baf  test    edx, edx
0x180006bb1  jz      short loc_180006BCE
0x180006bb3  add     rbx, 8
0x180006bb7  cmp     rbx, rbp
0x180006bba  jb      short loc_180006B82
0x180006bbc  mov     rdx, rdi
0x180006bbf  mov     ebx, 80040111h
0x180006bc4  mov     ecx, ebx
0x180006bc6  call    cs:__imp_RoOriginateError
0x180006bcc  jmp     short loc_180006C2D
0x180006bce  mov     [rsp+98h+var_64], 2
0x180006bd6  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x180006bdb  mov     r9, [rbx]; struct _GUID *
0x180006bde  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180006be3  mov     rcx, rsi; this
0x180006be6  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180006beb  mov     ebx, eax
0x180006bed  jmp     short loc_180006C2D
0x180006bef  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180006bf6  movups  [rsp+98h+var_60], xmm0
0x180006bfb  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180006c02  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180006c07  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180006c0f  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180006c15  lea     r8, [rsp+98h+var_60]
0x180006c1a  mov     edx, 12h
0x180006c1f  mov     ebx, 80070057h
0x180006c24  mov     ecx, ebx
0x180006c26  call    cs:__imp_RoOriginateErrorW
0x180006c2c  nop
0x180006c2d  mov     eax, ebx
0x180006c2f  mov     rcx, [rsp+98h+var_38]
0x180006c34  xor     rcx, rsp; StackCookie
0x180006c37  call    __security_check_cookie
0x180006c3c  mov     rbx, [rsp+98h+arg_10]
0x180006c44  add     rsp, 70h
0x180006c48  pop     r15
0x180006c4a  pop     r14
0x180006c4c  pop     rdi
0x180006c4d  pop     rsi
0x180006c4e  pop     rbp
0x180006c4f  retn
```
