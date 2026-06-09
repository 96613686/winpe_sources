# Ssl::LoadSecurityLibrary(void)

- ea: `0x3838913f0`
- end: `0x38389148f`
- name: `?LoadSecurityLibrary@Ssl@@CAKXZ`
- size: `159`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3838931f0`

## callees

- `0x383846430`
- `0x3838913f0`
- `0x383892180`
- `0x38391ac20`
- `0x38391ac40`
- `0x38391ae80`
- `0x383ab0c30`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x383901376`
- `KERNEL32!FreeLibrary` at `0x383901431`
- `KERNEL32!FreeLibrary` at `0x383901376`
- `KERNEL32!FreeLibrary` at `0x383901431`
- `KERNEL32!GetLastError` at `0x383901294`
- `KERNEL32!GetLastError` at `0x383901367`
- `KERNEL32!GetLastError` at `0x383901422`
- `KERNEL32!GetLastError` at `0x383901294`
- `KERNEL32!GetLastError` at `0x383901367`
- `KERNEL32!GetLastError` at `0x383901422`
- `KERNEL32!GetProcAddress` at `0x383891444`
- `KERNEL32!GetProcAddress` at `0x383891444`

## string_xrefs

- `0x38389141e`: `security.dll`
- `0x38389143a`: `InitSecurityInterfaceW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Ssl::LoadSecurityLibrary(void)
{
  HMODULE v0; // rax
  __int64 (*ProcAddress)(void); // rax
  DWORD LastError; // ebx
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  int v7; // [rsp+20h] [rbp-28h]

  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B488D0[0] && bidID != -1 )
  {
    v7 = (int)off_383B488D0[0];
    off_383B15048();
  }
  v0 = SNILoadSystemLibA("security.dll");
  Ssl::s_hSecurity = v0;
  if ( !v0 )
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_383B46F40[0] )
    {
      v4 = SniErrorIdFromStringId(0xC3B4u);
      bidTraceA(off_383B448C0[0], 8222720, off_383B46F40[0], 6, v4);
    }
    SNISetLastError(6, LastError, 50100);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46F38[0] )
      bidTraceA(off_383B448B8[0], 8224768, off_383B46F38[0], LastError, v7);
    return LastError;
  }
  ProcAddress = GetProcAddress(v0, "InitSecurityInterfaceW");
  if ( !ProcAddress )
  {
    LastError = GetLastError();
    FreeLibrary(Ssl::s_hSecurity);
    Ssl::s_hSecurity = 0;
    if ( (bidGblFlags & 2) != 0 && off_383B46F30[0] )
    {
      v5 = SniErrorIdFromStringId(0xC3B4u);
      bidTraceA(off_383B448B0[0], 8241152, off_383B46F30[0], 6, v5);
    }
    SNISetLastError(6, LastError, 50100);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46F28[0] )
      bidTraceA(off_383B448A8[0], 8243200, off_383B46F28[0], LastError, v7);
    return LastError;
  }
  Ssl::s_pfTable = (struct _SECURITY_FUNCTION_TABLE_W *)ProcAddress();
  if ( !Ssl::s_pfTable )
  {
    LastError = GetLastError();
    FreeLibrary(Ssl::s_hSecurity);
    Ssl::s_hSecurity = 0;
    if ( (bidGblFlags & 2) != 0 && off_383B46F20[0] )
    {
      v6 = SniErrorIdFromStringId(0xC3B4u);
      bidTraceA(off_383B448A0[0], 8256512, off_383B46F20[0], 6, v6);
    }
    SNISetLastError(6, LastError, 50100);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46F18[0] )
      bidTraceA(off_383B44898[0], 8258560, off_383B46F18[0], LastError, v7);
    return LastError;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 )
  {
    if ( off_383B46F10[0] )
      bidTraceA(off_383B44890[0], 8263680, off_383B46F10[0], 0, v7);
  }
  return 0;
}

```

## disassembly

