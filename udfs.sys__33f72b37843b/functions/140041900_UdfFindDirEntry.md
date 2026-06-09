# UdfFindDirEntry

- ea: `0x140041900`
- end: `0x140041dcf`
- name: `UdfFindDirEntry`
- size: `1231`
- prototype: `char __fastcall(__int64, __int64, const void **, char, char, char, union _LARGE_INTEGER FileOffset)`
- caller_count: `4`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140032404`
- `0x140033548`
- `0x140034450`
- `0x140042c40`

## callees

- `0x140004340`
- `0x14000b938`
- `0x14000cad4`
- `0x1400124ac`
- `0x140012600`
- `0x14001c080`
- `0x140041900`
- `0x140041de0`
- `0x1400425b0`
- `0x14004f8ac`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x140041a7e`
- `ntoskrnl!CcMapData` at `0x140041a7e`
- `ntoskrnl!CcUnpinData` at `0x1400419a7`
- `ntoskrnl!CcUnpinData` at `0x140041a36`
- `ntoskrnl!CcUnpinData` at `0x1400419a7`
- `ntoskrnl!CcUnpinData` at `0x140041a36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041987`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041987`
- `ntoskrnl!ExRaiseStatus` at `0x140041cd0`
- `ntoskrnl!ExRaiseStatus` at `0x140041cd0`
- `ntoskrnl!CcPinRead` at `0x140041cf9`
- `ntoskrnl!CcPinRead` at `0x140041cf9`
- `ntoskrnl!RtlCompareMemory` at `0x140041b69`
- `ntoskrnl!RtlCompareMemory` at `0x140041b69`

## pseudocode

```c
char __fastcall UdfFindDirEntry(
        __int64 a1,
        __int64 a2,
        const void **a3,
        char a4,
        char a5,
        char a6,
        union _LARGE_INTEGER FileOffset)
{
  _QWORD *Buffer; // rbx
  __int64 v11; // r14
  void *v12; // rcx
  void *v13; // rcx
  PVOID *v14; // rdi
  bool v15; // zf
  ULONG *v16; // r15
  union _LARGE_INTEGER v17; // rdx
  LONGLONG v18; // rcx
  unsigned __int16 *v19; // rbp
  ULONG v20; // r8d
  struct _FILE_OBJECT *v21; // rcx
  int v22; // edi
  unsigned int v23; // eax
  __int64 v24; // r8
  unsigned int v25; // eax
  __int64 v26; // r9
  int v27; // r8d
  __int16 v28; // dx
  unsigned int v29; // ebp
  unsigned int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rdx
  int v33; // eax
  __int64 v34; // rax
  PVOID *Bcb; // [rsp+20h] [rbp-58h]
  PVOID *Bcba; // [rsp+20h] [rbp-58h]
  PVOID *Bcbb; // [rsp+20h] [rbp-58h]
  _QWORD *v39; // [rsp+88h] [rbp+10h]

