# SetPartitionActive(IVdsService *,int,unsigned __int64)

- ea: `0x180040c1c`
- end: `0x180040e3d`
- name: `?SetPartitionActive@@YAJPEAUIVdsService@@H_K@Z`
- size: `545`
- prototype: `__int64 __fastcall(struct IVdsService *, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800244d4`

## callees

- `0x180040c1c`
- `0x1800417a8`
- `0x18004248c`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040dac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040dbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040d99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040dac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040dbf`

## pseudocode

```c
__int64 __fastcall SetPartitionActive(struct IVdsService *a1, int a2, __int64 a3)
{
  int Disk; // ebx
  struct IVdsDiskVtbl *lpVtbl; // rax
  int v6; // edi
  struct IVdsDisk *v7; // rcx
  struct IVdsAdvancedDisk *v9; // [rsp+30h] [rbp-89h] BYREF
  struct IVdsDisk *v10; // [rsp+38h] [rbp-81h] BYREF
  int v11; // [rsp+40h] [rbp-79h] BYREF
  struct IVdsPack *v12[2]; // [rsp+48h] [rbp-71h] BYREF
  int v13; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v14[64]; // [rsp+64h] [rbp-55h] BYREF
  int v15; // [rsp+A4h] [rbp-15h]
  LPVOID pv; // [rsp+B8h] [rbp-1h]
  LPVOID v17; // [rsp+C0h] [rbp+7h]
  LPVOID v18; // [rsp+C8h] [rbp+Fh]
  LPVOID v19; // [rsp+D0h] [rbp+17h]
  LPVOID v20; // [rsp+D8h] [rbp+1Fh]

  v10 = 0;
  v9 = 0;
  if ( !a1 || a2 < 0 || !a3 )
    return 2147942487LL;
  Disk = GetDisk(a1, a2, &v10, &v9, 0);
  if ( Disk >= 0 )
  {
    if ( v10 && v9 )
    {
      v12[0] = 0;
      lpVtbl = v10->lpVtbl;
      v11 = 0;
      v6 = ((__int64 (__fastcall *)(struct IVdsDisk *, struct IVdsPack **))lpVtbl->GetPack)(v10, v12);
      if ( v6 >= 0 )
      {
        if ( v12[0] )
        {
          v6 = IsPackDynamic(v12[0], &v11);
          if ( v12[0] )
            ((void (__fastcall *)(struct IVdsPack *))v12[0]->lpVtbl->Release)(v12[0]);
        }
      }
      if ( v6 < 0 || v11 )
      {
        if ( v6 >= 0 )
          v6 = -2147467259;
        Disk = v6;
      }
      else
      {
        v13 = 0;
        memset_0(v14, 0, 0x7Cu);
        Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, int *))v10->lpVtbl->GetProperties)(v10, &v13);
        if ( Disk >= 0 )
        {
          if ( v15 == 1 )
          {
            *(_OWORD *)v12 = 0;
            LOBYTE(v12[1]) = 1;
            LODWORD(v12[0]) = 1;
            Disk = ((__int64 (__fastcall *)(struct IVdsAdvancedDisk *, __int64, struct IVdsPack **))v9->lpVtbl->ChangeAttributes)(
                     v9,
                     a3,
                     v12);
          }
          else
          {
            Disk = -2147467259;
          }
        }
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v17 )
        {
          CoTaskMemFree(v17);
          v17 = 0;
        }
        if ( v18 )
        {
          CoTaskMemFree(v18);
          v18 = 0;
        }
        if ( v19 )
        {
          CoTaskMemFree(v19);
          v19 = 0;
        }
        if ( v20 )
          CoTaskMemFree(v20);
      }
      v7 = v10;
      if ( v9 )
      {
        ((void (__fastcall *)(struct IVdsAdvancedDisk *))v9->lpVtbl->Release)(v9);
        v7 = v10;
        v9 = 0;
      }
      if ( v7 )
        ((void (__fastcall *)(struct IVdsDisk *))v7->lpVtbl->Release)(v7);
    }
    else
    {
      return (unsigned int)-2147024883;
    }
  }
  return (unsigned int)Disk;
}

