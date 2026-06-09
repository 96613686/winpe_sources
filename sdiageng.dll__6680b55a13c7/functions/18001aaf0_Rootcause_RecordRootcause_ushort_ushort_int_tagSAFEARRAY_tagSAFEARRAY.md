# Rootcause::RecordRootcause(ushort *,ushort *,int,tagSAFEARRAY *,tagSAFEARRAY *)

- ea: `0x18001aaf0`
- end: `0x18001acf7`
- name: `?RecordRootcause@Rootcause@@QEAAJPEAG0HPEAUtagSAFEARRAY@@1@Z`
- size: `519`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY **this, unsigned __int16 *, unsigned __int16 *, int, struct tagSAFEARRAY *psa, struct tagSAFEARRAY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800171fc`

## callees

- `0x180019b88`
- `0x180019f40`
- `0x18001aaf0`
- `0x180026fa0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001ab93`
- `msvcrt!_wcsicmp` at `0x18001abd7`
- `msvcrt!_wcsicmp` at `0x18001ab93`
- `msvcrt!_wcsicmp` at `0x18001abd7`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001ac49`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001ac6d`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001ac49`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001ac6d`

## pseudocode

```c
__int64 __fastcall Rootcause::RecordRootcause(
        struct _LIST_ENTRY **this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        struct tagSAFEARRAY *psa,
        struct tagSAFEARRAY *a6)
{
  int v10; // r9d
  int v11; // r8d
  unsigned int v12; // ebx
  int Blink; // r15d
  int Instance; // eax
  const wchar_t *v15; // rdx
  int v16; // ebx
  unsigned int v17; // r9d
  SAFEARRAY **v18; // rdx
  SAFEARRAY **v19; // rdi
  SAFEARRAY *v20; // rcx
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v22; // [rsp+88h] [rbp+10h] BYREF

  v22 = 0;
  if ( !a2 )
  {
    v10 = -2147024809;
    v11 = 383;
    v12 = -2147024809;
LABEL_32:
    SdpDebugTrace(1u, L"Rootcause::RecordRootcause", v11, v10);
    return v12;
  }
  if ( !a3 )
  {
    v10 = -2147024809;
    v11 = 384;
    v12 = -2147024809;
    goto LABEL_32;
  }
  if ( !*this )
  {
    v12 = -2147467261;
    v11 = 386;
    v10 = -2147467261;
    goto LABEL_32;
  }
  Blink = (int)(*this)[5].Blink;
  Instance = Rootcause::GetInstance((Rootcause *)this, this[15], a3, &v22);
  v12 = Instance;
  if ( Instance < 0 )
  {
    v11 = 394;
LABEL_31:
    v10 = Instance;
    goto LABEL_32;
  }
  v15 = (const wchar_t *)this[5];
  if ( Blink == 3 )
  {
    v16 = (int)(*this)[3].Blink;
    if ( _wcsicmp(a2, v15) )
    {
      if ( (v16 & 1) == 0 )
      {
        v10 = -2147024809;
        v11 = 435;
        v12 = -2147024809;
        goto LABEL_32;
      }
      return 1;
    }
    else
    {
      v17 = (a4 != 0) + 1;
      if ( v22 )
      {
        if ( *((_DWORD *)v22 + 6)
          || (v18 = (SAFEARRAY **)((char *)v22 + 32), *((_QWORD *)v22 + 4))
          || (v19 = (SAFEARRAY **)((char *)v22 + 40), *((_QWORD *)v22 + 5)) )
        {
          v10 = -2147024809;
          v11 = 454;
          v12 = -2147024809;
          goto LABEL_32;
        }
        v20 = psa;
        v12 = 0;
        *((_DWORD *)v22 + 6) = v17;
        if ( v20 )
        {
          Instance = SafeArrayCopy(v20, v18);
          v12 = Instance;
          if ( Instance < 0 )
          {
            v11 = 465;
            goto LABEL_31;
          }
        }
        if ( a6 )
        {
          Instance = SafeArrayCopy(a6, v19);
          v12 = Instance;
          if ( Instance < 0 )
          {
            v11 = 470;
            goto LABEL_31;
          }
        }
      }
      else
      {
        Instance = Rootcause::CreateInstance(
                     (__int64)this,
                     (struct IXMLDOMDocument2 *)this[15],
                     (__int64)a3,
                     v17,
                     (__int64)psa,
                     (__int64)a6,
                     (struct IXMLDOMDocument2 ***)&v22);
        v12 = Instance;
        if ( Instance < 0 )
        {
          v11 = 483;
          goto LABEL_31;
        }
      }
    }
  }
  else
  {
    if ( _wcsicmp(a2, v15) )
    {
      v10 = -2147024809;
      v11 = 403;
      v12 = -2147024809;
      goto LABEL_32;
    }
    if ( v22 )
      *((_DWORD *)v22 + 6) = 4 - (a4 != 0);
  }
  return v12;
}

