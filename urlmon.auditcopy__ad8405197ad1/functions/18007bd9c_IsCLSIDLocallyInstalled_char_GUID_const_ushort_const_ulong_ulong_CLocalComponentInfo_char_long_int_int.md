# IsCLSIDLocallyInstalled(char *,_GUID * const,ushort const *,ulong,ulong,CLocalComponentInfo *,char *,long *,int,int *)

- ea: `0x18007bd9c`
- end: `0x18007c102`
- name: `?IsCLSIDLocallyInstalled@@YAJPEADQEAU_GUID@@PEBGKKPEAVCLocalComponentInfo@@0PEAJHPEAH@Z`
- size: `870`
- prototype: `__int64 __fastcall(char *, struct _GUID *const, const unsigned __int16 *, unsigned int, unsigned int, struct CLocalComponentInfo *, char *lpSubKey, int *hkey, int, int *phkResult)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007b978`

## callees

- `0x18002fee0`
- `0x18007bcc8`
- `0x18007bd9c`
- `0x18007c108`
- `0x18007d014`
- `0x1800a4ac0`
- `0x1800d1580`
- `0x1800d1c08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007be38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007be8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007bf04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007bf39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007bfd4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007be38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007be8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007bf04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007bf39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007bfd4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007bf76`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007c018`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007bf76`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007c018`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007bf93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007bfa6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c0db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007bf93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007bfa6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c0db`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007bdff`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007bdff`

## string_xrefs

- `0x18007be2a`: `CLSID`

## pseudocode

