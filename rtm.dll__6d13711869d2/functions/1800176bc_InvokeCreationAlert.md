# InvokeCreationAlert

- ea: `0x1800176bc`
- end: `0x180017a3b`
- name: `InvokeCreationAlert`
- size: `895`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180018070`

## callees

- `0x1800176bc`
- `0x18001b548`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800177b9`
- `KERNEL32!HeapAlloc` at `0x1800177b9`
- `KERNEL32!HeapFree` at `0x1800178f3`
- `KERNEL32!HeapFree` at `0x180017993`
- `KERNEL32!HeapFree` at `0x1800178f3`
- `KERNEL32!HeapFree` at `0x180017993`
- `rtutils!RouterLogEventA` at `0x180017981`
- `rtutils!RouterLogEventA` at `0x180017a0b`
- `rtutils!RouterLogEventA` at `0x180017981`
- `rtutils!RouterLogEventA` at `0x180017a0b`

## string_xrefs

- `0x1800179b2`: `CopyAndAppendIfList : Could not allocateout interface entry %x`
- `0x18001783e`: `Invoked Creation Alert for protocol %x, %x`
- `0x180017928`: `CopyAndAppendIfList : Integer overflow %x`

## pseudocode

```c
void __fastcall InvokeCreationAlert(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        _QWORD *a7,
        _DWORD *a8)
{
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  _QWORD *v11; // rbx
  __int64 *v12; // r12
  _DWORD *v13; // rcx
  _QWORD *v14; // r15
  _DWORD *v15; // rdx
  unsigned int v16; // edi
  _DWORD *v17; // rax
  _DWORD *v18; // rsi
  __int64 *v19; // rdx
  unsigned int i; // r8d
  __int64 v21; // rcx
  __int64 ProtocolEntry; // rax
  LPSTR *plpszSubStringArray; // r11
  __int64 v24; // r15
  unsigned int v25; // ecx
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  char v29[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v9 = (_QWORD *)*a7;
  while ( v9 != a7 )
  {
    v10 = v9;
    v9 = (_QWORD *)*v9;
    if ( v10[2] == __PAIR64__(a6, a5)
      || qword_18002B950 && (unsigned int)qword_18002B950(*((unsigned int *)v10 + 4), a3) )
    {
      *((_WORD *)v10 + 16) = 0;
    }
  }
  v11 = (_QWORD *)*a7;
  while ( 2 )
  {
    while ( 2 )
    {
      if ( v11 == a7 )
        return;
      v12 = v11;
      v13 = v11 + 3;
      v14 = v11;
      v15 = (_DWORD *)v11 + 7;
      v16 = 0;
      while ( !*((_WORD *)v11 + 16) )
      {
LABEL_13:
        v11 = (_QWORD *)*v11;
        if ( v11 == a7 )
          goto LABEL_14;
      }
      if ( *((_DWORD *)v11 + 6) == *v13 && *((_DWORD *)v11 + 7) == *v15 )
      {
        ++v16;
        goto LABEL_13;
      }
LABEL_14:
      if ( !v16 )
        continue;
      break;
    }
    v17 = HeapAlloc(hHeap, 0, 16LL * v16);
    v18 = v17;
    if ( v17 )
    {
      v19 = v12;
      for ( i = 0; i < v16; ++i )
      {
        if ( *((_WORD *)v19 + 16) )
        {
          v21 = 2LL * i;
          v17[2 * v21] = *((_DWORD *)v19 + 4);
          v17[2 * v21 + 1] = *((_DWORD *)v19 + 5);
          v17[2 * v21 + 3] = 1;
          v17[2 * v21 + 2] = *((_WORD *)v19 + 17) & 0x8000;
        }
        v19 = (__int64 *)*v19;
      }
      ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, *((unsigned int *)v14 + 6), *((unsigned int *)v14 + 7));
      v24 = ProtocolEntry;
      if ( *(LPSTR **)(ProtocolEntry + 48) != plpszSubStringArray )
      {
        if ( (LPSTR *)qword_18002B8A8 != plpszSubStringArray )
        {
          LOWORD(v28) = (_WORD)plpszSubStringArray;
          FormatRRASErrorString(
            &v28,
            L"Invoked Creation Alert for protocol %x, %x",
            *(unsigned int *)(ProtocolEntry + 16),
            *(unsigned int *)(ProtocolEntry + 20));
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v28);
        }
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, unsigned int, unsigned int, unsigned int, _DWORD *))(v24 + 48))(
          a1,
          0xFFFFFFFFLL,
          a3,
          0,
          a5,
          a6,
          v16,
          v18);
        plpszSubStringArray = 0;
      }
      if ( *a8 + v16 >= *a8 )
      {
        *a8 += v16;
        v25 = (unsigned int)plpszSubStringArray;
        do
        {
          v11 = (_QWORD *)*v12;
          if ( v18[4 * v25 + 3] == (_DWORD)plpszSubStringArray )
          {
            *((_WORD *)v12 + 16) = (_WORD)plpszSubStringArray;
            --*a8;
          }
          ++v25;
          v12 = v11;
        }
        while ( v25 < v16 );
        HeapFree(hHeap, 0, v18);
        continue;
      }
      *a8 = -1;
      if ( (LPSTR *)qword_18002B8A8 != plpszSubStringArray )
      {
        LOWORD(v28) = (_WORD)plpszSubStringArray;
        FormatRRASErrorString(&v28, L"CopyAndAppendIfList : Integer overflow %x", 534);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v28);
        plpszSubStringArray = 0;
      }
      if ( dword_18002BA54 )
        RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, plpszSubStringArray, 0x216u);
      HeapFree(hHeap, 0, v18);
    }
    else
    {
      if ( qword_18002B8A8 )
      {
        LOWORD(v28) = 0;
        FormatRRASErrorString(&v28, L"CopyAndAppendIfList : Could not allocateout interface entry %x", 8);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v28);
      }
      if ( dword_18002BA54 )
        RouterLogEventA(qword_18002BA58, 1u, 0xC353u, 0, 0, 8u);
    }
    break;
  }
}

```

