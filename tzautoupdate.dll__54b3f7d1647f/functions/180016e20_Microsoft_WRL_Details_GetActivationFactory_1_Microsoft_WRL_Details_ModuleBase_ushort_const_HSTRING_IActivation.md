# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180016e20`
- end: `0x180016f90`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800174d0`

## callees

- `0x180016e20`
- `0x180017134`
- `0x18001b150`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180016e70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180016e70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016e8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016e8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180016e5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180016e5a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180016f67`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180016f67`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180016f28`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180016f28`

## string_xrefs

- `0x180016f30`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetActivationFactory<1>(
        Microsoft::WRL::Details *this,
        __int64 a2,
        HSTRING a3,
        _QWORD *a4)
{
  PCWSTR StringRawBuffer; // r15
  const struct _GUID **v8; // rbx
  unsigned __int64 v9; // rbp
  __int64 v10; // rax
  unsigned __int16 *v11; // rcx
  __int64 v12; // rax
  int v13; // r8d
  int v14; // edx
  unsigned int v16; // ebx
  struct IUnknown **v17; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v19; // [rsp+34h] [rbp-64h] BYREF
  __int128 v20; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v21[22]; // [rsp+48h] [rbp-50h]

  *a4 = 0;
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
          v13 = *(unsigned __int16 *)((char *)v11 + v12);
          v14 = *v11 - v13;
          if ( v14 )
            break;
          ++v11;
        }
        while ( v13 );
        if ( !v14 )
        {
          v19 = 1;
          return Microsoft::WRL::Details::GetCacheEntry(
                   this,
                   (struct Microsoft::WRL::Details::ModuleBase *)&v19,
                   &GUID_00000035_0000_0000_c000_000000000046.Data1,
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
0x180016e20  mov     [rsp+arg_8], rbx
0x180016e25  push    rbp
0x180016e26  push    rsi
0x180016e27  push    rdi
0x180016e28  push    r14
0x180016e2a  push    r15
0x180016e2c  sub     rsp, 70h
0x180016e30  mov     rax, cs:__security_cookie
0x180016e37  xor     rax, rsp
0x180016e3a  mov     [rsp+98h+var_38], rax
0x180016e3f  mov     r14, r9
0x180016e42  mov     rdi, r8
0x180016e45  mov     rsi, rcx
0x180016e48  mov     qword ptr [r9], 0
0x180016e4f  mov     [rsp+98h+hasEmbedNull], 0
0x180016e57  mov     rcx, r8; string
0x180016e5a  call    cs:__imp_WindowsIsStringEmpty
0x180016e60  test    eax, eax
0x180016e62  jnz     loc_180016F30
0x180016e68  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180016e6d  mov     rcx, rdi; string
0x180016e70  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180016e76  test    eax, eax
0x180016e78  js      loc_180016F30
0x180016e7e  cmp     [rsp+98h+hasEmbedNull], 1
0x180016e83  jz      loc_180016F30
0x180016e89  xor     edx, edx; length
0x180016e8b  mov     rcx, rdi; string
0x180016e8e  call    cs:__imp_WindowsGetStringRawBuffer
0x180016e94  mov     r15, rax
0x180016e97  mov     rcx, [rsi]
0x180016e9a  mov     rax, [rcx+28h]
0x180016e9e  mov     rcx, rsi
0x180016ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ea6  lea     rbx, [rax+8]
0x180016eaa  mov     rcx, [rsi]
0x180016ead  mov     rax, [rcx+30h]
0x180016eb1  mov     rcx, rsi
0x180016eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016eb9  mov     rbp, rax
0x180016ebc  cmp     rbx, rbp
0x180016ebf  jnb     short loc_180016F1E
0x180016ec1  mov     rax, [rbx]
0x180016ec4  test    rax, rax
0x180016ec7  jz      short loc_180016EF2
0x180016ec9  mov     rax, [rax+8]
0x180016ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ed2  mov     rcx, r15
0x180016ed5  sub     rax, r15
0x180016ed8  movzx   edx, word ptr [rcx]
0x180016edb  movzx   r8d, word ptr [rcx+rax]
0x180016ee0  sub     edx, r8d
0x180016ee3  jnz     short loc_180016EEE
0x180016ee5  add     rcx, 2
0x180016ee9  test    r8d, r8d
0x180016eec  jnz     short loc_180016ED8
0x180016eee  test    edx, edx
0x180016ef0  jz      short loc_180016EF8
0x180016ef2  add     rbx, 8
0x180016ef6  jmp     short loc_180016EBC
0x180016ef8  mov     [rsp+98h+var_64], 1
0x180016f00  mov     [rsp+98h+Ptr], r14; Ptr
0x180016f05  mov     r9, [rbx]; struct _GUID *
0x180016f08  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180016f0f  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180016f14  mov     rcx, rsi; this
0x180016f17  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180016f1c  jmp     short loc_180016F6F
0x180016f1e  mov     rdx, rdi
0x180016f21  mov     ebx, 80040111h
0x180016f26  mov     ecx, ebx
0x180016f28  call    cs:__imp_RoOriginateError
0x180016f2e  jmp     short loc_180016F6D
0x180016f30  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180016f37  movups  [rsp+98h+var_60], xmm0
0x180016f3c  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180016f43  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180016f48  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180016f50  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180016f56  lea     r8, [rsp+98h+var_60]
0x180016f5b  mov     edx, 12h
0x180016f60  mov     ebx, 80070057h
0x180016f65  mov     ecx, ebx
0x180016f67  call    cs:__imp_RoOriginateErrorW
0x180016f6d  mov     eax, ebx
0x180016f6f  mov     rcx, [rsp+98h+var_38]
0x180016f74  xor     rcx, rsp; StackCookie
0x180016f77  call    __security_check_cookie
0x180016f7c  mov     rbx, [rsp+98h+arg_8]
0x180016f84  add     rsp, 70h
0x180016f88  pop     r15
0x180016f8a  pop     r14
0x180016f8c  pop     rdi
0x180016f8d  pop     rsi
0x180016f8e  pop     rbp
0x180016f8f  retn
```
