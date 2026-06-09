# CDVRRingBufferWriter::GetRecordings(ulong *,IDVRRecorder * * *,ushort * * *,unsigned __int64 * *,unsigned __int64 * *,int * *,ulong * *)

- ea: `0x18006c970`
- end: `0x18006cea9`
- name: `?GetRecordings@CDVRRingBufferWriter@@UEAAJPEAKPEAPEAPEAUIDVRRecorder@@PEAPEAPEAGPEAPEA_K3PEAPEAHPEAPEAK@Z`
- size: `1337`
- prototype: `__int64 __fastcall(CDVRRingBufferWriter *__hidden this, unsigned int *, struct IDVRRecorder ***, unsigned __int16 ***, unsigned __int64 **, unsigned __int64 **, int **, unsigned int **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000256c`
- `0x18006c970`
- `0x1800747f8`
- `0x1800b6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006cc8f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006cc8f`
- `KERNEL32!LeaveCriticalSection` at `0x18006ce9c`
- `KERNEL32!LeaveCriticalSection` at `0x1800b454a`
- `KERNEL32!LeaveCriticalSection` at `0x18006ce9c`
- `KERNEL32!LeaveCriticalSection` at `0x1800b454a`
- `KERNEL32!EnterCriticalSection` at `0x18006ca13`
- `KERNEL32!EnterCriticalSection` at `0x18006ca13`
- `ole32!CoTaskMemAlloc` at `0x18006ca50`
- `ole32!CoTaskMemAlloc` at `0x18006ca9a`
- `ole32!CoTaskMemAlloc` at `0x18006cad3`
- `ole32!CoTaskMemAlloc` at `0x18006cb02`
- `ole32!CoTaskMemAlloc` at `0x18006cb31`
- `ole32!CoTaskMemAlloc` at `0x18006cb70`
- `ole32!CoTaskMemAlloc` at `0x18006cc65`
- `ole32!CoTaskMemAlloc` at `0x18006ca50`
- `ole32!CoTaskMemAlloc` at `0x18006ca9a`
- `ole32!CoTaskMemAlloc` at `0x18006cad3`
- `ole32!CoTaskMemAlloc` at `0x18006cb02`
- `ole32!CoTaskMemAlloc` at `0x18006cb31`
- `ole32!CoTaskMemAlloc` at `0x18006cb70`
- `ole32!CoTaskMemAlloc` at `0x18006cc65`
- `ole32!CoTaskMemFree` at `0x18006cd7c`
- `ole32!CoTaskMemFree` at `0x18006cd93`
- `ole32!CoTaskMemFree` at `0x18006cda7`
- `ole32!CoTaskMemFree` at `0x18006cdc0`
- `ole32!CoTaskMemFree` at `0x18006cddb`
- `ole32!CoTaskMemFree` at `0x18006cdf1`
- `ole32!CoTaskMemFree` at `0x18006ce0a`
- `ole32!CoTaskMemFree` at `0x1800b441d`
- `ole32!CoTaskMemFree` at `0x1800b4433`
- `ole32!CoTaskMemFree` at `0x1800b444d`
- `ole32!CoTaskMemFree` at `0x1800b4464`
- `ole32!CoTaskMemFree` at `0x1800b447b`
- `ole32!CoTaskMemFree` at `0x1800b4492`
- `ole32!CoTaskMemFree` at `0x1800b44a9`
- `ole32!CoTaskMemFree` at `0x18006cd7c`
- `ole32!CoTaskMemFree` at `0x18006cd93`
- `ole32!CoTaskMemFree` at `0x18006cda7`
- `ole32!CoTaskMemFree` at `0x18006cdc0`
- `ole32!CoTaskMemFree` at `0x18006cddb`
- `ole32!CoTaskMemFree` at `0x18006cdf1`
- `ole32!CoTaskMemFree` at `0x18006ce0a`
- `ole32!CoTaskMemFree` at `0x1800b441d`
- `ole32!CoTaskMemFree` at `0x1800b4433`
- `ole32!CoTaskMemFree` at `0x1800b444d`
- `ole32!CoTaskMemFree` at `0x1800b4464`
- `ole32!CoTaskMemFree` at `0x1800b447b`
- `ole32!CoTaskMemFree` at `0x1800b4492`
- `ole32!CoTaskMemFree` at `0x1800b44a9`

