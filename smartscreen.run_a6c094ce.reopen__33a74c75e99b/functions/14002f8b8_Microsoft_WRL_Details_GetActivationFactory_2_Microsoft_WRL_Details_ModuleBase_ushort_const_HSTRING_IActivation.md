# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x14002f8b8`
- end: `0x14002fa40`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002f8a0`

## callees

- `0x140026c20`
- `0x14002f8b8`
- `0x14002fea4`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x14002f90e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x14002f90e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14002f932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14002f932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x14002f8f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x14002f8f2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14002f9cb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x14002f9cb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x14002fa10`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x14002fa10`

## string_xrefs

- `0x14002f9d9`: `activatibleClassId`

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
0x14002f8b8  mov     [rsp+arg_8], rbx
0x14002f8bd  push    rbp
0x14002f8be  push    rsi
0x14002f8bf  push    rdi
0x14002f8c0  push    r14
0x14002f8c2  push    r15
0x14002f8c4  sub     rsp, 70h
0x14002f8c8  mov     rax, cs:__security_cookie
0x14002f8cf  xor     rax, rsp
0x14002f8d2  mov     [rsp+98h+var_38], rax
0x14002f8d7  mov     r14, r9
0x14002f8da  mov     rdi, r8
0x14002f8dd  mov     rsi, rcx
0x14002f8e0  mov     qword ptr [r9], 0
0x14002f8e7  mov     [rsp+98h+hasEmbedNull], 0
0x14002f8ef  mov     rcx, r8; string
0x14002f8f2  call    cs:__imp_WindowsIsStringEmpty
0x14002f8f9  nop     dword ptr [rax+rax+00h]
0x14002f8fe  test    eax, eax
0x14002f900  jnz     loc_14002F9D9
0x14002f906  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x14002f90b  mov     rcx, rdi; string
0x14002f90e  call    cs:__imp_WindowsStringHasEmbeddedNull
0x14002f915  nop     dword ptr [rax+rax+00h]
0x14002f91a  test    eax, eax
0x14002f91c  js      loc_14002F9D9
0x14002f922  cmp     [rsp+98h+hasEmbedNull], 1
0x14002f927  jz      loc_14002F9D9
0x14002f92d  xor     edx, edx; length
0x14002f92f  mov     rcx, rdi; string
0x14002f932  call    cs:__imp_WindowsGetStringRawBuffer
0x14002f939  nop     dword ptr [rax+rax+00h]
0x14002f93e  mov     r15, rax
0x14002f941  mov     rcx, [rsi]
0x14002f944  mov     rax, [rcx+28h]
0x14002f948  mov     rcx, rsi
0x14002f94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f950  lea     rbx, [rax+8]
0x14002f954  mov     rcx, [rsi]
0x14002f957  mov     rax, [rcx+30h]
0x14002f95b  mov     rcx, rsi
0x14002f95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f963  mov     rbp, rax
0x14002f966  cmp     rbx, rbp
0x14002f969  jnb     short loc_14002F9C1
0x14002f96b  mov     rax, [rbx]
0x14002f96e  test    rax, rax
0x14002f971  jz      short loc_14002F99C
0x14002f973  mov     rax, [rax+8]
0x14002f977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f97c  mov     rcx, r15
0x14002f97f  sub     rax, r15
0x14002f982  movzx   edx, word ptr [rcx]
0x14002f985  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x14002f98a  sub     edx, r8d
0x14002f98d  jnz     short loc_14002F998
0x14002f98f  add     rcx, 2
0x14002f993  test    r8d, r8d
0x14002f996  jnz     short loc_14002F982
0x14002f998  test    edx, edx
0x14002f99a  jz      short loc_14002F9A2
0x14002f99c  add     rbx, 8
0x14002f9a0  jmp     short loc_14002F966
0x14002f9a2  mov     [rsp+98h+var_64], 2
0x14002f9aa  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x14002f9af  mov     r9, [rbx]; struct _GUID *
0x14002f9b2  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x14002f9b7  mov     rcx, rsi; this
0x14002f9ba  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x14002f9bf  jmp     short loc_14002FA1E
0x14002f9c1  mov     rdx, rdi
0x14002f9c4  mov     ebx, 80040111h
0x14002f9c9  mov     ecx, ebx
0x14002f9cb  call    cs:__imp_RoOriginateError
0x14002f9d2  nop     dword ptr [rax+rax+00h]
0x14002f9d7  jmp     short loc_14002FA1C
0x14002f9d9  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x14002f9e0  movups  [rsp+98h+var_60], xmm0
0x14002f9e5  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x14002f9ec  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x14002f9f1  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x14002f9f9  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x14002f9ff  lea     r8, [rsp+98h+var_60]
0x14002fa04  mov     edx, 12h
0x14002fa09  mov     ebx, 80070057h
0x14002fa0e  mov     ecx, ebx
0x14002fa10  call    cs:__imp_RoOriginateErrorW
0x14002fa17  nop     dword ptr [rax+rax+00h]
0x14002fa1c  mov     eax, ebx
0x14002fa1e  mov     rcx, [rsp+98h+var_38]
0x14002fa23  xor     rcx, rsp; StackCookie
0x14002fa26  call    __security_check_cookie
0x14002fa2b  mov     rbx, [rsp+98h+arg_8]
0x14002fa33  add     rsp, 70h
0x14002fa37  pop     r15
0x14002fa39  pop     r14
0x14002fa3b  pop     rdi
0x14002fa3c  pop     rsi
0x14002fa3d  pop     rbp
0x14002fa3e  retn
```
