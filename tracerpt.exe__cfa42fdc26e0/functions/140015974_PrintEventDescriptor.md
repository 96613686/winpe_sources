# PrintEventDescriptor

- ea: `0x140015974`
- end: `0x140015e7b`
- name: `PrintEventDescriptor`
- size: `1287`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x14001489c`

## callees

- `0x140013d50`
- `0x140013e10`
- `0x140013f20`
- `0x140015974`
- `0x140015e84`
- `0x140016360`
- `0x1400164c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015ab1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015bc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015c7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015d15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015ab1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015bc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015c7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140015d15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015ac3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015bdb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015c8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015d27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015ac3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015bdb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015c8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140015d27`

## string_xrefs

- `0x1400159e4`: `template="tid_%d" `
- `0x140015d69`: `task="task%d" `

## pseudocode

```c
void __fastcall PrintEventDescriptor(__int64 a1, __int64 a2)
{
  int v2; // r12d
  __int64 v5; // r8
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // r14
  int v11; // ebp
  _DWORD *i; // rsi
  wchar_t *v13; // r8
  char v14; // r15
  HANDLE ProcessHeap; // rax
  _DWORD *v16; // rax
  int v17; // ecx
  _QWORD *v18; // rax
  __int64 *v19; // r8
  unsigned int v20; // eax
  __int64 v21; // r14
  int v22; // ebp
  _DWORD *j; // rsi
  char v24; // r15
  HANDLE v25; // rax
  _DWORD *v26; // rax
  int v27; // ecx
  _QWORD *v28; // rax
  __int64 v29; // rax
  const wchar_t *v30; // rdx
  __int64 v31; // r14
  int v32; // ebp
  _OWORD *k; // rsi
  HANDLE v34; // rax
  _OWORD *v35; // rax
  int v36; // ecx
  _QWORD *v37; // rax
  __int64 v38; // r8
  __int64 v39; // r14
  int v40; // ebp
  _DWORD *m; // rsi
  __int16 v42; // r15
  HANDLE v43; // rax
  _DWORD *v44; // rax
  int v45; // ecx
  _QWORD *v46; // rax
  __int64 v47; // rbp
  __int64 n; // rbp
  unsigned __int64 v49; // rsi
  unsigned int v50; // eax
  __int64 *ii; // r8
  unsigned int v52; // eax

  if ( !a1 )
    return;
  v2 = *(_DWORD *)(a1 + 48);
  if ( v2 == 1 )
  {
    v5 = *(unsigned int *)(a2 + 24);
    *(_DWORD *)(a2 + 24) = v5 + 1;
  }
  else
  {
    v5 = *(unsigned __int16 *)(a1 + 32);
  }
  TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"\t\t\t<event value=\"%d\" ", v5);
  TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"version=\"%d\" ", *(unsigned __int8 *)(a1 + 34));
  if ( *(_DWORD *)(a1 + 100) )
  {
    v6 = AddTemplate(a2, a1);
    TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"template=\"tid_%d\" ", v6);
  }
  if ( *(_DWORD *)(a1 + 72) )
  {
    if ( v2 == 1 )
    {
      v7 = AddString(a2, a1 + *(unsigned int *)(a1 + 72));
      v8 = AddMofOpcode(a2, *(unsigned __int8 *)(a1 + 37), a1 + 16, v7);
      TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"opcode=\"opcode%d\" ", v8);
    }
    else
    {
      v9 = 0;
      while ( qword_140060188[2 * v9] != *(unsigned __int8 *)(a1 + 37) )
      {
        if ( ++v9 >= 0x1A )
          goto LABEL_13;
      }
      v13 = (&off_140060180)[2 * v9];
      if ( v13 )
      {
        TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"opcode=\"%ws\" ", v13, a1 + *(unsigned int *)(a1 + 72));
        goto LABEL_25;
      }