  Buffer = (_QWORD *)FileOffset.QuadPart;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x100) != 0 )
  {
    WPP_SF_qZDDq(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      a2,
      (_DWORD)a3,
      a2,
      (__int64)a3,
      a4,
      a6,
      FileOffset.QuadPart);
  }
  if ( a6 )
  {
    v11 = 14;
  }
  else
  {
    v11 = 8;
    if ( a4 )
      v11 = 10;
  }
  if ( (Buffer[7] & 0x40) != 0 )
  {
    v12 = (void *)Buffer[16];
    if ( v12 )
    {
      ExFreePoolWithTag(v12, 0);
      Buffer[16] = 0;
    }
  }
  v13 = (void *)Buffer[1];
  v14 = (PVOID *)(Buffer + 1);
  if ( v13 )
  {
    CcUnpinData(v13);
    *v14 = 0;
  }
  if ( (Buffer[7] & 4) != 0 )
    UdfFreePool(Buffer + 4);
  memset(Buffer, 0, 0x98u);
  if ( !*(_QWORD *)(a2 + 504) )
    UdfCreateInternalStream(a1, *(_QWORD *)(a1 + 16), a2, 0);
  v15 = (*(_DWORD *)(a2 + 212) & 0x8000000) == 0;
  v16 = (ULONG *)(Buffer + 3);
  FileOffset.QuadPart = 0;
  if ( v15 )
  {
    v17 = (union _LARGE_INTEGER)Buffer[2];
    *v16 = 4096;
    v18 = *(_QWORD *)(a2 + 32);
    if ( v17.QuadPart + 4096 > v18 )
      *v16 = v18 - v17.LowPart;
    FileOffset = v17;
  }
  else
  {
    UdfFindDataInMetadataStream(a1, a2, Buffer + 2, &FileOffset, Buffer + 3);
    if ( FileOffset.QuadPart + *v16 > *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 320LL) + 24LL) )
    {
      *(_DWORD *)(a1 + 24) = -1073741566;
      ExRaiseStatus(-1073741566);
    }
  }
  v19 = (unsigned __int16 *)&Buffer[v11];
  v39 = &Buffer[v11];
  if ( *v14 )
  {
    CcUnpinData(*v14);
    *v14 = 0;
  }
  v20 = *v16;
  v21 = *(struct _FILE_OBJECT **)(a2 + 504);
  Bcb = (PVOID *)(Buffer + 1);
  v22 = 1;
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 0x4000) != 0 )
  {
    CcMapData(v21, &FileOffset, v20, 1u, Bcb, (PVOID *)Buffer);
    v23 = Buffer[7] & 0xFFFFFFEF;
  }
  else
  {
    CcPinRead(v21, &FileOffset, v20, 1u, Bcb, (PVOID *)Buffer);
    v23 = *((_DWORD *)Buffer + 14) | 0x10;
  }
  *((_DWORD *)Buffer + 14) = v23 & 0xFFFFFFDF;
  Buffer[4] = *Buffer + *((unsigned int *)Buffer + 7);
  UdfLookupDirEntryPostProcessing(a1, a2, (__int64)Buffer, 0, (size_t)Bcba, 0);
  while ( 1 )
  {
    if ( (*(_BYTE *)(Buffer[4] + 18LL) & 4) != 0 )
      goto LABEL_41;
    v25 = *(_DWORD *)(a2 + 212);
    v26 = v25 >> 3;
    LOBYTE(v24) = a5 || (v25 & 0x800000) != 0;
    LOBYTE(v26) = (*(_DWORD *)(a2 + 212) & 8) != 0;
    UdfUpdateDirNames(a1, Buffer, v24, v26);
    if ( (Buffer[7] & 1) == 0 )
      goto LABEL_41;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x100) != 0 )
    {
      WPP_SF_ZZD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        (_DWORD)Buffer + 96,
        v27,
        (_DWORD)Buffer + 64,
        (__int64)(Buffer + 12),
        *((_DWORD *)Buffer + 7));
    }
    if ( a6 && !*((_WORD *)Buffer + 56) )
      goto LABEL_41;
    v28 = *v19;
    if ( *v19 <= *(_WORD *)a3 )
    {
      v22 = -1;
      v29 = *v19;
      if ( v28 == *(_WORD *)a3 )
        v22 = 0;
    }
    else
    {
      v29 = *(unsigned __int16 *)a3;
    }
    v30 = RtlCompareMemory((const void *)v39[1], a3[1], v29);
    if ( v30 < v29 )
    {
      v22 = -1;
      if ( *(_WORD *)(2 * ((unsigned __int64)v30 >> 1) + v39[1]) >= *((_WORD *)a3[1] + ((unsigned __int64)v30 >> 1)) )
        v22 = 1;
    }
    if ( !v22 )
      break;
    v19 = (unsigned __int16 *)&Buffer[v11];
    v22 = 1;
