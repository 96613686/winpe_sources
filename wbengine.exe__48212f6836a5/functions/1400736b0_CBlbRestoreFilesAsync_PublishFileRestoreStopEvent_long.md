# CBlbRestoreFilesAsync::PublishFileRestoreStopEvent(long)

- ea: `0x1400736b0`
- end: `0x140073cbc`
- name: `?PublishFileRestoreStopEvent@CBlbRestoreFilesAsync@@AEAAJJ@Z`
- size: `1548`
- prototype: `__int64 __fastcall(CBlbRestoreFilesAsync *__hidden this, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task`

## callers

- `0x140070400`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140071328`
- `0x1400736b0`
- `0x1400889f0`
- `0x14008fed0`
- `0x1400d64f0`
- `0x1400d65b8`
- `0x1400d668c`
- `0x1400d6768`
- `0x1400d6c94`
- `0x140101b64`
- `0x140113d68`
- `0x14011cf98`
- `0x14011d420`
- `0x140134d20`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1400737b1`
- `ole32!CoTaskMemAlloc` at `0x1400737e3`
- `ole32!CoTaskMemAlloc` at `0x14007380b`
- `ole32!CoTaskMemAlloc` at `0x140073833`
- `ole32!CoTaskMemAlloc` at `0x14007385f`
- `ole32!CoTaskMemAlloc` at `0x14007388b`
- `ole32!CoTaskMemAlloc` at `0x1400738b7`
- `ole32!CoTaskMemAlloc` at `0x1400738e3`
- `ole32!CoTaskMemAlloc` at `0x1400737b1`
- `ole32!CoTaskMemAlloc` at `0x1400737e3`
- `ole32!CoTaskMemAlloc` at `0x14007380b`
- `ole32!CoTaskMemAlloc` at `0x140073833`
- `ole32!CoTaskMemAlloc` at `0x14007385f`
- `ole32!CoTaskMemAlloc` at `0x14007388b`
- `ole32!CoTaskMemAlloc` at `0x1400738b7`
- `ole32!CoTaskMemAlloc` at `0x1400738e3`
- `ole32!CoTaskMemFree` at `0x140073c60`
- `ole32!CoTaskMemFree` at `0x140073c60`
- `RPCRT4!UuidCreate` at `0x140073740`
- `RPCRT4!UuidCreate` at `0x140073740`

## string_xrefs

- `0x14007376b`: `base\stor\blb\engine\service\restorefiles.cpp`
- `0x140073a7f`: `base\stor\blb\engine\service\restorefiles.cpp`

## pseudocode

