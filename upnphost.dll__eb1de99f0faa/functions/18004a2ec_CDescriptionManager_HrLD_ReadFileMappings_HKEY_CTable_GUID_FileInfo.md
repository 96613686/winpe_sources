# CDescriptionManager::HrLD_ReadFileMappings(HKEY__ *,CTable<_GUID,FileInfo> &)

- ea: `0x18004a2ec`
- end: `0x18004a52f`
- name: `?HrLD_ReadFileMappings@CDescriptionManager@@AEAAJPEAUHKEY__@@AEAV?$CTable@U_GUID@@UFileInfo@@@@@Z`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004aaf0`

## callees

- `0x18001d254`
- `0x180028968`
- `0x1800290d0`
- `0x18002fb24`
- `0x1800309a4`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x18004a2ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a44a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a45e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a49a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a4a3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a44a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a45e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a49a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a4a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a4ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a4cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a4ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a4cc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004a3f0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004a3f0`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::HrLD_ReadFileMappings(__int64 a1, HKEY a2, __int64 a3)
{
  int String; // esi
  unsigned int v6; // r14d
  void *v7; // rbx
  void *v8; // rdi
  unsigned __int16 *v10; // [rsp+20h] [rbp-E0h]
  unsigned int *v11; // [rsp+28h] [rbp-D8h]
  unsigned int v12; // [rsp+40h] [rbp-C0h] BYREF
  void *v13; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v15; // [rsp+58h] [rbp-A8h] BYREF
  void *v16; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME v17; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v18[2]; // [rsp+70h] [rbp-90h] BYREF
  GUID pclsid; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[264]; // [rsp+90h] [rbp-70h] BYREF

  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids);
  v15 = 0;
  String = HrRegOpenKeyEx(a2, L"Files", 0x2001Fu, &v15);
  if ( String >= 0 )
  {
    v12 = 260;
    v6 = 0;
    v17 = 0;
    while ( 1 )
    {
      if ( (unsigned int)HrRegEnumKeyEx(v15, v6, sz, &v12, v10, v11, &v17) )
      {
LABEL_17:
        RegCloseKey(v15);
        goto LABEL_18;
      }
      hKey = 0;
      String = HrRegOpenKeyEx(v15, sz, 0x2001Fu, &hKey);
      if ( String >= 0 )
        break;
LABEL_16:
      ++v6;
      v12 = 260;
      if ( String < 0 )
        goto LABEL_17;
    }
    pclsid = 0;
    String = CLSIDFromString(sz, &pclsid);
    if ( String < 0 )
    {
LABEL_15:
      RegCloseKey(hKey);
      goto LABEL_16;
    }
    v7 = 0;
    v13 = 0;
    v16 = 0;
    String = HrRegQueryString(hKey, L"Filename", (struct CUString *)&v13);
    if ( String >= 0 )
    {
      String = HrRegQueryString(hKey, L"Mimetype", (struct CUString *)&v16);
      if ( String >= 0 )
      {
        free(0);
        v18[0] = v13;
        v8 = 0;
        free(0);
        v18[1] = v16;
        String = CTable<_GUID,FileInfo>::HrInsertTransfer(a3, &pclsid, v18);
        FileInfo::~FileInfo((FileInfo *)v18);
LABEL_14:
        free(v7);
        free(v8);
        goto LABEL_15;
      }
      v7 = v16;
    }
    v8 = v13;
    goto LABEL_14;
  }
LABEL_18:
  if ( String && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      83,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)String);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18004a2ec  mov     [rsp-8+arg_0], rbx
