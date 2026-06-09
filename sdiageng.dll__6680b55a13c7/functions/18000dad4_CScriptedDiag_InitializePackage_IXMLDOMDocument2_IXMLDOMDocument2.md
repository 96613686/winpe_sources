# CScriptedDiag::InitializePackage(IXMLDOMDocument2 *,IXMLDOMDocument2 *)

- ea: `0x18000dad4`
- end: `0x18000dbad`
- name: `?InitializePackage@CScriptedDiag@@AEAAJPEAUIXMLDOMDocument2@@0@Z`
- size: `217`
- prototype: `__int64 __fastcall(CScriptedDiag *this, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000cf00`

## callees

- `0x180001264`
- `0x18000dad4`
- `0x180016080`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::InitializePackage(
        CScriptedDiag *this,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMDocument2 *a3)
{
  unsigned int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  _QWORD *v9; // rax
  int v10; // eax

  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 916;
    v8 = -2147024809;
LABEL_10:
    SdpDebugTrace(1u, L"CScriptedDiag::InitializePackage", v7, v8);
    return v6;
  }
  v9 = operator new(0x88u);
  if ( v9 )
  {
    *(_DWORD *)v9 = 0;
    v9[1] = 0;
    v9[2] = 0;
    v9[3] = 0;
    *((_DWORD *)v9 + 8) = 0;
    v9[5] = 0;
    v9[10] = 0;
    v9[11] = 0;
    v9[12] = 0;
    v9[13] = 0;
    v9[14] = 0;
    *((_DWORD *)v9 + 30) = 0;
    v9[16] = 0;
    *((_OWORD *)v9 + 3) = 0;
    *((_OWORD *)v9 + 4) = 0;
  }
  else
  {
    v9 = 0;
  }
  *((_QWORD *)this + 4) = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    v7 = 919;
    v8 = -2147024882;
    goto LABEL_10;
  }
  v10 = DiagPackage::Initialize((DiagPackage *)v9, *((struct Settings **)this + 3), a2, a3);
  v6 = v10;
  if ( v10 < 0 )
  {
    v8 = v10;
    v7 = 922;
    goto LABEL_10;
  }
  return v6;
}

```

## disassembly

```asm
0x18000dad4  push    rbx
0x18000dad6  push    rbp
0x18000dad7  push    rsi
0x18000dad8  push    rdi
0x18000dad9  sub     rsp, 28h
0x18000dadd  xor     ebp, ebp
0x18000dadf  mov     rsi, r8
0x18000dae2  mov     rdi, rdx
0x18000dae5  mov     rbx, rcx
0x18000dae8  test    rdx, rdx
0x18000daeb  jnz     short loc_18000DB00
0x18000daed  mov     ebx, 80070057h
0x18000daf2  mov     r8d, 394h
0x18000daf8  mov     r9d, ebx
0x18000dafb  jmp     loc_18000DB91
0x18000db00  mov     ecx, 88h; Size
0x18000db05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000db0a  mov     [rsp+48h+arg_8], rax
0x18000db0f  test    rax, rax
0x18000db12  jz      short loc_18000DB54
0x18000db14  xorps   xmm0, xmm0
0x18000db17  mov     [rax], ebp
0x18000db19  mov     [rax+8], rbp
0x18000db1d  mov     [rax+10h], rbp
0x18000db21  mov     [rax+18h], rbp
0x18000db25  mov     [rax+20h], ebp
0x18000db28  mov     [rax+28h], rbp
0x18000db2c  mov     [rax+50h], rbp
0x18000db30  mov     [rax+58h], rbp
0x18000db34  mov     [rax+60h], rbp
0x18000db38  mov     [rax+68h], rbp
0x18000db3c  mov     [rax+70h], rbp
0x18000db40  mov     [rax+78h], ebp
0x18000db43  mov     [rax+80h], rbp
0x18000db4a  movups  xmmword ptr [rax+30h], xmm0
0x18000db4e  movups  xmmword ptr [rax+40h], xmm0
0x18000db52  jmp     short loc_18000DB57
0x18000db54  mov     rax, rbp
0x18000db57  mov     [rbx+20h], rax
0x18000db5b  test    rax, rax
0x18000db5e  jnz     short loc_18000DB70
0x18000db60  mov     ebx, 8007000Eh
0x18000db65  mov     r8d, 397h
0x18000db6b  mov     r9d, ebx
0x18000db6e  jmp     short loc_18000DB91
0x18000db70  mov     rdx, [rbx+18h]; struct Settings *
0x18000db74  mov     r9, rsi; struct IXMLDOMDocument2 *
0x18000db77  mov     r8, rdi; struct IXMLDOMDocument2 *
0x18000db7a  mov     rcx, rax; this
0x18000db7d  call    ?Initialize@DiagPackage@@QEAAJPEAVSettings@@PEAUIXMLDOMDocument2@@1@Z; DiagPackage::Initialize(Settings *,IXMLDOMDocument2 *,IXMLDOMDocument2 *)
0x18000db82  mov     ebx, eax
0x18000db84  test    eax, eax
0x18000db86  jns     short loc_18000DBA2
0x18000db88  mov     r9d, eax; int
0x18000db8b  mov     r8d, 39Ah; int
0x18000db91  lea     rdx, aCscripteddiagI_1; "CScriptedDiag::InitializePackage"
0x18000db98  mov     ecx, 1; Level
0x18000db9d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000dba2  mov     eax, ebx
0x18000dba4  add     rsp, 28h
0x18000dba8  pop     rdi
0x18000dba9  pop     rsi
0x18000dbaa  pop     rbp
0x18000dbab  pop     rbx
0x18000dbac  retn
```
