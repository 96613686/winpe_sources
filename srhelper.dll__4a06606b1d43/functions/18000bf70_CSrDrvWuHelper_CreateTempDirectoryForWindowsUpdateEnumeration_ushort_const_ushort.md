# CSrDrvWuHelper::_CreateTempDirectoryForWindowsUpdateEnumeration(ushort const *,ushort * *)

- ea: `0x18000bf70`
- end: `0x18000c0f5`
- name: `?_CreateTempDirectoryForWindowsUpdateEnumeration@CSrDrvWuHelper@@CAJPEBGPEAPEAG@Z`
- size: `389`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, __int64, unsigned __int16)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000a790`
- `0x18000af70`

## callees

- `0x180003ce0`
- `0x18000bf70`
- `0x18000d348`
- `0x18000d43c`
- `0x18000e3b8`
- `0x18000e554`
- `0x180015390`
- `0x180015590`
- `0x180015760`

## string_xrefs

- `0x18000bfc0`: `CSrDrvWuHelper::_CreateTempDirectoryForWindowsUpdateEnumeration`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::_CreateTempDirectoryForWindowsUpdateEnumeration(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        __int64 a3,
        unsigned __int16 a4)
{
  const unsigned __int16 *v6; // r9
  __int16 v7; // ax
  int DirectoryUnderSVI; // ebx
  const unsigned __int16 *v9; // r9
  unsigned __int16 *v10; // rdx
  struct _TOKEN_PRIVILEGES *v11; // r8
  unsigned __int16 v12; // r9
  struct _SECURITY_ATTRIBUTES *v13; // rdx
  __int64 *v14; // rdi
  unsigned __int16 *v15; // rcx
  const unsigned __int16 *v17; // [rsp+20h] [rbp-59h]
  const unsigned __int16 *v18; // [rsp+20h] [rbp-59h]
  const unsigned __int16 *v19; // [rsp+28h] [rbp-51h]
  const unsigned __int16 *v20; // [rsp+28h] [rbp-51h]
  const unsigned __int16 *v21; // [rsp+30h] [rbp-49h]
  const unsigned __int16 *v22; // [rsp+30h] [rbp-49h]
  const unsigned __int16 *v23; // [rsp+38h] [rbp-41h]
  const unsigned __int16 *v24; // [rsp+38h] [rbp-41h]
  const unsigned __int16 *v25; // [rsp+40h] [rbp-39h]
  const unsigned __int16 *v26; // [rsp+40h] [rbp-39h]
  const unsigned __int16 *v27; // [rsp+48h] [rbp-31h]
  const unsigned __int16 *v28; // [rsp+48h] [rbp-31h]
  const unsigned __int16 *v29; // [rsp+50h] [rbp-29h]
  const unsigned __int16 *v30; // [rsp+50h] [rbp-29h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp-19h] BYREF
  __int64 v32; // [rsp+68h] [rbp-11h]
  int v33; // [rsp+70h] [rbp-9h] BYREF
  __int16 v34; // [rsp+74h] [rbp-5h]
  __int16 v35; // [rsp+76h] [rbp-3h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v33,
    "CSrDrvWuHelper::_CreateTempDirectoryForWindowsUpdateEnumeration",
    0x1CFu,
    a4);
  v32 = 0;
  lpFileName = (LPCWSTR)qword_18001A620;
  v7 = 465;
  if ( !a1 || (v34 = 465, v7 = 466, !a2) )
  {
    DirectoryUnderSVI = -2147024809;
    v33 = -2147024809;
LABEL_6:
    v35 = v7;
    goto LABEL_18;
  }
  v33 = 0;
  v34 = 466;
  *a2 = 0;
  DirectoryUnderSVI = CBsString::SetPath((CBsString *)&lpFileName, a1, 0, v6, v17, v19, v21, v23, v25, v27, v29);
  v33 = DirectoryUnderSVI;
  v7 = 470;
  if ( DirectoryUnderSVI < 0 )
    goto LABEL_6;
  v34 = 470;
  if ( !(_DWORD)v32 )
  {
    DirectoryUnderSVI = -2147020579;
    v33 = -2147020579;
LABEL_12:
    v7 = 471;
    goto LABEL_6;
  }
  v33 = CBsString::_CombinePathImpl(
          (CBsString *)&lpFileName,
          L"System Volume Information\\SPP\\SppCbsHiveStore",
          0,
          v9,
          v18,
          v20,
          v22,
          v24,
          v26,
          v28,
          v30);
  DirectoryUnderSVI = v33;
  if ( v33 < 0 )
    goto LABEL_12;
  v34 = 471;
  DirectoryUnderSVI = SxCreateDirectoryUnderSVI(a1, v10, v11, v12);
  v33 = DirectoryUnderSVI;
  v7 = 475;
  if ( DirectoryUnderSVI < 0 )
    goto LABEL_6;
  v14 = (__int64 *)lpFileName;
  v34 = 475;
  DirectoryUnderSVI = SxCreateDirectory(lpFileName, v13);
  v33 = DirectoryUnderSVI;
  v7 = 478;
  if ( DirectoryUnderSVI < 0 )
    goto LABEL_6;
  v15 = 0;
  v34 = 478;
  lpFileName = (LPCWSTR)qword_18001A620;
  v32 = 0;
  if ( v14 != qword_18001A620 )
    v15 = (unsigned __int16 *)v14;
  *a2 = v15;
LABEL_18:
  CBsString::_Release((CBsString *)&lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v33);
  return (unsigned int)DirectoryUnderSVI;
}

```

## disassembly

