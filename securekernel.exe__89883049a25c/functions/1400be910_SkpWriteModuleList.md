# SkpWriteModuleList

- ea: `0x1400be910`
- end: `0x1400becbf`
- name: `SkpWriteModuleList`
- size: `943`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400be4f8`

## callees

- `0x1400442ac`
- `0x1400be03c`
- `0x1400be910`
- `0x1400bed44`
- `0x1400d4e8c`
- `0x1400f3620`
- `0x1400f38f0`
- `0x1400f9a80`
- `0x1400fc664`
- `0x1400fc6a0`

## pseudocode

```c
__int64 __fastcall SkpWriteModuleList(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int64 v8; // rcx
  _DWORD *v10; // r15
  unsigned int *v11; // rbx
  unsigned int *ULong64FromUser; // r14
  unsigned int v13; // r12d
  int ULongFromUser; // eax
  unsigned __int16 v15; // di
  unsigned int v16; // ebx
  __int64 v17; // r9
  void *v18; // rdi
  _QWORD *v19; // rcx
  size_t v20; // r8
  _DWORD *v21; // rbx
  size_t v22; // r8
  __int64 v23; // rdi
  __int64 v24; // rdx
  int v25; // [rsp+20h] [rbp-168h]
  char v26; // [rsp+30h] [rbp-158h]
  int v27; // [rsp+38h] [rbp-150h] BYREF
  int v28; // [rsp+3Ch] [rbp-14Ch]
  unsigned int Src; // [rsp+40h] [rbp-148h] BYREF
  _DWORD Size[3]; // [rsp+44h] [rbp-144h]
  __int64 v31; // [rsp+50h] [rbp-138h]
  _QWORD *v32; // [rsp+58h] [rbp-130h]
  unsigned int *v33; // [rsp+60h] [rbp-128h]
  void *v34[2]; // [rsp+70h] [rbp-118h]
  __int64 v35; // [rsp+80h] [rbp-108h]
  __int64 v36; // [rsp+88h] [rbp-100h]
  __int64 v37; // [rsp+90h] [rbp-F8h]
  _DWORD *v38; // [rsp+A0h] [rbp-E8h]
  _QWORD *v39; // [rsp+A8h] [rbp-E0h]
  unsigned int *v40; // [rsp+B0h] [rbp-D8h]
  unsigned int *v41; // [rsp+B8h] [rbp-D0h]
  __int128 v42; // [rsp+C0h] [rbp-C8h]
  unsigned __int64 v43; // [rsp+D0h] [rbp-B8h] BYREF
  unsigned int v44; // [rsp+D8h] [rbp-B0h]
  int v45; // [rsp+DCh] [rbp-ACh]
  int v46; // [rsp+E0h] [rbp-A8h]
  int v47; // [rsp+E4h] [rbp-A4h]
  __int64 v48; // [rsp+11Ch] [rbp-6Ch]
  __int64 v49; // [rsp+124h] [rbp-64h]
  __int64 v50; // [rsp+12Ch] [rbp-5Ch]
  __int64 v51; // [rsp+134h] [rbp-54h]

  *(_QWORD *)&Size[1] = a1;
  v32 = a5;
  v36 = a1;
  v37 = a2;
  v31 = (__int64)a5;
  memset_0(&v43, 0, 0x6Cu);
  v27 = 0;
  v38 = (_DWORD *)(a2 + 72);
  v8 = *(unsigned int *)(a2 + 72);
  v39 = (_QWORD *)(a2 + 160);
  if ( *(_QWORD *)(a2 + 160) < (unsigned __int64)(v8 + 4) )
    return 3221225485LL;
  v26 = 1;
  Src = *(_DWORD *)(a2 + 212);
  RtlCopyVolatileMemory((void *)(a1 + v8), &Src, 4u);
  v10 = (_DWORD *)(a2 + 80);
  v35 = a2 + 80;
  *(_DWORD *)(a2 + 80) += 4;
  v11 = (unsigned int *)(RtlReadULong64FromUser((volatile void *)(*(_QWORD *)(a3 + 160) + 24LL)) + 16);
  v40 = v11;
  ULong64FromUser = (unsigned int *)RtlReadULong64FromUser(v11);
  v33 = ULong64FromUser;
  v13 = 0;
  v28 = 0;
  while ( ULong64FromUser != v11 )
  {
    v41 = ULong64FromUser;
    *(_OWORD *)v34 = 0;
    ULongFromUser = RtlReadULongFromUser(ULong64FromUser + 18);
    v15 = ULongFromUser;
    LODWORD(v34[0]) = ULongFromUser;
    v34[1] = (void *)RtlReadULong64FromUser(ULong64FromUser + 20);
    v42 = *(_OWORD *)v34;
    ProbeForRead(v34[1], v15, 2u);
    v16 = v15;
    Size[0] = v15;
    LOBYTE(v25) = 1;
    v17 = v15;
    v18 = v34[1];
    SkpWriteStringToPool(*(_QWORD *)&Size[1], a2, v34[1], v17, v25, &v27);
    v43 = RtlReadULong64FromUser(ULong64FromUser + 12);
    v44 = RtlReadULongFromUser(ULong64FromUser + 16);
    v45 = 0;
    v46 = RtlReadULongFromUser(ULong64FromUser + 32);
    v48 = 0;
    v49 = 0;
    v47 = v27;
    v50 = 0;
    v51 = 0;
    if ( v26 )
    {
      v20 = 518;
      if ( v16 < 0x206 )
        v20 = v16;
      v21 = (_DWORD *)v31;
      RtlCopyFromUser((void *)(v31 + 24), v18, v20);
      v21[2] = v46;
      v26 = 0;
    }
    else
    {
      v21 = (_DWORD *)v31;
    }
    if ( a4 && *(_QWORD *)(a4 + 16) >= v43 && *(_DWORD *)(a4 + 16) - (int)v43 <= v44 )
    {
      v22 = 518;
      if ( Size[0] < 0x206u )
        v22 = Size[0];
      RtlCopyFromUser(v21 + 136, v34[1], v22);
      v21[3] = v46;
      v19 = v32;
      *v32 = (unsigned int)(*(_DWORD *)(a4 + 16) - v43);
    }
    v23 = *(_QWORD *)&Size[1];
    if ( (int)SkpCheckSize(v19, (unsigned int)*v10, 108) >= 0
      && (int)v24 + 108 <= (unsigned int)(*v38 + *(_DWORD *)(a2 + 76))
      && *v39 >= (unsigned __int64)(unsigned int)(v24 + 108) )
    {
      RtlCopyVolatileMemory((void *)(v23 + v24), &v43, 0x6Cu);
      *v10 += 108;
    }
    ULong64FromUser = (unsigned int *)RtlReadULong64FromUser(ULong64FromUser);
    v33 = ULong64FromUser;
    v28 = ++v13;
    if ( v13 >= Src )
      break;
    v11 = v40;
  }
  return 0;
}

