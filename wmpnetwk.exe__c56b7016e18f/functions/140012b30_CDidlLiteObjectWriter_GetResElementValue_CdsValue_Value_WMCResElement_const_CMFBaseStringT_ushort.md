# CDidlLiteObjectWriter::GetResElementValue(CdsValue::Value,_WMCResElement const *,CMFBaseStringT<ushort> &)

- ea: `0x140012b30`
- end: `0x14001311a`
- name: `?GetResElementValue@CDidlLiteObjectWriter@@KAJW4Value@CdsValue@@PEBU_WMCResElement@@AEAV?$CMFBaseStringT@G@@@Z`
- size: `1514`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011d70`
- `0x1400124d0`

## callees

- `0x14000b3b0`
- `0x14000c920`
- `0x140011780`
- `0x140011930`
- `0x140011b50`
- `0x140011bb4`
- `0x140012b30`
- `0x140013120`
- `0x140013288`
- `0x14002eda0`
- `0x1400320e4`
- `0x14003e5f4`
- `0x14003f17c`
- `0x14005480c`
- `0x140099874`
- `0x14009ad10`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x140012e60`
- `KERNEL32!CompareStringOrdinal` at `0x140012e60`
- `KERNEL32!GetProcessHeap` at `0x140012c6d`
- `KERNEL32!GetProcessHeap` at `0x140012c6d`
- `KERNEL32!HeapAlloc` at `0x140012c7e`
- `KERNEL32!HeapAlloc` at `0x140012c7e`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x140012cee`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x140012cee`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140012e8a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140012e8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDidlLiteObjectWriter::GetResElementValue(
        unsigned int a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v5; // r14
  unsigned int v7; // esi
  unsigned __int64 v8; // kr00_8
  unsigned __int64 v9; // rcx
  unsigned int appended; // eax
  unsigned int v12; // r14d
  HANDLE ProcessHeap; // rax
  _WORD *v14; // rax
  _WORD *v15; // rsi
  const void *v16; // rdx
  int v17; // ebx
  __int64 v18; // r8
  __int64 v19; // rbx
  unsigned __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // r8d
  __int64 v23; // rcx
  int v24; // r8d
  __int64 v25; // rax
  const wchar_t *v26; // rax
  wchar_t v27; // dx
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rdx
  unsigned __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r10
  int v34; // [rsp+60h] [rbp+8h] BYREF
  __int64 v35; // [rsp+70h] [rbp+18h] BYREF

  v5 = (_QWORD *)a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids, a1, a2);
  }
  *(_QWORD *)(a3 + 4) = 0;
  if ( a1 == 7 )
  {
    a2 = v5[2];
    if ( a2 )
    {
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(a2 + 2 * v9) );
      if ( v9 <= 0x7FFFFFFF )
      {
        v7 = CMFBaseStringT<unsigned short>::_Append(a3, a2, (unsigned int)v9, a4);
      }
      else
      {
        *(_DWORD *)(a3 + 4) = -2147024785;
        v7 = -2147024785;
      }
    }
    else
    {
      v7 = 0;
    }
    goto LABEL_15;
  }
  v7 = 0;
  if ( a1 == 8 )
  {
    v12 = *((_DWORD *)v5 + 6);
    if ( v12 == -1 )
      goto LABEL_15;
    if ( *(int *)(a3 + 12) >= 34 )
      goto LABEL_29;
    if ( (*(_DWORD *)a3 & 6) == 4 )
    {
      v7 = -2147024774;
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v14 = HeapAlloc(ProcessHeap, 0, 0x44u);
      v15 = v14;
      if ( v14 )
      {
        v16 = *(const void **)(a3 + 16);
        if ( v16 )
        {
          memcpy_0(v14, v16, 2LL * *(int *)(a3 + 8));
          v17 = *(_DWORD *)(a3 + 8);
          CMFBaseStringT<unsigned short>::_FreeBuffer((unsigned int *)a3);
          *(_DWORD *)a3 &= ~1u;
          *(_DWORD *)(a3 + 8) = v17;
        }
        *(_QWORD *)(a3 + 16) = v15;
        *(_DWORD *)(a3 + 12) = 34;
        v15[*(int *)(a3 + 8)] = 0;
LABEL_29:
        v18 = *(int *)(a3 + 8);
        v19 = *(_QWORD *)(a3 + 16) + 2 * v18;
        if ( (unsigned int)_o__ultow_s(v12, v19, *(_DWORD *)(a3 + 12) - (int)v18, 10) )
          v19 = 0;
        v20 = -1;
        a2 = -1;
        do
          ++a2;
        while ( *(_WORD *)(v19 + 2 * a2) );
        if ( a2 <= 0xFFFFFFFF )
        {
          v7 = 0;
          v24 = a2 + *(_DWORD *)(a3 + 8);
          v34 = v24;
          if ( *(int *)(a3 + 4) >= 0 )
          {
            v25 = *(int *)(a3 + 12);
            if ( v24 < 0 )
            {
              if ( (int)v25 <= 0 )
              {
                v24 = 0;
              }
              else
              {
                *(_WORD *)(*(_QWORD *)(a3 + 16) + 2 * v25 - 2) = 0;
                do
                  ++v20;
                while ( *(_WORD *)(*(_QWORD *)(a3 + 16) + 2 * v20) );
                if ( (int)UIntPtrToLong(v20, &v34) < 0 )
                {
                  *(_DWORD *)(a3 + 4) = -2147024785;
                  goto LABEL_15;
                }
                v24 = v34;
              }
            }
            else
            {
              if ( v24 >= (int)v25 )
              {
                *(_DWORD *)(a3 + 4) = -2147024785;
                goto LABEL_15;
              }
              a2 = v24;
              *(_WORD *)(*(_QWORD *)(a3 + 16) + 2LL * v24) = 0;
            }
            *(_DWORD *)(a3 + 8) = v24;
          }
        }
        else
        {
          v7 = -2147024362;
          *(_DWORD *)(a3 + 4) = -2147024362;
        }
        goto LABEL_15;
      }
      *(_DWORD *)(a3 + 8) = 0;
      v7 = -2147024882;
    }
    *(_DWORD *)(a3 + 4) = v7;
    *(_DWORD *)(a3 + 4) = v7;
    goto LABEL_15;
  }
  if ( a1 != 6 )
  {
    if ( a1 != 9 )
    {
      if ( a1 == 14 )
      {
        a2 = *((unsigned int *)v5 + 16);
LABEL_19:
        if ( (_DWORD)a2 != -1 )
        {
          appended = CMFBaseStringT<unsigned short>::AppendUInt(a3);
LABEL_21:
          v7 = appended;
        }
      }
      else
      {
        v8 = a2;
        a2 = (unsigned __int64)&_ImageBase;
        switch ( a1 )
        {
          case 0xAu:
            v7 = CMFBaseStringT<unsigned short>::Append(a3, &_ImageBase, v5[5]);
            goto LABEL_15;
          case 0xBu:
            v7 = CMFBaseStringT<unsigned short>::Append(a3, &_ImageBase, v5[6]);
            goto LABEL_15;
          case 0xCu:
            a2 = *((unsigned int *)v5 + 14);
            goto LABEL_19;
          case 0xDu:
            a2 = *((unsigned int *)v5 + 15);
            goto LABEL_19;
          case 0xFu:
            a2 = *((unsigned int *)v5 + 17);
            goto LABEL_19;
          case 0x10u:
            v29 = *(_QWORD *)&GUID_NULL.Data1 - v5[9];
            if ( *(_QWORD *)&GUID_NULL.Data1 == v5[9] )
              v29 = *(_QWORD *)GUID_NULL.Data4 - v5[10];
            if ( v29 )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v35);
              CDidlLiteObjectWriter::GetAtlStringFromGUID((GUID *)(v5 + 9));
              v7 = CMFBaseStringT<unsigned short>::Append(a3, v30, v35);
              ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v35);
            }
            goto LABEL_15;
          case 0x4Au:
            if ( !*((_DWORD *)v5 + 23) || CompareStringOrdinal((LPCWCH)*v5, 7, L"rtsp://", -1, 1) == 2 )
              goto LABEL_15;
            CMFBaseStringT<unsigned short>::Append(a3, a2, *v5);
            v26 = (const wchar_t *)CMFBaseStringT<unsigned short>::PContents(a3, 63);
            if ( !wcsrchr(v26, v27) )
            {
              appended = CMFBaseStringT<unsigned short>::Append(a3, v28, L"?IFOFile=true");
              goto LABEL_21;
            }
            v7 = CMFBaseStringT<unsigned short>::Append(a3, v28, L",IFOFile=true");
            break;
          case 0x51u:
          case 0x52u:
          case 0x53u:
            goto LABEL_15;
          default:
            a2 = v8;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v7;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids, a1);
            goto LABEL_15;
        }
      }
      goto LABEL_15;
    }
    a2 = *((unsigned int *)v5 + 7);
    if ( (_DWORD)a2 == -1 || *((_DWORD *)v5 + 8) == -1 )
      goto LABEL_15;
    CMFBaseStringT<unsigned short>::AppendUInt(a3);
    if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(a3, *(_DWORD *)(a3 + 8) + 1) < 0
      || (*(_WORD *)(*(_QWORD *)(a3 + 16) + 2LL * *(int *)(a3 + 8)) = 120,
          v21 = *(int *)(a3 + 8),
          v22 = v21 + 1,
          v34 = v21 + 1,
          *(int *)(a3 + 4) < 0) )
    {
LABEL_45:
      v7 = CMFBaseStringT<unsigned short>::AppendUInt(a3);
      goto LABEL_15;
    }
    v23 = *(int *)(a3 + 12);
    if ( v22 < 0 )
    {
      if ( (int)v23 <= 0 )
      {
        v22 = 0;
        goto LABEL_44;
      }
      *(_WORD *)(*(_QWORD *)(a3 + 16) + 2 * v23 - 2) = 0;
      v31 = -1;
      do
        ++v31;
      while ( *(_WORD *)(*(_QWORD *)(a3 + 16) + 2 * v31) );
      if ( (int)UIntPtrToLong(v31, &v34) >= 0 )
      {
        v22 = v34;
        goto LABEL_44;
      }
    }
    else if ( v22 < (int)v23 )
    {
      *(_WORD *)(*(_QWORD *)(a3 + 16) + 2 * v21 + 2) = 0;
LABEL_44:
      *(_DWORD *)(a3 + 8) = v22;
      goto LABEL_45;
    }
    *(_DWORD *)(a3 + 4) = -2147024785;
    goto LABEL_45;
  }
  a2 = v5[1];
  if ( a2 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    v7 = CMFBaseStringT<unsigned short>::AppendUInt64(a3);
LABEL_15:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v32 = CMFBaseStringT<unsigned short>::PContents(a3, a2);
    WPP_SF_S(*(_QWORD *)(v33 + 16), 70, &WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids, v32);
  }
  return v7;
}

