# UdfNonCachedIo

- ea: `0x140046750`
- end: `0x140046d68`
- name: `UdfNonCachedIo`
- size: `1560`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, void *, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1400010f0`
- `0x140044f90`

## callees

- `0x140004484`
- `0x140009014`
- `0x14000a0ec`
- `0x14000a2e8`
- `0x14001bc30`
- `0x14001c080`
- `0x140046750`
- `0x140046d70`
- `0x14005610c`
- `0x1400563f0`
- `0x140058944`
- `0x140059540`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140046996`
- `ntoskrnl!IofCallDriver` at `0x140046996`
- `ntoskrnl!KeFlushIoBuffers` at `0x140046ce7`
- `ntoskrnl!KeFlushIoBuffers` at `0x140046ce7`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x140046a75`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x140046a95`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x140046a75`
- `ntoskrnl!ExSetResourceOwnerPointer` at `0x140046a95`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400469c8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400469c8`
- `ntoskrnl!KeClearEvent` at `0x1400469dc`
- `ntoskrnl!KeClearEvent` at `0x1400469dc`

## pseudocode

```c
__int64 __fastcall UdfNonCachedIo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        char *a5,
        __int64 a6,
        __int64 a7)
{
  char *v9; // r13
  int v10; // edi
  char v11; // r14
  __int64 v12; // rdx
  __int64 v13; // r9
  char v14; // r13
  unsigned int v15; // esi
  __int64 v16; // r12
  unsigned int v17; // r14d
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 (__fastcall *v21)(__int64, __int64, __int64); // rax
  __int64 v22; // rcx
  void *v23; // rdi
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  struct _ERESOURCE *v28; // rcx
  struct _ERESOURCE *v29; // rcx
  __int64 v30; // r14
  int v31; // ecx
  int v32; // ecx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 i; // r14
  char v36; // al
  __int64 v37; // rdx
  size_t Size; // [rsp+28h] [rbp-250h]
  char v40; // [rsp+60h] [rbp-218h] BYREF
  char v41; // [rsp+61h] [rbp-217h]
  int v42; // [rsp+64h] [rbp-214h]
  unsigned int v43; // [rsp+68h] [rbp-210h] BYREF
  char v44; // [rsp+6Ch] [rbp-20Ch]
  unsigned int v45; // [rsp+70h] [rbp-208h]
  int v46; // [rsp+74h] [rbp-204h]
  unsigned int v47; // [rsp+78h] [rbp-200h] BYREF
  int v48; // [rsp+7Ch] [rbp-1FCh]
  int v49[2]; // [rsp+80h] [rbp-1F8h]
  __int64 v50; // [rsp+88h] [rbp-1F0h]
  char *v51; // [rsp+90h] [rbp-1E8h]
  __int64 v52; // [rsp+98h] [rbp-1E0h]
  unsigned int v53; // [rsp+A0h] [rbp-1D8h]
  int v54; // [rsp+A4h] [rbp-1D4h]
  __int64 v55; // [rsp+A8h] [rbp-1D0h]
  __int64 v56; // [rsp+B0h] [rbp-1C8h]
  __int64 v57; // [rsp+B8h] [rbp-1C0h]
  char *v58; // [rsp+C0h] [rbp-1B8h]
  __int64 v59[46]; // [rsp+D0h] [rbp-1A8h] BYREF

  v50 = a3;
  *(_QWORD *)v49 = a2;
  v52 = a1;
  v9 = a5;
  v51 = a5;
  v56 = a6;
  v55 = a7;
  v10 = 0;
  v42 = 0;
  v43 = 0;
  v46 = 0;
  v47 = 0;
  v40 = 0;
  LOBYTE(v45) = 0;
  v11 = 1;
  v41 = *(_BYTE *)(a1 + 56);
  do
  {
    memset(v59, 0, 0x168u);
    LODWORD(Size) = a4;
    v14 = UdfPrepareBuffers(
            a1,
            v49[0],
            v9,
            v50,
            Size,
            (__int64)v59,
            (__int64)&v43,
            (__int64)&v47,
            (__int64)&v40,
            v56,
            v55);
    v15 = v43;
    if ( !v43 )
    {
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 48LL) = 0;
      v10 = 0;
      v42 = 0;
      goto LABEL_64;
    }
    v16 = v47;
    if ( v47 < a4 && (*(_DWORD *)(a1 + 28) & 4) == 0 )
      UdfRaiseStatusEx(a1, 3221225688LL, 0);
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 0x2000) != 0 )
    {
      v30 = *(_QWORD *)v49;
      if ( **(_WORD **)v49 == 2355 || (v31 = 0, (word_140025B56 & 2) != 0) )
        v31 = 6;
      *(_DWORD *)(a1 + 28) |= 4u;
      v10 = UdfRmwExecuteIoRuns(a1, v31);
      v42 = v10;
    }
    else
    {
      if ( v43 == 1 && !v14 && !v40 )
      {
        if ( v11 )
        {
          v17 = v59[1];
          if ( LODWORD(v59[1]) == a4 )
          {
            v18 = v59[0];
            v19 = *(_QWORD *)(a1 + 40);
            v20 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 184LL);
            v21 = (__int64 (__fastcall *)(__int64, __int64, __int64))UdfSingleSyncCompletionRoutine;
            if ( (*(_DWORD *)(a1 + 28) & 4) == 0 )
              v21 = UdfSingleAsyncCompletionRoutine;
            *(_QWORD *)(v20 - 16) = v21;
            *(_QWORD *)(v20 - 8) = v19;
            *(_BYTE *)(v20 - 69) = 0;
            *(_BYTE *)(v20 - 69) = 64;
            *(_BYTE *)(v20 - 69) = -64;
            *(_BYTE *)(v20 - 69) = -32;
            v22 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 184LL);
            *(_BYTE *)(v22 - 72) = *(_BYTE *)(a1 + 56);
            *(_DWORD *)(v22 - 64) = v17;
            *(_QWORD *)(v22 - 48) = v18;
            if ( (*(_DWORD *)(a1 + 28) & 0x20000) != 0 )
              *(_BYTE *)(v22 - 70) |= 4u;
            if ( (*(_DWORD *)(a1 + 28) & 0x100000) != 0 )
              *(_BYTE *)(v22 - 70) |= 0x20u;
            if ( (*(_DWORD *)(a1 + 28) & 0x2000) != 0 )
              *(_BYTE *)(v22 - 70) |= 2u;
            if ( (*(_DWORD *)(a1 + 28) & 4) != 0 )
            {
              v23 = 0;
            }
            else
            {
              v23 = (void *)(*(_QWORD *)(a1 + 40) | 3LL);
              *(_QWORD *)(*(_QWORD *)(a1 + 40) + 48LL) = v23;
            }
            v24 = *(_QWORD *)(a1 + 16);
            if ( (*(_DWORD *)(v24 + 48) & 0x200000) != 0 )
              UdfAcquireDeviceShared(a1, v24, v23);
            if ( v23 )
            {
              v28 = *(struct _ERESOURCE **)(*(_QWORD *)(a1 + 40) + 32LL);
              if ( v28 )
                ExSetResourceOwnerPointer(v28, v23);
              v29 = *(struct _ERESOURCE **)(*(_QWORD *)(a1 + 40) + 40LL);
              if ( v29 )
                ExSetResourceOwnerPointer(v29, v23);
            }
            IofCallDriver(*(PDEVICE_OBJECT *)(*(_QWORD *)(a1 + 16) + 24LL), *(PIRP *)(a1 + 8));
            v15 = 0;
            v43 = 0;
            v25 = *(_DWORD *)(a1 + 28);
            if ( (v25 & 4) != 0 )
            {
              KeWaitForSingleObject((PVOID)(*(_QWORD *)(a1 + 40) + 64LL), Executive, 0, 0, 0);
              KeClearEvent((PRKEVENT)(*(_QWORD *)(a1 + 40) + 64LL));
              v10 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 48LL);
              v42 = v10;
              v27 = *(_QWORD *)(a1 + 16);
              if ( (*(_DWORD *)(v27 + 48) & 0x200000) != 0 )
                UdfReleaseDevice(v26, v27, 0);
              if ( (*(_DWORD *)(*(_QWORD *)v49 + 212LL) & 0x80u) != 0 && v41 == 4 && v10 >= 0 )
                UdfSetMetaSectorState(a1, LODWORD(v59[8]), v17 >> *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL), 0);
              goto LABEL_64;
            }
            *(_DWORD *)(a1 + 28) = v25 & 0xFFFFFEFF;
LABEL_36:
            v10 = 259;
            v42 = 259;
            goto LABEL_64;
          }
        }
      }
      UdfMultipleAsync(a1, v12, v43, v59);
      v30 = *(_QWORD *)v49;
    }
    v32 = *(_DWORD *)(a1 + 28);
    if ( (v32 & 4) == 0 )
    {
      *(_DWORD *)(a1 + 28) = v32 & 0xFFFFFEFF;
      v15 = 0;
      v43 = 0;
      goto LABEL_36;
    }
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) & 0x2000) == 0 )
    {
      UdfWaitSync(a1);
      v10 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 48LL);
      v42 = v10;
      v34 = *(_QWORD *)(a1 + 16);
      if ( (*(_DWORD *)(v34 + 48) & 0x200000) != 0 )
        UdfReleaseDevice(v33, v34, 0);
    }
    if ( v10 < 0 )
      goto LABEL_64;
    if ( (*(_DWORD *)(v30 + 212) & 0x80u) != 0 && v41 == 4 )
    {
      v48 = 0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v48 = i;
        if ( (unsigned int)i >= v15 )
          break;
        UdfSetMetaSectorState(
          a1,
          LODWORD(v59[9 * i + 8]),
          (unsigned int)(LODWORD(v59[9 * i + 1]) >> *(_DWORD *)(*(_QWORD *)(a1 + 16) + 72LL)),
          0);
      }
    }
    if ( v14 )
    {
      v36 = UdfFinishBuffers(a1, v59, v15, 0);
      v37 = (unsigned __int8)v45;
      if ( v36 )
        v37 = 1;
      v45 = v37;
      v44 = v37;
    }
    else
    {
      v37 = v45;
    }
    v15 = 0;
    v43 = 0;
    a4 -= v16;
    v53 = a4;
    v50 += v16;
    v57 = v50;
    v9 = &v51[v16];
    v51 = v9;
    v58 = v9;
    v46 += v16;
    v54 = v46;
    v11 = 0;
  }
  while ( a4 );
  if ( (_BYTE)v37 )
  {
    LOBYTE(v37) = 1;
    KeFlushIoBuffers(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL), v37, 0);
  }
LABEL_64:
  if ( v15 )
  {
    LOBYTE(v13) = 1;
    UdfFinishBuffers(a1, v59, v15, v13);
  }
  if ( v10 == -1073741662 )
    *(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) |= 0x90u;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140046750  mov     [rsp+arg_10], rbx
0x140046755  mov     [rsp+arg_18], rsi
0x14004675a  push    rdi
0x14004675b  push    r12
0x14004675d  push    r13
0x14004675f  push    r14
0x140046761  push    r15
0x140046763  sub     rsp, 250h
0x14004676a  mov     rax, cs:__security_cookie
0x140046771  xor     rax, rsp
0x140046774  mov     [rsp+278h+var_38], rax
0x14004677c  mov     r15d, r9d
0x14004677f  mov     [rsp+278h+var_1F0], r8
0x140046787  mov     qword ptr [rsp+278h+var_1F8], rdx
0x14004678f  mov     rbx, rcx
0x140046792  mov     [rsp+278h+var_1E0], rcx
0x14004679a  mov     r13, [rsp+278h+arg_20]
0x1400467a2  mov     [rsp+278h+var_1E8], r13
0x1400467aa  mov     rax, [rsp+278h+arg_28]
0x1400467b2  mov     [rsp+278h+var_1C8], rax
0x1400467ba  mov     rax, [rsp+278h+arg_30]
0x1400467c2  mov     [rsp+278h+var_1D0], rax
0x1400467ca  xor     eax, eax
0x1400467cc  mov     edi, eax
0x1400467ce  mov     dword ptr [rsp+278h+var_218+4], eax
0x1400467d2  mov     dword ptr [rsp+278h+var_210], eax
0x1400467d6  mov     r12d, eax
0x1400467d9  mov     [rsp+278h+var_204], eax
0x1400467dd  mov     dword ptr [rsp+278h+var_200], eax
0x1400467e1  mov     byte ptr [rsp+278h+var_218], al
0x1400467e5  mov     byte ptr [rsp+278h+var_208], al
0x1400467e9  mov     r14b, 1
0x1400467ec  movzx   eax, byte ptr [rcx+38h]
0x1400467f0  mov     byte ptr [rsp+278h+var_218+1], al
0x1400467f4  xor     edx, edx; Val
0x1400467f6  mov     r8d, 168h; Size
0x1400467fc  lea     rcx, [rsp+278h+var_1A8]; void *
0x140046804  call    memset
0x140046809  mov     rax, [rsp+278h+var_1D0]
0x140046811  mov     [rsp+278h+var_220], rax; __int64
0x140046816  mov     rax, [rsp+278h+var_1C8]
0x14004681e  mov     [rsp+278h+var_228], rax; __int64
0x140046823  lea     rax, [rsp+278h+var_218]
0x140046828  mov     [rsp+278h+var_230], rax; __int64
0x14004682d  lea     rax, [rsp+278h+var_200]
0x140046832  mov     [rsp+278h+var_238], rax; __int64
0x140046837  lea     rax, [rsp+278h+var_210]
0x14004683c  mov     [rsp+278h+var_240], rax; __int64
0x140046841  lea     rax, [rsp+278h+var_1A8]
0x140046849  mov     [rsp+278h+var_248], rax; __int64
0x14004684e  mov     dword ptr [rsp+278h+Size], r15d; Size
0x140046853  mov     rax, [rsp+278h+var_1F0]
0x14004685b  mov     [rsp+278h+Timeout], rax; __int64
0x140046860  mov     r9d, r12d
0x140046863  mov     r8, r13; void *
0x140046866  mov     rdx, qword ptr [rsp+278h+var_1F8]; int
0x14004686e  mov     rcx, rbx; int
0x140046871  call    UdfPrepareBuffers
0x140046876  movzx   r13d, al
0x14004687a  mov     esi, dword ptr [rsp+278h+var_210]
0x14004687e  test    esi, esi
0x140046880  jz      loc_140046ABB
0x140046886  mov     r12d, dword ptr [rsp+278h+var_200]
0x14004688b  cmp     r12d, r15d
0x14004688e  jb      loc_140046ADA
0x140046894  mov     rax, [rbx+10h]
0x140046898  test    dword ptr [rax+30h], 2000h
0x14004689f  jnz     loc_140046B41
0x1400468a5  cmp     esi, 1
0x1400468a8  jnz     loc_140046B24
0x1400468ae  test    r13b, r13b
0x1400468b1  jnz     loc_140046B24
0x1400468b7  cmp     byte ptr [rsp+278h+var_218], r13b
0x1400468bc  jnz     loc_140046B24
0x1400468c2  test    r14b, r14b
0x1400468c5  jz      loc_140046B24
0x1400468cb  mov     r14d, [rsp+278h+var_1A0]
0x1400468d3  cmp     r14d, r15d
0x1400468d6  jnz     loc_140046B24
0x1400468dc  mov     r8, [rsp+278h+var_1A8]
0x1400468e4  mov     rcx, [rbx+28h]
0x1400468e8  mov     rax, [rbx+8]
0x1400468ec  mov     rdx, [rax+0B8h]
0x1400468f3  mov     eax, [rbx+1Ch]
0x1400468f6  test    al, 4
0x1400468f8  lea     rax, UdfSingleSyncCompletionRoutine
0x1400468ff  lea     r9, UdfSingleAsyncCompletionRoutine
0x140046906  cmovz   rax, r9
0x14004690a  mov     [rdx-10h], rax
0x14004690e  mov     [rdx-8], rcx
0x140046912  mov     [rdx-45h], r13b
0x140046916  mov     byte ptr [rdx-45h], 40h ; '@'
0x14004691a  mov     byte ptr [rdx-45h], 0C0h
0x14004691e  mov     byte ptr [rdx-45h], 0E0h
0x140046922  mov     rax, [rbx+8]
0x140046926  mov     rcx, [rax+0B8h]
0x14004692d  movzx   eax, byte ptr [rbx+38h]
0x140046931  mov     [rcx-48h], al
0x140046934  mov     [rcx-40h], r14d
0x140046938  mov     [rcx-30h], r8
0x14004693c  test    dword ptr [rbx+1Ch], 20000h
0x140046943  jnz     loc_140046AF5
0x140046949  test    dword ptr [rbx+1Ch], 100000h
0x140046950  jnz     loc_140046AD1
0x140046956  test    dword ptr [rbx+1Ch], 2000h
0x14004695d  jnz     loc_140046AFE
0x140046963  mov     eax, [rbx+1Ch]
0x140046966  test    al, 4
0x140046968  jz      loc_140046A51
0x14004696e  xor     edi, edi
0x140046970  mov     rdx, [rbx+10h]
0x140046974  test    dword ptr [rdx+30h], 200000h
0x14004697b  jnz     loc_140046B07
0x140046981  test    rdi, rdi
0x140046984  jnz     loc_140046A65
0x14004698a  mov     rcx, [rbx+10h]
0x14004698e  mov     rdx, [rbx+8]; Irp
0x140046992  mov     rcx, [rcx+18h]; DeviceObject
0x140046996  call    cs:__imp_IofCallDriver
0x14004699d  nop     dword ptr [rax+rax+00h]
0x1400469a2  xor     esi, esi
0x1400469a4  mov     dword ptr [rsp+278h+var_210], esi
0x1400469a8  mov     eax, [rbx+1Ch]
0x1400469ab  test    al, 4
0x1400469ad  jz      loc_140046AA6
0x1400469b3  mov     rcx, [rbx+28h]
0x1400469b7  add     rcx, 40h ; '@'; Object
0x1400469bb  mov     [rsp+278h+Timeout], rsi; Timeout
0x1400469c0  xor     r9d, r9d; Alertable
0x1400469c3  xor     r8d, r8d; WaitMode
0x1400469c6  xor     edx, edx; WaitReason
0x1400469c8  call    cs:__imp_KeWaitForSingleObject
0x1400469cf  nop     dword ptr [rax+rax+00h]
0x1400469d4  mov     rcx, [rbx+28h]
0x1400469d8  add     rcx, 40h ; '@'; Event
0x1400469dc  call    cs:__imp_KeClearEvent
0x1400469e3  nop     dword ptr [rax+rax+00h]
0x1400469e8  mov     rax, [rbx+8]
0x1400469ec  mov     edi, [rax+30h]
0x1400469ef  mov     dword ptr [rsp+278h+var_218+4], edi
0x1400469f3  mov     rdx, [rbx+10h]
0x1400469f7  test    dword ptr [rdx+30h], 200000h
0x1400469fe  jnz     loc_140046B17
0x140046a04  mov     rax, qword ptr [rsp+278h+var_1F8]
0x140046a0c  mov     eax, [rax+0D4h]
0x140046a12  test    al, al
0x140046a14  jns     loc_140046D07
0x140046a1a  cmp     byte ptr [rsp+278h+var_218+1], 4
0x140046a1f  jnz     loc_140046D07
0x140046a25  test    edi, edi
0x140046a27  js      loc_140046D07
0x140046a2d  mov     rcx, [rbx+10h]
0x140046a31  mov     ecx, [rcx+48h]
0x140046a34  shr     r14d, cl
0x140046a37  xor     r9d, r9d
0x140046a3a  mov     r8d, r14d
0x140046a3d  mov     edx, [rsp+278h+var_168]
0x140046a44  mov     rcx, rbx
0x140046a47  call    UdfSetMetaSectorState
0x140046a4c  jmp     loc_140046D07
0x140046a51  mov     rax, [rbx+28h]
0x140046a55  mov     rdi, rax
0x140046a58  or      rdi, 3
0x140046a5c  mov     [rax+30h], rdi
0x140046a60  jmp     loc_140046970
0x140046a65  mov     rax, [rbx+28h]
0x140046a69  mov     rcx, [rax+20h]; Resource
0x140046a6d  test    rcx, rcx
0x140046a70  jz      short loc_140046A81
0x140046a72  mov     rdx, rdi; OwnerPointer
0x140046a75  call    cs:__imp_ExSetResourceOwnerPointer
0x140046a7c  nop     dword ptr [rax+rax+00h]
0x140046a81  mov     rax, [rbx+28h]
0x140046a85  mov     rcx, [rax+28h]; Resource
0x140046a89  test    rcx, rcx
0x140046a8c  jz      loc_14004698A
0x140046a92  mov     rdx, rdi; OwnerPointer
0x140046a95  call    cs:__imp_ExSetResourceOwnerPointer
0x140046a9c  nop     dword ptr [rax+rax+00h]
0x140046aa1  jmp     loc_14004698A
0x140046aa6  btr     eax, 8
0x140046aaa  mov     [rbx+1Ch], eax
0x140046aad  mov     edi, 103h
0x140046ab2  mov     dword ptr [rsp+278h+var_218+4], edi
0x140046ab6  jmp     loc_140046D07
0x140046abb  mov     rax, [rbx+8]
0x140046abf  mov     dword ptr [rax+30h], 0
0x140046ac6  xor     edi, edi
0x140046ac8  mov     dword ptr [rsp+278h+var_218+4], edi
0x140046acc  jmp     loc_140046D07
0x140046ad1  or      byte ptr [rcx-46h], 20h
0x140046ad5  jmp     loc_140046956
0x140046ada  mov     eax, [rbx+1Ch]
0x140046add  test    al, 4
0x140046adf  jnz     loc_140046894
0x140046ae5  xor     r8d, r8d
0x140046ae8  mov     edx, 0C00000D8h
0x140046aed  mov     rcx, rbx
0x140046af0  call    UdfRaiseStatusEx
0x140046af5  or      byte ptr [rcx-46h], 4
0x140046af9  jmp     loc_140046949
0x140046afe  or      byte ptr [rcx-46h], 2
0x140046b02  jmp     loc_140046963
0x140046b07  mov     r8, rdi
0x140046b0a  mov     rcx, rbx
0x140046b0d  call    UdfAcquireDeviceShared
0x140046b12  jmp     loc_140046981
0x140046b17  xor     r8d, r8d
0x140046b1a  call    UdfReleaseDevice
0x140046b1f  jmp     loc_140046A04
0x140046b24  lea     r9, [rsp+278h+var_1A8]
0x140046b2c  mov     r8d, esi
0x140046b2f  mov     rcx, rbx
0x140046b32  call    UdfMultipleAsync
0x140046b37  mov     r14, qword ptr [rsp+278h+var_1F8]
0x140046b3f  jmp     short loc_140046B8C
0x140046b41  mov     r14, qword ptr [rsp+278h+var_1F8]
0x140046b49  mov     eax, 933h
0x140046b4e  cmp     [r14], ax
0x140046b52  jz      short loc_140046B5F
0x140046b54  xor     ecx, ecx
0x140046b56  test    byte ptr cs:word_140025B56, 2
0x140046b5d  jz      short loc_140046B64
0x140046b5f  mov     ecx, 6
0x140046b64  or      dword ptr [rbx+1Ch], 4
0x140046b68  cmp     byte ptr [rbx+38h], 4
0x140046b6c  setz    r9b
0x140046b70  mov     dword ptr [rsp+278h+Timeout], ecx; int
0x140046b74  lea     r8, [rsp+278h+var_1A8]
0x140046b7c  mov     edx, esi
0x140046b7e  mov     rcx, rbx; int
0x140046b81  call    UdfRmwExecuteIoRuns
0x140046b86  mov     edi, eax
0x140046b88  mov     dword ptr [rsp+278h+var_218+4], eax
0x140046b8c  mov     ecx, [rbx+1Ch]
0x140046b8f  test    cl, 4
0x140046b92  jz      loc_140046CF5
0x140046b98  mov     rcx, [rbx+10h]
0x140046b9c  test    dword ptr [rcx+30h], 2000h
0x140046ba3  jnz     short loc_140046BCD
0x140046ba5  mov     rcx, rbx
0x140046ba8  call    UdfWaitSync
0x140046bad  mov     rax, [rbx+8]
0x140046bb1  mov     edi, [rax+30h]
0x140046bb4  mov     dword ptr [rsp+278h+var_218+4], edi
0x140046bb8  mov     rdx, [rbx+10h]
0x140046bbc  mov     eax, [rdx+30h]
0x140046bbf  bt      eax, 15h
0x140046bc3  jnb     short loc_140046BCD
0x140046bc5  xor     r8d, r8d
0x140046bc8  call    UdfReleaseDevice
0x140046bcd  test    edi, edi
0x140046bcf  js      loc_140046D07
0x140046bd5  mov     eax, [r14+0D4h]
0x140046bdc  test    al, al
0x140046bde  jns     short loc_140046C34
0x140046be0  cmp     byte ptr [rsp+278h+var_218+1], 4
0x140046be5  jnz     short loc_140046C34
0x140046be7  mov     dword ptr [rsp+278h+var_200+4], 0
0x140046bef  xor     r14d, r14d
0x140046bf2  mov     dword ptr [rsp+278h+var_200+4], r14d
0x140046bf7  cmp     r14d, esi
0x140046bfa  jnb     short loc_140046C34
0x140046bfc  mov     eax, r14d
0x140046bff  lea     rcx, [r14+r14*8]
0x140046c03  lea     rdx, ds:0[rcx*8]
0x140046c0b  mov     rcx, [rbx+10h]
0x140046c0f  mov     r8d, [rsp+rdx+278h+var_1A0]
0x140046c17  mov     ecx, [rcx+48h]
0x140046c1a  shr     r8d, cl
0x140046c1d  xor     r9d, r9d
0x140046c20  mov     edx, [rsp+rdx+278h+var_168]
0x140046c27  mov     rcx, rbx
0x140046c2a  call    UdfSetMetaSectorState
0x140046c2f  inc     r14d
0x140046c32  jmp     short loc_140046BF2
0x140046c34  test    r13b, r13b
0x140046c37  jz      short loc_140046C6A
0x140046c39  xor     r9d, r9d
0x140046c3c  mov     r8d, esi
0x140046c3f  lea     rdx, [rsp+278h+var_1A8]
0x140046c47  mov     rcx, rbx
0x140046c4a  call    UdfFinishBuffers
0x140046c4f  mov     edx, [rsp+278h+var_208]
0x140046c53  movzx   edx, dl
0x140046c56  test    al, al
0x140046c58  mov     eax, 1
0x140046c5d  cmovnz  edx, eax
0x140046c60  mov     [rsp+278h+var_208], edx
0x140046c64  mov     byte ptr [rsp+278h+var_210+4], dl
0x140046c68  jmp     short loc_140046C6E
0x140046c6a  mov     edx, [rsp+278h+var_208]
0x140046c6e  xor     esi, esi
0x140046c70  mov     dword ptr [rsp+278h+var_210], esi
0x140046c74  sub     r15d, r12d
0x140046c77  mov     [rsp+278h+var_1D8], r15d
0x140046c7f  mov     rax, r12
0x140046c82  mov     rcx, [rsp+278h+var_1F0]
0x140046c8a  add     rcx, r12
0x140046c8d  mov     [rsp+278h+var_1F0], rcx
  ... truncated ...
```
