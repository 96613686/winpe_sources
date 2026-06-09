# CEcsPath::GetVolumeNameForPathName(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180062ffc`
- end: `0x1800632bc`
- name: `?GetVolumeNameForPathName@CEcsPath@@SAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z`
- size: `704`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName)`
- caller_count: `6`
- callee_count: `13`
- tags: `reparse_path`

## callers

- `0x180027bf4`
- `0x180031f0c`
- `0x180062c78`
- `0x1800632c4`
- `0x180063570`
- `0x1800c7390`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180008bdc`
- `0x180009384`
- `0x180010ee0`
- `0x180011314`
- `0x180015904`
- `0x18001db58`
- `0x180028490`
- `0x180062ffc`

## import_xrefs

- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18006318f`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180063201`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18006318f`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180063201`
- `KERNEL32!GetVolumePathNameW` at `0x1800630ef`
- `KERNEL32!GetVolumePathNameW` at `0x1800630ef`

## string_xrefs

- `0x180063090`: `CEcsPath::GetVolumeNameForPathName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CEcsPath::GetVolumeNameForPathName(LPCWSTR lpszFileName, __int64 a2, __int64 a3)
{
  _BYTE *v6; // rax
  char v7; // cl
  __int64 v8; // rdx
  int v9; // edx
  __int64 v10; // rbx
  unsigned __int64 v11; // rdi
  __int64 v12; // rax
  const WCHAR *v13; // rax
  __int64 v14; // rax
  const WCHAR *v15; // rdx
  int pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  int LastFailureAsHRESULT; // [rsp+28h] [rbp-D8h] BYREF
  int v18; // [rsp+2Ch] [rbp-D4h]
  char v19; // [rsp+30h] [rbp-D0h]
  const char *v20; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h]
  _BYTE v22[16]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h]
  WCHAR szVolumePathName[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[524]; // [rsp+74h] [rbp-8Ch] BYREF
  WCHAR szVolumeName[2]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v27[524]; // [rsp+284h] [rbp+184h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_5d95a7213829360425c4708bf03e9463_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (v6[68] & 2) == 0 || (v7 = 1, v6[65] < 6u) )
    v7 = 0;
  LastFailureAsHRESULT = 0;
  v18 = 396;
  v19 = v7;
  v20 = "CEcsPath::GetVolumeNameForPathName";
  v21 = 0;
  std::wstring::_Eos(a2, 0);
  std::wstring::_Eos(a3, v8);
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( lpszFileName[v11] );
  *(_DWORD *)szVolumePathName = 0;
  memset_0(v25, v9, 0x204u);
  if ( !GetVolumePathNameW(lpszFileName, szVolumePathName, 0x104u) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v18) = 408;
    pExceptionObject = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v18) = 408;
  std::wstring::wstring(v22, szVolumePathName);
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  if ( *(_WORD *)(v12 + 2 * v23 - 2) != 92 )
    std::wstring::append(v22, L"\\");
  szVolumePathName[0] = 0;
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  if ( !GetVolumeNameForVolumeMountPointW(v13, szVolumePathName, 0x104u) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v18) = 425;
    pExceptionObject = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v18) = 425;
  *(_DWORD *)szVolumeName = 0;
  memset_0(v27, 0, 0x204u);
  LastFailureAsHRESULT = 0;
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v18) = 430;
    pExceptionObject = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v18) = 430;
  std::wstring::operator=(a2, szVolumeName);
  v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
  do
    ++v10;
  while ( *(_WORD *)(v14 + 2 * v10) );
  if ( v10 - 1 > v11 )
    v15 = &lpszFileName[v11];
  else
    v15 = &lpszFileName[v10 - 1];
  std::wstring::operator=(a3, v15);
  std::wstring::~wstring(v22);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
}

```

## disassembly