0x18004a2f1  push    rbp
0x18004a2f2  push    rsi
0x18004a2f3  push    rdi
0x18004a2f4  push    r14
0x18004a2f6  push    r15
0x18004a2f8  lea     rbp, [rsp-1B0h]
0x18004a300  sub     rsp, 2B0h
0x18004a307  mov     rax, cs:__security_cookie
0x18004a30e  xor     rax, rsp
0x18004a311  mov     [rbp+1D0h+var_30], rax
0x18004a318  mov     r15, r8
0x18004a31b  mov     rbx, rdx
0x18004a31e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a325  lea     rdi, WPP_GLOBAL_Control
0x18004a32c  cmp     rcx, rdi
0x18004a32f  jz      short loc_18004A34C
0x18004a331  test    byte ptr [rcx+1Ch], 40h
0x18004a335  jz      short loc_18004A34C
0x18004a337  mov     rcx, [rcx+10h]
0x18004a33b  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18004a342  mov     edx, 52h ; 'R'
0x18004a347  call    WPP_SF_
0x18004a34c  lea     r9, [rsp+2D0h+var_278]; HKEY *
0x18004a351  mov     [rsp+2D0h+var_278], 0
0x18004a35a  mov     r8d, 2001Fh; unsigned int
0x18004a360  lea     rdx, SubKey; "Files"
0x18004a367  mov     rcx, rbx; HKEY
0x18004a36a  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18004a36f  mov     esi, eax
0x18004a371  test    eax, eax
0x18004a373  js      loc_18004A4D9
0x18004a379  mov     [rsp+2D0h+var_290], 104h
0x18004a381  xor     r14d, r14d
0x18004a384  mov     qword ptr [rsp+2D0h+var_268.dwLowDateTime], 0
0x18004a38d  mov     rcx, [rsp+2D0h+var_278]; HKEY
0x18004a392  lea     rax, [rsp+2D0h+var_268]
0x18004a397  lea     r9, [rsp+2D0h+var_290]; unsigned int *
0x18004a39c  mov     [rsp+2D0h+var_2A0], rax; struct _FILETIME *
0x18004a3a1  lea     r8, [rbp+1D0h+sz]; unsigned __int16 *
0x18004a3a5  mov     edx, r14d; unsigned int
0x18004a3a8  call    ?HrRegEnumKeyEx@@YAJPEAUHKEY__@@KPEAGPEAK12PEAU_FILETIME@@@Z; HrRegEnumKeyEx(HKEY__ *,ulong,ushort *,ulong *,ushort *,ulong *,_FILETIME *)
0x18004a3ad  test    eax, eax
0x18004a3af  jnz     loc_18004A4C7
0x18004a3b5  mov     rcx, [rsp+2D0h+var_278]; HKEY
0x18004a3ba  lea     r9, [rsp+2D0h+hKey]; HKEY *
0x18004a3bf  mov     r8d, 2001Fh; unsigned int
0x18004a3c5  mov     [rsp+2D0h+hKey], 0
0x18004a3ce  lea     rdx, [rbp+1D0h+sz]; unsigned __int16 *
0x18004a3d2  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18004a3d7  mov     esi, eax
0x18004a3d9  test    eax, eax
0x18004a3db  js      loc_18004A4B4
0x18004a3e1  xorps   xmm0, xmm0
0x18004a3e4  lea     rdx, [rbp+1D0h+pclsid]; pclsid
0x18004a3e8  lea     rcx, [rbp+1D0h+sz]; lpsz
0x18004a3ec  movups  xmmword ptr [rbp+1D0h+pclsid.Data1], xmm0
0x18004a3f0  call    cs:__imp_CLSIDFromString
0x18004a3f6  mov     esi, eax
0x18004a3f8  test    eax, eax
0x18004a3fa  js      loc_18004A4A9
0x18004a400  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18004a405  lea     r8, [rsp+2D0h+var_288]; this
0x18004a40a  xor     ebx, ebx
0x18004a40c  mov     [rsp+2D0h+var_288], 0
0x18004a415  lea     rdx, aFilename; "Filename"
0x18004a41c  mov     [rsp+2D0h+var_270], rbx
0x18004a421  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x18004a426  mov     esi, eax
0x18004a428  test    eax, eax
0x18004a42a  js      short loc_18004A492
0x18004a42c  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18004a431  lea     r8, [rsp+2D0h+var_270]; this
0x18004a436  lea     rdx, aMimetype_0; "Mimetype"
0x18004a43d  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x18004a442  mov     esi, eax
0x18004a444  test    eax, eax
0x18004a446  js      short loc_18004A48D
0x18004a448  xor     ecx, ecx; Block
0x18004a44a  call    cs:__imp_free
0x18004a450  mov     rax, [rsp+2D0h+var_288]
0x18004a455  xor     ecx, ecx; Block
0x18004a457  mov     [rsp+2D0h+var_260], rax
0x18004a45c  xor     edi, edi
0x18004a45e  call    cs:__imp_free
0x18004a464  mov     rax, [rsp+2D0h+var_270]
0x18004a469  lea     r8, [rsp+2D0h+var_260]
0x18004a46e  lea     rdx, [rbp+1D0h+pclsid]
0x18004a472  mov     [rsp+2D0h+var_258], rax
0x18004a477  mov     rcx, r15
0x18004a47a  call    ?HrInsertTransfer@?$CTable@U_GUID@@UFileInfo@@@@QEAAJAEAU_GUID@@AEAUFileInfo@@@Z; CTable<_GUID,FileInfo>::HrInsertTransfer(_GUID &,FileInfo &)
0x18004a47f  lea     rcx, [rsp+2D0h+var_260]; this
0x18004a484  mov     esi, eax
0x18004a486  call    ??1FileInfo@@QEAA@XZ; FileInfo::~FileInfo(void)
0x18004a48b  jmp     short loc_18004A497
0x18004a48d  mov     rbx, [rsp+2D0h+var_270]
0x18004a492  mov     rdi, [rsp+2D0h+var_288]
0x18004a497  mov     rcx, rbx; Block
0x18004a49a  call    cs:__imp_free
0x18004a4a0  mov     rcx, rdi; Block
0x18004a4a3  call    cs:__imp_free
0x18004a4a9  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18004a4ae  call    cs:__imp_RegCloseKey
0x18004a4b4  inc     r14d
0x18004a4b7  mov     [rsp+2D0h+var_290], 104h
0x18004a4bf  test    esi, esi
0x18004a4c1  jns     loc_18004A38D
0x18004a4c7  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18004a4cc  call    cs:__imp_RegCloseKey
0x18004a4d2  lea     rdi, WPP_GLOBAL_Control
0x18004a4d9  test    esi, esi
0x18004a4db  jz      short loc_18004A507
0x18004a4dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4e4  cmp     rcx, rdi
0x18004a4e7  jz      short loc_18004A507
0x18004a4e9  test    byte ptr [rcx+1Ch], 1
0x18004a4ed  jz      short loc_18004A507
0x18004a4ef  mov     rcx, [rcx+10h]
0x18004a4f3  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18004a4fa  mov     edx, 53h ; 'S'
0x18004a4ff  mov     r9d, esi
0x18004a502  call    WPP_SF_d
0x18004a507  mov     eax, esi
0x18004a509  mov     rcx, [rbp+1D0h+var_30]
0x18004a510  xor     rcx, rsp; StackCookie
0x18004a513  call    __security_check_cookie
0x18004a518  mov     rbx, [rsp+2D0h+arg_0]
0x18004a520  add     rsp, 2B0h
0x18004a527  pop     r15
0x18004a529  pop     r14
0x18004a52b  pop     rdi
0x18004a52c  pop     rsi
0x18004a52d  pop     rbp
0x18004a52e  retn
```
