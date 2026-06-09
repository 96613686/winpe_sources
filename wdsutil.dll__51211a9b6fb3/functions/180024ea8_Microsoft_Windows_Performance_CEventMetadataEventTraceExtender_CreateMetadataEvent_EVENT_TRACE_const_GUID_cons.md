# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(_EVENT_TRACE const *,_GUID const &,_EVENT_DESCRIPTOR const &)

- ea: `0x180024ea8`
- end: `0x180025330`
- name: `?CreateMetadataEvent@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBU_EVENT_TRACE@@AEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `1160`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__hidden this, const struct _EVENT_TRACE *, const struct _GUID *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026640`

## callees

- `0x180012cbc`
- `0x18001e0a8`
- `0x180023890`
- `0x1800246f4`
- `0x180024ea8`
- `0x180027b5c`
- `0x1800319ae`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `msvcrt!malloc` at `0x180024fa5`
- `msvcrt!malloc` at `0x180025203`
- `msvcrt!malloc` at `0x180024fa5`
- `msvcrt!malloc` at `0x180025203`
- `msvcrt!free` at `0x180024f93`
- `msvcrt!free` at `0x1800251ed`
- `msvcrt!free` at `0x180024f93`
- `msvcrt!free` at `0x1800251ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025179`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025179`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this,
        const struct _EVENT_TRACE *a2,
        const struct _GUID *a3,
        const struct _EVENT_DESCRIPTOR *a4)
{
  const struct _GUID *v5; // rdi
  FARPROC v8; // rax
  int v9; // eax
  FARPROC v10; // rax
  unsigned int v11; // edi
  void *v12; // rcx
  void *v13; // rax
  FARPROC v14; // rax
  __int64 result; // rax
  __int64 v16; // rcx
  ULONGLONG Keyword; // rax
  __int64 v18; // rcx
  unsigned int v19; // r14d
  __int64 v20; // rax
  _WORD *v21; // r15
  __int64 v22; // rdi
  __int64 v23; // r8
  int v24; // r8d
  unsigned int v25; // ecx
  unsigned int v26; // r12d
  FARPROC v27; // rax
  int v28; // eax
  unsigned int v29; // edi
  void *v30; // rcx
  void *v31; // rax
  FARPROC v32; // rax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h] BYREF
  const struct _GUID *v35; // [rsp+40h] [rbp-C0h]
  __int64 v36; // [rsp+48h] [rbp-B8h]
  _BYTE v37[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v38; // [rsp+60h] [rbp-A0h] BYREF
  __m256i v39; // [rsp+70h] [rbp-90h]
  __int128 v40; // [rsp+90h] [rbp-70h]
  __int128 v41; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+B0h] [rbp-50h]
  void *v43[3]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v44; // [rsp+D8h] [rbp-28h]
  __int16 v45; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v46[22]; // [rsp+E2h] [rbp-1Eh] BYREF
  struct _GUID v47; // [rsp+F8h] [rbp-8h]
  struct _EVENT_DESCRIPTOR v48; // [rsp+108h] [rbp+8h]

  v36 = -2;
  v5 = a3;
  v35 = a3;
  memset_0(v46, 0, 0x6Eu);
  v45 = 112;
  v47 = *v5;
  v48 = *a4;
  LODWORD(Size) = *((_DWORD *)this + 16);
  v8 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 36);
  v9 = ((__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))v8)(
         &v45,
         0,
         0,
         *((_QWORD *)this + 7),
         &Size);
  if ( v9 == 1168 )
  {
    v48.Keyword = 0;
    v10 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 36);
    v9 = ((__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))v10)(
           &v45,
           0,
           0,
           *((_QWORD *)this + 7),
           &Size);
  }
  if ( v9 == 122 )
  {
    v11 = Size;
    if ( (unsigned int)Size <= *((_DWORD *)this + 16) )
      return 1;
    v12 = (void *)*((_QWORD *)this + 7);
    if ( v12 )
    {
      free(v12);
      v11 = Size;
    }
    v13 = malloc(v11);
    *((_QWORD *)this + 7) = v13;
    if ( !v13 )
      return 2147942414LL;
    *((_DWORD *)this + 16) = v11;
    v14 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 36);
    v9 = ((__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))v14)(
           &v45,
           0,
           0,
           *((_QWORD *)this + 7),
           &Size);
    v5 = v35;
  }
  if ( v9 )
    return 1;
  v16 = *((_QWORD *)this + 7);
  if ( !*(_QWORD *)(v16 + 40) )
  {
    Keyword = a4->Keyword;
    if ( Keyword )
      *(_QWORD *)(v16 + 40) = Keyword;
  }
  v34 = *((_QWORD *)this + 7);
  Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(
    (_DWORD)this + 88,
    v34,
    Size,
    (unsigned int)&v34,
    (__int64)&Size);
  v38 = *(_OWORD *)&a2->Header.Size;
  v39 = *(__m256i *)&a2->Header.TimeStamp.LowPart;
  v40 = *(_OWORD *)&a2->InstanceId;
  v41 = *(_OWORD *)a2->ParentGuid.Data4;
  HIDWORD(v42) = HIDWORD(*(_QWORD *)&a2->MofLength);
  *(_OWORD *)&v39.m256i_u64[1] = EventMetadataGuid;
  DWORD1(v38) = 32;
  *((_QWORD *)&v41 + 1) = v34;
  LODWORD(v42) = Size;
  if ( (unsigned __int64)(unsigned int)Size + 48 > 0xFFB8
    || (result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                   *((_QWORD *)this + 2),
                   &v38,
                   0,
                   0),
        (int)result >= 0) )
  {
    if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 40) )
    {
      v18 = *((_QWORD *)this + 7);
      if ( *(_DWORD *)(v18 + 100) )
      {
        v19 = 0;
        while ( 1 )
        {
          if ( (*(_BYTE *)(v18 + 24LL * v19 + 112) & 1) != 0 )
            goto LABEL_40;
          v20 = *(unsigned int *)(v18 + 24LL * v19 + 124);
          if ( !(_DWORD)v20 )
            goto LABEL_40;
          v21 = (_WORD *)(v18 + v20);
          v22 = std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::operator[](
                  (char *)this + 40,
                  v5)
              + 16;
          v44 = 7;
          v43[2] = 0;
          LOWORD(v43[0]) = 0;
          if ( *v21 )
          {
            v23 = -1;
            do
              ++v23;
            while ( v21[v23] );
          }
          std::wstring::assign(v43, v21);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring,std::_Nil>(
            v22,
            (unsigned int)v37,
            v24,
            (unsigned int)v43,
            byte_18004D34A);
          if ( v44 >= 8 )
            operator delete(v43[0]);
          if ( !v37[8] )
            break;
          v25 = *((_DWORD *)this + 20);
          v26 = v25 - 16;
          if ( v25 < 0x10 )
            v26 = 0;
          LODWORD(v34) = v26;
          v27 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 40);
          v28 = ((__int64 (__fastcall *)(__int16 *, _WORD *, __int64, __int64 *))v27)(
                  &v45,
                  v21,
                  (*((_QWORD *)this + 9) + 16LL) & -(__int64)(*((_QWORD *)this + 9) != 0),
                  &v34);
          if ( v28 == 122 )
          {
            v29 = v34;
            if ( (unsigned int)v34 <= v26 )
              break;
            v30 = (void *)*((_QWORD *)this + 9);
            if ( v30 )
            {
              free(v30);
              v29 = v34;
            }
            v31 = malloc(v29 + 16LL);
            *((_QWORD *)this + 9) = v31;
            if ( !v31 )
              return 2147942414LL;
            *((_DWORD *)this + 20) = v29 + 16;
            v32 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 40);
            v28 = ((__int64 (__fastcall *)(__int16 *, _WORD *, __int64, __int64 *))v32)(
                    &v45,
                    v21,
                    *((_QWORD *)this + 9) + 16LL,
                    &v34);
          }
          v5 = v35;
          if ( !v28 )
          {
            v38 = *(_OWORD *)&a2->Header.Size;
            v39 = *(__m256i *)&a2->Header.TimeStamp.LowPart;
            v40 = *(_OWORD *)&a2->InstanceId;
            v41 = *(_OWORD *)a2->ParentGuid.Data4;
            v42 = *(_QWORD *)&a2->MofLength;
            *(_OWORD *)&v39.m256i_u64[1] = EventMetadataGuid;
            DWORD1(v38) = 33;
            *(struct _GUID *)*((_QWORD *)this + 9) = *v35;
            *((_QWORD *)&v41 + 1) = *((_QWORD *)this + 9);
            LODWORD(v42) = v34 + 16;
            if ( (unsigned __int64)(unsigned int)(v34 + 16) + 48 <= 0xFFB8 )
            {
              result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                         *((_QWORD *)this + 2),
                         &v38,
                         0,
                         0);
              if ( (int)result < 0 )
                return result;
            }
          }
LABEL_40:
          ++v19;
          v18 = *((_QWORD *)this + 7);
          if ( v19 >= *(_DWORD *)(v18 + 100) )
            return 0;
        }
        v5 = v35;
        goto LABEL_40;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180024ea8  push    rbp
0x180024eaa  push    rbx
0x180024eab  push    rsi
0x180024eac  push    rdi
0x180024ead  push    r12
0x180024eaf  push    r13
0x180024eb1  push    r14
0x180024eb3  push    r15
0x180024eb5  lea     rbp, [rsp-68h]
0x180024eba  sub     rsp, 168h
0x180024ec1  mov     [rsp+1A0h+var_158], 0FFFFFFFFFFFFFFFEh
0x180024eca  mov     rax, cs:__security_cookie
0x180024ed1  xor     rax, rsp
0x180024ed4  mov     [rbp+0A0h+var_50], rax
0x180024ed8  mov     r15, r9
0x180024edb  mov     rdi, r8
0x180024ede  mov     [rsp+1A0h+var_160], r8
0x180024ee3  mov     rsi, rdx
0x180024ee6  mov     rbx, rcx
0x180024ee9  xor     edx, edx; Val
0x180024eeb  lea     r8d, [rdx+6Eh]; Size
0x180024eef  lea     rcx, [rbp+0A0h+var_BE]; void *
0x180024ef3  call    memset_0
0x180024ef8  mov     eax, 70h ; 'p'
0x180024efd  mov     [rbp+0A0h+var_C0], ax
0x180024f01  movups  xmm0, xmmword ptr [rdi]
0x180024f04  movdqu  [rbp+0A0h+var_A8], xmm0
0x180024f09  mov     rax, [r15]
0x180024f0c  mov     [rbp+0A0h+var_98], rax
0x180024f10  mov     rax, [r15+8]
0x180024f14  mov     [rbp+0A0h+var_90], rax
0x180024f18  mov     eax, [rbx+40h]
0x180024f1b  mov     dword ptr [rsp+1A0h+Size], eax
0x180024f1f  lea     r14, [rbx+120h]
0x180024f26  mov     rcx, r14
0x180024f29  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180024f2e  lea     rcx, [rsp+1A0h+Size]
0x180024f33  mov     [rsp+1A0h+var_180], rcx
0x180024f38  mov     r9, [rbx+38h]
0x180024f3c  xor     r8d, r8d
0x180024f3f  xor     edx, edx
0x180024f41  lea     rcx, [rbp+0A0h+var_C0]
0x180024f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f4a  xor     r12d, r12d
0x180024f4d  cmp     eax, 490h
0x180024f52  jnz     short loc_180024F7C
0x180024f54  mov     [rbp+0A0h+var_90], r12
0x180024f58  mov     rcx, r14
0x180024f5b  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180024f60  lea     rcx, [rsp+1A0h+Size]
0x180024f65  mov     [rsp+1A0h+var_180], rcx
0x180024f6a  mov     r9, [rbx+38h]
0x180024f6e  xor     r8d, r8d
0x180024f71  xor     edx, edx
0x180024f73  lea     rcx, [rbp+0A0h+var_C0]
0x180024f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f7c  cmp     eax, 7Ah ; 'z'
0x180024f7f  jnz     short loc_180024FEA
0x180024f81  mov     edi, dword ptr [rsp+1A0h+Size]
0x180024f85  cmp     edi, [rbx+40h]
0x180024f88  jbe     short loc_180024FEE
0x180024f8a  mov     rcx, [rbx+38h]; Block
0x180024f8e  test    rcx, rcx
0x180024f91  jz      short loc_180024FA3
0x180024f93  call    cs:__imp_free
0x180024f9a  nop     dword ptr [rax+rax+00h]
0x180024f9f  mov     edi, dword ptr [rsp+1A0h+Size]
0x180024fa3  mov     ecx, edi; Size
0x180024fa5  call    cs:__imp_malloc
0x180024fac  nop     dword ptr [rax+rax+00h]
0x180024fb1  mov     [rbx+38h], rax
0x180024fb5  test    rax, rax
0x180024fb8  jz      loc_180025329
0x180024fbe  mov     [rbx+40h], edi
0x180024fc1  mov     rcx, r14
0x180024fc4  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180024fc9  lea     rcx, [rsp+1A0h+Size]
0x180024fce  mov     [rsp+1A0h+var_180], rcx
0x180024fd3  mov     r9, [rbx+38h]
0x180024fd7  xor     r8d, r8d
0x180024fda  xor     edx, edx
0x180024fdc  lea     rcx, [rbp+0A0h+var_C0]
0x180024fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fe5  mov     rdi, [rsp+1A0h+var_160]
0x180024fea  test    eax, eax
0x180024fec  jz      short loc_180024FF8
0x180024fee  mov     eax, 1
0x180024ff3  jmp     loc_180025308
0x180024ff8  mov     rcx, [rbx+38h]
0x180024ffc  cmp     [rcx+28h], r12
0x180025000  jnz     short loc_18002500F
0x180025002  mov     rax, [r15+8]
0x180025006  test    rax, rax
0x180025009  jz      short loc_18002500F
0x18002500b  mov     [rcx+28h], rax
0x18002500f  mov     rdx, [rbx+38h]
0x180025013  mov     [rsp+1A0h+var_168], rdx
0x180025018  lea     rcx, [rbx+58h]
0x18002501c  lea     rax, [rsp+1A0h+Size]
0x180025021  mov     [rsp+1A0h+var_180], rax
0x180025026  lea     r9, [rsp+1A0h+var_168]
0x18002502b  mov     r8d, dword ptr [rsp+1A0h+Size]
0x180025030  call    ?Transform@?$CTraceEventInfoTransformImpl@VCTraceEventInfoDelocalizer@Performance@Windows@Microsoft@@@Performance@Windows@Microsoft@@IEAAJPEBU_TRACE_EVENT_INFO@@KPEAPEBU5@PEAK@Z; Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(_TRACE_EVENT_INFO const *,ulong,_TRACE_EVENT_INFO const * *,ulong *)
0x180025035  movups  xmm0, xmmword ptr [rsi]
0x180025038  movaps  [rsp+1A0h+var_140], xmm0
0x18002503d  movups  xmm1, xmmword ptr [rsi+10h]
0x180025041  movaps  [rsp+1A0h+var_130], xmm1
0x180025046  movups  xmm0, xmmword ptr [rsi+20h]
0x18002504a  movaps  [rbp+0A0h+var_120], xmm0
0x18002504e  movups  xmm1, xmmword ptr [rsi+30h]
0x180025052  movaps  [rbp+0A0h+var_110], xmm1
0x180025056  movups  xmm0, xmmword ptr [rsi+40h]
0x18002505a  movaps  [rbp+0A0h+var_100], xmm0
0x18002505e  movsd   xmm1, qword ptr [rsi+50h]
0x180025063  movsd   [rbp+0A0h+var_F0], xmm1
0x180025068  movups  xmm0, cs:EventMetadataGuid
0x18002506f  movdqu  [rsp+1A0h+var_130+8], xmm0
0x180025075  mov     dword ptr [rsp+1A0h+var_140+4], 20h ; ' '
0x18002507d  mov     rax, [rsp+1A0h+var_168]
0x180025082  mov     qword ptr [rbp+0A0h+var_100+8], rax
0x180025086  mov     eax, dword ptr [rsp+1A0h+Size]
0x18002508a  mov     dword ptr [rbp+0A0h+var_F0], eax
0x18002508d  lea     rcx, [rax+30h]
0x180025091  cmp     rcx, 0FFB8h
0x180025098  ja      short loc_1800250C0
0x18002509a  mov     rcx, [rbx+10h]
0x18002509e  mov     rax, [rcx]
0x1800250a1  xor     r9d, r9d
0x1800250a4  xor     r8d, r8d
0x1800250a7  lea     rdx, [rsp+1A0h+var_140]
0x1800250ac  mov     rax, [rax+0C0h]
0x1800250b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250b8  test    eax, eax
0x1800250ba  js      loc_180025308
0x1800250c0  lea     r13, [rbx+140h]
0x1800250c7  mov     rcx, r13
0x1800250ca  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800250cf  test    rax, rax
0x1800250d2  jz      loc_180025306
0x1800250d8  mov     rcx, [rbx+38h]
0x1800250dc  cmp     [rcx+64h], r12d
0x1800250e0  jbe     loc_180025306
0x1800250e6  mov     r14d, r12d
0x1800250e9  mov     eax, r14d
0x1800250ec  lea     rdx, [rax+rax*2]
0x1800250f0  test    byte ptr [rcx+rdx*8+70h], 1
0x1800250f5  jnz     loc_1800252F5
0x1800250fb  mov     eax, [rcx+rdx*8+7Ch]
0x1800250ff  test    eax, eax
0x180025101  jz      loc_1800252F5
0x180025107  lea     r15, [rcx+rax]
0x18002510b  lea     rcx, [rbx+28h]
0x18002510f  mov     rdx, rdi
0x180025112  call    ??A?$map@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAUCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEBU_GUID@@@Z; std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::operator[](_GUID const &)
0x180025117  lea     rdi, [rax+10h]
0x18002511b  mov     [rbp+0A0h+var_C8], 7
0x180025123  mov     [rbp+0A0h+var_D0], r12
0x180025127  mov     word ptr [rbp+0A0h+var_E0], r12w
0x18002512c  cmp     [r15], r12w
0x180025130  jnz     short loc_180025137
0x180025132  mov     r8, r12
0x180025135  jmp     short loc_180025145
0x180025137  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002513b  inc     r8
0x18002513e  cmp     [r15+r8*2], r12w
0x180025143  jnz     short loc_18002513B
0x180025145  mov     rdx, r15; Src
0x180025148  lea     rcx, [rbp+0A0h+var_E0]; void *
0x18002514c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180025151  nop
0x180025152  mov     al, cs:byte_18004D34A
0x180025158  mov     byte ptr [rsp+1A0h+var_180], al
0x18002515c  lea     r9, [rbp+0A0h+var_E0]
0x180025160  lea     rdx, [rsp+1A0h+var_150]
0x180025165  mov     rcx, rdi
0x180025168  call    ??$_Insert_nohint@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Nil@2@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@_N$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring,std::_Nil>(bool,std::wstring &&,std::_Nil)
0x18002516d  nop
0x18002516e  cmp     [rbp+0A0h+var_C8], 8
0x180025173  jb      short loc_180025185
0x180025175  mov     rcx, [rbp+0A0h+var_E0]
0x180025179  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180025180  nop     dword ptr [rax+rax+00h]
0x180025185  cmp     [rsp+1A0h+var_148], r12b
0x18002518a  jz      loc_1800252F0
0x180025190  mov     ecx, [rbx+50h]
0x180025193  lea     r12d, [rcx-10h]
0x180025197  xor     eax, eax
0x180025199  cmp     ecx, 10h
0x18002519c  cmovb   r12d, eax
0x1800251a0  mov     dword ptr [rsp+1A0h+var_168], r12d
0x1800251a5  mov     rcx, r13
0x1800251a8  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800251ad  mov     rcx, [rbx+48h]
0x1800251b1  lea     rdx, [rcx+10h]
0x1800251b5  neg     rcx
0x1800251b8  sbb     r8, r8
0x1800251bb  and     r8, rdx
0x1800251be  lea     r9, [rsp+1A0h+var_168]
0x1800251c3  mov     rdx, r15
0x1800251c6  lea     rcx, [rbp+0A0h+var_C0]
0x1800251ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251cf  cmp     eax, 7Ah ; 'z'
0x1800251d2  jnz     short loc_180025245
0x1800251d4  mov     edi, dword ptr [rsp+1A0h+var_168]
0x1800251d8  cmp     edi, r12d
0x1800251db  jbe     loc_1800252ED
0x1800251e1  mov     rcx, [rbx+48h]; Block
0x1800251e5  xor     r12d, r12d
0x1800251e8  test    rcx, rcx
0x1800251eb  jz      short loc_1800251FD
0x1800251ed  call    cs:__imp_free
0x1800251f4  nop     dword ptr [rax+rax+00h]
0x1800251f9  mov     edi, dword ptr [rsp+1A0h+var_168]
0x1800251fd  mov     ecx, edi
0x1800251ff  add     rcx, 10h; Size
0x180025203  call    cs:__imp_malloc
0x18002520a  nop     dword ptr [rax+rax+00h]
0x18002520f  mov     [rbx+48h], rax
0x180025213  test    rax, rax
0x180025216  jz      loc_180025329
0x18002521c  lea     eax, [rdi+10h]
0x18002521f  mov     [rbx+50h], eax
0x180025222  mov     rcx, r13
0x180025225  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002522a  mov     r8, [rbx+48h]
0x18002522e  add     r8, 10h
0x180025232  lea     r9, [rsp+1A0h+var_168]
0x180025237  mov     rdx, r15
0x18002523a  lea     rcx, [rbp+0A0h+var_C0]
0x18002523e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025243  jmp     short loc_180025248
0x180025245  xor     r12d, r12d
0x180025248  mov     rdi, [rsp+1A0h+var_160]
0x18002524d  test    eax, eax
0x18002524f  jnz     loc_1800252F5
0x180025255  movups  xmm0, xmmword ptr [rsi]
0x180025258  movaps  [rsp+1A0h+var_140], xmm0
0x18002525d  movups  xmm1, xmmword ptr [rsi+10h]
0x180025261  movaps  [rsp+1A0h+var_130], xmm1
0x180025266  movups  xmm0, xmmword ptr [rsi+20h]
0x18002526a  movaps  [rbp+0A0h+var_120], xmm0
0x18002526e  movups  xmm1, xmmword ptr [rsi+30h]
0x180025272  movaps  [rbp+0A0h+var_110], xmm1
0x180025276  movups  xmm0, xmmword ptr [rsi+40h]
0x18002527a  movaps  [rbp+0A0h+var_100], xmm0
0x18002527e  movsd   xmm1, qword ptr [rsi+50h]
0x180025283  movsd   [rbp+0A0h+var_F0], xmm1
0x180025288  movups  xmm0, cs:EventMetadataGuid
0x18002528f  movdqu  [rsp+1A0h+var_130+8], xmm0
0x180025295  mov     dword ptr [rsp+1A0h+var_140+4], 21h ; '!'
0x18002529d  movups  xmm0, xmmword ptr [rdi]
0x1800252a0  mov     rax, [rbx+48h]
0x1800252a4  movdqu  xmmword ptr [rax], xmm0
0x1800252a8  mov     rax, [rbx+48h]
0x1800252ac  mov     qword ptr [rbp+0A0h+var_100+8], rax
0x1800252b0  mov     eax, dword ptr [rsp+1A0h+var_168]
0x1800252b4  add     eax, 10h
0x1800252b7  mov     dword ptr [rbp+0A0h+var_F0], eax
0x1800252ba  mov     ecx, eax
0x1800252bc  add     rcx, 30h ; '0'
0x1800252c0  cmp     rcx, 0FFB8h
0x1800252c7  ja      short loc_1800252F5
0x1800252c9  mov     rcx, [rbx+10h]
0x1800252cd  mov     rax, [rcx]
0x1800252d0  xor     r9d, r9d
0x1800252d3  xor     r8d, r8d
0x1800252d6  lea     rdx, [rsp+1A0h+var_140]
0x1800252db  mov     rax, [rax+0C0h]
0x1800252e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252e7  test    eax, eax
0x1800252e9  js      short loc_180025308
0x1800252eb  jmp     short loc_1800252F5
0x1800252ed  xor     r12d, r12d
0x1800252f0  mov     rdi, [rsp+1A0h+var_160]
0x1800252f5  inc     r14d
0x1800252f8  mov     rcx, [rbx+38h]
0x1800252fc  cmp     r14d, [rcx+64h]
0x180025300  jb      loc_1800250E9
0x180025306  xor     eax, eax
0x180025308  mov     rcx, [rbp+0A0h+var_50]
0x18002530c  xor     rcx, rsp; StackCookie
0x18002530f  call    __security_check_cookie
0x180025314  add     rsp, 168h
0x18002531b  pop     r15
0x18002531d  pop     r14
0x18002531f  pop     r13
0x180025321  pop     r12
0x180025323  pop     rdi
0x180025324  pop     rsi
0x180025325  pop     rbx
0x180025326  pop     rbp
0x180025327  retn
0x180025329  mov     eax, 8007000Eh
0x18002532e  jmp     short loc_180025308
```
