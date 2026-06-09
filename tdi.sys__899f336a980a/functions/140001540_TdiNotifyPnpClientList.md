# TdiNotifyPnpClientList

- ea: `0x140001540`
- end: `0x140001bfb`
- name: `TdiNotifyPnpClientList`
- size: `1723`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400032e0`

## callees

- `0x140001540`
- `0x140001c10`
- `0x140001c60`
- `0x140001cb0`
- `0x140001d30`
- `0x140005530`
- `0x140005600`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140001820`
- `ntoskrnl!ExAllocatePool2` at `0x140001820`
- `ntoskrnl!_wcsicmp` at `0x1400016bc`
- `ntoskrnl!_wcsicmp` at `0x140001b36`
- `ntoskrnl!_wcsicmp` at `0x1400016bc`
- `ntoskrnl!_wcsicmp` at `0x140001b36`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400018f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001a86`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400018f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001a86`
- `ntoskrnl!_wcsnicmp` at `0x14000177d`
- `ntoskrnl!_wcsnicmp` at `0x14000177d`
- `ntoskrnl!DbgPrint` at `0x140001bea`
- `ntoskrnl!DbgPrint` at `0x140001bea`

## pseudocode

```c
__int64 __fastcall TdiNotifyPnpClientList(_QWORD *a1, __int64 a2, size_t a3)
{
  _QWORD *v3; // r14
  __int64 result; // rax
  char v5; // si
  __int64 v6; // r12
  char v7; // al
  __int64 (__fastcall *v8)(__int64, _QWORD, _QWORD, _QWORD); // rax
  int v9; // eax
  void (__fastcall *v10)(__int64, __int64, _QWORD, __int64); // rax
  const wchar_t *v11; // rbx
  const wchar_t *v12; // rdi
  __int64 v13; // rax
  bool v14; // zf
  char v15; // al
  _QWORD *v16; // rbx
  int v17; // edi
  unsigned __int16 *v18; // r13
  const wchar_t *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rsi
  wchar_t *v23; // rbp
  size_t v24; // rdi
  size_t v25; // r12
  _WORD *Pool2; // rax
  _WORD *v27; // rbx
  int v28; // eax
  size_t v29; // r14
  __int64 i; // rdi
  void (__fastcall *v31)(__int64, __int64, _QWORD, __int64); // rax
  HRESULT v32; // eax
  wchar_t *v33; // r10
  size_t v34; // rdx
  HRESULT v35; // eax
  char IsSzInMultiSzSafe; // al
  size_t v37; // rbp
  __int64 v38; // rcx
  void (__fastcall *v39)(__int64, __int64 *, size_t, __int64); // rax
  const wchar_t *v40; // r14
  _WORD *v41; // rbp
  const wchar_t *j; // rdi
  __int64 v43; // rsi
  int v44; // eax
  __int64 v45; // r9
  __int64 v46; // rax
  _QWORD *v47; // [rsp+30h] [rbp-68h]
  size_t pcchLength[4]; // [rsp+38h] [rbp-60h] BYREF
  char v51; // [rsp+B0h] [rbp+18h]
  unsigned int v52; // [rsp+B8h] [rbp+20h]

  v51 = a3;
  v3 = (_QWORD *)*a1;
  result = 0;
  v52 = 0;
  v5 = a3;
  v47 = (_QWORD *)*a1;
  v6 = a2;
  if ( (_QWORD *)*a1 != a1 )
  {
    while ( 1 )
    {
      v7 = *(_BYTE *)(v6 + 16);
      *(_QWORD *)(v6 + 24) = v3;
      if ( !v7 )
        break;
      if ( v7 == 1 )
      {
        if ( *((_WORD *)v3 + 12) != 1 )
        {
          if ( v5 )
            v10 = (void (__fastcall *)(__int64, __int64, _QWORD, __int64))v3[8];
          else
            v10 = (void (__fastcall *)(__int64, __int64, _QWORD, __int64))v3[9];
          if ( v10 )
            v10(v6 + 120, v6 + 64, *(_QWORD *)(v6 + 88), 1);
          goto LABEL_6;
        }
        if ( v5 )
          v39 = (void (__fastcall *)(__int64, __int64 *, size_t, __int64))v3[8];
        else
          v39 = (void (__fastcall *)(__int64, __int64 *, size_t, __int64))v3[9];
LABEL_78:
        if ( v39 )
          v39(v6 + 120, qword_140007160, a3, 1);
        goto LABEL_6;
      }
      if ( v7 != 2 )
      {
        if ( v7 == 3 )
        {
          if ( *(_DWORD *)(v6 + 100) )
          {
            if ( *((_WORD *)v3 + 12) != 1 )
            {
              v31 = (void (__fastcall *)(__int64, __int64, _QWORD, __int64))v3[6];
              if ( v31 )
              {
                v31(4, v6 + 120, 0, 1);
                if ( ProvidersReady == ProvidersRegistered )
                  ((void (__fastcall *)(__int64, _QWORD, _QWORD))v3[6])(5, 0, 0);
              }
            }
          }
        }
        goto LABEL_6;
      }
      v8 = (__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))v3[10];
      if ( !v8 )
        goto LABEL_6;
      v28 = v8(v6 + 120, *(_QWORD *)(v6 + 40), *(_QWORD *)(v6 + 80), *(_QWORD *)(v6 + 88));
      if ( v28 != 259 )
      {
        if ( v28 < 0 )
        {
          *(_DWORD *)(v6 + 56) = v28;
          DbgPrint("Client: %wZ returned %x\n", v3 + 4, (unsigned int)v28);
        }
        _InterlockedDecrement((volatile signed __int32 *)(v6 + 96));
LABEL_6:
        v9 = v52;
        goto LABEL_7;
      }
      v9 = 259;
      v52 = 259;
LABEL_7:
      v3 = (_QWORD *)*v3;
      v47 = v3;
      *(_QWORD *)(v6 + 24) = 0;
      *(_DWORD *)(v6 + 32) = v9;
LABEL_8:
      v5 = v51;
      if ( v3 == a1 )
        return v52;
    }
    v11 = (const wchar_t *)v3[13];
    if ( v11 )
    {
      v12 = *(const wchar_t **)(v6 + 128);
      if ( v12 )
      {
        while ( *v11 )
        {
          if ( !_wcsicmp(v11, v12) )
          {
            v15 = 1;
            goto LABEL_24;
          }
          v13 = -1;
          do
            v14 = v11[++v13] == 0;
          while ( !v14 );
          v11 += v13 + 1;
        }
      }
    }
    v15 = 0;
LABEL_24:
    if ( *((_WORD *)v3 + 12) != 1 )
    {
      if ( !v15 )
      {
        if ( v3[6] )
        {
          v16 = (_QWORD *)v3[11];
          if ( v16 )
          {
            v17 = 0;
            v18 = (unsigned __int16 *)(v6 + 120);
            if ( *v16 )
            {
              do
              {
                a3 = (unsigned __int64)*v18 >> 1;
                v19 = (const wchar_t *)v16[v17];
                v20 = -1;
                do
                  ++v20;
                while ( v19[v20] );
                if ( a3 == v20 && !_wcsnicmp(*(const wchar_t **)(v6 + 128), v19, a3) )
                  break;
                ++v17;
              }
              while ( v16[v17] );
            }
            if ( v16[v17] )
            {
              pcchLength[0] = 0;
              v21 = 0;
              v22 = 0;
              v23 = (wchar_t *)(v3[11] + 8LL * *((unsigned int *)v3 + 24));
              while ( !v21 )
              {
                if ( !qword_140007160
                  || (v32 = StringLengthWorkerW((STRSAFE_PCNZWCH)qword_140007160, 3u, pcchLength), v32 < 0) )
                {
                  pcchLength[0] = 0;
                  goto LABEL_8;
                }
                if ( v32 )
                  goto LABEL_8;
                if ( !(unsigned __int8)TdipIsSzInMultiSzSafe(v33, v23) )
                  v22 += 2 * pcchLength[0] + 2;
                v21 += pcchLength[0] + 1;
              }
              if ( v22 )
              {
                v24 = (unsigned int)TdipCbOfMultiSzSafe(v23);
                v25 = v24 + v22;
                Pool2 = (_WORD *)ExAllocatePool2(64, v24 + v22 + 2, 1783186516);
                v27 = Pool2;
                if ( !Pool2 )
                {
                  v6 = a2;
                  goto LABEL_8;
                }
                v29 = v24 >> 1;
                memmove(Pool2, v23, v24);
                for ( i = 0; !i; i += v37 + 1 )
                {
                  if ( !qword_140007160
                    || (v34 = 1 - i + 1, v34 > 0x7FFFFFFF)
                    || (v35 = StringLengthWorkerW((STRSAFE_PCNZWCH)qword_140007160 + i, v34, pcchLength), v35 < 0) )
                  {
                    pcchLength[0] = 0;
LABEL_51:
                    ExFreePoolWithTag(v27, 0x6A494454u);
                    v3 = v47;
                    v6 = a2;
                    goto LABEL_8;
                  }
                  if ( v35 )
                    goto LABEL_51;
                  IsSzInMultiSzSafe = TdipIsSzInMultiSzSafe((wchar_t *)qword_140007160 + i, v27);
                  v37 = pcchLength[0];
                  if ( !IsSzInMultiSzSafe )
                  {
                    if ( StringCchCatW(&v27[v29], ((v25 + 2) >> 1) - v29, (STRSAFE_LPCWSTR)qword_140007160 + i) )
                      goto LABEL_51;
                    v29 += v37 + 1;
                  }
                }
                v40 = (const wchar_t *)v47[13];
                if ( v40 && *v40 && *v27 )
                {
                  v41 = v27;
                  do
                  {
                    for ( j = v40; *j; j += (unsigned int)(v43 + 1) )
                    {
                      v43 = -1;
                      do
                        ++v43;
                      while ( j[v43] );
                      if ( !_wcsicmp(v41, j) )
                      {
                        v44 = TdipCbOfMultiSzSafe(&v41[(unsigned int)v43 + 1]);
                        memmove(v41, (char *)v41 + v45 + 2, v44 + 2);
                        goto LABEL_95;
                      }
                    }
                    v46 = -1;
                    do
                      v14 = v41[++v46] == 0;
                    while ( !v14 );
                    v41 += v46 + 1;
LABEL_95:
                    ;
                  }
                  while ( *v41 );
                }
                v3 = v47;
                v6 = a2;
              }
              else
              {
                v27 = 0;
              }
              v38 = 1;
              if ( !v51 )
                v38 = 2;
              ((void (__fastcall *)(__int64, unsigned __int16 *, _WORD *))v3[6])(v38, v18, v27);
              ExFreePoolWithTag(v27, 0x6A494454u);
            }
          }
        }
      }
      goto LABEL_6;
    }
    if ( v5 )
      v39 = (void (__fastcall *)(__int64, __int64 *, size_t, __int64))v3[6];
    else
      v39 = (void (__fastcall *)(__int64, __int64 *, size_t, __int64))v3[7];
    goto LABEL_78;
  }
  return result;
}

```

