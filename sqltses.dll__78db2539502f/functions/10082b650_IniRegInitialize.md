# IniRegInitialize

- ea: `0x10082b650`
- end: `0x10082ba8a`
- name: `IniRegInitialize`
- size: `1082`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x10082bb30`

## callees

- `0x100422d60`
- `0x10082b5c0`
- `0x10082b5e0`
- `0x10082b650`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x10082b712`
- `KERNEL32!GetModuleFileNameW` at `0x10082b712`
- `KERNEL32!GetFileAttributesW` at `0x10082b8e3`
- `KERNEL32!GetFileAttributesW` at `0x10082b8e3`

## string_xrefs

- `0x10082b680`: `IniRegistryLib is getting loaded.\n`
- `0x10082b9c2`: `wszIniRegDirectory %s \n`
- `0x10082ba4a`: `g_wszIniRegExtPath: %s \n`

## pseudocode

```c
__int64 __fastcall IniRegInitialize(HMODULE a1, _WORD *a2, int a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int i; // [rsp+20h] [rbp-A8h]
  WCHAR *v9; // [rsp+28h] [rbp-A0h]
  DWORD ModuleFileNameW; // [rsp+30h] [rbp-98h]
  int v11; // [rsp+34h] [rbp-94h]
  char *j; // [rsp+38h] [rbp-90h]
  int v13; // [rsp+40h] [rbp-88h]
  __int64 v14; // [rsp+48h] [rbp-80h]
  WCHAR *v15; // [rsp+50h] [rbp-78h]
  __int64 v16; // [rsp+58h] [rbp-70h]
  __int64 v17; // [rsp+60h] [rbp-68h]
  WCHAR *v18; // [rsp+70h] [rbp-58h]
  void *v19; // [rsp+78h] [rbp-50h]
  int v20; // [rsp+80h] [rbp-48h]

  if ( dword_100CD46E0 )
    return 1;
  CEsCacheObj::Serialize(a1, a2);
  Trace(L"IniRegistryLib is getting loaded.\r\n");
  if ( a2 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v20 = v14;
  }
  else
  {
    v20 = 3;
  }
  v11 = v20 + 1;
  ModuleFileNameW = GetModuleFileNameW(a1, &FileName, 260 - (v20 + 1));
  if ( !ModuleFileNameW )
    goto LABEL_39;
  _mm_lfence();
  v9 = &FileName + ModuleFileNameW - 1;
  Trace(L"%s \r\n", v9);
  v15 = 0;
  v18 = 0;
  while ( !v15 && v9 > &FileName )
  {
    if ( v18 )
    {
      if ( *v9 == 92 )
        v15 = v9;
    }
    else if ( *v9 == 46 )
    {
      v18 = v9;
    }
    --v9;
  }
  if ( !v15 )
    goto LABEL_39;
  v13 = 0;
  v19 = v15 + 1;
  if ( a2 )
  {
    qmemcpy(v19, a2, (unsigned int)(2 * v11));
    v5 = 0;
  }
  else
  {
    for ( i = 0; !i; i = 1 )
    {
      _mm_lfence();
      if ( CmpString(
             (&off_100CB5A50)[2 * (unsigned __int8)i],
             *((_DWORD *)&off_100CB5A50 + 4 * (unsigned __int8)i + 2),
             (const WCHAR *)v19,
             ModuleFileNameW - (unsigned int)(((_BYTE *)v19 - (_BYTE *)&FileName) >> 1)) )
      {
        v13 = 1;
      }
    }
    qmemcpy(v18 + 1, L"ini", (unsigned int)(2 * v11));
    v5 = 0;
  }
  if ( v13 || GetFileAttributesW(&FileName) == -1 )
  {
LABEL_39:
    CEsCacheObj::Serialize(v5, v4);
    return 0;
  }
  else
  {
    qmemcpy(qword_100CD4900, &FileName, 0x208u);
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)qword_100CD4900 + v16) );
    for ( j = (char *)qword_100CD4900 + 2 * v16 - 2; *(_WORD *)j != 92 && j > (char *)qword_100CD4900; j -= 2 )
      ;
    *(_WORD *)j = 0;
    dword_100CD46E4 = ((j - (char *)qword_100CD4900) >> 1) + 1;
    Trace(L"wszIniRegDirectory %s \r\n", qword_100CD4900);
    qmemcpy(qword_100CD4B10, &FileName, 0x208u);
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)qword_100CD4B10 + v17) );
    qmemcpy((char *)qword_100CD4B10 + 2 * (unsigned int)v17, L".ext", 0xAu);
    Trace(L"g_wszIniRegExtPath: %s \r\n", qword_100CD4B10);
    dword_100CD46D8 = a3;
    dword_100CD46E0 = 1;
    CEsCacheObj::Serialize(v7, v6);
    return 1;
  }
}

```

