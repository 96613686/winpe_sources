# LocalDB::loadUserInstanceDll(void)

- ea: `0x383ac25f0`
- end: `0x383ac2c31`
- name: `?loadUserInstanceDll@LocalDB@@QEAAKXZ`
- size: `1601`
- prototype: `unsigned int __fastcall(LocalDB *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x383ac2c70`

## callees

- `0x3838434c0`
- `0x383846430`
- `0x38387d8a0`
- `0x383884780`
- `0x38391ac20`
- `0x38391ac40`
- `0x38391ae80`
- `0x383ab0c30`
- `0x383ac1f80`
- `0x383ac25f0`
- `0x383ad74e0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x383ac2b84`
- `KERNEL32!FreeLibrary` at `0x383ac2b84`
- `KERNEL32!GetLastError` at `0x383ac2974`
- `KERNEL32!GetLastError` at `0x383ac2ae3`
- `KERNEL32!GetLastError` at `0x383ac2974`
- `KERNEL32!GetLastError` at `0x383ac2ae3`
- `KERNEL32!GetProcAddress` at `0x383ac2a1f`
- `KERNEL32!GetProcAddress` at `0x383ac2a33`
- `KERNEL32!GetProcAddress` at `0x383ac2a1f`
- `KERNEL32!GetProcAddress` at `0x383ac2a33`
- `KERNEL32!LoadLibraryA` at `0x383ac2962`
- `KERNEL32!LoadLibraryA` at `0x383ac2962`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LocalDB::loadUserInstanceDll(LocalDB *this)
{
  __int64 v2; // rdi
  DWORD LastError; // ebx
  rsize_t v4; // rbp
  unsigned int v5; // r8d
  enum LocalDBErrorState *v6; // r9
  const char *v7; // r9
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  const char *v13; // r9
  unsigned int v14; // eax
  unsigned int v15; // eax
  HMODULE LibraryA; // rax
  HMODULE v17; // rdi
  unsigned int v18; // eax
  FARPROC ProcAddress; // rax
  unsigned int v21; // eax
  int v22; // [rsp+20h] [rbp-168h]
  char v23[4]; // [rsp+30h] [rbp-158h] BYREF
  __int64 v24; // [rsp+38h] [rbp-150h]
  rsize_t DestinationSize[2]; // [rsp+40h] [rbp-148h] BYREF
  int v26; // [rsp+50h] [rbp-138h]
  __int64 v27; // [rsp+58h] [rbp-130h]
  CHAR LibFileName[272]; // [rsp+60h] [rbp-128h] BYREF

  v27 = -2;
  v2 = -1;
  v24 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && *(_QWORD *)&off_383B48AF8 && bidID != -1 )
  {
    v22 = off_383B48AF8;
    off_383B15048();
  }
  LastError = 0;
  if ( *(_QWORD *)this )
    goto LABEL_76;
  v4 = *((_QWORD *)this + 3);
  DestinationSize[1] = v4;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v4 + 16) + 32LL) + 8LL))(*(_QWORD *)(v4 + 16) + 32LL);
  v26 = 1;
  if ( *(_QWORD *)this )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v4 + 16) + 32LL) + 24LL))(*(_QWORD *)(v4 + 16) + 32LL);
    goto LABEL_76;
  }
  LastError = NLregC::CSgetUserInstanceDllPath((NLregC *)LibFileName, v23, v5, v6);
  if ( LastError )
  {
    if ( (bidGblFlags & 2) != 0 && off_383B47920[0] )
    {
      v8 = MapLocalDBErrorStateToCode(*(unsigned int *)v23);
      v9 = SniErrorIdFromStringId(v8);
      bidTraceA(off_383B452A0[0], 235520, off_383B47920[0], 9, v9);
    }
    switch ( *(_DWORD *)v23 )
    {
      case 0:
        v10 = 50152;
        break;
      case 1:
        goto LABEL_16;
      case 2:
        v10 = 50154;
        break;
      case 3:
        v10 = 50155;
        break;
      default:
LABEL_16:
        v10 = 50153;
        break;
    }
    SNISetLastError(9, LastError, v10);
    if ( (bidGblFlags & 2) != 0 && off_383B47918[0] )
      bidTraceA(off_383B45298[0], 236544, off_383B47918[0], LastError, v22);
LABEL_55:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v4 + 16) + 32LL) + 24LL))(*(_QWORD *)(v4 + 16) + 32LL);
    goto LABEL_74;
  }
  v11 = -1;
  do
    ++v11;
  while ( LibFileName[v11] );
  v12 = v11 + 1;
  if ( LibFileName[0] )
  {
    if ( LibFileName[v12 - 1] )
    {
      LastError = 87;
LABEL_31:
      if ( (bidGblFlags & 2) != 0 && off_383B47910[0] )
      {
        v14 = SniErrorIdFromStringId(0xC3EBu);
        bidTraceA(off_383B45290[0], 245760, off_383B47910[0], 9, v14);
      }
      SNISetLastError(9, LastError, 50155);
      if ( (bidGblFlags & 2) != 0 && off_383B47908[0] )
        bidTraceA(off_383B45288[0], 246784, off_383B47908[0], LastError, v22);
      goto LABEL_55;
    }
    LastError = StrTrimRight_Sys(LibFileName, v12, DestinationSize, v7, v22);
    if ( LastError )
      goto LABEL_31;
    LastError = StrTrimLeft_Sys(LibFileName, DestinationSize[0], DestinationSize, v13, v22);
    if ( LastError )
      goto LABEL_31;
  }
  LastError = 0;
  do
    ++v2;
  while ( LibFileName[v2] );
  if ( !v2 )
  {
    LastError = 13;
    if ( (bidGblFlags & 2) != 0 && off_383B47900[0] )
    {
      v15 = SniErrorIdFromStringId(0xC3EBu);
      bidTraceA(off_383B45280[0], 256000, off_383B47900[0], 9, v15);
    }
    SNISetLastError(9, 13, 50155);
    if ( (bidGblFlags & 2) != 0 && off_383B478F8[0] )
      bidTraceA(off_383B45278[0], 257024, off_383B478F8[0], 13, v22);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v4 + 16) + 32LL) + 24LL))(*(_QWORD *)(v4 + 16) + 32LL);
