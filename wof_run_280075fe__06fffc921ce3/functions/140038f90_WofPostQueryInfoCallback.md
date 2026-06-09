# WofPostQueryInfoCallback

- ea: `0x140038f90`
- end: `0x1400396f9`
- name: `WofPostQueryInfoCallback`
- size: `1897`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400014d0`
- `0x140007670`
- `0x140011640`
- `0x1400116c0`
- `0x140038f90`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtection` at `0x140039126`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140039126`
- `ntoskrnl!RtlCompareMemory` at `0x140039515`
- `ntoskrnl!RtlCompareMemory` at `0x140039668`
- `ntoskrnl!RtlCompareMemory` at `0x140039515`
- `ntoskrnl!RtlCompareMemory` at `0x140039668`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003905e`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14003905e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140039146`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140039146`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003913a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003913a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400390b8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400390b8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400390cc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400390cc`
- `FLTMGR!FltGetStreamContext` at `0x140039008`
- `FLTMGR!FltGetStreamContext` at `0x140039008`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400393f7`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400393f7`
- `FLTMGR!FltReleaseContext` at `0x14003906c`
- `FLTMGR!FltReleaseContext` at `0x1400390a2`
- `FLTMGR!FltReleaseContext` at `0x1400393a8`
- `FLTMGR!FltReleaseContext` at `0x14003941e`
- `FLTMGR!FltReleaseContext` at `0x140039646`
- `FLTMGR!FltReleaseContext` at `0x1400396d4`
- `FLTMGR!FltReleaseContext` at `0x14003906c`
- `FLTMGR!FltReleaseContext` at `0x1400390a2`
- `FLTMGR!FltReleaseContext` at `0x1400393a8`
- `FLTMGR!FltReleaseContext` at `0x14003941e`
- `FLTMGR!FltReleaseContext` at `0x140039646`
- `FLTMGR!FltReleaseContext` at `0x1400396d4`

## pseudocode

```c
__int64 __fastcall WofPostQueryInfoCallback(__int64 a1, __int64 a2)
{
  struct _EX_RUNDOWN_REF *v4; // rsi
  int v5; // ecx
  int v6; // edi
  unsigned __int64 v7; // rax
  __int64 v8; // rcx
  bool v9; // r15
  _DWORD *v11; // r12
  int v12; // eax
  int v13; // r13d
  __int64 v14; // r8
  __int64 v15; // r10
  unsigned int *v16; // r11
  int v17; // edx
  int v18; // r9d
  int v19; // r8d
  unsigned int v20; // edi
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rax
  __int64 (__fastcall *v24)(char *, char *, _QWORD); // rax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  unsigned int *v28; // rdi
  __int64 v29; // rax
  unsigned int v30; // r12d
  _WORD *v31; // r15
  char *v32; // r13
  unsigned int v33; // r14d
  char *v34; // rdi
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  PFLT_CONTEXT Context; // [rsp+30h] [rbp-58h] BYREF
  PFLT_CONTEXT v40; // [rsp+38h] [rbp-50h] BYREF
  struct _EX_RUNDOWN_REF *v41; // [rsp+40h] [rbp-48h]
  __int128 v42; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v43; // [rsp+90h] [rbp+8h]

  Context = 0;
  v4 = 0;
  v41 = 0;
  v5 = *(_DWORD *)(a1 + 24);
  if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147483643 )
    goto LABEL_6;
  v6 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
  v7 = (unsigned int)(v6 - 18);
  if ( (unsigned int)v7 > 0x3B || (v8 = 0x814000000030411LL, !_bittest64(&v8, v7)) )
  {
    if ( (unsigned int)(v6 - 4) > 1 )
      goto LABEL_6;
  }
  v9 = 1;
  if ( FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context) >= 0 )
  {
    v11 = Context;
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v11 + 32LL));
    v12 = v11[2] & 0xF000000;
    if ( v12 == 0x1000000 )
    {
      v9 = 0;
    }
    else
    {
      if ( v12 == 0x2000000 )
      {
        v13 = 0;
        v9 = *(_QWORD *)(a2 + 40) == *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 16LL) + 56LL);
