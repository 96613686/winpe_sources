# SamiLookupNamesInDomain(void *,ulong,ulong,_UNICODE_STRING *,ulong * *,_SID_NAME_USE * *)

- ea: `0x180003a00`
- end: `0x1800040cb`
- name: `?SamiLookupNamesInDomain@@YAJPEAXKKPEAU_UNICODE_STRING@@PEAPEAKPEAPEAW4_SID_NAME_USE@@@Z`
- size: `1739`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, struct _UNICODE_STRING *@<r9>, unsigned int **, enum _SID_NAME_USE **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180003760`
- `0x1800038b0`

## callees

- `0x180003220`
- `0x180003a00`
- `0x1800078c0`
- `0x18000807c`
- `0x1800149b8`
- `0x180014a50`
- `0x180014ae0`
- `0x180017935`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004060`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003f93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004060`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003cf3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004029`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004048`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003cf3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004029`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004048`
- `RPCRT4!NdrClientCall3` at `0x180003dd4`
- `RPCRT4!NdrClientCall3` at `0x180003e23`
- `RPCRT4!NdrClientCall3` at `0x180003dd4`
- `RPCRT4!NdrClientCall3` at `0x180003e23`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003e73`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003e73`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017bde`
- `RPCRT4!I_RpcExceptionFilter` at `0x180017bde`

## pseudocode

