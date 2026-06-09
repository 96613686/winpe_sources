# YReader::NormalizeAttributeValue(StringPtr *)

- ea: `0x10040b880`
- end: `0x10040bb42`
- name: `?NormalizeAttributeValue@YReader@@AEAAXPEAUStringPtr@@@Z`
- size: `706`
- prototype: `void __fastcall(YReader *__hidden this, struct StringPtr *)`
- caller_count: `5`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1004038d0`
- `0x100403ba0`
- `0x100404070`
- `0x100404310`
- `0x1004055d0`

## callees

- `0x100401780`
- `0x10040b880`
- `0x10040bb50`
- `0x100415560`

## pseudocode

```c
void __fastcall YReader::NormalizeAttributeValue(YReader *this, struct StringPtr *a2)
{
  __int64 v2; // rax
  unsigned __int64 v4; // rdi
  _DWORD *v6; // rsi
  __int64 v7; // rsi
  unsigned __int64 v8; // rsi
  struct BlockAlloc::Header *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  struct BlockAlloc::Header *v12; // rax
  unsigned __int64 v13; // rbp
  unsigned int i; // ecx
  unsigned __int64 v15; // rdi
  struct BlockAlloc::Header *v16; // rbx
  _WORD *v17; // rdx
  __int64 v18; // rax
  struct BlockAlloc::Header *v19; // rax
  _WORD *v20; // rax
  struct StringPtr *v21; // rbx
  __int64 v22; // rdx
  __int16 *v23; // rax
  unsigned __int64 v24; // r8
  __int16 v25; // cx
  __int64 v26; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v27; // [rsp+28h] [rbp-30h]
  __int64 v28; // [rsp+30h] [rbp-28h] BYREF
  int v29; // [rsp+38h] [rbp-20h]

  v2 = *((int *)this + 1942);
  v4 = *((_QWORD *)this + 970);
  v6 = (_DWORD *)v4;
  if ( (_DWORD)v2 == 1 )
  {
    if ( *(_DWORD *)v4 == 7 || *(_DWORD *)v4 == 8 || *(_DWORD *)v4 == 9 || *(_DWORD *)v4 == 10 )
    {
      *(_OWORD *)a2 = *(_OWORD *)(v4 + 8);
    }
    else if ( *(_DWORD *)v4 == 11 )
    {
      v7 = *(unsigned int *)(v4 + 16);
      *((_DWORD *)a2 + 2) = v7;
      v8 = 2 * v7;
      if ( v8 > 0xFFFFFFFF )
      {
        _mm_lfence();
        MXRRaiseException(-2147024362);
        JUMPOUT(0x10040BB41LL);
      }
      v9 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
      v10 = *((_QWORD *)v9 + 2);
      if ( *((_DWORD *)v9 + 6) - (int)v10 < (unsigned int)v8 )
      {
        v11 = *((_QWORD *)v9 + 1);
        if ( v11 )
        {
          while ( 1 )
          {
            v9 = (struct BlockAlloc::Header *)v11;
            if ( *(_DWORD *)(v11 + 24) - (int)v11 - 32 >= (unsigned int)v8 )
              break;
            v11 = *(_QWORD *)(v11 + 8);
            if ( !v11 )
              goto LABEL_12;
          }
          *(_QWORD *)(v11 + 16) = v11 + 32;
        }
        else
        {
LABEL_12:
          _mm_lfence();
          v12 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v8, v9);
          *((_QWORD *)v9 + 1) = v12;
          v9 = v12;
        }
        *((_QWORD *)this + 55) = v9;
        v10 = *((_QWORD *)v9 + 2);
      }
      *((_QWORD *)v9 + 2) += (unsigned int)v8;
      *(_QWORD *)a2 = v10;
      v28 = v10;
      v29 = 0;
      YReader::ExpandAttributeValue(this, a2, (struct StringPtr *)(v4 + 8), (struct StringPtr *)&v28);
      *((_DWORD *)a2 + 2) = v29;
    }
  }
  else
  {
    v13 = v4 + 24 * v2;
    for ( i = *((_DWORD *)a2 + 2); v4 < v13; *((_DWORD *)a2 + 2) = i )
    {
      i += *(_DWORD *)(v4 + 16);
      v4 += 24LL;
    }
    v15 = 2LL * i;
    if ( v15 > 0xFFFFFFFF )
    {
      _mm_lfence();
      MXRRaiseException(-2147024362);
      __debugbreak();
    }
    v16 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
    v17 = (_WORD *)*((_QWORD *)v16 + 2);
    if ( *((_DWORD *)v16 + 6) - (int)v17 < (unsigned int)v15 )
    {
      v18 = *((_QWORD *)v16 + 1);
      if ( v18 )
      {
        while ( 1 )
        {
          v16 = (struct BlockAlloc::Header *)v18;
          if ( *(_DWORD *)(v18 + 24) - (int)v18 - 32 >= (unsigned int)v15 )
            break;
          v18 = *(_QWORD *)(v18 + 8);
          if ( !v18 )
            goto LABEL_25;
        }
        *(_QWORD *)(v18 + 16) = v18 + 32;
      }
      else
      {
LABEL_25:
        _mm_lfence();
        v19 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v15, v16);
        *((_QWORD *)v16 + 1) = v19;
        v16 = v19;
      }
      *((_QWORD *)this + 55) = v16;
      v17 = (_WORD *)*((_QWORD *)v16 + 2);
    }
    *((_QWORD *)v16 + 2) += (unsigned int)v15;
    v20 = v17;
    *(_QWORD *)a2 = v17;
    if ( (unsigned __int64)v6 < v13 )
    {
      v21 = (struct StringPtr *)(v6 + 2);
      do
      {
        if ( *v6 == 7 || *v6 == 8 || *v6 == 9 || *v6 == 10 )
        {
          v23 = *(__int16 **)v21;
          v24 = *(_QWORD *)v21 + 2LL * *((unsigned int *)v21 + 2);
          if ( *(_QWORD *)v21 < v24 )
          {
            do
            {
              v25 = *v23++;
              *v17++ = v25;
            }
            while ( (unsigned __int64)v23 < v24 );
          }
        }
        else if ( *v6 == 11 )
        {
          v22 = (__int64)v17 - *(_QWORD *)a2;
          v26 = *(_QWORD *)a2;
          v27 = v22 >> 1;
          YReader::ExpandAttributeValue(this, a2, v21, (struct StringPtr *)&v26);
          v17 = (_WORD *)(v26 + 2LL * v27);
        }
        v6 += 6;
        v21 = (struct StringPtr *)((char *)v21 + 24);
      }
      while ( (unsigned __int64)v6 < v13 );
      v20 = *(_WORD **)a2;
    }
    *((_DWORD *)a2 + 2) = v17 - v20;
  }
}

