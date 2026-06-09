# CScriptedDiag::get_ExtensionPoint(ushort * *)

- ea: `0x180013650`
- end: `0x180013719`
- name: `?get_ExtensionPoint@CScriptedDiag@@UEAAJPEAPEAG@Z`
- size: `201`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000a818`
- `0x180013650`
- `0x180026fa0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800136cd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800136cd`

## string_xrefs

- `0x180013678`: `CScriptedDiag::get_ExtensionPoint`
- `0x1800136e3`: `DiagPackage::get_ExtensionPoint`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::get_ExtensionPoint(CScriptedDiag *this, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  int v7; // eax
  __int64 v8; // rax
  const OLECHAR *v9; // rcx
  int v10; // r8d
  unsigned __int16 *v11; // rax

  if ( a2 )
  {
    v7 = CScriptedDiag::CheckStateInitialized(this);
    v4 = v7;
    if ( v7 < 0 )
    {
      v6 = v7;
      v5 = 206;
      goto LABEL_4;
    }
    v8 = *((_QWORD *)this + 4);
    if ( v8 )
    {
      v9 = *(const OLECHAR **)(v8 + 80);
      if ( v9 )
      {
        v11 = SysAllocString(v9);
        if ( v11 )
        {
          v4 = 0;
          *a2 = v11;
          return v4;
        }
        v4 = -2147024882;
        v10 = 728;
      }
      else
      {
        v4 = -2147467261;
        v10 = 725;
      }
      SdpDebugTrace(1u, L"DiagPackage::get_ExtensionPoint", v10, v4);
      v5 = 211;
    }
    else
    {
      v4 = -2147467261;
      v5 = 208;
    }
  }
  else
  {
    v4 = -2147024809;
    v5 = 203;
  }
  v6 = v4;
LABEL_4:
  SdpDebugTrace(1u, L"CScriptedDiag::get_ExtensionPoint", v5, v6);
  return v4;
}

```

## disassembly

```asm
0x180013650  mov     [rsp+arg_0], rbx
0x180013655  mov     [rsp+arg_8], rsi
0x18001365a  push    rdi
0x18001365b  sub     rsp, 20h
0x18001365f  mov     rsi, rdx
0x180013662  mov     rdi, rcx
0x180013665  test    rdx, rdx
0x180013668  jnz     short loc_18001368B
0x18001366a  mov     ebx, 80070057h
0x18001366f  mov     r8d, 0CBh; int
0x180013675  mov     r9d, ebx; int
0x180013678  lea     rdx, aCscripteddiagG_5; "CScriptedDiag::get_ExtensionPoint"
0x18001367f  mov     ecx, 1; Level
0x180013684  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180013689  jmp     short loc_180013707
0x18001368b  call    ?CheckStateInitialized@CScriptedDiag@@AEAAJXZ; CScriptedDiag::CheckStateInitialized(void)
0x180013690  mov     ebx, eax
0x180013692  test    eax, eax
0x180013694  jns     short loc_1800136A1
0x180013696  mov     r9d, eax
0x180013699  mov     r8d, 0CEh
0x18001369f  jmp     short loc_180013678
0x1800136a1  mov     rax, [rdi+20h]
0x1800136a5  test    rax, rax
0x1800136a8  jnz     short loc_1800136B7
0x1800136aa  mov     ebx, 80004003h
0x1800136af  mov     r8d, 0D0h
0x1800136b5  jmp     short loc_180013675
0x1800136b7  mov     rcx, [rax+50h]; psz
0x1800136bb  test    rcx, rcx
0x1800136be  jnz     short loc_1800136CD
0x1800136c0  mov     ebx, 80004003h
0x1800136c5  mov     r8d, 2D5h
0x1800136cb  jmp     short loc_1800136E3
0x1800136cd  call    cs:__imp_SysAllocString
0x1800136d3  test    rax, rax
0x1800136d6  jnz     short loc_180013702
0x1800136d8  mov     ebx, 8007000Eh
0x1800136dd  mov     r8d, 2D8h; int
0x1800136e3  lea     rdx, aDiagpackageGet; "DiagPackage::get_ExtensionPoint"
0x1800136ea  mov     r9d, ebx; int
0x1800136ed  mov     ecx, 1; Level
0x1800136f2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800136f7  mov     r8d, 0D3h
0x1800136fd  jmp     loc_180013675
0x180013702  xor     ebx, ebx
0x180013704  mov     [rsi], rax
0x180013707  mov     rsi, [rsp+28h+arg_8]
0x18001370c  mov     eax, ebx
0x18001370e  mov     rbx, [rsp+28h+arg_0]
0x180013713  add     rsp, 20h
0x180013717  pop     rdi
0x180013718  retn
```
