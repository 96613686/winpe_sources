# NetrWkstaSetInfo

- ea: `0x18002ce00`
- end: `0x18002cff7`
- name: `NetrWkstaSetInfo`
- size: `503`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callees

- `0x18000a240`
- `0x18000e140`
- `0x18002ce00`
- `0x18002d1e8`
- `0x18002d4f8`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002cf00`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002cf00`
- `ntdll!RtlReleaseResource` at `0x18002cfad`
- `ntdll!RtlReleaseResource` at `0x18002cfad`

## string_xrefs

- `0x18002ce89`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWkstaSetInfo(__int64 a1, __int64 a2, _DWORD **a3, _DWORD *a4)
{
  bool v4; // zf
  unsigned int v7; // ebp
  __int128 v9; // xmm6
  __int128 v10; // xmm7
  __int128 v11; // xmm8
  __int128 v12; // xmm9
  __int128 v13; // xmm10
  __int128 v14; // xmm11
  __int128 v15; // xmm12
  __int128 v16; // xmm13
  unsigned int updated; // edi
  __int128 v18; // [rsp+B0h] [rbp-C8h]
  unsigned int v19; // [rsp+190h] [rbp+18h] BYREF

  v4 = *a3 == 0;
  v7 = a2;
  v19 = 0;
  if ( v4 )
  {
    if ( a4 )
      *a4 = -1;
    return 87;
  }
  else
  {
    v9 = *(__int128 *)((char *)&xmmword_180051FF0 + 12);
    v10 = xmmword_180051F80;
    v11 = xmmword_180051F90;
    v12 = xmmword_180051FA0;
    v13 = xmmword_180051FB0;
    v14 = xmmword_180051FC0;
    v15 = xmmword_180051FD0;
    v16 = xmmword_180051FE0;
    v18 = xmmword_180051FF0;
    HIDWORD(v18) = HIDWORD(xmmword_180051FF0);
    if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    {
      return 5;
    }
    else if ( RtlAcquireResourceExclusive(&WsInfo, 1u) )
    {
      updated = WsValidateAndSetWksta(v7, *a3, a4, &v19);
      if ( updated || (updated = WsUpdateRedirToMatchWksta(v19, a4)) != 0 )
      {
        xmmword_180051FF0 = v18;
        *(__int128 *)((char *)&xmmword_180051FF0 + 12) = v9;
        xmmword_180051F80 = v10;
        xmmword_180051F90 = v11;
        xmmword_180051FA0 = v12;
        xmmword_180051FB0 = v13;
        xmmword_180051FC0 = v14;
        xmmword_180051FD0 = v15;
        xmmword_180051FE0 = v16;
      }
      else
      {
        WsUpdateRegistryToMatchWksta(v7, *a3, (__int64)a4);
      }
      RtlReleaseResource(&WsInfo);
      return updated;
    }
    else
    {
      return 2140;
    }
  }
}