```c
__int64 __fastcall SamiLookupNamesInDomain(
        void **a1,
        int a2,
        __int64 a3,
        struct _UNICODE_STRING *a4,
        unsigned int **a5,
        enum _SID_NAME_USE **a6)
{
  __int64 v7; // rdi
  int Pointer; // ebx
  unsigned int v12; // edx
  int v13; // r12d
  unsigned int v14; // r13d
  _QWORD *v15; // rcx
  unsigned int *v16; // rdx
  enum _SID_NAME_USE *v17; // r9
  const void **v18; // rdi
  __int64 v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  __int64 v22; // rax
  unsigned int *v23; // rax
  unsigned int *v24; // rdx
  char *v25; // r9
  char *v26; // r10
  unsigned int v27; // r8d
  unsigned int v28; // ecx
  struct _UNICODE_STRING *v29; // r11
  unsigned int **v30; // rax
  struct _UNICODE_STRING *v31; // rcx
  unsigned int v32; // eax
  CLIENT_CALL_RETURN v33; // rax
  struct _UNICODE_STRING *v34; // rcx
  unsigned int v35; // eax
  unsigned int v36; // r14d
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  SIZE_T v39; // rdi
  __int64 v40; // [rsp+20h] [rbp-C8h]
  char v41; // [rsp+40h] [rbp-A8h]
  char v42; // [rsp+41h] [rbp-A7h]
  enum _SID_NAME_USE *v43; // [rsp+48h] [rbp-A0h]
  unsigned int *v44; // [rsp+50h] [rbp-98h]
  HLOCAL hMem[2]; // [rsp+58h] [rbp-90h] BYREF
  int v46; // [rsp+68h] [rbp-80h]
  unsigned int v47; // [rsp+6Ch] [rbp-7Ch]
  int v48; // [rsp+70h] [rbp-78h]
  void *v49; // [rsp+78h] [rbp-70h] BYREF
  struct _UNICODE_STRING *v50; // [rsp+80h] [rbp-68h]
  CLIENT_CALL_RETURN v51; // [rsp+88h] [rbp-60h]
  CLIENT_CALL_RETURN v52; // [rsp+90h] [rbp-58h]

  v7 = (unsigned int)a3;
  *(_OWORD *)hMem = 0;
  v49 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, a3, a1, a2, a3);
  if ( !(_DWORD)v7 || !a4 )
    return 3221225485LL;
  if ( !(unsigned __int8)SampIsValidClientHandle(a1, &v49) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
    return 3221225480LL;
  }
  v50 = a4;
  Pointer = 0;
  v41 = 1;
  v42 = 0;
  v43 = 0;
  *a6 = 0;
  v44 = 0;
  v12 = (unsigned int)a5;
  *a5 = 0;
  hMem[1] = hMem;
  hMem[0] = hMem;
  v13 = 0;
  v48 = 0;
  v14 = 0;
  v15 = WPP_GLOBAL_Control;
  while ( v14 < (unsigned int)v7 )
  {
    if ( (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 5u )
    {
      WPP_SF_dZ(v15[2], v12, 32000, v14, (__int64)&a4[v14]);
      v15 = WPP_GLOBAL_Control;
    }
    if ( a4[v14].Length > 0x7D00u )
    {
      if ( (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 2u )
        WPP_SF_(v15[2], 92, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
LABEL_20:
      v16 = 0;
LABEL_21:
      v17 = 0;
      goto LABEL_22;
    }
    v23 = (unsigned int *)LocalAlloc(0x40u, 0x38u);
    v24 = v23;
    if ( !v23 )
      goto LABEL_20;
    v23[5] = 0;
    v23[4] = v14;
    v25 = (char *)(v23 + 6);
    *((_QWORD *)v23 + 4) = 0;
    v26 = (char *)(v23 + 10);
    *((_QWORD *)v23 + 6) = 0;
    v27 = 0;
    v28 = 0;
    v29 = v50;
    do
    {
      v27 += v29[v14].Length;
      if ( v27 >= 0x7D00 )
        break;
      if ( v28 >= 0x3E8 )
        break;
      v23[5] = ++v28;
      ++v14;
    }
    while ( v14 < (unsigned int)v7 );
    v47 = v14;
    v30 = (unsigned int **)hMem[1];
    if ( *(HLOCAL **)hMem[1] != hMem )
      goto LABEL_87;
    *(_QWORD *)v24 = hMem;
    *((_QWORD *)v24 + 1) = v30;
    *v30 = v24;
    hMem[1] = v24;
    if ( a2 == 1 )
    {
      v34 = &a4[v24[4]];
      v35 = v24[5];
      v52.Simple = 0;
      LODWORD(v40) = v35;
      v33.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x11u, 0, v49, v40, v34, v25, v26).Pointer;
      v52.Pointer = v33.Pointer;
      Pointer = (int)v33.Pointer;
    }
    else
    {
      if ( a2 != 2 )
        return 3221225659LL;
      v31 = &a4[v24[4]];
      v32 = v24[5];
      v51.Simple = 0;
      LODWORD(v40) = v32;
      v33.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x47u, 0, v49, v40, v31, v25, v26).Pointer;
      Pointer = (int)v33.Pointer;
      v51.Pointer = v33.Pointer;
    }
    v46 = (int)v33.Pointer;
    v12 = 0x80000000;
    v15 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        94,
        &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
        (unsigned int)Pointer);
      v15 = WPP_GLOBAL_Control;
      v12 = 0x80000000;
    }
    if ( ((Pointer + 0x80000000) & 0x80000000) == 0 && Pointer != -1073741709 )
      goto LABEL_20;
    v48 = ++v13;
    if ( Pointer >= 0 )
    {
      v41 = 0;
      if ( Pointer == 263 )
        v42 = 1;
    }
  }
  if ( !v41 )
  {
    if ( v42 )
    {
      v36 = 263;
      if ( (*((_BYTE *)v15 + 28) & 2) == 0 || *((_BYTE *)v15 + 25) < 4u )
        goto LABEL_66;
      v38 = 96;
    }
    else
    {
      v36 = 0;
      if ( (*((_BYTE *)v15 + 28) & 2) == 0 || *((_BYTE *)v15 + 25) < 4u )
        goto LABEL_66;
      v38 = 97;
    }
    WPP_SF_(v15[2], v38, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
    goto LABEL_66;
  }
  if ( (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 4u )
    WPP_SF_(v15[2], 95, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
  v36 = -1073741709;
LABEL_66:
  if ( v13 != 1 )
  {
    v39 = 4 * v7;
    v16 = (unsigned int *)LocalAlloc(0x40u, v39);
    v44 = v16;
    if ( !v16 )
      goto LABEL_21;
    v17 = (enum _SID_NAME_USE *)LocalAlloc(0x40u, v39);
    v43 = v17;
    if ( !v17 )
    {
      LocalFree(v44);
      v16 = 0;
      v44 = 0;
      goto LABEL_21;
    }
    v16 = v44;
LABEL_22:
    v18 = (const void **)hMem[0];
    if ( *((HLOCAL **)hMem[0] + 1) == hMem )
    {
      v19 = *(_QWORD *)hMem[0];
      if ( *(HLOCAL *)(*(_QWORD *)hMem[0] + 8LL) == hMem[0] )
      {
        hMem[0] = *(HLOCAL *)hMem[0];
        *(_QWORD *)(v19 + 8) = hMem;
        if ( v18 == (const void **)hMem )
        {
LABEL_36:
          *a6 = v17;
          *a5 = v16;
          if ( Pointer == -1073610749 )
            Pointer = -1073741816;
          if ( Pointer < 0 )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                100,
                &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
                (unsigned int)Pointer);
          }
          else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
          }
          return (unsigned int)Pointer;
        }
        while ( 1 )
        {
          if ( v16 )
          {
            memmove_0(&v16[*((unsigned int *)v18 + 4)], v18[4], 4LL * *((unsigned int *)v18 + 5));
            v17 = v43;
          }
          v20 = (void *)v18[4];
          if ( v20 )
          {
            LocalFree(v20);
            v17 = v43;
          }
          if ( v17 )
            memmove_0(&v17[*((unsigned int *)v18 + 4)], v18[6], 4LL * *((unsigned int *)v18 + 5));
          v21 = (void *)v18[6];
          if ( v21 )
            LocalFree(v21);
          LocalFree(v18);
          v18 = (const void **)hMem[0];
          if ( *((HLOCAL **)hMem[0] + 1) != hMem )
            break;
          v22 = *(_QWORD *)hMem[0];
          if ( *(HLOCAL *)(*(_QWORD *)hMem[0] + 8LL) != hMem[0] )
            break;
          hMem[0] = *(HLOCAL *)hMem[0];
          *(_QWORD *)(v22 + 8) = hMem;
          v16 = v44;
          v17 = v43;
          if ( v18 == (const void **)hMem )
            goto LABEL_36;
        }
      }
    }
LABEL_87:
    __fastfail(3u);
  }
  v37 = hMem[0];
  *a6 = (enum _SID_NAME_USE *)*((_QWORD *)hMem[0] + 6);
  *a5 = (unsigned int *)v37[4];
  LocalFree(v37);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, v36);
  return v36;
}

```