```c
__int64 __fastcall IsCLSIDLocallyInstalled(
        char *a1,
        struct _GUID *const a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        DWORD a5,
        struct CLocalComponentInfo *a6,
        char *lpSubKey,
        int *hkey,
        int a9,
        int *phkResult)
{
  int *v10; // r14
  char *v11; // rsi
  int *v12; // rdi
  int v15; // ebx
  struct CLocalComponentInfo *pvData; // rdi
  unsigned int v17; // r15d
  int v18; // eax
  HKEY v19; // rcx
  const char *v20; // r8
  __int64 v21; // r9
  LPOLESTR lpsz; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h] BYREF
  DWORD pdwType; // [rsp+90h] [rbp+40h] BYREF
  int v26; // [rsp+94h] [rbp+44h]
  DWORD pcbData; // [rsp+A0h] [rbp+50h] BYREF
  int v28; // [rsp+A4h] [rbp+54h]

  v28 = HIDWORD(a3);
  v26 = HIDWORD(a1);
  v10 = phkResult;
  v11 = 0;
  v12 = hkey;
  lpSubKey = 0;
  lpsz = 0;
  *phkResult = 0;
  pdwType = 0;
  hKey = 0;
  pcbData = 260;
  if ( v12 )
    *v12 = -2147467259;
  v15 = StringFromCLSID(a2, &lpsz);
  if ( v15 >= 0 )
  {
    if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x20019u, &hKey) )
    {
      v15 = Unicode2Ansi(lpsz, &lpSubKey);
      if ( v15 < 0 )
      {
        v11 = lpSubKey;
        goto LABEL_31;
      }
      phkResult = 0;
      hkey = 0;
      v11 = lpSubKey;
      if ( !RegOpenKeyExA(hKey, lpSubKey, 0, 0x20019u, (PHKEY)&phkResult) )
      {
        if ( v12 )
          *v12 = 0;
        pvData = a6;
        v17 = a5;
        v18 = CheckInstalledVersionHint((HKEY)phkResult, a6, a4, a5);
        v15 = v18;
        if ( v18 >= 0 )
        {
          if ( v18 == 1 )
            *v10 = 1;
          goto LABEL_19;
        }
        lpSubKey = 0;
        if ( !RegOpenKeyExA((HKEY)phkResult, "AppID", 0, 0x20019u, (PHKEY)&lpSubKey) )
        {
          v19 = (HKEY)lpSubKey;
          v15 = 0;
LABEL_18:
          RegCloseKey(v19);
LABEL_19:
          RegCloseKey((HKEY)phkResult);
          goto LABEL_31;
        }
        if ( RegOpenKeyExA((HKEY)phkResult, "InProcServer32", 0, 0x20019u, (PHKEY)&hkey) )
        {
          if ( RegOpenKeyExA((HKEY)phkResult, "LocalServer32", 0, 0x20019u, (PHKEY)&hkey) )
          {
            v15 = 1;
            goto LABEL_19;
          }
          pcbData = 260;
          if ( RegGetValueA((HKEY)hkey, 0, 0, 0xFFFFu, &pdwType, pvData, &pcbData) )
            goto LABEL_16;
          GetEXEName((char *)pvData);
        }
        else
        {
          pcbData = 260;
          if ( RegGetValueA((HKEY)hkey, 0, 0, 0xFFFFu, &pdwType, pvData, &pcbData) )
            goto LABEL_16;
        }
        if ( SearchPathA_Wrap(0, (const char *)pvData, v20, v21, (LPSTR)pvData, (LPSTR *)pvData + 33) )
        {
          v15 = LocalVersionOK((HKEY)phkResult, pvData, (unsigned __int64)a2, a4, v17, a9);
          if ( v15 == 1 )
            *v10 = 1;
          if ( *((_DWORD *)pvData + 77) )
            v15 = NeedForceLanguageCheck((HKEY)phkResult, pvData);
          goto LABEL_17;
        }
LABEL_16:
        v15 = 1;
LABEL_17:
        v19 = (HKEY)hkey;
        goto LABEL_18;
      }
    }
    v15 = 1;
  }
LABEL_31:
  if ( lpsz )
    operator delete(lpsz);
  if ( v11 )
    operator delete(v11);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18007bd9c  mov     [rsp-38h+arg_8], rbx
0x18007bda1  mov     qword ptr [rsp-38h+arg_10], r8
0x18007bda6  mov     qword ptr [rsp-38h+pdwType], rcx
0x18007bdab  push    rbp
0x18007bdac  push    rsi
0x18007bdad  push    rdi
0x18007bdae  push    r12
0x18007bdb0  push    r13
0x18007bdb2  push    r14
0x18007bdb4  push    r15
0x18007bdb6  mov     rbp, rsp
0x18007bdb9  sub     rsp, 50h
0x18007bdbd  mov     r14, [rbp+arg_48]
0x18007bdc4  xor     esi, esi
0x18007bdc6  mov     rdi, [rbp+hkey]
0x18007bdca  mov     r13d, r9d
0x18007bdcd  mov     [rbp+lpSubKey], rsi
0x18007bdd1  mov     r12, rdx
0x18007bdd4  mov     [rbp+lpsz], rsi
0x18007bdd8  mov     dword ptr [r14], 0
0x18007bddf  mov     [rbp+pdwType], esi
0x18007bde2  mov     [rbp+hKey], rsi
0x18007bde6  mov     [rbp+arg_10], 104h
0x18007bded  test    rdi, rdi
0x18007bdf0  jz      short loc_18007BDF8
0x18007bdf2  mov     dword ptr [rdi], 80004005h
0x18007bdf8  lea     rdx, [rbp+lpsz]; lplpsz
0x18007bdfc  mov     rcx, r12; rclsid
0x18007bdff  call    cs:__imp_StringFromCLSID
0x18007be06  nop     dword ptr [rax+rax+00h]
0x18007be0b  mov     ebx, eax
0x18007be0d  test    eax, eax
0x18007be0f  js      loc_18007C0B7
0x18007be15  lea     rax, [rbp+hKey]
0x18007be19  mov     r15d, 20019h
0x18007be1f  mov     r9d, r15d; samDesired
0x18007be22  mov     [rsp+50h+phkResult], rax; phkResult
0x18007be27  xor     r8d, r8d; ulOptions
0x18007be2a  lea     rdx, aClsid_3; "CLSID"
0x18007be31  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18007be38  call    cs:__imp_RegOpenKeyExA
0x18007be3f  nop     dword ptr [rax+rax+00h]
0x18007be44  test    eax, eax
0x18007be46  jnz     loc_18007C0B2
0x18007be4c  mov     rcx, [rbp+lpsz]; lpWideCharStr
0x18007be50  lea     rdx, [rbp+lpSubKey]
0x18007be54  call    Unicode2Ansi
0x18007be59  mov     ebx, eax
0x18007be5b  test    eax, eax
0x18007be5d  js      loc_18007C0AC
0x18007be63  mov     rcx, [rbp+hKey]; hKey
0x18007be67  lea     rax, [rbp+arg_48]
0x18007be6e  mov     [rbp+arg_48], rsi
0x18007be75  mov     r9d, r15d; samDesired
0x18007be78  mov     [rbp+hkey], rsi
0x18007be7c  xor     r8d, r8d; ulOptions
0x18007be7f  mov     rsi, [rbp+lpSubKey]
0x18007be83  mov     rdx, rsi; lpSubKey
0x18007be86  mov     [rsp+50h+phkResult], rax; phkResult
0x18007be8b  call    cs:__imp_RegOpenKeyExA
0x18007be92  nop     dword ptr [rax+rax+00h]
0x18007be97  test    eax, eax
0x18007be99  jnz     loc_18007C0B2
0x18007be9f  test    rdi, rdi
0x18007bea2  jz      short loc_18007BEA6
0x18007bea4  mov     [rdi], eax
0x18007bea6  mov     rdi, [rbp+arg_28]
0x18007beaa  mov     r8d, r13d; unsigned int
0x18007bead  mov     r15d, [rbp+arg_20]
0x18007beb1  mov     rdx, rdi; struct CLocalComponentInfo *
0x18007beb4  mov     rcx, [rbp+arg_48]; hKey
0x18007bebb  mov     r9d, r15d; unsigned int
0x18007bebe  call    ?CheckInstalledVersionHint@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@KK@Z; CheckInstalledVersionHint(HKEY__ *,CLocalComponentInfo *,ulong,ulong)
0x18007bec3  mov     ebx, eax
0x18007bec5  test    eax, eax
0x18007bec7  js      short loc_18007BEDA
0x18007bec9  cmp     eax, 1
0x18007becc  jnz     loc_18007BF9F
0x18007bed2  mov     [r14], eax
0x18007bed5  jmp     loc_18007BF9F
0x18007beda  mov     rcx, [rbp+arg_48]; hKey
0x18007bee1  lea     rax, [rbp+lpSubKey]
0x18007bee5  mov     ebx, 20019h
0x18007beea  mov     [rbp+lpSubKey], 0
0x18007bef2  mov     r9d, ebx; samDesired
0x18007bef5  mov     [rsp+50h+phkResult], rax; phkResult
0x18007befa  xor     r8d, r8d; ulOptions
0x18007befd  lea     rdx, aAppid; "AppID"
0x18007bf04  call    cs:__imp_RegOpenKeyExA
0x18007bf0b  nop     dword ptr [rax+rax+00h]
0x18007bf10  test    eax, eax
0x18007bf12  jnz     short loc_18007BF1C
0x18007bf14  mov     rcx, [rbp+lpSubKey]
0x18007bf18  xor     ebx, ebx
0x18007bf1a  jmp     short loc_18007BF93
0x18007bf1c  mov     rcx, [rbp+arg_48]; hKey
0x18007bf23  lea     rax, [rbp+hkey]
0x18007bf27  mov     r9d, ebx; samDesired
0x18007bf2a  mov     [rsp+50h+phkResult], rax; phkResult
0x18007bf2f  xor     r8d, r8d; ulOptions
0x18007bf32  lea     rdx, aInprocserver32_0; "InProcServer32"
0x18007bf39  call    cs:__imp_RegOpenKeyExA
0x18007bf40  nop     dword ptr [rax+rax+00h]
0x18007bf45  test    eax, eax
0x18007bf47  jnz     short loc_18007BFB7
0x18007bf49  mov     rcx, [rbp+hkey]; hkey
0x18007bf4d  lea     rax, [rbp+arg_10]
0x18007bf51  mov     [rsp+50h+pcbData], rax; pcbData
0x18007bf56  mov     r9d, 0FFFFh; dwFlags
0x18007bf5c  lea     rax, [rbp+pdwType]
0x18007bf60  mov     [rsp+50h+pvData], rdi; pvData
0x18007bf65  xor     r8d, r8d; lpValue
0x18007bf68  mov     [rsp+50h+phkResult], rax; pdwType
0x18007bf6d  xor     edx, edx; lpSubKey
0x18007bf6f  mov     [rbp+arg_10], 104h
0x18007bf76  call    cs:__imp_RegGetValueA
0x18007bf7d  nop     dword ptr [rax+rax+00h]
0x18007bf82  test    eax, eax
0x18007bf84  jz      loc_18007C034
0x18007bf8a  mov     ebx, 1
0x18007bf8f  mov     rcx, [rbp+hkey]; hKey
0x18007bf93  call    cs:__imp_RegCloseKey
0x18007bf9a  nop     dword ptr [rax+rax+00h]
0x18007bf9f  mov     rcx, [rbp+arg_48]; hKey
0x18007bfa6  call    cs:__imp_RegCloseKey
0x18007bfad  nop     dword ptr [rax+rax+00h]
0x18007bfb2  jmp     loc_18007C0B7
0x18007bfb7  mov     rcx, [rbp+arg_48]; hKey
0x18007bfbe  lea     rax, [rbp+hkey]
0x18007bfc2  mov     r9d, ebx; samDesired
0x18007bfc5  mov     [rsp+50h+phkResult], rax; phkResult
0x18007bfca  xor     r8d, r8d; ulOptions
0x18007bfcd  lea     rdx, aLocalserver32_0; "LocalServer32"
0x18007bfd4  call    cs:__imp_RegOpenKeyExA
0x18007bfdb  nop     dword ptr [rax+rax+00h]
0x18007bfe0  test    eax, eax
0x18007bfe2  jz      short loc_18007BFEB
0x18007bfe4  mov     ebx, 1
0x18007bfe9  jmp     short loc_18007BF9F
0x18007bfeb  mov     rcx, [rbp+hkey]; hkey
0x18007bfef  lea     rax, [rbp+arg_10]
0x18007bff3  mov     [rsp+50h+pcbData], rax; pcbData
0x18007bff8  mov     r9d, 0FFFFh; dwFlags
0x18007bffe  lea     rax, [rbp+pdwType]
0x18007c002  mov     [rsp+50h+pvData], rdi; pvData
0x18007c007  xor     r8d, r8d; lpValue
0x18007c00a  mov     [rsp+50h+phkResult], rax; pdwType
0x18007c00f  xor     edx, edx; lpSubKey
0x18007c011  mov     [rbp+arg_10], 104h
0x18007c018  call    cs:__imp_RegGetValueA
0x18007c01f  nop     dword ptr [rax+rax+00h]
0x18007c024  test    eax, eax
0x18007c026  jnz     loc_18007BF8A
0x18007c02c  mov     rcx, rdi; char *
0x18007c02f  call    ?GetEXEName@@YAHPEADI@Z; GetEXEName(char *,uint)
0x18007c034  lea     rax, [rdi+108h]
0x18007c03b  mov     rdx, rdi; char *
0x18007c03e  mov     [rsp+50h+pvData], rax; LPSTR *
0x18007c043  xor     ecx, ecx; char *
0x18007c045  mov     [rsp+50h+phkResult], rdi; LPSTR
0x18007c04a  call    ?SearchPathA_Wrap@@YAKPEBD00KPEADPEAPEAD@Z; SearchPathA_Wrap(char const *,char const *,char const *,ulong,char *,char * *)
0x18007c04f  test    eax, eax
0x18007c051  jz      loc_18007BF8A
0x18007c057  mov     eax, [rbp+arg_40]
0x18007c05d  mov     r9d, r13d; unsigned int
0x18007c060  mov     rcx, [rbp+arg_48]; hKey
0x18007c067  mov     r8, r12; struct _GUID *
0x18007c06a  mov     dword ptr [rsp+50h+pvData], eax; int
0x18007c06e  mov     rdx, rdi; struct CLocalComponentInfo *
0x18007c071  mov     dword ptr [rsp+50h+phkResult], r15d; unsigned int
0x18007c076  call    ?LocalVersionOK@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@PEAU_GUID@@KKH@Z; LocalVersionOK(HKEY__ *,CLocalComponentInfo *,_GUID *,ulong,ulong,int)
0x18007c07b  mov     ebx, eax
0x18007c07d  cmp     eax, 1
0x18007c080  jnz     short loc_18007C089
0x18007c082  mov     dword ptr [r14], 1
0x18007c089  cmp     dword ptr [rdi+134h], 0
0x18007c090  jz      loc_18007BF8F
0x18007c096  mov     rcx, [rbp+arg_48]; HKEY
0x18007c09d  mov     rdx, rdi; struct CLocalComponentInfo *
0x18007c0a0  call    ?NeedForceLanguageCheck@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@@Z; NeedForceLanguageCheck(HKEY__ *,CLocalComponentInfo *)
0x18007c0a5  mov     ebx, eax
0x18007c0a7  jmp     loc_18007BF8F
0x18007c0ac  mov     rsi, [rbp+lpSubKey]
0x18007c0b0  jmp     short loc_18007C0B7
0x18007c0b2  mov     ebx, 1
0x18007c0b7  mov     rcx, [rbp+lpsz]; void *
0x18007c0bb  test    rcx, rcx
0x18007c0be  jz      short loc_18007C0C5
0x18007c0c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c0c5  test    rsi, rsi
0x18007c0c8  jz      short loc_18007C0D2
0x18007c0ca  mov     rcx, rsi; void *
0x18007c0cd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c0d2  mov     rcx, [rbp+hKey]; hKey
0x18007c0d6  test    rcx, rcx
0x18007c0d9  jz      short loc_18007C0E7
0x18007c0db  call    cs:__imp_RegCloseKey
0x18007c0e2  nop     dword ptr [rax+rax+00h]
0x18007c0e7  mov     eax, ebx
0x18007c0e9  mov     rbx, [rsp+50h+arg_8]
0x18007c0f1  add     rsp, 50h
0x18007c0f5  pop     r15
0x18007c0f7  pop     r14
0x18007c0f9  pop     r13
0x18007c0fb  pop     r12
0x18007c0fd  pop     rdi
0x18007c0fe  pop     rsi
0x18007c0ff  pop     rbp
0x18007c100  retn
```