```

## disassembly

```asm
0x18002ce00  mov     rax, rsp
0x18002ce03  push    rbx
0x18002ce04  push    rbp
0x18002ce05  push    rsi
0x18002ce06  push    rdi
0x18002ce07  sub     rsp, 158h
0x18002ce0e  cmp     qword ptr [r8], 0
0x18002ce12  mov     rbx, r9
0x18002ce15  movaps  xmmword ptr [rax-38h], xmm6
0x18002ce19  mov     rsi, r8
0x18002ce1c  movaps  xmmword ptr [rax-48h], xmm7
0x18002ce20  mov     ebp, edx
0x18002ce22  movaps  xmmword ptr [rax-58h], xmm8
0x18002ce27  movaps  xmmword ptr [rax-68h], xmm9
0x18002ce2c  movaps  xmmword ptr [rax-78h], xmm10
0x18002ce31  movaps  xmmword ptr [rax-88h], xmm11
0x18002ce39  movaps  xmmword ptr [rax-98h], xmm12
0x18002ce41  movaps  xmmword ptr [rax-0A8h], xmm13
0x18002ce49  mov     dword ptr [rax+18h], 0
0x18002ce50  jnz     short loc_18002CE68
0x18002ce52  test    rbx, rbx
0x18002ce55  jz      short loc_18002CE5E
0x18002ce57  mov     dword ptr [r9], 0FFFFFFFFh
0x18002ce5e  mov     eax, 57h ; 'W'
0x18002ce63  jmp     loc_18002CFBB
0x18002ce68  movups  xmm0, cs:xmmword_180051FF0
0x18002ce6f  mov     rax, cs:ConfigurationInfoSd
0x18002ce76  lea     rcx, WsConfigInfoMapping
0x18002ce7d  movups  xmm6, cs:xmmword_180051FF0+0Ch
0x18002ce84  mov     [rsp+178h+var_148], rcx
0x18002ce89  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x18002ce90  movups  xmm7, cs:xmmword_180051F80
0x18002ce97  mov     [rsp+178h+var_150], 8
0x18002ce9f  movups  xmm8, cs:xmmword_180051F90
0x18002cea7  mov     [rsp+178h+var_158], rax
0x18002ceac  movups  xmm9, cs:xmmword_180051FA0
0x18002ceb4  movups  xmm10, cs:xmmword_180051FB0
0x18002cebc  movups  xmm11, cs:xmmword_180051FC0
0x18002cec4  movups  xmm12, cs:xmmword_180051FD0
0x18002cecc  movups  xmm13, cs:xmmword_180051FE0
0x18002ced4  movups  [rsp+178h+var_C8], xmm0
0x18002cedc  movups  [rsp+178h+var_C8+0Ch], xmm6
0x18002cee4  call    NetpAccessCheckAndAuditEx
0x18002cee9  test    eax, eax
0x18002ceeb  jz      short loc_18002CEF7
0x18002ceed  mov     eax, 5
0x18002cef2  jmp     loc_18002CFBB
0x18002cef7  mov     dl, 1; Wait
0x18002cef9  lea     rcx, WsInfo; Resource
0x18002cf00  call    cs:__imp_RtlAcquireResourceExclusive
0x18002cf07  nop     dword ptr [rax+rax+00h]
0x18002cf0c  test    al, al
0x18002cf0e  jnz     short loc_18002CF1A
0x18002cf10  mov     eax, 85Ch
0x18002cf15  jmp     loc_18002CFBB
0x18002cf1a  mov     rdx, [rsi]
0x18002cf1d  lea     r9, [rsp+178h+arg_10]
0x18002cf25  mov     r8, rbx
0x18002cf28  mov     ecx, ebp
0x18002cf2a  call    WsValidateAndSetWksta
0x18002cf2f  mov     edi, eax
0x18002cf31  test    eax, eax
0x18002cf33  jnz     short loc_18002CF59
0x18002cf35  mov     ecx, [rsp+178h+arg_10]
0x18002cf3c  mov     rdx, rbx
0x18002cf3f  call    WsUpdateRedirToMatchWksta
0x18002cf44  mov     edi, eax
0x18002cf46  test    eax, eax
0x18002cf48  jnz     short loc_18002CF59
0x18002cf4a  mov     rdx, [rsi]
0x18002cf4d  mov     r8, rbx
0x18002cf50  mov     ecx, ebp
0x18002cf52  call    WsUpdateRegistryToMatchWksta
0x18002cf57  jmp     short loc_18002CFA6
0x18002cf59  movaps  xmm0, [rsp+178h+var_C8]
0x18002cf61  movups  cs:xmmword_180051FF0, xmm0
0x18002cf68  movups  cs:xmmword_180051FF0+0Ch, xmm6
0x18002cf6f  movups  cs:xmmword_180051F80, xmm7
0x18002cf76  movups  cs:xmmword_180051F90, xmm8
0x18002cf7e  movups  cs:xmmword_180051FA0, xmm9
0x18002cf86  movups  cs:xmmword_180051FB0, xmm10
0x18002cf8e  movups  cs:xmmword_180051FC0, xmm11
0x18002cf96  movups  cs:xmmword_180051FD0, xmm12
0x18002cf9e  movups  cs:xmmword_180051FE0, xmm13
0x18002cfa6  lea     rcx, WsInfo; Resource
0x18002cfad  call    cs:__imp_RtlReleaseResource
0x18002cfb4  nop     dword ptr [rax+rax+00h]
0x18002cfb9  mov     eax, edi
0x18002cfbb  lea     r11, [rsp+178h+var_20]
0x18002cfc3  movaps  xmm6, xmmword ptr [r11-18h]
0x18002cfc8  movaps  xmm7, xmmword ptr [r11-28h]
0x18002cfcd  movaps  xmm8, xmmword ptr [r11-38h]
0x18002cfd2  movaps  xmm9, xmmword ptr [r11-48h]
0x18002cfd7  movaps  xmm10, xmmword ptr [r11-58h]
0x18002cfdc  movaps  xmm11, xmmword ptr [r11-68h]
0x18002cfe1  movaps  xmm12, xmmword ptr [r11-78h]
0x18002cfe6  movaps  xmm13, xmmword ptr [r11-88h]
0x18002cfee  mov     rsp, r11
0x18002cff1  pop     rdi
0x18002cff2  pop     rsi
0x18002cff3  pop     rbp
0x18002cff4  pop     rbx
0x18002cff5  retn
```
