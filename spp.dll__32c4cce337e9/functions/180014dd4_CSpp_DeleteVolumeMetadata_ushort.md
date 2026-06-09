# CSpp::_DeleteVolumeMetadata(ushort *)

- ea: `0x180014dd4`
- end: `0x180014ee9`
- name: `?_DeleteVolumeMetadata@CSpp@@AEAAJPEAG@Z`
- size: `277`
- prototype: `__int64 __fastcall(CSpp *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180014d00`

## callees

- `0x180014dd4`
- `0x180020908`
- `0x1800268b4`
- `0x1800269ac`
- `0x1800352cc`
- `0x180035b00`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180014e83`
- `KERNEL32!DeleteFileW` at `0x180014eb7`
- `KERNEL32!DeleteFileW` at `0x180014e83`
- `KERNEL32!DeleteFileW` at `0x180014eb7`

## string_xrefs

- `0x180014e26`: `CSpp::_DeleteVolumeMetadata`

## pseudocode

```c
__int64 __fastcall CSpp::_DeleteVolumeMetadata(CSpp *this, unsigned __int16 *a2)
{
  const unsigned __int16 *v3; // r8
  const unsigned __int16 *v4; // r9
  int v5; // ebx
  __int16 v6; // ax
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r8
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-50h] BYREF
  int v13; // [rsp+40h] [rbp-40h] BYREF
  __int16 v14; // [rsp+44h] [rbp-3Ch]
  __int16 v15; // [rsp+46h] [rbp-3Ah]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, a2);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "CSpp::_DeleteVolumeMetadata", 5472, 1);
  lpFileName[1] = 0;
  lpFileName[0] = &FileName;
  v5 = CBsString::Set((CBsString *)lpFileName, a2, v3, v4, L"snapshot-2");
  v13 = v5;
  v6 = 5484;
  if ( v5 < 0
    || (v14 = 5484,
        DeleteFileW(lpFileName[0]),
        v5 = CBsString::Set((CBsString *)lpFileName, a2, v7, v8, L"metadata-2"),
        v13 = v5,
        v6 = 5494,
        v5 < 0) )
  {
    v15 = v6;
  }
  else
  {
    v14 = 5494;
    DeleteFileW(lpFileName[0]);
    v5 = v13;
  }
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13, v9, v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014dd4  mov     [rsp-8+arg_0], rbx
0x180014dd9  mov     [rsp-8+arg_8], rdi
0x180014dde  push    rbp
0x180014ddf  mov     rbp, rsp
0x180014de2  sub     rsp, 80h
0x180014de9  mov     rdi, rdx
0x180014dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180014df3  lea     rax, WPP_GLOBAL_Control
0x180014dfa  cmp     rcx, rax
0x180014dfd  jz      short loc_180014E20
0x180014dff  test    dword ptr [rcx+1Ch], 20000000h
0x180014e06  jz      short loc_180014E20
0x180014e08  mov     rcx, [rcx+10h]
0x180014e0c  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180014e13  mov     edx, 5Bh ; '['
0x180014e18  mov     r9, rdi
0x180014e1b  call    WPP_SF_S
0x180014e20  mov     r9d, 1; unsigned __int16
0x180014e26  lea     rdx, aCsppDeletevolu; "CSpp::_DeleteVolumeMetadata"
0x180014e2d  mov     r8d, 1560h; unsigned __int16
0x180014e33  lea     rcx, [rbp+var_40]; this
0x180014e37  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180014e3c  lea     rax, FileName
0x180014e43  mov     [rbp+var_48], 0
0x180014e4b  mov     [rbp+lpFileName], rax
0x180014e4f  lea     rcx, [rbp+lpFileName]; this
0x180014e53  lea     rax, aSnapshot2; "snapshot-2"
0x180014e5a  mov     rdx, rdi; unsigned __int16 *
0x180014e5d  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x180014e62  call    ?Set@CBsString@@QEAAJPEBG000@Z; CBsString::Set(ushort const *,ushort const *,ushort const *,ushort const *)
0x180014e67  mov     ebx, eax
0x180014e69  mov     [rbp+var_40], eax
0x180014e6c  test    eax, eax
0x180014e6e  mov     eax, 156Ch
0x180014e73  jns     short loc_180014E7B
0x180014e75  mov     [rbp+var_3A], ax
0x180014e79  jmp     short loc_180014EC0
0x180014e7b  mov     rcx, [rbp+lpFileName]; lpFileName
0x180014e7f  mov     [rbp+var_3C], ax
0x180014e83  call    cs:__imp_DeleteFileW
0x180014e89  lea     rax, aMetadata2; "metadata-2"
0x180014e90  mov     rdx, rdi; unsigned __int16 *
0x180014e93  lea     rcx, [rbp+lpFileName]; this
0x180014e97  mov     [rsp+80h+var_60], rax; unsigned __int16 *
0x180014e9c  call    ?Set@CBsString@@QEAAJPEBG000@Z; CBsString::Set(ushort const *,ushort const *,ushort const *,ushort const *)
0x180014ea1  mov     ebx, eax
0x180014ea3  mov     [rbp+var_40], eax
0x180014ea6  test    eax, eax
0x180014ea8  mov     eax, 1576h
0x180014ead  js      short loc_180014E75
0x180014eaf  mov     rcx, [rbp+lpFileName]; lpFileName
0x180014eb3  mov     [rbp+var_3C], ax
0x180014eb7  call    cs:__imp_DeleteFileW
0x180014ebd  mov     ebx, [rbp+var_40]
0x180014ec0  lea     rcx, [rbp+lpFileName]; this
0x180014ec4  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180014ec9  lea     rcx, [rbp+var_40]; this
0x180014ecd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180014ed2  lea     r11, [rsp+80h+var_s0]
0x180014eda  mov     eax, ebx
0x180014edc  mov     rbx, [r11+10h]
0x180014ee0  mov     rdi, [r11+18h]
0x180014ee4  mov     rsp, r11
0x180014ee7  pop     rbp
0x180014ee8  retn
```