LABEL_19:
        if ( (v11[2] & 0x20) != 0 )
          v9 = 1;
LABEL_21:
        if ( v13 >= 0 && (v11[2] & 2) == 0 )
        {
          if ( v9 )
          {
            v4 = (struct _EX_RUNDOWN_REF *)WofAcquireFileSystemRundown(*(_QWORD *)(a2 + 32));
            v41 = v4;
          }
          else
          {
            v4 = (struct _EX_RUNDOWN_REF *)(*(_QWORD *)v11 + 24LL);
            v41 = v4;
            ExAcquireRundownProtection(v4);
          }
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v11 + 32LL));
        KeLeaveCriticalRegion();
        if ( v13 < 0 )
        {
          *(_DWORD *)(a1 + 24) = v13;
          goto LABEL_6;
        }
        if ( (*((_DWORD *)Context + 2) & 2) == 0 && v9 && v6 != 22 )
          goto LABEL_6;
        goto LABEL_27;
      }
      if ( *(_QWORD *)(a2 + 40) )
      {
        v40 = 0;
        if ( FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &v40) != -1073741275 )
        {
          if ( (*(_DWORD *)v40 & 1) != 0 )
          {
            FltReleaseContext(v40);
            v13 = -1072103421;
            goto LABEL_21;
          }
          if ( (*(_DWORD *)v40 & 2) != 0 && v11[3] < 4u )
          {
            FltReleaseContext(v40);
            v9 = 0;
          }
          else
          {
            FltReleaseContext(v40);
          }
        }
      }
    }
    v13 = 0;
    goto LABEL_19;
  }
  if ( v6 != 22 )
    goto LABEL_6;
  v40 = 0;
  if ( (int)WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24)) < 0 )
    goto LABEL_6;
  if ( (*((_DWORD *)v40 + 14) & 1) != 0 )
  {
    FltReleaseContext(v40);
    goto LABEL_6;
  }
  FltReleaseContext(v40);
