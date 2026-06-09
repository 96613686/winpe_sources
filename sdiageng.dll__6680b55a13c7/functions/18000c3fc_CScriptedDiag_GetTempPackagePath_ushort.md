# CScriptedDiag::GetTempPackagePath(ushort * *)

- ea: `0x18000c3fc`
- end: `0x18000c5a6`
- name: `?GetTempPackagePath@CScriptedDiag@@AEAAJPEAPEAG@Z`
- size: `426`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800101cc`

## callees

- `0x1800012a4`
- `0x1800020f8`
- `0x18000c144`
- `0x18000c31c`
- `0x18000c3fc`
- `0x18000c910`
- `0x180026fa0`
- `0x18002708c`
- `0x18002744c`

## string_xrefs

- `0x18000c443`: `CScriptedDiag::GetTempPackagePath`
- `0x18000c490`: `CScriptedDiag::GetTempPackagePath`
- `0x18000c4cb`: `CScriptedDiag::GetTempPackagePath`
- `0x18000c508`: `CScriptedDiag::GetTempPackagePath`
- `0x18000c541`: `CScriptedDiag::GetTempPackagePath`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::GetTempPackagePath(CScriptedDiag *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rsi
  unsigned __int16 *v3; // rdi
  unsigned int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  int IsAdmin; // eax
  CScriptedDiag *v9; // rcx
  int TempDirPath; // eax
  CScriptedDiag *v11; // rcx
  int v12; // r8d
  int UniqueName; // eax
  int v14; // eax
  int FullPath; // eax
  unsigned __int16 *v16; // rcx
  unsigned __int16 *v18; // [rsp+20h] [rbp-10h] BYREF
  int v19; // [rsp+60h] [rbp+30h] BYREF
  int v20; // [rsp+64h] [rbp+34h]
  void *Block; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int16 *v22; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int16 *v23; // [rsp+78h] [rbp+48h] BYREF

  v20 = HIDWORD(this);
  v2 = 0;
  v19 = 0;
  v3 = 0;
  Block = 0;
  v22 = 0;
  v23 = 0;
  v18 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 1807;
    v7 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"CScriptedDiag::GetTempPackagePath", v6, v7);
    return v5;
  }
  IsAdmin = SdpIsAdmin(&v19);
  v5 = IsAdmin;
  if ( IsAdmin < 0 )
  {
    v7 = IsAdmin;
    v6 = 1810;
    goto LABEL_3;
  }
  if ( !v19 )
  {
    TempDirPath = CScriptedDiag::GetTempDirPath(v9, (unsigned __int16 **)&Block);
    v5 = TempDirPath;
    if ( TempDirPath < 0 )
    {
      v12 = 1818;
      goto LABEL_9;
    }
LABEL_12:
    UniqueName = CScriptedDiag::GetUniqueName(v11, &v22);
    v5 = UniqueName;
    if ( UniqueName >= 0 )
    {
      v2 = v22;
      v14 = SdpBuildPath((const unsigned __int16 *)Block, v22, &v23);
      v5 = v14;
      if ( v14 >= 0 )
      {
        v3 = v23;
        FullPath = SdpGetFullPath(v23, &v18, 0);
        v5 = FullPath;
        if ( FullPath >= 0 )
        {
          v16 = 0;
          *a2 = v18;
        }
        else
        {
          SdpDebugTrace(1u, L"CScriptedDiag::GetTempPackagePath", 1828, FullPath);
          v16 = v18;
        }
        if ( v16 )
          operator delete(v16);
      }
      else
      {
        SdpDebugTrace(1u, L"CScriptedDiag::GetTempPackagePath", 1825, v14);
        v3 = v23;
      }
    }
    else
    {
      SdpDebugTrace(1u, L"CScriptedDiag::GetTempPackagePath", 1822, UniqueName);
      v2 = v22;
    }
    goto LABEL_21;
  }
  TempDirPath = CScriptedDiag::GetSystemTempDirPath(v9, (unsigned __int16 **)&Block);
  v5 = TempDirPath;
  if ( TempDirPath >= 0 )
    goto LABEL_12;
  v12 = 1814;
LABEL_9:
  SdpDebugTrace(1u, L"CScriptedDiag::GetTempPackagePath", v12, TempDirPath);
LABEL_21:
  if ( Block )
    operator delete(Block);
  if ( v2 )
    operator delete(v2);
  if ( v3 )
    operator delete(v3);
  return v5;
}

```

## disassembly

