# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180007478`
- end: `0x180007585`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180007478`
- `0x1800078b0`

## callees

- `0x1800045c4`
- `0x180005c2c`
- `0x180006c70`
- `0x180007478`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007524`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007524`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v4 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, *this, a2, 0x2001Fu);
  if ( !v4 )
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(hKey[0], 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      if ( v4 )
        goto LABEL_7;
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_7:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v4;
}

```

## disassembly

```asm
0x180007478  mov     [rsp-8+arg_10], rbx
0x18000747d  push    rbp
0x18000747e  push    rsi
0x18000747f  push    rdi
0x180007480  lea     rbp, [rsp-180h]
0x180007488  sub     rsp, 280h
0x18000748f  mov     rax, cs:__security_cookie
0x180007496  xor     rax, rsp
0x180007499  mov     [rbp+190h+var_20], rax
0x1800074a0  mov     rsi, rdx
0x1800074a3  mov     [rsp+290h+hKey], 0
0x1800074ac  mov     r8, rdx; lpSubKey
0x1800074af  mov     [rsp+290h+var_240], 0
0x1800074b8  mov     rdx, [rcx]; hKey
0x1800074bb  mov     rdi, rcx
0x1800074be  lea     rcx, [rsp+290h+hKey]; this
0x1800074c3  mov     [rsp+290h+var_238], 0
0x1800074cc  mov     r9d, 2001Fh; unsigned int
0x1800074d2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800074d7  mov     ebx, eax
0x1800074d9  test    eax, eax
0x1800074db  jnz     short loc_180007557
0x1800074dd  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x1800074e6  mov     rcx, [rsp+290h+hKey]; hKey
0x1800074eb  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800074f0  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800074f5  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800074fa  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180007503  lea     r8, [rsp+290h+Name]; lpName
0x180007508  mov     [rsp+290h+lpClass], 0; lpClass
0x180007511  xor     edx, edx; dwIndex
0x180007513  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18000751c  mov     [rsp+290h+cchName], 100h
0x180007524  call    cs:__imp_RegEnumKeyExW
0x18000752a  lea     rcx, [rsp+290h+hKey]; this
0x18000752f  test    eax, eax
0x180007531  jnz     short loc_180007545
0x180007533  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180007538  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000753d  mov     ebx, eax
0x18000753f  test    eax, eax
0x180007541  jnz     short loc_180007557
0x180007543  jmp     short loc_1800074E6
0x180007545  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000754a  mov     rdx, rsi; unsigned __int16 *
0x18000754d  mov     rcx, rdi; this
0x180007550  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180007555  mov     ebx, eax
0x180007557  lea     rcx, [rsp+290h+hKey]; this
0x18000755c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007561  mov     eax, ebx
0x180007563  mov     rcx, [rbp+190h+var_20]
0x18000756a  xor     rcx, rsp; StackCookie
0x18000756d  call    __security_check_cookie
0x180007572  mov     rbx, [rsp+290h+arg_10]
0x18000757a  add     rsp, 280h
0x180007581  pop     rdi
0x180007582  pop     rsi
0x180007583  pop     rbp
0x180007584  retn
```
