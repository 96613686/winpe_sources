# Triggers::Trigulator::StreamOut(HKEY__ *)

- ea: `0x180018a20`
- end: `0x18001902a`
- name: `?StreamOut@Trigulator@Triggers@@QEBAJPEAUHKEY__@@@Z`
- size: `1546`
- prototype: `int(Triggers::Trigulator *__hidden this, HKEY)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x180017e70`
- `0x18002db7c`

## callees

- `0x180016ed0`
- `0x180016f70`
- `0x180018a20`
- `0x180019030`
- `0x180019130`
- `0x180019150`
- `0x18001a260`
- `0x18002dce0`
- `0x18004aadc`
- `0x18004ada0`
- `0x18004beec`
- `0x180056794`
- `0x18005790c`
- `0x180057926`
- `0x18007e68a`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018a7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018b5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018fa0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018a7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018b5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018fa0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180018bb1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180018bb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018f75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019007`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018f75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019007`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018c66`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018c66`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Triggers::Trigulator::StreamOut(Triggers::Trigulator *this, HKEY a2)
{
  int v4; // ebx
  __int64 result; // rax
  const BYTE **v6; // rcx
  const BYTE *lpData; // rcx
  __int64 v8; // rax
  LSTATUS v9; // eax
  signed int v10; // esi
  LSTATUS v11; // eax
  unsigned __int16 *v12; // rbx
  Triggers::Trigulator *v13; // rcx
  const unsigned __int16 *v14; // r8
  int v15; // eax
  __int64 cbData; // r15
  __int64 *i; // rbx
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rsi
  const unsigned __int8 *v20; // r12
  unsigned __int8 *v21; // rax
  unsigned int StorageSize; // eax
  __int64 v23; // r13
  unsigned __int8 *v24; // rcx
  unsigned int v25; // r9d
  __int64 *v26; // rax
  __int64 v27; // r10
  unsigned int v28; // r9d
  const void *v29; // r10
  __int64 v30; // rbx
  unsigned __int64 v31; // rdx
  unsigned int v32; // r8d
  void **v33; // rax
  void *v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 *v37; // rbx
  int v38; // r13d
  _QWORD v39[2]; // [rsp+30h] [rbp-50h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-40h] BYREF
  char v41; // [rsp+48h] [rbp-38h]
  const unsigned __int16 *v42; // [rsp+50h] [rbp-30h]
  __int64 v43; // [rsp+58h] [rbp-28h]
  __int64 v44; // [rsp+60h] [rbp-20h]
  int v45; // [rsp+68h] [rbp-18h]
  __int64 v46; // [rsp+6Ch] [rbp-14h]
  unsigned int v47; // [rsp+C0h] [rbp+40h] BYREF
  unsigned __int8 *v48; // [rsp+D0h] [rbp+50h] BYREF
  unsigned __int16 *v49; // [rsp+D8h] [rbp+58h] BYREF

  if ( *(_OWORD *)((char *)this + 40) == 0 )
  {
    v4 = RegSetValueExW(a2, L"Triggers", 0, 3u, &NullData, 8u);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
          (unsigned int)L"Triggers",
          v4);
      }
      if ( v4 > 0 )
        return (unsigned __int16)v4 | 0x80070000;
    }
    return (unsigned int)v4;
  }
  result = Triggers::Trigulator::WriteRegistrationData(this, a2);
  if ( (int)result < 0 )
    return result;
  v49 = 0;
  v47 = 0;
  v6 = *(const BYTE ***)(*((_QWORD *)this + 6) + 176LL);
  if ( v6 && (lpData = *v6) != 0 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&lpData[2 * v8] );
    v9 = RegSetValueExW(a2, L"Package", 0, 1u, lpData, 2 * v8 + 2);
    v10 = v9;
    if ( v9
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
        (unsigned int)L"Package",
        v9);
    }
  }
  else
  {
    v11 = RegDeleteValueW(a2, L"Package");
    v10 = 0;
    if ( v11 != 2 )
      v10 = v11;
  }
  if ( v10 )
  {
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
  }
  else
  {
    JobBucket::GetCapabilities(*((_QWORD *)this + 6), &v49, &v47);
    v12 = v49;
    v15 = Triggers::Trigulator::WriteMultiString(v13, a2, v14, v49, v47);
    v10 = v15;
    if ( !v15 )
    {
      operator delete(v12);
      goto LABEL_32;
    }
    if ( v15 > 0 )
      v10 = (unsigned __int16)v15 | 0x80070000;
    operator delete(v12);
  }
  if ( v10 < 0 )
    return (unsigned int)v10;
