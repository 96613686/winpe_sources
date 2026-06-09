# Np::ReadSync(SNI_Packet * *,int)

- ea: `0x383868f50`
- end: `0x383869134`
- name: `?ReadSync@Np@@UEAAKPEAPEAVSNI_Packet@@H@Z`
- size: `484`
- prototype: `unsigned int(Np *__hidden this, struct SNI_Packet **, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x383842d70`
- `0x383843bc0`
- `0x383846430`
- `0x383868f50`
- `0x38391ac40`
- `0x38391ade0`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab0c30`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x38386905c`
- `KERNEL32!GetOverlappedResult` at `0x383895961`
- `KERNEL32!GetOverlappedResult` at `0x38386905c`
- `KERNEL32!GetOverlappedResult` at `0x383895961`
- `KERNEL32!GetLastError` at `0x383869002`
- `KERNEL32!GetLastError` at `0x3838fa3e8`
- `KERNEL32!GetLastError` at `0x3838fa405`
- `KERNEL32!GetLastError` at `0x383869002`
- `KERNEL32!GetLastError` at `0x3838fa3e8`
- `KERNEL32!GetLastError` at `0x3838fa405`
- `KERNEL32!GetTickCount` at `0x383869022`
- `KERNEL32!GetTickCount` at `0x3838fa436`
- `KERNEL32!GetTickCount` at `0x383869022`
- `KERNEL32!GetTickCount` at `0x3838fa436`
- `KERNEL32!ReadFile` at `0x383868ff4`
- `KERNEL32!ReadFile` at `0x383868ff4`
- `KERNEL32!WaitForSingleObject` at `0x383869031`
- `KERNEL32!WaitForSingleObject` at `0x383869031`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::ReadSync(Np *this, struct SNI_Packet **a2, signed int a3)
{
  __int64 v6; // rsi
  __int64 lpOverlapped; // rax
  void *v8; // rdx
  DWORD v9; // r8d
  DWORD LastError; // eax
  DWORD v11; // ebx
  DWORD TickCount; // ebp
  DWORD v13; // eax
  DWORD v15; // eax
  char *v16; // r8
  __int64 v17; // rdx
  char *v18; // rcx
  DWORD NumberOfBytesTransferred; // [rsp+70h] [rbp+8h] BYREF
  __int64 v20; // [rsp+78h] [rbp+10h] BYREF

  v20 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48688[0] )
    bidScopeEnterA(&v20, off_383B48688[0], *((unsigned int *)this + 11));
  NumberOfBytesTransferred = 0;
  *a2 = 0;
  while ( 1 )
  {
    v6 = *((_QWORD *)this + 15);
    if ( v6 )
    {
      *((_QWORD *)this + 15) = 0;
      goto LABEL_8;
    }
    lpOverlapped = SNIPacketAllocateEx2(*((_QWORD *)this + 4), 0);
    v6 = lpOverlapped;
    if ( !lpOverlapped )
    {
      v11 = 14;
      if ( (bidGblFlags & 2) != 0 && off_383B46510[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceA(off_383B43E90[0], 1335296, off_383B46510[0], *((unsigned int *)this + 28));
      }
      SNISetLastError(*((unsigned int *)this + 28), 14, 50100);
      goto LABEL_20;
    }
    v8 = (void *)(*(_QWORD *)(lpOverlapped + 88) + *(unsigned int *)(lpOverlapped + 104));
    v9 = *(_DWORD *)(lpOverlapped + 100);
    NumberOfBytesTransferred = 0;
    *(_QWORD *)(lpOverlapped + 16) = 0;
    if ( ReadFile(*((HANDLE *)this + 8), v8, v9, 0, (LPOVERLAPPED)lpOverlapped) )
      break;
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError == 234 )
      break;
    if ( LastError != 997 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B46508[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        v16 = off_383B46508[0];
        v17 = 1368064;
        v18 = off_383B43E88[0];
        goto LABEL_52;
      }
      goto LABEL_53;
    }
LABEL_8:
    TickCount = GetTickCount();
    v13 = WaitForSingleObject(*(HANDLE *)(v6 + 24), a3);
    v11 = v13;
    if ( v13 == -1 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B464F8[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceA(off_383B43E78[0], 1412096, off_383B464F8[0], *((unsigned int *)this + 28));
      }
      SNISetLastError(*((unsigned int *)this + 28), 0xFFFFFFFFLL, 50100);
LABEL_68:
      SNIPacketRelease((struct SNI_Packet *)v6);
      *((_QWORD *)this + 15) = 0;
      goto LABEL_20;
    }
    if ( v13 == 258 )
    {
      *((_QWORD *)this + 15) = v6;
      if ( (bidGblFlags & 2) != 0 && off_383B464F0[0] )
      {
        SniErrorIdFromStringId(0xC3BFu);
        bidTraceA(off_383B43E70[0], 1419264, off_383B464F0[0], *((unsigned int *)this + 28));
      }
      goto LABEL_19;
    }
    if ( GetOverlappedResult(*((HANDLE *)this + 8), (LPOVERLAPPED)v6, &NumberOfBytesTransferred, 0) )
      goto LABEL_11;
    v15 = GetLastError();
    v11 = v15;
    if ( v15 != 995 )
    {
      if ( v15 != 234 )
      {
        if ( (bidGblFlags & 2) != 0 && off_383B464E0[0] )
        {
          SniErrorIdFromStringId(0xC3B4u);
          v16 = off_383B464E0[0];
          v17 = 1456128;
          v18 = off_383B43E60[0];
LABEL_52:
          bidTraceA(v18, v17, v16, *((unsigned int *)this + 28));
        }
        goto LABEL_53;
      }
LABEL_11:
      *(_DWORD *)(v6 + 96) = NumberOfBytesTransferred;
      *a2 = (struct SNI_Packet *)v6;
      if ( (bidGblFlags & 0x24002) == 0x24002 && off_383B464D8[0] )
        bidTraceA(off_383B43E58[0], 1472512, off_383B464D8[0], NumberOfBytesTransferred);
      if ( (bidGblFlags & 0x24002) == 0x24002 )
        bidWriteBin(bidID, 16, *(_QWORD *)(v6 + 88) + *(unsigned int *)(v6 + 104), NumberOfBytesTransferred, 0);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B464D0[0] )
        bidTraceA(off_383B43E50[0], 1475584, off_383B464D0[0], 0);
      if ( v20 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
        off_383B15058();
      return 0;
    }
    SNIPacketRelease((struct SNI_Packet *)v6);
    *((_QWORD *)this + 15) = 0;
    NumberOfBytesTransferred = 0;
    if ( a3 != -1 )
    {
      a3 += TickCount - GetTickCount();
      if ( a3 <= 0 )
      {
        v11 = 258;
        if ( (bidGblFlags & 2) != 0 && off_383B464E8[0] )
        {
          SniErrorIdFromStringId(0xC3BFu);
          bidTraceA(off_383B43E68[0], 1445888, off_383B464E8[0], *((unsigned int *)this + 28));
        }
LABEL_19:
        SNISetLastError(*((unsigned int *)this + 28), 258, 50111);
        goto LABEL_20;
      }
    }
  }
  if ( GetOverlappedResult(*((HANDLE *)this + 8), (LPOVERLAPPED)v6, &NumberOfBytesTransferred, 1) )
    goto LABEL_11;
  v11 = GetLastError();
  if ( v11 == 234 )
    goto LABEL_11;
  if ( (bidGblFlags & 2) != 0 && off_383B46500[0] )
  {
    SniErrorIdFromStringId(0xC3B4u);
    v16 = off_383B46500[0];
    v17 = 1384448;
    v18 = off_383B43E80[0];
    goto LABEL_52;
  }
