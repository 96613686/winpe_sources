# SkpsCreateThread

- ea: `0x140033b58`
- end: `0x14003414b`
- name: `SkpsCreateThread`
- size: `1523`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, installer_update`

## callers

- `0x140014dd0`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x14000e460`
- `0x14000e8e0`
- `0x140013900`
- `0x140013a64`
- `0x14002bd78`
- `0x140033b58`
- `0x140034154`
- `0x140034ccc`
- `0x14004bf4c`
- `0x140063694`
- `0x140095cd8`
- `0x140098344`
- `0x140098400`
- `0x1400a1950`
- `0x1400ae4a8`
- `0x1400af528`
- `0x1400af72c`
- `0x1400b156c`
- `0x1400b7230`
- `0x1400b74ec`
- `0x1400f3620`
- `0x1400f9a80`
- `0x1400fc7c0`
- `0x1400ff128`

## pseudocode

```c
__int64 __fastcall SkpsCreateThread(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned __int64 a6,
        __int64 a7,
        _DWORD *a8)
{
  __int16 v8; // r15
  __int64 v10; // r9
  unsigned __int16 v11; // si
  __int64 v12; // r14
  __int64 result; // rax
  __int64 v14; // r15
  _QWORD *StackBase; // rcx
  __int64 v16; // rcx
  __int64 v17; // r13
  int WorkerFactoryStartParameters; // esi
  _QWORD *v19; // rbx
  __int64 v20; // r13
  __int64 v21; // rax
  _QWORD *v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // r10
  __int64 v25; // rdx
  int v26; // eax
  char v27; // al
  __int64 *v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  char v34; // [rsp+40h] [rbp-148h]
  unsigned __int16 v35; // [rsp+44h] [rbp-144h] BYREF
  int v36; // [rsp+48h] [rbp-140h]
  __int64 v37; // [rsp+50h] [rbp-138h]
  unsigned __int64 v38; // [rsp+58h] [rbp-130h]
  __int64 v39; // [rsp+60h] [rbp-128h] BYREF
  __int64 v40; // [rsp+68h] [rbp-120h] BYREF
  __int64 v41; // [rsp+70h] [rbp-118h] BYREF
  __int64 v42; // [rsp+78h] [rbp-110h] BYREF
  __int64 v43; // [rsp+80h] [rbp-108h] BYREF
  __int64 v44; // [rsp+88h] [rbp-100h] BYREF
  __int64 v45; // [rsp+90h] [rbp-F8h]
  __int64 v46; // [rsp+98h] [rbp-F0h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-E8h]
  _DWORD *v48; // [rsp+A8h] [rbp-E0h]
  _QWORD v49[2]; // [rsp+B0h] [rbp-D8h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-C8h]
  __int64 v51; // [rsp+C8h] [rbp-C0h]
  __int64 v52; // [rsp+D0h] [rbp-B8h]
  __int128 v53; // [rsp+D8h] [rbp-B0h] BYREF
  _BYTE v54[24]; // [rsp+100h] [rbp-88h] BYREF
  __int64 v55; // [rsp+118h] [rbp-70h]

  v47 = a4;
  v8 = a2;
  v45 = a2;
  v46 = a3;
  v48 = a8;
  v41 = 0;
  v49[0] = 0;
  v49[1] = 0;
  v50 = 0;
  v51 = 0;
  v42 = 0;
  memset_0(v54, 0, 0x40u);
  v53 = 0;
  v11 = 0;
  v36 = 0;
  v35 = 0;
  v43 = 0;
  v44 = 0;
  v40 = 0;
  v12 = 0;
  v39 = 0;
  v52 = 0;
  if ( ((qword_140167138 + 4095 + (v8 & 0xFFF)) & 0xFFFFFFFFFFFFF000uLL) != 0x1000 )
    return 3221225485LL;
  result = SkpsReferenceProcessByHandle(a1, 0, &v41, v10);
  if ( (int)result >= 0 )
  {
    v14 = v41;
    if ( v41 == PsIumSystemProcess )
    {
      SkReleaseRundownProtection(v41 + 80, 0);
      return 3221225485LL;
    }
    StackBase = KeGetPcr()->NtTib.StackBase;
    if ( StackBase )
    {
      v16 = StackBase[18];
      if ( v16 )
        --*(_WORD *)(v16 + xmmword_140167150);
    }
    v17 = SkiAttachProcess(v14);
    v37 = v17;
    if ( _interlockedbittestandset((volatile signed __int32 *)v14, 7u) )
    {
      v34 = 0;
      v22 = KeGetPcr()->NtTib.StackBase;
      v19 = (_QWORD *)v22[33];
      if ( v19 )
      {
        if ( v19[6] || a6 != *((_DWORD *)v22 + 42) || v14 != v19[1] )
        {
          WorkerFactoryStartParameters = -1073741811;
          goto LABEL_46;
        }
        v20 = v19[2];
        v38 = v19[3];
        v23 = v19[4];
        v21 = v19[5];
        goto LABEL_27;
      }
      v24 = a6;
      if ( a6 >> 60 == 1 )
      {
        WorkerFactoryStartParameters = SkpspGetWorkerFactoryStartParameters(
                                         a6,
                                         (unsigned int)&v42,
                                         (unsigned int)&a6,
                                         (unsigned int)&v35,
                                         (__int64)&v43,
                                         (__int64)&v44);
        if ( WorkerFactoryStartParameters < 0 )
          goto LABEL_45;
        v38 = a6;
        v11 = v35;
        v36 = v35;
        v20 = v42;
        LODWORD(v23) = v43;
        LODWORD(v21) = v44;
        goto LABEL_27;
      }
      v20 = SkpspLoaderHotPatchNotify;
      if ( a6 != SkpspLoaderHotPatchNotify || (SkmmQueryImageAdditionalTablePages(1) & 0xFFFFF) == 0 )
      {
        if ( (*(_DWORD *)v14 & 0x10) == 0 )
        {
          WorkerFactoryStartParameters = -1073741811;
LABEL_44:
          v17 = v37;
LABEL_45:
          if ( WorkerFactoryStartParameters >= 0 )
          {
LABEL_54:
            SkiAttachProcess(v17);
            SkReleaseRundownProtection(v14 + 80, 0);
            v31 = KeGetPcr()->NtTib.StackBase;
            if ( v31 )
            {
              v32 = v31[18];
              if ( v32 )
              {
                if ( (*(_WORD *)(v32 + xmmword_140167150))++ == 0xFFFF
                  && *(_QWORD *)(v32 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v31[17]
                  && !*(_WORD *)(v32 + *((_QWORD *)&xmmword_140167150 + 1)) )
                {
                  SkiCheckForKernelApcDelivery(xmmword_140167160, v32, v29, v30);
                }
              }
            }
            return (unsigned int)WorkerFactoryStartParameters;
          }
LABEL_46:
          if ( v12 )
          {
            SkDeleteThreadSystemServiceCallBuffer(v12);
            SkReleaseRundownProtection(v12 + 216, 0);
            SkWaitForRundownProtectionRelease(v12 + 216);
            SkeDeleteThread(v12);
          }
          if ( (v54[10] & 1) != 0 )
            SkmmUnmapMdl(v54);
          if ( v40 )
          {
            SkpspDeleteTeb(v14);
          }
          else if ( v52 )
          {
            RtlFreeUserStack();
          }
          goto LABEL_54;
        }
        v20 = v24;
      }
      v21 = a7;
    }
    else
    {
      WorkerFactoryStartParameters = SkmmGetSecureImageInfo(*(_QWORD *)(v14 + 168), &v53);
      if ( WorkerFactoryStartParameters < 0 )
        goto LABEL_45;
      v19 = 0;
      v20 = *((_QWORD *)&v53 + 1) + v53 - *(_QWORD *)(v14 + 176);
      v21 = *(_QWORD *)(v14 + 160);
      v11 = 1024;
      v36 = 1024;
      v34 = 1;
    }
    v38 = v21;
    LODWORD(v23) = 0;
    LODWORD(v21) = 0;
LABEL_27:
    WorkerFactoryStartParameters = SkpspCreateTeb(&v40, v49, v14, a5, v11, v23, v21);
    if ( WorkerFactoryStartParameters >= 0 )
    {
      SkmmInitializeShortMdl(v54, v45, qword_140167138, &v46);
      WorkerFactoryStartParameters = SkmmMapMdl(v54, 2);
      if ( WorkerFactoryStartParameters >= 0 )
      {
        WorkerFactoryStartParameters = SkeCreateThread(v14, SkpUserThreadStart, &v39);
        if ( WorkerFactoryStartParameters < 0 )
        {
          v12 = v39;
        }
        else
        {
          v12 = v39;
          RtlWriteULong64ToUser(v40 + 72, 4 * (*(_DWORD *)(v39 + 168) | 0xE0000000));
          WorkerFactoryStartParameters = SkCreateThreadSystemServiceCallBuffer(v12);
          if ( WorkerFactoryStartParameters >= 0 )
          {
            if ( v19 )
            {
              SkobReferenceObject(v12);
              v19[6] = v12;
            }
            v25 = v40;
            *(_QWORD *)(v12 + 160) = v40;
            *(_QWORD *)(v12 + 184) = v25;
            *(_BYTE *)(v12 + 96) = 1;
            *(_QWORD *)(v12 + 136) = v45;
            *(_QWORD *)(v12 + 144) = v55;
            *(_QWORD *)(v12 + 152) = v47;
            *(_QWORD *)(v12 + 208) = a5;
            if ( (v36 & 0x400) != 0 )
              _interlockedbittestandset((volatile signed __int32 *)(v12 + 172), 0);
            SkpspCreateThreadContext(v12, v50, v20, v38);
            v26 = _InterlockedIncrement((volatile signed __int32 *)(v14 + 188));
            if ( v26 < 1 || v26 == 1 && !v34 )
              __fastfail(0xEu);
            v27 = SkAcquireSpinLockExclusive(v14 + 4);
            v28 = *(__int64 **)(v14 + 24);
            if ( *v28 != v14 + 16 )
              __fastfail(3u);
            *(_QWORD *)v12 = v14 + 16;
            *(_QWORD *)(v12 + 8) = v28;
            *v28 = v12;
            *(_QWORD *)(v14 + 24) = v12;
            LOBYTE(v28) = v27;
            SkReleaseSpinLockExclusive(v14 + 4, v28);
            _InterlockedAnd((volatile signed __int32 *)(v12 + 172), 0xFFFFFFEF);
            *v48 = *(_DWORD *)(v12 + 168);
            SkReleaseRundownProtection(v12 + 216, 0);
            WorkerFactoryStartParameters = 0;
          }
        }
      }
    }
    goto LABEL_44;
  }
  return result;
}

```

