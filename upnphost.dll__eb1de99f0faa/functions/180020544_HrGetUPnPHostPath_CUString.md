# HrGetUPnPHostPath(CUString &)

- ea: `0x180020544`
- end: `0x180020726`
- name: `?HrGetUPnPHostPath@@YAJAEAVCUString@@@Z`
- size: `482`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001b890`
- `0x18001e790`

## callees

- `0x180013544`
- `0x180020544`
- `0x180038324`
- `0x180038ce4`
- `0x18003a560`
- `0x180043124`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800205f9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002064d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800206cc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800206d8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800205f9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002064d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800206cc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800206d8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800205ba`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800205ba`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180020588`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180020588`

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
0x180020544  push    rbx
0x180020546  push    rbp
0x180020547  push    rsi
0x180020548  push    rdi
0x180020549  push    r12
0x18002054b  push    r13
0x18002054d  push    r14
0x18002054f  push    r15
0x180020551  sub     rsp, 268h
0x180020558  mov     rax, cs:__security_cookie
0x18002055f  xor     rax, rsp
0x180020562  mov     [rsp+2A8h+var_58], rax
0x18002056a  xor     edx, edx
0x18002056c  lea     r8, [rsp+2A8h+pszSrc]
0x180020571  mov     rbp, rcx
0x180020574  xor     r12d, r12d
0x180020577  mov     ebx, r12d
0x18002057a  mov     r9d, 104h
0x180020580  mov     [rsp+2A8h+var_278], rbx
0x180020585  lea     ecx, [rdx+7]
0x180020588  call    cs:__imp_GetBasicProfileFolderPath
0x18002058e  lea     r13, WPP_GLOBAL_Control
0x180020595  mov     edi, eax
0x180020597  test    eax, eax
0x180020599  js      loc_180020642
0x18002059f  lea     rcx, [rsp+2A8h+pszSrc]
0x1800205a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800205a8  inc     rax
0x1800205ab  cmp     [rcx+rax*2], r12w
0x1800205b0  jnz     short loc_1800205A8
0x1800205b2  lea     r15, [rax+1]
0x1800205b6  lea     rcx, [r15+r15]; Size
0x1800205ba  call    cs:__imp_malloc
0x1800205c0  mov     r14, rax
0x1800205c3  test    rax, rax
0x1800205c6  jz      loc_1800206B3
0x1800205cc  mov     rdx, r15; cchDest
0x1800205cf  call    StringValidateDestW
0x1800205d4  mov     edi, eax
0x1800205d6  test    eax, eax
0x1800205d8  js      loc_1800206BA
0x1800205de  lea     r9, [rsp+2A8h+pszSrc]; pszSrc
0x1800205e3  mov     rcx, r14; pszDest
0x1800205e6  call    StringCopyWorkerW
0x1800205eb  mov     esi, eax
0x1800205ed  mov     edi, esi
0x1800205ef  test    esi, esi
0x1800205f1  js      loc_1800206C9
0x1800205f7  xor     ecx, ecx; Block
0x1800205f9  call    cs:__imp_free
0x1800205ff  mov     rbx, r14
0x180020602  mov     [rsp+2A8h+var_278], rbx
0x180020607  test    esi, esi
0x180020609  jnz     short loc_180020679
0x18002060b  lea     rdx, ?c_szMicrosoft@@3QBGB; "Microsoft"
0x180020612  lea     rcx, [rsp+2A8h+var_278]; struct CUString *
0x180020617  call    ?HrAddDirectoryToPath@@YAJAEAVCUString@@PEBG@Z; HrAddDirectoryToPath(CUString &,ushort const *)
0x18002061c  mov     edi, eax
0x18002061e  test    eax, eax
0x180020620  js      short loc_18002063D
0x180020622  lea     rdx, ?c_szUPnPDeviceHost@@3QBGB; "UPnP Device Host"
0x180020629  lea     rcx, [rsp+2A8h+var_278]; struct CUString *
0x18002062e  call    ?HrAddDirectoryToPath@@YAJAEAVCUString@@PEBG@Z; HrAddDirectoryToPath(CUString &,ushort const *)
0x180020633  mov     edi, eax
0x180020635  test    eax, eax
0x180020637  jns     loc_1800206D4
0x18002063d  mov     rbx, [rsp+2A8h+var_278]
0x180020642  test    edi, edi
0x180020644  jnz     loc_1800206EF
0x18002064a  mov     rcx, rbx; Block
0x18002064d  call    cs:__imp_free
0x180020653  mov     eax, edi
0x180020655  mov     rcx, [rsp+2A8h+var_58]
0x18002065d  xor     rcx, rsp; StackCookie
0x180020660  call    __security_check_cookie
0x180020665  add     rsp, 268h
0x18002066c  pop     r15
0x18002066e  pop     r14
0x180020670  pop     r13
0x180020672  pop     r12
0x180020674  pop     rdi
0x180020675  pop     rsi
0x180020676  pop     rbp
0x180020677  pop     rbx
0x180020678  retn
0x180020679  mov     rcx, cs:WPP_GLOBAL_Control
0x180020680  cmp     rcx, r13
0x180020683  jz      short loc_1800206AA
0x180020685  test    byte ptr [rcx+1Ch], 1
0x180020689  jz      short loc_1800206AA
0x18002068b  mov     rcx, [rcx+10h]
0x18002068f  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180020696  mov     edx, 0Ah
0x18002069b  mov     r9d, edi
0x18002069e  call    WPP_SF_d
0x1800206a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206aa  test    edi, edi
0x1800206ac  js      short loc_1800206F6
0x1800206ae  jmp     loc_18002060B
0x1800206b3  mov     edi, 8007000Eh
0x1800206b8  jmp     short loc_180020679
0x1800206ba  mov     esi, eax
0x1800206bc  test    r15, r15
0x1800206bf  jz      loc_1800205ED
0x1800206c5  mov     [r14], r12w
0x1800206c9  mov     rcx, r14; Block
0x1800206cc  call    cs:__imp_free
0x1800206d2  jmp     short loc_180020679
0x1800206d4  mov     rcx, [rbp+0]; Block
0x1800206d8  call    cs:__imp_free
0x1800206de  mov     rax, [rsp+2A8h+var_278]
0x1800206e3  mov     rbx, r12
0x1800206e6  mov     [rbp+0], rax
0x1800206ea  jmp     loc_180020642
0x1800206ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206f6  cmp     rcx, r13
0x1800206f9  jz      loc_18002064A
0x1800206ff  test    byte ptr [rcx+1Ch], 1
0x180020703  jz      loc_18002064A
0x180020709  mov     rcx, [rcx+10h]
0x18002070d  lea     r8, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids
0x180020714  mov     edx, 17h
0x180020719  mov     r9d, edi
0x18002071c  call    WPP_SF_d
0x180020721  jmp     loc_18002064A
```