## disassembly

```asm
0x1800176bc  mov     [rsp-8+arg_8], rbx
0x1800176c1  push    rbp
0x1800176c2  push    rsi
0x1800176c3  push    rdi
0x1800176c4  push    r12
0x1800176c6  push    r13
0x1800176c8  push    r14
0x1800176ca  push    r15
0x1800176cc  lea     rbp, [rsp-770h]
0x1800176d4  sub     rsp, 870h
0x1800176db  mov     rax, cs:__security_cookie
0x1800176e2  xor     rax, rsp
0x1800176e5  mov     [rbp+7A0h+var_40], rax
0x1800176ec  mov     r14, [rbp+7A0h+arg_30]
0x1800176f3  mov     r12d, r8d
0x1800176f6  mov     r13, [rbp+7A0h+arg_38]
0x1800176fd  xor     esi, esi
0x1800176ff  mov     [rsp+8A0h+var_850], r8d
0x180017704  xor     edx, edx; Val
0x180017706  mov     [rsp+8A0h+var_84C], ecx
0x18001770a  mov     r8d, 7FCh; Size
0x180017710  lea     rcx, [rsp+8A0h+var_83C]; void *
0x180017715  mov     [rsp+8A0h+var_840], esi
0x180017719  call    memset_0
0x18001771e  mov     rbx, [r14]
0x180017721  cmp     rbx, r14
0x180017724  jz      short loc_18001776B
0x180017726  mov     esi, [rbp+7A0h+arg_28]
0x18001772c  mov     r15d, [rbp+7A0h+arg_20]
0x180017733  lea     rdi, [rbx]
0x180017736  mov     rbx, [rbx]
0x180017739  mov     ecx, [rdi+10h]
0x18001773c  cmp     ecx, r15d
0x18001773f  jnz     short loc_180017746
0x180017741  cmp     [rdi+14h], esi
0x180017744  jz      short loc_18001775E
0x180017746  mov     rax, cs:qword_18002B950
0x18001774d  test    rax, rax
0x180017750  jz      short loc_180017764
0x180017752  mov     edx, r12d
0x180017755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001775a  test    eax, eax
0x18001775c  jz      short loc_180017764
0x18001775e  xor     eax, eax
0x180017760  mov     [rdi+20h], ax
0x180017764  cmp     rbx, r14
0x180017767  jnz     short loc_180017733
0x180017769  xor     esi, esi
0x18001776b  mov     rbx, [r14]
0x18001776e  jmp     loc_1800178FB
0x180017773  mov     r12, rbx
0x180017776  lea     rcx, [rbx+18h]
0x18001777a  mov     r15, rbx
0x18001777d  lea     rdx, [rbx+1Ch]
0x180017781  mov     edi, esi
0x180017783  cmp     [rbx+20h], si
0x180017787  jz      short loc_180017799
0x180017789  mov     eax, [rcx]
0x18001778b  cmp     [rbx+18h], eax
0x18001778e  jnz     short loc_1800177A1
0x180017790  mov     eax, [rdx]
0x180017792  cmp     [rbx+1Ch], eax
0x180017795  jnz     short loc_1800177A1
0x180017797  inc     edi
0x180017799  mov     rbx, [rbx]
0x18001779c  cmp     rbx, r14
0x18001779f  jnz     short loc_180017783
0x1800177a1  test    edi, edi
0x1800177a3  jz      loc_1800178FB
0x1800177a9  mov     rcx, cs:hHeap; hHeap
0x1800177b0  xor     edx, edx; dwFlags
0x1800177b2  mov     r8d, edi
0x1800177b5  shl     r8, 4; dwBytes
0x1800177b9  call    cs:__imp_HeapAlloc
0x1800177bf  xor     r11d, r11d
0x1800177c2  mov     rsi, rax
0x1800177c5  test    rax, rax
0x1800177c8  jz      loc_18001799B
0x1800177ce  mov     rdx, r12
0x1800177d1  mov     r8d, r11d
0x1800177d4  test    edi, edi
0x1800177d6  jz      short loc_180017812
0x1800177d8  cmp     [rdx+20h], r11w
0x1800177dd  jz      short loc_180017807
0x1800177df  mov     eax, [rdx+10h]
0x1800177e2  mov     ecx, r8d
0x1800177e5  add     rcx, rcx
0x1800177e8  mov     [rsi+rcx*8], eax
0x1800177eb  mov     eax, [rdx+14h]
0x1800177ee  mov     [rsi+rcx*8+4], eax
0x1800177f2  mov     dword ptr [rsi+rcx*8+0Ch], 1
0x1800177fa  movzx   eax, word ptr [rdx+22h]
0x1800177fe  and     eax, 8000h
0x180017803  mov     [rsi+rcx*8+8], eax
0x180017807  mov     rdx, [rdx]
0x18001780a  inc     r8d
0x18001780d  cmp     r8d, edi
0x180017810  jb      short loc_1800177D8
0x180017812  mov     r8d, [r15+1Ch]
0x180017816  lea     rcx, qword_18002B9A8
0x18001781d  mov     edx, [r15+18h]
0x180017821  call    GetProtocolEntry
0x180017826  mov     r15, rax
0x180017829  cmp     [rax+30h], r11
0x18001782d  jz      short loc_1800178AE
0x18001782f  cmp     cs:qword_18002B8A8, r11
0x180017836  jz      short loc_180017876
0x180017838  mov     word ptr [rsp+8A0h+var_840], r11w
0x18001783e  lea     rdx, aInvokedCreatio; "Invoked Creation Alert for protocol %x,"...
0x180017845  mov     r9d, [rax+14h]
0x180017849  lea     rcx, [rsp+8A0h+var_840]
0x18001784e  mov     r8d, [rax+10h]
0x180017852  call    FormatRRASErrorString
0x180017857  mov     rdx, cs:qword_18002B8A8
0x18001785e  lea     r8, [rsp+8A0h+var_840]
0x180017863  mov     rcx, cs:gMgmEtwContext
0x18001786a  mov     rax, cs:gMgmTemplateFunc
0x180017871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017876  mov     eax, [rbp+7A0h+arg_28]
0x18001787c  xor     r9d, r9d
0x18001787f  mov     r8d, [rsp+8A0h+var_850]
0x180017884  or      edx, 0FFFFFFFFh
0x180017887  mov     ecx, [rsp+8A0h+var_84C]
0x18001788b  mov     [rsp+8A0h+var_868], rsi
0x180017890  mov     [rsp+8A0h+var_870], edi
0x180017894  mov     [rsp+8A0h+dwErrorCode], eax
0x180017898  mov     eax, [rbp+7A0h+arg_20]
0x18001789e  mov     dword ptr [rsp+8A0h+plpszSubStringArray], eax
0x1800178a2  mov     rax, [r15+30h]
0x1800178a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178ab  xor     r11d, r11d
0x1800178ae  mov     eax, [r13+0]
0x1800178b2  lea     ecx, [rax+rdi]
0x1800178b5  cmp     ecx, eax
0x1800178b7  jb      short loc_180017909
0x1800178b9  mov     [r13+0], ecx
0x1800178bd  mov     ecx, r11d
0x1800178c0  test    edi, edi
0x1800178c2  jz      short loc_1800178E7
0x1800178c4  mov     rbx, [r12]
0x1800178c8  mov     eax, ecx
0x1800178ca  add     rax, rax
0x1800178cd  cmp     [rsi+rax*8+0Ch], r11d
0x1800178d2  jnz     short loc_1800178DE
0x1800178d4  mov     [r12+20h], r11w
0x1800178da  dec     dword ptr [r13+0]
0x1800178de  inc     ecx
0x1800178e0  mov     r12, rbx
0x1800178e3  cmp     ecx, edi
0x1800178e5  jb      short loc_1800178C4
0x1800178e7  mov     rcx, cs:hHeap; hHeap
0x1800178ee  mov     r8, rsi; lpMem
0x1800178f1  xor     edx, edx; dwFlags
0x1800178f3  call    cs:__imp_HeapFree
0x1800178f9  xor     esi, esi
0x1800178fb  cmp     rbx, r14
0x1800178fe  jnz     loc_180017773
0x180017904  jmp     loc_180017A11
0x180017909  mov     dword ptr [r13+0], 0FFFFFFFFh
0x180017911  mov     ebx, 216h
0x180017916  cmp     cs:qword_18002B8A8, r11
0x18001791d  jz      short loc_18001795B
0x18001791f  mov     r8d, ebx
0x180017922  mov     word ptr [rsp+8A0h+var_840], r11w
0x180017928  lea     rdx, aCopyandappendi_0; "CopyAndAppendIfList : Integer overflow "...
0x18001792f  lea     rcx, [rsp+8A0h+var_840]
0x180017934  call    FormatRRASErrorString
0x180017939  mov     rdx, cs:qword_18002B8A8
0x180017940  lea     r8, [rsp+8A0h+var_840]
0x180017945  mov     rcx, cs:gMgmEtwContext
0x18001794c  mov     rax, cs:gMgmTemplateFunc
0x180017953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017958  xor     r11d, r11d
0x18001795b  cmp     cs:dword_18002BA54, 1
0x180017962  jb      short loc_180017987
0x180017964  mov     rcx, cs:qword_18002BA58; hLogHandle
0x18001796b  xor     r9d, r9d; dwSubStringCount
0x18001796e  mov     [rsp+8A0h+dwErrorCode], ebx; dwErrorCode
0x180017972  mov     r8d, 0C353h; dwMessageId
0x180017978  mov     [rsp+8A0h+plpszSubStringArray], r11; plpszSubStringArray
0x18001797d  lea     edx, [r9+1]; dwEventType
0x180017981  call    cs:__imp_RouterLogEventA
0x180017987  mov     rcx, cs:hHeap; hHeap
0x18001798e  mov     r8, rsi; lpMem
0x180017991  xor     edx, edx; dwFlags
0x180017993  call    cs:__imp_HeapFree
0x180017999  jmp     short loc_180017A11
0x18001799b  cmp     cs:qword_18002B8A8, r11
0x1800179a2  mov     ebx, 8
0x1800179a7  jz      short loc_1800179E5
0x1800179a9  mov     r8d, ebx
0x1800179ac  mov     word ptr [rsp+8A0h+var_840], r11w
0x1800179b2  lea     rdx, aCopyandappendi; "CopyAndAppendIfList : Could not allocat"...
0x1800179b9  lea     rcx, [rsp+8A0h+var_840]
0x1800179be  call    FormatRRASErrorString
0x1800179c3  mov     rdx, cs:qword_18002B8A8
0x1800179ca  lea     r8, [rsp+8A0h+var_840]
0x1800179cf  mov     rcx, cs:gMgmEtwContext
0x1800179d6  mov     rax, cs:gMgmTemplateFunc
0x1800179dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179e2  xor     r11d, r11d
0x1800179e5  cmp     cs:dword_18002BA54, 1
0x1800179ec  jb      short loc_180017A11
0x1800179ee  mov     rcx, cs:qword_18002BA58; hLogHandle
0x1800179f5  xor     r9d, r9d; dwSubStringCount
0x1800179f8  mov     [rsp+8A0h+dwErrorCode], ebx; dwErrorCode
0x1800179fc  mov     r8d, 0C353h; dwMessageId
0x180017a02  mov     [rsp+8A0h+plpszSubStringArray], r11; plpszSubStringArray
0x180017a07  lea     edx, [r9+1]; dwEventType
0x180017a0b  call    cs:__imp_RouterLogEventA
0x180017a11  mov     rcx, [rbp+7A0h+var_40]
0x180017a18  xor     rcx, rsp; StackCookie
0x180017a1b  call    __security_check_cookie
0x180017a20  mov     rbx, [rsp+8A0h+arg_8]
0x180017a28  add     rsp, 870h
0x180017a2f  pop     r15
0x180017a31  pop     r14
0x180017a33  pop     r13
0x180017a35  pop     r12
0x180017a37  pop     rdi
0x180017a38  pop     rsi
0x180017a39  pop     rbp
0x180017a3a  retn
```
