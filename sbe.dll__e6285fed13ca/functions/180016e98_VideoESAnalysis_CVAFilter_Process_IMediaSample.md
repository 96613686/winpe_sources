# VideoESAnalysis::CVAFilter::Process(IMediaSample *)

- ea: `0x180016e98`
- end: `0x180017228`
- name: `?Process@CVAFilter@VideoESAnalysis@@QEAAJPEAUIMediaSample@@@Z`
- size: `912`
- prototype: `__int64 __fastcall(VideoESAnalysis::CVAFilter *__hidden this, struct IMediaSample *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800175a0`

## callees

- `0x180001c00`
- `0x18000256c`
- `0x180006944`
- `0x180006964`
- `0x180006af8`
- `0x180006c44`
- `0x1800146d8`
- `0x180016e98`
- `0x180017300`
- `0x18001863c`
- `0x1800188ac`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001716e`
- `KERNEL32!LeaveCriticalSection` at `0x1800171f6`
- `KERNEL32!LeaveCriticalSection` at `0x18001716e`
- `KERNEL32!LeaveCriticalSection` at `0x1800171f6`
- `KERNEL32!EnterCriticalSection` at `0x180016ed8`
- `KERNEL32!EnterCriticalSection` at `0x18001707b`
- `KERNEL32!EnterCriticalSection` at `0x180016ed8`
- `KERNEL32!EnterCriticalSection` at `0x18001707b`
- `ole32!CoTaskMemFree` at `0x1800171ab`
- `ole32!CoTaskMemFree` at `0x1800171ab`

## pseudocode

```c
__int64 __fastcall VideoESAnalysis::CVAFilter::Process(VideoESAnalysis::CVAFilter *this, struct IMediaSample *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r12
  struct IMediaSampleVtbl *lpVtbl; // rax
  int v6; // edi
  int *v7; // r8
  int OutputMediaTypesFromInputType; // esi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  bool v13; // [rsp+30h] [rbp-D0h] BYREF
  bool v14; // [rsp+31h] [rbp-CFh] BYREF
  _OWORD v15[3]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+68h] [rbp-98h]
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  __int64 v18; // [rsp+78h] [rbp-88h] BYREF
  struct _AMMediaType v19; // [rsp+80h] [rbp-80h] BYREF
  struct _AMMediaType v20; // [rsp+E0h] [rbp-20h] BYREF
  struct _AMMediaType v21; // [rsp+140h] [rbp+40h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 584);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 584));
  if ( *((_DWORD *)this + 10) )
  {
    if ( *((_QWORD *)this + 16) )
    {
      lpVtbl = a2->lpVtbl;
      pv = 0;
      v6 = 0;
      if ( ((unsigned int (__fastcall *)(struct IMediaSample *, LPVOID *))lpVtbl->GetMediaType)(a2, &pv) || !pv )
        goto LABEL_28;
      CMediaType::CMediaType((CMediaType *)&v19, (const struct CMediaType *)pv, v7);
      if ( (unsigned int)CMediaType::operator==(&v19, (char *)this + 4184) )
      {
        OutputMediaTypesFromInputType = 0;
      }
      else
      {
        v15[0] = v19.majortype;
        v6 = 1;
        v16 = 0;
        v15[1] = v19.subtype;
        v15[2] = v19.formattype;
        SBEPerf::CTeHomeETWEvent<EH_COMPLETE_CONNECT_EVENT>::TraceEvent((char *)this + 2056, v15);
        v13 = 0;
        v14 = 0;
        memset_0(&v21, 0, sizeof(v21));
        v21.lSampleSize = 1;
        v21.bFixedSizeSamples = 1;
        memset_0(&v20, 0, sizeof(v20));
        v20.lSampleSize = 1;
        v20.bFixedSizeSamples = 1;
        OutputMediaTypesFromInputType = VideoESAnalysis::CVAFilter::GetOutputMediaTypesFromInputType(
                                          this,
                                          (const struct CMediaType *)&v19,
                                          (struct CMediaType *)&v21,
                                          (struct CMediaType *)&v20,
                                          &v14,
                                          &v13);
        if ( OutputMediaTypesFromInputType >= 0 )
        {
          OutputMediaTypesFromInputType = VideoESAnalysis::CVESQueue::SetCurrentParser(
                                            (char *)this + 144,
                                            v13,
                                            *((_QWORD *)this + 16));
          if ( OutputMediaTypesFromInputType >= 0 )
          {
            (*(void (__fastcall **)(_QWORD, struct _AMMediaType *))(**((_QWORD **)this + 67) + 96LL))(
              *((_QWORD *)this + 67),
              &v19);
            v9 = *((_QWORD *)this + 15);
            if ( v9 )
              (*(void (__fastcall **)(__int64, struct _AMMediaType *))(*(_QWORD *)v9 + 72LL))(v9, &v19);
            v10 = *((_QWORD *)this + 16);
            if ( v10 )
              (*(void (__fastcall **)(__int64, struct _AMMediaType *))(*(_QWORD *)v10 + 72LL))(v10, &v21);
          }
          *((_BYTE *)this + 1552) = 1;
          if ( OutputMediaTypesFromInputType >= 0 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 4144));
            *((_BYTE *)this + 4448) = 1;
            CMediaType::Set((struct _AMMediaType *)((char *)this + 4272), &v21);
            CMediaType::Set((struct _AMMediaType *)((char *)this + 4184), &v19);
            if ( !(unsigned int)CMediaType::operator==(&v20, (char *)this + 4360) )
            {
              CMediaType::Set((struct _AMMediaType *)((char *)this + 4360), &v20);
              v11 = *((_QWORD *)this + 17);
              *(_WORD *)((char *)this + 4449) = 1;
              if ( v11 )
              {
                v18 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v11 + 24) + 48LL))(v11 + 24, &v18) >= 0
                  && v18 )
                {
                  if ( (*(unsigned int (__fastcall **)(__int64, struct _AMMediaType *))(*(_QWORD *)v18 + 88LL))(
                         v18,
                         &v20) )
                  {
                    *((_BYTE *)this + 4450) = 1;
                  }
                  else
                  {
                    (*(void (__fastcall **)(_QWORD, struct _AMMediaType *))(**((_QWORD **)this + 17) + 72LL))(
                      *((_QWORD *)this + 17),
                      &v20);
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                }
                else
                {
                  *((_BYTE *)this + 4450) = 1;
                }
                *((_BYTE *)this + 1552) = 1;
              }
              else
              {
                *((_BYTE *)this + 4450) = 1;
              }
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 4144));
          }
        }
        FreeMediaType(&v20);
        FreeMediaType(&v21);
      }
      ((void (__fastcall *)(struct IMediaSample *, char *))a2->lpVtbl->SetMediaType)(a2, (char *)this + 4272);
      FreeMediaType((struct _AMMediaType *)pv);
      CoTaskMemFree(pv);
      FreeMediaType(&v19);
      if ( OutputMediaTypesFromInputType >= 0 )
