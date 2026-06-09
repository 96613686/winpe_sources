# GetCipherStrength(void)

- ea: `0x180022728`
- end: `0x18002287c`
- name: `?GetCipherStrength@@YAKXZ`
- size: `340`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022900`

## callees

- `0x180012550`
- `0x180022728`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022852`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022852`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002277e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002277e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180022762`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180022762`

## string_xrefs

- `0x180022751`: `security.dll`
- `0x1800227c9`: `Microsoft Unified Security Protocol Provider`
- `0x180022774`: `InitSecurityInterfaceA`

## pseudocode

```c
__int64 GetCipherStrength(void)
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rdi
  __int64 (*ProcAddress)(void); // rax
  __int64 v3; // rax
  __int64 v4; // rbx
  unsigned int (__fastcall *v5)(_QWORD, const char *, __int64); // rax
  void (__fastcall *v6)(__int128 *); // rax
  _QWORD v8[2]; // [rsp+50h] [rbp-38h] BYREF
  __int128 v9; // [rsp+60h] [rbp-28h] BYREF

  if ( dword_1800593FC == -1 )
  {
    dword_1800593FC = 0;
    LibraryW = LoadLibraryW(L"security.dll");
    v1 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "InitSecurityInterfaceA");
      if ( ProcAddress )
      {
        v3 = ProcAddress();
        v4 = v3;
        if ( v3 )
        {
          v5 = *(unsigned int (__fastcall **)(_QWORD, const char *, __int64))(v3 + 24);
          if ( v5 )
          {
            if ( *(_QWORD *)(v4 + 16) )
            {
              v8[1] = 0;
              v8[0] = 0;
              v9 = 0;
              if ( !v5(0, "Microsoft Unified Security Protocol Provider", 2) )
              {
                if ( !(*(unsigned int (__fastcall **)(__int128 *, __int64, _QWORD *))(v4 + 16))(&v9, 87, v8) )
                  dword_1800593FC = HIDWORD(v8[0]);
                v6 = *(void (__fastcall **)(__int128 *))(v4 + 32);
                if ( v6 )
                  v6(&v9);
              }
            }
          }
        }
      }
      FreeLibrary(v1);
    }
  }
  return (unsigned int)dword_1800593FC;
}

```

## disassembly

```asm
0x180022728  mov     [rsp+arg_0], rbx
0x18002272d  push    rdi
0x18002272e  sub     rsp, 80h
0x180022735  mov     rax, cs:__security_cookie
0x18002273c  xor     rax, rsp
0x18002273f  mov     [rsp+88h+var_18], rax
0x180022744  cmp     cs:dword_1800593FC, 0FFFFFFFFh
0x18002274b  jnz     loc_180022858
0x180022751  lea     rcx, aSecurityDll; "security.dll"
0x180022758  mov     cs:dword_1800593FC, 0
0x180022762  call    cs:__imp_LoadLibraryW
0x180022768  mov     rdi, rax
0x18002276b  test    rax, rax
0x18002276e  jz      loc_180022858
0x180022774  lea     rdx, aInitsecurityin; "InitSecurityInterfaceA"
0x18002277b  mov     rcx, rax; hModule
0x18002277e  call    cs:__imp_GetProcAddress
0x180022784  test    rax, rax
0x180022787  jz      loc_18002284F
0x18002278d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022792  mov     rbx, rax
0x180022795  test    rax, rax
0x180022798  jz      loc_18002284F
0x18002279e  mov     rax, [rax+18h]
0x1800227a2  test    rax, rax
0x1800227a5  jz      loc_18002284F
0x1800227ab  cmp     qword ptr [rbx+10h], 0
0x1800227b0  jz      loc_18002284F
0x1800227b6  lea     rcx, [rsp+88h+var_30]
0x1800227bb  mov     [rsp+88h+var_30], 0
0x1800227c4  mov     [rsp+88h+var_48], rcx
0x1800227c9  lea     rdx, aMicrosoftUnifi; "Microsoft Unified Security Protocol Pro"...
0x1800227d0  xor     r9d, r9d
0x1800227d3  mov     [rsp+88h+var_38], 0
0x1800227dc  lea     rcx, [rsp+88h+var_28]
0x1800227e1  xorps   xmm0, xmm0
0x1800227e4  mov     [rsp+88h+var_50], rcx
0x1800227e9  xor     ecx, ecx
0x1800227eb  mov     [rsp+88h+var_58], 0
0x1800227f4  mov     [rsp+88h+var_60], 0
0x1800227fd  lea     r8d, [r9+2]
0x180022801  mov     [rsp+88h+var_68], 0
0x18002280a  movups  [rsp+88h+var_28], xmm0
0x18002280f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022814  test    eax, eax
0x180022816  jnz     short loc_18002284F
0x180022818  lea     edx, [rax+57h]
0x18002281b  mov     rax, [rbx+10h]
0x18002281f  lea     r8, [rsp+88h+var_38]
0x180022824  lea     rcx, [rsp+88h+var_28]
0x180022829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002282e  test    eax, eax
0x180022830  jnz     short loc_18002283C
0x180022832  mov     eax, dword ptr [rsp+88h+var_38+4]
0x180022836  mov     cs:dword_1800593FC, eax
0x18002283c  mov     rax, [rbx+20h]
0x180022840  test    rax, rax
0x180022843  jz      short loc_18002284F
0x180022845  lea     rcx, [rsp+88h+var_28]
0x18002284a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002284f  mov     rcx, rdi; hLibModule
0x180022852  call    cs:__imp_FreeLibrary
0x180022858  mov     eax, cs:dword_1800593FC
0x18002285e  mov     rcx, [rsp+88h+var_18]
0x180022863  xor     rcx, rsp; StackCookie
0x180022866  call    __security_check_cookie
0x18002286b  mov     rbx, [rsp+88h+arg_0]
0x180022873  add     rsp, 80h
0x18002287a  pop     rdi
0x18002287b  retn
```
