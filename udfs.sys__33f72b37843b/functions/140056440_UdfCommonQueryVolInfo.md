# UdfCommonQueryVolInfo

- ea: `0x140056440`
- end: `0x140056627`
- name: `UdfCommonQueryVolInfo`
- size: `487`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x14001bd80`
- `0x14002fa40`
- `0x1400444c4`
- `0x140056440`
- `0x140056630`
- `0x1400566b8`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14005661a`
- `ntoskrnl!ExRaiseStatus` at `0x14005661a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400564a3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400564a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400565e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ae18`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400565e4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ae18`
- `ntoskrnl!FsRtlGetSectorSizeInformation` at `0x14005659e`
- `ntoskrnl!FsRtlGetSectorSizeInformation` at `0x14005659e`

## pseudocode

```c
__int64 __fastcall UdfCommonQueryVolInfo(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  __int64 v3; // r13
  __int64 v4; // r12
  __int64 v5; // r15
  unsigned int v6; // edi
  __int64 v7; // rax
  __int64 v8; // r8
  unsigned int SectorSizeInformation; // esi
  struct _ERESOURCE *v10; // rbx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // edi
  unsigned int v14; // ecx
  unsigned int v15; // ebx
  unsigned int v16; // eax
  _DWORD *v17; // rdx
  unsigned int v19; // [rsp+60h] [rbp+8h] BYREF
  PERESOURCE Resource; // [rsp+68h] [rbp+10h]
  __int64 v21; // [rsp+70h] [rbp+18h]

  v2 = a2;
  v3 = a1;
  v4 = *(_QWORD *)(a2 + 184);
  v5 = *(_QWORD *)(a1 + 16);
  v6 = *(_DWORD *)(v4 + 8);
  v19 = v6;
  v7 = *(_QWORD *)(v4 + 48);
  v8 = *(_QWORD *)(v7 + 32);
  *(_QWORD *)(v7 + 32) = v8;
  SectorSizeInformation = -1073741811;
  if ( (v8 & 7) != 0 )
  {
    v21 = v5;
    v10 = (struct _ERESOURCE *)(v5 + 1480);
    Resource = (PERESOURCE)(v5 + 1480);
    if ( !ExAcquireResourceSharedLite((PERESOURCE)(v5 + 1480), (*(_DWORD *)(a1 + 28) & 4) != 0) )
    {
      *(_DWORD *)(v3 + 24) = -1073741608;
      ExRaiseStatus(-1073741608);
    }
    UdfVerifyVcb(v3, v5, v11);
    if ( *(_DWORD *)(v4 + 16) == 1 )
    {
      v12 = *(_QWORD *)(v2 + 24);
      *(_QWORD *)v12 = *(_QWORD *)(*(_QWORD *)(v5 + 280) + 464LL);
      *(_DWORD *)(v12 + 8) = *(_DWORD *)(*(_QWORD *)(v5 + 8) + 24LL);
      *(_BYTE *)(v12 + 16) = 0;
      v13 = v6 - 18;
      v19 = v13;
      v14 = *(unsigned __int16 *)(*(_QWORD *)(v5 + 8) + 6LL);
      SectorSizeInformation = v13 < v14 ? 0x80000005 : 0;
      if ( v13 < v14 )
        v14 = v13 & 0xFFFFFFFE;
      v15 = v14;
      *(_DWORD *)(v12 + 12) = v14;
      memmove((void *)(v12 + 18), (const void *)(*(_QWORD *)(v5 + 8) + 32LL), v14);
      v19 = v13 - v15;
      v10 = Resource;
      goto LABEL_19;
    }
    if ( *(_DWORD *)(v4 + 16) == 3 )
    {
      v16 = UdfQueryFsSizeInfo((unsigned int)(*(_DWORD *)(v4 + 16) - 3), v5, *(_QWORD *)(v2 + 24), &v19);
    }
    else
    {
      if ( *(_DWORD *)(v4 + 16) == 4 )
      {
        v17 = *(_DWORD **)(v2 + 24);
        v17[1] = *(_DWORD *)(*(_QWORD *)(v5 + 24) + 52LL);
        *v17 = 2;
        v19 = v6 - 8;
        SectorSizeInformation = 0;
        goto LABEL_19;
      }
      if ( *(_DWORD *)(v4 + 16) == 5 )
      {
        v16 = UdfQueryFsAttributeInfo((unsigned int)(*(_DWORD *)(v4 + 16) - 5), v5, *(_QWORD *)(v2 + 24), &v19);
      }
      else
      {
        if ( *(_DWORD *)(v4 + 16) != 7 )
        {
          if ( *(_DWORD *)(v4 + 16) == 11 )
          {
            SectorSizeInformation = FsRtlGetSectorSizeInformation(
                                      *(_QWORD *)(*(_QWORD *)(v5 + 8) + 16LL),
                                      *(_QWORD *)(v2 + 24));
            if ( (SectorSizeInformation & 0x80000000) == 0 )
              v19 -= 28;
          }
          goto LABEL_19;
        }
        v16 = UdfQueryFsFullSizeInfo((unsigned int)(*(_DWORD *)(v4 + 16) - 7), v5, *(_QWORD *)(v2 + 24), &v19);
      }
    }
    SectorSizeInformation = v16;
LABEL_19:
    *(_QWORD *)(v2 + 56) = *(_DWORD *)(v4 + 8) - v19;
    ExReleaseResourceLite(v10);
    a2 = v2;
    a1 = v3;
  }
  UdfCompleteRequest(a1, a2, SectorSizeInformation);
  return SectorSizeInformation;
}