```

## disassembly

```asm
0x1400be910  mov     [rsp+arg_18], r9
0x1400be915  push    rbx
0x1400be916  push    rdi
0x1400be917  push    r12
0x1400be919  push    r13
0x1400be91b  push    r14
0x1400be91d  push    r15
0x1400be91f  sub     rsp, 158h
0x1400be926  mov     rax, cs:__security_cookie
0x1400be92d  xor     rax, rsp
0x1400be930  mov     [rsp+188h+var_48], rax
0x1400be938  mov     rbx, r8
0x1400be93b  mov     r13, rdx
0x1400be93e  mov     rdi, rcx
0x1400be941  mov     qword ptr [rsp+188h+Size+4], rcx
0x1400be946  mov     rax, [rsp+188h+arg_20]
0x1400be94e  mov     [rsp+188h+var_130], rax
0x1400be953  mov     [rsp+188h+var_100], rcx
0x1400be95b  mov     [rsp+188h+var_F8], rdx
0x1400be963  mov     [rsp+188h+var_138], rax
0x1400be968  xor     edx, edx; Val
0x1400be96a  lea     r8d, [rdx+6Ch]; Size
0x1400be96e  lea     rcx, [rsp+188h+var_B8]; void *
0x1400be976  call    memset_0
0x1400be97b  mov     [rsp+188h+var_150], 0
0x1400be983  lea     rax, [r13+48h]
0x1400be987  mov     [rsp+188h+var_E8], rax
0x1400be98f  mov     ecx, [rax]
0x1400be991  lea     rdx, [r13+0A0h]
0x1400be998  mov     [rsp+188h+var_E0], rdx
0x1400be9a0  lea     rax, [rcx+4]
0x1400be9a4  cmp     [rdx], rax
0x1400be9a7  jnb     short loc_1400BE9B3
0x1400be9a9  mov     eax, 0C000000Dh
0x1400be9ae  jmp     loc_1400BEC9C
0x1400be9b3  mov     [rsp+188h+var_158], 1
0x1400be9b8  mov     eax, [r13+0D4h]
0x1400be9bf  mov     [rsp+188h+Src], eax
0x1400be9c3  add     rcx, rdi; void *
0x1400be9c6  mov     r8d, 4; Size
0x1400be9cc  lea     rdx, [rsp+188h+Src]; Src
0x1400be9d1  call    RtlCopyVolatileMemory
0x1400be9d6  lea     r15, [r13+50h]
0x1400be9da  mov     [rsp+188h+var_108], r15
0x1400be9e2  add     dword ptr [r15], 4
0x1400be9e6  mov     rcx, [rbx+0A0h]
0x1400be9ed  add     rcx, 18h
0x1400be9f1  call    RtlReadULong64FromUser
0x1400be9f6  lea     rbx, [rax+10h]
0x1400be9fa  mov     [rsp+188h+var_D8], rbx
0x1400bea02  mov     rcx, rbx
0x1400bea05  call    RtlReadULong64FromUser
0x1400bea0a  mov     r14, rax
0x1400bea0d  mov     [rsp+188h+var_128], rax
0x1400bea12  xor     r12d, r12d
0x1400bea15  mov     [rsp+188h+var_14C], r12d
0x1400bea1a  cmp     r14, rbx
0x1400bea1d  jz      loc_1400BEC94
0x1400bea23  mov     [rsp+188h+var_154], 0
0x1400bea2b  mov     [rsp+188h+var_D0], r14
0x1400bea33  xorps   xmm0, xmm0
0x1400bea36  movups  xmmword ptr [rsp+188h+var_118], xmm0
0x1400bea3b  lea     rcx, [r14+48h]
0x1400bea3f  call    RtlReadULongFromUser
0x1400bea44  mov     edi, eax
0x1400bea46  mov     dword ptr [rsp+188h+var_118], edi
0x1400bea4a  lea     rcx, [r14+50h]
0x1400bea4e  call    RtlReadULong64FromUser
0x1400bea53  mov     [rsp+188h+var_118+8], rax
0x1400bea58  movaps  xmm0, xmmword ptr [rsp+188h+var_118]
0x1400bea5d  movdqa  [rsp+188h+var_C8], xmm0
0x1400bea66  movzx   edx, di; Length
0x1400bea69  mov     r8d, 2; Alignment
0x1400bea6f  mov     rcx, rax; Address
0x1400bea72  call    ProbeForRead
0x1400bea77  movzx   ebx, di
0x1400bea7a  mov     dword ptr [rsp+188h+Size], ebx
0x1400bea7e  lea     rax, [rsp+188h+var_150]
0x1400bea83  mov     [rsp+188h+var_160], rax
0x1400bea88  mov     [rsp+188h+var_168], 1
0x1400bea8d  mov     r9d, ebx
0x1400bea90  mov     rdi, [rsp+188h+var_118+8]
0x1400bea95  mov     r8, rdi
0x1400bea98  mov     rdx, r13
0x1400bea9b  mov     rcx, qword ptr [rsp+188h+Size+4]
0x1400beaa0  call    SkpWriteStringToPool
0x1400beaa5  mov     [rsp+188h+var_154], eax
0x1400beaa9  lea     rcx, [r14+30h]
0x1400beaad  call    RtlReadULong64FromUser
0x1400beab2  mov     [rsp+188h+var_B8], rax
0x1400beaba  lea     rcx, [r14+40h]
0x1400beabe  call    RtlReadULongFromUser
0x1400beac3  mov     [rsp+188h+var_B0], eax
0x1400beaca  mov     [rsp+188h+var_AC], 0
0x1400bead5  lea     rcx, [r14+80h]
0x1400beadc  call    RtlReadULongFromUser
0x1400beae1  mov     [rsp+188h+var_A8], eax
0x1400beae8  mov     [rsp+188h+var_6C], 0
0x1400beaf4  mov     [rsp+188h+var_64], 0
0x1400beb00  mov     eax, [rsp+188h+var_150]
0x1400beb04  mov     [rsp+188h+var_A4], eax
0x1400beb0b  mov     [rsp+188h+var_5C], 0
0x1400beb17  mov     [rsp+188h+var_54], 0
0x1400beb23  cmp     [rsp+188h+var_158], 0
0x1400beb28  jz      short loc_1400BEB5A
0x1400beb2a  mov     ecx, 206h
0x1400beb2f  mov     r8d, ecx
0x1400beb32  cmp     ebx, ecx
0x1400beb34  cmovb   r8d, ebx; Size
0x1400beb38  mov     rbx, [rsp+188h+var_138]
0x1400beb3d  lea     rcx, [rbx+18h]; void *
0x1400beb41  mov     rdx, rdi; Src
0x1400beb44  call    RtlCopyFromUser
0x1400beb49  mov     eax, [rsp+188h+var_A8]
0x1400beb50  mov     [rbx+8], eax
0x1400beb53  mov     [rsp+188h+var_158], 0
0x1400beb58  jmp     short loc_1400BEB5F
0x1400beb5a  mov     rbx, [rsp+188h+var_138]
0x1400beb5f  mov     rdi, [rsp+188h+arg_18]
0x1400beb67  test    rdi, rdi
0x1400beb6a  jz      short loc_1400BEBCC
0x1400beb6c  mov     rax, [rsp+188h+var_B8]
0x1400beb74  cmp     [rdi+10h], rax
0x1400beb78  jb      short loc_1400BEBCC
0x1400beb7a  mov     eax, [rdi+10h]
0x1400beb7d  sub     eax, dword ptr [rsp+188h+var_B8]
0x1400beb84  cmp     eax, [rsp+188h+var_B0]
0x1400beb8b  ja      short loc_1400BEBCC
0x1400beb8d  mov     ecx, 206h
0x1400beb92  mov     r8d, ecx
0x1400beb95  cmp     dword ptr [rsp+188h+Size], ecx
0x1400beb99  cmovb   r8d, dword ptr [rsp+188h+Size]; Size
0x1400beb9f  lea     rcx, [rbx+220h]; void *
0x1400beba6  mov     rdx, [rsp+188h+var_118+8]; Src
0x1400bebab  call    RtlCopyFromUser
0x1400bebb0  mov     eax, [rsp+188h+var_A8]
0x1400bebb7  mov     [rbx+0Ch], eax
0x1400bebba  mov     eax, [rdi+10h]
0x1400bebbd  sub     eax, dword ptr [rsp+188h+var_B8]
0x1400bebc4  mov     rcx, [rsp+188h+var_130]
0x1400bebc9  mov     [rcx], rax
0x1400bebcc  mov     rdi, qword ptr [rsp+188h+Size+4]
0x1400bebd1  jmp     short loc_1400BEBFA
0x1400bebd3  mov     r14, [rsp+188h+var_128]
0x1400bebd8  mov     r12d, [rsp+188h+var_14C]
0x1400bebdd  mov     r15, [rsp+188h+var_108]
0x1400bebe5  mov     rdi, [rsp+188h+var_100]
0x1400bebed  mov     qword ptr [rsp+188h+Size+4], rdi
0x1400bebf2  mov     r13, [rsp+188h+var_F8]
0x1400bebfa  mov     edx, [r15]
0x1400bebfd  mov     r8d, 6Ch ; 'l'
0x1400bec03  call    SkpCheckSize
0x1400bec08  mov     ebx, eax
0x1400bec0a  test    eax, eax
0x1400bec0c  jns     short loc_1400BEC15
0x1400bec0e  mov     ebx, 0C0000023h
0x1400bec13  jmp     short loc_1400BEC5C
0x1400bec15  lea     ecx, [rdx+6Ch]
0x1400bec18  mov     eax, [r13+4Ch]
0x1400bec1c  mov     r8, [rsp+188h+var_E8]
0x1400bec24  add     eax, [r8]
0x1400bec27  cmp     ecx, eax
0x1400bec29  ja      short loc_1400BEC57
0x1400bec2b  mov     eax, ecx
0x1400bec2d  mov     rcx, [rsp+188h+var_E0]
0x1400bec35  cmp     [rcx], rax
0x1400bec38  jb      short loc_1400BEC57
0x1400bec3a  lea     rcx, [rdi+rdx]; void *
0x1400bec3e  mov     r8d, 6Ch ; 'l'; Size
0x1400bec44  lea     rdx, [rsp+188h+var_B8]; Src
0x1400bec4c  call    RtlCopyVolatileMemory
0x1400bec51  add     dword ptr [r15], 6Ch ; 'l'
0x1400bec55  jmp     short loc_1400BEC5C
0x1400bec57  mov     ebx, 0C000000Dh
0x1400bec5c  mov     [rsp+188h+var_154], ebx
0x1400bec60  mov     [rsp+188h+var_154], 0
0x1400bec68  mov     rcx, r14
0x1400bec6b  call    RtlReadULong64FromUser
0x1400bec70  mov     r14, rax
0x1400bec73  mov     [rsp+188h+var_128], rax
0x1400bec78  inc     r12d
0x1400bec7b  mov     [rsp+188h+var_14C], r12d
0x1400bec80  cmp     r12d, [rsp+188h+Src]
0x1400bec85  jnb     short loc_1400BEC94
0x1400bec87  mov     rbx, [rsp+188h+var_D8]
0x1400bec8f  jmp     loc_1400BEA1A
0x1400bec94  xor     eax, eax
0x1400bec96  jmp     short loc_1400BEC9C
0x1400bec98  mov     [rsp+188h+var_154], eax
0x1400bec9c  mov     rcx, [rsp+188h+var_48]
0x1400beca4  xor     rcx, rsp; StackCookie
0x1400beca7  call    __security_check_cookie
0x1400becac  add     rsp, 158h
0x1400becb3  pop     r15
0x1400becb5  pop     r14
0x1400becb7  pop     r13
0x1400becb9  pop     r12
0x1400becbb  pop     rdi
0x1400becbc  pop     rbx
0x1400becbd  retn
```