LABEL_13:
      v10 = a2 + 128;
      v11 = AddString(a2, a1 + *(unsigned int *)(a1 + 72));
      for ( i = *(_DWORD **)(a2 + 128); i != (_DWORD *)v10; i = *(_DWORD **)i )
      {
        if ( i[4] == v11 )
        {
          if ( i )
            goto LABEL_24;
          break;
        }
      }
      v14 = *(_BYTE *)(a1 + 37);
      ProcessHeap = GetProcessHeap();
      v16 = HeapAlloc(ProcessHeap, 8u, 0x20u);
      i = v16;
      if ( v16 )
      {
        v16[4] = v11;
        *((_BYTE *)v16 + 20) = v14;
        v17 = *(_DWORD *)(a2 + 120);
        *(_DWORD *)(a2 + 120) = v17 + 1;
        v16[6] = v17;
        v18 = *(_QWORD **)(a2 + 136);
        *(_QWORD *)i = v10;
        *((_QWORD *)i + 1) = v18;
        *v18 = i;
        *(_QWORD *)(a2 + 136) = i;
      }
      else
      {
        RaiseAllocationFailure();
      }
LABEL_24:
      TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"opcode=\"opcode%d\" ", (unsigned int)i[6]);
    }
  }
LABEL_25:
  if ( *(_DWORD *)(a1 + 60) )
  {
    v19 = *(__int64 **)(a2 + 32);
    if ( v19 != (__int64 *)(a2 + 32) )
    {
      while ( *((_BYTE *)v19 + 28) != *(_BYTE *)(a1 + 35) )
      {
        v19 = (__int64 *)*v19;
        if ( v19 == (__int64 *)(a2 + 32) )
          goto LABEL_32;
      }
      if ( v19 )
        TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"channel=\"channel%d\" ", *((unsigned int *)v19 + 8));
    }
  }
LABEL_32:
  if ( *(_DWORD *)(a1 + 56) )
  {
    v20 = 0;
    while ( qword_140060328[2 * v20] != *(unsigned __int8 *)(a1 + 36) )
    {
      if ( ++v20 >= 0x10 )
        goto LABEL_36;
    }
    if ( (&off_140060320)[2 * v20] )
    {
      TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"level=\"%ws\" ");
      goto LABEL_48;
    }
LABEL_36:
    v21 = a2 + 80;
    v22 = AddString(a2, a1 + *(unsigned int *)(a1 + 56));
    for ( j = *(_DWORD **)(a2 + 80); j != (_DWORD *)v21; j = *(_DWORD **)j )
    {
      if ( j[4] == v22 )
      {
        if ( j )
          goto LABEL_47;
        break;
      }
    }
    v24 = *(_BYTE *)(a1 + 36);
    v25 = GetProcessHeap();
    v26 = HeapAlloc(v25, 8u, 0x20u);
    j = v26;
    if ( v26 )
    {
      v26[4] = v22;
      *((_BYTE *)v26 + 20) = v24;
      v27 = *(_DWORD *)(a2 + 72);
      *(_DWORD *)(a2 + 72) = v27 + 1;
      v26[6] = v27;
      v28 = *(_QWORD **)(a2 + 88);
      *(_QWORD *)j = v21;
      *((_QWORD *)j + 1) = v28;
      *v28 = j;
      *(_QWORD *)(a2 + 88) = j;
    }
    else
    {
      RaiseAllocationFailure();
    }
LABEL_47:
    TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"level=\"level%d\" ", (unsigned int)j[6]);
  }
