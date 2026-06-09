# GetStartPageListForwardForDriver(_EMF_ATTRIBUTE_INFO *,_devicemodeW *,_PAGE_NUMBER * *,_PAGE_NUMBER * *,ulong)

- ea: `0x1800065e8`
- end: `0x18000676a`
- name: `?GetStartPageListForwardForDriver@@YAHPEAU_EMF_ATTRIBUTE_INFO@@PEAU_devicemodeW@@PEAPEAU_PAGE_NUMBER@@2K@Z`
- size: `386`
- prototype: `__int64 __fastcall(struct _EMF_ATTRIBUTE_INFO *, struct _devicemodeW *, struct _PAGE_NUMBER **, struct _PAGE_NUMBER **, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800070e0`

## callees

- `0x180003860`
- `0x180006514`
- `0x1800065e8`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000668e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000668e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180006741`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180006741`

## pseudocode

```c
__int64 __fastcall GetStartPageListForwardForDriver(
        struct _EMF_ATTRIBUTE_INFO *a1,
        struct _devicemodeW *a2,
        HLOCAL *a3,
        struct _PAGE_NUMBER **a4,
        unsigned int a5)
{
  __int64 v8; // rbp
  bool v9; // cf
  unsigned int v10; // ebx
  unsigned int v11; // r12d
  __int64 v12; // r11
  unsigned int v13; // r14d
  struct _PAGE_NUMBER *v14; // rax
  __int64 dmOrientation; // r8
  struct _PAGE_NUMBER *v16; // rdi
  __int64 PlaybackPageOrderForDriverNup; // rax
  __int64 v18; // r10
  unsigned int v19; // r9d
  __int64 v20; // r11
  unsigned int v21; // r8d
  unsigned int v22; // edx
  __int64 v23; // rax
  __int64 v24; // rax
  unsigned int v26; // [rsp+50h] [rbp+8h] BYREF
  SIZE_T uBytes; // [rsp+60h] [rbp+18h] BYREF

  v26 = 0;
  LODWORD(uBytes) = 0;
  if ( !a3 || !a4 )
    return 0;
  v8 = *((unsigned int *)a1 + 9);
  v9 = *((_DWORD *)a1 + 13) != 0;
  v10 = 1;
  *a3 = 0;
  *a4 = 0;
  v11 = v9 + 1;
  if ( (int)ULongLongToULong(v8 * v11, &v26) >= 0
    && (int)ULongLongToULong(24LL * v26, (unsigned int *)&uBytes) >= 0
    && (v13 = *(_DWORD *)(v12 + 60), (v14 = (struct _PAGE_NUMBER *)LocalAlloc(0x40u, (unsigned int)uBytes)) != 0) )
  {
    dmOrientation = (unsigned int)a2->dmOrientation;
    *a3 = v14;
    v16 = v14;
    *a4 = v14;
    PlaybackPageOrderForDriverNup = GetPlaybackPageOrderForDriverNup((unsigned int)v8, v13, dmOrientation);
    v19 = a5;
    v20 = PlaybackPageOrderForDriverNup;
    v21 = 1;
    do
    {
      if ( (_DWORD)v8 )
      {
        v22 = 1;
        if ( v21 == 2 )
        {
          do
          {
            if ( v22 == 1 )
            {
              *(_QWORD *)v18 = 0;
              *(_QWORD *)v16 = v18;
            }
            else
            {
              *(_QWORD *)(v18 - 16) = v18;
            }
            v23 = v22++ - 1;
            *(_DWORD *)(v18 + 16) = v19 + *(_DWORD *)(v20 + 4 * v23) - 1;
            v18 += 24;
          }
          while ( v22 <= (unsigned int)v8 );
        }
        else
        {
          do
          {
            if ( v22 == 1 )
              *(_QWORD *)v18 = 0;
            else
              *(_QWORD *)(v18 - 16) = v18;
            v24 = v22++ - 1;
            *(_DWORD *)(v18 + 16) = v19 + *(_DWORD *)(v20 + 4 * v24) - 1;
            v18 += 24;
          }
          while ( v22 <= (unsigned int)v8 );
        }
      }
      ++v21;
      v19 += v8;
    }
    while ( v21 <= v11 );
  }
  else
  {
    v10 = 0;
    if ( *a3 )
      LocalFree(*a3);
    *a3 = 0;
    *a4 = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x1800065e8  mov     rax, rsp
0x1800065eb  mov     [rax+10h], rbx
0x1800065ef  mov     [rax+20h], rbp
0x1800065f3  push    rsi
0x1800065f4  push    rdi
0x1800065f5  push    r12
0x1800065f7  push    r14
0x1800065f9  push    r15
0x1800065fb  sub     rsp, 20h
0x1800065ff  mov     dword ptr [rax+8], 0
0x180006606  mov     rsi, r9
0x180006609  mov     dword ptr [rax+18h], 0
0x180006610  mov     rdi, r8
0x180006613  mov     r15, rdx
0x180006616  mov     r11, rcx
0x180006619  test    r8, r8
0x18000661c  jz      loc_180006751
0x180006622  test    r9, r9
0x180006625  jz      loc_180006751
0x18000662b  mov     eax, [rcx+34h]
0x18000662e  lea     rdx, [rsp+48h+arg_0]; unsigned int *
0x180006633  mov     ebp, [rcx+24h]
0x180006636  neg     eax
0x180006638  mov     ebx, 1
0x18000663d  mov     qword ptr [r8], 0
0x180006644  sbb     ecx, ecx
0x180006646  mov     qword ptr [r9], 0
0x18000664d  neg     ecx
0x18000664f  add     ecx, ebx
0x180006651  mov     r12d, ecx
0x180006654  imul    rcx, rbp; unsigned __int64
0x180006658  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000665d  test    eax, eax
0x18000665f  js      loc_180006737
0x180006665  mov     eax, [rsp+48h+arg_0]
0x180006669  lea     rdx, [rsp+48h+uBytes]; unsigned int *
0x18000666e  lea     rcx, [rax+rax*2]
0x180006672  shl     rcx, 3; unsigned __int64
0x180006676  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000667b  test    eax, eax
0x18000667d  js      loc_180006737
0x180006683  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x180006687  lea     ecx, [rbx+3Fh]; uFlags
0x18000668a  mov     r14d, [r11+3Ch]
0x18000668e  call    cs:__imp_LocalAlloc
0x180006694  mov     r10, rax
0x180006697  test    rax, rax
0x18000669a  jz      loc_180006737
0x1800066a0  movsx   r8d, word ptr [r15+4Ch]
0x1800066a5  mov     edx, r14d
0x1800066a8  mov     [rdi], rax
0x1800066ab  mov     ecx, ebp
0x1800066ad  mov     rdi, rax
0x1800066b0  mov     [rsi], rax
0x1800066b3  call    ?GetPlaybackPageOrderForDriverNup@@YAPEAKKW4_ENupDirection@@H@Z; GetPlaybackPageOrderForDriverNup(ulong,_ENupDirection,int)
0x1800066b8  mov     r9d, [rsp+48h+arg_20]
0x1800066bd  mov     r11, rax
0x1800066c0  mov     r8d, ebx
0x1800066c3  cmp     ebp, ebx
0x1800066c5  jb      short loc_18000672A
0x1800066c7  mov     edx, ebx
0x1800066c9  cmp     r8d, 2
0x1800066cd  jnz     short loc_1800066FF
0x1800066cf  cmp     edx, ebx
0x1800066d1  jnz     short loc_1800066DF
0x1800066d3  mov     qword ptr [r10], 0
0x1800066da  mov     [rdi], r10
0x1800066dd  jmp     short loc_1800066E3
0x1800066df  mov     [r10-10h], r10
0x1800066e3  lea     eax, [rdx-1]
0x1800066e6  add     edx, ebx
0x1800066e8  mov     ecx, [r11+rax*4]
0x1800066ec  dec     ecx
0x1800066ee  add     ecx, r9d
0x1800066f1  mov     [r10+10h], ecx
0x1800066f5  add     r10, 18h
0x1800066f9  cmp     edx, ebp
0x1800066fb  jbe     short loc_1800066CF
0x1800066fd  jmp     short loc_18000672A
0x1800066ff  cmp     edx, ebx
0x180006701  jnz     short loc_18000670C
0x180006703  mov     qword ptr [r10], 0
0x18000670a  jmp     short loc_180006710
0x18000670c  mov     [r10-10h], r10
0x180006710  lea     eax, [rdx-1]
0x180006713  add     edx, ebx
0x180006715  mov     ecx, [r11+rax*4]
0x180006719  dec     ecx
0x18000671b  add     ecx, r9d
0x18000671e  mov     [r10+10h], ecx
0x180006722  add     r10, 18h
0x180006726  cmp     edx, ebp
0x180006728  jbe     short loc_1800066FF
0x18000672a  add     r8d, ebx
0x18000672d  add     r9d, ebp
0x180006730  cmp     r8d, r12d
0x180006733  jbe     short loc_1800066C3
0x180006735  jmp     short loc_18000674D
0x180006737  mov     rcx, [rdi]; hMem
0x18000673a  xor     ebx, ebx
0x18000673c  test    rcx, rcx
0x18000673f  jz      short loc_180006747
0x180006741  call    cs:__imp_LocalFree
0x180006747  mov     [rdi], rbx
0x18000674a  mov     [rsi], rbx
0x18000674d  mov     eax, ebx
0x18000674f  jmp     short loc_180006753
0x180006751  xor     eax, eax
0x180006753  mov     rbx, [rsp+48h+arg_8]
0x180006758  mov     rbp, [rsp+48h+arg_18]
0x18000675d  add     rsp, 20h
0x180006761  pop     r15
0x180006763  pop     r14
0x180006765  pop     r12
0x180006767  pop     rdi
0x180006768  pop     rsi
0x180006769  retn
```
