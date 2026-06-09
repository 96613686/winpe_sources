# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x14002e668`
- end: `0x14002e7d1`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002e650`

## callees

- `0x140025aa0`
- `0x14002e668`
- `0x14002ec20`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x14002e6b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x14002e6b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14002e6d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14002e6d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x14002e6a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x14002e6a2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14002e769`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14002e769`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x14002e7a8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x14002e7a8`

## string_xrefs

- `0x14002e771`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetActivationFactory<2>(
        Microsoft::WRL::Details *this,
        __int64 a2,
        HSTRING a3,
        const struct Microsoft::WRL::Details::CreatorMap *a4)
{
  PCWSTR StringRawBuffer; // r15
  const struct _GUID **v8; // rbx
  unsigned __int64 v9; // rbp
  __int64 v10; // rax
  unsigned __int16 *v11; // rcx
  __int64 v12; // rax
  unsigned int *v13; // r8
  int v14; // edx
  unsigned int v16; // ebx
  struct IUnknown **v17; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v19; // [rsp+34h] [rbp-64h] BYREF
  __int128 v20; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v21[22]; // [rsp+48h] [rbp-50h]

  *(_QWORD *)a4 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(a3) || WindowsStringHasEmbeddedNull(a3, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v20 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v21 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v21[14] = *(_QWORD *)L"sId";
    v16 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v20);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    v8 = (const struct _GUID **)((*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 40LL))(this)
                               + 8);
    v9 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
    while ( (unsigned __int64)v8 < v9 )
    {
      if ( *v8 )
      {
        v10 = (*(__int64 (**)(void))(*v8)->Data4)();
        v11 = (unsigned __int16 *)StringRawBuffer;
        v12 = v10 - (_QWORD)StringRawBuffer;
        do
        {
          v13 = (unsigned int *)*(unsigned __int16 *)((char *)v11 + v12);
          v14 = *v11 - (_DWORD)v13;
          if ( v14 )
            break;
          ++v11;
        }
        while ( (_DWORD)v13 );
        if ( !v14 )
        {
          v19 = 2;
          return Microsoft::WRL::Details::GetCacheEntry(
                   this,
                   (struct Microsoft::WRL::Details::ModuleBase *)&v19,
                   v13,
                   *v8,
                   a4,
                   v17);
        }
      }
      ++v8;
    }
    v16 = -2147221231;
    RoOriginateError(2147746065LL, a3);
  }
  return v16;
}

```

## disassembly

```asm
0x14002e668  mov     [rsp+arg_8], rbx
0x14002e66d  push    rbp
0x14002e66e  push    rsi
0x14002e66f  push    rdi
0x14002e670  push    r14
0x14002e672  push    r15
0x14002e674  sub     rsp, 70h
0x14002e678  mov     rax, cs:__security_cookie
0x14002e67f  xor     rax, rsp
0x14002e682  mov     [rsp+98h+var_38], rax
0x14002e687  mov     r14, r9
0x14002e68a  mov     rdi, r8
0x14002e68d  mov     rsi, rcx
0x14002e690  mov     qword ptr [r9], 0
0x14002e697  mov     [rsp+98h+hasEmbedNull], 0
0x14002e69f  mov     rcx, r8; string
0x14002e6a2  call    cs:__imp_WindowsIsStringEmpty
0x14002e6a8  test    eax, eax
0x14002e6aa  jnz     loc_14002E771
0x14002e6b0  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x14002e6b5  mov     rcx, rdi; string
0x14002e6b8  call    cs:__imp_WindowsStringHasEmbeddedNull
0x14002e6be  test    eax, eax
0x14002e6c0  js      loc_14002E771
0x14002e6c6  cmp     [rsp+98h+hasEmbedNull], 1
0x14002e6cb  jz      loc_14002E771
0x14002e6d1  xor     edx, edx; length
0x14002e6d3  mov     rcx, rdi; string
0x14002e6d6  call    cs:__imp_WindowsGetStringRawBuffer
0x14002e6dc  mov     r15, rax
0x14002e6df  mov     rcx, [rsi]
0x14002e6e2  mov     rax, [rcx+28h]
0x14002e6e6  mov     rcx, rsi
0x14002e6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e6ee  lea     rbx, [rax+8]
0x14002e6f2  mov     rcx, [rsi]
0x14002e6f5  mov     rax, [rcx+30h]
0x14002e6f9  mov     rcx, rsi
0x14002e6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e701  mov     rbp, rax
0x14002e704  cmp     rbx, rbp
0x14002e707  jnb     short loc_14002E75F
0x14002e709  mov     rax, [rbx]
0x14002e70c  test    rax, rax
0x14002e70f  jz      short loc_14002E73A
0x14002e711  mov     rax, [rax+8]
0x14002e715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e71a  mov     rcx, r15
0x14002e71d  sub     rax, r15
0x14002e720  movzx   edx, word ptr [rcx]
0x14002e723  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x14002e728  sub     edx, r8d
0x14002e72b  jnz     short loc_14002E736
0x14002e72d  add     rcx, 2
0x14002e731  test    r8d, r8d
0x14002e734  jnz     short loc_14002E720
0x14002e736  test    edx, edx
0x14002e738  jz      short loc_14002E740
0x14002e73a  add     rbx, 8
0x14002e73e  jmp     short loc_14002E704
0x14002e740  mov     [rsp+98h+var_64], 2
0x14002e748  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x14002e74d  mov     r9, [rbx]; struct _GUID *
0x14002e750  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x14002e755  mov     rcx, rsi; this
0x14002e758  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x14002e75d  jmp     short loc_14002E7B0
0x14002e75f  mov     rdx, rdi
0x14002e762  mov     ebx, 80040111h
0x14002e767  mov     ecx, ebx
0x14002e769  call    cs:__imp_RoOriginateError
0x14002e76f  jmp     short loc_14002E7AE
0x14002e771  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x14002e778  movups  [rsp+98h+var_60], xmm0
0x14002e77d  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x14002e784  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x14002e789  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x14002e791  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x14002e797  lea     r8, [rsp+98h+var_60]
0x14002e79c  mov     edx, 12h
0x14002e7a1  mov     ebx, 80070057h
0x14002e7a6  mov     ecx, ebx
0x14002e7a8  call    cs:__imp_RoOriginateErrorW
0x14002e7ae  mov     eax, ebx
0x14002e7b0  mov     rcx, [rsp+98h+var_38]
0x14002e7b5  xor     rcx, rsp; StackCookie
0x14002e7b8  call    __security_check_cookie
0x14002e7bd  mov     rbx, [rsp+98h+arg_8]
0x14002e7c5  add     rsp, 70h
0x14002e7c9  pop     r15
0x14002e7cb  pop     r14
0x14002e7cd  pop     rdi
0x14002e7ce  pop     rsi
0x14002e7cf  pop     rbp
0x14002e7d0  retn
```