## disassembly

```asm
0x140001540  mov     r11, rsp
0x140001543  mov     [r11+18h], r8b
0x140001547  mov     [r11+10h], rdx
0x14000154b  mov     [r11+8], rcx
0x14000154f  push    rsi
0x140001550  push    r12
0x140001552  push    r14
0x140001554  sub     rsp, 80h
0x14000155b  mov     r14, [rcx]
0x14000155e  xor     eax, eax
0x140001560  mov     [rsp+98h+arg_18], eax
0x140001567  movzx   esi, r8b
0x14000156b  mov     [rsp+98h+var_68], r14
0x140001570  mov     r12, rdx
0x140001573  cmp     r14, rcx
0x140001576  jz      loc_14000164B
0x14000157c  mov     [r11-20h], rbx
0x140001580  lea     rdx, qword_140007160
0x140001587  mov     [r11-28h], rbp
0x14000158b  mov     r9d, 1
0x140001591  mov     [r11-30h], rdi
0x140001595  mov     r10d, 2
0x14000159b  mov     [r11-38h], r13
0x14000159f  mov     [r11-40h], r15
0x1400015a3  mov     r11d, 4
0x1400015a9  nop     dword ptr [rax+00000000h]
0x1400015b0  movzx   eax, byte ptr [r12+10h]
0x1400015b6  mov     [r12+18h], r14
0x1400015bb  test    al, al
0x1400015bd  jz      loc_140001693
0x1400015c3  cmp     al, 1
0x1400015c5  jz      loc_140001659
0x1400015cb  cmp     al, 2
0x1400015cd  jnz     loc_14000190E
0x1400015d3  mov     rax, [r14+50h]
0x1400015d7  test    rax, rax
0x1400015da  jnz     loc_140001856
0x1400015e0  mov     eax, [rsp+98h+arg_18]
0x1400015e7  mov     r14, [r14]
0x1400015ea  mov     [rsp+98h+var_68], r14
0x1400015ef  mov     qword ptr [r12+18h], 0
0x1400015f8  mov     [r12+20h], eax
0x1400015fd  mov     rcx, [rsp+98h+arg_0]
0x140001605  mov     r11d, 4
0x14000160b  mov     r10d, 2
0x140001611  movzx   esi, [rsp+98h+arg_10]
0x140001619  mov     r9d, 1
0x14000161f  lea     rdx, qword_140007160
0x140001626  cmp     r14, rcx
0x140001629  jnz     short loc_1400015B0
0x14000162b  mov     r15, [rsp+98h+var_40]
0x140001630  mov     r13, [rsp+98h+var_38]
0x140001635  mov     rdi, [rsp+98h+var_30]
0x14000163a  mov     rbp, [rsp+98h+var_28]
0x14000163f  mov     rbx, [rsp+98h+var_20]
0x140001644  mov     eax, [rsp+98h+arg_18]
0x14000164b  add     rsp, 80h
0x140001652  pop     r14
0x140001654  pop     r12
0x140001656  pop     rsi
0x140001657  retn
0x140001659  cmp     r9w, [r14+18h]
0x14000165e  jz      loc_140001BBC
0x140001664  test    sil, sil
0x140001667  jnz     loc_140001BCE
0x14000166d  mov     rax, [r14+48h]
0x140001671  test    rax, rax
0x140001674  jz      loc_1400015E0
0x14000167a  mov     r8, [r12+58h]
0x14000167f  lea     rdx, [r12+40h]
0x140001684  lea     rcx, [r12+78h]
0x140001689  call    _guard_dispatch_icall
0x14000168e  jmp     loc_1400015E0
0x140001693  mov     rbx, [r14+68h]
0x140001697  test    rbx, rbx
0x14000169a  jz      short loc_140001717
0x14000169c  mov     rdi, [r12+80h]
0x1400016a4  test    rdi, rdi
0x1400016a7  jz      short loc_140001717
0x1400016a9  nop     dword ptr [rax+00000000h]
0x1400016b0  cmp     word ptr [rbx], 0
0x1400016b4  jz      short loc_1400016F6
0x1400016b6  mov     rdx, rdi; Str2
0x1400016b9  mov     rcx, rbx; Str1
0x1400016bc  call    cs:__imp__wcsicmp
0x1400016c3  nop     dword ptr [rax+rax+00h]
0x1400016c8  test    eax, eax
0x1400016ca  jz      loc_140001A97
0x1400016d0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400016d7  nop     word ptr [rax+rax+00000000h]
0x1400016e0  cmp     word ptr [rbx+rax*2+2], 0
0x1400016e6  lea     rax, [rax+1]
0x1400016ea  jnz     short loc_1400016E0
0x1400016ec  lea     rbx, [rbx+rax*2]
0x1400016f0  add     rbx, 2
0x1400016f4  jmp     short loc_1400016B0
0x1400016f6  mov     rcx, [rsp+98h+arg_0]
0x1400016fe  lea     rdx, qword_140007160
0x140001705  mov     r9d, 1
0x14000170b  mov     r10d, 2
0x140001711  mov     r11d, 4
0x140001717  xor     al, al
0x140001719  cmp     r9w, [r14+18h]
0x14000171e  jz      loc_140001ABF
0x140001724  test    al, al
0x140001726  jnz     loc_1400015E0
0x14000172c  cmp     qword ptr [r14+30h], 0
0x140001731  jz      loc_1400015E0
0x140001737  mov     rbx, [r14+58h]
0x14000173b  test    rbx, rbx
0x14000173e  jz      loc_1400015E0
0x140001744  xor     edi, edi
0x140001746  lea     r13, [r12+78h]
0x14000174b  cmp     [rbx], rdi
0x14000174e  jz      short loc_1400017AC
0x140001750  movzx   r8d, word ptr [r13+0]
0x140001755  movsxd  rax, edi
0x140001758  shr     r8, 1; MaxCount
0x14000175b  mov     rdx, [rbx+rax*8]; Str2
0x14000175f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140001766  inc     rax
0x140001769  cmp     word ptr [rdx+rax*2], 0
0x14000176e  jnz     short loc_140001766
0x140001770  cmp     r8, rax
0x140001773  jnz     loc_140001841
0x140001779  mov     rcx, [r13+8]; Str1
0x14000177d  call    cs:__imp__wcsnicmp
0x140001784  nop     dword ptr [rax+rax+00h]
0x140001789  test    eax, eax
0x14000178b  jnz     loc_140001841
0x140001791  mov     rcx, [rsp+98h+arg_0]
0x140001799  lea     rdx, qword_140007160
0x1400017a0  mov     r10d, 2
0x1400017a6  mov     r11d, 4
0x1400017ac  movsxd  rax, edi
0x1400017af  cmp     qword ptr [rbx+rax*8], 0
0x1400017b4  jz      loc_1400015E0
0x1400017ba  xor     eax, eax
0x1400017bc  movzx   edi, r10w
0x1400017c0  mov     dword ptr [rsp+98h+pcchLength+4], eax
0x1400017c4  mov     [rsp+38h], rax
0x1400017c9  movzx   eax, r11w
0x1400017cd  sub     rax, rdi
0x1400017d0  cmp     rax, 2
0x1400017d4  jb      loc_140001611
0x1400017da  mov     ecx, [r14+60h]
0x1400017de  xor     ebx, ebx
0x1400017e0  mov     rax, [r14+58h]
0x1400017e4  xor     esi, esi
0x1400017e6  mov     r15d, edi
0x1400017e9  shr     r15, 1
0x1400017ec  lea     rbp, [rax+rcx*8]
0x1400017f0  cmp     rbx, r15
0x1400017f3  jb      loc_14000188D
0x1400017f9  test    rsi, rsi
0x1400017fc  jz      loc_140001BB5
0x140001802  mov     rcx, rbp
0x140001805  call    TdipCbOfMultiSzSafe
0x14000180a  mov     edi, eax
0x14000180c  mov     r8d, 6A494454h
0x140001812  mov     ecx, 40h ; '@'
0x140001817  lea     r12, [rdi+rsi]
0x14000181b  lea     rdx, [r12+2]
0x140001820  call    cs:__imp_ExAllocatePool2
0x140001827  nop     dword ptr [rax+rax+00h]
0x14000182c  mov     rbx, rax
0x14000182f  test    rax, rax
0x140001832  jnz     short loc_1400018AC
0x140001834  mov     r12, [rsp+98h+arg_8]
0x14000183c  jmp     loc_1400015FD
0x140001841  inc     edi
0x140001843  movsxd  rax, edi
0x140001846  cmp     qword ptr [rbx+rax*8], 0
0x14000184b  jz      loc_140001791
0x140001851  jmp     loc_140001750
0x140001856  mov     r9, [r12+58h]
0x14000185b  lea     rcx, [r12+78h]
0x140001860  mov     r8, [r12+50h]
0x140001865  mov     rdx, [r12+28h]
0x14000186a  call    _guard_dispatch_icall
0x14000186f  cmp     eax, 103h
0x140001874  jz      loc_1400019D3
0x14000187a  test    eax, eax
0x14000187c  js      loc_140001BD7
0x140001882  lock dec dword ptr [r12+60h]
0x140001888  jmp     loc_1400015E0
0x14000188d  lea     rcx, [rbx+rbx]
0x140001891  lea     r10, [rcx+rdx]
0x140001895  test    r10, r10
0x140001898  jnz     loc_140001974
0x14000189e  mov     qword ptr [rsp+38h], 0
0x1400018a7  jmp     loc_1400015FD
0x1400018ac  mov     r14, rdi
0x1400018af  mov     r8, rdi; Size
0x1400018b2  mov     rdx, rbp; Src
0x1400018b5  shr     r14, 1
0x1400018b8  mov     rcx, rbx; void *
0x1400018bb  call    memmove
0x1400018c0  xor     edi, edi
0x1400018c2  cmp     rdi, r15
0x1400018c5  jnb     loc_140001AEC
0x1400018cb  lea     rax, qword_140007160
0x1400018d2  lea     rsi, [rax+rdi*2]
0x1400018d6  test    rsi, rsi
0x1400018d9  jnz     loc_1400019E4
0x1400018df  mov     qword ptr [rsp+38h], 0
0x1400018e8  mov     edx, 6A494454h; Tag
0x1400018ed  mov     rcx, rbx; P
0x1400018f0  call    cs:__imp_ExFreePoolWithTag
0x1400018f7  nop     dword ptr [rax+rax+00h]
0x1400018fc  mov     r14, [rsp+98h+var_68]
0x140001901  mov     r12, [rsp+98h+arg_8]
0x140001909  jmp     loc_1400015FD
0x14000190e  cmp     al, 3
0x140001910  jnz     loc_1400015E0
0x140001916  cmp     dword ptr [r12+64h], 0
0x14000191c  jz      loc_1400015E0
0x140001922  cmp     r9w, [r14+18h]
0x140001927  jz      loc_1400015E0
0x14000192d  mov     rax, [r14+30h]
0x140001931  test    rax, rax
0x140001934  jz      loc_1400015E0
0x14000193a  lea     rdx, [r12+78h]
0x14000193f  xor     r8d, r8d
0x140001942  mov     ecx, r11d
0x140001945  call    _guard_dispatch_icall
0x14000194a  mov     eax, cs:ProvidersRegistered
0x140001950  cmp     cs:ProvidersReady, eax
0x140001956  jnz     loc_1400015E0
0x14000195c  mov     rax, [r14+30h]
0x140001960  xor     r8d, r8d
0x140001963  xor     edx, edx
0x140001965  mov     ecx, 5
0x14000196a  call    _guard_dispatch_icall
0x14000196f  jmp     loc_1400015E0
0x140001974  mov     rdx, rdi
0x140001977  sub     rdx, rcx
0x14000197a  inc     rdx; cchMax
0x14000197d  cmp     rdx, 7FFFFFFFh
0x140001984  ja      loc_14000189E
0x14000198a  lea     r8, [rsp+98h+pcchLength]; pcchLength
0x14000198f  mov     rcx, r10; psz
0x140001992  call    StringLengthWorkerW
0x140001997  test    eax, eax
0x140001999  js      loc_14000189E
0x14000199f  jnz     loc_1400015FD
0x1400019a5  mov     rdx, rbp; Str1
0x1400019a8  mov     rcx, r10; Str2
0x1400019ab  call    TdipIsSzInMultiSzSafe
0x1400019b0  mov     rcx, [rsp+98h+pcchLength]
0x1400019b5  test    al, al
0x1400019b7  jnz     short loc_1400019C1
0x1400019b9  lea     rsi, [rsi+rcx*2]
0x1400019bd  add     rsi, 2
0x1400019c1  inc     rbx
0x1400019c4  lea     rdx, qword_140007160
0x1400019cb  add     rbx, rcx
0x1400019ce  jmp     loc_1400017F0
0x1400019d3  mov     eax, 103h
0x1400019d8  mov     [rsp+98h+arg_18], eax
0x1400019df  jmp     loc_1400015E7
0x1400019e4  mov     rdx, r15
0x1400019e7  sub     rdx, rdi
0x1400019ea  inc     rdx; cchMax
0x1400019ed  cmp     rdx, 7FFFFFFFh
0x1400019f4  ja      loc_1400018DF
0x1400019fa  lea     r8, [rsp+98h+pcchLength]; pcchLength
0x1400019ff  mov     rcx, rsi; psz
0x140001a02  call    StringLengthWorkerW
0x140001a07  test    eax, eax
0x140001a09  js      loc_1400018DF
0x140001a0f  jnz     loc_1400018E8
0x140001a15  mov     rdx, rbx; Str1
0x140001a18  mov     rcx, rsi; Str2
0x140001a1b  call    TdipIsSzInMultiSzSafe
0x140001a20  mov     rbp, [rsp+98h+pcchLength]
0x140001a25  test    al, al
0x140001a27  jz      short loc_140001A34
0x140001a29  inc     rdi
0x140001a2c  add     rdi, rbp
0x140001a2f  jmp     loc_1400018C2
0x140001a34  lea     rdx, [r12+2]
0x140001a39  mov     r8, rsi; pszSrc
0x140001a3c  shr     rdx, 1
0x140001a3f  lea     rcx, [rbx+r14*2]; pszDest
0x140001a43  sub     rdx, r14; cchDest
0x140001a46  call    StringCchCatW
0x140001a4b  test    eax, eax
0x140001a4d  jnz     loc_1400018E8
0x140001a53  inc     r14
0x140001a56  add     r14, rbp
0x140001a59  jmp     short loc_140001A29
0x140001a5b  cmp     [rsp+98h+arg_10], 0
0x140001a63  mov     r8, rbx
0x140001a66  mov     rax, [r14+30h]
0x140001a6a  mov     rdx, r13
0x140001a6d  mov     ecx, 1
0x140001a72  jnz     short loc_140001A79
0x140001a74  mov     ecx, 2
0x140001a79  call    _guard_dispatch_icall
  ... truncated ...
```