LABEL_75:
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 1) = 0;
LABEL_76:
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B478C8[0] )
      bidTraceA(off_383B45248[0], 316416, off_383B478C8[0], LastError, v22);
    if ( v24 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return LastError;
  }
  LibraryA = LoadLibraryA(LibFileName);
  v17 = LibraryA;
  if ( !LibraryA )
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_383B478F0[0] )
    {
      v18 = SniErrorIdFromStringId(0xC3ECu);
      bidTraceA(off_383B45270[0], 267264, off_383B478F0[0], 9, v18);
    }
    SNISetLastError(9, LastError, 50156);
    if ( (bidGblFlags & 2) != 0 && off_383B478E8[0] )
      bidTraceA(off_383B45268[0], 268288, off_383B478E8[0], LastError, v22);
    goto LABEL_55;
  }
  *((_QWORD *)this + 2) = GetProcAddress(LibraryA, "LocalDBStartInstance");
  ProcAddress = GetProcAddress(v17, "LocalDBFormatMessage");
  *((_QWORD *)this + 1) = ProcAddress;
  if ( !*((_QWORD *)this + 2) || !ProcAddress )
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_383B478E0[0] )
    {
      v21 = SniErrorIdFromStringId(0xC3EDu);
      bidTraceA(off_383B45260[0], 283648, off_383B478E0[0], 9, v21);
    }
    SNISetLastError(9, LastError, 50157);
    if ( (bidGblFlags & 2) != 0 && off_383B478D8[0] )
      bidTraceA(off_383B45258[0], 284672, off_383B478D8[0], LastError, v22);
    goto LABEL_73;
  }
  if ( _InterlockedExchange64((volatile __int64 *)this, (__int64)v17) )
  {
LABEL_73:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v4 + 16) + 32LL) + 24LL))(*(_QWORD *)(v4 + 16) + 32LL);
    FreeLibrary(v17);
LABEL_74:
    if ( !LastError )
      goto LABEL_76;
    goto LABEL_75;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(v4 + 16) + 32LL) + 24LL))(*(_QWORD *)(v4 + 16) + 32LL);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B478D0[0] )
    bidTraceA(off_383B45250[0], 299008, off_383B478D0[0], 0, v22);
  if ( v24 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return 0;
}