LABEL_32:
  cbData = JobBucket::GetStorageSize(*((JobBucket **)this + 6)) + 40;
  for ( i = (__int64 *)*((_QWORD *)this + 4);
        ;
        cbData = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)i[2] + 88LL))(i[2]) + (unsigned int)cbData )
  {
    i = (__int64 *)*i;
    if ( i == *((__int64 **)this + 4) )
      break;
  }
  v49 = 0;
  v18 = (unsigned __int16 *)HeapAlloc(g_PrivateHeap, 0, (unsigned int)cbData);
  v19 = v18;
  if ( !v18 )
  {
    v41 = 0;
    v42 = &qword_1800A4718;
    v43 = 0;
    v44 = 0;
    v45 = 14;
    v46 = -1;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&pExceptionObject;
  }
  v49 = v18;
  v20 = (const unsigned __int8 *)v18 + cbData;
  v48 = (unsigned __int8 *)v18;
  memset_0(v18, 72, (unsigned int)cbData);
  *(_QWORD *)v48 = 23;
  v21 = v48 + 8;
  v48 = v21;
  *(_OWORD *)v21 = *(_OWORD *)this;
  *((_OWORD *)v21 + 1) = *((_OWORD *)this + 1);
  v48 += 32;
  StorageSize = JobBucket::GetStorageSize(*((JobBucket **)this + 6));
  if ( &v48[StorageSize] > v20 )
  {
    operator delete(v19);
    return 2147549183LL;
  }
  v39[0] = &v48;
  v39[1] = v20;
  if ( v48 + 8 > v20 )
    goto LABEL_40;
  v23 = *((_QWORD *)this + 6);
  *(_DWORD *)v48 = *(_DWORD *)(v23 + 16);
  v24 = v48 + 8;
  v48 = v24;
  if ( v24 + 8 > v20 )
    goto LABEL_40;
  *(_DWORD *)v24 = *(_DWORD *)(v23 + 24);
  v48 += 8;
  if ( _bstr_t::length((_bstr_t *)(v23 + 72)) )
  {
    v25 = 2 * _bstr_t::length((_bstr_t *)(v23 + 72)) + 2;
    v26 = *(__int64 **)(v23 + 72);
    if ( v26 )
      v27 = *v26;
    else
      v27 = 0;
    v47 = v25;
    if ( !v25 || v27 )
    {
      v4 = DataAligner::WriteFixedSize<unsigned long>((__int64)v39, &v47);
      if ( v4 >= 0 && v28 )
      {
        if ( v29 && (v30 = (v28 + 7) & 0xFFFFFFF8, &v48[v30] <= v20) )
        {
          memcpy_0(v48, v29, v28);
          v48 += v30;
          v4 = 0;
        }
        else
        {
          v4 = -2147418113;
        }
      }
      if ( v4 < 0 )
        goto LABEL_77;
      goto LABEL_57;
    }
LABEL_40:
    v4 = -2147418113;
    goto LABEL_77;
  }
  v47 = 0;
  v4 = DataAligner::WriteFixedSize<unsigned long>((__int64)v39, &v47);
  if ( v4 < 0 )
    goto LABEL_77;
