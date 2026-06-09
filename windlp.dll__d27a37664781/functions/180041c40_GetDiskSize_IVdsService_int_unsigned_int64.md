# GetDiskSize(IVdsService *,int,unsigned __int64 *)

- ea: `0x180041c40`
- end: `0x180041d91`
- name: `?GetDiskSize@@YAJPEAUIVdsService@@HPEA_K@Z`
- size: `337`
- prototype: `__int64 __fastcall(struct IVdsService *, int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800244d4`

## callees

- `0x1800417a8`
- `0x180041c40`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041d4e`

## pseudocode

```c
__int64 __fastcall GetDiskSize(struct IVdsService *a1, int a2, unsigned __int64 *a3)
{
  int Disk; // edi
  struct IVdsDisk *v5; // rbx
  void *v6; // rcx
  struct IVdsDisk *v8; // [rsp+30h] [rbp-59h] BYREF
  int v9; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v10[36]; // [rsp+44h] [rbp-45h] BYREF
  unsigned __int64 v11; // [rsp+68h] [rbp-21h]
  LPVOID pv; // [rsp+98h] [rbp+Fh]
  LPVOID v13; // [rsp+A0h] [rbp+17h]
  LPVOID v14; // [rsp+A8h] [rbp+1Fh]
  LPVOID v15; // [rsp+B0h] [rbp+27h]
  LPVOID v16; // [rsp+B8h] [rbp+2Fh]

  v8 = 0;
  if ( a1 && a2 >= 0 && a3 )
  {
    Disk = GetDisk(a1, a2, &v8, 0, 0);
    if ( Disk >= 0 )
    {
      v5 = v8;
      if ( !v8 )
        return (unsigned int)Disk;
      v9 = 0;
      memset_0(v10, 0, 0x7Cu);
      Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, int *))v5->lpVtbl->GetProperties)(v5, &v9);
      if ( Disk >= 0 )
      {
        v6 = pv;
        *a3 = v11;
        if ( v6 )
        {
          CoTaskMemFree(v6);
          pv = 0;
        }
        if ( v13 )
        {
          CoTaskMemFree(v13);
          v13 = 0;
        }
        if ( v14 )
        {
          CoTaskMemFree(v14);
          v14 = 0;
        }
        if ( v15 )
        {
          CoTaskMemFree(v15);
          v15 = 0;
        }
        if ( v16 )
          CoTaskMemFree(v16);
      }
    }
    if ( v8 )
      ((void (__fastcall *)(struct IVdsDisk *))v8->lpVtbl->Release)(v8);
    return (unsigned int)Disk;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180041c40  mov     [rsp-8+arg_18], rbx
0x180041c45  push    rbp
0x180041c46  push    rsi
0x180041c47  push    rdi
0x180041c48  lea     rbp, [rsp-47h]
0x180041c4d  sub     rsp, 0D0h
0x180041c54  mov     rax, cs:__security_cookie
0x180041c5b  xor     rax, rsp
0x180041c5e  mov     [rbp+57h+var_20], rax
0x180041c62  mov     [rbp+57h+var_B0], 0
0x180041c6a  mov     rsi, r8
0x180041c6d  test    rcx, rcx
0x180041c70  jz      loc_180041D6D
0x180041c76  test    edx, edx
0x180041c78  js      loc_180041D6D
0x180041c7e  test    r8, r8
0x180041c81  jz      loc_180041D6D
0x180041c87  xor     r9d, r9d; struct IVdsAdvancedDisk **
0x180041c8a  mov     [rsp+0E0h+var_C0], 0; struct IVdsAdvancedDisk2 **
0x180041c93  lea     r8, [rbp+57h+var_B0]; struct IVdsDisk **
0x180041c97  call    ?GetDisk@@YAJPEAUIVdsService@@HPEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@PEAPEAUIVdsAdvancedDisk2@@@Z; GetDisk(IVdsService *,int,IVdsDisk * *,IVdsAdvancedDisk * *,IVdsAdvancedDisk2 * *)
0x180041c9c  mov     edi, eax
0x180041c9e  test    eax, eax
0x180041ca0  js      loc_180041D54
0x180041ca6  mov     rbx, [rbp+57h+var_B0]
0x180041caa  test    rbx, rbx
0x180041cad  jz      loc_180041D69
0x180041cb3  xor     edx, edx; Val
0x180041cb5  mov     [rbp+57h+var_A0], 0
0x180041cbc  lea     rcx, [rbp+57h+var_9C]; void *
0x180041cc0  lea     r8d, [rdx+7Ch]; Size
0x180041cc4  call    memset_0
0x180041cc9  mov     rax, [rbx]
0x180041ccc  lea     rdx, [rbp+57h+var_A0]
0x180041cd0  mov     rcx, rbx
0x180041cd3  mov     rax, [rax+18h]
0x180041cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041cdc  mov     edi, eax
0x180041cde  test    eax, eax
0x180041ce0  js      short loc_180041D54
0x180041ce2  mov     rcx, [rbp+57h+pv]; pv
0x180041ce6  mov     rax, [rbp+57h+var_78]
0x180041cea  mov     [rsi], rax
0x180041ced  test    rcx, rcx
0x180041cf0  jz      short loc_180041D00
0x180041cf2  call    cs:__imp_CoTaskMemFree
0x180041cf8  mov     [rbp+57h+pv], 0
0x180041d00  mov     rcx, [rbp+57h+var_40]; pv
0x180041d04  test    rcx, rcx
0x180041d07  jz      short loc_180041D17
0x180041d09  call    cs:__imp_CoTaskMemFree
0x180041d0f  mov     [rbp+57h+var_40], 0
0x180041d17  mov     rcx, [rbp+57h+var_38]; pv
0x180041d1b  test    rcx, rcx
0x180041d1e  jz      short loc_180041D2E
0x180041d20  call    cs:__imp_CoTaskMemFree
0x180041d26  mov     [rbp+57h+var_38], 0
0x180041d2e  mov     rcx, [rbp+57h+var_30]; pv
0x180041d32  test    rcx, rcx
0x180041d35  jz      short loc_180041D45
0x180041d37  call    cs:__imp_CoTaskMemFree
0x180041d3d  mov     [rbp+57h+var_30], 0
0x180041d45  mov     rcx, [rbp+57h+var_28]; pv
0x180041d49  test    rcx, rcx
0x180041d4c  jz      short loc_180041D54
0x180041d4e  call    cs:__imp_CoTaskMemFree
0x180041d54  mov     rcx, [rbp+57h+var_B0]
0x180041d58  test    rcx, rcx
0x180041d5b  jz      short loc_180041D69
0x180041d5d  mov     rax, [rcx]
0x180041d60  mov     rax, [rax+10h]
0x180041d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d69  mov     eax, edi
0x180041d6b  jmp     short loc_180041D72
0x180041d6d  mov     eax, 80070057h
0x180041d72  mov     rcx, [rbp+57h+var_20]
0x180041d76  xor     rcx, rsp; StackCookie
0x180041d79  call    __security_check_cookie
0x180041d7e  mov     rbx, [rsp+0E0h+arg_18]
0x180041d86  add     rsp, 0D0h
0x180041d8d  pop     rdi
0x180041d8e  pop     rsi
0x180041d8f  pop     rbp
0x180041d90  retn
```
