# _AssocCreateAppKey(ushort const *,int,ulong,HKEY__ * *)

- ea: `0x18001f454`
- end: `0x18001f54d`
- name: `?_AssocCreateAppKey@@YAJPEBGHKPEAPEAUHKEY__@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, int, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001fa90`

## callees

- `0x180003560`
- `0x180004e64`
- `0x180012550`
- `0x18001f454`
- `0x18001f554`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18001f49c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18001f49c`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x18001f504`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x18001f504`

## pseudocode

```c
int __fastcall _AssocCreateAppKey(LPCWSTR pszPath, int a2, __int64 a3, HKEY *a4)
{
  int result; // eax
  unsigned __int16 v8[264]; // [rsp+30h] [rbp-228h] BYREF

  StringCchPrintfW(v8, 0x104u, L"Software\\Classes\\Applications\\%s", pszPath);
  if ( !*PathFindExtensionW(pszPath) )
    StringCchCatW(v8, 0x104u, L".exe");
  result = _AssocOpenRegKey((HKEY)(-(__int64)(a2 != 0) - 2147483646), v8, 0x20006u, a4, 1);
  if ( result == -2147023875 )
  {
    if ( a2 )
    {
      SHDeleteKeyW(HKEY_CURRENT_USER, L"Software\\Classes\\Applications");
      return _AssocOpenRegKey(HKEY_CURRENT_USER, v8, 0x20006u, a4, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001f454  mov     [rsp+arg_8], rbx
0x18001f459  mov     [rsp+arg_10], rsi
0x18001f45e  push    rdi
0x18001f45f  sub     rsp, 250h
0x18001f466  mov     rax, cs:__security_cookie
0x18001f46d  xor     rax, rsp
0x18001f470  mov     [rsp+258h+var_18], rax
0x18001f478  mov     rsi, r9
0x18001f47b  lea     r8, aSoftwareClasse_1; "Software\\Classes\\Applications\\%s"
0x18001f482  mov     r9, rcx
0x18001f485  mov     edi, edx
0x18001f487  mov     rbx, rcx
0x18001f48a  mov     edx, 104h; unsigned __int64
0x18001f48f  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x18001f494  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f499  mov     rcx, rbx; pszPath
0x18001f49c  call    cs:__imp_PathFindExtensionW
0x18001f4a2  xor     ebx, ebx
0x18001f4a4  cmp     [rax], bx
0x18001f4a7  jnz     short loc_18001F4BF
0x18001f4a9  lea     r8, aExe; ".exe"
0x18001f4b0  mov     edx, 104h; unsigned __int64
0x18001f4b5  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x18001f4ba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001f4bf  mov     eax, edi
0x18001f4c1  mov     [rsp+258h+var_238], 1; int
0x18001f4c9  neg     eax
0x18001f4cb  lea     rdx, [rsp+258h+var_228]; unsigned __int16 *
0x18001f4d0  mov     r9, rsi; HKEY *
0x18001f4d3  mov     r8d, 20006h; unsigned int
0x18001f4d9  sbb     rcx, rcx
0x18001f4dc  add     rcx, 0FFFFFFFF80000002h; HKEY
0x18001f4e3  call    ?_AssocOpenRegKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@H@Z; _AssocOpenRegKey(HKEY__ *,ushort const *,ulong,HKEY__ * *,int)
0x18001f4e8  cmp     eax, 800703FDh
0x18001f4ed  jnz     short loc_18001F528
0x18001f4ef  test    edi, edi
0x18001f4f1  jz      short loc_18001F528
0x18001f4f3  mov     rbx, 0FFFFFFFF80000001h
0x18001f4fa  lea     rdx, aSoftwareClasse_0; "Software\\Classes\\Applications"
0x18001f501  mov     rcx, rbx; hkey
0x18001f504  call    cs:__imp_SHDeleteKeyW
0x18001f50a  mov     r9, rsi; HKEY *
0x18001f50d  mov     [rsp+258h+var_238], 1; int
0x18001f515  mov     r8d, 20006h; unsigned int
0x18001f51b  lea     rdx, [rsp+258h+var_228]; unsigned __int16 *
0x18001f520  mov     rcx, rbx; HKEY
0x18001f523  call    ?_AssocOpenRegKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@H@Z; _AssocOpenRegKey(HKEY__ *,ushort const *,ulong,HKEY__ * *,int)
0x18001f528  mov     rcx, [rsp+258h+var_18]
0x18001f530  xor     rcx, rsp; StackCookie
0x18001f533  call    __security_check_cookie
0x18001f538  lea     r11, [rsp+258h+var_8]
0x18001f540  mov     rbx, [r11+18h]
0x18001f544  mov     rsi, [r11+20h]
0x18001f548  mov     rsp, r11
0x18001f54b  pop     rdi
0x18001f54c  retn
```
