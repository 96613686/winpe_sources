# CBlbBackupAsync::CheckForLowSpaceOnTarget(void)

- ea: `0x14001d750`
- end: `0x14001dac7`
- name: `?CheckForLowSpaceOnTarget@CBlbBackupAsync@@AEAAJXZ`
- size: `887`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x140019fd0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bcbc`
- `0x140014260`
- `0x14001d750`
- `0x14003cad8`
- `0x14008863c`
- `0x1400d7a68`
- `0x140101b64`
- `0x1401068d4`
- `0x1401244c0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x14001d7d2`
- `ole32!CoTaskMemAlloc` at `0x14001d7f8`
- `ole32!CoTaskMemAlloc` at `0x14001d819`
- `ole32!CoTaskMemAlloc` at `0x14001d7d2`
- `ole32!CoTaskMemAlloc` at `0x14001d7f8`
- `ole32!CoTaskMemAlloc` at `0x14001d819`
- `ole32!CoTaskMemFree` at `0x14001da49`
- `ole32!CoTaskMemFree` at `0x14001da57`
- `ole32!CoTaskMemFree` at `0x14001da65`
- `ole32!CoTaskMemFree` at `0x14001da73`
- `ole32!CoTaskMemFree` at `0x14001da81`
- `ole32!CoTaskMemFree` at `0x14001da49`
- `ole32!CoTaskMemFree` at `0x14001da57`
- `ole32!CoTaskMemFree` at `0x14001da65`
- `ole32!CoTaskMemFree` at `0x14001da73`
- `ole32!CoTaskMemFree` at `0x14001da81`

## string_xrefs

- `0x14001d947`: `base\stor\blb\engine\service\backup.cpp`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::CheckForLowSpaceOnTarget(CBlbBackupAsync *this)
{
  unsigned __int16 *v2; // rsi
  unsigned __int16 *v3; // r15
  SIZE_T v4; // rcx
  struct _GUID *v5; // rbx
  int v6; // ebx
  unsigned int *v7; // r13
  unsigned __int8 *v8; // r12
  unsigned int v9; // eax
  __int64 i; // r9
  __int64 v11; // rdx
  int appended; // eax
  int v13; // edx
  int v14; // r8d
  PVOID *v15; // rcx
  __int64 v16; // r14
  unsigned __int64 v17; // r14
  int VolumeFriendlyNameForPublisher; // eax
  unsigned __int16 *v20; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int64 v21; // [rsp+48h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-18h]
  unsigned __int64 v23; // [rsp+B0h] [rbp+48h] BYREF
  unsigned __int64 v24; // [rsp+B8h] [rbp+50h] BYREF
  unsigned __int16 *v25; // [rsp+C0h] [rbp+58h] BYREF
  unsigned __int64 v26; // [rsp+C8h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 679, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v2 = 0;
  v3 = 0;
  v4 = 16LL * *((unsigned int *)this + 92);
  v24 = 0;
  v23 = 0;
  v21 = 0;
  v26 = 0;
  v25 = 0;
  v20 = 0;
  pv = CoTaskMemAlloc(v4);
  v5 = (struct _GUID *)pv;
  if ( !pv )
  {
    v6 = -2147024882;
    goto LABEL_43;
  }
  v7 = (unsigned int *)CoTaskMemAlloc(4LL * *((unsigned int *)this + 92));
  if ( v7 )
  {
    v8 = (unsigned __int8 *)CoTaskMemAlloc(*((unsigned int *)this + 92));
    if ( v8 )
    {
      v9 = *((_DWORD *)this + 92);
      for ( i = 0; (unsigned int)i < v9; v9 = *((_DWORD *)this + 92) )
      {
        v11 = 368LL * (unsigned int)i;
        v5[(unsigned int)i] = *(struct _GUID *)(v11 + *((_QWORD *)this + 27) + 68);
        v7[i] = *(_DWORD *)(v11 + *((_QWORD *)this + 27) + 84);
        v8[i] = 1;
        i = (unsigned int)(i + 1);
      }
      v6 = BlbQueryBackupSize(*((unsigned __int16 **)this + 71), 0, v5, v7, v8, v9, &v24, &v21);
      if ( v6 >= 0 )
      {
        appended = BlbutilAppendString(*((const unsigned __int16 **)this + 43), L"\\", &v25);
        v2 = v25;
        v6 = appended;
        if ( appended >= 0 )
        {
          v6 = BlbQueryFileSystemSpace(v25, &v23, &v26);
          if ( v6 >= 0 )
          {
            v15 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_SII(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, (_DWORD)v2, v23, v26);
              v15 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( (unsigned int)(*((_DWORD *)this + 84) - 2) > 2 )
            {
              BlbAssert(
                "base\\stor\\blb\\engine\\service\\backup.cpp",
                0x40A0u,
                "m_eMediaType == BLB_MT_FIXED || m_eMediaType == BLB_MT_YANKABLE || m_eMediaType == BLB_MT_NETWORK_SHARE");
              v15 = (PVOID *)WPP_GLOBAL_Control;
            }
            v16 = 80;
            if ( *((_DWORD *)this + 84) != 4 )
              v16 = 60;
            v17 = v23 * v16 / 0x64;
            if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 4u )
              WPP_SF_qq(v15[2], 681, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v24, v17);
            if ( v24 > v17 )
            {
              VolumeFriendlyNameForPublisher = GetVolumeFriendlyNameForPublisher(
                                                 *((_QWORD *)this + 43),
                                                 *((unsigned int *)this + 84),
                                                 &v20);
              v3 = v20;
              if ( VolumeFriendlyNameForPublisher < 0
                || (VolumeFriendlyNameForPublisher = PublishSingleVolumeInfoTemplate(
                                                       v20,
                                                       *((unsigned __int16 **)this + 44),
                                                       &BACKUP_TARGET_LOW_ON_SPACE_EVENT),
                    VolumeFriendlyNameForPublisher < 0) )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    682,
                    (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
                    (_DWORD)v3,
                    VolumeFriendlyNameForPublisher);
                }
              }
            }
          }
        }
      }
      goto LABEL_35;
    }
  }
  else
  {
    v8 = 0;
  }
  v6 = -2147024882;
LABEL_35:
  CoTaskMemFree(pv);
  if ( v7 )
    CoTaskMemFree(v7);
  if ( v8 )
    CoTaskMemFree(v8);
  if ( v2 )
    CoTaskMemFree(v2);
  if ( v3 )
    CoTaskMemFree(v3);
LABEL_43:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 683, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001d750  push    rbp
0x14001d752  push    rbx
0x14001d753  push    rsi
0x14001d754  push    rdi
0x14001d755  push    r12
0x14001d757  push    r13
0x14001d759  push    r14
0x14001d75b  push    r15
0x14001d75d  mov     rbp, rsp
0x14001d760  sub     rsp, 68h
0x14001d764  mov     rdi, rcx
0x14001d767  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d76e  lea     r14, WPP_GLOBAL_Control
0x14001d775  cmp     rcx, r14
0x14001d778  jz      short loc_14001D79B
0x14001d77a  test    byte ptr [rcx+1Ch], 1
0x14001d77e  jz      short loc_14001D79B
0x14001d780  cmp     byte ptr [rcx+19h], 4
0x14001d784  jb      short loc_14001D79B
0x14001d786  mov     rcx, [rcx+10h]
0x14001d78a  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001d791  mov     edx, 2A7h
0x14001d796  call    WPP_SF_
0x14001d79b  mov     ecx, [rdi+170h]
0x14001d7a1  xor     esi, esi
0x14001d7a3  xor     r15d, r15d
0x14001d7a6  shl     rcx, 4; cb
0x14001d7aa  mov     [rbp+arg_8], 0
0x14001d7b2  mov     [rbp+arg_0], 0
0x14001d7ba  mov     [rbp+var_20], 0
0x14001d7c2  mov     [rbp+arg_18], 0
0x14001d7ca  mov     [rbp+arg_10], rsi
0x14001d7ce  mov     [rbp+var_28], r15
0x14001d7d2  call    cs:__imp_CoTaskMemAlloc
0x14001d7d8  mov     [rbp+pv], rax
0x14001d7dc  mov     rbx, rax
0x14001d7df  test    rax, rax
0x14001d7e2  jnz     short loc_14001D7EE
0x14001d7e4  mov     ebx, 8007000Eh
0x14001d7e9  jmp     loc_14001DA87
0x14001d7ee  mov     ecx, [rdi+170h]
0x14001d7f4  shl     rcx, 2; cb
0x14001d7f8  call    cs:__imp_CoTaskMemAlloc
0x14001d7fe  mov     r13, rax
0x14001d801  test    rax, rax
0x14001d804  jnz     short loc_14001D813
0x14001d806  xor     r12d, r12d
0x14001d809  mov     ebx, 8007000Eh
0x14001d80e  jmp     loc_14001DA45
0x14001d813  mov     ecx, [rdi+170h]; cb
0x14001d819  call    cs:__imp_CoTaskMemAlloc
0x14001d81f  mov     r12, rax
0x14001d822  test    rax, rax
0x14001d825  jz      short loc_14001D809
0x14001d827  mov     eax, [rdi+170h]
0x14001d82d  xor     r9d, r9d
0x14001d830  test    eax, eax
0x14001d832  jz      short loc_14001D878
0x14001d834  mov     rax, [rdi+0D8h]
0x14001d83b  mov     r8d, r9d
0x14001d83e  imul    rdx, r8, 170h
0x14001d845  mov     ecx, r9d
0x14001d848  add     rcx, rcx
0x14001d84b  movups  xmm0, xmmword ptr [rdx+rax+44h]
0x14001d850  movdqu  xmmword ptr [rbx+rcx*8], xmm0
0x14001d855  mov     rax, [rdi+0D8h]
0x14001d85c  mov     ecx, [rdx+rax+54h]
0x14001d860  mov     [r13+r9*4+0], ecx
0x14001d865  mov     byte ptr [r9+r12], 1
0x14001d86a  inc     r9d
0x14001d86d  mov     eax, [rdi+170h]
0x14001d873  cmp     r9d, eax
0x14001d876  jb      short loc_14001D834
0x14001d878  lea     rcx, [rbp+var_20]
0x14001d87c  mov     r9, r13; unsigned int *
0x14001d87f  mov     [rsp+68h+var_30], rcx; unsigned __int64 *
0x14001d884  mov     r8, rbx; struct _GUID *
0x14001d887  lea     rcx, [rbp+arg_8]
0x14001d88b  xor     edx, edx; struct _BLBCAT_BACKUP_SET_INFO *
0x14001d88d  mov     [rsp+68h+var_38], rcx; unsigned __int64 *
0x14001d892  mov     rcx, [rdi+238h]; unsigned __int16 *
0x14001d899  mov     [rsp+68h+var_40], eax; unsigned int
0x14001d89d  mov     [rsp+68h+var_48], r12; unsigned __int8 *
0x14001d8a2  call    ?BlbQueryBackupSize@@YAJPEAGPEAU_BLBCAT_BACKUP_SET_INFO@@PEAU_GUID@@PEAKPEAEKPEA_K5@Z; BlbQueryBackupSize(ushort *,_BLBCAT_BACKUP_SET_INFO *,_GUID *,ulong *,uchar *,ulong,unsigned __int64 *,unsigned __int64 *)
0x14001d8a7  mov     ebx, eax
0x14001d8a9  test    eax, eax
0x14001d8ab  js      loc_14001DA45
0x14001d8b1  mov     rcx, [rdi+158h]; unsigned __int16 *
0x14001d8b8  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x14001d8bc  lea     rdx, asc_14013C090; "\\"
0x14001d8c3  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14001d8c8  mov     rsi, [rbp+arg_10]
0x14001d8cc  mov     ebx, eax
0x14001d8ce  test    eax, eax
0x14001d8d0  js      loc_14001DA45
0x14001d8d6  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x14001d8da  mov     rcx, rsi; unsigned __int16 *
0x14001d8dd  lea     rdx, [rbp+arg_0]; unsigned __int64 *
0x14001d8e1  call    ?BlbQueryFileSystemSpace@@YAJPEAGPEA_K1@Z; BlbQueryFileSystemSpace(ushort *,unsigned __int64 *,unsigned __int64 *)
0x14001d8e6  mov     ebx, eax
0x14001d8e8  test    eax, eax
0x14001d8ea  js      loc_14001DA45
0x14001d8f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d8f7  cmp     rcx, r14
0x14001d8fa  jz      short loc_14001D92D
0x14001d8fc  test    byte ptr [rcx+1Ch], 1
0x14001d900  jz      short loc_14001D92D
0x14001d902  cmp     byte ptr [rcx+19h], 4
0x14001d906  jb      short loc_14001D92D
0x14001d908  mov     rax, [rbp+arg_18]
0x14001d90c  mov     r9, rsi
0x14001d90f  mov     rcx, [rcx+10h]
0x14001d913  mov     qword ptr [rsp+68h+var_40], rax
0x14001d918  mov     rax, [rbp+arg_0]
0x14001d91c  mov     [rsp+68h+var_48], rax
0x14001d921  call    WPP_SF_SII
0x14001d926  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d92d  mov     eax, [rdi+150h]
0x14001d933  sub     eax, 2
0x14001d936  cmp     eax, 2
0x14001d939  jbe     short loc_14001D95A
0x14001d93b  lea     r8, aMEmediatypeBlb_0; "m_eMediaType == BLB_MT_FIXED || m_eMedi"...
0x14001d942  mov     edx, 40A0h; unsigned int
0x14001d947  lea     rcx, aBaseStorBlbEng_20; "base\\stor\\blb\\engine\\service\\backu"...
0x14001d94e  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14001d953  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d95a  cmp     dword ptr [rdi+150h], 4
0x14001d961  mov     eax, 3Ch ; '<'
0x14001d966  lea     r14d, [rax+14h]
0x14001d96a  cmovnz  r14d, eax
0x14001d96e  mov     rax, 47AE147AE147AE15h
0x14001d978  imul    r14, [rbp+arg_0]
0x14001d97d  mul     r14
0x14001d980  sub     r14, rdx
0x14001d983  shr     r14, 1
0x14001d986  add     r14, rdx
0x14001d989  shr     r14, 6
0x14001d98d  lea     rax, WPP_GLOBAL_Control
0x14001d994  cmp     rcx, rax
0x14001d997  jz      short loc_14001D9C3
0x14001d999  test    byte ptr [rcx+1Ch], 1
0x14001d99d  jz      short loc_14001D9C3
0x14001d99f  cmp     byte ptr [rcx+19h], 4
0x14001d9a3  jb      short loc_14001D9C3
0x14001d9a5  mov     r9, [rbp+arg_8]
0x14001d9a9  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001d9b0  mov     rcx, [rcx+10h]
0x14001d9b4  mov     edx, 2A9h
0x14001d9b9  mov     [rsp+68h+var_48], r14
0x14001d9be  call    WPP_SF_qq
0x14001d9c3  cmp     [rbp+arg_8], r14
0x14001d9c7  jbe     short loc_14001DA3E
0x14001d9c9  mov     edx, [rdi+150h]
0x14001d9cf  lea     r8, [rbp+var_28]
0x14001d9d3  mov     rcx, [rdi+158h]
0x14001d9da  call    ?GetVolumeFriendlyNameForPublisher@@YAJPEAGW4_BLB_MEDIA_TYPE@@AEAPEAG@Z; GetVolumeFriendlyNameForPublisher(ushort *,_BLB_MEDIA_TYPE,ushort * &)
0x14001d9df  mov     r15, [rbp+var_28]
0x14001d9e3  test    eax, eax
0x14001d9e5  js      short loc_14001DA01
0x14001d9e7  mov     rdx, [rdi+160h]; unsigned __int16 *
0x14001d9ee  lea     r8, BACKUP_TARGET_LOW_ON_SPACE_EVENT; struct _EVENT_DESCRIPTOR *
0x14001d9f5  mov     rcx, r15; unsigned __int16 *
0x14001d9f8  call    ?PublishSingleVolumeInfoTemplate@@YAJPEAG0PEBU_EVENT_DESCRIPTOR@@@Z; PublishSingleVolumeInfoTemplate(ushort *,ushort *,_EVENT_DESCRIPTOR const *)
0x14001d9fd  test    eax, eax
0x14001d9ff  jns     short loc_14001DA3E
0x14001da01  mov     rcx, cs:WPP_GLOBAL_Control
0x14001da08  lea     r14, WPP_GLOBAL_Control
0x14001da0f  cmp     rcx, r14
0x14001da12  jz      short loc_14001DA45
0x14001da14  test    byte ptr [rcx+1Ch], 1
0x14001da18  jz      short loc_14001DA45
0x14001da1a  cmp     byte ptr [rcx+19h], 2
0x14001da1e  jb      short loc_14001DA45
0x14001da20  mov     rcx, [rcx+10h]
0x14001da24  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001da2b  mov     edx, 2AAh
0x14001da30  mov     dword ptr [rsp+68h+var_48], eax
0x14001da34  mov     r9, r15
0x14001da37  call    WPP_SF_Sd
0x14001da3c  jmp     short loc_14001DA45
0x14001da3e  lea     r14, WPP_GLOBAL_Control
0x14001da45  mov     rcx, [rbp+pv]; pv
0x14001da49  call    cs:__imp_CoTaskMemFree
0x14001da4f  test    r13, r13
0x14001da52  jz      short loc_14001DA5D
0x14001da54  mov     rcx, r13; pv
0x14001da57  call    cs:__imp_CoTaskMemFree
0x14001da5d  test    r12, r12
0x14001da60  jz      short loc_14001DA6B
0x14001da62  mov     rcx, r12; pv
0x14001da65  call    cs:__imp_CoTaskMemFree
0x14001da6b  test    rsi, rsi
0x14001da6e  jz      short loc_14001DA79
0x14001da70  mov     rcx, rsi; pv
0x14001da73  call    cs:__imp_CoTaskMemFree
0x14001da79  test    r15, r15
0x14001da7c  jz      short loc_14001DA87
0x14001da7e  mov     rcx, r15; pv
0x14001da81  call    cs:__imp_CoTaskMemFree
0x14001da87  mov     rcx, cs:WPP_GLOBAL_Control
0x14001da8e  cmp     rcx, r14
0x14001da91  jz      short loc_14001DAB4
0x14001da93  test    byte ptr [rcx+1Ch], 1
0x14001da97  jz      short loc_14001DAB4
0x14001da99  cmp     byte ptr [rcx+19h], 4
0x14001da9d  jb      short loc_14001DAB4
0x14001da9f  mov     rcx, [rcx+10h]
0x14001daa3  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14001daaa  mov     edx, 2ABh
0x14001daaf  call    WPP_SF_
0x14001dab4  mov     eax, ebx
0x14001dab6  add     rsp, 68h
0x14001daba  pop     r15
0x14001dabc  pop     r14
0x14001dabe  pop     r13
0x14001dac0  pop     r12
0x14001dac2  pop     rdi
0x14001dac3  pop     rsi
0x14001dac4  pop     rbx
0x14001dac5  pop     rbp
0x14001dac6  retn
```
