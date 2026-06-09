# TranslateCouterPathToLangNeutral(_PDH_COUNTER_PATH_ELEMENTS_W *,ushort *)

- ea: `0x14001ac30`
- end: `0x14001aee4`
- name: `?TranslateCouterPathToLangNeutral@@YAXPEAU_PDH_COUNTER_PATH_ELEMENTS_W@@PEAG@Z`
- size: `692`
- prototype: `void __fastcall(struct _PDH_COUNTER_PATH_ELEMENTS_W *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x14001a760`

## callees

- `0x14001a314`
- `0x14001ac30`

## import_xrefs

- `msvcrt!wcschr` at `0x14001acea`
- `msvcrt!wcschr` at `0x14001acea`
- `msvcrt!wcsstr` at `0x14001acd6`
- `msvcrt!wcsstr` at `0x14001acd6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001aec7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001aec7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001aca6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ad1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001add9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ae45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001aeb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001aca6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ad1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001add9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ae45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001aeb9`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x14001ad2e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x14001ad2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001acba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001ade9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001ae57`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001acba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001ade9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001ae57`
- `pdh!PdhTranslate009CounterW` at `0x14001ad06`
- `pdh!PdhTranslate009CounterW` at `0x14001ad4b`
- `pdh!PdhTranslate009CounterW` at `0x14001ad06`
- `pdh!PdhTranslate009CounterW` at `0x14001ad4b`

## pseudocode

```c
void __fastcall TranslateCouterPathToLangNeutral(struct _PDH_COUNTER_PATH_ELEMENTS_W *a1, unsigned __int16 *a2)
{
  LPVOID *v4; // r8
  _QWORD *v5; // rsi
  char *v6; // rcx
  char *v7; // r9
  int v8; // edx
  int v9; // eax
  HANDLE ProcessHeap; // rax
  void *v11; // rdi
  wchar_t *v12; // rax
  wchar_t *v13; // rbp
  int v14; // eax
  SIZE_T v15; // rbx
  HANDLE v16; // rax
  LPVOID v17; // rax
  _QWORD *v18; // r8
  _QWORD *i; // rdx
  char *v20; // rcx
  char *v21; // r10
  int v22; // r9d
  int v23; // eax
  HANDLE v24; // rax
  _QWORD *v25; // rax
  struct _PDH_COUNTER_PATH_ELEMENTS_W *v26; // rax
  struct _PDH_COUNTER_PATH_ELEMENTS_W *v27; // rax
  HANDLE v28; // rax
  _QWORD *v29; // rbx
  __int64 v30; // rax
  struct _PDH_COUNTER_PATH_ELEMENTS_W *v31; // rax
  struct _PDH_COUNTER_PATH_ELEMENTS_W *v32; // rax
  HANDLE v33; // rax
  unsigned int v34; // [rsp+60h] [rbp+18h] BYREF

  v34 = 260;
  if ( !byte_140082278 )
  {
    v4 = (LPVOID *)qword_140082268;
    v5 = 0;
    while ( &qword_140082268 != v4 )
    {
      v6 = (char *)*((_QWORD *)v4[3] + 1);
      v7 = (char *)((char *)a1->szObjectName - v6);
      do
      {
        v8 = *(unsigned __int16 *)&v7[(_QWORD)v6];
        v9 = *(unsigned __int16 *)v6 - v8;
        if ( v9 )
          break;
        v6 += 2;
      }
      while ( v8 );
      if ( !v9 )
      {
        v5 = v4;
        v18 = v4 + 4;
        for ( i = (_QWORD *)*v18; v18 != i; i = (_QWORD *)*i )
        {
          v20 = *(char **)(i[3] + 40LL);
          v21 = (char *)((char *)a1->szCounterName - v20);
          do
          {
            v22 = *(unsigned __int16 *)&v21[(_QWORD)v20];
            v23 = *(unsigned __int16 *)v20 - v22;
            if ( v23 )
              break;
            v20 += 2;
          }
          while ( v22 );
          if ( !v23 )
          {
            if ( !i )
              goto LABEL_9;
            a1->szObjectName = *(LPWSTR *)(v5[2] + 8LL);
            a1->szCounterName = *(LPWSTR *)(i[2] + 40LL);
            return;
          }
        }
        break;
      }
      v4 = (LPVOID *)*v4;
    }
LABEL_9:
    ProcessHeap = GetProcessHeap();
    v11 = HeapAlloc(ProcessHeap, 8u, 0x208u);
    if ( v11 )
    {
      v12 = wcsstr(a2, L"\\\\");
      if ( !v12 || (v13 = wcschr(v12 + 2, 0x5Cu)) == 0 )
        v13 = a2;
      v14 = PdhTranslate009CounterW(v13, v11, &v34);
      if ( v14 == -2147481646 )
      {
        v15 = 2LL * v34;
        v16 = GetProcessHeap();
        v17 = HeapReAlloc(v16, 8u, v11, v15);
        if ( !v17 )
        {
LABEL_38:
          v33 = GetProcessHeap();
          HeapFree(v33, 0, v11);
          return;
        }
        v11 = v17;
        v14 = PdhTranslate009CounterW(v13, v17, &v34);
      }
      if ( v14 )
      {
        if ( v14 == -2147481648 )
          byte_140082278 = 1;
      }
      else
      {
        if ( v5 )
          goto LABEL_33;
        v24 = GetProcessHeap();
        v5 = HeapAlloc(v24, 8u, 0x30u);
        if ( v5 )
        {
          v25 = qword_140082268;
          *v5 = qword_140082268;
          v5[1] = &qword_140082268;
          v25[1] = v5;
          qword_140082268 = v5;
          v5[5] = v5 + 4;
          v5[4] = v5 + 4;
          v26 = ParsePdhCounterPath((LPCWSTR)v11);
          v5[2] = v26;
          if ( v26 )
          {
            v27 = ParsePdhCounterPath(a2);
            v5[3] = v27;
            if ( v27 )
            {
LABEL_33:
              v28 = GetProcessHeap();
              v29 = HeapAlloc(v28, 8u, 0x20u);
              if ( v29 )
              {
                v30 = v5[4];
                v29[1] = v5 + 4;
                *v29 = v30;
                *(_QWORD *)(v30 + 8) = v29;
                v5[4] = v29;
                v31 = ParsePdhCounterPath((LPCWSTR)v11);
                v29[2] = v31;
                if ( v31 )
                {
                  v32 = ParsePdhCounterPath(a2);
                  v29[3] = v32;
                  if ( v32 )
                  {
                    a1->szObjectName = *(LPWSTR *)(v5[2] + 8LL);
                    a1->szCounterName = *(LPWSTR *)(v29[2] + 40LL);
                  }
                }
              }
            }
          }
        }
      }
      if ( v11 )
        goto LABEL_38;
    }
  }
}

```