```c
__int64 __fastcall CBlbRestoreFilesAsync::PublishFileRestoreStopEvent(CBlbRestoreFilesAsync *this, int a2)
{
  unsigned int v4; // r12d
  void *v5; // r15
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned __int16 **v8; // rax
  int IsClientSKU; // ebx
  _DWORD *v10; // rax
  _DWORD *v11; // rax
  _DWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  void *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // r13
  __int64 v19; // rbx
  __int64 v20; // rdx
  int v21; // eax
  const OLECHAR *v22; // rax
  int v23; // esi
  unsigned int v24; // r14d
  unsigned __int8 v26[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h]
  void *v28; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h]
  UUID v31; // [rsp+78h] [rbp-88h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  int v35; // [rsp+98h] [rbp-68h]
  unsigned int v36; // [rsp+9Ch] [rbp-64h]
  unsigned __int16 **v37; // [rsp+A0h] [rbp-60h]
  _DWORD *v38; // [rsp+A8h] [rbp-58h]
  _DWORD *v39; // [rsp+B0h] [rbp-50h]
  _DWORD *v40; // [rsp+B8h] [rbp-48h]
  _QWORD *v41; // [rsp+C0h] [rbp-40h]
  _QWORD *v42; // [rsp+C8h] [rbp-38h]
  _QWORD *v43; // [rsp+D0h] [rbp-30h]
  _QWORD *v44; // [rsp+D8h] [rbp-28h]
  __int64 v45; // [rsp+E0h] [rbp-20h]
  int v46; // [rsp+E8h] [rbp-18h]
  int v47; // [rsp+ECh] [rbp-14h]
  int v48; // [rsp+F0h] [rbp-10h]
  const OLECHAR *v49; // [rsp+F8h] [rbp-8h]
  const OLECHAR *v50; // [rsp+100h] [rbp+0h]
  void *v51; // [rsp+108h] [rbp+8h]
  __int64 v52; // [rsp+110h] [rbp+10h]
  UUID Uuid; // [rsp+120h] [rbp+20h] BYREF

  memset_0(&v29, 0, 0xB8u);
  v4 = 0;
  v5 = 0;
  v28 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  Uuid = GUID_NULL;
  UuidCreate(&Uuid);
  v29 = *(_OWORD *)((char *)this + 252);
  if ( this == (CBlbRestoreFilesAsync *)-420LL )
    BlbAssert("base\\stor\\blb\\engine\\service\\restorefiles.cpp", 0x705u, "pTimeOfBackupSet");
  v6 = *((unsigned int *)this + 67);
  v30 = *(_QWORD *)((char *)this + 420);
  v33 = *((_DWORD *)this + 62);
  v7 = *((_QWORD *)this + 36);
  v36 = v6;
  v32 = v7;
  v31 = Uuid;
  v34 = a2;
  v35 = 0;
  v8 = (unsigned __int16 **)CoTaskMemAlloc(8 * v6);
  v37 = v8;
  if ( !v8 )
    goto LABEL_8;
  memset_0(v8, 0, 8LL * v36);
  v10 = CoTaskMemAlloc(4LL * v36);
  v38 = v10;
  if ( !v10 )
    goto LABEL_8;
  memset_0(v10, 0, 4LL * v36);
  v11 = CoTaskMemAlloc(4LL * v36);
  v39 = v11;
  if ( !v11 )
    goto LABEL_8;
  memset_0(v11, 0, 4LL * v36);
  v12 = CoTaskMemAlloc(4LL * v36);
  v40 = v12;
  if ( !v12 )
    goto LABEL_8;
  memset_0(v12, 0, 4LL * v36);
  v13 = CoTaskMemAlloc(8LL * v36);
  v41 = v13;
  if ( !v13 )
    goto LABEL_8;
  memset_0(v13, 0, 8LL * v36);
  v14 = CoTaskMemAlloc(8LL * v36);
  v42 = v14;
  if ( !v14 )
    goto LABEL_8;
  memset_0(v14, 0, 8LL * v36);
  v15 = CoTaskMemAlloc(8LL * v36);
  v43 = v15;
  if ( v15 && (memset_0(v15, 0, 8LL * v36), v16 = CoTaskMemAlloc(8LL * v36), (v44 = v16) != 0) )
  {
    v17 = 0;
    v27 = 0;
    v18 = 0;
    memset_0(v16, 0, 8LL * v36);
    while ( v4 < v36 )
    {
      IsClientSKU = BlbutilDuplicateString(
                      *(const unsigned __int16 **)(*((_QWORD *)this + 28) + 72LL * v4 + 48),
                      &v37[v4],
                      0);
      if ( IsClientSKU < 0 )
        goto LABEL_57;
      v19 = v27;
      v38[v4] = *(_DWORD *)(*((_QWORD *)this + 28) + 72LL * v4 + 4);
      v39[v4] = *(_DWORD *)(*((_QWORD *)this + 28) + 72LL * v4 + 8);
      v40[v4] = *(_DWORD *)(*((_QWORD *)this + 28) + 72LL * v4);
      v41[v4] = *(_QWORD *)(*((_QWORD *)this + 28) + 72LL * v4 + 40);
      v42[v4] = *(_QWORD *)(*((_QWORD *)this + 28) + 72LL * v4 + 24);
      v43[v4] = *(_QWORD *)(*((_QWORD *)this + 28) + 72LL * v4 + 32);
      v44[v4] = *(_QWORD *)(*((_QWORD *)this + 28) + 72LL * v4 + 16);
      v20 = *((_QWORD *)this + 28);
      v21 = v35;
      if ( *(int *)(v20 + 72LL * v4 + 8) < 0 )
        v21 = *(_DWORD *)(v20 + 72LL * v4 + 8);
      v35 = v21;
      v17 = *(_QWORD *)(v20 + 72LL * v4 + 32) + v19;
      v18 += *(_QWORD *)(v20 + 72LL * v4 + 40);
      v27 = v17;
      ++v4;
    }
    v22 = &String1;
    if ( *((_QWORD *)this + 26) )
      v22 = (const OLECHAR *)*((_QWORD *)this + 26);
    v49 = v22;
    if ( !*((_QWORD *)this + 27) || (v50 = (const OLECHAR *)*((_QWORD *)this + 27), v18 <= 0) )
      v50 = &String1;
    v45 = *((_QWORD *)this + 67);
    v46 = *((_DWORD *)this + 136);
    v47 = *((_DWORD *)this + 137);
    v48 = *((_DWORD *)this + 138);
    if ( !*((_QWORD *)this + 37) )
      BlbAssert("base\\stor\\blb\\engine\\service\\restorefiles.cpp", 0x783u, "m_wszTargetName != NULL");
    GetVolumeFriendlyNameForPublisher(*((_QWORD *)this + 37), *((unsigned int *)this + 76), &v28);
    v5 = v28;
    v52 = *((_QWORD *)this + 70);
    v51 = v28;
    if ( v18 || a2 < 0 )
    {
      if ( a2 == -2139619299 || a2 == -2139618969 )
      {
        PublishFileRestoreCanceledEvent((struct _BLB_FILE_RESTORE_STOP_EVENT_INFO *)&v29);
      }
      else if ( v17 <= 0 )
      {
        PublishFileRestoreGenericFailureEvent((struct _BLB_FILE_RESTORE_STOP_EVENT_INFO *)&v29);
      }
      else
      {
        PublishFileRestorePartialSuccessEvent((struct _BLB_FILE_RESTORE_STOP_EVENT_INFO *)&v29);
      }
    }
    else
    {
      PublishFileRestoreSuccessEvent((struct _BLB_FILE_RESTORE_STOP_EVENT_INFO *)&v29);
    }
    IsClientSKU = PublishFileRestoreStopEvent(
                    (struct _BLB_FILE_RESTORE_STOP_EVENT_INFO *)&v29,
                    &FILE_RESTORE_STOPPED_EVENT);
    if ( IsClientSKU >= 0 )
    {
      v23 = *((_DWORD *)this + 6);
      v24 = *((_DWORD *)this + 7);
      v26[0] = 0;
      IsClientSKU = BlbutilIsClientSKU(v26);
      if ( IsClientSKU >= 0 )
      {
        if ( v23 < 0 && !v26[0] )
        {
          if ( IsWERRequiredForError(v23) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
            }
            BlbGenerateErrorReport(*((unsigned int *)this + 76), 5, (unsigned int)v23, v24, 0, 0, 0, 0);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
          }
        }
        IsClientSKU = PublishRecoverySqmDatapoint(
                        (CBlbRestoreFilesAsync *)((char *)this + 568),
                        *((_DWORD *)this + 6),
                        *((_DWORD *)this + 7));
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
      }
    }
  }
  else
  {
LABEL_8:
    IsClientSKU = -2147024882;
  }
LABEL_57:
  FreeFileRestoreEventInfo(&v29);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  return (unsigned int)IsClientSKU;
}

```