## pseudocode

```c
__int64 __fastcall CDVRRingBufferWriter::GetRecordings(
        CDVRRingBufferWriter *this,
        unsigned int *a2,
        struct IDVRRecorder ***a3,
        unsigned __int16 ***a4,
        unsigned __int64 **a5,
        unsigned __int64 **a6,
        int **a7,
        unsigned int **a8)
{
  int LastStreamTime; // ebx
  _QWORD *v12; // r12
  _QWORD *v13; // r15
  void *v14; // r14
  unsigned int v15; // edi
  __int64 v16; // r8
  int v17; // eax
  char *v18; // rdx
  char *i; // rcx
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  LPVOID v22; // rsi
  unsigned int v23; // esi
  __int64 *j; // r14
  __int64 (__fastcall ***v25)(_QWORD, GUID *, char *, _QWORD, int); // rcx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rbx
  LPVOID v29; // rax
  _WORD *v30; // rcx
  unsigned int k; // esi
  __int64 v32; // rcx
  void *v33; // rcx
  int v34; // [rsp+20h] [rbp-B8h]
  void *v35; // [rsp+28h] [rbp-B0h]
  _QWORD *pv; // [rsp+38h] [rbp-A0h]
  _QWORD *v37; // [rsp+40h] [rbp-98h]
  char *v38; // [rsp+48h] [rbp-90h]
  unsigned __int64 v39; // [rsp+88h] [rbp-50h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+90h] [rbp-48h]

  if ( !a2 )
    return 2147500035LL;
  LastStreamTime = 0;
  v34 = 0;
  v12 = 0;
  v13 = 0;
  pv = 0;
  v37 = 0;
  v14 = 0;
  v35 = 0;
  v38 = 0;
  v15 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 496);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 496));
  v17 = 1;
  v18 = (char *)this + 544;
  for ( i = (char *)*((_QWORD *)this + 68); i != v18; i = *(char **)i )
    ++v15;
  if ( v15 )
  {
    if ( a3 )
    {
      v20 = CoTaskMemAlloc(8LL * v15);
      v12 = v20;
      if ( !v20 )
      {
LABEL_9:
        LastStreamTime = -2147024882;
        goto LABEL_63;
      }
      memset_0(v20, 0, 8LL * v15);
      v17 = 0;
    }
    if ( a4 )
    {
      v21 = CoTaskMemAlloc(8LL * v15);
      v13 = v21;
      if ( !v21 )
        goto LABEL_9;
      memset_0(v21, 0, 8LL * v15);
      v17 = 0;
    }
    if ( a5 )
    {
      pv = CoTaskMemAlloc(8LL * v15);
      if ( !pv )
        goto LABEL_9;
      v17 = 0;
    }
    if ( a6 )
    {
      v37 = CoTaskMemAlloc(8LL * v15);
      if ( !v37 )
        goto LABEL_9;
      v17 = 0;
    }
    if ( a7 )
    {
      v22 = CoTaskMemAlloc(4LL * v15);
      v35 = v22;
      if ( !v22 )
      {
LABEL_22:
        LastStreamTime = -2147024882;
LABEL_62:
        v14 = v35;
        goto LABEL_63;
      }
      v17 = 0;
    }
    else
    {
      v22 = 0;
    }
    if ( a8 )
    {
      v38 = (char *)CoTaskMemAlloc(4LL * v15);
      if ( !v38 )
        goto LABEL_22;
      v17 = 0;
    }
    if ( !v17 )
    {
      v39 = -1;
      if ( !v22
        || (*((_BYTE *)this + 492) & 2) != 0
        || (LastStreamTime = CDVRFileCollection::GetLastStreamTime(
                               *((CDVRFileCollection **)this + 72),
                               (CDVRRingBufferWriter *)((char *)this + 584),
                               &v39,
                               1),
            LastStreamTime >= 0) )
      {
        v23 = 0;
        for ( j = (__int64 *)*((_QWORD *)this + 68); j != (__int64 *)((char *)this + 544); j = (__int64 *)*j )
        {
          if ( v12 )
          {
            v25 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *, _QWORD, int))*(j - 1);
            if ( !v25 )
            {
              LastStreamTime = -2147467259;
              goto LABEL_62;
            }
            LastStreamTime = (**v25)(v25, &IID_IDVRRecorder, (char *)&v12[v23], 0, v34);
            if ( LastStreamTime < 0 )
              goto LABEL_62;
          }
          if ( v13 )
          {
            v26 = j[2];
            if ( v26 )
            {
              v27 = -1;
              do
                ++v27;
              while ( *(_WORD *)(v26 + 2 * v27) );
              v28 = v27 + 1;
            }
            else
            {
              v28 = 1;
            }
            v29 = CoTaskMemAlloc(2 * v28);
            v13[v23] = v29;
            if ( !v29 )
              goto LABEL_22;
            v16 = j[2];
            v30 = (_WORD *)v13[v23];
            if ( v16 )
              _o_wcscpy_s(v30, v28, v16, 0);
            else
              *v30 = 0;
          }
          if ( pv )
            pv[v23] = *(j - 5);
          if ( v37 )
            v37[v23] = *(j - 4);
          if ( v35 )
            *((_DWORD *)v35 + v23) = (*((_BYTE *)this + 492) & 2) == 0 && *(j - 5) != -1 && v39 >= *(j - 5);
          v18 = v38;
          if ( v38 )
            *(_DWORD *)&v38[4 * v23] = (unsigned __int64)(j[3] & 4 | (*((_DWORD *)j + 6) >> 2) & 2) >> 1;
          ++v23;
        }
        LastStreamTime = 0;
      }
    }
    goto LABEL_62;
  }
LABEL_63:
  if ( LastStreamTime < 0 )
  {
    for ( k = 0; k < v15; ++k )
    {
      if ( v12 )
      {
        v32 = v12[k];
        if ( v32 )
          (*(void (__fastcall **)(__int64, char *, __int64, _QWORD))(*(_QWORD *)v32 + 16LL))(v32, v18, v16, 0);
      }
      if ( v13 )
      {
        v33 = (void *)v13[k];
        if ( v33 )
          CoTaskMemFree(v33);
      }
    }
    if ( v12 )
    {
      CoTaskMemFree(v12);
      v12 = 0;
    }
    if ( v13 )
    {
      CoTaskMemFree(v13);
      v13 = 0;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v37 )
    {
      CoTaskMemFree(v37);
      v37 = 0;
    }
    if ( v14 )
    {
      CoTaskMemFree(v14);
      v14 = 0;
    }
    if ( v38 )
    {
      CoTaskMemFree(v38);
      v38 = 0;
    }
    v15 = 0;
  }
  *a2 = v15;
  if ( a3 )
    *a3 = (struct IDVRRecorder **)v12;
  if ( a4 )
    *a4 = (unsigned __int16 **)v13;
  if ( a5 )
    *a5 = pv;
  if ( a6 )
    *a6 = v37;
  if ( a7 )
    *a7 = (int *)v14;
  if ( a8 )
    *a8 = (unsigned int *)v38;
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)LastStreamTime;
}

```

