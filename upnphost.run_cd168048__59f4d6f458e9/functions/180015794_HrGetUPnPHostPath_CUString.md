# HrGetUPnPHostPath(CUString &)

- ea: `0x180015794`
- end: `0x18001599b`
- name: `?HrGetUPnPHostPath@@YAJAEAVCUString@@@Z`
- size: `519`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800106a8`
- `0x180013818`

## callees

- `0x1800075ac`
- `0x180015794`
- `0x18003a798`
- `0x18003b1cc`
- `0x18003cb60`
- `0x180045b90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015855`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800158af`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015935`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015947`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015855`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800158af`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015935`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180015947`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015810`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180015810`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800157d8`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800157d8`

## pseudocode

```c
__int64 __fastcall HrGetUPnPHostPath(void **a1)
{
  wchar_t *v2; // rbx
  int BasicProfileFolderPath; // edi
  __int64 v4; // rax
  size_t v5; // r15
  const wchar_t *v6; // rcx
  size_t v7; // r8
  wchar_t *v8; // r14
  HRESULT v9; // eax
  size_t v10; // rdx
  size_t *v11; // r8
  HRESULT v12; // esi
  STRSAFE_PCNZWCH v14; // rcx
  size_t v15; // [rsp+20h] [rbp-288h]
  _QWORD v16[2]; // [rsp+30h] [rbp-278h] BYREF
  wchar_t pszSrc[264]; // [rsp+40h] [rbp-268h] BYREF

  v2 = 0;
  v16[0] = 0;
  BasicProfileFolderPath = GetBasicProfileFolderPath(7, 0, pszSrc, 260);
  if ( BasicProfileFolderPath >= 0 )
  {
    v4 = -1;
    do
      ++v4;
    while ( pszSrc[v4] );
    v5 = v4 + 1;
    v8 = (wchar_t *)malloc(2 * (v4 + 1));
    if ( !v8 )
    {
      BasicProfileFolderPath = -2147024882;
      goto LABEL_14;
    }
    v9 = StringValidateDestW(v6, v5, v7);
    BasicProfileFolderPath = v9;
    if ( v9 < 0 )
    {
      v12 = v9;
      if ( v5 )
      {
        *v8 = 0;
        goto LABEL_22;
      }
    }
    else
    {
      v12 = StringCopyWorkerW(v8, v10, v11, pszSrc, v15);
    }
    BasicProfileFolderPath = v12;
    if ( v12 >= 0 )
    {
      free(0);
      v2 = v8;
      v16[0] = v8;
      if ( !v12 )
      {
LABEL_9:
        BasicProfileFolderPath = HrAddDirectoryToPath((struct CUString *)v16, L"Microsoft");
        if ( BasicProfileFolderPath >= 0
          && (BasicProfileFolderPath = HrAddDirectoryToPath((struct CUString *)v16, L"UPnP Device Host"),
              BasicProfileFolderPath >= 0) )
        {
          free(*a1);
          v2 = 0;
          *a1 = (void *)v16[0];
        }
        else
        {
          v2 = (wchar_t *)v16[0];
        }
        goto LABEL_12;
      }
LABEL_14:
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
          (unsigned int)BasicProfileFolderPath);
        v14 = WPP_GLOBAL_Control;
      }
      if ( BasicProfileFolderPath < 0 )
        goto LABEL_25;
      goto LABEL_9;
    }
LABEL_22:
    free(v8);
    goto LABEL_14;
  }
LABEL_12:
  if ( !BasicProfileFolderPath )
    goto LABEL_13;
  v14 = WPP_GLOBAL_Control;
LABEL_25:
  if ( v14 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v14[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)v14 + 2),
      23,
      WPP_cd0457ca62d634003859bdcf9006b616_Traceguids,
      (unsigned int)BasicProfileFolderPath);
LABEL_13:
  free(v2);
  return (unsigned int)BasicProfileFolderPath;
}

```

## disassembly

