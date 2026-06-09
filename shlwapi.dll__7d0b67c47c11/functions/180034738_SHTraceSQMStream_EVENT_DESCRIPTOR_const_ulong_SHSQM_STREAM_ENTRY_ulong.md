# SHTraceSQMStream(_EVENT_DESCRIPTOR const *,ulong,_SHSQM_STREAM_ENTRY *,ulong)

- ea: `0x180034738`
- end: `0x180034945`
- name: `?SHTraceSQMStream@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_SHSQM_STREAM_ENTRY@@K@Z`
- size: `525`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, unsigned int, struct _SHSQM_STREAM_ENTRY *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034bd0`

## callees

- `0x180012550`
- `0x180013066`
- `0x180034738`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180034920`
- `ntdll!EtwEventWrite` at `0x180034920`
- `ntdll!EtwEventEnabled` at `0x180034782`
- `ntdll!EtwEventEnabled` at `0x180034782`

## pseudocode

```c
void __fastcall SHTraceSQMStream(const struct _EVENT_DESCRIPTOR *a1, __int64 a2, struct _SHSQM_STREAM_ENTRY *a3)
{
  unsigned int v4; // esi
  unsigned int v5; // r8d
  int v6; // r9d
  int *v7; // rax
  int v8; // r11d
  int *v9; // rdx
  int *v10; // rbx
  int *v11; // rax
  __int64 v12; // rdx
  int *v13; // r10
  __int64 v14; // rcx
  unsigned int v15; // ecx
  __int64 v16; // rcx
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+28h] [rbp-D8h] BYREF
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  int v21; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+3Ch] [rbp-C4h] BYREF
  GUID *v23; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v24[61]; // [rsp+48h] [rbp-B8h] BYREF

  v17 = 2;
  v18 = 922;
  if ( (unsigned __int8)EtwEventEnabled(
                          Microsoft_Windows_Shell_Core_Provider_Context,
                          ShellTraceId_Shlwapi_SHRegisterValidateTemplate) )
  {
    memset_0(v24, 0, sizeof(v24));
    v4 = v17;
    v23 = &g_SHSqmGlobalSession;
    v5 = 0;
    v21 = 11;
    v24[1] = &v18;
    v24[3] = &v21;
    v24[5] = &v17;
    v22 = 0;
    v20 = 0;
    v19 = 48;
    v24[0] = 16;
    v24[2] = 4;
    v24[4] = 4;
    v24[6] = 4;
    do
    {
      v6 = 3 * v5;
      v24[6 * v5 + 8] = 4;
      if ( v5 >= v4 )
      {
        v24[2 * (unsigned int)(v6 + 4) - 1] = &v22;
        v14 = 2LL * (unsigned int)(v6 + 5);
        v12 = -1;
        v24[v14 - 1] = &v20;
        v24[v14] = 4;
        do
          ++v12;
        while ( *((_WORD *)&v19 + v12) );
        v13 = &v19;
      }
      else
      {
        v7 = (int *)((char *)a3 + 132 * v5);
        v24[2 * (unsigned int)(v6 + 4) - 1] = v7;
        v8 = *v7;
        v9 = v7 + 1;
        if ( *v7 != 1 )
          v9 = &v20;
        v10 = v7 + 1;
        v11 = &v19;
        if ( v8 == 2 )
          v11 = v10;
        v24[2 * (unsigned int)(v6 + 5) - 1] = v9;
        v12 = -1;
        v24[2 * (unsigned int)(v6 + 5)] = 4;
        do
          ++v12;
        while ( *((_WORD *)v11 + v12) );
        v13 = &v19;
        if ( v8 == 2 )
          v13 = v10;
      }
      v15 = v5++;
      v16 = 2LL * (2 * v15 + 6 + v15);
      v24[v16 - 1] = v13;
      v24[v16] = (unsigned int)(2 * v12 + 2);
    }
    while ( v5 < 9 );
    EtwEventWrite(
      Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_Shlwapi_SHRegisterValidateTemplate,
      31,
      &v23);
  }
}

```

## disassembly

