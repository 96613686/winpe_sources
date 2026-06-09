# SclOpenOS

- ea: `0x18000deec`
- end: `0x18000e4dc`
- name: `SclOpenOS`
- size: `1520`
- prototype: `__int64 __fastcall(void *, wchar_t *, const wchar_t **)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800061b0`

## callees

- `0x1800014e8`
- `0x180007ac4`
- `0x180009374`
- `0x180009904`
- `0x18000a75c`
- `0x18000dae0`
- `0x18000deec`
- `0x1800153c8`
- `0x18001555c`
- `0x1800179c5`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000e07c`
- `ntdll!RtlFreeHeap` at `0x18000e09b`
- `ntdll!RtlFreeHeap` at `0x18000e0f4`
- `ntdll!RtlFreeHeap` at `0x18000e164`
- `ntdll!RtlFreeHeap` at `0x18000e183`
- `ntdll!RtlFreeHeap` at `0x18000e1dd`
- `ntdll!RtlFreeHeap` at `0x18000e24d`
- `ntdll!RtlFreeHeap` at `0x18000e26c`
- `ntdll!RtlFreeHeap` at `0x18000e2c6`
- `ntdll!RtlFreeHeap` at `0x18000e336`
- `ntdll!RtlFreeHeap` at `0x18000e355`
- `ntdll!RtlFreeHeap` at `0x18000e3b5`
- `ntdll!RtlFreeHeap` at `0x18000e419`
- `ntdll!RtlFreeHeap` at `0x18000e47b`
- `ntdll!RtlFreeHeap` at `0x18000e498`
- `ntdll!RtlFreeHeap` at `0x18000e4b5`
- `ntdll!RtlFreeHeap` at `0x18000e07c`
- `ntdll!RtlFreeHeap` at `0x18000e09b`
- `ntdll!RtlFreeHeap` at `0x18000e0f4`
- `ntdll!RtlFreeHeap` at `0x18000e164`
- `ntdll!RtlFreeHeap` at `0x18000e183`
- `ntdll!RtlFreeHeap` at `0x18000e1dd`
- `ntdll!RtlFreeHeap` at `0x18000e24d`
- `ntdll!RtlFreeHeap` at `0x18000e26c`
- `ntdll!RtlFreeHeap` at `0x18000e2c6`
- `ntdll!RtlFreeHeap` at `0x18000e336`
- `ntdll!RtlFreeHeap` at `0x18000e355`
- `ntdll!RtlFreeHeap` at `0x18000e3b5`
- `ntdll!RtlFreeHeap` at `0x18000e419`
- `ntdll!RtlFreeHeap` at `0x18000e47b`
- `ntdll!RtlFreeHeap` at `0x18000e498`
- `ntdll!RtlFreeHeap` at `0x18000e4b5`
- `ntdll!wcsrchr` at `0x18000df89`
- `ntdll!wcsrchr` at `0x18000df89`

## string_xrefs

- `0x18000e189`: `SECURITY`
- `0x18000dfe4`: `System32\config`
- `0x18000e0ab`: `System32\config`
- `0x18000e193`: `System32\config`
- `0x18000e27c`: `System32\config`
- `0x18000e365`: `System32\config`

## pseudocode

```c
__int64 __fastcall SclOpenOS(void *a1, wchar_t *a2, const wchar_t **a3)
{
  __int64 v5; // rdx
  wchar_t *v6; // r15
  PVOID v7; // r14
  WCHAR *v8; // rsi
  const wchar_t **v9; // r13
  wchar_t *v10; // rcx
  int CanonicalMountKeyPath; // edi
  wchar_t *v12; // rax
  wchar_t v13; // bx
  const wchar_t *v14; // rbx
  wchar_t *v15; // rax
  int v16; // eax
  wchar_t *v17; // rax
  int v18; // eax
  wchar_t *v19; // rax
  int v20; // eax
  wchar_t *v21; // rax
  int v22; // eax
  wchar_t *v23; // rax
  int v24; // eax
  wchar_t *v26; // [rsp+20h] [rbp-10h]
  PVOID P; // [rsp+70h] [rbp+40h] BYREF
  wchar_t *v28; // [rsp+78h] [rbp+48h]
  PVOID v29; // [rsp+88h] [rbp+58h] BYREF

  v28 = a2;
  P = a1;
  if ( !a2 || !a3 )
    return 3221225485LL;
  memset_0(a3, 0, 0x40u);
  v5 = -1;
  v29 = 0;
  v6 = 0;
  P = 0;
  v7 = 0;
  *(_DWORD *)a3 = 2;
  v8 = 0;
  do
    ++v5;
  while ( a2[v5] );
  v9 = a3 + 1;
  CanonicalMountKeyPath = SclCloneString(a2, v5, a3 + 1, 0);
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_52;
  StrRTrm(*v9);
  v12 = wcsrchr(*v9, 0x5Cu);
  v26 = v12;
  v10 = v12;
  if ( !v12 || v12 <= *v9 )
  {
    CanonicalMountKeyPath = -1073741767;
    goto LABEL_52;
  }
  v13 = v12[1];
  v12[1] = 0;
  CanonicalMountKeyPath = SclDosPathToNtPath((__int64)*v9, a3 + 2);
  v26[1] = v13;
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_52;
  v14 = v28;
  v15 = BuildPathMulti(3u, v28, L"System32\\config", L"DEFAULT");
  v6 = v15;
  if ( !v15 )
    goto LABEL_36;
  CanonicalMountKeyPath = SclRegGetCanonicalMountKeyPath(v15, &P);
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_44;
  v16 = SclDosPathToNtPath((__int64)v6, &v29);
  v7 = v29;
  CanonicalMountKeyPath = v16;
  v8 = (WCHAR *)P;
  if ( v16 < 0 )
    goto LABEL_45;
  LOBYTE(v10) = 1;
  CanonicalMountKeyPath = SclRegLoadUnloadHive(v10, P, v29);
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_45;
  CanonicalMountKeyPath = SclCreateKey(0, v8, 0xF003Fu, (__int64)(a3 + 3));
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_45;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  P = 0;
  v8 = 0;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  v17 = BuildPathMulti(3u, v14, L"System32\\config", L"SAM");
  v6 = v17;
  if ( !v17 )
    goto LABEL_36;
  CanonicalMountKeyPath = SclRegGetCanonicalMountKeyPath(v17, &P);
  if ( CanonicalMountKeyPath < 0 )
  {
LABEL_44:
    v8 = (WCHAR *)P;
    goto LABEL_45;
  }
  if ( v7 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    v29 = 0;
  }
  v18 = SclDosPathToNtPath((__int64)v6, &v29);
  v7 = v29;
  CanonicalMountKeyPath = v18;
  v8 = (WCHAR *)P;
  if ( v18 < 0
    || (LOBYTE(v10) = 1, CanonicalMountKeyPath = SclRegLoadUnloadHive(v10, P, v29), CanonicalMountKeyPath < 0)
    || (CanonicalMountKeyPath = SclCreateKey(0, v8, 0xF003Fu, (__int64)(a3 + 4)), CanonicalMountKeyPath < 0) )
  {
LABEL_45:
    if ( v8 )
    {
      if ( CanonicalMountKeyPath < 0 )
      {
        SclRegLoadUnloadHive(0, v8, 0);
        goto LABEL_52;
      }
      CanonicalMountKeyPath = SclRegLoadUnloadHive(0, v8, 0);
    }
    if ( CanonicalMountKeyPath >= 0 )
    {
      CanonicalMountKeyPath = SclCloseOS(v10, a3);
      goto LABEL_53;
    }
LABEL_52:
    SclCloseOS(v10, a3);
    goto LABEL_53;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  P = 0;
  v8 = 0;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  v19 = BuildPathMulti(3u, v14, L"System32\\config", L"SECURITY");
  v6 = v19;
  if ( !v19 )
  {
LABEL_36:
    CanonicalMountKeyPath = -1073741801;
    goto LABEL_52;
  }
  CanonicalMountKeyPath = SclRegGetCanonicalMountKeyPath(v19, &P);
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_44;
  if ( v7 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    v29 = 0;
  }
  v20 = SclDosPathToNtPath((__int64)v6, &v29);
  v7 = v29;
  CanonicalMountKeyPath = v20;
  v8 = (WCHAR *)P;
  if ( v20 < 0 )
    goto LABEL_45;
  LOBYTE(v10) = 1;
  CanonicalMountKeyPath = SclRegLoadUnloadHive(v10, P, v29);
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_45;
  CanonicalMountKeyPath = SclCreateKey(0, v8, 0xF003Fu, (__int64)(a3 + 5));
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_45;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  P = 0;
  v8 = 0;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  v21 = BuildPathMulti(3u, v14, L"System32\\config", L"SOFTWARE");
  v6 = v21;
  if ( !v21 )
    goto LABEL_36;
  CanonicalMountKeyPath = SclRegGetCanonicalMountKeyPath(v21, &P);
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_44;
  if ( v7 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    v29 = 0;
  }
  v22 = SclDosPathToNtPath((__int64)v6, &v29);
  v7 = v29;
  CanonicalMountKeyPath = v22;
  v8 = (WCHAR *)P;
  if ( v22 < 0 )
    goto LABEL_45;
  LOBYTE(v10) = 1;
  CanonicalMountKeyPath = SclRegLoadUnloadHive(v10, P, v29);
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_45;
  CanonicalMountKeyPath = SclCreateKey(0, v8, 0xF003Fu, (__int64)(a3 + 6));
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_45;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  P = 0;
  v8 = 0;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  v23 = BuildPathMulti(3u, v14, L"System32\\config", L"SYSTEM");
  v6 = v23;
  if ( !v23 )
    goto LABEL_36;
  CanonicalMountKeyPath = SclRegGetCanonicalMountKeyPath(v23, &P);
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_44;
  if ( v7 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    v29 = 0;
  }
  v24 = SclDosPathToNtPath((__int64)v6, &v29);
  v7 = v29;
  CanonicalMountKeyPath = v24;
  v8 = (WCHAR *)P;
  if ( v24 < 0 )
    goto LABEL_45;
  LOBYTE(v10) = 1;
  CanonicalMountKeyPath = SclRegLoadUnloadHive(v10, P, v29);
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_45;
  CanonicalMountKeyPath = SclCreateKey(0, v8, 0xF003Fu, (__int64)(a3 + 7));
  if ( CanonicalMountKeyPath < 0 )
    goto LABEL_45;
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  v8 = 0;
LABEL_53:
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( v8 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  return (unsigned int)CanonicalMountKeyPath;
}

```

## disassembly

```asm
0x18000deec  mov     [rsp-38h+arg_10], rbx
0x18000def1  mov     [rsp-38h+arg_8], rdx
0x18000def6  mov     [rsp-38h+P], rcx
0x18000defb  push    rbp
0x18000defc  push    rsi
0x18000defd  push    rdi
0x18000defe  push    r12
0x18000df00  push    r13
0x18000df02  push    r14
0x18000df04  push    r15
0x18000df06  mov     rbp, rsp
0x18000df09  sub     rsp, 30h
0x18000df0d  xor     edi, edi
0x18000df0f  mov     r12, r8
0x18000df12  mov     rbx, rdx
0x18000df15  test    rdx, rdx
0x18000df18  jz      loc_18000E4BF
0x18000df1e  test    r8, r8
0x18000df21  jz      loc_18000E4BF
0x18000df27  xor     edx, edx; Val
0x18000df29  lea     r8d, [rdi+40h]; Size
0x18000df2d  mov     rcx, r12; void *
0x18000df30  call    memset_0
0x18000df35  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000df39  mov     [rbp+arg_18], rdi
0x18000df3d  mov     r15d, edi
0x18000df40  mov     [rbp+P], rdi
0x18000df44  mov     r14d, edi
0x18000df47  mov     dword ptr [r12], 2
0x18000df4f  mov     esi, edi
0x18000df51  inc     rdx
0x18000df54  cmp     [rbx+rdx*2], di
0x18000df58  jnz     short loc_18000DF51
0x18000df5a  lea     r13, [r12+8]
0x18000df5f  xor     r9d, r9d
0x18000df62  mov     r8, r13
0x18000df65  mov     rcx, rbx
0x18000df68  call    SclCloneString
0x18000df6d  mov     edi, eax
0x18000df6f  test    eax, eax
0x18000df71  js      loc_18000E45C
0x18000df77  mov     rcx, [r13+0]
0x18000df7b  call    StrRTrm
0x18000df80  mov     rcx, [r13+0]; Str
0x18000df84  mov     edx, 5Ch ; '\'; Ch
0x18000df89  call    cs:__imp_wcsrchr
0x18000df8f  mov     [rbp+var_10], rax
0x18000df93  mov     rcx, rax
0x18000df96  test    rax, rax
0x18000df99  jz      loc_18000E457
0x18000df9f  cmp     rax, [r13+0]
0x18000dfa3  jbe     loc_18000E457
0x18000dfa9  movzx   ebx, word ptr [rax+2]
0x18000dfad  lea     rdx, [r12+10h]
0x18000dfb2  xor     eax, eax
0x18000dfb4  mov     [rcx+2], ax
0x18000dfb8  mov     rcx, [r13+0]
0x18000dfbc  call    SclDosPathToNtPath
0x18000dfc1  mov     edi, eax
0x18000dfc3  xor     r13d, r13d
0x18000dfc6  mov     rax, [rbp+var_10]
0x18000dfca  mov     [rax+2], bx
0x18000dfce  test    edi, edi
0x18000dfd0  js      loc_18000E45C
0x18000dfd6  mov     rbx, [rbp+arg_8]
0x18000dfda  lea     r9, aDefault_0; "DEFAULT"
0x18000dfe1  mov     rdx, rbx
0x18000dfe4  lea     r8, aSystem32Config; "System32\\config"
0x18000dfeb  lea     ecx, [r13+3]
0x18000dfef  call    BuildPathMulti
0x18000dff4  mov     r15, rax
0x18000dff7  test    rax, rax
0x18000dffa  jz      loc_18000E37E
0x18000e000  lea     rdx, [rbp+P]
0x18000e004  mov     rcx, rax
0x18000e007  call    SclRegGetCanonicalMountKeyPath
0x18000e00c  mov     edi, eax
0x18000e00e  test    eax, eax
0x18000e010  js      loc_18000E424
0x18000e016  lea     rdx, [rbp+arg_18]
0x18000e01a  mov     rcx, r15
0x18000e01d  call    SclDosPathToNtPath
0x18000e022  mov     r14, [rbp+arg_18]
0x18000e026  mov     edi, eax
0x18000e028  mov     rsi, [rbp+P]
0x18000e02c  test    eax, eax
0x18000e02e  js      loc_18000E428
0x18000e034  mov     r8, r14
0x18000e037  mov     rdx, rsi
0x18000e03a  mov     cl, 1
0x18000e03c  call    SclRegLoadUnloadHive
0x18000e041  mov     edi, eax
0x18000e043  test    eax, eax
0x18000e045  js      loc_18000E428
0x18000e04b  lea     r9, [r12+18h]
0x18000e050  mov     r8d, 0F003Fh
0x18000e056  mov     rdx, rsi
0x18000e059  xor     ecx, ecx
0x18000e05b  call    SclCreateKey
0x18000e060  mov     edi, eax
0x18000e062  test    eax, eax
0x18000e064  js      loc_18000E428
0x18000e06a  mov     rcx, gs:60h
0x18000e073  mov     r8, rsi; P
0x18000e076  xor     edx, edx; Flags
0x18000e078  mov     rcx, [rcx+30h]; HeapHandle
0x18000e07c  call    cs:__imp_RtlFreeHeap
0x18000e082  mov     rcx, gs:60h
0x18000e08b  mov     r8, r15; P
0x18000e08e  xor     edx, edx; Flags
0x18000e090  mov     [rbp+P], r13
0x18000e094  mov     esi, r13d
0x18000e097  mov     rcx, [rcx+30h]; HeapHandle
0x18000e09b  call    cs:__imp_RtlFreeHeap
0x18000e0a1  lea     r9, aSam; "SAM"
0x18000e0a8  mov     rdx, rbx
0x18000e0ab  lea     r8, aSystem32Config; "System32\\config"
0x18000e0b2  lea     ecx, [r13+3]
0x18000e0b6  call    BuildPathMulti
0x18000e0bb  mov     r15, rax
0x18000e0be  test    rax, rax
0x18000e0c1  jz      loc_18000E37E
0x18000e0c7  lea     rdx, [rbp+P]
0x18000e0cb  mov     rcx, rax
0x18000e0ce  call    SclRegGetCanonicalMountKeyPath
0x18000e0d3  mov     edi, eax
0x18000e0d5  test    eax, eax
0x18000e0d7  js      loc_18000E424
0x18000e0dd  test    r14, r14
0x18000e0e0  jz      short loc_18000E0FE
0x18000e0e2  mov     rcx, gs:60h
0x18000e0eb  mov     r8, r14; P
0x18000e0ee  xor     edx, edx; Flags
0x18000e0f0  mov     rcx, [rcx+30h]; HeapHandle
0x18000e0f4  call    cs:__imp_RtlFreeHeap
0x18000e0fa  mov     [rbp+arg_18], r13
0x18000e0fe  lea     rdx, [rbp+arg_18]
0x18000e102  mov     rcx, r15
0x18000e105  call    SclDosPathToNtPath
0x18000e10a  mov     r14, [rbp+arg_18]
0x18000e10e  mov     edi, eax
0x18000e110  mov     rsi, [rbp+P]
0x18000e114  test    eax, eax
0x18000e116  js      loc_18000E428
0x18000e11c  mov     r8, r14
0x18000e11f  mov     rdx, rsi
0x18000e122  mov     cl, 1
0x18000e124  call    SclRegLoadUnloadHive
0x18000e129  mov     edi, eax
0x18000e12b  test    eax, eax
0x18000e12d  js      loc_18000E428
0x18000e133  lea     r9, [r12+20h]
0x18000e138  mov     r8d, 0F003Fh
0x18000e13e  mov     rdx, rsi
0x18000e141  xor     ecx, ecx
0x18000e143  call    SclCreateKey
0x18000e148  mov     edi, eax
0x18000e14a  test    eax, eax
0x18000e14c  js      loc_18000E428
0x18000e152  mov     rcx, gs:60h
0x18000e15b  mov     r8, rsi; P
0x18000e15e  xor     edx, edx; Flags
0x18000e160  mov     rcx, [rcx+30h]; HeapHandle
0x18000e164  call    cs:__imp_RtlFreeHeap
0x18000e16a  mov     rcx, gs:60h
0x18000e173  mov     r8, r15; P
0x18000e176  xor     edx, edx; Flags
0x18000e178  mov     [rbp+P], r13
0x18000e17c  mov     rsi, r13
0x18000e17f  mov     rcx, [rcx+30h]; HeapHandle
0x18000e183  call    cs:__imp_RtlFreeHeap
0x18000e189  lea     r9, aSecurity; "SECURITY"
0x18000e190  mov     rdx, rbx
0x18000e193  lea     r8, aSystem32Config; "System32\\config"
0x18000e19a  mov     ecx, 3
0x18000e19f  call    BuildPathMulti
0x18000e1a4  mov     r15, rax
0x18000e1a7  test    rax, rax
0x18000e1aa  jz      loc_18000E37E
0x18000e1b0  lea     rdx, [rbp+P]
0x18000e1b4  mov     rcx, rax
0x18000e1b7  call    SclRegGetCanonicalMountKeyPath
0x18000e1bc  mov     edi, eax
0x18000e1be  test    eax, eax
0x18000e1c0  js      loc_18000E424
0x18000e1c6  test    r14, r14
0x18000e1c9  jz      short loc_18000E1E7
0x18000e1cb  mov     rcx, gs:60h
0x18000e1d4  mov     r8, r14; P
0x18000e1d7  xor     edx, edx; Flags
0x18000e1d9  mov     rcx, [rcx+30h]; HeapHandle
0x18000e1dd  call    cs:__imp_RtlFreeHeap
0x18000e1e3  mov     [rbp+arg_18], r13
0x18000e1e7  lea     rdx, [rbp+arg_18]
0x18000e1eb  mov     rcx, r15
0x18000e1ee  call    SclDosPathToNtPath
0x18000e1f3  mov     r14, [rbp+arg_18]
0x18000e1f7  mov     edi, eax
0x18000e1f9  mov     rsi, [rbp+P]
0x18000e1fd  test    eax, eax
0x18000e1ff  js      loc_18000E428
0x18000e205  mov     r8, r14
0x18000e208  mov     rdx, rsi
0x18000e20b  mov     cl, 1
0x18000e20d  call    SclRegLoadUnloadHive
0x18000e212  mov     edi, eax
0x18000e214  test    eax, eax
0x18000e216  js      loc_18000E428
0x18000e21c  lea     r9, [r12+28h]
0x18000e221  mov     r8d, 0F003Fh
0x18000e227  mov     rdx, rsi
0x18000e22a  xor     ecx, ecx
0x18000e22c  call    SclCreateKey
0x18000e231  mov     edi, eax
0x18000e233  test    eax, eax
0x18000e235  js      loc_18000E428
0x18000e23b  mov     rcx, gs:60h
0x18000e244  mov     r8, rsi; P
0x18000e247  xor     edx, edx; Flags
0x18000e249  mov     rcx, [rcx+30h]; HeapHandle
0x18000e24d  call    cs:__imp_RtlFreeHeap
0x18000e253  mov     rcx, gs:60h
0x18000e25c  mov     r8, r15; P
0x18000e25f  xor     edx, edx; Flags
0x18000e261  mov     [rbp+P], r13
0x18000e265  mov     rsi, r13
0x18000e268  mov     rcx, [rcx+30h]; HeapHandle
0x18000e26c  call    cs:__imp_RtlFreeHeap
0x18000e272  lea     r9, aSoftware; "SOFTWARE"
0x18000e279  mov     rdx, rbx
0x18000e27c  lea     r8, aSystem32Config; "System32\\config"
0x18000e283  mov     ecx, 3
0x18000e288  call    BuildPathMulti
0x18000e28d  mov     r15, rax
0x18000e290  test    rax, rax
0x18000e293  jz      loc_18000E37E
0x18000e299  lea     rdx, [rbp+P]
0x18000e29d  mov     rcx, rax
0x18000e2a0  call    SclRegGetCanonicalMountKeyPath
0x18000e2a5  mov     edi, eax
0x18000e2a7  test    eax, eax
0x18000e2a9  js      loc_18000E424
0x18000e2af  test    r14, r14
0x18000e2b2  jz      short loc_18000E2D0
0x18000e2b4  mov     rcx, gs:60h
0x18000e2bd  mov     r8, r14; P
0x18000e2c0  xor     edx, edx; Flags
0x18000e2c2  mov     rcx, [rcx+30h]; HeapHandle
0x18000e2c6  call    cs:__imp_RtlFreeHeap
0x18000e2cc  mov     [rbp+arg_18], r13
0x18000e2d0  lea     rdx, [rbp+arg_18]
0x18000e2d4  mov     rcx, r15
0x18000e2d7  call    SclDosPathToNtPath
0x18000e2dc  mov     r14, [rbp+arg_18]
0x18000e2e0  mov     edi, eax
0x18000e2e2  mov     rsi, [rbp+P]
0x18000e2e6  test    eax, eax
0x18000e2e8  js      loc_18000E428
0x18000e2ee  mov     r8, r14
0x18000e2f1  mov     rdx, rsi
0x18000e2f4  mov     cl, 1
0x18000e2f6  call    SclRegLoadUnloadHive
0x18000e2fb  mov     edi, eax
0x18000e2fd  test    eax, eax
0x18000e2ff  js      loc_18000E428
0x18000e305  lea     r9, [r12+30h]
0x18000e30a  mov     r8d, 0F003Fh
0x18000e310  mov     rdx, rsi
0x18000e313  xor     ecx, ecx
0x18000e315  call    SclCreateKey
0x18000e31a  mov     edi, eax
0x18000e31c  test    eax, eax
0x18000e31e  js      loc_18000E428
0x18000e324  mov     rcx, gs:60h
0x18000e32d  mov     r8, rsi; P
0x18000e330  xor     edx, edx; Flags
0x18000e332  mov     rcx, [rcx+30h]; HeapHandle
0x18000e336  call    cs:__imp_RtlFreeHeap
0x18000e33c  mov     rcx, gs:60h
0x18000e345  mov     r8, r15; P
0x18000e348  xor     edx, edx; Flags
0x18000e34a  mov     [rbp+P], r13
0x18000e34e  mov     rsi, r13
0x18000e351  mov     rcx, [rcx+30h]; HeapHandle
0x18000e355  call    cs:__imp_RtlFreeHeap
0x18000e35b  lea     r9, aSystem; "SYSTEM"
0x18000e362  mov     rdx, rbx
0x18000e365  lea     r8, aSystem32Config; "System32\\config"
0x18000e36c  mov     ecx, 3
0x18000e371  call    BuildPathMulti
0x18000e376  mov     r15, rax
0x18000e379  test    rax, rax
0x18000e37c  jnz     short loc_18000E388
0x18000e37e  mov     edi, 0C0000017h
0x18000e383  jmp     loc_18000E45C
0x18000e388  lea     rdx, [rbp+P]
0x18000e38c  mov     rcx, r15
0x18000e38f  call    SclRegGetCanonicalMountKeyPath
0x18000e394  mov     edi, eax
0x18000e396  test    eax, eax
  ... truncated ...
```
