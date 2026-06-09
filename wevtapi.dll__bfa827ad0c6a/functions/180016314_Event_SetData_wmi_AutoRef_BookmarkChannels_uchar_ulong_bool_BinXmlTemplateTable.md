# Event::SetData(wmi::AutoRef<BookmarkChannels> &,uchar *,ulong,bool,BinXmlTemplateTable *)

- ea: `0x180016314`
- end: `0x1800166ba`
- name: `?SetData@Event@@QEAAXAEAV?$AutoRef@VBookmarkChannels@@@wmi@@PEAEK_NPEAVBinXmlTemplateTable@@@Z`
- size: `934`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001619c`
- `0x180016230`

## callees

- `0x180016314`
- `0x1800166c0`
- `0x1800169e8`
- `0x180016a40`
- `0x1800231d0`
- `0x180023548`
- `0x180025514`
- `0x180038fa4`

## pseudocode

```c
__int64 __fastcall Event::SetData(__int64 a1, __int64 a2, unsigned int *a3, unsigned int a4)
{
  unsigned int v7; // esi
  __int64 v8; // rcx
  unsigned int v9; // r8d
  __int64 v10; // rdx
  int v11; // ecx
  __int64 v12; // r13
  unsigned __int64 v13; // r12
  __int64 v14; // r13
  __int64 v15; // rcx
  unsigned __int64 v16; // r15
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 result; // rax
  int v20; // eax
  __int128 pExceptionObject; // [rsp+20h] [rbp-50h] BYREF
  __int64 v22; // [rsp+30h] [rbp-40h]
  int v23; // [rsp+38h] [rbp-38h]
  int v24; // [rsp+3Ch] [rbp-34h]
  int v25; // [rsp+40h] [rbp-30h]
  unsigned int v26; // [rsp+48h] [rbp-28h]
  unsigned int *v27; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v28; // [rsp+58h] [rbp-18h]
  unsigned int v29; // [rsp+5Ch] [rbp-14h]
  __int64 v30; // [rsp+68h] [rbp-8h]

  v30 = a2;
  v27 = a3;
  v29 = a4;
  if ( !a3 || a4 < 0x10 )
    goto LABEL_25;
  if ( a3[1] < 0x10 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c1974ef86549365898c1a36e0a65a7f2_Traceguids, 13);
    }
    v22 = 0;
    v23 = 13;
    v24 = -1;
    pExceptionObject = 0;
    v25 = 43;
    throw (EvtException *)&pExceptionObject;
  }
  v7 = *a3;
  if ( *a3 > a4 || a3[1] > v7 || (v8 = a3[2], (unsigned int)v8 >= v7) || (v26 = a3[3], v26 >= v7) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_c1974ef86549365898c1a36e0a65a7f2_Traceguids, 13);
    }
    v22 = 0;
    v23 = 13;
    v24 = -1;
    pExceptionObject = 0;
    v25 = 52;
    throw (EvtException *)&pExceptionObject;
  }
  if ( (unsigned int)v8 > a4 )
    goto LABEL_25;
  if ( a4 - (unsigned int)v8 < 4 )
    goto LABEL_25;
  v9 = *(unsigned int *)((char *)a3 + v8);
  v10 = (unsigned int)v8;
  if ( v9 > 0x10000000 )
    goto LABEL_25;
  v11 = v8 + 4;
  if ( v9 > a4 - v11 )
    goto LABEL_25;
  v12 = v11 + v9;
  v28 = v11 + v9;
  Buffer::Set((Buffer *)(a1 + 48), (const unsigned __int8 *)a3 + v10 + 4, v9);
  if ( a4 - (unsigned int)v12 < 4 )
    goto LABEL_25;
  v13 = *(unsigned int *)((char *)a3 + v12);
  v14 = (unsigned int)(v12 + 4);
  if ( (unsigned int)v13 > 0x3FFFFFFF || (unsigned int)(4 * v13) > 0x10000000 || 4 * (int)v13 > a4 - (unsigned int)v14 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_c1974ef86549365898c1a36e0a65a7f2_Traceguids, 13);
    }
    v22 = 0;
    v23 = 13;
    v24 = -1;
    pExceptionObject = 0;
    v25 = 78;
    throw (EvtException *)&pExceptionObject;
  }
  v15 = *(_QWORD *)(a1 + 80);
  v16 = (*(_QWORD *)(a1 + 88) - v15) >> 2;
  if ( v13 <= v16 )
  {
    v17 = v15 + 4 * v13;
  }
  else
  {
    if ( !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::reserve(a1 + 80, (unsigned int)v13) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_c1974ef86549365898c1a36e0a65a7f2_Traceguids, 14);
      }
      v22 = 0;
      v23 = 14;
      v24 = -1;
      pExceptionObject = 0;
      v25 = 83;
      throw (EvtException *)&pExceptionObject;
    }
    memset_0(*(void **)(a1 + 88), 0, 4 * ((unsigned int)v13 - v16));
    v17 = *(_QWORD *)(a1 + 80) + 4 * v13;
  }
  v18 = 0;
  *(_QWORD *)(a1 + 88) = v17;
  if ( (_DWORD)v13 )
  {
    while ( a4 - (unsigned int)v14 >= 4 )
    {
      v20 = *(unsigned int *)((char *)a3 + v14);
      v14 = (unsigned int)(v14 + 4);
      *(_DWORD *)(*(_QWORD *)(a1 + 80) + 4 * v18) = v20;
      v18 = (unsigned int)(v18 + 1);
      if ( (unsigned int)v18 >= (unsigned int)v13 )
        goto LABEL_20;
    }
LABEL_25:
    UserBuffer::ThrowUnexpectedEOFException();
  }
