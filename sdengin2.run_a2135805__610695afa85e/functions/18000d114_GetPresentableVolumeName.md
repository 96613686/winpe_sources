# GetPresentableVolumeName

- ea: `0x18000d114`
- end: `0x18000d31a`
- name: `GetPresentableVolumeName`
- size: `518`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000bc28`

## callees

- `0x180008370`
- `0x180009d44`
- `0x18000d114`
- `0x180072e08`
- `0x180072f14`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d1e4`
- `KERNEL32!GetLastError` at `0x18000d1e4`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18000d1d4`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x18000d1d4`
- `ole32!CoTaskMemFree` at `0x18000d2e6`
- `ole32!CoTaskMemFree` at `0x18000d2e6`
- `ole32!CoTaskMemRealloc` at `0x18000d1a5`
- `ole32!CoTaskMemRealloc` at `0x18000d1a5`

## pseudocode

```c
__int64 __fastcall GetPresentableVolumeName(LPCWSTR lpszVolumeName, unsigned __int16 *a2, DWORD a3)
{
  WCHAR *v5; // rbx
  __int16 v6; // ax
  DWORD v7; // eax
  WCHAR *v8; // rax
  signed int LastError; // eax
  WCHAR *v10; // r8
  const unsigned __int16 *v11; // rsi
  __int64 v12; // r9
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rax
  unsigned int v15; // ebx
  int v17; // [rsp+20h] [rbp-40h] BYREF
  __int16 v18; // [rsp+24h] [rbp-3Ch]
  __int16 v19; // [rsp+26h] [rbp-3Ah]
  DWORD cchBufferLength; // [rsp+A0h] [rbp+40h] BYREF

  cchBufferLength = a3;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "GetPresentableVolumeName", 0x873u, 1u);
  v5 = 0;
  cchBufferLength = 0;
  v6 = 2174;
  if ( !lpszVolumeName )
    goto LABEL_31;
  v18 = 2174;
  if ( !a2 )
  {
    v6 = 2175;
LABEL_31:
    v17 = -2147024809;
    goto LABEL_32;
  }
  v17 = 0;
  v18 = 2176;
  *a2 = 0;
  v7 = 261;
  for ( cchBufferLength = 261; ; v7 = cchBufferLength )
  {
    v8 = (WCHAR *)CoTaskMemRealloc(v5, 2LL * v7);
    v5 = v8;
    if ( !v8 )
    {
      v17 = -2147024882;
      v19 = 2187;
      goto LABEL_33;
    }
    v17 = 0;
    v18 = 2187;
    if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v8, cchBufferLength, &cchBufferLength) )
      break;
    LastError = GetLastError();
    if ( LastError == 122 || LastError == 234 )
    {
      LastError = 0;
    }
    else if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
    }
    v17 = LastError;
    if ( LastError < 0 )
    {
      v19 = 2197;
      goto LABEL_33;
    }
    v18 = 2197;
  }
  v10 = v5;
  v11 = v5;
  v12 = 0xFFFFFFFFLL;
  while ( *v10 )
  {
    if ( v10 >= &v5[cchBufferLength] )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids, v12);
      break;
    }
    v13 = -1;
    do
      ++v13;
    while ( v10[v13] );
    v14 = v10;
    if ( (unsigned int)v13 >= (unsigned int)v12 )
      v14 = v11;
    v11 = v14;
    v10 += (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= (unsigned int)v12 )
      LODWORD(v13) = v12;
    v12 = (unsigned int)v13;
  }
  v17 = StringCchCopyW(a2, 0x104u, v11);
  v6 = 2229;
  if ( v17 >= 0 )
  {
    v18 = 2229;
    goto LABEL_33;
  }
LABEL_32:
  v19 = v6;
LABEL_33:
  CoTaskMemFree(v5);
  v15 = v17;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return v15;
}

```

## disassembly

