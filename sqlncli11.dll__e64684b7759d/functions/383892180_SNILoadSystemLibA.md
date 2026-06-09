# SNILoadSystemLibA

- ea: `0x383892180`
- end: `0x383892446`
- name: `SNILoadSystemLibA`
- size: `710`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x3838913f0`
- `0x383891c80`
- `0x383891ef0`
- `0x3838946a0`
- `0x383ab2540`
- `0x383ac8520`
- `0x383ad9bc0`

## callees

- `0x3838434c0`
- `0x383892180`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x3838f835c`
- `KERNEL32!GetLastError` at `0x3838f84b2`
- `KERNEL32!GetLastError` at `0x3838f835c`
- `KERNEL32!GetLastError` at `0x3838f84b2`
- `KERNEL32!SetLastError` at `0x3838f85f2`
- `KERNEL32!SetLastError` at `0x3838f85f2`
- `KERNEL32!GetSystemDirectoryA` at `0x383892261`
- `KERNEL32!GetSystemDirectoryA` at `0x383892261`
- `KERNEL32!LoadLibraryA` at `0x3838923c2`
- `KERNEL32!LoadLibraryA` at `0x3838923c2`

## pseudocode

```c
HMODULE __fastcall SNILoadSystemLibA(CHAR *a1)
{
  HMODULE LibraryA; // rdi
  DWORD LastError; // esi
  CHAR *v4; // rax
  int v5; // edx
  __int64 v6; // rcx
  UINT SystemDirectoryA; // eax
  __int64 v8; // rcx
  CHAR *v9; // rax
  int v10; // r10d
  CHAR *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r8
  const char *v14; // r11
  CHAR v15; // r9
  __int64 v16; // rcx
  CHAR *v17; // rax
  int v18; // r10d
  CHAR *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  signed __int64 v22; // r9
  CHAR v23; // r8
  unsigned __int64 v25; // rbx
  __int64 v26; // r8
  char *v27; // r8
  char *v28; // rcx
  CHAR *v29; // r9
  __int64 v30; // rdx
  DWORD v31; // eax
  __int64 v32; // [rsp+30h] [rbp-148h] BYREF
  CHAR *v33; // [rsp+38h] [rbp-140h]
  CHAR Buffer[272]; // [rsp+40h] [rbp-138h] BYREF

  v32 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48508[0] )
    bidScopeEnterA(&v32, off_383B48508[0], a1);
  LibraryA = 0;
  Buffer[0] = 0;
  LastError = 0;
  if ( !a1 )
  {
    v5 = -2147024809;
LABEL_67:
    v33 = 0;
    LastError = v5;
    if ( (bidGblFlags & 2) == 0 || !off_383B45EF0[0] )
      goto LABEL_42;
    v27 = off_383B45EF0[0];
    v28 = off_383B43870[0];
    v29 = a1;
    v30 = 5513216;
LABEL_73:
    bidTraceA(v28, v30, v27, v29);
    goto LABEL_42;
  }
  v4 = a1;
  v5 = 0;
  v6 = 260;
  while ( *v4 )
  {
    ++v4;
    if ( !--v6 )
    {
      v5 = -2147024809;
      v25 = 0;
      goto LABEL_10;
    }
  }
  v25 = 260 - v6;
LABEL_10:
  v33 = (CHAR *)v25;
  if ( v5 < 0 )
    goto LABEL_67;
  if ( !v25 || v25 >= 0x104 )
  {
    LastError = 87;
    if ( (bidGblFlags & 2) == 0 || !off_383B45EE8[0] )
      goto LABEL_42;
    v27 = off_383B45EE8[0];
    v29 = v33;
    v28 = off_383B43868[0];
    v30 = 5521408;
    goto LABEL_73;
  }
  Buffer[260] = 0;
  SystemDirectoryA = GetSystemDirectoryA(Buffer, 260 - v25);
  if ( !SystemDirectoryA )
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_383B45EE0[0] )
      bidTraceA(off_383B43860[0], 5547008, off_383B45EE0[0], LastError);
    goto LABEL_42;
  }
  if ( 260 - v25 <= SystemDirectoryA )
  {
    LastError = 111;
    if ( (bidGblFlags & 2) != 0 && off_383B45ED8[0] )
      bidTraceA(off_383B43858[0], 5554176, off_383B45ED8[0], SystemDirectoryA);
    goto LABEL_42;
  }
  if ( Buffer[0] && (Buffer[0] != 92 || Buffer[1]) )
  {
    v8 = 261;
    v9 = Buffer;
    v10 = 0;
    while ( *v9 )
    {
      ++v9;
      if ( !--v8 )
      {
        v10 = -2147024809;
        v26 = 0;
        goto LABEL_22;
      }
    }
    v26 = 261 - v8;
LABEL_22:
    if ( v10 < 0 )
      goto LABEL_57;
    v10 = 0;
    v11 = &Buffer[v26];
    v12 = 261 - v26;
    if ( v26 == 261 )
      goto LABEL_56;
    v13 = 0x7FFFFFFF;
    v14 = (const char *)("\\" - v11);
    while ( v13 )
    {
      v15 = v11[(_QWORD)v14];
      if ( !v15 )
        break;
      *v11++ = v15;
      --v13;
      if ( !--v12 )
        goto LABEL_56;
    }
    if ( !v12 )
    {
LABEL_56:
      --v11;
      v10 = -2147024774;
    }
    *v11 = 0;
    if ( v10 < 0 )
    {
LABEL_57:
      LastError = v10;
      if ( (bidGblFlags & 2) == 0 || !off_383B45ED0[0] )
        goto LABEL_42;
      v27 = off_383B45ED0[0];
      v28 = off_383B43850[0];
      v29 = Buffer;
      v30 = 5577728;
      goto LABEL_73;
    }
  }
  v16 = 261;
  v17 = Buffer;
  while ( *v17 )
  {
    ++v17;
    if ( !--v16 )
      goto LABEL_60;
  }
  v18 = 0;
  v19 = &Buffer[261 - v16];
  v20 = v16;
  v21 = 0x7FFFFFFF;
  v22 = a1 - v19;
  while ( v21 )
  {
    v23 = v19[v22];
    if ( !v23 )
      break;
    *v19++ = v23;
    --v21;
    if ( !--v20 )
    {
      --v19;
      v18 = -2147024774;
      break;
    }
  }
  *v19 = 0;
  if ( v18 < 0 )
  {
LABEL_60:
    LastError = 111;
    if ( (bidGblFlags & 2) != 0 && off_383B45EC8[0] )
      bidTraceA(off_383B43848[0], 5594112, off_383B45EC8[0], Buffer);
    goto LABEL_42;
  }
  LibraryA = LoadLibraryA(Buffer);
  if ( !LibraryA )
  {
    v31 = GetLastError();
    LastError = v31;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B45EC0[0] )
        bidTraceA(off_383B43840[0], 5605376, off_383B45EC0[0], v31);
    }
  }
LABEL_42:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B45EB8[0] )
    bidTraceA(off_383B43838[0], 5612544, off_383B45EB8[0], LibraryA);
  if ( v32 != -1 )
  {
    if ( (bidGblFlags & 4) != 0 )
    {
      if ( bidID != -1 )
        off_383B15058();
    }
    else
    {
      v32 = -1;
    }
  }
  if ( LastError )
    SetLastError(LastError);
  if ( v32 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return LibraryA;
}

```

