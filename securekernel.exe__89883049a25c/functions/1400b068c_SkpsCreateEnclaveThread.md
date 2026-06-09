# SkpsCreateEnclaveThread

- ea: `0x1400b068c`
- end: `0x1400b0a4e`
- name: `SkpsCreateEnclaveThread`
- size: `962`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, char, _QWORD *)`
- caller_count: `3`
- callee_count: `17`
- tags: ``

## callers

- `0x14006ad64`
- `0x14006b7a8`
- `0x1400b04d8`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x14000f0f0`
- `0x140021bd0`
- `0x140034154`
- `0x140034ccc`
- `0x140037e68`
- `0x14004fff0`
- `0x140098344`
- `0x1400af528`
- `0x1400af72c`
- `0x1400b068c`
- `0x1400b0b38`
- `0x1400b0d18`
- `0x1400b156c`
- `0x1400fc7c0`
- `0x1400ff128`

## pseudocode

```c
__int64 __fastcall SkpsCreateEnclaveThread(__int64 a1, __int64 a2, _QWORD *a3, char a4, _QWORD *a5)
{
  __int64 v9; // rsi
  __int16 v10; // ax
  __int64 Pool; // rax
  _QWORD *v12; // r15
  int Teb; // r14d
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  __m128i v16; // xmm2
  __int64 i; // rax
  __int64 j; // rax
  unsigned __int64 v19; // rdx
  __int64 v20; // rdx
  char v21; // al
  _QWORD *v22; // rdx
  __int64 v24; // [rsp+40h] [rbp-78h] BYREF
  unsigned __int64 v25; // [rsp+48h] [rbp-70h] BYREF
  unsigned __int64 v26; // [rsp+50h] [rbp-68h] BYREF
  __int64 v27; // [rsp+58h] [rbp-60h]
  _QWORD v28[2]; // [rsp+60h] [rbp-58h] BYREF
  __int64 v29; // [rsp+70h] [rbp-48h]
  __int128 v30; // [rsp+78h] [rbp-40h]
  __int64 v31; // [rsp+D0h] [rbp+18h] BYREF

  v25 = 0;
  v26 = 0;
  v28[0] = 0;
  v28[1] = 0;
  v30 = 0;
  v29 = 0;
  v31 = 0;
  v9 = 0;
  v24 = 0;
  v10 = ~(8 * *(_WORD *)a1) & 0x400;
  if ( !a3 )
  {
    v12 = 0;
    v27 = 0;
    Teb = SkpspCreateTeb((unsigned int)&v31, (unsigned int)v28, a1, 0, v10, 0, 0);
    if ( Teb < 0 )
      goto LABEL_31;
    goto LABEL_7;
  }
  Pool = SkAllocatePool(512, 64, 1480873029);
  v12 = (_QWORD *)Pool;
  v27 = Pool;
  if ( Pool )
  {
    *(_QWORD *)(Pool + 32) = 0;
    *(_QWORD *)(Pool + 24) = a2;
    Teb = SkpspInsertEnclaveThreadNode(a1, Pool);
    if ( Teb < 0 )
    {
      SkFreePool(512, v12);
      v12 = 0;
      goto LABEL_31;
    }
LABEL_7:
    Teb = SkeCreateThread(a1, &SkpUserThreadReturn, &v24);
    if ( Teb < 0 )
    {
      v9 = v24;
    }
    else
    {
      v14 = SkmmReserveMappingAddress(4096);
      v9 = v24;
      *(_QWORD *)(v24 + 256) = v14;
      if ( !v14 )
        goto LABEL_3;
      if ( a3 )
      {
        SkmmGetEnclaveInformation(&v25, &v26);
        v15 = v25;
        if ( a4 )
        {
          v16 = _mm_unpacklo_epi64((__m128i)v25, (__m128i)v25);
          for ( i = 0; i != 4; i += 2 )
            *(__m128i *)&a3[i] = _mm_add_epi64(v16, _mm_loadu_si128((const __m128i *)&a3[i]));
          for ( j = 0; j != 4; ++j )
            a3[j + 4] += v15;
        }
        v19 = v26;
        if ( a3[4] - v15 >= v26
          || a3[6] - v15 >= v26
          || a3[5] - v15 >= v26
          || a3[7] - v15 >= v26
          || (v12[5] = a3[4], v12[6] = a3[6], v29 = a3[5], v12[7] = a3[7], *a3 - v15 >= v19)
          || a3[1] - v15 >= v19 )
        {
          Teb = -1073741503;
          goto LABEL_32;
        }
        *(_QWORD *)(v9 + 176) = *a3;
        *(_QWORD *)(v9 + 184) = a3[1];
        _InterlockedOr((volatile signed __int32 *)(v9 + 172), 0x800u);
        v12[4] = v9;
      }
      else
      {
        RtlWriteULong64ToUser(v31 + 72, 4 * (*(_DWORD *)(v9 + 168) | 0xE0000000));
        v20 = v31;
        *(_QWORD *)(v9 + 160) = v31;
        *(_QWORD *)(v9 + 184) = v20;
      }
      *(_BYTE *)(v9 + 96) = 1;
      SkpspCreateThreadContext(v9, v29, 0, 0);
      v21 = SkAcquireSpinLockExclusive(a1 + 4);
      v22 = *(_QWORD **)(a1 + 24);
      if ( *v22 != a1 + 16 )
        __fastfail(3u);
      *(_QWORD *)v9 = a1 + 16;
      *(_QWORD *)(v9 + 8) = v22;
      *v22 = v9;
      *(_QWORD *)(a1 + 24) = v9;
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 188));
      _InterlockedOr((volatile signed __int32 *)a1, 0x80u);
      if ( v12 )
      {
        *(_QWORD *)(v9 + 296) = v12;
        v12[4] = v9;
      }
      LOBYTE(v22) = v21;
      SkReleaseSpinLockExclusive(a1 + 4, v22);
      v31 = 0;
      Teb = 0;
      if ( a5 )
        *a5 = v9;
    }
LABEL_31:
    if ( Teb >= 0 )
      goto LABEL_40;
    goto LABEL_32;
  }
LABEL_3:
  Teb = -1073741670;
LABEL_32:
  if ( v9 )
  {
    SkReleaseRundownProtection(v9 + 216, 0);
    SkWaitForRundownProtectionRelease(v9 + 216);
    SkpspDeleteEnclaveThread(v9);
    v9 = 0;
  }
  if ( v31 )
  {
    SkpspDeleteTeb(a1);
  }
  else if ( *((_QWORD *)&v30 + 1) )
  {
    RtlFreeUserStack();
  }
  if ( v12 )
    SkFreePool(512, v12);
LABEL_40:
  if ( v9 )
    SkReleaseRundownProtection(v9 + 216, 0);
  return (unsigned int)Teb;
}

```