## disassembly

```asm
0x10082b650  mov     [rsp+arg_10], r8d
0x10082b655  mov     [rsp+arg_8], rdx
0x10082b65a  mov     [rsp+hModule], rcx
0x10082b65f  push    rsi
0x10082b660  push    rdi
0x10082b661  sub     rsp, 0B8h
0x10082b668  cmp     cs:dword_100CD46E0, 0
0x10082b66f  jz      short loc_10082B67B
0x10082b671  mov     eax, 1
0x10082b676  jmp     loc_10082BA80
0x10082b67b  call    ?Serialize@CEsCacheObj@@UEAAXPEAV?$CSerializeContext@VRPCStream@@@@I@Z; CEsCacheObj::Serialize(CSerializeContext<RPCStream> *,uint)
0x10082b680  lea     rcx, aIniregistrylib; "IniRegistryLib is getting loaded.\r\n"
0x10082b687  call    Trace
0x10082b68c  cmp     [rsp+0C8h+arg_8], 0
0x10082b695  jz      short loc_10082B6D8
0x10082b697  mov     rax, [rsp+0C8h+arg_8]
0x10082b69f  mov     [rsp+0C8h+var_38], rax
0x10082b6a7  mov     [rsp+0C8h+var_80], 0FFFFFFFFFFFFFFFFh
0x10082b6b0  inc     [rsp+0C8h+var_80]
0x10082b6b5  mov     rax, [rsp+0C8h+var_38]
0x10082b6bd  mov     rcx, [rsp+0C8h+var_80]
0x10082b6c2  cmp     word ptr [rax+rcx*2], 0
0x10082b6c7  jnz     short loc_10082B6B0
0x10082b6c9  mov     rax, [rsp+0C8h+var_80]
0x10082b6ce  mov     [rsp+0C8h+var_48], rax
0x10082b6d6  jmp     short loc_10082B6E4
0x10082b6d8  mov     [rsp+0C8h+var_48], 3
0x10082b6e4  mov     eax, dword ptr [rsp+0C8h+var_48]
0x10082b6eb  inc     eax
0x10082b6ed  mov     [rsp+0C8h+var_94], eax
0x10082b6f1  mov     eax, [rsp+0C8h+var_94]
0x10082b6f5  mov     ecx, 104h
0x10082b6fa  sub     rcx, rax
0x10082b6fd  mov     rax, rcx
0x10082b700  mov     r8d, eax; nSize
0x10082b703  lea     rdx, FileName; lpFilename
0x10082b70a  mov     rcx, [rsp+0C8h+hModule]; hModule
0x10082b712  call    cs:__imp_GetModuleFileNameW
0x10082b718  mov     [rsp+0C8h+var_98], eax
0x10082b71c  cmp     [rsp+0C8h+var_98], 0
0x10082b721  jbe     loc_10082BA79
0x10082b727  lfence
0x10082b72a  mov     eax, [rsp+0C8h+var_98]
0x10082b72e  lea     rcx, FileName
0x10082b735  lea     rax, [rcx+rax*2-2]
0x10082b73a  mov     [rsp+0C8h+var_A0], rax
0x10082b73f  mov     rdx, [rsp+0C8h+var_A0]
0x10082b744  lea     rcx, aS_2; "%s \r\n"
0x10082b74b  call    Trace
0x10082b750  mov     [rsp+0C8h+var_78], 0
0x10082b759  mov     [rsp+0C8h+var_58], 0
0x10082b762  cmp     [rsp+0C8h+var_78], 0
0x10082b768  jnz     short loc_10082B7C0
0x10082b76a  lea     rax, FileName
0x10082b771  cmp     [rsp+0C8h+var_A0], rax
0x10082b776  jbe     short loc_10082B7C0
0x10082b778  cmp     [rsp+0C8h+var_58], 0
0x10082b77e  jnz     short loc_10082B799
0x10082b780  mov     rax, [rsp+0C8h+var_A0]
0x10082b785  movzx   eax, word ptr [rax]
0x10082b788  cmp     eax, 2Eh ; '.'
0x10082b78b  jnz     short loc_10082B797
0x10082b78d  mov     rax, [rsp+0C8h+var_A0]
0x10082b792  mov     [rsp+0C8h+var_58], rax
0x10082b797  jmp     short loc_10082B7B0
0x10082b799  mov     rax, [rsp+0C8h+var_A0]
0x10082b79e  movzx   eax, word ptr [rax]
0x10082b7a1  cmp     eax, 5Ch ; '\'
0x10082b7a4  jnz     short loc_10082B7B0
0x10082b7a6  mov     rax, [rsp+0C8h+var_A0]
0x10082b7ab  mov     [rsp+0C8h+var_78], rax
0x10082b7b0  mov     rax, [rsp+0C8h+var_A0]
0x10082b7b5  sub     rax, 2
0x10082b7b9  mov     [rsp+0C8h+var_A0], rax
0x10082b7be  jmp     short loc_10082B762
0x10082b7c0  cmp     [rsp+0C8h+var_78], 0
0x10082b7c6  jz      loc_10082BA79
0x10082b7cc  mov     [rsp+0C8h+var_88], 0
0x10082b7d4  mov     rax, [rsp+0C8h+var_78]
0x10082b7d9  add     rax, 2
0x10082b7dd  mov     [rsp+0C8h+var_50], rax
0x10082b7e2  mov     rax, [rsp+0C8h+var_58]
0x10082b7e7  add     rax, 2
0x10082b7eb  mov     [rsp+0C8h+var_30], rax
0x10082b7f3  cmp     [rsp+0C8h+arg_8], 0
0x10082b7fc  jz      short loc_10082B81D
0x10082b7fe  mov     eax, [rsp+0C8h+var_94]
0x10082b802  shl     rax, 1
0x10082b805  mov     eax, eax
0x10082b807  mov     rdi, [rsp+0C8h+var_50]
0x10082b80c  mov     rsi, [rsp+0C8h+arg_8]
0x10082b814  mov     ecx, eax
0x10082b816  rep movsb
0x10082b818  jmp     loc_10082B8D1
0x10082b81d  lea     rax, FileName
0x10082b824  mov     rcx, [rsp+0C8h+var_50]
0x10082b829  sub     rcx, rax
0x10082b82c  mov     rax, rcx
0x10082b82f  sar     rax, 1
0x10082b832  mov     ecx, [rsp+0C8h+var_98]
0x10082b836  sub     ecx, eax
0x10082b838  mov     eax, ecx
0x10082b83a  mov     [rsp+0C8h+var_60], eax
0x10082b83e  mov     [rsp+0C8h+var_A8], 0
0x10082b846  jmp     short loc_10082B852
0x10082b848  mov     eax, [rsp+0C8h+var_A8]
0x10082b84c  inc     eax
0x10082b84e  mov     [rsp+0C8h+var_A8], eax
0x10082b852  mov     eax, [rsp+0C8h+var_A8]
0x10082b856  cmp     rax, 1
0x10082b85a  jnb     short loc_10082B8B2
0x10082b85c  lfence
0x10082b85f  mov     eax, [rsp+0C8h+var_A8]
0x10082b863  imul    rax, 10h
0x10082b867  lea     rcx, off_100CB5A50; "msmdsrv.exe"
0x10082b86e  add     rcx, rax
0x10082b871  mov     rax, rcx
0x10082b874  mov     [rsp+0C8h+var_40], rax
0x10082b87c  mov     r9d, [rsp+0C8h+var_60]
0x10082b881  mov     r8, [rsp+0C8h+var_50]
0x10082b886  mov     rax, [rsp+0C8h+var_40]
0x10082b88e  mov     edx, [rax+8]
0x10082b891  mov     rax, [rsp+0C8h+var_40]
0x10082b899  mov     rcx, [rax]
0x10082b89c  call    CmpString
0x10082b8a1  movzx   eax, al
0x10082b8a4  test    eax, eax
0x10082b8a6  jz      short loc_10082B8B0
0x10082b8a8  mov     [rsp+0C8h+var_88], 1
0x10082b8b0  jmp     short loc_10082B848
0x10082b8b2  mov     eax, [rsp+0C8h+var_94]
0x10082b8b6  shl     rax, 1
0x10082b8b9  mov     eax, eax
0x10082b8bb  lea     rcx, aIni; "ini"
0x10082b8c2  mov     rdi, [rsp+0C8h+var_30]
0x10082b8ca  mov     rsi, rcx
0x10082b8cd  mov     ecx, eax
0x10082b8cf  rep movsb
0x10082b8d1  cmp     [rsp+0C8h+var_88], 0
0x10082b8d6  jnz     loc_10082BA79
0x10082b8dc  lea     rcx, FileName; lpFileName
0x10082b8e3  call    cs:__imp_GetFileAttributesW
0x10082b8e9  cmp     eax, 0FFFFFFFFh
0x10082b8ec  jz      loc_10082BA79
0x10082b8f2  lea     rax, qword_100CD4900
0x10082b8f9  lea     rcx, FileName
0x10082b900  mov     rdi, rax
0x10082b903  mov     rsi, rcx
0x10082b906  mov     ecx, 208h
0x10082b90b  rep movsb
0x10082b90d  lea     rax, qword_100CD4900
0x10082b914  mov     [rsp+0C8h+var_28], rax
0x10082b91c  mov     [rsp+0C8h+var_70], 0FFFFFFFFFFFFFFFFh
0x10082b925  inc     [rsp+0C8h+var_70]
0x10082b92a  mov     rax, [rsp+0C8h+var_28]
0x10082b932  mov     rcx, [rsp+0C8h+var_70]
0x10082b937  cmp     word ptr [rax+rcx*2], 0
0x10082b93c  jnz     short loc_10082B925
0x10082b93e  mov     rax, [rsp+0C8h+var_70]
0x10082b943  lea     rcx, qword_100CD4900
0x10082b94a  lea     rax, [rcx+rax*2-2]
0x10082b94f  mov     [rsp+0C8h+var_90], rax
0x10082b954  mov     eax, 2
0x10082b959  imul    rax, 0
0x10082b95d  mov     rcx, [rsp+0C8h+var_90]
0x10082b962  movzx   eax, word ptr [rcx+rax]
0x10082b966  cmp     eax, 5Ch ; '\'
0x10082b969  jz      short loc_10082B989
0x10082b96b  lea     rax, qword_100CD4900
0x10082b972  cmp     [rsp+0C8h+var_90], rax
0x10082b977  jbe     short loc_10082B989
0x10082b979  mov     rax, [rsp+0C8h+var_90]
0x10082b97e  sub     rax, 2
0x10082b982  mov     [rsp+0C8h+var_90], rax
0x10082b987  jmp     short loc_10082B954
0x10082b989  mov     eax, 2
0x10082b98e  imul    rax, 0
0x10082b992  xor     ecx, ecx
0x10082b994  mov     rdx, [rsp+0C8h+var_90]
0x10082b999  mov     [rdx+rax], cx
0x10082b99d  lea     rax, qword_100CD4900
0x10082b9a4  mov     rcx, [rsp+0C8h+var_90]
0x10082b9a9  sub     rcx, rax
0x10082b9ac  mov     rax, rcx
0x10082b9af  sar     rax, 1
0x10082b9b2  inc     rax
0x10082b9b5  mov     cs:dword_100CD46E4, eax
0x10082b9bb  lea     rdx, qword_100CD4900
0x10082b9c2  lea     rcx, aWsziniregdirec; "wszIniRegDirectory %s \r\n"
0x10082b9c9  call    Trace
0x10082b9ce  lea     rax, qword_100CD4B10
0x10082b9d5  lea     rcx, FileName
0x10082b9dc  mov     rdi, rax
0x10082b9df  mov     rsi, rcx
0x10082b9e2  mov     ecx, 208h
0x10082b9e7  rep movsb
0x10082b9e9  lea     rax, qword_100CD4B10
0x10082b9f0  mov     [rsp+0C8h+var_20], rax
0x10082b9f8  mov     [rsp+0C8h+var_68], 0FFFFFFFFFFFFFFFFh
0x10082ba01  inc     [rsp+0C8h+var_68]
0x10082ba06  mov     rax, [rsp+0C8h+var_20]
0x10082ba0e  mov     rcx, [rsp+0C8h+var_68]
0x10082ba13  cmp     word ptr [rax+rcx*2], 0
0x10082ba18  jnz     short loc_10082BA01
0x10082ba1a  mov     rax, [rsp+0C8h+var_68]
0x10082ba1f  mov     [rsp+0C8h+var_5C], eax
0x10082ba23  mov     eax, [rsp+0C8h+var_5C]
0x10082ba27  lea     rcx, qword_100CD4B10
0x10082ba2e  lea     rdx, aExt; ".ext"
0x10082ba35  lea     rdi, [rcx+rax*2]
0x10082ba39  mov     rsi, rdx
0x10082ba3c  mov     ecx, 0Ah
0x10082ba41  rep movsb
0x10082ba43  lea     rdx, qword_100CD4B10
0x10082ba4a  lea     rcx, aGWsziniregextp; "g_wszIniRegExtPath: %s \r\n"
0x10082ba51  call    Trace
0x10082ba56  mov     eax, [rsp+0C8h+arg_10]
0x10082ba5d  mov     cs:dword_100CD46D8, eax
0x10082ba63  mov     cs:dword_100CD46E0, 1
0x10082ba6d  call    ?Serialize@CEsCacheObj@@UEAAXPEAV?$CSerializeContext@VRPCStream@@@@I@Z; CEsCacheObj::Serialize(CSerializeContext<RPCStream> *,uint)
0x10082ba72  mov     eax, 1
0x10082ba77  jmp     short loc_10082BA80
0x10082ba79  call    ?Serialize@CEsCacheObj@@UEAAXPEAV?$CSerializeContext@VRPCStream@@@@I@Z; CEsCacheObj::Serialize(CSerializeContext<RPCStream> *,uint)
0x10082ba7e  xor     eax, eax
0x10082ba80  add     rsp, 0B8h
0x10082ba87  pop     rdi
0x10082ba88  pop     rsi
0x10082ba89  retn
```