LABEL_53:
  SNISetLastError(*((unsigned int *)this + 28), v11, 50100);
  if ( v11 != 258 )
    goto LABEL_68;
LABEL_20:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B464C8[0] )
    bidTraceA(off_383B43E48[0], 1490944, off_383B464C8[0], v11);
  if ( v20 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return v11;
}

```

## disassembly

```asm
0x383868f50  mov     r11, rsp
0x383868f53  push    rsi
0x383868f54  push    rdi
0x383868f55  push    r12
0x383868f57  push    r14
0x383868f59  push    r15
0x383868f5b  sub     rsp, 40h
0x383868f5f  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFEh
0x383868f67  mov     [r11+18h], rbx
0x383868f6b  mov     [r11+20h], rbp
0x383868f6f  mov     r14d, r8d
0x383868f72  mov     r15, rdx
0x383868f75  mov     rdi, rcx
0x383868f78  mov     qword ptr [r11+10h], 0FFFFFFFFFFFFFFFFh
0x383868f80  mov     eax, cs:_bidGblFlags
0x383868f86  and     eax, 20004h
0x383868f8b  cmp     eax, 20004h
0x383868f90  jz      loc_3838FA3A7
0x383868f96  xor     r12d, r12d
0x383868f99  mov     ebx, r12d
0x383868f9c  mov     [rsp+68h+NumberOfBytesTransferred], r12d
0x383868fa1  mov     [r15], r12
0x383868fa4  nop     word ptr [rax+rax+00h]
0x383868faa  nop     word ptr [rax+rax+00h]
0x383868fb0  mov     rsi, [rdi+78h]
0x383868fb4  test    rsi, rsi
0x383868fb7  jnz     loc_3838690DF
0x383868fbd  xor     edx, edx
0x383868fbf  mov     rcx, [rdi+20h]
0x383868fc3  call    SNIPacketAllocateEx2
0x383868fc8  mov     rsi, rax
0x383868fcb  test    rax, rax
0x383868fce  jz      loc_3838FA4CD
0x383868fd4  mov     edx, [rax+68h]
0x383868fd7  add     rdx, [rax+58h]; lpBuffer
0x383868fdb  mov     r8d, [rax+64h]; nNumberOfBytesToRead
0x383868fdf  mov     [rsp+68h+NumberOfBytesTransferred], r12d
0x383868fe4  mov     [rax+10h], r12
0x383868fe8  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x383868fed  xor     r9d, r9d; lpNumberOfBytesRead
0x383868ff0  mov     rcx, [rdi+40h]; hFile
0x383868ff4  call    cs:__imp_ReadFile
0x383868ffa  test    eax, eax
0x383868ffc  jnz     loc_38389594F
0x383869002  call    cs:__imp_GetLastError
0x383869008  mov     ebx, eax
0x38386900a  cmp     eax, 0EAh
0x38386900f  jz      loc_3838FA3D8
0x383869015  cmp     eax, 3E5h
0x38386901a  jnz     loc_3838FA44F
0x383869020  jmp     short $+2
0x383869022  call    cs:__imp_GetTickCount
0x383869028  mov     ebp, eax
0x38386902a  mov     edx, r14d; dwMilliseconds
0x38386902d  mov     rcx, [rsi+18h]; hHandle
0x383869031  call    cs:__imp_WaitForSingleObject
0x383869037  mov     ebx, eax
0x383869039  cmp     eax, 0FFFFFFFFh
0x38386903c  jz      loc_3838FA6FF
0x383869042  cmp     eax, 102h
0x383869047  jz      loc_3838690E8
0x38386904d  xor     r9d, r9d; bWait
0x383869050  lea     r8, [rsp+68h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x383869055  mov     rdx, rsi; lpOverlapped
0x383869058  mov     rcx, [rdi+40h]; hFile
0x38386905c  call    cs:__imp_GetOverlappedResult
0x383869062  test    eax, eax
0x383869064  jz      loc_3838FA405
0x38386906a  mov     eax, [rsp+68h+NumberOfBytesTransferred]
0x38386906e  mov     [rsi+60h], eax
0x383869071  mov     [r15], rsi
0x383869074  mov     eax, cs:_bidGblFlags
0x38386907a  and     eax, 24002h
0x38386907f  cmp     eax, 24002h
0x383869084  jz      loc_3838FA5F6
0x38386908a  mov     eax, cs:_bidGblFlags
0x383869090  and     eax, 24002h
0x383869095  cmp     eax, 24002h
0x38386909a  jz      loc_3838FA629
0x3838690a0  mov     eax, cs:_bidGblFlags
0x3838690a6  and     eax, 20002h
0x3838690ab  cmp     eax, 20002h
0x3838690b0  jz      loc_3838FA652
0x3838690b6  cmp     [rsp+68h+arg_8], 0FFFFFFFFFFFFFFFFh
0x3838690bc  jnz     loc_3838FA683
0x3838690c2  xor     eax, eax
0x3838690c4  jmp     short $+2
0x3838690c6  lea     r11, [rsp+68h+var_28]
0x3838690cb  mov     rbx, [r11+40h]
0x3838690cf  mov     rbp, [r11+48h]
0x3838690d3  mov     rsp, r11
0x3838690d6  pop     r15
0x3838690d8  pop     r14
0x3838690da  pop     r12
0x3838690dc  pop     rdi
0x3838690dd  pop     rsi
0x3838690de  retn
0x3838690df  mov     [rdi+78h], r12
0x3838690e3  jmp     loc_383869022
0x3838690e8  mov     [rdi+78h], rsi
0x3838690ec  test    byte ptr cs:_bidGblFlags, 2
0x3838690f3  jnz     loc_3838FA6B7
0x3838690f9  mov     edx, 102h
0x3838690fe  mov     r8d, 0C3BFh
0x383869104  mov     ecx, [rdi+70h]
0x383869107  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x38386910c  jmp     short $+2
0x38386910e  mov     eax, cs:_bidGblFlags
0x383869114  and     eax, 20002h
0x383869119  cmp     eax, 20002h
0x38386911e  jz      loc_3838FA768
0x383869124  cmp     [rsp+68h+arg_8], 0FFFFFFFFFFFFFFFFh
0x38386912a  jnz     loc_3838FA799
0x383869130  mov     eax, ebx
0x383869132  jmp     short loc_3838690C6
0x38389594f  mov     r9d, 1; bWait
0x383895955  lea     r8, [rsp+68h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x38389595a  mov     rdx, rsi; lpOverlapped
0x38389595d  mov     rcx, [rdi+40h]; hFile
0x383895961  call    cs:__imp_GetOverlappedResult
0x383895967  test    eax, eax
0x383895969  jz      loc_3838FA3E8
0x38389596f  cmp     ebx, 3E5h
0x383895975  jnz     loc_38386906A
0x38389597b  jmp     loc_3838FA400
0x3838fa3a7  mov     rax, cs:off_383B48688; "<Np::ReadSync|API|SNI> %u#, ppNewPacket"...
0x3838fa3ae  test    rax, rax
0x3838fa3b1  jz      loc_383868F96
0x3838fa3b7  mov     [r11-48h], r8d
0x3838fa3bb  mov     r9, rdx
0x3838fa3be  mov     r8d, [rcx+2Ch]
0x3838fa3c2  mov     rdx, cs:off_383B48688; "<Np::ReadSync|API|SNI> %u#, ppNewPacket"...
0x3838fa3c9  lea     rcx, [r11+10h]
0x3838fa3cd  call    _bidScopeEnterA
0x3838fa3d2  nop
0x3838fa3d3  jmp     loc_383868F96
0x3838fa3d8  cmp     eax, 3E5h
0x3838fa3dd  jnz     loc_38389594F
0x3838fa3e3  jmp     loc_383869022
0x3838fa3e8  call    cs:__imp_GetLastError
0x3838fa3ee  mov     ebx, eax
0x3838fa3f0  cmp     eax, 0EAh
0x3838fa3f5  jz      loc_38389596F
0x3838fa3fb  jmp     loc_3838FA48E
0x3838fa400  jmp     loc_383869022
0x3838fa405  call    cs:__imp_GetLastError
0x3838fa40b  mov     ebx, eax
0x3838fa40d  cmp     eax, 3E3h
0x3838fa412  jnz     loc_3838FA587
0x3838fa418  mov     rcx, rsi; struct SNI_Packet *
0x3838fa41b  call    SNIPacketRelease
0x3838fa420  mov     [rdi+78h], r12
0x3838fa424  mov     [rsp+68h+NumberOfBytesTransferred], r12d
0x3838fa429  mov     ebx, r12d
0x3838fa42c  cmp     r14d, 0FFFFFFFFh
0x3838fa430  jz      loc_383868FB0
0x3838fa436  call    cs:__imp_GetTickCount
0x3838fa43c  sub     ebp, eax
0x3838fa43e  add     r14d, ebp
0x3838fa441  test    r14d, r14d
0x3838fa444  jle     loc_3838FA52A
0x3838fa44a  jmp     loc_383868FB0
0x3838fa44f  test    byte ptr cs:_bidGblFlags, 2
0x3838fa456  jz      loc_3838FA5D5
0x3838fa45c  mov     rax, cs:off_383B46508; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x3838fa463  test    rax, rax
0x3838fa466  jz      loc_3838FA5D5
0x3838fa46c  mov     ecx, 0C3B4h; unsigned int
0x3838fa471  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838fa476  mov     r8, cs:off_383B46508; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x3838fa47d  mov     edx, 14E000h
0x3838fa482  mov     rcx, cs:off_383B43E88; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa489  jmp     loc_3838FA5C4
0x3838fa48e  test    byte ptr cs:_bidGblFlags, 2
0x3838fa495  jz      loc_3838FA5D5
0x3838fa49b  mov     rax, cs:off_383B46500; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x3838fa4a2  test    rax, rax
0x3838fa4a5  jz      loc_3838FA5D5
0x3838fa4ab  mov     ecx, 0C3B4h; unsigned int
0x3838fa4b0  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838fa4b5  mov     r8, cs:off_383B46500; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x3838fa4bc  mov     edx, 152000h
0x3838fa4c1  mov     rcx, cs:off_383B43E80; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa4c8  jmp     loc_3838FA5C4
0x3838fa4cd  mov     ebx, 0Eh
0x3838fa4d2  test    byte ptr cs:_bidGblFlags, 2
0x3838fa4d9  jz      short loc_3838FA515
0x3838fa4db  mov     rax, cs:off_383B46510; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x3838fa4e2  test    rax, rax
0x3838fa4e5  jz      short loc_3838FA515
0x3838fa4e7  mov     ecx, 0C3B4h; unsigned int
0x3838fa4ec  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838fa4f1  mov     [rsp+68h+var_40], ebx
0x3838fa4f5  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x3838fa4f9  mov     r9d, [rdi+70h]
0x3838fa4fd  mov     r8, cs:off_383B46510; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x3838fa504  mov     edx, 146000h
0x3838fa509  mov     rcx, cs:off_383B43E90; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa510  call    _bidTraceA
0x3838fa515  mov     r8d, 0C3B4h
0x3838fa51b  mov     edx, ebx
0x3838fa51d  mov     ecx, [rdi+70h]
0x3838fa520  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3838fa525  jmp     loc_38386910E
0x3838fa52a  mov     ebx, 102h
0x3838fa52f  test    byte ptr cs:_bidGblFlags, 2
0x3838fa536  jz      short loc_3838FA572
0x3838fa538  mov     rax, cs:off_383B464E8; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x3838fa53f  test    rax, rax
0x3838fa542  jz      short loc_3838FA572
0x3838fa544  mov     ecx, 0C3BFh; unsigned int
0x3838fa549  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838fa54e  mov     [rsp+68h+var_40], ebx
0x3838fa552  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x3838fa556  mov     r9d, [rdi+70h]
0x3838fa55a  mov     r8, cs:off_383B464E8; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x3838fa561  mov     edx, 161000h
0x3838fa566  mov     rcx, cs:off_383B43E68; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa56d  call    _bidTraceA
0x3838fa572  mov     edx, ebx
0x3838fa574  mov     r8d, 0C3BFh
0x3838fa57a  mov     ecx, [rdi+70h]
0x3838fa57d  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3838fa582  jmp     loc_38386910E
0x3838fa587  cmp     eax, 0EAh
0x3838fa58c  jz      loc_38386906A
0x3838fa592  test    byte ptr cs:_bidGblFlags, 2
0x3838fa599  jz      short loc_3838FA5D5
0x3838fa59b  mov     rax, cs:off_383B464E0; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x3838fa5a2  test    rax, rax
0x3838fa5a5  jz      short loc_3838FA5D5
0x3838fa5a7  mov     ecx, 0C3B4h; unsigned int
0x3838fa5ac  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838fa5b1  mov     r8, cs:off_383B464E0; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x3838fa5b8  mov     edx, 163800h
0x3838fa5bd  mov     rcx, cs:off_383B43E60; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa5c4  mov     [rsp+68h+var_40], ebx
0x3838fa5c8  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x3838fa5cc  mov     r9d, [rdi+70h]
0x3838fa5d0  call    _bidTraceA
0x3838fa5d5  mov     r8d, 0C3B4h
0x3838fa5db  mov     edx, ebx
0x3838fa5dd  mov     ecx, [rdi+70h]
0x3838fa5e0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x3838fa5e5  cmp     ebx, 102h
0x3838fa5eb  jz      loc_38386910E
0x3838fa5f1  jmp     loc_3838FA757
0x3838fa5f6  mov     rax, cs:off_383B464D8; "<Np::ReadSync|SNI> Receive Packet, Byte"...
0x3838fa5fd  test    rax, rax
0x3838fa600  jz      loc_38386908A
0x3838fa606  mov     r9d, [rsp+68h+NumberOfBytesTransferred]
0x3838fa60b  mov     r8, cs:off_383B464D8; "<Np::ReadSync|SNI> Receive Packet, Byte"...
0x3838fa612  mov     edx, 167800h
0x3838fa617  mov     rcx, cs:off_383B43E58; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa61e  call    _bidTraceA
0x3838fa623  nop
0x3838fa624  jmp     loc_38386908A
0x3838fa629  mov     r8d, [rsi+68h]
0x3838fa62d  add     r8, [rsi+58h]
0x3838fa631  mov     [rsp+68h+lpOverlapped], r12
0x3838fa636  mov     r9d, [rsp+68h+NumberOfBytesTransferred]
0x3838fa63b  mov     edx, 10h
0x3838fa640  mov     rcx, cs:_bidID
0x3838fa647  call    _bidWriteBin
0x3838fa64c  nop
0x3838fa64d  jmp     loc_3838690A0
0x3838fa652  mov     rax, cs:off_383B464D0; "<Np::ReadSync|RET|SNI> %d{WINERR}\n"
0x3838fa659  test    rax, rax
0x3838fa65c  jz      loc_3838690B6
0x3838fa662  xor     r9d, r9d
0x3838fa665  mov     r8, cs:off_383B464D0; "<Np::ReadSync|RET|SNI> %d{WINERR}\n"
0x3838fa66c  mov     edx, 168400h
0x3838fa671  mov     rcx, cs:off_383B43E50; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa678  call    _bidTraceA
0x3838fa67d  nop
0x3838fa67e  jmp     loc_3838690B6
0x3838fa683  test    byte ptr cs:_bidGblFlags, 4
0x3838fa68a  jz      loc_3838690C2
0x3838fa690  mov     rcx, cs:_bidID
0x3838fa697  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x3838fa69b  jz      loc_3838690C2
0x3838fa6a1  lea     r9, [rsp+68h+arg_8]
0x3838fa6a6  xor     r8d, r8d
0x3838fa6a9  xor     edx, edx
0x3838fa6ab  call    cs:off_383B15058
0x3838fa6b1  nop
0x3838fa6b2  jmp     loc_3838690C2
0x3838fa6b7  mov     rax, cs:off_383B464F0; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x3838fa6be  test    rax, rax
0x3838fa6c1  jz      loc_3838690F9
0x3838fa6c7  mov     ecx, 0C3BFh; unsigned int
0x3838fa6cc  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x3838fa6d1  mov     [rsp+68h+var_40], 102h
0x3838fa6d9  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x3838fa6dd  mov     r9d, [rdi+70h]
0x3838fa6e1  mov     r8, cs:off_383B464F0; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x3838fa6e8  mov     edx, 15A800h
0x3838fa6ed  mov     rcx, cs:off_383B43E70; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838fa6f4  call    _bidTraceA
0x3838fa6f9  nop
  ... truncated ...
```
