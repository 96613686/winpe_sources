# PublisherConfigReader::PublisherConfigReader(_GUID const &,HKEY__ *,void *)

- ea: `0x1400050a0`
- end: `0x1400055ee`
- name: `??0PublisherConfigReader@@IEAA@AEBU_GUID@@PEAUHKEY__@@PEAX@Z`
- size: `1358`
- prototype: `PublisherConfigReader *__fastcall(PublisherConfigReader *__hidden this, const struct _GUID *, HKEY, void *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140004d40`
- `0x140017fbc`
- `0x14001e0c0`

## callees

- `0x1400050a0`
- `0x140005600`
- `0x140005620`
- `0x140005c9c`
- `0x14000cc80`
- `0x140022cec`
- `0x14002cb6c`
- `0x14002f6c8`
- `0x140031810`
- `0x140031828`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005377`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005377`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005319`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005368`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005319`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005368`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005327`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005327`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000544a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000544a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000526b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000527a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400053e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005412`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000526b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000527a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400053e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005412`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140005215`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x140005215`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
PublisherConfigReader *__fastcall PublisherConfigReader::PublisherConfigReader(
        PublisherConfigReader *this,
        const struct _GUID *a2,
        HKEY a3,
        void *a4)
{
  const char *v5; // r8
  char *v6; // r9
  _WORD *v7; // rcx
  PublisherConfigReader *v8; // rbx
  unsigned __int64 v9; // r13
  unsigned __int64 v10; // r12
  HKEY v11; // r14
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rax
  char *v15; // rbx
  HKEY v16; // rcx
  unsigned __int64 v17; // rax
  _WORD *v18; // rcx
  __int64 v19; // rcx
  void *hTransaction; // rax
  const WCHAR *v21; // r12
  __int64 v22; // r14
  LSTATUS v23; // eax
  __int64 v24; // r8
  unsigned int v25; // esi
  int StringValueNoThrow; // eax
  __int64 v27; // r8
  HKEY v28; // rax
  HKEY v29; // rcx
  HKEY v30; // rdx
  PVOID *v31; // rcx
  __int64 v32; // rcx
  unsigned __int64 v34; // rax
  unsigned __int64 v35; // rax
  SIZE_T v36; // rbx
  HANDLE ProcessHeap; // rax
  const void *v38; // rdx
  HANDLE v39; // rax
  __int64 v40; // [rsp+40h] [rbp-29h] BYREF
  __int64 v41; // [rsp+48h] [rbp-21h]
  _QWORD pExceptionObject[3]; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v43; // [rsp+68h] [rbp-1h]
  __int64 v44; // [rsp+6Ch] [rbp+3h]
  char v45; // [rsp+74h] [rbp+Bh]
  HKEY phkResult; // [rsp+D8h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+E0h] [rbp+77h]
  __int64 v48; // [rsp+E8h] [rbp+7Fh]

  hKey = a3;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = a4;
  *((struct _GUID *)this + 1) = *a2;
  *((_QWORD *)this + 4) = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((char *)this + 40);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((char *)this + 72);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((char *)this + 104);
  *((_BYTE *)this + 136) = 0;
  v7 = (_WORD *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 6) = v7;
  *v7 = 0;
  v8 = (PublisherConfigReader *)*((_QWORD *)this + 5);
  v9 = (__int64)(*((_QWORD *)this + 6) - (_QWORD)v8) >> 1;
  v10 = v9 + 38;
  if ( v9 >= v9 + 38 )
    goto LABEL_70;
  v11 = (HKEY)((char *)this + 56);
  v12 = 7;
  if ( v8 == (PublisherConfigReader *)((char *)this + 56) )
    v13 = 7;
  else
    v13 = (__int64)(*(_QWORD *)v11 - (_QWORD)v8) >> 1;
  if ( v13 >= v10 )
    goto LABEL_8;
  v14 = v8 == (PublisherConfigReader *)v11 ? 7LL : (__int64)(*(_QWORD *)v11 - (_QWORD)v8) >> 1;
  if ( v10 <= v14 )
    goto LABEL_8;
  if ( v8 != (PublisherConfigReader *)v11 )
    v12 = (__int64)(*(_QWORD *)v11 - (_QWORD)v8) >> 1;
  v34 = 2 * v12 + 1;
  if ( v34 < v10 )
    v34 = v9 + 38;
  if ( v34 > 0x3FFFFFFFFFFFFFF7LL )
    v34 = 0x3FFFFFFFFFFFFFF7LL;
  if ( v10 > v34
    || (v35 = (v34 + 8) & 0xFFFFFFFFFFFFFFF8uLL, v35 > 0x7FFFFFFFFFFFFFFFLL)
    || (v36 = 2 * v35,
        v40 = 2 * v35,
        ProcessHeap = GetProcessHeap(),
        (v8 = (PublisherConfigReader *)HeapAlloc(ProcessHeap, 0, v36)) == 0) )
  {
LABEL_70:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v5, 179);
    throw (EvtException *)pExceptionObject;
  }
  v38 = (const void *)*((_QWORD *)this + 5);
  v48 = 2 * ((__int64)(*((_QWORD *)this + 6) - (_QWORD)v38) >> 1);
  memcpy_0(v8, v38, v48 + 2);
  phkResult = (HKEY)*((_QWORD *)this + 5);
  if ( phkResult != v11 )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, phkResult);
  }
  *((_QWORD *)this + 5) = v8;
  *((_QWORD *)this + 6) = (char *)v8 + v48;
  *(_QWORD *)v11 = (char *)v8 + v40 - 2;
  v6 = (char *)this + 16;