```asm
0x180034738  push    rbp
0x18003473a  push    rbx
0x18003473b  push    rsi
0x18003473c  push    rdi
0x18003473d  push    r14
0x18003473f  push    r15
0x180034741  lea     rbp, [rsp-148h]
0x180034749  sub     rsp, 248h
0x180034750  mov     rax, cs:__security_cookie
0x180034757  xor     rax, rsp
0x18003475a  mov     [rbp+170h+var_40], rax
0x180034761  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context
0x180034768  lea     rdx, ShellTraceId_Shlwapi_SHRegisterValidateTemplate
0x18003476f  mov     rdi, r8
0x180034772  mov     [rsp+270h+var_250], 2
0x18003477a  mov     [rsp+270h+var_248], 39Ah
0x180034782  call    cs:__imp_EtwEventEnabled
0x180034788  xor     r14d, r14d
0x18003478b  test    al, al
0x18003478d  jz      loc_180034926
0x180034793  xor     edx, edx; Val
0x180034795  lea     rcx, [rsp+270h+var_228]; void *
0x18003479a  mov     r8d, 1E8h; Size
0x1800347a0  call    memset_0
0x1800347a5  mov     esi, [rsp+270h+var_250]
0x1800347a9  lea     rax, ?g_SHSqmGlobalSession@@3U_GUID@@B; _GUID const g_SHSqmGlobalSession
0x1800347b0  mov     [rsp+270h+var_230], rax
0x1800347b5  mov     r8d, r14d
0x1800347b8  lea     rax, [rsp+270h+var_248]
0x1800347bd  mov     [rsp+270h+var_238], 0Bh
0x1800347c5  mov     [rsp+270h+var_220], rax
0x1800347ca  lea     rax, [rsp+270h+var_238]
0x1800347cf  mov     [rsp+270h+var_210], rax
0x1800347d4  lea     rax, [rsp+270h+var_250]
0x1800347d9  mov     [rsp+270h+var_200], rax
0x1800347de  mov     [rsp+270h+var_234], r14d
0x1800347e3  mov     [rsp+270h+var_23C], r14d
0x1800347e8  mov     [rsp+270h+var_240], 30h ; '0'
0x1800347f0  mov     [rsp+270h+var_228], 10h
0x1800347f9  mov     [rsp+270h+var_218], 4
0x180034802  mov     [rsp+270h+var_208], 4
0x18003480b  mov     [rsp+270h+var_1F8], 4
0x180034814  lea     r9d, [r8+r8*2]
0x180034818  lea     edx, [r9+4]
0x18003481c  add     rdx, rdx
0x18003481f  mov     [rsp+rdx*8+270h+var_228], 4
0x180034828  cmp     r8d, esi
0x18003482b  jnb     short loc_180034894
0x18003482d  mov     eax, r8d
0x180034830  imul    rax, 84h
0x180034837  add     rax, rdi
0x18003483a  mov     [rsp+rdx*8+270h+var_230], rax
0x18003483f  mov     r11d, [rax]
0x180034842  lea     rdx, [rax+4]
0x180034846  cmp     r11d, 1
0x18003484a  jz      short loc_180034851
0x18003484c  lea     rdx, [rsp+270h+var_23C]
0x180034851  lea     rbx, [rax+4]
0x180034855  lea     ecx, [r9+5]
0x180034859  add     rcx, rcx
0x18003485c  lea     rax, [rsp+270h+var_240]
0x180034861  cmp     r11d, 2
0x180034865  cmovz   rax, rbx
0x180034869  mov     [rsp+rcx*8+270h+var_230], rdx
0x18003486e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180034872  mov     [rsp+rcx*8+270h+var_228], 4
0x18003487b  inc     rdx
0x18003487e  cmp     [rax+rdx*2], r14w
0x180034883  jnz     short loc_18003487B
0x180034885  cmp     r11d, 2
0x180034889  lea     r10, [rsp+270h+var_240]
0x18003488e  cmovz   r10, rbx
0x180034892  jmp     short loc_1800348D0
0x180034894  lea     rax, [rsp+270h+var_234]
0x180034899  mov     [rsp+rdx*8+270h+var_230], rax
0x18003489e  lea     ecx, [r9+5]
0x1800348a2  add     rcx, rcx
0x1800348a5  lea     rax, [rsp+270h+var_23C]
0x1800348aa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800348ae  mov     [rsp+rcx*8+270h+var_230], rax
0x1800348b3  lea     rax, [rsp+270h+var_240]
0x1800348b8  mov     [rsp+rcx*8+270h+var_228], 4
0x1800348c1  inc     rdx
0x1800348c4  cmp     [rax+rdx*2], r14w
0x1800348c9  jnz     short loc_1800348C1
0x1800348cb  lea     r10, [rsp+270h+var_240]
0x1800348d0  mov     ecx, r8d
0x1800348d3  lea     r9, [rsp+270h+var_230]
0x1800348d8  mov     eax, 6
0x1800348dd  inc     r8d
0x1800348e0  lea     eax, [rax+rcx*2]
0x1800348e3  add     ecx, eax
0x1800348e5  lea     eax, ds:2[rdx*2]
0x1800348ec  add     rcx, rcx
0x1800348ef  mov     [r9+rcx*8], r10
0x1800348f3  mov     [r9+rcx*8+8], eax
0x1800348f8  mov     [r9+rcx*8+0Ch], r14d
0x1800348fd  cmp     r8d, 9
0x180034901  jb      loc_180034814
0x180034907  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context
0x18003490e  lea     r9, [rsp+270h+var_230]
0x180034913  mov     r8d, 1Fh
0x180034919  lea     rdx, ShellTraceId_Shlwapi_SHRegisterValidateTemplate
0x180034920  call    cs:__imp_EtwEventWrite
0x180034926  mov     rcx, [rbp+170h+var_40]
0x18003492d  xor     rcx, rsp; StackCookie
0x180034930  call    __security_check_cookie
0x180034935  add     rsp, 248h
0x18003493c  pop     r15
0x18003493e  pop     r14
0x180034940  pop     rdi
0x180034941  pop     rsi
0x180034942  pop     rbx
0x180034943  pop     rbp
0x180034944  retn
```