LABEL_57:
  if ( _bstr_t::length((_bstr_t *)(v23 + 80)) )
  {
    v32 = 2 * _bstr_t::length((_bstr_t *)(v23 + 80)) + 2;
    v33 = *(void ***)(v23 + 80);
    if ( v33 )
      v34 = *v33;
    else
      v34 = 0;
    v4 = DataAligner::WriteVarSize((DataAligner *)v39, v34, v32);
    if ( v4 < 0 )
      goto LABEL_77;
  }
  else
  {
    v47 = 0;
    v4 = DataAligner::WriteFixedSize<unsigned long>((__int64)v39, &v47);
    if ( v4 < 0 )
      goto LABEL_77;
  }
  v4 = User::StreamOutImpl((User *)(v23 + 64), v31, &v48, v20);
  if ( v4 < 0 )
    goto LABEL_77;
  v35 = *(_QWORD *)(v23 + 208);
  if ( !v35 )
  {
    v47 = 0;
    v4 = DataAligner::WriteFixedSize<unsigned long>((__int64)v39, &v47);
    if ( v4 >= 0 )
      goto LABEL_78;
    goto LABEL_77;
  }
  if ( !TSTimePeriod::IsEmpty((TSTimePeriod *)(v35 + 56))
    || !TSTimePeriod::IsEmpty((TSTimePeriod *)(v36 + 70))
    || *(_DWORD *)(v36 + 84) == 1 )
  {
    v4 = DataAligner::WriteVarSize((DataAligner *)v39, (void *)v36, 0x58u);
    if ( v4 < 0 )
      goto LABEL_77;
    goto LABEL_78;
  }
  if ( !*(_QWORD *)(v36 + 48) )
  {
    v4 = DataAligner::WriteVarSize((DataAligner *)v39, (void *)v36, 0x2Cu);
    if ( v4 < 0 )
      goto LABEL_77;
LABEL_78:
    v37 = (__int64 *)*((_QWORD *)this + 4);
    while ( 1 )
    {
      v37 = (__int64 *)*v37;
      if ( v37 == *((__int64 **)this + 4) )
        break;
      v38 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int8 **, const unsigned __int8 *))(*(_QWORD *)v37[2] + 96LL))(
              v37[2],
              23,
              &v48,
              v20);
      if ( v38 < 0 )
      {
        HeapFree(g_PrivateHeap, 0, v19);
        return (unsigned int)v38;
      }
    }
    v4 = RegSetValueExW(a2, L"Triggers", 0, 3u, (const BYTE *)v19, cbData);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids,
          (unsigned int)L"Triggers",
          v4);
      }
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
    }
    HeapFree(g_PrivateHeap, 0, v19);
    return (unsigned int)v4;
  }
  v4 = DataAligner::WriteVarSize((DataAligner *)v39, (void *)v36, 0x38u);
  if ( v4 >= 0 )
    goto LABEL_78;
LABEL_77:
  operator delete(v19);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180018a20  mov     [rsp-38h+arg_8], rbx