```asm
0x18000c3fc  mov     qword ptr [rsp-28h+arg_0], rcx
0x18000c401  push    rbp
0x18000c402  push    rbx
0x18000c403  push    rsi
0x18000c404  push    rdi
0x18000c405  push    r14
0x18000c407  mov     rbp, rsp
0x18000c40a  sub     rsp, 30h
0x18000c40e  xor     esi, esi
0x18000c410  mov     [rbp+arg_0], 0
0x18000c417  xor     edi, edi
0x18000c419  mov     [rbp+Block], 0
0x18000c421  mov     [rbp+arg_10], rsi
0x18000c425  mov     r14, rdx
0x18000c428  mov     [rbp+arg_18], rdi
0x18000c42c  mov     [rbp+var_10], rsi
0x18000c430  test    rdx, rdx
0x18000c433  jnz     short loc_18000C459
0x18000c435  mov     ebx, 80070057h
0x18000c43a  mov     r8d, 70Fh; int
0x18000c440  mov     r9d, ebx; int
0x18000c443  lea     rdx, aCscripteddiagG_8; "CScriptedDiag::GetTempPackagePath"
0x18000c44a  mov     ecx, 1; Level
0x18000c44f  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c454  jmp     loc_18000C599
0x18000c459  lea     rcx, [rbp+arg_0]; int *
0x18000c45d  call    ?SdpIsAdmin@@YAJPEAH@Z; SdpIsAdmin(int *)
0x18000c462  mov     ebx, eax
0x18000c464  test    eax, eax
0x18000c466  jns     short loc_18000C473
0x18000c468  mov     r9d, eax
0x18000c46b  mov     r8d, 712h
0x18000c471  jmp     short loc_18000C443
0x18000c473  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18000c477  cmp     [rbp+arg_0], esi
0x18000c47a  jz      short loc_18000C4A6
0x18000c47c  call    ?GetSystemTempDirPath@CScriptedDiag@@AEAAJPEAPEAG@Z; CScriptedDiag::GetSystemTempDirPath(ushort * *)
0x18000c481  mov     ebx, eax
0x18000c483  test    eax, eax
0x18000c485  jns     short loc_18000C4B9
0x18000c487  mov     r8d, 716h; int
0x18000c48d  mov     r9d, eax; int
0x18000c490  lea     rdx, aCscripteddiagG_8; "CScriptedDiag::GetTempPackagePath"
0x18000c497  mov     ecx, 1; Level
0x18000c49c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c4a1  jmp     loc_18000C571
0x18000c4a6  call    ?GetTempDirPath@CScriptedDiag@@AEAAJPEAPEAG@Z; CScriptedDiag::GetTempDirPath(ushort * *)
0x18000c4ab  mov     ebx, eax
0x18000c4ad  test    eax, eax
0x18000c4af  jns     short loc_18000C4B9
0x18000c4b1  mov     r8d, 71Ah
0x18000c4b7  jmp     short loc_18000C48D
0x18000c4b9  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x18000c4bd  call    ?GetUniqueName@CScriptedDiag@@AEAAJPEAPEAG@Z; CScriptedDiag::GetUniqueName(ushort * *)
0x18000c4c2  mov     ebx, eax
0x18000c4c4  test    eax, eax
0x18000c4c6  jns     short loc_18000C4EB
0x18000c4c8  mov     r9d, eax; int
0x18000c4cb  lea     rdx, aCscripteddiagG_8; "CScriptedDiag::GetTempPackagePath"
0x18000c4d2  mov     r8d, 71Eh; int
0x18000c4d8  mov     ecx, 1; Level
0x18000c4dd  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c4e2  mov     rsi, [rbp+arg_10]
0x18000c4e6  jmp     loc_18000C571
0x18000c4eb  mov     rsi, [rbp+arg_10]
0x18000c4ef  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x18000c4f3  mov     rcx, [rbp+Block]; unsigned __int16 *
0x18000c4f7  mov     rdx, rsi; unsigned __int16 *
0x18000c4fa  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x18000c4ff  mov     ebx, eax
0x18000c501  test    eax, eax
0x18000c503  jns     short loc_18000C525
0x18000c505  mov     r9d, eax; int
0x18000c508  lea     rdx, aCscripteddiagG_8; "CScriptedDiag::GetTempPackagePath"
0x18000c50f  mov     r8d, 721h; int
0x18000c515  mov     ecx, 1; Level
0x18000c51a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c51f  mov     rdi, [rbp+arg_18]
0x18000c523  jmp     short loc_18000C571
0x18000c525  mov     rdi, [rbp+arg_18]
0x18000c529  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x18000c52d  mov     rcx, rdi; unsigned __int16 *
0x18000c530  xor     r8d, r8d; unsigned __int16 **
0x18000c533  call    ?SdpGetFullPath@@YAJPEBGPEAPEAG1@Z; SdpGetFullPath(ushort const *,ushort * *,ushort * *)
0x18000c538  mov     ebx, eax
0x18000c53a  test    eax, eax
0x18000c53c  jns     short loc_18000C55E
0x18000c53e  mov     r9d, eax; int
0x18000c541  lea     rdx, aCscripteddiagG_8; "CScriptedDiag::GetTempPackagePath"
0x18000c548  mov     r8d, 724h; int
0x18000c54e  mov     ecx, 1; Level
0x18000c553  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c558  mov     rcx, [rbp+var_10]
0x18000c55c  jmp     short loc_18000C567
0x18000c55e  mov     rax, [rbp+var_10]
0x18000c562  xor     ecx, ecx; Block
0x18000c564  mov     [r14], rax
0x18000c567  test    rcx, rcx
0x18000c56a  jz      short loc_18000C571
0x18000c56c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c571  mov     rcx, [rbp+Block]; Block
0x18000c575  test    rcx, rcx
0x18000c578  jz      short loc_18000C57F
0x18000c57a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c57f  test    rsi, rsi
0x18000c582  jz      short loc_18000C58C
0x18000c584  mov     rcx, rsi; Block
0x18000c587  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c58c  test    rdi, rdi
0x18000c58f  jz      short loc_18000C599
0x18000c591  mov     rcx, rdi; Block
0x18000c594  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c599  mov     eax, ebx
0x18000c59b  add     rsp, 30h
0x18000c59f  pop     r14
0x18000c5a1  pop     rdi
0x18000c5a2  pop     rsi
0x18000c5a3  pop     rbx
0x18000c5a4  pop     rbp
0x18000c5a5  retn
```
