# Np::SendPacketAsync(SNI_Packet *,int)

- ea: `0x383ab1510`
- end: `0x383ab1774`
- name: `?SendPacketAsync@Np@@AEAAKPEAVSNI_Packet@@H@Z`
- size: `612`
- prototype: `unsigned int(Np *__hidden this, struct SNI_Packet *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x383ab1780`
- `0x383ab1da0`

## callees

- `0x383846430`
- `0x38391ac40`
- `0x38391ade0`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab0c30`
- `0x383ab1510`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383ab15ad`
- `KERNEL32!GetLastError` at `0x383ab15ad`
- `KERNEL32!WriteFile` at `0x383ab159f`
- `KERNEL32!WriteFile` at `0x383ab159f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::SendPacketAsync(HANDLE *this, struct _OVERLAPPED *a2)
{
  char *v4; // rsi
  DWORD Internal; // ebp
  DWORD LastError; // ebx
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  v8 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48658[0] )
    bidScopeEnterA(&v8, off_383B48658[0], *((unsigned int *)this + 11));
  v4 = (char *)a2[2].hEvent + LODWORD(a2[3].InternalHigh);
  Internal = a2[3].Internal;
  a2->Pointer = 0;
  if ( WriteFile(this[8], v4, Internal, 0, a2) )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46410[0] )
      bidTraceA(off_383B43D90[0], 1892352, off_383B46410[0], 997);
    if ( v8 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return 997;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B46428[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceA(off_383B43DA8[0], 1846272, off_383B46428[0], *((unsigned int *)this + 28));
      }
      SNISetLastError(*((unsigned int *)this + 28), LastError, 50100);
      if ( (bidGblFlags & 0x24002) == 0x24002 && off_383B46420[0] )
        bidTraceA(off_383B43DA0[0], 1847296, off_383B46420[0], Internal);
      if ( (bidGblFlags & 0x24002) == 0x24002 )
        bidWriteBin(bidID, 16, v4, Internal, 0);
    }
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46418[0] )
      bidTraceA(off_383B43D98[0], 1868800, off_383B46418[0], LastError);
    if ( v8 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return LastError;
  }
}

```

## disassembly