LABEL_41:
    v31 = *((unsigned int *)Buffer + 10);
    v32 = v31 + Buffer[2];
    if ( v32 >= v31 && v32 != *(_QWORD *)(a2 + 32) )
    {
      v33 = *((_DWORD *)Buffer + 14);
      Buffer[6] = v32;
      if ( (v33 & 4) != 0 )
      {
        *((_DWORD *)Buffer + 14) = v33 & 0xFFFFFFFB;
        UdfFreePool(Buffer + 4);
      }
      v34 = *((unsigned int *)Buffer + 10);
      *((_DWORD *)Buffer + 7) = v34;
      Buffer[4] = *Buffer + v34;
      if ( (unsigned __int8)UdfLookupDirEntryPostProcessing(a1, a2, (__int64)Buffer, 0, (size_t)Bcbb, 0) )
        continue;
    }
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x100) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 18, WPP_7471fb31cf8e3b538dce4a4ba670d992_Traceguids);
    }
    return 0;
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x100) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 17, WPP_7471fb31cf8e3b538dce4a4ba670d992_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x140041900  mov     [rsp+arg_10], r8
0x140041905  push    rbx
0x140041906  push    rbp
0x140041907  push    rsi
0x140041908  push    rdi
0x140041909  push    r12
0x14004190b  push    r13
0x14004190d  push    r15
0x14004190f  sub     rsp, 40h
0x140041913  movzx   edi, r9b
0x140041917  mov     rsi, rdx
0x14004191a  mov     r13, rcx
0x14004191d  mov     rcx, cs:WPP_GLOBAL_Control
0x140041924  lea     rax, WPP_GLOBAL_Control
0x14004192b  mov     rbx, qword ptr [rsp+78h+FileOffset]
0x140041933  movzx   ebp, [rsp+78h+arg_28]
0x14004193b  cmp     rcx, rax
0x14004193e  jz      short loc_14004194D
0x140041940  test    dword ptr [rcx+2Ch], 100h
0x140041947  jnz     loc_140041D10
0x14004194d  mov     [rsp+78h+arg_0], r14
0x140041955  test    bpl, bpl
0x140041958  jnz     loc_140041CEE
0x14004195e  test    dil, dil
0x140041961  mov     eax, 50h ; 'P'
0x140041966  mov     r14d, 40h ; '@'
0x14004196c  cmovnz  r14d, eax
0x140041970  mov     eax, [rbx+38h]
0x140041973  xor     ebp, ebp
0x140041975  test    al, 40h
0x140041977  jz      short loc_14004199A
0x140041979  mov     rcx, [rbx+80h]; P
0x140041980  test    rcx, rcx
0x140041983  jz      short loc_14004199A
0x140041985  xor     edx, edx; Tag
0x140041987  call    cs:__imp_ExFreePoolWithTag
0x14004198e  nop     dword ptr [rax+rax+00h]
0x140041993  mov     [rbx+80h], rbp
0x14004199a  mov     rcx, [rbx+8]; Bcb
0x14004199e  lea     rdi, [rbx+8]
0x1400419a2  test    rcx, rcx
0x1400419a5  jz      short loc_1400419B6
0x1400419a7  call    cs:__imp_CcUnpinData
0x1400419ae  nop     dword ptr [rax+rax+00h]
0x1400419b3  mov     [rdi], rbp
0x1400419b6  mov     eax, [rbx+38h]
0x1400419b9  test    al, 4
0x1400419bb  jnz     loc_140041D33
0x1400419c1  xor     edx, edx; Val
0x1400419c3  mov     r8d, 98h; Size
0x1400419c9  mov     rcx, rbx; void *
0x1400419cc  call    memset
0x1400419d1  cmp     [rsi+1F8h], rbp
0x1400419d8  jz      loc_140041D41
0x1400419de  test    dword ptr [rsi+0D4h], 8000000h
0x1400419e8  lea     r15, [rbx+18h]
0x1400419ec  mov     qword ptr [rsp+78h+FileOffset], rbp
0x1400419f4  jnz     loc_140041C87
0x1400419fa  mov     rdx, [rbx+10h]
0x1400419fe  mov     dword ptr [r15], 1000h
0x140041a05  mov     rcx, [rsi+20h]
0x140041a09  lea     rax, [rdx+1000h]
0x140041a10  cmp     rax, rcx
0x140041a13  jle     short loc_140041A1A
0x140041a15  sub     ecx, edx
0x140041a17  mov     [r15], ecx
0x140041a1a  mov     qword ptr [rsp+78h+FileOffset], rdx
0x140041a22  mov     rcx, [rdi]; Bcb
0x140041a25  lea     rbp, [r14+rbx]
0x140041a29  mov     [rsp+78h+arg_8], rbp
0x140041a31  test    rcx, rcx
0x140041a34  jz      short loc_140041A49
0x140041a36  call    cs:__imp_CcUnpinData
0x140041a3d  nop     dword ptr [rax+rax+00h]
0x140041a42  mov     qword ptr [rdi], 0
0x140041a49  mov     rax, [r13+10h]
0x140041a4d  lea     rdx, [rsp+78h+FileOffset]; FileOffset
0x140041a55  mov     r8d, [r15]; Length
0x140041a58  mov     rcx, [rsi+1F8h]; FileObject
0x140041a5f  mov     [rsp+78h+Buffer], rbx; Buffer
0x140041a64  test    dword ptr [rax+30h], 4000h
0x140041a6b  mov     [rsp+78h+Bcb], rdi; Size
0x140041a70  mov     edi, 1
0x140041a75  mov     r9d, edi; Flags
0x140041a78  jz      loc_140041CF9
0x140041a7e  call    cs:__imp_CcMapData
0x140041a85  nop     dword ptr [rax+rax+00h]
0x140041a8a  mov     eax, [rbx+38h]
0x140041a8d  and     eax, 0FFFFFFEFh
0x140041a90  and     eax, 0FFFFFFDFh
0x140041a93  mov     dword ptr [rsp+78h+Buffer], 0; int
0x140041a9b  mov     [rbx+38h], eax
0x140041a9e  xor     r9d, r9d; int
0x140041aa1  mov     eax, [rbx+1Ch]
0x140041aa4  mov     r8, rbx; int
0x140041aa7  add     rax, [rbx]
0x140041aaa  mov     rdx, rsi; int
0x140041aad  mov     rcx, r13; int
0x140041ab0  mov     [rbx+20h], rax
0x140041ab4  call    UdfLookupDirEntryPostProcessing
0x140041ab9  movzx   r15d, [rsp+78h+arg_20]
0x140041ac2  mov     rax, [rbx+20h]
0x140041ac6  test    byte ptr [rax+12h], 4
0x140041aca  jnz     loc_140041BC4
0x140041ad0  mov     eax, [rsi+0D4h]
0x140041ad6  mov     r9d, eax
0x140041ad9  shr     r9d, 3
0x140041add  and     r9b, 1
0x140041ae1  test    r15b, r15b
0x140041ae4  jnz     loc_140041C3A
0x140041aea  bt      eax, 17h
0x140041aee  jb      loc_140041C3A
0x140041af4  xor     r8b, r8b
0x140041af7  mov     rdx, rbx
0x140041afa  mov     rcx, r13
0x140041afd  call    UdfUpdateDirNames
0x140041b02  mov     eax, [rbx+38h]
0x140041b05  test    al, 1
0x140041b07  jz      loc_140041BC4
0x140041b0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140041b14  lea     rax, WPP_GLOBAL_Control
0x140041b1b  cmp     rcx, rax
0x140041b1e  jz      short loc_140041B2D
0x140041b20  test    dword ptr [rcx+2Ch], 100h
0x140041b27  jnz     loc_140041D58
0x140041b2d  cmp     [rsp+78h+arg_28], 0
0x140041b35  jnz     loc_140041CDD
0x140041b3b  mov     r9, [rsp+78h+arg_10]
0x140041b43  movzx   edx, word ptr [rbp+0]
0x140041b47  movzx   ecx, word ptr [r9]
0x140041b4b  cmp     dx, cx
0x140041b4e  jbe     loc_140041C42
0x140041b54  mov     ebp, ecx
0x140041b56  mov     rcx, [rsp+78h+arg_8]
0x140041b5e  mov     rdx, [r9+8]; Source2
0x140041b62  mov     r8d, ebp; Length
0x140041b65  mov     rcx, [rcx+8]; Source1
0x140041b69  call    cs:__imp_RtlCompareMemory
0x140041b70  nop     dword ptr [rax+rax+00h]
0x140041b75  cmp     eax, ebp
0x140041b77  jnb     short loc_140041BAF
0x140041b79  mov     r8, [rsp+78h+arg_10]
0x140041b81  mov     edi, 0FFFFFFFFh
0x140041b86  mov     eax, eax
0x140041b88  shr     rax, 1
0x140041b8b  lea     rdx, [rax+rax]
0x140041b8f  mov     rax, [rsp+78h+arg_8]
0x140041b97  mov     rcx, [rax+8]
0x140041b9b  mov     rax, [r8+8]
0x140041b9f  movzx   eax, word ptr [rdx+rax]
0x140041ba3  cmp     [rdx+rcx], ax
0x140041ba7  mov     eax, 1
0x140041bac  cmovnb  edi, eax
0x140041baf  test    edi, edi
0x140041bb1  jz      loc_140041C56
0x140041bb7  mov     rbp, [rsp+78h+arg_8]
0x140041bbf  mov     edi, 1
0x140041bc4  mov     ecx, [rbx+28h]
0x140041bc7  mov     rdx, [rbx+10h]
0x140041bcb  add     rdx, rcx
0x140041bce  cmp     rdx, rcx
0x140041bd1  jl      short loc_140041C16
0x140041bd3  cmp     rdx, [rsi+20h]
0x140041bd7  jz      short loc_140041C16
0x140041bd9  mov     eax, [rbx+38h]
0x140041bdc  mov     [rbx+30h], rdx
0x140041be0  test    al, 4
0x140041be2  jnz     loc_140041D7A
0x140041be8  mov     eax, [rbx+28h]
0x140041beb  xor     r9d, r9d; int
0x140041bee  mov     [rbx+1Ch], eax
0x140041bf1  mov     r8, rbx; int
0x140041bf4  add     rax, [rbx]
0x140041bf7  mov     rdx, rsi; int
0x140041bfa  mov     rcx, r13; int
0x140041bfd  mov     [rbx+20h], rax
0x140041c01  mov     dword ptr [rsp+78h+Buffer], 0; int
0x140041c09  call    UdfLookupDirEntryPostProcessing
0x140041c0e  test    al, al
0x140041c10  jnz     loc_140041AC2
0x140041c16  mov     rcx, cs:WPP_GLOBAL_Control
0x140041c1d  lea     rax, WPP_GLOBAL_Control
0x140041c24  cmp     rcx, rax
0x140041c27  jz      short loc_140041C36
0x140041c29  test    dword ptr [rcx+2Ch], 100h
0x140041c30  jnz     loc_140041DB5
0x140041c36  xor     al, al
0x140041c38  jmp     short loc_140041C6F
0x140041c3a  mov     r8b, 1
0x140041c3d  jmp     loc_140041AF7
0x140041c42  xor     eax, eax
0x140041c44  mov     edi, 0FFFFFFFFh
0x140041c49  cmp     dx, cx
0x140041c4c  mov     ebp, edx
0x140041c4e  cmovz   edi, eax
0x140041c51  jmp     loc_140041B56
0x140041c56  mov     rcx, cs:WPP_GLOBAL_Control
0x140041c5d  lea     rax, WPP_GLOBAL_Control
0x140041c64  cmp     rcx, rax
0x140041c67  jnz     loc_140041D8E
0x140041c6d  mov     al, 1
0x140041c6f  mov     r14, [rsp+78h+arg_0]
0x140041c77  add     rsp, 40h
0x140041c7b  pop     r15
0x140041c7d  pop     r13
0x140041c7f  pop     r12
0x140041c81  pop     rdi
0x140041c82  pop     rsi
0x140041c83  pop     rbp
0x140041c84  pop     rbx
0x140041c85  retn
0x140041c87  lea     r9, [rsp+78h+FileOffset]
0x140041c8f  mov     [rsp+78h+Bcb], r15
0x140041c94  lea     r8, [rbx+10h]
0x140041c98  mov     rdx, rsi
0x140041c9b  mov     rcx, r13
0x140041c9e  call    UdfFindDataInMetadataStream
0x140041ca3  mov     rax, [r13+10h]
0x140041ca7  mov     edx, [r15]
0x140041caa  add     rdx, qword ptr [rsp+78h+FileOffset]
0x140041cb2  mov     rcx, [rax+140h]
0x140041cb9  cmp     rdx, [rcx+18h]
0x140041cbd  jle     loc_140041A22
0x140041cc3  mov     ecx, 0C0000102h; Status
0x140041cc8  mov     dword ptr [r13+18h], 0C0000102h
0x140041cd0  call    cs:__imp_ExRaiseStatus
0x140041cdd  xor     eax, eax
0x140041cdf  cmp     ax, [rbx+70h]
0x140041ce3  jz      loc_140041BC4
0x140041ce9  jmp     loc_140041B3B
0x140041cee  mov     r14d, 70h ; 'p'
0x140041cf4  jmp     loc_140041970
0x140041cf9  call    cs:__imp_CcPinRead
0x140041d00  nop     dword ptr [rax+rax+00h]
0x140041d05  mov     eax, [rbx+38h]
0x140041d08  or      eax, 10h
0x140041d0b  jmp     loc_140041A90
0x140041d10  mov     rcx, [rcx+18h]
0x140041d14  mov     r9, rsi
0x140041d17  mov     [rsp+78h+var_40], rbx
0x140041d1c  mov     [rsp+78h+var_48], ebp
0x140041d20  mov     dword ptr [rsp+78h+Buffer], edi
0x140041d24  mov     [rsp+78h+Bcb], r8
0x140041d29  call    WPP_SF_qZDDq
0x140041d2e  jmp     loc_14004194D
0x140041d33  lea     rcx, [rbx+20h]
0x140041d37  call    UdfFreePool
0x140041d3c  jmp     loc_1400419C1
0x140041d41  mov     rdx, [r13+10h]
0x140041d45  xor     r9d, r9d
0x140041d48  mov     r8, rsi
0x140041d4b  mov     rcx, r13
0x140041d4e  call    UdfCreateInternalStream
0x140041d53  jmp     loc_1400419DE
0x140041d58  mov     eax, [rbx+1Ch]
0x140041d5b  lea     rdx, [rbx+60h]
0x140041d5f  mov     rcx, [rcx+18h]
0x140041d63  lea     r9, [rbx+40h]
0x140041d67  mov     dword ptr [rsp+78h+Buffer], eax
0x140041d6b  mov     [rsp+78h+Bcb], rdx
0x140041d70  call    WPP_SF_ZZD
0x140041d75  jmp     loc_140041B2D
0x140041d7a  and     eax, 0FFFFFFFBh
0x140041d7d  lea     rcx, [rbx+20h]
0x140041d81  mov     [rbx+38h], eax
0x140041d84  call    UdfFreePool
0x140041d89  jmp     loc_140041BE8
0x140041d8e  test    dword ptr [rcx+2Ch], 100h
0x140041d95  jz      loc_140041C6D
0x140041d9b  mov     rcx, [rcx+18h]
0x140041d9f  lea     r8, WPP_7471fb31cf8e3b538dce4a4ba670d992_Traceguids
0x140041da6  mov     edx, 11h
0x140041dab  call    WPP_SF_
0x140041db0  jmp     loc_140041C6D
0x140041db5  mov     rcx, [rcx+18h]
0x140041db9  lea     r8, WPP_7471fb31cf8e3b538dce4a4ba670d992_Traceguids
0x140041dc0  mov     edx, 12h
0x140041dc5  call    WPP_SF_
0x140041dca  jmp     loc_140041C36
```