## disassembly

```asm
0x18006c970  mov     rax, rsp
0x18006c973  mov     [rax+20h], r9
0x18006c977  mov     [rax+18h], r8
0x18006c97b  mov     [rax+10h], rdx
0x18006c97f  mov     [rax+8], rcx
0x18006c983  push    rbx
0x18006c984  push    rsi
0x18006c985  push    rdi
0x18006c986  push    r12
0x18006c988  push    r13
0x18006c98a  push    r14
0x18006c98c  push    r15
0x18006c98e  sub     rsp, 0A0h
0x18006c995  mov     rsi, r8
0x18006c998  mov     r13, rcx
0x18006c99b  test    rdx, rdx
0x18006c99e  jnz     short loc_18006C9B8
0x18006c9a0  mov     eax, 80004003h
0x18006c9a5  add     rsp, 0A0h
0x18006c9ac  pop     r15
0x18006c9ae  pop     r14
0x18006c9b0  pop     r13
0x18006c9b2  pop     r12
0x18006c9b4  pop     rdi
0x18006c9b5  pop     rsi
0x18006c9b6  pop     rbx
0x18006c9b7  retn
0x18006c9b8  xor     ebx, ebx
0x18006c9ba  mov     [rsp+0D8h+var_B8], ebx
0x18006c9be  xor     r12d, r12d
0x18006c9c1  mov     [rsp+0D8h+var_88], r12
0x18006c9c6  xor     r15d, r15d
0x18006c9c9  mov     [rsp+0D8h+var_80], r15
0x18006c9ce  xor     eax, eax
0x18006c9d0  mov     [rsp+0D8h+pv], rax
0x18006c9d5  mov     [rsp+0D8h+var_78], rax
0x18006c9da  mov     [rsp+0D8h+var_98], rax
0x18006c9df  mov     [rsp+0D8h+var_70], rax
0x18006c9e4  xor     r14d, r14d
0x18006c9e7  mov     [rsp+0D8h+var_B0], r14
0x18006c9ec  mov     [rsp+0D8h+var_68], r14
0x18006c9f1  mov     [rsp+0D8h+var_90], rax
0x18006c9f6  mov     [rsp+0D8h+var_60], rax
0x18006c9fb  xor     edi, edi
0x18006c9fd  mov     [rsp+0D8h+var_A8], edi
0x18006ca01  lea     rax, [rcx+1F0h]
0x18006ca08  mov     [rsp+0D8h+lpCriticalSection], rax
0x18006ca10  mov     rcx, rax; lpCriticalSection
0x18006ca13  call    cs:__imp_EnterCriticalSection
0x18006ca19  nop
0x18006ca1a  lea     eax, [rbx+1]
0x18006ca1d  lea     rdx, [r13+220h]
0x18006ca24  mov     rcx, [rdx]
0x18006ca27  cmp     rcx, rdx
0x18006ca2a  jz      short loc_18006CA37
0x18006ca2c  inc     edi
0x18006ca2e  mov     [rsp+0D8h+var_A8], edi
0x18006ca32  mov     rcx, [rcx]
0x18006ca35  jmp     short loc_18006CA27
0x18006ca37  xor     r9d, r9d
0x18006ca3a  test    edi, edi
0x18006ca3c  jz      loc_18006CD3E
0x18006ca42  test    rsi, rsi
0x18006ca45  jz      short loc_18006CA87
0x18006ca47  mov     esi, edi
0x18006ca49  shl     rsi, 3
0x18006ca4d  mov     rcx, rsi; cb
0x18006ca50  call    cs:__imp_CoTaskMemAlloc
0x18006ca56  mov     r12, rax
0x18006ca59  mov     [rsp+0D8h+var_88], rax
0x18006ca5e  xor     r9d, r9d
0x18006ca61  test    rax, rax
0x18006ca64  jnz     short loc_18006CA74
0x18006ca66  mov     ebx, 8007000Eh
0x18006ca6b  mov     [rsp+0D8h+var_B8], ebx
0x18006ca6f  jmp     loc_18006CD3E
0x18006ca74  mov     r8, rsi; Size
0x18006ca77  xor     edx, edx; Val
0x18006ca79  mov     rcx, rax; void *
0x18006ca7c  call    memset_0
0x18006ca81  xor     r9d, r9d
0x18006ca84  mov     eax, r9d
0x18006ca87  cmp     [rsp+0D8h+arg_18], r9
0x18006ca8f  jz      short loc_18006CAC3
0x18006ca91  mov     esi, edi
0x18006ca93  shl     rsi, 3
0x18006ca97  mov     rcx, rsi; cb
0x18006ca9a  call    cs:__imp_CoTaskMemAlloc
0x18006caa0  mov     r15, rax
0x18006caa3  mov     [rsp+0D8h+var_80], rax
0x18006caa8  xor     r9d, r9d
0x18006caab  test    rax, rax
0x18006caae  jz      short loc_18006CA66
0x18006cab0  mov     r8, rsi; Size
0x18006cab3  xor     edx, edx; Val
0x18006cab5  mov     rcx, rax; void *
0x18006cab8  call    memset_0
0x18006cabd  xor     r9d, r9d
0x18006cac0  mov     eax, r9d
0x18006cac3  cmp     [rsp+0D8h+arg_20], r9
0x18006cacb  jz      short loc_18006CAF2
0x18006cacd  mov     ecx, edi
0x18006cacf  shl     rcx, 3; cb
0x18006cad3  call    cs:__imp_CoTaskMemAlloc
0x18006cad9  mov     [rsp+0D8h+pv], rax
0x18006cade  mov     [rsp+0D8h+var_78], rax
0x18006cae3  xor     r9d, r9d
0x18006cae6  test    rax, rax
0x18006cae9  jz      loc_18006CA66
0x18006caef  mov     eax, r9d
0x18006caf2  cmp     [rsp+0D8h+arg_28], r9
0x18006cafa  jz      short loc_18006CB21
0x18006cafc  mov     ecx, edi
0x18006cafe  shl     rcx, 3; cb
0x18006cb02  call    cs:__imp_CoTaskMemAlloc
0x18006cb08  mov     [rsp+0D8h+var_98], rax
0x18006cb0d  mov     [rsp+0D8h+var_70], rax
0x18006cb12  xor     r9d, r9d
0x18006cb15  test    rax, rax
0x18006cb18  jz      loc_18006CA66
0x18006cb1e  mov     eax, r9d
0x18006cb21  cmp     [rsp+0D8h+arg_30], r9
0x18006cb29  jz      short loc_18006CB5B
0x18006cb2b  mov     ecx, edi
0x18006cb2d  shl     rcx, 2; cb
0x18006cb31  call    cs:__imp_CoTaskMemAlloc
0x18006cb37  mov     rsi, rax
0x18006cb3a  mov     [rsp+0D8h+var_B0], rax
0x18006cb3f  mov     [rsp+0D8h+var_68], rax
0x18006cb44  xor     r9d, r9d
0x18006cb47  test    rax, rax
0x18006cb4a  jnz     short loc_18006CB56
0x18006cb4c  mov     ebx, 8007000Eh
0x18006cb51  jmp     loc_18006CD35
0x18006cb56  mov     eax, r9d
0x18006cb59  jmp     short loc_18006CB60
0x18006cb5b  mov     rsi, [rsp+0D8h+var_B0]
0x18006cb60  cmp     [rsp+0D8h+arg_38], r9
0x18006cb68  jz      short loc_18006CB8B
0x18006cb6a  mov     ecx, edi
0x18006cb6c  shl     rcx, 2; cb
0x18006cb70  call    cs:__imp_CoTaskMemAlloc
0x18006cb76  mov     [rsp+0D8h+var_90], rax
0x18006cb7b  mov     [rsp+0D8h+var_60], rax
0x18006cb80  xor     r9d, r9d
0x18006cb83  test    rax, rax
0x18006cb86  jz      short loc_18006CB4C
0x18006cb88  mov     eax, r9d
0x18006cb8b  test    eax, eax
0x18006cb8d  jnz     loc_18006CD39
0x18006cb93  mov     [rsp+0D8h+var_50], 0FFFFFFFFFFFFFFFFh
0x18006cb9f  test    rsi, rsi
0x18006cba2  jz      short loc_18006CBDF
0x18006cba4  test    byte ptr [r13+1ECh], 2
0x18006cbac  jnz     short loc_18006CBDF
0x18006cbae  lea     rdx, [r13+248h]; struct CDVRFileCollection::CClientInfo *
0x18006cbb5  lea     r9d, [rax+1]; int
0x18006cbb9  lea     r8, [rsp+0D8h+var_50]; unsigned __int64 *
0x18006cbc1  mov     rcx, [r13+240h]; this
0x18006cbc8  call    ?GetLastStreamTime@CDVRFileCollection@@QEAAJPEBUCClientInfo@1@PEA_KH@Z; CDVRFileCollection::GetLastStreamTime(CDVRFileCollection::CClientInfo const *,unsigned __int64 *,int)
0x18006cbcd  mov     ebx, eax
0x18006cbcf  xor     r9d, r9d
0x18006cbd2  test    eax, eax
0x18006cbd4  jns     short loc_18006CBDF
0x18006cbd6  mov     [rsp+0D8h+var_B8], eax
0x18006cbda  jmp     loc_18006CD39
0x18006cbdf  mov     esi, r9d
0x18006cbe2  mov     [rsp+0D8h+var_58], r9d
0x18006cbea  mov     r14, [r13+220h]
0x18006cbf1  lea     rax, [r13+220h]
0x18006cbf8  cmp     r14, rax
0x18006cbfb  jz      loc_18006CD32
0x18006cc01  test    r12, r12
0x18006cc04  jz      short loc_18006CC30
0x18006cc06  mov     rcx, [r14-8]
0x18006cc0a  test    rcx, rcx
0x18006cc0d  jz      short loc_18006CC52
0x18006cc0f  mov     edx, esi
0x18006cc11  mov     rax, [rcx]
0x18006cc14  lea     r8, [r12+rdx*8]
0x18006cc18  lea     rdx, IID_IDVRRecorder
0x18006cc1f  mov     rax, [rax]
0x18006cc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cc27  mov     ebx, eax
0x18006cc29  xor     r9d, r9d
0x18006cc2c  test    eax, eax
0x18006cc2e  js      short loc_18006CBD6
0x18006cc30  test    r15, r15
0x18006cc33  jz      short loc_18006CC9E
0x18006cc35  mov     rcx, [r14+10h]
0x18006cc39  test    rcx, rcx
0x18006cc3c  jz      short loc_18006CC5C
0x18006cc3e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006cc42  inc     rax
0x18006cc45  cmp     [rcx+rax*2], r9w
0x18006cc4a  jnz     short loc_18006CC42
0x18006cc4c  lea     rbx, [rax+1]
0x18006cc50  jmp     short loc_18006CC61
0x18006cc52  mov     ebx, 80004005h
0x18006cc57  jmp     loc_18006CD35
0x18006cc5c  mov     ebx, 1
0x18006cc61  lea     rcx, [rbx+rbx]; cb
0x18006cc65  call    cs:__imp_CoTaskMemAlloc
0x18006cc6b  mov     ecx, esi
0x18006cc6d  mov     [r15+rcx*8], rax
0x18006cc71  xor     r9d, r9d
0x18006cc74  test    rax, rax
0x18006cc77  jz      loc_18006CB4C
0x18006cc7d  mov     r8, [r14+10h]
0x18006cc81  mov     eax, esi
0x18006cc83  mov     rcx, [r15+rax*8]
0x18006cc87  test    r8, r8
0x18006cc8a  jz      short loc_18006CC9A
0x18006cc8c  mov     rdx, rbx
0x18006cc8f  call    cs:__imp__o_wcscpy_s
0x18006cc95  xor     r9d, r9d
0x18006cc98  jmp     short loc_18006CC9E
0x18006cc9a  mov     [rcx], r9w
0x18006cc9e  mov     rdx, [rsp+0D8h+pv]
0x18006cca3  test    rdx, rdx
0x18006cca6  jz      short loc_18006CCB2
0x18006cca8  mov     ecx, esi
0x18006ccaa  mov     rax, [r14-28h]
0x18006ccae  mov     [rdx+rcx*8], rax
0x18006ccb2  mov     rdx, [rsp+0D8h+var_98]
0x18006ccb7  test    rdx, rdx
0x18006ccba  jz      short loc_18006CCC6
0x18006ccbc  mov     ecx, esi
0x18006ccbe  mov     rax, [r14-20h]
0x18006ccc2  mov     [rdx+rcx*8], rax
0x18006ccc6  mov     rdx, [rsp+0D8h+var_B0]
0x18006cccb  test    rdx, rdx
0x18006ccce  jz      short loc_18006CCFF
0x18006ccd0  test    byte ptr [r13+1ECh], 2
0x18006ccd8  jnz     short loc_18006CCF9
0x18006ccda  mov     rax, [r14-28h]
0x18006ccde  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006cce2  jz      short loc_18006CCF9
0x18006cce4  mov     ecx, r9d
0x18006cce7  cmp     [rsp+0D8h+var_50], rax
0x18006ccef  setnb   cl
0x18006ccf2  mov     eax, esi
0x18006ccf4  mov     [rdx+rax*4], ecx
0x18006ccf7  jmp     short loc_18006CCFF
0x18006ccf9  mov     eax, esi
0x18006ccfb  mov     [rdx+rax*4], r9d
0x18006ccff  mov     rdx, [rsp+0D8h+var_90]
0x18006cd04  test    rdx, rdx
0x18006cd07  jz      short loc_18006CD21
0x18006cd09  mov     eax, [r14+18h]
0x18006cd0d  mov     ecx, eax
0x18006cd0f  shr     ecx, 2
0x18006cd12  and     ecx, 2
0x18006cd15  and     eax, 4
0x18006cd18  or      ecx, eax
0x18006cd1a  shr     ecx, 1
0x18006cd1c  mov     eax, esi
0x18006cd1e  mov     [rdx+rax*4], ecx
0x18006cd21  inc     esi
0x18006cd23  mov     [rsp+0D8h+var_58], esi
0x18006cd2a  mov     r14, [r14]
0x18006cd2d  jmp     loc_18006CBF1
0x18006cd32  mov     ebx, r9d
0x18006cd35  mov     [rsp+0D8h+var_B8], ebx
0x18006cd39  mov     r14, [rsp+0D8h+var_B0]
0x18006cd3e  test    ebx, ebx
0x18006cd40  jns     loc_18006CE1B
0x18006cd46  mov     esi, r9d
0x18006cd49  test    edi, edi
0x18006cd4b  jz      short loc_18006CD8B
0x18006cd4d  test    r12, r12
0x18006cd50  jz      short loc_18006CD6C
0x18006cd52  mov     eax, esi
0x18006cd54  mov     rcx, [r12+rax*8]
0x18006cd58  test    rcx, rcx
0x18006cd5b  jz      short loc_18006CD6C
0x18006cd5d  mov     rax, [rcx]
0x18006cd60  mov     rax, [rax+10h]
0x18006cd64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cd69  xor     r9d, r9d
0x18006cd6c  test    r15, r15
0x18006cd6f  jz      short loc_18006CD85
0x18006cd71  mov     eax, esi
0x18006cd73  mov     rcx, [r15+rax*8]; pv
0x18006cd77  test    rcx, rcx
0x18006cd7a  jz      short loc_18006CD85
0x18006cd7c  call    cs:__imp_CoTaskMemFree
0x18006cd82  xor     r9d, r9d
0x18006cd85  inc     esi
0x18006cd87  cmp     esi, edi
0x18006cd89  jb      short loc_18006CD4D
0x18006cd8b  test    r12, r12
0x18006cd8e  jz      short loc_18006CD9F
0x18006cd90  mov     rcx, r12; pv
0x18006cd93  call    cs:__imp_CoTaskMemFree
0x18006cd99  xor     r9d, r9d
0x18006cd9c  mov     r12d, r9d
0x18006cd9f  test    r15, r15
0x18006cda2  jz      short loc_18006CDB3
0x18006cda4  mov     rcx, r15; pv
  ... truncated ...
```