```

## disassembly

```asm
0x383ac25f0  mov     rax, rsp
0x383ac25f3  push    rdi
0x383ac25f4  sub     rsp, 180h
0x383ac25fb  mov     [rsp+188h+var_130], 0FFFFFFFFFFFFFFFEh
0x383ac2604  mov     [rax+10h], rbx
0x383ac2608  mov     [rax+18h], rbp
0x383ac260c  mov     [rax+20h], rsi
0x383ac2610  mov     rax, cs:__security_cookie
0x383ac2617  xor     rax, rsp
0x383ac261a  mov     [rsp+188h+var_18], rax
0x383ac2622  mov     rsi, rcx
0x383ac2625  or      rdi, 0FFFFFFFFFFFFFFFFh
0x383ac2629  mov     [rsp+188h+var_150], rdi
0x383ac262e  mov     eax, cs:_bidGblFlags
0x383ac2634  and     eax, 20004h
0x383ac2639  cmp     eax, 20004h
0x383ac263e  jnz     short loc_383AC2681
0x383ac2640  mov     rax, cs:off_383B48AF8; "<LocalDB::loadUserInstanceDll|API|SNI> "...
0x383ac2647  test    rax, rax
0x383ac264a  jz      short loc_383AC2681
0x383ac264c  cmp     cs:_bidID, rdi
0x383ac2653  jz      short loc_383AC2681
0x383ac2655  mov     [rsp+188h+var_160], 0
0x383ac265e  mov     rax, cs:off_383B48AF8; "<LocalDB::loadUserInstanceDll|API|SNI> "...
0x383ac2665  mov     qword ptr [rsp+188h+var_168], rax; int
0x383ac266a  lea     r9, [rsp+188h+var_150]
0x383ac266f  xor     r8d, r8d
0x383ac2672  xor     edx, edx
0x383ac2674  mov     rcx, cs:_bidID
0x383ac267b  call    cs:off_383B15048
0x383ac2681  xor     ebx, ebx
0x383ac2683  mov     rax, [rsi]
0x383ac2686  test    rax, rax
0x383ac2689  jnz     loc_383AC2B9E
0x383ac268f  mov     rbp, [rsi+18h]
0x383ac2693  mov     [rsp+188h+var_140], rbp
0x383ac2698  mov     rcx, [rbp+10h]
0x383ac269c  add     rcx, 20h ; ' '
0x383ac26a0  mov     rax, [rcx]
0x383ac26a3  call    qword ptr [rax+8]
0x383ac26a6  mov     [rsp+188h+var_138], 1
0x383ac26ae  mov     rax, [rsi]
0x383ac26b1  test    rax, rax
0x383ac26b4  jz      short loc_383AC26C9
0x383ac26b6  mov     rcx, [rbp+10h]
0x383ac26ba  add     rcx, 20h ; ' '
0x383ac26be  mov     rax, [rcx]
0x383ac26c1  call    qword ptr [rax+18h]
0x383ac26c4  jmp     loc_383AC2B9E
0x383ac26c9  lea     rdx, [rsp+188h+var_158]; char *
0x383ac26ce  lea     rcx, [rsp+188h+LibFileName]; this
0x383ac26d3  call    ?CSgetUserInstanceDllPath@NLregC@@QEAAJPEADKPEAW4LocalDBErrorState@@@Z; NLregC::CSgetUserInstanceDllPath(char *,ulong,LocalDBErrorState *)
0x383ac26d8  mov     ebx, eax
0x383ac26da  test    eax, eax
0x383ac26dc  jz      loc_383AC27AE
0x383ac26e2  test    byte ptr cs:_bidGblFlags, 2
0x383ac26e9  jz      short loc_383AC272D
0x383ac26eb  mov     rcx, cs:off_383B47920; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac26f2  test    rcx, rcx
0x383ac26f5  jz      short loc_383AC272D
0x383ac26f7  mov     ecx, dword ptr [rsp+188h+var_158]
0x383ac26fb  call    ?MapLocalDBErrorStateToCode@@YAKW4LocalDBErrorState@@@Z; MapLocalDBErrorStateToCode(LocalDBErrorState)
0x383ac2700  mov     ecx, eax; unsigned int
0x383ac2702  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383ac2707  mov     dword ptr [rsp+188h+var_160], ebx
0x383ac270b  mov     [rsp+188h+var_168], eax
0x383ac270f  mov     r9d, 9
0x383ac2715  mov     r8, cs:off_383B47920; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac271c  mov     edx, 39800h
0x383ac2721  mov     rcx, cs:off_383B452A0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac2728  call    _bidTraceA
0x383ac272d  mov     ecx, dword ptr [rsp+188h+var_158]
0x383ac2731  test    ecx, ecx
0x383ac2733  jz      short loc_383AC2756
0x383ac2735  dec     ecx
0x383ac2737  jz      short loc_383AC2741
0x383ac2739  dec     ecx
0x383ac273b  jz      short loc_383AC274F
0x383ac273d  dec     ecx
0x383ac273f  jz      short loc_383AC2748
0x383ac2741  mov     edi, 0C3E9h
0x383ac2746  jmp     short loc_383AC275B
0x383ac2748  mov     edi, 0C3EBh
0x383ac274d  jmp     short loc_383AC275B
0x383ac274f  mov     edi, 0C3EAh
0x383ac2754  jmp     short loc_383AC275B
0x383ac2756  mov     edi, 0C3E8h
0x383ac275b  mov     r8d, edi
0x383ac275e  mov     edx, ebx
0x383ac2760  mov     ecx, 9
0x383ac2765  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x383ac276a  test    byte ptr cs:_bidGblFlags, 2
0x383ac2771  jz      short loc_383AC279B
0x383ac2773  mov     rax, cs:off_383B47918; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac277a  test    rax, rax
0x383ac277d  jz      short loc_383AC279B
0x383ac277f  mov     r9d, ebx
0x383ac2782  mov     r8, cs:off_383B47918; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac2789  mov     edx, 39C00h
0x383ac278e  mov     rcx, cs:off_383B45298; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac2795  call    _bidTraceA
0x383ac279a  nop
0x383ac279b  mov     rcx, [rbp+10h]
0x383ac279f  add     rcx, 20h ; ' '
0x383ac27a3  mov     rax, [rcx]
0x383ac27a6  call    qword ptr [rax+18h]
0x383ac27a9  jmp     loc_383AC2B8A
0x383ac27ae  lea     rax, [rsp+188h+LibFileName]
0x383ac27b3  mov     rdx, rdi
0x383ac27b6  inc     rdx
0x383ac27b9  cmp     byte ptr [rdx+rax], 0
0x383ac27bd  jnz     short loc_383AC27B6
0x383ac27bf  inc     rdx; unsigned __int64
0x383ac27c2  cmp     [rsp+188h+LibFileName], 0
0x383ac27c7  jz      loc_383AC28A8
0x383ac27cd  cmp     byte ptr [rsp+rdx+188h+var_130+7], 0
0x383ac27d2  jz      short loc_383AC27DB
0x383ac27d4  mov     ebx, 57h ; 'W'
0x383ac27d9  jmp     short loc_383AC280E
0x383ac27db  lea     r8, [rsp+188h+DestinationSize]; unsigned __int64 *
0x383ac27e0  lea     rcx, [rsp+188h+LibFileName]; lpCurrentChar
0x383ac27e5  call    ?StrTrimRight_Sys@@YAKPEAD_KPEA_KPEBDH@Z; StrTrimRight_Sys(char *,unsigned __int64,unsigned __int64 *,char const *,int)
0x383ac27ea  mov     ebx, eax
0x383ac27ec  test    eax, eax
0x383ac27ee  jnz     short loc_383AC280E
0x383ac27f0  lea     r8, [rsp+188h+DestinationSize]; unsigned __int64 *
0x383ac27f5  mov     rdx, [rsp+188h+DestinationSize]; DestinationSize
0x383ac27fa  lea     rcx, [rsp+188h+LibFileName]; Source
0x383ac27ff  call    ?StrTrimLeft_Sys@@YAKPEAD_KPEA_KPEBDH@Z; StrTrimLeft_Sys(char *,unsigned __int64,unsigned __int64 *,char const *,int)
0x383ac2804  mov     ebx, eax
0x383ac2806  test    eax, eax
0x383ac2808  jz      loc_383AC28A8
0x383ac280e  mov     edi, 0C3EBh
0x383ac2813  test    byte ptr cs:_bidGblFlags, 2
0x383ac281a  jz      short loc_383AC2855
0x383ac281c  mov     rax, cs:off_383B47910; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac2823  test    rax, rax
0x383ac2826  jz      short loc_383AC2855
0x383ac2828  mov     ecx, edi; unsigned int
0x383ac282a  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383ac282f  mov     dword ptr [rsp+188h+var_160], ebx
0x383ac2833  mov     [rsp+188h+var_168], eax
0x383ac2837  mov     r9d, 9
0x383ac283d  mov     r8, cs:off_383B47910; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac2844  mov     edx, 3C000h
0x383ac2849  mov     rcx, cs:off_383B45290; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac2850  call    _bidTraceA
0x383ac2855  mov     r8d, edi
0x383ac2858  mov     edx, ebx
0x383ac285a  mov     ecx, 9
0x383ac285f  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x383ac2864  test    byte ptr cs:_bidGblFlags, 2
0x383ac286b  jz      short loc_383AC2895
0x383ac286d  mov     rax, cs:off_383B47908; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac2874  test    rax, rax
0x383ac2877  jz      short loc_383AC2895
0x383ac2879  mov     r9d, ebx
0x383ac287c  mov     r8, cs:off_383B47908; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac2883  mov     edx, 3C400h
0x383ac2888  mov     rcx, cs:off_383B45288; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac288f  call    _bidTraceA
0x383ac2894  nop
0x383ac2895  mov     rcx, [rbp+10h]
0x383ac2899  add     rcx, 20h ; ' '
0x383ac289d  mov     rax, [rcx]
0x383ac28a0  call    qword ptr [rax+18h]
0x383ac28a3  jmp     loc_383AC2B8A
0x383ac28a8  xor     ebx, ebx
0x383ac28aa  lea     rax, [rsp+188h+LibFileName]
0x383ac28af  nop
0x383ac28b0  inc     rdi
0x383ac28b3  cmp     byte ptr [rax+rdi], 0
0x383ac28b7  jnz     short loc_383AC28B0
0x383ac28b9  test    rdi, rdi
0x383ac28bc  jnz     loc_383AC295D
0x383ac28c2  lea     ebx, [rdi+0Dh]
0x383ac28c5  mov     edi, 0C3EBh
0x383ac28ca  test    byte ptr cs:_bidGblFlags, 2
0x383ac28d1  jz      short loc_383AC290A
0x383ac28d3  mov     rax, cs:off_383B47900; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac28da  test    rax, rax
0x383ac28dd  jz      short loc_383AC290A
0x383ac28df  mov     ecx, edi; unsigned int
0x383ac28e1  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383ac28e6  mov     dword ptr [rsp+188h+var_160], ebx
0x383ac28ea  mov     [rsp+188h+var_168], eax
0x383ac28ee  lea     r9d, [rbx-4]
0x383ac28f2  mov     r8, cs:off_383B47900; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac28f9  mov     edx, 3E800h
0x383ac28fe  mov     rcx, cs:off_383B45280; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac2905  call    _bidTraceA
0x383ac290a  mov     r8d, edi
0x383ac290d  mov     edx, ebx
0x383ac290f  mov     ecx, 9
0x383ac2914  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x383ac2919  test    byte ptr cs:_bidGblFlags, 2
0x383ac2920  jz      short loc_383AC294A
0x383ac2922  mov     rax, cs:off_383B478F8; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac2929  test    rax, rax
0x383ac292c  jz      short loc_383AC294A
0x383ac292e  mov     r9d, ebx
0x383ac2931  mov     r8, cs:off_383B478F8; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac2938  mov     edx, 3EC00h
0x383ac293d  mov     rcx, cs:off_383B45278; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac2944  call    _bidTraceA
0x383ac2949  nop
0x383ac294a  mov     rcx, [rbp+10h]
0x383ac294e  add     rcx, 20h ; ' '
0x383ac2952  mov     rax, [rcx]
0x383ac2955  call    qword ptr [rax+18h]
0x383ac2958  jmp     loc_383AC2B8E
0x383ac295d  lea     rcx, [rsp+188h+LibFileName]; lpLibFileName
0x383ac2962  call    cs:__imp_LoadLibraryA
0x383ac2968  mov     rdi, rax
0x383ac296b  test    rax, rax
0x383ac296e  jnz     loc_383AC2A15
0x383ac2974  call    cs:__imp_GetLastError
0x383ac297a  mov     ebx, eax
0x383ac297c  test    byte ptr cs:_bidGblFlags, 2
0x383ac2983  jz      short loc_383AC29BF
0x383ac2985  mov     rax, cs:off_383B478F0; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac298c  test    rax, rax
0x383ac298f  jz      short loc_383AC29BF
0x383ac2991  mov     ecx, 0C3ECh; unsigned int
0x383ac2996  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383ac299b  mov     dword ptr [rsp+188h+var_160], ebx
0x383ac299f  mov     [rsp+188h+var_168], eax
0x383ac29a3  lea     r9d, [rdi+9]
0x383ac29a7  mov     r8, cs:off_383B478F0; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac29ae  mov     edx, 41400h
0x383ac29b3  mov     rcx, cs:off_383B45270; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac29ba  call    _bidTraceA
0x383ac29bf  mov     r8d, 0C3ECh
0x383ac29c5  mov     edx, ebx
0x383ac29c7  mov     ecx, 9
0x383ac29cc  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x383ac29d1  test    byte ptr cs:_bidGblFlags, 2
0x383ac29d8  jz      short loc_383AC2A02
0x383ac29da  mov     rax, cs:off_383B478E8; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac29e1  test    rax, rax
0x383ac29e4  jz      short loc_383AC2A02
0x383ac29e6  mov     r9d, ebx
0x383ac29e9  mov     r8, cs:off_383B478E8; "<LocalDB::loadUserInstanceDll|ERR|SNI> "...
0x383ac29f0  mov     edx, 41800h
0x383ac29f5  mov     rcx, cs:off_383B45268; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac29fc  call    _bidTraceA
0x383ac2a01  nop
0x383ac2a02  mov     rcx, [rbp+10h]
0x383ac2a06  add     rcx, 20h ; ' '
0x383ac2a0a  mov     rax, [rcx]
0x383ac2a0d  call    qword ptr [rax+18h]
0x383ac2a10  jmp     loc_383AC2B8A
0x383ac2a15  lea     rdx, aLocaldbstartin; "LocalDBStartInstance"
0x383ac2a1c  mov     rcx, rax; hModule
0x383ac2a1f  call    cs:__imp_GetProcAddress
0x383ac2a25  mov     [rsi+10h], rax
0x383ac2a29  lea     rdx, aLocaldbformatm; "LocalDBFormatMessage"
0x383ac2a30  mov     rcx, rdi; hModule
0x383ac2a33  call    cs:__imp_GetProcAddress
0x383ac2a39  mov     [rsi+8], rax
0x383ac2a3d  cmp     qword ptr [rsi+10h], 0
0x383ac2a42  jz      loc_383AC2AE3
0x383ac2a48  test    rax, rax
0x383ac2a4b  jz      loc_383AC2AE3
0x383ac2a51  mov     rax, rdi
0x383ac2a54  xchg    rax, [rsi]
0x383ac2a57  test    rax, rax
0x383ac2a5a  jz      short loc_383AC2A61
0x383ac2a5c  jmp     loc_383AC2B73
0x383ac2a61  mov     rcx, [rbp+10h]
0x383ac2a65  add     rcx, 20h ; ' '
0x383ac2a69  mov     rax, [rcx]
0x383ac2a6c  call    qword ptr [rax+18h]
0x383ac2a6f  mov     r11d, cs:_bidGblFlags
0x383ac2a76  and     r11d, 20002h
0x383ac2a7d  cmp     r11d, 20002h
0x383ac2a84  jnz     short loc_383AC2AAE
0x383ac2a86  mov     rax, cs:off_383B478D0; "<LocalDB::loadUserInstanceDll|RET|SNI> "...
0x383ac2a8d  test    rax, rax
0x383ac2a90  jz      short loc_383AC2AAE
0x383ac2a92  xor     r9d, r9d
0x383ac2a95  mov     r8, cs:off_383B478D0; "<LocalDB::loadUserInstanceDll|RET|SNI> "...
0x383ac2a9c  mov     edx, 49000h
0x383ac2aa1  mov     rcx, cs:off_383B45250; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac2aa8  call    _bidTraceA
0x383ac2aad  nop
0x383ac2aae  cmp     [rsp+188h+var_150], 0FFFFFFFFFFFFFFFFh
0x383ac2ab4  jz      short loc_383AC2ADC
0x383ac2ab6  test    byte ptr cs:_bidGblFlags, 4
0x383ac2abd  jz      short loc_383AC2ADC
0x383ac2abf  mov     rcx, cs:_bidID
0x383ac2ac6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ac2aca  jz      short loc_383AC2ADC
0x383ac2acc  lea     r9, [rsp+188h+var_150]
0x383ac2ad1  xor     r8d, r8d
0x383ac2ad4  xor     edx, edx
0x383ac2ad6  call    cs:off_383B15058
0x383ac2adc  xor     eax, eax
0x383ac2ade  jmp     loc_383AC2C08
0x383ac2ae3  call    cs:__imp_GetLastError
  ... truncated ...
```
