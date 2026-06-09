# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800073c8`
- end: `0x1800074d5`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800073c8`
- `0x1800078ec`

## callees

- `0x180002570`
- `0x1800058ec`
- `0x180006ad4`
- `0x180006cac`
- `0x1800070c8`
- `0x1800073c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007486`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007486`

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
        goto LABEL_6;
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_6:
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)hKey);
  return v4;
}

```

## disassembly

```asm
0x1800073c8  mov     [rsp-8+arg_10], rbx
0x1800073cd  push    rbp
0x1800073ce  push    rsi
0x1800073cf  push    rdi
0x1800073d0  lea     rbp, [rsp-180h]
0x1800073d8  sub     rsp, 280h
0x1800073df  mov     rax, cs:__security_cookie
0x1800073e6  xor     rax, rsp
0x1800073e9  mov     [rbp+190h+var_20], rax
0x1800073f0  mov     rsi, rdx
0x1800073f3  mov     [rsp+290h+hKey], 0
0x1800073fc  mov     r8, rdx; lpSubKey
0x1800073ff  mov     [rsp+290h+var_240], 0
0x180007408  mov     rdx, [rcx]; hKey
0x18000740b  mov     rdi, rcx
0x18000740e  lea     rcx, [rsp+290h+hKey]; this
0x180007413  mov     [rsp+290h+var_238], 0
0x18000741c  mov     r9d, 2001Fh; unsigned int
0x180007422  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007427  mov     ebx, eax
0x180007429  test    eax, eax
0x18000742b  jnz     short loc_1800074A7
0x18000742d  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180007436  jmp     short loc_180007448
0x180007438  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000743d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180007442  mov     ebx, eax
0x180007444  test    eax, eax
0x180007446  jnz     short loc_1800074A7
0x180007448  mov     rcx, [rsp+290h+hKey]; hKey
0x18000744d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180007452  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180007457  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000745c  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180007465  lea     r8, [rsp+290h+Name]; lpName
0x18000746a  mov     [rsp+290h+lpClass], 0; lpClass
0x180007473  xor     edx, edx; dwIndex
0x180007475  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18000747e  mov     [rsp+290h+cchName], 100h
0x180007486  call    cs:__imp_RegEnumKeyExW
0x18000748c  lea     rcx, [rsp+290h+hKey]; this
0x180007491  test    eax, eax
0x180007493  jz      short loc_180007438
0x180007495  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000749a  mov     rdx, rsi; unsigned __int16 *
0x18000749d  mov     rcx, rdi; this
0x1800074a0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800074a5  mov     ebx, eax
0x1800074a7  lea     rcx, [rsp+290h+hKey]; this
0x1800074ac  call    ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
0x1800074b1  mov     eax, ebx
0x1800074b3  mov     rcx, [rbp+190h+var_20]
0x1800074ba  xor     rcx, rsp; StackCookie
0x1800074bd  call    __security_check_cookie
0x1800074c2  mov     rbx, [rsp+290h+arg_10]
0x1800074ca  add     rsp, 280h
0x1800074d1  pop     rdi
0x1800074d2  pop     rsi
0x1800074d3  pop     rbp
0x1800074d4  retn
```
