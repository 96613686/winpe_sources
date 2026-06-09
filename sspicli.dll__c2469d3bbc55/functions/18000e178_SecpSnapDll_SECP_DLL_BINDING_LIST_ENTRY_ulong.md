# SecpSnapDll(_SECP_DLL_BINDING *,_LIST_ENTRY *,ulong *)

- ea: `0x18000e178`
- end: `0x18000e889`
- name: `?SecpSnapDll@@YAJPEAU_SECP_DLL_BINDING@@PEAU_LIST_ENTRY@@PEAK@Z`
- size: `1809`
- prototype: `__int64 __fastcall(struct _SECP_DLL_BINDING *, struct _LIST_ENTRY *, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d6ec`
- `0x18001caa0`

## callees

- `0x18000cfec`
- `0x18000e178`
- `0x18000ee2c`
- `0x180016694`
- `0x18001d478`
- `0x18001d71c`
- `0x180022047`
- `0x180023010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000e354`
- `ntdll!RtlInitUnicodeString` at `0x18000e38a`
- `ntdll!RtlInitUnicodeString` at `0x18000e354`
- `ntdll!RtlInitUnicodeString` at `0x18000e38a`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18000e528`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18000e528`
- `ntdll!RtlCompareUnicodeString` at `0x18000e54d`
- `ntdll!RtlCompareUnicodeString` at `0x18000e54d`
- `ntdll!RtlFreeUnicodeString` at `0x18000e582`
- `ntdll!RtlFreeUnicodeString` at `0x18000e582`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e44b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e454`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e812`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e81b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e864`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e86f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e44b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e454`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e812`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e81b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e864`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e86f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e2c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e5ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e5fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e669`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e718`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e769`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e2c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e5ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e5fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e669`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e718`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e769`

## pseudocode

