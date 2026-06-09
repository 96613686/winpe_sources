# NtMapViewOfSection

- ea: `0x14005cad8`
- end: `0x14005cedf`
- name: `NtMapViewOfSection`
- size: `1031`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, volatile void *Address, __int64, int, int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140002ef0`
- `0x14000e130`
- `0x14003492c`
- `0x1400442ec`
- `0x14005cad8`
- `0x14005dd8c`
- `0x140060bd4`
- `0x14007148c`
- `0x1400fc664`
- `0x1400fc7c0`

## import_xrefs

- `skci!SkciCompareSigningLevels` at `0x14005ccc7`
- `skci!SkciCompareSigningLevels` at `0x14005cce5`
- `skci!SkciCompareSigningLevels` at `0x14005ccc7`
- `skci!SkciCompareSigningLevels` at `0x14005cce5`

## pseudocode

```c
__int64 __fastcall NtMapViewOfSection(
        unsigned __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        signed __int64 *Address,
        __int64 *a7,
        int a8,
        int a9,
        unsigned int a10)
{
  __int64 result; // rax
  char v13; // di
  __int64 ULong64FromUser; // rax
  __int64 *v15; // r12
  __int64 v16; // rax
  signed __int64 *v17; // rsi
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // r15
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r14
  __int64 (__fastcall **v24)(ULONG_PTR); // rax
  _DWORD *v25; // rbx
  _QWORD *StackBase; // rax
  __int64 v27; // r13
  unsigned int v28; // ecx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // ebx
  __int64 v33; // r9
  unsigned __int64 v34; // r8
  signed __int64 *v35; // r15
  ULONG BackTraceHash; // eax
  int v37; // r9d
  int v38; // r10d
  signed __int64 *v39; // [rsp+58h] [rbp-60h]
  signed __int64 v40; // [rsp+60h] [rbp-58h] BYREF
  int v41[2]; // [rsp+68h] [rbp-50h] BYREF
  int v42[2]; // [rsp+70h] [rbp-48h] BYREF
  _DWORD *v43; // [rsp+78h] [rbp-40h] BYREF
  unsigned __int64 v44; // [rsp+C0h] [rbp+8h] BYREF
  _DWORD *v45; // [rsp+C8h] [rbp+10h]
  _QWORD *v46; // [rsp+D0h] [rbp+18h]

  v46 = a3;
  v44 = a1;
  v43 = 0;
  v40 = 0;
  if ( a2 != -1 )
    return 3221225485LL;
  v13 = *((_BYTE *)KeGetPcr()->NtTib.StackBase + 96);
  LOBYTE(v45) = v13;
  if ( a4 )
    return 3221225714LL;
  if ( v13 )
  {
    ULong64FromUser = RtlReadULong64FromUser(a3);
    RtlWriteULong64ToUser(a3, ULong64FromUser);
    v15 = a7;
    v16 = RtlReadULong64FromUser(a7);
    RtlWriteULong64ToUser(v15, v16);
  }
  else
  {
    v15 = a7;
  }
  v17 = Address;
  if ( Address )
  {
    if ( v13 )
    {
      ProbeForWrite(Address, 8u, 4u);
      v18 = RtlReadULong64FromUser(v17);
    }
    else
    {
      v18 = *Address;
    }
    v40 = v18;
    v39 = &v40;
  }
  else
  {
    v40 = 0;
    v39 = 0;
  }
  if ( v13 )
    v19 = RtlReadULong64FromUser(a3);
  else
    v19 = *a3;
  *(_QWORD *)v42 = v19;
  if ( v13 )
    v20 = RtlReadULong64FromUser(v15);
  else
    v20 = *v15;
  *(_QWORD *)v41 = v20;
  result = SkobReferenceObjectByHandle(a1, v13, 0, 0, &v43, &v44);
  if ( (int)result >= 0 )
  {
    v23 = (__int64)v43;
    if ( !v43 )
      return 3221225508LL;
    v24 = (__int64 (__fastcall **)(ULONG_PTR))*((_QWORD *)v43 - 2);
    if ( v24 == (__int64 (__fastcall **)(ULONG_PTR))&SkmiSectionType )
    {
      v25 = 0;
      v45 = v43;
    }
    else
    {
      if ( v24 != &SkmiImageType )
      {
        v32 = -1073741788;
        goto LABEL_54;
      }
      v25 = v43;
      v45 = v43;
    }
    if ( v25 )
    {
      StackBase = KeGetPcr()->NtTib.StackBase;
      if ( StackBase )
        v27 = StackBase[10];
      else
        v27 = 0;
      v28 = v25[39];
      if ( (v28 & 2) == 0
        || (*v25 & 0x40) != 0
        || (v29 = v28 >> 5,
            LOBYTE(v29) = v29 & 0xF,
            LOBYTE(v21) = *(_BYTE *)(v27 + 280),
            !(unsigned int)SkciCompareSigningLevels(v29, v21)) )
      {
        v31 = 26;
        goto LABEL_37;
      }
      v30 = v25[39] >> 5;
      LOBYTE(v30) = v30 & 0xF;
      LOBYTE(v21) = 12;
      if ( !(unsigned int)SkciCompareSigningLevels(v30, v21)
        && (((unsigned __int8)((unsigned __int64)*(unsigned int *)(v27 + 400) >> 6)
           ^ (unsigned __int8)(v25[39] >> 4))
          & 1) != 0 )
      {
        v31 = 47;
LABEL_37:
        SKMI_BAD_IMAGE(v31, v21, v22);
        v32 = -1073740760;
        goto LABEL_54;
      }
    }
    v33 = v40 >> 12;
    v34 = (unsigned int)v45[1];
    if ( (unsigned int)(v40 >> 12) < (unsigned int)v34 )
    {
      if ( v20 + v40 <= v34 << 12 )
      {
        if ( v20 )
          v34 = (v20 + (unsigned __int64)(v40 & 0xFFF) + 4095) >> 12;
        else
          LODWORD(v34) = v34 - v33;
        v40 = (unsigned __int64)(unsigned int)v33 << 12;
        *(_QWORD *)v41 = (unsigned __int64)(unsigned int)v34 << 12;
        if ( v25 )
        {
          v35 = v39;
          if ( a5 )
          {
            v32 = -1073741581;
LABEL_55:
            LODWORD(v45) = v32;
            goto LABEL_56;
          }
          v32 = SkmiMapViewOfImage((_DWORD)v25, v44, (unsigned int)v42, (_DWORD)v39, (__int64)v41, v33, v34, a9, a10);
          LODWORD(v45) = v32;
        }
        else
        {
          BackTraceHash = SkmiMakeProtectionMask(a10);
          if ( !BackTraceHash )
          {
            v32 = -1073741755;
            goto LABEL_54;
          }
          v32 = SkmiMapViewOfSection(v38, (int)v42, (int)v41, v37, BackTraceHash);
          LODWORD(v45) = v32;
          v35 = v39;
        }
LABEL_56:
        SkobDereferenceObject(v23);
        if ( v32 >= 0 )
        {
          if ( v17 )
          {
            if ( v13 )
              RtlWriteULong64ToUser(v17, *v35);
            else
              *v17 = *v35;
          }
          if ( v13 )
            RtlWriteULong64ToUser(v15, *(_QWORD *)v41);
          else
            *v15 = *(_QWORD *)v41;
          if ( v13 )
            RtlWriteULong64ToUser(v46, *(_QWORD *)v42);
          else
            *v46 = *(_QWORD *)v42;
        }
        return (unsigned int)v32;
      }
      v32 = -1073741579;
    }
    else
    {
      v32 = -1073741580;
    }
LABEL_54:
    v35 = v39;
    goto LABEL_55;
  }
  return result;
}

