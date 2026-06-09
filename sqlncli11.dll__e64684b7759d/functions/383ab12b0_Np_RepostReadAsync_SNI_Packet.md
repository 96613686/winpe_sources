# Np::RepostReadAsync(SNI_Packet *)

- ea: `0x383ab12b0`
- end: `0x383ab14ff`
- name: `?RepostReadAsync@Np@@AEAAKPEAVSNI_Packet@@@Z`
- size: `591`
- prototype: `unsigned int __fastcall(Np *__hidden this, LPOVERLAPPED lpOverlapped)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x383ab18e0`

## callees

- `0x383846430`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab0c30`
- `0x383ab12b0`
- `0x383ac82c0`
- `0x383ac83e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383ab138d`
- `KERNEL32!GetLastError` at `0x383ab138d`
- `KERNEL32!ReadFile` at `0x383ab137f`
- `KERNEL32!ReadFile` at `0x383ab137f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::RepostReadAsync(HANDLE *this, LPOVERLAPPED lpOverlapped)
{
  char *v4; // rsi
  unsigned int v5; // ebx
  char *v6; // r8
  __int64 v7; // rdx
  char *v8; // rcx
  DWORD LastError; // eax
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48660[0] )
    bidScopeEnterA(&v11, off_383B48660[0], *((unsigned int *)this + 11));
  v4 = (char *)lpOverlapped[2].hEvent + LODWORD(lpOverlapped[3].InternalHigh);
  lpOverlapped->Pointer = 0;
  if ( !SNI::detail::Transport::FAddHandleRef((SNI::detail::Transport *)this) )
  {
    v5 = 6;
    if ( (bidGblFlags & 2) == 0 || !off_383B46448[0] )
      goto LABEL_15;
    SniErrorIdFromStringId(0xC3B4u);
    v6 = off_383B46448[0];
    v7 = 1735680;
    v8 = off_383B43DC8[0];
LABEL_14:
    bidTraceA(v8, v7, v6, *((unsigned int *)this + 28));
LABEL_15:
    SNISetLastError(*((unsigned int *)this + 28), v5, 50100);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46430[0] )
      bidTraceA(off_383B43DB0[0], 1778688, off_383B46430[0], v5);
    if ( v11 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return v5;
  }
  if ( !ReadFile(this[8], v4, HIDWORD(lpOverlapped[3].Internal) - LODWORD(lpOverlapped[3].Internal), 0, lpOverlapped) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 997 && LastError != 234 )
    {
      SNI::detail::Transport::ReleaseHandleRef((SNI::detail::Transport *)this);
      if ( (bidGblFlags & 2) == 0 || !off_383B46440[0] )
        goto LABEL_15;
      SniErrorIdFromStringId(0xC3B4u);
      v6 = off_383B46440[0];
      v7 = 1764352;
      v8 = off_383B43DC0[0];
      goto LABEL_14;
    }
  }
  SNI::detail::Transport::ReleaseHandleRef((SNI::detail::Transport *)this);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46438[0] )
    bidTraceA(off_383B43DB8[0], 1774592, off_383B46438[0], 997);
  if ( v11 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return 997;
}

