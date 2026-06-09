# ConvertDiskStyle(IVdsService *,int,_VDS_PARTITION_STYLE)

- ea: `0x18003e030`
- end: `0x18003e3b8`
- name: `?ConvertDiskStyle@@YAJPEAUIVdsService@@HW4_VDS_PARTITION_STYLE@@@Z`
- size: `904`
- prototype: `__int64 __fastcall(struct IVdsService *, int, enum _VDS_PARTITION_STYLE)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800244d4`
- `0x18003e3c0`

## callees

- `0x180039394`
- `0x18003e030`
- `0x180041338`
- `0x1800417a8`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e2eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e301`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e314`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e327`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e33a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e34d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e2eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e301`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e314`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e327`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e33a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e34d`

## pseudocode

```c
__int64 __fastcall ConvertDiskStyle(struct IVdsService *a1, unsigned int a2, unsigned int a3)
{
  int Disk; // ebx
  int v7; // edi
  struct IVdsDisk *v8; // rdi
  const wchar_t *v9; // rax
  const wchar_t *v10; // r14
  int v11; // r9d
  int v12; // edi
  int v13; // edx
  __int64 v15; // [rsp+28h] [rbp-91h]
  struct IVdsDisk *v16; // [rsp+30h] [rbp-89h] BYREF
  int v17; // [rsp+38h] [rbp-81h] BYREF
  struct IVdsAdvancedDisk *v18; // [rsp+40h] [rbp-79h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-71h] BYREF
  int v20; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v21[64]; // [rsp+54h] [rbp-65h] BYREF
  int v22; // [rsp+94h] [rbp-25h]
  LPVOID v23; // [rsp+A8h] [rbp-11h]
  LPVOID v24; // [rsp+B0h] [rbp-9h]
  LPVOID v25; // [rsp+B8h] [rbp-1h]
  LPVOID v26; // [rsp+C0h] [rbp+7h]
  LPVOID v27; // [rsp+C8h] [rbp+Fh]

  v16 = 0;
  v18 = 0;
  if ( a1 && (a2 & 0x80000000) == 0 && a3 - 1 <= 1 )
  {
    Disk = GetDisk(a1, a2, &v16, &v18, 0);
    if ( Disk < 0 || !v16 || !v18 )
      return (unsigned int)Disk;
    pv = 0;
    Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, LPVOID *))v16->lpVtbl->GetPack)(v16, &pv);
    if ( Disk != -2147212265 || pv )
    {
      v7 = 0;
      if ( pv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    }
    else
    {
      v7 = 1;
      Disk = 0;
    }
    if ( Disk < 0 )
      goto LABEL_51;
    if ( v7 )
    {
      Disk = ConvertUnallocatedDisk(a1, a2, VDS_PST_GPT, &v16, &v18);
      if ( Disk < 0 )
        goto LABEL_51;
    }
    v8 = v16;
    if ( !v16 )
      goto LABEL_52;
    if ( !v18 )
    {
LABEL_54:
      if ( v8 )
        ((void (__fastcall *)(struct IVdsDisk *))v8->lpVtbl->Release)(v8);
      return (unsigned int)Disk;
    }
    v20 = 0;
    memset_0(v21, 0, 0x7Cu);
    Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, int *))v8->lpVtbl->GetProperties)(v8, &v20);
    if ( Disk >= 0 )
    {
      if ( a3 != v22 )
      {
        pv = 0;
        v9 = L"MBR";
        v17 = 0;
        v10 = L"MBR";
        if ( a3 != 1 )
          v10 = L"GPT";
        if ( v22 != 1 )
          v9 = L"GPT";
        LibLog(&g_VdsLibLog, 0x4000000, L"ConvertDiskStyle: Disk [%d] is an %s disk; converting to %s...", a2, v9, v10);
        Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, LPVOID *, int *))v16->lpVtbl->QueryExtents)(v16, &pv, &v17);
        if ( Disk < 0 )
          goto LABEL_38;
        v11 = v17;
        v12 = 0;
        if ( v17 <= 0 )
        {
LABEL_35:
          Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, _QWORD))v16->lpVtbl->ConvertStyle)(v16, a3);
          if ( Disk >= 0 )
          {
            LibLog(&g_VdsLibLog, 0x4000000, L"ConvertDiskStyle: Successfully converted disk [%d] to %s.", a2, v10);
            goto LABEL_38;
          }
        }
        else
        {
          while ( Disk >= 0 )
          {
            v13 = *((_DWORD *)pv + 20 * v12 + 4);
            if ( v13 != 1
              && v13 != 0x7FFF
              && (unsigned int)(v13 - 5) > 1
              && (v13 || *((_QWORD *)pv + 10 * v12 + 3) || *((_QWORD *)pv + 10 * v12 + 4)) )
            {
              Disk = -2147467259;
              LibLog(&g_VdsLibLog, 0x2000000, L"ConvertDiskStyle: Conversion failed since disk [%d] is not empty.", a2);
              v11 = v17;
            }
            if ( ++v12 >= v11 )
            {
              if ( Disk < 0 )
                break;
              goto LABEL_35;
            }
          }
        }
        LODWORD(v15) = Disk;
        LibLog(&g_VdsLibLog, 0x2000000, L"ConvertDiskStyle: Failed to convert disk [%d] to %s; hr = 0x%x", a2, v10, v15);