```

## disassembly

```asm
0x180040c1c  push    rbp
0x180040c1e  push    rbx
0x180040c1f  push    rsi
0x180040c20  push    rdi
0x180040c21  push    r14
0x180040c23  lea     rbp, [rsp-37h]
0x180040c28  sub     rsp, 0F0h
0x180040c2f  mov     rax, cs:__security_cookie
0x180040c36  xor     rax, rsp
0x180040c39  mov     [rbp+57h+var_30], rax
0x180040c3d  xor     r14d, r14d
0x180040c40  mov     rsi, r8
0x180040c43  mov     [rsp+110h+var_D8], r14
0x180040c48  mov     [rsp+110h+var_E0], r14
0x180040c4d  test    rcx, rcx
0x180040c50  jz      loc_180040E1E
0x180040c56  test    edx, edx
0x180040c58  js      loc_180040E1E
0x180040c5e  test    r8, r8
0x180040c61  jz      loc_180040E1E
0x180040c67  lea     r9, [rsp+110h+var_E0]; struct IVdsAdvancedDisk **
0x180040c6c  mov     [rsp+110h+var_F0], r14; struct IVdsAdvancedDisk2 **
0x180040c71  lea     r8, [rsp+110h+var_D8]; struct IVdsDisk **
0x180040c76  call    ?GetDisk@@YAJPEAUIVdsService@@HPEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@PEAPEAUIVdsAdvancedDisk2@@@Z; GetDisk(IVdsService *,int,IVdsDisk * *,IVdsAdvancedDisk * *,IVdsAdvancedDisk2 * *)
0x180040c7b  mov     ebx, eax
0x180040c7d  test    eax, eax
0x180040c7f  js      loc_180040E1A
0x180040c85  mov     rcx, [rsp+110h+var_D8]
0x180040c8a  test    rcx, rcx
0x180040c8d  jz      loc_180040E15
0x180040c93  mov     rdx, [rsp+110h+var_E0]
0x180040c98  test    rdx, rdx
0x180040c9b  jz      loc_180040E15
0x180040ca1  mov     [rbp+57h+var_C8], r14
0x180040ca5  test    rcx, rcx
0x180040ca8  jz      loc_180040DDF
0x180040cae  mov     rax, [rcx]
0x180040cb1  lea     rdx, [rbp+57h+var_C8]
0x180040cb5  mov     [rbp+57h+var_D0], r14d
0x180040cb9  mov     rax, [rax+20h]
0x180040cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cc2  mov     edi, eax
0x180040cc4  test    eax, eax
0x180040cc6  js      short loc_180040CF1
0x180040cc8  mov     rcx, [rbp+57h+var_C8]; struct IVdsPack *
0x180040ccc  test    rcx, rcx
0x180040ccf  jz      short loc_180040CF1
0x180040cd1  lea     rdx, [rbp+57h+var_D0]; int *
0x180040cd5  call    ?IsPackDynamic@@YAJPEAUIVdsPack@@PEAH@Z; IsPackDynamic(IVdsPack *,int *)
0x180040cda  mov     rcx, [rbp+57h+var_C8]
0x180040cde  mov     edi, eax
0x180040ce0  test    rcx, rcx
0x180040ce3  jz      short loc_180040CF1
0x180040ce5  mov     rax, [rcx]
0x180040ce8  mov     rax, [rax+10h]
0x180040cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cf1  test    edi, edi
0x180040cf3  js      loc_180040DD1
0x180040cf9  cmp     [rbp+57h+var_D0], r14d
0x180040cfd  jnz     loc_180040DD1
0x180040d03  xor     edx, edx; Val
0x180040d05  mov     [rbp+57h+var_B0], r14d
0x180040d09  lea     rcx, [rbp+57h+var_AC]; void *
0x180040d0d  lea     r8d, [rdx+7Ch]; Size
0x180040d11  call    memset_0
0x180040d16  mov     rcx, [rsp+110h+var_D8]
0x180040d1b  lea     rdx, [rbp+57h+var_B0]
0x180040d1f  mov     rax, [rcx]
0x180040d22  mov     rax, [rax+18h]
0x180040d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d2b  mov     ebx, eax
0x180040d2d  test    eax, eax
0x180040d2f  js      short loc_180040D6A
0x180040d31  cmp     [rbp+57h+var_6C], 1
0x180040d35  jnz     short loc_180040D65
0x180040d37  mov     rcx, [rsp+110h+var_E0]
0x180040d3c  lea     r8, [rbp+57h+var_C8]
0x180040d40  xorps   xmm0, xmm0
0x180040d43  mov     rdx, rsi
0x180040d46  movups  xmmword ptr [rbp+57h+var_C8], xmm0
0x180040d4a  mov     byte ptr [rbp+57h+var_C8+8], 1
0x180040d4e  mov     dword ptr [rbp+57h+var_C8], 1
0x180040d55  mov     rax, [rcx]
0x180040d58  mov     rax, [rax+38h]
0x180040d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d61  mov     ebx, eax
0x180040d63  jmp     short loc_180040D6A
0x180040d65  mov     ebx, 80004005h
0x180040d6a  mov     rcx, [rbp+57h+pv]; pv
0x180040d6e  test    rcx, rcx
0x180040d71  jz      short loc_180040D7D
0x180040d73  call    cs:__imp_CoTaskMemFree
0x180040d79  mov     [rbp+57h+pv], r14
0x180040d7d  mov     rcx, [rbp+57h+var_50]; pv
0x180040d81  test    rcx, rcx
0x180040d84  jz      short loc_180040D90
0x180040d86  call    cs:__imp_CoTaskMemFree
0x180040d8c  mov     [rbp+57h+var_50], r14
0x180040d90  mov     rcx, [rbp+57h+var_48]; pv
0x180040d94  test    rcx, rcx
0x180040d97  jz      short loc_180040DA3
0x180040d99  call    cs:__imp_CoTaskMemFree
0x180040d9f  mov     [rbp+57h+var_48], r14
0x180040da3  mov     rcx, [rbp+57h+var_40]; pv
0x180040da7  test    rcx, rcx
0x180040daa  jz      short loc_180040DB6
0x180040dac  call    cs:__imp_CoTaskMemFree
0x180040db2  mov     [rbp+57h+var_40], r14
0x180040db6  mov     rcx, [rbp+57h+var_38]; pv
0x180040dba  test    rcx, rcx
0x180040dbd  jz      short loc_180040DC5
0x180040dbf  call    cs:__imp_CoTaskMemFree
0x180040dc5  mov     rcx, [rsp+110h+var_D8]
0x180040dca  mov     rdx, [rsp+110h+var_E0]
0x180040dcf  jmp     short loc_180040DE4
0x180040dd1  mov     ebx, 80004005h
0x180040dd6  test    edi, edi
0x180040dd8  cmovns  edi, ebx
0x180040ddb  mov     ebx, edi
0x180040ddd  jmp     short loc_180040DC5
0x180040ddf  mov     ebx, 80070057h
0x180040de4  test    rdx, rdx
0x180040de7  jz      short loc_180040E02
0x180040de9  mov     rax, [rdx]
0x180040dec  mov     rcx, rdx
0x180040def  mov     rax, [rax+10h]
0x180040df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040df8  mov     rcx, [rsp+110h+var_D8]
0x180040dfd  mov     [rsp+110h+var_E0], r14
0x180040e02  test    rcx, rcx
0x180040e05  jz      short loc_180040E1A
0x180040e07  mov     rax, [rcx]
0x180040e0a  mov     rax, [rax+10h]
0x180040e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e13  jmp     short loc_180040E1A
0x180040e15  mov     ebx, 8007000Dh
0x180040e1a  mov     eax, ebx
0x180040e1c  jmp     short loc_180040E23
0x180040e1e  mov     eax, 80070057h
0x180040e23  mov     rcx, [rbp+57h+var_30]
0x180040e27  xor     rcx, rsp; StackCookie
0x180040e2a  call    __security_check_cookie
0x180040e2f  add     rsp, 0F0h
0x180040e36  pop     r14
0x180040e38  pop     rdi
0x180040e39  pop     rsi
0x180040e3a  pop     rbx
0x180040e3b  pop     rbp
0x180040e3c  retn
```