## disassembly

```asm
0x383892180  mov     r11, rsp
0x383892183  push    rdi
0x383892184  sub     rsp, 170h
0x38389218b  mov     rax, cs:__security_cookie
0x383892192  xor     rax, rsp
0x383892195  mov     [rsp+178h+var_28], rax
0x38389219d  mov     eax, cs:_bidGblFlags
0x3838921a3  mov     [r11-10h], rsi
0x3838921a7  mov     [r11-18h], r14
0x3838921ab  and     eax, 20004h
0x3838921b0  mov     r14, rcx
0x3838921b3  mov     [rsp+178h+var_148], 0FFFFFFFFFFFFFFFFh
0x3838921bc  cmp     eax, 20004h
0x3838921c1  jnz     short loc_3838921E3
0x3838921c3  mov     rax, cs:off_383B48508; "<SNILoadSystemLibA|API|SNI> szDllFileNa"...
0x3838921ca  test    rax, rax
0x3838921cd  jz      short loc_3838921E3
0x3838921cf  mov     rdx, cs:off_383B48508; "<SNILoadSystemLibA|API|SNI> szDllFileNa"...
0x3838921d6  mov     r8, rcx
0x3838921d9  lea     rcx, [rsp+178h+var_148]
0x3838921de  call    _bidScopeEnterA
0x3838921e3  xor     edi, edi
0x3838921e5  mov     [rsp+178h+arg_8], rbx
0x3838921ed  mov     [rsp+178h+Buffer], 0
0x3838921f2  mov     [rsp+178h+arg_10], rbp
0x3838921fa  mov     esi, edi
0x3838921fc  test    r14, r14
0x3838921ff  jz      loc_3838F84F7
0x383892205  mov     ebp, 104h
0x38389220a  mov     rax, r14
0x38389220d  mov     edx, edi
0x38389220f  mov     ecx, ebp
0x383892211  cmp     [rax], dl
0x383892213  jz      short loc_383892222
0x383892215  inc     rax
0x383892218  dec     rcx
0x38389221b  jnz     short loc_383892211
0x38389221d  jmp     loc_3838F8342
0x383892222  test    rcx, rcx
0x383892225  jz      loc_3838F834F
0x38389222b  mov     rbx, rbp
0x38389222e  sub     rbx, rcx
0x383892231  mov     [rsp+178h+var_140], rbx
0x383892236  test    edx, edx
0x383892238  js      loc_3838F84FC
0x38389223e  test    rbx, rbx
0x383892241  jz      loc_3838F853C
0x383892247  cmp     rbx, rbp
0x38389224a  jnb     loc_3838F853C
0x383892250  mov     edx, ebp
0x383892252  lea     rcx, [rsp+178h+Buffer]; lpBuffer
0x383892257  mov     [rsp+178h+var_34], sil
0x38389225f  sub     edx, ebx; uSize
0x383892261  call    cs:__imp_GetSystemDirectoryA
0x383892267  mov     r9d, eax
0x38389226a  test    eax, eax
0x38389226c  jz      loc_3838F835C
0x383892272  sub     rbp, rbx
0x383892275  mov     rax, r9
0x383892278  cmp     rbp, r9
0x38389227b  jbe     loc_3838F83A1
0x383892281  movzx   eax, [rsp+178h+Buffer]
0x383892286  mov     edx, 105h
0x38389228b  test    al, al
0x38389228d  jz      loc_383892337
0x383892293  cmp     al, 5Ch ; '\'
0x383892295  jz      loc_3838F83E0
0x38389229b  mov     rcx, rdx
0x38389229e  lea     rax, [rsp+178h+Buffer]
0x3838922a3  mov     r10d, edi
0x3838922a6  cmp     [rax], sil
0x3838922a9  jz      short loc_3838922B8
0x3838922ab  inc     rax
0x3838922ae  dec     rcx
0x3838922b1  jnz     short loc_3838922A6
0x3838922b3  jmp     loc_3838F83F0
0x3838922b8  test    rcx, rcx
0x3838922bb  jz      loc_3838F83FE
0x3838922c1  mov     r8, rdx
0x3838922c4  sub     r8, rcx
0x3838922c7  test    r10d, r10d
0x3838922ca  js      loc_3838F841C
0x3838922d0  lea     rax, [rsp+178h+Buffer]
0x3838922d5  mov     rcx, rdx
0x3838922d8  mov     r10d, edi
0x3838922db  lea     rax, [rax+r8]
0x3838922df  sub     rcx, r8
0x3838922e2  jz      loc_3838F840E
0x3838922e8  add     r8, 7FFFFEFAh
0x3838922ef  lea     r11, asc_38387C798; "\\"
0x3838922f6  add     r8, rcx
0x3838922f9  sub     r11, rax
0x3838922fc  nop     dword ptr [rax+00h]
0x383892300  test    r8, r8
0x383892303  jz      short loc_383892322
0x383892305  movzx   r9d, byte ptr [r11+rax]
0x38389230a  test    r9b, r9b
0x38389230d  jz      short loc_383892322
0x38389230f  mov     [rax], r9b
0x383892312  inc     rax
0x383892315  dec     r8
0x383892318  dec     rcx
0x38389231b  jnz     short loc_383892300
0x38389231d  jmp     loc_3838F840C
0x383892322  test    rcx, rcx
0x383892325  jz      loc_3838F840E
0x38389232b  mov     [rax], sil
0x38389232e  test    r10d, r10d
0x383892331  js      loc_3838F841C
0x383892337  mov     rcx, rdx
0x38389233a  lea     rax, [rsp+178h+Buffer]
0x38389233f  nop
0x383892340  cmp     [rax], sil
0x383892343  jz      short loc_383892352
0x383892345  inc     rax
0x383892348  dec     rcx
0x38389234b  jnz     short loc_383892340
0x38389234d  jmp     loc_3838F8459
0x383892352  test    rcx, rcx
0x383892355  jz      loc_3838F8459
0x38389235b  mov     r8, rdx
0x38389235e  lea     rax, [rsp+178h+Buffer]
0x383892363  mov     r10d, edi
0x383892366  sub     r8, rcx
0x383892369  lea     rax, [rax+r8]
0x38389236d  sub     rdx, r8
0x383892370  jz      loc_3838F84A4
0x383892376  lea     rcx, [r8+7FFFFEFAh]
0x38389237d  mov     r9, r14
0x383892380  add     rcx, rdx
0x383892383  sub     r9, rax
0x383892386  test    rcx, rcx
0x383892389  jz      short loc_3838923A8
0x38389238b  movzx   r8d, byte ptr [r9+rax]
0x383892390  test    r8b, r8b
0x383892393  jz      short loc_3838923A8
0x383892395  mov     [rax], r8b
0x383892398  inc     rax
0x38389239b  dec     rcx
0x38389239e  dec     rdx
0x3838923a1  jnz     short loc_383892386
0x3838923a3  jmp     loc_3838F84A2
0x3838923a8  test    rdx, rdx
0x3838923ab  jz      loc_3838F84A4
0x3838923b1  mov     [rax], sil
0x3838923b4  test    r10d, r10d
0x3838923b7  js      loc_3838F8459
0x3838923bd  lea     rcx, [rsp+178h+Buffer]; lpLibFileName
0x3838923c2  call    cs:__imp_LoadLibraryA
0x3838923c8  mov     rdi, rax
0x3838923cb  test    rax, rax
0x3838923ce  jz      loc_3838F84B2
0x3838923d4  mov     eax, cs:_bidGblFlags
0x3838923da  mov     r14, [rsp+178h+var_18]
0x3838923e2  mov     rbp, [rsp+178h+arg_10]
0x3838923ea  mov     rbx, [rsp+178h+arg_8]
0x3838923f2  and     eax, 20002h
0x3838923f7  cmp     eax, 20002h
0x3838923fc  jz      loc_3838F8581
0x383892402  cmp     [rsp+178h+var_148], 0FFFFFFFFFFFFFFFFh
0x383892408  jnz     loc_3838F85B2
0x38389240e  test    esi, esi
0x383892410  jnz     loc_3838F85F0
0x383892416  cmp     [rsp+178h+var_148], 0FFFFFFFFFFFFFFFFh
0x38389241c  mov     rsi, [rsp+178h+var_10]
0x383892424  jnz     loc_3838F85FE
0x38389242a  mov     rax, rdi
0x38389242d  mov     rcx, [rsp+178h+var_28]
0x383892435  xor     rcx, rsp; StackCookie
0x383892438  call    __security_check_cookie
0x38389243d  add     rsp, 170h
0x383892444  pop     rdi
0x383892445  retn
0x3838f8342  mov     edx, 80070057h
0x3838f8347  mov     rbx, rdi
0x3838f834a  jmp     loc_383892231
0x3838f834f  mov     edx, 80070057h
0x3838f8354  mov     rbx, rdi
0x3838f8357  jmp     loc_383892231
0x3838f835c  call    cs:__imp_GetLastError
0x3838f8362  test    byte ptr cs:_bidGblFlags, 2
0x3838f8369  mov     esi, eax
0x3838f836b  jz      loc_3838923D4
0x3838f8371  mov     rax, cs:off_383B45EE0; "<SNILoadSystemLibA|ERR|SNI> GetSystemDi"...
0x3838f8378  test    rax, rax
0x3838f837b  jz      loc_3838923D4
0x3838f8381  mov     r8, cs:off_383B45EE0; "<SNILoadSystemLibA|ERR|SNI> GetSystemDi"...
0x3838f8388  mov     rcx, cs:off_383B43860; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f838f  mov     r9d, esi
0x3838f8392  mov     edx, 54A400h
0x3838f8397  call    _bidTraceA
0x3838f839c  jmp     loc_3838923D4
0x3838f83a1  test    byte ptr cs:_bidGblFlags, 2
0x3838f83a8  mov     esi, 6Fh ; 'o'
0x3838f83ad  jz      loc_3838923D4
0x3838f83b3  mov     rax, cs:off_383B45ED8; "<SNILoadSystemLibA|ERR|SNI> GetSystemDi"...
0x3838f83ba  test    rax, rax
0x3838f83bd  jz      loc_3838923D4
0x3838f83c3  mov     r8, cs:off_383B45ED8; "<SNILoadSystemLibA|ERR|SNI> GetSystemDi"...
0x3838f83ca  mov     rcx, cs:off_383B43858; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f83d1  mov     edx, 54C000h
0x3838f83d6  call    _bidTraceA
0x3838f83db  jmp     loc_3838923D4
0x3838f83e0  cmp     [rsp+178h+var_137], sil
0x3838f83e5  jnz     loc_38389229B
0x3838f83eb  jmp     loc_383892337
0x3838f83f0  mov     r10d, 80070057h
0x3838f83f6  mov     r8, rdi
0x3838f83f9  jmp     loc_3838922C7
0x3838f83fe  mov     r10d, 80070057h
0x3838f8404  mov     r8, rdi
0x3838f8407  jmp     loc_3838922C7
0x3838f840c  jmp     short $+2
0x3838f840e  dec     rax
0x3838f8411  mov     r10d, 8007007Ah
0x3838f8417  jmp     loc_38389232B
0x3838f841c  test    byte ptr cs:_bidGblFlags, 2
0x3838f8423  mov     esi, r10d
0x3838f8426  jz      loc_3838923D4
0x3838f842c  mov     rax, cs:off_383B45ED0; "<SNILoadSystemLibA|ERR|SNI> StringCchCa"...
0x3838f8433  test    rax, rax
0x3838f8436  jz      loc_3838923D4
0x3838f843c  mov     r8, cs:off_383B45ED0; "<SNILoadSystemLibA|ERR|SNI> StringCchCa"...
0x3838f8443  mov     rcx, cs:off_383B43850; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f844a  lea     r9, [rsp+178h+Buffer]
0x3838f844f  mov     edx, 551C00h
0x3838f8454  jmp     loc_3838F8576
0x3838f8459  test    byte ptr cs:_bidGblFlags, 2
0x3838f8460  mov     esi, 6Fh ; 'o'
0x3838f8465  jz      loc_3838923D4
0x3838f846b  mov     rax, cs:off_383B45EC8; "<SNILoadSystemLibA|ERR|SNI> StringCchCa"...
0x3838f8472  test    rax, rax
0x3838f8475  jz      loc_3838923D4
0x3838f847b  mov     r8, cs:off_383B45EC8; "<SNILoadSystemLibA|ERR|SNI> StringCchCa"...
0x3838f8482  mov     rcx, cs:off_383B43848; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f8489  lea     r9, [rsp+178h+Buffer]
0x3838f848e  mov     edx, 555C00h
0x3838f8493  mov     [rsp+178h+var_158], r14
0x3838f8498  call    _bidTraceA
0x3838f849d  jmp     loc_3838923D4
0x3838f84a2  jmp     short $+2
0x3838f84a4  dec     rax
0x3838f84a7  mov     r10d, 8007007Ah
0x3838f84ad  jmp     loc_3838923B1
0x3838f84b2  call    cs:__imp_GetLastError
0x3838f84b8  test    byte ptr cs:_bidGblFlags, 2
0x3838f84bf  mov     esi, eax
0x3838f84c1  jz      loc_3838923D4
0x3838f84c7  mov     rcx, cs:off_383B45EC0; "<SNILoadSystemLibA|ERR|SNI> LoadLibrary"...
0x3838f84ce  test    rcx, rcx
0x3838f84d1  jz      loc_3838923D4
0x3838f84d7  mov     r8, cs:off_383B45EC0; "<SNILoadSystemLibA|ERR|SNI> LoadLibrary"...
0x3838f84de  mov     rcx, cs:off_383B43840; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f84e5  mov     r9d, eax
0x3838f84e8  mov     edx, 558800h
0x3838f84ed  call    _bidTraceA
0x3838f84f2  jmp     loc_3838923D4
0x3838f84f7  mov     edx, 80070057h
0x3838f84fc  mov     [rsp+178h+var_140], rdi
0x3838f8501  test    edx, edx
0x3838f8503  jns     short loc_3838F853C
0x3838f8505  test    byte ptr cs:_bidGblFlags, 2
0x3838f850c  mov     esi, edx
0x3838f850e  jz      loc_3838923D4
0x3838f8514  mov     rax, cs:off_383B45EF0; "<SNILoadSystemLibA|ERR|SNI> StringCchLe"...
0x3838f851b  test    rax, rax
0x3838f851e  jz      loc_3838923D4
0x3838f8524  mov     r8, cs:off_383B45EF0; "<SNILoadSystemLibA|ERR|SNI> StringCchLe"...
0x3838f852b  mov     rcx, cs:off_383B43870; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f8532  mov     r9, r14
0x3838f8535  mov     edx, 542000h
0x3838f853a  jmp     short loc_3838F8576
0x3838f853c  test    byte ptr cs:_bidGblFlags, 2
0x3838f8543  mov     esi, 57h ; 'W'
0x3838f8548  jz      loc_3838923D4
0x3838f854e  mov     rax, cs:off_383B45EE8; "<SNILoadSystemLibA|ERR|SNI> StringCchLe"...
0x3838f8555  test    rax, rax
0x3838f8558  jz      loc_3838923D4
0x3838f855e  mov     r8, cs:off_383B45EE8; "<SNILoadSystemLibA|ERR|SNI> StringCchLe"...
0x3838f8565  mov     r9, [rsp+178h+var_140]
0x3838f856a  mov     rcx, cs:off_383B43868; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f8571  mov     edx, 544000h
0x3838f8576  call    _bidTraceA
0x3838f857b  nop
0x3838f857c  jmp     loc_3838923D4
0x3838f8581  mov     rax, cs:off_383B45EB8; "<SNILoadSystemLibA|RET|SNI> %p{HMODULE}"...
0x3838f8588  test    rax, rax
0x3838f858b  jz      loc_383892402
0x3838f8591  mov     r8, cs:off_383B45EB8; "<SNILoadSystemLibA|RET|SNI> %p{HMODULE}"...
0x3838f8598  mov     rcx, cs:off_383B43838; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x3838f859f  mov     r9, rdi
0x3838f85a2  mov     edx, 55A400h
0x3838f85a7  call    _bidTraceA
0x3838f85ac  nop
0x3838f85ad  jmp     loc_383892402
0x3838f85b2  test    byte ptr cs:_bidGblFlags, 4
0x3838f85b9  jnz     short loc_3838F85C9
0x3838f85bb  mov     [rsp+178h+var_148], 0FFFFFFFFFFFFFFFFh
0x3838f85c4  jmp     loc_38389240E
0x3838f85c9  mov     rcx, cs:_bidID
  ... truncated ...
```
