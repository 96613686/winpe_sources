# Triggers::Trigulator::StreamOut(HKEY__ *)

- ea: `0x1800324f0`
- end: `0x180032b20`
- name: `?StreamOut@Trigulator@Triggers@@QEBAJPEAUHKEY__@@@Z`
- size: `1584`
- prototype: `int(Triggers::Trigulator *__hidden this, HKEY)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x18002dbc4`
- `0x180031a40`

## callees

- `0x180004d10`
- `0x18000cc40`
- `0x1800324f0`
- `0x180032b28`
- `0x180032c30`
- `0x180032c58`
- `0x180034168`
- `0x180034510`
- `0x18004c9f4`
- `0x18004d1f0`
- `0x18004e3f8`
- `0x180059140`
- `0x18005a2bc`
- `0x18005a2d6`
- `0x1800829fa`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003254d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003262f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032a89`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003254d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003262f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032a89`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032688`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180032688`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032a58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032af6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032a58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180032af6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032743`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032743`

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
    v42 = &qword_1800A8718;
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
      v4 = DataAligner::WriteFixedSize<unsigned long>(v39, &v47);
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
  v4 = DataAligner::WriteFixedSize<unsigned long>(v39, &v47);
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
    v4 = DataAligner::WriteFixedSize<unsigned long>(v39, &v47);
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
    v4 = DataAligner::WriteFixedSize<unsigned long>(v39, &v47);
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
0x1800324f0  mov     [rsp-38h+arg_8], rbx
0x1800324f5  push    rbp
0x1800324f6  push    rsi
0x1800324f7  push    rdi
0x1800324f8  push    r12
0x1800324fa  push    r13
0x1800324fc  push    r14
0x1800324fe  push    r15
0x180032500  mov     rbp, rsp
0x180032503  sub     rsp, 80h
0x18003250a  mov     r14, rdx
0x18003250d  mov     rdi, rcx
0x180032510  cmp     qword ptr [rcx+28h], 0
0x180032515  jnz     loc_1800325BB
0x18003251b  cmp     qword ptr [rcx+30h], 0
0x180032520  jnz     loc_1800325BB
0x180032526  mov     [rsp+80h+cbData], 8; cbData
0x18003252e  lea     rax, ?NullData@@3PAEA; uchar near * NullData
0x180032535  mov     [rsp+80h+lpData], rax; lpData
0x18003253a  mov     r9d, 3; dwType
0x180032540  xor     r8d, r8d; Reserved
0x180032543  lea     rdx, aTriggers; "Triggers"
0x18003254a  mov     rcx, r14; hKey
0x18003254d  call    cs:__imp_RegSetValueExW
0x180032554  nop     dword ptr [rax+rax+00h]
0x180032559  mov     ebx, eax
0x18003255b  test    eax, eax
0x18003255d  jz      loc_180032B02
0x180032563  lea     rax, WPP_GLOBAL_Control
0x18003256a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032571  cmp     rcx, rax
0x180032574  jz      short loc_1800325A5
0x180032576  test    dword ptr [rcx+1Ch], 40000h
0x18003257d  jz      short loc_1800325A5
0x18003257f  cmp     byte ptr [rcx+19h], 2
0x180032583  jb      short loc_1800325A5
0x180032585  mov     edx, 12h
0x18003258a  mov     dword ptr [rsp+80h+lpData], ebx
0x18003258e  lea     r9, aTriggers; "Triggers"
0x180032595  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x18003259c  mov     rcx, [rcx+10h]
0x1800325a0  call    WPP_SF_Sd
0x1800325a5  test    ebx, ebx
0x1800325a7  jle     loc_180032B02
0x1800325ad  movzx   ebx, bx
0x1800325b0  or      ebx, 80070000h
0x1800325b6  jmp     loc_180032B02
0x1800325bb  call    ?WriteRegistrationData@Trigulator@Triggers@@AEBAJPEAUHKEY__@@@Z; Triggers::Trigulator::WriteRegistrationData(HKEY__ *)
0x1800325c0  test    eax, eax
0x1800325c2  js      loc_180032B04
0x1800325c8  xor     r12d, r12d
0x1800325cb  mov     [rbp+arg_18], r12
0x1800325cf  mov     [rbp+arg_0], r12d
0x1800325d3  mov     rax, [rdi+30h]
0x1800325d7  mov     rcx, [rax+0B0h]
0x1800325de  lea     rbx, WPP_GLOBAL_Control
0x1800325e5  test    rcx, rcx
0x1800325e8  jz      loc_18003267E
0x1800325ee  mov     rcx, [rcx]
0x1800325f1  test    rcx, rcx
0x1800325f4  jz      loc_18003267E
0x1800325fa  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180032601  lea     rax, [rax+1]
0x180032605  cmp     word ptr [rcx+rax*2], 0
0x18003260a  jnz     short loc_180032601
0x18003260c  lea     eax, ds:2[rax*2]
0x180032613  mov     [rsp+80h+cbData], eax; cbData
0x180032617  mov     [rsp+80h+lpData], rcx; lpData
0x18003261c  mov     r9d, 1; dwType
0x180032622  xor     r8d, r8d; Reserved
0x180032625  lea     rdx, aPackage; "Package"
0x18003262c  mov     rcx, r14; hKey
0x18003262f  call    cs:__imp_RegSetValueExW
0x180032636  nop     dword ptr [rax+rax+00h]
0x18003263b  mov     esi, eax
0x18003263d  test    eax, eax
0x18003263f  jz      short loc_18003269D
0x180032641  mov     rcx, cs:WPP_GLOBAL_Control
0x180032648  cmp     rcx, rbx
0x18003264b  jz      short loc_18003269D
0x18003264d  test    dword ptr [rcx+1Ch], 40000h
0x180032654  jz      short loc_18003269D
0x180032656  cmp     byte ptr [rcx+19h], 2
0x18003265a  jb      short loc_18003269D
0x18003265c  mov     edx, 10h
0x180032661  mov     dword ptr [rsp+80h+lpData], eax
0x180032665  lea     r9, aPackage; "Package"
0x18003266c  lea     r8, WPP_2e3cbcf08cb7377099a4c131f2f33a2b_Traceguids
0x180032673  mov     rcx, [rcx+10h]
0x180032677  call    WPP_SF_Sd
0x18003267c  jmp     short loc_18003269D
0x18003267e  lea     rdx, aPackage; "Package"
0x180032685  mov     rcx, r14; hKey
0x180032688  call    cs:__imp_RegDeleteValueW
0x18003268f  nop     dword ptr [rax+rax+00h]
0x180032694  mov     esi, r12d
0x180032697  cmp     eax, 2
0x18003269a  cmovnz  esi, eax
0x18003269d  test    esi, esi
0x18003269f  jz      short loc_1800326AE
0x1800326a1  jle     short loc_1800326AC
0x1800326a3  movzx   esi, si
0x1800326a6  or      esi, 80070000h
0x1800326ac  jmp     short loc_1800326EE
0x1800326ae  lea     r8, [rbp+arg_0]
0x1800326b2  lea     rdx, [rbp+arg_18]
0x1800326b6  mov     rcx, [rdi+30h]
0x1800326ba  call    ?GetCapabilities@JobBucket@@QEBAXAEAV?$AutoVectorPtr@G@wmi@@AEAK@Z; JobBucket::GetCapabilities(wmi::AutoVectorPtr<ushort> &,ulong &)
0x1800326bf  mov     eax, [rbp+arg_0]
0x1800326c2  mov     dword ptr [rsp+80h+lpData], eax; unsigned int
0x1800326c6  mov     rbx, [rbp+arg_18]
0x1800326ca  mov     r9, rbx; unsigned __int16 *
0x1800326cd  mov     rdx, r14; HKEY
0x1800326d0  call    ?WriteMultiString@Trigulator@Triggers@@AEBAKPEAUHKEY__@@PEBGPEAGK@Z; Triggers::Trigulator::WriteMultiString(HKEY__ *,ushort const *,ushort *,ulong)
0x1800326d5  mov     esi, eax
0x1800326d7  test    eax, eax
0x1800326d9  jz      short loc_1800326F9
0x1800326db  jle     short loc_1800326E6
0x1800326dd  movzx   esi, ax
0x1800326e0  or      esi, 80070000h
0x1800326e6  mov     rcx, rbx; void *
0x1800326e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800326ee  test    esi, esi
0x1800326f0  jns     short loc_180032701
0x1800326f2  mov     eax, esi
0x1800326f4  jmp     loc_180032B04
0x1800326f9  mov     rcx, rbx; void *
0x1800326fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032701  mov     rcx, [rdi+30h]; this
0x180032705  call    ?GetStorageSize@JobBucket@@QEBAKXZ; JobBucket::GetStorageSize(void)
0x18003270a  lea     r15d, [rax+28h]
0x18003270e  mov     rbx, [rdi+20h]
0x180032712  mov     rbx, [rbx]
0x180032715  cmp     rbx, [rdi+20h]
0x180032719  jz      short loc_180032730
0x18003271b  mov     rcx, [rbx+10h]
0x18003271f  mov     rdx, [rcx]
0x180032722  mov     rax, [rdx+58h]
0x180032726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003272b  add     r15d, eax
0x18003272e  jmp     short loc_180032712
0x180032730  mov     [rbp+arg_18], r12
0x180032734  mov     ebx, r15d
0x180032737  mov     r8d, r15d; dwBytes
0x18003273a  xor     edx, edx; dwFlags
0x18003273c  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x180032743  call    cs:__imp_HeapAlloc
0x18003274a  nop     dword ptr [rax+rax+00h]
0x18003274f  mov     rsi, rax
0x180032752  test    rax, rax
0x180032755  jnz     short loc_180032798
0x180032757  mov     [rbp+var_38], al
0x18003275a  lea     rax, qword_1800A8718
0x180032761  mov     [rbp+var_30], rax
0x180032765  mov     [rbp+var_28], r12
0x180032769  mov     [rbp+var_20], r12
0x18003276d  mov     [rbp+var_18], 0Eh
0x180032774  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x18003277c  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180032783  mov     [rbp+pExceptionObject], rax
0x180032787  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18003278e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180032792  call    _CxxThrowException_0
0x180032798  mov     [rbp+arg_18], rsi
0x18003279c  lea     r12, [r15+rax]
0x1800327a0  mov     [rbp+arg_10], rsi
0x1800327a4  mov     r8, rbx; Size
0x1800327a7  mov     edx, 48h ; 'H'; Val
0x1800327ac  mov     rcx, rsi; void *
0x1800327af  call    memset_0
0x1800327b4  mov     rax, [rbp+arg_10]
0x1800327b8  mov     qword ptr [rax], 17h
0x1800327bf  mov     rax, [rbp+arg_10]
0x1800327c3  add     rax, 8
0x1800327c7  mov     [rbp+arg_10], rax
0x1800327cb  movups  xmm0, xmmword ptr [rdi]
0x1800327ce  movups  xmmword ptr [rax], xmm0
0x1800327d1  movups  xmm1, xmmword ptr [rdi+10h]
0x1800327d5  movups  xmmword ptr [rax+10h], xmm1
0x1800327d9  add     [rbp+arg_10], 20h ; ' '
0x1800327de  mov     rcx, [rdi+30h]; this
0x1800327e2  call    ?GetStorageSize@JobBucket@@QEBAKXZ; JobBucket::GetStorageSize(void)
0x1800327e7  mov     eax, eax
0x1800327e9  mov     rcx, [rbp+arg_10]
0x1800327ed  add     rax, rcx
0x1800327f0  cmp     rax, r12
0x1800327f3  jbe     short loc_180032807
0x1800327f5  mov     rcx, rsi; void *
0x1800327f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800327fd  mov     eax, 8000FFFFh
0x180032802  jmp     loc_180032B04
0x180032807  lea     rax, [rbp+arg_10]
0x18003280b  mov     [rbp+var_50], rax
0x18003280f  mov     [rbp+var_48], r12
0x180032813  lea     rax, [rcx+8]
0x180032817  cmp     rax, r12
0x18003281a  jbe     short loc_180032826
0x18003281c  mov     ebx, 8000FFFFh
0x180032821  jmp     loc_180032A0F
0x180032826  mov     r13, [rdi+30h]
0x18003282a  mov     eax, [r13+10h]
0x18003282e  mov     [rcx], eax
0x180032830  mov     rcx, [rbp+arg_10]
0x180032834  add     rcx, 8
0x180032838  mov     [rbp+arg_10], rcx
0x18003283c  lea     rax, [rcx+8]
0x180032840  cmp     rax, r12
0x180032843  ja      short loc_18003281C
0x180032845  mov     eax, [r13+18h]
0x180032849  mov     [rcx], eax
0x18003284b  add     [rbp+arg_10], 8
0x180032850  lea     rcx, [r13+48h]; this
0x180032854  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180032859  test    eax, eax
0x18003285b  jnz     short loc_18003287C
0x18003285d  mov     [rbp+arg_0], eax
0x180032860  lea     rdx, [rbp+arg_0]
0x180032864  lea     rcx, [rbp+var_50]
0x180032868  call    ??$WriteFixedSize@K@DataAligner@@QEAAJAEBK@Z; DataAligner::WriteFixedSize<ulong>(ulong const &)
0x18003286d  mov     ebx, eax
0x18003286f  test    eax, eax
0x180032871  js      loc_180032A0F
0x180032877  jmp     loc_180032906
0x18003287c  lea     rcx, [r13+48h]; this
0x180032880  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180032885  lea     r9d, ds:2[rax*2]
0x18003288d  mov     rax, [r13+48h]
0x180032891  test    rax, rax
0x180032894  jz      short loc_18003289B
0x180032896  mov     r10, [rax]
0x180032899  jmp     short loc_18003289E
0x18003289b  xor     r10d, r10d
0x18003289e  mov     [rbp+arg_0], r9d
0x1800328a2  test    r9d, r9d
0x1800328a5  jz      short loc_1800328B0
0x1800328a7  test    r10, r10
0x1800328aa  jz      loc_18003281C
0x1800328b0  lea     rdx, [rbp+arg_0]
0x1800328b4  lea     rcx, [rbp+var_50]
0x1800328b8  call    ??$WriteFixedSize@K@DataAligner@@QEAAJAEBK@Z; DataAligner::WriteFixedSize<ulong>(ulong const &)
0x1800328bd  mov     ebx, eax
0x1800328bf  test    eax, eax
0x1800328c1  js      short loc_1800328FE
0x1800328c3  test    r9d, r9d
0x1800328c6  jz      short loc_1800328FE
0x1800328c8  test    r10, r10
0x1800328cb  jz      short loc_1800328F9
0x1800328cd  lea     ebx, [r9+7]
0x1800328d1  mov     eax, 0FFFFFFF8h
0x1800328d6  and     rbx, rax
0x1800328d9  mov     rcx, [rbp+arg_10]; void *
0x1800328dd  lea     rax, [rbx+rcx]
0x1800328e1  cmp     rax, r12
0x1800328e4  ja      short loc_1800328F9
0x1800328e6  mov     r8d, r9d; Size
0x1800328e9  mov     rdx, r10; Src
0x1800328ec  call    memcpy_0
0x1800328f1  add     [rbp+arg_10], rbx
0x1800328f5  xor     ebx, ebx
0x1800328f7  jmp     short loc_1800328FE
0x1800328f9  mov     ebx, 8000FFFFh
0x1800328fe  test    ebx, ebx
0x180032900  js      loc_180032A0F
0x180032906  lea     rcx, [r13+50h]; this
0x18003290a  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18003290f  test    eax, eax
0x180032911  jnz     short loc_18003292F
0x180032913  mov     [rbp+arg_0], eax
0x180032916  lea     rdx, [rbp+arg_0]
0x18003291a  lea     rcx, [rbp+var_50]
0x18003291e  call    ??$WriteFixedSize@K@DataAligner@@QEAAJAEBK@Z; DataAligner::WriteFixedSize<ulong>(ulong const &)
0x180032923  mov     ebx, eax
0x180032925  test    eax, eax
0x180032927  js      loc_180032A0F
0x18003292d  jmp     short loc_180032963
0x18003292f  lea     rcx, [r13+50h]; this
0x180032933  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180032938  lea     r8d, ds:2[rax*2]; unsigned int
0x180032940  mov     rax, [r13+50h]
0x180032944  test    rax, rax
0x180032947  jz      short loc_18003294E
0x180032949  mov     rdx, [rax]
0x18003294c  jmp     short loc_180032950
0x18003294e  xor     edx, edx; void *
0x180032950  lea     rcx, [rbp+var_50]; this
0x180032954  call    ?WriteVarSize@DataAligner@@QEAAJPEAXK@Z; DataAligner::WriteVarSize(void *,ulong)
0x180032959  mov     ebx, eax
0x18003295b  test    eax, eax
0x18003295d  js      loc_180032A0F
0x180032963  lea     rcx, [r13+40h]; this
0x180032967  mov     r9, r12; unsigned __int8 *
0x18003296a  lea     r8, [rbp+arg_10]; unsigned __int8 **
0x18003296e  call    ?StreamOutImpl@User@@QEBAJ_KAEAPEAEPEBE@Z; User::StreamOutImpl(unsigned __int64,uchar * &,uchar const *)
0x180032973  mov     ebx, eax
0x180032975  test    eax, eax
0x180032977  js      loc_180032A0F
0x18003297d  mov     rdx, [r13+0D0h]
0x180032984  test    rdx, rdx
0x180032987  jz      short loc_1800329F1
0x180032989  lea     rcx, [rdx+38h]; this
  ... truncated ...
```