```

## disassembly

```asm
0x10040b880  mov     [rsp+arg_8], rbx
0x10040b885  mov     [rsp+arg_10], rbp
0x10040b88a  mov     [rsp+arg_18], rsi
0x10040b88f  push    rdi
0x10040b890  push    r13
0x10040b892  push    r14
0x10040b894  sub     rsp, 40h
0x10040b898  movsxd  rax, dword ptr [rcx+1E58h]
0x10040b89f  mov     r14, rdx
0x10040b8a2  mov     rdi, [rcx+1E50h]
0x10040b8a9  mov     r13, rcx
0x10040b8ac  mov     rsi, rdi
0x10040b8af  cmp     eax, 1
0x10040b8b2  jnz     loc_10040B9BC
0x10040b8b8  mov     r8d, [rdi]
0x10040b8bb  sub     r8d, 7
0x10040b8bf  jz      loc_10040B9B3
0x10040b8c5  sub     r8d, eax
0x10040b8c8  jz      loc_10040B9B3
0x10040b8ce  sub     r8d, eax
0x10040b8d1  jz      loc_10040B9B3
0x10040b8d7  sub     r8d, eax
0x10040b8da  jz      loc_10040B9B3
0x10040b8e0  cmp     r8d, eax
0x10040b8e3  jnz     loc_10040B990
0x10040b8e9  mov     eax, [rdi+10h]
0x10040b8ec  mov     esi, eax
0x10040b8ee  mov     [rdx+8], eax
0x10040b8f1  add     rsi, rsi
0x10040b8f4  mov     eax, 0FFFFFFFFh
0x10040b8f9  cmp     rsi, rax
0x10040b8fc  ja      loc_10040BB34
0x10040b902  mov     rbx, [rcx+1B8h]
0x10040b909  mov     rcx, [rbx+10h]
0x10040b90d  mov     eax, [rbx+18h]
0x10040b910  sub     eax, ecx
0x10040b912  cmp     eax, esi
0x10040b914  jnb     short loc_10040B95E
0x10040b916  mov     rax, [rbx+8]
0x10040b91a  test    rax, rax
0x10040b91d  jz      short loc_10040B938
0x10040b91f  nop
0x10040b920  mov     rbx, rax
0x10040b923  mov     eax, [rax+18h]
0x10040b926  sub     eax, ebx
0x10040b928  sub     eax, 20h ; ' '
0x10040b92b  cmp     eax, esi
0x10040b92d  jnb     short loc_10040B9A9
0x10040b92f  mov     rax, [rbx+8]
0x10040b933  test    rax, rax
0x10040b936  jnz     short loc_10040B920
0x10040b938  lfence
0x10040b93b  mov     r8, rbx; struct BlockAlloc::Header *
0x10040b93e  lea     rcx, [r13+1A0h]; this
0x10040b945  mov     edx, esi; unsigned int
0x10040b947  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x10040b94c  mov     [rbx+8], rax
0x10040b950  mov     rbx, rax
0x10040b953  mov     [r13+1B8h], rbx
0x10040b95a  mov     rcx, [rbx+10h]
0x10040b95e  mov     eax, esi
0x10040b960  lea     r8, [rdi+8]; struct StringPtr *
0x10040b964  add     [rbx+10h], rax
0x10040b968  lea     r9, [rsp+58h+var_28]; struct StringPtr *
0x10040b96d  mov     [r14], rcx
0x10040b970  mov     rdx, r14; struct StringPtr *
0x10040b973  mov     [rsp+58h+var_28], rcx
0x10040b978  mov     rcx, r13; this
0x10040b97b  mov     [rsp+58h+var_20], 0
0x10040b983  call    ?ExpandAttributeValue@YReader@@AEAAXPEAUStringPtr@@00@Z; YReader::ExpandAttributeValue(StringPtr *,StringPtr *,StringPtr *)
0x10040b988  mov     eax, [rsp+58h+var_20]
0x10040b98c  mov     [r14+8], eax
0x10040b990  mov     rbx, [rsp+58h+arg_8]
0x10040b995  mov     rbp, [rsp+58h+arg_10]
0x10040b99a  mov     rsi, [rsp+58h+arg_18]
0x10040b99f  add     rsp, 40h
0x10040b9a3  pop     r14
0x10040b9a5  pop     r13
0x10040b9a7  pop     rdi
0x10040b9a8  retn
0x10040b9a9  lea     rax, [rbx+20h]
0x10040b9ad  mov     [rbx+10h], rax
0x10040b9b1  jmp     short loc_10040B953
0x10040b9b3  movups  xmm0, xmmword ptr [rdi+8]
0x10040b9b7  movups  xmmword ptr [rdx], xmm0
0x10040b9ba  jmp     short loc_10040B990
0x10040b9bc  lea     rcx, [rax+rax*2]
0x10040b9c0  lea     rbp, [rdi+rcx*8]
0x10040b9c4  mov     ecx, [rdx+8]
0x10040b9c7  cmp     rdi, rbp
0x10040b9ca  jnb     short loc_10040B9DF
0x10040b9cc  nop     dword ptr [rax+00h]
0x10040b9d0  add     ecx, [rdi+10h]
0x10040b9d3  add     rdi, 18h
0x10040b9d7  mov     [rdx+8], ecx
0x10040b9da  cmp     rdi, rbp
0x10040b9dd  jb      short loc_10040B9D0
0x10040b9df  mov     edi, ecx
0x10040b9e1  mov     eax, 0FFFFFFFFh
0x10040b9e6  add     rdi, rdi
0x10040b9e9  cmp     rdi, rax
0x10040b9ec  ja      loc_10040BB26
0x10040b9f2  mov     rbx, [r13+1B8h]
0x10040b9f9  mov     [rsp+58h+arg_0], r15
0x10040b9fe  mov     rdx, [rbx+10h]
0x10040ba02  mov     eax, [rbx+18h]
0x10040ba05  sub     eax, edx
0x10040ba07  cmp     eax, edi
0x10040ba09  jnb     short loc_10040BA62
0x10040ba0b  mov     rax, [rbx+8]
0x10040ba0f  test    rax, rax
0x10040ba12  jz      short loc_10040BA3C
0x10040ba14  nop     dword ptr [rax+00h]
0x10040ba18  nop     dword ptr [rax+rax+00000000h]
0x10040ba20  mov     rbx, rax
0x10040ba23  mov     eax, [rax+18h]
0x10040ba26  sub     eax, ebx
0x10040ba28  sub     eax, 20h ; ' '
0x10040ba2b  cmp     eax, edi
0x10040ba2d  jnb     loc_10040BACF
0x10040ba33  mov     rax, [rbx+8]
0x10040ba37  test    rax, rax
0x10040ba3a  jnz     short loc_10040BA20
0x10040ba3c  lfence
0x10040ba3f  mov     r8, rbx; struct BlockAlloc::Header *
0x10040ba42  lea     rcx, [r13+1A0h]; this
0x10040ba49  mov     edx, edi; unsigned int
0x10040ba4b  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x10040ba50  mov     [rbx+8], rax
0x10040ba54  mov     rbx, rax
0x10040ba57  mov     [r13+1B8h], rbx
0x10040ba5e  mov     rdx, [rbx+10h]
0x10040ba62  mov     r15, [rsp+58h+arg_0]
0x10040ba67  mov     eax, edi
0x10040ba69  add     [rbx+10h], rax
0x10040ba6d  mov     rax, rdx
0x10040ba70  mov     [r14], rdx
0x10040ba73  cmp     rsi, rbp
0x10040ba76  jnb     loc_10040BB17
0x10040ba7c  lea     rbx, [rsi+8]
0x10040ba80  mov     ecx, [rsi]
0x10040ba82  sub     ecx, 7
0x10040ba85  jz      short loc_10040BADC
0x10040ba87  sub     ecx, 1
0x10040ba8a  jz      short loc_10040BADC
0x10040ba8c  sub     ecx, 1
0x10040ba8f  jz      short loc_10040BADC
0x10040ba91  sub     ecx, 1
0x10040ba94  jz      short loc_10040BADC
0x10040ba96  cmp     ecx, 1
0x10040ba99  jnz     short loc_10040BB03
0x10040ba9b  mov     rax, [r14]
0x10040ba9e  lea     r9, [rsp+58h+var_38]; struct StringPtr *
0x10040baa3  sub     rdx, rax
0x10040baa6  mov     [rsp+58h+var_38], rax
0x10040baab  sar     rdx, 1
0x10040baae  mov     r8, rbx; struct StringPtr *
0x10040bab1  mov     [rsp+58h+var_30], edx
0x10040bab5  mov     rcx, r13; this
0x10040bab8  mov     rdx, r14; struct StringPtr *
0x10040babb  call    ?ExpandAttributeValue@YReader@@AEAAXPEAUStringPtr@@00@Z; YReader::ExpandAttributeValue(StringPtr *,StringPtr *,StringPtr *)
0x10040bac0  mov     ecx, [rsp+58h+var_30]
0x10040bac4  mov     rax, [rsp+58h+var_38]
0x10040bac9  lea     rdx, [rax+rcx*2]
0x10040bacd  jmp     short loc_10040BB03
0x10040bacf  lea     rax, [rbx+20h]
0x10040bad3  mov     [rbx+10h], rax
0x10040bad7  jmp     loc_10040BA57
0x10040badc  mov     rax, [rbx]
0x10040badf  mov     ecx, [rbx+8]
0x10040bae2  lea     r8, [rax+rcx*2]
0x10040bae6  cmp     rax, r8
0x10040bae9  jnb     short loc_10040BB03
0x10040baeb  nop     dword ptr [rax+rax+00h]
0x10040baf0  movzx   ecx, word ptr [rax]
0x10040baf3  add     rax, 2
0x10040baf7  mov     [rdx], cx
0x10040bafa  add     rdx, 2
0x10040bafe  cmp     rax, r8
0x10040bb01  jb      short loc_10040BAF0
0x10040bb03  add     rsi, 18h
0x10040bb07  add     rbx, 18h
0x10040bb0b  cmp     rsi, rbp
0x10040bb0e  jb      loc_10040BA80
0x10040bb14  mov     rax, [r14]
0x10040bb17  sub     rdx, rax
0x10040bb1a  sar     rdx, 1
0x10040bb1d  mov     [r14+8], edx
0x10040bb21  jmp     loc_10040B990
0x10040bb26  lfence
0x10040bb29  mov     ecx, 80070216h; int
0x10040bb2e  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040bb33  int     3; Trap to Debugger
0x10040bb34  lfence
0x10040bb37  mov     ecx, 80070216h; int
0x10040bb3c  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
