# CHtmlClipboardFormatParserForSavingResourceMap::_ProcessHtml(char const *,unsigned __int64,CSimplePointerArrayRelease<IStream> *,char * *)

- ea: `0x1800645a4`
- end: `0x180064878`
- name: `?_ProcessHtml@CHtmlClipboardFormatParserForSavingResourceMap@@AEAAJPEBD_KPEAV?$CSimplePointerArrayRelease@UIStream@@@@PEAPEAD@Z`
- size: `724`
- prototype: `__int64 __fastcall(__int64, const char *, unsigned __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180063450`

## callees

- `0x180002ad0`
- `0x18000581b`
- `0x1800161c8`
- `0x180061ab0`
- `0x180062c2c`
- `0x1800645a4`
- `0x18007e450`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180064832`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180064832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800646a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800646a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064793`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800647a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800647f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064793`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800647a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800647f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006479d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006479d`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180064698`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180064698`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHtmlClipboardFormatParserForSavingResourceMap::_ProcessHtml(
        __int64 a1,
        const char *a2,
        unsigned __int64 a3,
        _QWORD *a4,
        _QWORD *a5)
{
  signed int FileStreamList; // edi
  int TempPath2W; // eax
  signed int LastError; // eax
  void *v11; // rbx
  void *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h]
  __int64 v21; // [rsp+48h] [rbp-B8h]
  __int64 v22; // [rsp+50h] [rbp-B0h]
  void **v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h]
  _WORD v25[260]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+278h] [rbp+178h] BYREF
  __int128 v27; // [rsp+280h] [rbp+180h]
  __int64 v28; // [rsp+290h] [rbp+190h]
  char v29; // [rsp+298h] [rbp+198h]
  void ***v30; // [rsp+2A0h] [rbp+1A0h] BYREF
  char v31; // [rsp+2A8h] [rbp+1A8h]
  __int16 v32; // [rsp+2AAh] [rbp+1AAh]

  *a5 = 0;
  v18 = 0;
  FileStreamList = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 24) + 152LL))(
                     *(_QWORD *)(a1 + 24),
                     &v18);
  if ( FileStreamList < 0 )
    goto LABEL_30;
  v16 = 0;
  if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 56LL))(v18, &v16) < 0 || !v16 )
  {
    FileStreamList = -2147023728;
    RoOriginateError(2147943568LL, 0);
    goto LABEL_30;
  }
  v23 = &CSaveResMapHandler::`vftable';
  v24 = v18;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 1;
  v25[0] = 0;
  TempPath2W = GetTempPath2W(260, v25);
  if ( TempPath2W )
  {
    FileStreamList = (unsigned int)(TempPath2W - 1) > 0x103 ? 0x8007007A : 0;
  }
  else
  {
    LastError = GetLastError();
    FileStreamList = LastError;
    if ( LastError > 0 )
      FileStreamList = (unsigned __int16)LastError | 0x80070000;
    if ( FileStreamList >= 0 )
      FileStreamList = -2147467259;
  }
  if ( FileStreamList >= 0 )
  {
    v30 = &v23;
    v31 = 1;
    v32 = 48;
    pv = 0;
    FileStreamList = CHtmlProcessor::ProcessHtml((CHtmlProcessor *)&v30, a2, a3, (char **)&pv);
    if ( FileStreamList < 0 )
    {
      v11 = pv;
      goto LABEL_25;
    }
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    FileStreamList = CSaveResMapHandler::GetFileStreamList(&v23, &v19);
    if ( FileStreamList < 0 )
    {
      v11 = pv;
      goto LABEL_23;
    }
    *a4 = v19;
    a4[2] = v21;
    a4[1] = v20;
    a4[3] = v22;
    v19 = 0;
    v21 = 0;
    v20 = 0;
    v22 = 0;
    if ( v29 )
    {
      CoTaskMemFree(pv);
      v11 = CoTaskMemAlloc(a3 + 1);
      CoTaskMemFree(0);
      if ( !v11 )
      {
        FileStreamList = -2147024882;
LABEL_23:
        CSimplePointerArray<IStream,CTContainer_PolicyRelease<IStream>,CSimpleArrayStandardCompareHelper<IStream *>>::~CSimplePointerArray<IStream,CTContainer_PolicyRelease<IStream>,CSimpleArrayStandardCompareHelper<IStream *>>(&v19);
LABEL_25:
        CoTaskMemFree(v11);
        goto LABEL_26;
      }
      memcpy_0(v11, a2, a3);
      *((_BYTE *)v11 + a3) = 0;
    }
    else
    {
      v11 = pv;
    }
    v12 = v11;
    v11 = 0;
    *a5 = v12;
    goto LABEL_23;
  }
LABEL_26:
  CSimplePointerArray<IStream,CTContainer_PolicyRelease<IStream>,CSimpleArrayStandardCompareHelper<IStream *>>::~CSimplePointerArray<IStream,CTContainer_PolicyRelease<IStream>,CSimpleArrayStandardCompareHelper<IStream *>>(&v26);
  v13 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
LABEL_30:
  v14 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return (unsigned int)FileStreamList;
}

```

