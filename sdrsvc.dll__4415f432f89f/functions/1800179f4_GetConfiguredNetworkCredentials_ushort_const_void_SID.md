# GetConfiguredNetworkCredentials(ushort const *,void * *,_SID *)

- ea: `0x1800179f4`
- end: `0x180017c17`
- name: `?GetConfiguredNetworkCredentials@@YAJPEBGPEAPEAXPEAU_SID@@@Z`
- size: `547`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, struct _SID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180011fd4`

## callees

- `0x18001586c`
- `0x180015974`
- `0x1800171f4`
- `0x1800179f4`
- `0x180017c20`
- `0x18001b0e4`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017bde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017bde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017b8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017bc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017b8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017bc8`

## string_xrefs

- `0x180017a2c`: `GetConfiguredNetworkCredentials`

## pseudocode

```c
__int64 __fastcall GetConfiguredNetworkCredentials(const unsigned __int16 *a1, void **a2, struct _SID *a3)
{
  char *v5; // rbx
  void *v6; // rsi
  WCHAR *v7; // rdi
  bool v8; // zf
  __int16 v9; // ax
  int CredsFromRegistry; // eax
  bool v11; // sf
  __int64 v12; // rax
  __int64 v13; // rcx
  WCHAR *i; // rax
  unsigned int v15; // edi
  LPCWSTR lpszPassword; // [rsp+30h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-71h] BYREF
  void *v19; // [rsp+40h] [rbp-69h] BYREF
  int NetworkCredentials; // [rsp+48h] [rbp-61h] BYREF
  __int16 v21; // [rsp+4Ch] [rbp-5Dh]
  __int16 v22; // [rsp+4Eh] [rbp-5Bh]
  struct _SID v23; // [rsp+80h] [rbp-29h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&NetworkCredentials,
    "GetConfiguredNetworkCredentials",
    36,
    1);
  v5 = 0;
  v19 = 0;
  memset_0(&v23, 0, 0x48u);
  pv = 0;
  v6 = 0;
  lpszPassword = 0;
  v7 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !a1 || !*a1 )
  {
    v9 = 46;
LABEL_19:
    NetworkCredentials = -2147024809;
    goto LABEL_20;
  }
  NetworkCredentials = 0;
  v21 = 46;
  v8 = (unsigned int)SdIsPathUNC(a1) == 0;
  v9 = 47;
  if ( !v8 )
    goto LABEL_19;
  v21 = 47;
  v9 = 48;
  if ( !a2 )
    goto LABEL_19;
  NetworkCredentials = 0;
  v21 = 48;
  CredsFromRegistry = ReadCredsFromRegistry((unsigned __int16 **)&pv, (unsigned __int16 **)&lpszPassword);
  v6 = pv;
  v11 = CredsFromRegistry < 0;
  NetworkCredentials = CredsFromRegistry;
  v9 = 50;
  if ( v11 )
  {
LABEL_8:
    v7 = (WCHAR *)lpszPassword;
    goto LABEL_20;
  }
  v21 = 50;
  if ( !pv || !*(_WORD *)pv )
  {
    NetworkCredentials = -2130706391;
    v9 = 52;
    goto LABEL_8;
  }
  v7 = (WCHAR *)lpszPassword;
  NetworkCredentials = 0;
  v21 = 52;
  if ( lpszPassword && *lpszPassword )
  {
    v21 = 53;
    NetworkCredentials = GetNetworkCredentials(a1, (wchar_t *)pv, lpszPassword, &v19, &v23, 0);
    v9 = 55;
    if ( NetworkCredentials >= 0 )
    {
      v21 = 55;
      *a2 = v19;
      goto LABEL_21;
    }
    v5 = (char *)v19;
  }
  else
  {
    NetworkCredentials = -2130706391;
    v9 = 53;
  }
LABEL_20:
  v22 = v9;
LABEL_21:
  if ( v6 )
    CoTaskMemFree(v6);
  if ( v7 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v7[v12] );
    v13 = 2 * v12;
    for ( i = v7; v13; --v13 )
    {
      *(_BYTE *)i = 0;
      i = (WCHAR *)((char *)i + 1);
    }
    CoTaskMemFree(v7);
  }
  v15 = NetworkCredentials;
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&NetworkCredentials);
  return v15;
}

```

