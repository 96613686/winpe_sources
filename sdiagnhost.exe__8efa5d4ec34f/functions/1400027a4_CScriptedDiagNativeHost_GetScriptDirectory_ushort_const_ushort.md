# CScriptedDiagNativeHost::GetScriptDirectory(ushort const *,ushort * *)

- ea: `0x1400027a4`
- end: `0x1400028d3`
- name: `?GetScriptDirectory@CScriptedDiagNativeHost@@AEAAJPEBGPEAPEAG@Z`
- size: `303`
- prototype: `__int64 __fastcall(CScriptedDiagNativeHost *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140002af0`

## callees

- `0x1400027a4`
- `0x140005964`
- `0x140006050`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1400028c2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400028c2`

## string_xrefs

- `0x1400027cc`: `CScriptedDiagNativeHost::GetScriptDirectory`
- `0x140002800`: `CScriptedDiagNativeHost::GetScriptDirectory`
- `0x1400028ae`: `CScriptedDiagNativeHost::GetScriptDirectory`

## pseudocode

```c
__int64 __fastcall CScriptedDiagNativeHost::GetScriptDirectory(
        CScriptedDiagNativeHost *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int v4; // r8d
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rcx
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v9; // rax
  __int64 v10; // rax
  int v11; // r8d
  unsigned __int16 *v13; // [rsp+50h] [rbp+8h] BYREF

  v13 = 0;
  if ( !a2 )
  {
    v4 = 261;
LABEL_3:
    v5 = -2147024809;
    SdpDebugTrace((unsigned int)this, L"CScriptedDiagNativeHost::GetScriptDirectory", v4, -2147024809);
    return v5;
  }
  if ( !a3 )
  {
    v4 = 262;
    goto LABEL_3;
  }
  v6 = SdpStrCpy(&v13, a2);
  v5 = v6;
  if ( v6 < 0 )
  {
    SdpDebugTrace(v7, L"CScriptedDiagNativeHost::GetScriptDirectory", 265, v6);
    v8 = v13;
    goto LABEL_22;
  }
  v8 = v13;
  if ( v13 )
  {
    v9 = v13;
    v7 = 260;
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --v7;
    }
    while ( v7 );
    v5 = v7 == 0 ? 0x80070057 : 0;
    v10 = (260 - v7) & -(__int64)(v7 != 0);
    if ( v7 )
    {
      if ( v10 )
      {
        do
        {
          LODWORD(v10) = v10 - 1;
          if ( (int)v10 < 0 )
          {
            v5 = -2147024809;
            v11 = 284;
            goto LABEL_21;
          }
        }
        while ( v13[(unsigned int)v10] != 92 );
        v13[(unsigned int)v10 + 1] = 0;
        *a3 = v8;
        v8 = 0;
        goto LABEL_22;
      }
      v5 = -2147024809;
      v11 = 272;
      goto LABEL_21;
    }
  }
  else
  {
    v5 = -2147024809;
  }
  v11 = 268;
LABEL_21:
  SdpDebugTrace(v7, L"CScriptedDiagNativeHost::GetScriptDirectory", v11, -2147024809);
LABEL_22:
  if ( v8 )
    operator delete[](v8);
  return v5;
}

```

## disassembly

```asm
0x1400027a4  mov     [rsp+arg_0], rcx
0x1400027a9  push    rbx
0x1400027aa  push    rbp
0x1400027ab  push    rsi
0x1400027ac  push    rdi
0x1400027ad  sub     rsp, 28h
0x1400027b1  xor     ebp, ebp
0x1400027b3  mov     rsi, r8
0x1400027b6  mov     [rsp+48h+arg_0], rbp
0x1400027bb  test    rdx, rdx
0x1400027be  jnz     short loc_1400027E0
0x1400027c0  mov     r8d, 105h; int
0x1400027c6  mov     r9d, 80070057h; int
0x1400027cc  lea     rdx, aCscripteddiagn_0; "CScriptedDiagNativeHost::GetScriptDirec"...
0x1400027d3  mov     ebx, r9d
0x1400027d6  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1400027db  jmp     loc_1400028C8
0x1400027e0  test    rsi, rsi
0x1400027e3  jnz     short loc_1400027ED
0x1400027e5  mov     r8d, 106h
0x1400027eb  jmp     short loc_1400027C6
0x1400027ed  lea     rcx, [rsp+48h+arg_0]; unsigned __int16 **
0x1400027f2  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x1400027f7  mov     ebx, eax
0x1400027f9  test    eax, eax
0x1400027fb  jns     short loc_14000281C
0x1400027fd  mov     r9d, eax; int
0x140002800  lea     rdx, aCscripteddiagn_0; "CScriptedDiagNativeHost::GetScriptDirec"...
0x140002807  mov     r8d, 109h; int
0x14000280d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140002812  mov     rdi, [rsp+48h+arg_0]
0x140002817  jmp     loc_1400028BA
0x14000281c  mov     rdi, [rsp+48h+arg_0]
0x140002821  test    rdi, rdi
0x140002824  jz      short loc_14000289F
0x140002826  mov     edx, 104h
0x14000282b  mov     rax, rdi
0x14000282e  mov     ecx, edx
0x140002830  cmp     [rax], bp
0x140002833  jz      short loc_14000283F
0x140002835  add     rax, 2
0x140002839  sub     rcx, 1
0x14000283d  jnz     short loc_140002830
0x14000283f  mov     rax, rcx
0x140002842  mov     r9d, 80070057h
0x140002848  neg     rax
0x14000284b  mov     rax, rcx
0x14000284e  sbb     ebx, ebx
0x140002850  sub     rdx, rcx
0x140002853  not     ebx
0x140002855  and     ebx, r9d
0x140002858  neg     rax
0x14000285b  sbb     rax, rax
0x14000285e  and     rax, rdx
0x140002861  test    rcx, rcx
0x140002864  jnz     short loc_14000286B
0x140002866  mov     r9d, ebx
0x140002869  jmp     short loc_1400028A8
0x14000286b  test    rax, rax
0x14000286e  jnz     short loc_140002882
0x140002870  mov     ebx, r9d
0x140002873  mov     r8d, 110h
0x140002879  jmp     short loc_1400028AE
0x14000287b  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x140002880  jz      short loc_140002892
0x140002882  sub     eax, 1
0x140002885  jns     short loc_14000287B
0x140002887  mov     ebx, r9d
0x14000288a  mov     r8d, 11Ch
0x140002890  jmp     short loc_1400028AE
0x140002892  mov     [rdi+rax*2+2], bp
0x140002897  mov     [rsi], rdi
0x14000289a  mov     rdi, rbp
0x14000289d  jmp     short loc_1400028BA
0x14000289f  mov     r9d, 80070057h; int
0x1400028a5  mov     ebx, r9d
0x1400028a8  mov     r8d, 10Ch; int
0x1400028ae  lea     rdx, aCscripteddiagn_0; "CScriptedDiagNativeHost::GetScriptDirec"...
0x1400028b5  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1400028ba  test    rdi, rdi
0x1400028bd  jz      short loc_1400028C8
0x1400028bf  mov     rcx, rdi
0x1400028c2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1400028c8  mov     eax, ebx
0x1400028ca  add     rsp, 28h
0x1400028ce  pop     rdi
0x1400028cf  pop     rsi
0x1400028d0  pop     rbp
0x1400028d1  pop     rbx
0x1400028d2  retn
```