LABEL_38:
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_41;
      }
      Disk = 1;
    }
LABEL_41:
    if ( v23 )
    {
      CoTaskMemFree(v23);
      v23 = 0;
    }
    if ( v24 )
    {
      CoTaskMemFree(v24);
      v24 = 0;
    }
    if ( v25 )
    {
      CoTaskMemFree(v25);
      v25 = 0;
    }
    if ( v26 )
    {
      CoTaskMemFree(v26);
      v26 = 0;
    }
    if ( v27 )
      CoTaskMemFree(v27);
LABEL_51:
    v8 = v16;
LABEL_52:
    if ( v18 )
    {
      ((void (__fastcall *)(struct IVdsAdvancedDisk *))v18->lpVtbl->Release)(v18);
      v8 = v16;
      v18 = 0;
    }
    goto LABEL_54;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18003e030  push    rbp
0x18003e032  push    rbx
0x18003e033  push    rsi
0x18003e034  push    rdi
0x18003e035  push    r12
0x18003e037  push    r14
0x18003e039  push    r15
0x18003e03b  lea     rbp, [rsp-27h]
0x18003e040  sub     rsp, 0E0h
0x18003e047  mov     rax, cs:__security_cookie
0x18003e04e  xor     rax, rsp
0x18003e051  mov     [rbp+57h+var_40], rax
0x18003e055  xor     r12d, r12d
0x18003e058  mov     r15d, r8d
0x18003e05b  mov     [rsp+110h+var_E0], r12
0x18003e060  mov     esi, edx
0x18003e062  mov     [rbp+57h+var_D0], r12
0x18003e066  mov     r14, rcx
0x18003e069  test    rcx, rcx
0x18003e06c  jz      loc_18003E395
0x18003e072  test    edx, edx
0x18003e074  js      loc_18003E395
0x18003e07a  lea     eax, [r8-1]
0x18003e07e  cmp     eax, 1
0x18003e081  ja      loc_18003E395
0x18003e087  lea     r9, [rbp+57h+var_D0]; struct IVdsAdvancedDisk **
0x18003e08b  mov     [rsp+110h+var_F0], r12; struct IVdsAdvancedDisk2 **
0x18003e090  lea     r8, [rsp+110h+var_E0]; struct IVdsDisk **
0x18003e095  call    ?GetDisk@@YAJPEAUIVdsService@@HPEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@PEAPEAUIVdsAdvancedDisk2@@@Z; GetDisk(IVdsService *,int,IVdsDisk * *,IVdsAdvancedDisk * *,IVdsAdvancedDisk2 * *)
0x18003e09a  mov     ebx, eax
0x18003e09c  test    eax, eax
0x18003e09e  js      loc_18003E391
0x18003e0a4  mov     rdi, [rsp+110h+var_E0]
0x18003e0a9  test    rdi, rdi
0x18003e0ac  jz      loc_18003E391
0x18003e0b2  cmp     [rbp+57h+var_D0], r12
0x18003e0b6  jz      loc_18003E391
0x18003e0bc  mov     [rbp+57h+pv], r12
0x18003e0c0  test    rdi, rdi
0x18003e0c3  jz      loc_18003E35A
0x18003e0c9  mov     rax, [rdi]
0x18003e0cc  lea     rdx, [rbp+57h+pv]
0x18003e0d0  mov     rcx, rdi
0x18003e0d3  mov     rax, [rax+20h]
0x18003e0d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e0dc  mov     rcx, [rbp+57h+pv]
0x18003e0e0  mov     ebx, eax
0x18003e0e2  cmp     eax, 80042417h
0x18003e0e7  jnz     short loc_18003E0F6
0x18003e0e9  test    rcx, rcx
0x18003e0ec  jnz     short loc_18003E0F6
0x18003e0ee  lea     edi, [rcx+1]
0x18003e0f1  mov     ebx, r12d
0x18003e0f4  jmp     short loc_18003E10A
0x18003e0f6  mov     edi, r12d
0x18003e0f9  test    rcx, rcx
0x18003e0fc  jz      short loc_18003E10A
0x18003e0fe  mov     rax, [rcx]
0x18003e101  mov     rax, [rax+10h]
0x18003e105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e10a  test    ebx, ebx
0x18003e10c  js      loc_18003E353
0x18003e112  test    edi, edi
0x18003e114  jz      short loc_18003E13E
0x18003e116  lea     rax, [rbp+57h+var_D0]
0x18003e11a  mov     r8d, 2; enum _VDS_PARTITION_STYLE
0x18003e120  lea     r9, [rsp+110h+var_E0]; struct IVdsDisk **
0x18003e125  mov     [rsp+110h+var_F0], rax; struct IVdsAdvancedDisk **
0x18003e12a  mov     edx, esi; int
0x18003e12c  mov     rcx, r14; struct IVdsService *
0x18003e12f  call    ?ConvertUnallocatedDisk@@YAJPEAUIVdsService@@HW4_VDS_PARTITION_STYLE@@PEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@@Z; ConvertUnallocatedDisk(IVdsService *,int,_VDS_PARTITION_STYLE,IVdsDisk * *,IVdsAdvancedDisk * *)
0x18003e134  mov     ebx, eax
0x18003e136  test    eax, eax
0x18003e138  js      loc_18003E353
0x18003e13e  mov     rdi, [rsp+110h+var_E0]
0x18003e143  test    rdi, rdi
0x18003e146  jz      loc_18003E35F
0x18003e14c  cmp     [rbp+57h+var_D0], r12
0x18003e150  jz      loc_18003E37D
0x18003e156  xor     edx, edx; Val
0x18003e158  mov     [rbp+57h+var_C0], r12d
0x18003e15c  lea     rcx, [rbp+57h+var_BC]; void *
0x18003e160  lea     r8d, [rdx+7Ch]; Size
0x18003e164  call    memset_0
0x18003e169  mov     rax, [rdi]
0x18003e16c  lea     rdx, [rbp+57h+var_C0]
0x18003e170  mov     rcx, rdi
0x18003e173  mov     rax, [rax+18h]
0x18003e177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e17c  mov     ebx, eax
0x18003e17e  test    eax, eax
0x18003e180  js      loc_18003E2F8
0x18003e186  cmp     r15d, [rbp+57h+var_7C]
0x18003e18a  jz      loc_18003E2F3
0x18003e190  lea     rcx, aGpt; "GPT"
0x18003e197  mov     [rbp+57h+pv], r12
0x18003e19b  lea     rax, aMbr; "MBR"
0x18003e1a2  mov     [rsp+110h+var_D8], r12d
0x18003e1a7  mov     r14, rax
0x18003e1aa  lea     r8, aConvertdisksty_1; "ConvertDiskStyle: Disk [%d] is an %s di"...
0x18003e1b1  cmp     r15d, 1
0x18003e1b5  mov     r9d, esi
0x18003e1b8  mov     edx, 4000000h
0x18003e1bd  cmovnz  r14, rcx
0x18003e1c1  cmp     [rbp+57h+var_7C], 1
0x18003e1c5  mov     [rsp+110h+var_E8], r14
0x18003e1ca  cmovnz  rax, rcx
0x18003e1ce  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18003e1d5  mov     [rsp+110h+var_F0], rax
0x18003e1da  call    LibLog
0x18003e1df  mov     rcx, [rsp+110h+var_E0]
0x18003e1e4  lea     r8, [rsp+110h+var_D8]
0x18003e1e9  lea     rdx, [rbp+57h+pv]
0x18003e1ed  mov     rax, [rcx]
0x18003e1f0  mov     rax, [rax+30h]
0x18003e1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1f9  mov     ebx, eax
0x18003e1fb  test    eax, eax
0x18003e1fd  js      loc_18003E2E2
0x18003e203  mov     r9d, [rsp+110h+var_D8]
0x18003e208  mov     edi, r12d
0x18003e20b  test    r9d, r9d
0x18003e20e  jle     short loc_18003E282
0x18003e210  test    ebx, ebx
0x18003e212  js      loc_18003E2BE
0x18003e218  mov     r8, [rbp+57h+pv]
0x18003e21c  movsxd  rax, edi
0x18003e21f  lea     rcx, [rax+rax*4]
0x18003e223  add     rcx, rcx
0x18003e226  mov     edx, [r8+rcx*8+10h]
0x18003e22b  cmp     edx, 1
0x18003e22e  jz      short loc_18003E277
0x18003e230  cmp     edx, 7FFFh
0x18003e236  jz      short loc_18003E277
0x18003e238  lea     eax, [rdx-5]
0x18003e23b  cmp     eax, 1
0x18003e23e  jbe     short loc_18003E277
0x18003e240  test    edx, edx
0x18003e242  jnz     short loc_18003E252
0x18003e244  cmp     [r8+rcx*8+18h], r12
0x18003e249  jnz     short loc_18003E252
0x18003e24b  cmp     [r8+rcx*8+20h], r12
0x18003e250  jz      short loc_18003E277
0x18003e252  mov     r9d, esi
0x18003e255  lea     r8, aConvertdisksty; "ConvertDiskStyle: Conversion failed sin"...
0x18003e25c  mov     edx, 2000000h
0x18003e261  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18003e268  mov     ebx, 80004005h
0x18003e26d  call    LibLog
0x18003e272  mov     r9d, [rsp+110h+var_D8]
0x18003e277  inc     edi
0x18003e279  cmp     edi, r9d
0x18003e27c  jl      short loc_18003E210
0x18003e27e  test    ebx, ebx
0x18003e280  js      short loc_18003E2BE
0x18003e282  mov     rcx, [rsp+110h+var_E0]
0x18003e287  mov     edx, r15d
0x18003e28a  mov     rax, [rcx]
0x18003e28d  mov     rax, [rax+38h]
0x18003e291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e296  mov     ebx, eax
0x18003e298  test    eax, eax
0x18003e29a  js      short loc_18003E2BE
0x18003e29c  mov     r9d, esi
0x18003e29f  mov     [rsp+110h+var_F0], r14
0x18003e2a4  lea     r8, aConvertdisksty_0; "ConvertDiskStyle: Successfully converte"...
0x18003e2ab  mov     edx, 4000000h
0x18003e2b0  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18003e2b7  call    LibLog
0x18003e2bc  jmp     short loc_18003E2E2
0x18003e2be  mov     dword ptr [rsp+110h+var_E8], ebx
0x18003e2c2  lea     r8, aConvertdisksty_2; "ConvertDiskStyle: Failed to convert dis"...
0x18003e2c9  mov     r9d, esi
0x18003e2cc  mov     [rsp+110h+var_F0], r14
0x18003e2d1  mov     edx, 2000000h
0x18003e2d6  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18003e2dd  call    LibLog
0x18003e2e2  mov     rcx, [rbp+57h+pv]; pv
0x18003e2e6  test    rcx, rcx
0x18003e2e9  jz      short loc_18003E2F8
0x18003e2eb  call    cs:__imp_CoTaskMemFree
0x18003e2f1  jmp     short loc_18003E2F8
0x18003e2f3  mov     ebx, 1
0x18003e2f8  mov     rcx, [rbp+57h+var_68]; pv
0x18003e2fc  test    rcx, rcx
0x18003e2ff  jz      short loc_18003E30B
0x18003e301  call    cs:__imp_CoTaskMemFree
0x18003e307  mov     [rbp+57h+var_68], r12
0x18003e30b  mov     rcx, [rbp+57h+var_60]; pv
0x18003e30f  test    rcx, rcx
0x18003e312  jz      short loc_18003E31E
0x18003e314  call    cs:__imp_CoTaskMemFree
0x18003e31a  mov     [rbp+57h+var_60], r12
0x18003e31e  mov     rcx, [rbp+57h+var_58]; pv
0x18003e322  test    rcx, rcx
0x18003e325  jz      short loc_18003E331
0x18003e327  call    cs:__imp_CoTaskMemFree
0x18003e32d  mov     [rbp+57h+var_58], r12
0x18003e331  mov     rcx, [rbp+57h+var_50]; pv
0x18003e335  test    rcx, rcx
0x18003e338  jz      short loc_18003E344
0x18003e33a  call    cs:__imp_CoTaskMemFree
0x18003e340  mov     [rbp+57h+var_50], r12
0x18003e344  mov     rcx, [rbp+57h+var_48]; pv
0x18003e348  test    rcx, rcx
0x18003e34b  jz      short loc_18003E353
0x18003e34d  call    cs:__imp_CoTaskMemFree
0x18003e353  mov     rdi, [rsp+110h+var_E0]
0x18003e358  jmp     short loc_18003E35F
0x18003e35a  mov     ebx, 80070057h
0x18003e35f  mov     rcx, [rbp+57h+var_D0]
0x18003e363  test    rcx, rcx
0x18003e366  jz      short loc_18003E37D
0x18003e368  mov     rax, [rcx]
0x18003e36b  mov     rax, [rax+10h]
0x18003e36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e374  mov     rdi, [rsp+110h+var_E0]
0x18003e379  mov     [rbp+57h+var_D0], r12
0x18003e37d  test    rdi, rdi
0x18003e380  jz      short loc_18003E391
0x18003e382  mov     rax, [rdi]
0x18003e385  mov     rcx, rdi
0x18003e388  mov     rax, [rax+10h]
0x18003e38c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e391  mov     eax, ebx
0x18003e393  jmp     short loc_18003E39A
0x18003e395  mov     eax, 80070057h
0x18003e39a  mov     rcx, [rbp+57h+var_40]
0x18003e39e  xor     rcx, rsp; StackCookie
0x18003e3a1  call    __security_check_cookie
0x18003e3a6  add     rsp, 0E0h
0x18003e3ad  pop     r15
0x18003e3af  pop     r14
0x18003e3b1  pop     r12
0x18003e3b3  pop     rdi
0x18003e3b4  pop     rsi
0x18003e3b5  pop     rbx
0x18003e3b6  pop     rbp
0x18003e3b7  retn
```
