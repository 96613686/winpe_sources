# CCorrAPOBase::LockForProcess(uint,APO_CONNECTION_DESCRIPTOR * *,uint,APO_CONNECTION_DESCRIPTOR * *)

- ea: `0x1800066e0`
- end: `0x180006960`
- name: `?LockForProcess@CCorrAPOBase@@UEAAJIPEAPEAUAPO_CONNECTION_DESCRIPTOR@@I0@Z`
- size: `640`
- prototype: `__int64 __fastcall(CCorrAPOBase *__hidden this, unsigned int, struct APO_CONNECTION_DESCRIPTOR **, unsigned int, struct APO_CONNECTION_DESCRIPTOR **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800066e0`
- `0x180006bb0`
- `0x180006ca0`
- `0x180007ff4`
- `0x1800094a8`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000694b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000694b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000685c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000686d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006876`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000689e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000685c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000686d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006876`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000689e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006742`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006809`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006819`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006742`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006809`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006819`

## pseudocode

```c
__int64 __fastcall CCorrAPOBase::LockForProcess(
        CCorrAPOBase *this,
        int a2,
        struct APO_CONNECTION_DESCRIPTOR **a3,
        int a4,
        struct APO_CONNECTION_DESCRIPTOR **a5)
{
  struct APO_CONNECTION_DESCRIPTOR **v7; // rdi
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  char *v9; // r15
  CCorrAPOBase *u32MaxFrameCount; // rcx
  int FormatsFromMediaTypes; // edi
  _DWORD *v12; // r12
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  int v17; // r12d
  void *v18; // rcx
  signed int i; // r14d
  int v21; // eax
  int v22; // eax
  char v23; // [rsp+88h] [rbp+10h] BYREF

  if ( a2 != 1 || a4 != 1 )
    return 2289893383LL;
  if ( !a3 )
    return 2147500035LL;
  v7 = a5;
  if ( !a5 || !*a3 || !*a5 )
    return 2147500035LL;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 152);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v9 = (char *)this - 128;
  if ( *((_DWORD *)this + 2) )
  {
    FormatsFromMediaTypes = -2005073910;
LABEL_20:
    LeaveCriticalSection(v8);
    return (unsigned int)FormatsFromMediaTypes;
  }
  *((_DWORD *)this + 14) = (*a3)->u32MaxFrameCount;
  u32MaxFrameCount = (CCorrAPOBase *)(*v7)->u32MaxFrameCount;
  *((_DWORD *)this + 15) = (_DWORD)u32MaxFrameCount;
  FormatsFromMediaTypes = CCorrAPOBase::ExtractFormatsFromMediaTypes(
                            u32MaxFrameCount,
                            (*a3)->pFormat,
                            (*v7)->pFormat,
                            (struct _UNCOMPRESSEDAUDIOFORMAT *)((char *)this + 64),
                            (struct _UNCOMPRESSEDAUDIOFORMAT *)((char *)this + 100));
  if ( FormatsFromMediaTypes < 0 )
    goto LABEL_20;
  v12 = (_DWORD *)((char *)this + 144);
  FormatsFromMediaTypes = CCorrAPOBase::CollectPropertiesAndInit(
                            (CCorrAPOBase *)((char *)this - 128),
                            (void **)this + 17,
                            (const struct _UNCOMPRESSEDAUDIOFORMAT *)((char *)this + 64),
                            (const struct _UNCOMPRESSEDAUDIOFORMAT *)((char *)this + 100),
                            (unsigned int *)this + 36,
                            (unsigned int *)this + 6);
  if ( FormatsFromMediaTypes < 0 )
    goto LABEL_20;
  v13 = *(_QWORD *)((char *)this + 28) - *(_QWORD *)&GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1;
  if ( !v13 )
    v13 = *(_QWORD *)((char *)this + 36) - *(_QWORD *)GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4;
  if ( !v13 )
    *v12 = 0;
  v14 = (int)*((float *)this + 32);
  *((_QWORD *)this + 33) = 0;
  *((_DWORD *)this + 65) = v14;
  EnterCriticalSection((LPCRITICAL_SECTION)this - 2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  v16 = *((_DWORD *)this + 37);
  v17 = v16 & ~*v12;
  if ( v17 )
  {
    if ( (v17 & 0x41) != 0 )
    {
      *((_DWORD *)this + 37) = v16 & 0xFFFFFFBE;
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v9 + 160LL))((char *)this - 128, 11);
      v16 = *((_DWORD *)this + 37);
    }
    if ( (v17 & 0xB2) != 0 )
    {
      *((_DWORD *)this + 37) = v16 & 0xFFFFFF4D;
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v9 + 160LL))((char *)this - 128, 9);
    }
    for ( i = 0; i < 17; ++i )
    {
      v21 = PropIdx2FeatureIdx(i);
      if ( v21 >= 0 )
      {
        v22 = 1 << v21;
        if ( (v22 & v17) != 0 )
        {
          *((_DWORD *)this + 37) &= ~v22;
          (*(void (__fastcall **)(char *, _QWORD, _QWORD))(*(_QWORD *)v9 + 168LL))(
            (char *)this - 128,
            (unsigned int)i,
            0);
        }
      }
    }
  }
  corr_select_features(*((_QWORD *)this + 17), v15, *((unsigned int *)this + 37), &v23);
  v18 = (void *)*((_QWORD *)this + 6);
  if ( v18 )
    SetEvent(v18);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  *((_DWORD *)this + 2) = 1;
  LeaveCriticalSection((LPCRITICAL_SECTION)this - 2);
  LeaveCriticalSection(v8);
  return 0;
}

```

