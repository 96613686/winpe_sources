# LogAdapter::WdsLogger::InternalWriteLog(LogAdapter::LogLevel,char const *)

- ea: `0x180005540`
- end: `0x18000569a`
- name: `?InternalWriteLog@WdsLogger@LogAdapter@@UEAAJW4LogLevel@2@PEBD@Z`
- size: `346`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x1800054f0`
- `0x180005540`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800055ac`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800055ac`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18000558f`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18000558f`

## string_xrefs

- `0x180005586`: `wdscore.dll`

## pseudocode

```c
__int64 __fastcall LogAdapter::WdsLogger::InternalWriteLog(__int64 a1, int a2, __int64 a3)
{
  HMODULE *v6; // rsi
  HMODULE v7; // rcx
  void (__fastcall *v8)(_QWORD *, __int64, const char *, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD); // r10
  int v9; // ebx
  __int64 v10; // rdx
  _QWORD v12[2]; // [rsp+60h] [rbp-48h] BYREF
  __int128 v13; // [rsp+70h] [rbp-38h]

  if ( !*(_BYTE *)(a1 + 4224) )
  {
    v6 = (HMODULE *)(a1 + 4208);
    if ( *(_QWORD *)(a1 + 4208) )
      INTERNAL_ERROR_ACTION(-1073741595);
    if ( GetModuleHandleExW(0, L"wdscore.dll", (HMODULE *)(a1 + 4208)) )
      v7 = *v6;
    else
      v7 = &_ImageBase;
    *(_QWORD *)(a1 + 4216) = GetProcAddress(v7, "WdsSetupLogMessageA");
    *(_BYTE *)(a1 + 4224) = 1;
  }
  v8 = *(void (__fastcall **)(_QWORD *, __int64, const char *, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))(a1 + 4216);
  if ( v8 )
  {
    v12[0] = 0x4000000;
    v13 = 0;
    if ( a2 )
    {
      v9 = a2 - 2;
      if ( v9 )
      {
        if ( v9 == 1 )
          LODWORD(v12[0]) = 0x2000000;
      }
      else
      {
        LODWORD(v12[0]) = 50331648;
      }
    }
    else
    {
      LODWORD(v12[0]) = 1728053248;
    }
    v10 = *(unsigned int *)(a1 + 4228);
    v12[1] = a3;
    v8(v12, v10, "D", 0, 0, 0, 0, 0, 0, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180005540  mov     [rsp+arg_8], rbx
0x180005545  push    rbp
0x180005546  push    rsi
0x180005547  push    rdi
0x180005548  sub     rsp, 90h
0x18000554f  mov     rax, cs:__security_cookie
0x180005556  xor     rax, rsp
0x180005559  mov     [rsp+0A8h+var_28], rax
0x180005561  cmp     byte ptr [rcx+1080h], 0
0x180005568  mov     rbp, r8
0x18000556b  mov     ebx, edx
0x18000556d  mov     rdi, rcx
0x180005570  jnz     short loc_1800055C0
0x180005572  lea     rsi, [rcx+1070h]
0x180005579  cmp     qword ptr [rsi], 0
0x18000557d  jnz     loc_18000568F
0x180005583  mov     r8, rsi; phModule
0x180005586  lea     rdx, ModuleName; "wdscore.dll"
0x18000558d  xor     ecx, ecx; dwFlags
0x18000558f  call    cs:__imp_GetModuleHandleExW
0x180005595  test    eax, eax
0x180005597  jz      short loc_18000559E
0x180005599  mov     rcx, [rsi]
0x18000559c  jmp     short loc_1800055A5
0x18000559e  lea     rcx, __ImageBase; hModule
0x1800055a5  lea     rdx, ProcName; "WdsSetupLogMessageA"
0x1800055ac  call    cs:__imp_GetProcAddress
0x1800055b2  mov     [rdi+1078h], rax
0x1800055b9  mov     byte ptr [rdi+1080h], 1
0x1800055c0  mov     r10, [rdi+1078h]
0x1800055c7  test    r10, r10
0x1800055ca  jz      loc_18000566A
0x1800055d0  mov     [rsp+0A8h+var_48], 4000000h
0x1800055d9  xorps   xmm0, xmm0
0x1800055dc  movdqu  [rsp+0A8h+var_38], xmm0
0x1800055e2  test    ebx, ebx
0x1800055e4  jz      short loc_180005604
0x1800055e6  sub     ebx, 2
0x1800055e9  jz      short loc_1800055FA
0x1800055eb  cmp     ebx, 1
0x1800055ee  jnz     short loc_18000560C
0x1800055f0  mov     dword ptr [rsp+0A8h+var_48], 2000000h
0x1800055f8  jmp     short loc_18000560C
0x1800055fa  mov     dword ptr [rsp+0A8h+var_48], 3000000h
0x180005602  jmp     short loc_18000560C
0x180005604  mov     dword ptr [rsp+0A8h+var_48], 67000000h
0x18000560c  mov     edx, [rdi+1084h]
0x180005612  lea     r8, aD_0; "D"
0x180005619  mov     [rsp+0A8h+var_58], 0
0x180005621  lea     rcx, [rsp+0A8h+var_48]
0x180005626  mov     [rsp+0A8h+var_60], 0
0x18000562f  xor     r9d, r9d
0x180005632  mov     [rsp+0A8h+var_68], 0
0x18000563a  mov     rax, r10
0x18000563d  mov     [rsp+0A8h+var_70], 0
0x180005646  mov     [rsp+0A8h+var_78], 0
0x18000564f  mov     [rsp+0A8h+var_80], 0
0x180005658  mov     [rsp+0A8h+var_88], 0
0x180005660  mov     [rsp+0A8h+var_40], rbp
0x180005665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000566a  xor     eax, eax
0x18000566c  mov     rcx, [rsp+0A8h+var_28]
0x180005674  xor     rcx, rsp; StackCookie
0x180005677  call    __security_check_cookie
0x18000567c  mov     rbx, [rsp+0A8h+arg_8]
0x180005684  add     rsp, 90h
0x18000568b  pop     rdi
0x18000568c  pop     rsi
0x18000568d  pop     rbp
0x18000568e  retn
0x18000568f  mov     ecx, 0C00000E5h; int
0x180005694  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
