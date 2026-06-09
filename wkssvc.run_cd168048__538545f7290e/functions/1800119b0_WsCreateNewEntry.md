# WsCreateNewEntry

- ea: `0x1800119b0`
- end: `0x180011bb4`
- name: `WsCreateNewEntry`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b900`

## callees

- `0x18000b4f0`
- `0x1800119b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011ac0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011b04`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011b7b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011ac0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011b04`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011b7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a29`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011a12`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011b49`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011a12`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011b49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011b60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011b60`

## pseudocode

```c
DWORD __fastcall WsCreateNewEntry(
        HLOCAL *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        int a8,
        _OWORD *a9,
        _QWORD *a10,
        _QWORD *a11)
{
  __int64 v15; // rdi
  int v16; // ecx
  _QWORD *v17; // rax
  _QWORD *v18; // rdx
  int v20; // eax
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rax
  __int64 v23; // rbp
  unsigned int v24; // edi
  SIZE_T v25; // rdx
  _DWORD *v26; // rax
  _DWORD *v27; // rbx
  _QWORD *v28; // rax
  unsigned int v29; // [rsp+58h] [rbp+20h] BYREF

  if ( a4 <= 0xFFFF )
  {
    v29 = 2 * a4 + 98;
    NetpULongRoundUp(v29, 2, &v29);
    v15 = a7;
    if ( a3 )
      v16 = *(unsigned __int16 *)(a7 + 2);
    else
      v16 = 0;
    v17 = LocalAlloc(0x40u, v16 + v29);
    *a1 = v17;
    v18 = v17;
    if ( !v17 )
      return GetLastError();
    *v17 = 0;
    *((_DWORD *)v17 + 6) = a4;
    *((_DWORD *)v17 + 7) = 1;
    v17[4] = a2;
    v20 = dword_1800512F0;
    *((_DWORD *)v18 + 10) = dword_1800512F0;
    *((_DWORD *)v18 + 14) = a8;
    if ( a9 )
      *(_OWORD *)((char *)v18 + 60) = *a9;
    if ( a10 )
      *(_QWORD *)((char *)v18 + 76) = *a10;
    if ( a11 )
      *(_QWORD *)((char *)v18 + 84) = *a11;
    dword_1800512F0 = (v20 + 1) & 0x7FFFFFFF;
    if ( a3 )
    {
      v18[2] = v18 + 12;
      _o_wcscpy_s(v18 + 12, a4 + 1, a3);
      v21 = (unsigned __int64)*a1 + 2 * a4 + 98;
      if ( v21 + 2 < v21 )
        v22 = -1;
      else
        v22 = (v21 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
      *((_QWORD *)*a1 + 6) = v22;
      _o_wcscpy_s(*((_QWORD *)*a1 + 6), (unsigned __int64)*(unsigned __int16 *)(v15 + 2) >> 1, *(_QWORD *)(v15 + 8));
    }
    else
    {
      v18[2] = 0;
      v18[6] = 0;
    }
    v23 = a5;
    if ( !a5 )
      return 0;
    v24 = a6;
    v25 = 2 * a6 + 18;
    if ( (unsigned int)v25 >= 0x10 && (unsigned int)v25 >> 1 >= a6 )
    {
      v26 = LocalAlloc(0x40u, v25);
      v27 = v26;
      if ( !v26 )
      {
        LocalFree(*a1);
        return GetLastError();
      }
      _o_wcscpy_s(v26 + 2, v24 + 1, v23);
      v28 = *a1;
      v27[1] = v24;
      *v27 = 1;
      v28[1] = v27;
      return 0;
    }
  }
  return 2317;
}

```

## disassembly

```asm
0x1800119b0  mov     rax, rsp
0x1800119b3  mov     [rax+8], rbx
0x1800119b7  mov     [rax+10h], rbp
0x1800119bb  push    rsi
0x1800119bc  push    rdi
0x1800119bd  push    r14
0x1800119bf  sub     rsp, 20h
0x1800119c3  mov     ebx, r9d
0x1800119c6  mov     rbp, r8
0x1800119c9  mov     r14, rdx
0x1800119cc  mov     rsi, rcx
0x1800119cf  cmp     r9d, 0FFFFh
0x1800119d6  ja      loc_180011B9B
0x1800119dc  lea     ecx, ds:62h[r9*2]
0x1800119e4  mov     edx, 2
0x1800119e9  lea     r8, [rax+20h]
0x1800119ed  mov     [rax+20h], ecx
0x1800119f0  call    NetpULongRoundUp
0x1800119f5  mov     rdi, [rsp+38h+arg_30]
0x1800119fa  test    rbp, rbp
0x1800119fd  jz      short loc_180011A05
0x1800119ff  movzx   ecx, word ptr [rdi+2]
0x180011a03  jmp     short loc_180011A07
0x180011a05  xor     ecx, ecx
0x180011a07  mov     edx, [rsp+38h+arg_18]
0x180011a0b  add     edx, ecx; uBytes
0x180011a0d  mov     ecx, 40h ; '@'; uFlags
0x180011a12  call    cs:__imp_LocalAlloc
0x180011a19  nop     dword ptr [rax+rax+00h]
0x180011a1e  mov     [rsi], rax
0x180011a21  mov     rdx, rax
0x180011a24  test    rax, rax
0x180011a27  jnz     short loc_180011A3A
0x180011a29  call    cs:__imp_GetLastError
0x180011a30  nop     dword ptr [rax+rax+00h]
0x180011a35  jmp     loc_180011BA0
0x180011a3a  mov     qword ptr [rax], 0
0x180011a41  mov     [rax+18h], ebx
0x180011a44  mov     dword ptr [rax+1Ch], 1
0x180011a4b  mov     [rax+20h], r14
0x180011a4f  mov     eax, cs:dword_1800512F0
0x180011a55  mov     [rdx+28h], eax
0x180011a58  lea     ecx, [rax+1]
0x180011a5b  mov     eax, [rsp+38h+arg_38]
0x180011a5f  mov     [rdx+38h], eax
0x180011a62  mov     rax, [rsp+38h+arg_40]
0x180011a6a  test    rax, rax
0x180011a6d  jz      short loc_180011A77
0x180011a6f  movups  xmm0, xmmword ptr [rax]
0x180011a72  movdqu  xmmword ptr [rdx+3Ch], xmm0
0x180011a77  mov     rax, [rsp+38h+arg_48]
0x180011a7f  test    rax, rax
0x180011a82  jz      short loc_180011A8B
0x180011a84  mov     rax, [rax]
0x180011a87  mov     [rdx+4Ch], rax
0x180011a8b  mov     rax, [rsp+38h+arg_50]
0x180011a93  test    rax, rax
0x180011a96  jz      short loc_180011A9F
0x180011a98  mov     rax, [rax]
0x180011a9b  mov     [rdx+54h], rax
0x180011a9f  btr     ecx, 1Fh
0x180011aa3  mov     cs:dword_1800512F0, ecx
0x180011aa9  test    rbp, rbp
0x180011aac  jz      short loc_180011B12
0x180011aae  lea     rcx, [rdx+60h]
0x180011ab2  mov     r8, rbp
0x180011ab5  lea     eax, [rbx+1]
0x180011ab8  mov     [rdx+10h], rcx
0x180011abc  mov     edx, eax
0x180011abe  mov     ebx, eax
0x180011ac0  call    cs:__imp__o_wcscpy_s
0x180011ac7  nop     dword ptr [rax+rax+00h]
0x180011acc  mov     rdx, [rsi]
0x180011acf  lea     rcx, [rdx+60h]
0x180011ad3  lea     rcx, [rcx+rbx*2]
0x180011ad7  lea     rax, [rcx+2]
0x180011adb  cmp     rax, rcx
0x180011ade  jbe     short loc_180011AEA
0x180011ae0  lea     rax, [rcx+1]
0x180011ae4  and     rax, 0FFFFFFFFFFFFFFFEh
0x180011ae8  jmp     short loc_180011AEE
0x180011aea  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011aee  mov     [rdx+30h], rax
0x180011af2  mov     rcx, [rsi]
0x180011af5  movzx   edx, word ptr [rdi+2]
0x180011af9  mov     r8, [rdi+8]
0x180011afd  shr     rdx, 1
0x180011b00  mov     rcx, [rcx+30h]
0x180011b04  call    cs:__imp__o_wcscpy_s
0x180011b0b  nop     dword ptr [rax+rax+00h]
0x180011b10  jmp     short loc_180011B22
0x180011b12  mov     qword ptr [rdx+10h], 0
0x180011b1a  mov     qword ptr [rdx+30h], 0
0x180011b22  mov     rbp, [rsp+38h+arg_20]
0x180011b27  test    rbp, rbp
0x180011b2a  jz      short loc_180011B97
0x180011b2c  mov     edi, [rsp+38h+arg_28]
0x180011b30  lea     edx, ds:12h[rdi*2]; uBytes
0x180011b37  cmp     edx, 10h
0x180011b3a  jb      short loc_180011B9B
0x180011b3c  mov     eax, edx
0x180011b3e  shr     eax, 1
0x180011b40  cmp     eax, edi
0x180011b42  jb      short loc_180011B9B
0x180011b44  mov     ecx, 40h ; '@'; uFlags
0x180011b49  call    cs:__imp_LocalAlloc
0x180011b50  nop     dword ptr [rax+rax+00h]
0x180011b55  mov     rbx, rax
0x180011b58  test    rax, rax
0x180011b5b  jnz     short loc_180011B71
0x180011b5d  mov     rcx, [rsi]; hMem
0x180011b60  call    cs:__imp_LocalFree
0x180011b67  nop     dword ptr [rax+rax+00h]
0x180011b6c  jmp     loc_180011A29
0x180011b71  lea     edx, [rdi+1]
0x180011b74  mov     r8, rbp
0x180011b77  lea     rcx, [rax+8]
0x180011b7b  call    cs:__imp__o_wcscpy_s
0x180011b82  nop     dword ptr [rax+rax+00h]
0x180011b87  mov     rax, [rsi]
0x180011b8a  mov     [rbx+4], edi
0x180011b8d  mov     dword ptr [rbx], 1
0x180011b93  mov     [rax+8], rbx
0x180011b97  xor     eax, eax
0x180011b99  jmp     short loc_180011BA0
0x180011b9b  mov     eax, 90Dh
0x180011ba0  mov     rbx, [rsp+38h+arg_0]
0x180011ba5  mov     rbp, [rsp+38h+arg_8]
0x180011baa  add     rsp, 20h
0x180011bae  pop     r14
0x180011bb0  pop     rdi
0x180011bb1  pop     rsi
0x180011bb2  retn
```