LABEL_48:
  v29 = *(unsigned int *)(a1 + 68);
  if ( v2 == 1 )
  {
    v30 = (const wchar_t *)(a1 + v29);
    if ( !(_DWORD)v29 )
      v30 = L"(none)";
    v31 = a2 + 176;
    v32 = AddString(a2, v30);
    for ( k = *(_OWORD **)(a2 + 176); k != (_OWORD *)v31; k = *(_OWORD **)k )
    {
      if ( *((_QWORD *)k + 2) == *(_QWORD *)(a1 + 16) && *((_QWORD *)k + 3) == *(_QWORD *)(a1 + 24) )
      {
        if ( k )
          goto LABEL_61;
        break;
      }
    }
    v34 = GetProcessHeap();
    v35 = HeapAlloc(v34, 8u, 0x28u);
    k = v35;
    if ( v35 )
    {
      v35[1] = *(_OWORD *)(a1 + 16);
      v36 = *(_DWORD *)(a2 + 168);
      *(_DWORD *)(a2 + 168) = v36 + 1;
      *((_DWORD *)v35 + 9) = v36;
      *((_DWORD *)v35 + 8) = v32;
      v37 = *(_QWORD **)(a2 + 184);
      *(_QWORD *)k = v31;
      *((_QWORD *)k + 1) = v37;
      *v37 = k;
      *(_QWORD *)(a2 + 184) = k;
    }
    else
    {
      RaiseAllocationFailure();
    }
LABEL_61:
    v38 = *((unsigned int *)k + 9);
LABEL_73:
    TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"task=\"task%d\" ", v38);
    goto LABEL_74;
  }
  if ( (_DWORD)v29 )
  {
    v39 = a2 + 104;
    v40 = AddString(a2, a1 + v29);
    for ( m = *(_DWORD **)(a2 + 104); m != (_DWORD *)v39; m = *(_DWORD **)m )
    {
      if ( m[4] == v40 )
      {
        if ( m )
          goto LABEL_72;
        break;
      }
    }
    v42 = *(_WORD *)(a1 + 38);
    v43 = GetProcessHeap();
    v44 = HeapAlloc(v43, 8u, 0x20u);
    m = v44;
    if ( v44 )
    {
      v44[4] = v40;
      *((_WORD *)v44 + 10) = v42;
      v45 = *(_DWORD *)(a2 + 96);
      *(_DWORD *)(a2 + 96) = v45 + 1;
      v44[6] = v45;
      v46 = *(_QWORD **)(a2 + 112);
      *(_QWORD *)m = v39;
      *((_QWORD *)m + 1) = v46;
      *v46 = m;
      *(_QWORD *)(a2 + 112) = m;
    }
    else
    {
      RaiseAllocationFailure();
    }
LABEL_72:
    v38 = (unsigned int)m[6];
    goto LABEL_73;
  }
LABEL_74:
  if ( *(_DWORD *)(a1 + 64) )
  {
    v47 = *(_QWORD *)(a1 + 40);
    TracerptFPutws((wchar_t *)L"keywords=\"", *(struct _iobuf **)a2);
    for ( n = v47 & 0xFFFFFFFFFFFFFFLL; n; n &= ~v49 )
    {
      v49 = ((n ^ (unsigned __int64)(n - 1)) + 1) >> 1;
      v50 = 0;
      while ( qword_140060088[2 * v50] != v49 )
      {
        if ( ++v50 >= 0x10 )
          goto LABEL_79;
      }
      if ( (&off_140060080)[2 * v50] )
      {
        TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"%ws ");
        continue;
      }
LABEL_79:
      for ( ii = *(__int64 **)(a2 + 56); ii != (__int64 *)(a2 + 56); ii = (__int64 *)*ii )
      {
        if ( ii[3] == v49 )
        {
          if ( ii )
            TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"keyword%d ", *((unsigned int *)ii + 8));
          break;
        }
      }
    }
    TracerptFPutws((wchar_t *)L"\" ", *(struct _iobuf **)a2);
  }
  if ( *(_DWORD *)(a1 + 76) )
  {
    v52 = AddString(a2, a1 + *(unsigned int *)(a1 + 76));
    TracerptFWPrintf(*(struct _iobuf **)a2, (wchar_t *)L"message=\"$(string.string%d)\" ", v52);
  }
  TracerptFPutws((wchar_t *)L"/>\r\n", *(struct _iobuf **)a2);
}

