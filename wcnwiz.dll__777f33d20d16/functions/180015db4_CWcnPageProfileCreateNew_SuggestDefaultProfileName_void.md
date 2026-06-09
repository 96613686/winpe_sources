# CWcnPageProfileCreateNew::SuggestDefaultProfileName(void)

- ea: `0x180015db4`
- end: `0x180016002`
- name: `?SuggestDefaultProfileName@CWcnPageProfileCreateNew@@QEAAJXZ`
- size: `590`
- prototype: `__int64 __fastcall(CWcnPageProfileCreateNew *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180014880`

## callees

- `0x180001820`
- `0x180002a58`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x180010758`
- `0x180015db4`
- `0x18001f154`
- `0x18002b8dc`
- `0x18002c648`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e57`
- `KERNEL32!GetComputerNameW` at `0x180015e4d`
- `KERNEL32!GetComputerNameW` at `0x180015e4d`
- `KERNEL32!lstrcmpW` at `0x180015f00`
- `KERNEL32!lstrcmpW` at `0x180015f00`
- `USER32!SetWindowTextW` at `0x180015f3c`
- `USER32!SetWindowTextW` at `0x180015f3c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWcnPageProfileCreateNew::SuggestDefaultProfileName(CWcnPageProfileCreateNew *this)
{
  const char *Indent; // rax
  __int64 v3; // r10
  signed int LastError; // eax
  signed int v5; // ebx
  _BYTE *v6; // r10
  const char *v7; // rax
  __int64 v8; // r10
  __int64 v9; // rdx
  int v10; // esi
  int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // r15
  BOOL v14; // eax
  unsigned int v15; // eax
  __int64 v16; // r10
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[16]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h]
  wchar_t v22[16]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[16]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR String2[40]; // [rsp+A0h] [rbp-60h] BYREF

  memset(v22, 0, sizeof(v22));
  nSize = 16;
  CWcnNetworkProfileLoaderElevated::CWcnNetworkProfileLoaderElevated((CWcnNetworkProfileLoaderElevated *)v19);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v3 + 16), 32, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, Indent);
  }
  if ( GetComputerNameW(Buffer, &nSize) )
  {
    v10 = 0;
    CWcnNetworkProfileLoader::LoadWcnCompatibileProfiles((CWcnNetworkProfileLoader *)v19, 0xFFFFu, 0);
LABEL_12:
    v11 = WcnUxFormatString(0x1116u, 0x21u, String2, Buffer, v22);
    v5 = v11;
    if ( v11 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_30;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_26;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids,
        (unsigned int)v11);
      goto LABEL_25;
    }
    v12 = v20;
    v13 = v21;
    while ( v12 != v13 )
    {
      if ( !lstrcmpW((LPCWSTR)(*(_QWORD *)v12 + 88LL), String2) )
      {
        swprintf_s(v22, 0x10u, L"_%u", (unsigned int)++v10);
        goto LABEL_12;
      }
      v12 += 8;
    }
    *((_BYTE *)this + 666) = 1;
    v14 = SetWindowTextW(*((HWND *)this + 37), String2);
    *((_BYTE *)this + 666) = 0;
    if ( v14 )
    {
LABEL_25:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_26;
    }
    v5 = -2147467259;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_30;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_26;
    v7 = GetIndent(0);
    v9 = 35;
LABEL_10:
    WPP_SF_s(*(_QWORD *)(v8 + 16), v9, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, v7);
    goto LABEL_25;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_26:
      if ( v6 != (_BYTE *)&WPP_GLOBAL_Control && (v5 < 0 || v6[25] >= 6u) )
      {
        v15 = (unsigned int)GetIndent(-1);
        WPP_SF_sd(*(_QWORD *)(v16 + 16), 36, (unsigned int)WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, v15, v5);
      }
      goto LABEL_30;
    }
    v7 = GetIndent(0);
    v9 = 33;
    goto LABEL_10;
  }
LABEL_30:
  CWcnNetworkProfileLoader::~CWcnNetworkProfileLoader((CWcnNetworkProfileLoader *)v19);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180015db4  push    rbp
0x180015db6  push    rbx
0x180015db7  push    rsi
0x180015db8  push    rdi
0x180015db9  push    r12
0x180015dbb  push    r13
0x180015dbd  push    r14
0x180015dbf  push    r15
0x180015dc1  lea     rbp, [rsp-8]
0x180015dc6  sub     rsp, 108h
0x180015dcd  mov     rax, cs:__security_cookie
0x180015dd4  xor     rax, rsp
0x180015dd7  mov     [rbp+40h+var_50], rax
0x180015ddb  mov     r14, rcx
0x180015dde  xor     eax, eax
0x180015de0  mov     [rsp+140h+var_E0], ax
0x180015de5  xorps   xmm0, xmm0
0x180015de8  movups  xmmword ptr [rsp+140h+var_DE], xmm0
0x180015ded  movups  xmmword ptr [rsp+140h+var_DE+0Eh], xmm0
0x180015df2  mov     [rsp+140h+nSize], 10h
0x180015dfa  lea     rcx, [rsp+140h+var_108]; this
0x180015dff  call    ??0CWcnNetworkProfileLoaderElevated@@QEAA@XZ; CWcnNetworkProfileLoaderElevated::CWcnNetworkProfileLoaderElevated(void)
0x180015e04  nop
0x180015e05  lea     r12, WPP_GLOBAL_Control
0x180015e0c  lea     r13, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180015e13  mov     r10, cs:WPP_GLOBAL_Control
0x180015e1a  cmp     r10, r12
0x180015e1d  jz      short loc_180015E44
0x180015e1f  cmp     byte ptr [r10+19h], 6
0x180015e24  jb      short loc_180015E44
0x180015e26  mov     ecx, 1; int
0x180015e2b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015e30  mov     edx, 20h ; ' '
0x180015e35  mov     r9, rax
0x180015e38  mov     r8, r13
0x180015e3b  mov     rcx, [r10+10h]
0x180015e3f  call    WPP_SF_s
0x180015e44  lea     rdx, [rsp+140h+nSize]; nSize
0x180015e49  lea     rcx, [rbp+40h+Buffer]; lpBuffer
0x180015e4d  call    cs:__imp_GetComputerNameW
0x180015e53  test    eax, eax
0x180015e55  jnz     short loc_180015EA7
0x180015e57  call    cs:__imp_GetLastError
0x180015e5d  mov     ebx, eax
0x180015e5f  test    eax, eax
0x180015e61  jle     short loc_180015E6C
0x180015e63  movzx   ebx, ax
0x180015e66  or      ebx, 80070000h
0x180015e6c  mov     r10, cs:WPP_GLOBAL_Control
0x180015e73  cmp     r10, r12
0x180015e76  jz      loc_180015FD6
0x180015e7c  cmp     byte ptr [r10+19h], 2
0x180015e81  jb      loc_180015FA5
0x180015e87  xor     ecx, ecx; int
0x180015e89  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015e8e  mov     edx, 21h ; '!'
0x180015e93  mov     r9, rax
0x180015e96  mov     r8, r13
0x180015e99  mov     rcx, [r10+10h]
0x180015e9d  call    WPP_SF_s
0x180015ea2  jmp     loc_180015F9E
0x180015ea7  xor     esi, esi
0x180015ea9  xor     r8d, r8d; struct IWcnElevationHelper *
0x180015eac  mov     edx, 0FFFFh; unsigned int
0x180015eb1  lea     rcx, [rsp+140h+var_108]; this
0x180015eb6  call    ?LoadWcnCompatibileProfiles@CWcnNetworkProfileLoader@@QEAAXKPEAUIWcnElevationHelper@@@Z; CWcnNetworkProfileLoader::LoadWcnCompatibileProfiles(ulong,IWcnElevationHelper *)
0x180015ebb  lea     rax, [rsp+140h+var_E0]
0x180015ec0  mov     [rsp+140h+var_120], rax
0x180015ec5  lea     r9, [rbp+40h+Buffer]
0x180015ec9  lea     r8, [rbp+40h+String2]; unsigned __int16 *
0x180015ecd  mov     edx, 21h ; '!'; nSize
0x180015ed2  mov     ecx, 1116h; dwMessageId
0x180015ed7  call    ?WcnUxFormatString@@YAJIKPEAGZZ; WcnUxFormatString(uint,ulong,ushort *,...)
0x180015edc  mov     ebx, eax
0x180015ede  test    eax, eax
0x180015ee0  js      loc_180015F77
0x180015ee6  mov     rdi, [rsp+140h+var_F8]
0x180015eeb  mov     r15, [rsp+140h+var_F0]
0x180015ef0  lea     rdx, [rbp+40h+String2]; lpString
0x180015ef4  cmp     rdi, r15
0x180015ef7  jz      short loc_180015F2D
0x180015ef9  mov     rcx, [rdi]
0x180015efc  add     rcx, 58h ; 'X'; lpString1
0x180015f00  call    cs:__imp_lstrcmpW
0x180015f06  test    eax, eax
0x180015f08  jz      short loc_180015F10
0x180015f0a  add     rdi, 8
0x180015f0e  jmp     short loc_180015EF0
0x180015f10  inc     esi
0x180015f12  mov     r9d, esi
0x180015f15  lea     r8, aU; "_%u"
0x180015f1c  mov     edx, 10h; BufferCount
0x180015f21  lea     rcx, [rsp+140h+var_E0]; Buffer
0x180015f26  call    swprintf_s
0x180015f2b  jmp     short loc_180015EBB
0x180015f2d  mov     byte ptr [r14+29Ah], 1
0x180015f35  mov     rcx, [r14+128h]; hWnd
0x180015f3c  call    cs:__imp_SetWindowTextW
0x180015f42  mov     byte ptr [r14+29Ah], 0
0x180015f4a  test    eax, eax
0x180015f4c  jnz     short loc_180015F9E
0x180015f4e  mov     ebx, 80004005h
0x180015f53  mov     r10, cs:WPP_GLOBAL_Control
0x180015f5a  cmp     r10, r12
0x180015f5d  jz      short loc_180015FD6
0x180015f5f  cmp     byte ptr [r10+19h], 2
0x180015f64  jb      short loc_180015FA5
0x180015f66  xor     ecx, ecx; int
0x180015f68  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015f6d  mov     edx, 23h ; '#'
0x180015f72  jmp     loc_180015E93
0x180015f77  mov     r10, cs:WPP_GLOBAL_Control
0x180015f7e  cmp     r10, r12
0x180015f81  jz      short loc_180015FD6
0x180015f83  cmp     byte ptr [r10+19h], 2
0x180015f88  jb      short loc_180015FA5
0x180015f8a  mov     edx, 22h ; '"'
0x180015f8f  mov     r9d, eax
0x180015f92  mov     r8, r13
0x180015f95  mov     rcx, [r10+10h]
0x180015f99  call    WPP_SF_d
0x180015f9e  mov     r10, cs:WPP_GLOBAL_Control
0x180015fa5  cmp     r10, r12
0x180015fa8  jz      short loc_180015FD6
0x180015faa  test    ebx, ebx
0x180015fac  js      short loc_180015FB5
0x180015fae  cmp     byte ptr [r10+19h], 6
0x180015fb3  jb      short loc_180015FD6
0x180015fb5  or      ecx, 0FFFFFFFFh; int
0x180015fb8  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180015fbd  mov     edx, 24h ; '$'
0x180015fc2  mov     dword ptr [rsp+140h+var_120], ebx
0x180015fc6  mov     r9, rax
0x180015fc9  mov     r8, r13
0x180015fcc  mov     rcx, [r10+10h]
0x180015fd0  call    WPP_SF_sd
0x180015fd5  nop
0x180015fd6  lea     rcx, [rsp+140h+var_108]; this
0x180015fdb  call    ??1CWcnNetworkProfileLoader@@UEAA@XZ; CWcnNetworkProfileLoader::~CWcnNetworkProfileLoader(void)
0x180015fe0  mov     eax, ebx
0x180015fe2  mov     rcx, [rbp+40h+var_50]
0x180015fe6  xor     rcx, rsp; StackCookie
0x180015fe9  call    __security_check_cookie
0x180015fee  add     rsp, 108h
0x180015ff5  pop     r15
0x180015ff7  pop     r14
0x180015ff9  pop     r13
0x180015ffb  pop     r12
0x180015ffd  pop     rdi
0x180015ffe  pop     rsi
0x180015fff  pop     rbx
0x180016000  pop     rbp
0x180016001  retn
```
