# SxGetSystemVolume(ushort *,ulong)

- ea: `0x1800295bc`
- end: `0x1800297a6`
- name: `?SxGetSystemVolume@@YAJPEAGK@Z`
- size: `490`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x180016fac`

## callees

- `0x180020d98`
- `0x1800268b4`
- `0x1800269ac`
- `0x1800295bc`
- `0x1800297ac`
- `0x18002d6e8`
- `0x1800353c4`
- `0x180035b00`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x1800296a4`
- `KERNEL32!GetVolumePathNameW` at `0x1800296a4`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800296d8`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800296d8`

## pseudocode

```c
__int64 __fastcall SxGetSystemVolume(unsigned __int16 *a1)
{
  unsigned __int16 v2; // dx
  int SystemVolumeGlobalPath; // ebx
  __int16 v4; // ax
  __int64 v5; // rcx
  __int16 v6; // ax
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  LPCWSTR lpszFileName[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v13; // [rsp+44h] [rbp-BCh]
  __int16 v14; // [rsp+46h] [rbp-BAh]
  WCHAR szVolumePathName; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v16[526]; // [rsp+82h] [rbp-7Eh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SxGetSystemVolume", 1024, 1);
  lpszFileName[1] = 0;
  lpszFileName[0] = &FileName;
  szVolumePathName = 0;
  memset_0(v16, 0, 0x206u);
  if ( !a1 )
  {
    SystemVolumeGlobalPath = -2147024809;
    v4 = 1032;
    v12 = -2147024809;
LABEL_12:
    v14 = v4;
LABEL_13:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&szVolumePathName, (__int64)a1);
      SystemVolumeGlobalPath = v12;
    }
    goto LABEL_16;
  }
  *a1 = 0;
  v12 = 0;
  v13 = 1033;
  SystemVolumeGlobalPath = SxGetSystemVolumeGlobalPath((struct CBsString *)lpszFileName);
  v12 = SystemVolumeGlobalPath;
  v4 = 1035;
  if ( SystemVolumeGlobalPath < 0 )
    goto LABEL_12;
  v13 = 1035;
  SystemVolumeGlobalPath = CBsString::Trailing((CBsString *)lpszFileName, v2);
  v12 = SystemVolumeGlobalPath;
  v4 = 1041;
  if ( SystemVolumeGlobalPath < 0 )
    goto LABEL_12;
  v13 = 1041;
  if ( GetVolumePathNameW(lpszFileName[0], &szVolumePathName, 0x104u) )
  {
    v12 = 0;
    v13 = 1043;
    if ( GetVolumeNameForVolumeMountPointW(&szVolumePathName, a1, 0x104u) )
    {
      SystemVolumeGlobalPath = 0;
      v12 = 0;
      v13 = 1045;
      goto LABEL_16;
    }
    SystemVolumeGlobalPath = GetLastFailureAsHRESULT(v7);
    v6 = 1045;
  }
  else
  {
    SystemVolumeGlobalPath = GetLastFailureAsHRESULT(v5);
    v6 = 1043;
  }
  v14 = v6;
  v12 = SystemVolumeGlobalPath;
  if ( SystemVolumeGlobalPath < 0 )
    goto LABEL_13;
LABEL_16:
  CBsString::_Release((unsigned __int16 **)lpszFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12, v8, v9);
  return (unsigned int)SystemVolumeGlobalPath;
}

```

## disassembly

