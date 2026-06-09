# MpObHipsCallback

- ea: `0x140043520`
- end: `0x140043ecb`
- name: `MpObHipsCallback`
- size: `2475`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14002f510`

## callees

- `0x140004530`
- `0x1400049dc`
- `0x140005a70`
- `0x14000a970`
- `0x14000ddc8`
- `0x14000e0f4`
- `0x14000e2c8`
- `0x14000e40c`
- `0x14000e5f0`
- `0x1400434e8`
- `0x140043520`
- `0x140044130`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140043d28`
- `ntoskrnl!PsGetProcessId` at `0x140043d56`
- `ntoskrnl!PsGetProcessId` at `0x140043d28`
- `ntoskrnl!PsGetProcessId` at `0x140043d56`
- `ntoskrnl!IoGetCurrentProcess` at `0x140043b78`
- `ntoskrnl!IoGetCurrentProcess` at `0x140043b78`

## pseudocode

```c
char __fastcall MpObHipsCallback(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        unsigned __int8 *a7,
        unsigned __int8 *a8)
{
  int v8; // r11d
  __int64 v10; // rdi
  __int64 CurrentProcess; // rax
  unsigned __int8 v12; // r13
  unsigned __int8 v13; // r14
  const wchar_t *v14; // rcx
  struct _DEVICE_OBJECT *v15; // r9
  int v16; // edx
  int v17; // edi
  int v18; // r8d
  bool v19; // al
  char v20; // cl
  unsigned __int8 v21; // dl
  unsigned __int32 v22; // r10d
  __int64 v23; // rdx
  __int64 v24; // r8
  bool v25; // r9
  __int64 v26; // rdx
  unsigned __int8 v27; // r8
  unsigned __int64 v28; // rcx
  int v29; // r8d
  const wchar_t *v30; // rax
  char v31; // dl
  int v32; // r8d
  int v33; // r8d
  int v34; // edi
  char Value; // al
  __int64 v36; // rdx
  __int64 v37; // r8
  int v38; // r9d
  char v39; // r10
  int v40; // r11d
  int v42; // [rsp+20h] [rbp-B8h]
  char v43; // [rsp+50h] [rbp-88h]
  unsigned __int8 v44; // [rsp+70h] [rbp-68h]
  unsigned __int8 IsOfficeApplication; // [rsp+71h] [rbp-67h]
  char v46; // [rsp+74h] [rbp-64h]
  __int64 v47; // [rsp+78h] [rbp-60h]
  char v48; // [rsp+78h] [rbp-60h]
  __int64 v49; // [rsp+80h] [rbp-58h]
  char v51; // [rsp+E8h] [rbp+10h]
  bool v52; // [rsp+E8h] [rbp+10h]
  char ProcessId; // [rsp+E8h] [rbp+10h]
  int v54; // [rsp+F0h] [rbp+18h]

  v54 = a3;
  v8 = a4;
  v10 = a1;
  if ( a2 && (_DWORD)a3 && a4 && a5 && a6 && a1 )
  {
    if ( a7 )
      *a7 = 0;
    if ( a8 )
      *a8 = 0;
    LOBYTE(CurrentProcess) = MpData;
    v12 = 0;
    v13 = 0;
    if ( (*(_DWORD *)(MpData + 864) & 8) == 0 )
      goto LABEL_24;
    LODWORD(CurrentProcess) = *a2;
    v14 = L"ALLOWED";
    v15 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
    v16 = 1;
    if ( (CurrentProcess & 0x2A) == 0 )
      goto LABEL_13;
    v22 = _InterlockedIncrement((volatile signed __int32 *)(a6 + 104));
    v46 = v22;
    if ( v22 <= 2 )
    {
      LOBYTE(CurrentProcess) = (_BYTE)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_13;
      LODWORD(CurrentProcess) = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (CurrentProcess & 4) == 0 )
        goto LABEL_13;
      _mm_lfence();
      LOBYTE(CurrentProcess) = WPP_SF_qdddd(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 41,
                                 WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids,
                                 KeGetCurrentThread(),
                                 v22,
                                 (*(_DWORD *)(MpData + 864) >> 3) & 1,
                                 a3,
                                 v8);
      v15 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
LABEL_48:
      v8 = a4;
      v14 = L"ALLOWED";
LABEL_13:
      v17 = v54;
      goto LABEL_14;
    }
    _mm_lfence();
    v51 = MpAllowCodeInjection(a5, a6, a3, &WPP_GLOBAL_Control);
    if ( v51 && (*(_DWORD *)(a6 + 52) & 0x400) == 0 )
    {
      v23 = *(unsigned int *)(a5 + 56);
      if ( (v23 & 0x8000) == 0 || (*(_DWORD *)(a6 + 56) & 0x80000) != 0 )
      {
        v25 = 1;
        v51 = 1;
      }
      else
      {
        v23 &= 0x10000u;
        v12 = 1;
        v25 = (_DWORD)v23 != 0;
        v51 = (_DWORD)v23 != 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          _mm_lfence();
          v30 = L"ALLOWED";
          if ( !(_DWORD)v23 )
            v30 = L"BLOCKED";
          WPP_SF_DDDS(
            WPP_GLOBAL_Control->AttachedDevice,
            v23,
            v24,
            0x8000,
            *(_DWORD *)(a5 + 24),
            *(_DWORD *)(a6 + 24),
            (__int64)v30);
          v25 = v51;
        }
      }
      if ( (*(_DWORD *)(a6 + 292) & 0xF) != 1 && *(int *)(a6 + 296) <= 0 && *(_DWORD *)(MpData + 4168) && !v25 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          v42 = v54;
          WPP_SF_qddDD(WPP_GLOBAL_Control->AttachedDevice, *(_DWORD *)(a6 + 292) & 0xF, v24, KeGetCurrentThread());
        }
        v51 = 1;
        v12 = 0;
      }
    }
    IsOfficeApplication = MpIsOfficeApplication(a5, v23, v24);
    LOBYTE(CurrentProcess) = MpIsOfficeApplication(a6, v26, IsOfficeApplication);
    LOBYTE(v16) = (_BYTE)CurrentProcess
               || (v28 = *(int *)(a6 + 240), (_DWORD)v28 == 15)
               || (unsigned int)v28 <= 0x20 && (CurrentProcess = 0x110004000LL, _bittest64(&CurrentProcess, v28));
    v44 = v16;
    if ( v12 )
    {
      if ( !(unsigned int)MpFcKernelGetValue(288) && (_BYTE)v32 && v31 && (*(_DWORD *)(a5 + 288) & 2) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        {
          _mm_lfence();
          WPP_SF_qZDZD(
            WPP_GLOBAL_Control->AttachedDevice,
            43,
            v32,
            (unsigned int)KeGetCurrentThread(),
            *(_QWORD *)(a5 + 128),
            v54,
            *(_QWORD *)(a6 + 128),
            a4);
        }
        v12 = 0;
        v51 = 1;
      }
      LODWORD(CurrentProcess) = MpFcKernelGetValue(278);
      if ( !(_DWORD)CurrentProcess || *(_DWORD *)v10 != 2 || !v27 || !(_BYTE)v16 )
      {
LABEL_47:
        if ( !v51 )
        {
          *a2 &= 0xFFFFFFD5;
          LOBYTE(CurrentProcess) = (_BYTE)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != v15 )
          {
            LODWORD(CurrentProcess) = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (CurrentProcess & 1) != 0 )
            {
              _mm_lfence();
              LOBYTE(CurrentProcess) = WPP_SF_qDddZDZDDD(
                                         WPP_GLOBAL_Control->AttachedDevice,
                                         v12,
                                         *(_QWORD *)(a6 + 128),
                                         (unsigned int)KeGetCurrentThread(),
                                         v42,
                                         v12,
                                         *(_DWORD *)v10,
                                         *(_QWORD *)(a5 + 128),
                                         v54,
                                         *(_QWORD *)(a6 + 128),
                                         a4,
                                         *(_BYTE *)(a6 + 292) & 0xF,
                                         *(_DWORD *)(a6 + 296));
              v16 = v44;
              v15 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
              v27 = IsOfficeApplication;
              v10 = a1;
            }
          }
          if ( v27 )
          {
            if ( (_BYTE)v16 )
            {
              LOBYTE(CurrentProcess) = (_BYTE)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != v15 )
              {
                LODWORD(CurrentProcess) = HIDWORD(WPP_GLOBAL_Control->Timer);
                if ( (CurrentProcess & 2) != 0 )
                {
                  _mm_lfence();
                  if ( *(_DWORD *)v10 == 2 )
                    ProcessId = (unsigned __int8)PsGetProcessId(*(PEPROCESS *)(*(_QWORD *)(v10 + 32) + 16LL));
                  else
                    ProcessId = 0;
                  if ( *(_DWORD *)v10 == 2 )
                    v48 = (unsigned __int8)PsGetProcessId(*(PEPROCESS *)(*(_QWORD *)(v10 + 32) + 8LL));
                  else
                    v48 = 0;
                  v34 = (*(_DWORD *)(a5 + 288) >> 1) & 1;
                  Value = MpFcKernelGetValue(278);
                  v43 = v34;
                  v17 = v54;
                  LOBYTE(CurrentProcess) = WPP_SF_qdZDZDdddDD(
                                             v40,
                                             v36,
                                             v37,
                                             v38,
                                             v39,
                                             v37,
                                             v54,
                                             v36,
                                             a4,
                                             v46,
                                             v43,
                                             Value,
                                             v48,
                                             ProcessId);
                  v8 = a4;
                  v14 = L"ALLOWED";
                  v15 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
LABEL_14:
                  if ( (*a2 & 0xFFEDE7FE) != 0 )
                  {
                    if ( (*(_DWORD *)(a5 + 288) & 1) == 0
                      || (v16 = *(unsigned __int8 *)(a5 + 184), LOBYTE(CurrentProcess) = v16 & 7, (v16 & 7) == 0)
                      || (v21 = (unsigned __int8)v16 >> 4, v21 < 3u)
                      || v21 >= 8u )
                    {
                      v18 = *(_DWORD *)(a6 + 56);
                      if ( (v18 & 0x800000) == 0 || (*(_DWORD *)(a5 + 56) & 0x2000000) != 0 )
                      {
                        LOBYTE(v16) = 1;
                      }
                      else
                      {
                        v29 = v18 & 0x1000000;
                        v13 = 1;
                        LOBYTE(v16) = v29 != 0;
                        v52 = v29 != 0;
                        if ( WPP_GLOBAL_Control != v15 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                        {
                          if ( !v29 )
                            v14 = L"BLOCKED";
                          WPP_SF_DDDS(
                            WPP_GLOBAL_Control->AttachedDevice,
                            v16,
                            v29,
                            0x800000,
                            *(_DWORD *)(a6 + 24),
                            *(_DWORD *)(a5 + 24),
                            (__int64)v14);
                          v8 = a4;
                          v15 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
                          LOBYTE(v16) = v52;
                        }
                      }
                      v19 = (*(_DWORD *)(a5 + 292) & 0xF) == 1 || *(int *)(a5 + 296) > 0;
                      v20 = v19;
                      LOBYTE(CurrentProcess) = 1;
                      if ( !*(_DWORD *)(MpData + 4092) )
                        v20 = 1;
                      if ( (_BYTE)v16 || !v20 )
                      {
                        if ( v13 && !v20 )
                        {
                          LOBYTE(CurrentProcess) = (_BYTE)WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != v15 )
                          {
                            LODWORD(CurrentProcess) = HIDWORD(WPP_GLOBAL_Control->Timer);
                            if ( (CurrentProcess & 1) != 0 )
                              LOBYTE(CurrentProcess) = WPP_SF_qdddDD(
                                                         WPP_GLOBAL_Control->AttachedDevice,
                                                         48,
                                                         v13,
                                                         KeGetCurrentThread(),
                                                         v13,
                                                         v17,
                                                         v8,
                                                         *(_DWORD *)(a5 + 292) & 0xF,
                                                         *(_DWORD *)(a5 + 296));
                          }
                          v13 = 0;
                        }
                      }
                      else
                      {
                        *a2 &= 0x121801u;
                        LOBYTE(CurrentProcess) = (_BYTE)WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != v15 )
                        {
                          LODWORD(CurrentProcess) = HIDWORD(WPP_GLOBAL_Control->Timer);
                          if ( (CurrentProcess & 1) != 0 )
                            LOBYTE(CurrentProcess) = WPP_SF_qdddDD(
                                                       WPP_GLOBAL_Control->AttachedDevice,
                                                       47,
                                                       v13,
                                                       KeGetCurrentThread(),
                                                       v13,
                                                       v17,
                                                       v8,
                                                       *(_DWORD *)(a5 + 292) & 0xF,
                                                       *(_DWORD *)(a5 + 296));
                        }
                      }
                    }
                  }
LABEL_24:
                  if ( a7 )
                    *a7 = v12;
                  if ( a8 )
                    *a8 = v13;
                  return CurrentProcess;
                }
              }
            }
          }
        }
        goto LABEL_48;
      }
      v49 = *(_QWORD *)(v10 + 32);
      v47 = *(_QWORD *)(v49 + 16);
      CurrentProcess = (__int64)IoGetCurrentProcess();
      if ( CurrentProcess == v47 )
      {
        LOBYTE(CurrentProcess) = v49;
        if ( v47 == *(_QWORD *)(v49 + 8) )
        {
          LOBYTE(CurrentProcess) = (_BYTE)WPP_GLOBAL_Control;
          v15 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
          v17 = v54;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            LODWORD(CurrentProcess) = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (CurrentProcess & 2) != 0 )
            {
              _mm_lfence();
              LOBYTE(CurrentProcess) = WPP_SF_qZDZD(
                                         WPP_GLOBAL_Control->AttachedDevice,
                                         44,
                                         v33,
                                         (unsigned int)KeGetCurrentThread(),
                                         *(_QWORD *)(a5 + 128),
                                         v54,
                                         *(_QWORD *)(a6 + 128),
                                         a4);
              v15 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
            }
          }
          v8 = a4;
          v14 = L"ALLOWED";
          v12 = 0;
          goto LABEL_14;
        }
      }
      v27 = IsOfficeApplication;
      v16 = v44;
    }
    v15 = (struct _DEVICE_OBJECT *)&WPP_GLOBAL_Control;
    goto LABEL_47;
  }
  CurrentProcess = (__int64)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    LODWORD(CurrentProcess) = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (CurrentProcess & 1) != 0 )
      LOBYTE(CurrentProcess) = WPP_SF_(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 40,
                                 WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids);
  }
  return CurrentProcess;
}

```

