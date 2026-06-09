# CPhoneActivationBook::SetupReadPhoneList(ushort const *,CArray<SLUX_PhoneLocation,SLUX_PhoneLocation,CAdaptorDefault,CPoliciesDefault> *)

- ea: `0x180020620`
- end: `0x1800207df`
- name: `?SetupReadPhoneList@CPhoneActivationBook@@AEAAJPEBGPEAV?$CArray@USLUX_PhoneLocation@@U1@VCAdaptorDefault@@VCPoliciesDefault@@@@@Z`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001f8cc`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001d860`
- `0x18001e840`
- `0x18001e9c4`
- `0x180020620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002077b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002077b`
- `SETUPAPI!SetupCloseInfFile` at `0x1800207c3`
- `SETUPAPI!SetupCloseInfFile` at `0x1800207c3`
- `SETUPAPI!SetupGetLineCountW` at `0x180020677`
- `SETUPAPI!SetupGetLineCountW` at `0x180020677`
- `SETUPAPI!SetupOpenInfFileW` at `0x18002064f`
- `SETUPAPI!SetupOpenInfFileW` at `0x18002064f`
- `SETUPAPI!SetupGetLineByIndexW` at `0x1800206cc`
- `SETUPAPI!SetupGetLineByIndexW` at `0x1800206cc`

## pseudocode

```c
__int64 __fastcall CPhoneActivationBook::SetupReadPhoneList(__int64 a1, const WCHAR *a2, __int64 a3)
{
  char *v4; // rax
  char *v5; // rbx
  unsigned int LineCountW; // eax
  unsigned int v7; // esi
  DWORD v8; // r14d
  void *v9; // rcx
  CPhoneActivationBook *v10; // rcx
  int v11; // eax
  CPhoneActivationBook *v12; // rcx
  unsigned int v13; // edi
  CPhoneActivationBook *v14; // rcx
  CPhoneActivationBook *v15; // rcx
  CPhoneActivationBook *v16; // rcx
  __int64 v17; // rcx
  signed int LastError; // eax
  struct _INFCONTEXT Context; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int16 *v21[2]; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int16 *v22[2]; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int16 *v23; // [rsp+58h] [rbp-10h] BYREF

  memset(&Context, 0, sizeof(Context));
  v4 = (char *)SetupOpenInfFileW(a2, 0, 2u, 0);
  v5 = v4;
  if ( v4 == (char *)-1LL || (LineCountW = SetupGetLineCountW(v4, L"IsoCodes"), (v7 = LineCountW) == 0) )
  {
    v17 = 2147500037LL;
    v13 = -2147467259;
  }
  else
  {
    CArray<SLUX_PhoneLocation,SLUX_PhoneLocation,CAdaptorDefault,CPoliciesDefault>::SetSize(a3, LineCountW);
    v8 = 0;
    while ( 1 )
    {
      v9 = 0;
      v23 = 0;
      *(_OWORD *)v21 = 0;
      if ( v5 )
        v9 = v5;
      *(_OWORD *)v22 = 0;
      if ( !SetupGetLineByIndexW(v9, L"IsoCodes", v8, &Context) )
        break;
      v11 = CPhoneActivationBook::AddItemToPhoneEntry(v10, &Context, 1u, &v23);
      v13 = v11;
      if ( v11 < 0 )
        goto LABEL_14;
      v11 = CPhoneActivationBook::AddItemToPhoneEntry(v12, &Context, 4u, v21);
      v13 = v11;
      if ( v11 < 0
        || (v11 = CPhoneActivationBook::AddItemToPhoneEntry(v14, &Context, 5u, v22), v13 = v11, v11 < 0)
        || (v11 = CPhoneActivationBook::AddItemToPhoneEntry(v15, &Context, 6u, &v21[1]), v13 = v11, v11 < 0)
        || (v11 = CPhoneActivationBook::AddItemToPhoneEntry(v16, &Context, 7u, &v22[1]), v13 = v11, v11 < 0) )
      {
LABEL_14:
        v17 = (unsigned int)v11;
        goto LABEL_21;
      }
      CArray<SLUX_PhoneLocation,SLUX_PhoneLocation,CAdaptorDefault,CPoliciesDefault>::Append(a3, v21);
      if ( ++v8 >= v7 )
        goto LABEL_22;
    }
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v13 = -2147467259;
    }
    v17 = v13;
  }
LABEL_21:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
LABEL_22:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    SetupCloseInfFile(v5);
  return v13;
}

```