LABEL_28:
        OutputMediaTypesFromInputType = VideoESAnalysis::CVESQueue::QueueSample(
                                          (VideoESAnalysis::CVAFilter *)((char *)this + 144),
                                          a2,
                                          v6,
                                          *((struct VideoESAnalysis::CVAOutput **)this + 16),
                                          (VideoESAnalysis::CVAFilter *)((char *)this + 1384));
    }
    else
    {
      OutputMediaTypesFromInputType = 1;
    }
  }
  else
  {
    OutputMediaTypesFromInputType = -2147220953;
  }
  LeaveCriticalSection(v2);
  return (unsigned int)OutputMediaTypesFromInputType;
}

```

## disassembly

```asm
0x180016e98  mov     [rsp-8+arg_10], rbx
0x180016e9d  push    rbp
0x180016e9e  push    rsi
0x180016e9f  push    rdi
0x180016ea0  push    r12
0x180016ea2  push    r13
0x180016ea4  push    r14
0x180016ea6  push    r15
0x180016ea8  lea     rbp, [rsp-0B0h]
0x180016eb0  sub     rsp, 1B0h
0x180016eb7  mov     rax, cs:__security_cookie
0x180016ebe  xor     rax, rsp
0x180016ec1  mov     [rbp+0E0h+var_40], rax
0x180016ec8  lea     r12, [rcx+248h]
0x180016ecf  mov     rbx, rcx
0x180016ed2  mov     rcx, r12; lpCriticalSection
0x180016ed5  mov     r14, rdx
0x180016ed8  call    cs:__imp_EnterCriticalSection
0x180016ede  xor     r13d, r13d
0x180016ee1  cmp     [rbx+28h], r13d
0x180016ee5  jz      loc_1800171EE
0x180016eeb  cmp     [rbx+80h], r13
0x180016ef2  jz      loc_1800171E7
0x180016ef8  mov     rax, [r14]
0x180016efb  lea     rdx, [rsp+1E0h+pv]
0x180016f00  mov     rcx, r14
0x180016f03  mov     [rsp+1E0h+pv], r13
0x180016f08  mov     edi, r13d
0x180016f0b  mov     rax, [rax+68h]
0x180016f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f14  test    eax, eax
0x180016f16  jnz     loc_1800171BE
0x180016f1c  mov     rdx, [rsp+1E0h+pv]; struct CMediaType *
0x180016f21  test    rdx, rdx
0x180016f24  jz      loc_1800171BE
0x180016f2a  lea     rcx, [rbp+0E0h+var_160]; this
0x180016f2e  call    ??0CMediaType@@QEAA@AEBV0@PEAJ@Z; CMediaType::CMediaType(CMediaType const &,long *)
0x180016f33  lea     r15, [rbx+1058h]
0x180016f3a  mov     rdx, r15
0x180016f3d  lea     rcx, [rbp+0E0h+var_160]
0x180016f41  call    ??8CMediaType@@QEBAHAEBV0@@Z; CMediaType::operator==(CMediaType const &)
0x180016f46  test    eax, eax
0x180016f48  jz      short loc_180016F52
0x180016f4a  mov     esi, r13d
0x180016f4d  jmp     loc_180017186
0x180016f52  movaps  xmm0, xmmword ptr [rbp+0E0h+var_160.majortype.Data1]
0x180016f56  lea     rcx, [rbx+808h]
0x180016f5d  movaps  xmm1, xmmword ptr [rbp+0E0h+var_160.subtype.Data1]
0x180016f61  lea     rdx, [rsp+1E0h+var_1A8]
0x180016f66  movdqu  [rsp+1E0h+var_1A8], xmm0
0x180016f6c  mov     edi, 1
0x180016f71  mov     [rsp+1E0h+var_178], r13
0x180016f76  movups  xmm0, xmmword ptr [rbp+0E0h+var_160.formattype.Data1]
0x180016f7a  movdqu  [rsp+1E0h+var_198], xmm1
0x180016f80  movdqu  [rsp+1E0h+var_188], xmm0
0x180016f86  call    ?TraceEvent@?$CTeHomeETWEvent@UEH_COMPLETE_CONNECT_EVENT@@@SBEPerf@@QEAAXPEAUEH_COMPLETE_CONNECT_EVENT@@@Z; SBEPerf::CTeHomeETWEvent<EH_COMPLETE_CONNECT_EVENT>::TraceEvent(EH_COMPLETE_CONNECT_EVENT *)
0x180016f8b  lea     esi, [rdi+57h]
0x180016f8e  mov     [rsp+1E0h+var_1B0], r13b
0x180016f93  mov     r8d, esi; Size
0x180016f96  mov     [rsp+1E0h+var_1AF], r13b
0x180016f9b  xor     edx, edx; Val
0x180016f9d  lea     rcx, [rbp+0E0h+var_A0]; void *
0x180016fa1  call    memset_0
0x180016fa6  mov     r8d, esi; Size
0x180016fa9  mov     [rbp+0E0h+var_A0.lSampleSize], edi
0x180016fac  xor     edx, edx; Val
0x180016fae  mov     [rbp+0E0h+var_A0.bFixedSizeSamples], edi
0x180016fb1  lea     rcx, [rbp+0E0h+var_100]; void *
0x180016fb5  call    memset_0
0x180016fba  lea     rax, [rsp+1E0h+var_1B0]
0x180016fbf  mov     [rbp+0E0h+var_100.lSampleSize], edi
0x180016fc2  mov     [rsp+1E0h+var_1B8], rax; bool *
0x180016fc7  lea     r9, [rbp+0E0h+var_100]; struct CMediaType *
0x180016fcb  lea     rax, [rsp+1E0h+var_1AF]
0x180016fd0  mov     [rbp+0E0h+var_100.bFixedSizeSamples], edi
0x180016fd3  lea     r8, [rbp+0E0h+var_A0]; struct CMediaType *
0x180016fd7  mov     [rsp+1E0h+var_1C0], rax; bool *
0x180016fdc  lea     rdx, [rbp+0E0h+var_160]; struct CMediaType *
0x180016fe0  mov     rcx, rbx; this
0x180016fe3  call    ?GetOutputMediaTypesFromInputType@CVAFilter@VideoESAnalysis@@AEAAJAEBVCMediaType@@AEAV3@1AEA_N2@Z; VideoESAnalysis::CVAFilter::GetOutputMediaTypesFromInputType(CMediaType const &,CMediaType &,CMediaType &,bool &,bool &)
0x180016fe8  mov     esi, eax
0x180016fea  test    eax, eax
0x180016fec  js      loc_180017174
0x180016ff2  cmp     [rsp+1E0h+var_1B0], r13b
0x180016ff7  lea     rcx, [rbx+90h]
0x180016ffe  mov     r8, [rbx+80h]
0x180017005  mov     edx, r13d
0x180017008  setnz   dl
0x18001700b  call    ?SetCurrentParser@CVESQueue@VideoESAnalysis@@QEAAJW4_PARSING_MODE@2@PEAVCVAOutput@2@@Z; VideoESAnalysis::CVESQueue::SetCurrentParser(VideoESAnalysis::_PARSING_MODE,VideoESAnalysis::CVAOutput *)
0x180017010  mov     esi, eax
0x180017012  test    eax, eax
0x180017014  js      short loc_180017062
0x180017016  mov     rcx, [rbx+218h]
0x18001701d  lea     rdx, [rbp+0E0h+var_160]
0x180017021  mov     rax, [rcx]
0x180017024  mov     rax, [rax+60h]
0x180017028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001702d  mov     rcx, [rbx+78h]
0x180017031  test    rcx, rcx
0x180017034  jz      short loc_180017046
0x180017036  mov     rax, [rcx]
0x180017039  lea     rdx, [rbp+0E0h+var_160]
0x18001703d  mov     rax, [rax+48h]
0x180017041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017046  mov     rcx, [rbx+80h]
0x18001704d  test    rcx, rcx
0x180017050  jz      short loc_180017062
0x180017052  mov     rax, [rcx]
0x180017055  lea     rdx, [rbp+0E0h+var_A0]
0x180017059  mov     rax, [rax+48h]
0x18001705d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017062  mov     [rbx+610h], dil
0x180017069  test    esi, esi
0x18001706b  js      loc_180017174
0x180017071  lea     r13, [rbx+1030h]
0x180017078  mov     rcx, r13; lpCriticalSection
0x18001707b  call    cs:__imp_EnterCriticalSection
0x180017081  lea     rcx, [rbx+10B0h]; this
0x180017088  mov     [rbx+1160h], dil
0x18001708f  lea     rdx, [rbp+0E0h+var_A0]; struct _AMMediaType *
0x180017093  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x180017098  lea     rdx, [rbp+0E0h+var_160]; struct _AMMediaType *
0x18001709c  mov     rcx, r15; this
0x18001709f  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x1800170a4  lea     r15, [rbx+1108h]
0x1800170ab  mov     rdx, r15
0x1800170ae  lea     rcx, [rbp+0E0h+var_100]
0x1800170b2  call    ??8CMediaType@@QEBAHAEBV0@@Z; CMediaType::operator==(CMediaType const &)
0x1800170b7  test    eax, eax
0x1800170b9  jnz     loc_18001716B
0x1800170bf  lea     rdx, [rbp+0E0h+var_100]; struct _AMMediaType *
0x1800170c3  mov     rcx, r15; this
0x1800170c6  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x1800170cb  mov     rcx, [rbx+88h]
0x1800170d2  mov     [rbx+1161h], di
0x1800170d9  test    rcx, rcx
0x1800170dc  jnz     short loc_1800170EA
0x1800170de  mov     [rbx+1162h], dil
0x1800170e5  jmp     loc_18001716B
0x1800170ea  add     rcx, 18h
0x1800170ee  mov     [rsp+1E0h+var_168], 0
0x1800170f7  lea     rdx, [rsp+1E0h+var_168]
0x1800170fc  mov     rax, [rcx]
0x1800170ff  mov     rax, [rax+30h]
0x180017103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017108  test    eax, eax
0x18001710a  js      short loc_18001715D
0x18001710c  mov     rcx, [rsp+1E0h+var_168]
0x180017111  test    rcx, rcx
0x180017114  jz      short loc_18001715D
0x180017116  mov     rax, [rcx]
0x180017119  lea     rdx, [rbp+0E0h+var_100]
0x18001711d  mov     rax, [rax+58h]
0x180017121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017126  test    eax, eax
0x180017128  jz      short loc_180017133
0x18001712a  mov     [rbx+1162h], dil
0x180017131  jmp     short loc_18001714A
0x180017133  mov     rcx, [rbx+88h]
0x18001713a  lea     rdx, [rbp+0E0h+var_100]
0x18001713e  mov     rax, [rcx]
0x180017141  mov     rax, [rax+48h]
0x180017145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001714a  mov     rcx, [rsp+1E0h+var_168]
0x18001714f  mov     rax, [rcx]
0x180017152  mov     rax, [rax+10h]
0x180017156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001715b  jmp     short loc_180017164
0x18001715d  mov     [rbx+1162h], dil
0x180017164  mov     [rbx+610h], dil
0x18001716b  mov     rcx, r13; lpCriticalSection
0x18001716e  call    cs:__imp_LeaveCriticalSection
0x180017174  lea     rcx, [rbp+0E0h+var_100]; struct _AMMediaType *
0x180017178  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18001717d  lea     rcx, [rbp+0E0h+var_A0]; struct _AMMediaType *
0x180017181  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180017186  mov     rax, [r14]
0x180017189  lea     rdx, [rbx+10B0h]
0x180017190  mov     rcx, r14
0x180017193  mov     rax, [rax+70h]
0x180017197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001719c  mov     rcx, [rsp+1E0h+pv]; struct _AMMediaType *
0x1800171a1  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800171a6  mov     rcx, [rsp+1E0h+pv]; pv
0x1800171ab  call    cs:__imp_CoTaskMemFree
0x1800171b1  lea     rcx, [rbp+0E0h+var_160]; struct _AMMediaType *
0x1800171b5  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800171ba  test    esi, esi
0x1800171bc  js      short loc_1800171F3
0x1800171be  mov     r9, [rbx+80h]; struct VideoESAnalysis::CVAOutput *
0x1800171c5  lea     rax, [rbx+568h]
0x1800171cc  lea     rcx, [rbx+90h]; this
0x1800171d3  mov     [rsp+1E0h+var_1C0], rax; struct VideoESAnalysis::CVACCContainer *
0x1800171d8  mov     r8d, edi; int
0x1800171db  mov     rdx, r14; struct IMediaSample *
0x1800171de  call    ?QueueSample@CVESQueue@VideoESAnalysis@@QEAAJPEAUIMediaSample@@HPEAVCVAOutput@2@PEAVCVACCContainer@2@@Z; VideoESAnalysis::CVESQueue::QueueSample(IMediaSample *,int,VideoESAnalysis::CVAOutput *,VideoESAnalysis::CVACCContainer *)
0x1800171e3  mov     esi, eax
0x1800171e5  jmp     short loc_1800171F3
0x1800171e7  mov     esi, 1
0x1800171ec  jmp     short loc_1800171F3
0x1800171ee  mov     esi, 80040227h
0x1800171f3  mov     rcx, r12; lpCriticalSection
0x1800171f6  call    cs:__imp_LeaveCriticalSection
0x1800171fc  mov     eax, esi
0x1800171fe  mov     rcx, [rbp+0E0h+var_40]
0x180017205  xor     rcx, rsp; StackCookie
0x180017208  call    __security_check_cookie
0x18001720d  mov     rbx, [rsp+1E0h+arg_10]
0x180017215  add     rsp, 1B0h
0x18001721c  pop     r15
0x18001721e  pop     r14
0x180017220  pop     r13
0x180017222  pop     r12
0x180017224  pop     rdi
0x180017225  pop     rsi
0x180017226  pop     rbp
0x180017227  retn
```