## disassembly

```asm
0x1800179f4  mov     [rsp-8+arg_10], rbx
0x1800179f9  mov     [rsp-8+arg_18], rsi
0x1800179fe  push    rbp
0x1800179ff  push    rdi
0x180017a00  push    r12
0x180017a02  push    r14
0x180017a04  push    r15
0x180017a06  lea     rbp, [rsp-37h]
0x180017a0b  sub     rsp, 0E0h
0x180017a12  mov     rax, cs:__security_cookie
0x180017a19  xor     rax, rsp
0x180017a1c  mov     [rbp+57h+var_30], rax
0x180017a20  mov     r9d, 1; unsigned __int16
0x180017a26  mov     r15, rdx
0x180017a29  mov     r14, rcx
0x180017a2c  lea     rdx, aGetconfiguredn; "GetConfiguredNetworkCredentials"
0x180017a33  lea     rcx, [rbp+57h+var_B8]; this
0x180017a37  lea     r8d, [r9+23h]; unsigned __int16
0x180017a3b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180017a40  xor     r12d, r12d
0x180017a43  lea     rcx, [rbp+57h+var_80]; void *
0x180017a47  mov     ebx, r12d
0x180017a4a  xor     edx, edx; Val
0x180017a4c  mov     [rbp+57h+var_C0], rbx
0x180017a50  lea     r8d, [r12+48h]; Size
0x180017a55  call    memset_0
0x180017a5a  mov     [rbp+57h+pv], r12
0x180017a5e  mov     esi, r12d
0x180017a61  mov     [rbp+57h+lpszPassword], r12
0x180017a65  mov     edi, r12d
0x180017a68  test    r15, r15
0x180017a6b  jz      short loc_180017A70
0x180017a6d  mov     [r15], r12
0x180017a70  test    r14, r14
0x180017a73  jz      loc_180017B77
0x180017a79  cmp     [r14], r12w
0x180017a7d  jz      loc_180017B77
0x180017a83  mov     eax, 2Eh ; '.'
0x180017a88  mov     [rbp+57h+var_B8], r12d
0x180017a8c  mov     rcx, r14; unsigned __int16 *
0x180017a8f  mov     [rbp+57h+var_B4], ax
0x180017a93  call    ?SdIsPathUNC@@YAJPEBG@Z; SdIsPathUNC(ushort const *)
0x180017a98  test    eax, eax
0x180017a9a  mov     eax, 2Fh ; '/'
0x180017a9f  jnz     loc_180017B7C
0x180017aa5  mov     [rbp+57h+var_B4], ax
0x180017aa9  mov     eax, 30h ; '0'
0x180017aae  test    r15, r15
0x180017ab1  jz      loc_180017B7C
0x180017ab7  lea     rdx, [rbp+57h+lpszPassword]; unsigned __int16 **
0x180017abb  mov     [rbp+57h+var_B8], r12d
0x180017abf  lea     rcx, [rbp+57h+pv]; unsigned __int16 **
0x180017ac3  mov     [rbp+57h+var_B4], ax
0x180017ac7  call    ?ReadCredsFromRegistry@@YAJPEAPEAG0@Z; ReadCredsFromRegistry(ushort * *,ushort * *)
0x180017acc  mov     rsi, [rbp+57h+pv]
0x180017ad0  test    eax, eax
0x180017ad2  mov     [rbp+57h+var_B8], eax
0x180017ad5  mov     eax, 32h ; '2'
0x180017ada  jns     short loc_180017AE5
0x180017adc  mov     rdi, [rbp+57h+lpszPassword]
0x180017ae0  jmp     loc_180017B83
0x180017ae5  mov     [rbp+57h+var_B4], ax
0x180017ae9  test    rsi, rsi
0x180017aec  jz      short loc_180017B66
0x180017aee  cmp     [rsi], r12w
0x180017af2  jz      short loc_180017B66
0x180017af4  mov     rdi, [rbp+57h+lpszPassword]
0x180017af8  mov     eax, 34h ; '4'
0x180017afd  mov     [rbp+57h+var_B8], r12d
0x180017b01  mov     [rbp+57h+var_B4], ax
0x180017b05  test    rdi, rdi
0x180017b08  jz      short loc_180017B58
0x180017b0a  cmp     [rdi], r12w
0x180017b0e  jz      short loc_180017B58
0x180017b10  mov     eax, 35h ; '5'
0x180017b15  mov     [rsp+100h+var_D8], r12; int *
0x180017b1a  mov     [rbp+57h+var_B4], ax
0x180017b1e  lea     r9, [rbp+57h+var_C0]; void **
0x180017b22  lea     rax, [rbp+57h+var_80]
0x180017b26  mov     r8, rdi; lpszPassword
0x180017b29  mov     rdx, rsi; Str
0x180017b2c  mov     [rsp+100h+var_E0], rax; struct _SID *
0x180017b31  mov     rcx, r14; unsigned __int16 *
0x180017b34  call    ?GetNetworkCredentials@@YAJPEBG00PEAPEAXPEAU_SID@@PEAH@Z; GetNetworkCredentials(ushort const *,ushort const *,ushort const *,void * *,_SID *,int *)
0x180017b39  mov     [rbp+57h+var_B8], eax
0x180017b3c  test    eax, eax
0x180017b3e  mov     eax, 37h ; '7'
0x180017b43  jns     short loc_180017B4B
0x180017b45  mov     rbx, [rbp+57h+var_C0]
0x180017b49  jmp     short loc_180017B83
0x180017b4b  mov     [rbp+57h+var_B4], ax
0x180017b4f  mov     rax, [rbp+57h+var_C0]
0x180017b53  mov     [r15], rax
0x180017b56  jmp     short loc_180017B87
0x180017b58  mov     [rbp+57h+var_B8], 81000029h
0x180017b5f  mov     eax, 35h ; '5'
0x180017b64  jmp     short loc_180017B83
0x180017b66  mov     [rbp+57h+var_B8], 81000029h
0x180017b6d  mov     eax, 34h ; '4'
0x180017b72  jmp     loc_180017ADC
0x180017b77  mov     eax, 2Eh ; '.'
0x180017b7c  mov     [rbp+57h+var_B8], 80070057h
0x180017b83  mov     [rbp+57h+var_B2], ax
0x180017b87  test    rsi, rsi
0x180017b8a  jz      short loc_180017B95
0x180017b8c  mov     rcx, rsi; pv
0x180017b8f  call    cs:__imp_CoTaskMemFree
0x180017b95  test    rdi, rdi
0x180017b98  jz      short loc_180017BCE
0x180017b9a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017b9e  inc     rax
0x180017ba1  cmp     [rdi+rax*2], r12w
0x180017ba6  jnz     short loc_180017B9E
0x180017ba8  lea     rcx, [rax+rax]
0x180017bac  mov     rax, rdi
0x180017baf  test    rcx, rcx
0x180017bb2  jz      short loc_180017BC0
0x180017bb4  mov     [rax], r12b
0x180017bb7  inc     rax
0x180017bba  sub     rcx, 1
0x180017bbe  jnz     short loc_180017BB4
0x180017bc0  test    rdi, rdi
0x180017bc3  jz      short loc_180017BCE
0x180017bc5  mov     rcx, rdi; pv
0x180017bc8  call    cs:__imp_CoTaskMemFree
0x180017bce  mov     edi, [rbp+57h+var_B8]
0x180017bd1  lea     rcx, [rbx-1]
0x180017bd5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180017bd9  ja      short loc_180017BE4
0x180017bdb  mov     rcx, rbx; hObject
0x180017bde  call    cs:__imp_CloseHandle
0x180017be4  lea     rcx, [rbp+57h+var_B8]; this
0x180017be8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180017bed  mov     eax, edi
0x180017bef  mov     rcx, [rbp+57h+var_30]
0x180017bf3  xor     rcx, rsp; StackCookie
0x180017bf6  call    __security_check_cookie
0x180017bfb  lea     r11, [rsp+100h+var_20]
0x180017c03  mov     rbx, [r11+40h]
0x180017c07  mov     rsi, [r11+48h]
0x180017c0b  mov     rsp, r11
0x180017c0e  pop     r15
0x180017c10  pop     r14
0x180017c12  pop     r12
0x180017c14  pop     rdi
0x180017c15  pop     rbp
0x180017c16  retn
```