## disassembly

```asm
0x1800066e0  push    rbx
0x1800066e2  push    rbp
0x1800066e3  push    rsi
0x1800066e4  push    rdi
0x1800066e5  push    r12
0x1800066e7  push    r13
0x1800066e9  push    r14
0x1800066eb  push    r15
0x1800066ed  sub     rsp, 38h
0x1800066f1  mov     rsi, r8
0x1800066f4  mov     rbp, rcx
0x1800066f7  cmp     edx, 1
0x1800066fa  jnz     loc_180006956
0x180006700  cmp     r9d, edx
0x180006703  jnz     loc_180006956
0x180006709  xor     r12d, r12d
0x18000670c  test    r8, r8
0x18000670f  jz      loc_18000688F
0x180006715  mov     rdi, [rsp+78h+arg_20]
0x18000671d  test    rdi, rdi
0x180006720  jz      loc_18000688F
0x180006726  cmp     [r8], r12
0x180006729  jz      loc_18000688F
0x18000672f  cmp     [rdi], r12
0x180006732  jz      loc_18000688F
0x180006738  lea     rbx, [rcx+98h]
0x18000673f  mov     rcx, rbx; lpCriticalSection
0x180006742  call    cs:__imp_EnterCriticalSection
0x180006748  lea     r15, [rbp-80h]
0x18000674c  cmp     [r15+88h], r12d
0x180006753  jnz     loc_180006896
0x180006759  mov     rax, [rsi]
0x18000675c  lea     r14, [rbp+64h]
0x180006760  lea     r9, [rbp+40h]; struct _UNCOMPRESSEDAUDIOFORMAT *
0x180006764  mov     [rsp+78h+var_58], r14; struct _UNCOMPRESSEDAUDIOFORMAT *
0x180006769  mov     ecx, [rax+10h]
0x18000676c  mov     [rbp+38h], ecx
0x18000676f  mov     rax, [rdi]
0x180006772  mov     ecx, [rax+10h]; this
0x180006775  mov     [rbp+3Ch], ecx
0x180006778  mov     r8, [rdi]
0x18000677b  mov     rdx, [rsi]
0x18000677e  mov     r8, [r8+18h]; struct IAudioMediaType *
0x180006782  mov     rdx, [rdx+18h]; struct IAudioMediaType *
0x180006786  call    ?ExtractFormatsFromMediaTypes@CCorrAPOBase@@IEAAJPEAUIAudioMediaType@@0PEAU_UNCOMPRESSEDAUDIOFORMAT@@1@Z; CCorrAPOBase::ExtractFormatsFromMediaTypes(IAudioMediaType *,IAudioMediaType *,_UNCOMPRESSEDAUDIOFORMAT *,_UNCOMPRESSEDAUDIOFORMAT *)
0x18000678b  mov     edi, eax
0x18000678d  test    eax, eax
0x18000678f  js      loc_18000689B
0x180006795  lea     rax, [rbp+18h]
0x180006799  mov     r9, r14; struct _UNCOMPRESSEDAUDIOFORMAT *
0x18000679c  mov     [rsp+78h+var_50], rax; unsigned int *
0x1800067a1  lea     r12, [rbp+90h]
0x1800067a8  lea     rdx, [rbp+88h]; void **
0x1800067af  mov     [rsp+78h+var_58], r12; unsigned int *
0x1800067b4  lea     r8, [rbp+40h]; struct _UNCOMPRESSEDAUDIOFORMAT *
0x1800067b8  mov     rcx, r15; this
0x1800067bb  call    ?CollectPropertiesAndInit@CCorrAPOBase@@IEAAJPEAPEAXPEBU_UNCOMPRESSEDAUDIOFORMAT@@1PEAK2@Z; CCorrAPOBase::CollectPropertiesAndInit(void * *,_UNCOMPRESSEDAUDIOFORMAT const *,_UNCOMPRESSEDAUDIOFORMAT const *,ulong *,ulong *)
0x1800067c0  mov     edi, eax
0x1800067c2  test    eax, eax
0x1800067c4  js      loc_18000689B
0x1800067ca  mov     rax, [rbp+1Ch]
0x1800067ce  sub     rax, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x1800067d5  jnz     short loc_1800067E2
0x1800067d7  mov     rax, [rbp+24h]
0x1800067db  sub     rax, qword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data4
0x1800067e2  test    rax, rax
0x1800067e5  jnz     short loc_1800067EB
0x1800067e7  mov     [r12], eax
0x1800067eb  cvttss2si rax, dword ptr [rbp+80h]
0x1800067f4  lea     rcx, [rbp-50h]; lpCriticalSection
0x1800067f8  mov     qword ptr [rbp+108h], 0
0x180006803  mov     [rbp+104h], eax
0x180006809  call    cs:__imp_EnterCriticalSection
0x18000680f  lea     rsi, [rbp+0C0h]
0x180006816  mov     rcx, rsi; lpCriticalSection
0x180006819  call    cs:__imp_EnterCriticalSection
0x18000681f  mov     r12d, [r12]
0x180006823  mov     eax, [rbp+94h]
0x180006829  not     r12d
0x18000682c  and     r12d, eax
0x18000682f  jnz     short loc_1800068A8
0x180006831  mov     r8d, [rbp+94h]
0x180006838  lea     r9, [rsp+78h+arg_8]
0x180006840  mov     rcx, [rbp+88h]
0x180006847  call    corr_select_features
0x18000684c  mov     rcx, [rbp+30h]; hEvent
0x180006850  test    rcx, rcx
0x180006853  jnz     loc_18000694B
0x180006859  mov     rcx, rsi; lpCriticalSection
0x18000685c  call    cs:__imp_LeaveCriticalSection
0x180006862  lea     rcx, [rbp-50h]; lpCriticalSection
0x180006866  mov     dword ptr [rbp+8], 1
0x18000686d  call    cs:__imp_LeaveCriticalSection
0x180006873  mov     rcx, rbx; lpCriticalSection
0x180006876  call    cs:__imp_LeaveCriticalSection
0x18000687c  xor     eax, eax
0x18000687e  add     rsp, 38h
0x180006882  pop     r15
0x180006884  pop     r14
0x180006886  pop     r13
0x180006888  pop     r12
0x18000688a  pop     rdi
0x18000688b  pop     rsi
0x18000688c  pop     rbp
0x18000688d  pop     rbx
0x18000688e  retn
0x18000688f  mov     eax, 80004003h
0x180006894  jmp     short loc_18000687E
0x180006896  mov     edi, 887D000Ah
0x18000689b  mov     rcx, rbx; lpCriticalSection
0x18000689e  call    cs:__imp_LeaveCriticalSection
0x1800068a4  mov     eax, edi
0x1800068a6  jmp     short loc_18000687E
0x1800068a8  test    r12b, 41h
0x1800068ac  jz      short loc_1800068D6
0x1800068ae  and     eax, 0FFFFFFBEh
0x1800068b1  xor     r8d, r8d
0x1800068b4  mov     [rbp+94h], eax
0x1800068ba  mov     rcx, r15
0x1800068bd  mov     rax, [r15]
0x1800068c0  lea     edx, [r8+0Bh]
0x1800068c4  mov     rax, [rax+0A0h]
0x1800068cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068d0  mov     eax, [rbp+94h]
0x1800068d6  test    r12b, 0B2h
0x1800068da  jz      short loc_180006900
0x1800068dc  and     eax, 0FFFFFF4Dh
0x1800068e1  xor     r8d, r8d
0x1800068e4  mov     [rbp+94h], eax
0x1800068ea  mov     rcx, r15
0x1800068ed  mov     rax, [r15]
0x1800068f0  lea     edx, [r8+9]
0x1800068f4  mov     rax, [rax+0A0h]
0x1800068fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006900  xor     r14d, r14d
0x180006903  mov     ecx, r14d; unsigned int
0x180006906  call    ?PropIdx2FeatureIdx@@YAHK@Z; PropIdx2FeatureIdx(ulong)
0x18000690b  test    eax, eax
0x18000690d  js      short loc_18000693D
0x18000690f  mov     ecx, eax
0x180006911  mov     eax, 1
0x180006916  shl     eax, cl
0x180006918  test    r12d, eax
0x18000691b  jz      short loc_18000693D
0x18000691d  not     eax
0x18000691f  xor     r8d, r8d
0x180006922  and     [rbp+94h], eax
0x180006928  mov     edx, r14d
0x18000692b  mov     rax, [r15]
0x18000692e  mov     rcx, r15
0x180006931  mov     rax, [rax+0A8h]
0x180006938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000693d  inc     r14d
0x180006940  cmp     r14d, 11h
0x180006944  jl      short loc_180006903
0x180006946  jmp     loc_180006831
0x18000694b  call    cs:__imp_SetEvent
0x180006951  jmp     loc_180006859
0x180006956  mov     eax, 887D0007h
0x18000695b  jmp     loc_18000687E
```