LABEL_27:
  v15 = *(_QWORD *)(a1 + 16);
  v16 = *(unsigned int **)(v15 + 40);
  v40 = v16;
  if ( v6 == 22 )
  {
    if ( Context )
    {
      if ( !v9 && (*((_DWORD *)Context + 2) & 2) == 0 )
      {
        v26 = *((unsigned int *)Context + 3);
        if ( (unsigned int)v26 < 4 )
        {
          v27 = 53 * v26;
          if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v27 * 8) )
          {
            v28 = v16;
            if ( qword_14001A280[v27 + 1] )
            {
              while ( 1 )
              {
                if ( v28[1] == 14 && RtlCompareMemory(v28 + 6, L"::$DATA", 0xEu) == 14 )
                {
                  v38 = ((__int64 (__fastcall *)(char *, unsigned int *, _QWORD))qword_14001A280[53
                                                                                               * *((unsigned int *)Context
                                                                                                 + 3)
                                                                                               + 1])(
                          (char *)Context + 64,
                          v28 + 4,
                          0);
                  if ( v38 < 0 )
                    break;
                }
                v29 = *v28;
                if ( (_DWORD)v29 )
                {
                  v28 = (unsigned int *)((char *)v28 + v29);
                  if ( v28 )
                    continue;
                }
                goto LABEL_87;
              }
              *(_DWORD *)(a1 + 24) = v38;
LABEL_87:
              v16 = (unsigned int *)v40;
            }
          }
        }
      }
    }
    if ( *(int *)(a1 + 24) >= 0 && *(_QWORD *)(a1 + 32) )
    {
      v42 = 0;
      v20 = 0;
      v43 = 0;
LABEL_36:
      v21 = 424LL * v20;
      if ( !*(PVOID *)((char *)&WPP_MAIN_CB.Dpc.DeferredContext + v21) )
        goto LABEL_37;
      v30 = 0;
      v31 = v16;
      v32 = (char *)&WPP_MAIN_CB.Dpc.DeferredContext + v21;
      v33 = 0;
      v34 = (char *)v40;
      while ( 1 )
      {
        *((_QWORD *)&v42 + 1) = v31 + 12;
        WORD1(v42) = v31[2];
        LOWORD(v42) = WORD1(v42);
        v35 = *((unsigned int *)v31 + 1);
        if ( (unsigned int)v35 > 0xC && RtlCompareMemory((char *)v31 + v35 + 12, L":$DATA", 0xCu) == 12 )
          LOWORD(v42) = v42 - 12;
        LOBYTE(v14) = 1;
        v36 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64))v32)(0, &v42, v14);
        v37 = *(unsigned int *)v31;
        if ( v36 == -1073741275 )
        {
          if ( !(_DWORD)v37 )
          {
            *(_DWORD *)&v34[v33] = 0;
            LODWORD(v37) = *(_DWORD *)(a1 + 32) - v30;
          }
          *(_QWORD *)(a1 + 32) -= (unsigned int)v37;
          v14 = *(_QWORD *)(a1 + 32);
          if ( v14 == v30 )
          {
LABEL_94:
            v4 = v41;
            v20 = v43;
            if ( !*(_QWORD *)(a1 + 32) )
              break;
LABEL_37:
            v43 = ++v20;
            v16 = (unsigned int *)v40;
            if ( v20 >= 4 )
              break;
            goto LABEL_36;
          }
          memmove(v31, (char *)v31 + *(unsigned int *)v31, v14 - v30);
        }
        else
        {
          if ( !(_DWORD)v37 )
            goto LABEL_94;
          v33 = v30;
          v30 += v37;
          v31 = (_WORD *)((char *)v31 + v37);
        }
        if ( !v31 )
          goto LABEL_94;
      }
    }
  }
  else
  {
    if ( v6 == 68 )
    {
LABEL_39:
      v17 = 60;
      v19 = 56;
LABEL_40:
      v18 = 40;
    }
    else
    {
      v17 = -1;
      if ( v6 == 34 )
      {
        v19 = 48;
        v18 = 32;
      }
      else
      {
        v18 = -1;
        if ( v6 == 4 )
        {
          v19 = 32;
        }
        else
        {
          v19 = -1;
          switch ( v6 )
          {
            case 5:
            case 28:
              v18 = 0;
              break;
            case 18:
              v19 = 32;
              goto LABEL_40;
            case 35:
              v19 = 0;
              v17 = 4;
              break;
            case 70:
            case 77:
              goto LABEL_39;
            default:
              break;
          }
        }
      }
    }
    if ( v19 >= 0
      && (*(_DWORD *)(a1 + 24) != -2147483643 || *(unsigned int *)(v15 + 24) >= (unsigned __int64)(v19 + 4LL)) )
    {
      v22 = *(unsigned int *)((char *)v16 + v19);
      if ( byte_140018454 )
        v22 &= ~0x400u;
      if ( byte_140018455 && (*((_DWORD *)Context + 2) & 2) == 0 )
        v22 &= ~0x200u;
      if ( !v22 )
        v22 = 128;
      *(unsigned int *)((char *)v16 + v19) = v22;
    }
    if ( byte_140018454
      && v17 >= 0
      && (*(_DWORD *)(a1 + 24) != -2147483643
       || *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL) >= (unsigned __int64)(v17 + 4LL)) )
    {
      *(unsigned int *)((char *)v16 + v17) = 0;
    }
    if ( v18 >= 0
      && (*(_DWORD *)(a1 + 24) != -2147483643
       || *(unsigned int *)(*(_QWORD *)(a1 + 16) + 24LL) >= (unsigned __int64)(v18 + 8LL))
      && (*((_DWORD *)Context + 2) & 2) == 0 )
    {
      v23 = *((unsigned int *)Context + 3);
      if ( (unsigned int)v23 < 4 )
      {
        if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 424 * v23) )
        {
          v24 = (__int64 (__fastcall *)(char *, char *, _QWORD))qword_14001A280[53 * v23 + 1];
          if ( v24 )
          {
            v25 = v24((char *)Context + 64, (char *)v16 + v18, 0);
            if ( v25 < 0 )
              *(_DWORD *)(a1 + 24) = v25;
          }
        }
      }
    }
  }
