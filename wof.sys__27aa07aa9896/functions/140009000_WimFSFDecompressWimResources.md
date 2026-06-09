# WimFSFDecompressWimResources

- ea: `0x140009000`
- end: `0x1400094e8`
- name: `WimFSFDecompressWimResources`
- size: `1256`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c400`

## callees

- `0x14000263c`
- `0x140003a28`
- `0x140008df0`
- `0x140009000`
- `0x1400094f0`
- `0x140009590`
- `0x14000a1dc`
- `0x14000ca10`
- `0x14000cf20`
- `0x14000d280`
- `0x14000d3b8`
- `0x14000fb60`
- `0x1400116c0`
- `0x1400119c0`

## import_xrefs

- `ntoskrnl!RtlDecompressBufferEx` at `0x1400092aa`
- `ntoskrnl!RtlDecompressBufferEx` at `0x1400092aa`
- `ntoskrnl!RtlDecompressFragment` at `0x140009223`
- `ntoskrnl!RtlDecompressFragment` at `0x140009223`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140009465`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140009465`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000906e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000906e`

## pseudocode

```c
__int64 __fastcall WimFSFDecompressWimResources(PVOID Entry)
{
  __int64 v1; // rax
  ULONG v2; // r12d
  unsigned __int64 v4; // rsi
  __int64 v5; // r13
  char *v6; // rax
  char *v7; // r14
  NTSTATUS v8; // edi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  char *v13; // r15
  __int64 v14; // r8
  ULONG v15; // eax
  ULONG v16; // r9d
  __int64 v17; // r14
  int v18; // r12d
  int v19; // eax
  ULONG CompressedBufferSize; // r12d
  ULONG v21; // r10d
  ULONG v22; // r13d
  ULONG v23; // edx
  int v24; // ecx
  ULONG v25; // r15d
  char *v26; // r14
  int v27; // ecx
  int v28; // eax
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 result; // rax
  void **FragmentOffset; // [rsp+28h] [rbp-41h]
  void *v33; // [rsp+40h] [rbp-29h] BYREF
  PUCHAR CompressedBuffer; // [rsp+48h] [rbp-21h]
  __int64 v35; // [rsp+50h] [rbp-19h]
  ULONG v36[2]; // [rsp+58h] [rbp-11h]
  char *v37; // [rsp+60h] [rbp-9h]
  __int64 v38; // [rsp+68h] [rbp-1h]
  PVOID WorkSpace; // [rsp+70h] [rbp+7h]
  __int64 v40; // [rsp+78h] [rbp+Fh]
  ULONG FinalUncompressedSize; // [rsp+D0h] [rbp+67h] BYREF
  size_t Size; // [rsp+D8h] [rbp+6Fh]
  ULONG v43; // [rsp+E0h] [rbp+77h]
  ULONG v44; // [rsp+E8h] [rbp+7Fh]

  v1 = *((_QWORD *)Entry + 4);
  v2 = 0;
  v44 = 0;
  v4 = 0;
  v5 = *(unsigned int *)(v1 + 104);
  CompressedBuffer = (PUCHAR)*((_QWORD *)Entry + 11);
  LODWORD(Size) = *((_DWORD *)Entry + 26);
  v43 = v5;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
  v6 = (char *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(*((_QWORD *)Entry + 4) + 128LL));
  v37 = v6;
  v7 = v6;
  if ( !v6 )
    goto LABEL_5;
  v9 = *((_QWORD *)Entry + 4);
  v40 = v5;
  WorkSpace = &v6[v5];
  if ( (*(_DWORD *)(v9 + 96) & 0x40000) != 0 )
    v4 = LZX_DecodeInit(&v6[v5], *(unsigned int *)(v9 + 112), (unsigned int)v5);
  v10 = *((_QWORD *)Entry + 4);
  if ( (*(_DWORD *)(v10 + 96) & 0x20000) == 0 )
    goto LABEL_11;
  v11 = WimFSFAllocateXpress(v10, 4480);
  if ( !v11 )
  {
    v4 = 0;
    goto LABEL_5;
  }
  v4 = (v11 & 0xFFFFFFFFFFFFFF00uLL) + 256;
  *(_QWORD *)(v4 + 4208) = v11;
  *(_DWORD *)(v4 + 104) = 903790814;
  if ( (v11 & 0xFFFFFFFFFFFFFF00uLL) == 0xFFFFFFFFFFFFFF00uLL )
  {
LABEL_5:
    v8 = -1073741670;
    goto LABEL_68;
  }
LABEL_11:
  v8 = 0;
  LODWORD(v38) = 0;
  if ( *((_QWORD *)Entry + 5) )
    v38 = (unsigned int)((v5 + *((_QWORD *)Entry + 7) - 1LL) / v5) - 1;
  v12 = *((_QWORD *)Entry + 12) % v5;
  v13 = (char *)*((_QWORD *)Entry + 10);
  v14 = *((_QWORD *)Entry + 12) / v5;
  v35 = v14;
  v15 = Size;
  v16 = v12;
  *(_QWORD *)v36 = v12;
  v33 = v13;
  while ( v15 )
  {
    v17 = *((_QWORD *)Entry + 5);
    FinalUncompressedSize = 0;
    if ( v17 )
    {
      v18 = WimFSFGetChunkOffset(v17, (unsigned int)(v14 + 1));
      v19 = WimFSFGetChunkOffset(v17, (unsigned int)v35);
      v16 = v36[0];
      CompressedBufferSize = v18 - v19;
      v15 = Size;
      LODWORD(v14) = v35;
    }
    else
    {
      CompressedBufferSize = *((_DWORD *)Entry + 12);
    }
    v21 = v5 - v16;
    FinalUncompressedSize = v5 - v16;
    if ( (unsigned int)v5 - v16 <= v15 )
    {
      v22 = v5 - v16;
    }
    else
    {
      v21 = v15;
      FinalUncompressedSize = v15;
      v22 = v15;
    }
    if ( !CompressedBufferSize )
    {
      memset(v13, 0, v22);
      goto LABEL_59;
    }
    v23 = v43;
    if ( CompressedBufferSize == v43 )
      goto LABEL_58;
    if ( (_DWORD)v14 == (_DWORD)v38 )
    {
      if ( CompressedBufferSize == (unsigned int)(*((_QWORD *)Entry + 7) % v40) )
      {
LABEL_58:
        memmove(v13, &CompressedBuffer[v16], v22);
LABEL_59:
        if ( v8 < 0 )
        {
LABEL_63:
          if ( WimSqmIsOptedIn )
          {
            v2 = v44;
            v33 = v13;
            _InterlockedIncrement64(&WimDecompressionFailureCount);
          }
          else
          {
            v2 = v44;
          }
          break;
        }
        goto LABEL_60;
      }
      v23 = v43;
    }
    v24 = *(_DWORD *)(*((_QWORD *)Entry + 4) + 96LL);
    if ( (v24 & 0xFF000000) != 0 )
    {
      v8 = RtlDecompressFragment(
             2u,
             (PUCHAR)v13,
             v21,
             CompressedBuffer,
             CompressedBufferSize,
             v16,
             &FinalUncompressedSize,
             WorkSpace);
      goto LABEL_59;
    }
    if ( (_DWORD)v14 == (_DWORD)v38 )
      v25 = *((_DWORD *)Entry + 14) - v14 * v23;
    else
      v25 = v23;
    if ( (v24 & 0x40000) != 0 )
    {
      if ( v16 || v22 != v25 )
        goto LABEL_36;
    }
    else
    {
      v26 = 0;
      if ( (v24 & 0x220000) == 0 )
        goto LABEL_37;
      if ( v16 || v22 != v25 || !*((_QWORD *)Entry + 9) || !(unsigned __int8)WofIsMdlInvariant() )
      {
LABEL_36:
        v26 = v37;
        v21 = v25;
        FinalUncompressedSize = v25;
LABEL_37:
        v13 = (char *)v33;
        goto LABEL_38;
      }
      v21 = FinalUncompressedSize;
    }
    v13 = (char *)v33;
    v26 = (char *)v33;
LABEL_38:
    v27 = *(_DWORD *)(*((_QWORD *)Entry + 4) + 96LL);
    if ( (v27 & 0x200000) != 0 )
    {
      LODWORD(v33) = 0;
      FragmentOffset = &v33;
      v8 = RtlDecompressBufferEx(4, v26, v21, CompressedBuffer, CompressedBufferSize);
LABEL_54:
      v21 = FinalUncompressedSize;
      goto LABEL_55;
    }
    if ( (v27 & 0x20000) == 0 )
    {
      if ( (v27 & 0x40000) == 0 )
        goto LABEL_55;
      if ( (unsigned int)LZX_Decode(
                           v4,
                           v21,
                           (_DWORD)CompressedBuffer,
                           CompressedBufferSize,
                           (__int64)v26,
                           (_DWORD)FragmentOffset,
                           (__int64)&FinalUncompressedSize) )
        v8 = -1073741823;
      LZX_DecodeNewGroup(v4);
      goto LABEL_54;
    }
    v28 = WIM_XpressDecode(v4, (_DWORD)v26, v43, v21, (__int64)CompressedBuffer, CompressedBufferSize);
    v21 = FinalUncompressedSize;
    if ( FinalUncompressedSize != v28 )
      v8 = -1073741823;
LABEL_55:
    if ( v8 < 0 )
      goto LABEL_63;
    if ( v26 != v13 )
    {
      FinalUncompressedSize = v22;
      memmove(v13, &v26[v36[0]], v22);
LABEL_60:
      v21 = FinalUncompressedSize;
    }
    v16 = 0;
    LODWORD(v5) = v43;
    LODWORD(v14) = v35 + 1;
    v13 += v21;
    *(_QWORD *)v36 = 0;
    CompressedBuffer += CompressedBufferSize;
    v15 = Size - v21;
    v2 = v21 + v44;
    v33 = v13;
    LODWORD(Size) = Size - v21;
    v44 += v21;
    v35 = (unsigned int)(v35 + 1);
    if ( WimSqmIsOptedIn )
      _InterlockedIncrement64(&WimDecompressionCount);
  }
  v7 = v37;
LABEL_68:
  *((_DWORD *)Entry + 27) = v8;
  *((_DWORD *)Entry + 28) = v2;
  if ( v7 )
    ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(*((_QWORD *)Entry + 4) + 128LL), v7);
  v29 = *((_QWORD *)Entry + 4);
  if ( (*(_DWORD *)(v29 + 96) & 0x20000) != 0 && v4 && *(_DWORD *)(v4 + 104) == 903790814 )
  {
    v30 = *(_QWORD *)(v4 + 4208);
    *(_DWORD *)(v4 + 104) = 0;
    WimFSFFreeXpress(v29, v30);
  }
  WimFSFCompleteRequest(Entry);
  result = HIDWORD(WPP_GLOBAL_Control->Timer);
  if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    return WPP_SF_d(
             WPP_GLOBAL_Control->AttachedDevice,
             39,
             WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids,
             (unsigned int)v8);
  return result;
}

```