```asm
0x180062ffc  push    rbp
0x180062ffe  push    rbx
0x180062fff  push    rsi
0x180063000  push    rdi
0x180063001  push    r12
0x180063003  push    r14
0x180063005  push    r15
0x180063007  lea     rbp, [rsp-3A0h]
0x18006300f  sub     rsp, 4A0h
0x180063016  mov     rax, cs:__security_cookie
0x18006301d  xor     rax, rsp
0x180063020  mov     [rbp+3D0h+var_40], rax
0x180063027  mov     r14, r8
0x18006302a  mov     r15, rdx
0x18006302d  mov     rsi, rcx
0x180063030  lea     rcx, WPP_GLOBAL_Control
0x180063037  mov     rax, cs:WPP_GLOBAL_Control
0x18006303e  cmp     rax, rcx
0x180063041  jz      short loc_18006306B
0x180063043  test    byte ptr [rax+44h], 2
0x180063047  jz      short loc_18006306B
0x180063049  cmp     byte ptr [rax+41h], 6
0x18006304d  jb      short loc_18006306B
0x18006304f  mov     edx, 13h
0x180063054  lea     r8, WPP_5d95a7213829360425c4708bf03e9463_Traceguids
0x18006305b  mov     rcx, [rax+38h]
0x18006305f  call    WPP_SF_
0x180063064  mov     rax, cs:WPP_GLOBAL_Control
0x18006306b  xor     r12d, r12d
0x18006306e  test    byte ptr [rax+44h], 2
0x180063072  jz      short loc_18006307C
0x180063074  cmp     byte ptr [rax+41h], 6
0x180063078  mov     cl, 1
0x18006307a  jnb     short loc_18006307F
0x18006307c  mov     cl, r12b
0x18006307f  mov     [rsp+4D0h+var_4A8], r12d
0x180063084  mov     [rsp+4D0h+var_4A4], 18Ch
0x18006308c  mov     [rsp+4D0h+var_4A0], cl
0x180063090  lea     rax, aCecspathGetvol; "CEcsPath::GetVolumeNameForPathName"
0x180063097  mov     [rsp+4D0h+var_498], rax
0x18006309c  mov     [rsp+4D0h+var_490], r12
0x1800630a1  xor     edx, edx
0x1800630a3  mov     rcx, r15
0x1800630a6  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1800630ab  mov     rcx, r14
0x1800630ae  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1800630b3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800630b7  mov     rdi, rbx
0x1800630ba  inc     rdi
0x1800630bd  cmp     [rsi+rdi*2], r12w
0x1800630c2  jnz     short loc_1800630BA
0x1800630c4  mov     dword ptr [rsp+4D0h+szVolumePathName], r12d
0x1800630c9  mov     r8d, 204h; Size
0x1800630cf  lea     rcx, [rsp+4D0h+var_45C]; void *
0x1800630d4  call    memset_0
0x1800630d9  mov     eax, [rsp+4D0h+var_4A8]
0x1800630dd  mov     [rsp+4D0h+var_4A8], eax
0x1800630e1  mov     r8d, 104h; cchBufferLength
0x1800630e7  lea     rdx, [rsp+4D0h+szVolumePathName]; lpszVolumePathName
0x1800630ec  mov     rcx, rsi; lpszFileName
0x1800630ef  call    cs:__imp_GetVolumePathNameW
0x1800630f5  test    eax, eax
0x1800630f7  jnz     short loc_180063122
0x1800630f9  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800630fe  mov     [rsp+4D0h+var_4A8], eax
0x180063102  mov     ecx, 198h
0x180063107  mov     word ptr [rsp+4D0h+var_4A4+2], cx
0x18006310c  mov     [rsp+4D0h+pExceptionObject], eax
0x180063110  lea     rdx, _TI1J; pThrowInfo
0x180063117  lea     rcx, [rsp+4D0h+pExceptionObject]; pExceptionObject
0x18006311c  call    _CxxThrowException_0
0x180063122  mov     [rsp+4D0h+var_4A8], r12d
0x180063127  mov     ecx, 198h
0x18006312c  mov     word ptr [rsp+4D0h+var_4A4], cx
0x180063131  lea     rdx, [rsp+4D0h+szVolumePathName]
0x180063136  lea     rcx, [rsp+4D0h+var_488]
0x18006313b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180063140  nop
0x180063141  lea     rcx, [rsp+4D0h+var_488]
0x180063146  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006314b  mov     rcx, [rsp+4D0h+var_478]
0x180063150  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180063156  jz      short loc_180063169
0x180063158  lea     rdx, asc_18014CE40; "\\"
0x18006315f  lea     rcx, [rsp+4D0h+var_488]
0x180063164  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180063169  mov     [rsp+4D0h+szVolumePathName], r12w
0x18006316f  mov     eax, [rsp+4D0h+var_4A8]
0x180063173  mov     [rsp+4D0h+var_4A8], eax
0x180063177  lea     rcx, [rsp+4D0h+var_488]
0x18006317c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063181  mov     rcx, rax; lpszVolumeMountPoint
0x180063184  mov     r8d, 104h; cchBufferLength
0x18006318a  lea     rdx, [rsp+4D0h+szVolumePathName]; lpszVolumeName
0x18006318f  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180063195  test    eax, eax
0x180063197  jnz     short loc_1800631C2
0x180063199  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18006319e  mov     [rsp+4D0h+var_4A8], eax
0x1800631a2  mov     ecx, 1A9h
0x1800631a7  mov     word ptr [rsp+4D0h+var_4A4+2], cx
0x1800631ac  mov     [rsp+4D0h+pExceptionObject], eax
0x1800631b0  lea     rdx, _TI1J; pThrowInfo
0x1800631b7  lea     rcx, [rsp+4D0h+pExceptionObject]; pExceptionObject
0x1800631bc  call    _CxxThrowException_0
0x1800631c2  mov     [rsp+4D0h+var_4A8], r12d
0x1800631c7  mov     ecx, 1A9h
0x1800631cc  mov     word ptr [rsp+4D0h+var_4A4], cx
0x1800631d1  mov     dword ptr [rbp+3D0h+szVolumeName], r12d
0x1800631d8  xor     edx, edx; Val
0x1800631da  lea     r8d, [rcx+5Bh]; Size
0x1800631de  lea     rcx, [rbp+3D0h+var_24C]; void *
0x1800631e5  call    memset_0
0x1800631ea  mov     [rsp+4D0h+var_4A8], r12d
0x1800631ef  mov     r8d, 104h; cchBufferLength
0x1800631f5  lea     rdx, [rbp+3D0h+szVolumeName]; lpszVolumeName
0x1800631fc  lea     rcx, [rsp+4D0h+szVolumePathName]; lpszVolumeMountPoint
0x180063201  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180063207  test    eax, eax
0x180063209  jnz     short loc_180063234
0x18006320b  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180063210  mov     [rsp+4D0h+var_4A8], eax
0x180063214  mov     ecx, 1AEh
0x180063219  mov     word ptr [rsp+4D0h+var_4A4+2], cx
0x18006321e  mov     [rsp+4D0h+pExceptionObject], eax
0x180063222  lea     rdx, _TI1J; pThrowInfo
0x180063229  lea     rcx, [rsp+4D0h+pExceptionObject]; pExceptionObject
0x18006322e  call    _CxxThrowException_0
0x180063234  mov     [rsp+4D0h+var_4A8], r12d
0x180063239  mov     ecx, 1AEh
0x18006323e  mov     word ptr [rsp+4D0h+var_4A4], cx
0x180063243  lea     rdx, [rbp+3D0h+szVolumeName]
0x18006324a  mov     rcx, r15
0x18006324d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x180063252  lea     rcx, [rsp+4D0h+var_488]
0x180063257  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006325c  inc     rbx
0x18006325f  cmp     [rax+rbx*2], r12w
0x180063264  jnz     short loc_18006325C
0x180063266  lea     rax, [rbx-1]
0x18006326a  mov     rcx, r14
0x18006326d  cmp     rax, rdi
0x180063270  ja      short loc_18006327C
0x180063272  lea     rdx, [rsi-2]
0x180063276  lea     rdx, [rdx+rbx*2]
0x18006327a  jmp     short loc_180063280
0x18006327c  lea     rdx, [rsi+rdi*2]
0x180063280  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x180063285  nop
0x180063286  lea     rcx, [rsp+4D0h+var_488]
0x18006328b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180063290  nop
0x180063291  lea     rcx, [rsp+4D0h+var_4A8]; this
0x180063296  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x18006329b  mov     rcx, [rbp+3D0h+var_40]
0x1800632a2  xor     rcx, rsp; StackCookie
0x1800632a5  call    __security_check_cookie
0x1800632aa  add     rsp, 4A0h
0x1800632b1  pop     r15
0x1800632b3  pop     r14
0x1800632b5  pop     r12
0x1800632b7  pop     rdi
0x1800632b8  pop     rsi
0x1800632b9  pop     rbx
0x1800632ba  pop     rbp
0x1800632bb  retn
```
