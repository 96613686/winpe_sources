# CScriptedDiag::get_PrivacyLink(ushort * *)

- ea: `0x1800138d0`
- end: `0x180013a08`
- name: `?get_PrivacyLink@CScriptedDiag@@UEAAJPEAPEAG@Z`
- size: `312`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x1800012a4`
- `0x18000a818`
- `0x1800138d0`
- `0x180026fa0`
- `0x180027aa0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800139ce`
- `OLEAUT32!__imp_SysAllocString` at `0x1800139ce`

## string_xrefs

- `0x1800138f8`: `CScriptedDiag::get_PrivacyLink`
- `0x1800139b8`: `CScriptedDiag::get_PrivacyLink`
- `0x18001394f`: `Settings::get_PackagePrivacyLink`
- `0x18001397c`: `Settings::get_PackagePrivacyLink`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::get_PrivacyLink(CScriptedDiag *this, unsigned __int16 **a2)
{
  int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  int v7; // eax
  __int64 v8; // rax
  const unsigned __int16 *v9; // rdx
  unsigned __int16 *v10; // rdi
  int v11; // eax
  unsigned __int16 *v12; // rcx
  int v13; // r8d
  unsigned __int16 *v14; // rax
  unsigned __int16 *v16; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 464;
LABEL_3:
    v6 = v4;
LABEL_4:
    SdpDebugTrace(1u, L"CScriptedDiag::get_PrivacyLink", v5, v6);
    return (unsigned int)v4;
  }
  v7 = CScriptedDiag::CheckStateInitialized(this);
  v4 = v7;
  if ( v7 < 0 )
  {
    v6 = v7;
    v5 = 467;
    goto LABEL_4;
  }
  v8 = *((_QWORD *)this + 3);
  if ( !v8 )
  {
    v4 = -2147467261;
    v5 = 469;
    goto LABEL_3;
  }
  v9 = *(const unsigned __int16 **)(v8 + 40);
  v10 = 0;
  v16 = 0;
  if ( !v9 )
  {
    v4 = -2147467261;
    SdpDebugTrace(1u, L"Settings::get_PackagePrivacyLink", 1189, -2147467261);
LABEL_17:
    v13 = 472;
LABEL_18:
    SdpDebugTrace(1u, L"CScriptedDiag::get_PrivacyLink", v13, v4);
    goto LABEL_22;
  }
  v11 = SdpStrCpy(&v16, v9);
  v4 = v11;
  if ( v11 >= 0 )
  {
    v10 = v16;
    v12 = 0;
  }
  else
  {
    SdpDebugTrace(1u, L"Settings::get_PackagePrivacyLink", 1191, v11);
    v12 = v16;
  }
  if ( v12 )
    operator delete(v12);
  if ( v4 < 0 )
    goto LABEL_17;
  v14 = SysAllocString(v10);
  if ( !v14 )
  {
    v4 = -2147024882;
    v13 = 475;
    goto LABEL_18;
  }
  *a2 = v14;
LABEL_22:
  if ( v10 )
    operator delete(v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800138d0  mov     [rsp+arg_0], rbx
0x1800138d5  mov     [rsp+arg_10], rsi
0x1800138da  push    rdi
0x1800138db  sub     rsp, 20h
0x1800138df  mov     rsi, rdx
0x1800138e2  mov     rdi, rcx
0x1800138e5  test    rdx, rdx
0x1800138e8  jnz     short loc_18001390E
0x1800138ea  mov     ebx, 80070057h
0x1800138ef  mov     r8d, 1D0h; int
0x1800138f5  mov     r9d, ebx; int
0x1800138f8  lea     rdx, aCscripteddiagG_17; "CScriptedDiag::get_PrivacyLink"
0x1800138ff  mov     ecx, 1; Level
0x180013904  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180013909  jmp     loc_1800139F6
0x18001390e  call    ?CheckStateInitialized@CScriptedDiag@@AEAAJXZ; CScriptedDiag::CheckStateInitialized(void)
0x180013913  mov     ebx, eax
0x180013915  test    eax, eax
0x180013917  jns     short loc_180013924
0x180013919  mov     r9d, eax
0x18001391c  mov     r8d, 1D3h
0x180013922  jmp     short loc_1800138F8
0x180013924  mov     rax, [rdi+18h]
0x180013928  test    rax, rax
0x18001392b  jnz     short loc_18001393A
0x18001392d  mov     ebx, 80004003h
0x180013932  mov     r8d, 1D5h
0x180013938  jmp     short loc_1800138F5
0x18001393a  mov     rdx, [rax+28h]; unsigned __int16 *
0x18001393e  xor     edi, edi
0x180013940  mov     [rsp+28h+arg_8], rdi
0x180013945  test    rdx, rdx
0x180013948  jnz     short loc_180013969
0x18001394a  mov     ebx, 80004003h
0x18001394f  lea     rdx, aSettingsGetPac_1; "Settings::get_PackagePrivacyLink"
0x180013956  mov     r9d, ebx; int
0x180013959  lea     ecx, [rdi+1]; Level
0x18001395c  mov     r8d, 4A5h; int
0x180013962  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180013967  jmp     short loc_1800139AF
0x180013969  lea     rcx, [rsp+28h+arg_8]; unsigned __int16 **
0x18001396e  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x180013973  mov     ebx, eax
0x180013975  test    eax, eax
0x180013977  jns     short loc_18001399A
0x180013979  mov     r9d, eax; int
0x18001397c  lea     rdx, aSettingsGetPac_1; "Settings::get_PackagePrivacyLink"
0x180013983  mov     r8d, 4A7h; int
0x180013989  mov     ecx, 1; Level
0x18001398e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180013993  mov     rcx, [rsp+28h+arg_8]
0x180013998  jmp     short loc_1800139A1
0x18001399a  mov     rdi, [rsp+28h+arg_8]
0x18001399f  xor     ecx, ecx; Block
0x1800139a1  test    rcx, rcx
0x1800139a4  jz      short loc_1800139AB
0x1800139a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800139ab  test    ebx, ebx
0x1800139ad  jns     short loc_1800139CB
0x1800139af  mov     r8d, 1D8h; int
0x1800139b5  mov     r9d, ebx; int
0x1800139b8  lea     rdx, aCscripteddiagG_17; "CScriptedDiag::get_PrivacyLink"
0x1800139bf  mov     ecx, 1; Level
0x1800139c4  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800139c9  jmp     short loc_1800139E9
0x1800139cb  mov     rcx, rdi; psz
0x1800139ce  call    cs:__imp_SysAllocString
0x1800139d4  test    rax, rax
0x1800139d7  jnz     short loc_1800139E6
0x1800139d9  mov     ebx, 8007000Eh
0x1800139de  mov     r8d, 1DBh
0x1800139e4  jmp     short loc_1800139B5
0x1800139e6  mov     [rsi], rax
0x1800139e9  test    rdi, rdi
0x1800139ec  jz      short loc_1800139F6
0x1800139ee  mov     rcx, rdi; Block
0x1800139f1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800139f6  mov     rsi, [rsp+28h+arg_10]
0x1800139fb  mov     eax, ebx
0x1800139fd  mov     rbx, [rsp+28h+arg_0]
0x180013a02  add     rsp, 20h
0x180013a06  pop     rdi
0x180013a07  retn
```