0x180018a25  push    rbp
0x180018a26  push    rsi
0x180018a27  push    rdi
0x180018a28  push    r12
0x180018a2a  push    r13
0x180018a2c  push    r14
0x180018a2e  push    r15
0x180018a30  mov     rbp, rsp
0x180018a33  sub     rsp, 80h
0x180018a3a  mov     r14, rdx
0x180018a3d  mov     rdi, rcx
0x180018a40  cmp     qword ptr [rcx+28h], 0
0x180018a45  jnz     loc_180018AE5
0x180018a4b  cmp     qword ptr [rcx+30h], 0
0x180018a50  jnz     loc_180018AE5
0x180018a56  mov     [rsp+80h+cbData], 8; cbData
0x180018a5e  lea     rax, ?NullData@@3PAEA; uchar near * NullData
0x180018a65  mov     [rsp+80h+lpData], rax; lpData
0x180018a6a  mov     r9d, 3; dwType
0x180018a70  xor     r8d, r8d; Reserved
0x180018a73  lea     rdx, aTriggers; "Triggers"
0x180018a7a  mov     rcx, r14; hKey
0x180018a7d  call    cs:__imp_RegSetValueExW
0x180018a83  mov     ebx, eax
0x180018a85  test    eax, eax
0x180018a87  jz      loc_18001900D
0x180018a8d  lea     rax, WPP_GLOBAL_Control
0x180018a94  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a9b  cmp     rcx, rax
0x180018a9e  jz      short loc_180018ACF
0x180018aa0  test    dword ptr [rcx+1Ch], 40000h
0x180018aa7  jz      short loc_180018ACF
0x180018aa9  cmp     byte ptr [rcx+19h], 2
0x180018aad  jb      short loc_180018ACF
0x180018aaf  mov     edx, 12h
0x180018ab4  mov     dword ptr [rsp+80h+lpData], ebx
0x180018ab8  lea     r9, aTriggers; "Triggers"
0x180018abf  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x180018ac6  mov     rcx, [rcx+10h]
0x180018aca  call    WPP_SF_Sd
0x180018acf  test    ebx, ebx
0x180018ad1  jle     loc_18001900D
0x180018ad7  movzx   ebx, bx
0x180018ada  or      ebx, 80070000h
0x180018ae0  jmp     loc_18001900D
0x180018ae5  call    ?WriteRegistrationData@Trigulator@Triggers@@AEBAJPEAUHKEY__@@@Z; Triggers::Trigulator::WriteRegistrationData(HKEY__ *)
0x180018aea  test    eax, eax
0x180018aec  js      loc_18001900F
0x180018af2  xor     r12d, r12d
0x180018af5  mov     [rbp+arg_18], r12
0x180018af9  mov     [rbp+arg_0], r12d
0x180018afd  mov     rax, [rdi+30h]
0x180018b01  mov     rcx, [rax+0B0h]
0x180018b08  lea     rbx, WPP_GLOBAL_Control
0x180018b0f  test    rcx, rcx
0x180018b12  jz      loc_180018BA7
0x180018b18  mov     rcx, [rcx]
0x180018b1b  test    rcx, rcx
0x180018b1e  jz      loc_180018BA7
0x180018b24  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180018b2b  nop     dword ptr [rax+rax+00h]
0x180018b30  lea     rax, [rax+1]
0x180018b34  cmp     word ptr [rcx+rax*2], 0
0x180018b39  jnz     short loc_180018B30
0x180018b3b  lea     eax, ds:2[rax*2]
0x180018b42  mov     [rsp+80h+cbData], eax; cbData
0x180018b46  mov     [rsp+80h+lpData], rcx; lpData
0x180018b4b  mov     r9d, 1; dwType
0x180018b51  xor     r8d, r8d; Reserved
0x180018b54  lea     rdx, aPackage; "Package"
0x180018b5b  mov     rcx, r14; hKey
0x180018b5e  call    cs:__imp_RegSetValueExW
0x180018b64  mov     esi, eax
0x180018b66  test    eax, eax
0x180018b68  jz      short loc_180018BC0
0x180018b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b71  cmp     rcx, rbx
0x180018b74  jz      short loc_180018BC0
0x180018b76  test    dword ptr [rcx+1Ch], 40000h
0x180018b7d  jz      short loc_180018BC0
0x180018b7f  cmp     byte ptr [rcx+19h], 2
0x180018b83  jb      short loc_180018BC0
0x180018b85  mov     edx, 10h
0x180018b8a  mov     dword ptr [rsp+80h+lpData], eax
0x180018b8e  lea     r9, aPackage; "Package"
0x180018b95  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x180018b9c  mov     rcx, [rcx+10h]
0x180018ba0  call    WPP_SF_Sd
0x180018ba5  jmp     short loc_180018BC0
0x180018ba7  lea     rdx, aPackage; "Package"
0x180018bae  mov     rcx, r14; hKey
0x180018bb1  call    cs:__imp_RegDeleteValueW
0x180018bb7  mov     esi, r12d
0x180018bba  cmp     eax, 2
0x180018bbd  cmovnz  esi, eax
0x180018bc0  test    esi, esi
0x180018bc2  jz      short loc_180018BD1
0x180018bc4  jle     short loc_180018BCF
0x180018bc6  movzx   esi, si
0x180018bc9  or      esi, 80070000h
0x180018bcf  jmp     short loc_180018C11
0x180018bd1  lea     r8, [rbp+arg_0]
0x180018bd5  lea     rdx, [rbp+arg_18]
0x180018bd9  mov     rcx, [rdi+30h]
0x180018bdd  call    ?GetCapabilities@JobBucket@@QEBAXAEAV?$AutoVectorPtr@G@wmi@@AEAK@Z; JobBucket::GetCapabilities(wmi::AutoVectorPtr<ushort> &,ulong &)
0x180018be2  mov     eax, [rbp+arg_0]
0x180018be5  mov     dword ptr [rsp+80h+lpData], eax; unsigned int
0x180018be9  mov     rbx, [rbp+arg_18]
0x180018bed  mov     r9, rbx; unsigned __int16 *
0x180018bf0  mov     rdx, r14; HKEY
0x180018bf3  call    ?WriteMultiString@Trigulator@Triggers@@AEBAKPEAUHKEY__@@PEBGPEAGK@Z; Triggers::Trigulator::WriteMultiString(HKEY__ *,ushort const *,ushort *,ulong)
0x180018bf8  mov     esi, eax
0x180018bfa  test    eax, eax
0x180018bfc  jz      short loc_180018C1C
0x180018bfe  jle     short loc_180018C09
0x180018c00  movzx   esi, ax
0x180018c03  or      esi, 80070000h
0x180018c09  mov     rcx, rbx; void *
0x180018c0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018c11  test    esi, esi
0x180018c13  jns     short loc_180018C24
0x180018c15  mov     eax, esi
0x180018c17  jmp     loc_18001900F
0x180018c1c  mov     rcx, rbx; void *
0x180018c1f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018c24  mov     rcx, [rdi+30h]; this
0x180018c28  call    ?GetStorageSize@JobBucket@@QEBAKXZ; JobBucket::GetStorageSize(void)
0x180018c2d  lea     r15d, [rax+28h]
0x180018c31  mov     rbx, [rdi+20h]
0x180018c35  mov     rbx, [rbx]
0x180018c38  cmp     rbx, [rdi+20h]
0x180018c3c  jz      short loc_180018C53
0x180018c3e  mov     rcx, [rbx+10h]
0x180018c42  mov     rdx, [rcx]
0x180018c45  mov     rax, [rdx+58h]
0x180018c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c4e  add     r15d, eax
0x180018c51  jmp     short loc_180018C35
0x180018c53  mov     [rbp+arg_18], r12
0x180018c57  mov     ebx, r15d
0x180018c5a  mov     r8d, r15d; dwBytes
0x180018c5d  xor     edx, edx; dwFlags
0x180018c5f  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180018c66  call    cs:__imp_HeapAlloc
0x180018c6c  mov     rsi, rax
0x180018c6f  test    rax, rax
0x180018c72  jnz     short loc_180018CB5
0x180018c74  mov     [rbp+var_38], al
0x180018c77  lea     rax, qword_1800A4718
0x180018c7e  mov     [rbp+var_30], rax
0x180018c82  mov     [rbp+var_28], r12
0x180018c86  mov     [rbp+var_20], r12
0x180018c8a  mov     [rbp+var_18], 0Eh
0x180018c91  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180018c99  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180018ca0  mov     [rbp+pExceptionObject], rax
0x180018ca4  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180018cab  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018caf  call    _CxxThrowException_0
0x180018cb5  mov     [rbp+arg_18], rsi
0x180018cb9  lea     r12, [r15+rax]
0x180018cbd  mov     [rbp+arg_10], rsi
0x180018cc1  mov     r8, rbx; Size
0x180018cc4  mov     edx, 48h ; 'H'; Val
0x180018cc9  mov     rcx, rsi; void *
0x180018ccc  call    memset_0
0x180018cd1  mov     rax, [rbp+arg_10]
0x180018cd5  mov     qword ptr [rax], 17h
0x180018cdc  mov     rax, [rbp+arg_10]
0x180018ce0  add     rax, 8
0x180018ce4  mov     [rbp+arg_10], rax
0x180018ce8  movups  xmm0, xmmword ptr [rdi]
0x180018ceb  movups  xmmword ptr [rax], xmm0
0x180018cee  movups  xmm1, xmmword ptr [rdi+10h]
0x180018cf2  movups  xmmword ptr [rax+10h], xmm1
0x180018cf6  add     [rbp+arg_10], 20h ; ' '
0x180018cfb  mov     rcx, [rdi+30h]; this
0x180018cff  call    ?GetStorageSize@JobBucket@@QEBAKXZ; JobBucket::GetStorageSize(void)
0x180018d04  mov     eax, eax
0x180018d06  mov     rcx, [rbp+arg_10]
0x180018d0a  add     rax, rcx
0x180018d0d  cmp     rax, r12
0x180018d10  jbe     short loc_180018D24
0x180018d12  mov     rcx, rsi; void *
0x180018d15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018d1a  mov     eax, 8000FFFFh
0x180018d1f  jmp     loc_18001900F
0x180018d24  lea     rax, [rbp+arg_10]
0x180018d28  mov     [rbp+var_50], rax
0x180018d2c  mov     [rbp+var_48], r12
0x180018d30  lea     rax, [rcx+8]
0x180018d34  cmp     rax, r12
0x180018d37  jbe     short loc_180018D43
0x180018d39  mov     ebx, 8000FFFFh
0x180018d3e  jmp     loc_180018F2C
0x180018d43  mov     r13, [rdi+30h]
0x180018d47  mov     eax, [r13+10h]
0x180018d4b  mov     [rcx], eax
0x180018d4d  mov     rcx, [rbp+arg_10]
0x180018d51  add     rcx, 8
0x180018d55  mov     [rbp+arg_10], rcx
0x180018d59  lea     rax, [rcx+8]
0x180018d5d  cmp     rax, r12
0x180018d60  ja      short loc_180018D39
0x180018d62  mov     eax, [r13+18h]
0x180018d66  mov     [rcx], eax
0x180018d68  add     [rbp+arg_10], 8
0x180018d6d  lea     rcx, [r13+48h]; this
0x180018d71  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180018d76  test    eax, eax
0x180018d78  jnz     short loc_180018D99
0x180018d7a  mov     [rbp+arg_0], eax
0x180018d7d  lea     rdx, [rbp+arg_0]
0x180018d81  lea     rcx, [rbp+var_50]
0x180018d85  call    ??$WriteFixedSize@K@DataAligner@@QEAAJAEBK@Z; DataAligner::WriteFixedSize<ulong>(ulong const &)
0x180018d8a  mov     ebx, eax
0x180018d8c  test    eax, eax
0x180018d8e  js      loc_180018F2C
0x180018d94  jmp     loc_180018E23
0x180018d99  lea     rcx, [r13+48h]; this
0x180018d9d  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180018da2  lea     r9d, ds:2[rax*2]
0x180018daa  mov     rax, [r13+48h]
0x180018dae  test    rax, rax
0x180018db1  jz      short loc_180018DB8
0x180018db3  mov     r10, [rax]
0x180018db6  jmp     short loc_180018DBB
0x180018db8  xor     r10d, r10d
0x180018dbb  mov     [rbp+arg_0], r9d
0x180018dbf  test    r9d, r9d
0x180018dc2  jz      short loc_180018DCD
0x180018dc4  test    r10, r10
0x180018dc7  jz      loc_180018D39
0x180018dcd  lea     rdx, [rbp+arg_0]
0x180018dd1  lea     rcx, [rbp+var_50]
0x180018dd5  call    ??$WriteFixedSize@K@DataAligner@@QEAAJAEBK@Z; DataAligner::WriteFixedSize<ulong>(ulong const &)
0x180018dda  mov     ebx, eax
0x180018ddc  test    eax, eax
0x180018dde  js      short loc_180018E1B
0x180018de0  test    r9d, r9d
0x180018de3  jz      short loc_180018E1B
0x180018de5  test    r10, r10
0x180018de8  jz      short loc_180018E16
0x180018dea  lea     ebx, [r9+7]
0x180018dee  mov     eax, 0FFFFFFF8h
0x180018df3  and     rbx, rax
0x180018df6  mov     rcx, [rbp+arg_10]; void *
0x180018dfa  lea     rax, [rbx+rcx]
0x180018dfe  cmp     rax, r12
0x180018e01  ja      short loc_180018E16
0x180018e03  mov     r8d, r9d; Size
0x180018e06  mov     rdx, r10; Src
0x180018e09  call    memcpy_0
0x180018e0e  add     [rbp+arg_10], rbx
0x180018e12  xor     ebx, ebx
0x180018e14  jmp     short loc_180018E1B
0x180018e16  mov     ebx, 8000FFFFh
0x180018e1b  test    ebx, ebx
0x180018e1d  js      loc_180018F2C
0x180018e23  lea     rcx, [r13+50h]; this
0x180018e27  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180018e2c  test    eax, eax
0x180018e2e  jnz     short loc_180018E4C
0x180018e30  mov     [rbp+arg_0], eax
0x180018e33  lea     rdx, [rbp+arg_0]
0x180018e37  lea     rcx, [rbp+var_50]
0x180018e3b  call    ??$WriteFixedSize@K@DataAligner@@QEAAJAEBK@Z; DataAligner::WriteFixedSize<ulong>(ulong const &)
0x180018e40  mov     ebx, eax
0x180018e42  test    eax, eax
0x180018e44  js      loc_180018F2C
0x180018e4a  jmp     short loc_180018E80
0x180018e4c  lea     rcx, [r13+50h]; this
0x180018e50  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180018e55  lea     r8d, ds:2[rax*2]; unsigned int
0x180018e5d  mov     rax, [r13+50h]
0x180018e61  test    rax, rax
0x180018e64  jz      short loc_180018E6B
0x180018e66  mov     rdx, [rax]
0x180018e69  jmp     short loc_180018E6D
0x180018e6b  xor     edx, edx; void *
0x180018e6d  lea     rcx, [rbp+var_50]; this
0x180018e71  call    ?WriteVarSize@DataAligner@@QEAAJPEAXK@Z; DataAligner::WriteVarSize(void *,ulong)
0x180018e76  mov     ebx, eax
0x180018e78  test    eax, eax
0x180018e7a  js      loc_180018F2C
0x180018e80  lea     rcx, [r13+40h]; this
0x180018e84  mov     r9, r12; unsigned __int8 *
0x180018e87  lea     r8, [rbp+arg_10]; unsigned __int8 **
0x180018e8b  call    ?StreamOutImpl@User@@QEBAJ_KAEAPEAEPEBE@Z; User::StreamOutImpl(unsigned __int64,uchar * &,uchar const *)
0x180018e90  mov     ebx, eax
0x180018e92  test    eax, eax
0x180018e94  js      loc_180018F2C
0x180018e9a  mov     rdx, [r13+0D0h]
0x180018ea1  test    rdx, rdx
0x180018ea4  jz      short loc_180018F0E
0x180018ea6  lea     rcx, [rdx+38h]; this
0x180018eaa  call    ?IsEmpty@TSTimePeriod@@QEBA_NXZ; TSTimePeriod::IsEmpty(void)
0x180018eaf  test    al, al
0x180018eb1  jz      short loc_180018EF7
  ... truncated ...
```
