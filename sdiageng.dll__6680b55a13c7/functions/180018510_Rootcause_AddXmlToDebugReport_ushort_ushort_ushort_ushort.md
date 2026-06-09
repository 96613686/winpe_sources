# Rootcause::AddXmlToDebugReport(ushort *,ushort *,ushort *,ushort *)

- ea: `0x180018510`
- end: `0x18001870f`
- name: `?AddXmlToDebugReport@Rootcause@@QEAAJPEAG000@Z`
- size: `511`
- prototype: `__int64 __fastcall(Rootcause *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180014438`

## callees

- `0x180018510`
- `0x18001bcf8`
- `0x18001d470`
- `0x180026fa0`

## string_xrefs

- `0x1800186f6`: `Rootcause::AddXmlToDebugReport`
- `0x1800186a4`: `Resolver::AddXmlToDebugReport`
- `0x180018625`: `Verifier::AddXmlToDebugReport`

## pseudocode

```c
__int64 __fastcall Rootcause::AddXmlToDebugReport(
        Rootcause *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int v6; // r9d
  int v7; // r8d
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // rax
  Script *v13; // rcx
  int v14; // r9d
  int v15; // r8d
  int v16; // eax
  Script *v17; // rcx
  int v18; // r9d
  int v19; // r8d
  int v20; // eax
  Troubleshooter *v21; // rcx
  int v22; // eax

  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 1677;
    v8 = -2147024809;
LABEL_33:
    SdpDebugTrace(1u, L"Rootcause::AddXmlToDebugReport", v7, v6);
    return v8;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    v7 = 1678;
    v8 = -2147024809;
    goto LABEL_33;
  }
  if ( !a4 )
  {
    v6 = -2147024809;
    v7 = 1679;
    v8 = -2147024809;
    goto LABEL_33;
  }
  if ( !a5 )
  {
    v6 = -2147024809;
    v7 = 1680;
    v8 = -2147024809;
    goto LABEL_33;
  }
  v9 = *(_QWORD *)this;
  if ( !v9 )
  {
    v6 = -2147467261;
    v7 = 1682;
    v8 = -2147467261;
    goto LABEL_33;
  }
  v10 = *(_DWORD *)(v9 + 88) - 3;
  if ( v10 )
  {
    v11 = v10 - 2;
    if ( !v11 )
    {
      if ( *((int *)this + 26) < 0 )
      {
        v8 = -2147418113;
        v7 = 1697;
        v6 = -2147418113;
        goto LABEL_33;
      }
      v17 = *(Script **)(*((_QWORD *)this + 2) + 80LL * *((int *)this + 26) + 8);
      if ( v17 )
      {
        v20 = Script::AddXmlToDebugReport(v17, a2, a3, a4, a5);
        v8 = v20;
        if ( v20 >= 0 )
          return v8;
        v19 = 690;
        v18 = v20;
      }
      else
      {
        v18 = -2147467261;
        v19 = 688;
        v8 = -2147467261;
      }
      SdpDebugTrace(1u, L"Resolver::AddXmlToDebugReport", v19, v18);
      v6 = v8;
      v7 = 1703;
      goto LABEL_33;
    }
    if ( v11 != 1 )
    {
      v8 = -2147020579;
      v7 = 1716;
      v6 = -2147020579;
      goto LABEL_33;
    }
    v12 = *((_QWORD *)this + 3);
    if ( !v12 )
    {
      v6 = -2147467261;
      v7 = 1708;
      v8 = -2147467261;
      goto LABEL_33;
    }
    v13 = *(Script **)(v12 + 8);
    if ( !v13 )
    {
      v14 = -2147467261;
      v15 = 337;
      v8 = -2147467261;
LABEL_21:
      SdpDebugTrace(1u, L"Verifier::AddXmlToDebugReport", v15, v14);
      v6 = v8;
      v7 = 1710;
      goto LABEL_33;
    }
    v16 = Script::AddXmlToDebugReport(v13, a2, a3, a4, a5);
    v8 = v16;
    if ( v16 < 0 )
    {
      v15 = 339;
      v14 = v16;
      goto LABEL_21;
    }
  }
  else
  {
    v21 = (Troubleshooter *)*((_QWORD *)this + 1);
    if ( !v21 )
    {
      v6 = -2147467261;
      v7 = 1688;
      v8 = -2147467261;
      goto LABEL_33;
    }
    v22 = Troubleshooter::AddXmlToDebugReport(v21, a2, a3, a4, a5);
    v8 = v22;
    if ( v22 < 0 )
    {
      v6 = v22;
      v7 = 1690;
      goto LABEL_33;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180018510  push    rbx
0x180018512  sub     rsp, 30h
0x180018516  mov     r11, rdx
0x180018519  mov     r10, rcx
0x18001851c  test    rdx, rdx
0x18001851f  jnz     short loc_180018535
0x180018521  mov     r9d, 80070057h
0x180018527  mov     r8d, 68Dh
0x18001852d  mov     ebx, r9d
0x180018530  jmp     loc_1800186F6
0x180018535  test    r8, r8
0x180018538  jnz     short loc_18001854E
0x18001853a  mov     r9d, 80070057h
0x180018540  mov     r8d, 68Eh
0x180018546  mov     ebx, r9d
0x180018549  jmp     loc_1800186F6
0x18001854e  test    r9, r9
0x180018551  jnz     short loc_180018567
0x180018553  mov     r9d, 80070057h
0x180018559  mov     r8d, 68Fh
0x18001855f  mov     ebx, r9d
0x180018562  jmp     loc_1800186F6
0x180018567  mov     rdx, [rsp+38h+arg_20]
0x18001856c  test    rdx, rdx
0x18001856f  jnz     short loc_180018585
0x180018571  mov     r9d, 80070057h
0x180018577  mov     r8d, 690h
0x18001857d  mov     ebx, r9d
0x180018580  jmp     loc_1800186F6
0x180018585  mov     rcx, [rcx]
0x180018588  test    rcx, rcx
0x18001858b  jnz     short loc_1800185A1
0x18001858d  mov     r9d, 80004003h
0x180018593  mov     r8d, 692h
0x180018599  mov     ebx, r9d
0x18001859c  jmp     loc_1800186F6
0x1800185a1  mov     ecx, [rcx+58h]
0x1800185a4  sub     ecx, 3
0x1800185a7  jz      loc_1800186C0
0x1800185ad  sub     ecx, 2
0x1800185b0  jz      loc_180018644
0x1800185b6  cmp     ecx, 1
0x1800185b9  jz      short loc_1800185CE
0x1800185bb  mov     ebx, 800710DDh
0x1800185c0  mov     r8d, 6B4h
0x1800185c6  mov     r9d, ebx
0x1800185c9  jmp     loc_1800186F6
0x1800185ce  mov     rax, [r10+18h]
0x1800185d2  test    rax, rax
0x1800185d5  jnz     short loc_1800185EB
0x1800185d7  mov     r9d, 80004003h
0x1800185dd  mov     r8d, 6ACh
0x1800185e3  mov     ebx, r9d
0x1800185e6  jmp     loc_1800186F6
0x1800185eb  mov     rcx, [rax+8]; this
0x1800185ef  test    rcx, rcx
0x1800185f2  jnz     short loc_180018605
0x1800185f4  mov     r9d, 80004003h; unsigned __int16 *
0x1800185fa  mov     r8d, 151h; unsigned __int16 *
0x180018600  mov     ebx, r9d
0x180018603  jmp     short loc_180018625
0x180018605  mov     [rsp+38h+var_18], rdx; unsigned __int16 *
0x18001860a  mov     rdx, r11; unsigned __int16 *
0x18001860d  call    ?AddXmlToDebugReport@Script@@QEAAJPEAG000@Z; Script::AddXmlToDebugReport(ushort *,ushort *,ushort *,ushort *)
0x180018612  mov     ebx, eax
0x180018614  test    eax, eax
0x180018616  jns     loc_180018707
0x18001861c  mov     r8d, 153h; int
0x180018622  mov     r9d, eax; int
0x180018625  lea     rdx, aVerifierAddxml; "Verifier::AddXmlToDebugReport"
0x18001862c  mov     ecx, 1; Level
0x180018631  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180018636  mov     r9d, ebx
0x180018639  mov     r8d, 6AEh
0x18001863f  jmp     loc_1800186F6
0x180018644  cmp     dword ptr [r10+68h], 0
0x180018649  jge     short loc_18001865E
0x18001864b  mov     ebx, 8000FFFFh
0x180018650  mov     r8d, 6A1h
0x180018656  mov     r9d, ebx
0x180018659  jmp     loc_1800186F6
0x18001865e  movsxd  rax, dword ptr [r10+68h]
0x180018662  lea     rcx, [rax+rax*4]
0x180018666  mov     rax, [r10+10h]
0x18001866a  add     rcx, rcx
0x18001866d  mov     rcx, [rax+rcx*8+8]; this
0x180018672  test    rcx, rcx
0x180018675  jnz     short loc_180018688
0x180018677  mov     r9d, 80004003h; unsigned __int16 *
0x18001867d  mov     r8d, 2B0h; unsigned __int16 *
0x180018683  mov     ebx, r9d
0x180018686  jmp     short loc_1800186A4
0x180018688  mov     [rsp+38h+var_18], rdx; unsigned __int16 *
0x18001868d  mov     rdx, r11; unsigned __int16 *
0x180018690  call    ?AddXmlToDebugReport@Script@@QEAAJPEAG000@Z; Script::AddXmlToDebugReport(ushort *,ushort *,ushort *,ushort *)
0x180018695  mov     ebx, eax
0x180018697  test    eax, eax
0x180018699  jns     short loc_180018707
0x18001869b  mov     r8d, 2B2h; int
0x1800186a1  mov     r9d, eax; int
0x1800186a4  lea     rdx, aResolverAddxml; "Resolver::AddXmlToDebugReport"
0x1800186ab  mov     ecx, 1; Level
0x1800186b0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800186b5  mov     r9d, ebx
0x1800186b8  mov     r8d, 6A7h
0x1800186be  jmp     short loc_1800186F6
0x1800186c0  mov     rcx, [r10+8]; this
0x1800186c4  test    rcx, rcx
0x1800186c7  jnz     short loc_1800186DA
0x1800186c9  mov     r9d, 80004003h; unsigned __int16 *
0x1800186cf  mov     r8d, 698h; unsigned __int16 *
0x1800186d5  mov     ebx, r9d
0x1800186d8  jmp     short loc_1800186F6
0x1800186da  mov     [rsp+38h+var_18], rdx; unsigned __int16 *
0x1800186df  mov     rdx, r11; unsigned __int16 *
0x1800186e2  call    ?AddXmlToDebugReport@Troubleshooter@@QEAAJPEAG000@Z; Troubleshooter::AddXmlToDebugReport(ushort *,ushort *,ushort *,ushort *)
0x1800186e7  mov     ebx, eax
0x1800186e9  test    eax, eax
0x1800186eb  jns     short loc_180018707
0x1800186ed  mov     r9d, eax; int
0x1800186f0  mov     r8d, 69Ah; int
0x1800186f6  lea     rdx, aRootcauseAddxm_0; "Rootcause::AddXmlToDebugReport"
0x1800186fd  mov     ecx, 1; Level
0x180018702  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180018707  mov     eax, ebx
0x180018709  add     rsp, 30h
0x18001870d  pop     rbx
0x18001870e  retn
```
