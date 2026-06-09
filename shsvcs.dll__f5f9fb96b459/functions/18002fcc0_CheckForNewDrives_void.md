# CheckForNewDrives(void)

- ea: `0x18002fcc0`
- end: `0x18003004c`
- name: `?CheckForNewDrives@@YAXXZ`
- size: `908`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e720`

## callees

- `0x18002faec`
- `0x18002fcc0`
- `0x180030054`
- `0x1800301a8`
- `0x180032c6a`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003002c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18003002c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ff95`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002fcf5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002fcf5`

## pseudocode

```c
void CheckForNewDrives(void)
{
  struct IVdsService *v0; // rdi
  int v1; // eax
  int v2; // ebx
  int v3; // ebx
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  struct IVdsDisk *v7; // [rsp+30h] [rbp-D0h] BYREF
  struct IVdsService *v8; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v9; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v13; // [rsp+60h] [rbp-A0h] BYREF
  int v14; // [rsp+68h] [rbp-98h] BYREF
  int v15; // [rsp+6Ch] [rbp-94h] BYREF
  int v16; // [rsp+70h] [rbp-90h] BYREF
  __int64 v17; // [rsp+78h] [rbp-88h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v19[28]; // [rsp+90h] [rbp-70h] BYREF
  int v20; // [rsp+ACh] [rbp-54h]
  int v21; // [rsp+D0h] [rbp-30h]
  unsigned int v22; // [rsp+D4h] [rbp-2Ch]
  LPVOID pv; // [rsp+E8h] [rbp-18h]
  LPVOID v24; // [rsp+F0h] [rbp-10h]
  LPVOID v25; // [rsp+F8h] [rbp-8h]
  LPVOID v26; // [rsp+100h] [rbp+0h]
  LPVOID v27; // [rsp+108h] [rbp+8h]

  if ( (unsigned int)CheckForNewDrivesNoVds() && CoInitializeEx(0, 4u) >= 0 )
  {
    v8 = 0;
    if ( (int)ConnectToVDS(&v8) >= 0 )
    {
      v0 = v8;
      v18 = 0;
      if ( ((int (__fastcall *)(struct IVdsService *, __int64, __int64 *))v8->lpVtbl->QueryProviders)(v8, 1, &v18) >= 0 )
      {
        do
        {
          v14 = 0;
          v9 = 0;
          v1 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v18 + 24LL))(
                 v18,
                 1,
                 &v9,
                 &v14);
          if ( v1 < 0 )
            break;
          if ( v1 == 1 )
            break;
          v10 = 0;
          v2 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(
                 v9,
                 &GUID_9aa58360_ce33_4f92_b658_ed24b14425b8,
                 &v10);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          v9 = 0;
          if ( v2 < 0 )
            break;
          v8 = 0;
          v3 = (*(__int64 (__fastcall **)(__int64, struct IVdsService **))(*(_QWORD *)v10 + 24LL))(v10, &v8);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          v10 = 0;
          if ( v3 < 0 )
            break;
          do
          {
            v11 = 0;
            v15 = 0;
            v4 = ((__int64 (__fastcall *)(struct IVdsService *, __int64, __int64 *, int *))v8->lpVtbl->IsServiceReady)(
                   v8,
                   1,
                   &v11,
                   &v15);
            v5 = v4;
            if ( v4 < 0 )
              break;
            if ( v4 == 1 )
              break;
            v12 = 0;
            v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v11)(
                   v11,
                   &GUID_3b69d7f5_9d94_4648_91ca_79939ba263bf,
                   &v12);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            v11 = 0;
            if ( v5 < 0 )
              break;
            v17 = 0;
            v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 48LL))(v12, &v17);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            v12 = 0;
            if ( v5 < 0 )
              break;
            while ( 1 )
            {
              v13 = 0;
              v16 = 0;
              v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v17 + 24LL))(
                     v17,
                     1,
                     &v13,
                     &v16);
              v5 = v6;
              if ( v6 < 0 )
                break;
              if ( v6 == 1 )
                break;
              v7 = 0;
              v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IVdsDisk **))v13)(
                     v13,
                     &GUID_07e5c822_f00c_47a1_8fce_b244da56fd06,
                     &v7);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
              v13 = 0;
              if ( v5 < 0 )
                break;
              memset_0(v19, 0, 0x80u);
              if ( ((int (__fastcall *)(struct IVdsDisk *, _BYTE *))v7->lpVtbl->GetProperties)(v7, v19) >= 0 )
              {
                CoTaskMemFree(pv);
                pv = 0;
                CoTaskMemFree(v25);
                v25 = 0;
                CoTaskMemFree(v26);
                v26 = 0;
                CoTaskMemFree(v27);
                v27 = 0;
                CoTaskMemFree(v24);
                v24 = 0;
                if ( v20 == 7 && v22 <= 1 && ((unsigned int)(v21 - 1) <= 2 || v21 == 11) )
                  CheckDiskAndCreatePartitionIfNessecary(v7);
              }
              ((void (__fastcall *)(struct IVdsDisk *))v7->lpVtbl->Release)(v7);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          }
          while ( v5 >= 0 );
          ((void (__fastcall *)(struct IVdsService *))v8->lpVtbl->Release)(v8);
        }
        while ( v5 >= 0 );
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      ((void (__fastcall *)(struct IVdsService *))v0->lpVtbl->Release)(v0);
    }
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x18002fcc0  push    rbp
0x18002fcc2  push    rbx
0x18002fcc3  push    rsi
0x18002fcc4  push    rdi
0x18002fcc5  push    r14
0x18002fcc7  lea     rbp, [rsp-20h]
0x18002fccc  sub     rsp, 120h
0x18002fcd3  mov     rax, cs:__security_cookie
0x18002fcda  xor     rax, rsp
0x18002fcdd  mov     [rbp+40h+var_30], rax
0x18002fce1  call    ?CheckForNewDrivesNoVds@@YAHXZ; CheckForNewDrivesNoVds(void)
0x18002fce6  xor     esi, esi
0x18002fce8  test    eax, eax
0x18002fcea  jz      loc_180030032
0x18002fcf0  lea     edx, [rsi+4]; dwCoInit
0x18002fcf3  xor     ecx, ecx; pvReserved
0x18002fcf5  call    cs:__imp_CoInitializeEx
0x18002fcfb  test    eax, eax
0x18002fcfd  js      loc_180030032
0x18002fd03  lea     rcx, [rsp+140h+var_108]; struct IVdsService **
0x18002fd08  mov     [rsp+140h+var_108], rsi
0x18002fd0d  call    ?ConnectToVDS@@YAJPEAPEAUIVdsService@@@Z; ConnectToVDS(IVdsService * *)
0x18002fd12  test    eax, eax
0x18002fd14  js      loc_18003002C
0x18002fd1a  mov     rdi, [rsp+140h+var_108]
0x18002fd1f  lea     r14d, [rsi+1]
0x18002fd23  mov     [rbp+40h+var_C0], rsi
0x18002fd27  lea     r8, [rbp+40h+var_C0]
0x18002fd2b  mov     edx, r14d
0x18002fd2e  mov     rcx, rdi
0x18002fd31  mov     rax, [rdi]
0x18002fd34  mov     rax, [rax+30h]
0x18002fd38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd3d  test    eax, eax
0x18002fd3f  js      loc_18003001D
0x18002fd45  mov     rcx, [rbp+40h+var_C0]
0x18002fd49  lea     r9, [rsp+140h+var_D8]
0x18002fd4e  mov     [rsp+140h+var_D8], esi
0x18002fd52  lea     r8, [rsp+140h+var_100]
0x18002fd57  mov     [rsp+140h+var_100], rsi
0x18002fd5c  mov     edx, r14d
0x18002fd5f  mov     rax, [rcx]
0x18002fd62  mov     rax, [rax+18h]
0x18002fd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd6b  test    eax, eax
0x18002fd6d  js      loc_18003000D
0x18002fd73  cmp     eax, r14d
0x18002fd76  jz      loc_18003000D
0x18002fd7c  mov     rcx, [rsp+140h+var_100]
0x18002fd81  lea     r8, [rsp+140h+var_F8]
0x18002fd86  mov     [rsp+140h+var_F8], rsi
0x18002fd8b  lea     rdx, _GUID_9aa58360_ce33_4f92_b658_ed24b14425b8
0x18002fd92  mov     rax, [rcx]
0x18002fd95  mov     rax, [rax]
0x18002fd98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd9d  mov     rdx, [rsp+140h+var_100]
0x18002fda2  mov     ebx, eax
0x18002fda4  mov     rcx, [rdx]
0x18002fda7  mov     rax, [rcx+10h]
0x18002fdab  mov     rcx, rdx
0x18002fdae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdb3  mov     [rsp+140h+var_100], rsi
0x18002fdb8  test    ebx, ebx
0x18002fdba  js      loc_18003000D
0x18002fdc0  mov     rcx, [rsp+140h+var_F8]
0x18002fdc5  lea     rdx, [rsp+140h+var_108]
0x18002fdca  mov     [rsp+140h+var_108], rsi
0x18002fdcf  mov     rax, [rcx]
0x18002fdd2  mov     rax, [rax+18h]
0x18002fdd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fddb  mov     rdx, [rsp+140h+var_F8]
0x18002fde0  mov     ebx, eax
0x18002fde2  mov     rcx, [rdx]
0x18002fde5  mov     rax, [rcx+10h]
0x18002fde9  mov     rcx, rdx
0x18002fdec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdf1  mov     [rsp+140h+var_F8], rsi
0x18002fdf6  test    ebx, ebx
0x18002fdf8  js      loc_18003000D
0x18002fdfe  mov     rcx, [rsp+140h+var_108]
0x18002fe03  lea     r9, [rsp+140h+var_D4]
0x18002fe08  mov     [rsp+140h+var_F0], rsi
0x18002fe0d  lea     r8, [rsp+140h+var_F0]
0x18002fe12  mov     [rsp+140h+var_D4], esi
0x18002fe16  mov     edx, r14d
0x18002fe19  mov     rax, [rcx]
0x18002fe1c  mov     rax, [rax+18h]
0x18002fe20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe25  mov     ebx, eax
0x18002fe27  test    eax, eax
0x18002fe29  js      loc_18002FFF4
0x18002fe2f  cmp     eax, r14d
0x18002fe32  jz      loc_18002FFF4
0x18002fe38  mov     rcx, [rsp+140h+var_F0]
0x18002fe3d  lea     r8, [rsp+140h+var_E8]
0x18002fe42  mov     [rsp+140h+var_E8], rsi
0x18002fe47  lea     rdx, _GUID_3b69d7f5_9d94_4648_91ca_79939ba263bf
0x18002fe4e  mov     rax, [rcx]
0x18002fe51  mov     rax, [rax]
0x18002fe54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe59  mov     rcx, [rsp+140h+var_F0]
0x18002fe5e  mov     ebx, eax
0x18002fe60  mov     rax, [rcx]
0x18002fe63  mov     rax, [rax+10h]
0x18002fe67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe6c  mov     [rsp+140h+var_F0], rsi
0x18002fe71  test    ebx, ebx
0x18002fe73  js      loc_18002FFF4
0x18002fe79  mov     rcx, [rsp+140h+var_E8]
0x18002fe7e  lea     rdx, [rsp+140h+var_C8]
0x18002fe83  mov     [rsp+140h+var_C8], rsi
0x18002fe88  mov     rax, [rcx]
0x18002fe8b  mov     rax, [rax+30h]
0x18002fe8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe94  mov     rcx, [rsp+140h+var_E8]
0x18002fe99  mov     ebx, eax
0x18002fe9b  mov     rax, [rcx]
0x18002fe9e  mov     rax, [rax+10h]
0x18002fea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fea7  mov     [rsp+140h+var_E8], rsi
0x18002feac  test    ebx, ebx
0x18002feae  js      loc_18002FFF4
0x18002feb4  mov     rcx, [rsp+140h+var_C8]
0x18002feb9  lea     r9, [rsp+140h+var_D0]
0x18002febe  mov     [rsp+140h+var_E0], rsi
0x18002fec3  lea     r8, [rsp+140h+var_E0]
0x18002fec8  mov     [rsp+140h+var_D0], esi
0x18002fecc  mov     edx, r14d
0x18002fecf  mov     rax, [rcx]
0x18002fed2  mov     rax, [rax+18h]
0x18002fed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fedb  mov     ebx, eax
0x18002fedd  test    eax, eax
0x18002fedf  js      loc_18002FFDB
0x18002fee5  cmp     eax, r14d
0x18002fee8  jz      loc_18002FFDB
0x18002feee  mov     rcx, [rsp+140h+var_E0]
0x18002fef3  lea     r8, [rsp+140h+var_110]
0x18002fef8  mov     [rsp+140h+var_110], rsi
0x18002fefd  lea     rdx, _GUID_07e5c822_f00c_47a1_8fce_b244da56fd06
0x18002ff04  mov     rax, [rcx]
0x18002ff07  mov     rax, [rax]
0x18002ff0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff0f  mov     rcx, [rsp+140h+var_E0]
0x18002ff14  mov     ebx, eax
0x18002ff16  mov     rax, [rcx]
0x18002ff19  mov     rax, [rax+10h]
0x18002ff1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff22  mov     [rsp+140h+var_E0], rsi
0x18002ff27  test    ebx, ebx
0x18002ff29  js      loc_18002FFDB
0x18002ff2f  xor     edx, edx; Val
0x18002ff31  lea     rcx, [rbp+40h+var_B0]; void *
0x18002ff35  mov     r8d, 80h; Size
0x18002ff3b  call    memset_0
0x18002ff40  mov     rcx, [rsp+140h+var_110]
0x18002ff45  lea     rdx, [rbp+40h+var_B0]
0x18002ff49  mov     rax, [rcx]
0x18002ff4c  mov     rax, [rax+18h]
0x18002ff50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff55  test    eax, eax
0x18002ff57  js      short loc_18002FFC5
0x18002ff59  mov     rcx, [rbp+40h+pv]; pv
0x18002ff5d  call    cs:__imp_CoTaskMemFree
0x18002ff63  mov     rcx, [rbp+40h+var_48]; pv
0x18002ff67  mov     [rbp+40h+pv], rsi
0x18002ff6b  call    cs:__imp_CoTaskMemFree
0x18002ff71  mov     rcx, [rbp+40h+var_40]; pv
0x18002ff75  mov     [rbp+40h+var_48], rsi
0x18002ff79  call    cs:__imp_CoTaskMemFree
0x18002ff7f  mov     rcx, [rbp+40h+var_38]; pv
0x18002ff83  mov     [rbp+40h+var_40], rsi
0x18002ff87  call    cs:__imp_CoTaskMemFree
0x18002ff8d  mov     rcx, [rbp+40h+var_50]; pv
0x18002ff91  mov     [rbp+40h+var_38], rsi
0x18002ff95  call    cs:__imp_CoTaskMemFree
0x18002ff9b  cmp     [rbp+40h+var_94], 7
0x18002ff9f  mov     [rbp+40h+var_50], rsi
0x18002ffa3  jnz     short loc_18002FFC5
0x18002ffa5  cmp     [rbp+40h+var_6C], r14d
0x18002ffa9  ja      short loc_18002FFC5
0x18002ffab  mov     ecx, [rbp+40h+var_70]
0x18002ffae  lea     eax, [rcx-1]
0x18002ffb1  cmp     eax, 2
0x18002ffb4  jbe     short loc_18002FFBB
0x18002ffb6  cmp     ecx, 0Bh
0x18002ffb9  jnz     short loc_18002FFC5
0x18002ffbb  mov     rcx, [rsp+140h+var_110]; struct IVdsDisk *
0x18002ffc0  call    ?CheckDiskAndCreatePartitionIfNessecary@@YAXPEAUIVdsDisk@@@Z; CheckDiskAndCreatePartitionIfNessecary(IVdsDisk *)
0x18002ffc5  mov     rcx, [rsp+140h+var_110]
0x18002ffca  mov     rax, [rcx]
0x18002ffcd  mov     rax, [rax+10h]
0x18002ffd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffd6  jmp     loc_18002FEB4
0x18002ffdb  mov     rcx, [rsp+140h+var_C8]
0x18002ffe0  mov     rax, [rcx]
0x18002ffe3  mov     rax, [rax+10h]
0x18002ffe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffec  test    ebx, ebx
0x18002ffee  jns     loc_18002FDFE
0x18002fff4  mov     rcx, [rsp+140h+var_108]
0x18002fff9  mov     rax, [rcx]
0x18002fffc  mov     rax, [rax+10h]
0x180030000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030005  test    ebx, ebx
0x180030007  jns     loc_18002FD45
0x18003000d  mov     rcx, [rbp+40h+var_C0]
0x180030011  mov     rax, [rcx]
0x180030014  mov     rax, [rax+10h]
0x180030018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003001d  mov     rax, [rdi]
0x180030020  mov     rcx, rdi
0x180030023  mov     rax, [rax+10h]
0x180030027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003002c  call    cs:__imp_CoUninitialize
0x180030032  mov     rcx, [rbp+40h+var_30]
0x180030036  xor     rcx, rsp; StackCookie
0x180030039  call    __security_check_cookie
0x18003003e  add     rsp, 120h
0x180030045  pop     r14
0x180030047  pop     rdi
0x180030048  pop     rsi
0x180030049  pop     rbx
0x18003004a  pop     rbp
0x18003004b  retn
```
