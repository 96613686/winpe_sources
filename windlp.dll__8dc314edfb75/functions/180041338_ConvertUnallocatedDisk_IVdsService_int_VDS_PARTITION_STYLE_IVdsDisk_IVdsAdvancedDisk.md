# ConvertUnallocatedDisk(IVdsService *,int,_VDS_PARTITION_STYLE,IVdsDisk * *,IVdsAdvancedDisk * *)

- ea: `0x180041338`
- end: `0x180041585`
- name: `?ConvertUnallocatedDisk@@YAJPEAUIVdsService@@HW4_VDS_PARTITION_STYLE@@PEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@@Z`
- size: `589`
- prototype: `__int64 __fastcall(struct IVdsService *, int, unsigned int, struct IVdsDisk **, struct IVdsAdvancedDisk **)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003e030`
- `0x18003e3c0`

## callees

- `0x180039394`
- `0x180041338`
- `0x1800417a8`
- `0x180041d98`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800414f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041507`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004151a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004152d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041540`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800414f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041507`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004151a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004152d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041540`

## pseudocode

```c
__int64 __fastcall ConvertUnallocatedDisk(
        struct IVdsService *a1,
        int a2,
        unsigned int a3,
        struct IVdsDisk **a4,
        struct IVdsAdvancedDisk **a5)
{
  enum _VDS_PROVIDER_FLAG v9; // edx
  int Disk; // ebx
  __int64 v11; // rcx
  int Provider; // eax
  struct IVdsSwProvider *v13; // r14
  _QWORD v15[2]; // [rsp+30h] [rbp-A1h] BYREF
  struct IVdsSwProvider *v16[2]; // [rsp+40h] [rbp-91h] BYREF
  _OWORD v17[4]; // [rsp+50h] [rbp-81h] BYREF
  unsigned int v18; // [rsp+94h] [rbp-3Dh]
  LPVOID pv; // [rsp+A8h] [rbp-29h]
  LPVOID v20; // [rsp+B0h] [rbp-21h]
  LPVOID v21; // [rsp+B8h] [rbp-19h]
  LPVOID v22; // [rsp+C0h] [rbp-11h]
  LPVOID v23; // [rsp+C8h] [rbp-9h]

  v15[0] = 0;
  if ( a1 && a4 && *a4 )
  {
    Disk = ((__int64 (__fastcall *)(_QWORD, _QWORD *))(*a4)->lpVtbl->GetPack)(*a4, v15);
    if ( Disk == -2147212265 )
    {
      v11 = v15[0];
      if ( v15[0] )
        goto LABEL_34;
      v16[0] = 0;
      v15[0] = 0;
      Provider = GetProvider(a1, v9, v16);
      v13 = v16[0];
      Disk = Provider;
      if ( Provider >= 0 )
        Disk = ((__int64 (__fastcall *)(struct IVdsSwProvider *, _QWORD *))v16[0]->lpVtbl->CreatePack)(v16[0], v15);
      if ( v13 )
        ((void (__fastcall *)(struct IVdsSwProvider *))v13->lpVtbl->Release)(v13);
      if ( Disk >= 0 )
      {
        memset_0(v17, 0, 0x80u);
        Disk = ((__int64 (__fastcall *)(_QWORD, _OWORD *))(*a4)->lpVtbl->GetProperties)(*a4, v17);
        if ( Disk >= 0 )
        {
          if ( a3 - 1 > 1 )
          {
            a3 = v18;
            if ( !v18 )
              a3 = 1;
          }
          *(_OWORD *)v16 = v17[0];
          Disk = (*(__int64 (__fastcall **)(_QWORD, struct IVdsSwProvider **, _QWORD, _QWORD))(*(_QWORD *)v15[0] + 64LL))(
                   v15[0],
                   v16,
                   a3,
                   0);
          if ( Disk >= 0 )
          {
            LibLog(
              &g_VdsLibLog,
              0x4000000,
              L"ConvertUnallocatedDisk: Successfully added unallocated disk to a new basic pack");
            if ( *a4 )
              ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
            *a4 = 0;
            if ( a5 )
            {
              if ( *a5 )
                ((void (__fastcall *)(_QWORD))(*a5)->lpVtbl->Release)(*a5);
              *a5 = 0;
            }
            Disk = GetDisk(a1, a2, a4, a5, 0);
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( v20 )
          {
            CoTaskMemFree(v20);
            v20 = 0;
          }
          if ( v21 )
          {
            CoTaskMemFree(v21);
            v21 = 0;
          }
          if ( v22 )
          {
            CoTaskMemFree(v22);
            v22 = 0;
          }
          if ( v23 )
            CoTaskMemFree(v23);
        }
      }
    }
    v11 = v15[0];
    if ( !v15[0] )
      return (unsigned int)Disk;
LABEL_34:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    return (unsigned int)Disk;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180041338  push    rbp
0x18004133a  push    rbx
0x18004133b  push    rsi
0x18004133c  push    rdi
0x18004133d  push    r12
0x18004133f  push    r13
0x180041341  push    r14
0x180041343  push    r15
0x180041345  lea     rbp, [rsp-17h]
0x18004134a  sub     rsp, 0E8h
0x180041351  mov     rax, cs:__security_cookie
0x180041358  xor     rax, rsp
0x18004135b  mov     [rbp+4Fh+var_50], rax
0x18004135f  mov     r15, [rbp+4Fh+arg_20]
0x180041363  xor     r14d, r14d
0x180041366  mov     [rsp+120h+var_F0], r14
0x18004136b  mov     rdi, r9
0x18004136e  mov     esi, r8d
0x180041371  mov     r13d, edx
0x180041374  mov     r12, rcx
0x180041377  test    rcx, rcx
0x18004137a  jz      loc_180041560
0x180041380  test    r9, r9
0x180041383  jz      loc_180041560
0x180041389  mov     rcx, [r9]
0x18004138c  test    rcx, rcx
0x18004138f  jz      loc_180041560
0x180041395  mov     rax, [rcx]
0x180041398  lea     rdx, [rsp+120h+var_F0]
0x18004139d  mov     rax, [rax+20h]
0x1800413a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413a6  mov     ebx, eax
0x1800413a8  cmp     eax, 80042417h
0x1800413ad  jnz     loc_180041546
0x1800413b3  mov     rcx, [rsp+120h+var_F0]
0x1800413b8  test    rcx, rcx
0x1800413bb  jnz     loc_180041550
0x1800413c1  lea     r8, [rsp+120h+var_E0]; struct IVdsSwProvider **
0x1800413c6  mov     [rsp+120h+var_E0], r14
0x1800413cb  mov     rcx, r12; struct IVdsService *
0x1800413ce  mov     [rsp+120h+var_F0], r14
0x1800413d3  call    ?GetProvider@@YAJPEAUIVdsService@@W4_VDS_PROVIDER_FLAG@@PEAPEAUIVdsSwProvider@@@Z; GetProvider(IVdsService *,_VDS_PROVIDER_FLAG,IVdsSwProvider * *)
0x1800413d8  mov     r14, [rsp+120h+var_E0]
0x1800413dd  mov     ebx, eax
0x1800413df  test    eax, eax
0x1800413e1  js      short loc_1800413F9
0x1800413e3  mov     rax, [r14]
0x1800413e6  lea     rdx, [rsp+120h+var_F0]
0x1800413eb  mov     rcx, r14
0x1800413ee  mov     rax, [rax+20h]
0x1800413f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413f7  mov     ebx, eax
0x1800413f9  test    r14, r14
0x1800413fc  jz      short loc_18004140D
0x1800413fe  mov     rax, [r14]
0x180041401  mov     rcx, r14
0x180041404  mov     rax, [rax+10h]
0x180041408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004140d  xor     r14d, r14d
0x180041410  test    ebx, ebx
0x180041412  js      loc_180041546
0x180041418  xor     edx, edx; Val
0x18004141a  lea     rcx, [rsp+120h+var_D0]; void *
0x18004141f  mov     r8d, 80h; Size
0x180041425  call    memset_0
0x18004142a  mov     rcx, [rdi]
0x18004142d  lea     rdx, [rsp+120h+var_D0]
0x180041432  mov     rax, [rcx]
0x180041435  mov     rax, [rax+18h]
0x180041439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004143e  mov     ebx, eax
0x180041440  test    eax, eax
0x180041442  js      loc_180041546
0x180041448  lea     eax, [rsi-1]
0x18004144b  lea     ecx, [r14+1]
0x18004144f  cmp     eax, ecx
0x180041451  jbe     short loc_18004145B
0x180041453  mov     esi, [rbp+4Fh+var_8C]
0x180041456  test    esi, esi
0x180041458  cmovz   esi, ecx
0x18004145b  mov     rcx, [rsp+120h+var_F0]
0x180041460  lea     rdx, [rsp+120h+var_E0]
0x180041465  movaps  xmm0, [rsp+120h+var_D0]
0x18004146a  xor     r9d, r9d
0x18004146d  mov     r8d, esi
0x180041470  movdqu  xmmword ptr [rsp+120h+var_E0], xmm0
0x180041476  mov     rax, [rcx]
0x180041479  mov     rax, [rax+40h]
0x18004147d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041482  mov     ebx, eax
0x180041484  test    eax, eax
0x180041486  js      short loc_1800414EB
0x180041488  lea     r8, aConvertunalloc; "ConvertUnallocatedDisk: Successfully ad"...
0x18004148f  mov     edx, 4000000h
0x180041494  lea     rcx, ?g_VdsLibLog@@3U_LIBLOG_REGISTRATION@@A; _LIBLOG_REGISTRATION g_VdsLibLog
0x18004149b  call    LibLog
0x1800414a0  mov     rcx, [rdi]
0x1800414a3  test    rcx, rcx
0x1800414a6  jz      short loc_1800414B4
0x1800414a8  mov     rax, [rcx]
0x1800414ab  mov     rax, [rax+10h]
0x1800414af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414b4  mov     [rdi], r14
0x1800414b7  test    r15, r15
0x1800414ba  jz      short loc_1800414D3
0x1800414bc  mov     rcx, [r15]
0x1800414bf  test    rcx, rcx
0x1800414c2  jz      short loc_1800414D0
0x1800414c4  mov     rax, [rcx]
0x1800414c7  mov     rax, [rax+10h]
0x1800414cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414d0  mov     [r15], r14
0x1800414d3  mov     r9, r15; struct IVdsAdvancedDisk **
0x1800414d6  mov     [rsp+120h+var_100], r14; struct IVdsAdvancedDisk2 **
0x1800414db  mov     r8, rdi; struct IVdsDisk **
0x1800414de  mov     edx, r13d; int
0x1800414e1  mov     rcx, r12; struct IVdsService *
0x1800414e4  call    ?GetDisk@@YAJPEAUIVdsService@@HPEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@PEAPEAUIVdsAdvancedDisk2@@@Z; GetDisk(IVdsService *,int,IVdsDisk * *,IVdsAdvancedDisk * *,IVdsAdvancedDisk2 * *)
0x1800414e9  mov     ebx, eax
0x1800414eb  mov     rcx, [rbp+4Fh+pv]; pv
0x1800414ef  test    rcx, rcx
0x1800414f2  jz      short loc_1800414FE
0x1800414f4  call    cs:__imp_CoTaskMemFree
0x1800414fa  mov     [rbp+4Fh+pv], r14
0x1800414fe  mov     rcx, [rbp+4Fh+var_70]; pv
0x180041502  test    rcx, rcx
0x180041505  jz      short loc_180041511
0x180041507  call    cs:__imp_CoTaskMemFree
0x18004150d  mov     [rbp+4Fh+var_70], r14
0x180041511  mov     rcx, [rbp+4Fh+var_68]; pv
0x180041515  test    rcx, rcx
0x180041518  jz      short loc_180041524
0x18004151a  call    cs:__imp_CoTaskMemFree
0x180041520  mov     [rbp+4Fh+var_68], r14
0x180041524  mov     rcx, [rbp+4Fh+var_60]; pv
0x180041528  test    rcx, rcx
0x18004152b  jz      short loc_180041537
0x18004152d  call    cs:__imp_CoTaskMemFree
0x180041533  mov     [rbp+4Fh+var_60], r14
0x180041537  mov     rcx, [rbp+4Fh+var_58]; pv
0x18004153b  test    rcx, rcx
0x18004153e  jz      short loc_180041546
0x180041540  call    cs:__imp_CoTaskMemFree
0x180041546  mov     rcx, [rsp+120h+var_F0]
0x18004154b  test    rcx, rcx
0x18004154e  jz      short loc_18004155C
0x180041550  mov     rax, [rcx]
0x180041553  mov     rax, [rax+10h]
0x180041557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004155c  mov     eax, ebx
0x18004155e  jmp     short loc_180041565
0x180041560  mov     eax, 80070057h
0x180041565  mov     rcx, [rbp+4Fh+var_50]
0x180041569  xor     rcx, rsp; StackCookie
0x18004156c  call    __security_check_cookie
0x180041571  add     rsp, 0E8h
0x180041578  pop     r15
0x18004157a  pop     r14
0x18004157c  pop     r13
0x18004157e  pop     r12
0x180041580  pop     rdi
0x180041581  pop     rsi
0x180041582  pop     rbx
0x180041583  pop     rbp
0x180041584  retn
```