## disassembly

```asm
0x1400b068c  mov     rax, rsp
0x1400b068f  mov     [rax+10h], rbx
0x1400b0693  mov     [rax+8], rcx
0x1400b0697  push    rsi
0x1400b0698  push    r12
0x1400b069a  push    r13
0x1400b069c  push    r14
0x1400b069e  push    r15
0x1400b06a0  sub     rsp, 90h
0x1400b06a7  mov     r13b, r9b
0x1400b06aa  mov     rbx, r8
0x1400b06ad  mov     r14, rdx
0x1400b06b0  mov     r12, rcx
0x1400b06b3  mov     qword ptr [rax-70h], 0
0x1400b06bb  mov     qword ptr [rax-68h], 0
0x1400b06c3  mov     qword ptr [rax-58h], 0
0x1400b06cb  mov     qword ptr [rax-50h], 0
0x1400b06d3  xorps   xmm0, xmm0
0x1400b06d6  movdqu  xmmword ptr [rax-40h], xmm0
0x1400b06db  mov     qword ptr [rax-48h], 0
0x1400b06e3  mov     qword ptr [rax+18h], 0
0x1400b06eb  xor     esi, esi
0x1400b06ed  mov     [rax-78h], rsi
0x1400b06f1  movzx   eax, word ptr [rcx]
0x1400b06f4  shl     ax, 3
0x1400b06f8  not     ax
0x1400b06fb  mov     ecx, 400h
0x1400b0700  and     ax, cx
0x1400b0703  test    r8, r8
0x1400b0706  jz      short loc_1400B0762
0x1400b0708  lea     edx, [rsi+40h]
0x1400b070b  mov     ecx, 200h
0x1400b0710  mov     r8d, 58445445h
0x1400b0716  call    SkAllocatePool
0x1400b071b  mov     r15, rax
0x1400b071e  mov     [rsp+0B8h+var_60], rax
0x1400b0723  test    rax, rax
0x1400b0726  jnz     short loc_1400B0733
0x1400b0728  mov     r14d, 0C000009Ah
0x1400b072e  jmp     loc_1400B09BB
0x1400b0733  mov     [rax+20h], rsi
0x1400b0737  mov     [rax+18h], r14
0x1400b073b  mov     rdx, r15
0x1400b073e  mov     rcx, r12
0x1400b0741  call    SkpspInsertEnclaveThreadNode
0x1400b0746  mov     r14d, eax
0x1400b0749  test    eax, eax
0x1400b074b  jns     short loc_1400B079C
0x1400b074d  mov     rdx, r15
0x1400b0750  mov     ecx, 200h
0x1400b0755  call    SkFreePool
0x1400b075a  xor     r15d, r15d
0x1400b075d  jmp     loc_1400B09B6
0x1400b0762  xor     r15d, r15d
0x1400b0765  mov     [rsp+0B8h+var_60], r15
0x1400b076a  mov     [rsp+0B8h+var_88], rsi
0x1400b076f  mov     [rsp+0B8h+var_90], rsi
0x1400b0774  mov     [rsp+0B8h+var_98], ax
0x1400b0779  xor     r9d, r9d
0x1400b077c  mov     r8, r12
0x1400b077f  lea     rdx, [rsp+0B8h+var_58]
0x1400b0784  lea     rcx, [rsp+0B8h+arg_10]
0x1400b078c  call    SkpspCreateTeb
0x1400b0791  mov     r14d, eax
0x1400b0794  test    eax, eax
0x1400b0796  js      loc_1400B09B6
0x1400b079c  lea     r8, [rsp+0B8h+var_78]
0x1400b07a1  lea     rdx, SkpUserThreadReturn
0x1400b07a8  mov     rcx, r12
0x1400b07ab  call    SkeCreateThread
0x1400b07b0  mov     r14d, eax
0x1400b07b3  test    eax, eax
0x1400b07b5  js      loc_1400B09B1
0x1400b07bb  mov     ecx, 1000h
0x1400b07c0  call    SkmmReserveMappingAddress
0x1400b07c5  mov     rsi, [rsp+0B8h+var_78]
0x1400b07ca  mov     [rsi+100h], rax
0x1400b07d1  test    rax, rax
0x1400b07d4  jz      loc_1400B0728
0x1400b07da  test    rbx, rbx
0x1400b07dd  jz      loc_1400B08D0
0x1400b07e3  lea     rdx, [rsp+0B8h+var_68]
0x1400b07e8  lea     rcx, [rsp+0B8h+var_70]
0x1400b07ed  call    SkmmGetEnclaveInformation
0x1400b07f2  mov     rcx, [rsp+0B8h+var_70]
0x1400b07f7  test    r13b, r13b
0x1400b07fa  jz      short loc_1400B0833
0x1400b07fc  movq    xmm2, rcx
0x1400b0801  punpcklqdq xmm2, xmm2
0x1400b0805  xor     eax, eax
0x1400b0807  movdqu  xmm0, xmmword ptr [rbx+rax*8]
0x1400b080c  movdqa  xmm1, xmm2
0x1400b0810  paddq   xmm1, xmm0
0x1400b0814  movdqu  xmmword ptr [rbx+rax*8], xmm1
0x1400b0819  add     rax, 2
0x1400b081d  cmp     rax, 4
0x1400b0821  jnz     short loc_1400B0807
0x1400b0823  xor     eax, eax
0x1400b0825  add     [rbx+rax*8+20h], rcx
0x1400b082a  inc     rax
0x1400b082d  cmp     rax, 4
0x1400b0831  jnz     short loc_1400B0825
0x1400b0833  mov     r8, [rbx+20h]
0x1400b0837  mov     rax, r8
0x1400b083a  sub     rax, rcx
0x1400b083d  mov     rdx, [rsp+0B8h+var_68]
0x1400b0842  cmp     rax, rdx
0x1400b0845  jnb     short loc_1400B08C5
0x1400b0847  mov     rax, [rbx+30h]
0x1400b084b  sub     rax, rcx
0x1400b084e  cmp     rax, rdx
0x1400b0851  jnb     short loc_1400B08C5
0x1400b0853  mov     rax, [rbx+28h]
0x1400b0857  sub     rax, rcx
0x1400b085a  cmp     rax, rdx
0x1400b085d  jnb     short loc_1400B08C5
0x1400b085f  mov     rax, [rbx+38h]
0x1400b0863  sub     rax, rcx
0x1400b0866  cmp     rax, rdx
0x1400b0869  jnb     short loc_1400B08C5
0x1400b086b  mov     [r15+28h], r8
0x1400b086f  mov     rax, [rbx+30h]
0x1400b0873  mov     [r15+30h], rax
0x1400b0877  mov     rax, [rbx+28h]
0x1400b087b  mov     [rsp+0B8h+var_48], rax
0x1400b0880  mov     rax, [rbx+38h]
0x1400b0884  mov     [r15+38h], rax
0x1400b0888  mov     r8, [rbx]
0x1400b088b  mov     rax, r8
0x1400b088e  sub     rax, rcx
0x1400b0891  cmp     rax, rdx
0x1400b0894  jnb     short loc_1400B08C5
0x1400b0896  mov     rax, [rbx+8]
0x1400b089a  sub     rax, rcx
0x1400b089d  cmp     rax, rdx
0x1400b08a0  jnb     short loc_1400B08C5
0x1400b08a2  mov     [rsi+0B0h], r8
0x1400b08a9  mov     rax, [rbx+8]
0x1400b08ad  mov     [rsi+0B8h], rax
0x1400b08b4  lock or dword ptr [rsi+0ACh], 800h
0x1400b08bf  mov     [r15+20h], rsi
0x1400b08c3  jmp     short loc_1400B0907
0x1400b08c5  mov     r14d, 0C0000141h
0x1400b08cb  jmp     loc_1400B09BB
0x1400b08d0  mov     edx, [rsi+0A8h]
0x1400b08d6  or      edx, 0E0000000h
0x1400b08dc  shl     edx, 2
0x1400b08df  mov     rcx, [rsp+0B8h+arg_10]
0x1400b08e7  add     rcx, 48h ; 'H'
0x1400b08eb  call    RtlWriteULong64ToUser
0x1400b08f0  nop
0x1400b08f1  mov     rdx, [rsp+0B8h+arg_10]
0x1400b08f9  mov     [rsi+0A0h], rdx
0x1400b0900  mov     [rsi+0B8h], rdx
0x1400b0907  mov     byte ptr [rsi+60h], 1
0x1400b090b  xor     r9d, r9d
0x1400b090e  xor     r8d, r8d
0x1400b0911  mov     rdx, [rsp+0B8h+var_48]
0x1400b0916  mov     rcx, rsi
0x1400b0919  call    SkpspCreateThreadContext
0x1400b091e  lea     rcx, [r12+4]
0x1400b0923  call    SkAcquireSpinLockExclusive
0x1400b0928  lea     rcx, [r12+10h]
0x1400b092d  mov     rdx, [rcx+8]
0x1400b0931  cmp     [rdx], rcx
0x1400b0934  jz      short loc_1400B093D
0x1400b0936  mov     ecx, 3
0x1400b093b  int     29h; Win8: RtlFailFast(ecx)
0x1400b093d  mov     [rsi], rcx
0x1400b0940  mov     [rsi+8], rdx
0x1400b0944  mov     [rdx], rsi
0x1400b0947  mov     [rcx+8], rsi
0x1400b094b  lock inc dword ptr [r12+0BCh]
0x1400b0954  lock or dword ptr [r12], 80h
0x1400b095d  test    r15, r15
0x1400b0960  jz      short loc_1400B096D
0x1400b0962  mov     [rsi+128h], r15
0x1400b0969  mov     [r15+20h], rsi
0x1400b096d  mov     dl, al
0x1400b096f  lea     rcx, [r12+4]
0x1400b0974  call    SkReleaseSpinLockExclusive
0x1400b0979  mov     [rsp+0B8h+arg_10], 0
0x1400b0985  xor     r14d, r14d
0x1400b0988  mov     rax, [rsp+0B8h+arg_20]
0x1400b0990  test    rax, rax
0x1400b0993  jz      short loc_1400B09B6
0x1400b0995  mov     [rax], rsi
0x1400b0998  jmp     short loc_1400B09B6
0x1400b099a  mov     r14d, eax
0x1400b099d  mov     r12, [rsp+0B8h+arg_0]
0x1400b09a5  mov     rsi, [rsp+0B8h+var_78]
0x1400b09aa  mov     r15, [rsp+0B8h+var_60]
0x1400b09af  jmp     short loc_1400B09B6
0x1400b09b1  mov     rsi, [rsp+0B8h+var_78]
0x1400b09b6  test    r14d, r14d
0x1400b09b9  jns     short loc_1400B0A1E
0x1400b09bb  test    rsi, rsi
0x1400b09be  jz      short loc_1400B09E3
0x1400b09c0  lea     rbx, [rsi+0D8h]
0x1400b09c7  xor     edx, edx
0x1400b09c9  mov     rcx, rbx
0x1400b09cc  call    SkReleaseRundownProtection
0x1400b09d1  mov     rcx, rbx
0x1400b09d4  call    SkWaitForRundownProtectionRelease
0x1400b09d9  mov     rcx, rsi
0x1400b09dc  call    SkpspDeleteEnclaveThread
0x1400b09e1  xor     esi, esi
0x1400b09e3  mov     rdx, [rsp+0B8h+arg_10]
0x1400b09eb  test    rdx, rdx
0x1400b09ee  jz      short loc_1400B09FA
0x1400b09f0  mov     rcx, r12
0x1400b09f3  call    SkpspDeleteTeb
0x1400b09f8  jmp     short loc_1400B0A0C
0x1400b09fa  mov     rcx, [rsp+0B8h+var_38]
0x1400b0a02  test    rcx, rcx
0x1400b0a05  jz      short loc_1400B0A0C
0x1400b0a07  call    RtlFreeUserStack
0x1400b0a0c  test    r15, r15
0x1400b0a0f  jz      short loc_1400B0A1E
0x1400b0a11  mov     rdx, r15
0x1400b0a14  mov     ecx, 200h
0x1400b0a19  call    SkFreePool
0x1400b0a1e  test    rsi, rsi
0x1400b0a21  jz      short loc_1400B0A31
0x1400b0a23  lea     rcx, [rsi+0D8h]
0x1400b0a2a  xor     edx, edx
0x1400b0a2c  call    SkReleaseRundownProtection
0x1400b0a31  mov     eax, r14d
0x1400b0a34  mov     rbx, [rsp+0B8h+arg_8]
0x1400b0a3c  add     rsp, 90h
0x1400b0a43  pop     r15
0x1400b0a45  pop     r14
0x1400b0a47  pop     r13
0x1400b0a49  pop     r12
0x1400b0a4b  pop     rsi
0x1400b0a4c  retn
```
