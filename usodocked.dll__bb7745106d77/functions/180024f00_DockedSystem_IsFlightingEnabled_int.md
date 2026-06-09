# DockedSystem::IsFlightingEnabled(int *)

- ea: `0x180024f00`
- end: `0x180025085`
- name: `?IsFlightingEnabled@DockedSystem@@UEAAJPEAH@Z`
- size: `389`
- prototype: `__int64 __fastcall(DockedSystem *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007660`
- `0x1800183f4`
- `0x1800209fc`
- `0x180024f00`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024f81`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024f81`

## string_xrefs

- `0x180025049`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180024f36`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x18002505e`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180025072`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DockedSystem::IsFlightingEnabled(DockedSystem *this, int *a2)
{
  __int64 result; // rax
  int v4; // ebx
  HRESULT v5; // eax
  int v6; // eax
  int v7; // eax
  const char *v8; // r9
  int ppv; // [rsp+20h] [rbp-38h]
  int ppva; // [rsp+20h] [rbp-38h]
  __int16 v11; // [rsp+34h] [rbp-24h] BYREF
  int v12; // [rsp+38h] [rbp-20h] BYREF
  int v13; // [rsp+3Ch] [rbp-1Ch] BYREF
  LPVOID v14; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a2 )
  {
    v14 = 0;
    v4 = 1;
    v5 = CoCreateInstance(
           &GUID_3185a766_b338_11e4_a71e_12e3f512a338,
           0,
           1u,
           &GUID_e833feb2_c58a_45e4_8d93_08874744febb,
           &v14);
    try
    {
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v5,
          ppva);
      v12 = 0;
      v13 = 4;
      v6 = (*(__int64 (__fastcall **)(LPVOID, int *, int *))(*(_QWORD *)v14 + 96LL))(v14, &v12, &v13);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF2,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
          (const char *)(unsigned int)v6,
          ppva);
      v11 = 0;
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)v14 + 24LL))(v14, &v11);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
          (const char *)(unsigned int)v7,
          ppva);
      if ( (unsigned int)(v12 - 1) > 1 || v13 || v11 != -1 )
        v4 = 0;
      *a2 = v4;
      if ( v14 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0xFB,
                             (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\"
                                           "dll\\dockedsystem.cpp",
                             v8);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
      (const char *)0x80004003LL,
      ppv);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180024f00  mov     [rsp+arg_0], rbx
0x180024f05  push    rdi
0x180024f06  sub     rsp, 50h
0x180024f0a  mov     rax, cs:__security_cookie
0x180024f11  xor     rax, rsp
0x180024f14  mov     [rsp+58h+var_10], rax
0x180024f19  mov     rdi, rdx
0x180024f1c  mov     [rsp+58h+var_28], 0
0x180024f24  test    rdx, rdx
0x180024f27  jnz     short loc_180024F4E
0x180024f29  mov     rcx, [rsp+58h]; this
0x180024f2e  mov     ebx, 80004003h
0x180024f33  mov     r9d, ebx; char *
0x180024f36  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024f3d  mov     edx, 0ECh; void *
0x180024f42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024f47  mov     eax, ebx
0x180024f49  jmp     loc_18002502E
0x180024f4e  mov     [rsp+58h+var_28], 2
0x180024f56  mov     [rsp+58h+var_18], 0
0x180024f5f  lea     rax, [rsp+58h+var_18]
0x180024f64  mov     qword ptr [rsp+58h+ppv], rax; int
0x180024f69  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x180024f70  mov     ebx, 1
0x180024f75  mov     r8d, ebx; dwClsContext
0x180024f78  xor     edx, edx; pUnkOuter
0x180024f7a  lea     rcx, _GUID_3185a766_b338_11e4_a71e_12e3f512a338; rclsid
0x180024f81  call    cs:__imp_CoCreateInstance
0x180024f87  mov     rcx, [rsp+58h]; this
0x180024f8c  test    eax, eax
0x180024f8e  js      loc_180025046
0x180024f94  mov     [rsp+58h+var_20], 0
0x180024f9c  mov     [rsp+58h+var_1C], 4
0x180024fa4  mov     rcx, [rsp+58h+var_18]
0x180024fa9  mov     rax, [rcx]
0x180024fac  lea     r8, [rsp+58h+var_1C]
0x180024fb1  lea     rdx, [rsp+58h+var_20]
0x180024fb6  mov     rax, [rax+60h]
0x180024fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fbf  mov     rcx, [rsp+58h]; this
0x180024fc4  test    eax, eax
0x180024fc6  js      loc_18002505B
0x180024fcc  xor     eax, eax
0x180024fce  mov     [rsp+58h+var_24], ax
0x180024fd3  mov     rcx, [rsp+58h+var_18]
0x180024fd8  mov     rax, [rcx]
0x180024fdb  lea     rdx, [rsp+58h+var_24]
0x180024fe0  mov     rax, [rax+18h]
0x180024fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fe9  mov     rcx, [rsp+58h]; this
0x180024fee  test    eax, eax
0x180024ff0  js      short loc_18002506F
0x180024ff2  mov     eax, [rsp+58h+var_20]
0x180024ff6  dec     eax
0x180024ff8  cmp     eax, ebx
0x180024ffa  ja      short loc_18002500B
0x180024ffc  cmp     [rsp+58h+var_1C], 0
0x180025001  jnz     short loc_18002500B
0x180025003  cmp     [rsp+58h+var_24], 0FFFFh
0x180025009  jz      short loc_18002500D
0x18002500b  xor     ebx, ebx
0x18002500d  mov     [rdi], ebx
0x18002500f  mov     rcx, [rsp+58h+var_18]
0x180025014  test    rcx, rcx
0x180025017  jz      short loc_180025026
0x180025019  mov     rax, [rcx]
0x18002501c  mov     rax, [rax+10h]
0x180025020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025025  nop
0x180025026  xor     eax, eax
0x180025028  jmp     short loc_18002502E
0x18002502a  mov     eax, [rsp+58h+var_28]
0x18002502e  mov     rcx, [rsp+58h+var_10]
0x180025033  xor     rcx, rsp; StackCookie
0x180025036  call    __security_check_cookie
0x18002503b  mov     rbx, [rsp+58h+arg_0]
0x180025040  add     rsp, 50h
0x180025044  pop     rdi
0x180025045  retn
0x180025046  mov     r9d, eax; char *
0x180025049  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180025050  mov     edx, 1CBEh; void *
0x180025055  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002505b  mov     r9d, eax; char *
0x18002505e  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180025065  mov     edx, 0F2h; void *
0x18002506a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002506f  mov     r9d, eax; char *
0x180025072  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180025079  mov     edx, 0F5h; void *
0x18002507e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