```c
__int64 __fastcall SecpSnapDll(struct _LIST_ENTRY *a1, struct _LIST_ENTRY *a2, unsigned int *a3)
{
  int v6; // esi
  struct _LIST_ENTRY *v7; // rbx
  struct _LIST_ENTRY *v8; // r13
  unsigned int i; // r12d
  struct _LIST_ENTRY *v10; // rax
  __int64 v11; // r15
  struct _LIST_ENTRY *v12; // rax
  struct _LIST_ENTRY *v13; // rcx
  struct _LIST_ENTRY *v14; // rax
  __int64 v15; // r8
  struct _LIST_ENTRY **v16; // rcx
  struct _LIST_ENTRY **v17; // rax
  unsigned int j; // eax
  __int64 v19; // r12
  struct _LIST_ENTRY *k; // r15
  __int64 v21; // rax
  unsigned int v22; // eax
  struct _LIST_ENTRY *v23; // rax
  __int64 v24; // rax
  unsigned int v25; // eax
  struct _LIST_ENTRY *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  struct _LIST_ENTRY *v29; // rax
  struct _LIST_ENTRY *v30; // rax
  struct _LIST_ENTRY *v31; // rcx
  struct _LIST_ENTRY *v32; // r15
  __int64 v33; // rax
  unsigned int v34; // eax
  struct _LIST_ENTRY *v35; // rax
  __int64 v36; // rax
  unsigned int v37; // eax
  struct _LIST_ENTRY *v38; // rax
  __int64 v39; // r8
  struct _LIST_ENTRY **v40; // r12
  struct _LIST_ENTRY *v41; // rax
  __int64 v43; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+28h] [rbp-A0h] BYREF
  int v45; // [rsp+30h] [rbp-98h]
  HLOCAL hMem; // [rsp+38h] [rbp-90h] BYREF
  struct _LIST_ENTRY *v47; // [rsp+40h] [rbp-88h]
  int v48; // [rsp+48h] [rbp-80h] BYREF
  HLOCAL v49; // [rsp+50h] [rbp-78h] BYREF
  struct _LIST_ENTRY **p_Flink; // [rsp+58h] [rbp-70h]
  struct _LIST_ENTRY **p_Blink; // [rsp+60h] [rbp-68h]
  struct _LIST_ENTRY *v52; // [rsp+68h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-58h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+80h] [rbp-48h] BYREF
  unsigned int v56; // [rsp+D8h] [rbp+10h]
  unsigned int v58; // [rsp+E8h] [rbp+20h] BYREF

  hMem = 0;
  v49 = 0;
  v58 = 0;
  v43 = 0;
  v44 = 0;
  Destination = 0;
  DestinationString = 0;
  v48 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, a3, a1[1].Blink);
  p_Blink = &a2->Blink;
  a2->Blink = a2;
  a2->Flink = a2;
  *a3 = 0;
  v6 = SecpBindSspiDll(
         (struct _SECP_DLL_BINDING *)a1,
         (struct _SECURITY_FUNCTION_TABLE_A **)&hMem,
         (struct _SECURITY_FUNCTION_TABLE_W **)&v49,
         &v48);
  if ( v6 < 0 )
    goto LABEL_73;
  p_Flink = &a2->Blink;
  v7 = 0;
  v47 = 0;
  if ( v49 )
  {
    v6 = (*((__int64 (__fastcall **)(unsigned int *, __int64 *))v49 + 1))(&v58, &v44);
    v45 = v6;
    if ( v6 < 0 )
      goto LABEL_74;
    v52 = 0;
    v8 = 0;
    for ( i = 0; i < v58; ++i )
    {
      v10 = (struct _LIST_ENTRY *)LocalAlloc(0x40u, 0xD8u);
      v7 = v10;
      v47 = v10;
      if ( !v10 )
        goto LABEL_25;
      LODWORD(v10[1].Flink) = 33;
      v11 = 32LL * i;
      LODWORD(v10[5].Flink) = *(_DWORD *)(v11 + v44);
      v12 = (struct _LIST_ENTRY *)v49;
      v7[10].Blink = (struct _LIST_ENTRY *)v49;
      v7[11].Flink = v12;
      v13 = (struct _LIST_ENTRY *)(SecSspiPackageCount + 0x10000);
      ++SecSspiPackageCount;
      v7[1].Blink = v13;
      LODWORD(v7[2].Flink) = i;
      v14 = v52;
      if ( !i )
        v14 = v7;
      v52 = v14;
      v7[4].Flink = v14;
      if ( v8 )
        v8[4].Blink = v7;
      RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v11 + v44 + 16));
      if ( !(unsigned int)SecpDuplicateString((struct _UNICODE_STRING *)&v7[6], &DestinationString) )
        goto LABEL_24;
      v7[8].Flink = 0;
      RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v11 + v44 + 24));
      if ( !(unsigned int)SecpDuplicateString((struct _UNICODE_STRING *)&v7[7], &DestinationString) )
      {
        LocalFree(v7[6].Blink);
LABEL_24:
        LocalFree(v7);
LABEL_25:
        v6 = -2146893056;
        break;
      }
      WORD2(v7[5].Flink) = *(_WORD *)(v11 + v44 + 4);
      HIWORD(v7[5].Flink) = *(_WORD *)(v11 + v44 + 6);
      HIDWORD(v7[5].Blink) = *(_DWORD *)(v11 + v44 + 8);
      v7[3].Blink = a1;
      if ( v52 )
        ++LODWORD(a1[2].Flink);
      ++*a3;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, v15, v7[6].Blink);
      v16 = p_Blink;
      v17 = (struct _LIST_ENTRY **)*p_Blink;
      if ( (*p_Blink)->Flink != a2 )
LABEL_67:
        __fastfail(3u);
      v8 = v7;
      v7->Flink = a2;
      v7->Blink = (struct _LIST_ENTRY *)v17;
      *v17 = v7;
      *v16 = v7;
    }
    if ( v44 )
    {
      (*((void (**)(void))v49 + 16))();
      v44 = 0;
    }
  }
  if ( !hMem )
    goto LABEL_73;
  if ( v6 >= 0 )
  {
    v6 = (*((__int64 (__fastcall **)(unsigned int *, __int64 *))hMem + 1))(&v58, &v43);
    v45 = v6;
    if ( v6 >= 0 )
    {
      p_Flink = 0;
      v47 = 0;
      for ( j = 0; ; j = v56 + 1 )
      {
        v56 = j;
        if ( j >= v58 )
          break;
        v19 = 32LL * j;
        if ( !RtlCreateUnicodeStringFromAsciiz(&Destination, *(PCSZ *)(v19 + v43 + 16)) )
          goto LABEL_70;
        for ( k = a2->Flink; k != a2; k = k->Flink )
        {
          v7 = k;
          if ( !RtlCompareUnicodeString(&Destination, (PCUNICODE_STRING)&k[6], 1u) )
            break;
          v7 = 0;
        }
        if ( v7 )
        {
          LODWORD(v7[1].Flink) |= 0x10u;
          v7[10].Flink = (struct _LIST_ENTRY *)hMem;
          RtlFreeUnicodeString(&Destination);
          v21 = -1;
          do
            ++v21;
          while ( *(_BYTE *)(*(_QWORD *)(v19 + v43 + 16) + v21) );
          v22 = v21 + 1;
          LODWORD(v7[8].Blink) = v22;
          v23 = (struct _LIST_ENTRY *)LocalAlloc(0, v22);
          v7[8].Flink = v23;
          if ( v23 )
            memcpy_0(v23, *(const void **)(v19 + v43 + 16), LODWORD(v7[8].Blink));
          v24 = -1;
          do
            ++v24;
          while ( *(_BYTE *)(*(_QWORD *)(v19 + v43 + 24) + v24) );
          v25 = v24 + 1;
          LODWORD(v7[9].Blink) = v25;
          v26 = (struct _LIST_ENTRY *)LocalAlloc(0, v25);
          v7[9].Flink = v26;
          if ( v26 )
            memcpy_0(v26, *(const void **)(v19 + v43 + 24), LODWORD(v7[9].Blink));
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, v28, *(_QWORD *)(v19 + v43 + 16));
        }
        else
        {
          v29 = (struct _LIST_ENTRY *)LocalAlloc(0x40u, 0xD8u);
          v7 = v29;
          if ( !v29 )
            goto LABEL_70;
          LODWORD(v29[1].Flink) = 17;
          LODWORD(v29[5].Flink) = *(_DWORD *)(v19 + v43);
          v30 = (struct _LIST_ENTRY *)hMem;
          v7[10].Flink = (struct _LIST_ENTRY *)hMem;
          v7[11].Flink = v30;
          v31 = (struct _LIST_ENTRY *)(SecSspiPackageCount + 0x10000);
          ++SecSspiPackageCount;
          v7[1].Blink = v31;
          LODWORD(v7[2].Flink) = v56;
          v32 = (struct _LIST_ENTRY *)p_Flink;
          if ( !v56 )
            v32 = v7;
          p_Flink = &v32->Flink;
          v7[4].Flink = v32;
          if ( v47 )
            v47[4].Blink = v7;
          v7[6] = (struct _LIST_ENTRY)Destination;
          v33 = -1;
          do
            ++v33;
          while ( *(_BYTE *)(*(_QWORD *)(v19 + v43 + 16) + v33) );
          v34 = v33 + 1;
          LODWORD(v7[8].Blink) = v34;
          v35 = (struct _LIST_ENTRY *)LocalAlloc(0, v34);
          v7[8].Flink = v35;
          if ( !v35 )
            goto LABEL_69;
          memcpy_0(v35, *(const void **)(v19 + v43 + 16), LODWORD(v7[8].Blink));
          v36 = -1;
          do
            ++v36;
          while ( *(_BYTE *)(*(_QWORD *)(v19 + v43 + 24) + v36) );
          v37 = v36 + 1;
          LODWORD(v7[9].Blink) = v37;
          v38 = (struct _LIST_ENTRY *)LocalAlloc(0, v37);
          v7[9].Flink = v38;
          if ( !v38 )
          {
            LocalFree(v7[8].Flink);
LABEL_69:
            LocalFree(v7);
LABEL_70:
            v6 = -2146893056;
            break;
          }
          memcpy_0(v38, *(const void **)(v19 + v43 + 24), LODWORD(v7[9].Blink));
          v7[3].Blink = a1;
          ++LODWORD(a1[2].Flink);
          ++*a3;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v39, v7[6].Blink);
          v40 = p_Blink;
          v41 = *p_Blink;
          if ( (*p_Blink)->Flink != a2 )
            goto LABEL_67;
          v47 = v7;
          v7->Flink = a2;
          v7->Blink = v41;
          v41->Flink = v7;
          *v40 = v7;
        }
      }
      if ( v43 )
      {
        (*((void (**)(void))hMem + 16))();
        v43 = 0;
      }
LABEL_73:
      if ( v6 >= 0 )
        return (unsigned int)v6;
    }
  }
LABEL_74:
  SecpFreePackages(a2, 0);
  if ( v48 )
  {
    LocalFree(hMem);
    LocalFree(v49);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e178  mov     rax, rsp
0x18000e17b  mov     [rax+18h], r8
0x18000e17f  mov     [rax+10h], rdx
0x18000e183  mov     [rax+8], rcx
0x18000e187  push    rbx
0x18000e188  push    rsi
0x18000e189  push    r12
0x18000e18b  push    r13
0x18000e18d  push    r14
0x18000e18f  push    r15
0x18000e191  sub     rsp, 98h
0x18000e198  mov     rbx, r8
0x18000e19b  mov     r14, rdx
0x18000e19e  mov     r15, rcx
0x18000e1a1  mov     [rsp+0C8h+hMem], 0
0x18000e1aa  mov     qword ptr [rax-78h], 0
0x18000e1b2  mov     dword ptr [rax+20h], 0
0x18000e1b9  mov     [rsp+0C8h+var_A8], 0
0x18000e1c2  mov     [rsp+0C8h+var_A0], 0
0x18000e1cb  xorps   xmm0, xmm0
0x18000e1ce  movups  xmmword ptr [rax-48h], xmm0
0x18000e1d2  xorps   xmm1, xmm1
0x18000e1d5  movups  xmmword ptr [rax-58h], xmm1
0x18000e1d9  mov     dword ptr [rax-80h], 0
0x18000e1e0  lea     r13, WPP_GLOBAL_Control
0x18000e1e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1ee  cmp     rcx, r13
0x18000e1f1  jz      short loc_18000E20B
0x18000e1f3  test    byte ptr [rcx+1Ch], 4
0x18000e1f7  jz      short loc_18000E20B
0x18000e1f9  mov     edx, 23h ; '#'
0x18000e1fe  mov     r9, [r15+18h]
0x18000e202  mov     rcx, [rcx+10h]
0x18000e206  call    WPP_SF_S
0x18000e20b  lea     r12, [r14+8]
0x18000e20f  mov     [rsp+0C8h+var_68], r12
0x18000e214  mov     [r12], r14
0x18000e218  mov     [r14], r14
0x18000e21b  mov     dword ptr [rbx], 0
0x18000e221  lea     r9, [rsp+0C8h+var_80]; int *
0x18000e226  lea     r8, [rsp+0C8h+var_78]; struct _SECURITY_FUNCTION_TABLE_W **
0x18000e22b  lea     rdx, [rsp+0C8h+hMem]; struct _SECURITY_FUNCTION_TABLE_A **
0x18000e230  mov     rcx, r15; struct _SECP_DLL_BINDING *
0x18000e233  call    ?SecpBindSspiDll@@YAJPEAU_SECP_DLL_BINDING@@PEAPEAU_SECURITY_FUNCTION_TABLE_A@@PEAPEAU_SECURITY_FUNCTION_TABLE_W@@PEAH@Z; SecpBindSspiDll(_SECP_DLL_BINDING *,_SECURITY_FUNCTION_TABLE_A * *,_SECURITY_FUNCTION_TABLE_W * *,int *)
0x18000e238  mov     esi, eax
0x18000e23a  test    eax, eax
0x18000e23c  js      loc_18000E84A
0x18000e242  mov     [rsp+0C8h+var_70], r12
0x18000e247  xor     ebx, ebx
0x18000e249  mov     [rsp+0C8h+var_88], rbx
0x18000e24e  mov     rax, [rsp+0C8h+var_78]
0x18000e253  test    rax, rax
0x18000e256  jz      loc_18000E483
0x18000e25c  lea     rdx, [rsp+0C8h+var_A0]
0x18000e261  lea     rcx, [rsp+0C8h+arg_18]
0x18000e269  mov     rax, [rax+8]
0x18000e26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e272  mov     esi, eax
0x18000e274  mov     [rsp+0C8h+var_98], eax
0x18000e278  jmp     short loc_18000E29A
0x18000e27a  mov     esi, 80090301h
0x18000e27f  mov     [rsp+0C8h+var_98], esi
0x18000e283  mov     r14, [rsp+0C8h+arg_8]
0x18000e28b  mov     rbx, [rsp+0C8h+var_88]
0x18000e290  mov     rcx, [rsp+0C8h+var_70]
0x18000e295  mov     [rsp+0C8h+var_68], rcx
0x18000e29a  test    esi, esi
0x18000e29c  js      loc_18000E84E
0x18000e2a2  xor     eax, eax
0x18000e2a4  mov     [rsp+0C8h+var_60], rax
0x18000e2a9  xor     r13d, r13d
0x18000e2ac  xor     r12d, r12d
0x18000e2af  cmp     r12d, [rsp+0C8h+arg_18]
0x18000e2b7  jnb     loc_18000E45F
0x18000e2bd  mov     edx, 0D8h; uBytes
0x18000e2c2  mov     ecx, 40h ; '@'; uFlags
0x18000e2c7  call    cs:__imp_LocalAlloc
0x18000e2cd  mov     rbx, rax
0x18000e2d0  mov     [rsp+0C8h+var_88], rax
0x18000e2d5  test    rax, rax
0x18000e2d8  jz      loc_18000E45A
0x18000e2de  mov     dword ptr [rax+10h], 21h ; '!'
0x18000e2e5  mov     r15d, r12d
0x18000e2e8  shl     r15, 5
0x18000e2ec  mov     rcx, [rsp+0C8h+var_A0]
0x18000e2f1  mov     edx, [r15+rcx]
0x18000e2f5  mov     [rax+50h], edx
0x18000e2f8  mov     rax, [rsp+0C8h+var_78]
0x18000e2fd  mov     [rbx+0A8h], rax
0x18000e304  mov     [rbx+0B0h], rax
0x18000e30b  mov     edx, cs:?SecSspiPackageCount@@3KA; ulong SecSspiPackageCount
0x18000e311  lea     ecx, [rdx+10000h]
0x18000e317  inc     edx
0x18000e319  mov     cs:?SecSspiPackageCount@@3KA, edx; ulong SecSspiPackageCount
0x18000e31f  mov     [rbx+18h], rcx
0x18000e323  mov     [rbx+20h], r12d
0x18000e327  mov     rax, [rsp+0C8h+var_60]
0x18000e32c  test    r12d, r12d
0x18000e32f  cmovz   rax, rbx
0x18000e333  mov     [rsp+0C8h+var_60], rax
0x18000e338  mov     [rbx+40h], rax
0x18000e33c  test    r13, r13
0x18000e33f  jz      short loc_18000E345
0x18000e341  mov     [r13+48h], rbx
0x18000e345  mov     rdx, [rsp+0C8h+var_A0]
0x18000e34a  mov     rdx, [r15+rdx+10h]; SourceString
0x18000e34f  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x18000e354  call    cs:__imp_RtlInitUnicodeString
0x18000e35a  lea     rcx, [rbx+60h]; struct _UNICODE_STRING *
0x18000e35e  lea     rdx, [rsp+0C8h+DestinationString]; struct _UNICODE_STRING *
0x18000e363  call    ?SecpDuplicateString@@YAHPEAU_UNICODE_STRING@@0@Z; SecpDuplicateString(_UNICODE_STRING *,_UNICODE_STRING *)
0x18000e368  test    eax, eax
0x18000e36a  jz      loc_18000E451
0x18000e370  mov     qword ptr [rbx+80h], 0
0x18000e37b  mov     rdx, [rsp+0C8h+var_A0]
0x18000e380  mov     rdx, [r15+rdx+18h]; SourceString
0x18000e385  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x18000e38a  call    cs:__imp_RtlInitUnicodeString
0x18000e390  lea     rcx, [rbx+70h]; struct _UNICODE_STRING *
0x18000e394  lea     rdx, [rsp+0C8h+DestinationString]; struct _UNICODE_STRING *
0x18000e399  call    ?SecpDuplicateString@@YAHPEAU_UNICODE_STRING@@0@Z; SecpDuplicateString(_UNICODE_STRING *,_UNICODE_STRING *)
0x18000e39e  test    eax, eax
0x18000e3a0  jz      loc_18000E447
0x18000e3a6  mov     rax, [rsp+0C8h+var_A0]
0x18000e3ab  movzx   ecx, word ptr [r15+rax+4]
0x18000e3b1  mov     [rbx+54h], cx
0x18000e3b5  mov     rax, [rsp+0C8h+var_A0]
0x18000e3ba  movzx   ecx, word ptr [r15+rax+6]
0x18000e3c0  mov     [rbx+56h], cx
0x18000e3c4  mov     rax, [rsp+0C8h+var_A0]
0x18000e3c9  mov     ecx, [r15+rax+8]
0x18000e3ce  mov     [rbx+5Ch], ecx
0x18000e3d1  mov     r15, [rsp+0C8h+arg_0]
0x18000e3d9  mov     [rbx+38h], r15
0x18000e3dd  cmp     [rsp+0C8h+var_60], 0
0x18000e3e3  jz      short loc_18000E3E9
0x18000e3e5  inc     dword ptr [r15+20h]
0x18000e3e9  mov     rax, [rsp+0C8h+arg_10]
0x18000e3f1  inc     dword ptr [rax]
0x18000e3f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3fa  lea     rax, WPP_GLOBAL_Control
0x18000e401  cmp     rcx, rax
0x18000e404  jz      short loc_18000E41E
0x18000e406  test    byte ptr [rcx+1Ch], 4
0x18000e40a  jz      short loc_18000E41E
0x18000e40c  mov     edx, 24h ; '$'
0x18000e411  mov     r9, [rbx+68h]
0x18000e415  mov     rcx, [rcx+10h]
0x18000e419  call    WPP_SF_S
0x18000e41e  mov     rcx, [rsp+0C8h+var_68]
0x18000e423  mov     rax, [rcx]
0x18000e426  cmp     [rax], r14
0x18000e429  jnz     loc_18000E804
0x18000e42f  mov     r13, rbx
0x18000e432  mov     [rbx], r14
0x18000e435  mov     [rbx+8], rax
0x18000e439  mov     [rax], rbx
0x18000e43c  mov     [rcx], rbx
0x18000e43f  inc     r12d
0x18000e442  jmp     loc_18000E2AF
0x18000e447  mov     rcx, [rbx+68h]; hMem
0x18000e44b  call    cs:__imp_LocalFree
0x18000e451  mov     rcx, rbx; hMem
0x18000e454  call    cs:__imp_LocalFree
0x18000e45a  mov     esi, 80090300h
0x18000e45f  mov     rcx, [rsp+0C8h+var_A0]
0x18000e464  test    rcx, rcx
0x18000e467  jz      short loc_18000E483
0x18000e469  mov     rax, [rsp+0C8h+var_78]
0x18000e46e  mov     rax, [rax+80h]
0x18000e475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e47a  mov     [rsp+0C8h+var_A0], 0
0x18000e483  mov     rax, [rsp+0C8h+hMem]
0x18000e488  test    rax, rax
0x18000e48b  jz      loc_18000E84A
0x18000e491  test    esi, esi
0x18000e493  js      loc_18000E84E
0x18000e499  lea     rdx, [rsp+0C8h+var_A8]
0x18000e49e  lea     rcx, [rsp+0C8h+arg_18]
0x18000e4a6  mov     rax, [rax+8]
0x18000e4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4af  mov     esi, eax
0x18000e4b1  mov     [rsp+0C8h+var_98], eax
0x18000e4b5  jmp     short loc_18000E4D7
0x18000e4b7  mov     esi, 80090301h
0x18000e4bc  mov     [rsp+0C8h+var_98], esi
0x18000e4c0  mov     r14, [rsp+0C8h+arg_8]
0x18000e4c8  mov     rbx, [rsp+0C8h+var_88]
0x18000e4cd  mov     rax, [rsp+0C8h+var_70]
0x18000e4d2  mov     [rsp+0C8h+var_68], rax
0x18000e4d7  test    esi, esi
0x18000e4d9  js      loc_18000E84E
0x18000e4df  mov     [rsp+0C8h+var_70], 0
0x18000e4e8  mov     [rsp+0C8h+var_88], 0
0x18000e4f1  xor     eax, eax
0x18000e4f3  mov     r13, [rsp+0C8h+arg_0]
0x18000e4fb  mov     dword ptr [rsp+0C8h+arg_8], eax
0x18000e502  cmp     eax, [rsp+0C8h+arg_18]
0x18000e509  jnb     loc_18000E826
0x18000e50f  mov     r12d, eax
0x18000e512  shl     r12, 5
0x18000e516  mov     rdx, [rsp+0C8h+var_A8]
0x18000e51b  mov     rdx, [r12+rdx+10h]; Source
0x18000e520  lea     rcx, [rsp+0C8h+Destination]; Destination
0x18000e528  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18000e52e  test    al, al
0x18000e530  jz      loc_18000E821
0x18000e536  mov     r15, [r14]
0x18000e539  jmp     short loc_18000E55C
0x18000e53b  mov     rbx, r15
0x18000e53e  lea     rdx, [r15+60h]; String2
0x18000e542  mov     r8b, 1; CaseInsensitive
0x18000e545  lea     rcx, [rsp+0C8h+Destination]; String1
0x18000e54d  call    cs:__imp_RtlCompareUnicodeString
0x18000e553  test    eax, eax
0x18000e555  jz      short loc_18000E561
0x18000e557  xor     ebx, ebx
0x18000e559  mov     r15, [r15]
0x18000e55c  cmp     r15, r14
0x18000e55f  jnz     short loc_18000E53B
0x18000e561  test    rbx, rbx
0x18000e564  jz      loc_18000E65F
0x18000e56a  or      dword ptr [rbx+10h], 10h
0x18000e56e  mov     rax, [rsp+0C8h+hMem]
0x18000e573  mov     [rbx+0A0h], rax
0x18000e57a  lea     rcx, [rsp+0C8h+Destination]; UnicodeString
0x18000e582  call    cs:__imp_RtlFreeUnicodeString
0x18000e588  mov     rax, [rsp+0C8h+var_A8]
0x18000e58d  mov     rcx, [r12+rax+10h]
0x18000e592  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000e596  mov     rax, r15
0x18000e599  inc     rax
0x18000e59c  cmp     byte ptr [rcx+rax], 0
0x18000e5a0  jnz     short loc_18000E599
0x18000e5a2  inc     eax
0x18000e5a4  mov     [rbx+88h], eax
0x18000e5aa  mov     edx, eax; uBytes
0x18000e5ac  xor     ecx, ecx; uFlags
0x18000e5ae  call    cs:__imp_LocalAlloc
0x18000e5b4  mov     [rbx+80h], rax
0x18000e5bb  test    rax, rax
0x18000e5be  jz      short loc_18000E5D9
0x18000e5c0  mov     r8d, [rbx+88h]; Size
0x18000e5c7  mov     rdx, [rsp+0C8h+var_A8]
0x18000e5cc  mov     rdx, [r12+rdx+10h]; Src
0x18000e5d1  mov     rcx, rax; void *
0x18000e5d4  call    memcpy_0
0x18000e5d9  mov     rax, [rsp+0C8h+var_A8]
0x18000e5de  mov     rcx, [r12+rax+18h]
0x18000e5e3  mov     rax, r15
0x18000e5e6  inc     rax
0x18000e5e9  cmp     byte ptr [rcx+rax], 0
0x18000e5ed  jnz     short loc_18000E5E6
0x18000e5ef  inc     eax
0x18000e5f1  mov     [rbx+98h], eax
0x18000e5f7  mov     edx, eax; uBytes
0x18000e5f9  xor     ecx, ecx; uFlags
0x18000e5fb  call    cs:__imp_LocalAlloc
0x18000e601  mov     [rbx+90h], rax
0x18000e608  test    rax, rax
0x18000e60b  jz      short loc_18000E626
0x18000e60d  mov     r8d, [rbx+98h]; Size
0x18000e614  mov     rdx, [rsp+0C8h+var_A8]
0x18000e619  mov     rdx, [r12+rdx+18h]; Src
0x18000e61e  mov     rcx, rax; void *
0x18000e621  call    memcpy_0
0x18000e626  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e62d  lea     rax, WPP_GLOBAL_Control
0x18000e634  cmp     rcx, rax
0x18000e637  jz      loc_18000E7F6
0x18000e63d  test    byte ptr [rcx+1Ch], 4
0x18000e641  jz      loc_18000E7F6
0x18000e647  mov     r9, [rsp+0C8h+var_A8]
0x18000e64c  mov     r9, [r12+r9+10h]
0x18000e651  mov     rcx, [rcx+10h]
0x18000e655  call    WPP_SF_s
0x18000e65a  jmp     loc_18000E7F6
0x18000e65f  mov     edx, 0D8h; uBytes
0x18000e664  mov     ecx, 40h ; '@'; uFlags
0x18000e669  call    cs:__imp_LocalAlloc
0x18000e66f  mov     rbx, rax
0x18000e672  test    rax, rax
0x18000e675  jz      loc_18000E821
0x18000e67b  mov     dword ptr [rax+10h], 11h
0x18000e682  mov     rax, [rsp+0C8h+var_A8]
0x18000e687  mov     ecx, [r12+rax]
0x18000e68b  mov     [rbx+50h], ecx
0x18000e68e  mov     rax, [rsp+0C8h+hMem]
0x18000e693  mov     [rbx+0A0h], rax
0x18000e69a  mov     [rbx+0B0h], rax
0x18000e6a1  mov     edx, cs:?SecSspiPackageCount@@3KA; ulong SecSspiPackageCount
0x18000e6a7  lea     ecx, [rdx+10000h]
0x18000e6ad  inc     edx
0x18000e6af  mov     cs:?SecSspiPackageCount@@3KA, edx; ulong SecSspiPackageCount
0x18000e6b5  mov     [rbx+18h], rcx
0x18000e6b9  mov     eax, dword ptr [rsp+0C8h+arg_8]
0x18000e6c0  mov     [rbx+20h], eax
0x18000e6c3  mov     r15, [rsp+0C8h+var_70]
0x18000e6c8  test    eax, eax
0x18000e6ca  cmovz   r15, rbx
  ... truncated ...
```