LABEL_20:
  if ( v26 > a4 )
    goto LABEL_25;
  v28 = v26;
  result = Bookmark::UnMarshal(a1 + 104, v30, &v27);
  if ( v7 > v29 )
    goto LABEL_25;
  *(_QWORD *)(a1 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x180016314  mov     [rsp-38h+arg_10], rbx
0x180016319  push    rbp
0x18001631a  push    rsi
0x18001631b  push    rdi
0x18001631c  push    r12
0x18001631e  push    r13
0x180016320  push    r14
0x180016322  push    r15
0x180016324  mov     rbp, rsp
0x180016327  sub     rsp, 70h
0x18001632b  xor     r15d, r15d
0x18001632e  mov     [rbp+var_8], rdx
0x180016332  mov     [rbp+var_20], r8
0x180016336  mov     ebx, r9d
0x180016339  mov     [rbp+var_14], ebx
0x18001633c  mov     rdi, r8
0x18001633f  mov     r14, rcx
0x180016342  test    r8, r8
0x180016345  jz      loc_18001650B
0x18001634b  cmp     ebx, 10h
0x18001634e  jb      loc_18001650B
0x180016354  cmp     dword ptr [r8+4], 10h
0x180016359  jb      loc_180016543
0x18001635f  mov     esi, [r8]
0x180016362  cmp     esi, ebx
0x180016364  ja      loc_1800164C1
0x18001636a  cmp     [r8+4], esi
0x18001636e  ja      loc_1800164C1
0x180016374  mov     ecx, [r8+8]
0x180016378  cmp     ecx, esi
0x18001637a  jnb     loc_1800164C1
0x180016380  mov     eax, [r8+0Ch]
0x180016384  mov     [rbp+var_28], eax
0x180016387  cmp     eax, esi
0x180016389  jnb     loc_1800164C1
0x18001638f  cmp     ecx, ebx
0x180016391  ja      loc_18001650B
0x180016397  mov     eax, ebx
0x180016399  sub     eax, ecx
0x18001639b  cmp     eax, 4
0x18001639e  jb      loc_18001650B
0x1800163a4  mov     r8d, [rcx+r8]; unsigned int
0x1800163a8  mov     edx, ecx
0x1800163aa  cmp     r8d, 10000000h
0x1800163b1  ja      loc_18001650B
0x1800163b7  add     ecx, 4
0x1800163ba  mov     eax, ebx
0x1800163bc  sub     eax, ecx
0x1800163be  cmp     r8d, eax
0x1800163c1  ja      loc_18001650B
0x1800163c7  lea     r13d, [rcx+r8]
0x1800163cb  add     rdx, 4
0x1800163cf  add     rdx, rdi; unsigned __int8 *
0x1800163d2  mov     [rbp+var_18], r13d
0x1800163d6  lea     rcx, [r14+30h]; this
0x1800163da  call    ?Set@Buffer@@QEAAXPEBEK@Z; Buffer::Set(uchar const *,ulong)
0x1800163df  mov     eax, ebx
0x1800163e1  sub     eax, r13d
0x1800163e4  cmp     eax, 4
0x1800163e7  jb      loc_18001650B
0x1800163ed  mov     r12d, [r13+rdi+0]
0x1800163f2  add     r13d, 4
0x1800163f6  cmp     r12d, 3FFFFFFFh
0x1800163fd  ja      loc_18001661C
0x180016403  lea     ecx, ds:0[r12*4]
0x18001640b  cmp     ecx, 10000000h
0x180016411  ja      loc_18001661C
0x180016417  mov     eax, ebx
0x180016419  sub     eax, r13d
0x18001641c  cmp     ecx, eax
0x18001641e  ja      loc_18001661C
0x180016424  mov     rcx, [r14+50h]
0x180016428  mov     r15, [r14+58h]
0x18001642c  sub     r15, rcx
0x18001642f  sar     r15, 2
0x180016433  cmp     r12, r15
0x180016436  jbe     loc_18001653A
0x18001643c  mov     edx, r12d
0x18001643f  lea     rcx, [r14+50h]
0x180016443  call    ?reserve@?$vector@KV?$allocator@K@utl@@@utl@@QEAA_N_K@Z; utl::vector<ulong,utl::allocator<ulong>>::reserve(unsigned __int64)
0x180016448  test    al, al
0x18001644a  jz      loc_1800165AE
0x180016450  mov     rcx, [r14+58h]; void *
0x180016454  mov     r8d, r12d
0x180016457  sub     r8, r15
0x18001645a  xor     edx, edx; Val
0x18001645c  shl     r8, 2; Size
0x180016460  call    memset_0
0x180016465  mov     rax, [r14+50h]
0x180016469  lea     rdx, [rax+r12*4]
0x18001646d  xor     r8d, r8d
0x180016470  mov     [r14+58h], rdx
0x180016474  test    r12d, r12d
0x180016477  jnz     loc_180016511
0x18001647d  mov     eax, [rbp+var_28]
0x180016480  cmp     eax, ebx
0x180016482  ja      loc_18001650B
0x180016488  mov     rdx, [rbp+var_8]
0x18001648c  lea     rcx, [r14+68h]
0x180016490  lea     r8, [rbp+var_20]
0x180016494  mov     [rbp+var_18], eax
0x180016497  call    ?UnMarshal@Bookmark@@QEAAXAEAV?$AutoRef@VBookmarkChannels@@@wmi@@AEAVUserBuffer@@@Z; Bookmark::UnMarshal(wmi::AutoRef<BookmarkChannels> &,UserBuffer &)
0x18001649c  cmp     esi, [rbp+var_14]
0x18001649f  ja      short loc_18001650B
0x1800164a1  mov     rbx, [rsp+70h+arg_10]
0x1800164a9  mov     qword ptr [r14+28h], 0
0x1800164b1  add     rsp, 70h
0x1800164b5  pop     r15
0x1800164b7  pop     r14
0x1800164b9  pop     r13
0x1800164bb  pop     r12
0x1800164bd  pop     rdi
0x1800164be  pop     rsi
0x1800164bf  pop     rbp
0x1800164c0  retn
0x1800164c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800164c8  lea     rax, WPP_GLOBAL_Control
0x1800164cf  mov     ebx, 0Dh
0x1800164d4  cmp     rcx, rax
0x1800164d7  jnz     loc_180016686
0x1800164dd  xorps   xmm0, xmm0
0x1800164e0  mov     [rbp+var_40], r15
0x1800164e4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800164eb  mov     [rbp+var_38], ebx
0x1800164ee  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800164f2  mov     [rbp+var_34], 0FFFFFFFFh
0x1800164f9  movdqu  [rbp+pExceptionObject], xmm0
0x1800164fe  mov     [rbp+var_30], 34h ; '4'
0x180016505  call    _CxxThrowException_0
0x18001650b  call    ?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ; UserBuffer::ThrowUnexpectedEOFException(void)
0x180016511  mov     eax, ebx
0x180016513  sub     eax, r13d
0x180016516  cmp     eax, 4
0x180016519  jb      short loc_18001650B
0x18001651b  mov     eax, [r13+rdi+0]
0x180016520  add     r13d, 4
0x180016524  mov     rcx, [r14+50h]
0x180016528  mov     [rcx+r8*4], eax
0x18001652c  inc     r8d
0x18001652f  cmp     r8d, r12d
0x180016532  jnb     loc_18001647D
0x180016538  jmp     short loc_180016511
0x18001653a  lea     rdx, [rcx+r12*4]
0x18001653e  jmp     loc_18001646D
0x180016543  mov     rcx, cs:WPP_GLOBAL_Control
0x18001654a  lea     rax, WPP_GLOBAL_Control
0x180016551  mov     ebx, 0Dh
0x180016556  cmp     rcx, rax
0x180016559  jz      short loc_180016580
0x18001655b  test    dword ptr [rcx+1Ch], 40000h
0x180016562  jz      short loc_180016580
0x180016564  cmp     byte ptr [rcx+19h], 2
0x180016568  jb      short loc_180016580
0x18001656a  mov     rcx, [rcx+10h]
0x18001656e  lea     edx, [rbx-2]
0x180016571  mov     r9d, ebx
0x180016574  lea     r8, WPP_c1974ef86549365898c1a36e0a65a7f2_Traceguids
0x18001657b  call    WPP_SF_D
0x180016580  xorps   xmm0, xmm0
0x180016583  mov     [rbp+var_40], r15
0x180016587  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001658e  mov     [rbp+var_38], ebx
0x180016591  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180016595  mov     [rbp+var_34], 0FFFFFFFFh
0x18001659c  movdqu  [rbp+pExceptionObject], xmm0
0x1800165a1  mov     [rbp+var_30], 2Bh ; '+'
0x1800165a8  call    _CxxThrowException_0
0x1800165ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165b5  lea     rax, WPP_GLOBAL_Control
0x1800165bc  mov     ebx, 0Eh
0x1800165c1  cmp     rcx, rax
0x1800165c4  jz      short loc_1800165EA
0x1800165c6  test    dword ptr [rcx+1Ch], 40000h
0x1800165cd  jz      short loc_1800165EA
0x1800165cf  cmp     byte ptr [rcx+19h], 2
0x1800165d3  jb      short loc_1800165EA
0x1800165d5  mov     rcx, [rcx+10h]
0x1800165d9  lea     r8, WPP_c1974ef86549365898c1a36e0a65a7f2_Traceguids
0x1800165e0  mov     edx, ebx
0x1800165e2  mov     r9d, ebx
0x1800165e5  call    WPP_SF_D
0x1800165ea  xorps   xmm0, xmm0
0x1800165ed  mov     [rbp+var_40], 0
0x1800165f5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800165fc  mov     [rbp+var_38], ebx
0x1800165ff  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180016603  mov     [rbp+var_34], 0FFFFFFFFh
0x18001660a  movdqu  [rbp+pExceptionObject], xmm0
0x18001660f  mov     [rbp+var_30], 53h ; 'S'
0x180016616  call    _CxxThrowException_0
0x18001661c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016623  lea     rax, WPP_GLOBAL_Control
0x18001662a  mov     ebx, 0Dh
0x18001662f  cmp     rcx, rax
0x180016632  jz      short loc_180016658
0x180016634  test    dword ptr [rcx+1Ch], 40000h
0x18001663b  jz      short loc_180016658
0x18001663d  cmp     byte ptr [rcx+19h], 2
0x180016641  jb      short loc_180016658
0x180016643  mov     rcx, [rcx+10h]
0x180016647  lea     r8, WPP_c1974ef86549365898c1a36e0a65a7f2_Traceguids
0x18001664e  mov     edx, ebx
0x180016650  mov     r9d, ebx
0x180016653  call    WPP_SF_D
0x180016658  xorps   xmm0, xmm0
0x18001665b  mov     [rbp+var_40], r15
0x18001665f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180016666  mov     [rbp+var_38], ebx
0x180016669  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001666d  mov     [rbp+var_34], 0FFFFFFFFh
0x180016674  movdqu  [rbp+pExceptionObject], xmm0
0x180016679  mov     [rbp+var_30], 4Eh ; 'N'
0x180016680  call    _CxxThrowException_0
0x180016686  test    dword ptr [rcx+1Ch], 40000h
0x18001668d  jz      loc_1800164DD
0x180016693  cmp     byte ptr [rcx+19h], 2
0x180016697  jb      loc_1800164DD
0x18001669d  mov     rcx, [rcx+10h]
0x1800166a1  lea     r8, WPP_c1974ef86549365898c1a36e0a65a7f2_Traceguids
0x1800166a8  mov     edx, 0Ch
0x1800166ad  mov     r9d, ebx
0x1800166b0  call    WPP_SF_D
0x1800166b5  jmp     loc_1800164DD
```