```asm
0x180015794  push    rbx
0x180015796  push    rbp
0x180015797  push    rsi
0x180015798  push    rdi
0x180015799  push    r12
0x18001579b  push    r13
0x18001579d  push    r14
0x18001579f  push    r15
0x1800157a1  sub     rsp, 268h
0x1800157a8  mov     rax, cs:__security_cookie
0x1800157af  xor     rax, rsp
0x1800157b2  mov     [rsp+2A8h+var_58], rax
0x1800157ba  xor     edx, edx
0x1800157bc  lea     r8, [rsp+2A8h+pszSrc]
0x1800157c1  mov     rbp, rcx
0x1800157c4  xor     r12d, r12d
0x1800157c7  mov     ebx, r12d
0x1800157ca  mov     r9d, 104h
0x1800157d0  mov     [rsp+2A8h+var_278], rbx
0x1800157d5  lea     ecx, [rdx+7]
0x1800157d8  call    cs:__imp_GetBasicProfileFolderPath
0x1800157df  nop     dword ptr [rax+rax+00h]
0x1800157e4  lea     r13, WPP_GLOBAL_Control
0x1800157eb  mov     edi, eax
0x1800157ed  test    eax, eax
0x1800157ef  js      loc_1800158A4
0x1800157f5  lea     rcx, [rsp+2A8h+pszSrc]
0x1800157fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800157fe  inc     rax
0x180015801  cmp     [rcx+rax*2], r12w
0x180015806  jnz     short loc_1800157FE
0x180015808  lea     r15, [rax+1]
0x18001580c  lea     rcx, [r15+r15]; Size
0x180015810  call    cs:__imp_malloc
0x180015817  nop     dword ptr [rax+rax+00h]
0x18001581c  mov     r14, rax
0x18001581f  test    rax, rax
0x180015822  jz      loc_18001591C
0x180015828  mov     rdx, r15; cchDest
0x18001582b  call    StringValidateDestW
0x180015830  mov     edi, eax
0x180015832  test    eax, eax
0x180015834  js      loc_180015923
0x18001583a  lea     r9, [rsp+2A8h+pszSrc]; pszSrc
0x18001583f  mov     rcx, r14; pszDest
0x180015842  call    StringCopyWorkerW
0x180015847  mov     esi, eax
0x180015849  mov     edi, esi
0x18001584b  test    esi, esi
0x18001584d  js      loc_180015932
0x180015853  xor     ecx, ecx; Block
0x180015855  call    cs:__imp_free
0x18001585c  nop     dword ptr [rax+rax+00h]
0x180015861  mov     rbx, r14
0x180015864  mov     [rsp+2A8h+var_278], rbx
0x180015869  test    esi, esi
0x18001586b  jnz     short loc_1800158E2
0x18001586d  lea     rdx, ?c_szMicrosoft@@3QBGB; "Microsoft"
0x180015874  lea     rcx, [rsp+2A8h+var_278]; struct CUString *
0x180015879  call    ?HrAddDirectoryToPath@@YAJAEAVCUString@@PEBG@Z; HrAddDirectoryToPath(CUString &,ushort const *)
0x18001587e  mov     edi, eax
0x180015880  test    eax, eax
0x180015882  js      short loc_18001589F
0x180015884  lea     rdx, ?c_szUPnPDeviceHost@@3QBGB; "UPnP Device Host"
0x18001588b  lea     rcx, [rsp+2A8h+var_278]; struct CUString *
0x180015890  call    ?HrAddDirectoryToPath@@YAJAEAVCUString@@PEBG@Z; HrAddDirectoryToPath(CUString &,ushort const *)
0x180015895  mov     edi, eax
0x180015897  test    eax, eax
0x180015899  jns     loc_180015943
0x18001589f  mov     rbx, [rsp+2A8h+var_278]
0x1800158a4  test    edi, edi
0x1800158a6  jnz     loc_180015964
0x1800158ac  mov     rcx, rbx; Block
0x1800158af  call    cs:__imp_free
0x1800158b6  nop     dword ptr [rax+rax+00h]
0x1800158bb  mov     eax, edi
0x1800158bd  mov     rcx, [rsp+2A8h+var_58]
0x1800158c5  xor     rcx, rsp; StackCookie
0x1800158c8  call    __security_check_cookie
0x1800158cd  add     rsp, 268h
0x1800158d4  pop     r15
0x1800158d6  pop     r14
0x1800158d8  pop     r13
0x1800158da  pop     r12
0x1800158dc  pop     rdi
0x1800158dd  pop     rsi
0x1800158de  pop     rbp
0x1800158df  pop     rbx
0x1800158e0  retn
0x1800158e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158e9  cmp     rcx, r13
0x1800158ec  jz      short loc_180015913
0x1800158ee  test    byte ptr [rcx+1Ch], 1
0x1800158f2  jz      short loc_180015913
0x1800158f4  mov     rcx, [rcx+10h]
0x1800158f8  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x1800158ff  mov     edx, 0Ah
0x180015904  mov     r9d, edi
0x180015907  call    WPP_SF_d
0x18001590c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015913  test    edi, edi
0x180015915  js      short loc_18001596B
0x180015917  jmp     loc_18001586D
0x18001591c  mov     edi, 8007000Eh
0x180015921  jmp     short loc_1800158E2
0x180015923  mov     esi, eax
0x180015925  test    r15, r15
0x180015928  jz      loc_180015849
0x18001592e  mov     [r14], r12w
0x180015932  mov     rcx, r14; Block
0x180015935  call    cs:__imp_free
0x18001593c  nop     dword ptr [rax+rax+00h]
0x180015941  jmp     short loc_1800158E2
0x180015943  mov     rcx, [rbp+0]; Block
0x180015947  call    cs:__imp_free
0x18001594e  nop     dword ptr [rax+rax+00h]
0x180015953  mov     rax, [rsp+2A8h+var_278]
0x180015958  mov     rbx, r12
0x18001595b  mov     [rbp+0], rax
0x18001595f  jmp     loc_1800158A4
0x180015964  mov     rcx, cs:WPP_GLOBAL_Control
0x18001596b  cmp     rcx, r13
0x18001596e  jz      loc_1800158AC
0x180015974  test    byte ptr [rcx+1Ch], 1
0x180015978  jz      loc_1800158AC
0x18001597e  mov     rcx, [rcx+10h]
0x180015982  lea     r8, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids
0x180015989  mov     edx, 17h
0x18001598e  mov     r9d, edi
0x180015991  call    WPP_SF_d
0x180015996  jmp     loc_1800158AC
```