```asm
0x383ab1510  push    rdi
0x383ab1512  sub     rsp, 40h
0x383ab1516  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x383ab151f  mov     [rsp+48h+arg_8], rbx
0x383ab1524  mov     [rsp+48h+arg_10], rbp
0x383ab1529  mov     [rsp+48h+arg_18], rsi
0x383ab152e  mov     rbx, rdx
0x383ab1531  mov     rdi, rcx
0x383ab1534  mov     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383ab153d  mov     eax, cs:_bidGblFlags
0x383ab1543  and     eax, 20004h
0x383ab1548  cmp     eax, 20004h
0x383ab154d  jnz     short loc_383AB157B
0x383ab154f  mov     rax, cs:off_383B48658; "<Np::SendPacketAsync|API|SNI> %u#, pPac"...
0x383ab1556  test    rax, rax
0x383ab1559  jz      short loc_383AB157B
0x383ab155b  mov     dword ptr [rsp+48h+lpOverlapped], 1
0x383ab1563  mov     r9, rdx
0x383ab1566  mov     r8d, [rcx+2Ch]
0x383ab156a  mov     rdx, cs:off_383B48658; "<Np::SendPacketAsync|API|SNI> %u#, pPac"...
0x383ab1571  lea     rcx, [rsp+48h+arg_0]
0x383ab1576  call    _bidScopeEnterA
0x383ab157b  mov     esi, [rbx+68h]
0x383ab157e  add     rsi, [rbx+58h]
0x383ab1582  mov     ebp, [rbx+60h]
0x383ab1585  mov     qword ptr [rbx+10h], 0
0x383ab158d  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x383ab1592  xor     r9d, r9d; lpNumberOfBytesWritten
0x383ab1595  mov     r8d, ebp; nNumberOfBytesToWrite
0x383ab1598  mov     rdx, rsi; lpBuffer
0x383ab159b  mov     rcx, [rdi+40h]; hFile
0x383ab159f  call    cs:__imp_WriteFile
0x383ab15a5  test    eax, eax
0x383ab15a7  jnz     loc_383AB16EF
0x383ab15ad  call    cs:__imp_GetLastError
0x383ab15b3  mov     ebx, eax
0x383ab15b5  cmp     eax, 3E5h
0x383ab15ba  jz      loc_383AB1683
0x383ab15c0  test    byte ptr cs:_bidGblFlags, 2
0x383ab15c7  jz      short loc_383AB1603
0x383ab15c9  mov     rcx, cs:off_383B46428; "<Np::SendPacketAsync|ERR|SNI> ProviderN"...
0x383ab15d0  test    rcx, rcx
0x383ab15d3  jz      short loc_383AB1603
0x383ab15d5  mov     ecx, 0C3B4h; unsigned int
0x383ab15da  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383ab15df  mov     [rsp+48h+var_20], ebx
0x383ab15e3  mov     dword ptr [rsp+48h+lpOverlapped], eax
0x383ab15e7  mov     r9d, [rdi+70h]
0x383ab15eb  mov     r8, cs:off_383B46428; "<Np::SendPacketAsync|ERR|SNI> ProviderN"...
0x383ab15f2  mov     edx, 1C2C00h
0x383ab15f7  mov     rcx, cs:off_383B43DA8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab15fe  call    _bidTraceA
0x383ab1603  mov     r8d, 0C3B4h
0x383ab1609  mov     edx, ebx
0x383ab160b  mov     ecx, [rdi+70h]
0x383ab160e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x383ab1613  mov     r11d, cs:_bidGblFlags
0x383ab161a  and     r11d, 24002h
0x383ab1621  cmp     r11d, 24002h
0x383ab1628  jnz     short loc_383AB1651
0x383ab162a  mov     rax, cs:off_383B46420; "<Np::SendPacketAsync|ERR|SNI> Send Pack"...
0x383ab1631  test    rax, rax
0x383ab1634  jz      short loc_383AB1651
0x383ab1636  mov     r9d, ebp
0x383ab1639  mov     r8, cs:off_383B46420; "<Np::SendPacketAsync|ERR|SNI> Send Pack"...
0x383ab1640  mov     edx, 1C3000h
0x383ab1645  mov     rcx, cs:off_383B43DA0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab164c  call    _bidTraceA
0x383ab1651  mov     eax, cs:_bidGblFlags
0x383ab1657  and     eax, 24002h
0x383ab165c  cmp     eax, 24002h
0x383ab1661  jnz     short loc_383AB1683
0x383ab1663  mov     [rsp+48h+lpOverlapped], 0
0x383ab166c  mov     r9d, ebp
0x383ab166f  mov     r8, rsi
0x383ab1672  mov     edx, 10h
0x383ab1677  mov     rcx, cs:_bidID
0x383ab167e  call    _bidWriteBin
0x383ab1683  mov     eax, cs:_bidGblFlags
0x383ab1689  and     eax, 20002h
0x383ab168e  cmp     eax, 20002h
0x383ab1693  jnz     short loc_383AB16BD
0x383ab1695  mov     rax, cs:off_383B46418; "<Np::SendPacketAsync|RET|SNI> %d{WINERR"...
0x383ab169c  test    rax, rax
0x383ab169f  jz      short loc_383AB16BD
0x383ab16a1  mov     r9d, ebx
0x383ab16a4  mov     r8, cs:off_383B46418; "<Np::SendPacketAsync|RET|SNI> %d{WINERR"...
0x383ab16ab  mov     edx, 1C8400h
0x383ab16b0  mov     rcx, cs:off_383B43D98; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab16b7  call    _bidTraceA
0x383ab16bc  nop
0x383ab16bd  cmp     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383ab16c3  jz      short loc_383AB16EB
0x383ab16c5  test    byte ptr cs:_bidGblFlags, 4
0x383ab16cc  jz      short loc_383AB16EB
0x383ab16ce  mov     rcx, cs:_bidID
0x383ab16d5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ab16d9  jz      short loc_383AB16EB
0x383ab16db  lea     r9, [rsp+48h+arg_0]
0x383ab16e0  xor     r8d, r8d
0x383ab16e3  xor     edx, edx
0x383ab16e5  call    cs:off_383B15058
0x383ab16eb  mov     eax, ebx
0x383ab16ed  jmp     short loc_383AB175F
0x383ab16ef  mov     eax, cs:_bidGblFlags
0x383ab16f5  and     eax, 20002h
0x383ab16fa  cmp     eax, 20002h
0x383ab16ff  jnz     short loc_383AB172C
0x383ab1701  mov     rax, cs:off_383B46410; "<Np::SendPacketAsync|RET|SNI> %d{WINERR"...
0x383ab1708  test    rax, rax
0x383ab170b  jz      short loc_383AB172C
0x383ab170d  mov     r9d, 3E5h
0x383ab1713  mov     r8, cs:off_383B46410; "<Np::SendPacketAsync|RET|SNI> %d{WINERR"...
0x383ab171a  mov     edx, 1CE000h
0x383ab171f  mov     rcx, cs:off_383B43D90; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ab1726  call    _bidTraceA
0x383ab172b  nop
0x383ab172c  cmp     [rsp+48h+arg_0], 0FFFFFFFFFFFFFFFFh
0x383ab1732  jz      short loc_383AB175A
0x383ab1734  test    byte ptr cs:_bidGblFlags, 4
0x383ab173b  jz      short loc_383AB175A
0x383ab173d  mov     rcx, cs:_bidID
0x383ab1744  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ab1748  jz      short loc_383AB175A
0x383ab174a  lea     r9, [rsp+48h+arg_0]
0x383ab174f  xor     r8d, r8d
0x383ab1752  xor     edx, edx
0x383ab1754  call    cs:off_383B15058
0x383ab175a  mov     eax, 3E5h
0x383ab175f  mov     rbx, [rsp+48h+arg_8]
0x383ab1764  mov     rbp, [rsp+48h+arg_10]
0x383ab1769  mov     rsi, [rsp+48h+arg_18]
0x383ab176e  add     rsp, 40h
0x383ab1772  pop     rdi
0x383ab1773  retn
```