LABEL_6:
  if ( v4 )
    ExReleaseRundownProtection(v4);
  if ( Context )
    FltReleaseContext(Context);
  return 0;
}

```

## disassembly

```asm
0x140038f90  mov     [rsp+arg_8], rbx
0x140038f95  mov     [rsp+arg_10], rsi
0x140038f9a  mov     [rsp+arg_0], rcx
0x140038f9f  push    rdi
0x140038fa0  push    r12
0x140038fa2  push    r13
0x140038fa4  push    r14
0x140038fa6  push    r15
0x140038fa8  sub     rsp, 60h
0x140038fac  mov     r14, rdx
0x140038faf  mov     rbx, rcx
0x140038fb2  mov     [rsp+88h+Context], 0
0x140038fbb  xor     esi, esi
0x140038fbd  mov     [rsp+88h+var_48], rsi
0x140038fc2  mov     ecx, [rcx+18h]
0x140038fc5  mov     edx, 80000000h
0x140038fca  lea     eax, [rcx+rdx]
0x140038fcd  test    edx, eax
0x140038fcf  jz      short loc_14003904D
0x140038fd1  mov     rax, [rbx+10h]
0x140038fd5  mov     edi, [rax+20h]
0x140038fd8  lea     eax, [rdi-12h]
0x140038fdb  cmp     eax, 3Bh ; ';'
0x140038fde  ja      loc_1400396C3
0x140038fe4  mov     rcx, 814000000030411h
0x140038fee  bt      rcx, rax
0x140038ff2  jnb     loc_1400396C3
0x140038ff8  mov     r15b, 1
0x140038ffb  lea     r8, [rsp+88h+Context]; Context
0x140039000  mov     rdx, [r14+20h]; FileObject
0x140039004  mov     rcx, [r14+18h]; Instance
0x140039008  call    cs:__imp_FltGetStreamContext
0x14003900f  nop     dword ptr [rax+rax+00h]
0x140039014  test    eax, eax
0x140039016  jns     loc_1400390B3
0x14003901c  cmp     edi, 16h
0x14003901f  jz      short loc_14003907A
0x140039021  test    rsi, rsi
0x140039024  jnz     short loc_14003905B
0x140039026  mov     rcx, [rsp+88h+Context]; Context
0x14003902b  test    rcx, rcx
0x14003902e  jnz     short loc_14003906C
0x140039030  xor     eax, eax
0x140039032  lea     r11, [rsp+88h+var_28]
0x140039037  mov     rbx, [r11+38h]
0x14003903b  mov     rsi, [r11+40h]
0x14003903f  mov     rsp, r11
0x140039042  pop     r15
0x140039044  pop     r14
0x140039046  pop     r13
0x140039048  pop     r12
0x14003904a  pop     rdi
0x14003904b  retn
0x14003904d  cmp     ecx, 80000005h
0x140039053  jz      loc_140038FD1
0x140039059  jmp     short loc_140039021
0x14003905b  mov     rcx, rsi; RunRef
0x14003905e  call    cs:__imp_ExReleaseRundownProtection
0x140039065  nop     dword ptr [rax+rax+00h]
0x14003906a  jmp     short loc_140039026
0x14003906c  call    cs:__imp_FltReleaseContext
0x140039073  nop     dword ptr [rax+rax+00h]
0x140039078  jmp     short loc_140039030
0x14003907a  mov     [rsp+88h+var_50], rsi
0x14003907f  lea     rdx, [rsp+88h+var_50]
0x140039084  mov     rcx, [r14+18h]; Instance
0x140039088  call    WofGetVolumeContext
0x14003908d  test    eax, eax
0x14003908f  js      short loc_140039021
0x140039091  mov     rcx, [rsp+88h+var_50]; Context
0x140039096  mov     eax, [rcx+38h]
0x140039099  test    r15b, al
0x14003909c  jz      loc_1400393A8
0x1400390a2  call    cs:__imp_FltReleaseContext
0x1400390a9  nop     dword ptr [rax+rax+00h]
0x1400390ae  jmp     loc_140039021
0x1400390b3  mov     r12, [rsp+88h+Context]
0x1400390b8  call    cs:__imp_KeEnterCriticalRegion
0x1400390bf  nop     dword ptr [rax+rax+00h]
0x1400390c4  mov     rcx, [r12]
0x1400390c8  add     rcx, 20h ; ' '; FastMutex
0x1400390cc  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400390d3  nop     dword ptr [rax+rax+00h]
0x1400390d8  mov     eax, [r12+8]
0x1400390dd  and     eax, 0F000000h
0x1400390e2  cmp     eax, 1000000h
0x1400390e7  jnz     loc_1400393D0
0x1400390ed  xor     r15b, r15b
0x1400390f0  xor     r13d, r13d
0x1400390f3  mov     eax, [r12+8]
0x1400390f8  test    al, 20h
0x1400390fa  jz      short loc_1400390FF
0x1400390fc  mov     r15b, 1
0x1400390ff  test    r13d, r13d
0x140039102  js      short loc_140039132
0x140039104  mov     eax, [r12+8]
0x140039109  test    al, 2
0x14003910b  jnz     short loc_140039132
0x14003910d  test    r15b, r15b
0x140039110  jnz     loc_140039604
0x140039116  mov     rsi, [r12]
0x14003911a  add     rsi, 18h
0x14003911e  mov     [rsp+88h+var_48], rsi
0x140039123  mov     rcx, rsi; RunRef
0x140039126  call    cs:__imp_ExAcquireRundownProtection
0x14003912d  nop     dword ptr [rax+rax+00h]
0x140039132  mov     rcx, [r12]
0x140039136  add     rcx, 20h ; ' '; FastMutex
0x14003913a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140039141  nop     dword ptr [rax+rax+00h]
0x140039146  call    cs:__imp_KeLeaveCriticalRegion
0x14003914d  nop     dword ptr [rax+rax+00h]
0x140039152  test    r13d, r13d
0x140039155  js      loc_1400396E8
0x14003915b  mov     rax, [rsp+88h+Context]
0x140039160  mov     ecx, [rax+8]
0x140039163  test    cl, 2
0x140039166  jz      loc_1400393B9
0x14003916c  mov     r10, [rbx+10h]
0x140039170  mov     r11, [r10+28h]
0x140039174  mov     [rsp+88h+var_50], r11
0x140039179  cmp     edi, 16h
0x14003917c  jz      short loc_1400391B3
0x14003917e  lea     r14, cs:140000000h
0x140039185  cmp     edi, 44h ; 'D'
0x140039188  jz      loc_140039221; jumptable 00000001400395AA cases 70,77
0x14003918e  mov     edx, 0FFFFFFFFh
0x140039193  cmp     edi, 22h ; '"'
0x140039196  jz      loc_140039435
0x14003919c  mov     r9d, edx
0x14003919f  cmp     edi, 4
0x1400391a2  jnz     loc_140039584
0x1400391a8  mov     r8d, 20h ; ' '
0x1400391ae  jmp     def_1400395AA; jumptable 00000001400395AA default case, cases 6-17,19-27,29-34,36-69,71-76
0x1400391b3  mov     rcx, [rsp+88h+Context]
0x1400391b8  test    rcx, rcx
0x1400391bb  jnz     loc_140039446
0x1400391c1  lea     r14, cs:140000000h
0x1400391c8  cmp     dword ptr [rbx+18h], 0
0x1400391cc  jl      loc_140039021
0x1400391d2  cmp     qword ptr [rbx+20h], 0
0x1400391d7  jbe     loc_140039021
0x1400391dd  xorps   xmm0, xmm0
0x1400391e0  movups  [rsp+88h+var_40], xmm0
0x1400391e5  xor     edi, edi
0x1400391e7  mov     dword ptr [rsp+88h+arg_0], edi
0x1400391ee  xchg    ax, ax
0x1400391f0  mov     eax, edi
0x1400391f2  imul    rcx, rax, 1A8h
0x1400391f9  cmp     qword ptr [rcx+r14+1A1C8h], 0
0x140039202  jnz     loc_1400394BE
0x140039208  inc     edi
0x14003920a  mov     dword ptr [rsp+88h+arg_0], edi
0x140039211  cmp     edi, 4
0x140039214  mov     r11, [rsp+88h+var_50]
0x140039219  jnb     loc_140039021
0x14003921f  jmp     short loc_1400391F0
0x140039221  mov     edx, 3Ch ; '<'; jumptable 00000001400395AA cases 70,77
0x140039226  mov     r8d, 38h ; '8'
0x14003922c  mov     r9d, 28h ; '('
0x140039232  test    r8d, r8d; jumptable 00000001400395AA default case, cases 6-17,19-27,29-34,36-69,71-76
0x140039235  js      short loc_14003928A
0x140039237  cmp     dword ptr [rbx+18h], 80000005h
0x14003923e  jz      loc_14003932A
0x140039244  movsxd  r8, r8d
0x140039247  mov     rax, [rsp+88h+Context]
0x14003924c  mov     ecx, [rax+8]
0x14003924f  and     ecx, 2
0x140039252  mov     eax, [r8+r11]
0x140039256  mov     [rsp+88h+var_68], eax
0x14003925a  cmp     cs:byte_140018454, 0
0x140039261  jz      short loc_14003926B
0x140039263  btr     eax, 0Ah
0x140039267  mov     [rsp+88h+var_68], eax
0x14003926b  cmp     cs:byte_140018455, 0
0x140039272  jnz     loc_140039315
0x140039278  mov     ecx, 80h
0x14003927d  test    eax, eax
0x14003927f  cmovz   eax, ecx
0x140039282  mov     [rsp+88h+var_68], eax
0x140039286  mov     [r8+r11], eax
0x14003928a  cmp     cs:byte_140018454, 0
0x140039291  jz      short loc_14003929B
0x140039293  test    edx, edx
0x140039295  jns     loc_140039343
0x14003929b  test    r9d, r9d
0x14003929e  js      loc_14003938E
0x1400392a4  cmp     dword ptr [rbx+18h], 80000005h
0x1400392ab  jz      loc_14003935C
0x1400392b1  mov     rax, [rsp+88h+Context]
0x1400392b6  mov     ecx, [rax+8]
0x1400392b9  test    cl, 2
0x1400392bc  jnz     loc_14003938E
0x1400392c2  mov     rcx, [rsp+88h+Context]
0x1400392c7  mov     eax, [rcx+0Ch]
0x1400392ca  cmp     eax, 4
0x1400392cd  jnb     loc_14003938E
0x1400392d3  imul    rdx, rax, 1A8h
0x1400392da  cmp     byte ptr [rdx+r14+1A140h], 0
0x1400392e3  jz      loc_14003938E
0x1400392e9  mov     rax, [rdx+r14+1A288h]
0x1400392f1  test    rax, rax
0x1400392f4  jz      loc_14003938E
0x1400392fa  movsxd  rdx, r9d
0x1400392fd  add     rdx, r11
0x140039300  add     rcx, 40h ; '@'
0x140039304  xor     r8d, r8d
0x140039307  call    _guard_dispatch_icall
0x14003930c  test    eax, eax
0x14003930e  jns     short loc_14003938E
0x140039310  mov     [rbx+18h], eax
0x140039313  jmp     short loc_14003938E
0x140039315  test    ecx, ecx
0x140039317  jnz     loc_140039278
0x14003931d  btr     eax, 9
0x140039321  mov     [rsp+88h+var_68], eax
0x140039325  jmp     loc_140039278
0x14003932a  mov     ecx, [r10+18h]
0x14003932e  movsxd  rax, r8d
0x140039331  add     rax, 4
0x140039335  cmp     rcx, rax
0x140039338  jb      loc_14003928A
0x14003933e  jmp     loc_140039244
0x140039343  cmp     dword ptr [rbx+18h], 80000005h
0x14003934a  jz      short loc_140039375
0x14003934c  movsxd  rax, edx
0x14003934f  mov     dword ptr [rax+r11], 0
0x140039357  jmp     loc_14003929B
0x14003935c  mov     rax, [rbx+10h]
0x140039360  mov     ecx, [rax+18h]
0x140039363  movsxd  rax, r9d
0x140039366  add     rax, 8
0x14003936a  cmp     rcx, rax
0x14003936d  jnb     loc_1400392B1
0x140039373  jmp     short loc_14003938E
0x140039375  mov     rax, [rbx+10h]
0x140039379  mov     ecx, [rax+18h]
0x14003937c  movsxd  rax, edx
0x14003937f  add     rax, 4
0x140039383  cmp     rcx, rax
0x140039386  jb      loc_14003929B
0x14003938c  jmp     short loc_14003934C
0x14003938e  jmp     loc_140039021
0x140039393  mov     rcx, [rsp+88h+arg_0]
0x14003939b  mov     [rcx+18h], eax
0x14003939e  mov     rsi, [rsp+88h+var_48]
0x1400393a3  jmp     loc_140039021
0x1400393a8  call    cs:__imp_FltReleaseContext
0x1400393af  nop     dword ptr [rax+rax+00h]
0x1400393b4  jmp     loc_14003916C
0x1400393b9  test    r15b, r15b
0x1400393bc  jz      loc_14003916C
0x1400393c2  cmp     edi, 16h
0x1400393c5  jz      loc_14003916C
0x1400393cb  jmp     loc_140039021
0x1400393d0  cmp     eax, 2000000h
0x1400393d5  jz      loc_14003961A
0x1400393db  cmp     [r14+28h], rsi
0x1400393df  jz      loc_1400390F0
0x1400393e5  mov     [rsp+88h+var_50], rsi
0x1400393ea  lea     r8, [rsp+88h+var_50]; Context
0x1400393ef  mov     rdx, [r14+20h]; FileObject
0x1400393f3  mov     rcx, [r14+18h]; Instance
0x1400393f7  call    cs:__imp_FltGetStreamHandleContext
0x1400393fe  nop     dword ptr [rax+rax+00h]
0x140039403  cmp     eax, 0C0000225h
0x140039408  jz      loc_1400390F0
0x14003940e  mov     rcx, [rsp+88h+var_50]; Context
0x140039413  mov     eax, [rcx]
0x140039415  test    r15b, al
0x140039418  jz      loc_140039636
0x14003941e  call    cs:__imp_FltReleaseContext
0x140039425  nop     dword ptr [rax+rax+00h]
0x14003942a  mov     r13d, 0C0190003h
0x140039430  jmp     loc_1400390FF
0x140039435  mov     r8d, 30h ; '0'
0x14003943b  mov     r9d, 20h ; ' '
0x140039441  jmp     def_1400395AA; jumptable 00000001400395AA default case, cases 6-17,19-27,29-34,36-69,71-76
0x140039446  test    r15b, r15b
0x140039449  jnz     loc_1400391C1
0x14003944f  mov     eax, [rcx+8]
0x140039452  test    al, 2
0x140039454  jnz     loc_1400391C1
0x14003945a  mov     rax, [rsp+88h+Context]
0x14003945f  mov     ecx, [rax+0Ch]
0x140039462  lea     r14, cs:140000000h
0x140039469  cmp     ecx, 4
0x14003946c  jnb     loc_1400391C8
0x140039472  imul    rcx, 1A8h
0x140039479  cmp     [rcx+r14+1A140h], r15b
0x140039481  jz      loc_1400391C8
0x140039487  mov     rdi, r11
0x14003948a  cmp     qword ptr [rcx+r14+1A288h], 0
0x140039493  jz      loc_1400391C8
0x140039499  nop     dword ptr [rax+00000000h]
0x1400394a0  cmp     dword ptr [rdi+4], 0Eh
0x1400394a4  jz      loc_140039657
0x1400394aa  mov     eax, [rdi]
0x1400394ac  test    eax, eax
0x1400394ae  jnz     loc_1400396B5
  ... truncated ...
```
