# CRdrPnpSession::MarshalHardWareId(ushort * *,ulong,ushort const *,ulong *,int)

- ea: `0x18002a580`
- end: `0x18002a8de`
- name: `?MarshalHardWareId@CRdrPnpSession@@AEAAJPEAPEAGKPEBGPEAKH@Z`
- size: `862`
- prototype: `int(CRdrPnpSession *__hidden this, unsigned __int16 **, unsigned int, const unsigned __int16 *, unsigned int *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a8f0`

## callees

- `0x180009fa8`
- `0x18000b8f8`
- `0x18000b98c`
- `0x1800134cc`
- `0x18001ba64`
- `0x18002a580`
- `0x180033c90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a613`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a613`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a89e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a8c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a89e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a8c1`

## string_xrefs

- `0x18002a76f`: `StringCchCopyW FAILED`

## pseudocode

```c
__int64 __fastcall CRdrPnpSession::MarshalHardWareId(
        CRdrPnpSession *this,
        unsigned __int16 **a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        int a6)
{
  int v7; // ebx
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned int v11; // edi
  unsigned __int16 *v12; // r12
  unsigned int v13; // eax
  const unsigned __int16 *v14; // r14
  unsigned int v15; // r15d
  unsigned int v16; // ebp
  unsigned __int16 *v17; // rdi
  unsigned int v18; // eax
  unsigned int v19; // r11d
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v24; // edx
  __int64 v25; // rax
  __int64 v26; // rax
  const unsigned __int16 *v27; // r11
  unsigned int i; // esi
  __int64 v29; // r11
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // r11
  unsigned int *v34; // rax
  unsigned int v35; // ecx
  unsigned int v37; // [rsp+70h] [rbp+8h] BYREF
  int v38; // [rsp+74h] [rbp+Ch]
  __int64 v39; // [rsp+88h] [rbp+20h] BYREF

  v38 = HIDWORD(this);
  v7 = 0;
  v37 = 0;
  LODWORD(v39) = 0;
  DisectMultiSzString(*a2, a3, &v37, (unsigned int *)&v39);
  v9 = 2LL * ((_DWORD)v39 + 2 * v37 + v37);
  if ( !a6 )
    v9 += 2LL * (unsigned int)(v39 - 1);
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    v9 += 2LL * (unsigned int)(v10 + 1);
  }
  v11 = v9;
  if ( (unsigned int)v9 == v9 )
  {
    v12 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v9);
    if ( v12 )
    {
      v14 = *a2;
      v15 = 0;
      v16 = v11 >> 1;
      v39 = v11 >> 1;
      v17 = v12;
      while ( 1 )
      {
        v18 = v37;
        if ( v15 >= v37 )
          break;
        v7 = StringCchCopyW(v17, v16, L"TS_");
        if ( v7 < 0 )
        {
          if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
            || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
          {
            goto LABEL_56;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v24 = 16;
          goto LABEL_32;
        }
        v7 = StringCchCatW(v17, v19, v14);
        if ( v7 < 0 )
        {
          if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
            && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v24 = 17;
            goto LABEL_32;
          }
LABEL_56:
          CoTaskMemFree(v12);
          return (unsigned int)v7;
        }
        v20 = -1;
        do
          ++v20;
        while ( v17[v20] );
        v21 = (unsigned int)(v20 + 1);
        v16 -= v21;
        v17 += v21;
        v22 = -1;
        do
          ++v22;
        while ( v14[v22] );
        v14 += v22 + 1;
        ++v15;
      }
      if ( a4 )
      {
        v7 = StringCchCopyW(v17, v16, a4);
        if ( v7 < 0 )
        {
          if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
            || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
          {
            goto LABEL_56;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v24 = 18;
LABEL_32:
          WPP_SF_DsD(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            v24,
            (unsigned int)WPP_20fce98516ba3efe262bf7803cb2ce9d_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"StringCchCopyW FAILED",
            v7);
          goto LABEL_56;
        }
        v25 = -1;
        do
          ++v25;
        while ( v17[v25] );
        v26 = (unsigned int)(v25 + 1);
        v16 -= v26;
        v17 += v26;
        v18 = v37;
      }
      if ( !a6 )
      {
        v27 = *a2;
        for ( i = 0; i < v18; ++i )
        {
          v7 = StringCchCopyW(v17, v16, v27);
          if ( v7 < 0 )
          {
            if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
              && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v24 = 19;
              goto LABEL_32;
            }
            goto LABEL_56;
          }
          v30 = -1;
          do
            ++v30;
          while ( v17[v30] );
          v31 = (unsigned int)(v30 + 1);
          v16 -= v31;
          v17 += v31;
          v32 = -1;
          do
            ++v32;
          while ( *(_WORD *)(v29 + 2 * v32) );
          v33 = v29 + 2 * v32;
          v18 = v37;
          v27 = (const unsigned __int16 *)(v33 + 2);
        }
      }
      *v17 = 0;
      CoTaskMemFree(*a2);
      v34 = a5;
      v35 = v39;
      *a2 = v12;
      *v34 = v35;
      if ( v7 )
        goto LABEL_56;
    }
    else
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          15,
          (unsigned int)WPP_20fce98516ba3efe262bf7803cb2ce9d_Traceguids,
          v13,
          (__int64)"LPWSTR");
      }
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024362;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002a580  mov     r11, rsp
0x18002a583  mov     [r11+10h], rbx
0x18002a587  mov     [r11+8], rcx
0x18002a58b  push    rbp
0x18002a58c  push    rsi
0x18002a58d  push    rdi
0x18002a58e  push    r12
0x18002a590  push    r13
0x18002a592  push    r14
0x18002a594  push    r15
0x18002a596  sub     rsp, 30h
0x18002a59a  mov     r13, rdx
0x18002a59d  mov     eax, r8d
0x18002a5a0  xor     ebx, ebx
0x18002a5a2  lea     r8, [r11+8]; unsigned int *
0x18002a5a6  mov     rsi, r9
0x18002a5a9  mov     [rsp+68h+arg_0], ebx
0x18002a5ad  lea     r9, [r11+20h]; unsigned int *
0x18002a5b1  mov     [r11+20h], ebx
0x18002a5b5  mov     rcx, [r13+0]; unsigned __int16 *
0x18002a5b9  mov     edx, eax; unsigned int
0x18002a5bb  call    ?DisectMultiSzString@@YA_NPEAGKPEAK1@Z; DisectMultiSzString(ushort *,ulong,ulong *,ulong *)
0x18002a5c0  mov     ecx, [rsp+68h+arg_0]
0x18002a5c4  mov     r8d, dword ptr [rsp+68h+arg_18]
0x18002a5cc  lea     eax, [r8+rcx*2]
0x18002a5d0  add     ecx, eax
0x18002a5d2  lea     rdx, [rcx+rcx]
0x18002a5d6  cmp     [rsp+68h+arg_28], ebx
0x18002a5dd  jnz     short loc_18002A5E7
0x18002a5df  lea     eax, [r8-1]
0x18002a5e3  lea     rdx, [rdx+rax*2]
0x18002a5e7  test    rsi, rsi
0x18002a5ea  jz      short loc_18002A5FF
0x18002a5ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a5f0  inc     rax
0x18002a5f3  cmp     [rsi+rax*2], bx
0x18002a5f7  jnz     short loc_18002A5F0
0x18002a5f9  inc     eax
0x18002a5fb  lea     rdx, [rdx+rax*2]
0x18002a5ff  mov     edi, edx
0x18002a601  cmp     rdi, rdx
0x18002a604  jz      short loc_18002A610
0x18002a606  mov     ebx, 80070216h
0x18002a60b  jmp     loc_18002A8C7
0x18002a610  mov     rcx, rdi; cb
0x18002a613  call    cs:__imp_CoTaskMemAlloc
0x18002a619  xor     ecx, ecx
0x18002a61b  mov     r12, rax
0x18002a61e  test    rax, rax
0x18002a621  jnz     short loc_18002A67C
0x18002a623  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a62a  lea     rax, WPP_GLOBAL_Control
0x18002a631  cmp     rcx, rax
0x18002a634  jz      short loc_18002A672
0x18002a636  test    byte ptr [rcx+1Ch], 8
0x18002a63a  jz      short loc_18002A672
0x18002a63c  cmp     byte ptr [rcx+19h], 2
0x18002a640  jb      short loc_18002A672
0x18002a642  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002a647  lea     rcx, aLpwstr; "LPWSTR"
0x18002a64e  mov     r9d, eax
0x18002a651  mov     [rsp+68h+var_48], rcx
0x18002a656  lea     edx, [r12+0Fh]
0x18002a65b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a662  lea     r8, WPP_20fce98516ba3efe262bf7803cb2ce9d_Traceguids
0x18002a669  mov     rcx, [rcx+10h]
0x18002a66d  call    WPP_SF_Ds
0x18002a672  mov     ebx, 8007000Eh
0x18002a677  jmp     loc_18002A8C7
0x18002a67c  mov     r14, [r13+0]
0x18002a680  mov     r15d, ecx
0x18002a683  shr     edi, 1
0x18002a685  mov     eax, edi
0x18002a687  mov     ebp, edi
0x18002a689  mov     [rsp+68h+arg_18], rax
0x18002a691  mov     rdi, r12
0x18002a694  mov     eax, [rsp+68h+arg_0]
0x18002a698  cmp     r15d, eax
0x18002a69b  jnb     loc_18002A79E
0x18002a6a1  lea     r8, aTs; "TS_"
0x18002a6a8  mov     edx, ebp; unsigned __int64
0x18002a6aa  mov     rcx, rdi; unsigned __int16 *
0x18002a6ad  mov     r11d, ebp
0x18002a6b0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a6b5  mov     ebx, eax
0x18002a6b7  test    eax, eax
0x18002a6b9  js      short loc_18002A73A
0x18002a6bb  mov     r8, r14; unsigned __int16 *
0x18002a6be  mov     edx, r11d; unsigned __int64
0x18002a6c1  mov     rcx, rdi; unsigned __int16 *
0x18002a6c4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a6c9  xor     ecx, ecx
0x18002a6cb  mov     ebx, eax
0x18002a6cd  test    eax, eax
0x18002a6cf  js      short loc_18002A703
0x18002a6d1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002a6d5  mov     rax, rdx
0x18002a6d8  inc     rax
0x18002a6db  cmp     [rdi+rax*2], cx
0x18002a6df  jnz     short loc_18002A6D8
0x18002a6e1  inc     eax
0x18002a6e3  sub     ebp, eax
0x18002a6e5  lea     rdi, [rdi+rax*2]
0x18002a6e9  mov     rax, rdx
0x18002a6ec  inc     rax
0x18002a6ef  cmp     [r14+rax*2], cx
0x18002a6f4  jnz     short loc_18002A6EC
0x18002a6f6  lea     r14, [r14+rax*2]
0x18002a6fa  add     r14, 2
0x18002a6fe  inc     r15d
0x18002a701  jmp     short loc_18002A694
0x18002a703  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a70a  lea     rax, WPP_GLOBAL_Control
0x18002a711  cmp     rcx, rax
0x18002a714  jz      loc_18002A8BE
0x18002a71a  test    byte ptr [rcx+1Ch], 8
0x18002a71e  jz      loc_18002A8BE
0x18002a724  cmp     byte ptr [rcx+19h], 2
0x18002a728  jb      loc_18002A8BE
0x18002a72e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002a733  mov     edx, 11h
0x18002a738  jmp     short loc_18002A76F
0x18002a73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a741  lea     rax, WPP_GLOBAL_Control
0x18002a748  cmp     rcx, rax
0x18002a74b  jz      loc_18002A8BE
0x18002a751  test    byte ptr [rcx+1Ch], 8
0x18002a755  jz      loc_18002A8BE
0x18002a75b  cmp     byte ptr [rcx+19h], 2
0x18002a75f  jb      loc_18002A8BE
0x18002a765  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002a76a  mov     edx, 10h
0x18002a76f  lea     rcx, aStringcchcopyw; "StringCchCopyW FAILED"
0x18002a776  mov     [rsp+68h+var_40], ebx
0x18002a77a  mov     [rsp+68h+var_48], rcx
0x18002a77f  lea     r8, WPP_20fce98516ba3efe262bf7803cb2ce9d_Traceguids
0x18002a786  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a78d  mov     r9d, eax
0x18002a790  mov     rcx, [rcx+10h]
0x18002a794  call    WPP_SF_DsD
0x18002a799  jmp     loc_18002A8BE
0x18002a79e  test    rsi, rsi
0x18002a7a1  jz      short loc_18002A808
0x18002a7a3  mov     edx, ebp; unsigned __int64
0x18002a7a5  mov     r8, rsi; unsigned __int16 *
0x18002a7a8  mov     rcx, rdi; unsigned __int16 *
0x18002a7ab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a7b0  xor     ecx, ecx
0x18002a7b2  mov     ebx, eax
0x18002a7b4  test    eax, eax
0x18002a7b6  jns     short loc_18002A7EF
0x18002a7b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7bf  lea     rax, WPP_GLOBAL_Control
0x18002a7c6  cmp     rcx, rax
0x18002a7c9  jz      loc_18002A8BE
0x18002a7cf  test    byte ptr [rcx+1Ch], 8
0x18002a7d3  jz      loc_18002A8BE
0x18002a7d9  cmp     byte ptr [rcx+19h], 2
0x18002a7dd  jb      loc_18002A8BE
0x18002a7e3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002a7e8  mov     edx, 12h
0x18002a7ed  jmp     short loc_18002A76F
0x18002a7ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a7f3  inc     rax
0x18002a7f6  cmp     [rdi+rax*2], cx
0x18002a7fa  jnz     short loc_18002A7F3
0x18002a7fc  inc     eax
0x18002a7fe  sub     ebp, eax
0x18002a800  lea     rdi, [rdi+rax*2]
0x18002a804  mov     eax, [rsp+68h+arg_0]
0x18002a808  cmp     [rsp+68h+arg_28], ecx
0x18002a80f  jnz     loc_18002A897
0x18002a815  mov     r11, [r13+0]
0x18002a819  mov     esi, ecx
0x18002a81b  cmp     esi, eax
0x18002a81d  jnb     short loc_18002A897
0x18002a81f  mov     edx, ebp; unsigned __int64
0x18002a821  mov     r8, r11; unsigned __int16 *
0x18002a824  mov     rcx, rdi; unsigned __int16 *
0x18002a827  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a82c  xor     ecx, ecx
0x18002a82e  mov     ebx, eax
0x18002a830  test    eax, eax
0x18002a832  js      short loc_18002A869
0x18002a834  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002a838  mov     rax, rdx
0x18002a83b  inc     rax
0x18002a83e  cmp     [rdi+rax*2], cx
0x18002a842  jnz     short loc_18002A83B
0x18002a844  inc     eax
0x18002a846  sub     ebp, eax
0x18002a848  lea     rdi, [rdi+rax*2]
0x18002a84c  mov     rax, rdx
0x18002a84f  inc     rax
0x18002a852  cmp     [r11+rax*2], cx
0x18002a857  jnz     short loc_18002A84F
0x18002a859  lea     r11, [r11+rax*2]
0x18002a85d  mov     eax, [rsp+68h+arg_0]
0x18002a861  add     r11, 2
0x18002a865  inc     esi
0x18002a867  jmp     short loc_18002A81B
0x18002a869  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a870  lea     rax, WPP_GLOBAL_Control
0x18002a877  cmp     rcx, rax
0x18002a87a  jz      short loc_18002A8BE
0x18002a87c  test    byte ptr [rcx+1Ch], 8
0x18002a880  jz      short loc_18002A8BE
0x18002a882  cmp     byte ptr [rcx+19h], 2
0x18002a886  jb      short loc_18002A8BE
0x18002a888  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002a88d  mov     edx, 13h
0x18002a892  jmp     loc_18002A76F
0x18002a897  mov     [rdi], cx
0x18002a89a  mov     rcx, [r13+0]; pv
0x18002a89e  call    cs:__imp_CoTaskMemFree
0x18002a8a4  mov     rax, [rsp+68h+arg_20]
0x18002a8ac  mov     rcx, [rsp+68h+arg_18]
0x18002a8b4  mov     [r13+0], r12
0x18002a8b8  mov     [rax], ecx
0x18002a8ba  test    ebx, ebx
0x18002a8bc  jz      short loc_18002A8C7
0x18002a8be  mov     rcx, r12; pv
0x18002a8c1  call    cs:__imp_CoTaskMemFree
0x18002a8c7  mov     eax, ebx
0x18002a8c9  mov     rbx, [rsp+68h+arg_8]
0x18002a8ce  add     rsp, 30h
0x18002a8d2  pop     r15
0x18002a8d4  pop     r14
0x18002a8d6  pop     r13
0x18002a8d8  pop     r12
0x18002a8da  pop     rdi
0x18002a8db  pop     rsi
0x18002a8dc  pop     rbp
0x18002a8dd  retn
```
