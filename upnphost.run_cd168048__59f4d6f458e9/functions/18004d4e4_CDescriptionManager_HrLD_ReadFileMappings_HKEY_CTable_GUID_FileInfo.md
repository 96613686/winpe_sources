# CDescriptionManager::HrLD_ReadFileMappings(HKEY__ *,CTable<_GUID,FileInfo> &)

- ea: `0x18004d4e4`
- end: `0x18004d752`
- name: `?HrLD_ReadFileMappings@CDescriptionManager@@AEAAJPEAUHKEY__@@AEAV?$CTable@U_GUID@@UFileInfo@@@@@Z`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004dc80`

## callees

- `0x180011cfc`
- `0x180029e68`
- `0x1800311fc`
- `0x180031534`
- `0x180032540`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x18004d4e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004d648`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004d662`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004d6a4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004d6b3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004d648`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004d662`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004d6a4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004d6b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d6c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d6e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d6c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d6e8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004d5e8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004d5e8`

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
0x18004d4e4  mov     [rsp-8+arg_0], rbx
0x18004d4e9  push    rbp
0x18004d4ea  push    rsi
0x18004d4eb  push    rdi
0x18004d4ec  push    r14
0x18004d4ee  push    r15
0x18004d4f0  lea     rbp, [rsp-1B0h]
0x18004d4f8  sub     rsp, 2B0h
0x18004d4ff  mov     rax, cs:__security_cookie
0x18004d506  xor     rax, rsp
0x18004d509  mov     [rbp+1D0h+var_30], rax
0x18004d510  mov     r15, r8
0x18004d513  mov     rbx, rdx
0x18004d516  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d51d  lea     rdi, WPP_GLOBAL_Control
0x18004d524  cmp     rcx, rdi
0x18004d527  jz      short loc_18004D544
0x18004d529  test    byte ptr [rcx+1Ch], 40h
0x18004d52d  jz      short loc_18004D544
0x18004d52f  mov     rcx, [rcx+10h]
0x18004d533  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18004d53a  mov     edx, 52h ; 'R'
0x18004d53f  call    WPP_SF_
0x18004d544  lea     r9, [rsp+2D0h+var_278]; HKEY *
0x18004d549  mov     [rsp+2D0h+var_278], 0
0x18004d552  mov     r8d, 2001Fh; unsigned int
0x18004d558  lea     rdx, SubKey; "Files"
0x18004d55f  mov     rcx, rbx; HKEY
0x18004d562  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18004d567  mov     esi, eax
0x18004d569  test    eax, eax
0x18004d56b  js      loc_18004D6FB
0x18004d571  mov     [rsp+2D0h+var_290], 104h
0x18004d579  xor     r14d, r14d
0x18004d57c  mov     qword ptr [rsp+2D0h+var_268.dwLowDateTime], 0
0x18004d585  mov     rcx, [rsp+2D0h+var_278]; HKEY
0x18004d58a  lea     rax, [rsp+2D0h+var_268]
0x18004d58f  lea     r9, [rsp+2D0h+var_290]; unsigned int *
0x18004d594  mov     [rsp+2D0h+var_2A0], rax; struct _FILETIME *
0x18004d599  lea     r8, [rbp+1D0h+sz]; unsigned __int16 *
0x18004d59d  mov     edx, r14d; unsigned int
0x18004d5a0  call    ?HrRegEnumKeyEx@@YAJPEAUHKEY__@@KPEAGPEAK12PEAU_FILETIME@@@Z; HrRegEnumKeyEx(HKEY__ *,ulong,ushort *,ulong *,ushort *,ulong *,_FILETIME *)
0x18004d5a5  test    eax, eax
0x18004d5a7  jnz     loc_18004D6E3
0x18004d5ad  mov     rcx, [rsp+2D0h+var_278]; HKEY
0x18004d5b2  lea     r9, [rsp+2D0h+hKey]; HKEY *
0x18004d5b7  mov     r8d, 2001Fh; unsigned int
0x18004d5bd  mov     [rsp+2D0h+hKey], 0
0x18004d5c6  lea     rdx, [rbp+1D0h+sz]; unsigned __int16 *
0x18004d5ca  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18004d5cf  mov     esi, eax
0x18004d5d1  test    eax, eax
0x18004d5d3  js      loc_18004D6D0
0x18004d5d9  xorps   xmm0, xmm0
0x18004d5dc  lea     rdx, [rbp+1D0h+pclsid]; pclsid
0x18004d5e0  lea     rcx, [rbp+1D0h+sz]; lpsz
0x18004d5e4  movups  xmmword ptr [rbp+1D0h+pclsid.Data1], xmm0
0x18004d5e8  call    cs:__imp_CLSIDFromString
0x18004d5ef  nop     dword ptr [rax+rax+00h]
0x18004d5f4  mov     esi, eax
0x18004d5f6  test    eax, eax
0x18004d5f8  js      loc_18004D6BF
0x18004d5fe  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18004d603  lea     r8, [rsp+2D0h+var_288]; this
0x18004d608  xor     ebx, ebx
0x18004d60a  mov     [rsp+2D0h+var_288], 0
0x18004d613  lea     rdx, aFilename; "Filename"
0x18004d61a  mov     [rsp+2D0h+var_270], rbx
0x18004d61f  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x18004d624  mov     esi, eax
0x18004d626  test    eax, eax
0x18004d628  js      short loc_18004D69C
0x18004d62a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18004d62f  lea     r8, [rsp+2D0h+var_270]; this
0x18004d634  lea     rdx, aMimetype_0; "Mimetype"
0x18004d63b  call    ?HrRegQueryString@@YAJPEAUHKEY__@@PEBGAEAVCUString@@@Z; HrRegQueryString(HKEY__ *,ushort const *,CUString &)
0x18004d640  mov     esi, eax
0x18004d642  test    eax, eax
0x18004d644  js      short loc_18004D697
0x18004d646  xor     ecx, ecx; Block
0x18004d648  call    cs:__imp_free
0x18004d64f  nop     dword ptr [rax+rax+00h]
0x18004d654  mov     rax, [rsp+2D0h+var_288]
0x18004d659  xor     ecx, ecx; Block
0x18004d65b  mov     [rsp+2D0h+var_260], rax
0x18004d660  xor     edi, edi
0x18004d662  call    cs:__imp_free
0x18004d669  nop     dword ptr [rax+rax+00h]
0x18004d66e  mov     rax, [rsp+2D0h+var_270]
0x18004d673  lea     r8, [rsp+2D0h+var_260]
0x18004d678  lea     rdx, [rbp+1D0h+pclsid]
0x18004d67c  mov     [rsp+2D0h+var_258], rax
0x18004d681  mov     rcx, r15
0x18004d684  call    ?HrInsertTransfer@?$CTable@U_GUID@@UFileInfo@@@@QEAAJAEAU_GUID@@AEAUFileInfo@@@Z; CTable<_GUID,FileInfo>::HrInsertTransfer(_GUID &,FileInfo &)
0x18004d689  lea     rcx, [rsp+2D0h+var_260]; this
0x18004d68e  mov     esi, eax
0x18004d690  call    ??1FileInfo@@QEAA@XZ; FileInfo::~FileInfo(void)
0x18004d695  jmp     short loc_18004D6A1
0x18004d697  mov     rbx, [rsp+2D0h+var_270]
0x18004d69c  mov     rdi, [rsp+2D0h+var_288]
0x18004d6a1  mov     rcx, rbx; Block
0x18004d6a4  call    cs:__imp_free
0x18004d6ab  nop     dword ptr [rax+rax+00h]
0x18004d6b0  mov     rcx, rdi; Block
0x18004d6b3  call    cs:__imp_free
0x18004d6ba  nop     dword ptr [rax+rax+00h]
0x18004d6bf  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18004d6c4  call    cs:__imp_RegCloseKey
0x18004d6cb  nop     dword ptr [rax+rax+00h]
0x18004d6d0  inc     r14d
0x18004d6d3  mov     [rsp+2D0h+var_290], 104h
0x18004d6db  test    esi, esi
0x18004d6dd  jns     loc_18004D585
0x18004d6e3  mov     rcx, [rsp+2D0h+var_278]; hKey
0x18004d6e8  call    cs:__imp_RegCloseKey
0x18004d6ef  nop     dword ptr [rax+rax+00h]
0x18004d6f4  lea     rdi, WPP_GLOBAL_Control
0x18004d6fb  test    esi, esi
0x18004d6fd  jz      short loc_18004D729
0x18004d6ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d706  cmp     rcx, rdi
0x18004d709  jz      short loc_18004D729
0x18004d70b  test    byte ptr [rcx+1Ch], 1
0x18004d70f  jz      short loc_18004D729
0x18004d711  mov     rcx, [rcx+10h]
0x18004d715  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18004d71c  mov     edx, 53h ; 'S'
0x18004d721  mov     r9d, esi
0x18004d724  call    WPP_SF_d
0x18004d729  mov     eax, esi
0x18004d72b  mov     rcx, [rbp+1D0h+var_30]
0x18004d732  xor     rcx, rsp; StackCookie
0x18004d735  call    __security_check_cookie
0x18004d73a  mov     rbx, [rsp+2D0h+arg_0]
0x18004d742  add     rsp, 2B0h
0x18004d749  pop     r15
0x18004d74b  pop     r14
0x18004d74d  pop     rdi
0x18004d74e  pop     rsi
0x18004d74f  pop     rbp
0x18004d750  retn
```
