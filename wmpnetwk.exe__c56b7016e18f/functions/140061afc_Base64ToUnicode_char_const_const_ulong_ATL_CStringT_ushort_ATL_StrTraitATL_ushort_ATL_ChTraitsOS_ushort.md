# Base64ToUnicode(char const * const,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x140061afc`
- end: `0x140061f2b`
- name: `?Base64ToUnicode@@YAJQEBDKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1071`
- prototype: `__int64 __fastcall(char *, int, __int64 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x14003a168`

## callees

- `0x14000b3b0`
- `0x140019270`
- `0x1400194d8`
- `0x140027660`
- `0x14002c46c`
- `0x14002d7f4`
- `0x14002e2c4`
- `0x14002eb14`
- `0x14003f17c`
- `0x140047798`
- `0x14004a834`
- `0x140054490`
- `0x1400619c8`
- `0x140061afc`
- `0x140063dd8`
- `0x140063e3c`
- `0x140063ed4`
- `0x140063f9c`

## import_xrefs

- `KERNEL32!CompareStringA` at `0x140061d6c`
- `KERNEL32!CompareStringA` at `0x140061d6c`
- `KERNEL32!MultiByteToWideChar` at `0x140061e21`
- `KERNEL32!MultiByteToWideChar` at `0x140061e21`
- `KERNEL32!GetLastError` at `0x140061e2b`
- `KERNEL32!GetLastError` at `0x140061e2b`

## pseudocode