## disassembly

```asm
0x14001ac30  mov     [rsp+arg_0], rbx
0x14001ac35  mov     [rsp+arg_8], rbp
0x14001ac3a  push    rsi
0x14001ac3b  push    rdi
0x14001ac3c  push    r13
0x14001ac3e  push    r14
0x14001ac40  push    r15
0x14001ac42  sub     rsp, 20h
0x14001ac46  cmp     cs:byte_140082278, 0
0x14001ac4d  mov     r15, rdx
0x14001ac50  mov     r14, rcx
0x14001ac53  mov     [rsp+48h+arg_10], 104h
0x14001ac5b  jnz     loc_14001AECD
0x14001ac61  mov     r8, cs:qword_140082268
0x14001ac68  lea     r13, qword_140082268
0x14001ac6f  xor     esi, esi
0x14001ac71  jmp     short loc_14001ACA1
0x14001ac73  mov     rax, [r8+18h]
0x14001ac77  mov     r9, [r14+8]
0x14001ac7b  mov     rcx, [rax+8]
0x14001ac7f  sub     r9, rcx
0x14001ac82  movzx   eax, word ptr [rcx]
0x14001ac85  movzx   edx, word ptr [rcx+r9]
0x14001ac8a  sub     eax, edx
0x14001ac8c  jnz     short loc_14001AC96
0x14001ac8e  add     rcx, 2
0x14001ac92  test    edx, edx
0x14001ac94  jnz     short loc_14001AC82
0x14001ac96  test    eax, eax
0x14001ac98  jz      loc_14001AD6C
0x14001ac9e  mov     r8, [r8]
0x14001aca1  cmp     r13, r8
0x14001aca4  jnz     short loc_14001AC73
0x14001aca6  call    cs:__imp_GetProcessHeap
0x14001acac  mov     edx, 8; dwFlags
0x14001acb1  mov     r8d, 208h; dwBytes
0x14001acb7  mov     rcx, rax; hHeap
0x14001acba  call    cs:__imp_HeapAlloc
0x14001acc0  mov     rdi, rax
0x14001acc3  test    rax, rax
0x14001acc6  jz      loc_14001AECD
0x14001accc  lea     rdx, SubStr; "\\\\"
0x14001acd3  mov     rcx, r15; Str
0x14001acd6  call    cs:__imp_wcsstr
0x14001acdc  test    rax, rax
0x14001acdf  jz      short loc_14001ACF8
0x14001ace1  mov     edx, 5Ch ; '\'; Ch
0x14001ace6  lea     rcx, [rax+4]; Str
0x14001acea  call    cs:__imp_wcschr
0x14001acf0  mov     rbp, rax
0x14001acf3  test    rax, rax
0x14001acf6  jnz     short loc_14001ACFB
0x14001acf8  mov     rbp, r15
0x14001acfb  lea     r8, [rsp+48h+arg_10]
0x14001ad00  mov     rdx, rdi
0x14001ad03  mov     rcx, rbp
0x14001ad06  call    cs:__imp_PdhTranslate009CounterW
0x14001ad0c  cmp     eax, 800007D2h
0x14001ad11  jnz     short loc_14001AD51
0x14001ad13  mov     ebx, [rsp+48h+arg_10]
0x14001ad17  add     rbx, rbx
0x14001ad1a  call    cs:__imp_GetProcessHeap
0x14001ad20  mov     r9, rbx; dwBytes
0x14001ad23  mov     r8, rdi; lpMem
0x14001ad26  mov     rcx, rax; hHeap
0x14001ad29  mov     edx, 8; dwFlags
0x14001ad2e  call    cs:__imp_HeapReAlloc
0x14001ad34  test    rax, rax
0x14001ad37  jz      loc_14001AEB9
0x14001ad3d  lea     r8, [rsp+48h+arg_10]
0x14001ad42  mov     rdx, rax
0x14001ad45  mov     rcx, rbp
0x14001ad48  mov     rdi, rax
0x14001ad4b  call    cs:__imp_PdhTranslate009CounterW
0x14001ad51  test    eax, eax
0x14001ad53  jz      short loc_14001ADD4
0x14001ad55  cmp     eax, 800007D0h
0x14001ad5a  jnz     loc_14001AEB4
0x14001ad60  mov     cs:byte_140082278, 1
0x14001ad67  jmp     loc_14001AEB4
0x14001ad6c  mov     rsi, r8
0x14001ad6f  add     r8, 20h ; ' '
0x14001ad73  mov     rdx, [r8]
0x14001ad76  jmp     short loc_14001ADA4
0x14001ad78  mov     rax, [rdx+18h]
0x14001ad7c  mov     r10, [r14+28h]
0x14001ad80  mov     rcx, [rax+28h]
0x14001ad84  sub     r10, rcx
0x14001ad87  movzx   eax, word ptr [rcx]
0x14001ad8a  movzx   r9d, word ptr [rcx+r10]
0x14001ad8f  sub     eax, r9d
0x14001ad92  jnz     short loc_14001AD9D
0x14001ad94  add     rcx, 2
0x14001ad98  test    r9d, r9d
0x14001ad9b  jnz     short loc_14001AD87
0x14001ad9d  test    eax, eax
0x14001ad9f  jz      short loc_14001ADAE
0x14001ada1  mov     rdx, [rdx]
0x14001ada4  cmp     r8, rdx
0x14001ada7  jnz     short loc_14001AD78
0x14001ada9  jmp     loc_14001ACA6
0x14001adae  test    rdx, rdx
0x14001adb1  jz      loc_14001ACA6
0x14001adb7  mov     rax, [rsi+10h]
0x14001adbb  mov     rcx, [rax+8]
0x14001adbf  mov     [r14+8], rcx
0x14001adc3  mov     rax, [rdx+10h]
0x14001adc7  mov     rcx, [rax+28h]
0x14001adcb  mov     [r14+28h], rcx
0x14001adcf  jmp     loc_14001AECD
0x14001add4  test    rsi, rsi
0x14001add7  jnz     short loc_14001AE45
0x14001add9  call    cs:__imp_GetProcessHeap
0x14001addf  mov     rcx, rax; hHeap
0x14001ade2  lea     edx, [rsi+8]; dwFlags
0x14001ade5  lea     r8d, [rsi+30h]; dwBytes
0x14001ade9  call    cs:__imp_HeapAlloc
0x14001adef  mov     rsi, rax
0x14001adf2  test    rax, rax
0x14001adf5  jz      loc_14001AEB4
0x14001adfb  mov     rax, cs:qword_140082268
0x14001ae02  mov     rcx, rdi; szFullPathBuffer
0x14001ae05  mov     [rsi], rax
0x14001ae08  mov     [rsi+8], r13
0x14001ae0c  mov     [rax+8], rsi
0x14001ae10  lea     rax, [rsi+20h]
0x14001ae14  mov     cs:qword_140082268, rsi
0x14001ae1b  mov     [rsi+28h], rax
0x14001ae1f  mov     [rax], rax
0x14001ae22  call    ?ParsePdhCounterPath@@YAPEAU_PDH_COUNTER_PATH_ELEMENTS_W@@PEAG@Z; ParsePdhCounterPath(ushort *)
0x14001ae27  mov     [rsi+10h], rax
0x14001ae2b  test    rax, rax
0x14001ae2e  jz      loc_14001AEB4
0x14001ae34  mov     rcx, r15; szFullPathBuffer
0x14001ae37  call    ?ParsePdhCounterPath@@YAPEAU_PDH_COUNTER_PATH_ELEMENTS_W@@PEAG@Z; ParsePdhCounterPath(ushort *)
0x14001ae3c  mov     [rsi+18h], rax
0x14001ae40  test    rax, rax
0x14001ae43  jz      short loc_14001AEB4
0x14001ae45  call    cs:__imp_GetProcessHeap
0x14001ae4b  mov     edx, 8; dwFlags
0x14001ae50  mov     rcx, rax; hHeap
0x14001ae53  lea     r8d, [rdx+18h]; dwBytes
0x14001ae57  call    cs:__imp_HeapAlloc
0x14001ae5d  mov     rbx, rax
0x14001ae60  test    rax, rax
0x14001ae63  jz      short loc_14001AEB4
0x14001ae65  lea     rcx, [rsi+20h]
0x14001ae69  mov     rax, [rcx]
0x14001ae6c  mov     [rbx+8], rcx
0x14001ae70  mov     [rbx], rax
0x14001ae73  mov     [rax+8], rbx
0x14001ae77  mov     [rcx], rbx
0x14001ae7a  mov     rcx, rdi; szFullPathBuffer
0x14001ae7d  call    ?ParsePdhCounterPath@@YAPEAU_PDH_COUNTER_PATH_ELEMENTS_W@@PEAG@Z; ParsePdhCounterPath(ushort *)
0x14001ae82  mov     [rbx+10h], rax
0x14001ae86  test    rax, rax
0x14001ae89  jz      short loc_14001AEB4
0x14001ae8b  mov     rcx, r15; szFullPathBuffer
0x14001ae8e  call    ?ParsePdhCounterPath@@YAPEAU_PDH_COUNTER_PATH_ELEMENTS_W@@PEAG@Z; ParsePdhCounterPath(ushort *)
0x14001ae93  mov     [rbx+18h], rax
0x14001ae97  test    rax, rax
0x14001ae9a  jz      short loc_14001AEB4
0x14001ae9c  mov     rax, [rsi+10h]
0x14001aea0  mov     rcx, [rax+8]
0x14001aea4  mov     [r14+8], rcx
0x14001aea8  mov     rax, [rbx+10h]
0x14001aeac  mov     rcx, [rax+28h]
0x14001aeb0  mov     [r14+28h], rcx
0x14001aeb4  test    rdi, rdi
0x14001aeb7  jz      short loc_14001AECD
0x14001aeb9  call    cs:__imp_GetProcessHeap
0x14001aebf  mov     r8, rdi; lpMem
0x14001aec2  xor     edx, edx; dwFlags
0x14001aec4  mov     rcx, rax; hHeap
0x14001aec7  call    cs:__imp_HeapFree
0x14001aecd  mov     rbx, [rsp+48h+arg_0]
0x14001aed2  mov     rbp, [rsp+48h+arg_8]
0x14001aed7  add     rsp, 20h
0x14001aedb  pop     r15
0x14001aedd  pop     r14
0x14001aedf  pop     r13
0x14001aee1  pop     rdi
0x14001aee2  pop     rsi
0x14001aee3  retn
```