```

## disassembly

```asm
0x383ab12b0  push    rdi
0x383ab12b2  sub     rsp, 40h
0x383ab12b6  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x383ab12bf  mov     [rsp+48h+arg_0], rbx
0x383ab12c4  mov     [rsp+48h+arg_10], rsi
0x383ab12c9  mov     rbx, rdx
0x383ab12cc  mov     rdi, rcx
0x383ab12cf  mov     [rsp+48h+arg_8], 0FFFFFFFFFFFFFFFFh
0x383ab12d8  mov     eax, cs:_bidGblFlags
0x383ab12de  and     eax, 20004h
0x383ab12e3  cmp     eax, 20004h
0x383ab12e8  jnz     short loc_383AB130E
0x383ab12ea  mov     rax, cs:off_383B48660; "<Np::RepostReadAsync|API|SNI> %u#, pPac"...
0x383ab12f1  test    rax, rax
0x383ab12f4  jz      short loc_383AB130E
0x383ab12f6  mov     r9, rdx
0x383ab12f9  mov     r8d, [rcx+2Ch]
0x383ab12fd  mov     rdx, cs:off_383B48660; "<Np::RepostReadAsync|API|SNI> %u#, pPac"...
0x383ab1304  lea     rcx, [rsp+48h+arg_8]
0x383ab1309  call    _bidScopeEnterA
0x383ab130e  mov     esi, [rbx+68h]
0x383ab1311  add     rsi, [rbx+58h]
0x383ab1315  xor     eax, eax
0x383ab1317  mov     [rbx+10h], rax
0x383ab131b  mov     rcx, rdi; this
0x383ab131e  call    ?FAddHandleRef@Transport@detail@SNI@@IEAA_NXZ; SNI::detail::Transport::FAddHandleRef(void)
0x383ab1323  test    al, al
0x383ab1325  jnz     short loc_383AB1368
0x383ab1327  mov     ebx, 6
0x383ab132c  test    byte ptr cs:_bidGblFlags, 2
0x383ab1333  jz      loc_383AB13F6
0x383ab1339  mov     rax, cs:off_383B46448; "<Np::RepostReadAsync|ERR|SNI> ProviderN"...
0x383ab1340  test    rax, rax
0x383ab1343  jz      loc_383AB13F6
0x383ab1349  mov     ecx, 0C3B4h; unsigned int
0x383ab134e  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383ab1353  mov     r8, cs:off_383B46448; "<Np::RepostReadAsync|ERR|SNI> ProviderN"...
0x383ab135a  mov     edx, 1A7C00h
0x383ab135f  mov     rcx, cs:off_383B43DC8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab1366  jmp     short loc_383AB13E5
0x383ab1368  mov     r8d, [rbx+64h]
0x383ab136c  sub     r8d, [rbx+60h]; nNumberOfBytesToRead
0x383ab1370  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x383ab1375  xor     r9d, r9d; lpNumberOfBytesRead
0x383ab1378  mov     rdx, rsi; lpBuffer
0x383ab137b  mov     rcx, [rdi+40h]; hFile
0x383ab137f  call    cs:__imp_ReadFile
0x383ab1385  test    eax, eax
0x383ab1387  jnz     loc_383AB1472
0x383ab138d  call    cs:__imp_GetLastError
0x383ab1393  mov     ebx, eax
0x383ab1395  cmp     eax, 3E5h
0x383ab139a  jz      loc_383AB1472
0x383ab13a0  cmp     eax, 0EAh
0x383ab13a5  jz      loc_383AB1472
0x383ab13ab  mov     rcx, rdi; this
0x383ab13ae  call    ?ReleaseHandleRef@Transport@detail@SNI@@IEAAXXZ; SNI::detail::Transport::ReleaseHandleRef(void)
0x383ab13b3  test    byte ptr cs:_bidGblFlags, 2
0x383ab13ba  jz      short loc_383AB13F6
0x383ab13bc  mov     rcx, cs:off_383B46440; "<Np::RepostReadAsync|ERR|SNI> ProviderN"...
0x383ab13c3  test    rcx, rcx
0x383ab13c6  jz      short loc_383AB13F6
0x383ab13c8  mov     ecx, 0C3B4h; unsigned int
0x383ab13cd  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383ab13d2  mov     r8, cs:off_383B46440; "<Np::RepostReadAsync|ERR|SNI> ProviderN"...
0x383ab13d9  mov     edx, 1AEC00h
0x383ab13de  mov     rcx, cs:off_383B43DC0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab13e5  mov     [rsp+48h+var_20], ebx
0x383ab13e9  mov     dword ptr [rsp+48h+lpOverlapped], eax
0x383ab13ed  mov     r9d, [rdi+70h]
0x383ab13f1  call    _bidTraceA
0x383ab13f6  mov     r8d, 0C3B4h
0x383ab13fc  mov     edx, ebx
0x383ab13fe  mov     ecx, [rdi+70h]
0x383ab1401  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x383ab1406  mov     eax, cs:_bidGblFlags
0x383ab140c  and     eax, 20002h
0x383ab1411  cmp     eax, 20002h
0x383ab1416  jnz     short loc_383AB1440
0x383ab1418  mov     rax, cs:off_383B46430; "<Np::RepostReadAsync|RET|SNI> %d{WINERR"...
0x383ab141f  test    rax, rax
0x383ab1422  jz      short loc_383AB1440
0x383ab1424  mov     r9d, ebx
0x383ab1427  mov     r8, cs:off_383B46430; "<Np::RepostReadAsync|RET|SNI> %d{WINERR"...
0x383ab142e  mov     edx, 1B2400h
0x383ab1433  mov     rcx, cs:off_383B43DB0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab143a  call    _bidTraceA
0x383ab143f  nop
0x383ab1440  cmp     [rsp+48h+arg_8], 0FFFFFFFFFFFFFFFFh
0x383ab1446  jz      short loc_383AB146E
0x383ab1448  test    byte ptr cs:_bidGblFlags, 4
0x383ab144f  jz      short loc_383AB146E
0x383ab1451  mov     rcx, cs:_bidID
0x383ab1458  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ab145c  jz      short loc_383AB146E
0x383ab145e  lea     r9, [rsp+48h+arg_8]
0x383ab1463  xor     r8d, r8d
0x383ab1466  xor     edx, edx
0x383ab1468  call    cs:off_383B15058
0x383ab146e  mov     eax, ebx
0x383ab1470  jmp     short loc_383AB14EF
0x383ab1472  mov     rcx, rdi; this
0x383ab1475  call    ?ReleaseHandleRef@Transport@detail@SNI@@IEAAXXZ; SNI::detail::Transport::ReleaseHandleRef(void)
0x383ab147a  mov     r11d, cs:_bidGblFlags
0x383ab1481  and     r11d, 20002h
0x383ab1488  cmp     r11d, 20002h
0x383ab148f  jnz     short loc_383AB14BC
0x383ab1491  mov     rax, cs:off_383B46438; "<Np::RepostReadAsync|RET|SNI> %d{WINERR"...
0x383ab1498  test    rax, rax
0x383ab149b  jz      short loc_383AB14BC
0x383ab149d  mov     r9d, 3E5h
0x383ab14a3  mov     r8, cs:off_383B46438; "<Np::RepostReadAsync|RET|SNI> %d{WINERR"...
0x383ab14aa  mov     edx, 1B1400h
0x383ab14af  mov     rcx, cs:off_383B43DB8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab14b6  call    _bidTraceA
0x383ab14bb  nop
0x383ab14bc  cmp     [rsp+48h+arg_8], 0FFFFFFFFFFFFFFFFh
0x383ab14c2  jz      short loc_383AB14EA
0x383ab14c4  test    byte ptr cs:_bidGblFlags, 4
0x383ab14cb  jz      short loc_383AB14EA
0x383ab14cd  mov     rcx, cs:_bidID
0x383ab14d4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ab14d8  jz      short loc_383AB14EA
0x383ab14da  lea     r9, [rsp+48h+arg_8]
0x383ab14df  xor     r8d, r8d
0x383ab14e2  xor     edx, edx
0x383ab14e4  call    cs:off_383B15058
0x383ab14ea  mov     eax, 3E5h
0x383ab14ef  mov     rbx, [rsp+48h+arg_0]
0x383ab14f4  mov     rsi, [rsp+48h+arg_10]
0x383ab14f9  add     rsp, 40h
0x383ab14fd  pop     rdi
0x383ab14fe  retn
```
