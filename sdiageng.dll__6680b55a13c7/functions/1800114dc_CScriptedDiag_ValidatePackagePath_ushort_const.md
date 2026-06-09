# CScriptedDiag::ValidatePackagePath(ushort const *)

- ea: `0x1800114dc`
- end: `0x18001162a`
- name: `?ValidatePackagePath@CScriptedDiag@@AEAAJPEBG@Z`
- size: `334`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800101cc`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x1800114dc`
- `0x180026fa0`

## import_xrefs

- `KERNEL32!GetDriveTypeW` at `0x1800115cb`
- `KERNEL32!GetDriveTypeW` at `0x1800115cb`

## string_xrefs

- `0x1800115e5`: `CScriptedDiag::ValidatePackagePath`
- `0x18001160e`: `CScriptedDiag::ValidatePackagePath`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::ValidatePackagePath(CScriptedDiag *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rdi
  const unsigned __int16 *v3; // rax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v6; // r9d
  int v7; // r8d
  WCHAR *v8; // rsi
  __int64 v9; // rax
  WCHAR *v10; // r8
  __int64 v11; // rdx
  WCHAR *v12; // rcx
  int v13; // r9d
  int v14; // r8d

  v2 = a2;
  if ( !a2 )
  {
    v5 = -2147024809;
LABEL_23:
    v7 = 2063;
    goto LABEL_24;
  }
  v3 = a2;
  v4 = 260;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v4;
  }
  while ( v4 );
  v5 = v4 == 0 ? 0x80070057 : 0;
  if ( !v4 )
    goto LABEL_23;
  if ( ((260 - v4) & (unsigned __int64)-(__int64)(v4 != 0)) < 3 )
  {
    v6 = -2147467259;
    v7 = 2067;
    v5 = -2147467259;
LABEL_25:
    SdpDebugTrace(1u, L"CScriptedDiag::ValidatePackagePath", v7, v6);
    return v5;
  }
  v8 = (WCHAR *)operator new[](8u);
  if ( !v8 )
  {
    v5 = -2147024882;
    v7 = 2071;
LABEL_24:
    v6 = v5;
    goto LABEL_25;
  }
  v9 = 3;
  v10 = v8;
  v11 = 4;
  do
  {
    if ( !v9 )
      break;
    if ( !*v2 )
      break;
    *v10++ = *v2++;
    --v9;
    --v11;
  }
  while ( v11 );
  v12 = v10 - 1;
  v5 = v11 == 0 ? 0x8007007A : 0;
  if ( v11 )
    v12 = v10;
  *v12 = 0;
  if ( !v11 )
  {
    v13 = -2147024774;
    v14 = 2077;
LABEL_20:
    SdpDebugTrace(1u, L"CScriptedDiag::ValidatePackagePath", v14, v13);
    goto LABEL_21;
  }
  if ( GetDriveTypeW(v8) != 3 )
  {
    v13 = -2147467259;
    v14 = 2083;
    v5 = -2147467259;
    goto LABEL_20;
  }
LABEL_21:
  operator delete(v8);
  return v5;
}

```

## disassembly

```asm
0x1800114dc  push    rbx
0x1800114de  push    rbp
0x1800114df  push    rsi
0x1800114e0  push    rdi
0x1800114e1  sub     rsp, 28h
0x1800114e5  xor     ebp, ebp
0x1800114e7  mov     rdi, rdx
0x1800114ea  test    rdx, rdx
0x1800114ed  jz      loc_180011600
0x1800114f3  mov     edx, 104h
0x1800114f8  mov     rax, rdi
0x1800114fb  mov     ecx, edx
0x1800114fd  cmp     [rax], bp
0x180011500  jz      short loc_18001150C
0x180011502  add     rax, 2
0x180011506  sub     rcx, 1
0x18001150a  jnz     short loc_1800114FD
0x18001150c  mov     rax, rcx
0x18001150f  neg     rax
0x180011512  mov     rax, rcx
0x180011515  sbb     ebx, ebx
0x180011517  sub     rdx, rcx
0x18001151a  not     ebx
0x18001151c  and     ebx, 80070057h
0x180011522  neg     rax
0x180011525  sbb     r8, r8
0x180011528  and     r8, rdx
0x18001152b  test    rcx, rcx
0x18001152e  jz      loc_180011605
0x180011534  cmp     r8, 3
0x180011538  jnb     short loc_18001154E
0x18001153a  mov     r9d, 80004005h
0x180011540  mov     r8d, 813h
0x180011546  mov     ebx, r9d
0x180011549  jmp     loc_18001160E
0x18001154e  mov     ecx, 8; unsigned __int64
0x180011553  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011558  mov     rsi, rax
0x18001155b  test    rax, rax
0x18001155e  jnz     short loc_180011570
0x180011560  mov     ebx, 8007000Eh
0x180011565  mov     r8d, 817h
0x18001156b  jmp     loc_18001160B
0x180011570  mov     eax, 3
0x180011575  mov     r8, rsi
0x180011578  lea     edx, [rax+1]
0x18001157b  test    rax, rax
0x18001157e  jz      short loc_18001159D
0x180011580  movzx   ecx, word ptr [rdi]
0x180011583  test    cx, cx
0x180011586  jz      short loc_18001159D
0x180011588  mov     [r8], cx
0x18001158c  add     rdi, 2
0x180011590  add     r8, 2
0x180011594  dec     rax
0x180011597  sub     rdx, 1
0x18001159b  jnz     short loc_18001157B
0x18001159d  mov     rax, rdx
0x1800115a0  lea     rcx, [r8-2]
0x1800115a4  neg     rax
0x1800115a7  sbb     ebx, ebx
0x1800115a9  not     ebx
0x1800115ab  and     ebx, 8007007Ah
0x1800115b1  test    rdx, rdx
0x1800115b4  cmovnz  rcx, r8
0x1800115b8  mov     [rcx], bp
0x1800115bb  jnz     short loc_1800115C8
0x1800115bd  mov     r9d, ebx
0x1800115c0  mov     r8d, 81Dh
0x1800115c6  jmp     short loc_1800115E5
0x1800115c8  mov     rcx, rsi; lpRootPathName
0x1800115cb  call    cs:__imp_GetDriveTypeW
0x1800115d1  cmp     eax, 3
0x1800115d4  jz      short loc_1800115F6
0x1800115d6  mov     r9d, 80004005h; int
0x1800115dc  mov     r8d, 823h; int
0x1800115e2  mov     ebx, r9d
0x1800115e5  lea     rdx, aCscripteddiagV; "CScriptedDiag::ValidatePackagePath"
0x1800115ec  mov     ecx, 1; Level
0x1800115f1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800115f6  mov     rcx, rsi; Block
0x1800115f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800115fe  jmp     short loc_18001161F
0x180011600  mov     ebx, 80070057h
0x180011605  mov     r8d, 80Fh; int
0x18001160b  mov     r9d, ebx; int
0x18001160e  lea     rdx, aCscripteddiagV; "CScriptedDiag::ValidatePackagePath"
0x180011615  mov     ecx, 1; Level
0x18001161a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001161f  mov     eax, ebx
0x180011621  add     rsp, 28h
0x180011625  pop     rdi
0x180011626  pop     rsi
0x180011627  pop     rbp
0x180011628  pop     rbx
0x180011629  retn
```