```

## disassembly

```asm
0x140015974  test    rcx, rcx
0x140015977  jz      locret_140015E7A
0x14001597d  push    rbx
0x14001597e  push    rbp
0x14001597f  push    rsi
0x140015980  push    rdi
0x140015981  push    r12
0x140015983  push    r14
0x140015985  push    r15
0x140015987  sub     rsp, 20h
0x14001598b  mov     r12d, [rcx+30h]
0x14001598f  mov     rbx, rdx
0x140015992  mov     rdi, rcx
0x140015995  cmp     r12d, 1
0x140015999  jnz     short loc_1400159A8
0x14001599b  mov     r8d, [rdx+18h]
0x14001599f  lea     eax, [r8+1]
0x1400159a3  mov     [rdx+18h], eax
0x1400159a6  jmp     short loc_1400159AD
0x1400159a8  movzx   r8d, word ptr [rcx+20h]
0x1400159ad  mov     rcx, [rbx]; struct _iobuf *
0x1400159b0  lea     rdx, aEventValueD; "\t\t\t<event value=\"%d\" "
0x1400159b7  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400159bc  movzx   r8d, byte ptr [rdi+22h]
0x1400159c1  lea     rdx, aVersionD; "version=\"%d\" "
0x1400159c8  mov     rcx, [rbx]; struct _iobuf *
0x1400159cb  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400159d0  cmp     dword ptr [rdi+64h], 0
0x1400159d4  jz      short loc_1400159F3
0x1400159d6  mov     rdx, rdi
0x1400159d9  mov     rcx, rbx
0x1400159dc  call    AddTemplate
0x1400159e1  mov     rcx, [rbx]; struct _iobuf *
0x1400159e4  lea     rdx, aTemplateTidD; "template=\"tid_%d\" "
0x1400159eb  mov     r8d, eax
0x1400159ee  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x1400159f3  cmp     dword ptr [rdi+48h], 0
0x1400159f7  lea     rsi, cs:140000000h
0x1400159fe  jz      loc_140015B17
0x140015a04  mov     r9d, [rdi+48h]
0x140015a08  add     r9, rdi
0x140015a0b  cmp     r12d, 1
0x140015a0f  jnz     short loc_140015A46
0x140015a11  mov     rdx, r9
0x140015a14  mov     rcx, rbx
0x140015a17  call    AddString
0x140015a1c  movzx   edx, byte ptr [rdi+25h]
0x140015a20  lea     r8, [rdi+10h]
0x140015a24  mov     r9d, eax
0x140015a27  mov     rcx, rbx
0x140015a2a  call    AddMofOpcode
0x140015a2f  mov     rcx, [rbx]; struct _iobuf *
0x140015a32  lea     rdx, aOpcodeOpcodeD; "opcode=\"opcode%d\" "
0x140015a39  mov     r8d, eax
0x140015a3c  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140015a41  jmp     loc_140015B17
0x140015a46  movzx   edx, byte ptr [rdi+25h]
0x140015a4a  xor     eax, eax
0x140015a4c  mov     ecx, eax
0x140015a4e  add     rcx, rcx
0x140015a51  cmp     rva qword_140060188[rsi+rcx*8], rdx
0x140015a59  jz      short loc_140015A7B
0x140015a5b  inc     eax
0x140015a5d  cmp     eax, 1Ah
0x140015a60  jb      short loc_140015A4C
0x140015a62  mov     rdx, r9
0x140015a65  mov     rcx, rbx
0x140015a68  call    AddString
0x140015a6d  lea     r14, [rbx+80h]
0x140015a74  mov     ebp, eax
0x140015a76  mov     rsi, [r14]
0x140015a79  jmp     short loc_140015AA1
0x140015a7b  mov     r8, rva off_140060180[rsi+rcx*8]; "win:Info" ...
0x140015a83  test    r8, r8
0x140015a86  jz      short loc_140015A62
0x140015a88  mov     rcx, [rbx]; struct _iobuf *
0x140015a8b  lea     rdx, aOpcodeWs; "opcode=\"%ws\" "
0x140015a92  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140015a97  jmp     short loc_140015B17
0x140015a99  cmp     [rsi+10h], ebp
0x140015a9c  jz      short loc_140015AA8
0x140015a9e  mov     rsi, [rsi]
0x140015aa1  cmp     rsi, r14
0x140015aa4  jnz     short loc_140015A99
0x140015aa6  jmp     short loc_140015AAD
0x140015aa8  test    rsi, rsi
0x140015aab  jnz     short loc_140015AFD
0x140015aad  mov     r15b, [rdi+25h]
0x140015ab1  call    cs:__imp_GetProcessHeap
0x140015ab7  mov     edx, 8; dwFlags
0x140015abc  mov     rcx, rax; hHeap
0x140015abf  lea     r8d, [rdx+18h]; dwBytes
0x140015ac3  call    cs:__imp_HeapAlloc
0x140015ac9  mov     rsi, rax
0x140015acc  test    rax, rax
0x140015acf  jz      short loc_140015AF8
0x140015ad1  mov     [rax+10h], ebp
0x140015ad4  mov     [rax+14h], r15b
0x140015ad8  mov     ecx, [rbx+78h]
0x140015adb  lea     eax, [rcx+1]
0x140015ade  mov     [rbx+78h], eax
0x140015ae1  mov     [rsi+18h], ecx
0x140015ae4  mov     rax, [r14+8]
0x140015ae8  mov     [rsi], r14
0x140015aeb  mov     [rsi+8], rax
0x140015aef  mov     [rax], rsi
0x140015af2  mov     [r14+8], rsi
0x140015af6  jmp     short loc_140015AFD
0x140015af8  call    RaiseAllocationFailure
0x140015afd  mov     r8d, [rsi+18h]
0x140015b01  lea     rdx, aOpcodeOpcodeD; "opcode=\"opcode%d\" "
0x140015b08  mov     rcx, [rbx]; struct _iobuf *
0x140015b0b  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140015b10  lea     rsi, cs:140000000h
0x140015b17  cmp     dword ptr [rdi+3Ch], 0
0x140015b1b  jz      short loc_140015B54
0x140015b1d  lea     rax, [rbx+20h]
0x140015b21  mov     r8, [rax]
0x140015b24  cmp     r8, rax
0x140015b27  jz      short loc_140015B54
0x140015b29  mov     cl, [rdi+23h]
0x140015b2c  cmp     [r8+1Ch], cl
0x140015b30  jz      short loc_140015B3C
0x140015b32  mov     r8, [r8]
0x140015b35  cmp     r8, rax
0x140015b38  jnz     short loc_140015B2C
0x140015b3a  jmp     short loc_140015B54
0x140015b3c  test    r8, r8
0x140015b3f  jz      short loc_140015B54
0x140015b41  mov     r8d, [r8+20h]
0x140015b45  lea     rdx, aChannelChannel; "channel=\"channel%d\" "
0x140015b4c  mov     rcx, [rbx]; struct _iobuf *
0x140015b4f  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140015b54  cmp     dword ptr [rdi+38h], 0
0x140015b58  jz      loc_140015C28
0x140015b5e  movzx   edx, byte ptr [rdi+24h]
0x140015b62  xor     eax, eax
0x140015b64  mov     ecx, eax
0x140015b66  add     rcx, rcx
0x140015b69  cmp     rva qword_140060328[rsi+rcx*8], rdx
0x140015b71  jz      short loc_140015B93
0x140015b73  inc     eax
0x140015b75  cmp     eax, 10h
0x140015b78  jb      short loc_140015B64
0x140015b7a  mov     edx, [rdi+38h]
0x140015b7d  mov     rcx, rbx
0x140015b80  add     rdx, rdi
0x140015b83  call    AddString
0x140015b88  lea     r14, [rbx+50h]
0x140015b8c  mov     ebp, eax
0x140015b8e  mov     rsi, [r14]
0x140015b91  jmp     short loc_140015BB9
0x140015b93  mov     r8, rva off_140060320[rsi+rcx*8]; "win:LogAlways" ...
0x140015b9b  test    r8, r8
0x140015b9e  jz      short loc_140015B7A
0x140015ba0  mov     rcx, [rbx]; struct _iobuf *
0x140015ba3  lea     rdx, aLevelWs; "level=\"%ws\" "
0x140015baa  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140015baf  jmp     short loc_140015C28
0x140015bb1  cmp     [rsi+10h], ebp
0x140015bb4  jz      short loc_140015BC0
0x140015bb6  mov     rsi, [rsi]
0x140015bb9  cmp     rsi, r14
0x140015bbc  jnz     short loc_140015BB1
0x140015bbe  jmp     short loc_140015BC5
0x140015bc0  test    rsi, rsi
0x140015bc3  jnz     short loc_140015C15
0x140015bc5  mov     r15b, [rdi+24h]
0x140015bc9  call    cs:__imp_GetProcessHeap
0x140015bcf  mov     edx, 8; dwFlags
0x140015bd4  mov     rcx, rax; hHeap
0x140015bd7  lea     r8d, [rdx+18h]; dwBytes
0x140015bdb  call    cs:__imp_HeapAlloc
0x140015be1  mov     rsi, rax
0x140015be4  test    rax, rax
0x140015be7  jz      short loc_140015C10
0x140015be9  mov     [rax+10h], ebp
0x140015bec  mov     [rax+14h], r15b
0x140015bf0  mov     ecx, [rbx+48h]
0x140015bf3  lea     eax, [rcx+1]
0x140015bf6  mov     [rbx+48h], eax
0x140015bf9  mov     [rsi+18h], ecx
0x140015bfc  mov     rax, [r14+8]
0x140015c00  mov     [rsi], r14
0x140015c03  mov     [rsi+8], rax
0x140015c07  mov     [rax], rsi
0x140015c0a  mov     [r14+8], rsi
0x140015c0e  jmp     short loc_140015C15
0x140015c10  call    RaiseAllocationFailure
0x140015c15  mov     r8d, [rsi+18h]
0x140015c19  lea     rdx, aLevelLevelD; "level=\"level%d\" "
0x140015c20  mov     rcx, [rbx]; struct _iobuf *
0x140015c23  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140015c28  mov     eax, [rdi+44h]
0x140015c2b  cmp     r12d, 1
0x140015c2f  jnz     loc_140015CDD
0x140015c35  lea     rdx, [rdi+rax]
0x140015c39  test    eax, eax
0x140015c3b  jnz     short loc_140015C44
0x140015c3d  lea     rdx, aNone; "(none)"
0x140015c44  mov     rcx, rbx
0x140015c47  call    AddString
0x140015c4c  lea     r14, [rbx+0B0h]
0x140015c53  mov     ebp, eax
0x140015c55  mov     rsi, [r14]
0x140015c58  jmp     short loc_140015C71
0x140015c5a  mov     rcx, [rsi+10h]
0x140015c5e  cmp     rcx, [rdi+10h]
0x140015c62  jnz     short loc_140015C6E
0x140015c64  mov     rax, [rsi+18h]
0x140015c68  cmp     rax, [rdi+18h]
0x140015c6c  jz      short loc_140015C78
0x140015c6e  mov     rsi, [rsi]
0x140015c71  cmp     rsi, r14
0x140015c74  jnz     short loc_140015C5A
0x140015c76  jmp     short loc_140015C7D
0x140015c78  test    rsi, rsi
0x140015c7b  jnz     short loc_140015CD4
0x140015c7d  call    cs:__imp_GetProcessHeap
0x140015c83  mov     edx, 8; dwFlags
0x140015c88  mov     rcx, rax; hHeap
0x140015c8b  lea     r8d, [rdx+20h]; dwBytes
0x140015c8f  call    cs:__imp_HeapAlloc
0x140015c95  mov     rsi, rax
0x140015c98  test    rax, rax
0x140015c9b  jz      short loc_140015CCF
0x140015c9d  movups  xmm0, xmmword ptr [rdi+10h]
0x140015ca1  movdqu  xmmword ptr [rax+10h], xmm0
0x140015ca6  mov     ecx, [rbx+0A8h]
0x140015cac  lea     eax, [rcx+1]
0x140015caf  mov     [rbx+0A8h], eax
0x140015cb5  mov     [rsi+24h], ecx
0x140015cb8  mov     [rsi+20h], ebp
0x140015cbb  mov     rax, [r14+8]
0x140015cbf  mov     [rsi], r14
0x140015cc2  mov     [rsi+8], rax
0x140015cc6  mov     [rax], rsi
0x140015cc9  mov     [r14+8], rsi
0x140015ccd  jmp     short loc_140015CD4
0x140015ccf  call    RaiseAllocationFailure
0x140015cd4  mov     r8d, [rsi+24h]
0x140015cd8  jmp     loc_140015D66
0x140015cdd  test    eax, eax
0x140015cdf  jz      loc_140015D75
0x140015ce5  lea     rdx, [rdi+rax]
0x140015ce9  mov     rcx, rbx
0x140015cec  call    AddString
0x140015cf1  lea     r14, [rbx+68h]
0x140015cf5  mov     ebp, eax
0x140015cf7  mov     rsi, [r14]
0x140015cfa  jmp     short loc_140015D04
0x140015cfc  cmp     [rsi+10h], ebp
0x140015cff  jz      short loc_140015D0B
0x140015d01  mov     rsi, [rsi]
0x140015d04  cmp     rsi, r14
0x140015d07  jnz     short loc_140015CFC
0x140015d09  jmp     short loc_140015D10
0x140015d0b  test    rsi, rsi
0x140015d0e  jnz     short loc_140015D62
0x140015d10  movzx   r15d, word ptr [rdi+26h]
0x140015d15  call    cs:__imp_GetProcessHeap
0x140015d1b  mov     edx, 8; dwFlags
0x140015d20  mov     rcx, rax; hHeap
0x140015d23  lea     r8d, [rdx+18h]; dwBytes
0x140015d27  call    cs:__imp_HeapAlloc
0x140015d2d  mov     rsi, rax
0x140015d30  test    rax, rax
0x140015d33  jz      short loc_140015D5D
0x140015d35  mov     [rax+10h], ebp
0x140015d38  mov     [rax+14h], r15w
0x140015d3d  mov     ecx, [rbx+60h]
0x140015d40  lea     eax, [rcx+1]
0x140015d43  mov     [rbx+60h], eax
0x140015d46  mov     [rsi+18h], ecx
0x140015d49  mov     rax, [r14+8]
0x140015d4d  mov     [rsi], r14
0x140015d50  mov     [rsi+8], rax
0x140015d54  mov     [rax], rsi
0x140015d57  mov     [r14+8], rsi
0x140015d5b  jmp     short loc_140015D62
0x140015d5d  call    RaiseAllocationFailure
0x140015d62  mov     r8d, [rsi+18h]
0x140015d66  mov     rcx, [rbx]; struct _iobuf *
0x140015d69  lea     rdx, aTaskTaskD; "task=\"task%d\" "
0x140015d70  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140015d75  cmp     dword ptr [rdi+40h], 0
0x140015d79  jz      loc_140015E37
0x140015d7f  mov     rdx, [rbx]; struct _iobuf *
0x140015d82  lea     rcx, aKeywords_2; "keywords=\""
0x140015d89  mov     rbp, [rdi+28h]
0x140015d8d  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140015d92  mov     rax, 0FFFFFFFFFFFFFFh
0x140015d9c  and     rbp, rax
0x140015d9f  jz      loc_140015E28
0x140015da5  lea     r14, cs:140000000h
0x140015dac  lea     rsi, [rbp-1]
0x140015db0  xor     rsi, rbp
0x140015db3  inc     rsi
0x140015db6  shr     rsi, 1
0x140015db9  xor     eax, eax
  ... truncated ...
```