## disassembly

```asm
0x1800645a4  push    rbp
0x1800645a6  push    rbx
0x1800645a7  push    rsi
0x1800645a8  push    rdi
0x1800645a9  push    r12
0x1800645ab  push    r14
0x1800645ad  push    r15
0x1800645af  lea     rbp, [rsp-1210h]
0x1800645b7  mov     eax, 1310h
0x1800645bc  call    _alloca_probe
0x1800645c1  sub     rsp, rax
0x1800645c4  mov     rax, cs:__security_cookie
0x1800645cb  xor     rax, rsp
0x1800645ce  mov     [rbp+1240h+var_40], rax
0x1800645d5  mov     rbx, r9
0x1800645d8  mov     rsi, r8
0x1800645db  mov     r14, rdx
0x1800645de  mov     r15, [rbp+1240h+arg_20]
0x1800645e5  xor     r12d, r12d
0x1800645e8  mov     [r15], r12
0x1800645eb  mov     [rsp+1340h+var_1310], r12
0x1800645f0  mov     rcx, [rcx+18h]
0x1800645f4  mov     rax, [rcx]
0x1800645f7  lea     rdx, [rsp+1340h+var_1310]
0x1800645fc  mov     rax, [rax+98h]
0x180064603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064608  mov     edi, eax
0x18006460a  test    eax, eax
0x18006460c  js      loc_180064839
0x180064612  mov     [rsp+1340h+var_1320], r12d
0x180064617  mov     rcx, [rsp+1340h+var_1310]
0x18006461c  mov     rax, [rcx]
0x18006461f  lea     rdx, [rsp+1340h+var_1320]
0x180064624  mov     rax, [rax+38h]
0x180064628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006462d  test    eax, eax
0x18006462f  js      loc_180064829
0x180064635  cmp     [rsp+1340h+var_1320], r12d
0x18006463a  jbe     loc_180064829
0x180064640  lea     rax, ??_7CSaveResMapHandler@@6B@; const CSaveResMapHandler::`vftable'
0x180064647  mov     [rsp+1340h+var_12E0], rax
0x18006464c  mov     rcx, [rsp+1340h+var_1310]
0x180064651  mov     [rsp+1340h+var_12D8], rcx
0x180064656  test    rcx, rcx
0x180064659  jz      short loc_180064668
0x18006465b  mov     rax, [rcx]
0x18006465e  mov     rax, [rax+8]
0x180064662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064667  nop
0x180064668  mov     [rbp+1240h+var_10C8], r12
0x18006466f  xorps   xmm0, xmm0
0x180064672  movdqa  [rbp+1240h+var_10C0], xmm0
0x18006467a  mov     [rbp+1240h+var_10B0], r12
0x180064681  mov     [rbp+1240h+var_10A8], 1
0x180064688  mov     [rsp+1340h+var_12D0], r12w
0x18006468e  lea     rdx, [rsp+1340h+var_12D0]
0x180064693  mov     ecx, 104h
0x180064698  call    cs:__imp_GetTempPath2W
0x18006469e  test    eax, eax
0x1800646a0  jnz     short loc_1800646C3
0x1800646a2  call    cs:__imp_GetLastError
0x1800646a8  mov     edi, eax
0x1800646aa  test    eax, eax
0x1800646ac  jle     short loc_1800646B7
0x1800646ae  movzx   edi, ax
0x1800646b1  or      edi, 80070000h
0x1800646b7  mov     eax, 80004005h
0x1800646bc  test    edi, edi
0x1800646be  cmovns  edi, eax
0x1800646c1  jmp     short loc_1800646D4
0x1800646c3  dec     eax
0x1800646c5  mov     ecx, 103h
0x1800646ca  cmp     ecx, eax
0x1800646cc  sbb     edi, edi
0x1800646ce  and     edi, 8007007Ah
0x1800646d4  test    edi, edi
0x1800646d6  js      loc_1800647FE
0x1800646dc  lea     rax, [rsp+1340h+var_12E0]
0x1800646e1  mov     [rbp+1240h+var_10A0], rax
0x1800646e8  mov     [rbp+1240h+var_1098], 1
0x1800646ef  mov     eax, 30h ; '0'
0x1800646f4  mov     [rbp+1240h+var_1096], ax
0x1800646fb  mov     [rsp+1340h+pv], r12
0x180064700  lea     r9, [rsp+1340h+pv]; char **
0x180064705  mov     r8, rsi; unsigned __int64
0x180064708  mov     rdx, r14; char *
0x18006470b  lea     rcx, [rbp+1240h+var_10A0]; this
0x180064712  call    ?ProcessHtml@CHtmlProcessor@@QEAAJPEBD_KPEAPEAD@Z; CHtmlProcessor::ProcessHtml(char const *,unsigned __int64,char * *)
0x180064717  mov     edi, eax
0x180064719  test    eax, eax
0x18006471b  js      loc_1800647EF
0x180064721  mov     [rsp+1340h+var_1308], r12
0x180064726  mov     [rsp+1340h+var_1300], r12
0x18006472b  mov     [rsp+1340h+var_12F8], r12
0x180064730  mov     [rsp+1340h+var_12F0], r12
0x180064735  lea     rdx, [rsp+1340h+var_1308]
0x18006473a  lea     rcx, [rsp+1340h+var_12E0]
0x18006473f  call    ?GetFileStreamList@CSaveResMapHandler@@QEAAJPEAV?$CSimplePointerArrayRelease@UIStream@@@@@Z; CSaveResMapHandler::GetFileStreamList(CSimplePointerArrayRelease<IStream> *)
0x180064744  mov     edi, eax
0x180064746  test    eax, eax
0x180064748  js      loc_1800647DE
0x18006474e  mov     rax, [rsp+1340h+var_1308]
0x180064753  mov     [rbx], rax
0x180064756  mov     rax, [rsp+1340h+var_12F8]
0x18006475b  mov     [rbx+10h], rax
0x18006475f  mov     rax, [rsp+1340h+var_1300]
0x180064764  mov     [rbx+8], rax
0x180064768  mov     rax, [rsp+1340h+var_12F0]
0x18006476d  mov     [rbx+18h], rax
0x180064771  mov     [rsp+1340h+var_1308], r12
0x180064776  mov     [rsp+1340h+var_12F8], r12
0x18006477b  mov     [rsp+1340h+var_1300], r12
0x180064780  mov     [rsp+1340h+var_12F0], r12
0x180064785  cmp     [rbp+1240h+var_10A8], r12b
0x18006478c  jz      short loc_1800647CE
0x18006478e  mov     rcx, [rsp+1340h+pv]; pv
0x180064793  call    cs:__imp_CoTaskMemFree
0x180064799  lea     rcx, [rsi+1]; cb
0x18006479d  call    cs:__imp_CoTaskMemAlloc
0x1800647a3  mov     rbx, rax
0x1800647a6  xor     ecx, ecx; pv
0x1800647a8  call    cs:__imp_CoTaskMemFree
0x1800647ae  test    rbx, rbx
0x1800647b1  jz      short loc_1800647C7
0x1800647b3  mov     r8, rsi; Size
0x1800647b6  mov     rdx, r14; Src
0x1800647b9  mov     rcx, rbx; void *
0x1800647bc  call    memcpy_0
0x1800647c1  mov     [rsi+rbx], r12b
0x1800647c5  jmp     short loc_1800647D3
0x1800647c7  mov     edi, 8007000Eh
0x1800647cc  jmp     short loc_1800647E3
0x1800647ce  mov     rbx, [rsp+1340h+pv]
0x1800647d3  mov     rax, rbx
0x1800647d6  mov     rbx, r12
0x1800647d9  mov     [r15], rax
0x1800647dc  jmp     short loc_1800647E3
0x1800647de  mov     rbx, [rsp+1340h+pv]
0x1800647e3  lea     rcx, [rsp+1340h+var_1308]
0x1800647e8  call    ??1?$CSimplePointerArray@UIStream@@V?$CTContainer_PolicyRelease@UIStream@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIStream@@@@@@QEAA@XZ; CSimplePointerArray<IStream,CTContainer_PolicyRelease<IStream>,CSimpleArrayStandardCompareHelper<IStream *>>::~CSimplePointerArray<IStream,CTContainer_PolicyRelease<IStream>,CSimpleArrayStandardCompareHelper<IStream *>>(void)
0x1800647ed  jmp     short loc_1800647F4
0x1800647ef  mov     rbx, [rsp+1340h+pv]
0x1800647f4  mov     rcx, rbx; pv
0x1800647f7  call    cs:__imp_CoTaskMemFree
0x1800647fd  nop
0x1800647fe  lea     rcx, [rbp+1240h+var_10C8]
0x180064805  call    ??1?$CSimplePointerArray@UIStream@@V?$CTContainer_PolicyRelease@UIStream@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIStream@@@@@@QEAA@XZ; CSimplePointerArray<IStream,CTContainer_PolicyRelease<IStream>,CSimpleArrayStandardCompareHelper<IStream *>>::~CSimplePointerArray<IStream,CTContainer_PolicyRelease<IStream>,CSimpleArrayStandardCompareHelper<IStream *>>(void)
0x18006480a  nop
0x18006480b  mov     rcx, [rsp+1340h+var_12D8]
0x180064810  test    rcx, rcx
0x180064813  jz      short loc_180064827
0x180064815  mov     [rsp+1340h+var_12D8], r12
0x18006481a  mov     rax, [rcx]
0x18006481d  mov     rax, [rax+10h]
0x180064821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064826  nop
0x180064827  jmp     short loc_180064839
0x180064829  xor     edx, edx
0x18006482b  mov     edi, 80070490h
0x180064830  mov     ecx, edi
0x180064832  call    cs:__imp_RoOriginateError
0x180064838  nop
0x180064839  mov     rcx, [rsp+1340h+var_1310]
0x18006483e  test    rcx, rcx
0x180064841  jz      short loc_180064855
0x180064843  mov     [rsp+1340h+var_1310], r12
0x180064848  mov     rax, [rcx]
0x18006484b  mov     rax, [rax+10h]
0x18006484f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064854  nop
0x180064855  mov     eax, edi
0x180064857  mov     rcx, [rbp+1240h+var_40]
0x18006485e  xor     rcx, rsp; StackCookie
0x180064861  call    __security_check_cookie
0x180064866  add     rsp, 1310h
0x18006486d  pop     r15
0x18006486f  pop     r14
0x180064871  pop     r12
0x180064873  pop     rdi
0x180064874  pop     rsi
0x180064875  pop     rbx
0x180064876  pop     rbp
0x180064877  retn
```
