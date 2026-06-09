# SrmIsRemotePath(ushort const *,bool,ushort * *)

- ea: `0x18007dbc0`
- end: `0x18007de6c`
- name: `?SrmIsRemotePath@@YA_NPEBG_NPEAPEAG@Z`
- size: `684`
- prototype: `bool __fastcall(wchar_t *String1, bool, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x180096d3c`

## callees

- `0x180001350`
- `0x18000af40`
- `0x180061be4`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x18007b264`
- `0x18007dbc0`
- `0x180083a68`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18007dcd7`
- `msvcrt!_wcsnicmp` at `0x18007dcf7`
- `msvcrt!_wcsnicmp` at `0x18007dcd7`
- `msvcrt!_wcsnicmp` at `0x18007dcf7`
- `msvcrt!iswalpha` at `0x18007dd22`
- `msvcrt!iswalpha` at `0x18007dd22`
- `ole32!CoTaskMemFree` at `0x18007ddb3`
- `ole32!CoTaskMemFree` at `0x18007ddc6`
- `ole32!CoTaskMemFree` at `0x18007ddb3`
- `ole32!CoTaskMemFree` at `0x18007ddc6`
- `KERNEL32!GetDriveTypeW` at `0x18007dd5d`
- `KERNEL32!GetDriveTypeW` at `0x18007dd5d`

## string_xrefs

- `0x18007dc02`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007de40`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007dc1a`: `SRMPATHC`
- `0x18007de39`: `SRMPATHC`
- `0x18007dc0e`: `SrmIsRemotePath`
- `0x18007de32`: `SrmIsRemotePath`
- `0x18007de52`: `Path should not be only the drive letter specification`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall SrmIsRemotePath(wchar_t *String1, __int64 a2, unsigned __int16 **a3)
{
  char v5; // al
  wchar_t *v6; // rbx
  char v7; // r14
  void **v8; // rdx
  wchar_t *v9; // rdi
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rax
  __int64 v12; // rdx
  unsigned __int16 *v13; // rax
  __int64 v15; // rax
  unsigned __int16 *v16; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v18; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v19[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v20; // [rsp+78h] [rbp-88h]
  _BYTE v21[96]; // [rsp+80h] [rbp-80h] BYREF
  int v22; // [rsp+E0h] [rbp-20h]
  void *Block[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v25; // [rsp+100h] [rbp+0h]
  _QWORD v26[22]; // [rsp+110h] [rbp+10h] BYREF

  v18 = v19;
  v19[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v19[1] = L"SrmIsRemotePath";
  v19[2] = L"SRMPATHC";
  v19[3] = 1294;
  v20 = 255;
  v22 = 0x1000000;
  memset_0(v21, 0, sizeof(v21));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v26, (const struct CSrmDebugInfo *)v19, 0);
  *a3 = 0;
  String2 = 0;
  CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&String2, String1);
  v16 = 0;
  v25 = 7;
  v24 = 0;
  LOWORD(Block[0]) = 0;
  v5 = IsUncPath(String1, Block);
  v6 = String2;
  if ( v5 )
  {
    v7 = 1;
    v8 = Block;
    if ( v25 >= 8 )
      v8 = (void **)Block[0];
    CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v16, (const unsigned __int16 *)v8);
  }
  else
  {
    v7 = 0;
    if ( _wcsnicmp(L"\\\\?\\", String2, 4u) )
    {
      v9 = v6 + 4;
      if ( _wcsnicmp(L"\\\\.\\", v6, 4u) )
        v9 = v6;
    }
    else
    {
      v9 = v6 + 4;
    }
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( v9[v11] );
    if ( v11 >= 2 && iswalpha(*v9) && v9[1] == 58 )
    {
      do
        ++v10;
      while ( v9[v10] );
      if ( v10 <= 2 )
      {
        v18 = v19;
        v15 = CSrmDebugInfo::CSrmDebugInfo(
                (__int64)v19,
                (__int64)L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp",
                (__int64)L"SRMPATHC",
                (__int64)L"SrmIsRemotePath",
                1343,
                17);
        CSrmFunctionTracer::Throw(v26, v15, 2147942487LL, L"Path should not be only the drive letter specification");
      }
      v9[3] = 0;
      CSrmImpersonationSession::CSrmImpersonationSession((CSrmImpersonationSession *)&v18, v12, 0);
      if ( GetDriveTypeW(v9) == 4 )
      {
        v7 = 1;
        CSrmAutoPWSZ::CopyFrom((CSrmAutoPWSZ *)&v16, v6);
      }
      CSrmImpersonationSession::RevertImpersonation((CSrmImpersonationSession *)&v18);
    }
  }
  v13 = v16;
  v16 = 0;
  *a3 = v13;
  if ( v25 >= 8 )
    operator delete(Block[0]);
  v25 = 7;
  v24 = 0;
  LOWORD(Block[0]) = 0;
  CoTaskMemFree(0);
  v16 = 0;
  CoTaskMemFree(v6);
  String2 = 0;
  v26[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v26);
  return v7;
}

