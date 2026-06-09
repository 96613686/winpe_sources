# MpFgCreateProtectedFoldersTable

- ea: `0x1400856dc`
- end: `0x140085b97`
- name: `MpFgCreateProtectedFoldersTable`
- size: `1211`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140075108`

## callees

- `0x1400026c0`
- `0x140004b48`
- `0x140004d24`
- `0x1400051bc`
- `0x140006ea0`
- `0x14000c604`
- `0x14000d834`
- `0x1400118d0`
- `0x1400856dc`

## import_xrefs

- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400857ce`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1400857ce`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140085b0d`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140085b0d`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400858eb`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400858eb`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140085aed`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140085b33`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140085aed`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140085b33`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008590f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085a41`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085b21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085b4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008590f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085a41`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085b21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085b4f`

## pseudocode

```c
__int64 __fastcall MpFgCreateProtectedFoldersTable(__int64 a1, struct _RTL_AVL_TABLE **a2, char *a3)
{
  unsigned int v3; // edi
  __int64 result; // rax
  unsigned int v6; // r15d
  struct _RTL_AVL_TABLE *PoolWithTag; // rax
  struct _RTL_AVL_TABLE *v8; // r14
  __int64 v9; // r13
  ULONG v10; // ecx
  const wchar_t *v11; // r13
  unsigned __int16 v12; // r15
  char IsRemoteFileName; // al
  char v14; // cl
  PVOID inserted; // rdi
  int v16; // edx
  __int64 v17; // rdx
  _QWORD *v18; // rax
  void *v19; // rbx
  char *v20; // rcx
  int TableContext; // [rsp+20h] [rbp-49h]
  NTSTATUS v22; // [rsp+30h] [rbp-39h]
  char v23; // [rsp+34h] [rbp-35h]
  unsigned int v24; // [rsp+38h] [rbp-31h]
  ULONG pulResult; // [rsp+3Ch] [rbp-2Dh] BYREF
  ULONG ulMinuend; // [rsp+40h] [rbp-29h]
  size_t pcbLength; // [rsp+48h] [rbp-21h] BYREF
  __int64 v28; // [rsp+50h] [rbp-19h]
  struct _RTL_AVL_TABLE **v29; // [rsp+58h] [rbp-11h]
  char *v30; // [rsp+60h] [rbp-9h]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-1h] BYREF
  PVOID P; // [rsp+78h] [rbp+Fh]
  unsigned __int8 NewElement[8]; // [rsp+80h] [rbp+17h] BYREF

  v3 = 0;
  v30 = a3;
  result = 0;
  *a2 = 0;
  *a3 = 0;
  v29 = a2;
  v6 = 0;
  v24 = 0;
  DestinationString = 0;
  P = 0;
  pcbLength = 0;
  v23 = 0;
  if ( *(_DWORD *)(a1 + 16) )
  {
    PoolWithTag = (struct _RTL_AVL_TABLE *)MpAllocatePoolWithTag(1, 104, 1883656269);
    v8 = PoolWithTag;
    if ( PoolWithTag )
    {
      RtlInitializeGenericTableAvl(PoolWithTag, MpFgAvlCompareRoutine, MpFgAvlAllocateRoutine, MpFgAvlFreeRoutine, 0);
      v9 = *(_QWORD *)(a1 + 24);
      v10 = *(_DWORD *)(a1 + 16);
      pulResult = v10;
      v11 = (const wchar_t *)(a1 + v9);
      while ( 1 )
      {
        ulMinuend = v10;
        if ( v6 >= *(_DWORD *)(a1 + 16) )
        {
LABEL_51:
          v20 = v30;
          *v29 = v8;
          *v20 = v23;
          return v3;
        }
        NewElement[0] = 0;
        v22 = RtlStringCbLengthW(v11, v10, &pcbLength);
        v3 = v22;
        if ( v22 < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_47;
          }
          _mm_lfence();
          v17 = 16;
LABEL_45:
          TableContext = v3;
          goto LABEL_46;
        }
        v12 = pcbLength;
        if ( pcbLength > 0xFFFF )
          break;
        v3 = 0;
        if ( !(_WORD)pcbLength )
          goto LABEL_51;
        P = 0;
        DestinationString = 0;
        *(_DWORD *)&DestinationString.Length = 1628698;
        v28 = (unsigned __int16)pcbLength;
        P = (PVOID)MpAllocatePoolWithTag(1, (unsigned __int16)pcbLength, 1732661325);
        if ( !P )
        {
          v3 = -1073741670;
          v22 = -1073741670;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            v17 = 18;
LABEL_31:
            TableContext = -1073741670;
LABEL_46:
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              v17,
              WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
              KeGetCurrentThread(),
              TableContext);
            goto LABEL_47;
          }
          goto LABEL_47;
        }
        LOWORD(DestinationString.Buffer) = 0;
        WORD1(DestinationString.Buffer) = v12;
        v22 = RtlUnicodeStringCopyString((PUNICODE_STRING)&DestinationString.Buffer, v11);
        v3 = v22;
        if ( v22 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            _mm_lfence();
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              19,
              WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
              KeGetCurrentThread(),
              v22);
          }
          ExFreePoolWithTag(P, 0x6746504Du);
          P = 0;
          goto LABEL_47;
        }
        IsRemoteFileName = MpIsRemoteFileName((PCUNICODE_STRING)&DestinationString.Buffer);
        v14 = v23;
        if ( IsRemoteFileName )
          v14 = 1;
        v23 = v14;
        if ( *((_WORD *)P + ((unsigned __int64)LOWORD(DestinationString.Buffer) >> 1) - 1) == 92 )
          LOWORD(DestinationString.Buffer) -= 2;
        inserted = RtlInsertElementGenericTableAvl(v8, &DestinationString, 0x18u, NewElement);
        if ( !inserted || !NewElement[0] )
        {
          ExFreePoolWithTag(P, 0x6746504Du);
          P = 0;
          if ( !inserted )
          {
            v3 = -1073741670;
            v22 = -1073741670;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              v17 = 20;
              goto LABEL_31;
            }
            goto LABEL_47;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_qS(
              WPP_GLOBAL_Control->AttachedDevice,
              21,
              (unsigned int)WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
              (unsigned int)KeGetCurrentThread(),
              (__int64)v11);
          }
        }
        v16 = v12;
        v11 = (const wchar_t *)((char *)v11 + v28 + 2);
        v6 = v12 + v24 + 2;
        v24 = v6;
        v22 = RtlULongSub(ulMinuend, v16 + 2, &pulResult);
        v3 = v22;
        if ( v22 < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_47;
          }
          v17 = 22;
          goto LABEL_45;
        }
        v10 = pulResult;
        v3 = 0;
      }
      v3 = -1073741675;
      v22 = -1073741675;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        v17 = 17;
        TableContext = -1073741675;
        goto LABEL_46;
      }
LABEL_47:
      v18 = RtlEnumerateGenericTableAvl(v8, 1u);
      if ( v18 )
      {
        do
        {
          v19 = (void *)v18[2];
          RtlDeleteElementGenericTableAvl(v8, v18);
          ExFreePoolWithTag(v19, 0x6746504Du);
          v18 = RtlEnumerateGenericTableAvl(v8, 1u);
        }
        while ( v18 );
        v3 = v22;
      }
      ExFreePoolWithTag(v8, 0x7046504Du);
    }
    else
    {
      v3 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          WPP_d4b33eac157739e0890aa4122bf243af_Traceguids,
          KeGetCurrentThread(),
          -1073741670);
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x1400856dc  mov     [rsp-8+arg_18], rbx
0x1400856e1  push    rbp
0x1400856e2  push    rsi
0x1400856e3  push    rdi
0x1400856e4  push    r12
0x1400856e6  push    r13
0x1400856e8  push    r14
0x1400856ea  push    r15
0x1400856ec  lea     rbp, [rsp-27h]
0x1400856f1  sub     rsp, 90h
0x1400856f8  mov     rax, cs:__security_cookie
0x1400856ff  xor     rax, rsp
0x140085702  mov     [rbp+57h+var_38], rax
0x140085706  xor     edi, edi
0x140085708  mov     [rbp+57h+var_60], r8
0x14008570c  xor     eax, eax
0x14008570e  mov     [rdx], rdi
0x140085711  mov     [r8], dil
0x140085714  xorps   xmm0, xmm0
0x140085717  mov     r12, rcx
0x14008571a  mov     [rbp+57h+var_68], rdx
0x14008571e  mov     r15d, edi
0x140085721  mov     [rbp+57h+var_88], edi
0x140085724  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140085728  mov     [rbp+57h+P], rax
0x14008572c  mov     [rbp+57h+pcbLength], rdi
0x140085730  mov     [rbp+57h+var_8C], eax
0x140085733  cmp     [rcx+10h], edi
0x140085736  jz      loc_140085B6F
0x14008573c  mov     edx, 68h ; 'h'
0x140085741  mov     r8d, 7046504Dh
0x140085747  lea     esi, [rdx-67h]
0x14008574a  mov     ecx, esi
0x14008574c  call    MpAllocatePoolWithTag
0x140085751  mov     r14, rax
0x140085754  test    rax, rax
0x140085757  jnz     short loc_1400857B1
0x140085759  mov     edi, 0C000009Ah
0x14008575e  mov     rax, cs:WPP_GLOBAL_Control
0x140085765  lea     rbx, WPP_GLOBAL_Control
0x14008576c  cmp     rax, rbx
0x14008576f  jz      loc_140085B6D
0x140085775  mov     eax, [rax+2Ch]
0x140085778  test    sil, al
0x14008577b  jz      loc_140085B6D
0x140085781  mov     r9, gs:188h
0x14008578a  lea     edx, [rsi+0Eh]
0x14008578d  mov     rcx, cs:WPP_GLOBAL_Control
0x140085794  lea     r8, WPP_d4b33eac157739e0890aa4122bf243af_Traceguids
0x14008579b  mov     [rsp+0C0h+TableContext], 0C000009Ah
0x1400857a3  mov     rcx, [rcx+18h]
0x1400857a7  call    WPP_SF_qD
0x1400857ac  jmp     loc_140085B6D
0x1400857b1  lea     r9, MpFgAvlFreeRoutine; FreeRoutine
0x1400857b8  mov     qword ptr [rsp+0C0h+TableContext], rdi; TableContext
0x1400857bd  lea     r8, MpFgAvlAllocateRoutine; AllocateRoutine
0x1400857c4  mov     rcx, r14; Table
0x1400857c7  lea     rdx, MpFgAvlCompareRoutine; CompareRoutine
0x1400857ce  call    cs:__imp_RtlInitializeGenericTableAvl
0x1400857d5  nop     dword ptr [rax+rax+00h]
0x1400857da  mov     r13, [r12+18h]
0x1400857df  lea     rbx, WPP_GLOBAL_Control
0x1400857e6  mov     ecx, [r12+10h]
0x1400857eb  lea     rsi, WPP_d4b33eac157739e0890aa4122bf243af_Traceguids
0x1400857f2  mov     [rbp+57h+pulResult], ecx
0x1400857f5  add     r13, r12
0x1400857f8  mov     [rbp+57h+ulMinuend], ecx
0x1400857fb  cmp     r15d, [r12+10h]
0x140085800  jnb     loc_140085B5D
0x140085806  mov     edx, ecx; cbMax
0x140085808  lea     r8, [rbp+57h+pcbLength]; pcbLength
0x14008580c  mov     rcx, r13; psz
0x14008580f  mov     [rbp+57h+NewElement], dil
0x140085813  call    RtlStringCbLengthW
0x140085818  mov     [rbp+57h+var_90], eax
0x14008581b  mov     edi, eax
0x14008581d  test    eax, eax
0x14008581f  js      loc_140085AAA
0x140085825  mov     r15, [rbp+57h+pcbLength]
0x140085829  cmp     r15, 0FFFFh
0x140085830  ja      loc_140085A7D
0x140085836  xor     edi, edi
0x140085838  cmp     di, r15w
0x14008583c  jz      loc_140085B5D
0x140085842  xor     eax, eax
0x140085844  lea     ecx, [rdi+1]
0x140085847  mov     [rbp+57h+P], rax
0x14008584b  xorps   xmm0, xmm0
0x14008584e  movzx   eax, r15w
0x140085852  mov     r8d, 6746504Dh
0x140085858  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14008585c  mov     edx, eax
0x14008585e  mov     dword ptr [rbp+57h+DestinationString.Length], 18DA1Ah
0x140085865  mov     [rbp+57h+var_70], rax
0x140085869  call    MpAllocatePoolWithTag
0x14008586e  mov     [rbp+57h+P], rax
0x140085872  test    rax, rax
0x140085875  jz      loc_140085A58
0x14008587b  mov     rdx, r13; pszSrc
0x14008587e  mov     word ptr [rbp+57h+DestinationString.Buffer], di
0x140085882  lea     rcx, [rbp+57h+DestinationString.Buffer]; DestinationString
0x140085886  mov     word ptr [rbp+57h+DestinationString.Buffer+2], r15w
0x14008588b  call    RtlUnicodeStringCopyString
0x140085890  mov     [rbp+57h+var_90], eax
0x140085893  mov     edi, eax
0x140085895  test    eax, eax
0x140085897  js      loc_1400859FD
0x14008589d  lea     rcx, [rbp+57h+DestinationString.Buffer]; String2
0x1400858a1  call    MpIsRemoteFileName
0x1400858a6  mov     ecx, [rbp+57h+var_8C]
0x1400858a9  test    al, al
0x1400858ab  movzx   edx, word ptr [rbp+57h+DestinationString.Buffer]
0x1400858af  mov     eax, 1
0x1400858b4  movzx   ecx, cl
0x1400858b7  cmovnz  ecx, eax
0x1400858ba  mov     rax, [rbp+57h+P]
0x1400858be  mov     [rbp+57h+var_8C], ecx
0x1400858c1  mov     ecx, edx
0x1400858c3  shr     rcx, 1
0x1400858c6  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400858cc  jnz     short loc_1400858DA
0x1400858ce  mov     eax, 0FFFEh
0x1400858d3  add     dx, ax
0x1400858d6  mov     word ptr [rbp+57h+DestinationString.Buffer], dx
0x1400858da  lea     r9, [rbp+57h+NewElement]; NewElement
0x1400858de  mov     r8d, 18h; BufferSize
0x1400858e4  lea     rdx, [rbp+57h+DestinationString]; Buffer
0x1400858e8  mov     rcx, r14; Table
0x1400858eb  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1400858f2  nop     dword ptr [rax+rax+00h]
0x1400858f7  mov     rdi, rax
0x1400858fa  xor     eax, eax
0x1400858fc  test    rdi, rdi
0x1400858ff  jz      short loc_140085906
0x140085901  cmp     [rbp+57h+NewElement], al
0x140085904  jnz     short loc_140085963
0x140085906  mov     rcx, [rbp+57h+P]; P
0x14008590a  mov     edx, 6746504Dh; Tag
0x14008590f  call    cs:__imp_ExFreePoolWithTag
0x140085916  nop     dword ptr [rax+rax+00h]
0x14008591b  xor     eax, eax
0x14008591d  mov     [rbp+57h+P], rax
0x140085921  test    rdi, rdi
0x140085924  jz      loc_1400859C8
0x14008592a  mov     rax, cs:WPP_GLOBAL_Control
0x140085931  cmp     rax, rbx
0x140085934  jz      short loc_140085963
0x140085936  mov     eax, [rax+2Ch]
0x140085939  test    al, 4
0x14008593b  jz      short loc_140085963
0x14008593d  mov     r9, gs:188h
0x140085946  mov     edx, 15h
0x14008594b  mov     rcx, cs:WPP_GLOBAL_Control
0x140085952  mov     r8, rsi
0x140085955  mov     qword ptr [rsp+0C0h+TableContext], r13
0x14008595a  mov     rcx, [rcx+18h]
0x14008595e  call    WPP_SF_qS
0x140085963  mov     rax, [rbp+57h+var_70]
0x140085967  lea     r8, [rbp+57h+pulResult]; pulResult
0x14008596b  mov     ecx, [rbp+57h+ulMinuend]; ulMinuend
0x14008596e  add     rax, 2
0x140085972  movzx   edx, r15w
0x140085976  add     r13, rax
0x140085979  mov     r15d, [rbp+57h+var_88]
0x14008597d  add     r15d, 2
0x140085981  add     r15d, edx
0x140085984  add     edx, 2; ulSubtrahend
0x140085987  mov     [rbp+57h+var_88], r15d
0x14008598b  call    RtlULongSub
0x140085990  mov     [rbp+57h+var_90], eax
0x140085993  mov     edi, eax
0x140085995  test    eax, eax
0x140085997  js      short loc_1400859A3
0x140085999  mov     ecx, [rbp+57h+pulResult]
0x14008599c  xor     edi, edi
0x14008599e  jmp     loc_1400857F8
0x1400859a3  mov     rax, cs:WPP_GLOBAL_Control
0x1400859aa  cmp     rax, rbx
0x1400859ad  jz      loc_140085AE5
0x1400859b3  mov     eax, [rax+2Ch]
0x1400859b6  test    al, 1
0x1400859b8  jz      loc_140085AE5
0x1400859be  mov     edx, 16h
0x1400859c3  jmp     loc_140085AC5
0x1400859c8  mov     edi, 0C000009Ah
0x1400859cd  mov     [rbp+57h+var_90], edi
0x1400859d0  mov     rax, cs:WPP_GLOBAL_Control
0x1400859d7  cmp     rax, rbx
0x1400859da  jz      loc_140085AE5
0x1400859e0  mov     eax, [rax+2Ch]
0x1400859e3  test    al, 1
0x1400859e5  jz      loc_140085AE5
0x1400859eb  mov     edx, 14h
0x1400859f0  mov     [rsp+0C0h+TableContext], 0C000009Ah
0x1400859f8  jmp     loc_140085AC9
0x1400859fd  mov     rax, cs:WPP_GLOBAL_Control
0x140085a04  cmp     rax, rbx
0x140085a07  jz      short loc_140085A38
0x140085a09  mov     eax, [rax+2Ch]
0x140085a0c  test    al, 1
0x140085a0e  jz      short loc_140085A38
0x140085a10  lfence
0x140085a13  mov     r9, gs:188h
0x140085a1c  mov     edx, 13h
0x140085a21  mov     rcx, cs:WPP_GLOBAL_Control
0x140085a28  mov     r8, rsi
0x140085a2b  mov     [rsp+0C0h+TableContext], edi
0x140085a2f  mov     rcx, [rcx+18h]
0x140085a33  call    WPP_SF_qD
0x140085a38  mov     rcx, [rbp+57h+P]; P
0x140085a3c  mov     edx, 6746504Dh; Tag
0x140085a41  call    cs:__imp_ExFreePoolWithTag
0x140085a48  nop     dword ptr [rax+rax+00h]
0x140085a4d  xor     eax, eax
0x140085a4f  mov     [rbp+57h+P], rax
0x140085a53  jmp     loc_140085AE5
0x140085a58  mov     edi, 0C000009Ah
0x140085a5d  mov     [rbp+57h+var_90], edi
0x140085a60  mov     rax, cs:WPP_GLOBAL_Control
0x140085a67  cmp     rax, rbx
0x140085a6a  jz      short loc_140085AE5
0x140085a6c  mov     eax, [rax+2Ch]
0x140085a6f  test    al, 1
0x140085a71  jz      short loc_140085AE5
0x140085a73  mov     edx, 12h
0x140085a78  jmp     loc_1400859F0
0x140085a7d  mov     edi, 0C0000095h
0x140085a82  mov     [rbp+57h+var_90], edi
0x140085a85  mov     rax, cs:WPP_GLOBAL_Control
0x140085a8c  cmp     rax, rbx
0x140085a8f  jz      short loc_140085AE5
0x140085a91  mov     eax, [rax+2Ch]
0x140085a94  test    al, 1
0x140085a96  jz      short loc_140085AE5
0x140085a98  lfence
0x140085a9b  mov     edx, 11h
0x140085aa0  mov     [rsp+0C0h+TableContext], 0C0000095h
0x140085aa8  jmp     short loc_140085AC9
0x140085aaa  mov     rax, cs:WPP_GLOBAL_Control
0x140085ab1  cmp     rax, rbx
0x140085ab4  jz      short loc_140085AE5
0x140085ab6  mov     eax, [rax+2Ch]
0x140085ab9  test    al, 1
0x140085abb  jz      short loc_140085AE5
0x140085abd  lfence
0x140085ac0  mov     edx, 10h
0x140085ac5  mov     [rsp+0C0h+TableContext], edi
0x140085ac9  mov     r9, gs:188h
0x140085ad2  mov     r8, rsi
0x140085ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x140085adc  mov     rcx, [rcx+18h]
0x140085ae0  call    WPP_SF_qD
0x140085ae5  mov     edx, 1; Restart
0x140085aea  mov     rcx, r14; Table
0x140085aed  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140085af4  nop     dword ptr [rax+rax+00h]
0x140085af9  test    rax, rax
0x140085afc  jz      short loc_140085B47
0x140085afe  mov     edi, 1
0x140085b03  mov     rbx, [rax+10h]
0x140085b07  mov     rdx, rax; Buffer
0x140085b0a  mov     rcx, r14; Table
0x140085b0d  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140085b14  nop     dword ptr [rax+rax+00h]
0x140085b19  mov     edx, 6746504Dh; Tag
0x140085b1e  mov     rcx, rbx; P
0x140085b21  call    cs:__imp_ExFreePoolWithTag
0x140085b28  nop     dword ptr [rax+rax+00h]
0x140085b2d  mov     dl, dil; Restart
0x140085b30  mov     rcx, r14; Table
0x140085b33  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140085b3a  nop     dword ptr [rax+rax+00h]
0x140085b3f  test    rax, rax
0x140085b42  jnz     short loc_140085B03
0x140085b44  mov     edi, [rbp+57h+var_90]
0x140085b47  mov     edx, 7046504Dh; Tag
0x140085b4c  mov     rcx, r14; P
0x140085b4f  call    cs:__imp_ExFreePoolWithTag
0x140085b56  nop     dword ptr [rax+rax+00h]
0x140085b5b  jmp     short loc_140085B6D
0x140085b5d  mov     rax, [rbp+57h+var_68]
0x140085b61  mov     rcx, [rbp+57h+var_60]
0x140085b65  mov     [rax], r14
0x140085b68  mov     eax, [rbp+57h+var_8C]
0x140085b6b  mov     [rcx], al
0x140085b6d  mov     eax, edi
0x140085b6f  mov     rcx, [rbp+57h+var_38]
0x140085b73  xor     rcx, rsp; StackCookie
0x140085b76  call    __security_check_cookie
0x140085b7b  mov     rbx, [rsp+0C0h+arg_18]
0x140085b83  add     rsp, 90h
0x140085b8a  pop     r15
0x140085b8c  pop     r14
0x140085b8e  pop     r13
0x140085b90  pop     r12
0x140085b92  pop     rdi
0x140085b93  pop     rsi
0x140085b94  pop     rbp
0x140085b95  retn
```
