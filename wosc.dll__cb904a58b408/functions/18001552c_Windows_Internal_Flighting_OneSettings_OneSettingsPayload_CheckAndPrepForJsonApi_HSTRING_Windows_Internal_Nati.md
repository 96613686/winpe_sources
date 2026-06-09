# Windows::Internal::Flighting::OneSettings::OneSettingsPayload::CheckAndPrepForJsonApi(HSTRING__ *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x18001552c`
- end: `0x1800155c3`
- name: `?CheckAndPrepForJsonApi@OneSettingsPayload@OneSettings@Flighting@Internal@Windows@@AEAAJPEAUHSTRING__@@AEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@45@@Z`
- size: `151`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180016b40`
- `0x180016ca0`
- `0x180016e00`
- `0x180016f60`
- `0x1800170c0`
- `0x180017220`

## callees

- `0x18000e5ac`
- `0x18001552c`
- `0x180019c58`
- `0x180019d84`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001556a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001556a`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x1800155b0`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x1800155b0`

## string_xrefs

- `0x180015548`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`
- `0x18001558a`: `onecore\base\flighting\onesettings\libs\configurationsmanager\onesettingspayload.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Flighting::OneSettings::OneSettingsPayload::CheckAndPrepForJsonApi(
        __int64 a1,
        HSTRING a2,
        __int64 a3)
{
  PCWSTR StringRawBuffer; // rax
  int v6; // eax
  unsigned int v7; // edi
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_QWORD *)(a1 + 80) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
           a3,
           StringRawBuffer,
           -1);
    v7 = v6;
    if ( v6 >= 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a3);
      CharUpperBuffW(*(LPWSTR *)a3, *(_DWORD *)(a3 + 8));
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2EB,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
        (const char *)(unsigned int)v6,
        v8);
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E6,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\onesettingspayload.cpp",
      (const char *)0x8007000DLL,
      v8);
    return 2147942413LL;
  }
}

```

## disassembly

```asm
0x18001552c  mov     [rsp+arg_0], rbx
0x180015531  push    rdi; int
0x180015532  sub     rsp, 20h
0x180015536  cmp     qword ptr [rcx+50h], 0
0x18001553b  mov     rbx, r8
0x18001553e  mov     rax, rdx
0x180015541  jnz     short loc_180015565
0x180015543  mov     rcx, [rsp+28h]; this
0x180015548  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\onesettings\\"...
0x18001554f  mov     ebx, 8007000Dh
0x180015554  mov     edx, 2E6h; void *
0x180015559  mov     r9d, ebx; char *
0x18001555c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015561  mov     eax, ebx
0x180015563  jmp     short loc_1800155B8
0x180015565  xor     edx, edx; length
0x180015567  mov     rcx, rax; string
0x18001556a  call    cs:__imp_WindowsGetStringRawBuffer
0x180015570  or      r8, 0FFFFFFFFFFFFFFFFh
0x180015574  mov     rcx, rbx
0x180015577  mov     rdx, rax
0x18001557a  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001557f  mov     edi, eax
0x180015581  test    eax, eax
0x180015583  jns     short loc_1800155A2
0x180015585  mov     rcx, [rsp+28h]; this
0x18001558a  lea     r8, aOnecoreBaseFli_30; "onecore\\base\\flighting\\onesettings\\"...
0x180015591  mov     r9d, eax; char *
0x180015594  mov     edx, 2EBh; void *
0x180015599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001559e  mov     eax, edi
0x1800155a0  jmp     short loc_1800155B8
0x1800155a2  mov     rcx, rbx
0x1800155a5  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800155aa  mov     edx, [rbx+8]; cchLength
0x1800155ad  mov     rcx, [rbx]; lpsz
0x1800155b0  call    cs:__imp_CharUpperBuffW
0x1800155b6  xor     eax, eax
0x1800155b8  mov     rbx, [rsp+28h+arg_0]
0x1800155bd  add     rsp, 20h
0x1800155c1  pop     rdi
0x1800155c2  retn
```