```asm
0x3838913f0  push    rbx
0x3838913f2  sub     rsp, 40h
0x3838913f6  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x3838913ff  mov     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383891408  mov     eax, cs:_bidGblFlags
0x38389140e  and     eax, 20004h
0x383891413  cmp     eax, 20004h
0x383891418  jz      loc_383901244
0x38389141e  lea     rcx, aSecurityDll; "security.dll"
0x383891425  call    SNILoadSystemLibA
0x38389142a  mov     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Ssl::s_hSecurity
0x383891431  test    rax, rax
0x383891434  jz      loc_383901294
0x38389143a  lea     rdx, aInitsecurityin; "InitSecurityInterfaceW"
0x383891441  mov     rcx, rax; hModule
0x383891444  call    cs:__imp_GetProcAddress
0x38389144a  test    rax, rax
0x38389144d  jz      loc_383901367
0x383891453  call    rax
0x383891455  mov     cs:?s_pfTable@Ssl@@0PEAU_SECURITY_FUNCTION_TABLE_W@@EA, rax; _SECURITY_FUNCTION_TABLE_W * Ssl::s_pfTable
0x38389145c  test    rax, rax
0x38389145f  jz      loc_383901422
0x383891465  mov     eax, cs:_bidGblFlags
0x38389146b  and     eax, 20002h
0x383891470  cmp     eax, 20002h
0x383891475  jz      loc_3839014DD
0x38389147b  cmp     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383891481  jnz     loc_38390150E
0x383891487  xor     eax, eax
0x383891489  add     rsp, 40h
0x38389148d  pop     rbx
0x38389148e  retn
0x383901244  mov     rax, cs:off_383B488D0; "<Ssl::LoadSecurityLibrary|API|SNI> \n"
0x38390124b  test    rax, rax
0x38390124e  jz      loc_38389141E
0x383901254  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x38390125c  jz      loc_38389141E
0x383901262  mov     [rsp+48h+var_20], 0
0x38390126b  mov     rax, cs:off_383B488D0; "<Ssl::LoadSecurityLibrary|API|SNI> \n"
0x383901272  mov     [rsp+48h+var_28], rax
0x383901277  lea     r9, [rsp+48h+arg_0]
0x38390127c  xor     r8d, r8d
0x38390127f  xor     edx, edx
0x383901281  mov     rcx, cs:_bidID
0x383901288  call    cs:off_383B15048
0x38390128e  nop
0x38390128f  jmp     loc_38389141E
0x383901294  call    cs:__imp_GetLastError
0x38390129a  mov     ebx, eax
0x38390129c  test    byte ptr cs:_bidGblFlags, 2
0x3839012a3  jz      short loc_3839012E1
0x3839012a5  mov     rcx, cs:off_383B46F40; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x3839012ac  test    rcx, rcx
0x3839012af  jz      short loc_3839012E1
0x3839012b1  mov     ecx, 0C3B4h; unsigned int
0x3839012b6  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3839012bb  mov     dword ptr [rsp+48h+var_20], ebx
0x3839012bf  mov     dword ptr [rsp+48h+var_28], eax
0x3839012c3  mov     r9d, 6
0x3839012c9  mov     r8, cs:off_383B46F40; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x3839012d0  mov     edx, 7D7800h
0x3839012d5  mov     rcx, cs:off_383B448C0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3839012dc  call    _bidTraceA
0x3839012e1  mov     r8d, 0C3B4h
0x3839012e7  mov     edx, ebx
0x3839012e9  mov     ecx, 6
0x3839012ee  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3839012f3  mov     r11d, cs:_bidGblFlags
0x3839012fa  and     r11d, 20002h
0x383901301  cmp     r11d, 20002h
0x383901308  jnz     short loc_383901332
0x38390130a  mov     rax, cs:off_383B46F38; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x383901311  test    rax, rax
0x383901314  jz      short loc_383901332
0x383901316  mov     r9d, ebx
0x383901319  mov     r8, cs:off_383B46F38; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x383901320  mov     edx, 7D8000h
0x383901325  mov     rcx, cs:off_383B448B8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x38390132c  call    _bidTraceA
0x383901331  nop
0x383901332  cmp     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383901338  jz      short loc_383901360
0x38390133a  test    byte ptr cs:_bidGblFlags, 4
0x383901341  jz      short loc_383901360
0x383901343  mov     rcx, cs:_bidID
0x38390134a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x38390134e  jz      short loc_383901360
0x383901350  lea     r9, [rsp+48h+arg_0]
0x383901355  xor     r8d, r8d
0x383901358  xor     edx, edx
0x38390135a  call    cs:off_383B15058
0x383901360  mov     eax, ebx
0x383901362  jmp     loc_383891489
0x383901367  call    cs:__imp_GetLastError
0x38390136d  mov     ebx, eax
0x38390136f  mov     rcx, cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA; hLibModule
0x383901376  call    cs:__imp_FreeLibrary
0x38390137c  mov     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Ssl::s_hSecurity
0x383901387  test    byte ptr cs:_bidGblFlags, 2
0x38390138e  jz      short loc_3839013CC
0x383901390  mov     rcx, cs:off_383B46F30; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x383901397  test    rcx, rcx
0x38390139a  jz      short loc_3839013CC
0x38390139c  mov     ecx, 0C3B4h; unsigned int
0x3839013a1  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3839013a6  mov     dword ptr [rsp+48h+var_20], ebx
0x3839013aa  mov     dword ptr [rsp+48h+var_28], eax
0x3839013ae  mov     r9d, 6
0x3839013b4  mov     r8, cs:off_383B46F30; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x3839013bb  mov     edx, 7DC000h
0x3839013c0  mov     rcx, cs:off_383B448B0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3839013c7  call    _bidTraceA
0x3839013cc  mov     r8d, 0C3B4h
0x3839013d2  mov     edx, ebx
0x3839013d4  mov     ecx, 6
0x3839013d9  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3839013de  mov     r11d, cs:_bidGblFlags
0x3839013e5  and     r11d, 20002h
0x3839013ec  cmp     r11d, 20002h
0x3839013f3  jnz     short loc_38390141D
0x3839013f5  mov     rax, cs:off_383B46F28; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x3839013fc  test    rax, rax
0x3839013ff  jz      short loc_38390141D
0x383901401  mov     r9d, ebx
0x383901404  mov     r8, cs:off_383B46F28; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x38390140b  mov     edx, 7DC800h
0x383901410  mov     rcx, cs:off_383B448A8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383901417  call    _bidTraceA
0x38390141c  nop
0x38390141d  jmp     loc_383901332
0x383901422  call    cs:__imp_GetLastError
0x383901428  mov     ebx, eax
0x38390142a  mov     rcx, cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA; hLibModule
0x383901431  call    cs:__imp_FreeLibrary
0x383901437  mov     cs:?s_hSecurity@Ssl@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Ssl::s_hSecurity
0x383901442  test    byte ptr cs:_bidGblFlags, 2
0x383901449  jz      short loc_383901487
0x38390144b  mov     rcx, cs:off_383B46F20; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x383901452  test    rcx, rcx
0x383901455  jz      short loc_383901487
0x383901457  mov     ecx, 0C3B4h; unsigned int
0x38390145c  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383901461  mov     dword ptr [rsp+48h+var_20], ebx
0x383901465  mov     dword ptr [rsp+48h+var_28], eax
0x383901469  mov     r9d, 6
0x38390146f  mov     r8, cs:off_383B46F20; "<Ssl::LoadSecurityLibrary|ERR|SNI> Prov"...
0x383901476  mov     edx, 7DFC00h
0x38390147b  mov     rcx, cs:off_383B448A0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383901482  call    _bidTraceA
0x383901487  mov     r8d, 0C3B4h
0x38390148d  mov     edx, ebx
0x38390148f  mov     ecx, 6
0x383901494  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x383901499  mov     r11d, cs:_bidGblFlags
0x3839014a0  and     r11d, 20002h
0x3839014a7  cmp     r11d, 20002h
0x3839014ae  jnz     short loc_3839014D8
0x3839014b0  mov     rax, cs:off_383B46F18; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x3839014b7  test    rax, rax
0x3839014ba  jz      short loc_3839014D8
0x3839014bc  mov     r9d, ebx
0x3839014bf  mov     r8, cs:off_383B46F18; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x3839014c6  mov     edx, 7E0400h
0x3839014cb  mov     rcx, cs:off_383B44898; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3839014d2  call    _bidTraceA
0x3839014d7  nop
0x3839014d8  jmp     loc_383901332
0x3839014dd  mov     rax, cs:off_383B46F10; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x3839014e4  test    rax, rax
0x3839014e7  jz      loc_38389147B
0x3839014ed  xor     r9d, r9d
0x3839014f0  mov     r8, cs:off_383B46F10; "<Ssl::LoadSecurityLibrary|RET|SNI> %d{W"...
0x3839014f7  mov     edx, 7E1800h
0x3839014fc  mov     rcx, cs:off_383B44890; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383901503  call    _bidTraceA
0x383901508  nop
0x383901509  jmp     loc_38389147B
0x38390150e  test    byte ptr cs:_bidGblFlags, 4
0x383901515  jz      loc_383891487
0x38390151b  mov     rcx, cs:_bidID
0x383901522  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383901526  jz      loc_383891487
0x38390152c  lea     r9, [rsp+48h+arg_0]
0x383901531  xor     r8d, r8d
0x383901534  xor     edx, edx
0x383901536  call    cs:off_383B15058
0x38390153c  nop
0x38390153d  jmp     loc_383891487
```
