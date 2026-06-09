# SdbOpenDatabaseEx

- ea: `0x140016198`
- end: `0x140016514`
- name: `SdbOpenDatabaseEx`
- size: `892`
- prototype: `_BYTE **__fastcall(const wchar_t *, __int64, unsigned int)`
- caller_count: `8`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400045e0`
- `0x140004df8`
- `0x140008500`
- `0x140015b08`
- `0x140018e34`
- `0x14001a678`
- `0x1400242ac`
- `0x14002b138`

## callees

- `0x14000f644`
- `0x14000f980`
- `0x14000fa64`
- `0x14001008c`
- `0x140010270`
- `0x140015eb4`
- `0x140016198`
- `0x1400178a0`
- `0x140017be4`
- `0x140019018`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140016223`
- `ntdll!RtlAllocateHeap` at `0x140016223`
- `ntdll!RtlFreeHeap` at `0x140016371`
- `ntdll!RtlFreeHeap` at `0x1400164e7`
- `ntdll!RtlFreeHeap` at `0x140016371`
- `ntdll!RtlFreeHeap` at `0x1400164e7`

## string_xrefs

- `0x140016393`: `Failed to create file mapping [%x]`
- `0x1400161c2`: `Flags:%d; DatabasePath:%ws`
- `0x1400161dd`: `SdbOpenDatabaseEx`
- `0x140016242`: `SdbOpenDatabaseEx`
- `0x1400162d7`: `SdbOpenDatabaseEx`
- `0x140016317`: `SdbOpenDatabaseEx`
- `0x140016343`: `SdbOpenDatabaseEx`
- `0x1400163a0`: `SdbOpenDatabaseEx`
- `0x140016476`: `SdbOpenDatabaseEx`
- `0x1400164b5`: `SdbOpenDatabaseEx`
- `0x140016331`: `SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]`
- `0x140016306`: `Failed to create file mapping for redirected SDB file [%x]`
- `0x1400164a8`: `Failed to open SDB - File size too large or small.`
- `0x140016418`: `Failed to read database header`
- `0x140016469`: `SdbpOpenCompressedDatabase failed to open compressed database.`

## pseudocode

```c
_BYTE **__fastcall SdbOpenDatabaseEx(const wchar_t *a1, __int64 a2, unsigned int a3)
{
  const wchar_t *v5; // rax
  _BYTE **Heap; // rax
  _BYTE **v7; // rbx
  int MergeRedirectPath; // eax
  int v9; // r15d
  int v10; // esi
  const wchar_t *FileNamePart; // rax
  int v12; // eax
  int v13; // eax
  const char *v14; // r9
  __int64 v15; // r8
  __int64 v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v20; // [rsp+20h] [rbp-40h]
  BOOL v21; // [rsp+30h] [rbp-30h] BYREF
  PVOID P; // [rsp+38h] [rbp-28h] BYREF
  _BYTE **v23; // [rsp+40h] [rbp-20h] BYREF
  __int64 v24; // [rsp+48h] [rbp-18h] BYREF
  int v25; // [rsp+50h] [rbp-10h]

  v24 = 0;
  v25 = 0;
  v21 = 0;
  v5 = a1;
  if ( !a1 )
    v5 = &Format;
  AslLogCallPrintf(3, "SdbOpenDatabaseEx", 2501, "Flags:%d; DatabasePath:%ws", a3, v5);
  Heap = (_BYTE **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v23 = Heap;
  v7 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0xA80u);
    P = 0;
    if ( (a3 & 0x10) != 0 )
      goto LABEL_49;
    MergeRedirectPath = SdbGetMergeRedirectPath(&P, &v21, (a3 & 0x20) == 0, a1);
    v9 = MergeRedirectPath;
    if ( MergeRedirectPath < 0 )
    {
      if ( MergeRedirectPath != -1073741772 )
        AslLogCallPrintf(
          3,
          "SdbOpenDatabaseEx",
          2527,
          "SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]",
          MergeRedirectPath);
      v10 = v9;
    }
    else if ( P )
    {
      if ( (a3 & 0x20) != 0 )
      {
        if ( !v21 )
          *((_DWORD *)v7 + 6) |= 0x20u;
      }
      else if ( v21 )
      {
        FileNamePart = AslPathGetFileNamePart(a1);
        AslLogCallPrintf(
          1,
          "SdbOpenDatabaseEx",
          2539,
          "Handled Error: MergeSdb staged deletion feature was used to prevent sdb mismatch error. SdbName: [%ls].",
          FileNamePart);
      }
      v12 = AslFileMappingCreate(v7, (const WCHAR *)P, 0);
      v10 = v12;
      if ( v12 < 0 )
        AslLogCallPrintf(
          1,
          "SdbOpenDatabaseEx",
          2558,
          "Failed to create file mapping for redirected SDB file [%x]",
          v12);
    }
    else
    {
      v10 = -1073741772;
    }
    if ( P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    if ( v10 < 0 || !*v7 )
    {
LABEL_49:
      v13 = AslFileMappingCreate(v7, a1, 0);
      if ( v13 < 0 )
      {
        v14 = "Failed to create file mapping [%x]";
        v15 = 2580;
LABEL_25:
        LODWORD(v20) = v13;
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", v15, v14, v20);
        goto LABEL_44;
      }
    }
    v16 = *((_QWORD *)*v7 + 3);
    if ( (unsigned __int64)(v16 - 42) > 0xFFFFFD5 )
    {
      AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2589, "Failed to open SDB - File size too large or small.");
      goto LABEL_44;
    }
    v13 = AslFileMappingEnsureMappedAsEx();
    if ( v13 < 0 )
    {
      v14 = "Failed to map SDB [%x]";
      v15 = 2595;
      goto LABEL_25;
    }
    *((_DWORD *)v7 + 4) = 0;
    *((_DWORD *)v7 + 5) = v16;
    v17 = (__int64)*v7;
    if ( *v7 )
      v17 = *(_QWORD *)(v17 + 32);
    v7[1] = (_BYTE *)v17;
    if ( !(unsigned int)SdbpReadMappedData(v7, 0, &v24, 12) )
    {
      AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2608, "Failed to read database header");
      goto LABEL_44;
    }
    v13 = v25;
    if ( v25 != 1717724275 )
    {
      if ( v25 == 1717724282 )
      {
        if ( (unsigned int)SdbpOpenCompressedDatabase(&v23, v18, a3) )
          return v23;
        AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2627, "SdbpOpenCompressedDatabase failed to open compressed database.");
        v7 = v23;
LABEL_44:
        if ( v7 )
        {
          AslFileMappingDelete(*v7);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        }
        return 0;
      }
      if ( (a3 & 2) == 0 )
      {
        v14 = "Magic does not match a valid value: 0x%lx";
        v15 = 2621;
        goto LABEL_25;
      }
    }
    if ( (unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v24, a3) )
      return v7;
    goto LABEL_44;
  }
  AslLogCallPrintf(1, "SdbOpenDatabaseEx", 2509, "Failed to allocate DB structure");
  return 0;
}

```

