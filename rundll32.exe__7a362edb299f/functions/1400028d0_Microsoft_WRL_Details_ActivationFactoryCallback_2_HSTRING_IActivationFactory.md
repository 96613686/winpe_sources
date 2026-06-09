# Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)

- ea: `0x1400028d0`
- end: `0x140002a3f`
- name: `??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(HSTRING string, struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400015a0`
- `0x1400028d0`
- `0x140004564`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x140002a16`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x140002a16`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1400029b6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1400029b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x14000290b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x14000290b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x140002921`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x140002921`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000293f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000293f`

## string_xrefs

- `0x1400029df`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ActivationFactoryCallback<2>(
        HSTRING string,
        struct Microsoft::WRL::Details::CreatorMap *a2)
{
  Microsoft::WRL::Details *v2; // rsi
  PCWSTR StringRawBuffer; // r15
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rbp
  __int64 v8; // rax
  unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  unsigned int *v11; // r8
  int v12; // edx
  unsigned int v13; // ebx
  const struct _GUID *v14; // r9
  struct IUnknown **v16; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v18; // [rsp+34h] [rbp-64h] BYREF
  __int128 v19; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v20[22]; // [rsp+48h] [rbp-50h]

  v2 = Microsoft::WRL::Details::ModuleBase::module_;
  *(_QWORD *)a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v13 = -2147024809;
    v19 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v20 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v20[14] = *(_QWORD *)L"sId";
    RoOriginateErrorW(2147942487LL, 18, &v19);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v6 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v2 + 40LL))(v2) + 8;
    v7 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v2 + 48LL))(v2);
    if ( v6 >= v7 )
    {
LABEL_11:
      v13 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *(_QWORD *)v6 )
        {
          v8 = (*(__int64 (**)(void))(*(_QWORD *)v6 + 8LL))();
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
        v6 += 8LL;
        if ( v6 >= v7 )
          goto LABEL_11;
      }
      v14 = *(const struct _GUID **)v6;
      v18 = 2;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             v2,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v18,
                             v11,
                             v14,
                             a2,
                             v16);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x1400028d0  mov     [rsp+arg_10], rbx
0x1400028d5  push    rbp
0x1400028d6  push    rsi
0x1400028d7  push    rdi
0x1400028d8  push    r14
0x1400028da  push    r15
0x1400028dc  sub     rsp, 70h
0x1400028e0  mov     rax, cs:__security_cookie
0x1400028e7  xor     rax, rsp
0x1400028ea  mov     [rsp+98h+var_38], rax
0x1400028ef  mov     rsi, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1400028f6  mov     r14, rdx
0x1400028f9  mov     rdi, rcx
0x1400028fc  mov     qword ptr [rdx], 0
0x140002903  mov     [rsp+98h+hasEmbedNull], 0
0x14000290b  call    cs:__imp_WindowsIsStringEmpty
0x140002911  test    eax, eax
0x140002913  jnz     loc_1400029DF
0x140002919  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x14000291e  mov     rcx, rdi; string
0x140002921  call    cs:__imp_WindowsStringHasEmbeddedNull
0x140002927  test    eax, eax
0x140002929  js      loc_1400029DF
0x14000292f  cmp     [rsp+98h+hasEmbedNull], 1
0x140002934  jz      loc_1400029DF
0x14000293a  xor     edx, edx; length
0x14000293c  mov     rcx, rdi; string
0x14000293f  call    cs:__imp_WindowsGetStringRawBuffer
0x140002945  mov     rcx, [rsi]
0x140002948  mov     r15, rax
0x14000294b  mov     rax, [rcx+28h]
0x14000294f  mov     rcx, rsi
0x140002952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002957  mov     rcx, [rsi]
0x14000295a  lea     rbx, [rax+8]
0x14000295e  mov     rax, [rcx+30h]
0x140002962  mov     rcx, rsi
0x140002965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000296a  mov     rbp, rax
0x14000296d  cmp     rbx, rax
0x140002970  jnb     short loc_1400029AC
0x140002972  mov     rax, [rbx]
0x140002975  test    rax, rax
0x140002978  jz      short loc_1400029A3
0x14000297a  mov     rax, [rax+8]
0x14000297e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002983  mov     rcx, r15
0x140002986  sub     rax, r15
0x140002989  movzx   edx, word ptr [rcx]
0x14000298c  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x140002991  sub     edx, r8d
0x140002994  jnz     short loc_14000299F
0x140002996  add     rcx, 2
0x14000299a  test    r8d, r8d
0x14000299d  jnz     short loc_140002989
0x14000299f  test    edx, edx
0x1400029a1  jz      short loc_1400029BE
0x1400029a3  add     rbx, 8
0x1400029a7  cmp     rbx, rbp
0x1400029aa  jb      short loc_140002972
0x1400029ac  mov     ebx, 80040111h
0x1400029b1  mov     rdx, rdi
0x1400029b4  mov     ecx, ebx
0x1400029b6  call    cs:__imp_RoOriginateError
0x1400029bc  jmp     short loc_140002A1C
0x1400029be  mov     r9, [rbx]; struct _GUID *
0x1400029c1  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x1400029c6  mov     rcx, rsi; this
0x1400029c9  mov     [rsp+98h+var_64], 2
0x1400029d1  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x1400029d6  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x1400029db  mov     ebx, eax
0x1400029dd  jmp     short loc_140002A1C
0x1400029df  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x1400029e6  mov     ebx, 80070057h
0x1400029eb  lea     r8, [rsp+98h+var_60]
0x1400029f0  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x1400029f7  mov     edx, 12h
0x1400029fc  mov     ecx, ebx
0x1400029fe  movups  [rsp+98h+var_60], xmm0
0x140002a03  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x140002a0b  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x140002a10  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x140002a16  call    cs:__imp_RoOriginateErrorW
0x140002a1c  mov     eax, ebx
0x140002a1e  mov     rcx, [rsp+98h+var_38]
0x140002a23  xor     rcx, rsp; StackCookie
0x140002a26  call    __security_check_cookie
0x140002a2b  mov     rbx, [rsp+98h+arg_10]
0x140002a33  add     rsp, 70h
0x140002a37  pop     r15
0x140002a39  pop     r14
0x140002a3b  pop     rdi
0x140002a3c  pop     rsi
0x140002a3d  pop     rbp
0x140002a3e  retn
```