```

## disassembly

```asm
0x140012b30  mov     [rsp+arg_8], rbx
0x140012b35  mov     [rsp+arg_18], rbp
0x140012b3a  push    rsi
0x140012b3b  push    rdi
0x140012b3c  push    r12
0x140012b3e  push    r14
0x140012b40  push    r15
0x140012b42  sub     rsp, 30h
0x140012b46  mov     rdi, r8
0x140012b49  mov     r14, rdx
0x140012b4c  mov     ebx, ecx
0x140012b4e  lea     r12, WPP_GLOBAL_Control
0x140012b55  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b5c  cmp     rcx, r12
0x140012b5f  jz      short loc_140012B6B
0x140012b61  test    byte ptr [rcx+1Ch], 2
0x140012b65  jnz     loc_140012F17
0x140012b6b  xor     r15d, r15d
0x140012b6e  mov     [rdi+4], r15
0x140012b72  cmp     ebx, 7
0x140012b75  jz      short loc_140012BCD
0x140012b77  mov     esi, r15d
0x140012b7a  cmp     ebx, 8
0x140012b7d  jz      loc_140012C4D
0x140012b83  cmp     ebx, 6
0x140012b86  jz      loc_140012D25
0x140012b8c  cmp     ebx, 9
0x140012b8f  jz      loc_140012D46
0x140012b95  cmp     ebx, 0Eh
0x140012b98  jz      loc_140012C34
0x140012b9e  lea     eax, [rbx-0Ah]; switch 74 cases
0x140012ba1  cmp     eax, 49h
0x140012ba4  ja      def_140012BC5; jumptable 0000000140012BC5 default case, cases 14,17-73,75-80
0x140012baa  cdqe
0x140012bac  lea     rdx, __ImageBase
0x140012bb3  movzx   eax, ds:(byte_1400130D0 - 140000000h)[rdx+rax]
0x140012bbb  mov     ecx, ds:(jpt_140012BC5 - 140000000h)[rdx+rax*4]
0x140012bc2  add     rcx, rdx
0x140012bc5  jmp     rcx; switch jump
0x140012bc7  mov     edx, [r14+38h]; jumptable 0000000140012BC5 case 12
0x140012bcb  jmp     short loc_140012C38
0x140012bcd  mov     rdx, [r14+10h]
0x140012bd1  test    rdx, rdx
0x140012bd4  jz      loc_140013071
0x140012bda  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140012be1  inc     rcx
0x140012be4  cmp     [rdx+rcx*2], r15w
0x140012be9  jnz     short loc_140012BE1
0x140012beb  cmp     rcx, 7FFFFFFFh
0x140012bf2  jbe     loc_140012EAD
0x140012bf8  mov     dword ptr [rdi+4], 8007006Fh
0x140012bff  mov     esi, 8007006Fh
0x140012c04  mov     r10, cs:WPP_GLOBAL_Control; jumptable 0000000140012BC5 cases 81-83
0x140012c0b  cmp     r10, r12
0x140012c0e  jz      short loc_140012C1B
0x140012c10  test    byte ptr [r10+1Ch], 2
0x140012c15  jnz     loc_140013079
0x140012c1b  mov     eax, esi
0x140012c1d  mov     rbx, [rsp+58h+arg_8]
0x140012c22  mov     rbp, [rsp+58h+arg_18]
0x140012c27  add     rsp, 30h
0x140012c2b  pop     r15
0x140012c2d  pop     r14
0x140012c2f  pop     r12
0x140012c31  pop     rdi
0x140012c32  pop     rsi
0x140012c33  retn
0x140012c34  mov     edx, [r14+40h]
0x140012c38  mov     ebp, 0FFFFFFFFh
0x140012c3d  cmp     edx, ebp
0x140012c3f  jz      short loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012c41  mov     rcx, rdi
0x140012c44  call    ?AppendUInt@?$CMFBaseStringT@G@@QEAAJIH@Z; CMFBaseStringT<ushort>::AppendUInt(uint,int)
0x140012c49  mov     esi, eax
0x140012c4b  jmp     short loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012c4d  mov     r14d, [r14+18h]
0x140012c51  mov     ebp, 0FFFFFFFFh
0x140012c56  cmp     r14d, ebp
0x140012c59  jz      short loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012c5b  cmp     dword ptr [rdi+0Ch], 22h ; '"'
0x140012c5f  jge     short loc_140012CCD
0x140012c61  mov     eax, [rdi]
0x140012c63  and     al, 6
0x140012c65  cmp     al, 4
0x140012c67  jz      loc_140012E28
0x140012c6d  call    cs:__imp_GetProcessHeap
0x140012c73  mov     rcx, rax; hHeap
0x140012c76  xor     edx, edx; dwFlags
0x140012c78  mov     r8d, 44h ; 'D'; dwBytes
0x140012c7e  call    cs:__imp_HeapAlloc
0x140012c84  mov     rsi, rax
0x140012c87  test    rax, rax
0x140012c8a  jz      loc_14001300F
0x140012c90  mov     rdx, [rdi+10h]; Src
0x140012c94  test    rdx, rdx
0x140012c97  jz      short loc_140012CB9
0x140012c99  movsxd  r8, dword ptr [rdi+8]
0x140012c9d  add     r8, r8; Size
0x140012ca0  mov     rcx, rax; void *
0x140012ca3  call    memcpy_0
0x140012ca8  mov     ebx, [rdi+8]
0x140012cab  mov     rcx, rdi
0x140012cae  call    ?_FreeBuffer@?$CMFBaseStringT@G@@IEAAXXZ; CMFBaseStringT<ushort>::_FreeBuffer(void)
0x140012cb3  and     dword ptr [rdi], 0FFFFFFFEh
0x140012cb6  mov     [rdi+8], ebx
0x140012cb9  mov     [rdi+10h], rsi
0x140012cbd  mov     dword ptr [rdi+0Ch], 22h ; '"'
0x140012cc4  movsxd  rcx, dword ptr [rdi+8]
0x140012cc8  mov     [rsi+rcx*2], r15w
0x140012ccd  movsxd  r8, dword ptr [rdi+8]
0x140012cd1  mov     rax, [rdi+10h]
0x140012cd5  lea     rbx, [rax+r8*2]
0x140012cd9  mov     eax, [rdi+0Ch]
0x140012cdc  sub     eax, r8d
0x140012cdf  movsxd  r8, eax
0x140012ce2  mov     r9d, 0Ah
0x140012ce8  mov     rdx, rbx
0x140012ceb  mov     ecx, r14d
0x140012cee  call    cs:__imp__o__ultow_s
0x140012cf4  test    eax, eax
0x140012cf6  jz      short loc_140012CFB
0x140012cf8  mov     rbx, r15
0x140012cfb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140012d02  mov     rdx, rcx
0x140012d05  inc     rdx
0x140012d08  cmp     [rbx+rdx*2], r15w
0x140012d0d  jnz     short loc_140012D05
0x140012d0f  cmp     rdx, rbp
0x140012d12  jbe     loc_140012DE4
0x140012d18  mov     esi, 80070216h
0x140012d1d  mov     [rdi+4], esi
0x140012d20  jmp     loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012d25  mov     rdx, [r14+8]
0x140012d29  lea     rax, [rdx-1]
0x140012d2d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140012d31  ja      loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012d37  mov     rcx, rdi
0x140012d3a  call    ?AppendUInt64@?$CMFBaseStringT@G@@QEAAJ_KH@Z; CMFBaseStringT<ushort>::AppendUInt64(unsigned __int64,int)
0x140012d3f  mov     esi, eax
0x140012d41  jmp     loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012d46  mov     edx, [r14+1Ch]
0x140012d4a  mov     ebp, 0FFFFFFFFh
0x140012d4f  cmp     edx, ebp
0x140012d51  jz      loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012d57  cmp     [r14+20h], ebp
0x140012d5b  jz      loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012d61  mov     rcx, rdi
0x140012d64  call    ?AppendUInt@?$CMFBaseStringT@G@@QEAAJIH@Z; CMFBaseStringT<ushort>::AppendUInt(uint,int)
0x140012d69  mov     edx, [rdi+8]
0x140012d6c  inc     edx
0x140012d6e  mov     rcx, rdi
0x140012d71  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x140012d76  test    eax, eax
0x140012d78  js      short loc_140012DBE
0x140012d7a  movsxd  rcx, dword ptr [rdi+8]
0x140012d7e  mov     rax, [rdi+10h]
0x140012d82  mov     word ptr [rax+rcx*2], 78h ; 'x'
0x140012d88  movsxd  rax, dword ptr [rdi+8]
0x140012d8c  lea     r8d, [rax+1]
0x140012d90  mov     [rsp+58h+arg_0], r8d
0x140012d95  cmp     [rdi+4], esi
0x140012d98  jl      short loc_140012DBE
0x140012d9a  movsxd  rcx, dword ptr [rdi+0Ch]
0x140012d9e  test    r8d, r8d
0x140012da1  js      loc_140012FBE
0x140012da7  cmp     r8d, ecx
0x140012daa  jge     loc_140012FFB
0x140012db0  mov     rcx, [rdi+10h]
0x140012db4  mov     [rcx+rax*2+2], r15w
0x140012dba  mov     [rdi+8], r8d
0x140012dbe  mov     edx, [r14+20h]
0x140012dc2  mov     rcx, rdi
0x140012dc5  call    ?AppendUInt@?$CMFBaseStringT@G@@QEAAJIH@Z; CMFBaseStringT<ushort>::AppendUInt(uint,int)
0x140012dca  mov     esi, eax
0x140012dcc  jmp     loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012dd1  mov     r8, [r14+28h]; jumptable 0000000140012BC5 case 10
0x140012dd5  mov     rcx, rdi
0x140012dd8  call    ?Append@?$CMFBaseStringT@G@@QEAAJIPEBGJ@Z; CMFBaseStringT<ushort>::Append(uint,ushort const *,long)
0x140012ddd  mov     esi, eax
0x140012ddf  jmp     loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012de4  mov     esi, r15d
0x140012de7  mov     r8d, [rdi+8]
0x140012deb  add     r8d, edx
0x140012dee  mov     [rsp+58h+arg_0], r8d
0x140012df3  cmp     [rdi+4], r15d
0x140012df7  jl      loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012dfd  movsxd  rax, dword ptr [rdi+0Ch]
0x140012e01  test    r8d, r8d
0x140012e04  js      loc_140013029
0x140012e0a  cmp     r8d, eax
0x140012e0d  jge     loc_14001301D
0x140012e13  movsxd  rdx, r8d
0x140012e16  mov     rcx, [rdi+10h]
0x140012e1a  mov     [rcx+rdx*2], r15w
0x140012e1f  mov     [rdi+8], r8d
0x140012e23  jmp     loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012e28  mov     esi, 8007007Ah
0x140012e2d  mov     [rdi+4], esi
0x140012e30  mov     [rdi+4], esi
0x140012e33  jmp     loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012e38  cmp     [r14+5Ch], esi; jumptable 0000000140012BC5 case 74
0x140012e3c  jz      loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012e42  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x140012e4a  mov     r9, 0FFFFFFFFFFFFFFFFh; cchCount2
0x140012e51  lea     r8, aRtsp_1; "rtsp://"
0x140012e58  mov     edx, 7; cchCount1
0x140012e5d  mov     rcx, [r14]; lpString1
0x140012e60  call    cs:__imp_CompareStringOrdinal
0x140012e66  cmp     eax, 2
0x140012e69  jz      loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012e6f  mov     r8, [r14]
0x140012e72  mov     rcx, rdi
0x140012e75  call    ?Append@?$CMFBaseStringT@G@@QEAAJIPEBGJ@Z; CMFBaseStringT<ushort>::Append(uint,ushort const *,long)
0x140012e7a  mov     edx, 3Fh ; '?'
0x140012e7f  mov     rcx, rdi
0x140012e82  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x140012e87  mov     rcx, rax; Str
0x140012e8a  call    cs:__imp_wcsrchr
0x140012e90  mov     rcx, rdi
0x140012e93  test    rax, rax
0x140012e96  jnz     loc_140012F43
0x140012e9c  lea     r8, aIfofileTrue_1; "?IFOFile=true"
0x140012ea3  call    ?Append@?$CMFBaseStringT@G@@QEAAJIPEBGJ@Z; CMFBaseStringT<ushort>::Append(uint,ushort const *,long)
0x140012ea8  jmp     loc_140012C49
0x140012ead  mov     r8d, ecx
0x140012eb0  mov     rcx, rdi
0x140012eb3  call    ?_Append@?$CMFBaseStringT@G@@IEAAJPEBGJ@Z; CMFBaseStringT<ushort>::_Append(ushort const *,long)
0x140012eb8  mov     esi, eax
0x140012eba  jmp     loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012ebf  mov     rax, qword ptr cs:GUID_NULL.Data1; jumptable 0000000140012BC5 case 16
0x140012ec6  sub     rax, [r14+48h]
0x140012eca  jnz     short loc_140012ED7
0x140012ecc  mov     rax, qword ptr cs:GUID_NULL.Data4
0x140012ed3  sub     rax, [r14+50h]
0x140012ed7  test    rax, rax
0x140012eda  jz      loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012ee0  lea     rcx, [rsp+58h+arg_10]
0x140012ee5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140012eea  lea     rdx, [rsp+58h+arg_10]
0x140012eef  lea     rcx, [r14+48h]; rguid
0x140012ef3  call    ?GetAtlStringFromGUID@CDidlLiteObjectWriter@@SAJAEBU_GUID@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CDidlLiteObjectWriter::GetAtlStringFromGUID(_GUID const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140012ef8  mov     r8, [rsp+58h+arg_10]
0x140012efd  mov     rcx, rdi
0x140012f00  call    ?Append@?$CMFBaseStringT@G@@QEAAJIPEBGJ@Z; CMFBaseStringT<ushort>::Append(uint,ushort const *,long)
0x140012f05  mov     esi, eax
0x140012f07  lea     rcx, [rsp+58h+arg_10]
0x140012f0c  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140012f11  nop
0x140012f12  jmp     loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012f17  cmp     byte ptr [rcx+19h], 5
0x140012f1b  jb      loc_140012B6B
0x140012f21  mov     edx, 44h ; 'D'
0x140012f26  mov     qword ptr [rsp+58h+bIgnoreCase], r14
0x140012f2b  mov     r9d, ebx
0x140012f2e  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x140012f35  mov     rcx, [rcx+10h]
0x140012f39  call    WPP_SF_dq
0x140012f3e  jmp     loc_140012B6B
0x140012f43  lea     r8, aIfofileTrue; ",IFOFile=true"
0x140012f4a  call    ?Append@?$CMFBaseStringT@G@@QEAAJIPEBGJ@Z; CMFBaseStringT<ushort>::Append(uint,ushort const *,long)
0x140012f4f  mov     esi, eax
0x140012f51  jmp     loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012f56  mov     r8, [r14+30h]; jumptable 0000000140012BC5 case 11
0x140012f5a  mov     rcx, rdi
0x140012f5d  call    ?Append@?$CMFBaseStringT@G@@QEAAJIPEBGJ@Z; CMFBaseStringT<ushort>::Append(uint,ushort const *,long)
0x140012f62  mov     esi, eax
0x140012f64  jmp     loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012f69  mov     edx, [r14+3Ch]; jumptable 0000000140012BC5 case 13
0x140012f6d  jmp     loc_140012C38
0x140012f72  mov     edx, [r14+44h]; jumptable 0000000140012BC5 case 15
0x140012f76  jmp     loc_140012C38
0x140012f7b  mov     r10, cs:WPP_GLOBAL_Control; jumptable 0000000140012BC5 default case, cases 14,17-73,75-80
0x140012f82  cmp     r10, r12
0x140012f85  jz      loc_140012C1B
0x140012f8b  test    byte ptr [r10+1Ch], 20h
0x140012f90  jz      loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012f96  cmp     byte ptr [r10+19h], 4
0x140012f9b  jb      loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012fa1  mov     edx, 45h ; 'E'
0x140012fa6  mov     r9d, ebx
0x140012fa9  lea     r8, WPP_478ffc6658c23ee89d991dcff0807d2d_Traceguids
0x140012fb0  mov     rcx, [r10+10h]
0x140012fb4  call    WPP_SF_d
0x140012fb9  jmp     loc_140012C04; jumptable 0000000140012BC5 cases 81-83
0x140012fbe  test    ecx, ecx
0x140012fc0  jle     short loc_140013007
0x140012fc2  mov     rdx, rcx
0x140012fc5  mov     rcx, [rdi+10h]
0x140012fc9  mov     [rcx+rdx*2-2], r15w
0x140012fcf  mov     rax, [rdi+10h]
0x140012fd3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140012fda  inc     rcx; unsigned __int64
0x140012fdd  cmp     [rax+rcx*2], si
0x140012fe1  jnz     short loc_140012FDA
0x140012fe3  lea     rdx, [rsp+58h+arg_0]; int *
0x140012fe8  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x140012fed  test    eax, eax
0x140012fef  js      short loc_140012FFB
0x140012ff1  mov     r8d, [rsp+58h+arg_0]
0x140012ff6  jmp     loc_140012DBA
  ... truncated ...
```
