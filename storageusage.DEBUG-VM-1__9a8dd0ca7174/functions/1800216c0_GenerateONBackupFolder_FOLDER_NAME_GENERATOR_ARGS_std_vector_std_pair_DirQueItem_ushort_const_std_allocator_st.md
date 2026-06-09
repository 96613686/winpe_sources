# GenerateONBackupFolder(FOLDER_NAME_GENERATOR_ARGS,std::vector<std::pair<DirQueItem,ushort const *>,std::allocator<std::pair<DirQueItem,ushort const *>>> &)

- ea: `0x1800216c0`
- end: `0x180021930`
- name: `?GenerateONBackupFolder@@YAJUFOLDER_NAME_GENERATOR_ARGS@@AEAV?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@@Z`
- size: `624`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x1800152d4`
- `0x180015bac`
- `0x18001c940`
- `0x18001faac`
- `0x18001fc6c`
- `0x1800216c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800218fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800218fb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021831`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180021831`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180021730`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180021730`

## pseudocode

```c
__int64 __fastcall GenerateONBackupFolder(__int64 *a1, __int64 a2)
{
  HRESULT v4; // eax
  int v5; // ebx
  _QWORD *v6; // rdi
  char v7; // r14
  unsigned __int64 v8; // rdx
  __int64 v9; // rcx
  _OWORD *v10; // rdx
  unsigned __int16 *v11; // rax
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int64 v19; // rdx
  int v21; // [rsp+20h] [rbp-E0h]
  PWSTR ppszPath; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v23[10]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[520]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+2A8h] [rbp+1A8h]
  unsigned __int16 v26[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR FileName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+718h] [rbp+618h]

  ppszPath = 0;
  memset_0(v26, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  v4 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v5 = 0;
    v23[0] = L"16.0";
    v6 = v23;
    v7 = 0;
    v23[1] = L"15.0";
    v23[2] = L"14.0";
    v23[3] = L"13.0";
    v23[4] = L"12.0";
    v23[5] = L"11.0";
    v23[6] = L"17.0";
    v23[7] = L"18.0";
    v23[8] = L"19.0";
    v23[9] = L"20.0";
    while ( v6 != (_QWORD *)v24 )
    {
      v5 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s\\%s\\%s", ppszPath, L"Microsoft\\OneNote", *v6, L"Backup");
      if ( v5 >= 0 && GetFileAttributesW(FileName) != -1 )
      {
        v5 = StringCbCopyW(v26, v8, FileName);
        if ( v5 >= 0 )
        {
          v9 = 4;
          v10 = v24;
          v11 = v26;
          do
          {
            v12 = *((_OWORD *)v11 + 1);
            *v10 = *(_OWORD *)v11;
            v13 = *((_OWORD *)v11 + 2);
            v10[1] = v12;
            v14 = *((_OWORD *)v11 + 3);
            v10[2] = v13;
            v15 = *((_OWORD *)v11 + 4);
            v10[3] = v14;
            v16 = *((_OWORD *)v11 + 5);
            v10[4] = v15;
            v17 = *((_OWORD *)v11 + 6);
            v10[5] = v16;
            v18 = *((_OWORD *)v11 + 7);
            v11 += 64;
            v10[6] = v17;
            v10[7] = v18;
            v10 += 8;
            --v9;
          }
          while ( v9 );
          *(_QWORD *)v10 = *(_QWORD *)v11;
          v19 = *(_QWORD *)(a2 + 8);
          v25 = *a1;
          if ( v19 == *(_QWORD *)(a2 + 16) )
            std::vector<std::pair<DirQueItem,unsigned short const *>>::_Emplace_reallocate<std::pair<DirQueItem,unsigned short const *>>(
              a2,
              v19,
              v24);
          else
            std::vector<std::pair<DirQueItem,unsigned short const *>>::_Emplace_back_with_unused_capacity<std::pair<DirQueItem,unsigned short const *>>(
              a2,
              v24);
        }
        v7 = 1;
        break;
      }
      ++v6;
    }
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
    if ( v5 >= 0 && !v7 )
      return (unsigned int)-2147024893;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x527,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\dirscanner.cpp",
      (const char *)(unsigned int)v4,
      v21);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800216c0  push    rbp
0x1800216c2  push    rbx
0x1800216c3  push    rsi
0x1800216c4  push    rdi
0x1800216c5  push    r14
0x1800216c7  push    r15
0x1800216c9  lea     rbp, [rsp-5E8h]
0x1800216d1  sub     rsp, 6E8h
0x1800216d8  mov     rax, cs:__security_cookie
0x1800216df  xor     rax, rsp
0x1800216e2  mov     [rbp+610h+var_40], rax
0x1800216e9  mov     rsi, rdx
0x1800216ec  mov     [rsp+710h+ppszPath], 0
0x1800216f5  mov     r15, rcx
0x1800216f8  mov     ebx, 208h
0x1800216fd  mov     r8d, ebx; Size
0x180021700  lea     rcx, [rbp+610h+var_460]; void *
0x180021707  xor     edx, edx; Val
0x180021709  call    memset_0
0x18002170e  mov     r8d, ebx; Size
0x180021711  lea     rcx, [rbp+610h+FileName]; void *
0x180021718  xor     edx, edx; Val
0x18002171a  call    memset_0
0x18002171f  lea     r9, [rsp+710h+ppszPath]; ppszPath
0x180021724  xor     r8d, r8d; hToken
0x180021727  xor     edx, edx; dwFlags
0x180021729  lea     rcx, FOLDERID_LocalAppData; rfid
0x180021730  call    cs:__imp_SHGetKnownFolderPath
0x180021736  mov     ebx, eax
0x180021738  test    eax, eax
0x18002173a  jns     short loc_18002175C
0x18002173c  mov     rcx, [rbp+618h]; this
0x180021743  lea     r8, aOnecoreDrivers_4; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002174a  mov     r9d, eax; char *
0x18002174d  mov     edx, 527h; void *
0x180021752  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021757  jmp     loc_18002190F
0x18002175c  lea     rax, a160; "16.0"
0x180021763  xor     ebx, ebx
0x180021765  mov     [rsp+710h+var_6C0], rax
0x18002176a  lea     rdi, [rsp+710h+var_6C0]
0x18002176f  lea     rax, a150; "15.0"
0x180021776  xor     r14b, r14b
0x180021779  mov     [rsp+710h+var_6B8], rax
0x18002177e  lea     rax, a140; "14.0"
0x180021785  mov     [rsp+710h+var_6B0], rax
0x18002178a  lea     rax, a130; "13.0"
0x180021791  mov     [rsp+710h+var_6A8], rax
0x180021796  lea     rax, a120; "12.0"
0x18002179d  mov     [rsp+710h+var_6A0], rax
0x1800217a2  lea     rax, a110; "11.0"
0x1800217a9  mov     [rsp+710h+var_698], rax
0x1800217ae  lea     rax, a170; "17.0"
0x1800217b5  mov     [rbp+610h+var_690], rax
0x1800217b9  lea     rax, a180; "18.0"
0x1800217c0  mov     [rbp+610h+var_688], rax
0x1800217c4  lea     rax, a190; "19.0"
0x1800217cb  mov     [rbp+610h+var_680], rax
0x1800217cf  lea     rax, a200; "20.0"
0x1800217d6  mov     [rbp+610h+var_678], rax
0x1800217da  lea     rax, [rbp+610h+var_670]
0x1800217de  cmp     rdi, rax
0x1800217e1  jz      loc_1800218F1
0x1800217e7  mov     r9, [rsp+710h+ppszPath]
0x1800217ec  lea     rax, aBackup; "Backup"
0x1800217f3  mov     [rsp+710h+var_6E0], rax
0x1800217f8  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x1800217ff  mov     rax, [rdi]
0x180021802  lea     rcx, [rbp+610h+FileName]; unsigned __int16 *
0x180021809  mov     [rsp+710h+var_6E8], rax
0x18002180e  mov     edx, 104h; unsigned __int64
0x180021813  lea     rax, aMicrosoftOneno; "Microsoft\\OneNote"
0x18002181a  mov     [rsp+710h+var_6F0], rax
0x18002181f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021824  mov     ebx, eax
0x180021826  test    eax, eax
0x180021828  js      short loc_18002183C
0x18002182a  lea     rcx, [rbp+610h+FileName]; lpFileName
0x180021831  call    cs:__imp_GetFileAttributesW
0x180021837  cmp     eax, 0FFFFFFFFh
0x18002183a  jnz     short loc_180021842
0x18002183c  add     rdi, 8
0x180021840  jmp     short loc_1800217DA
0x180021842  lea     r8, [rbp+610h+FileName]; unsigned __int16 *
0x180021849  lea     rcx, [rbp+610h+var_460]; unsigned __int16 *
0x180021850  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180021855  mov     ebx, eax
0x180021857  test    eax, eax
0x180021859  js      loc_1800218EE
0x18002185f  mov     ecx, 4
0x180021864  lea     rdx, [rbp+610h+var_670]
0x180021868  lea     rax, [rbp+610h+var_460]
0x18002186f  lea     r8d, [rcx+7Ch]
0x180021873  movups  xmm0, xmmword ptr [rax]
0x180021876  movups  xmm1, xmmword ptr [rax+10h]
0x18002187a  movups  xmmword ptr [rdx], xmm0
0x18002187d  movups  xmm0, xmmword ptr [rax+20h]
0x180021881  movups  xmmword ptr [rdx+10h], xmm1
0x180021885  movups  xmm1, xmmword ptr [rax+30h]
0x180021889  movups  xmmword ptr [rdx+20h], xmm0
0x18002188d  movups  xmm0, xmmword ptr [rax+40h]
0x180021891  movups  xmmword ptr [rdx+30h], xmm1
0x180021895  movups  xmm1, xmmword ptr [rax+50h]
0x180021899  movups  xmmword ptr [rdx+40h], xmm0
0x18002189d  movups  xmm0, xmmword ptr [rax+60h]
0x1800218a1  movups  xmmword ptr [rdx+50h], xmm1
0x1800218a5  movups  xmm1, xmmword ptr [rax+70h]
0x1800218a9  add     rax, r8
0x1800218ac  movups  xmmword ptr [rdx+60h], xmm0
0x1800218b0  movups  xmmword ptr [rdx+70h], xmm1
0x1800218b4  add     rdx, r8
0x1800218b7  sub     rcx, 1
0x1800218bb  jnz     short loc_180021873
0x1800218bd  mov     rax, [rax]
0x1800218c0  mov     rcx, rsi
0x1800218c3  mov     [rdx], rax
0x1800218c6  mov     rdx, [rsi+8]
0x1800218ca  mov     rax, [r15]
0x1800218cd  mov     [rbp+610h+var_468], rax
0x1800218d4  cmp     rdx, [rsi+10h]
0x1800218d8  jz      short loc_1800218E5
0x1800218da  lea     rdx, [rbp+610h+var_670]
0x1800218de  call    ??$_Emplace_back_with_unused_capacity@U?$pair@UDirQueItem@@PEBG@std@@@?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@AEAAAEAU?$pair@UDirQueItem@@PEBG@1@$$QEAU21@@Z; std::vector<std::pair<DirQueItem,ushort const *>>::_Emplace_back_with_unused_capacity<std::pair<DirQueItem,ushort const *>>(std::pair<DirQueItem,ushort const *> &&)
0x1800218e3  jmp     short loc_1800218EE
0x1800218e5  lea     r8, [rbp+610h+var_670]
0x1800218e9  call    ??$_Emplace_reallocate@U?$pair@UDirQueItem@@PEBG@std@@@?$vector@U?$pair@UDirQueItem@@PEBG@std@@V?$allocator@U?$pair@UDirQueItem@@PEBG@std@@@2@@std@@AEAAPEAU?$pair@UDirQueItem@@PEBG@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<DirQueItem,ushort const *>>::_Emplace_reallocate<std::pair<DirQueItem,ushort const *>>(std::pair<DirQueItem,ushort const *> * const,std::pair<DirQueItem,ushort const *> &&)
0x1800218ee  mov     r14b, 1
0x1800218f1  mov     rcx, [rsp+710h+ppszPath]; pv
0x1800218f6  test    rcx, rcx
0x1800218f9  jz      short loc_180021901
0x1800218fb  call    cs:__imp_CoTaskMemFree
0x180021901  test    ebx, ebx
0x180021903  js      short loc_18002190F
0x180021905  test    r14b, r14b
0x180021908  jnz     short loc_18002190F
0x18002190a  mov     ebx, 80070003h
0x18002190f  mov     eax, ebx
0x180021911  mov     rcx, [rbp+610h+var_40]
0x180021918  xor     rcx, rsp; StackCookie
0x18002191b  call    __security_check_cookie
0x180021920  add     rsp, 6E8h
0x180021927  pop     r15
0x180021929  pop     r14
0x18002192b  pop     rdi
0x18002192c  pop     rsi
0x18002192d  pop     rbx
0x18002192e  pop     rbp
0x18002192f  retn
```
