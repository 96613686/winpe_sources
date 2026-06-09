# FindWindowsMailPath(ushort *,ulong)

- ea: `0x180064068`
- end: `0x1800641ce`
- name: `?FindWindowsMailPath@@YAXPEAGK@Z`
- size: `358`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180067820`

## callees

- `0x1800045e4`
- `0x180064068`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800640ee`
- `ADVAPI32!RegOpenKeyExW` at `0x1800640ee`
- `ADVAPI32!RegCloseKey` at `0x1800641a1`
- `ADVAPI32!RegCloseKey` at `0x1800641a1`
- `ADVAPI32!RegQueryValueExW` at `0x180064134`
- `ADVAPI32!RegQueryValueExW` at `0x180064134`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180064152`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180064152`

## string_xrefs

- `0x18006412d`: `DllPath`

## pseudocode

```c
void __fastcall FindWindowsMailPath(unsigned __int16 *a1)
{
  LSTATUS v2; // ebx
  __int64 v3; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Data[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dst[264]; // [rsp+250h] [rbp+150h] BYREF

  hKey = 0;
  cbData = 0;
  memset_0(Data, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  Type = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Clients\\Mail\\Windows Mail", 0, 0x20019u, &hKey) )
  {
    Data[0] = 0;
    cbData = 260;
    v2 = RegQueryValueExW(hKey, L"DllPath", 0, &Type, (LPBYTE)Data, &cbData);
    if ( Type == 2 )
    {
      ExpandEnvironmentStringsW(Data, Dst, 0x104u);
      StringCchCopyW(Data, 0x104u, Dst);
    }
    if ( !v2 )
    {
      v3 = -1;
      do
        ++v3;
      while ( Data[v3] );
      if ( v3 )
        StringCchCopyW(a1, 0x104u, Data);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180064068  mov     [rsp-8+arg_8], rbx
0x18006406d  mov     [rsp-8+arg_10], rsi
0x180064072  push    rbp
0x180064073  push    rdi
0x180064074  push    r14
0x180064076  lea     rbp, [rsp-370h]
0x18006407e  sub     rsp, 470h
0x180064085  mov     rax, cs:__security_cookie
0x18006408c  xor     rax, rsp
0x18006408f  mov     [rbp+380h+var_20], rax
0x180064096  mov     rdi, rcx
0x180064099  xor     esi, esi
0x18006409b  mov     ebx, 208h
0x1800640a0  mov     [rsp+480h+hKey], rsi
0x1800640a5  mov     r8d, ebx; Size
0x1800640a8  mov     [rsp+480h+cbData], esi
0x1800640ac  xor     edx, edx; Val
0x1800640ae  lea     rcx, [rsp+480h+Data]; void *
0x1800640b3  call    memset_0
0x1800640b8  mov     r8d, ebx; Size
0x1800640bb  lea     rcx, [rbp+380h+Dst]; void *
0x1800640c2  xor     edx, edx; Val
0x1800640c4  call    memset_0
0x1800640c9  lea     rax, [rsp+480h+hKey]
0x1800640ce  mov     [rsp+480h+Type], esi
0x1800640d2  mov     r9d, 20019h; samDesired
0x1800640d8  mov     [rsp+480h+phkResult], rax; phkResult
0x1800640dd  xor     r8d, r8d; ulOptions
0x1800640e0  lea     rdx, aSoftwareClient; "Software\\Clients\\Mail\\Windows Mail"
0x1800640e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800640ee  call    cs:__imp_RegOpenKeyExW
0x1800640f4  test    eax, eax
0x1800640f6  jnz     loc_180064197
0x1800640fc  mov     rcx, [rsp+480h+hKey]; hKey
0x180064101  lea     rax, [rsp+480h+cbData]
0x180064106  mov     [rsp+480h+lpcbData], rax; lpcbData
0x18006410b  lea     r9, [rsp+480h+Type]; lpType
0x180064110  lea     rax, [rsp+480h+Data]
0x180064115  mov     [rsp+480h+Data], si
0x18006411a  mov     r14d, 104h
0x180064120  mov     [rsp+480h+phkResult], rax; lpData
0x180064125  xor     r8d, r8d; lpReserved
0x180064128  mov     [rsp+480h+cbData], r14d
0x18006412d  lea     rdx, aDllpath; "DllPath"
0x180064134  call    cs:__imp_RegQueryValueExW
0x18006413a  cmp     [rsp+480h+Type], 2
0x18006413f  mov     ebx, eax
0x180064141  jnz     short loc_18006416C
0x180064143  mov     r8d, r14d; nSize
0x180064146  lea     rdx, [rbp+380h+Dst]; lpDst
0x18006414d  lea     rcx, [rsp+480h+Data]; lpSrc
0x180064152  call    cs:__imp_ExpandEnvironmentStringsW
0x180064158  lea     r8, [rbp+380h+Dst]; unsigned __int16 *
0x18006415f  mov     edx, r14d; unsigned __int64
0x180064162  lea     rcx, [rsp+480h+Data]; unsigned __int16 *
0x180064167  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006416c  test    ebx, ebx
0x18006416e  jnz     short loc_180064197
0x180064170  lea     rcx, [rsp+480h+Data]
0x180064175  or      rax, 0FFFFFFFFFFFFFFFFh
0x180064179  inc     rax
0x18006417c  cmp     [rcx+rax*2], si
0x180064180  jnz     short loc_180064179
0x180064182  test    rax, rax
0x180064185  jz      short loc_180064197
0x180064187  lea     r8, [rsp+480h+Data]; unsigned __int16 *
0x18006418c  mov     rdx, r14; unsigned __int64
0x18006418f  mov     rcx, rdi; unsigned __int16 *
0x180064192  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180064197  mov     rcx, [rsp+480h+hKey]; hKey
0x18006419c  test    rcx, rcx
0x18006419f  jz      short loc_1800641A7
0x1800641a1  call    cs:__imp_RegCloseKey
0x1800641a7  mov     rcx, [rbp+380h+var_20]
0x1800641ae  xor     rcx, rsp; StackCookie
0x1800641b1  call    __security_check_cookie
0x1800641b6  lea     r11, [rsp+480h+var_10]
0x1800641be  mov     rbx, [r11+28h]
0x1800641c2  mov     rsi, [r11+30h]
0x1800641c6  mov     rsp, r11
0x1800641c9  pop     r14
0x1800641cb  pop     rdi
0x1800641cc  pop     rbp
0x1800641cd  retn
```