```

## disassembly

```asm
0x140056440  push    rbx
0x140056442  push    rsi
0x140056443  push    rdi
0x140056444  push    r12
0x140056446  push    r13
0x140056448  push    r14
0x14005644a  push    r15
0x14005644c  sub     rsp, 20h
0x140056450  mov     r14, rdx
0x140056453  mov     r13, rcx
0x140056456  mov     r12, [rdx+0B8h]
0x14005645d  mov     r15, [rcx+10h]
0x140056461  mov     edi, [r12+8]
0x140056466  mov     [rsp+58h+arg_0], edi
0x14005646a  mov     rax, [r12+30h]
0x14005646f  mov     r8, [rax+20h]
0x140056473  mov     [rax+20h], r8
0x140056477  mov     esi, 0C000000Dh
0x14005647c  test    r8b, 7
0x140056480  jz      loc_1400565F6
0x140056486  mov     [rsp+58h+arg_10], r15
0x14005648b  lea     rbx, [r15+5C8h]
0x140056492  mov     [rsp+58h+Resource], rbx
0x140056497  mov     edx, [rcx+1Ch]
0x14005649a  shr     edx, 2
0x14005649d  and     dl, 1; Wait
0x1400564a0  mov     rcx, rbx; Resource
0x1400564a3  call    cs:__imp_ExAcquireResourceSharedLite
0x1400564aa  nop     dword ptr [rax+rax+00h]
0x1400564af  test    al, al
0x1400564b1  jz      loc_140056611
0x1400564b7  mov     rdx, r15
0x1400564ba  mov     rcx, r13
0x1400564bd  call    UdfVerifyVcb
0x1400564c2  mov     ecx, [r12+10h]
0x1400564c7  sub     ecx, 1
0x1400564ca  jnz     short loc_14005653E
0x1400564cc  mov     r9, [r14+18h]
0x1400564d0  mov     rax, [r15+118h]
0x1400564d7  mov     rcx, [rax+1D0h]
0x1400564de  mov     [r9], rcx
0x1400564e1  mov     rax, [r15+8]
0x1400564e5  mov     ecx, [rax+18h]
0x1400564e8  mov     [r9+8], ecx
0x1400564ec  mov     byte ptr [r9+10h], 0
0x1400564f1  add     edi, 0FFFFFFEEh
0x1400564f4  mov     [rsp+58h+arg_0], edi
0x1400564f8  mov     rax, [r15+8]
0x1400564fc  movzx   ecx, word ptr [rax+6]
0x140056500  cmp     edi, ecx
0x140056502  sbb     esi, esi
0x140056504  and     esi, 80000005h
0x14005650a  mov     eax, edi
0x14005650c  and     eax, 0FFFFFFFEh
0x14005650f  cmp     edi, ecx
0x140056511  cmovb   ecx, eax
0x140056514  mov     ebx, ecx
0x140056516  mov     [r9+0Ch], ebx
0x14005651a  mov     r8d, ecx; Size
0x14005651d  mov     rdx, [r15+8]
0x140056521  add     rdx, 20h ; ' '; Src
0x140056525  lea     rcx, [r9+12h]; void *
0x140056529  call    memmove
0x14005652e  sub     edi, ebx
0x140056530  mov     [rsp+58h+arg_0], edi
0x140056534  mov     rbx, [rsp+58h+Resource]
0x140056539  jmp     loc_1400565D4
0x14005653e  sub     ecx, 2
0x140056541  jz      short loc_14005657A
0x140056543  sub     ecx, 1
0x140056546  jz      short loc_1400565B7
0x140056548  sub     ecx, 1
0x14005654b  jz      short loc_140056567
0x14005654d  sub     ecx, 2
0x140056550  jnz     short loc_14005658D
0x140056552  lea     r9, [rsp+58h+arg_0]
0x140056557  mov     r8, [r14+18h]
0x14005655b  mov     rdx, r15
0x14005655e  call    UdfQueryFsFullSizeInfo
0x140056563  mov     esi, eax
0x140056565  jmp     short loc_1400565D4
0x140056567  lea     r9, [rsp+58h+arg_0]
0x14005656c  mov     r8, [r14+18h]
0x140056570  mov     rdx, r15
0x140056573  call    UdfQueryFsAttributeInfo
0x140056578  jmp     short loc_140056563
0x14005657a  lea     r9, [rsp+58h+arg_0]
0x14005657f  mov     r8, [r14+18h]
0x140056583  mov     rdx, r15
0x140056586  call    UdfQueryFsSizeInfo
0x14005658b  jmp     short loc_140056563
0x14005658d  cmp     ecx, 4
0x140056590  jnz     short loc_1400565D4
0x140056592  mov     rcx, [r15+8]
0x140056596  mov     rdx, [r14+18h]
0x14005659a  mov     rcx, [rcx+10h]
0x14005659e  call    cs:__imp_FsRtlGetSectorSizeInformation
0x1400565a5  nop     dword ptr [rax+rax+00h]
0x1400565aa  mov     esi, eax
0x1400565ac  test    eax, eax
0x1400565ae  js      short loc_1400565D4
0x1400565b0  add     [rsp+58h+arg_0], 0FFFFFFE4h
0x1400565b5  jmp     short loc_1400565D4
0x1400565b7  mov     rdx, [r14+18h]
0x1400565bb  mov     rax, [r15+18h]
0x1400565bf  mov     ecx, [rax+34h]
0x1400565c2  mov     [rdx+4], ecx
0x1400565c5  mov     dword ptr [rdx], 2
0x1400565cb  lea     eax, [rdi-8]
0x1400565ce  mov     [rsp+58h+arg_0], eax
0x1400565d2  xor     esi, esi
0x1400565d4  mov     eax, [r12+8]
0x1400565d9  sub     eax, [rsp+58h+arg_0]
0x1400565dd  mov     [r14+38h], rax
0x1400565e1  mov     rcx, rbx; Resource
0x1400565e4  call    cs:__imp_ExReleaseResourceLite
0x1400565eb  nop     dword ptr [rax+rax+00h]
0x1400565f0  mov     rdx, r14
0x1400565f3  mov     rcx, r13
0x1400565f6  mov     r8d, esi
0x1400565f9  call    UdfCompleteRequest
0x1400565fe  mov     eax, esi
0x140056600  add     rsp, 20h
0x140056604  pop     r15
0x140056606  pop     r14
0x140056608  pop     r13
0x14005660a  pop     r12
0x14005660c  pop     rdi
0x14005660d  pop     rsi
0x14005660e  pop     rbx
0x14005660f  retn
0x140056611  mov     ecx, 0C00000D8h; Status
0x140056616  mov     [r13+18h], ecx
0x14005661a  call    cs:__imp_ExRaiseStatus
0x14005ae04  push    rbp
0x14005ae06  sub     rsp, 20h
0x14005ae0a  mov     rbp, rdx
0x14005ae0d  mov     rcx, [rbp+70h]
0x14005ae11  add     rcx, 5C8h; Resource
0x14005ae18  call    cs:__imp_ExReleaseResourceLite
0x14005ae1f  nop     dword ptr [rax+rax+00h]
0x14005ae24  nop
0x14005ae25  add     rsp, 20h
0x14005ae29  pop     rbp
0x14005ae2a  retn
```