## disassembly

```asm
0x180003a00  mov     [rsp+arg_18], r9
0x180003a05  mov     [rsp+arg_10], r8d
0x180003a0a  mov     [rsp+arg_8], edx
0x180003a0e  push    rbx
0x180003a0f  push    rsi
0x180003a10  push    rdi
0x180003a11  push    r12
0x180003a13  push    r13
0x180003a15  push    r14
0x180003a17  push    r15
0x180003a19  sub     rsp, 0B0h
0x180003a20  mov     r14, r9
0x180003a23  mov     edi, r8d
0x180003a26  mov     r15d, edx
0x180003a29  mov     rbx, rcx
0x180003a2c  xorps   xmm0, xmm0
0x180003a2f  movups  xmmword ptr [rsp+0E8h+hMem], xmm0
0x180003a34  xor     esi, esi
0x180003a36  mov     [rsp+0E8h+var_70], rsi
0x180003a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a42  test    byte ptr [rcx+1Ch], 2
0x180003a46  jz      short loc_180003A68
0x180003a48  cmp     byte ptr [rcx+19h], 4
0x180003a4c  jb      short loc_180003A68
0x180003a4e  mov     edx, 59h ; 'Y'
0x180003a53  mov     dword ptr [rsp+0E8h+var_C0], edi
0x180003a57  mov     dword ptr [rsp+0E8h+var_C8], r15d
0x180003a5c  mov     r9, rbx
0x180003a5f  mov     rcx, [rcx+10h]
0x180003a63  call    WPP_SF_qDD
0x180003a68  test    edi, edi
0x180003a6a  jz      loc_1800040B3
0x180003a70  test    r14, r14
0x180003a73  jz      loc_1800040B3
0x180003a79  lea     rdx, [rsp+0E8h+var_70]; void **
0x180003a7e  mov     rcx, rbx; void *
0x180003a81  call    ?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z; SampIsValidClientHandle(void *,void * *)
0x180003a86  test    al, al
0x180003a88  jnz     short loc_180003ABF
0x180003a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a91  test    byte ptr [rcx+1Ch], 2
0x180003a95  jz      short loc_180003AB5
0x180003a97  cmp     byte ptr [rcx+19h], 2
0x180003a9b  jb      short loc_180003AB5
0x180003a9d  mov     edx, 5Ah ; 'Z'
0x180003aa2  mov     r9, rbx
0x180003aa5  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180003aac  mov     rcx, [rcx+10h]
0x180003ab0  call    WPP_SF_q
0x180003ab5  mov     eax, 0C0000008h
0x180003aba  jmp     loc_1800040B8
0x180003abf  mov     [rsp+0E8h+var_68], r14
0x180003ac7  mov     ebx, esi
0x180003ac9  mov     [rsp+0E8h+var_A8], 1
0x180003ace  mov     [rsp+0E8h+var_A7], bl
0x180003ad2  mov     [rsp+0E8h+var_A0], rsi
0x180003ad7  mov     r9, [rsp+0E8h+arg_28]
0x180003adf  mov     [r9], rsi
0x180003ae2  mov     [rsp+0E8h+var_98], rsi
0x180003ae7  mov     rdx, [rsp+0E8h+arg_20]
0x180003aef  mov     [rdx], rsi
0x180003af2  lea     rax, [rsp+0E8h+hMem]
0x180003af7  mov     [rsp+0E8h+hMem+8], rax
0x180003afc  lea     rax, [rsp+0E8h+hMem]
0x180003b01  mov     [rsp+0E8h+hMem], rax
0x180003b06  mov     r12d, esi
0x180003b09  mov     [rsp+0E8h+var_78], esi
0x180003b0d  mov     r13d, esi
0x180003b10  mov     r8d, 7D00h
0x180003b16  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b1d  nop     dword ptr [rax]
0x180003b20  cmp     r13d, edi
0x180003b23  jnb     loc_180003F34
0x180003b29  test    byte ptr [rcx+1Ch], 2
0x180003b2d  jz      short loc_180003B5D
0x180003b2f  cmp     byte ptr [rcx+19h], 5
0x180003b33  jb      short loc_180003B5D
0x180003b35  mov     eax, r13d
0x180003b38  shl     rax, 4
0x180003b3c  add     rax, r14
0x180003b3f  mov     [rsp+0E8h+var_C8], rax
0x180003b44  mov     r9d, r13d
0x180003b47  mov     rcx, [rcx+10h]
0x180003b4b  call    WPP_SF_dZ
0x180003b50  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b57  mov     r8d, 7D00h
0x180003b5d  mov     eax, r13d
0x180003b60  add     rax, rax
0x180003b63  cmp     [r14+rax*8], r8w
0x180003b68  jbe     loc_180003CE9
0x180003b6e  test    byte ptr [rcx+1Ch], 2
0x180003b72  jz      short loc_180003B8F
0x180003b74  cmp     byte ptr [rcx+19h], 2
0x180003b78  jb      short loc_180003B8F
0x180003b7a  mov     edx, 5Ch ; '\'
0x180003b7f  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180003b86  mov     rcx, [rcx+10h]
0x180003b8a  call    WPP_SF_
0x180003b8f  mov     rdx, [rsp+0E8h+var_98]
0x180003b94  mov     r9, [rsp+0E8h+var_A0]
0x180003b99  mov     rdi, [rsp+0E8h+hMem]
0x180003b9e  lea     rax, [rsp+0E8h+hMem]
0x180003ba3  cmp     [rdi+8], rax
0x180003ba7  jnz     loc_1800040AC
0x180003bad  mov     rcx, [rdi]
0x180003bb0  cmp     [rcx+8], rdi
0x180003bb4  jnz     loc_1800040AC
0x180003bba  mov     [rsp+0E8h+hMem], rcx
0x180003bbf  lea     rax, [rsp+0E8h+hMem]
0x180003bc4  mov     [rcx+8], rax
0x180003bc8  lea     rax, [rsp+0E8h+hMem]
0x180003bcd  cmp     rdi, rax
0x180003bd0  jz      loc_180003C88
0x180003bd6  test    rdx, rdx
0x180003bd9  jz      short loc_180003BF8
0x180003bdb  mov     r8d, [rdi+14h]
0x180003bdf  shl     r8, 2; Size
0x180003be3  mov     eax, [rdi+10h]
0x180003be6  lea     rcx, [rdx+rax*4]; void *
0x180003bea  mov     rdx, [rdi+20h]; Src
0x180003bee  call    memmove_0
0x180003bf3  mov     r9, [rsp+0E8h+var_A0]
0x180003bf8  mov     rcx, [rdi+20h]; hMem
0x180003bfc  test    rcx, rcx
0x180003bff  jz      short loc_180003C0C
0x180003c01  call    cs:__imp_LocalFree
0x180003c07  mov     r9, [rsp+0E8h+var_A0]
0x180003c0c  test    r9, r9
0x180003c0f  jz      short loc_180003C29
0x180003c11  mov     r8d, [rdi+14h]
0x180003c15  shl     r8, 2; Size
0x180003c19  mov     eax, [rdi+10h]
0x180003c1c  lea     rcx, [r9+rax*4]; void *
0x180003c20  mov     rdx, [rdi+30h]; Src
0x180003c24  call    memmove_0
0x180003c29  mov     rcx, [rdi+30h]; hMem
0x180003c2d  test    rcx, rcx
0x180003c30  jz      short loc_180003C38
0x180003c32  call    cs:__imp_LocalFree
0x180003c38  mov     rcx, rdi; hMem
0x180003c3b  call    cs:__imp_LocalFree
0x180003c41  mov     rdi, [rsp+0E8h+hMem]
0x180003c46  lea     rax, [rsp+0E8h+hMem]
0x180003c4b  cmp     [rdi+8], rax
0x180003c4f  jnz     loc_1800040AC
0x180003c55  mov     rax, [rdi]
0x180003c58  cmp     [rax+8], rdi
0x180003c5c  jnz     loc_1800040AC
0x180003c62  mov     [rsp+0E8h+hMem], rax
0x180003c67  lea     rcx, [rsp+0E8h+hMem]
0x180003c6c  mov     [rax+8], rcx
0x180003c70  lea     rax, [rsp+0E8h+hMem]
0x180003c75  cmp     rdi, rax
0x180003c78  mov     rdx, [rsp+0E8h+var_98]
0x180003c7d  mov     r9, [rsp+0E8h+var_A0]
0x180003c82  jnz     loc_180003BD6
0x180003c88  mov     r8, [rsp+0E8h+arg_28]
0x180003c90  mov     [r8], r9
0x180003c93  mov     r8, [rsp+0E8h+arg_20]
0x180003c9b  mov     [r8], rdx
0x180003c9e  mov     eax, 0C0000008h
0x180003ca3  cmp     ebx, 0C0020003h
0x180003ca9  cmovz   ebx, eax
0x180003cac  test    ebx, ebx
0x180003cae  js      loc_18000407D
0x180003cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cbb  test    byte ptr [rcx+1Ch], 2
0x180003cbf  jz      loc_1800040A8
0x180003cc5  cmp     byte ptr [rcx+19h], 4
0x180003cc9  jb      loc_1800040A8
0x180003ccf  mov     edx, 63h ; 'c'
0x180003cd4  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180003cdb  mov     rcx, [rcx+10h]
0x180003cdf  call    WPP_SF_
0x180003ce4  jmp     loc_1800040A8
0x180003ce9  mov     edx, 38h ; '8'; uBytes
0x180003cee  mov     ecx, 40h ; '@'; uFlags
0x180003cf3  call    cs:__imp_LocalAlloc
0x180003cf9  mov     rdx, rax
0x180003cfc  test    rax, rax
0x180003cff  jz      loc_180003B8F
0x180003d05  mov     [rax+14h], esi
0x180003d08  mov     [rax+10h], r13d
0x180003d0c  lea     r9, [rax+18h]
0x180003d10  mov     [r9+8], rsi
0x180003d14  lea     r10, [rax+28h]
0x180003d18  mov     [r10+8], rsi
0x180003d1c  mov     r8d, esi
0x180003d1f  mov     ecx, esi
0x180003d21  mov     r11, [rsp+0E8h+var_68]
0x180003d29  mov     eax, r13d
0x180003d2c  add     rax, rax
0x180003d2f  movzx   eax, word ptr [r11+rax*8]
0x180003d34  add     r8d, eax
0x180003d37  cmp     r8d, 7D00h
0x180003d3e  jnb     short loc_180003D55
0x180003d40  cmp     ecx, 3E8h
0x180003d46  jnb     short loc_180003D55
0x180003d48  inc     ecx
0x180003d4a  mov     [rdx+14h], ecx
0x180003d4d  inc     r13d
0x180003d50  cmp     r13d, edi
0x180003d53  jb      short loc_180003D29
0x180003d55  mov     [rsp+0E8h+var_7C], r13d
0x180003d5a  mov     rax, [rsp+0E8h+hMem+8]
0x180003d5f  lea     rcx, [rsp+0E8h+hMem]
0x180003d64  cmp     [rax], rcx
0x180003d67  jnz     loc_1800040AC
0x180003d6d  lea     rcx, [rsp+0E8h+hMem]
0x180003d72  mov     [rdx], rcx
0x180003d75  mov     [rdx+8], rax
0x180003d79  mov     [rax], rdx
0x180003d7c  mov     [rsp+0E8h+hMem+8], rdx
0x180003d81  mov     eax, r15d
0x180003d84  sub     eax, 1
0x180003d87  jz      short loc_180003DE7
0x180003d89  cmp     eax, 1
0x180003d8c  jz      short loc_180003D98
0x180003d8e  mov     eax, 0C00000BBh
0x180003d93  jmp     loc_1800040B8
0x180003d98  mov     ecx, [rdx+10h]
0x180003d9b  shl     rcx, 4
0x180003d9f  add     rcx, r14
0x180003da2  mov     eax, [rdx+14h]
0x180003da5  mov     [rsp+0E8h+var_60], rsi
0x180003dad  mov     [rsp+0E8h+var_B0], r10
0x180003db2  mov     [rsp+0E8h+var_B8], r9
0x180003db7  mov     [rsp+0E8h+var_C0], rcx
0x180003dbc  mov     dword ptr [rsp+0E8h+var_C8], eax
0x180003dc0  mov     r9, [rsp+0E8h+var_70]
0x180003dc5  xor     r8d, r8d; pReturnValue
0x180003dc8  mov     edx, 47h ; 'G'; nProcNum
0x180003dcd  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180003dd4  call    cs:__imp_NdrClientCall3
0x180003dda  mov     rbx, rax
0x180003ddd  mov     [rsp+0E8h+var_60], rax
0x180003de5  jmp     short loc_180003E33
0x180003de7  mov     ecx, [rdx+10h]
0x180003dea  shl     rcx, 4
0x180003dee  add     rcx, r14
0x180003df1  mov     eax, [rdx+14h]
0x180003df4  mov     [rsp+0E8h+var_58], rsi
0x180003dfc  mov     [rsp+0E8h+var_B0], r10
0x180003e01  mov     [rsp+0E8h+var_B8], r9
0x180003e06  mov     [rsp+0E8h+var_C0], rcx
0x180003e0b  mov     dword ptr [rsp+0E8h+var_C8], eax
0x180003e0f  mov     r9, [rsp+0E8h+var_70]
0x180003e14  xor     r8d, r8d; pReturnValue
0x180003e17  mov     edx, 11h; nProcNum
0x180003e1c  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180003e23  call    cs:__imp_NdrClientCall3
0x180003e29  mov     [rsp+0E8h+var_58], rax
0x180003e31  mov     ebx, eax
0x180003e33  mov     [rsp+0E8h+var_80], eax
0x180003e37  mov     edx, 80000000h
0x180003e3c  mov     r8d, 7D00h
0x180003e42  jmp     short loc_180003EB9
0x180003e44  mov     ebx, eax
0x180003e46  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e4d  test    byte ptr [rcx+1Ch], 2
0x180003e51  jz      short loc_180003E71
0x180003e53  cmp     byte ptr [rcx+19h], 3
0x180003e57  jb      short loc_180003E71
0x180003e59  mov     r9d, eax
0x180003e5c  mov     edx, 5Dh ; ']'
0x180003e61  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180003e68  mov     rcx, [rcx+10h]
0x180003e6c  call    WPP_SF_D
0x180003e71  mov     ecx, ebx; Status
0x180003e73  call    cs:__imp_I_RpcMapWin32Status
0x180003e79  mov     ebx, eax
0x180003e7b  mov     [rsp+0E8h+var_80], eax
0x180003e7f  xor     esi, esi
0x180003e81  mov     edx, 80000000h
0x180003e86  mov     r8d, 7D00h
0x180003e8c  mov     r14, [rsp+0E8h+arg_18]
0x180003e94  mov     edi, [rsp+0E8h+arg_10]
0x180003e9b  mov     r15d, [rsp+0E8h+arg_8]
0x180003ea3  mov     eax, esi
0x180003ea5  mov     [rsp+0E8h+var_A0], rax
0x180003eaa  mov     [rsp+0E8h+var_98], rax
0x180003eaf  mov     r12d, [rsp+0E8h+var_78]
0x180003eb4  mov     r13d, [rsp+0E8h+var_7C]
0x180003eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ec0  test    byte ptr [rcx+1Ch], 2
0x180003ec4  jz      short loc_180003EF6
0x180003ec6  cmp     byte ptr [rcx+19h], 4
0x180003eca  jb      short loc_180003EF6
0x180003ecc  mov     edx, 5Eh ; '^'
0x180003ed1  mov     r9d, ebx
0x180003ed4  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180003edb  mov     rcx, [rcx+10h]
0x180003edf  call    WPP_SF_D
0x180003ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eeb  mov     edx, 80000000h
0x180003ef0  mov     r8d, 7D00h
0x180003ef6  lea     eax, [rbx+rdx]
0x180003ef9  test    edx, eax
0x180003efb  jnz     short loc_180003F09
0x180003efd  cmp     ebx, 0C0000073h
  ... truncated ...
```