## disassembly

```asm
0x1400736b0  mov     [rsp-8+arg_10], rbx
0x1400736b5  push    rbp
0x1400736b6  push    rsi
0x1400736b7  push    rdi
0x1400736b8  push    r12
0x1400736ba  push    r13
0x1400736bc  push    r14
0x1400736be  push    r15
0x1400736c0  lea     rbp, [rsp-40h]
0x1400736c5  sub     rsp, 140h
0x1400736cc  mov     rax, cs:__security_cookie
0x1400736d3  xor     rax, rsp
0x1400736d6  mov     [rbp+70h+var_40], rax
0x1400736da  mov     esi, edx
0x1400736dc  mov     rdi, rcx
0x1400736df  xor     edx, edx; Val
0x1400736e1  lea     rcx, [rsp+170h+var_110]; void *
0x1400736e6  mov     r8d, 0B8h; Size
0x1400736ec  call    memset_0
0x1400736f1  xor     r12d, r12d
0x1400736f4  mov     r15d, r12d
0x1400736f7  mov     [rsp+170h+var_120], r12
0x1400736fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140073703  lea     r14, WPP_GLOBAL_Control
0x14007370a  cmp     rcx, r14
0x14007370d  jz      short loc_140073730
0x14007370f  test    byte ptr [rcx+1Ch], 1
0x140073713  jz      short loc_140073730
0x140073715  cmp     byte ptr [rcx+19h], 4
0x140073719  jb      short loc_140073730
0x14007371b  mov     rcx, [rcx+10h]
0x14007371f  lea     edx, [r12+39h]
0x140073724  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x14007372b  call    WPP_SF_
0x140073730  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140073737  lea     rcx, [rbp+70h+Uuid]; Uuid
0x14007373b  movdqu  xmmword ptr [rbp+70h+Uuid.Data1], xmm0
0x140073740  call    cs:__imp_UuidCreate
0x140073746  movups  xmm0, xmmword ptr [rdi+0FCh]
0x14007374d  lea     rbx, [rdi+1A4h]
0x140073754  movdqu  [rsp+170h+var_110], xmm0
0x14007375a  test    rbx, rbx
0x14007375d  jnz     short loc_140073777
0x14007375f  lea     r8, aPtimeofbackups; "pTimeOfBackupSet"
0x140073766  mov     edx, 705h; unsigned int
0x14007376b  lea     rcx, aBaseStorBlbEng_38; "base\\stor\\blb\\engine\\service\\resto"...
0x140073772  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140073777  mov     rax, [rbx]
0x14007377a  mov     ecx, [rdi+10Ch]
0x140073780  movups  xmm0, xmmword ptr [rbp+70h+Uuid.Data1]
0x140073784  mov     [rsp+170h+var_100], rax
0x140073789  mov     eax, [rdi+0F8h]
0x14007378f  mov     [rbp+70h+var_E0], eax
0x140073792  mov     rax, [rdi+120h]
0x140073799  mov     [rbp+70h+var_D4], ecx
0x14007379c  shl     rcx, 3; cb
0x1400737a0  mov     [rbp+70h+var_E8], rax
0x1400737a4  movdqu  [rsp+170h+var_F8], xmm0
0x1400737aa  mov     [rbp+70h+var_DC], esi
0x1400737ad  mov     [rbp+70h+var_D8], r12d
0x1400737b1  call    cs:__imp_CoTaskMemAlloc
0x1400737b7  mov     [rbp+70h+var_D0], rax
0x1400737bb  test    rax, rax
0x1400737be  jnz     short loc_1400737CA
0x1400737c0  mov     ebx, 8007000Eh
0x1400737c5  jmp     loc_140073C4E
0x1400737ca  mov     r8d, [rbp+70h+var_D4]
0x1400737ce  xor     edx, edx; Val
0x1400737d0  shl     r8, 3; Size
0x1400737d4  mov     rcx, rax; void *
0x1400737d7  call    memset_0
0x1400737dc  mov     ecx, [rbp+70h+var_D4]
0x1400737df  shl     rcx, 2; cb
0x1400737e3  call    cs:__imp_CoTaskMemAlloc
0x1400737e9  mov     [rbp+70h+var_C8], rax
0x1400737ed  test    rax, rax
0x1400737f0  jz      short loc_1400737C0
0x1400737f2  mov     r8d, [rbp+70h+var_D4]
0x1400737f6  xor     edx, edx; Val
0x1400737f8  shl     r8, 2; Size
0x1400737fc  mov     rcx, rax; void *
0x1400737ff  call    memset_0
0x140073804  mov     ecx, [rbp+70h+var_D4]
0x140073807  shl     rcx, 2; cb
0x14007380b  call    cs:__imp_CoTaskMemAlloc
0x140073811  mov     [rbp+70h+var_C0], rax
0x140073815  test    rax, rax
0x140073818  jz      short loc_1400737C0
0x14007381a  mov     r8d, [rbp+70h+var_D4]
0x14007381e  xor     edx, edx; Val
0x140073820  shl     r8, 2; Size
0x140073824  mov     rcx, rax; void *
0x140073827  call    memset_0
0x14007382c  mov     ecx, [rbp+70h+var_D4]
0x14007382f  shl     rcx, 2; cb
0x140073833  call    cs:__imp_CoTaskMemAlloc
0x140073839  mov     [rbp+70h+var_B8], rax
0x14007383d  test    rax, rax
0x140073840  jz      loc_1400737C0
0x140073846  mov     r8d, [rbp+70h+var_D4]
0x14007384a  xor     edx, edx; Val
0x14007384c  shl     r8, 2; Size
0x140073850  mov     rcx, rax; void *
0x140073853  call    memset_0
0x140073858  mov     ecx, [rbp+70h+var_D4]
0x14007385b  shl     rcx, 3; cb
0x14007385f  call    cs:__imp_CoTaskMemAlloc
0x140073865  mov     [rbp+70h+var_B0], rax
0x140073869  test    rax, rax
0x14007386c  jz      loc_1400737C0
0x140073872  mov     r8d, [rbp+70h+var_D4]
0x140073876  xor     edx, edx; Val
0x140073878  shl     r8, 3; Size
0x14007387c  mov     rcx, rax; void *
0x14007387f  call    memset_0
0x140073884  mov     ecx, [rbp+70h+var_D4]
0x140073887  shl     rcx, 3; cb
0x14007388b  call    cs:__imp_CoTaskMemAlloc
0x140073891  mov     [rbp+70h+var_A8], rax
0x140073895  test    rax, rax
0x140073898  jz      loc_1400737C0
0x14007389e  mov     r8d, [rbp+70h+var_D4]
0x1400738a2  xor     edx, edx; Val
0x1400738a4  shl     r8, 3; Size
0x1400738a8  mov     rcx, rax; void *
0x1400738ab  call    memset_0
0x1400738b0  mov     ecx, [rbp+70h+var_D4]
0x1400738b3  shl     rcx, 3; cb
0x1400738b7  call    cs:__imp_CoTaskMemAlloc
0x1400738bd  mov     [rbp+70h+var_A0], rax
0x1400738c1  test    rax, rax
0x1400738c4  jz      loc_1400737C0
0x1400738ca  mov     r8d, [rbp+70h+var_D4]
0x1400738ce  xor     edx, edx; Val
0x1400738d0  shl     r8, 3; Size
0x1400738d4  mov     rcx, rax; void *
0x1400738d7  call    memset_0
0x1400738dc  mov     ecx, [rbp+70h+var_D4]
0x1400738df  shl     rcx, 3; cb
0x1400738e3  call    cs:__imp_CoTaskMemAlloc
0x1400738e9  mov     [rbp+70h+var_98], rax
0x1400738ed  test    rax, rax
0x1400738f0  jz      loc_1400737C0
0x1400738f6  mov     r8d, [rbp+70h+var_D4]
0x1400738fa  mov     rbx, r12
0x1400738fd  shl     r8, 3; Size
0x140073901  xor     edx, edx; Val
0x140073903  mov     rcx, rax; void *
0x140073906  mov     [rsp+170h+var_128], rbx
0x14007390b  mov     r13, r12
0x14007390e  call    memset_0
0x140073913  cmp     r12d, [rbp+70h+var_D4]
0x140073917  jnb     loc_140073A0C
0x14007391d  mov     rax, [rbp+70h+var_D0]
0x140073921  xor     r8d, r8d; unsigned __int64
0x140073924  mov     rcx, [rdi+0E0h]
0x14007392b  mov     r14d, r12d
0x14007392e  lea     r9, [r14+r14*8]
0x140073932  mov     rcx, [rcx+r9*8+30h]; unsigned __int16 *
0x140073937  lea     rdx, [rax+r14*8]; unsigned __int16 **
0x14007393b  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140073940  mov     ebx, eax
0x140073942  test    eax, eax
0x140073944  js      loc_140073C47
0x14007394a  mov     rax, [rdi+0E0h]
0x140073951  lea     r8, [r14+r14*8]
0x140073955  mov     rbx, [rsp+170h+var_128]
0x14007395a  mov     ecx, [rax+r8*8+4]
0x14007395f  mov     rax, [rbp+70h+var_C8]
0x140073963  mov     [rax+r14*4], ecx
0x140073967  mov     rax, [rdi+0E0h]
0x14007396e  mov     ecx, [rax+r8*8+8]
0x140073973  mov     rax, [rbp+70h+var_C0]
0x140073977  mov     [rax+r14*4], ecx
0x14007397b  mov     rax, [rdi+0E0h]
0x140073982  mov     ecx, [rax+r8*8]
0x140073986  mov     rax, [rbp+70h+var_B8]
0x14007398a  mov     [rax+r14*4], ecx
0x14007398e  mov     rax, [rdi+0E0h]
0x140073995  mov     rcx, [rax+r8*8+28h]
0x14007399a  mov     rax, [rbp+70h+var_B0]
0x14007399e  mov     [rax+r14*8], rcx
0x1400739a2  mov     rax, [rdi+0E0h]
0x1400739a9  mov     rcx, [rax+r8*8+18h]
0x1400739ae  mov     rax, [rbp+70h+var_A8]
0x1400739b2  mov     [rax+r14*8], rcx
0x1400739b6  mov     rax, [rdi+0E0h]
0x1400739bd  mov     rcx, [rax+r8*8+20h]
0x1400739c2  mov     rax, [rbp+70h+var_A0]
0x1400739c6  mov     [rax+r14*8], rcx
0x1400739ca  mov     rax, [rdi+0E0h]
0x1400739d1  mov     rcx, [rax+r8*8+10h]
0x1400739d6  mov     rax, [rbp+70h+var_98]
0x1400739da  mov     [rax+r14*8], rcx
0x1400739de  mov     rdx, [rdi+0E0h]
0x1400739e5  mov     eax, [rbp+70h+var_D8]
0x1400739e8  mov     ecx, [rdx+r8*8+8]
0x1400739ed  test    ecx, ecx
0x1400739ef  cmovs   eax, ecx
0x1400739f2  mov     [rbp+70h+var_D8], eax
0x1400739f5  add     rbx, [rdx+r8*8+20h]
0x1400739fa  add     r13, [rdx+r8*8+28h]
0x1400739ff  mov     [rsp+170h+var_128], rbx
0x140073a04  inc     r12d
0x140073a07  jmp     loc_140073913
0x140073a0c  mov     rcx, [rdi+0D0h]
0x140073a13  lea     rdx, String1
0x140073a1a  xor     r12d, r12d
0x140073a1d  mov     rax, rdx
0x140073a20  test    rcx, rcx
0x140073a23  cmovnz  rax, rcx
0x140073a27  mov     [rbp+70h+var_78], rax
0x140073a2b  mov     rax, [rdi+0D8h]
0x140073a32  test    rax, rax
0x140073a35  jz      short loc_140073A40
0x140073a37  mov     [rbp+70h+var_70], rax
0x140073a3b  test    r13, r13
0x140073a3e  jg      short loc_140073A44
0x140073a40  mov     [rbp+70h+var_70], rdx
0x140073a44  mov     rax, [rdi+218h]
0x140073a4b  mov     [rbp+70h+var_90], rax
0x140073a4f  mov     eax, [rdi+220h]
0x140073a55  mov     [rbp+70h+var_88], eax
0x140073a58  mov     eax, [rdi+224h]
0x140073a5e  mov     [rbp+70h+var_84], eax
0x140073a61  mov     eax, [rdi+228h]
0x140073a67  mov     [rbp+70h+var_80], eax
0x140073a6a  cmp     [rdi+128h], r12
0x140073a71  jnz     short loc_140073A8B
0x140073a73  lea     r8, aMWsztargetname_0; "m_wszTargetName != NULL"
0x140073a7a  mov     edx, 783h; unsigned int
0x140073a7f  lea     rcx, aBaseStorBlbEng_38; "base\\stor\\blb\\engine\\service\\resto"...
0x140073a86  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140073a8b  mov     edx, [rdi+130h]
0x140073a91  lea     r8, [rsp+170h+var_120]
0x140073a96  mov     rcx, [rdi+128h]
0x140073a9d  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAGW4_BLB_MEDIA_TYPE@@AEAPEAG@Z; GetVolumeFriendlyNameForPublisher(ushort *,_BLB_MEDIA_TYPE,ushort * &)
0x140073aa2  mov     rax, [rdi+230h]
0x140073aa9  mov     r15, [rsp+170h+var_120]
0x140073aae  mov     [rbp+70h+var_60], rax
0x140073ab2  mov     [rbp+70h+var_68], r15
0x140073ab6  test    r13, r13
0x140073ab9  jnz     short loc_140073ACB
0x140073abb  test    esi, esi
0x140073abd  js      short loc_140073ACB
0x140073abf  lea     rcx, [rsp+170h+var_110]; struct _BLB_FILE_RESTORE_STOP_EVENT_INFO *
0x140073ac4  call    ?PublishFileRestoreSuccessEvent@@YAJPEAU_BLB_FILE_RESTORE_STOP_EVENT_INFO@@@Z; PublishFileRestoreSuccessEvent(_BLB_FILE_RESTORE_STOP_EVENT_INFO *)
0x140073ac9  jmp     short loc_140073AFD
0x140073acb  cmp     esi, 8078001Dh
0x140073ad1  jz      short loc_140073AF3
0x140073ad3  cmp     esi, 80780167h
0x140073ad9  jz      short loc_140073AF3
0x140073adb  lea     rcx, [rsp+170h+var_110]; struct _BLB_FILE_RESTORE_STOP_EVENT_INFO *
0x140073ae0  test    rbx, rbx
0x140073ae3  jle     short loc_140073AEC
0x140073ae5  call    ?PublishFileRestorePartialSuccessEvent@@YAJPEAU_BLB_FILE_RESTORE_STOP_EVENT_INFO@@@Z; PublishFileRestorePartialSuccessEvent(_BLB_FILE_RESTORE_STOP_EVENT_INFO *)
0x140073aea  jmp     short loc_140073AFD
0x140073aec  call    ?PublishFileRestoreGenericFailureEvent@@YAJPEAU_BLB_FILE_RESTORE_STOP_EVENT_INFO@@@Z; PublishFileRestoreGenericFailureEvent(_BLB_FILE_RESTORE_STOP_EVENT_INFO *)
0x140073af1  jmp     short loc_140073AFD
0x140073af3  lea     rcx, [rsp+170h+var_110]; struct _BLB_FILE_RESTORE_STOP_EVENT_INFO *
0x140073af8  call    ?PublishFileRestoreCanceledEvent@@YAJPEAU_BLB_FILE_RESTORE_STOP_EVENT_INFO@@@Z; PublishFileRestoreCanceledEvent(_BLB_FILE_RESTORE_STOP_EVENT_INFO *)
0x140073afd  lea     rdx, FILE_RESTORE_STOPPED_EVENT; struct _EVENT_DESCRIPTOR *
0x140073b04  lea     rcx, [rsp+170h+var_110]; struct _BLB_FILE_RESTORE_STOP_EVENT_INFO *
0x140073b09  call    ?PublishFileRestoreStopEvent@@YAJPEAU_BLB_FILE_RESTORE_STOP_EVENT_INFO@@PEBU_EVENT_DESCRIPTOR@@@Z; PublishFileRestoreStopEvent(_BLB_FILE_RESTORE_STOP_EVENT_INFO *,_EVENT_DESCRIPTOR const *)
0x140073b0e  mov     ebx, eax
0x140073b10  test    eax, eax
0x140073b12  js      loc_140073C47
0x140073b18  mov     esi, [rdi+18h]
0x140073b1b  lea     rcx, [rsp+170h+var_130]; unsigned __int8 *
0x140073b20  mov     r14d, [rdi+1Ch]
0x140073b24  mov     [rsp+170h+var_130], r12b
0x140073b29  call    ?BlbutilIsClientSKU@@YAJPEAE@Z; BlbutilIsClientSKU(uchar *)
0x140073b2e  mov     ebx, eax
0x140073b30  test    eax, eax
0x140073b32  jns     short loc_140073B7C
0x140073b34  mov     rcx, cs:WPP_GLOBAL_Control
0x140073b3b  lea     r14, WPP_GLOBAL_Control
0x140073b42  cmp     rcx, r14
0x140073b45  jz      loc_140073C4E
0x140073b4b  test    byte ptr [rcx+1Ch], 1
0x140073b4f  jz      loc_140073C4E
0x140073b55  cmp     byte ptr [rcx+19h], 2
0x140073b59  jb      loc_140073C4E
0x140073b5f  mov     rcx, [rcx+10h]
0x140073b63  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140073b6a  mov     edx, 3Ah ; ':'
0x140073b6f  mov     r9d, eax
0x140073b72  call    WPP_SF_d
0x140073b77  jmp     loc_140073C4E
0x140073b7c  test    esi, esi
0x140073b7e  jns     short loc_140073BF0
0x140073b80  cmp     [rsp+170h+var_130], r12b
0x140073b85  jnz     short loc_140073BF0
0x140073b87  mov     ecx, esi; int
0x140073b89  call    ?IsWERRequiredForError@@YAEJ@Z; IsWERRequiredForError(long)
0x140073b8e  test    al, al
0x140073b90  jz      short loc_140073C0E
0x140073b92  mov     rcx, cs:WPP_GLOBAL_Control
0x140073b99  lea     rax, WPP_GLOBAL_Control
0x140073ba0  cmp     rcx, rax
  ... truncated ...
```
