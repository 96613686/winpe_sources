# SdbpMergeUpdateEntryIndexKeys

- ea: `0x14001f90c`
- end: `0x14001fc03`
- name: `SdbpMergeUpdateEntryIndexKeys`
- size: `759`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001cd7c`
- `0x14001d808`

## callees

- `0x14001008c`
- `0x140013898`
- `0x140013938`
- `0x140013e60`
- `0x140013f74`
- `0x140014380`
- `0x140018d48`
- `0x14001f90c`

## string_xrefs

- `0x14001fba0`: `SdbpMergeUpdateEntryIndexKeys`
- `0x14001fb8c`: `QUIRKS encountered without TAG_QUIRK_COMPONENT_CODE_ID child.`

## pseudocode

```c
__int64 __fastcall SdbpMergeUpdateEntryIndexKeys(
        unsigned __int64 *a1,
        unsigned __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  unsigned __int64 v5; // rax
  __int64 v6; // rdi
  unsigned __int64 v9; // r15
  __int64 v10; // rbx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  unsigned int v13; // r14d
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  unsigned __int8 v16; // cf
  __int64 v17; // rax
  unsigned __int64 v18; // rax
  __int64 v19; // rbp
  unsigned int FirstTag; // eax
  unsigned int v21; // esi
  __int64 v22; // rax
  int v23; // eax
  int TagDataSize; // eax
  __int64 MappedTagData; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int v29; // esi
  __int64 v30; // rax
  __int64 StringTagPtr; // rax
  unsigned int v32; // eax
  unsigned int v33; // eax
  __int64 v35; // [rsp+70h] [rbp+18h]

  v35 = a3;
  v5 = a1[2];
  v6 = a4;
  if ( v5 )
  {
    v9 = 0;
    while ( 1 )
    {
      v10 = 0;
      if ( v9 < v5 )
      {
        v11 = a1[1] * v9;
        if ( !is_mul_ok(a1[1], v9) || (v12 = a1[5], v10 = v12 + v11, v12 + v11 < v12) )
          v10 = 0;
      }
      v13 = *(_DWORD *)(v10 + 4);
      *(_DWORD *)(v10 + 8) = 0;
      if ( v13 )
      {
        if ( !a5 && (unsigned int)SdbFindFirstTag(v6, v13, 4120) )
        {
          *(_WORD *)(v10 + 14) = 4120;
          *(_QWORD *)(v10 + 16) = 0;
          *(_QWORD *)(v10 + 24) = 0;
          goto LABEL_54;
        }
      }
      else
      {
        v13 = *(_DWORD *)v10;
        v6 = a3;
      }
      if ( a2[2] )
      {
        v14 = 0;
        while ( 1 )
        {
          if ( v14 >= 0x40 )
          {
            v17 = *(_QWORD *)(v10 + 24);
            v16 = _bittest64(&v17, (unsigned __int8)(v14 - 64));
          }
          else
          {
            v15 = *(_QWORD *)(v10 + 16);
            v16 = _bittest64(&v15, v14);
          }
          if ( v16 )
            break;
          if ( ++v14 >= a2[2] )
            goto LABEL_36;
        }
        if ( !is_mul_ok(a2[1], v14) || (v18 = a2[5] + a2[1] * v14, v18 < a2[5]) )
          v18 = 0;
        v19 = *(_QWORD *)v18;
        *(_WORD *)(v10 + 14) = *(_WORD *)(*(_QWORD *)v18 + 6LL);
        FirstTag = SdbFindFirstTag(v6, v13, *(_WORD *)(v19 + 6));
        v21 = FirstTag;
        if ( FirstTag )
          v22 = SdbpTagToKey(v6, FirstTag, *(unsigned int *)(v19 + 32));
        else
          v22 = 0;
        *(_QWORD *)(v10 + 32) = v22;
        if ( v21 )
        {
          v23 = *(_WORD *)(v19 + 6) & 0xF000;
          if ( v23 == 4096 )
          {
            *(_DWORD *)(v10 + 48) = 0;
            MappedTagData = 0;
          }
          else if ( ((v23 - 24576) & 0xFFFFDFFF) != 0 )
          {
            TagDataSize = SdbGetTagDataSize(v6, v21);
            *(_DWORD *)(v10 + 48) = TagDataSize;
            if ( TagDataSize == 0x20000000 )
              return 3221227787LL;
            MappedTagData = SdbpGetMappedTagData(v6, v21);
          }
          else
          {
            *(_DWORD *)(v10 + 48) = 0;
            MappedTagData = SdbGetStringTagPtr(v6, v21);
          }
          v26 = 40;
          v27 = v10;
        }
        else
        {
          v26 = v10;
          *(_DWORD *)(v10 + 48) = 0;
          MappedTagData = 0;
          v27 = 40;
        }
        *(_QWORD *)(v27 + v26) = MappedTagData;
        *(_DWORD *)(v10 + 8) = v21;
      }
LABEL_36:
      if ( !*(_DWORD *)(v10 + 8) )
      {
        if ( *(_WORD *)(v10 + 12) == 28683 )
        {
          *(_WORD *)(v10 + 14) = 24577;
          v28 = SdbFindFirstTag(v6, v13, 24577);
          *(_DWORD *)(v10 + 8) = v28;
          v29 = v28;
          if ( v28 )
            v30 = SdbpTagToKey(v6, v28, 0);
          else
            v30 = 0;
          *(_QWORD *)(v10 + 32) = v30;
          if ( v29 )
            StringTagPtr = SdbGetStringTagPtr(v6, v29);
          else
            StringTagPtr = 0;
          *(_QWORD *)(v10 + 40) = StringTagPtr;
          goto LABEL_52;
        }
        if ( *(_WORD *)(v10 + 12) != 28715 )
        {
          *(_QWORD *)(v10 + 32) = 0;
          *(_WORD *)(v10 + 14) = 0;
          goto LABEL_51;
        }
        *(_WORD *)(v10 + 14) = 12290;
        v32 = SdbFindFirstTag(v6, v13, 12290);
        *(_DWORD *)(v10 + 8) = v32;
        if ( v32 )
        {
          *(_QWORD *)(v10 + 32) = (unsigned __int64)(unsigned __int16)SdbReadWORDTag(v6, v32, 0) << 16;
          v33 = SdbFindFirstTag(v6, v13, 12291);
          if ( v33 )
            *(_QWORD *)(v10 + 32) |= (unsigned __int16)SdbReadWORDTag(v6, v33, 0);
LABEL_51:
          *(_QWORD *)(v10 + 40) = 0;
LABEL_52:
          *(_DWORD *)(v10 + 48) = 0;
          goto LABEL_53;
        }
        *(_QWORD *)(v10 + 32) = 0;
        *(_DWORD *)(v10 + 48) = 0;
        *(_QWORD *)(v10 + 40) = 0;
        *(_WORD *)(v10 + 14) = 0;
        AslLogCallPrintf(
          1,
          "SdbpMergeUpdateEntryIndexKeys",
          2074,
          "QUIRKS encountered without TAG_QUIRK_COMPONENT_CODE_ID child.");
      }
LABEL_53:
      v6 = a4;
LABEL_54:
      v5 = a1[2];
      if ( ++v9 >= v5 )
        return 0;
      a3 = v35;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001f90c  mov     [rsp+arg_8], rbx
0x14001f911  mov     [rsp+arg_18], r9
0x14001f916  mov     [rsp+arg_10], r8
0x14001f91b  push    rbp
0x14001f91c  push    rsi
0x14001f91d  push    rdi
0x14001f91e  push    r12
0x14001f920  push    r13
0x14001f922  push    r14
0x14001f924  push    r15
0x14001f926  sub     rsp, 20h
0x14001f92a  mov     rax, [rcx+10h]
0x14001f92e  xor     ebp, ebp
0x14001f930  mov     rdi, r9
0x14001f933  mov     r12, rdx
0x14001f936  mov     r13, rcx
0x14001f939  test    rax, rax
0x14001f93c  jz      loc_14001FBEC
0x14001f942  mov     r15d, ebp
0x14001f945  mov     esi, 1018h
0x14001f94a  mov     rbx, rbp
0x14001f94d  cmp     r15, rax
0x14001f950  jnb     short loc_14001F96E
0x14001f952  mov     rax, r15
0x14001f955  mul     qword ptr [r13+8]
0x14001f959  test    rdx, rdx
0x14001f95c  jnz     short loc_14001F96B
0x14001f95e  mov     rcx, [r13+28h]
0x14001f962  lea     rbx, [rcx+rax]
0x14001f966  cmp     rbx, rcx
0x14001f969  jnb     short loc_14001F96E
0x14001f96b  mov     rbx, rbp
0x14001f96e  mov     r14d, [rbx+4]
0x14001f972  mov     [rbx+8], ebp
0x14001f975  test    r14d, r14d
0x14001f978  jz      short loc_14001F9A6
0x14001f97a  cmp     [rsp+58h+arg_20], ebp
0x14001f981  jnz     short loc_14001F9AC
0x14001f983  mov     r8d, esi
0x14001f986  mov     edx, r14d
0x14001f989  mov     rcx, rdi
0x14001f98c  call    SdbFindFirstTag
0x14001f991  test    eax, eax
0x14001f993  jz      short loc_14001F9AC
0x14001f995  mov     [rbx+0Eh], si
0x14001f999  mov     [rbx+10h], rbp
0x14001f99d  mov     [rbx+18h], rbp
0x14001f9a1  jmp     loc_14001FBCF
0x14001f9a6  mov     r14d, [rbx]
0x14001f9a9  mov     rdi, r8
0x14001f9ac  cmp     [r12+10h], rbp
0x14001f9b1  jbe     loc_14001FAB6
0x14001f9b7  mov     rdx, rbp
0x14001f9ba  cmp     rdx, 40h ; '@'
0x14001f9be  jnb     short loc_14001F9CA
0x14001f9c0  mov     rax, [rbx+10h]
0x14001f9c4  bt      rax, rdx
0x14001f9c8  jmp     short loc_14001F9DB
0x14001f9ca  lea     eax, [rdx+0C0h]
0x14001f9d0  movzx   ecx, al
0x14001f9d3  mov     rax, [rbx+18h]
0x14001f9d7  bt      rax, rcx
0x14001f9db  jb      short loc_14001F9EC
0x14001f9dd  inc     rdx
0x14001f9e0  cmp     rdx, [r12+10h]
0x14001f9e5  jb      short loc_14001F9BA
0x14001f9e7  jmp     loc_14001FAB6
0x14001f9ec  mov     rax, rdx
0x14001f9ef  mul     qword ptr [r12+8]
0x14001f9f4  test    rdx, rdx
0x14001f9f7  jnz     short loc_14001FA05
0x14001f9f9  add     rax, [r12+28h]
0x14001f9fe  cmp     rax, [r12+28h]
0x14001fa03  jnb     short loc_14001FA08
0x14001fa05  mov     rax, rbp
0x14001fa08  mov     rbp, [rax]
0x14001fa0b  mov     edx, r14d
0x14001fa0e  mov     rcx, rdi
0x14001fa11  movzx   eax, word ptr [rbp+6]
0x14001fa15  mov     [rbx+0Eh], ax
0x14001fa19  movzx   r8d, word ptr [rbp+6]
0x14001fa1e  call    SdbFindFirstTag
0x14001fa23  mov     esi, eax
0x14001fa25  test    eax, eax
0x14001fa27  jz      short loc_14001FA39
0x14001fa29  mov     r8d, [rbp+20h]
0x14001fa2d  mov     edx, eax
0x14001fa2f  mov     rcx, rdi
0x14001fa32  call    SdbpTagToKey
0x14001fa37  jmp     short loc_14001FA3B
0x14001fa39  xor     eax, eax
0x14001fa3b  mov     [rbx+20h], rax
0x14001fa3f  test    esi, esi
0x14001fa41  jz      short loc_14001FAA2
0x14001fa43  movzx   eax, word ptr [rbp+6]
0x14001fa47  and     eax, 0F000h
0x14001fa4c  cmp     eax, 1000h
0x14001fa51  jz      short loc_14001FA91
0x14001fa53  add     eax, 0FFFFA000h
0x14001fa58  mov     edx, esi
0x14001fa5a  mov     rcx, rdi
0x14001fa5d  test    eax, 0FFFFDFFFh
0x14001fa62  jz      short loc_14001FA85
0x14001fa64  call    SdbGetTagDataSize
0x14001fa69  mov     [rbx+30h], eax
0x14001fa6c  cmp     eax, 20000000h
0x14001fa71  jz      loc_14001FBE5
0x14001fa77  mov     edx, esi
0x14001fa79  mov     rcx, rdi
0x14001fa7c  call    SdbpGetMappedTagData
0x14001fa81  xor     ebp, ebp
0x14001fa83  jmp     short loc_14001FA98
0x14001fa85  xor     ebp, ebp
0x14001fa87  mov     [rbx+30h], ebp
0x14001fa8a  call    SdbGetStringTagPtr
0x14001fa8f  jmp     short loc_14001FA98
0x14001fa91  xor     ebp, ebp
0x14001fa93  mov     [rbx+30h], ebp
0x14001fa96  mov     eax, ebp
0x14001fa98  mov     ecx, 28h ; '('
0x14001fa9d  mov     rdx, rbx
0x14001faa0  jmp     short loc_14001FAAF
0x14001faa2  xor     ebp, ebp
0x14001faa4  mov     rcx, rbx
0x14001faa7  mov     [rbx+30h], ebp
0x14001faaa  mov     eax, ebp
0x14001faac  lea     edx, [rbp+28h]
0x14001faaf  mov     [rdx+rcx], rax
0x14001fab3  mov     [rbx+8], esi
0x14001fab6  cmp     [rbx+8], ebp
0x14001fab9  jnz     loc_14001FBCA
0x14001fabf  mov     eax, 700Bh
0x14001fac4  cmp     [rbx+0Ch], ax
0x14001fac8  jnz     short loc_14001FB1C
0x14001faca  mov     eax, 6001h
0x14001facf  mov     edx, r14d
0x14001fad2  mov     r8d, eax
0x14001fad5  mov     [rbx+0Eh], ax
0x14001fad9  mov     rcx, rdi
0x14001fadc  call    SdbFindFirstTag
0x14001fae1  mov     [rbx+8], eax
0x14001fae4  mov     esi, eax
0x14001fae6  test    eax, eax
0x14001fae8  jz      short loc_14001FAF9
0x14001faea  xor     r8d, r8d
0x14001faed  mov     edx, eax
0x14001faef  mov     rcx, rdi
0x14001faf2  call    SdbpTagToKey
0x14001faf7  jmp     short loc_14001FAFC
0x14001faf9  mov     rax, rbp
0x14001fafc  mov     [rbx+20h], rax
0x14001fb00  test    esi, esi
0x14001fb02  jz      short loc_14001FB10
0x14001fb04  mov     edx, esi
0x14001fb06  mov     rcx, rdi
0x14001fb09  call    SdbGetStringTagPtr
0x14001fb0e  jmp     short loc_14001FB13
0x14001fb10  mov     rax, rbp
0x14001fb13  mov     [rbx+28h], rax
0x14001fb17  jmp     loc_14001FBC7
0x14001fb1c  mov     eax, 702Bh
0x14001fb21  cmp     [rbx+0Ch], ax
0x14001fb25  jnz     loc_14001FBBB
0x14001fb2b  mov     eax, 3002h
0x14001fb30  mov     edx, r14d
0x14001fb33  mov     r8d, eax
0x14001fb36  mov     [rbx+0Eh], ax
0x14001fb3a  mov     rcx, rdi
0x14001fb3d  call    SdbFindFirstTag
0x14001fb42  mov     [rbx+8], eax
0x14001fb45  test    eax, eax
0x14001fb47  jz      short loc_14001FB8C
0x14001fb49  xor     r8d, r8d
0x14001fb4c  mov     edx, eax
0x14001fb4e  mov     rcx, rdi
0x14001fb51  call    SdbReadWORDTag
0x14001fb56  movzx   eax, ax
0x14001fb59  mov     r8d, 3003h
0x14001fb5f  shl     rax, 10h
0x14001fb63  mov     edx, r14d
0x14001fb66  mov     rcx, rdi
0x14001fb69  mov     [rbx+20h], rax
0x14001fb6d  call    SdbFindFirstTag
0x14001fb72  test    eax, eax
0x14001fb74  jz      short loc_14001FBC3
0x14001fb76  xor     r8d, r8d
0x14001fb79  mov     edx, eax
0x14001fb7b  mov     rcx, rdi
0x14001fb7e  call    SdbReadWORDTag
0x14001fb83  movzx   eax, ax
0x14001fb86  or      [rbx+20h], rax
0x14001fb8a  jmp     short loc_14001FBC3
0x14001fb8c  lea     r9, aQuirksEncounte; "QUIRKS encountered without TAG_QUIRK_CO"...
0x14001fb93  mov     [rbx+20h], rbp
0x14001fb97  mov     r8d, 81Ah
0x14001fb9d  mov     [rbx+30h], ebp
0x14001fba0  lea     rdx, aSdbpmergeupdat; "SdbpMergeUpdateEntryIndexKeys"
0x14001fba7  mov     [rbx+28h], rbp
0x14001fbab  mov     ecx, 1
0x14001fbb0  mov     [rbx+0Eh], bp
0x14001fbb4  call    AslLogCallPrintf
0x14001fbb9  jmp     short loc_14001FBCA
0x14001fbbb  mov     [rbx+20h], rbp
0x14001fbbf  mov     [rbx+0Eh], bp
0x14001fbc3  mov     [rbx+28h], rbp
0x14001fbc7  mov     [rbx+30h], ebp
0x14001fbca  mov     rdi, [rsp+58h+arg_18]
0x14001fbcf  mov     rax, [r13+10h]
0x14001fbd3  inc     r15
0x14001fbd6  cmp     r15, rax
0x14001fbd9  jnb     short loc_14001FBEC
0x14001fbdb  mov     r8, [rsp+58h+arg_10]
0x14001fbe0  jmp     loc_14001F945
0x14001fbe5  mov     eax, 0C000090Bh
0x14001fbea  jmp     short loc_14001FBEE
0x14001fbec  xor     eax, eax
0x14001fbee  mov     rbx, [rsp+58h+arg_8]
0x14001fbf3  add     rsp, 20h
0x14001fbf7  pop     r15
0x14001fbf9  pop     r14
0x14001fbfb  pop     r13
0x14001fbfd  pop     r12
0x14001fbff  pop     rdi
0x14001fc00  pop     rsi
0x14001fc01  pop     rbp
0x14001fc02  retn
```