```

## disassembly

```asm
0x14005cad8  mov     rax, rsp
0x14005cadb  mov     [rax+18h], r8
0x14005cadf  mov     [rax+8], rcx
0x14005cae3  push    rbx
0x14005cae4  push    rsi
0x14005cae5  push    rdi
0x14005cae6  push    r12
0x14005cae8  push    r13
0x14005caea  push    r14
0x14005caec  push    r15
0x14005caee  sub     rsp, 80h
0x14005caf5  mov     rbx, r8
0x14005caf8  mov     r14, rcx
0x14005cafb  mov     qword ptr [rax-60h], 0
0x14005cb03  mov     qword ptr [rax-40h], 0
0x14005cb0b  mov     qword ptr [rax-58h], 0
0x14005cb13  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x14005cb17  jz      short loc_14005CB23
0x14005cb19  mov     eax, 0C000000Dh
0x14005cb1e  jmp     loc_14005CECB
0x14005cb23  mov     rax, gs:8
0x14005cb2c  mov     dil, [rax+60h]
0x14005cb30  mov     byte ptr [rsp+0B8h+arg_8], dil
0x14005cb38  test    r9, r9
0x14005cb3b  jz      short loc_14005CB47
0x14005cb3d  mov     eax, 0C00000F2h
0x14005cb42  jmp     loc_14005CECB
0x14005cb47  test    dil, dil
0x14005cb4a  jz      short loc_14005CB7C
0x14005cb4c  mov     rcx, rbx
0x14005cb4f  call    RtlReadULong64FromUser
0x14005cb54  mov     rdx, rax
0x14005cb57  mov     rcx, rbx
0x14005cb5a  call    RtlWriteULong64ToUser
0x14005cb5f  mov     r12, [rsp+0B8h+arg_30]
0x14005cb67  mov     rcx, r12
0x14005cb6a  call    RtlReadULong64FromUser
0x14005cb6f  mov     rdx, rax
0x14005cb72  mov     rcx, r12
0x14005cb75  call    RtlWriteULong64ToUser
0x14005cb7a  jmp     short loc_14005CB84
0x14005cb7c  mov     r12, [rsp+0B8h+arg_30]
0x14005cb84  mov     rsi, [rsp+0B8h+Address]
0x14005cb8c  test    rsi, rsi
0x14005cb8f  jz      short loc_14005CBCA
0x14005cb91  test    dil, dil
0x14005cb94  jz      short loc_14005CBB6
0x14005cb96  mov     edx, 8; Length
0x14005cb9b  lea     r8d, [rdx-4]; Alignment
0x14005cb9f  mov     rcx, rsi; Address
0x14005cba2  call    ProbeForWrite
0x14005cba7  test    dil, dil
0x14005cbaa  jz      short loc_14005CBB6
0x14005cbac  mov     rcx, rsi
0x14005cbaf  call    RtlReadULong64FromUser
0x14005cbb4  jmp     short loc_14005CBB9
0x14005cbb6  mov     rax, [rsi]
0x14005cbb9  mov     [rsp+0B8h+var_58], rax
0x14005cbbe  lea     rax, [rsp+0B8h+var_58]
0x14005cbc3  mov     [rsp+0B8h+var_60], rax
0x14005cbc8  jmp     short loc_14005CBDC
0x14005cbca  mov     [rsp+0B8h+var_58], 0
0x14005cbd3  mov     [rsp+0B8h+var_60], 0
0x14005cbdc  test    dil, dil
0x14005cbdf  jz      short loc_14005CBEB
0x14005cbe1  mov     rcx, rbx
0x14005cbe4  call    RtlReadULong64FromUser
0x14005cbe9  jmp     short loc_14005CBEE
0x14005cbeb  mov     rax, [rbx]
0x14005cbee  mov     qword ptr [rsp+0B8h+var_48], rax
0x14005cbf3  test    dil, dil
0x14005cbf6  jz      short loc_14005CC05
0x14005cbf8  mov     rcx, r12
0x14005cbfb  call    RtlReadULong64FromUser
0x14005cc00  mov     r15, rax
0x14005cc03  jmp     short loc_14005CC09
0x14005cc05  mov     r15, [r12]
0x14005cc09  mov     qword ptr [rsp+0B8h+var_50], r15
0x14005cc0e  lea     rax, [rsp+0B8h+arg_0]
0x14005cc16  mov     [rsp+0B8h+var_90], rax
0x14005cc1b  lea     rax, [rsp+0B8h+var_40]
0x14005cc20  mov     qword ptr [rsp+0B8h+BackTraceHash], rax
0x14005cc25  xor     r9d, r9d
0x14005cc28  xor     r8d, r8d
0x14005cc2b  mov     dl, dil
0x14005cc2e  mov     rcx, r14
0x14005cc31  call    SkobReferenceObjectByHandle
0x14005cc36  test    eax, eax
0x14005cc38  js      loc_14005CECB
0x14005cc3e  mov     r14, [rsp+0B8h+var_40]
0x14005cc43  test    r14, r14
0x14005cc46  jnz     short loc_14005CC52
0x14005cc48  mov     eax, 0C0000024h
0x14005cc4d  jmp     loc_14005CECB
0x14005cc52  mov     rax, [r14-10h]
0x14005cc56  lea     rcx, SkmiSectionType
0x14005cc5d  cmp     rax, rcx
0x14005cc60  jnz     short loc_14005CC6E
0x14005cc62  xor     ebx, ebx
0x14005cc64  mov     [rsp+0B8h+arg_8], r14
0x14005cc6c  jmp     short loc_14005CC89
0x14005cc6e  lea     rcx, SkmiImageType
0x14005cc75  cmp     rax, rcx
0x14005cc78  jnz     loc_14005CE4A
0x14005cc7e  mov     rbx, r14
0x14005cc81  mov     [rsp+0B8h+arg_8], rbx
0x14005cc89  test    rbx, rbx
0x14005cc8c  jz      loc_14005CD2B
0x14005cc92  mov     rax, gs:8
0x14005cc9b  test    rax, rax
0x14005cc9e  jz      short loc_14005CCA6
0x14005cca0  mov     r13, [rax+50h]
0x14005cca4  jmp     short loc_14005CCA9
0x14005cca6  xor     r13d, r13d
0x14005cca9  mov     ecx, [rbx+9Ch]
0x14005ccaf  test    cl, 2
0x14005ccb2  jz      short loc_14005CD24
0x14005ccb4  mov     eax, [rbx]
0x14005ccb6  test    al, 40h
0x14005ccb8  jnz     short loc_14005CD24
0x14005ccba  shr     ecx, 5
0x14005ccbd  and     cl, 0Fh
0x14005ccc0  mov     dl, [r13+118h]
0x14005ccc7  call    cs:__imp_SkciCompareSigningLevels
0x14005ccce  nop     dword ptr [rax+rax+00h]
0x14005ccd3  test    eax, eax
0x14005ccd5  jz      short loc_14005CD24
0x14005ccd7  mov     ecx, [rbx+9Ch]
0x14005ccdd  shr     ecx, 5
0x14005cce0  and     cl, 0Fh
0x14005cce3  mov     dl, 0Ch
0x14005cce5  call    cs:__imp_SkciCompareSigningLevels
0x14005ccec  nop     dword ptr [rax+rax+00h]
0x14005ccf1  test    eax, eax
0x14005ccf3  jnz     short loc_14005CD2B
0x14005ccf5  mov     ecx, [rbx+9Ch]
0x14005ccfb  shr     ecx, 4
0x14005ccfe  mov     eax, [r13+190h]
0x14005cd05  shr     rax, 6
0x14005cd09  xor     ecx, eax
0x14005cd0b  test    cl, 1
0x14005cd0e  jz      short loc_14005CD2B
0x14005cd10  mov     ecx, 2Fh ; '/'
0x14005cd15  call    SKMI_BAD_IMAGE
0x14005cd1a  mov     ebx, 0C0000428h
0x14005cd1f  jmp     loc_14005CE4F
0x14005cd24  mov     ecx, 1Ah
0x14005cd29  jmp     short loc_14005CD15
0x14005cd2b  mov     rax, [rsp+0B8h+var_58]
0x14005cd30  mov     r9, rax
0x14005cd33  sar     r9, 0Ch
0x14005cd37  mov     r10, [rsp+0B8h+arg_8]
0x14005cd3f  mov     r8d, [r10+4]
0x14005cd43  cmp     r9d, r8d
0x14005cd46  jb      short loc_14005CD52
0x14005cd48  mov     ebx, 0C00000F4h
0x14005cd4d  jmp     loc_14005CE4F
0x14005cd52  mov     rdx, r8
0x14005cd55  shl     rdx, 0Ch
0x14005cd59  lea     rcx, [r15+rax]
0x14005cd5d  cmp     rcx, rdx
0x14005cd60  jbe     short loc_14005CD6C
0x14005cd62  mov     ebx, 0C00000F5h
0x14005cd67  jmp     loc_14005CE4F
0x14005cd6c  test    r15, r15
0x14005cd6f  jnz     short loc_14005CD76
0x14005cd71  sub     r8d, r9d
0x14005cd74  jmp     short loc_14005CD89
0x14005cd76  and     eax, 0FFFh
0x14005cd7b  lea     r8, [rax+0FFFh]
0x14005cd82  add     r8, r15
0x14005cd85  shr     r8, 0Ch
0x14005cd89  mov     eax, r9d
0x14005cd8c  shl     rax, 0Ch
0x14005cd90  mov     [rsp+0B8h+var_58], rax
0x14005cd95  mov     eax, r8d
0x14005cd98  shl     rax, 0Ch
0x14005cd9c  mov     qword ptr [rsp+0B8h+var_50], rax
0x14005cda1  test    rbx, rbx
0x14005cda4  jz      short loc_14005CE0D
0x14005cda6  mov     r15, [rsp+0B8h+var_60]
0x14005cdab  cmp     [rsp+0B8h+arg_20], 0
0x14005cdb4  jz      short loc_14005CDC0
0x14005cdb6  mov     ebx, 0C00000F3h
0x14005cdbb  jmp     loc_14005CE54
0x14005cdc0  mov     eax, [rsp+0B8h+arg_48]
0x14005cdc7  mov     [rsp+0B8h+var_78], eax
0x14005cdcb  mov     eax, [rsp+0B8h+arg_40]
0x14005cdd2  mov     [rsp+0B8h+var_80], eax
0x14005cdd6  mov     [rsp+0B8h+var_88], r8d
0x14005cddb  mov     dword ptr [rsp+0B8h+var_90], r9d
0x14005cde0  lea     rax, [rsp+0B8h+var_50]
0x14005cde5  mov     qword ptr [rsp+0B8h+BackTraceHash], rax
0x14005cdea  mov     r9, r15
0x14005cded  lea     r8, [rsp+0B8h+var_48]
0x14005cdf2  mov     rdx, [rsp+0B8h+arg_0]
0x14005cdfa  mov     rcx, rbx
0x14005cdfd  call    SkmiMapViewOfImage
0x14005ce02  mov     ebx, eax
0x14005ce04  mov     dword ptr [rsp+0B8h+arg_8], eax
0x14005ce0b  jmp     short loc_14005CE5B
0x14005ce0d  mov     ecx, [rsp+0B8h+arg_48]
0x14005ce14  call    SkmiMakeProtectionMask
0x14005ce19  test    eax, eax
0x14005ce1b  jnz     short loc_14005CE24
0x14005ce1d  mov     ebx, 0C0000045h
0x14005ce22  jmp     short loc_14005CE4F
0x14005ce24  mov     [rsp+0B8h+BackTraceHash], eax; BackTraceHash
0x14005ce28  lea     r8, [rsp+0B8h+var_50]; int
0x14005ce2d  lea     rdx, [rsp+0B8h+var_48]; int
0x14005ce32  mov     rcx, r10; int
0x14005ce35  call    SkmiMapViewOfSection
0x14005ce3a  mov     ebx, eax
0x14005ce3c  mov     dword ptr [rsp+0B8h+arg_8], eax
0x14005ce43  mov     r15, [rsp+0B8h+var_60]
0x14005ce48  jmp     short loc_14005CE5B
0x14005ce4a  mov     ebx, 0C0000024h
0x14005ce4f  mov     r15, [rsp+0B8h+var_60]
0x14005ce54  mov     dword ptr [rsp+0B8h+arg_8], ebx
0x14005ce5b  mov     rcx, r14
0x14005ce5e  call    SkobDereferenceObject
0x14005ce63  test    ebx, ebx
0x14005ce65  js      short loc_14005CEC7
0x14005ce67  test    rsi, rsi
0x14005ce6a  jz      short loc_14005CE84
0x14005ce6c  mov     rax, [r15]
0x14005ce6f  test    dil, dil
0x14005ce72  jz      short loc_14005CE81
0x14005ce74  mov     rdx, rax
0x14005ce77  mov     rcx, rsi
0x14005ce7a  call    RtlWriteULong64ToUser
0x14005ce7f  jmp     short loc_14005CE84
0x14005ce81  mov     [rsi], rax
0x14005ce84  mov     rax, qword ptr [rsp+0B8h+var_50]
0x14005ce89  test    dil, dil
0x14005ce8c  jz      short loc_14005CE9B
0x14005ce8e  mov     rdx, rax
0x14005ce91  mov     rcx, r12
0x14005ce94  call    RtlWriteULong64ToUser
0x14005ce99  jmp     short loc_14005CE9F
0x14005ce9b  mov     [r12], rax
0x14005ce9f  mov     rax, qword ptr [rsp+0B8h+var_48]
0x14005cea4  mov     rcx, [rsp+0B8h+arg_10]
0x14005ceac  test    dil, dil
0x14005ceaf  jz      short loc_14005CEBB
0x14005ceb1  mov     rdx, rax
0x14005ceb4  call    RtlWriteULong64ToUser
0x14005ceb9  jmp     short loc_14005CEBE
0x14005cebb  mov     [rcx], rax
0x14005cebe  jmp     short loc_14005CEC7
0x14005cec0  mov     ebx, dword ptr [rsp+0B8h+arg_8]
0x14005cec7  mov     eax, ebx
0x14005cec9  jmp     short $+2
0x14005cecb  add     rsp, 80h
0x14005ced2  pop     r15
0x14005ced4  pop     r14
0x14005ced6  pop     r13
0x14005ced8  pop     r12
0x14005ceda  pop     rdi
0x14005cedb  pop     rsi
0x14005cedc  pop     rbx
0x14005cedd  retn
0x1400fa80f  push    rbp
0x1400fa811  sub     rsp, 50h
0x1400fa815  mov     rbp, rdx
0x1400fa818  xor     eax, eax
0x1400fa81a  cmp     [rbp+0C8h], al
0x1400fa820  setnz   al
0x1400fa823  mov     [rbp+50h], eax
0x1400fa826  mov     eax, [rbp+50h]
0x1400fa829  add     rsp, 50h
0x1400fa82d  pop     rbp
0x1400fa82e  retn
```
