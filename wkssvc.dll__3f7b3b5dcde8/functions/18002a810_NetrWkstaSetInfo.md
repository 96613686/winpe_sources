# NetrWkstaSetInfo

- ea: `0x18002a810`
- end: `0x18002a9fa`
- name: `NetrWkstaSetInfo`
- size: `490`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int **, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callees

- `0x180009a40`
- `0x18000d500`
- `0x18002a810`
- `0x18002abe4`
- `0x18002aee4`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002a910`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002a910`
- `ntdll!RtlReleaseResource` at `0x18002a9b7`
- `ntdll!RtlReleaseResource` at `0x18002a9b7`

## string_xrefs

- `0x18002a899`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWkstaSetInfo(__int64 a1, __int64 a2, unsigned int **a3, _DWORD *a4)
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
    v9 = *(__int128 *)((char *)&xmmword_18004EFF0 + 12);
    v10 = xmmword_18004EF80;
    v11 = xmmword_18004EF90;
    v12 = xmmword_18004EFA0;
    v13 = xmmword_18004EFB0;
    v14 = xmmword_18004EFC0;
    v15 = xmmword_18004EFD0;
    v16 = xmmword_18004EFE0;
    v18 = xmmword_18004EFF0;
    HIDWORD(v18) = HIDWORD(xmmword_18004EFF0);
    if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    {
      return 5;
    }
    else if ( RtlAcquireResourceExclusive(&WsInfo, 1u) )
    {
      updated = WsValidateAndSetWksta(v7, *a3, a4, &v19);
      if ( updated || (updated = WsUpdateRedirToMatchWksta(v19, a4)) != 0 )
      {
        xmmword_18004EFF0 = v18;
        *(__int128 *)((char *)&xmmword_18004EFF0 + 12) = v9;
        xmmword_18004EF80 = v10;
        xmmword_18004EF90 = v11;
        xmmword_18004EFA0 = v12;
        xmmword_18004EFB0 = v13;
        xmmword_18004EFC0 = v14;
        xmmword_18004EFD0 = v15;
        xmmword_18004EFE0 = v16;
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
0x18002a810  mov     rax, rsp
0x18002a813  push    rbx
0x18002a814  push    rbp
0x18002a815  push    rsi
0x18002a816  push    rdi
0x18002a817  sub     rsp, 158h
0x18002a81e  cmp     qword ptr [r8], 0
0x18002a822  mov     rbx, r9
0x18002a825  movaps  xmmword ptr [rax-38h], xmm6
0x18002a829  mov     rsi, r8
0x18002a82c  movaps  xmmword ptr [rax-48h], xmm7
0x18002a830  mov     ebp, edx
0x18002a832  movaps  xmmword ptr [rax-58h], xmm8
0x18002a837  movaps  xmmword ptr [rax-68h], xmm9
0x18002a83c  movaps  xmmword ptr [rax-78h], xmm10
0x18002a841  movaps  xmmword ptr [rax-88h], xmm11
0x18002a849  movaps  xmmword ptr [rax-98h], xmm12
0x18002a851  movaps  xmmword ptr [rax-0A8h], xmm13
0x18002a859  mov     dword ptr [rax+18h], 0
0x18002a860  jnz     short loc_18002A878
0x18002a862  test    rbx, rbx
0x18002a865  jz      short loc_18002A86E
0x18002a867  mov     dword ptr [r9], 0FFFFFFFFh
0x18002a86e  mov     eax, 57h ; 'W'
0x18002a873  jmp     loc_18002A9BF
0x18002a878  movups  xmm0, cs:xmmword_18004EFF0
0x18002a87f  mov     rax, cs:ConfigurationInfoSd
0x18002a886  lea     rcx, WsConfigInfoMapping
0x18002a88d  movups  xmm6, cs:xmmword_18004EFF0+0Ch
0x18002a894  mov     [rsp+178h+var_148], rcx
0x18002a899  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x18002a8a0  movups  xmm7, cs:xmmword_18004EF80
0x18002a8a7  mov     [rsp+178h+var_150], 8
0x18002a8af  movups  xmm8, cs:xmmword_18004EF90
0x18002a8b7  mov     [rsp+178h+var_158], rax
0x18002a8bc  movups  xmm9, cs:xmmword_18004EFA0
0x18002a8c4  movups  xmm10, cs:xmmword_18004EFB0
0x18002a8cc  movups  xmm11, cs:xmmword_18004EFC0
0x18002a8d4  movups  xmm12, cs:xmmword_18004EFD0
0x18002a8dc  movups  xmm13, cs:xmmword_18004EFE0
0x18002a8e4  movups  [rsp+178h+var_C8], xmm0
0x18002a8ec  movups  [rsp+178h+var_C8+0Ch], xmm6
0x18002a8f4  call    NetpAccessCheckAndAuditEx
0x18002a8f9  test    eax, eax
0x18002a8fb  jz      short loc_18002A907
0x18002a8fd  mov     eax, 5
0x18002a902  jmp     loc_18002A9BF
0x18002a907  mov     dl, 1; Wait
0x18002a909  lea     rcx, WsInfo; Resource
0x18002a910  call    cs:__imp_RtlAcquireResourceExclusive
0x18002a916  test    al, al
0x18002a918  jnz     short loc_18002A924
0x18002a91a  mov     eax, 85Ch
0x18002a91f  jmp     loc_18002A9BF
0x18002a924  mov     rdx, [rsi]
0x18002a927  lea     r9, [rsp+178h+arg_10]
0x18002a92f  mov     r8, rbx
0x18002a932  mov     ecx, ebp
0x18002a934  call    WsValidateAndSetWksta
0x18002a939  mov     edi, eax
0x18002a93b  test    eax, eax
0x18002a93d  jnz     short loc_18002A963
0x18002a93f  mov     ecx, [rsp+178h+arg_10]
0x18002a946  mov     rdx, rbx
0x18002a949  call    WsUpdateRedirToMatchWksta
0x18002a94e  mov     edi, eax
0x18002a950  test    eax, eax
0x18002a952  jnz     short loc_18002A963
0x18002a954  mov     rdx, [rsi]
0x18002a957  mov     r8, rbx
0x18002a95a  mov     ecx, ebp
0x18002a95c  call    WsUpdateRegistryToMatchWksta
0x18002a961  jmp     short loc_18002A9B0
0x18002a963  movaps  xmm0, [rsp+178h+var_C8]
0x18002a96b  movups  cs:xmmword_18004EFF0, xmm0
0x18002a972  movups  cs:xmmword_18004EFF0+0Ch, xmm6
0x18002a979  movups  cs:xmmword_18004EF80, xmm7
0x18002a980  movups  cs:xmmword_18004EF90, xmm8
0x18002a988  movups  cs:xmmword_18004EFA0, xmm9
0x18002a990  movups  cs:xmmword_18004EFB0, xmm10
0x18002a998  movups  cs:xmmword_18004EFC0, xmm11
0x18002a9a0  movups  cs:xmmword_18004EFD0, xmm12
0x18002a9a8  movups  cs:xmmword_18004EFE0, xmm13
0x18002a9b0  lea     rcx, WsInfo; Resource
0x18002a9b7  call    cs:__imp_RtlReleaseResource
0x18002a9bd  mov     eax, edi
0x18002a9bf  lea     r11, [rsp+178h+var_20]
0x18002a9c7  movaps  xmm6, xmmword ptr [r11-18h]
0x18002a9cc  movaps  xmm7, xmmword ptr [r11-28h]
0x18002a9d1  movaps  xmm8, xmmword ptr [r11-38h]
0x18002a9d6  movaps  xmm9, xmmword ptr [r11-48h]
0x18002a9db  movaps  xmm10, xmmword ptr [r11-58h]
0x18002a9e0  movaps  xmm11, xmmword ptr [r11-68h]
0x18002a9e5  movaps  xmm12, xmmword ptr [r11-78h]
0x18002a9ea  movaps  xmm13, xmmword ptr [r11-88h]
0x18002a9f2  mov     rsp, r11
0x18002a9f5  pop     rdi
0x18002a9f6  pop     rsi
0x18002a9f7  pop     rbp
0x18002a9f8  pop     rbx
0x18002a9f9  retn
```
