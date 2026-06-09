# CreateCallMonitors

- ea: `0x180003498`
- end: `0x1800038c4`
- name: `CreateCallMonitors`
- size: `1068`
- prototype: `__int64 __fastcall(unsigned __int64, int)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x180008910`
- `0x180011090`
- `0x180016d20`
- `0x180017be0`

## callees

- `0x180001f50`
- `0x180003498`
- `0x180003f58`
- `0x180005b24`
- `0x180006dec`
- `0x18001f620`
- `0x18002c8d4`
- `0x18002f778`
- `0x1800342d4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000389e`
- `KERNEL32!LeaveCriticalSection` at `0x18000389e`

## pseudocode

```c
__int64 __fastcall CreateCallMonitors(unsigned __int64 a1, int a2)
{
  BOOL v3; // r12d
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 result; // rax
  unsigned int v8; // esi
  __int64 v9; // r15
  int v10; // ecx
  BOOL v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // rcx
  BOOL v15; // [rsp+4Ch] [rbp-16Ch]
  unsigned int v16; // [rsp+50h] [rbp-168h]
  unsigned int v17; // [rsp+54h] [rbp-164h]
  unsigned int v18; // [rsp+58h] [rbp-160h]
  __int64 v19; // [rsp+60h] [rbp-158h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-150h] BYREF
  __int64 v21; // [rsp+70h] [rbp-148h]
  __int64 v22; // [rsp+78h] [rbp-140h]
  unsigned int v23[7]; // [rsp+90h] [rbp-128h] BYREF
  int v24; // [rsp+ACh] [rbp-10Ch]
  int v25; // [rsp+B0h] [rbp-108h]
  int v26; // [rsp+B4h] [rbp-104h]
  int v27; // [rsp+B8h] [rbp-100h]
  unsigned int v28[20]; // [rsp+E0h] [rbp-D8h] BYREF
  __int64 v29; // [rsp+130h] [rbp-88h]
  _BYTE v30[4]; // [rsp+140h] [rbp-78h] BYREF
  int v31; // [rsp+144h] [rbp-74h]
  int v33; // [rsp+1D0h] [rbp+18h]
  int v34; // [rsp+1D8h] [rbp+20h]

  v3 = 0;
  v31 = 0;
  memset_0(v30, 0, 0x44u);
  lpMem = v30;
  v21 = 0;
  v4 = *(_QWORD *)(a1 + 136);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    v3 = *(_QWORD *)(v4 + 24) == a1;
  v16 = *(_DWORD *)(a1 + 52);
  v17 = *(_DWORD *)(a1 + 160);
  v18 = *(_DWORD *)(a1 + 164);
  v5 = *(_QWORD *)(a1 + 16);
  v29 = v5;
  v6 = *(_QWORD *)(a1 + 8);
  if ( v6 )
    v6 = *(_QWORD *)(v6 + 16);
  v21 = v6;
  result = GetLineClientListFromLine(v5, &lpMem);
  v8 = result;
  if ( !(_DWORD)result )
  {
    v15 = 0;
    v33 = 0;
    while ( 1 )
    {
      v34 = result;
      if ( (unsigned int)result >= *(_DWORD *)lpMem )
        break;
      v19 = 0;
      v9 = *((_QWORD *)lpMem + result + 1);
      v22 = v9;
      if ( (*(_BYTE *)(v9 + 64) & 2) == 0 || v22 == v21 )
      {
        v10 = 1;
      }
      else
      {
        v10 = 0;
        v11 = (*(_QWORD *)(*(_QWORD *)(v22 + 8) + 8LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0xFFFFFFFFFFFFFFFEuLL
           || *(_QWORD *)(*(_QWORD *)(v22 + 8) + 8LL) == -3;
        v15 = v11;
      }
      if ( !v10 && !(unsigned int)CreatetCallClient(a1, v22, v15 ? 4 : 2, 1, 0, (__int64)&v19, a2) )
      {
        if ( a2 )
        {
          ++v8;
        }
        else
        {
          if ( !v33 )
          {
            v28[0] = 52;
            v28[2] = 0;
            v28[4] = 23;
            v28[6] = v16;
            v28[8] = 2;
            v28[10] = v17;
            v28[11] = v18;
            v28[12] = v3;
            v23[0] = 44;
            v23[2] = 0;
            v23[4] = 2;
            v23[6] = 0x8000;
            v27 = 0;
            v33 = 1;
          }
          v12 = *(unsigned int *)(*(_QWORD *)(v9 + 16) + 48LL);
          v13 = v9 + 168;
          if ( (unsigned int)v12 < 0x20000 )
          {
            v25 = 2;
          }
          else
          {
            if ( !(unsigned int)FMsgDisabled(v12, v9 + 168, 23) )
            {
              v28[1] = *(_DWORD *)(*(_QWORD *)(v9 + 16) + 28LL);
              v28[3] = *(_DWORD *)(v9 + 56);
              v28[5] = *(_DWORD *)(v9 + 72);
              v28[7] = *(_DWORD *)(v19 + 88);
              WriteEventBuffer(*(_QWORD *)(v9 + 8), v28);
            }
            v25 = 0;
            v13 = v9 + 168;
          }
          if ( !(unsigned int)FMsgDisabled(*(unsigned int *)(*(_QWORD *)(v9 + 16) + 48LL), v13, 2) )
          {
            v23[1] = *(_DWORD *)(*(_QWORD *)(v9 + 16) + 28LL);
            v23[3] = *(_DWORD *)(v19 + 88);
            v23[5] = *(_DWORD *)(v9 + 72);
            v26 = *(_DWORD *)(v9 + 56);
            v14 = *(_QWORD *)(v9 + 8);
            if ( (*(_QWORD *)(v14 + 8) & 0xFFFFFFFFFFFFFFFEuLL) == 0xFFFFFFFFFFFFFFFEuLL || *(_QWORD *)(v14 + 8) == -3 )
            {
              v24 = 2;
              v25 = 2;
            }
            else
            {
              v24 = 0;
            }
            WriteEventBuffer(v14, v23);
            ++v8;
          }
        }
      }
      result = (unsigned int)(v34 + 1);
    }
    if ( lpMem != v30 )
      ServerFree(lpMem);
    if ( (unsigned int)WaitForExclusivetCallAccess(a1, 1280065859) )
    {
      DoCallHubHashing(a1, 0);
      *(_DWORD *)(a1 + 36) = 1;
      LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (a1 >> 4)));
    }
    else
    {
      return (unsigned int)-2147483576;
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180003498  mov     [rsp+arg_8], edx
0x18000349c  mov     r11, rsp
0x18000349f  mov     [r11+8], rcx
0x1800034a3  push    rsi
0x1800034a4  push    rdi
0x1800034a5  push    r12
0x1800034a7  push    r14
0x1800034a9  push    r15
0x1800034ab  sub     rsp, 190h
0x1800034b2  mov     rdi, rcx
0x1800034b5  xor     r12d, r12d
0x1800034b8  mov     [rsp+1B8h+var_174], r12d
0x1800034bd  xor     eax, eax
0x1800034bf  mov     [r11-74h], eax
0x1800034c3  xor     edx, edx; Val
0x1800034c5  lea     r8d, [r12+44h]; Size
0x1800034ca  lea     rcx, [r11-78h]; void *
0x1800034ce  call    memset_0
0x1800034d3  lea     rax, [rsp+1B8h+var_78]
0x1800034db  mov     [rsp+1B8h+lpMem], rax
0x1800034e0  mov     [rsp+1B8h+var_148], r12
0x1800034e5  mov     rcx, [rdi+88h]
0x1800034ec  lea     rax, [rcx-1]
0x1800034f0  lea     r14d, [r12+1]
0x1800034f5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800034f9  ja      short loc_180003508
0x1800034fb  cmp     [rcx+18h], rdi
0x1800034ff  cmovz   r12d, r14d
0x180003503  mov     [rsp+1B8h+var_174], r12d
0x180003508  mov     eax, [rdi+34h]
0x18000350b  mov     [rsp+1B8h+var_168], eax
0x18000350f  mov     eax, [rdi+0A0h]
0x180003515  mov     [rsp+1B8h+var_164], eax
0x180003519  mov     eax, [rdi+0A4h]
0x18000351f  mov     [rsp+1B8h+var_160], eax
0x180003523  mov     rcx, [rdi+10h]
0x180003527  mov     [rsp+1B8h+var_88], rcx
0x18000352f  mov     rax, [rdi+8]
0x180003533  test    rax, rax
0x180003536  jz      short loc_18000353C
0x180003538  mov     rax, [rax+10h]
0x18000353c  mov     [rsp+1B8h+var_148], rax
0x180003541  lea     rdx, [rsp+1B8h+lpMem]
0x180003546  call    GetLineClientListFromLine
0x18000354b  mov     esi, eax
0x18000354d  mov     [rsp+1B8h+var_178], eax
0x180003551  test    eax, eax
0x180003553  jnz     loc_1800038B4
0x180003559  mov     [rsp+1B8h+var_16C], eax
0x18000355d  mov     [rsp+1B8h+arg_10], eax
0x180003564  mov     [rsp+1B8h+arg_18], eax
0x18000356b  mov     rcx, [rsp+1B8h+lpMem]; lpMem
0x180003570  cmp     eax, [rcx]
0x180003572  jnb     loc_180003851
0x180003578  mov     [rsp+1B8h+var_158], 0
0x180003581  mov     r10, [rcx+rax*8+8]
0x180003586  mov     r15, r10
0x180003589  mov     [rsp+1B8h+var_140], r10
0x18000358e  test    byte ptr [r10+40h], 2
0x180003593  jz      short loc_1800035CA
0x180003595  cmp     r10, [rsp+1B8h+var_148]
0x18000359a  jz      short loc_1800035CA
0x18000359c  xor     ecx, ecx
0x18000359e  mov     [rsp+1B8h+var_170], ecx
0x1800035a2  mov     rax, [r10+8]
0x1800035a6  mov     rdx, [rax+8]
0x1800035aa  mov     rax, rdx
0x1800035ad  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800035b1  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x1800035b5  jz      short loc_1800035C1
0x1800035b7  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800035bb  jz      short loc_1800035C1
0x1800035bd  xor     eax, eax
0x1800035bf  jmp     short loc_1800035C4
0x1800035c1  mov     eax, r14d
0x1800035c4  mov     [rsp+1B8h+var_16C], eax
0x1800035c8  jmp     short loc_1800035D1
0x1800035ca  mov     ecx, r14d
0x1800035cd  mov     [rsp+1B8h+var_170], ecx
0x1800035d1  jmp     short loc_1800035F8
0x1800035d3  mov     ecx, 1
0x1800035d8  mov     [rsp+1B8h+var_170], ecx
0x1800035dc  mov     r14d, ecx
0x1800035df  mov     rdi, [rsp+1B8h+arg_0]
0x1800035e7  mov     esi, [rsp+1B8h+var_178]
0x1800035eb  mov     r12d, [rsp+1B8h+var_174]
0x1800035f0  mov     r15, [rsp+1B8h+var_140]
0x1800035f5  mov     r10, r15
0x1800035f8  test    ecx, ecx
0x1800035fa  jnz     loc_180003842
0x180003600  mov     eax, [rsp+1B8h+var_16C]
0x180003604  neg     eax
0x180003606  sbb     r8d, r8d
0x180003609  and     r8d, 2
0x18000360d  add     r8d, 2
0x180003611  mov     eax, [rsp+1B8h+arg_8]
0x180003618  mov     [rsp+1B8h+var_188], eax
0x18000361c  lea     rax, [rsp+1B8h+var_158]
0x180003621  mov     [rsp+1B8h+var_190], rax
0x180003626  mov     [rsp+1B8h+var_198], ecx
0x18000362a  mov     r9d, r14d
0x18000362d  mov     rdx, r10
0x180003630  mov     rcx, rdi
0x180003633  call    CreatetCallClient
0x180003638  test    eax, eax
0x18000363a  jnz     loc_180003842
0x180003640  cmp     [rsp+1B8h+arg_8], eax
0x180003647  jz      short loc_180003655
0x180003649  add     esi, r14d
0x18000364c  mov     [rsp+1B8h+var_178], esi
0x180003650  jmp     loc_180003842
0x180003655  cmp     [rsp+1B8h+arg_10], 0
0x18000365d  jnz     loc_1800036F7
0x180003663  mov     [rsp+1B8h+var_D8], 34h ; '4'
0x18000366e  mov     [rsp+1B8h+var_D0], 0
0x180003679  mov     [rsp+1B8h+var_C8], 17h
0x180003684  mov     eax, [rsp+1B8h+var_168]
0x180003688  mov     [rsp+1B8h+var_C0], eax
0x18000368f  mov     [rsp+1B8h+var_B8], 2
0x18000369a  mov     eax, [rsp+1B8h+var_164]
0x18000369e  mov     [rsp+1B8h+var_B0], eax
0x1800036a5  mov     eax, [rsp+1B8h+var_160]
0x1800036a9  mov     [rsp+1B8h+var_AC], eax
0x1800036b0  mov     [rsp+1B8h+var_A8], r12d
0x1800036b8  mov     [rsp+1B8h+var_128], 2Ch ; ','
0x1800036c3  mov     [rsp+1B8h+var_120], 0
0x1800036ce  mov     [rsp+1B8h+var_118], 2
0x1800036d9  mov     [rsp+1B8h+var_110], 8000h
0x1800036e4  mov     [rsp+1B8h+var_100], 0
0x1800036ef  mov     [rsp+1B8h+arg_10], r14d
0x1800036f7  mov     rax, [r15+10h]
0x1800036fb  mov     ecx, [rax+30h]
0x1800036fe  lea     rax, [r15+0A8h]
0x180003705  cmp     ecx, 20000h
0x18000370b  jb      short loc_180003778
0x18000370d  xor     r9d, r9d
0x180003710  lea     r8d, [r9+17h]
0x180003714  mov     rdx, rax
0x180003717  call    FMsgDisabled
0x18000371c  test    eax, eax
0x18000371e  jnz     short loc_180003764
0x180003720  mov     rax, [r15+10h]
0x180003724  mov     ecx, [rax+1Ch]
0x180003727  mov     [rsp+1B8h+var_D4], ecx
0x18000372e  mov     eax, [r15+38h]
0x180003732  mov     [rsp+1B8h+var_CC], eax
0x180003739  mov     eax, [r15+48h]
0x18000373d  mov     [rsp+1B8h+var_C4], eax
0x180003744  mov     rax, [rsp+1B8h+var_158]
0x180003749  mov     ecx, [rax+58h]
0x18000374c  mov     [rsp+1B8h+var_BC], ecx
0x180003753  lea     rdx, [rsp+1B8h+var_D8]
0x18000375b  mov     rcx, [r15+8]
0x18000375f  call    WriteEventBuffer
0x180003764  mov     [rsp+1B8h+var_108], 0
0x18000376f  lea     rax, [r15+0A8h]
0x180003776  jmp     short loc_180003783
0x180003778  mov     [rsp+1B8h+var_108], 2
0x180003783  mov     rcx, [r15+10h]
0x180003787  mov     r9d, 8000h
0x18000378d  mov     r8d, 2
0x180003793  mov     rdx, rax
0x180003796  mov     ecx, [rcx+30h]
0x180003799  call    FMsgDisabled
0x18000379e  test    eax, eax
0x1800037a0  jnz     loc_180003842
0x1800037a6  mov     rax, [r15+10h]
0x1800037aa  mov     ecx, [rax+1Ch]
0x1800037ad  mov     [rsp+1B8h+var_124], ecx
0x1800037b4  mov     rax, [rsp+1B8h+var_158]
0x1800037b9  mov     ecx, [rax+58h]
0x1800037bc  mov     [rsp+1B8h+var_11C], ecx
0x1800037c3  mov     eax, [r15+48h]
0x1800037c7  mov     [rsp+1B8h+var_114], eax
0x1800037ce  mov     eax, [r15+38h]
0x1800037d2  mov     [rsp+1B8h+var_104], eax
0x1800037d9  mov     rcx, [r15+8]
0x1800037dd  mov     rax, [rcx+8]
0x1800037e1  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800037e5  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x1800037e9  jz      short loc_1800037FF
0x1800037eb  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFDh
0x1800037f0  jz      short loc_1800037FF
0x1800037f2  mov     [rsp+1B8h+var_10C], 0
0x1800037fd  jmp     short loc_180003815
0x1800037ff  mov     [rsp+1B8h+var_10C], 2
0x18000380a  mov     [rsp+1B8h+var_108], 2
0x180003815  lea     rdx, [rsp+1B8h+var_128]
0x18000381d  call    WriteEventBuffer
0x180003822  add     esi, r14d
0x180003825  mov     [rsp+1B8h+var_178], esi
0x180003829  jmp     short loc_180003842
0x18000382b  mov     r14d, 1
0x180003831  mov     rdi, [rsp+1B8h+arg_0]
0x180003839  mov     esi, [rsp+1B8h+var_178]
0x18000383d  mov     r12d, [rsp+1B8h+var_174]
0x180003842  mov     eax, [rsp+1B8h+arg_18]
0x180003849  add     eax, r14d
0x18000384c  jmp     loc_180003564
0x180003851  lea     rax, [rsp+1B8h+var_78]
0x180003859  cmp     rcx, rax
0x18000385c  jz      short loc_180003863
0x18000385e  call    ServerFree
0x180003863  mov     edx, 4C4C4143h
0x180003868  mov     rcx, rdi
0x18000386b  call    WaitForExclusivetCallAccess
0x180003870  test    eax, eax
0x180003872  jz      short loc_1800038A6
0x180003874  xor     edx, edx
0x180003876  mov     rcx, rdi
0x180003879  call    DoCallHubHashing
0x18000387e  mov     [rdi+24h], r14d
0x180003882  shr     rdi, 4
0x180003886  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18000388c  and     rdi, rax
0x18000388f  lea     rcx, [rdi+rdi*4]
0x180003893  mov     rax, cs:gLockTable
0x18000389a  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18000389e  call    cs:__imp_LeaveCriticalSection
0x1800038a4  jmp     short loc_1800038AB
0x1800038a6  mov     esi, 80000048h
0x1800038ab  mov     eax, esi
0x1800038ad  jmp     short loc_1800038B4
0x1800038af  mov     eax, 80000048h
0x1800038b4  add     rsp, 190h
0x1800038bb  pop     r15
0x1800038bd  pop     r14
0x1800038bf  pop     r12
0x1800038c1  pop     rdi
0x1800038c2  pop     rsi
0x1800038c3  retn
```