## disassembly

```asm
0x140009000  push    rbp
0x140009002  push    rbx
0x140009003  push    rsi
0x140009004  push    rdi
0x140009005  push    r12
0x140009007  push    r13
0x140009009  push    r14
0x14000900b  push    r15
0x14000900d  lea     rbp, [rsp-1Fh]
0x140009012  sub     rsp, 88h
0x140009019  mov     rax, [rcx+20h]
0x14000901d  xor     r12d, r12d
0x140009020  mov     rbx, rcx
0x140009023  mov     [rbp+57h+arg_18], r12d
0x140009027  xor     esi, esi
0x140009029  mov     r13d, [rax+68h]
0x14000902d  mov     rax, [rcx+58h]
0x140009031  mov     [rbp+57h+CompressedBuffer], rax
0x140009035  mov     eax, [rcx+68h]
0x140009038  mov     dword ptr [rbp+57h+Size], eax
0x14000903b  mov     [rbp+57h+arg_10], r13d
0x14000903f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009046  mov     eax, [rcx+2Ch]
0x140009049  test    al, 20h
0x14000904b  jz      short loc_140009066
0x14000904d  cmp     byte ptr [rcx+29h], 4
0x140009051  jb      short loc_140009066
0x140009053  mov     rcx, [rcx+18h]
0x140009057  lea     edx, [rsi+26h]
0x14000905a  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x140009061  call    WPP_SF_
0x140009066  mov     rcx, [rbx+20h]
0x14000906a  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x14000906e  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140009075  nop     dword ptr [rax+rax+00h]
0x14000907a  mov     [rbp+57h+var_60], rax
0x14000907e  mov     r14, rax
0x140009081  test    rax, rax
0x140009084  jnz     short loc_140009090
0x140009086  mov     edi, 0C000009Ah
0x14000908b  jmp     loc_14000944E
0x140009090  mov     rdx, [rbx+20h]
0x140009094  lea     rcx, [rax+r13]
0x140009098  mov     r15, r13
0x14000909b  mov     [rbp+57h+var_48], r13
0x14000909f  mov     [rbp+57h+var_50], rcx
0x1400090a3  test    dword ptr [rdx+60h], 40000h
0x1400090aa  jz      short loc_1400090BA
0x1400090ac  mov     edx, [rdx+70h]
0x1400090af  mov     r8d, r13d
0x1400090b2  call    LZX_DecodeInit
0x1400090b7  mov     rsi, rax
0x1400090ba  mov     rcx, [rbx+20h]
0x1400090be  test    dword ptr [rcx+60h], 20000h
0x1400090c5  jz      short loc_1400090FB
0x1400090c7  mov     edx, 1180h
0x1400090cc  call    WimFSFAllocateXpress
0x1400090d1  test    rax, rax
0x1400090d4  jz      loc_14000917F
0x1400090da  mov     rsi, rax
0x1400090dd  and     rsi, 0FFFFFFFFFFFFFF00h
0x1400090e4  add     rsi, 100h
0x1400090eb  mov     [rsi+1070h], rax
0x1400090f2  mov     dword ptr [rsi+68h], 35DEC0DEh
0x1400090f9  jz      short loc_140009086
0x1400090fb  xor     edi, edi
0x1400090fd  mov     dword ptr [rbp+57h+var_58], edi
0x140009100  cmp     [rbx+28h], rdi
0x140009104  jz      short loc_14000911B
0x140009106  mov     rax, [rbx+38h]
0x14000910a  dec     rax
0x14000910d  add     rax, r15
0x140009110  cqo
0x140009112  idiv    r15
0x140009115  dec     eax
0x140009117  mov     [rbp+57h+var_58], rax
0x14000911b  mov     rax, [rbx+60h]
0x14000911f  cqo
0x140009121  idiv    r15
0x140009124  mov     r15, [rbx+50h]
0x140009128  mov     r8, rax
0x14000912b  mov     [rbp+57h+var_70], rax
0x14000912f  mov     eax, dword ptr [rbp+57h+Size]
0x140009132  mov     r9, rdx
0x140009135  mov     qword ptr [rbp+57h+var_68], rdx
0x140009139  mov     [rbp+57h+var_80], r15
0x14000913d  test    eax, eax
0x14000913f  jz      loc_14000944A
0x140009145  mov     r14, [rbx+28h]
0x140009149  mov     [rbp+57h+arg_0], 0
0x140009150  test    r14, r14
0x140009153  jz      short loc_140009186
0x140009155  lea     edx, [r8+1]
0x140009159  mov     rcx, r14
0x14000915c  call    WimFSFGetChunkOffset
0x140009161  mov     edx, dword ptr [rbp+57h+var_70]
0x140009164  mov     rcx, r14
0x140009167  mov     r12, rax
0x14000916a  call    WimFSFGetChunkOffset
0x14000916f  mov     r9, qword ptr [rbp+57h+var_68]
0x140009173  sub     r12d, eax
0x140009176  mov     eax, dword ptr [rbp+57h+Size]
0x140009179  mov     r8, [rbp+57h+var_70]
0x14000917d  jmp     short loc_14000918A
0x14000917f  xor     esi, esi
0x140009181  jmp     loc_140009086
0x140009186  mov     r12d, [rbx+30h]
0x14000918a  mov     r10d, r13d
0x14000918d  sub     r10d, r9d
0x140009190  mov     [rbp+57h+arg_0], r10d
0x140009194  cmp     r10d, eax
0x140009197  jbe     short loc_1400091A4
0x140009199  mov     r10d, eax
0x14000919c  mov     [rbp+57h+arg_0], eax
0x14000919f  mov     r13d, eax
0x1400091a2  jmp     short loc_1400091A7
0x1400091a4  mov     r13d, r10d
0x1400091a7  test    r12d, r12d
0x1400091aa  jnz     short loc_1400091BE
0x1400091ac  mov     r8d, r13d; Size
0x1400091af  xor     edx, edx; Val
0x1400091b1  mov     rcx, r15; void *
0x1400091b4  call    memset
0x1400091b9  jmp     loc_1400093A0
0x1400091be  mov     edx, [rbp+57h+arg_10]
0x1400091c1  cmp     r12d, edx
0x1400091c4  jz      loc_14000938E
0x1400091ca  mov     r11, [rbp+57h+var_58]
0x1400091ce  cmp     r8d, r11d
0x1400091d1  jnz     short loc_1400091E9
0x1400091d3  mov     rax, [rbx+38h]
0x1400091d7  cqo
0x1400091d9  idiv    [rbp+57h+var_48]
0x1400091dd  cmp     r12d, edx
0x1400091e0  jz      loc_14000938E
0x1400091e6  mov     edx, [rbp+57h+arg_10]
0x1400091e9  mov     rax, [rbx+20h]
0x1400091ed  mov     ecx, [rax+60h]
0x1400091f0  test    ecx, 0FF000000h
0x1400091f6  jz      short loc_140009236
0x1400091f8  mov     rax, [rbp+57h+var_50]
0x1400091fc  mov     ecx, 2; CompressionFormat
0x140009201  mov     [rsp+0C0h+WorkSpace], rax; WorkSpace
0x140009206  mov     r8d, r10d; UncompressedFragmentSize
0x140009209  lea     rax, [rbp+57h+arg_0]
0x14000920d  mov     rdx, r15; UncompressedFragment
0x140009210  mov     [rsp+0C0h+FinalUncompressedSize], rax; FinalUncompressedSize
0x140009215  mov     [rsp+0C0h+FragmentOffset], r9d; FragmentOffset
0x14000921a  mov     r9, [rbp+57h+CompressedBuffer]; CompressedBuffer
0x14000921e  mov     [rsp+0C0h+CompressedBufferSize], r12d; CompressedBufferSize
0x140009223  call    cs:__imp_RtlDecompressFragment
0x14000922a  nop     dword ptr [rax+rax+00h]
0x14000922f  mov     edi, eax
0x140009231  jmp     loc_1400093A0
0x140009236  cmp     r8d, r11d
0x140009239  jnz     short loc_14000924A
0x14000923b  mov     r15d, [rbx+38h]
0x14000923f  mov     eax, edx
0x140009241  imul    eax, r8d
0x140009245  sub     r15d, eax
0x140009248  jmp     short loc_14000924D
0x14000924a  mov     r15d, edx
0x14000924d  bt      ecx, 12h
0x140009251  jnb     short loc_1400092BD
0x140009253  test    r9d, r9d
0x140009256  jnz     short loc_140009261
0x140009258  cmp     r13d, r15d
0x14000925b  jz      loc_1400092EC
0x140009261  mov     r14, [rbp+57h+var_60]
0x140009265  mov     r10d, r15d
0x140009268  mov     [rbp+57h+arg_0], r15d
0x14000926c  mov     r15, [rbp+57h+var_80]
0x140009270  mov     rax, [rbx+20h]
0x140009274  mov     ecx, [rax+60h]
0x140009277  bt      ecx, 15h
0x14000927b  jnb     short loc_1400092F8
0x14000927d  mov     rax, [rbp+57h+var_50]
0x140009281  mov     ecx, 4
0x140009286  mov     r9, [rbp+57h+CompressedBuffer]
0x14000928a  mov     r8d, r10d
0x14000928d  mov     [rsp+0C0h+FinalUncompressedSize], rax
0x140009292  mov     rdx, r14
0x140009295  lea     rax, [rbp+57h+var_80]
0x140009299  mov     dword ptr [rbp+57h+var_80], 0
0x1400092a0  mov     qword ptr [rsp+0C0h+FragmentOffset], rax
0x1400092a5  mov     [rsp+0C0h+CompressedBufferSize], r12d
0x1400092aa  call    cs:__imp_RtlDecompressBufferEx
0x1400092b1  nop     dword ptr [rax+rax+00h]
0x1400092b6  mov     edi, eax
0x1400092b8  jmp     loc_140009366
0x1400092bd  xor     r14d, r14d
0x1400092c0  test    ecx, 220000h
0x1400092c6  jz      short loc_14000926C
0x1400092c8  test    r9d, r9d
0x1400092cb  jnz     short loc_140009261
0x1400092cd  cmp     r13d, r15d
0x1400092d0  jnz     short loc_140009261
0x1400092d2  mov     rcx, [rbx+48h]
0x1400092d6  test    rcx, rcx
0x1400092d9  jz      short loc_140009261
0x1400092db  call    WofIsMdlInvariant
0x1400092e0  test    al, al
0x1400092e2  jz      loc_140009261
0x1400092e8  mov     r10d, [rbp+57h+arg_0]
0x1400092ec  mov     r15, [rbp+57h+var_80]
0x1400092f0  mov     r14, r15
0x1400092f3  jmp     loc_140009270
0x1400092f8  bt      ecx, 11h
0x1400092fc  jnb     short loc_14000932E
0x1400092fe  mov     rax, [rbp+57h+CompressedBuffer]
0x140009302  mov     r9d, r10d
0x140009305  mov     r8d, [rbp+57h+arg_10]
0x140009309  mov     rdx, r14
0x14000930c  mov     [rsp+0C0h+FragmentOffset], r12d
0x140009311  mov     rcx, rsi
0x140009314  mov     qword ptr [rsp+0C0h+CompressedBufferSize], rax
0x140009319  call    WIM_XpressDecode
0x14000931e  mov     r10d, [rbp+57h+arg_0]
0x140009322  cmp     r10d, eax
0x140009325  jz      short loc_14000936A
0x140009327  mov     edi, 0C0000001h
0x14000932c  jmp     short loc_14000936A
0x14000932e  bt      ecx, 12h
0x140009332  jnb     short loc_14000936A
0x140009334  mov     r8, [rbp+57h+CompressedBuffer]
0x140009338  lea     rax, [rbp+57h+arg_0]
0x14000933c  mov     [rsp+0C0h+FinalUncompressedSize], rax
0x140009341  mov     r9d, r12d
0x140009344  mov     edx, r10d
0x140009347  mov     qword ptr [rsp+0C0h+CompressedBufferSize], r14
0x14000934c  mov     rcx, rsi
0x14000934f  call    LZX_Decode
0x140009354  test    eax, eax
0x140009356  mov     rcx, rsi
0x140009359  mov     eax, 0C0000001h
0x14000935e  cmovnz  edi, eax
0x140009361  call    LZX_DecodeNewGroup
0x140009366  mov     r10d, [rbp+57h+arg_0]
0x14000936a  test    edi, edi
0x14000936c  js      loc_1400093FD
0x140009372  cmp     r14, r15
0x140009375  jz      short loc_1400093A8
0x140009377  mov     edx, [rbp+57h+var_68]
0x14000937a  mov     rcx, r15; void *
0x14000937d  add     rdx, r14; Src
0x140009380  mov     r8d, r13d; Size
0x140009383  mov     [rbp+57h+arg_0], r13d
0x140009387  call    memmove
0x14000938c  jmp     short loc_1400093A4
0x14000938e  mov     edx, r9d
0x140009391  mov     rcx, r15; void *
0x140009394  add     rdx, [rbp+57h+CompressedBuffer]; Src
0x140009398  mov     r8d, r13d; Size
0x14000939b  call    memmove
0x1400093a0  test    edi, edi
0x1400093a2  js      short loc_1400093FD
0x1400093a4  mov     r10d, [rbp+57h+arg_0]
0x1400093a8  mov     r8, [rbp+57h+var_70]
0x1400093ac  xor     r9d, r9d
0x1400093af  mov     r13d, [rbp+57h+arg_10]
0x1400093b3  inc     r8d
0x1400093b6  mov     eax, r10d
0x1400093b9  add     r15, rax
0x1400093bc  mov     qword ptr [rbp+57h+var_68], r9
0x1400093c0  mov     eax, r12d
0x1400093c3  add     [rbp+57h+CompressedBuffer], rax
0x1400093c7  mov     eax, dword ptr [rbp+57h+Size]
0x1400093ca  mov     r12d, [rbp+57h+arg_18]
0x1400093ce  sub     eax, r10d
0x1400093d1  add     r12d, r10d
0x1400093d4  mov     [rbp+57h+var_80], r15
0x1400093d8  cmp     cs:WimSqmIsOptedIn, r9b
0x1400093df  mov     dword ptr [rbp+57h+Size], eax
0x1400093e2  mov     [rbp+57h+arg_18], r12d
0x1400093e6  mov     [rbp+57h+var_70], r8
0x1400093ea  jz      loc_14000913D
0x1400093f0  lock inc cs:WimDecompressionCount
0x1400093f8  jmp     loc_14000913D
0x1400093fd  cmp     cs:WimSqmIsOptedIn, 0
0x140009404  jz      short loc_140009446
0x140009406  mov     r12, [rbp+57h+CompressedBuffer]
0x14000940a  mov     eax, dword ptr [rbp+57h+Size]
0x14000940d  mov     [rbp+57h+CompressedBuffer], r12
0x140009411  mov     r12d, [rbp+57h+arg_18]
0x140009415  mov     [rbp+57h+arg_18], r12d
0x140009419  mov     dword ptr [rbp+57h+Size], eax
0x14000941c  mov     [rbp+57h+var_80], r15
0x140009420  lock inc cs:WimDecompressionFailureCount
0x140009428  mov     r8, [rbp+57h+var_70]
0x14000942c  mov     r9, qword ptr [rbp+57h+var_68]
0x140009430  mov     r13d, [rbp+57h+arg_10]
0x140009434  mov     [rbp+57h+var_70], r8
0x140009438  mov     qword ptr [rbp+57h+var_68], r9
0x14000943c  test    edi, edi
0x14000943e  jns     loc_14000913D
0x140009444  jmp     short loc_14000944A
0x140009446  mov     r12d, [rbp+57h+arg_18]
0x14000944a  mov     r14, [rbp+57h+var_60]
0x14000944e  mov     [rbx+6Ch], edi
0x140009451  mov     [rbx+70h], r12d
  ... truncated ...
```
