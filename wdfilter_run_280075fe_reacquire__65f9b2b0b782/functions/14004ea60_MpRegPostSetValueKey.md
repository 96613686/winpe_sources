# MpRegPostSetValueKey

- ea: `0x14004ea60`
- end: `0x14004ef26`
- name: `MpRegPostSetValueKey`
- size: `1222`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004d0d0`

## callees

- `0x1400034e0`
- `0x1400049dc`
- `0x1400051bc`
- `0x140006afc`
- `0x14000a760`
- `0x140011890`
- `0x140011bc0`
- `0x14003be04`
- `0x14004ea60`
- `0x14004f660`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14004ebea`
- `ntoskrnl!RtlCompareMemory` at `0x14004ebea`
- `ntoskrnl!ExQueryDepthSList` at `0x14004eaa7`
- `ntoskrnl!ExQueryDepthSList` at `0x14004eaa7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14004eac6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14004eac6`

## pseudocode

```c
__int64 __fastcall MpRegPostSetValueKey(__int64 a1, unsigned __int16 *a2)
{
  int v4; // r14d
  struct _SLIST_ENTRY *v5; // rsi
  PVOID v6; // r15
  USHORT v7; // di
  int v9; // ecx
  __int64 v10; // r14
  struct _SLIST_ENTRY *v11; // rax
  __int64 v12; // r15
  SIZE_T v13; // r8
  unsigned int v14; // r9d
  __int64 v15; // rax
  const void *v16; // rdx
  unsigned int v17; // eax
  const void *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-48h]

  v4 = 0;
  v5 = 0;
  if ( !a1 )
  {
    v4 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_4;
    v20 = 68;
    v21 = -1073741811;
LABEL_30:
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v20,
      WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
      KeGetCurrentThread(),
      v21);
    goto LABEL_4;
  }
  if ( *(int *)(a1 + 8) < 0 || !a2 )
    goto LABEL_4;
  v9 = *a2;
  if ( (_WORD)v9 != 0xDA0C )
  {
    v4 = -1073741788;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        69,
        WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
        KeGetCurrentThread(),
        v9,
        -1073741788);
    goto LABEL_4;
  }
  if ( !*((_QWORD *)a2 + 8) )
  {
    v4 = -1073741823;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        70,
        WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
        KeGetCurrentThread(),
        -1073741823);
    goto LABEL_4;
  }
  if ( !*((_QWORD *)a2 + 5) )
  {
    v4 = -1073741823;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_4;
    v20 = 71;
    v21 = -1073741823;
    goto LABEL_30;
  }
  v10 = *(_QWORD *)(a1 + 16);
  if ( !v10 )
  {
    v4 = -1073741823;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_4;
    v20 = 72;
    v21 = -1073741823;
    goto LABEL_30;
  }
  v11 = (struct _SLIST_ENTRY *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64));
  v12 = (__int64)v11;
  v5 = v11;
  if ( !v11 )
  {
    v4 = -1073741670;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_4;
    v20 = 73;
    v21 = -1073741670;
    goto LABEL_30;
  }
  memset(v11, 0, 0x78u);
  v5[6].Next = (struct _SLIST_ENTRY *)*((_QWORD *)a2 + 8);
  *((_QWORD *)&v5->Next + 1) = *((_QWORD *)a2 + 5);
  v5->Next = *(struct _SLIST_ENTRY **)a1;
  v14 = *((_DWORD *)a2 + 14);
  LODWORD(v5[4].Next) = v14;
  v5[1].Next = *(struct _SLIST_ENTRY **)(v10 + 8);
  if ( *(_BYTE *)(*((_QWORD *)a2 + 8) + 16LL) != 1 )
    goto LABEL_26;
  v15 = *((_QWORD *)a2 + 6);
  if ( v15 )
  {
    HIDWORD(v5[3].Next) = *(_DWORD *)(v15 + 8);
    *((_QWORD *)&v5[3].Next + 1) = *((_QWORD *)a2 + 6) + 12LL;
    LODWORD(v5[3].Next) = *(_DWORD *)(*((_QWORD *)a2 + 6) + 4LL);
  }
  v16 = *(const void **)(v10 + 24);
  *(_QWORD *)(v12 + 80) = v16;
  v17 = *(_DWORD *)(v10 + 32);
  *(_DWORD *)(v12 + 68) = v17;
  v13 = *(unsigned int *)(v12 + 52);
  if ( *(_QWORD *)(v12 + 48) != __PAIR64__(v17, v14) )
    goto LABEL_26;
  v4 = 0;
  v18 = *(const void **)(v12 + 56);
  if ( v18 )
  {
    if ( v16 && RtlCompareMemory(v18, v16, v13) == *(_DWORD *)(v12 + 52) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 75, v13, *(_QWORD *)(v12 + 8), *(_QWORD *)(v12 + 16));
      v4 = 0;
      goto LABEL_4;
    }
    goto LABEL_26;
  }
  if ( v16 )
  {
LABEL_26:
    v19 = *(_QWORD *)(*(_QWORD *)(v12 + 96) + 24LL);
    *(_QWORD *)(v12 + 88) = v19;
    *(_BYTE *)(v12 + 89) = BYTE1(v19) & 0xF8 | 1;
    *(_BYTE *)(v12 + 108) = *((_BYTE *)a2 + 72);
    v4 = MpRegpSendNotification(0, v12, v13);
    if ( v4 >= 0
      || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    {
      goto LABEL_4;
    }
    v20 = 77;
    v21 = v4;
    _mm_lfence();
    goto LABEL_30;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids);
LABEL_4:
  if ( v5 )
  {
    v6 = MpRegData;
    ++*((_DWORD *)MpRegData + 23);
    v7 = *((_WORD *)v6 + 40);
    if ( ExQueryDepthSList((PSLIST_HEADER)v6 + 4) >= v7 )
    {
      ++*((_DWORD *)v6 + 24);
      (*((void (__fastcall **)(struct _SLIST_ENTRY *))v6 + 15))(v5);
    }
    else
    {
      _mm_lfence();
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v6 + 4, v5);
    }
  }
  if ( a2 )
    MpRegpFreeCallContext(a2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14004ea60  mov     [rsp+arg_8], rdx
0x14004ea65  push    rbx
0x14004ea66  push    rsi
0x14004ea67  push    rdi
0x14004ea68  push    r14
0x14004ea6a  push    r15
0x14004ea6c  sub     rsp, 40h
0x14004ea70  mov     rbx, rdx
0x14004ea73  mov     rdi, rcx
0x14004ea76  xor     r14d, r14d
0x14004ea79  xor     esi, esi
0x14004ea7b  test    rcx, rcx
0x14004ea7e  jz      loc_14004EDE4
0x14004ea84  cmp     [rcx+8], esi
0x14004ea87  jl      short loc_14004EA8E
0x14004ea89  test    rdx, rdx
0x14004ea8c  jnz     short loc_14004EAEF
0x14004ea8e  test    rsi, rsi
0x14004ea91  jz      short loc_14004EAD2
0x14004ea93  mov     r15, cs:MpRegData
0x14004ea9a  inc     dword ptr [r15+5Ch]
0x14004ea9e  movzx   edi, word ptr [r15+50h]
0x14004eaa3  lea     rcx, [r15+40h]; SListHead
0x14004eaa7  call    cs:__imp_ExQueryDepthSList
0x14004eaae  nop     dword ptr [rax+rax+00h]
0x14004eab3  cmp     ax, di
0x14004eab6  jnb     loc_14004ECF1
0x14004eabc  lfence
0x14004eabf  mov     rdx, rsi; ListEntry
0x14004eac2  lea     rcx, [r15+40h]; ListHead
0x14004eac6  call    cs:__imp_ExpInterlockedPushEntrySList
0x14004eacd  nop     dword ptr [rax+rax+00h]
0x14004ead2  test    rbx, rbx
0x14004ead5  jz      short loc_14004EADF
0x14004ead7  mov     rcx, rbx
0x14004eada  call    MpRegpFreeCallContext
0x14004eadf  mov     eax, r14d
0x14004eae2  add     rsp, 40h
0x14004eae6  pop     r15
0x14004eae8  pop     r14
0x14004eaea  pop     rdi
0x14004eaeb  pop     rsi
0x14004eaec  pop     rbx
0x14004eaed  retn
0x14004eaef  movzx   ecx, word ptr [rdx]
0x14004eaf2  mov     eax, 0DA0Ch
0x14004eaf7  cmp     ax, cx
0x14004eafa  jnz     loc_14004ED07
0x14004eb00  cmp     [rdx+40h], rsi
0x14004eb04  jz      loc_14004EE1E
0x14004eb0a  cmp     [rdx+28h], rsi
0x14004eb0e  jz      loc_14004EE78
0x14004eb14  mov     r14, [rdi+10h]
0x14004eb18  test    r14, r14
0x14004eb1b  jz      loc_14004ED65
0x14004eb21  mov     rcx, cs:MpRegData
0x14004eb28  add     rcx, 40h ; '@'; Lookaside
0x14004eb2c  call    ExAllocateFromPagedLookasideList
0x14004eb31  mov     r15, rax
0x14004eb34  mov     rsi, rax
0x14004eb37  mov     [rsp+68h+arg_0], rax
0x14004eb3c  test    rax, rax
0x14004eb3f  jz      loc_14004EEB2
0x14004eb45  xor     edx, edx; Val
0x14004eb47  mov     r8d, 78h ; 'x'; Size
0x14004eb4d  mov     rcx, rax; void *
0x14004eb50  call    memset
0x14004eb55  mov     rax, [rbx+40h]
0x14004eb59  mov     [rsi+60h], rax
0x14004eb5d  mov     rax, [rbx+28h]
0x14004eb61  mov     [rsi+8], rax
0x14004eb65  mov     rax, [rdi]
0x14004eb68  mov     [rsi], rax
0x14004eb6b  mov     r9d, [rbx+38h]
0x14004eb6f  mov     [rsi+40h], r9d
0x14004eb73  mov     rax, [r14+8]
0x14004eb77  mov     [rsi+10h], rax
0x14004eb7b  mov     rax, [rbx+40h]
0x14004eb7f  cmp     byte ptr [rax+10h], 1
0x14004eb83  jnz     loc_14004EC65
0x14004eb89  mov     rax, [rbx+30h]
0x14004eb8d  test    rax, rax
0x14004eb90  jz      short loc_14004EBAE
0x14004eb92  mov     eax, [rax+8]
0x14004eb95  mov     [rsi+34h], eax
0x14004eb98  mov     rax, [rbx+30h]
0x14004eb9c  add     rax, 0Ch
0x14004eba0  mov     [rsi+38h], rax
0x14004eba4  mov     rax, [rbx+30h]
0x14004eba8  mov     ecx, [rax+4]
0x14004ebab  mov     [rsi+30h], ecx
0x14004ebae  mov     rdx, [r14+18h]; Source2
0x14004ebb2  mov     [r15+50h], rdx
0x14004ebb6  mov     eax, [r14+20h]
0x14004ebba  mov     [r15+44h], eax
0x14004ebbe  mov     r8d, [r15+34h]; Length
0x14004ebc2  cmp     r8d, eax
0x14004ebc5  jnz     loc_14004EC65
0x14004ebcb  cmp     [r15+30h], r9d
0x14004ebcf  jnz     loc_14004EC65
0x14004ebd5  xor     r14d, r14d
0x14004ebd8  mov     rcx, [r15+38h]; Source1
0x14004ebdc  test    rcx, rcx
0x14004ebdf  jz      loc_14004ED9F
0x14004ebe5  test    rdx, rdx
0x14004ebe8  jz      short loc_14004EC65
0x14004ebea  call    cs:__imp_RtlCompareMemory
0x14004ebf1  nop     dword ptr [rax+rax+00h]
0x14004ebf6  mov     rcx, rax
0x14004ebf9  mov     eax, [r15+34h]
0x14004ebfd  cmp     rcx, rax
0x14004ec00  jnz     short loc_14004EC46
0x14004ec02  lea     rax, WPP_GLOBAL_Control
0x14004ec09  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ec10  cmp     rcx, rax
0x14004ec13  jz      short loc_14004EC1C
0x14004ec15  mov     eax, [rcx+2Ch]
0x14004ec18  test    al, 4
0x14004ec1a  jnz     short loc_14004EC29
0x14004ec1c  xor     r14d, r14d
0x14004ec1f  mov     [rsp+68h+var_38], r14d
0x14004ec24  jmp     loc_14004EA8E
0x14004ec29  mov     edx, 4Bh ; 'K'
0x14004ec2e  mov     rax, [r15+10h]
0x14004ec32  mov     [rsp+68h+var_48], rax
0x14004ec37  mov     r9, [r15+8]
0x14004ec3b  mov     rcx, [rcx+18h]
0x14004ec3f  call    WPP_SF_ZZ
0x14004ec44  jmp     short loc_14004EC1C
0x14004ec46  jmp     short loc_14004EC5C
0x14004ec48  mov     r14d, eax
0x14004ec4b  mov     [rsp+68h+var_38], eax
0x14004ec4f  mov     rbx, [rsp+68h+arg_8]
0x14004ec54  mov     rsi, [rsp+68h+arg_0]
0x14004ec59  mov     r15, rsi
0x14004ec5c  test    r14d, r14d
0x14004ec5f  js      loc_14004EEFA
0x14004ec65  mov     rax, [r15+60h]
0x14004ec69  mov     rcx, [rax+18h]
0x14004ec6d  mov     [r15+58h], rcx
0x14004ec71  shr     rcx, 8
0x14004ec75  and     cl, 0F9h
0x14004ec78  or      cl, 1
0x14004ec7b  mov     [r15+59h], cl
0x14004ec7f  movzx   eax, byte ptr [rbx+48h]
0x14004ec83  mov     [r15+6Ch], al
0x14004ec87  mov     rdx, r15
0x14004ec8a  xor     ecx, ecx
0x14004ec8c  call    MpRegpSendNotification
0x14004ec91  mov     r14d, eax
0x14004ec94  test    eax, eax
0x14004ec96  jns     loc_14004EA8E
0x14004ec9c  lea     rax, WPP_GLOBAL_Control
0x14004eca3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ecaa  cmp     rcx, rax
0x14004ecad  jz      loc_14004EA8E
0x14004ecb3  mov     ecx, [rcx+2Ch]
0x14004ecb6  test    cl, 1
0x14004ecb9  jz      loc_14004EA8E
0x14004ecbf  mov     edx, 4Dh ; 'M'
0x14004ecc4  mov     dword ptr [rsp+68h+var_48], r14d
0x14004ecc9  lfence
0x14004eccc  mov     r9, gs:188h
0x14004ecd5  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ecdc  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004ece3  mov     rcx, [rcx+18h]
0x14004ece7  call    WPP_SF_qD
0x14004ecec  jmp     loc_14004EA8E
0x14004ecf1  inc     dword ptr [r15+60h]
0x14004ecf5  mov     rax, [r15+78h]
0x14004ecf9  mov     rcx, rsi
0x14004ecfc  call    cs:__guard_dispatch_icall_fptr
0x14004ed02  jmp     loc_14004EAD2
0x14004ed07  mov     r14d, 0C0000024h
0x14004ed0d  lea     rax, WPP_GLOBAL_Control
0x14004ed14  mov     rdx, cs:WPP_GLOBAL_Control
0x14004ed1b  cmp     rdx, rax
0x14004ed1e  jz      loc_14004EA8E
0x14004ed24  mov     eax, [rdx+2Ch]
0x14004ed27  test    al, 1
0x14004ed29  jz      loc_14004EA8E
0x14004ed2f  mov     r9, gs:188h
0x14004ed38  mov     edx, 45h ; 'E'
0x14004ed3d  mov     [rsp+68h+var_40], 0C0000024h
0x14004ed45  mov     dword ptr [rsp+68h+var_48], ecx
0x14004ed49  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004ed50  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ed57  mov     rcx, [rcx+18h]
0x14004ed5b  call    WPP_SF_qDD
0x14004ed60  jmp     loc_14004EA8E
0x14004ed65  mov     r14d, 0C0000001h
0x14004ed6b  lea     rax, WPP_GLOBAL_Control
0x14004ed72  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ed79  cmp     rcx, rax
0x14004ed7c  jz      loc_14004EA8E
0x14004ed82  mov     eax, [rcx+2Ch]
0x14004ed85  test    al, 1
0x14004ed87  jz      loc_14004EA8E
0x14004ed8d  mov     edx, 48h ; 'H'
0x14004ed92  mov     dword ptr [rsp+68h+var_48], 0C0000001h
0x14004ed9a  jmp     loc_14004ECCC
0x14004ed9f  test    rdx, rdx
0x14004eda2  jnz     loc_14004EEEC
0x14004eda8  lea     rax, WPP_GLOBAL_Control
0x14004edaf  mov     rcx, cs:WPP_GLOBAL_Control
0x14004edb6  cmp     rcx, rax
0x14004edb9  jz      loc_14004EA8E
0x14004edbf  mov     eax, [rcx+2Ch]
0x14004edc2  test    al, 4
0x14004edc4  jz      loc_14004EA8E
0x14004edca  mov     edx, 4Ah ; 'J'
0x14004edcf  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004edd6  mov     rcx, [rcx+18h]
0x14004edda  call    WPP_SF_
0x14004eddf  jmp     loc_14004EA8E
0x14004ede4  mov     r14d, 0C000000Dh
0x14004edea  lea     rax, WPP_GLOBAL_Control
0x14004edf1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004edf8  cmp     rcx, rax
0x14004edfb  jz      loc_14004EA8E
0x14004ee01  mov     eax, [rcx+2Ch]
0x14004ee04  test    al, 1
0x14004ee06  jz      loc_14004EA8E
0x14004ee0c  mov     edx, 44h ; 'D'
0x14004ee11  mov     dword ptr [rsp+68h+var_48], 0C000000Dh
0x14004ee19  jmp     loc_14004ECCC
0x14004ee1e  mov     r14d, 0C0000001h
0x14004ee24  lea     rax, WPP_GLOBAL_Control
0x14004ee2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ee32  cmp     rcx, rax
0x14004ee35  jz      loc_14004EA8E
0x14004ee3b  mov     eax, [rcx+2Ch]
0x14004ee3e  test    al, 1
0x14004ee40  jz      loc_14004EA8E
0x14004ee46  mov     r9, gs:188h
0x14004ee4f  mov     edx, 46h ; 'F'
0x14004ee54  mov     dword ptr [rsp+68h+var_48], 0C0000001h
0x14004ee5c  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004ee63  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ee6a  mov     rcx, [rcx+18h]
0x14004ee6e  call    WPP_SF_qD
0x14004ee73  jmp     loc_14004EA8E
0x14004ee78  mov     r14d, 0C0000001h
0x14004ee7e  lea     rax, WPP_GLOBAL_Control
0x14004ee85  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ee8c  cmp     rcx, rax
0x14004ee8f  jz      loc_14004EA8E
0x14004ee95  mov     eax, [rcx+2Ch]
0x14004ee98  test    al, 1
0x14004ee9a  jz      loc_14004EA8E
0x14004eea0  mov     edx, 47h ; 'G'
0x14004eea5  mov     dword ptr [rsp+68h+var_48], 0C0000001h
0x14004eead  jmp     loc_14004ECCC
0x14004eeb2  mov     r14d, 0C000009Ah
0x14004eeb8  lea     rax, WPP_GLOBAL_Control
0x14004eebf  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eec6  cmp     rcx, rax
0x14004eec9  jz      loc_14004EA8E
0x14004eecf  mov     eax, [rcx+2Ch]
0x14004eed2  test    al, 1
0x14004eed4  jz      loc_14004EA8E
0x14004eeda  mov     edx, 49h ; 'I'
0x14004eedf  mov     dword ptr [rsp+68h+var_48], 0C000009Ah
0x14004eee7  jmp     loc_14004ECCC
0x14004eeec  test    rcx, rcx
0x14004eeef  jz      loc_14004EC65
0x14004eef5  jmp     loc_14004EBE5
0x14004eefa  lea     rax, WPP_GLOBAL_Control
0x14004ef01  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ef08  cmp     rcx, rax
0x14004ef0b  jz      loc_14004EA8E
0x14004ef11  mov     eax, [rcx+2Ch]
0x14004ef14  test    al, 1
0x14004ef16  jz      loc_14004EA8E
0x14004ef1c  mov     edx, 4Ch ; 'L'
0x14004ef21  jmp     loc_14004ECC4
```
