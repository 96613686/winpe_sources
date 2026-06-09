# CScriptedDiag::CopyPackage(ushort const *,ushort const *)

- ea: `0x18000a86c`
- end: `0x18000aa85`
- name: `?CopyPackage@CScriptedDiag@@AEAAJPEBG0@Z`
- size: `537`
- prototype: `__int64 __fastcall(CScriptedDiag *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1800101cc`

## callees

- `0x1800012a4`
- `0x1800020f8`
- `0x1800027f8`
- `0x18000a86c`
- `0x18001e6c0`
- `0x180026958`
- `0x180026fa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a9bf`
- `KERNEL32!GetLastError` at `0x18000a9fc`
- `KERNEL32!GetLastError` at `0x18000a9bf`
- `KERNEL32!GetLastError` at `0x18000a9fc`
- `KERNEL32!CreateDirectoryW` at `0x18000a9f2`
- `KERNEL32!CreateDirectoryW` at `0x18000a9f2`

## string_xrefs

- `0x18000a8b1`: `CScriptedDiag::CopyPackage`
- `0x18000a91f`: `CScriptedDiag::CopyPackage`
- `0x18000a986`: `CScriptedDiag::CopyPackage`
- `0x18000aa3a`: `CScriptedDiag::CopyPackage`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::CopyPackage(
        CScriptedDiag *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rdi
  int v7; // r8d
  int v8; // r9d
  signed int v9; // ebx
  int v10; // eax
  Settings *v11; // rcx
  int Locale; // eax
  unsigned __int16 *v13; // rsi
  int v14; // eax
  WCHAR *v15; // r15
  int v16; // r8d
  int v17; // eax
  int v18; // r8d
  int v19; // r9d
  signed int v20; // eax
  signed int LastError; // eax
  int v22; // r9d
  unsigned __int16 *v24; // [rsp+20h] [rbp-10h] BYREF
  void *Block; // [rsp+28h] [rbp-8h] BYREF
  int v26; // [rsp+68h] [rbp+38h] BYREF
  LPCWSTR lpPathName; // [rsp+78h] [rbp+48h] BYREF

  v3 = 0;
  Block = 0;
  lpPathName = 0;
  v24 = 0;
  v26 = 0;
  if ( !a2 )
  {
    v7 = 1727;
LABEL_3:
    v8 = -2147024809;
    v9 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"CScriptedDiag::CopyPackage", v7, v8);
    return (unsigned int)v9;
  }
  if ( !a3 )
  {
    v7 = 1728;
    goto LABEL_3;
  }
  v10 = SdpCopyDirectory(a2, a3);
  v9 = v10;
  if ( v10 < 0 )
  {
    v8 = v10;
    v7 = 1731;
    goto LABEL_4;
  }
  v11 = (Settings *)*((_QWORD *)this + 3);
  if ( !v11 )
  {
    v9 = -2147467261;
    v7 = 1733;
    v8 = -2147467261;
    goto LABEL_4;
  }
  Locale = Settings::get_Locale(v11, &v24);
  v13 = v24;
  v9 = Locale;
  if ( Locale >= 0 )
  {
    if ( !v24 )
      return (unsigned int)v9;
    v14 = SdpBuildPath(a2, v24, (unsigned __int16 **)&Block);
    v15 = (WCHAR *)Block;
    v9 = v14;
    if ( v14 < 0 )
    {
      v16 = 1747;
LABEL_35:
      v22 = v14;
      goto LABEL_36;
    }
    v17 = SdpBuildPath(a3, v13, (unsigned __int16 **)&lpPathName);
    v9 = v17;
    if ( v17 >= 0 )
    {
      v17 = SdpPathExists(v15, &v26);
      v9 = v17;
      if ( v17 >= 0 )
      {
        if ( v26 )
        {
          v3 = (unsigned __int16 *)lpPathName;
          if ( !CreateDirectoryW(lpPathName, 0) )
          {
            LastError = GetLastError();
            v9 = LastError;
            if ( LastError > 0 )
              v9 = (unsigned __int16)LastError | 0x80070000;
            if ( v9 < 0 )
            {
              v22 = v9;
              v16 = 1760;
LABEL_36:
              SdpDebugTrace(1u, L"CScriptedDiag::CopyPackage", v16, v22);
              goto LABEL_37;
            }
          }
          v14 = SdpCopyDirectory(v15, v3);
          v9 = v14;
          if ( v14 < 0 )
          {
            v16 = 1763;
            goto LABEL_35;
          }
LABEL_37:
          if ( v15 )
            operator delete(v15);
          if ( v3 )
            operator delete(v3);
          goto LABEL_41;
        }
        v20 = GetLastError();
        v9 = v20;
        if ( v20 > 0 )
          v9 = (unsigned __int16)v20 | 0x80070000;
        v18 = 1757;
        if ( v9 >= 0 )
          v9 = -2147467259;
        v19 = v9;
LABEL_19:
        SdpDebugTrace(1u, L"CScriptedDiag::CopyPackage", v18, v19);
        v3 = (unsigned __int16 *)lpPathName;
        goto LABEL_37;
      }
      v18 = 1756;
    }
    else
    {
      v18 = 1750;
    }
    v19 = v17;
    goto LABEL_19;
  }
  SdpDebugTrace(1u, L"CScriptedDiag::CopyPackage", 1736, Locale);
