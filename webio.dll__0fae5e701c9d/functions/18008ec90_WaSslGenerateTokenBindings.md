# WaSslGenerateTokenBindings

- ea: `0x18008ec90`
- end: `0x18008f0d1`
- name: `WaSslGenerateTokenBindings`
- size: `1089`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18008d97c`
- `0x18008f0d8`

## callees

- `0x180004040`
- `0x180013820`
- `0x1800391c0`
- `0x18006b7b8`
- `0x18006d73c`
- `0x1800722f0`
- `0x18008ec90`
- `0x180091678`
- `0x18009234c`
- `0x180092564`
- `0x1800971ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008efb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008efde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008f006`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008f036`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008f066`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008efb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008efde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008f006`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008f036`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008f066`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ef1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ef9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008efca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008eff1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008f021`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008f051`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ef1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ef9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008efca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008eff1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008f021`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008f051`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008ef34`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008ef34`
- `TOKENBINDING!TokenBindingGenerateMessage` at `0x18008eee1`
- `TOKENBINDING!TokenBindingGenerateMessage` at `0x18008eee1`
- `TOKENBINDING!TokenBindingGenerateBinding` at `0x18008ee17`
- `TOKENBINDING!TokenBindingGenerateBinding` at `0x18008ee8f`
- `TOKENBINDING!TokenBindingGenerateBinding` at `0x18008ee17`
- `TOKENBINDING!TokenBindingGenerateBinding` at `0x18008ee8f`

## pseudocode