## disassembly

```asm
0x140043520  mov     rax, rsp
0x140043523  mov     [rax+20h], r9
0x140043527  mov     [rax+18h], r8
0x14004352b  mov     [rax+8], rcx
0x14004352f  push    rbp
0x140043530  push    rdi
0x140043531  push    r12
0x140043533  push    r15
0x140043535  sub     rsp, 0B8h
0x14004353c  mov     r11, r9
0x14004353f  mov     r12, rdx
0x140043542  mov     rdi, rcx
0x140043545  test    rdx, rdx
0x140043548  jz      loc_140043E8F
0x14004354e  test    r8d, r8d
0x140043551  jz      loc_140043E8F
0x140043557  test    r11d, r11d
0x14004355a  jz      loc_140043E8F
0x140043560  mov     rbp, [rsp+0D8h+arg_20]
0x140043568  test    rbp, rbp
0x14004356b  jz      loc_140043E8F
0x140043571  mov     r15, [rsp+0D8h+arg_28]
0x140043579  test    r15, r15
0x14004357c  jz      loc_140043E8F
0x140043582  test    rcx, rcx
0x140043585  jz      loc_140043E8F
0x14004358b  mov     [rax-28h], rbx
0x14004358f  mov     [rax-30h], rsi
0x140043593  mov     rsi, [rsp+0D8h+arg_30]
0x14004359b  mov     [rax-38h], r13
0x14004359f  mov     [rax-40h], r14
0x1400435a3  test    rsi, rsi
0x1400435a6  jz      short loc_1400435AB
0x1400435a8  mov     byte ptr [rsi], 0
0x1400435ab  mov     rbx, [rsp+0D8h+arg_38]
0x1400435b3  test    rbx, rbx
0x1400435b6  jz      short loc_1400435BB
0x1400435b8  mov     byte ptr [rbx], 0
0x1400435bb  mov     rax, cs:MpData
0x1400435c2  xor     r13b, r13b
0x1400435c5  xor     r14b, r14b
0x1400435c8  mov     ecx, [rax+360h]
0x1400435ce  test    cl, 8
0x1400435d1  jz      loc_140043661
0x1400435d7  mov     eax, [rdx]
0x1400435d9  lea     rcx, aAllowed; "ALLOWED"
0x1400435e0  lea     r9, WPP_GLOBAL_Control
0x1400435e7  mov     edx, 1
0x1400435ec  test    al, 2Ah
0x1400435ee  jnz     loc_1400436DF
0x1400435f4  mov     rdi, [rsp+0D8h+arg_10]
0x1400435fc  test    dword ptr [r12], 0FFEDE7FEh
0x140043604  jz      short loc_140043661
0x140043606  mov     eax, [rbp+120h]
0x14004360c  test    al, 1
0x14004360e  jnz     loc_1400436A0
0x140043614  mov     r8d, [r15+38h]
0x140043618  bt      r8d, 17h
0x14004361d  jb      loc_140043957
0x140043623  mov     dl, 1
0x140043625  mov     eax, [rbp+124h]
0x14004362b  and     al, 0Fh
0x14004362d  cmp     al, 1
0x14004362f  jnz     loc_1400436CA
0x140043635  mov     al, 1
0x140043637  movzx   ecx, al
0x14004363a  mov     rax, cs:MpData
0x140043641  cmp     dword ptr [rax+0FFCh], 0
0x140043648  mov     eax, 1
0x14004364d  cmovz   ecx, eax
0x140043650  test    dl, dl
0x140043652  jz      loc_1400438DD
0x140043658  test    r14b, r14b
0x14004365b  jnz     loc_140043E22
0x140043661  test    rsi, rsi
0x140043664  jz      short loc_140043669
0x140043666  mov     [rsi], r13b
0x140043669  mov     r13, [rsp+0D8h+var_38]
0x140043671  mov     rsi, [rsp+0D8h+var_30]
0x140043679  test    rbx, rbx
0x14004367c  jz      short loc_140043681
0x14004367e  mov     [rbx], r14b
0x140043681  mov     rbx, [rsp+0D8h+var_28]
0x140043689  mov     r14, [rsp+0D8h+var_40]
0x140043691  add     rsp, 0B8h
0x140043698  pop     r15
0x14004369a  pop     r12
0x14004369c  pop     rdi
0x14004369d  pop     rbp
0x14004369e  retn
0x1400436a0  movzx   edx, byte ptr [rbp+0B8h]
0x1400436a7  movzx   eax, dl
0x1400436aa  and     al, 7
0x1400436ac  cmp     al, 1
0x1400436ae  jb      loc_140043614
0x1400436b4  shr     dl, 4
0x1400436b7  cmp     dl, 3
0x1400436ba  jb      loc_140043614
0x1400436c0  cmp     dl, 8
0x1400436c3  jb      short loc_140043661
0x1400436c5  jmp     loc_140043614
0x1400436ca  mov     eax, [rbp+128h]
0x1400436d0  test    eax, eax
0x1400436d2  jg      loc_140043635
0x1400436d8  xor     al, al
0x1400436da  jmp     loc_140043637
0x1400436df  mov     r10d, edx
0x1400436e2  lock xadd [r15+68h], r10d
0x1400436e8  inc     r10d
0x1400436eb  mov     [rsp+0D8h+var_64], r10d
0x1400436f0  cmp     r10d, 2
0x1400436f4  jbe     loc_1400437C0
0x1400436fa  lfence
0x1400436fd  mov     rdx, r15
0x140043700  mov     rcx, rbp
0x140043703  call    MpAllowCodeInjection
0x140043708  mov     byte ptr [rsp+0D8h+arg_8], al
0x14004370f  test    al, al
0x140043711  jz      short loc_140043768
0x140043713  test    dword ptr [r15+34h], 400h
0x14004371b  jnz     short loc_140043768
0x14004371d  mov     edx, [rbp+38h]
0x140043720  bt      edx, 0Fh
0x140043724  jb      loc_1400439E1
0x14004372a  mov     r9b, 1
0x14004372d  mov     byte ptr [rsp+0D8h+arg_8], r9b
0x140043735  lea     rcx, WPP_GLOBAL_Control
0x14004373c  mov     eax, [r15+124h]
0x140043743  and     al, 0Fh
0x140043745  cmp     al, 1
0x140043747  jz      short loc_140043768
0x140043749  mov     eax, [r15+128h]
0x140043750  test    eax, eax
0x140043752  jg      short loc_140043768
0x140043754  mov     rax, cs:MpData
0x14004375b  cmp     dword ptr [rax+1048h], 0
0x140043762  jnz     loc_140043864
0x140043768  mov     rcx, rbp
0x14004376b  call    MpIsOfficeApplication
0x140043770  mov     rcx, r15
0x140043773  mov     [rsp+0D8h+var_67], al
0x140043777  movzx   r8d, al
0x14004377b  call    MpIsOfficeApplication
0x140043780  test    al, al
0x140043782  jz      loc_140043834
0x140043788  mov     dl, 1
0x14004378a  mov     [rsp+0D8h+var_68], dl
0x14004378e  test    r13b, r13b
0x140043791  jnz     loc_140043A75
0x140043797  lea     r9, WPP_GLOBAL_Control
0x14004379e  cmp     byte ptr [rsp+0D8h+arg_8], r14b
0x1400437a6  jz      loc_140043C3D
0x1400437ac  mov     r11, [rsp+0D8h+arg_18]
0x1400437b4  lea     rcx, aAllowed; "ALLOWED"
0x1400437bb  jmp     loc_1400435F4
0x1400437c0  mov     rax, cs:WPP_GLOBAL_Control
0x1400437c7  cmp     rax, r9
0x1400437ca  jz      loc_1400435F4
0x1400437d0  mov     eax, [rax+2Ch]
0x1400437d3  test    al, 4
0x1400437d5  jz      loc_1400435F4
0x1400437db  lfence
0x1400437de  mov     r9, gs:188h
0x1400437e7  mov     rax, cs:MpData
0x1400437ee  mov     dword ptr [rsp+0D8h+var_A0], r11d
0x1400437f3  mov     dword ptr [rsp+0D8h+var_A8], r8d
0x1400437f8  lea     r8, WPP_987d9fc7520d333ff9fdca1fa9c66d57_Traceguids
0x1400437ff  mov     ecx, [rax+360h]
0x140043805  shr     ecx, 3
0x140043808  and     ecx, edx
0x14004380a  mov     edx, 29h ; ')'
0x14004380f  mov     dword ptr [rsp+0D8h+var_B0], ecx
0x140043813  mov     rcx, cs:WPP_GLOBAL_Control
0x14004381a  mov     dword ptr [rsp+0D8h+var_B8], r10d
0x14004381f  mov     rcx, [rcx+18h]
0x140043823  call    WPP_SF_qdddd
0x140043828  lea     r9, WPP_GLOBAL_Control
0x14004382f  jmp     loc_1400437AC
0x140043834  movsxd  rcx, dword ptr [r15+0F0h]
0x14004383b  cmp     ecx, 0Fh
0x14004383e  jz      loc_140043788
0x140043844  cmp     ecx, 20h ; ' '
0x140043847  ja      short loc_14004385D
0x140043849  mov     rax, 110004000h
0x140043853  bt      rax, rcx
0x140043857  jb      loc_140043788
0x14004385d  xor     dl, dl
0x14004385f  jmp     loc_14004378A
0x140043864  test    r9b, r9b
0x140043867  jnz     loc_140043768
0x14004386d  mov     rax, cs:WPP_GLOBAL_Control
0x140043874  cmp     rax, rcx
0x140043877  jz      short loc_1400438CD
0x140043879  mov     eax, [rax+2Ch]
0x14004387c  test    al, 1
0x14004387e  jz      short loc_1400438CD
0x140043880  lfence
0x140043883  mov     r9, gs:188h
0x14004388c  mov     rax, cs:WPP_GLOBAL_Control
0x140043893  mov     edx, [r15+124h]
0x14004389a  and     edx, 0Fh
0x14004389d  mov     rcx, [rax+18h]
0x1400438a1  mov     eax, [r15+128h]
0x1400438a8  mov     dword ptr [rsp+0D8h+var_A0], eax
0x1400438ac  mov     rax, [rsp+0D8h+arg_18]
0x1400438b4  mov     dword ptr [rsp+0D8h+var_A8], edx
0x1400438b8  mov     dword ptr [rsp+0D8h+var_B0], eax
0x1400438bc  mov     rax, [rsp+0D8h+arg_10]
0x1400438c4  mov     dword ptr [rsp+0D8h+var_B8], eax
0x1400438c8  call    WPP_SF_qddDD
0x1400438cd  mov     byte ptr [rsp+0D8h+arg_8], 1
0x1400438d5  xor     r13b, r13b
0x1400438d8  jmp     loc_140043768
0x1400438dd  test    cl, cl
0x1400438df  jz      loc_140043658
0x1400438e5  and     dword ptr [r12], 121801h
0x1400438ed  mov     rax, cs:WPP_GLOBAL_Control
0x1400438f4  cmp     rax, r9
0x1400438f7  jz      loc_140043661
0x1400438fd  mov     eax, [rax+2Ch]
0x140043900  test    al, 1
0x140043902  jz      loc_140043661
0x140043908  mov     r9, gs:188h
0x140043911  mov     edx, 2Fh ; '/'
0x140043916  mov     rax, cs:WPP_GLOBAL_Control
0x14004391d  mov     r10d, [rbp+124h]
0x140043924  and     r10d, 0Fh
0x140043928  movzx   r8d, r14b
0x14004392c  mov     rcx, [rax+18h]
0x140043930  mov     eax, [rbp+128h]
0x140043936  mov     [rsp+0D8h+var_98], eax
0x14004393a  mov     dword ptr [rsp+0D8h+var_A0], r10d
0x14004393f  mov     dword ptr [rsp+0D8h+var_A8], r11d
0x140043944  mov     dword ptr [rsp+0D8h+var_B0], edi
0x140043948  mov     dword ptr [rsp+0D8h+var_B8], r8d
0x14004394d  call    WPP_SF_qdddDD
0x140043952  jmp     loc_140043661
0x140043957  test    dword ptr [rbp+38h], 2000000h
0x14004395e  jnz     loc_140043623
0x140043964  and     r8d, 1000000h
0x14004396b  mov     r14b, 1
0x14004396e  setnz   dl
0x140043971  mov     byte ptr [rsp+0D8h+arg_8], dl
0x140043978  mov     r10, cs:WPP_GLOBAL_Control
0x14004397f  cmp     r10, r9
0x140043982  jz      loc_140043625
0x140043988  mov     eax, [r10+2Ch]
0x14004398c  test    al, 4
0x14004398e  jz      loc_140043625
0x140043994  lea     rax, aBlocked; "BLOCKED"
0x14004399b  test    r8d, r8d
0x14004399e  mov     r9d, 800000h
0x1400439a4  cmovz   rcx, rax
0x1400439a8  mov     eax, [rbp+18h]
0x1400439ab  mov     [rsp+0D8h+var_A8], rcx
0x1400439b0  mov     rcx, [r10+18h]
0x1400439b4  mov     dword ptr [rsp+0D8h+var_B0], eax
0x1400439b8  mov     eax, [r15+18h]
0x1400439bc  mov     dword ptr [rsp+0D8h+var_B8], eax
0x1400439c0  call    WPP_SF_DDDS
0x1400439c5  mov     r11, [rsp+0D8h+arg_18]
0x1400439cd  lea     r9, WPP_GLOBAL_Control
0x1400439d4  movzx   edx, byte ptr [rsp+0D8h+arg_8]
0x1400439dc  jmp     loc_140043625
0x1400439e1  test    dword ptr [r15+38h], 80000h
0x1400439e9  jnz     loc_14004372A
0x1400439ef  and     edx, 10000h
0x1400439f5  mov     r13b, 1
0x1400439f8  setnz   r9b
0x1400439fc  mov     byte ptr [rsp+0D8h+arg_8], r9b
0x140043a04  mov     rax, cs:WPP_GLOBAL_Control
0x140043a0b  lea     rcx, WPP_GLOBAL_Control
0x140043a12  cmp     rax, rcx
0x140043a15  jz      loc_14004373C
0x140043a1b  mov     eax, [rax+2Ch]
0x140043a1e  test    al, 4
0x140043a20  jz      loc_14004373C
0x140043a26  lfence
0x140043a29  test    edx, edx
0x140043a2b  lea     rcx, aBlocked; "BLOCKED"
0x140043a32  lea     rax, aAllowed; "ALLOWED"
0x140043a39  mov     r9d, 8000h
0x140043a3f  cmovz   rax, rcx
0x140043a43  mov     rcx, cs:WPP_GLOBAL_Control
0x140043a4a  mov     [rsp+0D8h+var_A8], rax
0x140043a4f  mov     eax, [r15+18h]
0x140043a53  mov     dword ptr [rsp+0D8h+var_B0], eax
0x140043a57  mov     eax, [rbp+18h]
0x140043a5a  mov     rcx, [rcx+18h]
0x140043a5e  mov     dword ptr [rsp+0D8h+var_B8], eax
0x140043a62  call    WPP_SF_DDDS
0x140043a67  movzx   r9d, byte ptr [rsp+0D8h+arg_8]
0x140043a70  jmp     loc_140043735
0x140043a75  mov     ecx, 120h
0x140043a7a  call    MpFcKernelGetValue
0x140043a7f  test    eax, eax
0x140043a81  jnz     loc_140043B30
0x140043a87  test    r8b, r8b
0x140043a8a  jz      loc_140043B30
0x140043a90  test    dl, dl
  ... truncated ...
```
