# Np::WriteSync(SNI_Packet *,SNI_ProvInfo *)

- ea: `0x383868e50`
- end: `0x383868f46`
- name: `?WriteSync@Np@@UEAAKPEAVSNI_Packet@@PEAUSNI_ProvInfo@@@Z`
- size: `246`
- prototype: `unsigned int(Np *__hidden this, struct SNI_Packet *, struct SNI_ProvInfo *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x383846430`
- `0x383868e50`
- `0x38391ac40`
- `0x38391ade0`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab0c30`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x383868ed4`
- `KERNEL32!GetOverlappedResult` at `0x383868ed4`
- `KERNEL32!GetLastError` at `0x3838a3128`
- `KERNEL32!GetLastError` at `0x3838fa86e`
- `KERNEL32!GetLastError` at `0x3838a3128`
- `KERNEL32!GetLastError` at `0x3838fa86e`
- `KERNEL32!WriteFile` at `0x383868eb7`
- `KERNEL32!WriteFile` at `0x383868eb7`
- `KERNEL32!WaitForSingleObject` at `0x3838a3142`
- `KERNEL32!WaitForSingleObject` at `0x3838a3142`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::WriteSync(HANDLE *this, struct _OVERLAPPED *a2, struct SNI_ProvInfo *a3)
{
  char *v5; // rbp
  DWORD Internal; // r14d
  DWORD LastError; // ebx
  DWORD v9; // eax
  unsigned int v10; // eax
  char *v11; // r8
  __int64 v12; // rdx
  char *v13; // rcx
  int lpOverlapped; // [rsp+20h] [rbp-48h]
  DWORD NumberOfBytesTransferred; // [rsp+70h] [rbp+8h] BYREF
  __int64 v16; // [rsp+78h] [rbp+10h] BYREF

  v16 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48680[0] )
    bidScopeEnterA(&v16, off_383B48680[0], *((unsigned int *)this + 11));
  NumberOfBytesTransferred = 0;
  v5 = (char *)a2[2].hEvent + LODWORD(a2[3].InternalHigh);
  Internal = a2[3].Internal;
  a2->Pointer = 0;
  if ( !WriteFile(this[8], v5, Internal, 0, a2) )
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      if ( (bidGblFlags & 2) == 0 || !off_383B464C0[0] )
        goto LABEL_27;
      v10 = SniErrorIdFromStringId(0xC3B4u);
      v11 = off_383B464C0[0];
      v12 = 1538048;
      v13 = off_383B43E40[0];
      goto LABEL_26;
    }
    v9 = WaitForSingleObject(a2->hEvent, 0xFFFFFFFF);
    LastError = v9;
    if ( v9 == -1 || v9 == 258 )
    {
      if ( (bidGblFlags & 2) == 0 || !off_383B464B8[0] )
        goto LABEL_27;
      v10 = SniErrorIdFromStringId(0xC3B4u);
      v11 = off_383B464B8[0];
      v12 = 1546240;
      v13 = off_383B43E38[0];
      goto LABEL_26;
    }
    if ( v9 )
    {
LABEL_4:
      if ( (bidGblFlags & 0x24002) == 0x24002 && off_383B464A8[0] )
        bidTraceA(off_383B43E28[0], 1562624, off_383B464A8[0], NumberOfBytesTransferred, lpOverlapped);
      if ( (bidGblFlags & 0x24002) == 0x24002 )
      {
        lpOverlapped = 0;
        bidWriteBin(bidID, 16, v5, NumberOfBytesTransferred);
      }
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B464A0[0] )
        bidTraceA(off_383B43E20[0], 1565696, off_383B464A0[0], 0, lpOverlapped);
      if ( v16 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
        off_383B15058();
      return 0;
    }
  }
  if ( GetOverlappedResult(this[8], a2, &NumberOfBytesTransferred, 0) )
    goto LABEL_4;
  LastError = GetLastError();
  if ( (bidGblFlags & 2) != 0 && off_383B464B0[0] )
  {
    v10 = SniErrorIdFromStringId(0xC3B4u);
    v11 = off_383B464B0[0];
    v12 = 1556480;
    v13 = off_383B43E30[0];
LABEL_26:
    bidTraceA(v13, v12, v11, *((unsigned int *)this + 28), v10);
  }