```asm
0x18000d114  mov     [rsp-28h+arg_0], rbx
0x18000d119  mov     [rsp-28h+arg_8], rsi
0x18000d11e  mov     [rsp-28h+cchBufferLength], r8d
0x18000d123  push    rbp
0x18000d124  push    rdi
0x18000d125  push    r12
0x18000d127  push    r14
0x18000d129  push    r15
0x18000d12b  mov     rbp, rsp
0x18000d12e  sub     rsp, 60h
0x18000d132  mov     rdi, rdx
0x18000d135  mov     rsi, rcx
0x18000d138  mov     r9d, 1; unsigned __int16
0x18000d13e  mov     r8d, 873h; unsigned __int16
0x18000d144  lea     rdx, aGetpresentable; "GetPresentableVolumeName"
0x18000d14b  lea     rcx, [rbp+var_40]; this
0x18000d14f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000d154  xor     r14d, r14d
0x18000d157  mov     ebx, r14d
0x18000d15a  mov     [rbp+cchBufferLength], r14d
0x18000d15e  mov     eax, 87Eh
0x18000d163  test    rsi, rsi
0x18000d166  jz      loc_18000D2D8
0x18000d16c  mov     [rbp+var_3C], ax
0x18000d170  test    rdi, rdi
0x18000d173  jz      loc_18000D2D3
0x18000d179  mov     [rbp+var_40], r14d
0x18000d17d  mov     eax, 880h
0x18000d182  mov     [rbp+var_3C], ax
0x18000d186  mov     [rdi], r14w
0x18000d18a  mov     eax, 105h
0x18000d18f  mov     [rbp+cchBufferLength], eax
0x18000d192  mov     r12d, 88Bh
0x18000d198  lea     r15d, [r12+0Ah]
0x18000d19d  mov     edx, eax
0x18000d19f  add     rdx, rdx; cb
0x18000d1a2  mov     rcx, rbx; pv
0x18000d1a5  call    cs:__imp_CoTaskMemRealloc
0x18000d1ac  nop     dword ptr [rax+rax+00h]
0x18000d1b1  mov     rbx, rax
0x18000d1b4  test    rax, rax
0x18000d1b7  jz      loc_18000D2C5
0x18000d1bd  mov     [rbp+var_40], r14d
0x18000d1c1  mov     [rbp+var_3C], r12w
0x18000d1c6  lea     r9, [rbp+cchBufferLength]; lpcchReturnLength
0x18000d1ca  mov     r8d, [rbp+cchBufferLength]; cchBufferLength
0x18000d1ce  mov     rdx, rax; lpszVolumePathNames
0x18000d1d1  mov     rcx, rsi; lpszVolumeName
0x18000d1d4  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18000d1db  nop     dword ptr [rax+rax+00h]
0x18000d1e0  test    eax, eax
0x18000d1e2  jnz     short loc_18000D22B
0x18000d1e4  call    cs:__imp_GetLastError
0x18000d1eb  nop     dword ptr [rax+rax+00h]
0x18000d1f0  cmp     eax, 7Ah ; 'z'
0x18000d1f3  jz      short loc_18000D20A
0x18000d1f5  cmp     eax, 0EAh
0x18000d1fa  jz      short loc_18000D20A
0x18000d1fc  test    eax, eax
0x18000d1fe  jle     short loc_18000D20D
0x18000d200  movzx   eax, ax
0x18000d203  or      eax, 80070000h
0x18000d208  jmp     short loc_18000D20D
0x18000d20a  mov     eax, r14d
0x18000d20d  mov     [rbp+var_40], eax
0x18000d210  test    eax, eax
0x18000d212  js      short loc_18000D221
0x18000d214  mov     [rbp+var_3C], r15w
0x18000d219  mov     eax, [rbp+cchBufferLength]
0x18000d21c  jmp     loc_18000D19D
0x18000d221  mov     [rbp+var_3A], r15w
0x18000d226  jmp     loc_18000D2E3
0x18000d22b  mov     r8, rbx
0x18000d22e  mov     rsi, rbx
0x18000d231  or      r9d, 0FFFFFFFFh
0x18000d235  cmp     [r8], r14w
0x18000d239  jz      short loc_18000D2A3
0x18000d23b  mov     eax, [rbp+cchBufferLength]
0x18000d23e  lea     rcx, [rbx+rax*2]
0x18000d242  cmp     r8, rcx
0x18000d245  jnb     short loc_18000D272
0x18000d247  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000d24b  inc     rdx
0x18000d24e  cmp     [r8+rdx*2], r14w
0x18000d253  jnz     short loc_18000D24B
0x18000d255  mov     rax, r8
0x18000d258  cmp     edx, r9d
0x18000d25b  cmovnb  rax, rsi
0x18000d25f  mov     rsi, rax
0x18000d262  lea     eax, [rdx+1]
0x18000d265  lea     r8, [r8+rax*2]
0x18000d269  cmovnb  edx, r9d
0x18000d26d  mov     r9d, edx
0x18000d270  jmp     short loc_18000D235
0x18000d272  lea     rax, WPP_GLOBAL_Control
0x18000d279  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d280  cmp     rcx, rax
0x18000d283  jz      short loc_18000D2A3
0x18000d285  test    dword ptr [rcx+1Ch], 4000000h
0x18000d28c  jz      short loc_18000D2A3
0x18000d28e  mov     edx, 17h
0x18000d293  lea     r8, WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids
0x18000d29a  mov     rcx, [rcx+10h]
0x18000d29e  call    WPP_SF_
0x18000d2a3  mov     r8, rsi; unsigned __int16 *
0x18000d2a6  mov     edx, 104h; unsigned __int64
0x18000d2ab  mov     rcx, rdi; unsigned __int16 *
0x18000d2ae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d2b3  mov     [rbp+var_40], eax
0x18000d2b6  test    eax, eax
0x18000d2b8  mov     eax, 8B5h
0x18000d2bd  js      short loc_18000D2DF
0x18000d2bf  mov     [rbp+var_3C], ax
0x18000d2c3  jmp     short loc_18000D2E3
0x18000d2c5  mov     [rbp+var_40], 8007000Eh
0x18000d2cc  mov     [rbp+var_3A], r12w
0x18000d2d1  jmp     short loc_18000D2E3
0x18000d2d3  mov     eax, 87Fh
0x18000d2d8  mov     [rbp+var_40], 80070057h
0x18000d2df  mov     [rbp+var_3A], ax
0x18000d2e3  mov     rcx, rbx; pv
0x18000d2e6  call    cs:__imp_CoTaskMemFree
0x18000d2ed  nop     dword ptr [rax+rax+00h]
0x18000d2f2  mov     ebx, [rbp+var_40]
0x18000d2f5  lea     rcx, [rbp+var_40]; this
0x18000d2f9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d2fe  mov     eax, ebx
0x18000d300  lea     r11, [rsp+60h+var_s0]
0x18000d305  mov     rbx, [r11+30h]
0x18000d309  mov     rsi, [r11+38h]
0x18000d30d  mov     rsp, r11
0x18000d310  pop     r15
0x18000d312  pop     r14
0x18000d314  pop     r12
0x18000d316  pop     rdi
0x18000d317  pop     rbp
0x18000d318  retn
```