LABEL_41:
  if ( v13 )
    operator delete(v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a86c  mov     [rsp-28h+arg_0], rbx
0x18000a871  push    rbp
0x18000a872  push    rsi
0x18000a873  push    rdi
0x18000a874  push    r14
0x18000a876  push    r15
0x18000a878  mov     rbp, rsp
0x18000a87b  sub     rsp, 30h
0x18000a87f  xor     edi, edi
0x18000a881  mov     [rbp+Block], 0
0x18000a889  mov     [rbp+lpPathName], rdi
0x18000a88d  mov     r14, r8
0x18000a890  mov     [rbp+var_10], rdi
0x18000a894  mov     r15, rdx
0x18000a897  mov     [rbp+arg_8], edi
0x18000a89a  mov     rsi, rcx
0x18000a89d  test    rdx, rdx
0x18000a8a0  jnz     short loc_18000A8C7
0x18000a8a2  mov     r8d, 6BFh; int
0x18000a8a8  mov     r9d, 80070057h; int
0x18000a8ae  mov     ebx, r9d
0x18000a8b1  lea     rdx, aCscripteddiagC_3; "CScriptedDiag::CopyPackage"
0x18000a8b8  mov     ecx, 1; Level
0x18000a8bd  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000a8c2  jmp     loc_18000AA72
0x18000a8c7  test    r14, r14
0x18000a8ca  jnz     short loc_18000A8D4
0x18000a8cc  mov     r8d, 6C0h
0x18000a8d2  jmp     short loc_18000A8A8
0x18000a8d4  mov     rdx, r14; unsigned __int16 *
0x18000a8d7  mov     rcx, r15; unsigned __int16 *
0x18000a8da  call    ?SdpCopyDirectory@@YAJPEBG0@Z; SdpCopyDirectory(ushort const *,ushort const *)
0x18000a8df  mov     ebx, eax
0x18000a8e1  test    eax, eax
0x18000a8e3  jns     short loc_18000A8F0
0x18000a8e5  mov     r9d, eax
0x18000a8e8  mov     r8d, 6C3h
0x18000a8ee  jmp     short loc_18000A8B1
0x18000a8f0  mov     rcx, [rsi+18h]; this
0x18000a8f4  test    rcx, rcx
0x18000a8f7  jnz     short loc_18000A909
0x18000a8f9  mov     ebx, 80004003h
0x18000a8fe  mov     r8d, 6C5h
0x18000a904  mov     r9d, ebx
0x18000a907  jmp     short loc_18000A8B1
0x18000a909  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x18000a90d  call    ?get_Locale@Settings@@QEAAJPEAPEAG@Z; Settings::get_Locale(ushort * *)
0x18000a912  mov     rsi, [rbp+var_10]
0x18000a916  mov     ebx, eax
0x18000a918  test    eax, eax
0x18000a91a  jns     short loc_18000A93B
0x18000a91c  mov     r9d, eax; int
0x18000a91f  lea     rdx, aCscripteddiagC_3; "CScriptedDiag::CopyPackage"
0x18000a926  mov     r8d, 6C8h; int
0x18000a92c  mov     ecx, 1; Level
0x18000a931  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000a936  jmp     loc_18000AA65
0x18000a93b  test    rsi, rsi
0x18000a93e  jz      loc_18000AA72
0x18000a944  lea     r8, [rbp+Block]; unsigned __int16 **
0x18000a948  mov     rdx, rsi; unsigned __int16 *
0x18000a94b  mov     rcx, r15; unsigned __int16 *
0x18000a94e  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x18000a953  mov     r15, [rbp+Block]
0x18000a957  mov     ebx, eax
0x18000a959  test    eax, eax
0x18000a95b  jns     short loc_18000A968
0x18000a95d  mov     r8d, 6D3h
0x18000a963  jmp     loc_18000AA37
0x18000a968  lea     r8, [rbp+lpPathName]; unsigned __int16 **
0x18000a96c  mov     rdx, rsi; unsigned __int16 *
0x18000a96f  mov     rcx, r14; unsigned __int16 *
0x18000a972  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x18000a977  mov     ebx, eax
0x18000a979  test    eax, eax
0x18000a97b  jns     short loc_18000A9A0
0x18000a97d  mov     r8d, 6D6h; int
0x18000a983  mov     r9d, eax; int
0x18000a986  lea     rdx, aCscripteddiagC_3; "CScriptedDiag::CopyPackage"
0x18000a98d  mov     ecx, 1; Level
0x18000a992  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000a997  mov     rdi, [rbp+lpPathName]
0x18000a99b  jmp     loc_18000AA4B
0x18000a9a0  lea     rdx, [rbp+arg_8]; int *
0x18000a9a4  mov     rcx, r15; lpFileName
0x18000a9a7  call    ?SdpPathExists@@YAJPEBGPEAH@Z; SdpPathExists(ushort const *,int *)
0x18000a9ac  mov     ebx, eax
0x18000a9ae  test    eax, eax
0x18000a9b0  jns     short loc_18000A9BA
0x18000a9b2  mov     r8d, 6DCh
0x18000a9b8  jmp     short loc_18000A983
0x18000a9ba  cmp     [rbp+arg_8], edi
0x18000a9bd  jnz     short loc_18000A9E9
0x18000a9bf  call    cs:__imp_GetLastError
0x18000a9c5  mov     ebx, eax
0x18000a9c7  test    eax, eax
0x18000a9c9  jle     short loc_18000A9D4
0x18000a9cb  movzx   ebx, ax
0x18000a9ce  or      ebx, 80070000h
0x18000a9d4  test    ebx, ebx
0x18000a9d6  mov     eax, 80004005h
0x18000a9db  mov     r8d, 6DDh
0x18000a9e1  cmovns  ebx, eax
0x18000a9e4  mov     r9d, ebx
0x18000a9e7  jmp     short loc_18000A986
0x18000a9e9  mov     rdi, [rbp+lpPathName]
0x18000a9ed  xor     edx, edx; lpSecurityAttributes
0x18000a9ef  mov     rcx, rdi; lpPathName
0x18000a9f2  call    cs:__imp_CreateDirectoryW
0x18000a9f8  test    eax, eax
0x18000a9fa  jnz     short loc_18000AA20
0x18000a9fc  call    cs:__imp_GetLastError
0x18000aa02  mov     ebx, eax
0x18000aa04  test    eax, eax
0x18000aa06  jle     short loc_18000AA11
0x18000aa08  movzx   ebx, ax
0x18000aa0b  or      ebx, 80070000h
0x18000aa11  test    ebx, ebx
0x18000aa13  jns     short loc_18000AA20
0x18000aa15  mov     r9d, ebx
0x18000aa18  mov     r8d, 6E0h
0x18000aa1e  jmp     short loc_18000AA3A
0x18000aa20  mov     rdx, rdi; unsigned __int16 *
0x18000aa23  mov     rcx, r15; unsigned __int16 *
0x18000aa26  call    ?SdpCopyDirectory@@YAJPEBG0@Z; SdpCopyDirectory(ushort const *,ushort const *)
0x18000aa2b  mov     ebx, eax
0x18000aa2d  test    eax, eax
0x18000aa2f  jns     short loc_18000AA4B
0x18000aa31  mov     r8d, 6E3h; int
0x18000aa37  mov     r9d, eax; int
0x18000aa3a  lea     rdx, aCscripteddiagC_3; "CScriptedDiag::CopyPackage"
0x18000aa41  mov     ecx, 1; Level
0x18000aa46  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000aa4b  test    r15, r15
0x18000aa4e  jz      short loc_18000AA58
0x18000aa50  mov     rcx, r15; Block
0x18000aa53  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000aa58  test    rdi, rdi
0x18000aa5b  jz      short loc_18000AA65
0x18000aa5d  mov     rcx, rdi; Block
0x18000aa60  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000aa65  test    rsi, rsi
0x18000aa68  jz      short loc_18000AA72
0x18000aa6a  mov     rcx, rsi; Block
0x18000aa6d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000aa72  mov     eax, ebx
0x18000aa74  mov     rbx, [rsp+30h+arg_0]
0x18000aa79  add     rsp, 30h
0x18000aa7d  pop     r15
0x18000aa7f  pop     r14
0x18000aa81  pop     rdi
0x18000aa82  pop     rsi
0x18000aa83  pop     rbp
0x18000aa84  retn
```