```c
__int64 __fastcall WaSslGenerateTokenBindings(__int64 a1, __int64 a2, _QWORD *a3, _DWORD *a4, LPVOID *a5)
{
  unsigned int v5; // ebx
  _DWORD *v6; // r14
  void *v7; // rsi
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  size_t v14; // rbx
  _DWORD *Heap; // rax
  __int64 v16; // r8
  HANDLE ProcessHeap; // rax
  SIZE_T v18; // rbx
  _DWORD *v19; // rcx
  int v20; // eax
  HANDLE v21; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  _DWORD *v27; // [rsp+50h] [rbp-71h] BYREF
  __int64 v28; // [rsp+58h] [rbp-69h] BYREF
  void *Src; // [rsp+60h] [rbp-61h] BYREF
  SIZE_T dwBytes; // [rsp+68h] [rbp-59h] BYREF
  __int64 v31; // [rsp+70h] [rbp-51h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-49h] BYREF
  LPVOID v33; // [rsp+80h] [rbp-41h] BYREF
  LPVOID v34; // [rsp+88h] [rbp-39h] BYREF
  LPVOID v35; // [rsp+90h] [rbp-31h] BYREF
  unsigned int v36; // [rsp+98h] [rbp-29h] BYREF
  int v37; // [rsp+9Ch] [rbp-25h] BYREF
  int v38; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-19h] BYREF
  __int128 v40; // [rsp+B0h] [rbp-11h] BYREF

  v5 = 0;
  Src = 0;
  v6 = 0;
  v28 = 0;
  v35 = 0;
  v7 = 0;
  v37 = 0;
  v34 = 0;
  v38 = 0;
  v33 = 0;
  v36 = 0;
  v40 = 0;
  v39 = 0;
  dwBytes = 0;
  v31 = 0;
  lpMem = 0;
  v27 = a4;
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_qDD(1027, 58, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids);
  if ( *(_DWORD *)(a1 + 116) == -1 )
  {
    if ( (xmmword_1800AD720 & 8) != 0 )
      WPP_SF_(1027, 59, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids);
    goto LABEL_29;
  }
  v11 = WaDetermineMinimizedDomain(*(_QWORD *)(a1 + 168), &Src, &v28);
  v5 = v11;
  if ( v11 )
  {
    if ( (xmmword_1800AD710 & 8) == 0 )
      goto LABEL_29;
    v13 = 60;
    goto LABEL_9;
  }
  v14 = 2 * v28;
  Heap = (_DWORD *)WxAllocateHeapEx(v12, 2 * v28 + 2);
  v6 = Heap;
  if ( !Heap )
  {
    v5 = 8;
    goto LABEL_29;
  }
  memcpy_0(Heap, Src, v14);
  *(_WORD *)((char *)v6 + v14) = 0;
  v11 = TokenBindingGenerateBinding(
          *(unsigned int *)(a1 + 116),
          v6,
          0,
          *(_QWORD *)(a1 + 120),
          *(_DWORD *)(a1 + 128),
          0,
          0,
          &v35,
          &v37,
          &lpMem);
  v5 = v11;
  if ( v11 )
  {
    if ( (xmmword_1800AD710 & 8) == 0 )
      goto LABEL_29;
    v13 = 61;
    goto LABEL_9;
  }
  *(_QWORD *)&v40 = v35;
  v16 = 1;
  LODWORD(v39) = v37;
  if ( a2 )
  {
    v11 = TokenBindingGenerateBinding(
            *(unsigned int *)(a1 + 116),
            a2,
            1,
            *(_QWORD *)(a1 + 120),
            *(_DWORD *)(a1 + 128),
            0,
            0,
            &v34,
            &v38,
            0);
    v5 = v11;
    if ( v11 )
    {
      if ( (xmmword_1800AD710 & 8) == 0 )
        goto LABEL_29;
      v13 = 62;
      goto LABEL_9;
    }
    v16 = 2;
    *((_QWORD *)&v40 + 1) = v34;
    HIDWORD(v39) = v38;
  }
  v11 = TokenBindingGenerateMessage(&v40, &v39, v16, &v33, &v36);
  v5 = v11;
  if ( v11 )
  {
    if ( (xmmword_1800AD710 & 8) == 0 )
      goto LABEL_29;
    v13 = 63;
LABEL_9:
    WPP_SF_d(515, v13, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids, v11);
    goto LABEL_29;
  }
  v5 = WaBinaryToBase64Length(v36, &dwBytes);
  if ( !v5 )
  {
    ProcessHeap = GetProcessHeap();
    v18 = dwBytes;
    v7 = HeapAlloc(ProcessHeap, 0, dwBytes);
    if ( v7 )
    {
      v5 = WapBinaryToBase64(1, (_DWORD)v33, v36, (_DWORD)v7, v18, (__int64)&v31);
      if ( !v5 )
      {
        v19 = v27;
        v20 = v31;
        *a3 = v7;
        v7 = 0;
        *v19 = v20;
        if ( a5 )
        {
          *a5 = lpMem;
          lpMem = 0;
        }
      }
    }
    else
    {
      v5 = 14;
    }
  }
LABEL_29:
  if ( lpMem )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, lpMem);
    lpMem = 0;
  }
  if ( v7 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v7);
  }
  if ( v33 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v33);
    v33 = 0;
  }
  if ( v34 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v34);
    v34 = 0;
  }
  if ( v35 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v35);
    v35 = 0;
  }
  if ( v6 )
  {
    v27 = v6;
    WxFreeHeapEx(&v27);
  }
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_d(1027, 64, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18008ec90  push    rbp
0x18008ec92  push    rbx
0x18008ec93  push    rsi
0x18008ec94  push    rdi
0x18008ec95  push    r12
0x18008ec97  push    r13
0x18008ec99  push    r14
0x18008ec9b  push    r15
0x18008ec9d  lea     rbp, [rsp-17h]
0x18008eca2  sub     rsp, 0D8h
0x18008eca9  mov     rax, cs:__security_cookie
0x18008ecb0  xor     rax, rsp
0x18008ecb3  mov     [rbp+4Fh+var_50], rax
0x18008ecb7  mov     r15, [rbp+4Fh+arg_20]
0x18008ecbb  xor     ebx, ebx
0x18008ecbd  xorps   xmm0, xmm0
0x18008ecc0  mov     [rbp+4Fh+Src], rbx
0x18008ecc4  mov     r14d, ebx
0x18008ecc7  mov     [rbp+4Fh+var_B8], rbx
0x18008eccb  mov     [rbp+4Fh+var_80], rbx
0x18008eccf  mov     esi, ebx
0x18008ecd1  mov     [rbp+4Fh+var_74], ebx
0x18008ecd4  mov     r13, r8
0x18008ecd7  mov     [rbp+4Fh+var_88], rbx
0x18008ecdb  mov     r12, rdx
0x18008ecde  mov     [rbp+4Fh+var_70], ebx
0x18008ece1  mov     rdi, rcx
0x18008ece4  mov     [rbp+4Fh+var_90], rbx
0x18008ece8  mov     [rbp+4Fh+var_78], ebx
0x18008eceb  movups  [rbp+4Fh+var_60], xmm0
0x18008ecef  mov     [rbp+4Fh+var_68], rbx
0x18008ecf3  mov     [rbp+4Fh+dwBytes], rbx
0x18008ecf7  mov     [rbp+4Fh+var_A0], rbx
0x18008ecfb  mov     [rbp+4Fh+lpMem], rbx
0x18008ecff  mov     [rbp+4Fh+var_C0], r9
0x18008ed03  test    byte ptr cs:xmmword_1800AD720, 8
0x18008ed0a  jz      short loc_18008ED32
0x18008ed0c  lea     r9, [rcx+30h]
0x18008ed10  mov     ecx, 403h
0x18008ed15  mov     eax, [r9]
0x18008ed18  lea     edx, [rbx+3Ah]
0x18008ed1b  mov     dword ptr [rsp+110h+var_E8], eax
0x18008ed1f  lea     r8, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids
0x18008ed26  mov     eax, [rdi+38h]
0x18008ed29  mov     dword ptr [rsp+110h+var_F0], eax
0x18008ed2d  call    WPP_SF_qDD
0x18008ed32  cmp     dword ptr [rdi+74h], 0FFFFFFFFh
0x18008ed36  jnz     short loc_18008ED60
0x18008ed38  test    byte ptr cs:xmmword_1800AD720, 8
0x18008ed3f  jz      loc_18008EF95
0x18008ed45  mov     edx, 3Bh ; ';'
0x18008ed4a  lea     r8, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids
0x18008ed51  mov     ecx, 403h
0x18008ed56  call    WPP_SF_
0x18008ed5b  jmp     loc_18008EF95
0x18008ed60  mov     rcx, [rdi+0A8h]
0x18008ed67  lea     r8, [rbp+4Fh+var_B8]
0x18008ed6b  lea     rdx, [rbp+4Fh+Src]
0x18008ed6f  call    WaDetermineMinimizedDomain
0x18008ed74  mov     ebx, eax
0x18008ed76  test    eax, eax
0x18008ed78  jz      short loc_18008EDA5
0x18008ed7a  test    byte ptr cs:xmmword_1800AD710, 8
0x18008ed81  jz      loc_18008EF95
0x18008ed87  mov     edx, 3Ch ; '<'
0x18008ed8c  mov     ecx, 203h
0x18008ed91  lea     r8, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids
0x18008ed98  mov     r9d, eax
0x18008ed9b  call    WPP_SF_d
0x18008eda0  jmp     loc_18008EF95
0x18008eda5  mov     rax, [rbp+4Fh+var_B8]
0x18008eda9  lea     rbx, [rax+rax]
0x18008edad  lea     rdx, [rbx+2]
0x18008edb1  call    WxAllocateHeapEx
0x18008edb6  mov     r14, rax
0x18008edb9  test    rax, rax
0x18008edbc  jnz     short loc_18008EDC6
0x18008edbe  lea     ebx, [rax+8]
0x18008edc1  jmp     loc_18008EF95
0x18008edc6  mov     rdx, [rbp+4Fh+Src]; Src
0x18008edca  mov     r8, rbx; Size
0x18008edcd  mov     rcx, r14; void *
0x18008edd0  call    memcpy_0
0x18008edd5  xor     eax, eax
0x18008edd7  xor     r8d, r8d
0x18008edda  mov     [rbx+r14], ax
0x18008eddf  mov     rdx, r14
0x18008ede2  mov     r9, [rdi+78h]
0x18008ede6  lea     rax, [rbp+4Fh+lpMem]
0x18008edea  mov     ecx, [rdi+74h]
0x18008eded  mov     [rsp+110h+var_C8], rax
0x18008edf2  lea     rax, [rbp+4Fh+var_74]
0x18008edf6  mov     [rsp+110h+var_D0], rax
0x18008edfb  lea     rax, [rbp+4Fh+var_80]
0x18008edff  mov     [rsp+110h+var_D8], rax
0x18008ee04  mov     eax, [rdi+80h]
0x18008ee0a  mov     [rsp+110h+var_E0], rsi
0x18008ee0f  mov     dword ptr [rsp+110h+var_E8], esi
0x18008ee13  mov     dword ptr [rsp+110h+var_F0], eax
0x18008ee17  call    cs:__imp_TokenBindingGenerateBinding
0x18008ee1e  nop     dword ptr [rax+rax+00h]
0x18008ee23  xor     ecx, ecx
0x18008ee25  mov     ebx, eax
0x18008ee27  test    eax, eax
0x18008ee29  jz      short loc_18008EE40
0x18008ee2b  test    byte ptr cs:xmmword_1800AD710, 8
0x18008ee32  jz      loc_18008EF95
0x18008ee38  lea     edx, [rcx+3Dh]
0x18008ee3b  jmp     loc_18008ED8C
0x18008ee40  mov     rax, [rbp+4Fh+var_80]
0x18008ee44  mov     edx, 1
0x18008ee49  mov     qword ptr [rbp+4Fh+var_60], rax
0x18008ee4d  mov     r8d, edx
0x18008ee50  mov     eax, [rbp+4Fh+var_74]
0x18008ee53  mov     dword ptr [rbp+4Fh+var_68], eax
0x18008ee56  test    r12, r12
0x18008ee59  jz      short loc_18008EECC
0x18008ee5b  mov     r9, [rdi+78h]
0x18008ee5f  lea     rax, [rbp+4Fh+var_70]
0x18008ee63  mov     [rsp+110h+var_C8], rcx
0x18008ee68  mov     rdx, r12
0x18008ee6b  mov     [rsp+110h+var_D0], rax
0x18008ee70  lea     rax, [rbp+4Fh+var_88]
0x18008ee74  mov     [rsp+110h+var_D8], rax
0x18008ee79  mov     eax, [rdi+80h]
0x18008ee7f  mov     [rsp+110h+var_E0], rcx
0x18008ee84  mov     dword ptr [rsp+110h+var_E8], ecx
0x18008ee88  mov     ecx, [rdi+74h]
0x18008ee8b  mov     dword ptr [rsp+110h+var_F0], eax
0x18008ee8f  call    cs:__imp_TokenBindingGenerateBinding
0x18008ee96  nop     dword ptr [rax+rax+00h]
0x18008ee9b  mov     ebx, eax
0x18008ee9d  test    eax, eax
0x18008ee9f  jz      short loc_18008EEB8
0x18008eea1  test    byte ptr cs:xmmword_1800AD710, 8
0x18008eea8  jz      loc_18008EF95
0x18008eeae  mov     edx, 3Eh ; '>'
0x18008eeb3  jmp     loc_18008ED8C
0x18008eeb8  mov     rax, [rbp+4Fh+var_88]
0x18008eebc  mov     r8d, 2
0x18008eec2  mov     qword ptr [rbp+4Fh+var_60+8], rax
0x18008eec6  mov     eax, [rbp+4Fh+var_70]
0x18008eec9  mov     dword ptr [rbp+4Fh+var_68+4], eax
0x18008eecc  lea     rax, [rbp+4Fh+var_78]
0x18008eed0  lea     r9, [rbp+4Fh+var_90]
0x18008eed4  mov     [rsp+110h+var_F0], rax
0x18008eed9  lea     rdx, [rbp+4Fh+var_68]
0x18008eedd  lea     rcx, [rbp+4Fh+var_60]
0x18008eee1  call    cs:__imp_TokenBindingGenerateMessage
0x18008eee8  nop     dword ptr [rax+rax+00h]
0x18008eeed  mov     ebx, eax
0x18008eeef  test    eax, eax
0x18008eef1  jz      short loc_18008EF0A
0x18008eef3  test    byte ptr cs:xmmword_1800AD710, 8
0x18008eefa  jz      loc_18008EF95
0x18008ef00  mov     edx, 3Fh ; '?'
0x18008ef05  jmp     loc_18008ED8C
0x18008ef0a  mov     ecx, [rbp+4Fh+var_78]
0x18008ef0d  lea     rdx, [rbp+4Fh+dwBytes]
0x18008ef11  call    WaBinaryToBase64Length
0x18008ef16  mov     ebx, eax
0x18008ef18  test    eax, eax
0x18008ef1a  jnz     short loc_18008EF95
0x18008ef1c  call    cs:__imp_GetProcessHeap
0x18008ef23  nop     dword ptr [rax+rax+00h]
0x18008ef28  mov     rbx, [rbp+4Fh+dwBytes]
0x18008ef2c  xor     edx, edx; dwFlags
0x18008ef2e  mov     rcx, rax; hHeap
0x18008ef31  mov     r8, rbx; dwBytes
0x18008ef34  call    cs:__imp_HeapAlloc
0x18008ef3b  nop     dword ptr [rax+rax+00h]
0x18008ef40  mov     rsi, rax
0x18008ef43  test    rax, rax
0x18008ef46  jnz     short loc_18008EF4D
0x18008ef48  lea     ebx, [rax+0Eh]
0x18008ef4b  jmp     short loc_18008EF95
0x18008ef4d  mov     r8d, [rbp+4Fh+var_78]
0x18008ef51  lea     rax, [rbp+4Fh+var_A0]
0x18008ef55  mov     rdx, [rbp+4Fh+var_90]
0x18008ef59  mov     r9, rsi
0x18008ef5c  mov     [rsp+110h+var_E8], rax
0x18008ef61  mov     ecx, 1
0x18008ef66  mov     [rsp+110h+var_F0], rbx
0x18008ef6b  call    WapBinaryToBase64
0x18008ef70  mov     ebx, eax
0x18008ef72  test    eax, eax
0x18008ef74  jnz     short loc_18008EF95
0x18008ef76  mov     rcx, [rbp+4Fh+var_C0]
0x18008ef7a  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x18008ef7d  mov     [r13+0], rsi
0x18008ef81  xor     esi, esi
0x18008ef83  mov     [rcx], eax
0x18008ef85  test    r15, r15
0x18008ef88  jz      short loc_18008EF95
0x18008ef8a  mov     rax, [rbp+4Fh+lpMem]
0x18008ef8e  mov     [r15], rax
0x18008ef91  mov     [rbp+4Fh+lpMem], rsi
0x18008ef95  cmp     [rbp+4Fh+lpMem], 0
0x18008ef9a  jz      short loc_18008EFC5
0x18008ef9c  call    cs:__imp_GetProcessHeap
0x18008efa3  nop     dword ptr [rax+rax+00h]
0x18008efa8  mov     r8, [rbp+4Fh+lpMem]; lpMem
0x18008efac  xor     edx, edx; dwFlags
0x18008efae  mov     rcx, rax; hHeap
0x18008efb1  call    cs:__imp_HeapFree
0x18008efb8  nop     dword ptr [rax+rax+00h]
0x18008efbd  mov     [rbp+4Fh+lpMem], 0
0x18008efc5  test    rsi, rsi
0x18008efc8  jz      short loc_18008EFEA
0x18008efca  call    cs:__imp_GetProcessHeap
0x18008efd1  nop     dword ptr [rax+rax+00h]
0x18008efd6  mov     r8, rsi; lpMem
0x18008efd9  xor     edx, edx; dwFlags
0x18008efdb  mov     rcx, rax; hHeap
0x18008efde  call    cs:__imp_HeapFree
0x18008efe5  nop     dword ptr [rax+rax+00h]
0x18008efea  cmp     [rbp+4Fh+var_90], 0
0x18008efef  jz      short loc_18008F01A
0x18008eff1  call    cs:__imp_GetProcessHeap
0x18008eff8  nop     dword ptr [rax+rax+00h]
0x18008effd  mov     r8, [rbp+4Fh+var_90]; lpMem
0x18008f001  xor     edx, edx; dwFlags
0x18008f003  mov     rcx, rax; hHeap
0x18008f006  call    cs:__imp_HeapFree
0x18008f00d  nop     dword ptr [rax+rax+00h]
0x18008f012  mov     [rbp+4Fh+var_90], 0
0x18008f01a  cmp     [rbp+4Fh+var_88], 0
0x18008f01f  jz      short loc_18008F04A
0x18008f021  call    cs:__imp_GetProcessHeap
0x18008f028  nop     dword ptr [rax+rax+00h]
0x18008f02d  mov     r8, [rbp+4Fh+var_88]; lpMem
0x18008f031  xor     edx, edx; dwFlags
0x18008f033  mov     rcx, rax; hHeap
0x18008f036  call    cs:__imp_HeapFree
0x18008f03d  nop     dword ptr [rax+rax+00h]
0x18008f042  mov     [rbp+4Fh+var_88], 0
0x18008f04a  cmp     [rbp+4Fh+var_80], 0
0x18008f04f  jz      short loc_18008F07A
0x18008f051  call    cs:__imp_GetProcessHeap
0x18008f058  nop     dword ptr [rax+rax+00h]
0x18008f05d  mov     r8, [rbp+4Fh+var_80]; lpMem
0x18008f061  xor     edx, edx; dwFlags
0x18008f063  mov     rcx, rax; hHeap
0x18008f066  call    cs:__imp_HeapFree
0x18008f06d  nop     dword ptr [rax+rax+00h]
0x18008f072  mov     [rbp+4Fh+var_80], 0
0x18008f07a  test    r14, r14
0x18008f07d  jz      short loc_18008F08C
0x18008f07f  lea     rcx, [rbp+4Fh+var_C0]
0x18008f083  mov     [rbp+4Fh+var_C0], r14
0x18008f087  call    WxFreeHeapEx
0x18008f08c  test    byte ptr cs:xmmword_1800AD720, 8
0x18008f093  jz      short loc_18008F0AE
0x18008f095  mov     edx, 40h ; '@'
0x18008f09a  lea     r8, WPP_56419e6f729131a1bc9745be6fd81bf0_Traceguids
0x18008f0a1  mov     ecx, 403h
0x18008f0a6  mov     r9d, ebx
0x18008f0a9  call    WPP_SF_d
0x18008f0ae  mov     eax, ebx
0x18008f0b0  mov     rcx, [rbp+4Fh+var_50]
0x18008f0b4  xor     rcx, rsp; StackCookie
0x18008f0b7  call    __security_check_cookie
0x18008f0bc  add     rsp, 0D8h
0x18008f0c3  pop     r15
0x18008f0c5  pop     r14
0x18008f0c7  pop     r13
0x18008f0c9  pop     r12
0x18008f0cb  pop     rdi
0x18008f0cc  pop     rsi
0x18008f0cd  pop     rbx
0x18008f0ce  pop     rbp
0x18008f0cf  retn
```
