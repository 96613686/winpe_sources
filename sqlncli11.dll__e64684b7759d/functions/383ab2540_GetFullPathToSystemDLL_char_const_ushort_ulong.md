# GetFullPathToSystemDLL(char const *,ushort *,ulong)

- ea: `0x383ab2540`
- end: `0x383ab264f`
- name: `?GetFullPathToSystemDLL@@YAKPEBDPEAGK@Z`
- size: `271`
- prototype: `unsigned int __fastcall(LPWSTR lpFilename, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x383ab2670`

## callees

- `0x383892180`
- `0x38391ae80`
- `0x383ab2540`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x383ab2631`
- `KERNEL32!FreeLibrary` at `0x383ab2631`
- `KERNEL32!GetModuleFileNameW` at `0x383ab25ca`
- `KERNEL32!GetModuleFileNameW` at `0x383ab25ca`
- `KERNEL32!GetLastError` at `0x383ab25e7`
- `KERNEL32!GetLastError` at `0x383ab25e7`

## string_xrefs

- `0x383ab2553`: `mswsock.dll`
- `0x383ab2595`: `mswsock.dll`
- `0x383ab2619`: `mswsock.dll`

## pseudocode

```c
__int64 __fastcall GetFullPathToSystemDLL(LPWSTR lpFilename, unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  HMODULE v4; // rax
  HMODULE v5; // rsi
  DWORD ModuleFileNameW; // eax

  v3 = -1;
  v4 = SNILoadSystemLibA("mswsock.dll");
  v5 = v4;
  if ( v4 )
  {
    ModuleFileNameW = GetModuleFileNameW(v4, lpFilename, 0x104u);
    if ( ModuleFileNameW && ModuleFileNameW < 0x104 )
    {
      v3 = 0;
      lpFilename[ModuleFileNameW] = 0;
    }
    else
    {
      GetLastError();
      if ( (bidGblFlags & 2) != 0 && off_383B46CA0[0] )
        bidTraceA(off_383B44620[0], 1923072, off_383B46CA0[0], "mswsock.dll");
    }
    FreeLibrary(v5);
  }
  else if ( (bidGblFlags & 2) != 0 && off_383B46CA8[0] )
  {
    bidTraceA(off_383B44628[0], 1907712, off_383B46CA8[0], "mswsock.dll");
    return 0xFFFFFFFFLL;
  }
  return v3;
}

```

## disassembly

```asm
0x383ab2540  mov     [rsp+arg_8], rbx
0x383ab2545  mov     [rsp+arg_10], rsi
0x383ab254a  push    r14
0x383ab254c  sub     rsp, 30h
0x383ab2550  mov     r14, rcx
0x383ab2553  lea     rcx, aMswsockDll; "mswsock.dll"
0x383ab255a  or      ebx, 0FFFFFFFFh
0x383ab255d  call    SNILoadSystemLibA
0x383ab2562  mov     rsi, rax
0x383ab2565  test    rax, rax
0x383ab2568  jnz     short loc_383AB25B9
0x383ab256a  test    byte ptr cs:_bidGblFlags, 2
0x383ab2571  jz      loc_383AB263C
0x383ab2577  mov     rcx, cs:off_383B46CA8; "<GetFullPathToSystemDLL|ERR|SNI> Couldn"...
0x383ab257e  test    rcx, rcx
0x383ab2581  jz      loc_383AB263C
0x383ab2587  mov     r8, cs:off_383B46CA8; "<GetFullPathToSystemDLL|ERR|SNI> Couldn"...
0x383ab258e  mov     rcx, cs:off_383B44628; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab2595  lea     r9, aMswsockDll; "mswsock.dll"
0x383ab259c  mov     edx, 1D1C00h
0x383ab25a1  call    _bidTraceA
0x383ab25a6  mov     eax, ebx
0x383ab25a8  mov     rbx, [rsp+38h+arg_8]
0x383ab25ad  mov     rsi, [rsp+38h+arg_10]
0x383ab25b2  add     rsp, 30h
0x383ab25b6  pop     r14
0x383ab25b8  retn
0x383ab25b9  mov     r8d, 104h; nSize
0x383ab25bf  mov     rdx, r14; lpFilename
0x383ab25c2  mov     rcx, rax; hModule
0x383ab25c5  mov     [rsp+38h+arg_0], rdi
0x383ab25ca  call    cs:__imp_GetModuleFileNameW
0x383ab25d0  mov     edi, eax
0x383ab25d2  test    eax, eax
0x383ab25d4  jz      short loc_383AB25E7
0x383ab25d6  cmp     edi, 104h
0x383ab25dc  jnb     short loc_383AB25E7
0x383ab25de  xor     ebx, ebx
0x383ab25e0  mov     [r14+rdi*2], bx
0x383ab25e5  jmp     short loc_383AB262E
0x383ab25e7  call    cs:__imp_GetLastError
0x383ab25ed  test    eax, eax
0x383ab25ef  cmovz   eax, ebx
0x383ab25f2  test    byte ptr cs:_bidGblFlags, 2
0x383ab25f9  jz      short loc_383AB262E
0x383ab25fb  mov     rcx, cs:off_383B46CA0; "<GetFullPathToSystemDLL|ERR|SNI> Invali"...
0x383ab2602  test    rcx, rcx
0x383ab2605  jz      short loc_383AB262E
0x383ab2607  mov     r8, cs:off_383B46CA0; "<GetFullPathToSystemDLL|ERR|SNI> Invali"...
0x383ab260e  mov     rcx, cs:off_383B44620; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab2615  mov     [rsp+38h+var_10], eax
0x383ab2619  lea     r9, aMswsockDll; "mswsock.dll"
0x383ab2620  mov     edx, 1D5800h
0x383ab2625  mov     [rsp+38h+var_18], edi
0x383ab2629  call    _bidTraceA
0x383ab262e  mov     rcx, rsi; hLibModule
0x383ab2631  call    cs:__imp_FreeLibrary
0x383ab2637  mov     rdi, [rsp+38h+arg_0]
0x383ab263c  mov     rsi, [rsp+38h+arg_10]
0x383ab2641  mov     eax, ebx
0x383ab2643  mov     rbx, [rsp+38h+arg_8]
0x383ab2648  add     rsp, 30h
0x383ab264c  pop     r14
0x383ab264e  retn
```