## disassembly

```asm
0x140033b58  mov     r11, rsp
0x140033b5b  push    rbx
0x140033b5c  push    rsi
0x140033b5d  push    rdi
0x140033b5e  push    r12
0x140033b60  push    r13
0x140033b62  push    r14
0x140033b64  push    r15
0x140033b66  sub     rsp, 150h
0x140033b6d  mov     rax, cs:__security_cookie
0x140033b74  xor     rax, rsp
0x140033b77  mov     [rsp+188h+var_48], rax
0x140033b7f  mov     [rsp+188h+var_E8], r9
0x140033b87  mov     r15, rdx
0x140033b8a  mov     [rsp+188h+var_F8], rdx
0x140033b92  mov     rbx, rcx
0x140033b95  mov     [r11-0F0h], r8
0x140033b9c  mov     rax, [rsp+188h+arg_38]
0x140033ba4  mov     [rsp+188h+var_E0], rax
0x140033bac  xor     edi, edi
0x140033bae  mov     [rsp+188h+var_118], rdi
0x140033bb3  mov     [r11-0D8h], rdi
0x140033bba  mov     [r11-0D0h], rdi
0x140033bc1  mov     [r11-0C8h], rdi
0x140033bc8  mov     [r11-0C0h], rdi
0x140033bcf  mov     [rsp+188h+var_110], rdi
0x140033bd4  xor     edx, edx; Val
0x140033bd6  lea     r8d, [rdi+40h]; Size
0x140033bda  lea     rcx, [r11-88h]; void *
0x140033be1  call    memset_0
0x140033be6  xorps   xmm0, xmm0
0x140033be9  movups  [rsp+188h+var_B0], xmm0
0x140033bf1  movzx   esi, di
0x140033bf4  mov     [rsp+188h+var_140], esi
0x140033bf8  mov     [rsp+188h+var_144], di
0x140033bfd  mov     [rsp+188h+var_108], rdi
0x140033c05  mov     [rsp+188h+var_100], rdi
0x140033c0d  mov     [rsp+188h+var_120], rdi
0x140033c12  mov     r14d, edi
0x140033c15  mov     [rsp+188h+var_128], rdi
0x140033c1a  mov     [rsp+188h+var_B8], rdi
0x140033c22  mov     ecx, r15d
0x140033c25  and     ecx, 0FFFh
0x140033c2b  mov     rax, cs:qword_140167138
0x140033c32  add     rax, 0FFFh
0x140033c38  add     rcx, rax
0x140033c3b  and     rcx, 0FFFFFFFFFFFFF000h
0x140033c42  cmp     rcx, 1000h
0x140033c49  jz      short loc_140033C55
0x140033c4b  mov     eax, 0C000000Dh
0x140033c50  jmp     loc_140034127
0x140033c55  lea     r8, [rsp+188h+var_118]
0x140033c5a  xor     edx, edx
0x140033c5c  mov     rcx, rbx
0x140033c5f  call    SkpsReferenceProcessByHandle
0x140033c64  test    eax, eax
0x140033c66  js      loc_140034127
0x140033c6c  mov     r15, [rsp+188h+var_118]
0x140033c71  cmp     r15, cs:PsIumSystemProcess
0x140033c78  jnz     short loc_140033C87
0x140033c7a  lea     rcx, [r15+50h]
0x140033c7e  xor     edx, edx
0x140033c80  call    SkReleaseRundownProtection
0x140033c85  jmp     short loc_140033C4B
0x140033c87  mov     rcx, gs:8
0x140033c90  test    rcx, rcx
0x140033c93  jz      short loc_140033CAD
0x140033c95  mov     rcx, [rcx+90h]
0x140033c9c  test    rcx, rcx
0x140033c9f  jz      short loc_140033CAD
0x140033ca1  mov     rax, qword ptr cs:xmmword_140167150
0x140033ca8  dec     word ptr [rcx+rax]
0x140033cac  nop
0x140033cad  mov     rcx, r15
0x140033cb0  call    SkiAttachProcess
0x140033cb5  mov     r13, rax
0x140033cb8  mov     [rsp+188h+var_138], rax
0x140033cbd  lock bts dword ptr [r15], 7
0x140033cc3  jb      short loc_140033D1D
0x140033cc5  lea     rdx, [rsp+188h+var_B0]
0x140033ccd  mov     rcx, [r15+0A8h]
0x140033cd4  call    SkmmGetSecureImageInfo
0x140033cd9  mov     esi, eax
0x140033cdb  mov     r12d, 1
0x140033ce1  test    eax, eax
0x140033ce3  js      loc_140034050
0x140033ce9  mov     rbx, rdi
0x140033cec  mov     r13, qword ptr [rsp+188h+var_B0]
0x140033cf4  sub     r13, [r15+0B0h]
0x140033cfb  add     r13, qword ptr [rsp+188h+var_B0+8]
0x140033d03  mov     rax, [r15+0A0h]
0x140033d0a  mov     esi, 400h
0x140033d0f  mov     [rsp+188h+var_140], esi
0x140033d13  mov     [rsp+188h+var_148], r12b
0x140033d18  jmp     loc_140033E39
0x140033d1d  mov     [rsp+188h+var_148], dil
0x140033d22  mov     rax, gs:8
0x140033d2b  mov     rbx, [rax+108h]
0x140033d32  test    rbx, rbx
0x140033d35  jz      short loc_140033D83
0x140033d37  cmp     [rbx+30h], rdi
0x140033d3b  jnz     short loc_140033D73
0x140033d3d  mov     eax, [rax+0A8h]
0x140033d43  cmp     [rsp+188h+arg_28], rax
0x140033d4b  jnz     short loc_140033D73
0x140033d4d  cmp     r15, [rbx+8]
0x140033d51  jnz     short loc_140033D73
0x140033d53  mov     r13, [rbx+10h]
0x140033d57  mov     rax, [rbx+18h]
0x140033d5b  mov     [rsp+188h+var_130], rax
0x140033d60  mov     rcx, [rbx+20h]
0x140033d64  mov     rax, [rbx+28h]
0x140033d68  mov     r12d, 1
0x140033d6e  jmp     loc_140033E44
0x140033d73  mov     esi, 0C000000Dh
0x140033d78  mov     r12d, 1
0x140033d7e  jmp     loc_140034054
0x140033d83  mov     r10, [rsp+188h+arg_28]
0x140033d8b  mov     rax, r10
0x140033d8e  shr     rax, 3Ch
0x140033d92  mov     r12d, 1
0x140033d98  cmp     al, r12b
0x140033d9b  jnz     short loc_140033E08
0x140033d9d  lea     rax, [rsp+188h+var_100]
0x140033da5  mov     [rsp+188h+var_160], rax
0x140033daa  lea     rax, [rsp+188h+var_108]
0x140033db2  mov     [rsp+188h+var_168], rax
0x140033db7  lea     r9, [rsp+188h+var_144]
0x140033dbc  lea     r8, [rsp+188h+arg_28]
0x140033dc4  lea     rdx, [rsp+188h+var_110]
0x140033dc9  mov     rcx, r10
0x140033dcc  call    SkpspGetWorkerFactoryStartParameters
0x140033dd1  mov     esi, eax
0x140033dd3  test    eax, eax
0x140033dd5  js      loc_140034050
0x140033ddb  mov     rax, [rsp+188h+arg_28]
0x140033de3  mov     [rsp+188h+var_130], rax
0x140033de8  movzx   esi, [rsp+188h+var_144]
0x140033ded  mov     [rsp+188h+var_140], esi
0x140033df1  mov     r13, [rsp+188h+var_110]
0x140033df6  mov     rcx, [rsp+188h+var_108]
0x140033dfe  mov     rax, [rsp+188h+var_100]
0x140033e06  jmp     short loc_140033E44
0x140033e08  mov     r13, cs:SkpspLoaderHotPatchNotify
0x140033e0f  cmp     r10, r13
0x140033e12  jnz     short loc_140033E23
0x140033e14  mov     ecx, r12d
0x140033e17  call    SkmmQueryImageAdditionalTablePages
0x140033e1c  test    eax, 0FFFFFh
0x140033e21  jnz     short loc_140033E31
0x140033e23  mov     eax, [r15]
0x140033e26  test    al, 10h
0x140033e28  jz      loc_140034046
0x140033e2e  mov     r13, r10
0x140033e31  mov     rax, [rsp+188h+arg_30]
0x140033e39  mov     [rsp+188h+var_130], rax
0x140033e3e  mov     rcx, rdi
0x140033e41  mov     rax, rdi
0x140033e44  mov     [rsp+188h+var_158], rax
0x140033e49  mov     [rsp+188h+var_160], rcx
0x140033e4e  mov     word ptr [rsp+188h+var_168], si
0x140033e53  mov     r9, [rsp+188h+arg_20]
0x140033e5b  mov     r8, r15
0x140033e5e  lea     rdx, [rsp+188h+var_D8]
0x140033e66  lea     rcx, [rsp+188h+var_120]
0x140033e6b  call    SkpspCreateTeb
0x140033e70  mov     esi, eax
0x140033e72  test    eax, eax
0x140033e74  js      loc_14003404B
0x140033e7a  lea     r9, [rsp+188h+var_F0]
0x140033e82  mov     r8, cs:qword_140167138
0x140033e89  mov     rdx, [rsp+188h+var_F8]
0x140033e91  lea     rcx, [rsp+188h+var_88]
0x140033e99  call    SkmmInitializeShortMdl
0x140033e9e  mov     edx, 2
0x140033ea3  lea     rcx, [rsp+188h+var_88]
0x140033eab  call    SkmmMapMdl
0x140033eb0  mov     esi, eax
0x140033eb2  test    eax, eax
0x140033eb4  js      loc_14003404B
0x140033eba  lea     r8, [rsp+188h+var_128]
0x140033ebf  lea     rdx, SkpUserThreadStart
0x140033ec6  mov     rcx, r15
0x140033ec9  call    SkeCreateThread
0x140033ece  mov     esi, eax
0x140033ed0  test    eax, eax
0x140033ed2  js      loc_14003403F
0x140033ed8  mov     r14, [rsp+188h+var_128]
0x140033edd  mov     edx, [r14+0A8h]
0x140033ee4  or      edx, 0E0000000h
0x140033eea  shl     edx, 2
0x140033eed  mov     rcx, [rsp+188h+var_120]
0x140033ef2  add     rcx, 48h ; 'H'
0x140033ef6  call    RtlWriteULong64ToUser
0x140033efb  nop
0x140033efc  mov     rcx, r14
0x140033eff  call    SkCreateThreadSystemServiceCallBuffer
0x140033f04  mov     esi, eax
0x140033f06  test    eax, eax
0x140033f08  js      loc_14003404B
0x140033f0e  test    rbx, rbx
0x140033f11  jz      short loc_140033F1F
0x140033f13  mov     rcx, r14
0x140033f16  call    SkobReferenceObject
0x140033f1b  mov     [rbx+30h], r14
0x140033f1f  mov     rdx, [rsp+188h+var_120]
0x140033f24  mov     [r14+0A0h], rdx
0x140033f2b  mov     [r14+0B8h], rdx
0x140033f32  mov     [r14+60h], r12b
0x140033f36  mov     rax, [rsp+188h+var_F8]
0x140033f3e  mov     [r14+88h], rax
0x140033f45  mov     rax, [rsp+188h+var_70]
0x140033f4d  mov     [r14+90h], rax
0x140033f54  mov     rax, [rsp+188h+var_E8]
0x140033f5c  mov     [r14+98h], rax
0x140033f63  mov     rax, [rsp+188h+arg_20]
0x140033f6b  mov     [r14+0D0h], rax
0x140033f72  mov     eax, 400h
0x140033f77  test    word ptr [rsp+188h+var_140], ax
0x140033f7c  jz      short loc_140033F88
0x140033f7e  lock bts dword ptr [r14+0ACh], 0
0x140033f88  mov     r9, [rsp+188h+var_130]
0x140033f8d  mov     r8, r13
0x140033f90  mov     rdx, [rsp+188h+var_C8]
0x140033f98  mov     rcx, r14
0x140033f9b  call    SkpspCreateThreadContext
0x140033fa0  mov     eax, r12d
0x140033fa3  lock xadd [r15+0BCh], eax
0x140033fac  add     eax, r12d
0x140033faf  cmp     eax, r12d
0x140033fb2  jl      short loc_140033FBD
0x140033fb4  jnz     short loc_140033FC4
0x140033fb6  cmp     [rsp+188h+var_148], dil
0x140033fbb  jnz     short loc_140033FC4
0x140033fbd  mov     ecx, 0Eh
0x140033fc2  int     29h; Win8: RtlFailFast(ecx)
0x140033fc4  lea     rcx, [r15+4]
0x140033fc8  call    SkAcquireSpinLockExclusive
0x140033fcd  lea     rcx, [r15+10h]
0x140033fd1  mov     rdx, [rcx+8]
0x140033fd5  cmp     [rdx], rcx
0x140033fd8  jz      short loc_140033FE1
0x140033fda  mov     ecx, 3
0x140033fdf  int     29h; Win8: RtlFailFast(ecx)
0x140033fe1  mov     [r14], rcx
0x140033fe4  mov     [r14+8], rdx
0x140033fe8  mov     [rdx], r14
0x140033feb  mov     [rcx+8], r14
0x140033fef  mov     dl, al
0x140033ff1  lea     rcx, [r15+4]
0x140033ff5  call    SkReleaseSpinLockExclusive
0x140033ffa  lock and dword ptr [r14+0ACh], 0FFFFFFEFh
0x140034003  mov     eax, [r14+0A8h]
0x14003400a  mov     rcx, [rsp+188h+var_E0]
0x140034012  mov     [rcx], eax
0x140034014  lea     rcx, [r14+0D8h]
0x14003401b  xor     edx, edx
0x14003401d  call    SkReleaseRundownProtection
0x140034022  mov     esi, edi
0x140034024  jmp     short loc_14003404B
0x140034026  mov     esi, eax
0x140034028  xor     edi, edi
0x14003402a  lea     r12d, [rdi+1]
0x14003402e  mov     r15, [rsp+188h+var_118]
0x140034033  mov     r14, [rsp+188h+var_128]
0x140034038  mov     r13, [rsp+188h+var_138]
0x14003403d  jmp     short loc_140034050
0x14003403f  mov     r14, [rsp+188h+var_128]
0x140034044  jmp     short loc_14003404B
0x140034046  mov     esi, 0C000000Dh
0x14003404b  mov     r13, [rsp+188h+var_138]
0x140034050  test    esi, esi
0x140034052  jns     short loc_1400340BF
0x140034054  test    r14, r14
0x140034057  jz      short loc_140034082
0x140034059  mov     rcx, r14
0x14003405c  call    SkDeleteThreadSystemServiceCallBuffer
0x140034061  lea     rbx, [r14+0D8h]
0x140034068  xor     edx, edx
0x14003406a  mov     rcx, rbx
0x14003406d  call    SkReleaseRundownProtection
0x140034072  mov     rcx, rbx
0x140034075  call    SkWaitForRundownProtectionRelease
0x14003407a  mov     rcx, r14
0x14003407d  call    SkeDeleteThread
0x140034082  test    [rsp+188h+var_7E], r12b
0x14003408a  jz      short loc_140034099
0x14003408c  lea     rcx, [rsp+188h+var_88]
0x140034094  call    SkmmUnmapMdl
0x140034099  mov     rdx, [rsp+188h+var_120]
0x14003409e  test    rdx, rdx
0x1400340a1  jz      short loc_1400340AD
0x1400340a3  mov     rcx, r15
0x1400340a6  call    SkpspDeleteTeb
0x1400340ab  jmp     short loc_1400340BF
0x1400340ad  mov     rcx, [rsp+188h+var_B8]
0x1400340b5  test    rcx, rcx
0x1400340b8  jz      short loc_1400340BF
0x1400340ba  call    RtlFreeUserStack
0x1400340bf  mov     rcx, r13
  ... truncated ...
```
