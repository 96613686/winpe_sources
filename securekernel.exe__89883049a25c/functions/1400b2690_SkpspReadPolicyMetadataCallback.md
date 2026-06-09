# SkpspReadPolicyMetadataCallback

- ea: `0x1400b2690`
- end: `0x1400b293f`
- name: `SkpspReadPolicyMetadataCallback`
- size: `687`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x14002ba08`
- `0x1400b22c4`
- `0x1400b2690`
- `0x1400f38f0`
- `0x1400fc664`
- `0x1400fc6a0`
- `0x1400fea90`

## string_xrefs

- `0x1400b28ef`: `SkpspReadPolicyMetadataCallback: Invalid Etw Policy - duplicate entry\n`
- `0x1400b2907`: `SkpspReadPolicyMetadataCallback: Invalid Etw Policy type\n`
- `0x1400b289c`: `SkpspReadPolicyMetadataCallback: Invalid Parent SD Policy - duplicate entry\n`
- `0x1400b28aa`: `SkpspReadPolicyMetadataCallback: Invalid Parent SD Policy type\n`
- `0x1400b2859`: `SkpspReadPolicyMetadataCallback: Invalid Parent SD Revision Policy - duplicate entry\n`
- `0x1400b286a`: `SkpspReadPolicyMetadataCallback: Invalid Parent SD Revision Policy type\n`
- `0x1400b280e`: `SkpspReadPolicyMetadataCallback: Invalid SVN Policy - duplicate entry\n`
- `0x1400b281f`: `SkpspReadPolicyMetadataCallback: Invalid SVN Policy type\n`
- `0x1400b27b3`: `SkpspReadPolicyMetadataCallback: Invalid capability Policy type\n`
- `0x1400b27dc`: `SkpspReadPolicyMetadataCallback: Invalid capability policy with value %I64u\n`
- `0x1400b2745`: `SkpspReadPolicyMetadataCallback: Invalid capability overridable Policy type\n`
- `0x1400b276e`: `SkpspReadPolicyMetadataCallback: Invalid capability overridable policy with value %I64u\n`

## pseudocode

```c
__int64 __fastcall SkpspReadPolicyMetadataCallback(__int64 a1, __int64 *a2, __int64 a3)
{
  char v3; // si
  const void *v5; // rdx
  int v8; // edx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  int *v11; // rcx
  int v12; // ecx
  int v13; // eax
  __int64 ULong64FromUser; // rax
  int v16; // eax
  int v17; // [rsp+48h] [rbp+10h] BYREF
  int ULongFromUser; // [rsp+50h] [rbp+18h] BYREF

  v3 = *(_BYTE *)(a3 + 4);
  v5 = (char *)a2 + 4;
  ULongFromUser = 0;
  v17 = 0;
  if ( v3 )
  {
    ULongFromUser = RtlReadULongFromUser(v5);
    v8 = RtlReadULongFromUser(a2);
    v17 = v8;
  }
  else
  {
    RtlCopyVolatileMemory(&ULongFromUser, v5, 4u);
    RtlCopyVolatileMemory(&v17, a2, 4u);
    v8 = v17;
  }
  switch ( ULongFromUser )
  {
    case 1:
      if ( (*(_DWORD *)a3 & 1) != 0 )
      {
        DbgPrint("SkpspReadPolicyMetadataCallback: Invalid Etw Policy - duplicate entry\n");
        return 3221225506LL;
      }
      if ( v8 != 7 )
      {
        DbgPrint("SkpspReadPolicyMetadataCallback: Invalid Etw Policy type\n");
        return 3221225506LL;
      }
      if ( v3 )
        v16 = RtlReadULongFromUser(a2 + 1);
      else
        v16 = *((_DWORD *)a2 + 2);
      if ( v16 == 1 )
        *(_DWORD *)(a3 + 8) |= 0x20u;
      *(_DWORD *)a3 |= 1u;
      break;
    case 6:
      if ( (*(_DWORD *)a3 & 2) != 0 )
      {
        DbgPrint("SkpspReadPolicyMetadataCallback: Invalid Parent SD Policy - duplicate entry\n");
        return 3221225506LL;
      }
      if ( v8 != 11 )
      {
        DbgPrint("SkpspReadPolicyMetadataCallback: Invalid Parent SD Policy type\n");
        return 3221225506LL;
      }
      if ( (unsigned int)RtlReadImagePolicyValue(a1, a2, 0, a3 + 40) != -1073741789 )
        return 3221225506LL;
      *(_DWORD *)a3 |= 2u;
      if ( v3 )
        ULong64FromUser = RtlReadULong64FromUser(a2 + 1);
      else
        ULong64FromUser = a2[1];
      *(_QWORD *)(a3 + 24) = ULong64FromUser;
      break;
    case 7:
      if ( (*(_DWORD *)a3 & 4) != 0 )
      {
        DbgPrint("SkpspReadPolicyMetadataCallback: Invalid Parent SD Revision Policy - duplicate entry\n");
        return 3221225506LL;
      }
      if ( v8 != 7 )
      {
        DbgPrint("SkpspReadPolicyMetadataCallback: Invalid Parent SD Revision Policy type\n");
        return 3221225506LL;
      }
      *(_DWORD *)a3 |= 4u;
      if ( v3 )
        v13 = RtlReadULongFromUser(a2 + 1);
      else
        v13 = *((_DWORD *)a2 + 2);
      *(_DWORD *)(a3 + 32) = v13;
      break;
    case 8:
      if ( (*(_DWORD *)a3 & 8) != 0 )
      {
        DbgPrint("SkpspReadPolicyMetadataCallback: Invalid SVN Policy - duplicate entry\n");
        return 3221225506LL;
      }
      if ( v8 != 7 )
      {
        DbgPrint("SkpspReadPolicyMetadataCallback: Invalid SVN Policy type\n");
        return 3221225506LL;
      }
      v11 = (int *)(a2 + 1);
      *(_DWORD *)a3 |= 8u;
      if ( v3 )
        v12 = RtlReadULongFromUser(v11);
      else
        v12 = *v11;
      *(_DWORD *)(*(_QWORD *)(a3 + 48) + 416LL) = v12;
      break;
    case 10:
      if ( v8 != 9 )
      {
        DbgPrint("SkpspReadPolicyMetadataCallback: Invalid capability Policy type\n");
        return 3221225506LL;
      }
      if ( v3 )
        v10 = RtlReadULong64FromUser(a2 + 1);
      else
        v10 = a2[1];
      if ( v10 >= 8 )
      {
        DbgPrint("SkpspReadPolicyMetadataCallback: Invalid capability policy with value %I64u\n");
        return 3221225506LL;
      }
      *(_QWORD *)(*(_QWORD *)(a3 + 48) + 400LL) |= 1LL << v10;
      break;
    case 11:
      if ( (int)SkpspCaptureScenarioId(*(_QWORD *)(a3 + 48), a1, a2) < 0 )
        return 3221225506LL;
      break;
    case 12:
      if ( v8 != 9 )
      {
        DbgPrint("SkpspReadPolicyMetadataCallback: Invalid capability overridable Policy type\n");
        return 3221225506LL;
      }
      if ( v3 )
        v9 = RtlReadULong64FromUser(a2 + 1);
      else
        v9 = a2[1];
      if ( v9 >= 8 )
      {
        DbgPrint("SkpspReadPolicyMetadataCallback: Invalid capability overridable policy with value %I64u\n");
        return 3221225506LL;
      }
      *(_QWORD *)(*(_QWORD *)(a3 + 48) + 408LL) |= 1LL << v9;
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x1400b2690  mov     [rsp+arg_0], rbx
0x1400b2695  push    rbp
0x1400b2696  push    rsi
0x1400b2697  push    rdi
0x1400b2698  sub     rsp, 20h
0x1400b269c  mov     sil, [r8+4]
0x1400b26a0  mov     rdi, rdx
0x1400b26a3  add     rdx, 4; Src
0x1400b26a7  mov     [rsp+38h+arg_10], 0
0x1400b26af  mov     [rsp+38h+arg_8], 0
0x1400b26b7  mov     rbx, r8
0x1400b26ba  mov     rbp, rcx
0x1400b26bd  test    sil, sil
0x1400b26c0  jz      short loc_1400B26DE
0x1400b26c2  mov     rcx, rdx
0x1400b26c5  call    RtlReadULongFromUser
0x1400b26ca  mov     rcx, rdi
0x1400b26cd  mov     [rsp+38h+arg_10], eax
0x1400b26d1  call    RtlReadULongFromUser
0x1400b26d6  mov     edx, eax
0x1400b26d8  mov     [rsp+38h+arg_8], eax
0x1400b26dc  jmp     short loc_1400B2705
0x1400b26de  mov     r8d, 4; Size
0x1400b26e4  lea     rcx, [rsp+38h+arg_10]; void *
0x1400b26e9  call    RtlCopyVolatileMemory
0x1400b26ee  mov     r8d, 4; Size
0x1400b26f4  lea     rcx, [rsp+38h+arg_8]; void *
0x1400b26f9  mov     rdx, rdi; Src
0x1400b26fc  call    RtlCopyVolatileMemory
0x1400b2701  mov     edx, [rsp+38h+arg_8]
0x1400b2705  mov     ecx, [rsp+38h+arg_10]
0x1400b2709  sub     ecx, 1
0x1400b270c  jz      loc_1400B28E9
0x1400b2712  sub     ecx, 5
0x1400b2715  jz      loc_1400B2896
0x1400b271b  sub     ecx, 1
0x1400b271e  jz      loc_1400B2853
0x1400b2724  sub     ecx, 1
0x1400b2727  jz      loc_1400B2808
0x1400b272d  sub     ecx, 2
0x1400b2730  jz      short loc_1400B27AE
0x1400b2732  sub     ecx, 1
0x1400b2735  jz      short loc_1400B2792
0x1400b2737  cmp     ecx, 1
0x1400b273a  jnz     loc_1400B292F
0x1400b2740  cmp     edx, 9
0x1400b2743  jz      short loc_1400B2751
0x1400b2745  lea     rcx, aSkpspreadpolic_4; "SkpspReadPolicyMetadataCallback: Invali"...
0x1400b274c  jmp     loc_1400B28F6
0x1400b2751  test    sil, sil
0x1400b2754  jz      short loc_1400B2764
0x1400b2756  lea     rcx, [rdi+8]
0x1400b275a  call    RtlReadULong64FromUser
0x1400b275f  mov     rdx, rax
0x1400b2762  jmp     short loc_1400B2768
0x1400b2764  mov     rdx, [rdi+8]
0x1400b2768  cmp     rdx, 8
0x1400b276c  jb      short loc_1400B2777
0x1400b276e  lea     rcx, aSkpspreadpolic_7; "SkpspReadPolicyMetadataCallback: Invali"...
0x1400b2775  jmp     short loc_1400B27E3
0x1400b2777  mov     rcx, [rbx+30h]
0x1400b277b  mov     rax, [rcx+198h]
0x1400b2782  bts     rax, rdx
0x1400b2786  mov     [rcx+198h], rax
0x1400b278d  jmp     loc_1400B292F
0x1400b2792  mov     rcx, [rbx+30h]
0x1400b2796  mov     r8, rdi
0x1400b2799  mov     rdx, rbp
0x1400b279c  call    SkpspCaptureScenarioId
0x1400b27a1  test    eax, eax
0x1400b27a3  js      loc_1400B28FB
0x1400b27a9  jmp     loc_1400B292F
0x1400b27ae  cmp     edx, 9
0x1400b27b1  jz      short loc_1400B27BF
0x1400b27b3  lea     rcx, aSkpspreadpolic_10; "SkpspReadPolicyMetadataCallback: Invali"...
0x1400b27ba  jmp     loc_1400B28F6
0x1400b27bf  test    sil, sil
0x1400b27c2  jz      short loc_1400B27D2
0x1400b27c4  lea     rcx, [rdi+8]
0x1400b27c8  call    RtlReadULong64FromUser
0x1400b27cd  mov     rdx, rax
0x1400b27d0  jmp     short loc_1400B27D6
0x1400b27d2  mov     rdx, [rdi+8]
0x1400b27d6  cmp     rdx, 8
0x1400b27da  jb      short loc_1400B27ED
0x1400b27dc  lea     rcx, aSkpspreadpolic_9; "SkpspReadPolicyMetadataCallback: Invali"...
0x1400b27e3  call    DbgPrint
0x1400b27e8  jmp     loc_1400B28FB
0x1400b27ed  mov     rcx, [rbx+30h]
0x1400b27f1  mov     rax, [rcx+190h]
0x1400b27f8  bts     rax, rdx
0x1400b27fc  mov     [rcx+190h], rax
0x1400b2803  jmp     loc_1400B292F
0x1400b2808  mov     eax, [rbx]
0x1400b280a  test    al, 8
0x1400b280c  jz      short loc_1400B281A
0x1400b280e  lea     rcx, aSkpspreadpolic_0; "SkpspReadPolicyMetadataCallback: Invali"...
0x1400b2815  jmp     loc_1400B28F6
0x1400b281a  cmp     edx, 7
0x1400b281d  jz      short loc_1400B282B
0x1400b281f  lea     rcx, aSkpspreadpolic_6; "SkpspReadPolicyMetadataCallback: Invali"...
0x1400b2826  jmp     loc_1400B28F6
0x1400b282b  or      eax, 8
0x1400b282e  lea     rcx, [rdi+8]
0x1400b2832  mov     [rbx], eax
0x1400b2834  test    sil, sil
0x1400b2837  jz      short loc_1400B2842
0x1400b2839  call    RtlReadULongFromUser
0x1400b283e  mov     ecx, eax
0x1400b2840  jmp     short loc_1400B2844
0x1400b2842  mov     ecx, [rcx]
0x1400b2844  mov     rax, [rbx+30h]
0x1400b2848  mov     [rax+1A0h], ecx
0x1400b284e  jmp     loc_1400B292F
0x1400b2853  mov     eax, [rbx]
0x1400b2855  test    al, 4
0x1400b2857  jz      short loc_1400B2865
0x1400b2859  lea     rcx, aSkpspreadpolic_8; "SkpspReadPolicyMetadataCallback: Invali"...
0x1400b2860  jmp     loc_1400B28F6
0x1400b2865  cmp     edx, 7
0x1400b2868  jz      short loc_1400B2876
0x1400b286a  lea     rcx, aSkpspreadpolic_3; "SkpspReadPolicyMetadataCallback: Invali"...
0x1400b2871  jmp     loc_1400B28F6
0x1400b2876  or      eax, 4
0x1400b2879  mov     [rbx], eax
0x1400b287b  test    sil, sil
0x1400b287e  jz      short loc_1400B288B
0x1400b2880  lea     rcx, [rdi+8]
0x1400b2884  call    RtlReadULongFromUser
0x1400b2889  jmp     short loc_1400B288E
0x1400b288b  mov     eax, [rdi+8]
0x1400b288e  mov     [rbx+20h], eax
0x1400b2891  jmp     loc_1400B292F
0x1400b2896  mov     eax, [rbx]
0x1400b2898  test    al, 2
0x1400b289a  jz      short loc_1400B28A5
0x1400b289c  lea     rcx, aSkpspreadpolic; "SkpspReadPolicyMetadataCallback: Invali"...
0x1400b28a3  jmp     short loc_1400B28F6
0x1400b28a5  cmp     edx, 0Bh
0x1400b28a8  jz      short loc_1400B28B3
0x1400b28aa  lea     rcx, aSkpspreadpolic_2; "SkpspReadPolicyMetadataCallback: Invali"...
0x1400b28b1  jmp     short loc_1400B28F6
0x1400b28b3  lea     r9, [rbx+28h]
0x1400b28b7  xor     r8d, r8d
0x1400b28ba  mov     rdx, rdi
0x1400b28bd  mov     rcx, rbp
0x1400b28c0  call    RtlReadImagePolicyValue
0x1400b28c5  cmp     eax, 0C0000023h
0x1400b28ca  jnz     short loc_1400B28FB
0x1400b28cc  or      dword ptr [rbx], 2
0x1400b28cf  test    sil, sil
0x1400b28d2  jz      short loc_1400B28DF
0x1400b28d4  lea     rcx, [rdi+8]
0x1400b28d8  call    RtlReadULong64FromUser
0x1400b28dd  jmp     short loc_1400B28E3
0x1400b28df  mov     rax, [rdi+8]
0x1400b28e3  mov     [rbx+18h], rax
0x1400b28e7  jmp     short loc_1400B292F
0x1400b28e9  mov     eax, [rbx]
0x1400b28eb  test    al, 1
0x1400b28ed  jz      short loc_1400B2902
0x1400b28ef  lea     rcx, aSkpspreadpolic_1; "SkpspReadPolicyMetadataCallback: Invali"...
0x1400b28f6  call    DbgPrint
0x1400b28fb  mov     eax, 0C0000022h
0x1400b2900  jmp     short loc_1400B2931
0x1400b2902  cmp     edx, 7
0x1400b2905  jz      short loc_1400B2910
0x1400b2907  lea     rcx, aSkpspreadpolic_5; "SkpspReadPolicyMetadataCallback: Invali"...
0x1400b290e  jmp     short loc_1400B28F6
0x1400b2910  test    sil, sil
0x1400b2913  jz      short loc_1400B2920
0x1400b2915  lea     rcx, [rdi+8]
0x1400b2919  call    RtlReadULongFromUser
0x1400b291e  jmp     short loc_1400B2923
0x1400b2920  mov     eax, [rdi+8]
0x1400b2923  cmp     eax, 1
0x1400b2926  jnz     short loc_1400B292C
0x1400b2928  or      dword ptr [rbx+8], 20h
0x1400b292c  or      dword ptr [rbx], 1
0x1400b292f  xor     eax, eax
0x1400b2931  mov     rbx, [rsp+38h+arg_0]
0x1400b2936  add     rsp, 20h
0x1400b293a  pop     rdi
0x1400b293b  pop     rsi
0x1400b293c  pop     rbp
0x1400b293d  retn
```