LABEL_27:
  SNISetLastError(*((unsigned int *)this + 28), LastError, 50100);
  if ( (bidGblFlags & 0x24002) == 0x24002 && off_383B46498[0] )
    bidTraceA(off_383B43E18[0], 1571840, off_383B46498[0], Internal, lpOverlapped);
  if ( (bidGblFlags & 0x24002) == 0x24002 )
  {
    lpOverlapped = 0;
    bidWriteBin(bidID, 16, v5, Internal);
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B46490[0] )
    bidTraceA(off_383B43E10[0], 1573888, off_383B46490[0], LastError, lpOverlapped);
  if ( v16 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return LastError;
}

```

## disassembly

```asm
0x383868e50  mov     r11, rsp
0x383868e53  push    rbp
0x383868e54  push    rsi
0x383868e55  push    rdi
0x383868e56  push    r14
0x383868e58  push    r15
0x383868e5a  sub     rsp, 40h
0x383868e5e  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x383868e66  mov     [r11+18h], rbx
0x383868e6a  mov     rsi, rdx
0x383868e6d  mov     rdi, rcx
0x383868e70  mov     qword ptr [r11+10h], 0FFFFFFFFFFFFFFFFh
0x383868e78  mov     eax, cs:_bidGblFlags
0x383868e7e  and     eax, 20004h
0x383868e83  cmp     eax, 20004h
0x383868e88  jz      loc_3838FA7CD
0x383868e8e  xor     r15d, r15d
0x383868e91  mov     [rsp+68h+NumberOfBytesTransferred], r15d
0x383868e96  mov     ebp, [rsi+68h]
0x383868e99  add     rbp, [rsi+58h]
0x383868e9d  mov     r14d, [rsi+60h]
0x383868ea1  mov     [rsi+10h], r15
0x383868ea5  mov     [rsp+68h+lpOverlapped], rsi; lpOverlapped
0x383868eaa  xor     r9d, r9d; lpNumberOfBytesWritten
0x383868ead  mov     r8d, r14d; nNumberOfBytesToWrite
0x383868eb0  mov     rdx, rbp; lpBuffer
0x383868eb3  mov     rcx, [rdi+40h]; hFile
0x383868eb7  call    cs:__imp_WriteFile
0x383868ebd  test    eax, eax
0x383868ebf  jz      loc_3838A3128
0x383868ec5  xor     r9d, r9d; bWait
0x383868ec8  lea     r8, [rsp+68h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x383868ecd  mov     rdx, rsi; lpOverlapped
0x383868ed0  mov     rcx, [rdi+40h]; hFile
0x383868ed4  call    cs:__imp_GetOverlappedResult
0x383868eda  test    eax, eax
0x383868edc  jz      loc_3838FA86E
0x383868ee2  mov     eax, cs:_bidGblFlags
0x383868ee8  and     eax, 24002h
0x383868eed  cmp     eax, 24002h
0x383868ef2  jz      loc_3838FA99F
0x383868ef8  mov     eax, cs:_bidGblFlags
0x383868efe  and     eax, 24002h
0x383868f03  cmp     eax, 24002h
0x383868f08  jz      loc_3838FA9D2
0x383868f0e  mov     eax, cs:_bidGblFlags
0x383868f14  and     eax, 20002h
0x383868f19  cmp     eax, 20002h
0x383868f1e  jz      loc_3838FA9F6
0x383868f24  cmp     [rsp+68h+arg_8], 0FFFFFFFFFFFFFFFFh
0x383868f2a  jnz     loc_3838FAA27
0x383868f30  xor     eax, eax
0x383868f32  mov     rbx, [rsp+68h+arg_10]
0x383868f3a  add     rsp, 40h
0x383868f3e  pop     r15
0x383868f40  pop     r14
0x383868f42  pop     rdi
0x383868f43  pop     rsi
0x383868f44  pop     rbp
0x383868f45  retn
0x3838a3128  call    cs:__imp_GetLastError
0x3838a312e  mov     ebx, eax
0x3838a3130  cmp     eax, 3E5h
0x3838a3135  jnz     loc_3838FA7FE
0x3838a313b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x3838a313e  mov     rcx, [rsi+18h]; hHandle
0x3838a3142  call    cs:__imp_WaitForSingleObject
0x3838a3148  mov     ebx, eax
0x3838a314a  cmp     eax, 0FFFFFFFFh
0x3838a314d  jz      loc_3838FA83A
0x3838a3153  cmp     eax, 102h
0x3838a3158  jz      loc_3838FA83A
0x3838a315e  test    eax, eax
0x3838a3160  jnz     loc_383868EE2
0x3838a3166  jmp     loc_383868EC5
0x3838fa7cd  mov     rax, cs:off_383B48680; "<Np::WriteSync|API|SNI> %u#, pPacket: %"...
0x3838fa7d4  test    rax, rax
0x3838fa7d7  jz      loc_383868E8E
0x3838fa7dd  mov     [r11-48h], r8
0x3838fa7e1  mov     r9, rdx
0x3838fa7e4  mov     r8d, [rcx+2Ch]
0x3838fa7e8  mov     rdx, cs:off_383B48680; "<Np::WriteSync|API|SNI> %u#, pPacket: %"...
0x3838fa7ef  lea     rcx, [r11+10h]
0x3838fa7f3  call    _bidScopeEnterA
0x3838fa7f8  nop
0x3838fa7f9  jmp     loc_383868E8E
0x3838fa7fe  test    byte ptr cs:_bidGblFlags, 2
0x3838fa805  jz      loc_3838FA8B9
0x3838fa80b  mov     rcx, cs:off_383B464C0; "<Np::WriteSync|ERR|SNI> ProviderNum: %d"...
0x3838fa812  test    rcx, rcx
0x3838fa815  jz      loc_3838FA8B9
0x3838fa81b  mov     ecx, 0C3B4h; unsigned int
0x3838fa820  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838fa825  mov     r8, cs:off_383B464C0; "<Np::WriteSync|ERR|SNI> ProviderNum: %d"...
0x3838fa82c  mov     edx, 177800h
0x3838fa831  mov     rcx, cs:off_383B43E40; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa838  jmp     short loc_3838FA8A8
0x3838fa83a  test    byte ptr cs:_bidGblFlags, 2
0x3838fa841  jz      short loc_3838FA8B9
0x3838fa843  mov     rax, cs:off_383B464B8; "<Np::WriteSync|ERR|SNI> ProviderNum: %d"...
0x3838fa84a  test    rax, rax
0x3838fa84d  jz      short loc_3838FA8B9
0x3838fa84f  mov     ecx, 0C3B4h; unsigned int
0x3838fa854  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838fa859  mov     r8, cs:off_383B464B8; "<Np::WriteSync|ERR|SNI> ProviderNum: %d"...
0x3838fa860  mov     edx, 179800h
0x3838fa865  mov     rcx, cs:off_383B43E38; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa86c  jmp     short loc_3838FA8A8
0x3838fa86e  call    cs:__imp_GetLastError
0x3838fa874  mov     ebx, eax
0x3838fa876  test    byte ptr cs:_bidGblFlags, 2
0x3838fa87d  jz      short loc_3838FA8B9
0x3838fa87f  mov     rax, cs:off_383B464B0; "<Np::WriteSync|ERR|SNI> ProviderNum: %d"...
0x3838fa886  test    rax, rax
0x3838fa889  jz      short loc_3838FA8B9
0x3838fa88b  mov     ecx, 0C3B4h; unsigned int
0x3838fa890  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838fa895  mov     r8, cs:off_383B464B0; "<Np::WriteSync|ERR|SNI> ProviderNum: %d"...
0x3838fa89c  mov     edx, 17C000h
0x3838fa8a1  mov     rcx, cs:off_383B43E30; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa8a8  mov     [rsp+68h+var_40], ebx
0x3838fa8ac  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x3838fa8b0  mov     r9d, [rdi+70h]
0x3838fa8b4  call    _bidTraceA
0x3838fa8b9  mov     r8d, 0C3B4h
0x3838fa8bf  mov     edx, ebx
0x3838fa8c1  mov     ecx, [rdi+70h]
0x3838fa8c4  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3838fa8c9  mov     eax, cs:_bidGblFlags
0x3838fa8cf  and     eax, 24002h
0x3838fa8d4  cmp     eax, 24002h
0x3838fa8d9  jnz     short loc_3838FA902
0x3838fa8db  mov     rax, cs:off_383B46498; "<Np::WriteSync|ERR|SNI> Send Packet Err"...
0x3838fa8e2  test    rax, rax
0x3838fa8e5  jz      short loc_3838FA902
0x3838fa8e7  mov     r9d, r14d
0x3838fa8ea  mov     r8, cs:off_383B46498; "<Np::WriteSync|ERR|SNI> Send Packet Err"...
0x3838fa8f1  mov     edx, 17FC00h
0x3838fa8f6  mov     rcx, cs:off_383B43E18; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa8fd  call    _bidTraceA
0x3838fa902  mov     eax, cs:_bidGblFlags
0x3838fa908  and     eax, 24002h
0x3838fa90d  cmp     eax, 24002h
0x3838fa912  jnz     short loc_3838FA930
0x3838fa914  mov     [rsp+68h+lpOverlapped], r15
0x3838fa919  mov     r9d, r14d
0x3838fa91c  mov     r8, rbp
0x3838fa91f  mov     edx, 10h
0x3838fa924  mov     rcx, cs:_bidID
0x3838fa92b  call    _bidWriteBin
0x3838fa930  mov     eax, cs:_bidGblFlags
0x3838fa936  and     eax, 20002h
0x3838fa93b  cmp     eax, 20002h
0x3838fa940  jnz     short loc_3838FA96A
0x3838fa942  mov     rax, cs:off_383B46490; "<Np::WriteSync|RET|SNI> %d{WINERR}\n"
0x3838fa949  test    rax, rax
0x3838fa94c  jz      short loc_3838FA96A
0x3838fa94e  mov     r9d, ebx
0x3838fa951  mov     r8, cs:off_383B46490; "<Np::WriteSync|RET|SNI> %d{WINERR}\n"
0x3838fa958  mov     edx, 180400h
0x3838fa95d  mov     rcx, cs:off_383B43E10; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa964  call    _bidTraceA
0x3838fa969  nop
0x3838fa96a  cmp     [rsp+68h+arg_8], 0FFFFFFFFFFFFFFFFh
0x3838fa970  jz      short loc_3838FA998
0x3838fa972  test    byte ptr cs:_bidGblFlags, 4
0x3838fa979  jz      short loc_3838FA998
0x3838fa97b  mov     rcx, cs:_bidID
0x3838fa982  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838fa986  jz      short loc_3838FA998
0x3838fa988  lea     r9, [rsp+68h+arg_8]
0x3838fa98d  xor     r8d, r8d
0x3838fa990  xor     edx, edx
0x3838fa992  call    cs:off_383B15058
0x3838fa998  mov     eax, ebx
0x3838fa99a  jmp     loc_383868F32
0x3838fa99f  mov     rax, cs:off_383B464A8; "<Np::WriteSync|SNI> Send Packet, BytesW"...
0x3838fa9a6  test    rax, rax
0x3838fa9a9  jz      loc_383868EF8
0x3838fa9af  mov     r9d, [rsp+68h+NumberOfBytesTransferred]
0x3838fa9b4  mov     r8, cs:off_383B464A8; "<Np::WriteSync|SNI> Send Packet, BytesW"...
0x3838fa9bb  mov     edx, 17D800h
0x3838fa9c0  mov     rcx, cs:off_383B43E28; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa9c7  call    _bidTraceA
0x3838fa9cc  nop
0x3838fa9cd  jmp     loc_383868EF8
0x3838fa9d2  mov     [rsp+68h+lpOverlapped], r15
0x3838fa9d7  mov     r9d, [rsp+68h+NumberOfBytesTransferred]
0x3838fa9dc  mov     r8, rbp
0x3838fa9df  mov     edx, 10h
0x3838fa9e4  mov     rcx, cs:_bidID
0x3838fa9eb  call    _bidWriteBin
0x3838fa9f0  nop
0x3838fa9f1  jmp     loc_383868F0E
0x3838fa9f6  mov     rax, cs:off_383B464A0; "<Np::WriteSync|RET|SNI> %d{WINERR}\n"
0x3838fa9fd  test    rax, rax
0x3838faa00  jz      loc_383868F24
0x3838faa06  xor     r9d, r9d
0x3838faa09  mov     r8, cs:off_383B464A0; "<Np::WriteSync|RET|SNI> %d{WINERR}\n"
0x3838faa10  mov     edx, 17E400h
0x3838faa15  mov     rcx, cs:off_383B43E20; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838faa1c  call    _bidTraceA
0x3838faa21  nop
0x3838faa22  jmp     loc_383868F24
0x3838faa27  test    byte ptr cs:_bidGblFlags, 4
0x3838faa2e  jz      loc_383868F30
0x3838faa34  mov     rcx, cs:_bidID
0x3838faa3b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838faa3f  jz      loc_383868F30
0x3838faa45  lea     r9, [rsp+68h+arg_8]
0x3838faa4a  xor     r8d, r8d
0x3838faa4d  xor     edx, edx
0x3838faa4f  call    cs:off_383B15058
0x3838faa55  nop
0x3838faa56  jmp     loc_383868F30
```