```

## disassembly

```asm
0x18001aaf0  mov     rax, rsp
0x18001aaf3  push    rbx
0x18001aaf4  push    rbp
0x18001aaf5  push    rsi
0x18001aaf6  push    rdi
0x18001aaf7  push    r14
0x18001aaf9  push    r15
0x18001aafb  sub     rsp, 48h
0x18001aaff  mov     qword ptr [rax+10h], 0
0x18001ab07  mov     esi, r9d
0x18001ab0a  mov     r14, r8
0x18001ab0d  mov     rbp, rdx
0x18001ab10  mov     rdi, rcx
0x18001ab13  test    rdx, rdx
0x18001ab16  jnz     short loc_18001AB2C
0x18001ab18  mov     r9d, 80070057h
0x18001ab1e  mov     r8d, 17Fh
0x18001ab24  mov     ebx, r9d
0x18001ab27  jmp     loc_18001ACD7
0x18001ab2c  test    r14, r14
0x18001ab2f  jnz     short loc_18001AB45
0x18001ab31  mov     r9d, 80070057h
0x18001ab37  mov     r8d, 180h
0x18001ab3d  mov     ebx, r9d
0x18001ab40  jmp     loc_18001ACD7
0x18001ab45  mov     rax, [rcx]
0x18001ab48  test    rax, rax
0x18001ab4b  jnz     short loc_18001AB60
0x18001ab4d  mov     ebx, 80004003h
0x18001ab52  mov     r8d, 182h; String1
0x18001ab58  mov     r9d, ebx
0x18001ab5b  jmp     loc_18001ACD7
0x18001ab60  mov     r15d, [rax+58h]
0x18001ab64  mov     rdx, [rcx+78h]; struct _LIST_ENTRY *
0x18001ab68  lea     r9, [rsp+78h+arg_8]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x18001ab70  call    ?GetInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEBGPEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetInstance(_LIST_ENTRY *,ushort const *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001ab75  mov     ebx, eax
0x18001ab77  test    eax, eax
0x18001ab79  jns     short loc_18001AB86
0x18001ab7b  mov     r8d, 18Ah
0x18001ab81  jmp     loc_18001ACD4
0x18001ab86  mov     rdx, [rdi+28h]; String2
0x18001ab8a  mov     rcx, rbp; String1
0x18001ab8d  cmp     r15d, 3
0x18001ab91  jz      short loc_18001ABD1
0x18001ab93  call    cs:__imp__wcsicmp
0x18001ab99  test    eax, eax
0x18001ab9b  jz      short loc_18001ABB1
0x18001ab9d  mov     r9d, 80070057h
0x18001aba3  mov     r8d, 193h
0x18001aba9  mov     ebx, r9d
0x18001abac  jmp     loc_18001ACD7
0x18001abb1  mov     rcx, [rsp+78h+arg_8]
0x18001abb9  test    rcx, rcx
0x18001abbc  jz      loc_18001ACE8
0x18001abc2  neg     esi
0x18001abc4  sbb     eax, eax
0x18001abc6  add     eax, 4
0x18001abc9  mov     [rcx+18h], eax
0x18001abcc  jmp     loc_18001ACE8
0x18001abd1  mov     rax, [rdi]
0x18001abd4  mov     ebx, [rax+38h]
0x18001abd7  call    cs:__imp__wcsicmp
0x18001abdd  test    eax, eax
0x18001abdf  jz      short loc_18001AC04
0x18001abe1  test    bl, 1
0x18001abe4  jz      short loc_18001ABF0
0x18001abe6  mov     ebx, 1
0x18001abeb  jmp     loc_18001ACE8
0x18001abf0  mov     r9d, 80070057h
0x18001abf6  mov     r8d, 1B3h
0x18001abfc  mov     ebx, r9d
0x18001abff  jmp     loc_18001ACD7
0x18001ac04  mov     rax, [rsp+78h+arg_8]
0x18001ac0c  neg     esi
0x18001ac0e  sbb     r9d, r9d
0x18001ac11  neg     r9d
0x18001ac14  inc     r9d
0x18001ac17  test    rax, rax
0x18001ac1a  jz      short loc_18001AC92
0x18001ac1c  cmp     dword ptr [rax+18h], 0
0x18001ac20  jnz     short loc_18001AC81
0x18001ac22  lea     rdx, [rax+20h]; ppsaOut
0x18001ac26  cmp     qword ptr [rdx], 0
0x18001ac2a  jnz     short loc_18001AC81
0x18001ac2c  lea     rdi, [rax+28h]
0x18001ac30  cmp     qword ptr [rdi], 0
0x18001ac34  jnz     short loc_18001AC81
0x18001ac36  mov     rcx, [rsp+78h+psa]; psa
0x18001ac3e  xor     ebx, ebx
0x18001ac40  mov     [rax+18h], r9d
0x18001ac44  test    rcx, rcx
0x18001ac47  jz      short loc_18001AC5D
0x18001ac49  call    cs:__imp_SafeArrayCopy
0x18001ac4f  mov     ebx, eax
0x18001ac51  test    eax, eax
0x18001ac53  jns     short loc_18001AC5D
0x18001ac55  mov     r8d, 1D1h
0x18001ac5b  jmp     short loc_18001ACD4
0x18001ac5d  mov     rcx, [rsp+78h+arg_28]; psa
0x18001ac65  test    rcx, rcx
0x18001ac68  jz      short loc_18001ACE8
0x18001ac6a  mov     rdx, rdi; ppsaOut
0x18001ac6d  call    cs:__imp_SafeArrayCopy
0x18001ac73  mov     ebx, eax
0x18001ac75  test    eax, eax
0x18001ac77  jns     short loc_18001ACE8
0x18001ac79  mov     r8d, 1D6h
0x18001ac7f  jmp     short loc_18001ACD4
0x18001ac81  mov     r9d, 80070057h
0x18001ac87  mov     r8d, 1C6h
0x18001ac8d  mov     ebx, r9d
0x18001ac90  jmp     short loc_18001ACD7
0x18001ac92  mov     rdx, [rdi+78h]
0x18001ac96  lea     rax, [rsp+78h+arg_8]
0x18001ac9e  mov     [rsp+78h+var_48], rax
0x18001aca3  mov     r8, r14
0x18001aca6  mov     rax, [rsp+78h+arg_28]
0x18001acae  mov     rcx, rdi
0x18001acb1  mov     [rsp+78h+var_50], rax
0x18001acb6  mov     rax, [rsp+78h+psa]
0x18001acbe  mov     [rsp+78h+var_58], rax
0x18001acc3  call    ?CreateInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEBGW4SDIAG_ROOTCAUSE_STATUS@1@PEAUtagSAFEARRAY@@3PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::CreateInstance(_LIST_ENTRY *,ushort const *,Rootcause::SDIAG_ROOTCAUSE_STATUS,tagSAFEARRAY *,tagSAFEARRAY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001acc8  mov     ebx, eax
0x18001acca  test    eax, eax
0x18001accc  jns     short loc_18001ACE8
0x18001acce  mov     r8d, 1E3h; int
0x18001acd4  mov     r9d, eax; int
0x18001acd7  lea     rdx, aRootcauseRecor; "Rootcause::RecordRootcause"
0x18001acde  mov     ecx, 1; Level
0x18001ace3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001ace8  mov     eax, ebx
0x18001acea  add     rsp, 48h
0x18001acee  pop     r15
0x18001acf0  pop     r14
0x18001acf2  pop     rdi
0x18001acf3  pop     rsi
0x18001acf4  pop     rbp
0x18001acf5  pop     rbx
0x18001acf6  retn
```