```

## disassembly

```asm
0x18007dbc0  mov     [rsp-8+arg_8], rbx
0x18007dbc5  mov     [rsp-8+arg_18], rsi
0x18007dbca  push    rbp
0x18007dbcb  push    rdi
0x18007dbcc  push    r12
0x18007dbce  push    r14
0x18007dbd0  push    r15
0x18007dbd2  lea     rbp, [rsp-0D0h]
0x18007dbda  sub     rsp, 1D0h
0x18007dbe1  mov     rax, cs:__security_cookie
0x18007dbe8  xor     rax, rsp
0x18007dbeb  mov     [rbp+0F0h+var_30], rax
0x18007dbf2  mov     r15, r8
0x18007dbf5  mov     rbx, rcx
0x18007dbf8  lea     rax, [rsp+1F0h+var_198]
0x18007dbfd  mov     [rsp+1F0h+var_1A0], rax
0x18007dc02  lea     rax, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007dc09  mov     [rsp+1F0h+var_198], rax
0x18007dc0e  lea     rax, aSrmisremotepat; "SrmIsRemotePath"
0x18007dc15  mov     [rsp+1F0h+var_190], rax
0x18007dc1a  lea     rax, aSrmpathc; "SRMPATHC"
0x18007dc21  mov     [rsp+1F0h+var_188], rax
0x18007dc26  mov     [rsp+1F0h+var_180], 50Eh
0x18007dc2f  xor     r12d, r12d
0x18007dc32  mov     [rsp+1F0h+var_178], 0FFh
0x18007dc3a  mov     [rbp+0F0h+var_110], 1000000h
0x18007dc41  xor     edx, edx; Val
0x18007dc43  lea     r8d, [r12+60h]; Size
0x18007dc48  lea     rcx, [rbp+0F0h+var_170]; void *
0x18007dc4c  call    memset_0
0x18007dc51  nop
0x18007dc52  xor     r8d, r8d
0x18007dc55  lea     rdx, [rsp+1F0h+var_198]
0x18007dc5a  lea     rcx, [rbp+0F0h+var_E0]
0x18007dc5e  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007dc63  nop
0x18007dc64  mov     [r15], r12
0x18007dc67  mov     [rsp+1F0h+String2], r12
0x18007dc6c  mov     rdx, rbx; unsigned __int16 *
0x18007dc6f  lea     rcx, [rsp+1F0h+String2]; this
0x18007dc74  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007dc79  mov     [rsp+1F0h+var_1B0], r12
0x18007dc7e  mov     [rbp+0F0h+var_F0], 7
0x18007dc86  mov     [rbp+0F0h+var_F8], r12
0x18007dc8a  mov     word ptr [rbp+0F0h+Block], r12w
0x18007dc8f  lea     rdx, [rbp+0F0h+Block]; Src
0x18007dc93  mov     rcx, rbx; String1
0x18007dc96  call    ?IsUncPath@@YA_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsUncPath(ushort const *,std::wstring &)
0x18007dc9b  mov     rbx, [rsp+1F0h+String2]
0x18007dca0  test    al, al
0x18007dca2  jz      short loc_18007DCC4
0x18007dca4  mov     r14b, 1
0x18007dca7  lea     rdx, [rbp+0F0h+Block]
0x18007dcab  cmp     [rbp+0F0h+var_F0], 8
0x18007dcb0  cmovnb  rdx, [rbp+0F0h+Block]; unsigned __int16 *
0x18007dcb5  lea     rcx, [rsp+1F0h+var_1B0]; this
0x18007dcba  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007dcbf  jmp     loc_18007DD83
0x18007dcc4  mov     r14b, r12b
0x18007dcc7  mov     r8d, 4; MaxCount
0x18007dccd  mov     rdx, rbx; String2
0x18007dcd0  lea     rcx, asc_1800EFAE0; "\\\\?\\"
0x18007dcd7  call    cs:__imp__wcsnicmp
0x18007dcdd  test    eax, eax
0x18007dcdf  jnz     short loc_18007DCE7
0x18007dce1  lea     rdi, [rbx+8]
0x18007dce5  jmp     short loc_18007DD08
0x18007dce7  mov     r8d, 4; MaxCount
0x18007dced  mov     rdx, rbx; String2
0x18007dcf0  lea     rcx, asc_1800EFB08; "\\\\.\\"
0x18007dcf7  call    cs:__imp__wcsnicmp
0x18007dcfd  test    eax, eax
0x18007dcff  lea     rdi, [rbx+8]
0x18007dd03  jz      short loc_18007DD08
0x18007dd05  mov     rdi, rbx
0x18007dd08  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18007dd0c  mov     rax, rsi
0x18007dd0f  inc     rax
0x18007dd12  cmp     [rdi+rax*2], r12w
0x18007dd17  jnz     short loc_18007DD0F
0x18007dd19  cmp     rax, 2
0x18007dd1d  jb      short loc_18007DD83
0x18007dd1f  movzx   ecx, word ptr [rdi]; C
0x18007dd22  call    cs:__imp_iswalpha
0x18007dd28  test    eax, eax
0x18007dd2a  jz      short loc_18007DD83
0x18007dd2c  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18007dd31  jnz     short loc_18007DD83
0x18007dd33  inc     rsi
0x18007dd36  cmp     [rdi+rsi*2], r12w
0x18007dd3b  jnz     short loc_18007DD33
0x18007dd3d  cmp     rsi, 2
0x18007dd41  jbe     loc_18007DE18
0x18007dd47  mov     [rdi+6], r12w
0x18007dd4c  xor     r8d, r8d; bool
0x18007dd4f  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18007dd54  call    ??0CSrmImpersonationSession@@QEAA@_N0@Z; CSrmImpersonationSession::CSrmImpersonationSession(bool,bool)
0x18007dd59  nop
0x18007dd5a  mov     rcx, rdi; lpRootPathName
0x18007dd5d  call    cs:__imp_GetDriveTypeW
0x18007dd63  cmp     eax, 4
0x18007dd66  jnz     short loc_18007DD79
0x18007dd68  mov     r14b, 1
0x18007dd6b  mov     rdx, rbx; unsigned __int16 *
0x18007dd6e  lea     rcx, [rsp+1F0h+var_1B0]; this
0x18007dd73  call    ?CopyFrom@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::CopyFrom(ushort const *)
0x18007dd78  nop
0x18007dd79  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18007dd7e  call    ?RevertImpersonation@CSrmImpersonationSession@@QEAAJXZ; CSrmImpersonationSession::RevertImpersonation(void)
0x18007dd83  mov     rax, [rsp+1F0h+var_1B0]
0x18007dd88  mov     [rsp+1F0h+var_1B0], r12
0x18007dd8d  mov     [r15], rax
0x18007dd90  cmp     [rbp+0F0h+var_F0], 8
0x18007dd95  jb      short loc_18007DDA0
0x18007dd97  mov     rcx, [rbp+0F0h+Block]; Block
0x18007dd9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007dda0  mov     [rbp+0F0h+var_F0], 7
0x18007dda8  mov     [rbp+0F0h+var_F8], r12
0x18007ddac  mov     word ptr [rbp+0F0h+Block], r12w
0x18007ddb1  xor     ecx, ecx; pv
0x18007ddb3  call    cs:__imp_CoTaskMemFree
0x18007ddb9  mov     [rsp+1F0h+var_1B0], r12
0x18007ddbe  mov     [rsp+1F0h+var_1B0], r12
0x18007ddc3  mov     rcx, rbx; pv
0x18007ddc6  call    cs:__imp_CoTaskMemFree
0x18007ddcc  mov     [rsp+1F0h+String2], r12
0x18007ddd1  mov     [rsp+1F0h+String2], r12
0x18007ddd6  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007dddd  mov     [rbp+0F0h+var_E0], rax
0x18007dde1  lea     rcx, [rbp+0F0h+var_E0]; this
0x18007dde5  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007ddea  mov     al, r14b
0x18007dded  mov     rcx, [rbp+0F0h+var_30]
0x18007ddf4  xor     rcx, rsp; StackCookie
0x18007ddf7  call    __security_check_cookie
0x18007ddfc  lea     r11, [rsp+1F0h+var_20]
0x18007de04  mov     rbx, [r11+38h]
0x18007de08  mov     rsi, [r11+48h]
0x18007de0c  mov     rsp, r11
0x18007de0f  pop     r15
0x18007de11  pop     r14
0x18007de13  pop     r12
0x18007de15  pop     rdi
0x18007de16  pop     rbp
0x18007de17  retn
0x18007de18  lea     rax, [rsp+1F0h+var_198]
0x18007de1d  mov     [rsp+1F0h+var_1A0], rax
0x18007de22  mov     [rsp+1F0h+var_1C8], 11h
0x18007de2a  mov     [rsp+1F0h+var_1D0], 53Fh
0x18007de32  lea     r9, aSrmisremotepat; "SrmIsRemotePath"
0x18007de39  lea     r8, aSrmpathc; "SRMPATHC"
0x18007de40  lea     rdx, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007de47  lea     rcx, [rsp+1F0h+var_198]
0x18007de4c  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007de51  nop
0x18007de52  lea     r9, aPathShouldNotB; "Path should not be only the drive lette"...
0x18007de59  mov     r8d, 80070057h
0x18007de5f  mov     rdx, rax
0x18007de62  lea     rcx, [rbp+0F0h+var_E0]
0x18007de66  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