## disassembly

```asm
0x140016198  mov     r11, rsp
0x14001619b  mov     [r11+10h], rbx
0x14001619f  mov     [r11+20h], rsi
0x1400161a3  push    rbp
0x1400161a4  push    rdi
0x1400161a5  push    r12
0x1400161a7  push    r13
0x1400161a9  push    r15
0x1400161ab  mov     rbp, rsp
0x1400161ae  sub     rsp, 60h
0x1400161b2  mov     rax, cs:__security_cookie
0x1400161b9  xor     rax, rsp
0x1400161bc  mov     [rbp+var_8], rax
0x1400161c0  xor     eax, eax
0x1400161c2  lea     r9, aFlagsDDatabase; "Flags:%d; DatabasePath:%ws"
0x1400161c9  mov     r13, rcx
0x1400161cc  mov     [rbp+var_18], rax
0x1400161d0  mov     [rbp+var_10], eax
0x1400161d3  lea     rcx, Format
0x1400161da  mov     [rbp+var_30], eax
0x1400161dd  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1400161e4  mov     r12d, r8d
0x1400161e7  test    r13, r13
0x1400161ea  mov     rax, r13
0x1400161ed  cmovz   rax, rcx
0x1400161f1  mov     ecx, 3
0x1400161f6  mov     [r11-60h], rax
0x1400161fa  mov     [r11-68h], r8d
0x1400161fe  mov     r8d, 9C5h
0x140016204  call    AslLogCallPrintf
0x140016209  mov     rcx, gs:60h
0x140016212  mov     edi, 0A80h
0x140016217  mov     r8d, edi; Size
0x14001621a  mov     edx, 8; Flags
0x14001621f  mov     rcx, [rcx+30h]; HeapHandle
0x140016223  call    cs:__imp_RtlAllocateHeap
0x140016229  mov     [rbp+var_20], rax
0x14001622d  mov     rbx, rax
0x140016230  test    rax, rax
0x140016233  jnz     short loc_140016256
0x140016235  lea     r9, aFailedToAlloca_8; "Failed to allocate DB structure"
0x14001623c  mov     r8d, 9CDh
0x140016242  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140016249  lea     ecx, [rax+1]
0x14001624c  call    AslLogCallPrintf
0x140016251  jmp     loc_1400164ED
0x140016256  mov     r8, rdi; Size
0x140016259  xor     edx, edx; Val
0x14001625b  mov     rcx, rbx; void *
0x14001625e  call    memset_0
0x140016263  mov     [rbp+P], 0
0x14001626b  mov     edi, 1
0x140016270  test    r12b, 10h
0x140016274  jnz     loc_140016381
0x14001627a  lea     r8d, [rdi-1]
0x14001627e  mov     esi, r12d
0x140016281  and     esi, 20h
0x140016284  lea     rdx, [rbp+var_30]
0x140016288  mov     r9, r13
0x14001628b  lea     rcx, [rbp+P]
0x14001628f  setz    r8b
0x140016293  call    SdbGetMergeRedirectPath
0x140016298  mov     r15d, eax
0x14001629b  test    eax, eax
0x14001629d  js      loc_140016327
0x1400162a3  cmp     [rbp+P], 0
0x1400162a8  jnz     short loc_1400162B4
0x1400162aa  mov     esi, 0C0000034h
0x1400162af  jmp     loc_140016357
0x1400162b4  test    esi, esi
0x1400162b6  jnz     short loc_1400162E7
0x1400162b8  cmp     [rbp+var_30], esi
0x1400162bb  jz      short loc_1400162F1
0x1400162bd  mov     rcx, r13
0x1400162c0  call    AslPathGetFileNamePart
0x1400162c5  lea     r9, aHandledErrorMe; "Handled Error: MergeSdb staged deletion"...
0x1400162cc  mov     [rsp+60h+var_40], rax
0x1400162d1  mov     r8d, 9EBh
0x1400162d7  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1400162de  mov     ecx, edi
0x1400162e0  call    AslLogCallPrintf
0x1400162e5  jmp     short loc_1400162F1
0x1400162e7  cmp     [rbp+var_30], 0
0x1400162eb  jnz     short loc_1400162F1
0x1400162ed  or      dword ptr [rbx+18h], 20h
0x1400162f1  mov     rdx, [rbp+P]
0x1400162f5  xor     r8d, r8d
0x1400162f8  mov     rcx, rbx
0x1400162fb  call    AslFileMappingCreate
0x140016300  mov     esi, eax
0x140016302  test    eax, eax
0x140016304  jns     short loc_140016357
0x140016306  lea     r9, aFailedToCreate_6; "Failed to create file mapping for redir"...
0x14001630d  mov     dword ptr [rsp+60h+var_40], eax
0x140016311  mov     r8d, 9FEh
0x140016317  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x14001631e  mov     ecx, edi
0x140016320  call    AslLogCallPrintf
0x140016325  jmp     short loc_140016357
0x140016327  mov     esi, 0C0000034h
0x14001632c  cmp     r15d, esi
0x14001632f  jz      short loc_140016354
0x140016331  lea     r9, aSdbgetmergered; "SdbGetMergeRedirectPath failed to check"...
0x140016338  mov     dword ptr [rsp+60h+var_40], r15d
0x14001633d  mov     r8d, 9DFh
0x140016343  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x14001634a  mov     ecx, 3
0x14001634f  call    AslLogCallPrintf
0x140016354  mov     esi, r15d
0x140016357  cmp     [rbp+P], 0
0x14001635c  jz      short loc_140016377
0x14001635e  mov     rcx, gs:60h
0x140016367  xor     edx, edx; Flags
0x140016369  mov     r8, [rbp+P]; P
0x14001636d  mov     rcx, [rcx+30h]; HeapHandle
0x140016371  call    cs:__imp_RtlFreeHeap
0x140016377  test    esi, esi
0x140016379  js      short loc_140016381
0x14001637b  cmp     qword ptr [rbx], 0
0x14001637f  jnz     short loc_1400163B7
0x140016381  xor     r8d, r8d
0x140016384  mov     rdx, r13
0x140016387  mov     rcx, rbx
0x14001638a  call    AslFileMappingCreate
0x14001638f  test    eax, eax
0x140016391  jns     short loc_1400163B7
0x140016393  lea     r9, aFailedToCreate_2; "Failed to create file mapping [%x]"
0x14001639a  mov     r8d, 0A14h
0x1400163a0  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1400163a7  mov     dword ptr [rsp+60h+var_40], eax
0x1400163ab  mov     ecx, edi
0x1400163ad  call    AslLogCallPrintf
0x1400163b2  jmp     loc_1400164C3
0x1400163b7  mov     rcx, [rbx]
0x1400163ba  mov     rsi, [rcx+18h]
0x1400163be  lea     rax, [rsi-2Ah]
0x1400163c2  cmp     rax, 0FFFFFD5h
0x1400163c8  ja      loc_1400164A8
0x1400163ce  call    AslFileMappingEnsureMappedAsEx
0x1400163d3  test    eax, eax
0x1400163d5  jns     short loc_1400163E6
0x1400163d7  lea     r9, aFailedToMapSdb; "Failed to map SDB [%x]"
0x1400163de  mov     r8d, 0A23h
0x1400163e4  jmp     short loc_1400163A0
0x1400163e6  mov     dword ptr [rbx+10h], 0
0x1400163ed  mov     [rbx+14h], esi
0x1400163f0  mov     rax, [rbx]
0x1400163f3  test    rax, rax
0x1400163f6  jz      short loc_1400163FC
0x1400163f8  mov     rax, [rax+20h]
0x1400163fc  mov     r9d, 0Ch
0x140016402  mov     [rbx+8], rax
0x140016406  lea     r8, [rbp+var_18]
0x14001640a  xor     edx, edx
0x14001640c  mov     rcx, rbx
0x14001640f  call    SdbpReadMappedData
0x140016414  test    eax, eax
0x140016416  jnz     short loc_14001642A
0x140016418  lea     r9, aFailedToReadDa_2; "Failed to read database header"
0x14001641f  mov     r8d, 0A30h
0x140016425  jmp     loc_1400164B5
0x14001642a  mov     eax, [rbp+var_10]
0x14001642d  mov     ecx, 6662647Ah
0x140016432  cmp     eax, 66626473h
0x140016437  jz      short loc_140016455
0x140016439  cmp     eax, ecx
0x14001643b  jz      short loc_140016459
0x14001643d  test    r12b, 2
0x140016441  jnz     short loc_140016455
0x140016443  lea     r9, aMagicDoesNotMa_0; "Magic does not match a valid value: 0x%"...
0x14001644a  mov     r8d, 0A3Dh
0x140016450  jmp     loc_1400163A0
0x140016455  cmp     eax, ecx
0x140016457  jnz     short loc_140016490
0x140016459  mov     r8d, r12d
0x14001645c  lea     rcx, [rbp+var_20]
0x140016460  call    SdbpOpenCompressedDatabase
0x140016465  test    eax, eax
0x140016467  jnz     short loc_14001648A
0x140016469  lea     r9, aSdbpopencompre; "SdbpOpenCompressedDatabase failed to op"...
0x140016470  mov     r8d, 0A43h
0x140016476  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x14001647d  mov     ecx, edi
0x14001647f  call    AslLogCallPrintf
0x140016484  mov     rbx, [rbp+var_20]
0x140016488  jmp     short loc_1400164C3
0x14001648a  mov     rbx, [rbp+var_20]
0x14001648e  jmp     short loc_1400164A3
0x140016490  mov     r8d, r12d
0x140016493  lea     rdx, [rbp+var_18]
0x140016497  mov     rcx, rbx
0x14001649a  call    SdbpValidateAndApplyCompatFlags
0x14001649f  test    eax, eax
0x1400164a1  jz      short loc_1400164C3
0x1400164a3  mov     rax, rbx
0x1400164a6  jmp     short loc_1400164EF
0x1400164a8  lea     r9, aFailedToOpenSd_3; "Failed to open SDB - File size too larg"...
0x1400164af  mov     r8d, 0A1Dh
0x1400164b5  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1400164bc  mov     ecx, edi
0x1400164be  call    AslLogCallPrintf
0x1400164c3  test    rbx, rbx
0x1400164c6  jz      short loc_1400164ED
0x1400164c8  mov     rcx, [rbx]; P
0x1400164cb  call    AslFileMappingDelete
0x1400164d0  test    rbx, rbx
0x1400164d3  jz      short loc_1400164ED
0x1400164d5  mov     rcx, gs:60h
0x1400164de  mov     r8, rbx; P
0x1400164e1  xor     edx, edx; Flags
0x1400164e3  mov     rcx, [rcx+30h]; HeapHandle
0x1400164e7  call    cs:__imp_RtlFreeHeap
0x1400164ed  xor     eax, eax
0x1400164ef  mov     rcx, [rbp+var_8]
0x1400164f3  xor     rcx, rsp; StackCookie
0x1400164f6  call    __security_check_cookie
0x1400164fb  lea     r11, [rsp+60h+var_s0]
0x140016500  mov     rbx, [r11+38h]
0x140016504  mov     rsi, [r11+48h]
0x140016508  mov     rsp, r11
0x14001650b  pop     r15
0x14001650d  pop     r13
0x14001650f  pop     r12
0x140016511  pop     rdi
0x140016512  pop     rbp
0x140016513  retn
```