```asm
0x1800295bc  mov     [rsp-8+arg_8], rbx
0x1800295c1  mov     [rsp-8+arg_10], rdi
0x1800295c6  push    rbp
0x1800295c7  lea     rbp, [rsp-1A0h]
0x1800295cf  sub     rsp, 2A0h
0x1800295d6  mov     rax, cs:__security_cookie
0x1800295dd  xor     rax, rsp
0x1800295e0  mov     [rbp+1A0h+var_10], rax
0x1800295e7  mov     rdi, rcx
0x1800295ea  lea     rdx, aSxgetsystemvol; "SxGetSystemVolume"
0x1800295f1  lea     rcx, [rsp+2A0h+var_260]; this
0x1800295f6  mov     r9d, 1; unsigned __int16
0x1800295fc  mov     r8d, 400h; unsigned __int16
0x180029602  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180029607  lea     rax, FileName
0x18002960e  mov     [rsp+2A0h+var_268], 0
0x180029617  mov     [rsp+2A0h+lpszFileName], rax
0x18002961c  lea     rcx, [rbp+1A0h+var_21E]; void *
0x180029620  xor     eax, eax
0x180029622  xor     edx, edx; Val
0x180029624  mov     r8d, 206h; Size
0x18002962a  mov     [rbp+1A0h+szVolumePathName], ax
0x18002962e  call    memset_0
0x180029633  test    rdi, rdi
0x180029636  jz      loc_180029711
0x18002963c  xor     eax, eax
0x18002963e  lea     rcx, [rsp+2A0h+lpszFileName]; this
0x180029643  mov     [rdi], ax
0x180029646  mov     [rsp+2A0h+var_260], eax
0x18002964a  mov     eax, 409h
0x18002964f  mov     [rsp+2A0h+var_25C], ax
0x180029654  call    ?SxGetSystemVolumeGlobalPath@@YAJPEAVCBsString@@@Z; SxGetSystemVolumeGlobalPath(CBsString *)
0x180029659  mov     ebx, eax
0x18002965b  mov     [rsp+2A0h+var_260], eax
0x18002965f  test    eax, eax
0x180029661  mov     eax, 40Bh
0x180029666  js      loc_18002971F
0x18002966c  lea     rcx, [rsp+2A0h+lpszFileName]; this
0x180029671  mov     [rsp+2A0h+var_25C], ax
0x180029676  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18002967b  mov     ebx, eax
0x18002967d  mov     [rsp+2A0h+var_260], eax
0x180029681  test    eax, eax
0x180029683  mov     eax, 411h
0x180029688  js      loc_18002971F
0x18002968e  mov     rcx, [rsp+2A0h+lpszFileName]; lpszFileName
0x180029693  lea     rdx, [rbp+1A0h+szVolumePathName]; lpszVolumePathName
0x180029697  mov     ebx, 104h
0x18002969c  mov     [rsp+2A0h+var_25C], ax
0x1800296a1  mov     r8d, ebx; cchBufferLength
0x1800296a4  call    cs:__imp_GetVolumePathNameW
0x1800296aa  test    eax, eax
0x1800296ac  jnz     short loc_1800296BC
0x1800296ae  call    GetLastFailureAsHRESULT
0x1800296b3  mov     ebx, eax
0x1800296b5  mov     eax, 413h
0x1800296ba  jmp     short loc_1800296EE
0x1800296bc  mov     eax, 413h
0x1800296c1  mov     [rsp+2A0h+var_260], 0
0x1800296c9  mov     r8d, ebx; cchBufferLength
0x1800296cc  mov     [rsp+2A0h+var_25C], ax
0x1800296d1  mov     rdx, rdi; lpszVolumeName
0x1800296d4  lea     rcx, [rbp+1A0h+szVolumePathName]; lpszVolumeMountPoint
0x1800296d8  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800296de  test    eax, eax
0x1800296e0  jnz     short loc_1800296FF
0x1800296e2  call    GetLastFailureAsHRESULT
0x1800296e7  mov     ebx, eax
0x1800296e9  mov     eax, 415h
0x1800296ee  mov     [rsp+2A0h+var_25A], ax
0x1800296f3  mov     eax, ebx
0x1800296f5  mov     [rsp+2A0h+var_260], ebx
0x1800296f9  test    eax, eax
0x1800296fb  jns     short loc_18002976C
0x1800296fd  jmp     short loc_180029724
0x1800296ff  xor     ebx, ebx
0x180029701  mov     eax, 415h
0x180029706  mov     [rsp+2A0h+var_260], ebx
0x18002970a  mov     [rsp+2A0h+var_25C], ax
0x18002970f  jmp     short loc_18002976C
0x180029711  mov     ebx, 80070057h
0x180029716  mov     eax, 408h
0x18002971b  mov     [rsp+2A0h+var_260], ebx
0x18002971f  mov     [rsp+2A0h+var_25A], ax
0x180029724  mov     rcx, cs:WPP_GLOBAL_Control
0x18002972b  lea     rax, WPP_GLOBAL_Control
0x180029732  cmp     rcx, rax
0x180029735  jz      short loc_18002976C
0x180029737  test    dword ptr [rcx+1Ch], 2000000h
0x18002973e  jz      short loc_18002976C
0x180029740  mov     r9, [rsp+2A0h+lpszFileName]
0x180029745  lea     rax, [rbp+1A0h+szVolumePathName]
0x180029749  mov     rcx, [rcx+10h]; LoggerHandle
0x18002974d  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180029754  mov     edx, 1Bh
0x180029759  mov     [rsp+2A0h+var_278], rdi; __int64
0x18002975e  mov     [rsp+2A0h+var_280], rax; __int64
0x180029763  call    WPP_SF_SSS
0x180029768  mov     ebx, [rsp+2A0h+var_260]
0x18002976c  lea     rcx, [rsp+2A0h+lpszFileName]; this
0x180029771  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180029776  lea     rcx, [rsp+2A0h+var_260]; this
0x18002977b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180029780  mov     eax, ebx
0x180029782  mov     rcx, [rbp+1A0h+var_10]
0x180029789  xor     rcx, rsp; StackCookie
0x18002978c  call    __security_check_cookie
0x180029791  lea     r11, [rsp+2A0h+var_s0]
0x180029799  mov     rbx, [r11+18h]
0x18002979d  mov     rdi, [r11+20h]
0x1800297a1  mov     rsp, r11
0x1800297a4  pop     rbp
0x1800297a5  retn
```