## disassembly

```asm
0x180020620  push    rbp
0x180020622  push    rbx
0x180020623  push    rsi
0x180020624  push    rdi
0x180020625  push    r14
0x180020627  push    r15
0x180020629  mov     rbp, rsp
0x18002062c  sub     rsp, 68h
0x180020630  xor     ecx, ecx
0x180020632  mov     rax, rdx
0x180020635  mov     r15, r8
0x180020638  mov     qword ptr [rbp+Context.Section], rcx
0x18002063c  xorps   xmm0, xmm0
0x18002063f  xor     r9d, r9d; ErrorLine
0x180020642  xor     edx, edx; InfClass
0x180020644  lea     r8d, [rcx+2]; InfStyle
0x180020648  mov     rcx, rax; FileName
0x18002064b  movups  xmmword ptr [rbp+Context.Inf], xmm0
0x18002064f  call    cs:__imp_SetupOpenInfFileW
0x180020656  nop     dword ptr [rax+rax+00h]
0x18002065b  mov     rbx, rax
0x18002065e  test    rax, rax
0x180020661  jz      short loc_18002066D
0x180020663  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020667  jz      loc_1800207A3
0x18002066d  lea     rdx, aIsocodes; "IsoCodes"
0x180020674  mov     rcx, rbx; InfHandle
0x180020677  call    cs:__imp_SetupGetLineCountW
0x18002067e  nop     dword ptr [rax+rax+00h]
0x180020683  mov     esi, eax
0x180020685  test    eax, eax
0x180020687  jz      loc_1800207A3
0x18002068d  mov     edx, eax
0x18002068f  mov     rcx, r15
0x180020692  xor     edi, edi
0x180020694  call    ?SetSize@?$CArray@USLUX_PhoneLocation@@U1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<SLUX_PhoneLocation,SLUX_PhoneLocation,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x180020699  xor     r14d, r14d
0x18002069c  test    esi, esi
0x18002069e  jz      loc_1800207AF
0x1800206a4  xor     eax, eax
0x1800206a6  lea     r9, [rbp+Context]; Context
0x1800206aa  xor     ecx, ecx
0x1800206ac  mov     [rbp+var_10], rax
0x1800206b0  xorps   xmm0, xmm0
0x1800206b3  lea     rdx, aIsocodes; "IsoCodes"
0x1800206ba  test    rbx, rbx
0x1800206bd  mov     r8d, r14d; Index
0x1800206c0  movups  xmmword ptr [rbp+var_30], xmm0
0x1800206c4  cmovnz  rcx, rbx; InfHandle
0x1800206c8  movups  xmmword ptr [rbp+var_20], xmm0
0x1800206cc  call    cs:__imp_SetupGetLineByIndexW
0x1800206d3  nop     dword ptr [rax+rax+00h]
0x1800206d8  test    eax, eax
0x1800206da  jz      loc_18002077B
0x1800206e0  lea     r9, [rbp+var_10]; unsigned __int16 **
0x1800206e4  mov     r8d, 1; unsigned int
0x1800206ea  lea     rdx, [rbp+Context]; struct _INFCONTEXT *
0x1800206ee  call    ?AddItemToPhoneEntry@CPhoneActivationBook@@AEAAJPEAU_INFCONTEXT@@KPEAPEAG@Z; CPhoneActivationBook::AddItemToPhoneEntry(_INFCONTEXT *,ulong,ushort * *)
0x1800206f3  mov     edi, eax
0x1800206f5  test    eax, eax
0x1800206f7  js      short loc_180020777
0x1800206f9  lea     r9, [rbp+var_30]; unsigned __int16 **
0x1800206fd  mov     r8d, 4; unsigned int
0x180020703  lea     rdx, [rbp+Context]; struct _INFCONTEXT *
0x180020707  call    ?AddItemToPhoneEntry@CPhoneActivationBook@@AEAAJPEAU_INFCONTEXT@@KPEAPEAG@Z; CPhoneActivationBook::AddItemToPhoneEntry(_INFCONTEXT *,ulong,ushort * *)
0x18002070c  mov     edi, eax
0x18002070e  test    eax, eax
0x180020710  js      short loc_180020777
0x180020712  lea     r9, [rbp+var_20]; unsigned __int16 **
0x180020716  mov     r8d, 5; unsigned int
0x18002071c  lea     rdx, [rbp+Context]; struct _INFCONTEXT *
0x180020720  call    ?AddItemToPhoneEntry@CPhoneActivationBook@@AEAAJPEAU_INFCONTEXT@@KPEAPEAG@Z; CPhoneActivationBook::AddItemToPhoneEntry(_INFCONTEXT *,ulong,ushort * *)
0x180020725  mov     edi, eax
0x180020727  test    eax, eax
0x180020729  js      short loc_180020777
0x18002072b  lea     r9, [rbp+var_30+8]; unsigned __int16 **
0x18002072f  mov     r8d, 6; unsigned int
0x180020735  lea     rdx, [rbp+Context]; struct _INFCONTEXT *
0x180020739  call    ?AddItemToPhoneEntry@CPhoneActivationBook@@AEAAJPEAU_INFCONTEXT@@KPEAPEAG@Z; CPhoneActivationBook::AddItemToPhoneEntry(_INFCONTEXT *,ulong,ushort * *)
0x18002073e  mov     edi, eax
0x180020740  test    eax, eax
0x180020742  js      short loc_180020777
0x180020744  lea     r9, [rbp+var_20+8]; unsigned __int16 **
0x180020748  mov     r8d, 7; unsigned int
0x18002074e  lea     rdx, [rbp+Context]; struct _INFCONTEXT *
0x180020752  call    ?AddItemToPhoneEntry@CPhoneActivationBook@@AEAAJPEAU_INFCONTEXT@@KPEAPEAG@Z; CPhoneActivationBook::AddItemToPhoneEntry(_INFCONTEXT *,ulong,ushort * *)
0x180020757  mov     edi, eax
0x180020759  test    eax, eax
0x18002075b  js      short loc_180020777
0x18002075d  lea     rdx, [rbp+var_30]
0x180020761  mov     rcx, r15
0x180020764  call    ?Append@?$CArray@USLUX_PhoneLocation@@U1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBUSLUX_PhoneLocation@@@Z; CArray<SLUX_PhoneLocation,SLUX_PhoneLocation,CAdaptorDefault,CPoliciesDefault>::Append(SLUX_PhoneLocation const &)
0x180020769  inc     r14d
0x18002076c  cmp     r14d, esi
0x18002076f  jb      loc_1800206A4
0x180020775  jmp     short loc_1800207AF
0x180020777  mov     ecx, eax
0x180020779  jmp     short loc_1800207AA
0x18002077b  call    cs:__imp_GetLastError
0x180020782  nop     dword ptr [rax+rax+00h]
0x180020787  mov     edi, eax
0x180020789  test    eax, eax
0x18002078b  jnz     short loc_180020794
0x18002078d  mov     edi, 80004005h
0x180020792  jmp     short loc_18002079F
0x180020794  jle     short loc_18002079F
0x180020796  movzx   edi, ax
0x180020799  or      edi, 80070000h
0x18002079f  mov     ecx, edi
0x1800207a1  jmp     short loc_1800207AA
0x1800207a3  mov     ecx, 80004005h
0x1800207a8  mov     edi, ecx
0x1800207aa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800207af  mov     ecx, edi
0x1800207b1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800207b6  lea     rax, [rbx-1]
0x1800207ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800207be  ja      short loc_1800207CF
0x1800207c0  mov     rcx, rbx; InfHandle
0x1800207c3  call    cs:__imp_SetupCloseInfFile
0x1800207ca  nop     dword ptr [rax+rax+00h]
0x1800207cf  mov     eax, edi
0x1800207d1  add     rsp, 68h
0x1800207d5  pop     r15
0x1800207d7  pop     r14
0x1800207d9  pop     rdi
0x1800207da  pop     rsi
0x1800207db  pop     rbx
0x1800207dc  pop     rbp
0x1800207dd  retn
```