LABEL_8:
  v15 = (char *)v8 + 2 * v9;
  if ( !v15 )
    goto LABEL_70;
  *(_WORD *)v15 = 123;
  tlx::guid_to_string_lower<wchar_t>(v15 + 2, v6, 0);
  *(_DWORD *)(v15 + 74) = 125;
  v16 = (HKEY)*((_QWORD *)this + 5);
  if ( v16 == v11 )
    v17 = 7;
  else
    v17 = (__int64)(*(_QWORD *)v11 - (_QWORD)v16) >> 1;
  if ( v10 > v17 )
    __int2c();
  v18 = (_WORD *)v16 + v10;
  *((_QWORD *)this + 6) = v18;
  *v18 = 0;
  v19 = *((_QWORD *)this + 4);
  if ( v19 && _InterlockedExchangeAdd((volatile signed __int32 *)(v19 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
  *((_QWORD *)this + 4) = 0;
  hTransaction = (void *)*((_QWORD *)this + 1);
  v21 = (const WCHAR *)*((_QWORD *)this + 5);
  v22 = (__int64)(*((_QWORD *)this + 6) - (_QWORD)v21) >> 1;
  phkResult = 0;
  if ( hTransaction == (void *)-1LL )
    v23 = RegOpenKeyExW(hKey, v21, 0, 0x20019u, &phkResult);
  else
    v23 = RegOpenKeyTransactedW(hKey, v21, 0, 0x20019u, &phkResult, hTransaction, 0);
  v25 = v23;
  if ( v23 )
  {
    v31 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v40 = (__int64)v21;
      v41 = v22;
      WPP_SF__utlwsv_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v24, &v40, v23);
      v31 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      v31 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    StringValueNoThrow = RegReadStringValueNoThrow(phkResult);
    if ( StringValueNoThrow )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v40 = (__int64)v21;
        v41 = v22;
        WPP_SF__utlwsv_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v27, &v40, StringValueNoThrow);
      }
      eventlog::ai::WarningMessage((eventlog::ai *)0x50, (unsigned int)v21);
      if ( phkResult )
        RegCloseKey(phkResult);
      v25 = 15010;
    }
    else
    {
      v28 = phkResult;
      v29 = 0;
      phkResult = 0;
      v30 = *(HKEY *)this;
      *(_QWORD *)this = v28;
      if ( v30 )
      {
        RegCloseKey(v30);
        v29 = phkResult;
      }
      if ( v29 )
        RegCloseKey(v29);
      v25 = 0;
    }
    v31 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v25 )
  {
    if ( v31 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v31 + 28) & 4) != 0 && *((_BYTE *)v31 + 25) >= 2u )
      {
        WPP_SF_d(v31[2], 18, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, v25);
        v31 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 4) != 0 && *((_BYTE *)v31 + 25) >= 2u )
        WPP_SF_d(v31[2], 24, &WPP_e40e9425320d341abfed50516b3c9004_Traceguids, v25);
    }
    pExceptionObject[0] = word_14003838A;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v43 = v25;
    v44 = -1;
    v45 = 0;
    throw (EvtException *)pExceptionObject;
  }
  v32 = *((_QWORD *)this + 4);
  if ( v32 && _InterlockedExchangeAdd((volatile signed __int32 *)(v32 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v32)(v32, 1);
  *((_QWORD *)this + 4) = 0;
  return this;
}

```

## disassembly

```asm
0x1400050a0  mov     [rsp-8+hKey], r8
0x1400050a5  mov     [rsp-8+arg_0], rcx
0x1400050aa  push    rbp
0x1400050ab  push    rbx
0x1400050ac  push    rsi
0x1400050ad  push    rdi
0x1400050ae  push    r12
0x1400050b0  push    r13
0x1400050b2  push    r14
0x1400050b4  push    r15
0x1400050b6  lea     rbp, [rsp-1Fh]
0x1400050bb  sub     rsp, 88h
0x1400050c2  mov     rdi, rcx
0x1400050c5  xor     r14d, r14d
0x1400050c8  mov     [rcx], r14
0x1400050cb  mov     [rcx+8], r9
0x1400050cf  lea     r9, [rcx+10h]
0x1400050d3  movups  xmm0, xmmword ptr [rdx]
0x1400050d6  movups  xmmword ptr [r9], xmm0
0x1400050da  mov     [rcx+20h], r14
0x1400050de  add     rcx, 28h ; '('
0x1400050e2  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400050e7  nop
0x1400050e8  lea     rcx, [rdi+48h]
0x1400050ec  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400050f1  nop
0x1400050f2  lea     rcx, [rdi+68h]
0x1400050f6  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1400050fb  nop
0x1400050fc  mov     [rdi+88h], r14b
0x140005103  mov     rcx, [rdi+28h]
0x140005107  mov     [rdi+30h], rcx
0x14000510b  mov     [rcx], r14w
0x14000510f  mov     rbx, [rdi+28h]
0x140005113  mov     r13, [rdi+30h]
0x140005117  sub     r13, rbx
0x14000511a  sar     r13, 1
0x14000511d  lea     r12, [r13+26h]
0x140005121  cmp     r13, r12
0x140005124  jnb     loc_14000558F
0x14000512a  lea     r14, [rdi+38h]
0x14000512e  mov     ecx, 7
0x140005133  cmp     rbx, r14
0x140005136  jnz     loc_1400053A3
0x14000513c  mov     eax, ecx
0x14000513e  cmp     rax, r12
0x140005141  jnb     short loc_140005158
0x140005143  cmp     rbx, r14
0x140005146  jnz     loc_1400053B1
0x14000514c  mov     rax, rcx
0x14000514f  cmp     r12, rax
0x140005152  ja      loc_1400052C4
0x140005158  lea     rbx, [rbx+r13*2]
0x14000515c  test    rbx, rbx
0x14000515f  jz      loc_14000558F
0x140005165  mov     word ptr [rbx], 7Bh ; '{'
0x14000516a  xor     r8d, r8d
0x14000516d  mov     rdx, r9
0x140005170  lea     rcx, [rbx+2]
0x140005174  call    ??$guid_to_string_lower@_W@tlx@@YAXPEA_WAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<wchar_t>(wchar_t *,_GUID const &,bool)
0x140005179  mov     dword ptr [rbx+4Ah], 7Dh ; '}'
0x140005180  xor     r13d, r13d
0x140005183  mov     rcx, [rdi+28h]
0x140005187  cmp     rcx, r14
0x14000518a  jnz     loc_1400053BF
0x140005190  mov     eax, 7
0x140005195  cmp     r12, rax
0x140005198  ja      loc_140005425
0x14000519e  lea     rcx, [rcx+r12*2]
0x1400051a2  mov     [rdi+30h], rcx
0x1400051a6  mov     [rcx], r13w
0x1400051aa  mov     rcx, [rdi+20h]
0x1400051ae  mov     ebx, 0FFFFFFFFh
0x1400051b3  test    rcx, rcx
0x1400051b6  jz      short loc_1400051C8
0x1400051b8  mov     eax, ebx
0x1400051ba  lock xadd [rcx+8], eax
0x1400051bf  cmp     eax, 1
0x1400051c2  jz      loc_14000542C
0x1400051c8  lea     rcx, [rdi+20h]
0x1400051cc  mov     rax, r13
0x1400051cf  mov     [rcx], rax
0x1400051d2  mov     rax, [rdi+8]
0x1400051d6  mov     r12, [rdi+28h]
0x1400051da  mov     r14, [rdi+30h]
0x1400051de  sub     r14, r12
0x1400051e1  sar     r14, 1
0x1400051e4  mov     [rbp+57h+arg_8], r13
0x1400051e8  mov     r9d, 20019h; samDesired
0x1400051ee  xor     r8d, r8d; ulOptions
0x1400051f1  mov     rdx, r12; lpSubKey
0x1400051f4  mov     rcx, [rbp+57h+hKey]; hKey
0x1400051f8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400051fc  jz      loc_140005441
0x140005202  mov     [rsp+0C0h+pExtendedParemeter], r13; pExtendedParemeter
0x140005207  mov     [rsp+0C0h+hTransaction], rax; hTransaction
0x14000520c  lea     rax, [rbp+57h+arg_8]
0x140005210  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140005215  call    cs:__imp_RegOpenKeyTransactedW
0x14000521b  mov     esi, eax
0x14000521d  lea     r13, WPP_GLOBAL_Control
0x140005224  test    eax, eax
0x140005226  jnz     loc_140005455
0x14000522c  lea     r9, [rdi+48h]
0x140005230  lea     r8, ValueName
0x140005237  lea     rdx, ValueName
0x14000523e  mov     rcx, [rbp+57h+arg_8]; hKey
0x140005242  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140005247  test    eax, eax
0x140005249  jnz     loc_1400054A3
0x14000524f  mov     rax, [rbp+57h+arg_8]
0x140005253  xor     r14d, r14d
0x140005256  mov     ecx, r14d
0x140005259  mov     [rbp+57h+arg_8], rcx
0x14000525d  mov     rdx, [rdi]
0x140005260  mov     [rdi], rax
0x140005263  test    rdx, rdx
0x140005266  jz      short loc_140005275
0x140005268  mov     rcx, rdx; hKey
0x14000526b  call    cs:__imp_RegCloseKey
0x140005271  mov     rcx, [rbp+57h+arg_8]; hKey
0x140005275  test    rcx, rcx
0x140005278  jz      short loc_140005280
0x14000527a  call    cs:__imp_RegCloseKey
0x140005280  mov     esi, r14d
0x140005283  mov     rcx, cs:WPP_GLOBAL_Control
0x14000528a  test    esi, esi
0x14000528c  jnz     loc_1400054EA
0x140005292  mov     rcx, [rdi+20h]
0x140005296  test    rcx, rcx
0x140005299  jz      short loc_1400052A9
0x14000529b  lock xadd [rcx+8], ebx
0x1400052a0  cmp     ebx, 1
0x1400052a3  jz      loc_14000557A
0x1400052a9  mov     [rdi+20h], r14
0x1400052ad  mov     rax, rdi
0x1400052b0  add     rsp, 88h
0x1400052b7  pop     r15
0x1400052b9  pop     r14
0x1400052bb  pop     r13
0x1400052bd  pop     r12
0x1400052bf  pop     rdi
0x1400052c0  pop     rsi
0x1400052c1  pop     rbx
0x1400052c2  pop     rbp
0x1400052c3  retn
0x1400052c4  cmp     rbx, r14
0x1400052c7  jnz     loc_1400053CD
0x1400052cd  lea     rax, ds:1[rcx*2]
0x1400052d5  cmp     rax, r12
0x1400052d8  cmovb   rax, r12
0x1400052dc  mov     rcx, 3FFFFFFFFFFFFFF7h
0x1400052e6  cmp     rax, rcx
0x1400052e9  cmova   rax, rcx
0x1400052ed  cmp     r12, rax
0x1400052f0  ja      loc_14000558F
0x1400052f6  add     rax, 8
0x1400052fa  and     rax, 0FFFFFFFFFFFFFFF8h
0x1400052fe  mov     rcx, 7FFFFFFFFFFFFFFFh
0x140005308  cmp     rax, rcx
0x14000530b  ja      loc_14000558F
0x140005311  lea     rbx, [rax+rax]
0x140005315  mov     [rbp+57h+var_80], rbx
0x140005319  call    cs:__imp_GetProcessHeap
0x14000531f  mov     rcx, rax; hHeap
0x140005322  mov     r8, rbx; dwBytes
0x140005325  xor     edx, edx; dwFlags
0x140005327  call    cs:__imp_HeapAlloc
0x14000532d  mov     rbx, rax
0x140005330  test    rax, rax
0x140005333  jz      loc_14000558F
0x140005339  mov     rdx, [rdi+28h]; Src
0x14000533d  mov     rcx, [rdi+30h]
0x140005341  sub     rcx, rdx
0x140005344  sar     rcx, 1
0x140005347  lea     rax, [rcx+rcx]
0x14000534b  mov     [rbp+57h+arg_18], rax
0x14000534f  lea     r8, [rax+2]; Size
0x140005353  mov     rcx, rbx; void *
0x140005356  call    memcpy_0
0x14000535b  mov     rax, [rdi+28h]
0x14000535f  mov     [rbp+57h+arg_8], rax
0x140005363  cmp     rax, r14
0x140005366  jz      short loc_14000537D
0x140005368  call    cs:__imp_GetProcessHeap
0x14000536e  mov     rcx, rax; hHeap
0x140005371  mov     r8, [rbp+57h+arg_8]; lpMem
0x140005375  xor     edx, edx; dwFlags
0x140005377  call    cs:__imp_HeapFree
0x14000537d  mov     [rdi+28h], rbx
0x140005381  mov     rax, [rbp+57h+arg_18]
0x140005385  add     rax, rbx
0x140005388  mov     [rdi+30h], rax
0x14000538c  mov     rax, [rbp+57h+var_80]
0x140005390  add     rax, 0FFFFFFFFFFFFFFFEh
0x140005394  add     rax, rbx
0x140005397  mov     [r14], rax
0x14000539a  lea     r9, [rdi+10h]
0x14000539e  jmp     loc_140005158
0x1400053a3  mov     rax, [r14]
0x1400053a6  sub     rax, rbx
0x1400053a9  sar     rax, 1
0x1400053ac  jmp     loc_14000513E
0x1400053b1  mov     rax, [r14]
0x1400053b4  sub     rax, rbx
0x1400053b7  sar     rax, 1
0x1400053ba  jmp     loc_14000514F
0x1400053bf  mov     rax, [r14]
0x1400053c2  sub     rax, rcx
0x1400053c5  sar     rax, 1
0x1400053c8  jmp     loc_140005195
0x1400053cd  mov     rcx, [r14]
0x1400053d0  sub     rcx, rbx
0x1400053d3  sar     rcx, 1
0x1400053d6  jmp     loc_1400052CD
0x1400053db  mov     rax, [rbp+57h+arg_8]
0x1400053df  test    rax, rax
0x1400053e2  jz      short loc_1400053F4
0x1400053e4  mov     rcx, rax; hKey
0x1400053e7  call    cs:__imp_RegCloseKey
0x1400053ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400053f4  xor     r14d, r14d
0x1400053f7  jmp     loc_14000528A
0x1400053fc  mov     rdx, r12; unsigned int
0x1400053ff  mov     ecx, 50h ; 'P'; this
0x140005404  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x140005409  mov     rcx, [rbp+57h+arg_8]; hKey
0x14000540d  test    rcx, rcx
0x140005410  jz      short loc_140005418
0x140005412  call    cs:__imp_RegCloseKey
0x140005418  mov     esi, 3AA2h
0x14000541d  xor     r14d, r14d
0x140005420  jmp     loc_140005283
0x140005425  int     2Ch; Windows NT - assertion failure
0x140005427  jmp     loc_14000519E
0x14000542c  mov     rax, [rcx]
0x14000542f  mov     edx, 1
0x140005434  mov     rax, [rax]
0x140005437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000543c  jmp     loc_1400051C8
0x140005441  lea     rax, [rbp+57h+arg_8]
0x140005445  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14000544a  call    cs:__imp_RegOpenKeyExW
0x140005450  jmp     loc_14000521B
0x140005455  mov     rcx, cs:WPP_GLOBAL_Control
0x14000545c  cmp     rcx, r13
0x14000545f  jz      loc_1400053DB
0x140005465  test    byte ptr [rcx+1Ch], 4
0x140005469  jz      loc_1400053DB
0x14000546f  cmp     byte ptr [rcx+19h], 2
0x140005473  jb      loc_1400053DB
0x140005479  mov     [rbp+57h+var_80], r12
0x14000547d  mov     [rbp+57h+var_78], r14
0x140005481  mov     edx, 10h
0x140005486  mov     dword ptr [rsp+0C0h+phkResult], esi
0x14000548a  lea     r9, [rbp+57h+var_80]
0x14000548e  mov     rcx, [rcx+10h]
0x140005492  call    WPP_SF__utlwsv_D
0x140005497  mov     rcx, cs:WPP_GLOBAL_Control
0x14000549e  jmp     loc_1400053DB
0x1400054a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400054aa  cmp     rcx, r13
0x1400054ad  jz      loc_1400053FC
0x1400054b3  test    byte ptr [rcx+1Ch], 4
0x1400054b7  jz      loc_1400053FC
0x1400054bd  cmp     byte ptr [rcx+19h], 3
0x1400054c1  jb      loc_1400053FC
0x1400054c7  mov     [rbp+57h+var_80], r12
0x1400054cb  mov     [rbp+57h+var_78], r14
0x1400054cf  mov     edx, 11h
0x1400054d4  mov     dword ptr [rsp+0C0h+phkResult], eax
0x1400054d8  lea     r9, [rbp+57h+var_80]
0x1400054dc  mov     rcx, [rcx+10h]
0x1400054e0  call    WPP_SF__utlwsv_D
0x1400054e5  jmp     loc_1400053FC
0x1400054ea  cmp     rcx, r13
0x1400054ed  jz      short loc_140005543
0x1400054ef  test    byte ptr [rcx+1Ch], 4
0x1400054f3  jz      short loc_14000551A
0x1400054f5  cmp     byte ptr [rcx+19h], 2
0x1400054f9  jb      short loc_14000551A
0x1400054fb  mov     edx, 12h
0x140005500  mov     r9d, esi
0x140005503  lea     r8, WPP_e40e9425320d341abfed50516b3c9004_Traceguids
0x14000550a  mov     rcx, [rcx+10h]
0x14000550e  call    WPP_SF_d
0x140005513  mov     rcx, cs:WPP_GLOBAL_Control
0x14000551a  cmp     rcx, r13
0x14000551d  jz      short loc_140005543
0x14000551f  test    byte ptr [rcx+1Ch], 4
0x140005523  jz      short loc_140005543
0x140005525  cmp     byte ptr [rcx+19h], 2
0x140005529  jb      short loc_140005543
0x14000552b  mov     edx, 18h
0x140005530  mov     r9d, esi
0x140005533  lea     r8, WPP_e40e9425320d341abfed50516b3c9004_Traceguids
0x14000553a  mov     rcx, [rcx+10h]
0x14000553e  call    WPP_SF_d
0x140005543  lea     rax, word_14003838A
0x14000554a  mov     [rbp+57h+pExceptionObject], rax
  ... truncated ...
```