```c
__int64 __fastcall Base64ToUnicode(char *a1, int a2, __int64 *a3)
{
  __int64 v5; // r8
  __int64 v6; // rbx
  unsigned __int8 *BufferSetLength; // rax
  int v8; // esi
  PVOID *v9; // r10
  unsigned int v10; // edx
  int v11; // r8d
  const unsigned __int8 *v12; // rbx
  __int64 v13; // rcx
  unsigned int v14; // edi
  __int64 v15; // r8
  char *v16; // rax
  __int64 v17; // rdx
  int v18; // r8d
  const CHAR *v19; // rdi
  int v20; // r8d
  __int64 v21; // r8
  WCHAR *v22; // rax
  DWORD LastError; // ebx
  int v24; // edx
  int v25; // r8d
  unsigned int lpString2; // [rsp+20h] [rbp-20h]
  LPCCH lpMultiByteStr[2]; // [rsp+30h] [rbp-10h] BYREF
  int RequiredLength; // [rsp+78h] [rbp+38h] BYREF
  PCNZCH v30; // [rsp+88h] [rbp+48h] BYREF

  RequiredLength = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sDq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, (_DWORD)a3, (_DWORD)a1);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(lpMultiByteStr);
  RequiredLength = 500;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, v5, a1);
  }
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  BufferSetLength = (unsigned __int8 *)ATL::CSimpleStringT<char,0>::GetBufferSetLength(lpMultiByteStr, 501);
  if ( (unsigned int)ATL::Base64Decode(a1, v6, BufferSetLength, &RequiredLength) )
  {
    ATL::CSimpleStringT<char,0>::ReleaseBuffer(lpMultiByteStr, (unsigned int)RequiredLength);
    v12 = (const unsigned __int8 *)lpMultiByteStr[0];
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, v11, (_DWORD)a1, (__int64)lpMultiByteStr[0]);
    }
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    RequiredLength = ATL::Base64EncodeGetRequiredLength(v13, v10);
    v14 = RequiredLength;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v30);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, v15, v12);
    }
    v16 = (char *)ATL::CSimpleStringT<char,0>::GetBufferSetLength(&v30, v14);
    v17 = -1;
    do
      ++v17;
    while ( v12[v17] );
    if ( (unsigned int)ATL::Base64Encode(v12, v17, v16, &RequiredLength, lpString2) )
    {
      v8 = 0;
      ATL::CSimpleStringT<char,0>::ReleaseBuffer(&v30, (unsigned int)RequiredLength);
      v19 = v30;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, v18, (_DWORD)v12, (__int64)v30);
      }
      if ( CompareStringA(0x7Fu, 0, a1, -1, v19, -1) != 2 )
      {
        v8 = -2147024809;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, v20, (_DWORD)a1, (__int64)v19);
        }
      }
    }
    else
    {
      v8 = -2147024809;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_303f939d6e7d39dbb8332b4d709257ff_Traceguids);
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v30);
    if ( v8 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, v21, v12);
      }
      v22 = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(a3, 500);
      if ( MultiByteToWideChar(0xFDE9u, 0, (LPCCH)v12, -1, v22, 499) )
      {
        ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(a3, 0xFFFFFFFFLL);
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_61;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
          goto LABEL_57;
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v25, (_DWORD)v12, *a3);
      }
      else
      {
        LastError = GetLastError();
        v8 = -2147024809;
        ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(a3, 0);
        v9 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_61;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_57;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_303f939d6e7d39dbb8332b4d709257ff_Traceguids, LastError);
      }
    }
    goto LABEL_56;
  }
  v8 = -2147024809;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_61;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_303f939d6e7d39dbb8332b4d709257ff_Traceguids, 500);
LABEL_56:
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_57:
  if ( v9 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v9 + 28) & 1) != 0
    && *((unsigned __int8 *)v9 + 25) >= ((v8 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_dS((unsigned int)v9[2], 122, (unsigned int)&WPP_303f939d6e7d39dbb8332b4d709257ff_Traceguids, v8, *a3);
  }
LABEL_61:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(lpMultiByteStr);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140061afc  mov     rax, rsp
0x140061aff  mov     [rax+8], rbx
0x140061b03  mov     [rax+18h], rsi
0x140061b07  mov     [rax+10h], edx
0x140061b0a  push    rbp
0x140061b0b  push    rdi
0x140061b0c  push    r12
0x140061b0e  push    r13
0x140061b10  push    r14
0x140061b12  mov     rbp, rsp
0x140061b15  sub     rsp, 40h
0x140061b19  mov     r12, r8
0x140061b1c  mov     r14, rcx
0x140061b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140061b26  lea     rsi, WPP_GLOBAL_Control
0x140061b2d  cmp     rcx, rsi
0x140061b30  jz      short loc_140061B4E
0x140061b32  test    byte ptr [rcx+1Ch], 1
0x140061b36  jz      short loc_140061B4E
0x140061b38  cmp     byte ptr [rcx+19h], 5
0x140061b3c  jb      short loc_140061B4E
0x140061b3e  mov     rcx, [rcx+10h]
0x140061b42  mov     r9, r14
0x140061b45  mov     [rax-40h], r8
0x140061b49  call    WPP_SF_sDq
0x140061b4e  lea     rcx, [rbp+lpMultiByteStr]
0x140061b52  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140061b57  mov     [rbp+arg_8], 1F4h
0x140061b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140061b65  mov     r13d, 2
0x140061b6b  cmp     rcx, rsi
0x140061b6e  jz      short loc_140061B8C
0x140061b70  test    [rcx+1Ch], r13b
0x140061b74  jz      short loc_140061B8C
0x140061b76  cmp     byte ptr [rcx+19h], 5
0x140061b7a  jb      short loc_140061B8C
0x140061b7c  mov     rcx, [rcx+10h]
0x140061b80  lea     edx, [r13+6Eh]
0x140061b84  mov     r9, r14
0x140061b87  call    WPP_SF_s
0x140061b8c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140061b90  mov     rbx, rdi
0x140061b93  inc     rbx
0x140061b96  cmp     byte ptr [r14+rbx], 0
0x140061b9b  jnz     short loc_140061B93
0x140061b9d  mov     edx, 1F5h
0x140061ba2  lea     rcx, [rbp+lpMultiByteStr]
0x140061ba6  call    ?GetBufferSetLength@?$CSimpleStringT@D$0A@@ATL@@QEAAPEADH@Z; ATL::CSimpleStringT<char,0>::GetBufferSetLength(int)
0x140061bab  mov     r8, rax; unsigned __int8 *
0x140061bae  lea     r9, [rbp+arg_8]; int *
0x140061bb2  mov     edx, ebx; int
0x140061bb4  mov     rcx, r14; char *
0x140061bb7  call    ?Base64Decode@ATL@@YAHPEBDHPEAEPEAH@Z; ATL::Base64Decode(char const *,int,uchar *,int *)
0x140061bbc  test    eax, eax
0x140061bbe  jnz     short loc_140061C15
0x140061bc0  mov     esi, 80070057h
0x140061bc5  mov     r10, cs:WPP_GLOBAL_Control
0x140061bcc  lea     rdi, WPP_GLOBAL_Control
0x140061bd3  cmp     r10, rdi
0x140061bd6  jz      loc_140061F07
0x140061bdc  test    [r10+1Ch], r13b
0x140061be0  jz      loc_140061EC6
0x140061be6  cmp     [r10+19h], r13b
0x140061bea  jb      loc_140061EC6
0x140061bf0  mov     rcx, [r10+10h]
0x140061bf4  lea     edx, [rax+71h]
0x140061bf7  mov     eax, [rbp+arg_8]
0x140061bfa  lea     r8, WPP_303f939d6e7d39dbb8332b4d709257ff_Traceguids
0x140061c01  mov     r9d, 1F4h
0x140061c07  mov     dword ptr [rsp+40h+lpString2], eax
0x140061c0b  call    WPP_SF_Dd
0x140061c10  jmp     loc_140061EBF
0x140061c15  mov     edx, [rbp+arg_8]
0x140061c18  lea     rcx, [rbp+lpMultiByteStr]
0x140061c1c  call    ?ReleaseBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::ReleaseBuffer(int)
0x140061c21  mov     rcx, cs:WPP_GLOBAL_Control
0x140061c28  mov     rbx, [rbp+lpMultiByteStr]
0x140061c2c  cmp     rcx, rsi
0x140061c2f  jz      short loc_140061C53
0x140061c31  test    [rcx+1Ch], r13b
0x140061c35  jz      short loc_140061C53
0x140061c37  cmp     byte ptr [rcx+19h], 5
0x140061c3b  jb      short loc_140061C53
0x140061c3d  mov     rcx, [rcx+10h]
0x140061c41  mov     edx, 72h ; 'r'
0x140061c46  mov     r9, r14
0x140061c49  mov     [rsp+40h+lpString2], rbx; unsigned int
0x140061c4e  call    WPP_SF_ss
0x140061c53  mov     rcx, rdi
0x140061c56  inc     rcx; int
0x140061c59  cmp     byte ptr [rbx+rcx], 0
0x140061c5d  jnz     short loc_140061C56
0x140061c5f  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x140061c64  lea     rcx, [rbp+arg_18]
0x140061c68  mov     [rbp+arg_8], eax
0x140061c6b  mov     edi, eax
0x140061c6d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140061c72  mov     rcx, cs:WPP_GLOBAL_Control
0x140061c79  cmp     rcx, rsi
0x140061c7c  jz      short loc_140061C9B
0x140061c7e  test    [rcx+1Ch], r13b
0x140061c82  jz      short loc_140061C9B
0x140061c84  cmp     byte ptr [rcx+19h], 5
0x140061c88  jb      short loc_140061C9B
0x140061c8a  mov     rcx, [rcx+10h]
0x140061c8e  mov     edx, 73h ; 's'
0x140061c93  mov     r9, rbx
0x140061c96  call    WPP_SF_s
0x140061c9b  mov     edx, edi
0x140061c9d  lea     rcx, [rbp+arg_18]
0x140061ca1  call    ?GetBufferSetLength@?$CSimpleStringT@D$0A@@ATL@@QEAAPEADH@Z; ATL::CSimpleStringT<char,0>::GetBufferSetLength(int)
0x140061ca6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140061caa  inc     rdx; int
0x140061cad  cmp     byte ptr [rbx+rdx], 0
0x140061cb1  jnz     short loc_140061CAA
0x140061cb3  lea     r9, [rbp+arg_8]; int *
0x140061cb7  mov     r8, rax; char *
0x140061cba  mov     rcx, rbx; unsigned __int8 *
0x140061cbd  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x140061cc2  test    eax, eax
0x140061cc4  jnz     short loc_140061D0E
0x140061cc6  mov     esi, 80070057h
0x140061ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x140061cd2  lea     rdi, WPP_GLOBAL_Control
0x140061cd9  cmp     rcx, rdi
0x140061cdc  jz      loc_140061DB8
0x140061ce2  test    [rcx+1Ch], r13b
0x140061ce6  jz      loc_140061DB8
0x140061cec  cmp     [rcx+19h], r13b
0x140061cf0  jb      loc_140061DB8
0x140061cf6  mov     rcx, [rcx+10h]
0x140061cfa  lea     edx, [rax+74h]
0x140061cfd  lea     r8, WPP_303f939d6e7d39dbb8332b4d709257ff_Traceguids
0x140061d04  call    WPP_SF_
0x140061d09  jmp     loc_140061DB8
0x140061d0e  mov     edx, [rbp+arg_8]
0x140061d11  lea     rcx, [rbp+arg_18]
0x140061d15  xor     esi, esi
0x140061d17  call    ?ReleaseBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<char,0>::ReleaseBuffer(int)
0x140061d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140061d23  lea     rax, WPP_GLOBAL_Control
0x140061d2a  mov     rdi, [rbp+arg_18]
0x140061d2e  cmp     rcx, rax
0x140061d31  jz      short loc_140061D53
0x140061d33  test    [rcx+1Ch], r13b
0x140061d37  jz      short loc_140061D53
0x140061d39  cmp     byte ptr [rcx+19h], 5
0x140061d3d  jb      short loc_140061D53
0x140061d3f  mov     rcx, [rcx+10h]
0x140061d43  lea     edx, [rsi+75h]
0x140061d46  mov     r9, rbx
0x140061d49  mov     [rsp+40h+lpString2], rdi
0x140061d4e  call    WPP_SF_ss
0x140061d53  xor     edx, edx; dwCmpFlags
0x140061d55  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x140061d5d  or      r9d, 0FFFFFFFFh; cchCount1
0x140061d61  mov     [rsp+40h+lpString2], rdi; lpString2
0x140061d66  mov     r8, r14; lpString1
0x140061d69  lea     ecx, [rdx+7Fh]; Locale
0x140061d6c  call    cs:__imp_CompareStringA
0x140061d72  cmp     eax, r13d
0x140061d75  jz      short loc_140061DB1
0x140061d77  mov     esi, 80070057h
0x140061d7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140061d83  lea     rax, WPP_GLOBAL_Control
0x140061d8a  cmp     rcx, rax
0x140061d8d  jz      short loc_140061DB1
0x140061d8f  test    [rcx+1Ch], r13b
0x140061d93  jz      short loc_140061DB1
0x140061d95  cmp     [rcx+19h], r13b
0x140061d99  jb      short loc_140061DB1
0x140061d9b  mov     rcx, [rcx+10h]
0x140061d9f  mov     edx, 76h ; 'v'
0x140061da4  mov     r9, r14
0x140061da7  mov     [rsp+40h+lpString2], rdi
0x140061dac  call    WPP_SF_ss
0x140061db1  lea     rdi, WPP_GLOBAL_Control
0x140061db8  lea     rcx, [rbp+arg_18]
0x140061dbc  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140061dc1  test    esi, esi
0x140061dc3  js      loc_140061EBF
0x140061dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140061dd0  lea     rax, WPP_GLOBAL_Control
0x140061dd7  cmp     rcx, rax
0x140061dda  jz      short loc_140061DF9
0x140061ddc  test    [rcx+1Ch], r13b
0x140061de0  jz      short loc_140061DF9
0x140061de2  cmp     byte ptr [rcx+19h], 5
0x140061de6  jb      short loc_140061DF9
0x140061de8  mov     rcx, [rcx+10h]
0x140061dec  mov     edx, 77h ; 'w'
0x140061df1  mov     r9, rbx
0x140061df4  call    WPP_SF_s
0x140061df9  mov     edx, 1F4h
0x140061dfe  mov     rcx, r12
0x140061e01  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x140061e06  or      r9d, 0FFFFFFFFh; cbMultiByte
0x140061e0a  mov     [rsp+40h+cchCount2], 1F3h; cchWideChar
0x140061e12  mov     r8, rbx; lpMultiByteStr
0x140061e15  mov     [rsp+40h+lpString2], rax; lpWideCharStr
0x140061e1a  xor     edx, edx; dwFlags
0x140061e1c  mov     ecx, 0FDE9h; CodePage
0x140061e21  call    cs:__imp_MultiByteToWideChar
0x140061e27  test    eax, eax
0x140061e29  jnz     short loc_140061E7F
0x140061e2b  call    cs:__imp_GetLastError
0x140061e31  xor     edx, edx
0x140061e33  mov     rcx, r12
0x140061e36  mov     ebx, eax
0x140061e38  mov     esi, 80070057h
0x140061e3d  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x140061e42  mov     r10, cs:WPP_GLOBAL_Control
0x140061e49  lea     rdi, WPP_GLOBAL_Control
0x140061e50  cmp     r10, rdi
0x140061e53  jz      loc_140061F07
0x140061e59  test    [r10+1Ch], r13b
0x140061e5d  jz      short loc_140061EC6
0x140061e5f  cmp     [r10+19h], r13b
0x140061e63  jb      short loc_140061EC6
0x140061e65  mov     rcx, [r10+10h]
0x140061e69  lea     r8, WPP_303f939d6e7d39dbb8332b4d709257ff_Traceguids
0x140061e70  mov     edx, 78h ; 'x'
0x140061e75  mov     r9d, ebx
0x140061e78  call    WPP_SF_d
0x140061e7d  jmp     short loc_140061EBF
0x140061e7f  or      edx, 0FFFFFFFFh
0x140061e82  mov     rcx, r12
0x140061e85  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x140061e8a  mov     r10, cs:WPP_GLOBAL_Control
0x140061e91  lea     rdi, WPP_GLOBAL_Control
0x140061e98  cmp     r10, rdi
0x140061e9b  jz      short loc_140061F07
0x140061e9d  test    [r10+1Ch], r13b
0x140061ea1  jz      short loc_140061EC6
0x140061ea3  cmp     byte ptr [r10+19h], 5
0x140061ea8  jb      short loc_140061EC6
0x140061eaa  mov     rax, [r12]
0x140061eae  mov     r9, rbx
0x140061eb1  mov     rcx, [r10+10h]
0x140061eb5  mov     [rsp+40h+lpString2], rax
0x140061eba  call    WPP_SF_sS
0x140061ebf  mov     r10, cs:WPP_GLOBAL_Control
0x140061ec6  cmp     r10, rdi
0x140061ec9  jz      short loc_140061F07
0x140061ecb  test    byte ptr [r10+1Ch], 1
0x140061ed0  jz      short loc_140061F07
0x140061ed2  movzx   ecx, byte ptr [r10+19h]
0x140061ed7  mov     edx, esi
0x140061ed9  sar     edx, 1Fh
0x140061edc  and     edx, 0FFFFFFFDh
0x140061edf  add     edx, 5
0x140061ee2  cmp     ecx, edx
0x140061ee4  jb      short loc_140061F07
0x140061ee6  mov     rcx, [r12]
0x140061eea  lea     r8, WPP_303f939d6e7d39dbb8332b4d709257ff_Traceguids
0x140061ef1  mov     [rsp+40h+lpString2], rcx
0x140061ef6  mov     edx, 7Ah ; 'z'
0x140061efb  mov     rcx, [r10+10h]
0x140061eff  mov     r9d, esi
0x140061f02  call    WPP_SF_dS
0x140061f07  lea     rcx, [rbp+lpMultiByteStr]
0x140061f0b  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140061f10  lea     r11, [rsp+40h+var_s0]
0x140061f15  mov     eax, esi
0x140061f17  mov     rbx, [r11+30h]
0x140061f1b  mov     rsi, [r11+40h]
0x140061f1f  mov     rsp, r11
0x140061f22  pop     r14
0x140061f24  pop     r13
0x140061f26  pop     r12
0x140061f28  pop     rdi
0x140061f29  pop     rbp
0x140061f2a  retn
```