```asm
0x18000bf70  push    rbp
0x18000bf72  push    rbx
0x18000bf73  push    rsi
0x18000bf74  push    rdi
0x18000bf75  push    r15
0x18000bf77  lea     rbp, [rsp-37h]
0x18000bf7c  sub     rsp, 0B0h
0x18000bf83  mov     rsi, rdx
0x18000bf86  mov     rdi, rcx
0x18000bf89  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf90  lea     rax, WPP_GLOBAL_Control
0x18000bf97  cmp     rcx, rax
0x18000bf9a  jz      short loc_18000BFBA
0x18000bf9c  test    dword ptr [rcx+1Ch], 20000000h
0x18000bfa3  jz      short loc_18000BFBA
0x18000bfa5  mov     rcx, [rcx+10h]
0x18000bfa9  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000bfb0  mov     edx, 15h
0x18000bfb5  call    WPP_SF_
0x18000bfba  mov     r8d, 1CFh; unsigned __int16
0x18000bfc0  lea     rdx, aCsrdrvwuhelper_4; "CSrDrvWuHelper::_CreateTempDirectoryFor"...
0x18000bfc7  lea     rcx, [rbp+57h+var_60]; this
0x18000bfcb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000bfd0  mov     [rbp+57h+var_68], 0
0x18000bfd8  lea     r15, qword_18001A620
0x18000bfdf  mov     [rbp+57h+lpFileName], r15
0x18000bfe3  mov     eax, 1D1h
0x18000bfe8  test    rdi, rdi
0x18000bfeb  jnz     short loc_18000BFFE
0x18000bfed  mov     ebx, 80070057h
0x18000bff2  mov     [rbp+57h+var_60], ebx
0x18000bff5  mov     [rbp+57h+var_5A], ax
0x18000bff9  jmp     loc_18000C0D3
0x18000bffe  mov     [rbp+57h+var_5C], ax
0x18000c002  mov     eax, 1D2h
0x18000c007  test    rsi, rsi
0x18000c00a  jz      short loc_18000BFED
0x18000c00c  xor     r8d, r8d; unsigned __int16 *
0x18000c00f  mov     [rbp+57h+var_60], 0
0x18000c016  mov     rdx, rdi; unsigned __int16 *
0x18000c019  mov     [rbp+57h+var_5C], ax
0x18000c01d  lea     rcx, [rbp+57h+lpFileName]; this
0x18000c021  mov     qword ptr [rsi], 0
0x18000c028  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000c02d  mov     ebx, eax
0x18000c02f  mov     [rbp+57h+var_60], eax
0x18000c032  test    eax, eax
0x18000c034  mov     eax, 1D6h
0x18000c039  js      short loc_18000BFF5
0x18000c03b  cmp     dword ptr [rbp+57h+var_68], 0
0x18000c03f  mov     [rbp+57h+var_5C], ax
0x18000c043  jnz     short loc_18000C04F
0x18000c045  mov     ebx, 800710DDh
0x18000c04a  mov     [rbp+57h+var_60], ebx
0x18000c04d  jmp     short loc_18000C06B
0x18000c04f  xor     r8d, r8d; unsigned __int16 *
0x18000c052  lea     rdx, aSystemVolumeIn_1; "System Volume Information\\SPP\\SppCbsH"...
0x18000c059  lea     rcx, [rbp+57h+lpFileName]; this
0x18000c05d  call    ?_CombinePathImpl@CBsString@@AEAAJPEBG000000000@Z; CBsString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000c062  mov     [rbp+57h+var_60], eax
0x18000c065  mov     ebx, eax
0x18000c067  test    eax, eax
0x18000c069  jns     short loc_18000C072
0x18000c06b  mov     eax, 1D7h
0x18000c070  jmp     short loc_18000BFF5
0x18000c072  mov     eax, 1D7h
0x18000c077  mov     rcx, rdi; unsigned __int16 *
0x18000c07a  mov     [rbp+57h+var_5C], ax
0x18000c07e  call    ?SxCreateDirectoryUnderSVI@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@@Z; SxCreateDirectoryUnderSVI(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *)
0x18000c083  mov     ebx, eax
0x18000c085  mov     [rbp+57h+var_60], eax
0x18000c088  test    eax, eax
0x18000c08a  mov     eax, 1DBh
0x18000c08f  js      loc_18000BFF5
0x18000c095  mov     rdi, [rbp+57h+lpFileName]
0x18000c099  mov     rcx, rdi; lpFileName
0x18000c09c  mov     [rbp+57h+var_5C], ax
0x18000c0a0  call    ?SxCreateDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; SxCreateDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18000c0a5  mov     ebx, eax
0x18000c0a7  mov     [rbp+57h+var_60], eax
0x18000c0aa  test    eax, eax
0x18000c0ac  mov     eax, 1DEh
0x18000c0b1  js      loc_18000BFF5
0x18000c0b7  xor     ecx, ecx
0x18000c0b9  mov     [rbp+57h+var_5C], ax
0x18000c0bd  cmp     rdi, r15
0x18000c0c0  mov     [rbp+57h+lpFileName], r15
0x18000c0c4  mov     [rbp+57h+var_68], 0
0x18000c0cc  cmovnz  rcx, rdi
0x18000c0d0  mov     [rsi], rcx
0x18000c0d3  lea     rcx, [rbp+57h+lpFileName]; this
0x18000c0d7  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000c0dc  lea     rcx, [rbp+57h+var_60]; this
0x18000c0e0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000c0e5  mov     eax, ebx
0x18000c0e7  add     rsp, 0B0h
0x18000c0ee  pop     r15
0x18000c0f0  pop     rdi
0x18000c0f1  pop     rsi
0x18000c0f2  pop     rbx
0x18000c0f3  pop     rbp
0x18000c0f4  retn
```
